---
ms.technology: vs-ai-tools
ms.openlocfilehash: 5e4623715133f6203e4e967eb29eca20cb2f181e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49821360"
---
# <a name="create-an-ai-project-from-a-template-in-visual-studio"></a>Tworzenie projektu sztucznej Inteligencji z szablonu w programie Visual Studio

Po [zainstalowany program Visual Studio Tools for AI](installation.md), ułatwia utworzenie nowego projektu sztucznej Inteligencji przy użyciu różnych szablonów.

1. Uruchom program Visual Studio.

2. Wybierz **Plik > Nowy > Projekt** (Ctrl + Shift + N). W **nowy projekt** okno dialogowe, wyszukaj "**narzędzia si**", a następnie wybierz szablon ma. Należy pamiętać, że wybranie szablonu wyświetla krótki opis, w jaki szablon zawiera.

    ![Program VS2017 okna dialogowego Nowy projekt z szablonu języka Python](media/create-project/new-ai-project.png)

3. W tym przewodniku Szybki Start wybierz pozycję "**aplikacji TensorFlow**" szablonu, należy nadać projektowi nazwę (na przykład "mnist ręcznie ZAPISANYCH") i lokalizację, a następnie wybierz pozycję **OK**.

4. Program Visual Studio tworzy pliku projektu ( `.pyproj` pliku na dysku) wraz z innymi plikami zgodnie z opisem w szablonie. Z szablonem "TensorFlow aplikacja" projektu zawiera jeden plik o nazwie taka sama jak projekt. Plik jest otwarty w edytorze programu Visual Studio domyślnie.

    ![Projekt wynikowy, korzystając z szablonu aplikacji w języku Python](media/create-project/new-tensorflowapp.png)

5. Zwróć uwagę, że kod importuje już kilka bibliotek, takich jak TensorFlow, numpy, sys i systemu operacyjnego. Ponadto możesz już aplikacji rozpoczynają się one od niektórych argumentów wejściowych umożliwiające łatwe przełączanie lokalizacji danych wejściowych szkoleniowych, modele danych wyjściowych i pliki dziennika. Te parametry są przydatne podczas przesyłania zadań do wielu konteksty obliczeniowe (ie inny katalog w swojej lokalnej okna niż w udziale plików platformy Azure).

6. Projekt zawiera również właściwościami, który został utworzony, aby ułatwić debugowanie aplikacji automatycznie przekazując argumenty wiersza polecenia do tych parametrów wejściowych. **Kliknij prawym przyciskiem myszy** projekt następnie wybierz pozycję **właściwości**

    ![Właściwości](media/create-project/project-properties.png)

7. Kliknij przycisk **debugowania** dodano kartę, aby zobaczyć argumenty skryptu automatycznie. można je zmienić zgodnie z potrzebami, na którym znajduje się dane wejściowe i gdzie ma się dane wyjściowe przechowywane.

    ![Właściwości](media/create-project//project-properties_1.png)

8. Uruchom program, naciskając klawisze Ctrl + F5 lub wybierając **Debuguj > Uruchom bez debugowania** w menu. Wyniki są wyświetlane w oknie konsoli.
