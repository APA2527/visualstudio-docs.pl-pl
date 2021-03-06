---
title: Projektant przepływu pracy — Potwierdź działanie projektanta działań
description: Dowiedz się więcej o programie Confirming Designer i sposobach tworzenia i konfigurowania działań potwierdzających za pomocą tego projektanta.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Confirm.UI
ms.assetid: c753b67b-b0e7-462a-bb4e-ba8db04a078d
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4928dcd7a9e1b83ba797614545315022d0f36ac3
ms.sourcegitcommit: ed26b6e313b766c4d92764c303954e2385c6693e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94438155"
---
# <a name="confirm-activity-designer"></a>Confirm, projektant działań

Aby utworzyć i skonfigurować działanie, należy użyć programu **confirming** Designer <xref:System.Activities.Statements.Confirm> .

## <a name="the-confirm-activity"></a>Potwierdzenie działania
 <xref:System.Activities.Statements.Confirm>Działanie jawnie wywołuje <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> działanie dla działania zawartego w <xref:System.Activities.Statements.CompensableActivity> . Jeśli <xref:System.Activities.Statements.Confirm> działanie nie jest używane w <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> , <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> , lub, należy <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> <xref:System.Activities.Statements.CompensableActivity> określić <xref:System.Activities.Statements.Confirm.Target%2A> Właściwość.

 <xref:System.Activities.Statements.CompensationToken>Określony przez <xref:System.Activities.Statements.Compensate.Target%2A> zawiera metodę, aby jawnie potwierdzić lub skompensować <xref:System.Activities.Statements.CompensableActivity> po <xref:System.Activities.Statements.CompensableActivity.Body%2A> <xref:System.Activities.Statements.CompensableActivity> pomyślnym zakończeniu.

### <a name="using-the-confirm-activity-designer"></a>Korzystanie z programu Confirme Designer
 Można znaleźć **projektanta działań w** kategorii **transakcji** **przybornika** , do którego uzyskuje się dostęp, klikając kartę **Przybornik** po lewej stronie Projektant przepływu pracy. Alternatywnie możesz wybrać **Przybornik** z menu **Widok** lub nacisnąć **klawisze CTRL** + **Alt** + **X**.

 Można przeciągać **projektanta aktywności z** **przybornika** i znajdować się na Projektant przepływu pracy powierzchni, wszędzie tam, gdzie działania są zwykle umieszczane, na przykład wewnątrz <xref:System.Activities.Statements.Sequence> . Spowoduje to utworzenie <xref:System.Activities.Statements.Confirm> działania z domyślnym <xref:System.Activities.Activity.DisplayName%2A> potwierdzeniem. <xref:System.Activities.Activity.DisplayName%2A>Wartość można edytować w nagłówku programu **Confirmed** Activity Designer lub w polu **DisplayName** siatki właściwości.

### <a name="the-confirm-properties"></a>Potwierdzenie właściwości
 W poniższej tabeli przedstawiono <xref:System.Activities.Statements.Confirm> właściwości i opisano sposób ich użycia w projektancie. <xref:System.Activities.Activity.DisplayName%2A>Właściwość można edytować w siatce właściwości lub na Projektant przepływu pracy powierzchni, ale <xref:System.Activities.Statements.Confirm.Target%2A> Właściwość musi być edytowana w siatce właściwości.

|Nazwa właściwości|Wymagany|Użycie|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|Fałsz|Określa opcjonalną przyjazną nazwę <xref:System.Activities.Statements.CancellationScope> działania. Wartość domyślna to Confirm (Potwierdź).|
|<xref:System.Activities.Statements.Confirm.Target%2A>|Prawda|Określa <xref:System.Activities.InArgument%601> , który zawiera <xref:System.Activities.Statements.CompensationToken> dla tego <xref:System.Activities.Statements.Confirm> działania.|

## <a name="see-also"></a>Zobacz też

- [Transakcja](../workflow-designer/transaction-activity-designers.md)
- [CancellationScope](../workflow-designer/cancellationscope-activity-designer.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Compensate](../workflow-designer/compensate-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)