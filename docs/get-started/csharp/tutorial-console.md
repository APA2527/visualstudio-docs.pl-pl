---
title: 'Samouczek: Rozpoczynanie pracy z usługą C# aplikacji konsoli'
description: Dowiedz się, jak w programie Visual Studio krok po kroku dotyczące tworzenia aplikacji konsolowej C#.
ms.custom: seodec18, get-started
ms.date: 12/12/2018
ms.technology: vs-ide-general
ms.prod: visual-studio-dev15
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 333eeb3f826663d979e1cec444ede7eda4b55b2a
ms.sourcegitcommit: 35bebf794f528d73d82602e096fd97d7b8f82c25
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/18/2018
ms.locfileid: "53562220"
---
# <a name="tutorial-get-started-with-a-c-console-app-in-visual-studio"></a>Samouczek: Wprowadzenie do aplikacji konsolowej C# w programie Visual Studio

W ramach tego samouczka dla języka C#, użyjesz programu Visual Studio do tworzenia i uruchomisz aplikację konsoli i zapoznaj się z niektórymi funkcjami [środowiska zintegrowanego rozwoju Visual Studio (IDE)](../visual-studio-ide.md) podczas możesz to zrobić.

Jeśli jeszcze nie zainstalowano programu Visual Studio, przejdź do strony [program Visual Studio pobiera](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) strony, aby zainstalować go za darmo.

## <a name="create-a-project"></a>Tworzenie projektu

Aby rozpocząć, utworzymy C# projekt aplikacji. Typ projektu jest dostarczany z wszystkie pliki szablonu, które będą potrzebne, zanim dodaniu jeszcze nic!

1. Otwórz program Visual Studio 2017.

2. Na pasku menu u góry wybierz **pliku** > **New** > **projektu**.

3. W **nowy projekt** okno dialogowe w okienku po lewej stronie rozwiń **C#**, a następnie wybierz **platformy .NET Core**. W środkowym okienku wybierz **Aplikacja konsoli (.NET Core)**. Następnie Nazwij plik *Kalkulator*.

   ![Szablon projektu aplikacji (.NET Core) w oknie dialogowym Nowy projekt w programie Visual Studio IDE konsoli](./media/new-project-csharp-calculator-console-app.png)

### <a name="add-a-workgroup-optional"></a>Dodaj grupy roboczej (opcjonalnie)

Jeśli nie widzisz **Aplikacja konsoli (.NET Core)** szablon projektu, możesz ją uzyskać, dodając **programowanie dla wielu platform .NET Core** obciążenia. Aby dowiedzieć się, jak to zrobić, zobacz "[co to jest obciążenie i jak jedną dodać?](#workload)" sekcja w często zadawanych PYTAŃ.

## <a name="create-the-app"></a>Tworzenie aplikacji

Najpierw dodamy kod, aby utworzyć podstawowy kalkulatora. Firma Microsoft będzie następnie dostosować kod, aby dodać funkcje. Po tym możemy debugować aplikację, aby znaleźć i naprawić błędy. Na koniec mamy uściślić kod, aby bardziej wydajne.

Zacznijmy od dodania kodu podstawowego Kalkulator do projektu.

1. W edytorze kodu należy usunąć domyślny kod "Hello World".

    ![Usuń domyślnego kodu Hello World z nowej aplikacji Kalkulator](./media/csharp-console-calculator-deletehelloworld.png)

   Ściślej mówiąc Usuń cały kod, który zostanie wyświetlony w edytorze kodu.

1. Wprowadź lub wklej następujący kod do nowego edytora kodu:

    ```csharp
    using System;

    namespace Calculator
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Declare variables and then initialize to zero
                int num1 = 0; int num2 = 0;

                // Display title as the C# console calculator app
                Console.WriteLine("Console Calculator in C#\r");
                Console.WriteLine("------------------------\n");

                // Ask the user to type the first number
                Console.WriteLine("Type a number, and then press Enter");
                num1 = Convert.ToInt32(Console.ReadLine());

                // Ask the user to type the second number
                Console.WriteLine("Type another number, and then press Enter");
                num2 = Convert.ToInt32(Console.ReadLine());

                // Ask the user to choose an option
                Console.WriteLine("Choose an option from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                // Use a switch statement to do the math
                switch (Console.ReadLine())
                {
                    case "a":
                        Console.WriteLine($"Your result: {num1} + {num2} = " + (num1 + num2));
                        break;
                    case "s":
                        Console.WriteLine($"Your result: {num1} - {num2} = " + (num1 - num2));
                        break;
                    case "m":
                        Console.WriteLine($"Your result: {num1} * {num2} = " + (num1 * num2));
                        break;
                    case "d":
                        Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                        break;
                }
                // Wait for the user to respond before closing
                Console.Write("Press any key to close the Calculator console app...");
                Console.ReadKey();
            }
        }
    }
    ```
