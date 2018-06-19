---
title: 'Porady: dostosowywanie diagramów klasy (Projektant klas)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- class diagrams, customizing
- shapes, removing type from class diagrams
- type shapes, removing from class diagrams
- class diagrams, removing type shapes
ms.assetid: e9030aea-c77d-4cc1-b8f6-b6ca469b692d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8ed2a6112d59e5d433201a417d8d85fd6683b36d
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2018
ms.locfileid: "33956760"
---
# <a name="how-to-customize-class-diagrams"></a>Porady: dostosowywanie diagramów klasy

Można zmienić sposób wyświetlania informacji na diagramach klas. Można dostosować cały diagram lub poszczególne typy na powierzchni projektowej.

Na przykład, można dostosować poziom powiększenia całego diagramu klasy, zmienić grupowanie i sortowanie poszczególnych składowych typu, ukrywać lub pokazywać relacje i przenieść pojedyncze typy lub zestawy typów w dowolne miejsce na diagramie.

> [!NOTE]
> Dostosowywanie sposobu wyświetlania kształtów na diagramie nie zmienia podstawowego kodu dla typów reprezentowanych na diagramie.

Sekcje, które zawierają typ elementów członkowskich, takich jak **właściwości** sekcji w klasie, są nazywane przedziałami. Można ukryć lub pokazać poszczególne przedziały i elementy członkowskie typu.

## <a name="zoom-in-and-out-of-the-class-diagram"></a>Powiększanie i pomniejszanie diagramu klasy

1. Otwórz i wybierz plik diagramu klasy w **Projektant klas**.

2. Na **Projektant klas** narzędzi, kliknij przycisk **Powiększ** lub **Pomniejsz** przycisk, aby zmienić poziom powiększenia powierzchni projektanta.

     lub

     Określ konkretną wartość stopnia powiększenia. Można użyć **powiększenie** listy rozwijanej lub wpisz prawidłową powiększenia (prawidłowy zakres to od 10% i 400%).

    > [!NOTE]
    > Zmiana powiększenia nie wpływa na skalę wydruku diagramu klasy.

## <a name="customize-grouping-and-sorting-of-type-members"></a>Dostosowywanie grupowania i sortowania elementów członkowskich typu

1. Otwórz i wybierz plik diagramu klasy w **Projektant klas**.

2. Kliknij prawym przyciskiem myszy pusty obszar na powierzchni projektu, a następnie wskaż **członków grupy**.

3. Wybierz jedną z dostępnych opcji:

    - **Grupuj według rodzaju** oddziela elementy członkowskie typu poszczególnych na listę pogrupowanych właściwości, metody, zdarzeń i pól. Pojedyncze grupy zależą od definicji jednostki: na przykład, klasa nie wyświetli żadnej grupy zdarzeń, jeśli nie istnieją jeszcze żadne zdarzenia zdefiniowane dla tej klasy.

    - **Grupuj według dostępu** modyfikatorów dostępu oddziela elementy członkowskie typu poszczególnych na listę pogrupowanych według elementu członkowskiego. Na przykład, publiczne i prywatne.

    - **Sortuj alfabetycznie** Wyświetla elementy wchodzące w skład jednostki jako jedną listę porządku alfabetycznym. Lista jest sortowana w kolejności rosnącej.

## <a name="hide-compartments-on-a-type"></a>Ukrywanie przedziałów w danym typie

1. Otwórz i wybierz plik diagramu klasy w **Projektant klas**.

2. Kliknij prawym przyciskiem myszy kategorii Członkowskich w typie, który chcesz dostosować (na przykład wybierz **metody** węzła w klasie.

3. Kliknij przycisk **Ukryj przedział**.

     Wybrany przedział znika z kontenera typu.

## <a name="hide-individual-members-on-a-type"></a>Ukrywanie poszczególnych elementów członkowskich w danym typie

1. Otwórz i wybierz plik diagramu klasy w **Projektant klas**.

2. Kliknij prawym przyciskiem myszy element członkowski w typie, który chcesz ukryć.

3. Kliknij przycisk **Ukryj**.

     Wybrany element członkowski znika z kontenera typu.

## <a name="show-hidden-compartments-and-members-on-a-type"></a>Pokazywanie ukrytych przedziałów i elementów członkowskich w danym typie

1. Otwórz i wybierz plik diagramu klasy w **Projektant klas**.

2. Kliknij prawym przyciskiem myszy nazwę typu z ukrytym przedziałem.

3. Kliknij przycisk **Pokaż wszystkie elementy członkowskie**.

     Wszystkie ukryte przedziały i elementy członkowskie pojawiają się w kontenerze typu.

## <a name="hide-relationships"></a>Ukrywanie relacji

1. Otwórz i wybierz plik diagramu klasy w **Projektant klas**.

2. Kliknij prawym przyciskiem myszy linię skojarzenia lub dziedziczenia, którą chcesz ukryć.

3. Kliknij przycisk **Ukryj** linie asocjacji, a następnie kliknij przycisk **Ukryj linii dziedziczenia** linii dziedziczenia.

4. Kliknij przycisk **Pokaż wszystkie elementy członkowskie**.

     Wszystkie ukryte przedziały i elementy członkowskie pojawiają się w kontenerze typu.

## <a name="show-hidden-relationships"></a>Pokazywanie ukrytych relacji

1. Otwórz i wybierz plik diagramu klasy w **Projektant klas**.

2. Kliknij prawym przyciskiem myszy typ z ukrytym skojarzeniem lub dziedziczeniem.

 Kliknij przycisk **Pokaż wszystkie elementy członkowskie** linie asocjacji, a następnie kliknij przycisk **Pokaż klasa podstawowa** lub **Pokaż klas pochodnych** linii dziedziczenia.

## <a name="remove-a-shape-from-a-class-diagram"></a>Usuwanie kształtu z diagramu klasy
Możesz usunąć kształt typu z diagramu klasy bez wpływu na podstawowy kod typu. Usuwanie kształtów typu z diagramu klasy dotyczy tylko tego diagramu: podstawowy kod, który określa typ, i inne diagramy, które wyświetlają typ, nie są modyfikowane.

1. Na diagramie klasy zaznacz kształt typu, który chcesz usunąć z diagramu.

2. Na **Edytuj** menu, wybierz **usunąć z diagramu**.

     Kształt typu i wszystkie linie skojarzeń lub dziedziczenia połączone z kształtem nie są już wyświetlane na diagramie.

## <a name="delete-a-type-shape-and-its-underlying-code"></a>Usuwanie kształtu typu i jego kodu podstawowego

1. Kliknij prawym przyciskiem myszy kształt na powierzchni projektowej.

2. Wybierz **usunąć kod** z menu kontekstowego.

     Kształt zostanie usunięty z diagramu, a jego podstawowy kod zostanie usunięty z projektu.

## <a name="see-also"></a>Zobacz także

- [Praca z diagramami klas](working-with-class-diagrams.md)
- [Porady: zmiana pomiędzy notacją członka i skojarzeniem notacji](how-to-change-between-member-notation-and-association-notation.md)
- [Porady: wyświetlanie istniejących typów](how-to-view-existing-types.md)
- [Wyświetlanie typów i relacji](viewing-types-and-relationships.md)