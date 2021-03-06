---
title: Określ wersję .NET Framework do debugowania | Microsoft Docs
description: Określ starszą wersję .NET Framework na potrzeby debugowania. Debuger programu Visual Studio obsługuje debugowanie starszych wersji .NET Framework, a także bieżącą wersję.
ms.custom: SEO-VS-2020, seodec18
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- .NET Framework, specifying version for debugging
- debugging [Visual Studio], specifying .NET Framework version
ms.assetid: 7a4893ba-4620-4774-893f-378d4ca28893
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- dotnet
ms.openlocfilehash: 197cd51d31729119d48e255d038ad2e53f17a891
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99908367"
---
# <a name="specify-an-older-net-framework-version-for-debugging-c-visual-basic-f"></a>Określ starszą wersję .NET Framework dla debugowania (C#, Visual Basic, F #)

Debuger programu Visual Studio obsługuje debugowanie starszych wersji platformy Microsoft .NET, a także bieżącą wersję. Po uruchomieniu aplikacji z programu Visual Studio debuger zawsze może zidentyfikować poprawną wersję .NET Framework dla debugowanej aplikacji. Jeśli jednak aplikacja jest już uruchomiona i rozpocznie debugowanie przy użyciu funkcji **Dołącz do**, debuger może nie zawsze identyfikować starszej wersji .NET Framework. W takim przypadku zostanie wyświetlony komunikat o błędzie z informacją,

``` cmd
The debugger has made an incorrect assumption about the .NET Framework version your application is going to use.
```

W rzadkich przypadkach, gdy ten błąd pojawia się, można ustawić klucz rejestru, aby wskazać debuger, którego wersja ma używać.

### <a name="to-specify-a-net-framework-version-for-debugging"></a>Aby określić wersję .NET Framework do debugowania

1. W katalogu Windows\Microsoft.NET\Framework Znajdź wersje .NET Framework zainstalowanych na maszynie. Numery wersji wyglądają następująco:

    `V1.1.4322`

    Zidentyfikuj poprawny numer wersji i zanotuj go.

2. Uruchom **Edytor rejestru** (regedit).

3. W **Edytorze rejestru** otwórz folder HKEY_LOCAL_MACHINE.

4. Przejdź do: HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine\\ {449EC4CC-30D2-4032-9256-EE18EB41B62B}

    Jeśli klucz nie istnieje, kliknij prawym przyciskiem myszy pozycję HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine, a następnie kliknij pozycję **nowy klucz**. Nadaj nazwę nowemu kluczowi `{449EC4CC-30D2-4032-9256-EE18EB41B62B}` .

5. Po przejściu do programu {449EC4CC-30D2-4032-9256-EE18EB41B62B} zajrzyj do kolumny **name (nazwa** ) i Znajdź klucz CLRVersionForDebugging.

   1. Jeśli klucz nie istnieje, kliknij prawym przyciskiem myszy pozycję {449EC4CC-30D2-4032-9256-EE18EB41B62B}, a następnie kliknij pozycję **Nowa wartość ciągu**. Następnie kliknij prawym przyciskiem myszy nową wartość ciągu, kliknij polecenie **Zmień nazwę** i wpisz `CLRVersionForDebugging` .

6. Kliknij dwukrotnie pozycję **CLRVersionForDebugging**.

7. W polu **Edytuj ciąg** wpisz numer wersji .NET Framework w polu **wartość** . Na przykład: V 1.1.4322

8. Kliknij przycisk **OK**.

9. Zamknij **Edytor rejestru**.

     Jeśli po rozpoczęciu debugowania nadal pojawia się komunikat o błędzie, sprawdź, czy w rejestrze wprowadzono numer wersji. Sprawdź również, czy używasz wersji .NET Framework obsługiwanej przez program Visual Studio. Debuger jest zgodny z bieżącą wersją .NET Framework i poprzednimi wersjami, ale może nie być zgodny z przyszłymi wersjami.

## <a name="see-also"></a>Zobacz też
- [Ustawienia debugera i przygotowanie](../debugger/debugger-settings-and-preparation.md)