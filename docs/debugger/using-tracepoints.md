---
title: Używanie punkty śledzenia w debugerze | Microsoft Docs
ms.date: 9/17/2019
ms.topic: conceptual
helpviewer_keywords:
- tracepoints, about tracepoints
author: Sagar-S-S
ms.author: sashe
manager: AndSter
ms.workload:
- multiple
ms.openlocfilehash: 7680b305fad6f8ea1d7961ec5a70ddafd578c77d
ms.sourcegitcommit: 6993bcb0d2b0067b1b7b7899bfba52c31c70b7e7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095260"
---
# <a name="use-tracepoints-in-the-visual-studio-debugger"></a>Używanie punkty śledzenia w debugerze programu Visual Studio

Punkty śledzenia umożliwiają rejestrowanie informacji w oknie danych wyjściowych w ramach konfigurowalnych warunków bez modyfikowania lub zatrzymywania kodu. Ta funkcja jest obsługiwana dla kodu zarządzanego i natywnego, a także kilku języków, takich jak JavaScript C#i.

## <a name="let39s-take-an-example"></a>&#39;Zapoznaj się z przykładem

Poniższy przykładowy program to prosta `for` pętla ze zmienną licznika, która zwiększa się o jeden za każdym razem, gdy pętla uruchamia kolejną iterację.

![Przykład licznika](../debugger/media/counterexample.png "Przykład licznika")

## <a name="set-tracepoints-in-source-code"></a>Ustaw punkty śledzenia w kodzie źródłowym

Możesz ustawić punkty śledzenia, określając ciąg wyjściowy w obszarze pola wyboru **Akcja** w oknie **Ustawienia punktu przerwania** .

1. Aby zainicjować punkt śledzenia, najpierw kliknij odstęp po lewej stronie numeru wiersza, w którym ma zostać ustawiona wartość punkt śledzenia.

   ![Inicjowanie punktu przerwania](../debugger/media/breakpointinitialization.png "Inicjowanie punktu przerwania")

2. Umieść kursor na czerwonym kółku, a następnie kliknij ikonę koła zębatego.
3. Spowoduje to otwarcie okna **Ustawienia punktu przerwania** .

   ![Okno punktu przerwania](../debugger/media/breakpointwindow.png "Okno punktu przerwania")

4. Zaznacz pole wyboru **Akcja** .

   ![Zaznaczone akcje — pole](../debugger/media/checkedactionsbox.png "Zaznaczone akcje — pole")

   Zauważ, że czerwony okrąg zmieni się na romb wskazujący, że przełączono punkt przerwania do punkt śledzenia.

5. Wprowadź komunikat, który chcesz zalogować do pola tekstowego **Pokaż komunikat w okno dane wyjściowe** (Aby uzyskać szczegółowe informacje, zobacz sekcję w dalszej części tego artykułu).

   Punkt śledzenia jest teraz ustawiony. Naciśnij przycisk &quot;Zamknij&quot; , jeśli wszystko, co chcesz zrobić, rejestruje pewne informacje w okno dane wyjściowe.

6. Jeśli chcesz dodać warunki określające, czy wiadomość jest wyświetlana, zaznacz pole wyboru **warunki** .

   ![Pole zaewidencjonowanych warunków](../debugger/media/checkedconditionsbox.png "Pole zaewidencjonowanych warunków")

   Istnieją trzy opcje dla warunków: **Wyrażenie warunkowe**, **Filtr**i **licznik trafień**.

## <a name="actions-menu"></a>Menu Akcje

To menu umożliwia zarejestrowanie komunikatu w oknie danych wyjściowych. Wpisz ciągi, które mają być wyprowadzane w polu komunikatu (bez cudzysłowów). Jeśli chcesz wyświetlić wartości zmiennych, upewnij się, że zostały one ujęte w nawiasy klamrowe.

Na przykład, jeśli chcesz wyświetlić wartość `counter` zmiennej w konsoli wyjściowej, wpisz {Counter} w polu tekstowym komunikat.

![Komunikat wyjściowy licznika](../debugger/media/counteroutputmessage.png "Komunikat wyjściowy licznika")

Jeśli klikniesz przycisk **Zamknij** , a następnie debugujesz program (**F5**), zobaczysz następujące dane wyjściowe w oknie danych wyjściowych.

![Komunikat akcji w okno dane wyjściowe](../debugger/media/actionsmessageinoutputwindow.png "Komunikat akcji w okno dane wyjściowe")

