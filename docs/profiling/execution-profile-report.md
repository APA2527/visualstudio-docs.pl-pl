---
title: Raport profilu wykonywania | Microsoft Docs
description: Zapoznaj się z raportem profil wykonywania, który jest tradycyjnym profilem próbkowania w rozszerzeniu Concurrency Visualizer dla programu Visual Studio.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.report.execution
helpviewer_keywords:
- Concurrency Visualizer, Execution Profile Report
ms.assetid: c8128472-a8ed-46f4-b1c8-a25358d6f2c1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 98361f9abad40e447d7198265d21ef193bb9ddf5
ms.sourcegitcommit: 589d96700208bf22c8da9e26a1d2041fbf39b8f9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98801382"
---
# <a name="execution-profile-report"></a>Raport profilu wykonania
Raport profil wykonywania jest tradycyjnym profilem próbkowania. Próbki są pobierane około co milisekundy w czasie, gdy wątek jest uruchomiony na rdzeniu logicznym, a Wizualizator współbieżności tworzy typowe drzewo wywołań przez zsumowanie skumulowanego zestawu przykładowych stosów. Do danych w tej tabeli może wpływ bieżący zakres czasu i ukryte wątki oraz następujące filtry, które mogą być stosowane:

- Jeśli Tylko mój kod jest zaznaczone, wyświetlane są tylko ramki stosu, które mają kod użytkownika i jeden poziom poniżej kodu użytkownika.

- Jeśli ustawiona jest wartość redukcja szumów, wysortowane stosy, które mają mniej niż określona częstotliwość, są filtrowane z raportu.

  W poniższej tabeli przedstawiono kolumny w raporcie.

|Kolumna|Opis|
|------------|-----------------|
|Nazwa|Nazwa funkcji dla każdego poziomu stosu wywołań.|
|Próbki włączne|Łączna liczba próbek zebranych dla wszystkich stosów, które są rzutowane na ten poziom drzewa stosu wywołań. Liczba włącznie jest sumą próbek wyłącznych dla tej funkcji i liczników włącznie dla wszystkich jej węzłów podrzędnych.|
|Próbki wyłączne|Łączna Liczba zebranych próbek, dla których ta funkcja jest najniższym poziomem stosu wywołań.|
|% Włącznie|Procent łącznych próbek pokazywanych w kolumnie próbki włączne. Wartości procentowe są zaokrąglane do dwóch miejsc po przecinku.|
|% Wyłącznego|Procent łącznych próbek pokazywanych w kolumnie próbki wyłączne. Wartości procentowe są zaokrąglane do dwóch miejsc po przecinku.|
|Szczegóły|W pełni kwalifikowana nazwa funkcji. Obejmuje to liczbę wierszy, gdy jest dostępna.|

 Ta tabela raportu może być widoczna w widoku [czasu wykonywania (Widok wątków)](../profiling/execution-time-threads-view.md) .

## <a name="see-also"></a>Zobacz także
- [Widok wątków](../profiling/threads-view-parallel-performance.md)