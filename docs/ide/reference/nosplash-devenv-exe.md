---
title: -NoSplash (devenv.exe)
description: Dowiedz się, jak za pomocą przełącznika wiersza polecenia nopowitaln devenv wyświetlić ekran powitalny.
ms.custom: SEO-VS-2020
ms.date: 12/10/2018
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /NoSplash switch
- /NoSplash Devenv switch
- NoSplash Devenv switch
author: DennisLee-DennisLee
ms.author: v-dele
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e86398663ea7b6c8209d4123ab3cb12651d4491e
ms.sourcegitcommit: 967c2f8c1b3f805cf42c0246389517689d971b53
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96044001"
---
# <a name="nosplash-devenvexe"></a>/NoSplash (devenv.exe)

Zapobiega wyświetlaniu ekranu powitalnego.

## <a name="syntax"></a>Składnia

```shell
devenv /NoSplash [File1[ FileN]...]
```

## <a name="arguments"></a>Argumenty

- *File1*

  Opcjonalny. Plik do otwarcia w istniejącym wystąpieniu programu Visual Studio. Jeśli wystąpienie programu Visual Studio nie istnieje, nowe wystąpienie jest tworzone z uproszczonym układem okna, a narzędzie otwiera *plik1* w nowym wystąpieniu.

- *Plikn*

  Opcjonalny. Co najmniej jeden dodatkowy plik do otwarcia w istniejącym wystąpieniu programu Visual Studio.

## <a name="remarks"></a>Uwagi

Ten przełącznik powoduje ukrycie ekranu powitalnego. Pozostawienie tego przełącznika powoduje wyświetlenie ekranu powitalnego. Jeśli chcesz przeanalizować ekran powitalny (na przykład aby sprawdzić ikonę produktu pakietu VSPackage), użyj przełącznika [/Splash](../../extensibility/devenv-command-line-switches-for-vspackage-development.md) .

`/NoSplash`Przełącznik może być połączony z innymi przełącznikami, takimi jak [/Run](run-devenv-exe.md) lub [/DebugExe](debugexe-devenv-exe.md).

## <a name="example"></a>Przykład

Wszystkie trzy przykłady otwierają środowisko IDE bez wyświetlania ekranu powitalnego. Drugi przykład kompiluje także wybrane rozwiązanie i uruchamia skompilowany plik wykonywalny. Trzeci przykład otwiera określony plik wykonywalny do debugowania w środowisku IDE.

```shell
devenv /nosplash

devenv /nosplash /run MySolution.sln

devenv /nosplash /debugexe MySolution.exe
```

## <a name="see-also"></a>Zobacz też

- [Przełączniki wiersza polecenia Devenv](../../ide/reference/devenv-command-line-switches.md)
- [Devenv przełączniki wiersza polecenia pakietu VSPackage Development](../../extensibility/devenv-command-line-switches-for-vspackage-development.md)
