---
title: Informacje o rozwiązaniach i projektach
description: Dowiedz się więcej o projektach i rozwiązaniach programu Visual Studio, sposobach tworzenia nowych projektów na podstawie szablonu oraz sposobie wyświetlania & zarządzania projektami w programie Eksplorator rozwiązań.
ms.custom: SEO-VS-2020, contperf-fy21q2
ms.date: 12/31/2020
ms.topic: conceptual
f1_keywords:
- vs.addnewitem
- vs.addnewsolutionitem
- vs.openproject
- vs.addexistingitem
- vs.addexistingsolutionitem
- vs.environment.projects
- vs.environment.solutions
- VS.SolutionExplorer
- VS.SolutionExplorer.Solutions
helpviewer_keywords:
- solutions [Visual Studio]
- projects [Visual Studio]
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 473c3ca0e4a9998d6a320e384bf39b4b5e037085
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99878503"
---
# <a name="solutions-and-projects-in-visual-studio"></a>Rozwiązania i projekty w programie Visual Studio

Ta strona zawiera opis koncepcji *projektu* i *rozwiązania* w programie Visual Studio. Zawarto również krótko omówiono okno narzędzia Eksplorator rozwiązań i sposób tworzenia nowego projektu.

> [!NOTE]
> Ten temat ma zastosowanie do programu Visual Studio w systemie Windows. Aby uzyskać Visual Studio dla komputerów Mac, zobacz [projekty i rozwiązania w Visual Studio dla komputerów Mac](/visualstudio/mac/projects-and-solutions).

## <a name="projects"></a>Projekty

Podczas tworzenia aplikacji lub witryny sieci Web w programie Visual Studio rozpoczyna się od *projektu*. W sensie logicznym projekt zawiera wszystkie pliki, które są kompilowane do pliku wykonywalnego, biblioteki lub witryny sieci Web. Pliki te mogą obejmować kod źródłowy, ikony, obrazy, pliki danych itd. Projekt zawiera również ustawienia kompilatora i inne pliki konfiguracji, które mogą być konieczne przez różne usługi lub składniki, z którymi program komunikuje się.

### <a name="project-file"></a>Plik projektu

Program Visual Studio używa programu [MSBuild](../msbuild/msbuild.md) do kompilowania każdego projektu w rozwiązaniu, a każdy projekt zawiera plik projektu MSBuild. Rozszerzenie pliku odzwierciedla typ projektu, na przykład projekt C# (. csproj), projekt Visual Basic (. vbproj) lub projekt bazy danych (. DBPROJ). Plik projektu to dokument XML, który zawiera wszystkie informacje i instrukcje wymagane przez MSBuild w celu skompilowania projektu, w tym zawartość, wymagania dotyczące platformy, informacje o wersji, ustawienia serwera sieci Web lub serwera bazy danych oraz zadania do wykonania.

Pliki projektu są oparte na [schemacie XML programu MSBuild](../msbuild/msbuild-project-file-schema-reference.md). Aby sprawdzić zawartość nowszych [plików projektu w stylu zestawu SDK](../msbuild/how-to-use-project-sdk.md) w programie Visual Studio, kliknij prawym przyciskiem myszy węzeł projektu w **Eksplorator rozwiązań** i wybierz polecenie **Edytuj \<projectname\>**. Aby przyjrzeć się zawartości .NET Framework i innych projektów tego stylu, najpierw Zwolnij projekt (kliknij prawym przyciskiem myszy węzeł projektu w **Eksplorator rozwiązań** i wybierz polecenie **Zwolnij projekt**). Następnie kliknij prawym przyciskiem myszy projekt i wybierz polecenie **Edytuj \<projectname\>**.

> [!NOTE]
> Nie musisz używać rozwiązań ani projektów w programie Visual Studio do edytowania, kompilowania i debugowania kodu. Możesz po prostu otworzyć folder zawierający pliki źródłowe w programie Visual Studio i rozpocząć edycję. Aby uzyskać więcej informacji, zobacz [Programowanie kodu w programie Visual Studio bez projektów i rozwiązań](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md).

### <a name="create-new-projects"></a>Utwórz nowe projekty

Najprostszym sposobem tworzenia nowego projektu jest użycie szablonu projektu dla tego typu projektu. Szablon projektu zawiera podstawowy zestaw wstępnie wygenerowanych plików kodu, plików konfiguracji, zasobów i ustawień. Użyj opcji **plik**  >  **Nowy**  >  **projekt** , aby wybrać szablon projektu. Aby uzyskać więcej informacji, zobacz [Tworzenie nowego projektu](create-new-project.md).

Można również utworzyć niestandardowy szablon projektu, za pomocą którego można tworzyć nowe projekty z programu. Aby uzyskać więcej informacji, zobacz [Tworzenie szablonów projektów i elementów](../ide/creating-project-and-item-templates.md).

Podczas tworzenia nowego projektu program Visual Studio zapisuje go w domyślnej lokalizacji *%USERPROFILE%\source\repos*. Aby zmienić tę lokalizację, przejdź do **lokalizacji narzędzia**  >  **Opcje**  >  **projekty i rozwiązania**  >  . Aby uzyskać więcej informacji, zobacz [okno dialogowe Opcje: projekty i rozwiązania > lokalizacje](./reference/projects-solutions-locations-options.md).

## <a name="solutions"></a>Rozwiązania

Projekt jest zawarty w *rozwiązaniu*. Pomimo nazwy, rozwiązanie nie jest "odpowiedzią". Jest to po prostu kontener dla co najmniej jednego powiązanego projektu, a także informacje o kompilacji, ustawienia okna programu Visual Studio oraz inne pliki, które nie są skojarzone z określonym projektem.

