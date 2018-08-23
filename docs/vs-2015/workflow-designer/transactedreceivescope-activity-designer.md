---
title: TransactedReceiveScope, Projektant działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.TransactedReceiveScope.UI
ms.assetid: 7ca93aad-4e83-4d81-90f4-998ee114d9b6
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: a40f29bc9928d354d99be282e5cd4ea32f869270
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632518"
---
# <a name="transactedreceivescope-activity-designer"></a>TransactedReceiveScope, projektant działań
**TransactedReceiveScope** projektanta jest używany do tworzenia i konfigurowania <xref:System.ServiceModel.Activities.TransactedReceiveScope> działania.  
  
## <a name="the-transactedreceivescope-activity"></a>Działanie TransactedReceiveScope  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope> Działanie umożliwia przepływu transakcji na serwerze transakcji utworzone przez przepływ pracy lub dyspozytora.  
  
### <a name="using-the-transactedreceivescope-activity-designer"></a>Za pomocą TransactedReceiveScope, Projektant działań  
 **TransactedReceiveScope** projektanta działań można znaleźć w **komunikatów** kategorii **przybornika**, które jest dostępne po kliknięciu **przybornika**  karcie [!INCLUDE[wfd2](../includes/wfd2-md.md)] (można także wybrać **narzędzi** z **widoku** menu lub klawiszy CTRL + ALT + X.)  
  
 **TransactedReceiveScope** projektanta działań mogą być przeciągnięte z **przybornika** i porzuconych do [!INCLUDE[wfd2](../includes/wfd2-md.md)] powierzchni wszędzie tam, gdzie działań są zazwyczaj umieszczone. Spowoduje to utworzenie <xref:System.ServiceModel.Activities.TransactedReceiveScope> działanie przy użyciu domyślnego **DisplayName** transactedreceivescope. <xref:System.Activities.Activity.DisplayName%2A> Mogą być edytowane w nagłówku **TransactedReceiveScope** projektanta działań lub **DisplayName** pola siatki właściwości.  
  
 **TransactedReceiveScope** Projektant zawiera **żądania** i **treści** pola. Są one używane do konfigurowania <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> właściwość, która określa <xref:System.ServiceModel.Activities.Receive> działania i <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> właściwość, która określa niektóre inne <xref:System.Activities.Activity>. <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> Tworzy transakcji. Następnie transakcja ma zostać otoczenia w zakresie <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> tak, aby wszystkie działania w tym zakresie wykonuje wewnątrz tej transakcji.  
  
### <a name="the-transactedreceivescope-properties"></a>Właściwości TransactedReceiveScope  
 W poniższej tabeli przedstawiono <xref:System.ServiceModel.Activities.TransactedReceiveScope> właściwości i w tym artykule opisano, jak są używane w projektancie. Te <xref:System.Activities.Activity.DisplayName%2A> właściwości można edytować w siatce właściwości lub na [!INCLUDE[wfd2](../includes/wfd2-md.md)] powierzchni, ale innych, należy edytować na powierzchni projektowej.  
  
|Nazwa właściwości|Wymagane|Użycie|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Opcjonalna nazwa przyjazna <xref:System.ServiceModel.Activities.TransactedReceiveScope> działania. Wartość domyślna to TransactedReceiveScope.<br /><br /> Mimo że <xref:System.Activities.Activity.DisplayName%2A> nazwa nie jest bezwzględnie konieczne, jest najlepszym rozwiązaniem, aby użyć nazwy wyświetlanej.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>|True|Spadnie <xref:System.ServiceModel.Activities.Receive> działanie do **żądania** bloku na powierzchni projektanta działań.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>|False|Spadnie <xref:System.Activities.Activity> do **treści** bloku na powierzchni projektanta działań.|  
  
## <a name="see-also"></a>Zobacz też  
 [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)   
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [Odbieranie](../workflow-designer/receive-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Wyślij](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)