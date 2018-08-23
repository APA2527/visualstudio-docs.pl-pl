---
title: CorrelationScope, Projektant działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.CorrelationScope.UI
ms.assetid: 75f20664-9042-464d-8e2b-148d365a2286
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 61ce707f0a26a11d7e8c81899d5c2d65a7dc3f22
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683819"
---
# <a name="correlationscope-activity-designer"></a>CorrelationScope, projektant działań
**CorrelationScope** projektanta działań służy do tworzenia i konfigurowania <xref:System.ServiceModel.Activities.CorrelationScope> działanie, które umożliwia niejawne Zarządzanie podrzędnych działań dotyczących komunikatów za pomocą <xref:System.ServiceModel.Activities.CorrelationHandle> obiektu.  
  
## <a name="the-correlationscope-activity"></a>Działanie CorrelationScope  
 <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> Właściwość określa <xref:System.ServiceModel.Activities.CorrelationHandle> używany do zarządzania działań dotyczących komunikatów podrzędnych. <xref:System.ServiceModel.Activities.Send> i <xref:System.ServiceModel.Activities.Receive> działań zawartych w <xref:System.ServiceModel.Activities.CorrelationScope.Body%2A> są skonfigurowane do używania <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> właściwości zawierającego <xref:System.ServiceModel.Activities.CorrelationScope> działania do wykonania korelacji.  
  
### <a name="using-the-correlationscope-activity-designer"></a>Za pomocą CorrelationScope, Projektant działań  
 **CorrelationScope** projektanta działań można znaleźć w **komunikatów** kategorii **przybornika**, które jest dostępne po kliknięciu **przybornika** karty w lewej części [!INCLUDE[wfd2](../includes/wfd2-md.md)] (można także wybrać **narzędzi** z **widoku** menu lub klawiszy CTRL + ALT + X.)  
  
 **CorrelationScope** projektanta działań mogą być przeciągnięte z **przybornika** i porzuconych do [!INCLUDE[wfd2](../includes/wfd2-md.md)] powierzchni. Spowoduje to utworzenie <xref:System.ServiceModel.Activities.CorrelationScope> działanie przy użyciu domyślnego **DisplayName** z CorrelationScope. <xref:System.Activities.Activity.DisplayName%2A> Mogą być edytowane w nagłówku **CorrelationScope** projektanta działań lub **DisplayName** pole **właściwości** okna.  
  
 Aby określić <xref:System.ServiceModel.Activities.CorrelationHandle> używany przez podrzędny działań dotyczących komunikatów, kliknij przycisk wielokropka obok **CorrelatesWith** pole **właściwości** okno, aby wyświetlić **edytora wyrażeń**  okno dialogowe. Można również ustawić tę właściwość na powierzchni projektanta działań.  
  
 Działania o określonym zakresie w ramach korelację są określone przez usunięcie ich projektantów w ramach **treści** polu w ramach **CorrelationScope** projektanta.  
  
### <a name="the-correlationscope-properties"></a>Właściwości CorrelationScope  
 W poniższej tabeli przedstawiono <xref:System.ServiceModel.Activities.CorrelationScope> właściwości i w tym artykule opisano, jak są używane w projektancie. Te właściwości mogą być edytowane w **właściwości** oknie lub na [!INCLUDE[wfd2](../includes/wfd2-md.md)] projektanta powierzchni i często w obu.  
  
|Nazwa właściwości|Wymagane|Użycie|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Opcjonalna nazwa przyjazna <xref:System.ServiceModel.Activities.InitializeCorrelation> działania.|  
|<xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A>|False|Określa <xref:System.ServiceModel.Activities.CorrelationHandle> używany do zarządzania działań dotyczących komunikatów podrzędnych. Jeśli nie ustawisz tę właściwość, <xref:System.ServiceModel.Activities.CorrelationScope> tworzy ukrytego <xref:System.ServiceModel.Activities.CorrelationHandle> automatycznie.|  
|<xref:System.ServiceModel.Activities.CorrelationScope.Body%2A>|False|Określa działań w zakresie korelacji.|  
  
## <a name="see-also"></a>Zobacz też  
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [Odbieranie](../workflow-designer/receive-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Wyślij](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)