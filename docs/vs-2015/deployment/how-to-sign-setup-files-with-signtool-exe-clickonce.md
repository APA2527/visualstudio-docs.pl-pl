---
title: 'Porady: podpisywanie plików za pomocą SignTool.exe (ClickOnce) konfiguracji | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, signtool.exe
- deploying applications [ClickOnce], re-signing setup.exe
- ClickOnce deployment, signtool.exe
- ClickOnce applications, re-signing setup.exe
- ClickOnce deployment, re-signing setup.exe
ms.assetid: 545a4005-d283-4110-9821-c78a9833c250
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: f6975fb9c3c3e1abeeaebe23b4a85f41833e421e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49179312"
---
# <a name="how-to-sign-setup-files-with-signtoolexe-clickonce"></a>Porady: podpisywanie plików konfiguracji przy użyciu narzędzia SignTool.exe (ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

SignTool.exe służy do podpisywania Instalatora (setup.exe). Ten proces pozwala upewnić się, że zmodyfikowany pliki nie są zainstalowane na komputerach użytkowników końcowych.  
  
 Domyślnie ClickOnce zalogował się manifestów i podpisem program instalacyjny. Jednak jeśli chcesz zmienić parametry Instalatora później, należy zalogować się Instalatora później. Jeśli zmienisz parametry po podpisaniu program instalacyjny, podpis jest uszkodzony.  
  
 Poniższa procedura generuje nieoznaczone manifesty i bez znaku program instalacyjny. Następnie w celu wygenerowania podpisanych manifestów podpisywanie ClickOnce jest włączone w programie Visual Studio. Pozostało program instalacyjny bez znaku, dzięki czemu klient może zarejestrować plik wykonywalny przy użyciu ich własnych certyfikatów.  
  
### <a name="to-generate-an-unsigned-setup-program-and-sign-later"></a>Aby generować niepodpisane program instalacyjny i podpisać później  
  
1.  Na komputerze deweloperskim, należy zainstalować certyfikat, który ma znak manifesty za pomocą.  
  
2.  Wybierz projekt w **Eksploratora rozwiązań**.  
  
3.  Na **projektu** menu, kliknij przycisk *ProjectName* **właściwości**.  
  
4.  W **podpisywanie** strony, wyczyść **Podpisz manifesty ClickOnce**.  
  
5.  W **Publikuj** kliknij **wymagania wstępne**.  
  
6.  Sprawdź, czy wszystkie wymagania wstępne są zaznaczone, a następnie kliknij **OK**.  
  
7.  W **Publikuj** strony, sprawdź ustawienia publikowania, a następnie kliknij przycisk **Publikuj teraz**.  
  
     Rozwiązanie publikuje manifest aplikacji bez znaku, manifest wdrożenia bez znaku, specyficzny dla wersji plików i bez znaku program instalacyjny do publikowania lokalizacji folderu.  
  
8.  W **Publikuj** kliknij **wymagania wstępne**.  
  
9. W **wymagania wstępne** okno dialogowe wyczyść **Utwórz program instalacyjny, aby zainstalować wstępnie wymagane składniki**.  
  
10. W **Publikuj** strony, sprawdź ustawienia publikowania, a następnie kliknij przycisk **Publikuj teraz**.  
  
     Rozwiązanie publikuje manifest podpisaną aplikację, manifest wdrożenia podpisane i specyficzny dla wersji plików do publikowania lokalizacji folderu. Niepodpisane program instalacyjny nie jest zastępowany przez proces publikowania.  
  
11. W lokacji klienta otwórz wiersz polecenia.  
  
12. Przejdź do katalogu, który zawiera plik .exe.  
  
13. Podpisz plik .exe, za pomocą następującego polecenia:  
  
    ```  
    signtool sign /sha1 CertificateHash Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
     Na przykład aby zarejestrować program instalacyjny, użyj jednej z następujących poleceń:  
  
    ```  
    signtool sign /sha1 CCB... Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
## <a name="see-also"></a>Zobacz też  
 [Instrukcje: ponowne podpisywanie aplikacji i manifestów wdrożenia](../deployment/how-to-re-sign-application-and-deployment-manifests.md)



