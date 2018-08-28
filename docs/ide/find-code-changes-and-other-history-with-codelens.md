---
title: Znajdowanie zmian w kodzie i innych elementów historii kodu za pomocą funkcji CodeLens
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22d3a6ea380fdbfb8f6a41fce21d0ad283808d85
ms.sourcegitcommit: e04e52bddf81239ad346efb4797f52e38de5cb98
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/27/2018
ms.locfileid: "43054481"
---
# <a name="find-code-changes-and-other-history-with-codelens"></a>Znajdowanie zmian w kodzie i innych elementów historii kodu za pomocą funkcji CodeLens

Funkcja CodeLens umożliwia skoncentrowanie się na pracy, chociaż możesz dowiedzieć się, co się stało z kodu&ndash;bez opuszczania edytora. Można znaleźć odwołania do fragmentu kodu, zmiany kodu, połączone usterki, elementy robocze, przeglądy kodu i testów jednostkowych.

> [!NOTE]
> Funkcja CodeLens jest dostępna tylko w wersjach programu Visual Studio Enterprise i Visual Studio Professional. Nie jest dostępne w programie Visual Studio Community edition.

Zobacz, gdzie i w jaki sposób poszczególne fragmenty kodu są używane w rozwiązaniu:

![Wskaźniki CodeLens w edytorze kodu](../ide/media/codelens-overview.png)

Bez opuszczania edytora, skontaktuj się z zespołem o zmianach w kodzie:

![Funkcja CodeLens — skontaktuj się z zespołem](../ide/media/codelens-contact-info.png)

Aby wybrać wskaźników, które chcesz wyświetlić lub wyłącz i Włącz CodeLens, przejdź do **narzędzia** > **opcje** > **edytora tekstów**  >  **Wszystkie języki** > **CodeLens**.

## <a name="find-references-to-your-code"></a>Znajdowanie odwołań w kodzie

Odwołania można znaleźć w języku C# lub kod języka Visual Basic.

1. Wybierz **odwołania** wskaźnika lub naciśnij klawisz **Alt**+**2**.

   ![Odwołania do wskaźników CodeLens](../ide/media/codelens-view-references.png)

   > [!NOTE]
   > Jeśli wskaźnik przedstawia **0 odwołań**, nie ma odwołań z kodu C# lub Visual Basic. Jednak mogą występować odwołania w innych elementów takich jak *.xaml* i *.aspx* plików.

2. Aby wyświetlić kod odwołujący się, wskaźnik myszy nad odwołanie, na liście.

   ![Funkcja CodeLens — odwołanie do podglądu](../ide/media/codelens-peek-reference.png)

3. Aby otworzyć plik, który zawiera odwołania, kliknij dwukrotnie odwołanie.

### <a name="code-maps"></a>Mapy kodu

Aby wyświetlić relacje między kodem i jego odwołaniami [utworzenie mapy kodu](../modeling/map-dependencies-across-your-solutions.md). Wybierz z menu skrótów mapy kodu **Pokaż wszystkie odwołania**.

![Funkcja CodeLens — odwołania na mapie kodu](../ide/media/codelensmappedreferences.png)

## <a name="a-namefind-code-historyfind-changes-in-your-code"></a><a name="find-code-history"/>Znajdowanie zmian w kodzie

Sprawdź, czy historią swojego kodu, aby dowiedzieć się, co się stało z kodu. Lub przejrzyj zmiany, zanim one scalane w kodzie, dzięki czemu można lepiej zrozumieć, jak zmiany w innych gałęzi, mogą mieć wpływ na kod.

Potrzebujesz:

- Visual Studio Enterprise lub Professional programu Visual Studio

- Team Foundation Server 2013 or later, Visual Studio Team Services, or Git

- [Skype dla firm](/skypeforbusiness/), lub Lync 2010 lub nowszej, aby skontaktować się z zespołem z poziomu edytora kodu

Dla kodu C# lub Visual Basic, przechowywanego z Team Foundation Version Control (TFVC) lub Git, Pobierz szczegóły CodeLens na poziomie klasy i metody (*element kodu na poziomie* wskaźniki). Jeśli repozytorium Git jest hostowana w TfGit, możesz także uzyskać łącza do elementów roboczych TFS.

