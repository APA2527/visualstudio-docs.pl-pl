---
title: Konspekt | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- outlining
- Visual Studio, expand/collapse code
- Visual Studio, outlining
- expand/collapse code
- code [Visual Studio], outlining
- code [Visual Studio], hiding
- outlining code
ms.assetid: d1476758-9d35-4d74-b63c-310661932ecd
caps.latest.revision: 38
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 939bb5ac1188a54217339c1bf3e9e3a828493d90
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629812"
---
# <a name="outlining"></a>Tworzenie konspektu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [konspekt](https://docs.microsoft.com/visualstudio/ide/outlining).  
  
Można ukryć jakiś kod w widoku, zwijając obszar kodu, aby była ona wyświetlana w obszarze znak plus (+). Zwinięty region jest rozwiniesz, klikając znak plus. (Lub można nacisnąć klawisze CTRL + M + M, aby zwinąć region, a następnie klawisz CTRL + M + M aby go rozwinąć ponownie). Można również zwinąć konspektu region przez dwukrotne kliknięcie każdego wiersza w regionie na marginesie konspektu, który jest wyświetlany z lewej strony kodu. Jako etykietka narzędzia można wyświetlić zawartość Zwinięty region, po najechaniu kursorem na zwinięty region.  
  
 Regiony na marginesie konspektu są również wyróżnione po najechaniu kursorem na marginesie za pomocą myszy. Domyślny kolor wyróżnienia, może wydawać się zamiast Blade, w niektórych konfiguracjach kolorów. Można zmienić w **narzędzia/Opcje/środowisko/czcionki i kolory/Collapsible Region**.  
  
 Podczas pracy w kodzie schemat można rozszerzyć sekcje, które chcesz pracować nad, zwijając, gdy będzie gotowe, a następnie przenieść do innej sekcji. Jeśli chcesz, aby Tworzenie konspektu wyświetlane, można użyć **Zatrzymaj tworzenie konspektu** polecenie, aby usunąć informacje konspektu bez zakłócania działania kodu bazowego.  
  
 **Cofnij** i **wykonaj ponownie** polecenia na **Edytuj** menu mają wpływ na te akcje. **Kopiowania**, **Wytnij**, **Wklej**, i operacji przeciągania i upuszczania zachowywanie informacji konspektu, ale nie stan region zwijany. Na przykład podczas kopiowania region, który jest zwinięte, **Wklej** operacji będzie Wklej skopiowany tekst jako rozwinięty region.  
  
> [!CAUTION]
>  Po zmianie konturu region konspekt mogą zostać utracone. Na przykład usunięcia lub operacji Znajdź i Zamień może wymazać koniec regionu.  
  
 Następujące polecenia można znaleźć na **edycji/konspekt** podmenu.  
  
|||  
|-|-|  
|Ukryj zaznaczenie|(CTRL + M, CTRL + H) - zwija wybranego bloku kodu, który normalnie byłyby niedostępne dla konspektu, na przykład `if` bloku. Aby usunąć niestandardowy regionie, użyj **Zatrzymaj ukrywanie bieżącego** (lub CTRL + M, CTRL + U). Nie jest dostępna w języku Visual Basic.|  
|Przełącz rozszerzanie konspektu|-Odwraca bieżący stan ukryte lub rozszerzona najbardziej wewnętrzną funkcją zwijanie sekcji, gdy kursor znajduje się w zagnieżdżonych zwiniętą sekcję.|  
|Przełącz wszystkie konspekty|(CTRL + M, CTRL + L) — zestawy we wszystkich regionach do tej samej zwijania i rozwijania stanu. Jeśli niektóre regiony są rozszerzane, a niektóre zwinięte, następnie zwinięte regiony są rozwijane.|  
|Przestań tworzyć konspekt|(CTRL + M, CTRL + P) — usuwa wszystkie informacje konspektu dla całego dokumentu.|  
|Zatrzymaj ukrywanie bieżącego|(CTRL + M, CTRL + U) - usuwa konspektu informacje dotyczące aktualnie wybranego regionu użytkownika. Nie jest dostępna w języku Visual Basic.|  
|Zwiń do definicji|(CTRL + M, CTRL + O) - Zwija wszystkie typy elementów członkowskich.|  
|Zwiń blok:\<logiczne granic >|(Visual C++) Zwija regionu w funkcji znajduje się punkt wstawiania. Na przykład jeśli punkt wstawiania znajduje się wewnątrz pętli, pętla jest ukryta.|  
|Zwiń wszystkie w: \<logicznej struktury >|(Visual C++) Zwija wszystkie struktury wewnątrz funkcji.|  
  
 Aby zdefiniować regionów tekst, który chcesz rozwinąć lub zwinąć umożliwia także zestawu SDK programu Visual Studio. Zobacz [wskazówki: Tworzenie konspektu](../extensibility/walkthrough-outlining.md).



