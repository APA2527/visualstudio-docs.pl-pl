---
title: 'CA1307: Określ StringComparison'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 67f0d5152dcdef5ffa3abb76d92e68fd99f9b637
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550417"
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307: Określ StringComparison

|||
|-|-|
|TypeName|SpecifyStringComparison|
|CheckId|CA1307|
|Kategoria|Microsoft.Globalization|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Operacja porównania ciągu używa przeciążenia metody, która nie ustawia <xref:System.StringComparison> parametru.

## <a name="rule-description"></a>Opis reguły
 Wiele ciągów operacje najważniejszych <xref:System.String.Compare%2A> i <xref:System.String.Equals%2A> metod, zapewnienia przeciążenia, które akceptuje <xref:System.StringComparison> wartość wyliczenia jako parametr.

 Zawsze, gdy istnieje tego przyjmuje przeciążenie <xref:System.StringComparison> parametru należy używać zamiast przeciążenia, które nie przyjmuje tego parametru. Poprzez jawne ustawienie tego parametru, kod jest często co wykonane i łatwiejsze w utrzymaniu.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, należy zmienić metody porównania ciągu do przeciążenia, które akceptują <xref:System.StringComparison> wyliczenia jako parametr. Na przykład: zmienianie `String.Compare(str1, str2)` do `String.Compare(str1, str2, StringComparison.Ordinal)`.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Jest bezpieczne pominąć ostrzeżenie od tej reguły, gdy biblioteka lub aplikacja jest przeznaczona dla ograniczone odbiorców lokalnych i w związku z tym nie będzie lokalizowany.

## <a name="see-also"></a>Zobacz także

- [Ostrzeżenia dotyczące globalizacji](../code-quality/globalization-warnings.md)
- [CA1309: Używaj wyliczenia StringComparison stosującego reguły sortowania oparte na wartości](../code-quality/ca1309-use-ordinal-stringcomparison.md)