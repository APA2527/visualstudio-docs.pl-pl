---
title: Projektant przepływu pracy — Assign, Projektant działań
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Assign.UI
ms.assetid: ba3feb3c-f144-47ea-926d-cf752b804153
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 600f38d7bcd387915ba61fc148805705e8609431
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49905259"
---
# <a name="assign-activity-designer"></a>Assign, projektant działań

**Przypisać** projektanta działań służy do tworzenia i konfigurowania <xref:System.Activities.Statements.Assign> działania.

## <a name="the-assign-activity"></a>Przypisywania działania

<xref:System.Activities.Statements.Assign> Działania przypisuje wartość do zmiennej lub argumentu.

### <a name="using-the-assign-activity-designer"></a>Za pomocą Przypisz Projektant działań

**Przypisać** projektanta działań można znaleźć w **podstawowych** kategorii **przybornika**, które jest dostępne po kliknięciu **przybornika**karty (opcjonalnie zaznacz **przybornika** z **widoku** menu lub klawiszy CTRL + ALT + X.)

**Przypisać** projektanta działań mogą być przeciągnięte z **przybornika** i porzucić do powierzchni projektanta przepływów pracy, gdzie odkąd działań są umieszczane, takie jak wewnątrz <xref:System.Activities.Statements.Sequence>. Upuszczanie **przypisać** tworzy Projektant działań <xref:System.Activities.Statements.Assign> działanie przy użyciu domyślnego **DisplayName** z przypisania. <xref:System.Activities.Activity.DisplayName%2A> Mogą być edytowane w nagłówku **przypisać** projektanta działań lub **DisplayName** pola siatki właściwości.

### <a name="the-assign-properties"></a>Przypisz właściwości

W poniższej tabeli przedstawiono <xref:System.Activities.Statements.Assign> właściwości i w tym artykule opisano, jak są używane w projektancie. Te właściwości można edytować w siatce właściwości, a niektóre z nich mogą być edytowane na powierzchni projektanta przepływów pracy.

|Nazwa właściwości|Wymagane|Użycie|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Przyjazna nazwa <xref:System.Activities.Statements.Assign> działania. Wartość domyślna to przypisanie. Mimo że <xref:System.Activities.Activity.DisplayName%2A> wartość nie jest bezwzględnie konieczne, jest najlepszym rozwiązaniem, aby użyć jednego.|
|<xref:System.Activities.Statements.Assign.To%2A>|True|Zmiennej lub argumentu, do którego <xref:System.Activities.Statements.Assign.Value%2A> jest przypisany. Wartość musi być prawidłowym identyfikatorem języka Visual Basic. Aby ustawić właściwości, wpisz wyrażenie języka Visual Basic w **do** polu na **przypisać** działanie projektanta lub w siatce właściwości.|
|<xref:System.Activities.Statements.Assign.Value%2A>|True|Wartość, która jest przypisana do zmiennej. Aby ustawić <xref:System.Activities.Statements.Assign.Value%2A>, wpisz wyrażenie języka Visual Basic w **wartość** polu na **przypisać** działanie projektanta lub w siatce właściwości.|

## <a name="see-also"></a>Zobacz także

- [Typy pierwotne](../workflow-designer/primitives-activity-designers.md)
- [Delay](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)