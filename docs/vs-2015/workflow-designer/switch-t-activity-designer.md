---
title: Przełącznik&lt;T&gt; projektanta działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.ModelItemKeyValuePair.UI
- System.Activities.Statements.Switch`1.UI
ms.assetid: 18a6c96e-49a9-4356-ab61-fbd7e3ab44bb
caps.latest.revision: 3
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 3b7ae322bbdb4d93106c468409cab77127e5eb0b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631271"
---
# <a name="switchlttgt-activity-designer"></a>Przełącznik&lt;T&gt; Projektant działań
<xref:System.Activities.Statements.Switch%601> Działanie oblicza określone wyrażenie i wykonuje działania z kolekcji działań, w których skojarzony klucz pasuje do wartości uzyskanej z oceny.  
  
 **Przełącznika\<T >** projektanta działań służy do tworzenia i konfigurowania <xref:System.Activities.Statements.Switch%601> działania w [!INCLUDE[wfd1](../includes/wfd1-md.md)].  
  
## <a name="the-switchtactivity"></a>Przełącznik\<T > działania  
 A <xref:System.Activities.Statements.Switch%601> zawiera działanie <xref:System.Activities.Statements.Switch%601.Expression%2A> i słownika <xref:System.Activities.Statements.Switch%601.Cases%2A>. Każdy przypadek w słowniku składa się z parą, która zawiera *klucz* i działań, która służy jako odpowiadającymi mu dostawcami *wartość*. <xref:System.Activities.Statements.Switch%601> Ocenia aktywności <xref:System.Activities.Statements.Switch%601.Expression%2A> i porównuje ją z każdego z kluczy. Jeśli zostanie znalezione dopasowanie, odpowiadające mu działanie jest wykonywana. Tylko jedno dopasowanie jest możliwe, ponieważ klucze słownikowe musi być unikatowy, zależnie od typu równości zdefiniowane przez moduł porównujący równość słownika. Jeśli nie zostanie znalezione dopasowanie, <xref:System.Activities.Statements.Switch%601.Default%2A> jest wykonywane działanie.  
  
## <a name="how-to-use-the-switcht-activity-designer"></a>Jak użyć przełącznika\<T > Projektant działań  
 **Przełącznika\<T >** projektanta działań można znaleźć w **przepływ sterowania** kategorii **przybornika**, które jest dostępne po kliknięciu **Przybornika** karcie [!INCLUDE[wfd2](../includes/wfd2-md.md)] (można także wybrać **narzędzi** z **widoku** menu lub klawiszy CTRL + ALT + X.) Po upuszczając go do [!INCLUDE[wfd2](../includes/wfd2-md.md)], wyświetla **wybierz typy** okna dialogowego, aby zezwolić użytkownikom na określanie typu ogólnego *T* używane w <xref:System.Activities.Statements.Switch%601> działania. Wartość domyślna to **Int32**. Po typie ogólnym *T* został zaznaczony, **przełącznika\<T >** Projektant zostanie dodany do projektanta przepływów pracy.  
  
 Poniżej przedstawiono właściwości **przełącznika\<T >** projektanta. Wszystkie te właściwości można edytować w siatce właściwości. Niektóre z nich, można również edytować na powierzchni projektanta.  
  
 W poniższej tabeli przedstawiono najbardziej przydatne <xref:System.Activities.Statements.Switch%601> właściwości i w tym artykule opisano, jak są używane w projektancie.  
  
|Nazwa właściwości|Wymagane|Użycie|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Określa przyjazną nazwę <xref:System.Activities.Statements.Switch%601> projektanta działań. Wartość domyślna to przełącznik\<Int32 >. Wartość może być edytowana w **właściwości** okna lub bezpośrednio w nagłówku projektanta.<br /><br /> Mimo że <xref:System.Activities.Activity.DisplayName%2A> nie jest bezwzględnie konieczne jest najlepszym rozwiązaniem, aby użyć jednego.|  
|<xref:System.Activities.Statements.Switch%601.Expression%2A>|True|Określa wyrażenie używane do porównania z kluczy w kolekcji spraw, aby ustalić którym to przypadku do wykonania.|  
|<xref:System.Activities.Statements.Switch%601.Default%2A>||Określa działanie wykonywane, jeśli nie zostanie znalezione dopasowanie. Kliknij przycisk **dodać działanie** przycisku w projektancie, aby otworzyć **domyślne** pola, których można było porzucić działania.|  
|<xref:System.Activities.Statements.Switch%601.Cases%2A>||Określa przypadki, które ma zostać obliczone. Aby dodać przypadek, kliknij **Dodaj nowy przypadek** znajdujący się u dołu **przełącznika\<T >** projektanta. Przycisk zmienia się na pola tekstowego (pola kombi, w przypadku wybrania typu ogólnego, podczas dodawania przełącznika\<T > jest ciągiem lub typu wyliczeniowego). Po dodaniu klucza w **wartość Case** w polu Obszar przypadków rozszerza i działania można było porzucić gdzie tekst wskazówki "W tym miejscu listy activity" Aby zdefiniować logiki wykonywania w przypadku.|  
  
 Można dodać wiele przypadków, tak długo, jak wielkość klucze nie są duplikowane. W przeciwnym razie pojawia się okno dialogowe wyświetla raportowania, określonego klucza przypadków już istnieje i czy należy wybrać inny klucz. W **przełącznika\<T >** projektanta, tylko jeden obszar przypadków mogą znajdować się w widoku rozwiniętego w danym momencie. Jeśli obszar przypadków znajduje się w widoku zwiniętym, klikając przypadków obszar powiększa go. Należy zauważyć, że w przypadku zwinięty Projektant pokazuje nazwę wyświetlaną działania w przypadku po prawej stronie czy dowolny. W przeciwnym razie pokazuje **dodać działanie** przycisk, który rozwija tak, kliknij je, a także pozwala dodać działanie.  
  
 Klikając klucz istniejącego przypadku zmienia klucza z etykietę do pola tekstowego, dzięki czemu można edytować klucza przypadków.  
  
 Istnieją 2 sposoby usunięcie sprawy:  
  
1.  Wybierz przypadek i usuń go.  
  
2.  Wybierz przypadek, kliknij prawym przyciskiem myszy aby wyświetlić menu kontekstowe i wybierz **Usuń**.  
  
 Należy pamiętać, że należy wybrać tak, aby go usunąć. Wybierając i usuwając działanie w przypadku usuwa tylko działania inaczej.  
  
## <a name="see-also"></a>Zobacz też  
 [Przepływ sterowania](../workflow-designer/control-flow-activity-designers.md)