---
title: Projektant przepływu pracy — Projektant działań w sekwencji
description: Dowiedz się, jak działanie sekwencji zawiera uporządkowaną kolekcję działań podrzędnych wykonywanych w określonej kolejności.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Sequence.UI
ms.assetid: 51c8d3cb-4d43-458f-9631-b63755f9ac94
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b9e7e6e9114405bc1575e0256dd63211a4fb6d08
ms.sourcegitcommit: ed26b6e313b766c4d92764c303954e2385c6693e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94433976"
---
# <a name="sequence-activity-designer"></a>Sequence, projektant działań

<xref:System.Activities.Statements.Sequence>Działanie zawiera uporządkowaną kolekcję działań podrzędnych wykonywanych w określonej kolejności.

Innym sposobem wykonania zestawu działań jest użycie <xref:System.Activities.Statements.Flowchart> działania. Należy rozważyć użycie [schematu blokowego](../workflow-designer/flowchart-activity-designer.md) , gdy istnieje prosty przepływ programu rozgałęziania lub zapętlenia, który ma być modelem diagrammatically.

## <a name="using-the-sequence-activity-designer"></a>Korzystanie z projektanta działania sekwencji

Aby dodać <xref:System.Activities.Statements.Sequence> działanie, przeciągnij projektanta działania **sekwencji** z **przybornika** i upuść go na powierzchnię Projektant przepływu pracy. Aby dodać działanie podrzędne do tego <xref:System.Activities.Statements.Sequence> działania, przeciągnij inne działanie z **przybornika** i upuść je na Trójkącie w polu zawierającym tekst wskazówki "upuść działanie tutaj".

### <a name="sequence-activity-properties-in-the-workflow-designer"></a>Właściwości działania sekwencji w Projektant przepływu pracy

W poniższej tabeli przedstawiono <xref:System.Activities.Statements.Sequence> właściwości i opisano sposób ich użycia w projektancie. Te właściwości można edytować w siatce właściwości lub na powierzchni projektanta.

|Nazwa właściwości|Wymagany|Użycie|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|Fałsz|Określa przyjazną nazwę <xref:System.Activities.Statements.Sequence> projektanta działań w nagłówku. Wartość domyślna to Sequence. Wartość można edytować w siatce właściwości lub bezpośrednio w nagłówku projektanta działań.<br /><br /> Chociaż <xref:System.Activities.Activity.DisplayName%2A> nie jest to ściśle wymagane, najlepszym rozwiązaniem jest użycie jednego z nich.|

## <a name="see-also"></a>Zobacz też

- [Schemat blokowy](../workflow-designer/flowchart-activity-designer.md)
- [Przepływ sterowania](../workflow-designer/control-flow-activity-designers.md)