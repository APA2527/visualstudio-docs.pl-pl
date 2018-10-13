---
title: Ostrzeżenia dotyczące utrzymania | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f709a7bb2d433ab86b5088349f1977a66c9a4c42
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49238501"
---
# <a name="maintainability-warnings"></a>Utrzymanie — Ostrzeżenia
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ostrzeżenia dotyczące utrzymania obsługuje konserwacji biblioteki i aplikacji.  
  
## <a name="in-this-section"></a>W tej sekcji  
  
|Reguła|Opis|  
|----------|-----------------|  
|[CA1500: Nazwy zmiennych nie powinny odpowiadać nazwom pól](../code-quality/ca1500-variable-names-should-not-match-field-names.md)|Metoda wystąpienia deklaruje parametr lub zmienna lokalna, których nazwa pasuje do pola wystąpienia typu deklarującego, co prowadzi do błędów.|  
|[CA1501: Unikaj nadmiernego dziedziczenia](../code-quality/ca1501-avoid-excessive-inheritance.md)|Typ jest głęboki na więcej niż cztery poziomy w hierarchii dziedziczenia. Hierarchie typów głęboko zagnieżdżonych mogą być trudne do śledzenia, zrozumienia i utrzymania.|  
|[CA1502: Unikaj nadmiernej złożoności](../code-quality/ca1502-avoid-excessive-complexity.md)|Ta reguła mierzy liczbę liniowo niezależnych ścieżek za pośrednictwem metody, która jest określona przez liczbę i złożoność rozgałęzień warunkowych.|  
|[CA1504: Przejrzyj mylące nazwy pól](../code-quality/ca1504-review-misleading-field-names.md)|Nazwa pola wystąpienia zaczyna się od "s_" lub nazwa statycznego (udostępnionego w [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) pola rozpoczyna się od "m_".|  
|[CA1505: Unikaj kodu trudnego w utrzymaniu](../code-quality/ca1505-avoid-unmaintainable-code.md)|Typ lub metoda ma niską wartość indeksu konserwacji. Niski indeks konserwacji wskazuje, że typ lub metoda są prawdopodobnie trudne do utrzymania i są dobrymi kandydatami do przeprojektowania.|  
|[CA1506: Unikaj nadmiernego sprzężenia klas](../code-quality/ca1506-avoid-excessive-class-coupling.md)|Ta reguła mierzy sprzęgnięcie klasy przez liczenie unikatowych odwołań typów, które zawiera typ lub metoda.|  
  
## <a name="see-also"></a>Zobacz też  
 [Mierzenie złożoności i poziomu łatwości konserwacji kodu zarządzanego](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)



