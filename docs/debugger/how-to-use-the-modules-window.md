---
title: Wyświetlanie plików dll i plików wykonywalnych w debugerze | Dokumentacja firmy Microsoft
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.modules
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, Modules window
- Modules window
- executable files, displaying while debugging
- debugging [Visual Studio], displaying modules
- DLLs, displaying while debugging
- modules, displaying
ms.assetid: d840fdca-b035-4452-b652-72580c831896
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f582c435239c83503b179d6bb5e142936a41cb4b
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279014"
---
# <a name="view-dlls-and-executables-using-the-modules-window-in-the-visual-studio-debugger"></a>Wyświetlanie plików dll i pliki wykonywalne w oknie modułów w debugerze programu Visual Studio
 
**Modułów** okno zawiera listę bibliotek DLL i plików wykonywalnych (EXE), które są używane przez program i ukazuje istotne informacje dla każdego. 

> [!NOTE]
>  Ta funkcja nie jest dostępna dla bazy danych SQL lub debugowania skryptu. 
  
### <a name="to-display-the-modules-window"></a>Aby wyświetlić okno modułów  
  
-   Podczas debugowania, wybierz **Debuguj > Windows** a następnie kliknij przycisk **modułów**.  
  
     Domyślnie **modułów** okna sortuje moduły według kolejności ładowania. Można sortować według dowolnej kolumny.  
  
### <a name="to-sort-by-any-column"></a>Aby sortować według dowolnej kolumny  
  
-   Kliknij przycisk u góry kolumny.  
  
     Możesz załadować symbole lub określenie ścieżki symbolu z **modułów** oknie za pomocą menu skrótów.  
  
## <a name="loading-symbols"></a>Ładowanie symboli  
 W **modułów** okna, możesz zobaczyć, które moduły mają załadowane symbole debugowania. Te informacje są wyświetlane w **stan symboli** kolumny. Jeśli stan jest wyświetlany komunikat **loadingCannot pomijane znaleźć lub otworzyć pliku PDB**, lub **ładowanie wyłączone przez ustawienie dołączania lub wykluczania**, można kierować debugera, aby pobrać symbole z publicznego symboli firmy Microsoft serwery lub załadować symbole z katalogu symboli na komputerze. Aby uzyskać więcej informacji, zobacz [Określ symboli (.pdb) i plików źródłowych](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
#### <a name="to-load-symbols-manually"></a>Aby ręcznie załadować symbole  
  
1.  W **modułów** okna, kliknij prawym przyciskiem myszy moduł, dla której symbole nie zostały załadowane.  
  
2.  Wskaż **Załaduj symbole z** a następnie kliknij przycisk **serwery symboli firmy Microsoft** lub **ścieżki symboli**.  
  
#### <a name="to-change-symbol-load-settings"></a>Aby zmienić ustawienia ładowania symboli  
  
1.  W **modułów** okna, kliknij prawym przyciskiem myszy dowolny moduł.  
  
2.  Kliknij przycisk **ustawienia symboli**.  
  
     Można teraz zmienić ustawienia ładowania symboli, zgodnie z opisem w [Określ lokalizacje symboli i zachowanie ładowania](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Specify_symbol_locations_and_loading_behavior). Zmiana zostanie wprowadzona dopiero po ponownym uruchomieniu sesji debugowania.  
  
#### <a name="to-change-symbol-load-behavior-for-a-specific-module"></a>Aby zmienić zachowanie ładowania symboli dla określonego modułu  
  
1.  W **modułów** okna, kliknij prawym przyciskiem myszy moduł.  
  
2.  Wskaż **ustawienia automatycznego ładowania symboli** a następnie kliknij przycisk **zawsze obciążenia ręcznie** lub **domyślne**. Zmiana zostanie wprowadzona dopiero po ponownym uruchomieniu sesji debugowania.  
  
## <a name="see-also"></a>Zobacz też  
 [Przerwanie wykonywania](/previous-versions/visualstudio/visual-studio-2010/7z9se2d8(v=vs.100))   
 [Wyświetlanie danych w debugerze](../debugger/viewing-data-in-the-debugger.md)   
 [Określanie plików symboli (pdb) i plików źródłowych](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)