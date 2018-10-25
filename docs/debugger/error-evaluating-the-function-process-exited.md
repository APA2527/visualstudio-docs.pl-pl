---
title: 'Błąd: Proces docelowy zakończył działanie z kodem &#39;kodu&#39; podczas obliczania funkcji &#39;funkcja&#39; | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 4/06/2018
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.process_exit_during_func_eval
ms.technology: vs-ide-debug
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 98923757912d1f4619cc79c8f946aabaa531ac05
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49936267"
---
# <a name="error-the-target-process-exited-with-code-39code39-while-evaluating-the-function-39function39"></a>Błąd: Proces docelowy zakończył działanie z kodem &#39;kodu&#39; podczas obliczania funkcji &#39;— funkcja&#39;

Pełny tekst komunikatu: Proces docelowy zakończył działanie z kodem "code" podczas obliczania funkcji "function".

Aby ułatwić sprawdzić stan obiektów platformy .NET, debuger automatycznie wymusi debugowanego procesu, aby uruchomić kod dodatkowy (zwykle metody pobierającej właściwości i `ToString` funkcji). W większości przypadków te funkcje zakończona pomyślnie, lub generują wyjątki, które może zostać przechwycony przez debuger. Istnieją jednak pewne okoliczności, w których nie można przechwycić wyjątków ponieważ między granicami jądra, wymagają, przekazywanie wiadomości użytkownika lub są nie do odzyskania. Jako wynik, metoda pobierająca właściwości lub metody ToString, który jest wykonywany kod dowolna jawnie kończy proces (na przykład wywołuje `ExitProcess()`) lub zgłasza wyjątek nieobsługiwany wyjątek, który nie może zostać przechwycony (na przykład `StackOverflowException`) spowoduje przerwanie działania debugowanego procesu i zakończenie sesji debugowania. Jeśli napotkasz ten komunikat o błędzie, ten błąd wystąpił.
 
Jedną typową przyczyną tego problemu jest, że gdy debuger ocenia właściwość, która wywołuje sam siebie, może to spowodować wyjątek przepełnienia stosu. Nie można odzyskać wyjątek przepełnienia stosu i zakończy proces docelowy.
 
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd
 
Istnieją dwa możliwe rozwiązania tego problemu.
 
### <a name="solution-1-prevent-the-debugger-from-calling-the-getter-property-or-tostring-method"></a>Rozwiązanie #1: Zapobiega debuger wywołanie metody pobierającej właściwości lub metody ToString 

Komunikat o błędzie informuje o nazwę funkcji, który debuger próbował wywołać. Nazwą funkcji, możesz spróbować ponownie przeprowadzić ocenę tej funkcji z **bezpośrednie** okna, aby debugować oceny. Debugowanie jest możliwe, podczas obliczania z **bezpośrednie** okna, ponieważ w odróżnieniu od niejawne obliczanie z **Autos/zmienne lokalne/Obejrzyj** systemu windows, debuger przerywa na nieobsłużonych wyjątkach.

Jeśli zmodyfikujesz tę funkcję, można zapobiec debuger podczas wywoływania metody pobierającej lub `ToString` metody. Wypróbuj jedną z następujących czynności:
 
* Zmienić metodę na inny rodzaj kodu oprócz pobierającą właściwość lub metoda ToString i problem znikną.
    —lub—
* (Aby uzyskać `ToString`) Zdefiniuj `DebuggerDisplay` atrybut na typ, może mieć debugera oceny coś innego niż `ToString`.
    —lub—
* (Dla metody pobierającej właściwości) Umieść `[System.Diagnostics.DebuggerBrowsable(DebuggerBrowsableState.Never)]` atrybutu dla właściwości. Może to być przydatne, jeśli masz metodę, która powinna być właściwością API ze względu na zgodność, ale należy go tak naprawdę metody.

Nie można zmodyfikować tej metody, może być możliwe przerwanie procesu docelowego w instrukcji alternatywny, a następnie spróbuj ponownie oceny.
 
### <a name="solution-2-disable-all-implicit-evaluation"></a>Rozwiązanie #2: Wyłącz wszystkie bezwarunkowa ocena
 
Jeśli poprzednie rozwiązania nie rozwiązują problemu, przejdź do strony **narzędzia** > **opcje**i usuń zaznaczenie opcji **debugowanie**  >   **Ogólne** > **Włącz obliczanie właściwości i inne niejawne wywołania funkcji**. To spowoduje wyłączenie większość Obliczanie funkcji niejawnie i powinno rozwiązać problem.



  
