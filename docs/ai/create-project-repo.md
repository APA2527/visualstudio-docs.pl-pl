---
ms.technology: vs-ai-tools
ms.openlocfilehash: 5abaf2aafe2ff265123e9d4ed12f0ee350b22879
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283525"
---
# <a name="clone-a-repository-of-python-code-in-visual-studio"></a>Klonowanie repozytorium kodu w języku Python w programie Visual Studio

Po [zainstalowany program Visual Studio Tools for AI](installation.md), można łatwo klonowanie repozytorium kodu w języku Python i Utwórz projekt z niego.

1. Aby nawiązać połączenie z repozytoriami GitHub, uruchom Instalatora programu Visual Studio wybierz **Modyfikuj**i wybierz pozycję **poszczególne składniki** kartę. Przewiń w dół do **kodu narzędzia** zaznacz **rozszerzeniu GitHub extension for Visual Studio**i wybierz **Modyfikuj**.

    ![Wybieranie rozszerzenia GitHub w Instalatorze programu Visual Studio](media\create-project-repo\installation-github-extension.png)

2. Uruchom program Visual Studio.

3. Wybierz **Widok > Team Explorer...**  otworzyć **Team Explorer** okna, w którym można połączyć się z usługi GitHub lub DevOps platformy Azure lub klonowanie repozytorium.

    ![Okno Eksploratora zespołu DevOps platformy Azure, usługi GitHub, wyświetlanie i klonowanie repozytorium](media\create-project-repo\team-explorer.png)

4. W polu adres URL w taki sposób, w obszarze **lokalne repozytoria Git**, wprowadź `https://github.com/Microsoft/samples-for-ai`, wprowadź folderu na sklonowane pliki i wybierz **klonowania**.

    > [!Tip]
    > Folder, który określisz w programie Team Explorer jest dany folder do odbierania sklonowane pliki. W odróżnieniu od `git clone` polecenia Tworzenie własnego klonu w programie Team Explorer nie tworzy automatycznie podfolder o nazwie repozytorium.

5. Po ukończeniu klonowania, kliknij dwukrotnie folder repozytorium w dolnej części programu Team Explorer, aby przejść do pulpitu nawigacyjnego repozytorium. W obszarze **rozwiązania**, wybierz opcję **nowy...** .

    ![Okno Eksploratora zespołu, tworząc nowy projekt z klonu](media\create-project-repo\team-explorer-new-project.png)

6. W **nowy projekt** wyświetlonym oknie dialogowym wybierz pozycję "**z istniejącego kodu języka Python**", określ nazwę dla projektu, ustawianie **lokalizacji** na tym samym folderze co repozytorium, i Wybierz **OK**. W oknie kreatora wybierz **Zakończ**.

7. Wybierz **Widok > Eksploratorze rozwiązań** z menu.

8. W Eksploratorze rozwiązań rozwiń `TensorFlow Examples> MNIST` węzła, kliknij prawym przyciskiem myszy `convolutional.py`i wybierz **Ustaw jako plik startowy**. W tym kroku opisano programu Visual Studio, plik, który należy używać, podczas uruchamiania projektu.

10. Naciśnij kombinację klawiszy Ctrl + F5 lub wybierz **Debuguj > Uruchom bez debugowania** do uruchomienia programu. Jeśli widzisz ", ponownie Sprawdź katalog roboczy ustawienia w poprzednim kroku.


11. Gdy program zostanie uruchomiony pomyślnie, zobaczysz go uruchomić, aby pobrać szkolenia i testowanie zestawu danych, a następnie uczenie modelu oraz Twoje współczynnik błędów wyjścia. Chcesz, aby współczynnik błędów, aby zmniejszyć wraz z upływem czasu

    ![Pierwsze dane wyjściowe programu Python mnist ręcznie ZAPISANYCH](media\create-project-repo\tensorflow-mnist-running.png)

> Jeśli używasz pakietu Anaconda i komunikatu o błędzie informującego o brakujących numpy, konieczne może być [zmiany w środowisku Python, aby użyć pakietu Anaconda](../python/selecting-a-python-environment-for-a-project.md).

11. Można wizualizować postęp przy użyciu narzędzia TensorBoard. Kliknij prawym przyciskiem myszy projekt, a następnie kliknij przycisk **uruchom narzędzia TensorBoard** następnie wybierz katalog danych wyjściowych dzienników narzędzia TensorBoard.

    ![Uruchom narzędzia tensorboard](media\create-project-repo\run-tensorboard.png)

11. Zwróć uwagę, błąd zmniejsza się z czasem, co oznacza, że w celu ulepszania jakości

    ![Uruchom narzędzia tensorboard](media\create-project-repo\tensorboard.png)