---
title: Węzły tekstury | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7df5ef3-dd4f-4964-9d96-34e0e180515e
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bda107323b24940ed8cab18a61f9e491f8392f53
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49252359"
---
# <a name="texture-nodes"></a>Węzły tekstury
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

W projektancie programu do cieniowania węzły tekstury przykładowy różne typy tekstury i geometrii, tworzyć i przekształcenia współrzędnych tekstury. Tekstury zapewniają kolorów i oświetlenia szczegółów obiektów.  
  
## <a name="texture-node-reference"></a>Odwołanie do węzła tekstury  
  
|Węzeł|Szczegóły|Właściwości|  
|----------|-------------|----------------|  
|**Przykładowa mapa sześcienna**|Pobiera próbkę koloru z mapy sześciennej na określonych współrzędnych.<br /><br /> Można użyć mapy sześciennej, aby udostępnić szczegóły koloru na potrzeby efektów odbicia lub aby zastosować dla kulistego obiektu teksturę, która ma zniekształceniami niż tekstury 2-D.<br /><br /> **Dane wejściowe:**<br /><br /> `UVW`: `float3`<br /> Wektor, który określa lokalizację w module tekstury, gdzie próbki. Próbka jest pobierana, gdzie to wektor przecina modułu.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float4`<br /> Przykład koloru.|**Tekstury**<br /> Rejestr tekstury skojarzony z próbnikiem.|  
|**Przykładowa mapa normalna**|Pobiera próbkę normalną z mapy normalnej 2-D na określonych współrzędnych<br /><br /> Można użyć mapy normalnej do symulowania wyglądu dodatkowych szczegółów geometrycznych na powierzchni obiektu. Mapy normalne zawierają spakowane dane, które reprezentuje wektor jednostki, a nie dane koloru<br /><br /> **Dane wejściowe:**<br /><br /> `UV`: `float2`<br /> Współrzędne, w którym próbki.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float3`<br /> Przykład normalny.|**Dostosowanie osi**<br /> Czynnik, który jest używany do dostosowania skrętności dla próbki mapy normalnej.<br /><br /> **Tekstury**<br /> Rejestr tekstury skojarzony z próbnikiem.|  
|**Przesuń mapowanie UV**|Miednice określonego tekstury koordynuje w funkcji czasu.<br /><br /> Służy to do przesunięcia tekstury lub mapy normalnej na powierzchni obiektu.<br /><br /> **Dane wejściowe:**<br /><br /> `UV`: `float2`<br /> Współrzędne, aby przesunąć.<br /><br /> `Time`: `float`<br /> Długość czasu, aby przesunąć, w ciągu kilku sekund.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float2`<br /> Współrzędne panned.|**Prędkość w osi X**<br /> Liczba tekseli przesuwanych wzdłuż osi x na sekundę.<br /><br /> **Prędkość w osi Y**<br /> Liczba tekseli przesuwanych wzdłuż osi y na sekundę.|  
|**Równoległe mapowanie UV**|Powoduje przemieszczenie współrzędnych tekstury określona w funkcji wysokości i kąta widzenia.<br /><br /> Efekt, spowoduje to utworzenie jest znany jako *mapowanie równoległe*, lub mapowanie przemieszczenia wirtualnego. Można go użyć do utworzenia iluzji głębi w przypadku płaskiej powierzchni.<br /><br /> **Dane wejściowe:**<br /><br /> `UV`: `float2`<br /> Współrzędne się wykluczają.<br /><br /> `Height`: `float`<br /> Wartość heightmap, która jest skojarzona z `UV` współrzędnych.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float2`<br /> Przesuniętą współrzędne.|**Płaszczyzna głębi**<br /> Głębokość odniesienia dla efektu równoległe. Domyślna wartość wynosi 0,5. Mniejsze wartości Podnieś teksturę. większe jej zapadanie w powierzchnię.<br /><br /> **Skala głębi**<br /> Skala efekt równoległe. Dzięki temu bardziej lub mniej wyraźnego głębi. Typowe wartości z zakresu od 0,02 do 0,1.|  
|**Obróć mapowanie UV**|Obraca się współrzędnych tekstury określonego wokół punktu centralnego w funkcji czasu.<br /><br /> Służy to do obrócenia tekstury lub mapy normalnej na powierzchni obiektu.<br /><br /> **Dane wejściowe:**<br /><br /> `UV`: `float2`<br /> Współrzędne wymiany.<br /><br /> `Time`: `float`<br /> Długość czasu, aby przesunąć, w ciągu kilku sekund.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float2`<br /> Obrócony współrzędne.|**Współrzędnej X środka**<br /> Współrzędna x definiująca środek obrotu.<br /><br /> **Wyśrodkuj na osi Y**<br /> Współrzędna y definiująca środek obrotu.<br /><br /> **szybkość**<br /> Kąt w radianach, przez który Tekstura obraca się w ciągu sekundy.|  
|**Współrzędna tekstury**|Współrzędne tekstury bieżącego piksela.<br /><br /> Współrzędne tekstury są określane przez interpolacji między atrybutów współrzędnych tekstury pobliskich wierzchołków. To można traktować jako pozycję bieżącego piksela w przestrzeni tekstury.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float2`<br /> Współrzędne tekstury.|Brak|  
|**Wymiary tekstury**|Dane wyjściowe, szerokość i wysokość mapy tekstury 2-D.<br /><br /> Wymiary tekstury umożliwia należy wziąć pod uwagę szerokość i wysokość tekstury w modułu cieniującego.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float2`<br /> Szerokość i wysokość tekstury, wyrażone jako wektor. Szerokość znajduje się w pierwszym elemencie wektora. Wysokość jest przechowywany w elemencie drugiego.|**Tekstury**<br /> Rejestr tekstury skojarzony z wymiarów tekstury.|  
|**Delta Teksela**|Generuje różnicowej (odległość) między tekseli mapy tekstury 2-D.<br /><br /> Delta teksela służy do próbkowania sąsiadujących wartości texel w module cieniującym.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float2`<br /> Delta (odległość) z teksela do dalej teksela (przenoszenie po przekątnej w kierunku dodatnią,), wyrażone jako wektor w przestrzeni tekstury znormalizowana. Pochodzi z pozycji wszystkie tekseli sąsiednich, selektywnie ignorowanie lub Negacja współrzędne U lub V różnicowej.|**Tekstury**<br /> Rejestr tekstury skojarzony z delty teksela.|  
|**Próbki tekstury**|Pobiera próbkę koloru z mapy tekstury 2-D na określonych współrzędnych.<br /><br /> Można użyć mapy tekstury, aby udostępnić szczegóły koloru na powierzchni obiektu.<br /><br /> **Dane wejściowe:**<br /><br /> `UV`: `float2`<br /> Współrzędne, w którym próbki.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float4`<br /> Przykład koloru.|**Tekstury**<br /> Rejestr tekstury skojarzony z próbnikiem.|



