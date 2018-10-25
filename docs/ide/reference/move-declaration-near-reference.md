---
title: Przenieś deklarację zmiennej blisko odwołania w programie Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: e8587b7bd94f85f40371a211af82661030e3f288
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49908189"
---
# <a name="move-declaration-near-reference-refactoring"></a>Przenoszenie deklaracji blisko odwołania refaktoryzacji

Ta Refaktoryzacja mają zastosowanie do:

- C#

**Co:** pozwala na przechodzenie bliżej deklaracje zmiennych do ich użycia.

**Kiedy:** masz deklaracji zmiennych, które mogą znajdować się w węższy zakres.

**Dlaczego:** może ona pozostaw, ponieważ istnieje, ale mogą powodować problemy czytelność lub ukrywanie informacji. Jest to możliwość refaktoryzacji w celu poprawienia czytelności.

## <a name="how-to"></a>Instrukcje

1. Umieść kursor w deklaracji zmiennej.

1. Następnie wykonaj jedną z następujących czynności:

   - **Keyboard**
      - Naciśnij klawisz **Ctrl**+**.** wyzwalacz **szybkie akcje i Refaktoryzacje** menu, a następnie wybierz **przenoszenie deklaracji blisko odwołania** z menu podręcznego okna podglądu.
   - **Myszy**
      - Kliknij prawym przyciskiem myszy ten kod, wybierz **szybkie akcje i Refaktoryzacje** menu, a następnie wybierz **przenoszenie deklaracji blisko odwołania** z menu podręcznego okna podglądu.

1. Po zakończeniu zmiany, naciśnij klawisz **Enter** lub kliknij poprawki w menu, a zmiany zostaną zatwierdzone.

Przykład:

```csharp
// Before
int x;
if (condition)
{
    x = 1;
    Console.WriteLine(x);
}

// Move declaration near reference

// After
if (condition)
{
    int x = 1;
    Console.WriteLine(x);
}
```

## <a name="see-also"></a>Zobacz także

- [Refaktoryzacja](../refactoring-in-visual-studio.md)
- [Podgląd zmian](../../ide/preview-changes.md)