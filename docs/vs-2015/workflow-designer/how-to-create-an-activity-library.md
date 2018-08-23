---
title: 'Porady: Tworzenie biblioteki działań | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1eeebe74-7303-4345-8a83-fe37a26bc84b
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 8e3579061b65d142fdfb0cc992813ffc45663464
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683156"
---
# <a name="how-to-create-an-activity-library"></a>Porady: Tworzenie biblioteki działań
Działania niestandardowe są używane do modelowania procesów biznesowych w szczególności w przepływie pracy. Szablon Biblioteka działań w [!INCLUDE[vs2010](../includes/vs2010-md.md)] została przekazana do utworzenia takiego działania niestandardowe, które wizualnie za pomocą [!INCLUDE[wfd1](../includes/wfd1-md.md)].  
  
### <a name="to-create-a-workflow-activity-library"></a>Aby utworzyć biblioteki działania przepływu pracy  
  
1.  Rozpocznij [!INCLUDE[vs2010](../includes/vs2010-md.md)].  
  
2.  Na **pliku** menu wskaż **New**, a następnie wybierz pozycję **projektu...** .  
  
     **Nowy projekt** zostanie otwarte okno dialogowe.  
  
3.  W **typów projektów** okienku wybierz **przepływu pracy** albo **Visual C#** projektów lub **języka Visual Basic** grupowania w zależności od usługi Preferencje językowe.  
  
4.  W **szablony** okienku wybierz **Biblioteka działań**.  
  
5.  W **nazwa** polu wpisz opisową nazwę projektu, aby ułatwić identyfikowanie.  
  
6.  W **lokalizacji** , wpisz w katalogu, w którym chcesz zapisać projekt, lub kliknij przycisk **Przeglądaj** można przejść do niego.  
  
7.  W **rozwiązania** polu, wpisz nazwę opisową dla danego rozwiązania, a następnie kliknij przycisk **OK**.  
  
    > [!NOTE]
    >  Jeśli chcesz dodać aplikację konsoli przepływu pracy do istniejącego rozwiązania, otwórz rozwiązanie w [!INCLUDE[vs2010](../includes/vs2010-md.md)], kliknij prawym przyciskiem myszy rozwiązanie w **Eksploratora rozwiązań**i wybierz **Dodaj**, następnie  **Nowy projekt...** Aby otworzyć **nowy projekt** okno dialogowe. Należy postępować zgodnie z powyższym opisem w tej procedurze.  
  
8.  Szablon projektu umożliwia utworzenie definicji działania w XAML. [!INCLUDE[wfd1](../includes/wfd1-md.md)] Otwiera i wyświetla obszar roboczy dla działania niestandardowego.  
  
9. Przeciągnij działanie z **przybornika** do powierzchni projektu, które mają zostać objęte działanie niestandardowe.  
  
    > [!CAUTION]
    >  Tylko jeden element podrzędny działania są dozwolone w treści działanie niestandardowe; jednak działania podrzędne może być złożone działania, takie jak <xref:System.Activities.Statements.Sequence> działania lub <xref:System.Activities.Statements.Flowchart> działania.  
  
## <a name="see-also"></a>Zobacz też  
 [Porady: tworzenie działania](http://msdn.microsoft.com/library/c09b1e99-21b5-4d96-9c04-ec31db3f4436)   
 [Tworzenie projektu przepływu pracy](../workflow-designer/creating-a-workflow-project.md)