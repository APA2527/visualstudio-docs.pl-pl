---
title: While, Projektant działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.While.UI
ms.assetid: ea008091-2e4c-4f64-bfa5-afb919552446
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 529978a9303892aed74a5d490a19b542357303f9
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49263162"
---
# <a name="while-activity-designer"></a>While, projektant działań

<xref:System.Activities.Statements.While> Działanie wykonuje działania zawarte w jego <xref:System.Activities.Statements.While.Body%2A> podczas, gdy określony warunek ma **true**. Zawarte działanie nigdy nie może zostać wykonany. Jeśli chcesz, aby zawarte działanie do wykonania, co najmniej raz, użyj <xref:System.Activities.Statements.DoWhile> działania zamiast tego.

## <a name="while-properties-in-workflow-designer"></a>Podczas gdy właściwości w Projektancie przepływu pracy

W poniższej tabeli przedstawiono najbardziej przydatne <xref:System.Activities.Statements.While> właściwości działania i w tym artykule opisano, jak są używane w projektancie.

|Nazwa właściwości|Wymagane|Użycie|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Określa przyjazną nazwę <xref:System.Activities.Statements.While> projektanta działań w nagłówku. Wartość domyślna to a. Wartość może być edytowana w **właściwości** okna lub bezpośrednio w nagłówku projektanta działań.<br /><br /> Mimo że <xref:System.Activities.Activity.DisplayName%2A> nie jest bezwzględnie konieczne jest najlepszym rozwiązaniem, aby użyć jednego.|
|<xref:System.Activities.Statements.While.Body%2A>|False|Zawiera działanie do wykonania podczas <xref:System.Activities.Statements.While.Condition%2A> daje w wyniku **true**.|
|<xref:System.Activities.Statements.While.Condition%2A>|True|Zawiera [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] wyrażenie, które jest obliczane, aby określić, czy działania w <xref:System.Activities.Statements.While.Body%2A> ma zostać wykonana.|

## <a name="see-also"></a>Zobacz także

- [Przepływ sterowania](../workflow-designer/control-flow-activity-designers.md)
- [DoWhile](../workflow-designer/dowhile-activity-designer.md)