---
title: Rejestrowanie i wyrejestrowywanie pakietów VSPackage | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
ms.assetid: e25e7a46-6a55-4726-8def-ca316f553d6b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2075bec37e29359fb9c403f9cb149b70c01845b6
ms.sourcegitcommit: 9571742f4a808c75b1034aa72fc24b54bc50692e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2018
ms.locfileid: "49410991"
---
# <a name="register-and-unregister-vspackages"></a>Rejestrowanie i wyrejestrowywanie pakietów VSPackage
Używanie atrybutów do zarejestrowania pakietu VSPackage, ale  
  
## <a name="register-a-vspackage"></a>Rejestrowanie pakietu VSPackage  
 Atrybuty można użyć do kontrolowania rejestracji zarządzanego pakietów VSPackage. Wszystkie informacje o rejestracji znajduje się w *.pkgdef* pliku. Aby uzyskać więcej informacji na temat rejestracji opartych na plikach, zobacz [narzędzie CreatePkgDef](../extensibility/internals/createpkgdef-utility.md).  
  
 Poniższy kod przedstawia sposób używania atrybutów standardowa rejestracji można zarejestrować usługi pakietu VSPackage.  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("0B81D86C-0A85-4f30-9B26-DD2616447F95")]  
public sealed class BasicPackage : Package  
{
    // ...
}  
```  
  
## <a name="unregister-an-extension"></a>Wyrejestruj rozszerzenia  
 Jeśli zostały eksperymentowanie z dużą liczbą różnych pakietów VSPackage i chcesz je usunąć z doświadczalne wystąpienie, można po prostu uruchomisz **resetowania** polecenia. Wyszukaj **Zresetuj wystąpienie eksperymentalne programu Visual Studio** na stronie początkowej na komputerze lub uruchom następujące polecenie w wierszu polecenia:  
  
```cmd  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe" /Reset /VSInstance=14.0 /RootSuffix=Exp  
```  
  
 Jeśli chcesz odinstalować rozszerzenie, które zainstalowano na rozwój wystąpienia programu Visual Studio, przejdź do strony **narzędzia** > **rozszerzenia i aktualizacje**, znaleźć rozszerzenia, a kliknij  **Odinstaluj**.  
  
 Jeśli jakiegoś powodu żadna z tych metod nie powiedzie się i wyznaczy odinstalować rozszerzenie, można wyrejestrować pakietu VSPackage zestawu z wiersza polecenia w następujący sposób:  
  
```cmd  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\regpkg" /unregister <pathToVSPackage assembly>  
```  
  
<a name="using-a-custom-registration-attribute-to-register-an-extension"></a>  
  
## <a name="use-a-custom-registration-attribute-to-register-an-extension"></a>Użyj atrybutu niestandardowego rejestracji, aby zarejestrować rozszerzenie  
  
W niektórych przypadkach może być konieczne utworzenie nowego atrybutu rejestracji dla rozszerzenia. Można użyć atrybutów rejestracji, aby dodać nowe klucze rejestru lub dodać nowe wartości do istniejących kluczy. Nowy atrybut musi pochodzić od klasy <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute>, i musi ono przesłonić <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register%2A> i <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister%2A> metody.  
  
### <a name="create-a-custom-attribute"></a>Tworzenie atrybutów niestandardowych  
  
Poniższy kod przedstawia sposób tworzenia nowego atrybutu rejestracji.  
  
```csharp  
[AttributeUsage(AttributeTargets.Class, Inherited = true, AllowMultiple = false)]  
public class CustomRegistrationAttribute : RegistrationAttribute  
{  
}  
```  
  
 <xref:System.AttributeUsageAttribute> Na klasy atrybutów służy do określenia elementu programu, (klasy, metody itp.), do którego odnoszą się atrybut, czy może służyć więcej niż jeden raz i czy mogą być dziedziczone.  
  
### <a name="create-a-registry-key"></a>Utwórz klucz rejestru  
  
Poniższy kod powoduje utworzenie niestandardowego atrybutu **niestandardowe** podkluczy klucza dla pakietu VSPackage, który jest rejestrowany.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + @"}\Custom");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
    }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveKey(@"Packages\" + context.ComponentType.GUID + @"}\Custom");  
}  
```  
  
### <a name="create-a-new-value-under-an-existing-registry-key"></a>Utwórz nową wartość istniejącego klucza rejestru  
  
Wartości niestandardowe można dodać do istniejącego klucza. Poniższy kod przedstawia sposób dodawania nowej wartości z kluczem rejestracji pakietu VSPackage.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + "}");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
    }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveValue(@"Packages\" + context.ComponentType.GUID, "NewCustom");  
}  
```
  
## <a name="see-also"></a>Zobacz także  
 [Pakiety VSPackage](../extensibility/internals/vspackages.md)
