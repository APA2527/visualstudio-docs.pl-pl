---
title: Właściwości kształtów obrazu
description: Dowiedz się więcej o kształtach obrazów i sposobach używania kształtów obrazu w celu określenia sposobu wyświetlania klas domeny w wygenerowanym projektancie.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.selectimagedialog
- vs.dsltools.dsldesigner.imageshape
helpviewer_keywords:
- Domain-Specific Language, image shape
author: JoshuaPartlow
ms.author: joshuapa
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 8bbd2fff30ab59d14c8aa2762d8cca942063bd79
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99918353"
---
# <a name="properties-of-image-shapes"></a>Właściwości kształtów obrazu

Można użyć kształtów obrazu, aby określić sposób wyświetlania klas domeny w wygenerowanym projektancie. Zdefiniuj kształt obrazu, ustawiając `Image` Właściwość klasy do wstępnie zdefiniowanego pliku obrazu. Obsługiwane są następujące formaty:

- gif

- jpg

- jpeg

- bmp

- . wmf

- . EMF

- png

Domyślnie pliki zasobów projektanta, takie jak pliki obrazów, znajdują się w folderze **resources** w projekcie **DSL** .

Aby uzyskać więcej informacji, zobacz [How to define a Domain-Specific Language](../modeling/how-to-define-a-domain-specific-language.md). Aby uzyskać więcej informacji na temat sposobu korzystania z tych właściwości, zobacz [Dostosowywanie i rozszerzanie języka Domain-Specific](../modeling/customizing-and-extending-a-domain-specific-language.md).

Kształty obrazów mają właściwości, które są wymienione w poniższej tabeli.

|Właściwość|Opis|Domyślne|
|-|-|-|
|Kolor wypełnienia|Kolor wypełnienia tego kształtu.|Biały|
|Tryb gradientu wypełnienia|Tryb gradientu wypełnienia tego kształtu.|Pozioma|
|Ma domyślne punkty połączenia|Jeśli `True` kształt będzie używać górnego, dolnego, lewego i prawego punktu połączenia w wygenerowanym projektancie.|Fałsz|
|Kolor konturu|Kolor konturu tego kształtu.|Czarnoskórzy|
|Styl kreskowania konturu|Styl kreskowania konturu tego kształtu (pełny, kreska, kropka, DashDot, DashDotDot lub niestandardowy).|Ciągła|
|Grubość konturu|Grubość konturu tego kształtu.|0,03125|
|Kolor tekstu|Kolor używany dla dekoratory tekstu, które są skojarzone z tym kształtem.|Czarnoskórzy|
|Modyfikator dostępu|Modyfikator dostępu kształtu geometrycznego (publiczny lub wewnętrzny).|Publiczne|
|Atrybuty niestandardowe|Służy do dodawania atrybutów do klasy kodu źródłowego, która jest generowana z tego kształtu.|\<none>|
|Generuje podwójny pochodny|Jeśli `True` , zostanie wygenerowany zarówno klasę bazową, jak i Klasa częściowa (do obsługi dostosowywania za pomocą przesłonięć). Aby uzyskać więcej informacji, zobacz [przesłanianie i rozszerzanie wygenerowanych klas](../modeling/overriding-and-extending-the-generated-classes.md).|Fałsz|
|Ma Konstruktor niestandardowy|Jeśli `True` w kodzie źródłowym zostanie podany Konstruktor niestandardowy. Aby uzyskać więcej informacji, zobacz [przesłanianie i rozszerzanie wygenerowanych klas](../modeling/overriding-and-extending-the-generated-classes.md).|Fałsz|
|Modyfikator dziedziczenia|Opisuje rodzaj dziedziczenia klasy kodu źródłowego, która jest generowana z kształtu obrazu ( `none` `abstract` lub `sealed` ).|brak|
|Podstawowy kształt obrazu|Klasa bazowa tego kształtu.|(brak)|
|Nazwa|Nazwa tego kształtu.|Bieżąca nazwa|
|Przestrzeń nazw|Przestrzeń nazw, która jest powiązana z tym kształtem.|Bieżąca przestrzeń nazw|
|Typ etykietki narzędzia|Miejsce, w którym jest zdefiniowana etykietka narzędzia (stała, zmienna lub brak). Jeśli stała, wartość `Fixed Tooltip Text` właściwości jest używana jako etykietka narzędzia; Jeśli zmienna, a następnie etykietka narzędzia jest definiowana w kodzie niestandardowym.|brak|
|Uwagi|Nieformalne notatki, które są skojarzone z tym kształtem.|\<none>|
|Początkowa wysokość|Początkowa wysokość tego kształtu (w calach).|1|
|Szerokość początkowa|Początkowa Szerokość tego kształtu (w calach).|1.5|
|Uwidoczniony kolor wypełnienia jako właściwość<br /><br /> Uwidaczniany tryb gradientu wypełnienia<br /><br /> Uwidoczniony kolor konturu jako właściwość<br /><br /> Uwidoczniony styl kreskowania konturu jako właściwość<br /><br /> Uwidoczniona grubość konturu jako właściwość<br /><br /> Uwidacznia kolor tekstu|Jeśli `True` użytkownik może ustawić właściwość wartość dla kształtu. Aby ustawić tę opcję, kliknij prawym przyciskiem myszy definicję kształtu, a następnie kliknij pozycję **Dodaj uwidocznione**.|Fałsz|
|Opis|Służy do dokumentowania wygenerowanego projektanta.|\<none>|
|Nazwa wyświetlana|Nazwa, która będzie wyświetlana w wygenerowanym projektancie dla tego kształtu.|\<none>|
|Stały tekst etykietki narzędzia|Tekst, który jest używany dla stałej etykietki narzędzia.|\<none>|
|Słowo kluczowe pomocy|Słowo kluczowe, które jest używane do indeksowania pomocy F1 dla tego elementu.|\<none>|
|Image (Obraz)|Ścieżka do pliku obrazu, który jest używany dla tego kształtu.|\<none>|

## <a name="see-also"></a>Zobacz też

- [narzędzia języka specyficznego dla domeny słownik](/previous-versions/bb126564(v=vs.100))