1. Wybierz **Kalkulator** Aby uruchomić program, lub naciśnij **F5**.

   ![Wybierz przycisk Kalkulator, aby uruchomić aplikację z paska narzędzi](./media/csharp-console-calculator-button.png)

   Zostanie otwarte okno konsoli.

1. Wyświetlanie aplikacji w oknie konsoli, a następnie postępuj zgodnie z monitami, aby dodać numery **42** i **119**.

   Aplikacja powinna wyglądać na poniższym zrzucie ekranu:

    ![Aplikacja Kalkulator wyświetlana w oknie konsoli i zawiera monity w przypadku których akcje do wykonania](./media/csharp-console-calculator.png)

### <a name="add-decimals"></a>Dodaj liczbę miejsc dziesiętnych

Aplikacja Kalkulator obecnie akceptuje i zwraca wartość liczby całkowite. Jednak będzie bardziej precyzyjne możemy dodać kod, który pozwala na liczbę miejsc dziesiętnych.

Tak jak w poniższym zrzucie ekranu Jeśli Uruchom aplikację i podzielić liczbę 42 numerem 119 wynik Twojego jest 0 (zero), nie jest dokładne.

![Okna konsoli, w wyniku przedstawiający ruchów aplikacji Kalkulator, która nie zwraca wartości dziesiętnej](./media/csharp-console-calculator-nodecimal.png)

Możemy naprawić kod tak, że obsługuje ona liczbę miejsc dziesiętnych.