![Wskaźniki poziomu element Code](../ide/media/codelens-element-level-indicators.png)

Dla pliku typów innych niż *.cs* lub *.vb*, możesz uzyskać szczegółowe informacje CodeLens cały plik w jednym miejscu w dolnej części okna (*poziomu plików* wskaźniki).

![Wskaźniki CodeLens poziomie plików](../ide/media/almcodelensfilelevelindicators.png)

### <a name="code-element-level-indicators"></a>Wskaźniki poziomu element Code

Wskaźniki poziomu elementu pozwalają zobaczyć, kto zmienił kod i jakich zmian kodu zostały wykonane. Wskaźniki poziomu elementu kodu są dostępne dla kodu C# i Visual Basic.

Jest to, zobacz korzystając z Team Foundation Version Control (TFVC) w Team Foundation Server lub Visual Studio Team Services:

![CodeLens: Historia zmian Get dla kodu w TFVC](../ide/media/codelens-code-changes.png)

Domyślny okres czasu jest ostatnich 12 miesięcy. Jeśli Twój kod jest przechowywany na serwerze Team Foundation Server, można zmienić okres czasu, uruchamiając [polecenia TFSConfig](/tfs/server/ref/command-line/tfsconfig-cmd) z [polecenie CodeIndex](../ide/codeindex-command.md) i **/indexHistoryPeriod**flagi.

Aby wyświetlić szczegółowej historii wszystkich zmian, łącznie ze składnikami z ponad rok temu, wybierz opcję **Pokaż wszystkie zmiany pliku**:

![Pokaż wszystkie zmiany kodu](../ide/media/codelens-show-all-file-changes.png)

**Historii** zostanie otwarte okno:

![Okno Historia dla wszystkich zmian w kodzie](../ide/media/codelenscodechangeshistory.png)

Jeśli pliki znajdują się w repozytorium Git, i wybierz wskaźnik zmian na poziomie elementu kodu, jest to, co widzą:

![CodeLens: Historia zmian Get dla kodu w Git](../ide/media/codelens-code-changes-git.png)

### <a name="file-level-indicators"></a>Wskaźniki poziomu plików

Znajdowanie zmian dla całego pliku wskaźniki poziomu plików w dolnej części okna:

![CodeLens: Uzyskaj kod szczegółów pliku](../ide/media/codelens-file-level.png)

> [!NOTE]
> Wskaźniki poziomu plików nie są dostępne dla plików języka C# i Visual Basic.

Aby uzyskać więcej informacji na temat zmian, kliknij prawym przyciskiem myszy ten element. W zależności od tego, czy używasz TFVC lub Git dostępne są opcje porównywać wersje pliku, Wyświetl szczegóły śledzenia zmian, pobrać wybraną wersję pliku i wiadomości e-mail autora zmiany. Niektóre z tych informacji są wyświetlane w **Team Explorer**.

Widać również, kto zmienił kod, wraz z upływem czasu. Może to pomóc Ci znaleźć wzorce w zmiany swojego zespołu i ocena ich skutków.

![CodeLens: Zobacz historię zmian kod jako Graf](../ide/media/codelens.png)

### <a name="find-changes-in-your-current-branch"></a>Znajdowanie zmian w gałęzi bieżącej

Twój zespół może mieć wielu gałęzi, na przykład głównej gałęzi i Programowanie gałęzi podrzędnej, aby zmniejszyć ryzyko istotne stabilnym kodem.

![CodeLens: Dowiedz się, gdy został rozgałęziony kodu](../ide/media/codelensfirstbranchconceptual.png)

Możesz dowiedzieć się jak wiele osób zmieniło kodu i jak wiele zmian w gałęzi głównej, naciskając klawisz **Alt**+**6**:

![CodeLens: Znajdź liczby zmian w gałęzi](../ide/media/codelens-branch-changes.png)

### <a name="find-when-your-code-was-branched"></a>Dowiedz się, gdy został rozgałęziony kodu

Aby dowiedzieć się, gdy kod został rozgałęziony, przejdź do kodu w gałęzi podrzędnej. Następnie wybierz **zmiany** wskaźnika lub naciśnij klawisz**Alt**+**6**:

![CodeLens: Dowiedz się, gdy został rozgałęziony kodu](../ide/media/codelens-first-branch.png)

