---
title: 'CA1823: Unikaj nieużywanych pól prywatnych | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- AvoidUnusedPrivateFields
- CA1823
helpviewer_keywords:
- AvoidUnusedPrivateFields
- CA1823
ms.assetid: 614f94f6-0dc7-430f-8124-cb889a4a720f
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 306c587daa63089114d2bceefda42b064f8cc6fc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677080"
---
# <a name="ca1823-avoid-unused-private-fields"></a>CA1823: Unikaj nieużywanych pól prywatnych
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1823: Unikaj nieużywanych pól prywatnych](https://docs.microsoft.com/visualstudio/code-quality/ca1823-avoid-unused-private-fields).  
  
Element TypeName | AvoidUnusedPrivateFields |  
| CheckId | CA1823 |  
| Kategoria | Microsoft.Performance|  
| Zmiana powodująca niezgodność | Bez podziału |  
  
## <a name="cause"></a>Przyczyna  
 Ta reguła jest zgłaszany, gdy istnieje pole private w kodzie, ale nie jest używany przez wszystkie ścieżce kodu.  
  
## <a name="rule-description"></a>Opis reguły  
 Zostały wykryte pola prywatne, które w zestawie nie są widoczne jako dostępne.  
  
## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia  
 Aby naprawić naruszenie tej zasady, usuń pole, lub Dodaj kod, który korzysta z niego.  
  
## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia  
 Jest bezpieczne pominąć ostrzeżenie od tej reguły.  
  
## <a name="related-rules"></a>Powiązane reguły  
 [CA1812: Unikaj klas wewnętrznych bez wystąpień](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)  
  
 [CA1801: Przejrzyj nieużywane parametry](../code-quality/ca1801-review-unused-parameters.md)  
  
 [CA1804: Usuń nieużywane zmienne lokalne](../code-quality/ca1804-remove-unused-locals.md)  
  
 [CA1811: Unikaj niewywoływanego kodu prywatnego](../code-quality/ca1811-avoid-uncalled-private-code.md)



