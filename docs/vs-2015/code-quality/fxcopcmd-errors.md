---
title: błędy FxCopCmd
ms.date: 10/19/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
helpviewer_keywords:
- FxCopCmd errors
ms.author: gewarren
author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 71e2a39b792dcc5a01eb28611664736f6620bb1f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685939"
---
# <a name="fxcopcmd-tool-errors"></a>Fxcopcmd — błędy narzędzi

Fxcopcmd — nie należy wziąć pod uwagę wszystkie błędy jako krytyczny. Jeśli FxCopCmd ma wystarczające informacje, aby przeprowadzić analizę częściowe, wykonuje błędów analizy i raporty, które wystąpiły. Kod błędu, który jest 32-bitową liczbę całkowitą, zawiera bitowa kombinacja wartości liczbowe, które odnoszą się do błędów.

W poniższej tabeli opisano kody błędów zwracane przez polecenia FxCopCmd:

|Błąd|Wartość liczbowa|
|-----------|-------------------|
|Brak błędów|0x0|
|Błąd analizy|0x1|
|Wyjątki od reguły|0x2|
|Błąd ładowania projektu|0x4|
|Błąd ładowania zestawu|0x8|
|Błąd ładowania biblioteki reguły|0x10|
|Błąd ładowania raportu importu|0x20|
|Błąd danych wyjściowych|0x40|
|Błąd przełącznik wiersza polecenia|0x80|
|Błąd podczas inicjowania|0x100|
|Błąd odwołania do zestawu|0x200|
|BuildBreakingMessage|0x400|
|Nieznany błąd|0x1000000|

**Błąd analizy** jest zwracany w przypadku błędów krytycznych. Wskazuje, że nie można wykonać analizy. Jeśli ma to zastosowanie, kod błędu zawiera także podstawową przyczyną błędu krytycznego. Następujące warunki generować błędy krytyczne:

- Nie można wykonać analizy ze względu na niewystarczające dane wejściowe.

- Analiza zgłosiła wyjątek, który nie jest obsługiwany przez FxCopCmd.

- Plik projektu nie można odnaleźć lub jest uszkodzony.

- Nie określono opcji output lub nie można zapisać pliku.

> [!NOTE]
> Kod powrotny polecenia FxCopCmd **błąd odwołuje się zestaw** 0x200 przez siebie to ostrzeżenie, a nie błąd. Ten kod powrotny wskazuje, że zawierają odwołania pośrednie niejedna FxCopCmd mógł je obsłużyć. Ostrzeżenie oznacza, że istnieje możliwość, że niektóre wyniki analizy mogą zabezpieczenia mogły zostać naruszone. Traktuj **błąd odwołuje się zestaw** jako błąd, w połączeniu z innymi kod powrotny.

## <a name="see-also"></a>Zobacz także

- [Błędy zgłaszane przez aplikację do analizy kodu](../code-quality/code-analysis-application-errors.md)