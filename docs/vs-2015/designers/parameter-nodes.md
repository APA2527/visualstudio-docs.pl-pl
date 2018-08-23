---
title: Węzły parametrów | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da54db0b-3a3d-48dc-858c-7ac43aa04b13
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bed941a35af21b78ea5159a218ccd36d2ff5f1e9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680328"
---
# <a name="parameter-nodes"></a>Węzły parametrów
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [węzły parametrów](https://docs.microsoft.com/visualstudio/designers/parameter-nodes).  
  
W projektancie programu do cieniowania węzły parametrów reprezentują dane wejściowe programu do cieniowania, które są pod kontrolą aplikacji na podstawie na rysunku, na przykład, właściwości materiału, światła kierunkowego, położenie kamery i czasu. Ponieważ możesz zmienić te parametry, z każdym wywołaniem rysowania, można użyć tego samego programu do cieniowania, aby nadać inny wygląd obiektu.  
  
## <a name="parameter-node-reference"></a>Węzeł odwołania do parametru  
  
|Węzeł|Szczegóły|Właściwości|  
|----------|-------------|----------------|  
|**Pozycja kamery świata**|Pozycja kamery w przestrzeni świata.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float4`<br /> Pozycja kamery.|Brak|  
|**Kierunek światła**|Wektor definiujący kierunek, w którym światła jest rzutowanie ze źródła światła w przestrzeni świata.<br /><br /> Służy to do obliczenia udziału oświetlenia i odblasków w przestrzeni świata.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float3`<br /> Wektor od bieżącego piksela do źródła światła.|Brak|  
|**Otoczenie materiału**|Udział koloru rozpraszania bieżącego piksela, która jest przypisana do oświetlenia pośredniego.<br /><br /> Kolor rozpraszania piksel symuluje sposobu interakcji oświetlenia nierównej powierzchni. Otaczających materiał parametr umożliwia określenie w przybliżeniu jak wspiera oświetlenia pośredniego w wyglądzie obiektów w świecie rzeczywistym.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float4`<br /> Kolor rozpraszania bieżącego piksela, która wynika z pośrednich — czyli otoczenia — oświetlenia.|**Dostęp do**<br /> **Publiczne** Aby włączyć właściwość można ustawić w edytorze modeli w przeciwnym razie **prywatnej**.<br /><br /> **Wartość**<br /> Kolor rozpraszania bieżącego piksela, która wynika z pośrednich — czyli otoczenia — oświetlenia.|  
|**Rozpraszanie materiału**|Kolor, który opisuje, jak diffuses przez bieżący piksel oświetlenia bezpośredniego.<br /><br /> Kolor rozpraszania piksel symuluje sposobu interakcji oświetlenia nierównej powierzchni. Można zmienić, jak diffuses przez bieżący piksel oświetlenia bezpośredniego służy parametr rozpraszanie materiału — czyli kierunkowego punktu i reflektor.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float4`<br /> Kolor, który opisuje, jak diffuses przez bieżący piksel oświetlenia bezpośredniego.|**Dostęp do**<br /> **Publiczne** Aby włączyć właściwość można ustawić w edytorze modeli w przeciwnym razie **prywatnej**.<br /><br /> **Wartość**<br /> Kolor, który opisuje, jak diffuses przez bieżący piksel oświetlenia bezpośredniego.|  
|**Emisja materiału**|Udział koloru materiału bieżącego piksela, które jest przypisane do oświetlenia dostarczającego do samego siebie.<br /><br /> Służy to do symulowania świecącego obiektu; oznacza to, że obiekt, który wydziela światło. Ta światło nie ma wpływu na inne obiekty.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float4`<br /> Udział koloru materiału bieżącego piksela, które wkrótce samodzielnie emitowanego oświetlenia.|**Dostęp do**<br /> **Publiczne** Aby włączyć właściwość można ustawić w edytorze modeli w przeciwnym razie **prywatnej**.<br /><br /> **Wartość**<br /> Udział koloru materiału bieżącego piksela, które wkrótce samodzielnie emitowanego oświetlenia.|  
|**Odblask materiału**|Kolor opisujący Odbijanie oświetlenia bezpośredniego przez bieżącego piksela.<br /><br /> Kolor Odblaskowy piksela symuluje sposobu interakcji oświetlenia smooth, lustrzanej powierzchni. Materiał Odblaskowy parametr służy do zmiany, jak bieżący piksel oświetlenia bezpośredniego — czyli kierunkowego punktu i reflektor.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float4`<br /> Kolor opisujący Odbijanie oświetlenia bezpośredniego przez bieżącego piksela.|**Dostęp do**<br /> **Publiczne** umożliwia właściwość można ustawić w edytorze modeli w przeciwnym razie **prywatnej**.<br /><br /> **Wartość**<br /> Kolor opisujący Odbijanie oświetlenia bezpośredniego przez bieżącego piksela.|  
|**Moc odblasku materiału**|Wartość skalarna opisująca intensywność światła odbitego.<br /><br /> Im większy moc odblasku, bardziej intensywny i Week stają się światłem odbitym.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float`<br /> Termin wykładniczego, opisująca intensywność światła odbitego na bieżącego piksela.|**Dostęp do**<br /> **Publiczne** Aby włączyć właściwość można ustawić w edytorze modeli w przeciwnym razie **prywatnej**.<br /><br /> **Wartość**<br /> Wykładnik definiujący intensywność światła odbitego na bieżącego piksela.|  
|**Znormalizowany czas**|Czas w sekundach, znormalizowane do zakresu [0, 1], taki sposób, że gdy jest to czas osiągnięcia 1, przywraca 0.<br /><br /> Służy to jako parametru w obliczeniach cieniowania, na przykład celu animowania współrzędnych tekstury, wartości kolorów lub innych atrybutów.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float`<br /> Znormalizowany czas w sekundach.|Brak|  
|**czas**|Czas w sekundach.<br /><br /> Służy to jako parametru w obliczeniach cieniowania, na przykład celu animowania współrzędnych tekstury, wartości kolorów lub innych atrybutów.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float`<br /> Czas w sekundach.|Brak|



