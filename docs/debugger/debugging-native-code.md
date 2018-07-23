---
title: Debugowanie kodu natywnego | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 04/11/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging native code
- debugging [C++], native code
- debugging [Visual Studio], native code
- native code, debugging
ms.assetid: d94eee90-7e0d-4cac-88c1-9831030daa5e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: eba1f156589babb9a3bec38982bd27b7c17a83c8
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/20/2018
ms.locfileid: "39180194"
---
# <a name="debugging-native-code"></a>Debugowanie kodu natywnego
Sekcji omówiono niektóre typowe problemy z debugowania i technik dla natywnych aplikacji. Technik opisanych w tej sekcji są techniki wysokiego poziomu. Mechanika przy użyciu debugera programu Visual Studio, można zobaczyć [plan debugera](../debugger/getting-started-with-the-debugger.md).  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Porady: debugowanie zoptymalizowanego kodu](../debugger/how-to-debug-optimized-code.md)  
 Zawiera wskazówki dotyczące debugowania zoptymalizowane pod kątem kodu, w szczególności dlatego powinna debugowania niezoptymalizowanym wersję usługi programu, domyślne ustawienia pozycji Optymalizacja konfiguracji Debug i Release i porady dotyczące znajdowania błędów, które są wyświetlane tylko w zoptymalizowanym kodzie (włączenie Optymalizacja w konfiguracji kompilacji debugowania).  
  
 [DebugBreak i __debugbreak](../debugger/debugbreak-and-debugbreak.md)  
 W tym artykule opisano Win32 `DebugBreak` funkcji i Link do jego temat referencyjny w zestawie SDK platformy. Opisano również `__debugbreak` wewnętrzne.  
  
 [Potwierdzenia C/C++](../debugger/c-cpp-assertions.md)  
 W tym artykule omówiono instrukcji potwierdzania, jak to działa, zalety korzystania z nich (połowowe błędy logiczne, sprawdzanie wyników operacji i testowanie warunki błędu), ich interakcji z `_DEBUG`oraz typy potwierdzenia obsługiwane w [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 [Porady: debugowanie kodu zestawu wbudowanego](../debugger/how-to-debug-inline-assembly-code.md)  
 Zawiera instrukcje na temat korzystania z okna dezasemblacji Aby wyświetlić instrukcje zestawu i z okna rejestrów, aby wyświetlić zawartość rejestru i zawiera łącza do tematów dotyczących tych oknach.  
  
 [Techniki testowania MFC](../debugger/mfc-debugging-techniques.md)  
 Podano łącza do debugowania programów MFC, łącznie z: afxdebugbreak —, TRACE — makro, wykrywanie pamięci przecieki w MFC, MFC, asercje i zmniejszenie rozmiaru debugowania MFC kompilacji.  
  
 [Techniki testowania CRT](../debugger/crt-debugging-techniques.md)  
 Łącza do debugowania dla biblioteki wykonawczej C, w tym o korzystaniu z biblioteki debugowania CRT, makra dla raportowania, różnice funkcji malloc i _malloc_dbg, pisanie debugowanie funkcji punktów zaczepienia i CRT debugowania sterty.  
  
 [Debugowanie kodu natywnego — często zadawane pytania](../debugger/debugging-native-code-faqs.md)  
 Zawiera odpowiedzi na często zadawane pytania dotyczące debugowania programów Visual C++  
  
 [COM i debugowanie ActiveX](../debugger/com-and-activex-debugging.md)  
 Zawiera informacje dotyczące debugowania aplikacji modelu COM i ActiveX, w tym narzędzia, których można używać dla modelu COM i debugowanie ActiveX.  
  
 [Porady: debugowanie wprowadzonego kodu](../debugger/how-to-debug-injected-code.md)  
 Wskazówki dotyczące debugowania kodu, który używa atrybutów. Instrukcje zawierają włączanie adnotacji źródła, jak wyświetlić wprowadzonego kodu i sposób wyświetlić kod dezasemblacji w bieżącym punkcie Wykonywanie.  
  
 [Wskazówki: Debugowanie aplikacji równoległych](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Opisuje sposób używania **zadań równoległych** i **stosów równoległych** narzędzia systemu windows do debugowania aplikacji równoległej.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Typy projektów Visual C++](../debugger/debugging-preparation-visual-cpp-project-types.md)  
 Zawiera łącza do tematów opisujących sposób debugowania natywnego projektu typów, utworzone przez Szablony projektów Visual C++.  

 [Debugowanie projektów DLL](../debugger/debugging-dll-projects.md) zawiera informacje na temat debugowania bibliotek DLL macierzystych i zarządzanych.
  
 [Przewodnik po funkcjach debugera](../debugger/debugger-feature-tour.md)  
 Zawiera łącza do większych sekcji dokumentacji debugowania. Informacje dotyczące nowości w debugerze, ustawienia i przygotowania, punkty przerwania, obsługa wyjątków, Edytuj i Kontynuuj, debugowanie kodu zarządzanego, debugowanie kodu natywnego, debugowanie SQL i odwołania interfejsu użytkownika.  
  
## <a name="see-also"></a>Zobacz też  
 [Zabezpieczenia debugera](../debugger/debugger-security.md)  
 [Debugowanie w programie Visual Studio](../debugger/index.md) [Przewodnik po funkcjach debugera](../debugger/debugger-feature-tour.md)