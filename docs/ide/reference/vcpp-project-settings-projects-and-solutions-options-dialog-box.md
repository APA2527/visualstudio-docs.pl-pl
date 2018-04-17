---
title: Ustawienia projektu VC ++, projekty i rozwiązania, opcje — Okno dialogowe | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 08/02/2017
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Projects.VCBuild
helpviewer_keywords:
- builds [Visual Studio], logs
- build process [C++]
- files [Visual Studio], built by C/C++ compiler
- file extensions, built by C or C++ compiler
- cl.exe compiler, file extensions
- extensions, files built by C or C++ compiler
- BuildLog.htm
ms.assetid: 56420efd-6a95-464e-b890-e2b38c48d66a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 875dc15434be8d21a9bcee66d4091ecda9a4375a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="vc-project-settings-projects-and-solutions-options-dialog-box"></a>Ustawienia projektu VC++, projekty i rozwiązania, opcje — Okno dialogowe
To okno dialogowe pozwala zdefiniować [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] kompilacji i ustawienia dotyczące rejestrowania, wydajności i obsługi typów plików projektu.  
  
### <a name="to-access-this-dialog-box"></a>Dostęp do tego okna dialogowego  
  
1.  Na **narzędzia** menu, kliknij przycisk **opcje**.  
  
2.  Wybierz **projekty i rozwiązania**, a następnie wybierz **ustawienia projektu VC ++**.  
 
## <a name="build-logging"></a>Rejestrowanie kompilacji  
 **Tak**  
  Włącza generowanie pliku dziennika kompilacji. Ta opcja powoduje wygenerowanie BuildLog.htm, które znajdują się w katalogu pośrednim plików projektu. Co nowego kompilacji zastępuje poprzedniego pliku BuildLog.htm.  
  
 **Brak**  
  Wyłącza generowanie pliku dziennika kompilacji.  

## <a name="show-environment-in-log"></a>Pokaż środowisko w rejestrze  
 **Tak**  
 Wyświetla listę zmiennych środowiskowych w pliku dziennika kompilacji. Ta opcja określa, aby wyświetlić wszystkie zmienne środowiskowe, podczas kompilacji z [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] projektów, w pliku dziennika kompilacji.  
  
 **Brak**  
 Wyklucz zmienne środowiskowe w pliku dziennika kompilacji.  

## <a name="build-timing"></a>Czas kompilacji  
 **Tak**  
  Włącza funkcję chronometrażu kompilacji. Jeśli zaznaczone, czas potrzebny na zakończenie kompilacji jest zamieszczana w oknie danych wyjściowych. Aby uzyskać więcej informacji, zobacz [okno danych wyjściowych](../../ide/reference/output-window.md).  
  
 **Brak**  
 Wyłącza kolejność kompilacji.  
   
## <a name="maximum-concurrent-c-compilations"></a>Maksimum współbieżnych kompilacji C++  
  Określa maksymalną liczbę rdzeni CPU używanych w równoległej kompilacji C++.  
  
## <a name="extensions-to-include"></a>Rozszerzenia do uwzględnienia  
  Określa rozszerzeń nazw plików, które mogą być przenoszone do projektu.  

## <a name="extensions-to-hide"></a>Ukryte rozszerzenia  
  Określa rozszerzeń nazw plików, które nie będą wyświetlane w **Eksploratora rozwiązań** podczas **Pokaż wszystkie pliki** jest włączona.  

 ## <a name="build-customization-search-path"></a>Ścieżka wyszukiwania dostosowania kompilacji  
  Określa listę katalogów, zawierające Rules pliki, które pomagają zdefiniować reguły kompilacji dla projektów.  

# <a name="solution-explorer-mode"></a>Tryb Eksploratora rozwiązań  
 **Pokaż tylko pliki w projekcie**  
  Konfiguruje **Eksploratora rozwiązań** Aby wyświetlić tylko pliki w projekcie.  
  
 **Pokaż wszystkie pliki**  
  Konfiguruje **Eksploratora rozwiązań** Aby wyświetlić pliki w projekcie i plików na dysku w folderze projektu.  

## <a name="enable-project-caching"></a>Włącz buforowanie projektu
**Tak**  
Umożliwia środowisku Visual Studio do pamięci podręcznej danych projektu tak, aby po przy następnym otwarciu projektu go załadować tych buforowanych danych, zamiast ponownego przetwarzania danych z plików projektu. Przy użyciu danych z pamięci podręcznej można skrócić czas ładowania projektu znacznie.   

**Brak**  
Nie należy używać dane buforowane projektu. Przeanalizować ładuje projekt zawsze pliki projektu.

## <a name="see-also"></a>Zobacz także  
 [Kompilowanie programów C/C++](/cpp/build/building-c-cpp-programs)   
 [Dokumentacja kompilacji w języku C/C++](/cpp/build/reference/c-cpp-building-reference)