### <a name="find-incoming-changes-from-other-branches"></a>Znajdź zmiany przychodzące z innych gałęzi

![CodeLens: Znajdowanie zmian w kodzie w innych gałęzi](../ide/media/codelensbranchchangecheckinconceptual.png)

Możesz wyświetlić zmiany przychodzące. Poniższy zrzut ekranu poprawkę została wprowadzona w gałęzi "Dev":

![CodeLens: Zmiana sprawdzone w innej gałęzi](../ide/media/codelens-branch-changes-dev.png)

Możesz przejrzeć zmiany bez wychodzenia z bieżącej gałęzi ("Main"):

![CodeLens: Zobacz Zmiana przychodząca z innej gałęzi](../ide/media/codelens-branch-changes-main.png)

### <a name="find-when-changes-got-merged"></a>Dowiedz się, gdy została scalona zmiany

Możesz zobaczyć podczas zmian została scalona, dzięki czemu można określić, jakie zmiany są uwzględnione w Twojej gałęzi:

![Funkcja CodeLens - scalone zmiany między gałęziami](../ide/media/codelensbranchmergedconceptual.png)

Na przykład kod w gałęzi głównej ma teraz poprawki w gałęzi "Dev":

![Funkcja CodeLens - scalone zmiany między gałęziami](../ide/media/codelens-branch-merged.png)

### <a name="compare-an-incoming-change-with-your-local-version"></a>Porównaj zmiany przychodzące z lokalnej wersji

Porównaj zmiany przychodzące z lokalnej wersji, naciskając klawisz **Shift**+**F10**, lub klikając dwukrotnie zestaw zmian.

![CodeLens: Porównaj zmiany przychodzące z lokalnego](../ide/media/codelens-branch-incoming-change-menu.png)

### <a name="branch-icons"></a>Ikony gałęzi

Ikona w **gałęzi** kolumny informuje, jak gałęzi jest powiązany do gałęzi, w której pracujesz.

|**Ikona**|**Zmiana pochodzi od:**|
|--------------|-----------------------------------------|
|![CodeLens: Zmienić z bieżącej gałęzi ikona](../ide/media/codelensbranchcurrenticon.png)|Current branch|
|![CodeLens: Zmiana nadrzędnej gałęzi ikona](../ide/media/codelensbranchparenticon.png)|Gałąź nadrzędna|
|![CodeLens: Zmienić ikony gałęzi podrzędnej](../ide/media/codelensbranchchildicon.png)|Gałęzi podrzędnej|
|![CodeLens: Zmienić ikony gałęzi elementu równorzędnego](../ide/media/codelensbranchpeericon.png)|Gałęzi elementu równorzędnego|
|![CodeLens: Zmienić jedno kliknięcie ikony dalsze gałęzi](../ide/media/codelensbranchfurtherawayicon.png)|Gałąź dalsze natychmiast niż nadrzędne, podrzędne lub elementów równorzędnych|
|![CodeLens: Scalanie z nadrzędnego ikony](../ide/media/codelensbranchmergefromparenticon.png)|Scalanie z gałęzi do gałęzi podrzędnej|
|![CodeLens: Scalanie z ikony gałęzi podrzędnej](../ide/media/codelensbranchmergefromchildicon.png)|Scalanie z gałęzi podrzędnej do gałęzi nadrzędnej|
|![CodeLens: Scal z gałęzi niepowiązanych ikony](../ide/media/codelensbranchmergefromunrelatedicon.png)|Scalanie gałęzi niepowiązanych (scalanie)|

## <a name="linked-work-items"></a>Połączone elementy robocze

Znajdź połączonych elementów roboczych, wybierając **elementów roboczych** wskaźnika lub naciskając **Alt**+**8**.

![Funkcja CodeLens — Znajdź elementy robocze dla określonego kodu](../ide/media/codelens-work-items.png)

## <a name="linked-code-reviews"></a>Przeglądy kodu połączone

Znajdowanie przeglądów kodu połączone przez wybranie **przeglądy** wskaźnika. Aby użyć klawiatury, przytrzymaj wciśnięty **Alt** klucza, a następnie naciśnij klawisz **Strzałka w lewo** lub **strzałkę w prawo** Przejdź Opcje wskaźnika.

