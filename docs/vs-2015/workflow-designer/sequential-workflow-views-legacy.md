---
title: Widoki sekwencyjnego przepływu pracy (starsza wersja) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- sequential workflow views
- sequential workflows, views
ms.assetid: 135f24b9-1b37-442b-9ef8-f0f2108a3212
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 46c37ec7f3813078b9e70076bf92e6d0e1b86453
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692383"
---
# <a name="sequential-workflow-views-legacy"></a>Widoki sekwencyjnego przepływu pracy (starsza wersja)
[!INCLUDE[vs2010](../includes/vs2010-md.md)] udostępnia starszej [!INCLUDE[wfd1](../includes/wfd1-md.md)] mogą służyć do obiektu docelowego [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] lub [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 [!INCLUDE[wfd2](../includes/wfd2-md.md)] Zapewnia sposób graficznie tworzyć [!INCLUDE[wf](../includes/wf-md.md)] aplikacji przy użyciu znanej [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] interfejsu użytkownika. [!INCLUDE[wf](../includes/wf-md.md)] aplikacje składają się z listą kroków procesu przepływu pracy nazywane działaniami. Aby utworzyć przepływ pracy, tworzą działań na powierzchni projektowej przez przeciąganie ich projektanci odpowiednich działań z **przybornika** na powierzchnię projektu.  
  
 Po utworzeniu sekwencyjnego przepływu pracy, który jest [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040), dostępne są trzy widoki przepływu pracy. Widoki te są dostępne z **przepływu pracy** menu i z menu kontekstowego na powierzchni projektowej.  
  
 Poniższa lista zawiera nazwę i opis każdego widoku.  
  
|Opcja menu, karta|Opis|  
|----------------------|-----------------|  
|**Wyświetl sekwencyjnego przepływu pracy**|Kliknij prawym przyciskiem myszy projekt powierzchni i wybierz **sekwencyjnego przepływu pracy Wyświetl** opcję z menu kontekstowego, aby wyświetlić **sekwencyjnego przepływu pracy** widoku, który zawiera działania oparte na graficznym Reprezentacja sekwencyjnego przepływu pracy. Lub wybierz **sekwencyjnego przepływu pracy Wyświetl** z **przepływu pracy** menu.|  
|**Wyświetl obsługę operacji anulowania**|Kliknij prawym przyciskiem myszy projekt powierzchni i wybierz **widoku anulowania obsługi** opcję z menu kontekstowego, aby wyświetlić **sekwencyjnego przepływu pracy** wyświetlić, który pokazuje [aktivity typu CancellationHandlerActivity ](http://go.microsoft.com/fwlink?LinkID=65050) działanie skojarzone z przepływem pracy. Lub wybierz **widoku anulowania obsługi** z **przepływu pracy** menu.|  
|**Obsługa błędów widoku**|Kliknij prawym przyciskiem myszy projekt powierzchni i wybierz **obsługi błędów w widoku** opcję z menu kontekstowego, aby wyświetlić **błędów** wyświetlić, który pokazuje [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) działania związane z przepływem pracy. Lub wybierz **obsługi błędów w widoku** z **przepływu pracy** menu.|  
  
 Aby uzyskać więcej informacji na temat podobne widoki zobacz [widoki działania (starsza wersja)](../workflow-designer/activity-views-legacy.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Widoki działania (starsza wersja)](../workflow-designer/activity-views-legacy.md)   
 [Tworzenie starszej wersji projektów przepływu pracy](../workflow-designer/creating-legacy-workflow-projects.md)   
 [Trybów tworzenia przepływu pracy](http://go.microsoft.com/fwlink?LinkID=65014)