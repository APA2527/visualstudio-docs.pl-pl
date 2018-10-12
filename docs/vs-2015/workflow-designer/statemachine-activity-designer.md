---
title: StateMachine, Projektant działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- StateMachine Designer
- System.Activities.Statements.StateMachine.UI
ms.assetid: 474d5fb3-1049-4b3f-bc6b-7524dbbe1672
caps.latest.revision: 5
author: steved0x
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 18f7cc5eb88265de1250e4a06f78b13bcc419fb7
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49301408"
---
# <a name="statemachine-activity-designer"></a>StateMachine, projektant działań
<xref:System.Activities.Statements.StateMachine> Działanie zawiera kolekcję stanów i modele przepływów pracy za pomocą modelu maszyny znanego stanu.  
  
## <a name="using-the-statemachine-activity-designer"></a>Za pomocą StateMachine, Projektant działań  
 Aby dodać <xref:System.Activities.Statements.StateMachine> działania, przeciągnij **StateMachine** projektanta działań z **automatu stanów** części **przybornika** i upuść je na [!INCLUDE[wfd1](../includes/wfd1-md.md)] powierzchni. Aby dodać stan podrzędnych do tego <xref:System.Activities.Statements.StateMachine> działania, przeciągnij <xref:System.Activities.Statements.State> lub <xref:System.Activities.Core.Presentation.FinalState> z **przybornika** i upuść je na **StateMachine**.  
  
### <a name="statemachine-activity-properties-in-the-workflow-designer"></a>Automat stanów właściwości działania w Projektancie przepływu pracy  
 W poniższej tabeli przedstawiono <xref:System.Activities.Statements.StateMachine> właściwości, które można ustawić za pomocą projektanta przepływów pracy i w tym artykule opisano, jak są używane w projektancie. Te właściwości można edytować w siatce właściwości, a niektóre z nich mogą być edytowane na powierzchni projektowej.  
  
|Nazwa właściwości|Wymagane|Użycie|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Określa przyjazną nazwę <xref:System.Activities.Statements.StateMachine> projektanta działań w nagłówku. Wartość domyślna to **StateMachine**. Wartość można edytować w siatce właściwości lub bezpośrednio w nagłówku projektanta działań. <xref:System.Activities.Activity.DisplayName%2A> Jest używany w nadrzędnych, która jest wyświetlana w górnej części projektanta przepływów pracy.<br /><br /> Mimo że <xref:System.Activities.Activity.DisplayName%2A> nie jest bezwzględnie konieczne jest najlepszym rozwiązaniem, aby użyć jednego.|  
  
## <a name="see-also"></a>Zobacz też  
 [Schemat blokowy](../workflow-designer/flowchart-activity-designer.md)   
 [Przepływ sterowania](../workflow-designer/control-flow-activity-designers.md)