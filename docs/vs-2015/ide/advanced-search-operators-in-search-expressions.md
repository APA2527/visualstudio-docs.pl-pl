---
title: Operatory wyszukiwania zaawansowanego w wyrażeniach wyszukiwania | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Help Viewer 2.0, searching for keywords
- Help Viewer 2.0, searching code
- Help Viewer 2.0, searching code by programming language
- Help Viewer 2.0, searching titles
- searching code [Help Viewer 2.0]
- searching titles [Help Viewer 2.0]
ms.assetid: 0cdc1746-8481-45ec-9c53-d0d89cdcbd5e
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 706d6d89d46a1e5db4f94c2e7d5e35ace73e1bac
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49178005"
---
# <a name="advanced-search-operators-in-search-expressions"></a>Operatory wyszukiwania zaawansowanego w wyrażeniach wyszukiwania
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Za pomocą operatorów wyszukiwania zaawansowanego, można uściślić wyszukiwanie zawartości, tworząc bardziej złożonych wyszukiwania z tymi prostsze. Jak pokazano w poniższej tabeli, te operatory ograniczyć kontekst, w którym jest uruchamiane zapytanie.  
  
> [!WARNING]
>  Należy wprowadzić operatory wyszukiwania zaawansowanego z dwukropkiem ostateczne i nie pośredniczące odstęp przed dwukropkiem dla aparatów wyszukiwania można je rozpoznać.  
  
|Aby wyszukać|Zastosowanie|Przykład|Wynik|  
|-------------------|---------|-------------|------------|  
|Termin w tytuł tematu|Tytuł:|Tytuł: binaryreader|Tematy, które zawierają "binaryreader" w tytułach.|  
|Termin w przykładzie kodu|Kod:|Kod: readdouble|Tematy, które zawierają "readdouble" w przykładzie kodu.|  
|Termin w przykładzie określonego języka programowania|Kod: vb:|Kod: vb:string|Tematy, które zawierają "string", w przykładzie Visual Basic.|  
|Temat, który jest skojarzony z określonym indeksem słowem kluczowym|słowa kluczowe:|słowo kluczowe: readbyte|Tematy, które są skojarzone ze słowem kluczowym "readbyte" indeksu.|  
  
 Można użyć kodu: Aby znaleźć zawartość informacji na temat kilku języków programowania, ale zwraca wyniki tylko dla zawartości, oznaczony za pomocą określonego języka programowania. Poniższa tabela zawiera listę języków programowania, które obsługuje tego operatora:  
  
|Język programowania|Zastosowanie|  
|--------------------------|---------|  
|Visual Basic|Kod: vb<br /><br /> lub<br /><br /> Kod: języka Visual Basic|  
|C#|Kod: c#<br /><br /> lub<br /><br /> Kod: csharp|  
|C++|Kod: cpp<br /><br /> lub<br /><br /> Kod: c ++<br /><br /> lub<br /><br /> Kod: cplusplus|  
|F#|Kod: f #<br /><br /> lub<br /><br /> Kod: fsharp|  
|JavaScript|Kod: javascript<br /><br /> lub<br /><br /> Kod: js|  
|XAML|Kod: xaml|  
  
## <a name="see-also"></a>Zobacz też  
 [Operatory logiczne w wyrażeniach wyszukiwania](../ide/logical-operators-in-search-expressions.md)   
 [Wskazówki dotyczące wyszukiwania pełnotekstowego](../ide/full-text-search-tips.md)



