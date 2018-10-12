---
title: Karta klasa, okno dialogowe właściwości | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Window Properties dialog box, Class Tab
ms.assetid: eaec9f07-d580-436d-934d-76c4e59439aa
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 25eddb34038db1bab0f33d33e33301da492d295c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49255375"
---
# <a name="class-tab-window-properties-dialog-box"></a>Karta Klasa, okno dialogowe właściwości okna
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Użyj **klasy** kartę, aby wyświetlić informacje dotyczące klasy wybranego okna. Aby wyświetlić [okno dialogowe właściwości](../debugger/window-properties-dialog-box.md), Przenieś fokus do [widoku Windows](../debugger/windows-view.md) okna. Zaznacz dowolny węzeł okna w drzewie, a następnie wybierz **właściwości** z **widoku** menu.  
  
 Następujące ustawienia są dostępne na **klasy** karty:  
  
|Wpis|Opis|  
|-----------|-----------------|  
|**Nazwa klasy**|Nazwa (lub liczbę porządkową) tej klasy okna.|  
|**Style klasy**|Kombinacja kody stylu klasy.|  
|**Bajty klasy**|Dane aplikacji skojarzonych z tą klasą okna.|  
|**Atom klasy**|Atom klasy zwrócony przez **RegisterClass** wywołania.|  
|**Dojście wystąpienia**|Dojście wystąpienia modułu, który zarejestrował klasy. Uchwyty wystąpienia nie są unikatowe.|  
|**Bajty okna**|Liczba bajtów dodatkowej skojarzony z oknem każdej tej klasy. Znaczenie tych bajtów jest określany przez aplikację. Rozwiń pole listy, aby wyświetlić wartości bajtów w formacie typu DWORD.|  
|**Proces okna**|Bieżący adres **WndProc** funkcji dla systemu windows tej klasy. To różni się od **proces okna** na **ogólne** kartę, jeśli okno jest podklasą klasy.|  
|**Nazwy menu**|Nazwa menu głównego, skojarzony z systemem windows tej klasy ("none" w przypadku menu nie).|  
|**Uchwyt ikony**|Uchwyt ikony, która jest skojarzona z systemem windows tej klasy ("none" w przypadku żadnej ikony).|  
|**Uchwyt kursora**|Dojście do kursora, który jest skojarzony z systemem windows tej klasy ("none" w przypadku brak kursora).|  
|**Pędzel**|Dojście do pędzel tła, skojarzony z systemem windows w tej klasie lub jednego z wstępnie zdefiniowanych kolorów COLOR_ * za malowanie tło okna, ("none" w przypadku brak pędzla).|



