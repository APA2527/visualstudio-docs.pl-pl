---
title: Widoki działania (starsza wersja) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- activities, activity views
- views, activity
- activity views
ms.assetid: 83dc68cd-2cb2-45c2-9a6e-10d82053171a
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: ef7aaa042ea358ecdf3d45b6ee75dd14cf117a01
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42679631"
---
# <a name="activity-views-legacy"></a>Widoki działania (starsza wersja)
Wiele działań, dostarczone przez [!INCLUDE[wf](../includes/wf-md.md)], które przepływy pracy są składane, zawiera kilka widoków projektu dostępne w starszych [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Podczas przeciągania projektanta działań z **przybornika** na powierzchnię projektu, a następnie zawsze wtedy, gdy działanie zostanie wybrana, można przełączać się między widokami różnorodności przy użyciu **przepływu pracy**menu lub klikając prawym przyciskiem myszy wybrane działanie. Ponadto podczas przesuwania wskaźnika nad nazwa wybranego działania, listy rozwijanej zbiór kart pojawia się której można przełączać się między różnymi widokami.  
  
 Każde działanie ma co najmniej jeden widok; jest to domyślny widok wyświetlany podczas przeciągania projektanta działań z **przybornika** na powierzchnię projektu. Widok domyślny to działanie jest dostępne jako **wyświetlić [Typ działania]** opcji menu i karty, na przykład **widoku równoległe**. Większość działań ma dodatkowe widoki i różnych działań może mieć różne widoki. Na przykład [działania TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093) aktywności zawiera widok wynagrodzenie i [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030) działanie ma zdarzenia widoku. Wiele działań, które są dostarczane z programem Windows Workflow Foundation ma **widoku anulowania obsługi** i **widoku błędów** projektowaniu widoków do widoku [aktivity typu CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) i [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) skojarzonych z nimi.  
  
 Poniższa lista zawiera nazwę i opis każdego widoku.  
  
|Opcja menu, karta|Opis|  
|----------------------|-----------------|  
|**Widok [Typ działania]**|Wybierz tę opcję menu lub kartę, aby wyświetlić domyślne graficzna reprezentacja wybranego działania.|  
|**Wyświetl obsługę operacji anulowania**|Wybierz tę opcję menu lub karta widokami [aktivity typu CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) skojarzone z wybranego działania.|  
|**Obsługa błędów widoku**|Wybierz tę opcję menu lub karta widokami [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) skojarzone z wybranego działania.|  
|**Wyświetl procedurę obsługi**|Wybierz tę opcję menu lub karta widokami [CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65053) skojarzonych z wybranym [działania TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093).|  
|**Program obsługi zdarzeń widoku**|Wybierz tę opcję menu lub karta widokami [działanie EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018) skojarzonych z wybranym [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030).|  
  
 Uzyskać informacji o podobnych widokach, zobacz [sekwencyjne widoków przepływu pracy (starsza wersja)](../workflow-designer/sequential-workflow-views-legacy.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Działania przepływu pracy w starszej wersji](../workflow-designer/legacy-workflow-activities.md)   
 [Widoki sekwencyjnego przepływu pracy (starsza wersja)](../workflow-designer/sequential-workflow-views-legacy.md)