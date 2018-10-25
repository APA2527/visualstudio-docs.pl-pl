---
title: Operatory logiczne i operatorzy zaawansowani w wyrażeniach wyszukiwania
ms.date: 11/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: reference
helpviewer_keywords:
- Help Viewer, logical operators in search
- logical operators in search [Help Viewer]
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a2c189afe9051d0f85c7f5f24a928d475d0eaca9
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49872853"
---
# <a name="logical-and-advanced-operators-in-search-expressions"></a>Operatory logiczne i Zaawansowane w wyrażeniach wyszukiwania

Można użyć operatorów logicznych i operatory wyszukiwania zaawansowanego, aby uściślić wyszukiwanie zawartości pomocy w **podglądu pomocy**.

## <a name="logical-operators"></a>Operatory logiczne

Operatory logiczne Określanie wielu warunków wyszukiwania powinny być one łączone w zapytaniu wyszukiwania. W poniższej tabeli nie zawiera operatorów logicznych AND, OR i w pobliżu.

|Aby wyszukać|Zastosowanie|Przykład|Wynik|
|-------------------|---------|-------------|------------|
|Oba warianty pojęć, w tym samym artykule|AND|dib i palety|Tematy, które zawierają "dib" i "palety".|
|Albo termin w artykule|LUB|rastrowych wektor OR|Tematy, które zawierają "rastrowych" lub "vector".|
|Pierwszy okres bez drugi warunek, w tym samym artykule|NIE|"system operacyjny" nie DOS|Tematy, które zawierają "system operacyjny", ale nie "DOS".|
|Oba warianty pojęć blisko siebie w artykule|W POBLIŻU|użytkownik w pobliżu jądra|Tematy zawierające "user" w pobliżu "jądra".|

> [!IMPORTANT]
> Operatory logiczne należy wprowadzić wielkimi literami dla aparatu wyszukiwania, rozpoznawał.

## <a name="advanced-operators"></a>Operatorzy zaawansowani

Operatory wyszukiwania zaawansowanego Uściślij kryteria wyszukiwania dla zawartości, przez określenie miejsca w artykule, aby wyszukać termin wyszukiwania. W poniższej tabeli opisano cztery operatory wyszukiwania zaawansowanego dostępne.

|Aby wyszukać|Zastosowanie|Przykład|Wynik|
|-------------------|---------|-------------|------------|
|Termin w tytuł artykułu|`title:`|`title:binaryreader`|Tematy, które zawierają "binaryreader" w tytułach.|
|Termin w przykładzie kodu|`code:`|`code:readdouble`|Tematy, które zawierają "readdouble" w przykładzie kodu.|
|Termin w przykładzie określonego języka programowania|`code:vb:`|`code:vb:string`|Tematy, które zawierają "string", w przykładzie kodu języka Visual Basic.|
|Artykułu, który jest skojarzony z określonym indeksem słowem kluczowym|`keyword:`|`keyword:readbyte`|Tematy, które są skojarzone ze słowem kluczowym "readbyte" indeksu.|

> [!IMPORTANT]
> Należy wprowadzić operatory wyszukiwania zaawansowanego z dwukropkiem ostateczne i nie pośredniczące odstęp przed dwukropkiem dla aparatów wyszukiwania można je rozpoznać.

### <a name="programming-languages-for-code-examples"></a>Języki programowania, przykłady kodu

Możesz użyć `code:` operatora, aby znaleźć zawartość informacji na temat kilku języków programowania. Aby zwrócić przykłady dla określonego języka programowania, użyj jednej z następujących wartości język programowania:

|Język programowania|Składnia poleceń wyszukiwania — operator|
| - |---------|
|Visual Basic|`code:vb`<br/>`code:visualbasic`|
|C#|`code:c#`<br/>`code:csharp`|
|C++|`code:cpp`<br/>`code:c++`<br/>`code:cplusplus`|
|F#|`code:f#`<br/>`code:fsharp`|
|JavaScript|`code:javascript`<br/>`code:js`|
|XAML|`code:xaml`|

> [!NOTE]
> `code:` Operatora tylko znajdzie zawartości oznaczonej etykietą programowania języka, w przeciwieństwie do zawartości, ogólną oznaczony jako kod.

## <a name="see-also"></a>Zobacz także

- [Porady: wyszukiwanie tematów](how-to-search-for-topics.md)
- [Podgląd Pomocy firmy Microsoft](microsoft-help-viewer.md)
