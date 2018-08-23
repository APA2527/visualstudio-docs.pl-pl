---
title: Ostrzeżenia niezawodności | Dokumentacja firmy Microsoft
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
- vs.codeanalysis.reliabilityrules
helpviewer_keywords:
- warnings, reliability
- reliability warnings
- managed code analysis warnings, reliability warnings
ms.assetid: 77886846-10a2-4585-968a-7eb60ebe07e8
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f3bfaff6a434a138024f0baa454935a6da4e67da
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42679787"
---
# <a name="reliability-warnings"></a>Ostrzeżenia niezawodności
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [ostrzeżenia niezawodności](https://docs.microsoft.com/visualstudio/code-quality/reliability-warnings).  
  
Ostrzeżenia niezawodności obsługuje niezawodność biblioteki i aplikacji, takich jak poprawne użycie pamięci i wątku.  
  
## <a name="in-this-section"></a>W tej sekcji  
  
|Reguła|Opis|  
|----------|-----------------|  
|[CA2000: Likwiduj obiekty przed utratą zakresu](../code-quality/ca2000-dispose-objects-before-losing-scope.md)|Ze względu na to, że może wystąpić wyjątkowe zdarzenie, które uniemożliwi uruchomienie finalizatora obiektu, obiekty powinny być jawnie usuwane, zanim wszystkie odwołania do niego znajdą się poza zakresem.|  
|[CA2001: Unikaj wywoływania problematycznych metod](../code-quality/ca2001-avoid-calling-problematic-methods.md)|Element członkowski wywołuje potencjalnie niebezpieczną lub problematyczną metodę.|  
|[CA2002: Nie blokuj obiektów o słabej tożsamości](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|Obiekt ma słabą tożsamość, gdy można uzyskać do niego bezpośredni dostęp poza granicami domeny aplikacji. Wątek, który próbuje uzyskać blokadę na obiekcie o słabej tożsamości, może zostać zablokowany przez drugi wątek w domenie innej aplikacji, która ma blokady dla tego samego obiektu.|  
|[CA2003: Nie traktuj włókien jak wątków](../code-quality/ca2003-do-not-treat-fibers-as-threads.md)|Zarządzane zarządzalny wątek jest traktowany jako wątek Win32.|  
|[CA2004: Usuń wywołania funkcji GC.KeepAlive](../code-quality/ca2004-remove-calls-to-gc-keepalive.md)|W przypadku konwertowania użycia SafeHandle należy usunąć wszystkie wywołania GC. KeepAlive (obiekt). W tym przypadku klasy nie powinny wywołać GC. Obsługuj KeepAlive, zakładając, że nie ma finalizatora, ale zależą od klasy SafeHandle w celu sfinalizowania systemu operacyjnego dla nich.|  
|[CA2006: Używaj klasy SafeHandle w celu hermetyzacji zasobów natywnych](../code-quality/ca2006-use-safehandle-to-encapsulate-native-resources.md)|Wykorzystanie elementu IntPtr w kodzie zarządzanym może wskazywać na potencjalny problem dotyczący bezpieczeństwa i niezawodności. Wszystkie użycia elementu IntPtr muszą być przejrzane w celu ustalenia, czy użycie elementu SafeHandle lub podobnej technologii jest w tym miejscu wymagane.|



