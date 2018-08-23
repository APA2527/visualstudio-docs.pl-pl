---
title: 'Porady: zmiana między notacją składowych i notacją skojarzeń (Projektant klas) | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- notation, member
- association notation
- member notation
- notation, association
ms.assetid: 65881c5a-d251-4a36-ad0d-73d088436092
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0659d024f74f154811c51248d523b8826824431f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42679016"
---
# <a name="how-to-change-between-member-notation-and-association-notation-class-designer"></a>Porady: zmiana pomiędzy notacją członka i skojarzeniem notacji (Projektant klas)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [porady: zmiana między notacją składowych i notacją skojarzeń (Projektant klas)](https://docs.microsoft.com/visualstudio/ide/how-to-change-between-member-notation-and-association-notation-class-designer).  
  
W Projektancie klas możesz zmienić sposób diagram klas reprezentuje relacja skojarzenia między dwoma typami z notacją składowych notacją skojarzeń i na odwrót. Składowe wyświetlane jako linie asocjacji często zawierają użyteczne wizualizację jak typy są powiązane.  
  
> [!NOTE]
>  Skojarzenie relacji może być reprezentowana jako właściwość składowej lub pola. Aby zmienić notacją składowych notacją skojarzeń, jeden typ musi mieć członkiem innego typu. Aby zmienić notacją skojarzeń notacją składowych, dwa typy muszą być podłączone przez linia skojarzenia. Aby uzyskać więcej informacji, zobacz [porady: Tworzenie skojarzeń między typami (Projektant klas)](../ide/how-to-create-associations-between-types-class-designer.md). Jeśli projekt zawiera wiele diagramów klas, zmiany wprowadzone w sposób skojarzenia relacje są wyświetlane na diagramie wpływa na tylko tego diagramu. Aby zmienić sposób innego diagramu zawiera relacje skojarzenia, Otwórz lub wyświetlania tego diagramu i wykonaj następujące kroki.  
  
### <a name="to-change-member-notation-to-association-notation"></a>Aby zmienić notacją składowych i notacją skojarzeń  
  
1.  W węźle projektu w Eksploratorze rozwiązań Otwórz plik diagramu klasy (.cd).  
  
2.  Typ kształtu na diagramie klas, kliknij prawym przyciskiem myszy właściwość element członkowski lub pole reprezentujący skojarzenie, a następnie wybierz **wyświetlić jako skojarzenie**.  
  
    > [!TIP]
    >  Jeśli nie właściwości lub pola są widoczne w kształcie typu, mogą być zwinięte przedziałów w kształcie. Aby rozwinąć kształt typu, kliknij dwukrotnie nazwę przedziału lub kliknij prawym przyciskiem myszy kształt typu, a wybierz **rozwiń**.  
  
     Element członkowski znika z przedziału w kształcie typu, a linia skojarzenia pojawi się połączyć z dwóch typów. Linia skojarzenia ma etykietę o nazwie właściwości lub pola.  
  
### <a name="to-change-association-notation-to-member-notation"></a>Aby zmienić notacją skojarzeń notacją składowych  
  
-   Na diagramie klas kliknij prawym przyciskiem myszy linia skojarzenia, a następnie wybierz **Pokaż jako właściwość** lub **Pokaż jako pole** odpowiednio.  
  
     Linia asocjacji znika, i właściwość pojawią się w odpowiednich przedziału w ramach jego kształt typu na diagramie.  
  
## <a name="see-also"></a>Zobacz też  
 [Porady: Tworzenie dziedziczenia między typami (Projektant klas)](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [Porady: wyświetlanie dziedziczenia pomiędzy typami (Projektant klas)](../ide/how-to-view-inheritance-between-types-class-designer.md)   
 [Wyświetlanie typów i relacji (Projektant klas)](../ide/viewing-types-and-relationships-class-designer.md)   
 [Instrukcje: Wizualizacja skojarzenia kolekcji (Projektant klas)](../ide/how-to-visualize-a-collection-association-class-designer.md)