Możesz również użyć specjalnych słów kluczowych, aby wyświetlić bardziej szczegółowe informacje. Wprowadź słowo kluczowe dokładnie tak, jak pokazano poniżej (Użyj "$" przed słowami kluczowymi i wersalikami dla samego słowa kluczowego.

| Słowo kluczowe | Co jest wyświetlane |
| --- | --- |
| $ADDRESS | Bieżąca instrukcja |
| $CALLER | Nazwa funkcji wywołującej |
| $CALLSTACK | Stos wywołań |
| $FUNCTION | Nazwa bieżącej funkcji |
| $PID | Identyfikator procesu |
| $PNAME | Nazwa procesu |
| $TID | Identyfikator wątku |
| $TNAME   | Nazwa wątku |
| $TICK | Liczba cykli (z systemu Windows GetTickCount) |

## <a name="conditions-menu"></a>Menu warunki

Warunki umożliwiają filtrowanie komunikatów wyjściowych, aby były wyświetlane tylko w określonych scenariuszach. Dostępne są trzy główne rodzaje warunków.

### <a name="conditional-expression"></a>Wyrażenie warunkowe
W przypadku wyrażenia warunkowego komunikat wyjściowy jest wyświetlany tylko wtedy, gdy są spełnione określone warunki.

W przypadku wyrażeń warunkowych można ustawić punkt śledzenia na wyjściowy komunikat, gdy określony warunek ma wartość true lub po zmianie. Na przykład, jeśli chcesz wyświetlić wartość licznika tylko w przypadku iteracji `for` pętli, możesz wybrać opcję **jest true** , a następnie wpisz `i%2 == 0` w polu tekstowym komunikat.

![Wyrażenie warunkowe jest prawdziwe](../debugger/media/conditionalexpressionistrue.png "Wyrażenie warunkowe jest prawdziwe")

Jeśli chcesz wydrukować wartość licznika podczas zmiany iteracji `for` w pętli, zaznacz opcję **kiedy zmieniono** i wpisz `i` w polu tekstowym komunikat.

![Wyrażenie warunkowe po zmianie](../debugger/media/conditionalexpressionwhenchanged.png "Wyrażenie warunkowe po zmianie")

Zachowanie opcji **gdy zmiana** jest inne dla różnych języków programowania.

- W przypadku kodu natywnego debuger nie rozważa pierwszej oceny warunku, który ma zostać zmieniony, więc nie trafi punkt śledzenia przy pierwszej ocenie.
- W przypadku kodu zarządzanego debuger trafi punkt śledzenia podczas pierwszej oceny po wybraniu opcji **zmiana** .

Aby uzyskać bardziej szczegółowy podgląd prawidłowych wyrażeń, których można użyć podczas ustawiania warunków, zobacz [wyrażenia w debugerze](expressions-in-the-debugger.md)

### <a name="hit-count"></a>Liczba trafień
Warunek liczby trafień umożliwia wysyłanie danych wyjściowych dopiero po wierszu kodu, w którym ustawiono punkt śledzenia, wykonanej określoną liczbę razy.

W polu liczba trafień można wybrać, aby wyprowadzić komunikat, gdy linia kodu, w którym ustawiono punkt śledzenia, wykonała liczbę razy równą, jest wielokrotnością lub jest większa lub równa określonej wartości liczby trafień. Wybierz opcję, która najlepiej odpowiada Twoim potrzebom, a następnie wpisz wartość całkowitą w polu (na przykład 5), która reprezentuje tę iterację.

![Liczba trafień wyrażenia warunkowego](../debugger/media/conditionalexpressionhitcount.png "Liczba trafień wyrażenia warunkowego")

### <a name="filter"></a>Filtr
Dla warunku filtru Określ, które urządzenia, procesy lub wątki będą wyświetlane.

![Filtr wyrażenia warunkowego](../debugger/media/conditionalexpressionfilter.png "Filtr wyrażenia warunkowego")

Lista wyrażeń filtrów:

- MachineName = "name"
- ProcessId = wartość
- ProcessName = "name"
- ThreadId = wartość
- ThreadName = "name"

Ujmij ciągi (takie jak nazwy) w podwójnych cudzysłowach. Wartości można wprowadzać bez cudzysłowów. Można łączyć klauzule using `&` (`AND`), `||` (`OR`), `!` (`NOT`) i nawiasów.

## <a name="considerations"></a>Uwagi

Podczas gdy punkty śledzenia mają na celu debugowanie bardziej przejrzystego i płynniejszego środowiska, istnieją pewne kwestie, o których należy pamiętać, gdy chodzi o korzystanie z nich.

Czasami, gdy sprawdzasz właściwość lub atrybut obiektu, jego wartość może się zmienić. Nie jest to błąd spowodowany przez samą funkcję punkt śledzenia, ale warto zauważyć, że użycie punkty śledzenia do sprawdzenia obiektów nie pozwala uniknąć tych przypadkowych modyfikacji.

Sposób, w jaki wyrażenia są oceniane w oknie komunikatu **akcji** , może być inny niż język aktualnie używany do programowania. Na przykład, aby wyprowadzić ciąg, nie trzeba zawijać wiadomości w cudzysłowie, nawet jeśli podczas korzystania z `Debug.WriteLine()` lub. `console.log()` Ponadto składnia nawiasów klamrowych (`{ }`) do wyrażeń wyjściowych może być również inna niż Konwencja do wyprowadzania wartości w języku deweloperskim. (Jednak zawartość w nawiasach klamrowych (`{ }`) powinna być nadal zapisywana przy użyciu składni języka programowania).

## <a name="see-also"></a>Zobacz także

- [Co to jest debugowanie?](../debugger/what-is-debugging.md)
- [Tworzenie lepszych C# kodu za pomocą programu Visual Studio](../debugger/write-better-code-with-visual-studio.md)
- [Pierwsze spojrzenie na profilowanie](../debugger/debugger-feature-tour.md)
- [Wyrażenia w debugerze](expressions-in-the-debugger.md)
- [Używanie punktów przerwania](../debugger/using-breakpoints.md)