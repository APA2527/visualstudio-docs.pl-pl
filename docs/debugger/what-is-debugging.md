---
title: Co to jest debugowanie?
description: Zrozumienie, co oznacza debugować aplikację
ms.custom: debug-experiments
ms.date: 10/17/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugger
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7cd96d61718972c82c6002888e123003530c019c
ms.sourcegitcommit: 331dbb12e11fcd7f5d15fab05f3c861e48126e43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2018
ms.locfileid: "51826664"
---
# <a name="what-is-debugging"></a>Co to jest debugowanie?

Debuger programu Visual Studio jest zaawansowanym narzędziem. Przed pokazujemy, jak z niej korzystać, chcemy, aby można było mówić o niektórych warunków, takich jak *debugera*, *debugowania*, i *tryb debugowania*. W ten sposób odnosimy później wyszukując i naprawiając usterki, firma Microsoft będzie mówić tak samo.

## <a name="debugger-vs-debugging"></a>Debuger i debugowanie

Termin *debugowania* jest dość ogólny i może oznaczać wiele różnych rzeczy. W najbardziej literału użycia wyrazu oznacza to, usuwania usterek w kodzie. Teraz istnieje wiele sposobów, aby to zrobić. Na przykład debug przez zeskanowanie kodu szuka literówki lub za pomocą analizator kodu. Może debugować kod, za pomocą profilera wydajności. Lub może debugować przy użyciu *debugera*.

Debuger jest narzędziem bardzo wyspecjalizowany dla deweloperów. Debuger dołączony do uruchomionej aplikacji i umożliwia inspekcję swój kod. W dokumentacji debugowania programu Visual Studio jest to zazwyczaj co mamy na myśli gdy mówimy "debugowanie".

## <a name="debug-mode-vs-running-your-app"></a>Debugowanie trybu w porównaniu z tą aplikacją

Po uruchomieniu aplikacji w programie Visual Studio po raz pierwszy, może uruchomić ją, naciskając przycisk zielona strzałka ![Rozpocznij debugowanie](../debugger/media/dbg-tour-start-debugging.png "Rozpocznij debugowanie") na pasku narzędzi. Domyślnie **debugowania** wartość znajduje się w rozwijanej po lewej stronie. Jeśli jesteś nowym użytkownikiem programu Visual Studio, to pozostawienie wrażenie, że debugowanie aplikacji ma coś zrobić z uruchomioną aplikację — którego jest--, ale są one całkowicie dwóch zupełnie inne zadania.

![Wybierz kompilację debugowania](../debugger/media/what-is-debugging-debug-build.png)

A **debugowania** wartość wskazuje konfiguracji debugowania. Po uruchomieniu aplikacji (naciśnij klawisz zieloną strzałkę lub **F5**) w konfiguracji debugowania, możesz uruchomić aplikację w *tryb debugowania*, co oznacza, że używasz aplikacji załączonym debuggerze. Dzięki temu pełny zestaw funkcji służących do znajdowania usterek w aplikacji do debugowania.

Jeśli jest otwarty projekt, wybierz selektorze listy rozwijanej, w którym jest wyświetlany komunikat **debugowania** i wybierz polecenie **wersji** zamiast tego.

![Wybierz kompilację wydania](../debugger/media/what-is-debugging-release-build.png)

Gdy przełączysz to ustawienie, możesz zmienić projekt z konfiguracji debugowania, konfiguracja wydania. Projektów programu Visual Studio mają oddzielnych wersji i konfiguracji programu do debugowania. Kompilujesz wersję debugera do debugowania i wersję zwolnienia do ostatecznej dystrybucji zwolnienia. Kompilacja wydania jest zoptymalizowana pod kątem wydajności, ale Kompilacja debugowania jest lepszym rozwiązaniem dla debugowania.

## <a name="when-to-use-a-debugger"></a>Kiedy należy używać w debugerze

Debuger to podstawowe narzędzie do znajdowania i rozwiązywania usterek w aplikacjach. Kontekst jest najważniejsza i ważne jest, aby wykorzystać wszystkie narzędzia w swojej jednorazowe ułatwiające szybkie usunięcia usterki lub błędy. Czasami po prawej stronie "narzędzia" może być rozwiązaniem lepiej kodowania. Dzięki informacjom, kiedy należy używać debugera, a inne narzędzie, zostanie też nauczysz się bardziej efektywne wykorzystanie debugera. Jeśli już znasz, potrzebujesz więcej informacji dotyczących debugera, zobacz [debugowania dla początkujących](../debugger/debugging-absolute-beginners.md). W przeciwnym razie kliknij link w **następne kroki**.

## <a name="next-steps"></a>Następne kroki

W tym artykule wyjaśniono kilka ogólnych pojęć debugowania. Następnie można uruchomić uczenia sposób debugowania w programie Visual Studio oraz pisania kodu z mniej błędów. Poniższy artykuł przedstawia C# przykłady kodu, ale pojęcia dotyczą wszystkich językach obsługiwanych przez program Visual Studio.

> [!div class="nextstepaction"]
> [Tworzenie lepszych C# kodu za pomocą programu Visual Studio](../debugger/write-better-code-with-visual-studio.md)
