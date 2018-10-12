---
title: CompensableActivity, Projektant działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.CompensableActivity.UI
ms.assetid: e0340d89-d39e-4a52-8557-13e27040d7b5
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 670d3e92b24e35979074df3817611ceff692f59d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49290449"
---
# <a name="compensableactivity-activity-designer"></a>CompensableActivity, projektant działań
**CompensableActivity** projektanta działań służy do tworzenia i konfigurowania <xref:System.Activities.Statements.CompensableActivity> działania.  
  
## <a name="the-compensableactivity-activity"></a>Działanie CompensableActivity  
 <xref:System.Activities.Statements.CompensableActivity> Definiuje jednostkę pracy, która potwierdzenia lub płatne po pomyślnym ukończeniu.  
  
### <a name="using-the-compensableactivity-activity-designer"></a>Za pomocą CompensableActivity, Projektant działań  
 **CompensableActivity** projektanta działań można znaleźć w **transakcji** kategorii **przybornika**, które jest dostępne po kliknięciu **przybornika**  karty w lewej części [!INCLUDE[wfd2](../includes/wfd2-md.md)] (można także wybrać **narzędzi** z **widoku** menu lub klawiszy CTRL + ALT + X.)  
  
 **CompensableActivity** projektanta działań mogą być przeciągnięte z **przybornika** i porzuconych do [!INCLUDE[wfd2](../includes/wfd2-md.md)] powierzchni wszędzie tam, gdzie działań są zwyczajowo umieszczane, takie jak wewnątrz <xref:System.Activities.Statements.Sequence>. Spowoduje to utworzenie <xref:System.Activities.Statements.CompensableActivity> działanie przy użyciu domyślnego <xref:System.Activities.Activity.DisplayName%2A> z CompensableActivity. <xref:System.Activities.Activity.DisplayName%2A> Wartość może być edytowana w nagłówku **CompensableActivity** projektanta działań lub **DisplayName** pola siatki właściwości.  
  
### <a name="the-compensableactivity-properties"></a>Właściwości CompensableActivity  
 W poniższej tabeli przedstawiono <xref:System.Activities.Statements.CompensableActivity> właściwości i w tym artykule opisano, jak są używane w projektancie. <xref:System.Activities.Activity.DisplayName%2A> i <xref:System.Activities.Activity%601.Result%2A> właściwości można edytować w siatce właściwości, ale inne właściwości, należy edytować na [!INCLUDE[wfd2](../includes/wfd2-md.md)] powierzchni.  
  
|Nazwa właściwości|Wymagane|Użycie|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Opcjonalna nazwa przyjazna <xref:System.Activities.Statements.CompensableActivity> działania. Wartość domyślna to CompensableActivity.|  
|<xref:System.Activities.Activity%601.Result%2A>|False|Określa wartość zwracaną przez <xref:System.Activities.Statements.CompensableActivity>. Można edytować tej właściwości, w siatce właściwości.|  
|<xref:System.Activities.Statements.CompensableActivity.Body%2A>|True|Określa działania, dla których dostępny jest logiki wynagrodzenie, anulowanie i potwierdzenia. Można dodać <xref:System.Activities.Statements.CompensableActivity.Body%2A> działania, listy działanie z **przybornika** do **treści** polu na **CompensableActivity** projektanta działań z tekst wskazówki "listy działanie tutaj".|  
|<xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>|False|Określa działania, który jest wykonywany w przypadku anulowania. Aby dodać działanie, Porzuć swojego projektanta z **przybornika** do **CancellationHandler** polu na **CompensableActivity** projektanta działań z tekst wskazówki "listy Działanie tutaj".|  
|<xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>|False|Określa działania, które zostaną wykonane podczas kompensowania <xref:System.Activities.Statements.CompensableActivity.Body%2A> działania. Ten program obsługi może być jawnie wywołana, za pomocą <xref:System.Activities.Statements.Compensate> działania.<br /><br /> Aby dodać działanie, Porzuć swojego projektanta działań z **przybornika** do **CompensationHandler** polu na **CompensableActivity** projektanta działań z tekst wskazówki " Upuść działanie tutaj".|  
|<xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>|False|Określa działanie do wykonania podczas potwierdzania <xref:System.Activities.Statements.CompensableActivity.Body%2A> działania. Ten program obsługi może być jawnie wywołana, za pomocą <xref:System.Activities.Statements.Confirm> działania.<br /><br /> Aby dodać działanie, Porzuć swojego projektanta działań z **przybornika** do **ConfirmationHandler** polu na **CompensableActivity** projektanta działań z tekst wskazówki " Upuść działanie tutaj".|  
  
## <a name="see-also"></a>Zobacz też  
 [Transakcji](../workflow-designer/transaction-activity-designers.md)   
 [CancellationScope](../workflow-designer/cancellationscope-activity-designer.md)   
 [Wyrównania](../workflow-designer/compensate-activity-designer.md)   
 [Upewnij się](../workflow-designer/confirm-activity-designer.md)   
 [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)