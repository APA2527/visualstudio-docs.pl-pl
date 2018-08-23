---
title: 'Porady: Określanie alternatywnej lokalizacji aktualizacji wdrażania | Dokumentacja firmy Microsoft'
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
- ClickOnce deployment, updates
- deployment update, alternative locations
ms.assetid: 7faacd35-2638-492d-80f6-6b57e5f820de
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: a0db7eddc38a2b2ab3581ba2b1ff04c90e2adb77
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681946"
---
# <a name="how-to-specify-an-alternate-location-for-deployment-updates"></a>Porady: określanie alternatywnej lokalizacji aktualizacji wdrażania
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [porady: Określanie alternatywnej lokalizacji aktualizacji wdrażania](https://docs.microsoft.com/visualstudio/deployment/how-to-specify-an-alternate-location-for-deployment-updates).  
  
Można zainstalować usługi [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikacja początkowo z dysku CD lub udział plików, ale aplikacja musi sprawdzić okresowe aktualizacje w sieci Web. Tak, aby aplikacja może automatycznie zaktualizowana z sieci Web po jego wstępnej instalacji, można określić alternatywną lokalizację aktualizacji w manifeście wdrożenia.  
  
> [!NOTE]
>  Twoja aplikacja musi być skonfigurowana do zainstalowania lokalnie, aby użyć tej funkcji. Aby uzyskać więcej informacji, zobacz [wskazówki: ręczne wdrażanie aplikacji ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Ponadto, jeśli zainstalujesz [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] na ustawienie lokalizacji alternatywnej powoduje, że sieci [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] można użyć tej lokalizacji dla początkowej instalacji i wszystkich kolejnych aktualizacji. Po zainstalowaniu aplikacji w środowisku lokalnym (na przykład z dysku CD), początkowej instalacji odbywa się przy użyciu oryginalnego nośnika, a wszystkie kolejne aktualizacje użyje lokalizacji alternatywnej.  
  
### <a name="specifying-an-alternate-location-for-updates-by-using-mageuiexe-windows-forms-based-utility"></a>Określanie alternatywnej lokalizacji aktualizacji za pomocą MageUI.exe (narzędzie oparte na formularzach Windows)  
  
1.  Otwórz wiersz polecenia w programie .NET Framework i wpisz:  
  
     **mageui.exe**  
  
2.  Na **pliku** menu, wybierz **Otwórz** na otwarcie manifestu wdrażania aplikacji.  
  
3.  Wybierz **opcje wdrażania** kartę.  
  
4.  W polu tekstowym o nazwie **Uruchom lokalizacji**, wprowadź adres URL do katalogu, który będzie zawierać manifest wdrażania aktualizacji aplikacji.  
  
5.  Zapisywanie pliku manifestu wdrożenia.  
  
### <a name="specifying-an-alternate-location-for-updates-by-using-mageexe"></a>Określanie alternatywnej lokalizacji aktualizacji za pomocą Mage.exe  
  
1.  Otwórz wiersz polecenia .NET Framework.  
  
2.  Ustaw lokalizację aktualizacji, używając następującego polecenia. W tym przykładzie **HelloWorld.exe.application** jest ścieżką do Twojego [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] manifest aplikacji, która zawsze ma rozszerzenie .application, i **http://adatum.com/Update/Path** jest adres URL tego [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] będzie szukać aktualizacji aplikacji.  
  
     **Mage — aktualizowanie HelloWorld.exe.application - ProviderUrl http://adatum.com/Update/Path**  
  
3.  Zapisz plik.  
  
    > [!NOTE]
    >  Teraz należy ponownie podpisać plik za pomocą Mage.exe. Aby uzyskać więcej informacji, zobacz [wskazówki: ręczne wdrażanie aplikacji ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="net-framework-security"></a>Zabezpieczenia.NET Framework  
 Jeśli instalowanie aplikacji w trybie offline średnie, takich jak dysk CD, a komputer jest w trybie online [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] najpierw sprawdza ją pod adres URL określony przez `<deploymentProvider>` tag w manifeście wdrożenia, aby ustalić, czy lokalizacji aktualizacji zawiera nowszą wersję aplikacja. Jeśli tak jest, [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] instaluje aplikację bezpośrednio stamtąd, a nie z katalogu instalacji początkowej i środowisko uruchomieniowe języka wspólnego (CLR) określa zaufania aplikacji przy użyciu na poziomie `<deploymentProvider>`. Jeśli komputer jest w trybie offline lub `<deploymentProvider>` jest nieosiągalny, [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] instalacji z dysku CD, a środowisko CLR przyznaje zaufania, w oparciu o punkt instalacji; w przypadku instalacji z dysku CD, oznacza to, Twoja aplikacja otrzyma pełnego zaufania. Wszystkie kolejne aktualizacje będą dziedziczyć ten poziom zaufania.  
  
 Wszystkie [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikacje, które używają `<deploymentProvider>` powinny jawnie deklarować uprawnień potrzebnych w manifeście aplikacji tak, aby aplikacja nie otrzyma różne poziomy zaufania na różnych komputerach.  
  
## <a name="see-also"></a>Zobacz też  
 [Wskazówki: Ręczne wdrażanie aplikacji ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [Manifest wdrażania ClickOnce](../deployment/clickonce-deployment-manifest.md)   
 [Zabezpieczanie aplikacji ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Wybieranie strategii aktualizacji ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)



