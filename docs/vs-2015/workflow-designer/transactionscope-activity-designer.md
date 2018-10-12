---
title: TransactionScope, Projektant działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TransactionScope.UI
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 5ea9f0860bf1794ff8c5a4824a60b28aefd4c54d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49238488"
---
# <a name="transactionscope-activity-designer"></a>TransactionScope, projektant działań
**TransactionScope** projektanta działań służy do tworzenia i konfigurowania <xref:System.Activities.Statements.TransactionScope> działania.  
  
## <a name="the-transactionscope-activity"></a>Działanie elementu TransactionScope  
 <xref:System.Activities.Statements.TransactionScope> Działanie wykonuje zawarte działanie w ramach jednej transakcji. Zatwierdzenia transakcji, gdy <xref:System.Activities.Statements.TransactionScope.Body%2A> działanie i innych uczestników transakcji zostały ukończone pomyślnie.  
  
### <a name="using-the-transactionscope-activity-designer"></a>Za pomocą TransactionScope, Projektant działań  
 **TransactionScope** projektanta działań można znaleźć w **transakcji** kategorii **przybornika**, które jest dostępne po kliknięciu **przybornika**  karcie [!INCLUDE[wfd2](../includes/wfd2-md.md)] (można także wybrać **narzędzi** z **widoku** menu lub klawiszy CTRL + ALT + X.)  
  
 **TransactionScope** projektanta działań mogą być przeciągnięte z **przybornika** i porzuconych do [!INCLUDE[wfd2](../includes/wfd2-md.md)] powierzchni wszędzie tam, gdzie działań są zwyczajowo umieszczane, takie jak wewnątrz <xref:System.Activities.Statements.Sequence>. Spowoduje to utworzenie <xref:System.Activities.Statements.TransactionScope> działanie przy użyciu domyślnego <xref:System.Activities.Activity.DisplayName%2A> elementu TransactionScope. <xref:System.Activities.Activity.DisplayName%2A> Wartość może być edytowana w nagłówku **TransactionScope** projektanta działań lub **DisplayName** pola siatki właściwości.  
  
### <a name="the-transactionscope-properties"></a>Właściwości elementu TransactionScope  
 W poniższej tabeli przedstawiono <xref:System.Activities.Statements.TransactionScope> właściwości i w tym artykule opisano, jak są używane w projektancie. <xref:System.Activities.Activity.DisplayName%2A> i <xref:System.Activities.Statements.TransactionScope.Body%2A> właściwości można edytować na [!INCLUDE[wfd2](../includes/wfd2-md.md)] powierzchni. Ale inne właściwości, należy edytować w siatce właściwości.  
  
|Nazwa właściwości|Wymagane|Użycie|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Opcjonalna nazwa przyjazna <xref:System.Activities.Statements.TransactionScope> działania. Wartość domyślna to TransactionScope. Mimo że <xref:System.Activities.Activity.DisplayName%2A> wartość nie jest bezwzględnie konieczne, jest najlepszym rozwiązaniem, aby użyć jednego.|  
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|True|Określa działanie do wykonania w ramach jednej transakcji. Można dodać <xref:System.Activities.Statements.TransactionScope.Body%2A> działania, listy działanie z **przybornika** do **treści** polu na **TransactionScope** projektanta działań z tekst wskazówki "listy działanie w tym miejscu".|  
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|True|Określa <xref:System.Transactions.IsolationLevel> tego <xref:System.Activities.Statements.TransactionScope>.|  
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|Określa przedział czasu (w formacie 00:00:00, co oznacza godziny: minuty: sekundy) zawierającej transakcji zakończyć. Wartość domyślna to 1 minuta (00: 01:00).|  
|<xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure?qualifyHint=False&autoUpgrade=True>|True|Określa wartość, która wskazuje, czy przepływ pracy powinien przerwane w przypadku transakcji przerywa.|  
  
## <a name="see-also"></a>Zobacz też  
 [Transakcji](../workflow-designer/transaction-activity-designers.md)   
 [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)   
 [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Wyrównania](../workflow-designer/compensate-activity-designer.md)   
 [Confirm](../workflow-designer/confirm-activity-designer.md)