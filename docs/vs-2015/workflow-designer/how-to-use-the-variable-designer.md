---
title: 'Porady: Używanie projektanta zmiennych | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.DesignTimeVariable.UI
ms.assetid: 0318dfb0-bf8f-4f92-9b86-ae4c1b2161ad
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 2348fbe0ed51f72ee1218f7ed1ed2006a48a124d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49265159"
---
# <a name="how-to-use-the-variable-designer"></a>Porady: Używanie projektanta zmiennych
Projektanta zmiennych służy do tworzenia zmiennych do użytku w scenariuszach powiązanie danych i instrukcji warunkowych. Projektant jest dostępne po kliknięciu **zmienne** przycisku w lewym dolnym rogu obszaru roboczego projektowania. Projektant zawiera listę zmiennych, które są wyświetlane w formie tabelarycznej i mogą być sortowane przez każdy z nagłówków kolumn, z wyjątkiem **domyślne** kolumny. Każda zmienna zawiera nazwę, typ zmiennej, zakresu i wartość domyślną (jeśli istnieje). Nazwa i domyślne wartości są tekst do edycji i typie i zakresie są rozwijane. Zakres jest działania, który został wybrany, gdy wywołano projektanta zmiennych. Jeśli nie można utworzyć zmiennej w zakresie wyboru, zakres będzie domyślnie do najbliższej działania nadrzędnego zaznaczenia, umożliwiający zmiennych, które można utworzyć w swoim zakresie. [!INCLUDE[crabout](../includes/crabout-md.md)] zmienne, zobacz [zmienne i argumenty](http://msdn.microsoft.com/library/d03dbe34-5b2e-4f21-8b57-693ee49611b8).  
  
 Kolejność sortowania nie została zastosowana, dopóki użytkownik jawnie używa sortowania formantów, zostanie zamknięty i ponownie otwiera projektanta zmiennych lub tworzy innej zmiennej.  
  
### <a name="to-create-a-new-variable"></a>Aby utworzyć nową zmienną  
  
1.  Otwórz rozwiązanie przepływu pracy lub działania w [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)].  
  
2.  W obszarze roboczym projektu wybierz działanie w przepływie pracy.  
  
3.  Otwórz projektanta zmiennych, klikając pozycję **zmienne** przycisku w lewym dolnym rogu obszaru roboczego projektowania. Pojawi się projektanta zmiennych.  
  
4.  Kliknij pusty wiersz etykietą **Tworzenie zmiennej**. Spowoduje to dodanie nowego wiersza przy użyciu nowej zmiennej, używając następujących wartości domyślne: variablex dla **nazwa** gdzie x jest liczbą całkowitą o początkowej wartości 1, który jest automatycznie zwiększany w celu tworzenia unikatowych nazw zmiennych,  **Ciąg** dla **typ zmiennej**, i **sekwencji** dla **zakres**. Wartość nie jest dodawany do **domyślne**. Wartości te można zmienić w dowolnym momencie podczas procesu projektowania przepływu pracy.  
  
    > [!NOTE]
    >  Aby usunąć zmienną, wybierz zmienną, klikając go, a następnie naciśnij klawisz **Usuń** klucza.  
  
## <a name="see-also"></a>Zobacz też  
 [Używanie projektanta przepływu pracy](../workflow-designer/using-the-workflow-designer.md)   
 [Zmienne i argumenty](http://msdn.microsoft.com/library/d03dbe34-5b2e-4f21-8b57-693ee49611b8)   
 [Instrukcje: Używanie projektanta argumentów](../workflow-designer/how-to-use-the-argument-designer.md)