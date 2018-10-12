---
title: Krok 5. Dodawanie odwołań do etykiet | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d418350c-0396-494e-8149-71fa61b395c5
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 829911bc2f08010b9e0d3d9c710862097720d4df
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49285227"
---
# <a name="step-5-add-label-references"></a>Krok 5. Dodawanie odwołań do etykiet
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Program musi śledzić, które formanty etykiet wybiera gracz. W tej chwili program pokazuje wszystkie etykiety wybrane przez gracza. Ale zaraz to zmienimy. Po wybraniu pierwszej etykiety program powinien wyświetlać ikonę etykiety. Po wybraniu drugiej etykiety program powinien wyświetlić obie ikony przez krótki czas i potem ponownie je ukryć. Program będą teraz przechowywać informacje o który formant etykiety został wybrany jako pierwszy, a który jako drugi przy użyciu *odwoływać się do zmiennych*.  
  
### <a name="to-add-label-references"></a>Aby dodać odwołania do etykiet  
  
1.  Dodaj odwołania do etykiet do formularza przy użyciu następującego kodu.  
  
     [!code-csharp[VbExpressTutorial4Step5#5](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step5/cs/form1.cs#5)]
     [!code-vb[VbExpressTutorial4Step5#5](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step5/vb/form1.vb#5)]  
  
     Te zmienne odwołania wyglądają podobnie do instrukcji było wcześniej używane do dodawania obiektów (takich jak `Timer` obiektów `List` obiekty, i `Random` obiektów) do formularza. Jednakże te instrukcje nie powodują dwa dodatkowe formanty etykiet do wyświetlane w formularzu, ponieważ nie istnieje żadne `new` słowa kluczowego w jednym z dwóch instrukcji. Bez `new` — słowo kluczowe, zostanie utworzony żaden obiekt. Dlatego `firstClicked` i `secondClicked` są nazywane zmiennymi odwołania: one po prostu śledzić (lub odwoływać się do) `Label` obiektów.  
  
     Jeśli zmienna nie jest rejestrowanie informacji o obiekcie, jest ustawiona na specjalną zarezerwowaną wartość: `null` w języku Visual C# i `Nothing` w języku Visual Basic. Tak, po uruchomieniu programu, zarówno `firstClicked` i `secondClicked` są ustawione na `null` lub `Nothing`, co oznacza, że zmienne nie są utrzymywanie o wszystkim.  
  
2.  Zmodyfikuj obsługę zdarzenia Click, aby używała nowej `firstClicked` zmienną odwołania. Usuń ostatnią instrukcję w `label_Click()` metody obsługi zdarzeń (`clickedLabel.ForeColor = Color.Black;`) i zastąp go wartością `if` kolejnej instrukcji. (Należy dołączyć komentarz oraz całą `if` instrukcja.)  
  
     [!code-csharp[VbExpressTutorial4Step5#6](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step5/cs/form1.cs#6)]
     [!code-vb[VbExpressTutorial4Step5#6](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step5/vb/form1.vb#6)]  
  
3.  Zapisz i uruchom program. Wybierz jeden z formantów etykiet, pojawi się jego ikona.  
  
4.  Wybierz następny formant etykiety i zauważ, że nic się nie dzieje. Program jest już rejestrowanie informacji o pierwszą etykietę, którą wybrał gracz, więc `firstClicked` nie jest równa `null` w języku Visual C# lub `Nothing` w języku Visual Basic. Gdy Twoje `if` instrukcji kontroli `firstClicked` do określenia, czy jest równa `null` lub `Nothing`, stwierdzi, że nie jest, a więc nie wykonuje instrukcji w `if` instrukcji. Tak więc, tylko pierwsza wybrana ikona zmienia kolor na czarny, a inne ikony są niewidoczne, jak pokazano na poniższej ilustracji.  
  
     ![Gra w dopasowywanie pokazująca jedną ikonę](../ide/media/express-tut4step5.png "Express_Tut4Step5")  
Gra w dopasowywanie pokazująca jedną ikonę  
  
     Dodając naprawisz tę sytuację w następnym kroku samouczka **czasomierza** kontroli.  
  
### <a name="to-continue-or-review"></a>Aby kontynuować lub przeglądnąć  
  
-   Aby przejść do następnego kroku samouczka, zobacz [krok 6: Dodawanie czasomierza](../ide/step-6-add-a-timer.md).  
  
-   Aby powrócić do poprzedniego kroku samouczka, zobacz [krok 4: Dodawanie obsługi zdarzeń kliknij do każdej etykiety](../ide/step-4-add-a-click-event-handler-to-each-label.md).



