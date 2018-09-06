---
title: Widok rdzeni | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.cores
helpviewer_keywords:
- Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2f9fdd88640999759fe729b3949785a79e763986
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "35677449"
---
# <a name="cores-view"></a>Widok rdzeni
**Widoku rdzeni** pokazuje, jak wykonanie wątku został zamapowany na rdzeni procesora logicznego (wybierz **analizy** > **Concurrency Visualizer** do uruchomienia Narzędzie CONCURRENCY visualizer). Jeśli piszesz aplikacje serwera, ten widok może pomóc w optymalizacji wydajności pamięci podręcznej przy użyciu przystawki Zarządzanie puli wątków koligacji lub wątku. Może również pomóc możesz sprawdzić przypadki, w którym korzystanie z koligacji wątku może mieć pogorszyła problem migracji między różnymi rdzeniami. Widok rdzeni ma dwie części, wykresu i legenda.  
  
 Na wykresie widać rdzenie logiczne na osi y i godziny na osi x. Każdy wątek na wykresie ma unikatowy kolor, więc możliwe jest śledzenie jego ruchu między rdzeniami wraz z upływem czasu. Wątki na tym wykresie można filtrować, wybierając je w obszarze legendy.  
  
 W obszarze legendy ma wpis dla każdego koloru na wykresie. Każdy wpis zawiera kolor wątku i nazwę, liczba przełączeń kontekstu między rdzeniami, całkowita liczba przełączeń kontekstu i procent przełączeń kontekstu przecinających rdzenie. Legendy są posortowane według liczby przełączeń kontekstu między rdzeniami, w kolejności malejącej. Wyświetla listę wątków, które wykonywane w czasie wyświetlane.  Lista jest aktualizowana, jeśli użytkownik przybliżanie/Oddalanie lub przesuwanie.  
  
## <a name="see-also"></a>Zobacz także  
 [Narzędzie CONCURRENCY Visualizer](../profiling/concurrency-visualizer.md)   
 [Widok wykorzystania](../profiling/utilization-view.md)   
 [Widok wątków](../profiling/threads-view-parallel-performance.md)