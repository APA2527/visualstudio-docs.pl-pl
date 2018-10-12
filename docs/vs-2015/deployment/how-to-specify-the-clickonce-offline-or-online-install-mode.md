---
title: 'Porady: Określanie ClickOnce w trybie Offline lub Online instalowania tryb | Dokumentacja firmy Microsoft'
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
- ClickOnce deployment, specifying install mode
- install mode
- online applications
- offline applications
- ClickOnce install mode
ms.assetid: 0aee5fc1-e966-4bda-9b8f-d9997aeaa779
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: b243811f2c6c36266443cd34e0e37ddd01390f87
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49266074"
---
# <a name="how-to-specify-the-clickonce-offline-or-online-install-mode"></a>Porady: określanie trybu offline lub online instalowania za pomocą technologii ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`Install Mode` Dla [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikacji określa, czy aplikacja będzie dostępna w trybie offline lub online. Po wybraniu **aplikacja jest dostępna online tylko**, użytkownik musi mieć dostęp do [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] publikowania lokalizacji (strony sieci Web lub udziału plików) w celu uruchomienia aplikacji. Po wybraniu **aplikacja jest dostępna w trybie offline oraz**, aplikacja dodaje wpisy do **Start** menu i **apletu Dodaj lub usuń programy** okno dialogowe; użytkownik jest można uruchomić aplikację, gdy nie są połączone.  
  
 `Install Mode` Nelze nastavit **Publikuj** strony **projektanta projektu**.  
  
 **Uwaga** `Install Mode` można również ustawić za pomocą Kreatora publikacji. Aby uzyskać więcej informacji, zobacz [porady: publikowanie aplikacji ClickOnce za pomocą Kreatora publikacji](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-make-a-clickonce-application-available-online-only"></a>Aby udostępnić aplikację ClickOnce online tylko  
  
1.  Za pomocą projektu wybranego w **Eksploratora rozwiązań**na **projektu** menu, kliknij przycisk **właściwości**.  
  
2.  Kliknij przycisk **Publikuj** kartę.  
  
3.  W **zainstalować tryb i ustawienia** obszaru, kliknij przycisk **aplikacja jest dostępna online tylko** przycisku opcji.  
  
### <a name="to-make-a-clickonce-application-available-online-or-offline"></a>Aby udostępnić aplikację ClickOnce, online lub offline  
  
1.  Za pomocą projektu wybranego w **Eksploratora rozwiązań**na **projektu** menu, kliknij przycisk **właściwości**.  
  
2.  Kliknij przycisk **Publikuj** kartę.  
  
3.  W **zainstalować tryb i ustawienia** obszaru, kliknij przycisk **aplikacja jest dostępna w trybie offline oraz** przycisku opcji.  
  
     Po zainstalowaniu aplikacji dodaje wpisy do **Start** menu i **apletu Dodaj lub usuń programy** w Panelu sterowania.  
  
## <a name="see-also"></a>Zobacz też  
 [Publikowanie aplikacji ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Porady: publikowanie aplikacji ClickOnce za pomocą Kreatora publikacji](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Wybieranie strategii wdrażania ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)



