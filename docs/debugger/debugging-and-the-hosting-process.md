---
title: Debugowanie i proces hostingu | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 08/01/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], hosting process
- hosting process
ms.assetid: d0f0b9a6-2a6e-463d-b6ea-9518ee727933
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 59ef28f5724c12fd9897adbaa9125bafe26beb60
ms.sourcegitcommit: 0cf1e63b6e0e6a0130668278489b21a6e5038084
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2018
ms.locfileid: "39468263"
---
# <a name="debugging-and-the-hosting-process"></a>Debugowanie i proces hostingu
Procesu hostingu Visual Studio zwiększa wydajność debugera i włącza nowe funkcje debugera, takich jak debugowanie częściowego zaufania i Obliczanie wyrażenia czasu projektowania. Jeśli chcesz, możesz wyłączyć procesu hostingu. W poniższych sekcjach opisano niektóre różnice między debugowania i bez procesu hostingu.

> [!NOTE]
> W programie Visual Studio 2017 możliwość debugowania za pomocą procesu hostingu nie jest już potrzebna i został usunięty. Aby uzyskać więcej informacji, zobacz [debugowania: Visual Studio 2017 cele do szybkości się Twój co najmniej Ulubione zadania](https://vslive.com/Blogs/News-and-Tips/2017/02/Debugging-Visual-Studio-2017-aims-to-speed-up-your-least-favorite-job.aspx).

## <a name="partial-trust-debugging-and-click-once-security"></a>Częściowego zaufania, debugowania i kliknij przycisk — raz zabezpieczeń
 Debugowanie częściowego zaufania wymaga procesu hostingu. Jeśli wyłączysz procesu hostingu, debugowanie częściowego zaufania nie będzie działać nawet, jeśli włączona jest funkcja zabezpieczeń częściowego zaufania **zabezpieczeń** strony **właściwości projektu**. Aby uzyskać więcej informacji, zobacz [porady: debugowanie aplikacji częściowej zaufania](../debugger/how-to-debug-a-partial-trust-application.md).

## <a name="design-time-expression-evaluation"></a>Obliczanie wyrażenia czasu projektowania
 Zawsze wyrażenia czasu projektowania używa procesu hostingu. Wyłączanie hostingu przetworzyć w **właściwości projektu** wyłącza Obliczanie wyrażenia czasu projektowania dla projektów biblioteki klas. Obliczanie wyrażenia czasu projektowania dla innych typów projektów nie jest wyłączone. Zamiast tego program Visual Studio uruchamia rzeczywiste pliki wykonywalne i używa go na potrzeby oceny czasu projektowania bez procesu hostingu. Różnica ta może wygenerować różne wyniki.

## <a name="appdomaincurrentdomainfriendlyname-differences"></a>Różnice AppDomain.CurrentDomain.FriendlyName
 `AppDomain.CurrentDomain.FriendlyName` Zwraca różne wyniki, w zależności od tego, czy jest włączona procesu hostingu. Jeśli wywołasz `AppDomain.CurrentDomain.FriendlyName` przy użyciu procesu hostingu włączone, zwraca *nazwa_aplikacji*`.vhost.exe`. Jeśli wywołasz ją procesu hostingu wyłączone, funkcja zwraca *nazwa_aplikacji*`.exe`.

## <a name="assemblygetcallingassemblyfullname-differences"></a>Assembly.GetCallingAssembly(). Różnice imię i nazwisko
 `Assembly.GetCallingAssembly().FullName` Zwraca różne wyniki, w zależności od tego, czy jest włączona procesu hostingu. Jeśli wywołasz `Assembly.GetCallingAssembly().FullName` przy użyciu procesu hostingu włączone, zwraca `mscorlib`. Jeśli wywołasz `Assembly.GetCallingAssembly().FullName` przy użyciu procesu hostingu wyłączone, funkcja zwraca nazwę aplikacji.

## <a name="see-also"></a>Zobacz także

- [Porady: debugowanie aplikacji częściowej relacji zaufania](../debugger/how-to-debug-a-partial-trust-application.md)