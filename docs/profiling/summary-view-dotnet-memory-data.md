---
title: Widok podsumowania — dane pamięci platformy .NET | Microsoft Docs
description: Dowiedz się, w jaki sposób widok podsumowania Wyświetla informacje o funkcjach i typach programu .NET, które przydzieliły największą ilość pamięci.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Summary view
ms.assetid: 0cb317c3-0ae6-4531-aaa8-447576eec037
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- dotnet
ms.openlocfilehash: 590705e7fb55315176d5533a9cd009784430ea4d
ms.sourcegitcommit: 18729d7c99c999865cc2defb17d3d956eb3fe35c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2021
ms.locfileid: "98722675"
---
# <a name="summary-view---net-memory-data"></a>Widok podsumowania — dane pamięci platformy .NET
Widok podsumowania zawiera informacje o funkcjach i typach programu .NET, które przydzieliły najwięcej pamięci, oraz typy, które zostały utworzone najczęściej w ramach uruchomienia profilowania. Aby uzyskać więcej informacji, w tym opis linków powiadomień i list raportów, zobacz [Widok podsumowania](../profiling/summary-view.md).

## <a name="timeline-graph"></a>Wykres osi czasu
 Wykres osi czasu w widoku Podsumowanie przedstawia wykorzystanie procesora (CPU) przez profilowaną aplikację w czasie, w którym nastąpiło profilowanie. Możesz użyć wykresu osi czasu do filtrowania widoku do wybranego przedziału czasu. Aby uzyskać więcej informacji, zobacz [How to: Filter viewss Reports from a Summary oś czasu](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).

## <a name="functions-allocating-most-memory"></a>Funkcje przydzielające najwięcej pamięci
 Wyświetla listę funkcji, które przydzieliły największą liczbę bajtów pamięci w przebiegu profilowania.

|Kolumna|Opis|
|------------|-----------------|
|**Nazwa**|Nazwa funkcji.|
|**Szybkość**|Procent wszystkich przydzielonej liczby bajtów w przebiegu profilowania, który został przydzielony przez tę funkcję lub przez funkcję podrzędną, która została wywołana przez tę funkcję.|

## <a name="types-with-most-memory-allocated"></a>Typy z największą przydzieloną ilością pamięci
 Wyświetla listę typów, dla których w przebiegu profilowania jest przydzielono największą liczbę bajtów pamięci.

|Kolumna|Opis|
|------------|-----------------|
|**Nazwa**|Nazwa typu.|
|**Szybkość**|Procent wszystkich przydzieloną bajtów w przebiegu profilowania, który został przydzielony dla tego typu.|

## <a name="types-with-most-instances"></a>Typy z większością wystąpień
 Wyświetla listę typów, które zostały utworzone najczęściej podczas przebiegu profilowania. wprowadzono

|Kolumna|Opis|
|------------|-----------------|
|**Nazwa**|Nazwa typu.|
|**Liczba**|Wartość procentowa łącznej liczby obiektów of.NET, które zostały utworzone w ramach uruchomienia profilowania, które były wystąpieniami tego typu.|

## <a name="see-also"></a>Zobacz także
- [Widok podsumowania — dane próbkowania](../profiling/summary-view-sampling-data.md)
- [Widok podsumowania — dane Instrumentacji](../profiling/summary-view-instrumentation-data.md)
