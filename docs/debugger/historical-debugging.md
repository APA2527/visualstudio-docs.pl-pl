---
title: Debugowanie historyczne | Microsoft Docs
description: Rozwiązywanie problemów z aplikacją przez sprawdzenie jej stanu podczas przesuwania do tyłu i do przodu przez jej wykonanie. IntelliTrace zbiera informacje dotyczące tej funkcji.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7cc5ddf2-2f7c-4f83-b7ca-58e92e9bfdd2
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: c4a6bf07cc7905fc48bcc82c8b38fa5b6f6e7cfa
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99904409"
---
# <a name="historical-debugging-c-visual-basic-c"></a>Debugowanie historyczne (C#, Visual Basic, C++)

Debugowanie historyczne jest trybem debugowania, który zależy od informacji zbieranych przez IntelliTrace. Umożliwia przejście do tyłu i do przodu przez wykonanie aplikacji i sprawdzenie jej stanu.

 Możesz użyć IntelliTrace w wersji Visual Studio Enterprise (ale nie wersji Professional lub Community).

## <a name="why-use-historical-debugging"></a>Dlaczego warto używać debugowania historycznego?

 Ustawienie punktów przerwania w celu znalezienia usterek może być Affair trafień lub chybień. Punkt przerwania jest ustawiany blisko miejsca w kodzie, w którym podejrzewasz, że usterka jest uruchamiana, a następnie uruchom aplikację w debugerze i polubisz, że punkt przerwania zostanie osiągnięty, i że miejsce, gdzie wykonywanie przerw w działaniu może ujawnić Źródło błędu. W przeciwnym razie trzeba będzie spróbować ustawić punkt przerwania w innym miejscu kodu i ponownie uruchomić debuger, wykonując kroki testu w trybie failover i aż do momentu znalezienia problemu.

 ![Ustawianie punktu przerwania](../debugger/media/breakpointprocesa.png "BreakpointProcesa")

 Można użyć IntelliTrace i debugowania historycznego, aby poruszać się w aplikacji i sprawdzać stan (stos wywołań i zmienne lokalne) bez konieczności ustawiania punktów przerwania, ponownego uruchomienia debugowania i powtarzania kroków testu. Pozwala to zaoszczędzić dużo czasu, szczególnie w przypadku, gdy błąd znajduje się w scenariuszu testowym, który zajmuje dużo czasu na wykonanie.

## <a name="how-do-i-start-using-historical-debugging"></a>Jak mogę rozpocząć korzystanie z debugowania historycznego?

IntelliTrace jest domyślnie włączona. Wszystko, co musisz zrobić, decyduje o tym, które zdarzenia i wywołania funkcji są interesujące dla użytkownika oraz czy chcesz wyświetlić migawki pełnego stanu aplikacji. Aby uzyskać więcej informacji na temat definiowania elementów, które chcesz wyszukać, zobacz [IntelliTrace Features](../debugger/intellitrace-features.md). Obsługa funkcji różni się w zależności od języka i typu aplikacji.

- Aby wyświetlić migawki z debugowaniem historycznym, zobacz [Inspekcja poprzednich stanów aplikacji przy użyciu IntelliTrace](../debugger/view-historical-application-state.md)
- Aby dowiedzieć się, jak zbadać zmienne i poruszać się po kodzie, zobacz [Inspekcja aplikacji za pomocą debugowania historycznego](../debugger/historical-debugging-inspect-app.md)
- Aby dowiedzieć się więcej na temat debugowania ze zdarzeniami IntelliTrace, zobacz [Przewodnik: korzystanie z IntelliTrace](../debugger/walkthrough-using-intellitrace.md).