---
title: Widok modułów — dane próbkowania | Microsoft Docs
description: Dowiedz się, w jaki sposób widok modułów danych próbkowania przedstawia dane wydajności pogrupowane według modułów, które zostały próbkowane w danych profilowania.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Modules view
- sampling profiling method,Modules view
ms.assetid: 816f5633-65d7-41e5-aee1-033628d4e2df
author: mikejo5000
ms.author: mikejo
manager: jmartens
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 2b498279b085f19cd6ea218b4300301184da8e0c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99879751"
---
# <a name="modules-view---sampling-data"></a>Widok modułów — dane próbkowania
Widok moduły danych próbkowania przedstawia dane wydajności pogrupowane według modułów, które zostały próbkowane w danych profilowania. Każdy moduł jest katalogiem głównym drzewa hierarchicznego. Przykładowe funkcje modułu są wyświetlane poniżej węzła moduł.

> [!NOTE]
> Ulepszone funkcje zabezpieczeń w systemach Windows 8 i Windows Server 2012 wymagały znaczących zmian w sposobie, w jaki program Visual Studio profiler zbiera dane na tych platformach. Aplikacje platformy UWP wymagają również nowych technik zbierania danych. Zobacz [Narzędzia do oceny wydajności w aplikacjach systemu Windows 8 i Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

 Jeśli funkcja była wykonywana po zebraniu próbek (oznacza to, że funkcja była w górnej części stosu wywołań), wiersze źródłowe i podane przez siebie adresy są wyświetlane poniżej węzła funkcji. Ponieważ dane są zbierane dla linii źródłowej lub wskaźnika instrukcji podczas wykonywania wiersza lub instrukcji, Włączne i wyłączne wartości są zawsze takie same dla danych wierszowych i danych instrukcji.

|Kolumna|Opis|
|------------|-----------------|
|**Nazwa**|Nazwa modułu, funkcji, numeru wiersza lub wskaźnika instrukcji.|
|**Identyfikator procesu**|Identyfikator procesu (PID) przebiegu profilowania.|
|**Nazwa procesu**|Nazwa procesu|
|**Nazwa modułu**|Nazwa modułu, który zawiera funkcję, linię lub wskaźnik instrukcji.|
|**Ścieżka modułu**|Ścieżka modułu zawierającego moduł, funkcję, wiersz lub wskaźnik instrukcji.|
|**Plik źródłowy**|Plik źródłowy, który zawiera definicję dla tej funkcji.|
|**Numer wiersza funkcji**|Numer wiersza początku tej funkcji w pliku źródłowym.|
|**Próbki włączne**|-Dla funkcji, liczbę próbek, w których wykonywana jest ta funkcja lub funkcja, która została wywołana przez tę funkcję; oznacza to, że liczba próbek stosu wywołań, które zawierały tę funkcję.<br />-Dla modułu, liczba próbek, w których wykonano co najmniej jedną funkcję z modułu.<br />-Dla linii lub instrukcji, liczba próbek, w których wykonano ten wiersz lub instrukcję.|
|**Próbki włączne%**|-Dla funkcji lub modułu, procent wszystkich próbek w przebiegu profilowania, które były włącznie próbkami tej funkcji lub modułu.<br />— W przypadku linii lub instrukcji, procent wszystkich próbek w profilowania, w których uruchomiono ten wiersz lub instrukcję.|
|**Próbki wyłączne**|-Dla funkcji, liczba próbek stosu wywołań, w których ta funkcja była wykonywana bezpośrednio; oznacza to, że liczba próbek, w których ta funkcja znajdowała się w górnej części stosu wywołań.<br />-Dla modułu, suma próbek wyłącznych funkcji w module.<br />-Dla linii lub instrukcji, liczba próbek, w których wykonano ten wiersz lub instrukcję.|
|**Wyłącznych próbek%**|-Dla funkcji lub modułu, procent wszystkich próbek w przebiegu profilowania, które były wyłącznymi próbkami tej funkcji lub modułu.<br />— W przypadku linii lub instrukcji, procent wszystkich próbek w profilowania, w których uruchomiono ten wiersz lub instrukcję.|

## <a name="see-also"></a>Zobacz też
- [Widok modułów-próbkowanie](../profiling/modules-view-dotnet-memory-sampling-data.md)
- [Widok modułów-Instrumentacja](../profiling/modules-view-dotnet-memory-instrumentation-data.md)
- [Widok modułów](../profiling/modules-view-instrumentation-data.md)
