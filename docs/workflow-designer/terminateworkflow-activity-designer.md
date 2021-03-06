---
title: TerminateWorkflow, Projektant działań
description: W Projektant przepływu pracy należy dowiedzieć się, jak za pomocą projektanta działań TerminateWorkflow utworzyć i skonfigurować działanie TerminateWorkflow.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 3f37c862768dd0d72ba66d435478faed9bee8ef3
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99931490"
---
# <a name="terminateworkflow-activity-designer"></a>TerminateWorkflow, projektant działań

Projektant działań **TerminateWorkflow** służy do tworzenia i konfigurowania <xref:System.Activities.Statements.TerminateWorkflow> działania.

## <a name="the-terminateworkflow-activity"></a>Działanie TerminateWorkflow

<xref:System.Activities.Statements.TerminateWorkflow>Działanie kończy wykonywanie przepływu pracy.

### <a name="using-the-terminateworkflow-activity-designer"></a>Korzystanie z projektanta działań TerminateWorkflow

Projektanta działań **TerminateWorkflow** można znaleźć w kategorii **środowiska uruchomieniowego** **przybornika**, do którego uzyskuje się dostęp przez kliknięcie karty **przybornika** (można również wybrać **Przybornik** z menu **Widok** lub CTRL + ALT + X).

Projektanta działań **TerminateWorkflow** można przeciągnąć z **przybornika** i porzucić na Projektant przepływu pracy powierzchnię, wszędzie tam, gdzie działania są zwykle umieszczane, na przykład wewnątrz <xref:System.Activities.Statements.Sequence> . Spowoduje to utworzenie <xref:System.Activities.Statements.TerminateWorkflow> działania z domyślną wartością **DisplayName** elementu TerminateWorkflow. <xref:System.Activities.Activity.DisplayName%2A>Można edytować w nagłówku projektanta działań **TerminateWorkflow** lub w polu **DisplayName** siatki właściwości.

### <a name="the-terminateworkflow-properties"></a>Właściwości TerminateWorkflow

W poniższej tabeli przedstawiono <xref:System.Activities.Statements.TerminateWorkflow> właściwości i opisano sposób ich użycia w projektancie. Te właściwości można edytować w siatce właściwości, a niektóre z nich można edytować na Projektant przepływu pracy powierzchni.

|Nazwa właściwości|Wymagany|Użycie|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|Fałsz|Przyjazna nazwa <xref:System.Activities.Statements.TerminateWorkflow> działania. Wartość domyślna to TerminateWorkflow. Chociaż nazwa wyświetlana nie jest ściśle wymagana, najlepszym rozwiązaniem jest użycie nazwy wyświetlanej.|
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|Fałsz|Wyjątek, który należy zgłosić po zakończeniu przepływu pracy. Ustaw tę właściwość w siatce właściwości.|
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|Fałsz|Powód, który wyjaśnia, dlaczego przepływ pracy został zakończony. Ustaw tę właściwość w siatce właściwości.|

## <a name="see-also"></a>Zobacz też

- [Środowisko uruchomieniowe](../workflow-designer/runtime-activity-designers.md)
- [Persist](../workflow-designer/persist-activity-designer.md)
