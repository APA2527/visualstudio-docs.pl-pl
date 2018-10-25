---
title: Projektant przepływu pracy — FlowSwitch<T> Projektant działań
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Core.Presentation.FlowSwitchLink.UI
- System.Activities.Statements.FlowSwitch`1.UI
- System.Activities.Core.Presentation.FlowSwitchLink`1.UI
- System.Activities.Core.Presentation.FlowSwitchLinkIdentifier.UI
ms.assetid: 5b9c5afe-7499-4ee8-8c33-28aff14bde07
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 783f3101f567f5fe45a1de24a8dad866ea619a39
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49848136"
---
# <a name="flowswitcht-activity-designer"></a>FlowSwitch\<T > Projektant działań

<xref:System.Activities.Statements.FlowSwitch%601> Działanie jest warunkowego węzeł, który zapewnia rozgałęzianie przepływ kontroli w oparciu o kryterium dopasowywania, gdy więcej niż dwie gałęzie alternatywne są wymagane. Jeśli rozgałęzianie przepływów wymaga tylko dwóch ścieżek, należy użyć <xref:System.Activities.Statements.FlowDecision> działania zamiast tego.

## <a name="the-flowswitcht-activity"></a>FlowSwitch\<T > działania

<xref:System.Activities.Statements.FlowSwitch%601> Zawiera działanie <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> zwracającego wartość typu *T* (określonego przez parametr ogólny) podczas oceny. Działanie zawiera także zestaw <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>, który określa unikatowy mapowanie możliwe wyniki tej oceny do zestawu <xref:System.Activities.Statements.FlowNode> obiektów. <xref:System.Activities.Statements.FlowNode> Wykonywany jest ten, którego obiekt typu *T* dopasowuje wartość wyliczana <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>. A <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> przypadek (opcjonalnie) można podać w przypadku, w którym są uzyskiwane Brak dopasowania.

### <a name="using-the-flowswitcht-activity-designer"></a>Za pomocą FlowSwitch\<T > Projektant działań

**FlowSwitch\<T >** projektanta działań można znaleźć w **schemat blokowy** kategorii **przybornika**, które jest dostępne po kliknięciu **Przybornika** karty w lewej części projektanta przepływów pracy. Można także wybrać **przybornika** z **widoku** menu lub naciśnij klawisz **Ctrl**+**Alt** + **X**.

**FlowSwitch\<T >** projektanta działań mogą być przeciągnięte z **przybornika** i porzucić do powierzchni projektanta przepływów pracy w ramach **schemat blokowy** Projektant działań. Użyj **wybierz typy** okno, które wyświetla, aby określić typ (skojarzonych w kodzie za pomocą <xref:System.Activities.Statements.FlowSwitch%601> przez jego parametr ogólny) uzyskany z oceny <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>. Ta procedura powoduje utworzenie <xref:System.Activities.Statements.FlowSwitch%601> działania etykietą **przełącznika** w ramach <xref:System.Activities.Statements.Flowchart> działania. <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> Można wpisać w **wyrażenie** pole **właściwości** , klikając pozycję okna, gdy tekst wskazówki jest wyświetlany komunikat "Wprowadź wyrażenie VB".

Wskaźnik myszy nad **FlowSwitch\<T >** projektanta działań, aby spowodować kwadratowe uchwyty, które są używane do łączenia <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> wokół jego krawędzi. Po przeciągnięciu **FlowSwitch < T\>**  projektanta działań i innych projektantów działań na **schemat blokowy**, <xref:System.Activities.Activity> obiekty, które reprezentują one gotowe ze sobą powiązane Aby określić kolejność wykonywania. Utworzenie jednego z <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> skojarzone z <xref:System.Activities.Statements.FlowSwitch%601>, kliknij jeden z uchwytów kwadratu przypadków, w obwodzie **FlowSwitch < T\>**  i przeciągnij go (na przykład, przytrzymując przycisk myszy) na jeden z uchwytów który pojawia się w podobny sposób na działanie docelowe po wskaźnika myszy nad swojego projektanta. Zwolnij przycisk myszy i Strzałka z **FlowSwitch < T\>**  projektanta docelowego pojawia się reprezentujący ten przypadek. Wartość domyślna dla tego przypadku wyświetla na strzałkę i można je edytować w **przypadek** pole **właściwości** okna.

### <a name="the-flowswitcht-properties"></a>FlowSwitch\<T > Właściwości

W poniższej tabeli przedstawiono <xref:System.Activities.Statements.FlowSwitch%601> właściwości i w tym artykule opisano, jak są używane w projektancie. Te właściwości można edytować w siatce właściwości lub na powierzchni projektowej.

|Nazwa właściwości|Wymagane|Użycie|
|-|--------------|-|
|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>|True|Określa wyrażenie, które jest obliczane, aby określić, które <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> Aby przełączyć się do ścieżki wykonywania.|
|<xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>|False|Określa unikatowy mapowanie możliwe wyniki uzyskane z oceny <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> do zestawu <xref:System.Activities.Statements.FlowNode> obiektów.|
|<xref:System.Activities.Statements.FlowSwitch%601.Default%2A>|True|Określa mapowanie podczas obliczania <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> nie pasuje do jednej wartości zawartych w <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> obiektu.|

## <a name="see-also"></a>Zobacz także

- [Schemat blokowy](../workflow-designer/flowchart-activity-designers.md)
- [Schemat blokowy](../workflow-designer/flowchart-activity-designer.md)
- [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)