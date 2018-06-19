---
title: Ostrzeżenia niezawodności
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- vs.codeanalysis.reliabilityrules
helpviewer_keywords:
- warnings, reliability
- reliability warnings
- managed code analysis warnings, reliability warnings
ms.assetid: 77886846-10a2-4585-968a-7eb60ebe07e8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c690be59758ca17a573d742fc0f75c81b955d5ad
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31916751"
---
# <a name="reliability-warnings"></a>Ostrzeżenia niezawodności
Ostrzeżenia niezawodności obsługuje niezawodności biblioteki i aplikacji, takich jak odpowiednie użycie pamięci i wątku.

## <a name="in-this-section"></a>W tej sekcji

|Reguła|Opis|
|----------|-----------------|
|[CA2000: Likwiduj obiekty przed utratą zakresu](../code-quality/ca2000-dispose-objects-before-losing-scope.md)|Ze względu na to, że może wystąpić wyjątkowe zdarzenie, które uniemożliwi uruchomienie finalizatora obiektu, obiekty powinny być jawnie usuwane, zanim wszystkie odwołania do niego znajdą się poza zakresem.|
|[CA2001: Unikaj wywoływania problematycznych metod](../code-quality/ca2001-avoid-calling-problematic-methods.md)|Element członkowski wywołuje potencjalnie niebezpieczną lub problematyczną metodę.|
|[CA2002: Nie blokuj obiektów o słabej tożsamości](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|Obiekt ma słabą tożsamość, gdy można uzyskać do niego bezpośredni dostęp poza granicami domeny aplikacji. Wątek, który próbuje uzyskać blokadę na obiekcie o słabej tożsamości, może zostać zablokowany przez drugi wątek w domenie innej aplikacji, która ma blokady dla tego samego obiektu.|
|[CA2003: Nie traktuj włókien jak wątków](../code-quality/ca2003-do-not-treat-fibers-as-threads.md)|Zarządzanego wątku jest traktowana jako wątku Win32.|
|[CA2004: Usuń wywołania funkcji GC.KeepAlive](../code-quality/ca2004-remove-calls-to-gc-keepalive.md)|Jeśli są konwertowane na użycie klasy SafeHandle, należy usunąć wszystkie wywołania GC. KeepAlive (obiekt). W takim przypadku klas nie powinna mieć wywołać GC. Obsługa KeepAlive, zakładając, że nie ma finalizator, ale zależne od klasy SafeHandle w celu zakończenia systemu operacyjnego dla nich.|
|[CA2006: Używaj klasy SafeHandle w celu hermetyzacji zasobów natywnych](../code-quality/ca2006-use-safehandle-to-encapsulate-native-resources.md)|Wykorzystanie elementu IntPtr w kodzie zarządzanym może wskazywać na potencjalny problem dotyczący bezpieczeństwa i niezawodności. Wszystkie użycia elementu IntPtr muszą być przejrzane w celu ustalenia, czy użycie elementu SafeHandle lub podobnej technologii jest w tym miejscu wymagane.|