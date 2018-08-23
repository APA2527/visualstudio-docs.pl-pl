---
title: 'Porady: uwzględnianie pliku danych w aplikacji ClickOnce | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
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
- ClickOnce deployment, data
- deploying applications [ClickOnce], data files
- data access, ClickOnce applications
ms.assetid: 89ee46ef-bc8c-4ab0-a2ac-1220f9da06fc
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: ee465b3b4524b4f5c530369722f8bdaf36b85227
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692429"
---
# <a name="how-to-include-a-data-file-in-a-clickonce-application"></a>Porady: uwzględnianie pliku danych w aplikacji ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [porady: uwzględnianie pliku danych w aplikacji ClickOnce](https://docs.microsoft.com/visualstudio/deployment/how-to-include-a-data-file-in-a-clickonce-application).  
  
Każdy [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] instalowania aplikacji jest przypisany do katalogu danych na dysku lokalnym komputera docelowego, gdzie aplikacja można zarządzać swoimi danymi. Pliki danych może zawierać pliki dowolnego typu: pliki tekstowe, pliki XML lub nawet Microsoft Access (.mdb) wynoszącego. Poniższe procedury pokazują, jak dodać plik danych dowolnego typu do Twojej [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikacji.  
  
### <a name="to-include-a-data-file-by-using-mageexe"></a>Aby dołączyć plik danych przy użyciu Mage.exe  
  
1.  Dodaj plik danych do katalogu aplikacji z użyciem usług rest plików aplikacji.  
  
     Zazwyczaj będzie katalog etykietą bieżąca wersja wdrożenia katalogu aplikacji — na przykład v1.0.0.0.  
  
2.  Zaktualizuj manifest aplikacji do listy plików danych.  
  
     **mage -u v1.0.0.0\Application.manifest - FromDirectory v1.0.0.0**  
  
     Wykonanie tego zadania ponownie utworzy listę plików w manifeście aplikacji, a także automatycznie wygeneruje sygnatury skrótu.  
  
3.  Otwórz manifest aplikacji w preferowanym tekstu lub edytora XML i Znajdź `file` element ostatnio dodane pliku.  
  
     Jeśli został dodany plik XML o nazwie `Data.xml`, plik będzie wyglądać podobnie jak w poniższym przykładzie kodu.  
  
 `<file name="Data.xml" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`  
  
1.  Dodaj atrybut `type` do tego elementu i dostarczyć wartość `data`.  
  
 `<file name="Data.xml" writeableType="applicationData" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`  
  
1.  Ponownie podpisać manifest aplikacji przy użyciu certyfikatu lub parę kluczy, a następnie ponownie podpisać manifest wdrożenia.  
  
     Należy ponownie podpisać manifest wdrożenia, ponieważ jego skrót manifest aplikacji została zmieniona.  
  
     **app -s mage manifestu - cf cert_file - pwd hasła**  
  
     **mage -u wdrażania manifestu - appm manifestu**  
  
     **manifestu wdrażania -s mage - cf certfile - pwd hasła**  
  
2.  
  
### <a name="to-include-a-data-file-by-using-mageuiexe"></a>Aby dołączyć plik danych przy użyciu MageUI.exe  
  
1.  Dodaj plik danych do katalogu aplikacji z użyciem usług rest plików aplikacji.  
  
2.  Zazwyczaj będzie katalog etykietą bieżąca wersja wdrożenia katalogu aplikacji — na przykład v1.0.0.0.  
  
3.  Na **pliku** menu, kliknij przycisk **Otwórz** otworzyć manifest aplikacji.  
  
4.  Wybierz **pliki** kartę.  
  
5.  W polu tekstowym w górnej części karty wprowadź katalog, który zawiera pliki aplikacji, a następnie kliknij przycisk **wypełniania**.  
  
     Plik danych zostaną wyświetlone w siatce.  
  
6.  Ustaw **typ pliku** wartość plik danych do **danych**.  
  
7.  Zapisz manifest aplikacji, a następnie ponowne podpisywanie pliku.  
  
     MageUI.exe wyświetli monit o ponowne podpisywanie pliku.  
  
8.  Ponownie podpisać manifest wdrożenia  
  
     Należy ponownie podpisać manifest wdrożenia, ponieważ jego skrót manifest aplikacji została zmieniona.  
  
## <a name="see-also"></a>Zobacz też  
 [Uzyskiwanie dostępu do danych lokalnych i zdalnych w aplikacjach ClickOnce](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)



