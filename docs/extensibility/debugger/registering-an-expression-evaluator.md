---
title: Rejestrowanie ewaluatora wyrażeń | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluators, registering
ms.assetid: 236be234-e05f-4ad8-9200-24ce51768ecf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b3e764220fe5fe01e20b66af403dfd8b423e34e7
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234029"
---
# <a name="registering-an-expression-evaluator"></a>Rejestrowanie ewaluatora wyrażeń
> [!IMPORTANT]
>  W programie Visual Studio 2015 ten sposób wdrażania ewaluatorów wyrażeń jest przestarzały. Aby uzyskać informacje dotyczące wdrożenia ewaluatorów wyrażeń CLR, zobacz [Ewaluatorów wyrażeń CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) i [zarządzane próbki ewaluatora wyrażenia](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Ewaluator wyrażeń (EE) musi zarejestrować się jako fabrykę klas w środowisku COM systemu Windows i programu Visual Studio. EE jest implementowany jako biblioteki DLL, dzięki czemu mogą zostać dodane do przestrzeni adresowej (DE) Aparat debugowania lub przestrzeni adresowej programu Visual Studio, w zależności od tego, która tworzy wystąpienie jednostki EE.  
  
## <a name="managed-code-expression-evaluator"></a>Kod zarządzany Ewaluator wyrażeń  
 Zarządzany kod EE jest zaimplementowany jako biblioteki klas, czyli bibliotekę DLL, która rejestruje się ze środowiskiem COM, zazwyczaj uruchamiane przez wywołanie do programu VSIP **regpkg.exe**. Rzeczywisty proces zapisywania kluczy rejestru dla środowiska COM odbywa się automatycznie.  
  
 Metoda klasy głównym jest oznaczona atrybutem <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>, co oznacza, że metoda jest wywoływana, gdy biblioteka DLL jest rejestrowana z modelu COM. Ta metoda rejestracji, często nazywane `RegisterClass`, wykonuje zadanie rejestrowania biblioteki DLL programu Visual Studio. Odpowiadającego `UnregisterClass` (oznaczone <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>), cofa skutków `RegisterClass` po odinstalowaniu biblioteki DLL.  
  
 Tym samym wpisy rejestru są wprowadzane podobnie jak w przypadku EE zapisywane w niezarządzanym kodzie; Jedyna różnica polega na brak żadnej funkcji pomocnika takich jak `SetEEMetric` które wykonają tę pracę za Ciebie. Przykładem tego procesu rejestracji/wyrejestrowanie wygląda następująco:  
  
### <a name="example"></a>Przykład  
 Ta funkcja pokazuje, jak kod zarządzany EE rejestruje i wyrejestrowuje się z programem Visual Studio.  
  
```csharp  
namespace EEMC  
{  
    [GuidAttribute("462D4A3D-B257-4AEE-97CD-5918C7531757")]  
    public class EEMCClass : IDebugExpressionEvaluator  
    {  
        #region Register and unregister.  
        private static Guid guidMycLang = new Guid("462D4A3E-B257-4AEE-97CD-5918C7531757");  
        private static string languageName = "MyC";  
        private static string eeName = "MyC Expression Evaluator";  
  
        private static Guid guidMicrosoftVendor = new Guid("994B45C4-E6E9-11D2-903F-00C04FA302A1");  
        private static Guid guidCOMPlusOnlyEng = new Guid("449EC4CC-30D2-4032-9256-EE18EB41B62B");  
        private static Guid guidCOMPlusNativeEng = new Guid("92EF0900-2251-11D2-B72E-0000F87572EF");  
  
        /// <summary>  
        /// Register the expression evaluator.  
        /// Set "project properties/configuration properties/build/register for COM interop" to true.  
        /// </summary>  
         [ComRegisterFunctionAttribute]  
        public static void RegisterClass(Type t)  
        {  
            // Get Visual Studio version (set by regpkg.exe)  
            string hive = Environment.GetEnvironmentVariable("EnvSdk_RegKey");  
            string s = @"SOFTWARE\Microsoft\VisualStudio\"  
                        + hive  
                        + @"\AD7Metrics\ExpressionEvaluator";  
  
            RegistryKey rk = Registry.LocalMachine.CreateSubKey(s);  
            if (rk == null)  return;  
  
            rk = rk.CreateSubKey(guidMycLang.ToString("B"));  
            rk = rk.CreateSubKey(guidMicrosoftVendor.ToString("B"));  
            rk.SetValue("CLSID", t.GUID.ToString("B"));  
            rk.SetValue("Language", languageName);  
            rk.SetValue("Name", eeName);  
  
            rk = rk.CreateSubKey("Engine");  
            rk.SetValue("0", guidCOMPlusOnlyEng.ToString("B"));  
            rk.SetValue("1", guidCOMPlusNativeEng.ToString("B"));  
        }  
        /// <summary>  
        /// Unregister the expression evaluator.  
        /// </summary>  
         [ComUnregisterFunctionAttribute]  
        public static void UnregisterClass(Type t)  
        {  
            // Get Visual Studio version (set by regpkg.exe)  
            string hive = Environment.GetEnvironmentVariable("EnvSdk_RegKey");  
            string s = @"SOFTWARE\Microsoft\VisualStudio\"  
                        + hive  
                        + @"\AD7Metrics\ExpressionEvaluator\"  
                        + guidMycLang.ToString("B");  
            RegistryKey key = Registry.LocalMachine.OpenSubKey(s);  
            if (key != null)  
            {  
                key.Close();  
                Registry.LocalMachine.DeleteSubKeyTree(s);  
            }  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code-expression-evaluator"></a>Ewaluatora wyrażenia z kodem niezarządzanym  
 Implementuje EE DLL `DllRegisterServer` funkcji do zarejestrowania się w środowisku COM, jak również Visual Studio.  
  
> [!NOTE]
>  MyCEE kod przykładowy rejestru można znaleźć w dllentry.cpp pliku, który znajduje się w instalacji VSIP w obszarze EnVSDK\MyCPkgs\MyCEE.  
  
### <a name="dll-server-process"></a>Proces serwera biblioteki DLL  
 Podczas rejestrowania EE, serwer biblioteki DLL:  
  
1.  Rejestruje fabrykę jego klasa `CLSID` zgodnie z normalnym konwencje COM.  
  
2.  Wywołuje funkcję Pomocnika `SetEEMetric` zarejestrować za pomocą programu Visual Studio metryki EE pokazano w poniższej tabeli. Funkcja `SetEEMetric` i metryki wymienionymi poniżej są częścią biblioteki dbgmetric.lib. Zobacz [pomocników zestawu SDK dla debugowania](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) szczegółowe informacje.  
  
    |Metryka|Opis|  
    |------------|-----------------|  
    |`metricCLSID`|`CLSID` fabryki klas EE|  
    |`metricName`|Nazwa EE jako ciąg wyświetlanej|  
    |`metricLanguage`|Nazwa języka, który jest EE zaprojektowane do oceny|  
    |`metricEngine`|`GUID`s aparatami debugowania (DE), które współpracują z tym EE|  
  
    > [!NOTE]
    >  `metricLanguage``GUID` Identyfikuje język według nazwy, ale jest `guidLang` argument `SetEEMetric` który wybiera języka. Gdy kompilator generuje pliku informacji o debugowaniu, należy zapisać odpowiednie `guidLang` tak, aby DE wie, które EE do użycia. Niemcy zwykle zapyta dostawcy symboli dla tego języka `GUID`, który jest przechowywany w pliku informacji o debugowaniu.  
  
3.  Rejestruje z programem Visual Studio przez utworzenie kluczy w obszarze HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*X.Y*, gdzie *X.Y* jest wersja programu Visual Studio, aby zarejestrować w usłudze.  
  
### <a name="example"></a>Przykład  
 Ta funkcja pokazuje, jak niezarządzanego kodu (C++) EE rejestruje i wyrejestrowuje się z programem Visual Studio.  
  
```cpp  
/*---------------------------------------------------------  
  Registration  
-----------------------------------------------------------*/  
#ifndef LREGKEY_VISUALSTUDIOROOT  
    #define LREGKEY_VISUALSTUDIOROOT L"Software\\Microsoft\\VisualStudio\\8.0"  
#endif  
  
static HRESULT RegisterMetric( bool registerIt )  
{  
    // check where we should register  
    const ULONG cchBuffer = _MAX_PATH;  
    WCHAR wszRegistrationRoot[cchBuffer];  
    DWORD cchFreeBuffer = cchBuffer - 1;  
    wcscpy(wszRegistrationRoot, LREGKEY_VISUALSTUDIOROOT_NOVERSION);  
    wcscat(wszRegistrationRoot, L"\\");  
  
    // this is Environment SDK specific  
    // we check for  EnvSdk_RegKey environment variable to  
    // determine where to register  
    DWORD cchDefRegRoot = lstrlenW(LREGKEY_VISUALSTUDIOROOT_NOVERSION) + 1;  
    cchFreeBuffer = cchFreeBuffer - cchDefRegRoot;  
    DWORD cchEnvVarRead = GetEnvironmentVariableW(  
        /* LPCTSTR */ L"EnvSdk_RegKey", // environment variable name  
        /* LPTSTR  */ &wszRegistrationRoot[cchDefRegRoot],// buffer for variable value  
        /* DWORD   */ cchFreeBuffer);// size of buffer  
    if (cchEnvVarRead >= cchFreeBuffer)  
        return E_UNEXPECTED;  
    // If the environment variable does not exist then we must use   
    // LREGKEY_VISUALSTUDIOROOT which has the version number.  
    if (0 == cchEnvVarRead)  
        wcscpy(wszRegistrationRoot, LREGKEY_VISUALSTUDIOROOT);  
  
    if (registerIt)  
    {  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricCLSID,  
                    CLSID_MycEE,  
                    wszRegistrationRoot );  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricName,  
                    GetString(IDS_INFO_MYCDESCRIPTION),  
                    wszRegistrationRoot );  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricLanguage, L"MyC",  
                    wszRegistrationRoot);  
  
        GUID engineGuids[2];  
        engineGuids[0] = guidCOMPlusOnlyEng;  
        engineGuids[1] = guidCOMPlusNativeEng;  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricEngine,  
                    engineGuids,  
                    2,  
                    wszRegistrationRoot);  
    }  
    else  
    {  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricCLSID,  
                        wszRegistrationRoot);  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricName,  
                        wszRegistrationRoot );  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricLanguage,  
                        wszRegistrationRoot );  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricEngine,  
                        wszRegistrationRoot );  
    }  
  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Zapisywanie Ewaluator wyrażeń CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Pomocnicy zestawu SDK do debugowania](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)