### <a name="solution-file"></a>Plik rozwiązania

Program Visual Studio używa dwóch typów plików (*. sln* i *. suo*) do przechowywania ustawień rozwiązań:

|Wewnętrzny|Nazwa|Opis|
|---------------|----------|-----------------|
|. sln|Rozwiązanie programu Visual Studio|Organizuje projekty, elementy projektu i elementy rozwiązania w rozwiązaniu.|
|. suo|Opcje użytkownika rozwiązania|Przechowuje ustawienia i dostosowania na poziomie użytkownika, takie jak punkty przerwania.|

> [!IMPORTANT]
> Rozwiązanie jest opisane przez plik tekstowy (rozszerzenie *. sln*) z własnym unikatowym formatem; nie jest przeznaczona do edycji. Z kolei plik *. suo* to ukryty plik, który nie jest wyświetlany w domyślnych ustawieniach Eksploratora plików. Aby wyświetlić ukryte pliki, w menu **Widok** w Eksploratorze plików zaznacz pole wyboru **ukryte elementy** .

### <a name="solution-folder"></a>Folder rozwiązania

"Folder rozwiązania" to folder wirtualny, który jest tylko w **Eksplorator rozwiązań**, w którym można go użyć do grupowania projektów w rozwiązaniu. Jeśli chcesz zlokalizować plik rozwiązania na komputerze, przejdź do pozycji **Narzędzia**  >  **Opcje**  >  **projekty i rozwiązania**  >  . Aby uzyskać więcej informacji, zobacz [okno dialogowe Opcje: projekty i rozwiązania > lokalizacje](./reference/projects-solutions-locations-options.md).

> [!TIP]
> Aby zapoznać się z przykładem projektu i rozwiązania utworzonego od podstaw, wykonaj instrukcje krok po kroku i przykładowy kod, zobacz [wprowadzenie do projektów i rozwiązań](../get-started/tutorial-projects-solutions.md).

## <a name="solution-explorer"></a>Eksplorator rozwiązań

Po utworzeniu nowego projektu można użyć **Eksplorator rozwiązań** , aby wyświetlić projekt i rozwiązanie oraz ich skojarzone elementy i zarządzać nimi. Na poniższej ilustracji przedstawiono **Eksplorator rozwiązań** z rozwiązaniem w języku C# zawierającym dwa projekty:

::: moniker range="vs-2017"

![Zrzut ekranu przedstawiający Eksplorator rozwiązań z dwoma projektami.](../ide/media/vs2015_solution_explorer.png)

Pasek narzędzi w górnej części **Eksplorator rozwiązań** zawiera przyciski do przełączenia z widoku rozwiązania do widoku folderu, wyświetlania ukrytych plików, zwijania wszystkich węzłów i innych.

::: moniker-end

::: moniker range="vs-2019"

![Zrzut ekranu przedstawiający Eksplorator rozwiązań z dwoma projektami w programie Visual Studio 2019.](../ide/media/solution-explorer.png)

Pasek narzędzi w górnej części **Eksplorator rozwiązań** zawiera przyciski do przełączania z widoku rozwiązania do widoku folderu, filtrowania oczekujących zmian, wyświetlania wszystkich plików, zwijania wszystkich węzłów, wyświetlania stron [Właściwości](managing-project-and-solution-properties.md) , podglądu kodu w [edytorze kodu](writing-code-in-the-code-and-text-editor.md)i innych.

::: moniker-end

Wiele poleceń menu jest dostępnych w menu kontekstowym po kliknięciu prawym przyciskiem myszy dla różnych elementów w **Eksplorator rozwiązań**. Te polecenia obejmują Kompilowanie projektu, zarządzanie pakietami NuGet, Dodawanie odwołania, zmiana nazwy pliku i uruchamianie testów, po prostu do nazwy a.

W przypadku projektów ASP.NET Core można dostosować sposób zagnieżdżania plików w **Eksplorator rozwiązań**. Aby uzyskać więcej informacji, zobacz [Dostosowywanie zagnieżdżania plików w Eksplorator rozwiązań](file-nesting-solution-explorer.md).

> [!TIP]
> Jeśli zamknięto Eksplorator rozwiązań i chcesz go otworzyć ponownie, wybierz pozycję **Wyświetl**  >  **Eksplorator rozwiązań** z paska menu lub naciśnij **klawisze CTRL** + **Alt** + **L**. A Jeśli zamknąłeś karty boczne i chcesz przywrócić ich domyślne lokalizacje **, wybierz opcję**  >  **Resetuj układ okna** z paska menu.

> [!NOTE]
> Aby wyświetlić obrazy i ikony aplikacji, które pojawiają się w programie Visual Studio, Pobierz [**bibliotekę obrazów programu Visual Studio**](https://www.microsoft.com/download/details.aspx?id=35825).

## <a name="see-also"></a>Zobacz też

- [Wprowadzenie do projektów i rozwiązań](../get-started/tutorial-projects-solutions.md)
- [Zarządzanie właściwościami projektów i rozwiązań](managing-project-and-solution-properties.md)
- [Rozwiązania filtrowane w programie Visual Studio](filtered-solutions.md)
- [Przenoszenie, migrowanie i uaktualnianie projektów](../porting/port-migrate-and-upgrade-visual-studio-projects.md)
- [Zasoby do rozwiązywania problemów z błędami środowiska IDE programu Visual Studio](./reference/resources-for-troubleshooting-integrated-development-environment-errors.md)
- [Projekty i rozwiązania (Visual Studio dla komputerów Mac)](/visualstudio/mac/projects-and-solutions)