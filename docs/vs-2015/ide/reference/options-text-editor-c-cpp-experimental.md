---
title: Opcje, Edytor tekstu, C-C++, eksperymentalne | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.C/C++.Experimental
- VS.ToolsOptionsPages.Text_Editor.C%2FC%2B%2B.Experimental
- VS.ToolsOptionsPages.Text_Editor.C\C++.Experimental
ms.assetid: b9e9dda2-350c-460d-b368-37d6c5342eee
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6b07bdc7ab114619629ab4ef360ded3bf6655e6e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49285119"
---
# <a name="options-text-editor-cc-experimental"></a>Opcje, Edytor tekstu, C/C++, eksperymentalne
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Zmieniając tych opcji, możesz zmienić zachowanie związane z technologii IntelliSense i bazy danych przeglądania w przypadku programowania w języku C lub C++.  
  
 Dostępu do tej strony, w **opcje** rozwiń w lewym okienku w oknie dialogowym **edytora tekstów**, rozwiń węzeł **C/C++**, a następnie wybierz **eksperymentalne**.  
  
 Te funkcje są dostępne w instalacji programu Visual Studio 2015 Update 1 RC.  
  
> [!NOTE]
>  Na komputerze w poniższych instrukcjach mogą być wyświetlane inne nazwy i lokalizacje niektórych elementów interfejsu użytkownika programu Visual Studio. Te elementy są określane przez numer wersji Visual Studio oraz twoje ustawienia. Zobacz [Dostosowywanie ustawień środowiska deweloperskiego w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="browsingnavigation"></a>Przeglądanie nawigacji  
 **Włącz nowy aparat bazy danych**  
 Automatycznie powinno to przyspieszyć wypełniania bazy danych i szybciej wszystkie operacje bazy danych (z bez utraty dokładności) dla operacji takich jak **przejdź do definicji** i **Znajdź wszystkie odwołania**. (Po prostu zamknąć i ponownie otwórz rozwiązanie, aby zastosować zmiany; nie jest konieczne ponowne uruchomienie programu Visual Studio).  
  
## <a name="intellisense"></a>IntelliSense  
 **Element członkowski listy kropki na strzałkę**  
 Zastępuje "." strzałką "->" Jeśli jest to wymagane na liście składowych.  
  
## <a name="refactoring"></a>Refaktoryzacja  
 **Włącz funkcję wyodrębniania**  
 Wyodrębnij zaznaczony kod do odrębnej funkcji i Zastąp kod przy użyciu wywołania do nowych funkcji. Aby uzyskać dostęp do tej funkcji, kliknij prawym przyciskiem myszy w zaznaczonym kodzie, a następnie wybierz **szybkie akcje**, lub po prostu naciśnij domyślny skrót Ctrl + kropka [Ctrl +.].  
  
 **Włącz zmianę sygnatury**  
 Dodać, zmienić kolejność, usuwanie parametrów funkcji i propagujące zmiany do wszystkich lokacji wywołania. Aby uzyskać dostęp do tej funkcji, kliknij prawym przyciskiem myszy każde użycie funkcji, a następnie wybierz pozycję **szybkie akcje**, lub po prostu naciśnij domyślny skrót Ctrl + kropka [Ctrl +.].  
  
## <a name="text-editor"></a>Edytor tekstu  
 **Włącz rozwiń zakresy**  
 Jeśli włączone, można otoczyć zaznaczony tekst w nawiasach klamrowych, wpisując "{" do edytora tekstów.  
  
 **Włącz rozwiń pierwszeństwo**  
 Jeśli włączone, można otoczyć zaznaczony tekst w nawiasach, wpisując "(" do edytora tekstów.  
  
 Dla funkcji edytora dodatkowego tekstu w galerii Visual Studio, należy zapoznać się z listą [tutaj](http://go.microsoft.com/fwlink/?LinkId=692016). Na przykład [C++ szybkich poprawek](https://visualstudiogallery.msdn.microsoft.com/be91feef-8dc3-4f7a-ac9f-f34e7ca5918f), który obsługuje następujące czynności:  
  
-   **Dodaj brakujące #include** -sugeruje odpowiednie #include przez nieznany symboli w kodzie  
  
-   **Dodaj instrukcję using przestrzeń nazw/pełnej kwalifikacji symbol** — podobnie jak poprzedni element, ale w przypadku przestrzeni nazw  
  
-   **Dodaj Brak średnika**  
  
-   **Pomoc MSDN** — komunikaty o błędach w witrynie MSDN wyszukiwania  
  
 Możesz albo umieść kursor nad wężyk do pobrania żarówki, lub użyj domyślnej skrótu klawiaturowego Ctrl + kropka (Ctrl +.). Należy zauważyć, że dla skrótu klawiaturowego swoje karetki nie się znajdować na konkretny błąd lub tokenu po prostu można w tym samym wierszu jako błąd do wywołania sugestie dla wszystkich elementów w danym wierszu.  
  
## <a name="see-also"></a>Zobacz też  
 [Ustawianie opcji edytora specyficznych dla języka](../../ide/reference/setting-language-specific-editor-options.md)   
 [Refaktoryzacja języka C++ (VC Blog)](http://blogs.msdn.com/b/vcblog/archive/2014/11/14/all-about-c-refactoring-in-visual-studio-2015-preview.aspx)



