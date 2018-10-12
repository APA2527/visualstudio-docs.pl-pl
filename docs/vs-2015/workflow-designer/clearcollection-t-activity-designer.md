---
title: ClearCollection&lt;T&gt; projektanta działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ClearCollection`1.UI
ms.assetid: db0e5da2-7b5a-4f1a-864c-f3aeeeeb51a7
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 7c71d9a09cb3f64464ce968296799b27d573bfcd
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49232878"
---
# <a name="clearcollectionlttgt-activity-designer"></a>ClearCollection&lt;T&gt; Projektant działań
**ClearCollection\<T >** projektanta działań służy do tworzenia i konfigurowania <xref:System.Activities.Statements.ClearCollection%601> działania.  
  
## <a name="the-clearcollectiont-activity"></a>ClearCollection\<T > działania  
 <xref:System.Activities.Statements.ClearCollection%601> Działania czyści wszystkie elementy dla określonej kolekcji.  
  
### <a name="using-the-clearcollectiont-activity-designer"></a>Za pomocą ClearCollection\<T > Projektant działań  
 **ClearCollection\<T >** projektanta działań można znaleźć w **kolekcji** kategorii **przybornika**, które jest dostępne po kliknięciu  **Przybornik** karcie [!INCLUDE[wfd2](../includes/wfd2-md.md)] (można także wybrać **narzędzi** z **widoku** menu lub klawiszy CTRL + ALT + X.)  
  
 **ClearCollection\<T >** projektanta działań mogą być przeciągnięte z **przybornika** i porzuconych do [!INCLUDE[wfd2](../includes/wfd2-md.md)] powierzchni wszędzie tam, gdzie działań są zwyczajowo umieszczane, takie jak wewnątrz <xref:System.Activities.Statements.Sequence>. Spowoduje to utworzenie <xref:System.Activities.Statements.ClearCollection%601> działanie przy użyciu domyślnego <xref:System.Activities.Activity.DisplayName%2A> z ClearCollection\<Int32 >. (Domyślnie *elementu typeargument w języku* jest **Int32**. Można to zmienić w siatce właściwości.) <xref:System.Activities.Activity.DisplayName%2A> Wartość może być edytowana w nagłówku **ClearCollection\<T >** projektanta działań lub **DisplayName** pola siatki właściwości. W siatce właściwości, należy edytować inne właściwości.  
  
### <a name="the-clearcollectiont-properties"></a>ClearCollection\<T > Właściwości  
 W poniższej tabeli przedstawiono <xref:System.Activities.Statements.ClearCollection%601> właściwości i w tym artykule opisano, jak są używane w projektancie.  
  
|Nazwa właściwości|Wymagane|Użycie|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Określa opcjonalny przyjazna nazwa <xref:System.Activities.Statements.ClearCollection%601> działania. Wartość domyślna to ClearCollection\<Int32 >. Mimo że <xref:System.Activities.Activity.DisplayName%2A> wartość nie jest bezwzględnie konieczne, jest najlepszym rozwiązaniem, aby użyć jednego.|  
|<xref:System.Activities.Statements.ClearCollection%601.Collection%2A>|True|Określa kolekcję elementów zostaje wyczyszczona. Ta kolekcja jest typu **ICollection\<elementu typeargument w języku >.** Aby określić kolekcję, wpisz wyrażenie języka Visual Basic w siatce właściwości.|  
|*TypeArgument*|True|Określa typ T elementów znajdujących się w <xref:System.Collections.Generic.ICollection%601>. Domyślnie to *elementu typeargument w języku* ustawiono typ **Int32**. Aby zmienić typ, zmień wartość *elementu typeargument w języku* w polu kombi w siatce właściwości.|  
  
## <a name="see-also"></a>Zobacz też  
 [Kolekcja](../workflow-designer/collection-activity-designers.md)   
 [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)   
 [ExistsInCollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)   
 [RemoveFromCollection\<T >](../workflow-designer/removefromcollection-t-activity-designer.md)