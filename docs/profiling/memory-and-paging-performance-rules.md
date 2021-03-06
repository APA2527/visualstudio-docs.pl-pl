---
title: Reguły wydajności pamięci i stronicowania | Microsoft Docs
description: Dowiedz się, w jaki sposób reguły wydajności w kategorii pamięć i stronicowanie identyfikują aktywność stronicowania w przebiegu profilowania, który może mieć wpływ na wydajność aplikacji i czas odpowiedzi.
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f37972b2-efe4-4a1c-a5d1-a246ccd76817
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: e1cddda12fbb67f9b604186e754146558cdd62ee
ms.sourcegitcommit: 18729d7c99c999865cc2defb17d3d956eb3fe35c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2021
ms.locfileid: "98720608"
---
# <a name="memory-and-paging-performance-rules"></a>Reguły wydajności pamięci i stronicowania
Reguły wydajności w kategorii pamięć i stronicowanie identyfikują aktywność stronicowania w przebiegu profilowania, który może mieć wpływ na wydajność aplikacji i czas odpowiedzi.

|Reguła|Opis|
|-|-|
|[DA0014: Skrajnie intensywne stronicowanie aktywnej pamięci na dysk](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md)|Bardzo wysoki wskaźnik stronicowania aktywnej pamięci na i z dysku wystąpił w trakcie przebiegu profilowania. Stawki stronicowania na tym poziomie mają zwykle wpływ na wydajność aplikacji i czas odpowiedzi. Rozważ zmniejszenie alokacji pamięci przez skorygowanie algorytmów. Może być również konieczne uwzględnienie wymagań dotyczących pamięci aplikacji. Spróbuj ponownie uruchomić profilowanie na komputerze z większą ilością pamięci. Ta zasada jest wyzwalana, gdy ilość aktywności stronicowania przekroczy górny próg reguły D0017.|
|[DA0017: Intensywne stronicowanie aktywnej pamięci na dysk](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|Relatywnie wysoki współczynnik stronicowania aktywnej pamięci do i z dysku wystąpił w trakcie przebiegu profilowania. Stawki stronicowania na tym poziomie mają zwykle wpływ na wydajność aplikacji i czas odpowiedzi. Rozważ zmniejszenie alokacji pamięci przez skorygowanie algorytmów. Może być również konieczne uwzględnienie wymagań dotyczących pamięci aplikacji. Spróbuj ponownie uruchomić profilowanie na komputerze z większą ilością pamięci.|
