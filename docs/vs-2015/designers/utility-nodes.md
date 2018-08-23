---
title: Węzły narzędzi | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff732221-b731-424c-ad5b-82ef5f21dff5
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fa242e6c2f609c8ac6214fcbd20d210f7c794b77
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681252"
---
# <a name="utility-nodes"></a>Węzły narzędzi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [węzły narzędzi](https://docs.microsoft.com/visualstudio/designers/utility-nodes).  
  
W projektancie programu do cieniowania węzły narzędzie reprezentują obliczeniach cieniowania wspólny, przydatne, które nie pasują do innych kategorii. Niektóre węzły narzędzie do wykonywania prostych operacji takich jak dołączanie wektorów razem lub wybierając warunkowo wyniki oraz wykonywania innych złożonych operacji, takich jak przetwarzanie oświetlenia wkładów, zgodnie z modele oświetlenia popularne.  
  
## <a name="utility-node-reference"></a>Odwołanie do narzędzia node  
  
|Węzeł|Szczegóły|Właściwości|  
|----------|-------------|----------------|  
|**Dołącz wektor**|Tworzy wektor, dodając określoną danych wejściowych ze sobą.<br /><br /> **Dane wejściowe:**<br /><br /> `Vector`: `float`, `float2`, lub `float3`<br /> Wartości, które można dołączyć do.<br /><br /> `Value to Append`: `float`<br /> Wartość do dołączenia.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float2`, `float3`, lub `float4` w zależności od typu danych wejściowych `Vector`<br /> Nowy wektor.|Brak|  
|**Element Fresnela**|Oblicza Fresnela oparte na określonej normalnych powierzchni.<br /><br /> Element Fresnela fall off wartość określa, jak blisko normalna powierzchni bieżącego piksela pokrywa się z wektorem widoku. Gdy wektory są wyrównane, wynikiem funkcji jest 0. Wynik zwiększa się, jak wektory stają się mniej podobne i osiągnie maksymalną, gdy wektory są prostopadły. Możesz użyć tego, aby efektu więcej lub mniej jasne na podstawie relacji między orientację bieżącego piksela i kamery.<br /><br /> **Dane wejściowe:**<br /><br /> `Surface Normal`: `float3`<br /> Normalna powierzchni bieżącego piksela, zdefiniowane w przestrzeni stycznej bieżącego piksela. Służy to do perturb powierzchnia widoczna normalne, tak jak w normalnym mapowania.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float`<br /> Współczynnik odbicia kuli bieżącego piksela.|**Wykładnik**<br /> Wykładnik, który jest używany do obliczania Fresnela.|  
|**If**|Warunkowo wybiera jeden z trzech potencjalnych wyników dla danego składnika. Warunek jest definiowany przez relację między dwóch pozostałych określonego danych wejściowych.<br /><br /> Dla każdego składnika wyniku jest wybierany odpowiadający składnik jednego z trzech potencjalnych wyników, na podstawie relacji między odpowiadającymi składnikami dwóch pierwszych danych wejściowych.<br /><br /> **Dane wejściowe:**<br /><br /> `X`: `float`, `float2`, `float3`, lub `float4`<br /> Wartość po lewej stronie do porównania.<br /><br /> `Y`: tego samego typu jako dane wejściowe `X`<br /> Wartość po prawej stronie do porównania.<br /><br /> `X > Y`: tego samego typu jako dane wejściowe `X`<br /> Wartości, które zostały wybrane podczas `X` jest większa niż `Y`.<br /><br /> `X = Y`: tego samego typu jako dane wejściowe `X`<br /> Wartości, które zostały wybrane podczas `X` jest równa `Y`.<br /><br /> `X < Y`: tego samego typu jako dane wejściowe `X`<br /> Wartości, które zostały wybrane podczas `X` jest mniejsza niż `Y`.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float3`<br /> Wybrane wyniku dla danego składnika.|Brak|  
|**Lamberta**|Oblicza kolor bieżącego piksela zgodnie z modelu oświetlenia Lamberta przy użyciu określonego normalnych powierzchni.<br /><br /> Ten kolor to suma koloru otoczenia i oświetleniem wnosić swój kod w obszarze oświetlenia bezpośredniego. Kolor otoczenia przybliża łączny udział oświetlenia pośredniego, lecz daje płaski i niekontrastowy obraz bez udziału dodatkowego oświetlenia. Rozpraszanie oświetlenia ułatwia dodanie kształtu i głębi do obiektu.<br /><br /> **Dane wejściowe:**<br /><br /> `Surface Normal`: `float3`<br /> Normalna powierzchni bieżącego piksela, zdefiniowane w przestrzeni stycznej bieżącego piksela. Służy to do perturb powierzchnia widoczna normalne, tak jak w normalnym mapowania.<br /><br /> `Diffuse Color`: `float3`<br /> Kolor rozpraszania bieżącego piksela zazwyczaj **koloru punktu**. Jeśli nie podano żadnych danych wejściowych, wartością domyślną jest białe.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float3`<br /> Kolor rozpraszania bieżącego piksela.|Brak|  
|**Wektor maski**|Składniki maski określonego wektora.<br /><br /> Możesz użyć tego do usunięcia kanałów określonego koloru z wartości koloru lub aby uniemożliwić określonych składników mających wpływ na dalsze obliczenia.<br /><br /> **Dane wejściowe:**<br /><br /> `Vector`: `float4`<br /> Wektor, który ma być maskowane.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float4`<br /> Wektor maskowanego.|**Czerwony / X**<br /> **FALSE** powoduje zamaskowanie składnika czerwony (x); w przeciwnym razie **True**.<br /><br /> **Zielony / Y**<br /> **FALSE** powoduje zamaskowanie składnika zielony (y); w przeciwnym razie **True**.<br /><br /> **Niebieski / Z**<br /> **FALSE** powoduje zamaskowanie składnika niebieski (z); w przeciwnym razie **True**.<br /><br /> **Alfa / W**<br /> **FALSE** powoduje zamaskowanie składnika alfa (w); w przeciwnym razie **True**.|  
|**Wektor odbicia**|Oblicza wektor odbicia dla bieżącego piksela w przestrzeni stycznej na podstawie pozycji kamery.<br /><br /> Służy to do obliczenia odbić, współrzędnych mapy sześciennej i odblasków oświetlenia<br /><br /> **Dane wejściowe:**<br /><br /> `Tangent Space Surface Normal`: `float3`<br /> Normalna powierzchni bieżącego piksela, zdefiniowane w przestrzeni stycznej bieżącego piksela. Służy to do perturb powierzchnia widoczna normalne, tak jak w normalnym mapowania.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float3`<br /> Wektor odbicia.|Brak|  
|**Odblasku**|Oblicza udział odblasków oświetlenia zgodnie z model Phong oświetlenia przy użyciu określonego normalnych powierzchni.<br /><br /> Odblasków oświetlenia zapewnia wygląd do obiektu, na przykład wody, plastiku lub metali.<br /><br /> **Dane wejściowe:**<br /><br /> `Surface Normal`: `float3`<br /> Normalna powierzchni bieżącego piksela, zdefiniowane w przestrzeni stycznej bieżącego piksela. Służy to do perturb powierzchnia widoczna normalne, tak jak w normalnym mapowania.<br /><br /> **Dane wyjściowe:**<br /><br /> `Output`: `float3`<br /> Udział koloru materiału światłem odbitym.|Brak|



