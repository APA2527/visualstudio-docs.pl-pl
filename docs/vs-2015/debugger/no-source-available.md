---
title: Brak dostępnego źródła | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.nosource
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- No Source Code Available for the Current Location dialog box
ms.assetid: ed0732bc-4b8c-490f-adb1-af06869a2a6b
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4fd7643dd7334a220d1e5c78ef12bddf07af11f8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630240"
---
# <a name="no-source-available"></a>Nie jest dostępne żadne źródło
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [dostępne źródła nie](https://docs.microsoft.com/visualstudio/debugger/no-source-available).  
  
Projekt nie zawiera kodu źródłowego dla kodu, który chcesz wyświetlić. Najczęstszą przyczyną jest dwukrotne kliknięcie modułu, który nie ma kodu źródłowego w **okna stosu wywołań** lub **okno wątków**. Można kontynuować debugowania, ale nie można użyć okna źródła do ustawiania punktów przerwania i wykonywać inne działania w tej lokalizacji. Jeśli potrzebujesz ustawić punkt przerwania, użyj **okna dezasemblacji** zamiast tego.  
  
 Na stronach właściwości rozwiązania można zmienić katalogi, gdzie debuger wyszukuje pliki źródłowe i polecić debugerowi, aby zignorować wybrane źródło plików. Zobacz [debugowania okno dialogowe strony właściwości rozwiązania źródła plików, typowe właściwości,](../debugger/debug-source-files-common-properties-solution-property-pages-dialog-box.md).  
  
 **Przeglądaj w poszukiwaniu kodu źródłowego**  
 Kliknij ten link, aby otworzyć okno dialogowe, w którym możesz przejść do znalezienia kodu źródłowego.  
  
 **Pokaż Dezasemblację**  
 Uruchamia **okna dezasemblacji**.  
  
 **Zawsze pokazuj dezasemblację dla brakujących plików źródłowych**  
 Wybierz tę opcję, aby wyświetlić **okna dezasemblacji** automatycznie, gdy jest dostępne żadne źródło. To ustawienie można zmienić w **opcje** okno dialogowe **debugowanie** kategorii **ogólne** strony, zaznaczając lub usuwając **Pokaż dezasemblację Jeśli źródło jest niedostępne**.  
  
## <a name="see-also"></a>Zobacz też  
 [Okno dialogowe strony właściwości rozwiązania źródła pliki, typowe właściwości debugowania](../debugger/debug-source-files-common-properties-solution-property-pages-dialog-box.md)   
 [Określ symboli (.pdb) i pliki źródłowe](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [SOS.dll (rozszerzenie do debugowania SOS)](http://msdn.microsoft.com/library/9ac1b522-77ab-4cdc-852a-20fcdc9ae498)



