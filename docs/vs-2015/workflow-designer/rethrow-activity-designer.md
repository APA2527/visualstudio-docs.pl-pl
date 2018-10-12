---
title: Rethrow, Projektant działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 724e0b69fb14735682d437c9f21906560b15a590
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49280686"
---
# <a name="rethrow-activity-designer"></a>Rethrow, projektant działań
**Zgłoś ponownie** projektanta działań służy do tworzenia i konfigurowania <xref:System.Activities.Statements.Rethrow> działania.  
  
## <a name="the-rethrow-activity"></a>Działanie ponownego zgłoszenia  
 <xref:System.Activities.Statements.Rethrow> Działanie zgłasza wcześniej zgłoszony wyjątek. To działanie można używać tylko w <xref:System.Activities.Statements.Catch> obsługi w <xref:System.Activities.Statements.TryCatch> działania.  
  
### <a name="using-the-rethrow-activity-designer"></a>Za pomocą projektanta działań Zgłoś ponownie  
 **Zgłoś ponownie** projektanta działań można znaleźć w **obsługę błędów** kategorii **przybornika**, które jest dostępne po kliknięciu **przybornika**karty w lewej części [!INCLUDE[wfd2](../includes/wfd2-md.md)] (można także wybrać **narzędzi** z **widoku** menu lub klawiszy CTRL + ALT + X.)  
  
 **Zgłoś ponownie** projektanta działań mogą być przeciągnięte z **przybornika** i porzuconych do [!INCLUDE[wfd2](../includes/wfd2-md.md)] powierzchni wszędzie tam, gdzie działań są zwyczajowo umieszczane, takie jak wewnątrz <xref:System.Activities.Statements.Sequence>. Spowoduje to utworzenie <xref:System.Activities.Statements.Rethrow> działanie przy użyciu domyślnego **DisplayName** z Throw. <xref:System.Activities.Activity.DisplayName%2A> Wartość może być edytowana w nagłówku **Zgłoś ponownie** projektanta działań lub **DisplayName** pola siatki właściwości.  
  
### <a name="the-rethrow-properties"></a>Zgłoś ponownie właściwości  
 W poniższej tabeli przedstawiono <xref:System.Activities.Statements.Rethrow> właściwości i w tym artykule opisano, jak są używane w projektancie.  
  
|Nazwa właściwości|Wymagane|Użycie|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Określa opcjonalny przyjazna nazwa <xref:System.Activities.Statements.Rethrow> działania. Wartość domyślna to Zgłoś ponownie.|  
  
## <a name="see-also"></a>Zobacz też  
 [Kolekcja](../workflow-designer/collection-activity-designers.md)   
 [throw](../workflow-designer/throw-activity-designer.md)   
 [TryCatch](../workflow-designer/trycatch-activity-designer.md)