1. Zmienić każde wystąpienie `int` zmienną `float`.

   (Możesz użyć [Znajdź i Zamień](../../ide/finding-and-replacing-text.md#find-and-replace-control) formantu, aby ułatwić to zadanie. Aby uzyskać dostęp do formantu wyszukiwania w edytorze kodu, naciśnij klawisz **Crtl**+**F**. Następnie wybierz **Znajdź następny** przycisk lub **Find Previous** przycisku na kontrolce wyszukiwania. Aby przejść do opcji zastępowania, kliknij przycisk Dalej, aby **znaleźć** pola tekstowego. Aby wykonywać jedną zamianę naraz, wybierz opcję **Zamień następny** znajdujący się obok **Zastąp** pola tekstowego. Aby zamienić wszystkie dopasowania, wybierz opcję **Zamień wszystkie** przycisku.)

1. Ponownie uruchom aplikację Kalkulator, a następnie Podziel liczbę **42** przez liczbę **119**.

   Należy zauważyć, że aplikacja zwraca teraz liczb dziesiętnych zamiast zero.

    ![Okno konsoli przedstawiający aplikację Kalkulator, która teraz Zwraca ułamek dziesiętny liczb w wyniku](./media/csharp-console-calculator-decimal.png)

Jednak aplikacja generuje dziesiętna wynik. Upewnijmy się kilka więcej atrakcji w kodzie, dzięki czemu aplikacja może obliczyć liczbę miejsc dziesiętnych zbyt.

1. Zmienić każde wystąpienie `float` zmienną `double`.

1. Zmienić każde wystąpienie `Convert.ToInt32` metody `Convert.ToDouble`.

1. Uruchom aplikację Kalkulator, a następnie Podziel liczbę **42,5** przez liczbę **119.75**.

   Należy zauważyć, że aplikacja teraz akceptuje wartości dziesiętnych i zwraca dłużej cyfry dziesiętnej jako wynik.

    ![Okno konsoli aplikacji Kalkulator, która teraz przyjmuje liczb dziesiętnych i zwraca dłużej liczb dziesiętnych w wyniku](./media/csharp-console-calculator-usedecimals.png)

    (Naprawimy liczbę miejsc dziesiętnych w [Popraw kod](#revise-the-code) sekcji.)

## <a name="debug-the-app"></a>Debugowanie aplikacji

Udoskonaliliśmy nasza aplikacja Kalkulator podstawowego, ale go nie ma jeszcze failsafes w celu obsługi wyjątków, takie jak błędy danych wejściowych użytkownika.

Na przykład, jeśli zostanie podjęta próba dzielenia liczby przez zero, lub wprowadź znaków alfanumerycznych, gdy aplikacja oczekuje, że znak numeryczny (lub odwrotnie), aplikacja przestaje działać i zwraca błąd.

Teraz omówimy kilka typowych błędów danych wejściowych użytkownika, zlokalizuj je w [debugera](../../debugger/debugger-feature-tour.md)i rozwiąż je w kodzie.

### <a name="fix-the-divide-by-zero-error"></a>Napraw błąd "dzielenie przez zero"

Próba dzielenia liczby przez zero zawiesza się aplikacja konsoli. Program Visual Studio następnie dowiesz się, czym jest problem w edytorze kodu.

   ![Edytor kodu programu Visual Studio pokazuje błąd dzielenia przez zero](./media/csharp-console-calculator-dividebyzero-error.png)

Zmieńmy kod służący do obsługi tego błędu.

1. Usuń kod, który pojawia się bezpośrednio między `case "d":` i komentarz, który jest wyświetlany komunikat `// Wait for the user to respond before closing`.

1. Zastąp go następującym kodem:

   ```csharp
            // Ask the user to enter a non-zero divisor until they do so
                while (num2 == 0)
                {
                    Console.WriteLine("Enter a non-zero divisor: ");
                    num2 = Convert.ToInt32(Console.ReadLine());
                }
                Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                break;
        }
    ```

   Po dodaniu kodu sekcji z `switch` instrukcji powinien wyglądać podobnie do poniższej zrzut ekranu:

   ![W sekcji poprawione "switch" w edytorze kodu programu Visual Studio](./media/csharp-console-calculator-switch-code.png)

Teraz gdy dowolna liczba jest dzielenie przez zero, aplikacji poprosi o inny numer. Nawet lepiej: Nie będzie zatrzymać, pytaniem, dopóki nie podasz różna od zera.

   ![Edytor kodu programu Visual Studio pokazuje błąd dzielenia przez zero](./media/csharp-console-calculator-dividebyzero.png)

### <a name="fix-the-format-error"></a>Napraw błąd "format"

Jeśli wprowadzasz znaków alfanumerycznych, gdy aplikacja oczekuje, że znak numeryczny (lub odwrotnie), zawiesza się z aplikacji konsoli. Program Visual Studio następnie dowiesz się, czym jest problem w edytorze kodu.

   ![Edytor kodu programu Visual Studio pokazuje błąd formatu.](./media/csharp-console-calculator-format-error.png)

Aby naprawić ten błąd, możemy refaktoryzować kod, który wcześniej wpisano.

#### <a name="revise-the-code"></a>Popraw kod

Zamiast polegać na `program` klasy do obsługi całego kodu, firma Microsoft będzie podzielić naszą aplikację dwóch klas: `calculator` i `program`.  

`calculator` Klasy będzie obsługiwać większość pracy obliczeń i `program` klasy będzie obsługiwać interfejs użytkownika i przechwytywania błędów pracy.

Zaczynajmy.

1. Usuń wszystko, czego *po* poniższy blok kodu:

    ```csharp

    using System;

    namespace Calculator
    {

    ```

1. Następnie dodaj nową `calculator` klasy w następujący sposób:

    ```csharp
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    ```

1. Następnie należy dodać nowy `program` klasy w następujący sposób:

    ```csharp
    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
    ```
1. Wybierz **Kalkulator** Aby uruchomić program, lub naciśnij **F5**.

1. Postępuj zgodnie z monitami i podzieleniu **42** przez liczbę **119**. Aplikacja powinna wyglądać podobnie do następującego:

    ![Okno konsoli wycofanej aplikacji Kalkulator, która zawiera monity, na którym akcje do wykonania i obsługi błędów dla nieprawidłowe dane wejściowe](./media/csharp-console-calculator-refactored.png)

    Należy zauważyć, że masz opcję, aby wprowadzić więcej równania, dopóki nie wybierzesz zamknąć aplikację konsoli. A także zmniejszyliśmy liczbę miejsc dziesiętnych, w wyniku.

## <a name="close-the-app"></a>Zamknij aplikację

1. Jeśli jeszcze tego nie zrobiono, należy zamknąć aplikację kalkulatora.

1. Zamknij **dane wyjściowe** okienko w programie Visual Studio.

   ![Zamknij okienko danych wyjściowych w programie Visual Studio](./media/csharp-calculator-close-output-pane.png)

1. W programie Visual Studio, naciśnij klawisz **Ctrl**+**S** można zapisać aplikacji.

1. Zamknij program Visual Studio.

## <a name="code-complete"></a>Kompletności kodu

Podczas tego tutortial Wprowadziliśmy wiele zmian do aplikacji kalkulatora. Aplikacja wydajniej teraz obsługuje zasobów obliczeniowych i obsługuje on większość błędów danych wejściowych użytkownika.

Oto kompletny kod w jednym miejscu:

```csharp

using System;

namespace Calculator
{
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
}

```

## <a name="quick-answers-faq"></a>Szybkie odpowiedzi na często zadawane pytania

Poniżej przedstawiono listę często zadawanych PYTAŃ szybkiego aby zaznaczyć kilka podstawowych pojęć. Często zadawane pytania obejmuje również odpowiedzi na pytania, które mogą się po wykonaniu procedury w tym samouczku.

### <a name="what-is-c"></a>Co to jest C#?

C# to bezpieczny typowo język programowania, który działa w .NET Framework i .NET Core. Za pomocą języka C# można utworzyć Windows aplikacji, aplikacji typu klient serwer, aplikacji baz danych, sieci Web XML usług, rozpowszechnianych komponentów i więcej.

### <a name="what-is-visual-studio"></a>Co to jest program Visual Studio?

Program Visual Studio jest zintegrowanego rozwoju pakietu narzędzi zwiększających produktywność dla deweloperów. Go traktować jako program, który służy do tworzenia aplikacji i programów.

### <a name="what-is-a-console-app"></a>Co to jest aplikacją konsoli?

Aplikacja konsoli akceptuje dane wejściowe i wyświetla dane wyjściowe w oknie wiersza polecenia, zwanego również Konsola.

### <a name="what-is-net-core"></a>Co to jest .NET Core?

Platforma .NET core to ewolucyjny następnym krokiem programu .NET Framework. Gdzie programu .NET Framework mogą pozwala na udostępnianie kodu w językach programowania .NET Core dodaje możliwość udostępniania kodu między platformami. Jeszcze lepiej jest "open source".

(.NET Framework i .NET Core zawierają biblioteki, funkcji wbudowanych. Te aktualizacje obejmują również środowisko uruchomieniowe języka wspólnego (CLR), który działa jako maszynę wirtualną, w którym ma być uruchamiany w kodzie.)

### <a id="workload"></a>Co to jest obciążenie i jak jedną dodać?

Obciążenia w programie Visual Studio reprezentuje zestaw programistycznych, opcji i szablony, które umożliwiają dostosowanie instalacji programu Visual Studio. Obciążenie instaluje tylko narzędzia potrzebne do programowania języka i wybranej platformy. Poniżej przedstawiono sposób je zainstalować.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Opcja 1: Użyj okna dialogowego Nowy projekt

1. Wybierz **Otwórz Instalator programu Visual Studio** łącze w okienku po lewej stronie **nowy projekt** okno dialogowe.

   ![Wybierz łącze Otwórz Instalator programu Visual Studio z okna dialogowego Nowy projekt](./media/csharp-open-visual-studio-installer-generic-dark.png)

1. Uruchamia Instalatora programu Visual Studio. Wybierz **programowanie dla wielu platform .NET Core** obciążenia, a następnie wybierz **Modyfikuj**.

   ![Obciążenia programowanie dla wielu platform .NET core w Instalatorze programu Visual Studio](./media/dot-net-core-xplat-dev-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>Opcja 2: Użyj paska menu Narzędzia

1. Anuluj poza **nowy projekt** okna dialogowego pole, a następnie na pasku menu u góry wybierz **narzędzia** > **Pobierz narzędzia i funkcje**.

1. Uruchamia Instalatora programu Visual Studio. Wybierz **programowanie dla wielu platform .NET Core** obciążenia, a następnie wybierz **Modyfikuj**.

## <a name="next-steps"></a>Następne kroki

Gratulujemy wykonanie kroków tego samouczka! Aby uzyskać jeszcze więcej, przejdź do następujących samouczków.

> [!div class="nextstepaction"]
> [Samouczki języka C#](/dotnet/csharp/tutorials/)

## <a name="see-also"></a>Zobacz także

* [Podstawy języka C# dla początkujących kurs wideo](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169)