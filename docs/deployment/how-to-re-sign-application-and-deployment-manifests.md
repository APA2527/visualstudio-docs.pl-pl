---
title: 'Porady: ponowne podpisywanie aplikacji i manifestów wdrożenia | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Office applications, signing manifests
- deploying applications [ClickOnce], signing manifests
- deploying applications, signing manifests
- ClickOnce deployment, signing manifests
- Office development in Visual Studio, signing manifests
ms.assetid: d53bceb9-4d3b-4c22-b909-8f370e7231fb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ba634ffb30d6459c940811f0ea080f8b71a37f34
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-re-sign-application-and-deployment-manifests"></a>Porady: ponowne podpisywanie aplikacji i manifestów wdrożenia
Po wprowadzeniu zmian do właściwości wdrożenia w aplikacji manifestu dla aplikacji formularzy systemu Windows, aplikacje systemu Windows Presentation Foundation (xbap) lub rozwiązań pakietu Office, musisz ponownie zalogować się zarówno aplikacji i manifesty wdrożenia z certyfikat. Ten proces gwarantuje, że zmodyfikowany pliki nie są zainstalowane na komputerach użytkowników końcowych.  
  
 Inny scenariusz, w którym mogą ponownie podpisać manifestów jest, gdy klienci mają do podpisania aplikacji i manifesty wdrożenia z własnych certyfikatów.  
  
## <a name="re-signing-the-application-and-deployment-manifests"></a>Ponowne podpisywanie aplikacji i wdrażania manifestów  
 W tej procedurze założono, że już zostały wprowadzone zmiany do pliku manifestu aplikacji (manifest). Aby uzyskać więcej informacji, zobacz [porady: Zmienianie właściwości wdrożenia](http://msdn.microsoft.com/en-us/66052a3a-8127-4964-8147-2477ef5d1472).  
  
#### <a name="to-re-sign-the-application-and-deployment-manifests-with-mageexe"></a>Do ponownego podpisania aplikacji i wdrażania manifesty z Mage.exe  
  
1.  Otwórz **wiersz polecenia programu Visual Studio** okna.  
  
2.  Przejdź do folderu, który zawiera pliki manifestu, które chcesz zarejestrować.  
  
3.  Wpisz następujące polecenie, aby podpisać plik manifestu aplikacji. Zamień na nazwę pliku manifestu plus rozszerzenie ManifestFileName. Zamień certyfikatu względną lub w pełni kwalifikowana ścieżka pliku certyfikatu i zamienić hasło hasło dla certyfikatu.  
  
    ```  
    mage -sign ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     Na przykład można uruchomić następujące polecenie, aby podpisać manifest aplikacji dodatku, aplikacji formularzy systemu Windows lub aplikacji przeglądarka Windows Presentation Foundation. Certyfikaty tymczasowe utworzone przez program Visual Studio nie są zalecane do wdrożenia w środowisku produkcyjnym.  
  
    ```  
    mage -sign WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -sign ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -sign WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
4.  Wpisz następujące polecenie, aby zaktualizować i podpisać plik manifestu wdrożenia, zastępując nazwy symbolu zastępczego, jak w poprzednim kroku.  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     Na przykład można uruchomić następujące polecenie, aby zaktualizować i podpisać manifest wdrażania dodatek programu Excel, aplikacji formularzy systemu Windows lub aplikacji przeglądarka Windows Presentation Foundation.  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5.  Opcjonalnie skopiować manifest wdrażania głównego (publikowanie\\*appname*.application) do katalogu wdrażania wersji (pliki publish\Application\\*appname*_ *wersji*).  
  
## <a name="updating-and-re-signing-the-application-and-deployment-manifests"></a>Aktualizowanie i ponowne podpisywanie aplikacji i manifestów wdrożenia  
 W tej procedurze założono, że już dokonano zmian w aplikacji (manifest) pliku manifestu, ale istnieją inne pliki, które zostały zaktualizowane. Podczas aktualizacji plików, musisz również zaktualizować wyznaczania wartości skrótu, który reprezentuje plik.  
  
#### <a name="to-update-and-re-sign-the-application-and-deployment-manifests-with-mageexe"></a>Aby zaktualizować i ponowne podpisywanie aplikacji i wdrażania manifesty z Mage.exe  
  
1.  Otwórz **wiersz polecenia programu Visual Studio** okna.  
  
2.  Przejdź do folderu, który zawiera pliki manifestu, które chcesz zarejestrować.  
  
3.  Usuń rozszerzenie pliku .deploy z plików w folderze wyjściowym publikowania.  
  
4.  Wpisz następujące polecenie, aby zaktualizować manifest aplikacji z nowych skrótów do zaktualizowanych plików i podpisać plik manifestu aplikacji. Zamień na nazwę pliku manifestu plus rozszerzenie ManifestFileName. Zamień certyfikatu względną lub w pełni kwalifikowana ścieżka pliku certyfikatu i zamienić hasło hasło dla certyfikatu.  
  
    ```  
    mage -update ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     Na przykład można uruchomić następujące polecenie, aby podpisać manifest aplikacji dodatku, aplikacji formularzy systemu Windows lub aplikacji przeglądarka Windows Presentation Foundation. Certyfikaty tymczasowe utworzone przez program Visual Studio nie są zalecane do wdrożenia w środowisku produkcyjnym.  
  
    ```  
    mage -update WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5.  Wpisz następujące polecenie, aby zaktualizować i podpisać plik manifestu wdrożenia, zastępując nazwy symbolu zastępczego, jak w poprzednim kroku.  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     Na przykład można uruchomić następujące polecenie, aby zaktualizować i podpisać manifest wdrażania dodatek programu Excel, aplikacji formularzy systemu Windows lub aplikacji przeglądarka Windows Presentation Foundation.  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
6.  Dodaj rozszerzenie pliku .deploy z powrotem do plików, z wyjątkiem aplikacji i wdrażania pliki manifestu.  
  
7.  Opcjonalnie skopiować manifest wdrażania głównego (publikowanie\\*appname*.application) do katalogu wdrażania wersji (pliki publish\Application\\*appname*_ *wersji*).  
  
## <a name="see-also"></a>Zobacz też  
 [Zabezpieczanie aplikacji ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpieczenia dostępu kodu dla aplikacji ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce i podpis Authenticode](../deployment/clickonce-and-authenticode.md)   
 [Przegląd wdrażania zaufanych aplikacji](../deployment/trusted-application-deployment-overview.md)   
 [Porady: włączanie ustawień zabezpieczeń technologii ClickOnce](../deployment/how-to-enable-clickonce-security-settings.md)   
 [Porady: ustawienie strefy zabezpieczeń dla aplikacji ClickOnce](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Porady: ustawienie uprawnień niestandardowych dla aplikacji ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Porady: debugowanie aplikacji ClickOnce z ograniczonymi uprawnieniami](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Porady: Dodawanie zaufanego wydawcy do komputera klienckiego dla aplikacji ClickOnce](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [Instrukcje: konfigurowanie funkcji zaufanego monitowania technologii ClickOnce](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)