![CodeLens — Wyświetl kod przeglądu żądań](../ide/media/codelens-code-reviews.png)

## <a name="linked-bugs"></a>Powiązane błędy

Znaleźć połączone błędy, wybierając **usterki** wskaźnika lub naciskając **Alt**+**7**.

![Funkcja CodeLens — Znajdź błędy związane z zestawami zmian](../ide/media/codelens-bugs-changesets.png)

## <a name="contact-the-owner-of-an-item"></a>Skontaktuj się z właścicielem elementu

Znajdowanie autor elementu przez wybranie **autorzy** wskaźnika lub naciskając **Alt**+**5**.

![Skontaktuj się z właścicielem elementu](../ide/media/codelens-contact-item-owner.png)

Otwórz menu skrótów dla elementu, aby wyświetlić opcje kontaktu. Jeśli masz Lync lub Skype dla firm zainstalowany, zostanie wyświetlony tych opcji:

![Skontaktuj się z opcjami dla elementu](../ide/media/codelens-item-contact-menu.png)

## <a name="associated-unit-tests"></a>Testów jednostkowych skojarzone

Możesz odkryć testy jednostkowe, które istnieją w kodzie języka C# lub Visual Basic, bez otwierania **Eksplorator testów**.

1. Przejdź do kodu aplikacji, która jest skojarzona [kod testu jednostkowego](../test/unit-test-your-code.md).

2. Jeśli jeszcze tego nie zrobiono, należy skompilować aplikację można załadować testu wskaźniki CodeLens. Upewnij się, że [odnajdywane przez program skompilowany zestaw](../test/test-explorer-faq.md#assembly-based-discovery) jest włączona.

3. Przejrzyj testów dla kodu, naciskając klawisz **Alt**+**3**.

     ![Funkcja CodeLens — wybierz stan testu w edytorze kodu](../ide/media/codelens-choose-test-indicator.png)

4. Jeśli widoczna jest ikona ostrzeżenia ![ikona ostrzeżenia](../ide/media/codelenstestwarningicon.png), testy nie jeszcze Uruchom jeszcze, więc można ich uruchomić.

     ![Funkcja CodeLens — widoku testów jednostkowych nie jeszcze uruchomione](../ide/media/codelens-tests-not-yet-run.png)

5. Aby przejrzeć definicję testu, kliknij dwukrotnie element testu w oknie wskaźnik CodeLens, aby otworzyć plik kodu w edytorze.

     ![Funkcja CodeLens — przejdź do definicji testu jednostki](../ide/media/codelens-unit-test-definition.png)

6. Aby przejrzeć wyniki testów, wybierz wskaźnik stanu testu (![nie powiodło się ikona testowa](../ide/media/codelenstestfailedicon.png) lub ![ikonę pomyślny](../ide/media/codelenstestpassedicon.png)), lub naciśnij **Alt**+**1**.

     ![Funkcja CodeLens - wyniku testu jednostkowego zobacz](../ide/media/codelens-unit-test-result.png)

7. Aby zobaczyć, ile osób zmieniło ten test, kto go zmienił lub ile zmian z tym testem [znajdowanie historii kodu](#find-code-history) i połączone elementy.

## <a name="keyboard-shortcuts"></a>Skróty klawiaturowe

Aby wybrać wskaźników za pomocą klawiatury, naciśnij i przytrzymaj **Alt** klucza, aby wyświetlić powiązane klawisze numeryczne, a następnie naciśnij numer, który odpowiada wskaźnika, którą chcesz wybrać.

![Numery dostępu do klawiatury](../ide/media/codelens-alt-keys.png)

> [!NOTE]
> Aby wybrać **przeglądy** wskaźnik, naciśnij i przytrzymaj klawisz **Alt** podczas korzystania z klawiszy strzałek w lewo i w prawo do nawigacji.

## <a name="q--a"></a>Pytania i odpowiedzi

### <a name="q-how-do-i-turn-codelens-off-or-on-or-choose-which-indicators-to-see"></a>P: jak włączanie i wyłączanie funkcji CodeLens, lub wybierz wskaźników, które się?

**Odp.:** można włączyć wskaźników lub wyłączyć, z wyjątkiem wskaźnik odwołań. Przejdź do **narzędzia** > **opcje** > **edytora tekstów** > **wszystkie języki**  >  **CodeLens**.

Wskaźniki są włączone, można również otworzyć Opcje CodeLens, pochodzące ze wskaźników.

![Funkcja CodeLens - wskaźniki Włączanie lub wyłączanie](../ide/media/codelensturnoffonindicatorsfromcode.png)

Włącz wskaźniki poziomu plików CodeLens, włączać i wyłączać przy użyciu ikon kół cudzysłów ostrokątny u dołu okna edytora.

![Włącz wskaźniki poziomu plików włączać i wyłączać](../ide/media/codelensfilelevelonandoff.png)

### <a name="q-where-is-codelens"></a>Pyt.: gdzie jest CodeLens?

**Odp.:** CodeLens jest wyświetlana w kodzie języka C# i Visual Basic na poziomie metody, klasy, indeksatora i właściwości. Funkcja CodeLens pojawia się na poziomie pliku dla wszystkich typów plików.

- Upewnij się, że jest włączona funkcja CodeLens. Przejdź do **narzędzia** > **opcje** > **edytora tekstów** > **wszystkie języki**  >  **CodeLens**.

- Jeśli Twój kod jest przechowywany w programie TFS, upewnij się, że indeksowanie kodu jest włączone za pomocą [polecenie CodeIndex](../ide/codeindex-command.md) z [polecenia konfiguracji TFS](/tfs/server/ref/command-line/tfsconfig-cmd).

- Wskaźniki związane z TFS pojawiają się tylko wtedy, gdy elementy robocze są połączone z kodem, a użytkownik ma uprawnienia do otwierania połączonych elementów roboczych. Upewnij się, że masz [uprawnienia zabezpieczeń elementów członkowskich zespołu](/vsts/work/scale/multiple-teams).

- Nie pojawiają się wskaźniki testów jednostkowych, gdy kod aplikacji nie ma testów jednostkowych. Wskaźniki stanu testu są automatycznie wyświetlane w projektach testów. Jeśli wiesz, że kod aplikacji ma testy jednostkowe, ale nie pojawiają się wskaźniki testów, spróbuj skompilować rozwiązanie (**Ctrl**+**Shift**+**B**).

### <a name="q-why-dont-i-see-the-work-item-details-for-a-commit"></a>P: Dlaczego nie widzę szczegóły elementu roboczego do zatwierdzenia

**Odp.:** może się to zdarzyć, ponieważ funkcja CodeLens nie może znaleźć elementy robocze w programie TFS. Sprawdź, czy są połączone w do projektu zespołowego, który ma te elementów roboczych, i czy masz uprawnienia do wyświetlania tych elementów roboczych. Szczegóły elementu roboczego może również nie są wyświetlane czy opis zatwierdzenie ma nieprawidłowe informacje o identyfikatorach elementów roboczych w programie TFS.

### <a name="q-why-dont-i-see-the-skype-indicators"></a>P: Dlaczego nie widzę wskaźników Skype?

**Odp.:** nie pojawiają się wskaźniki Skype, jeśli użytkownik nie zalogował się do usługi Skype dla firm, nie jest ona zainstalowana lub nie ma obsługiwanej konfiguracji. Jednak nadal można wysyłać wiadomości e-mail:

![Funkcja CodeLens — skontaktuj się z właścicielem zestawu zmian za pomocą poczty e-mail](../ide/media/codelenscodesendmailchangesetnolync1.png)

**Które konfiguracje programu Skype i Lync są obsługiwane?**

- Skype dla firm (32-bitowy lub 64-bitowy)

- Lync 2010 lub nowszej samodzielnie (32-bitowy lub 64-bitowy), ale nie Lync Basic 2013 za pomocą Windows 8.1

Zainstalowany program Skype lub CodeLens nie obsługuje różnych wersji programu Lync. One może nie być zlokalizowana dla wszystkich zlokalizowanych wersji programu Visual Studio.

### <a name="q-how-do-i-change-the-font-and-color-for-codelens"></a>P: jak zmienić czcionkę i kolor wskaźników codelens?

**Odp.:** przejdź do **narzędzia** > **opcje** > **środowiska** > **czcionki i kolory**.

![Funkcja CodeLens — Zmień ustawienia czcionek i kolorów](../ide/media/codelensoptionsfontscolorssettings.png)

Aby użyć klawiatury:

1. Naciśnij klawisz **Alt**+**T**+**O** otworzyć **opcje** okno dialogowe.

2. Naciśnij klawisz **Strzałka w górę** lub **strzałkę w dół** można przejść do **środowiska** węzła, naciśnij klawisz **Strzałka w lewo** Aby rozwinąć węzeł.

3. Naciśnij klawisz **strzałkę w dół** można przejść do **czcionki i kolory**.

4. Naciśnij klawisz **kartę** można przejść do **Pokaż ustawienia dla** listy, a następnie naciśnij klawisz **strzałkę w dół** wybrać **CodeLens**.

### <a name="q-can-i-move-the-codelens-heads-up-display"></a>Pyt.: Czy można przesunąć ekran projekcyjny CodeLens?

**Odp.:** tak, wybierz polecenie ![ikonę dokowania](../ide/media/codelensdockwindow.png) Aby zadokować CodeLens jako okno.

![Przycisk dokowania w oknie wskaźników CodeLens](../ide/media/codelensselectdockwindow.png)

![Okno zadokowane odwołania do wskaźników CodeLens](../ide/media/codelensreferencesdockedwindow.png)

### <a name="q-how-do-i-refresh-the-indicators"></a>Pyt.: Jak odświeżyć wskaźniki?

**Odp.:** zależy to od wskaźnika:

- **Odwołania**: ten wskaźnik jest aktualizowany automatycznie po wprowadzeniu zmian w kodzie. Jeśli **odwołania** wskaźnik jest zadokowany jako oddzielne okno, Odśwież wskaźnika, wybierając **Odśwież**:

     ![Odśwież w funkcji CodeLens odwołania](../ide/media/codelensviewreferencesdocked.png)

- **Zespół**: Odśwież te wskaźniki, wybierając **Odśwież wskaźniki zespołu CodeLens** menu kliknij prawym przyciskiem myszy:

     ![Odśwież wskaźniki zespołu CodeLens elementu menu.](../ide/media/codelensrefreshindicatorsfromcode.png)

- **Test**: [znaleźć testów jednostkowych dla kodu](#Find-unit-tests-for-your-code) odświeżyć **testu** wskaźnika.

### <a name="q-whats-local-version"></a>Pyt.: co to jest "Wersja lokalna"?

**Odp.:** **lokalnej wersji** Strzałka wskazuje na najnowszy zestaw zmian w lokalnej wersji pliku. Gdy serwerze znajdują się nowsze zestawy zmian, są one wyświetlane powyżej lub poniżej **lokalnej wersji** strzałka, w zależności od kolejności ich sortowania.

### <a name="q-can-i-manage-how-codelens-processes-code-to-show-history-and-linked-items"></a>P: czy można zarządzać jak funkcja CodeLens przetwarza kod w celu wyświetlenia historii i połączone elementy?

**Odp.:** tak. Jeśli swój kod w programie TFS, użyj [polecenie CodeIndex](../ide/codeindex-command.md) z [polecenia konfiguracji TFS](/tfs/server/ref/command-line/tfsconfig-cmd).

### <a name="q-my-codelens-test-indicators-no-longer-appear-in-my-file-when-i-first-open-my-solution-how-can-i-load-them"></a>Pytanie: Moja CodeLens nie pojawiają się wskaźniki testów w pliku po raz pierwszy jest otwarty Moje rozwiązanie. Jak załadować je?

**Odp.:** ponownie skompiluj projekt, aby uzyskać wskaźniki testu CodeLens do załadowania w pliku. Upewnij się, że [odnajdywane przez program skompilowany zestaw](../test/test-explorer-faq.md#assembly-based-discovery
) jest włączona. W celu poprawy wydajności programu Visual Studio nie jest już pobieranie informacji o źródle wskaźniki testu w przypadku pliki kodu są ładowane. Wskaźniki testu są ładowane po kompilacji lub po przejściu do testu, klikając go dwukrotnie **Eksploratora testów**.

## <a name="see-also"></a>Zobacz także

- [Funkcje edytora kodu](../ide/writing-code-in-the-code-and-text-editor.md)
