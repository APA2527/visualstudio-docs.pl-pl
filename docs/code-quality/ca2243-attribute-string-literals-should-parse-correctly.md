---
title: 'CA2243: Literały ciągu atrybutu powinny być analizowane poprawnie'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2243
- AttributeStringLiteralsShouldParseCorrectly
helpviewer_keywords:
- AttributeStringLiteralsShouldParseCorrectly
- CA2243
ms.assetid: bfadb366-379d-4ee4-b17b-c4a09bf1106b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c6808520f3b28a2da8421394619550166d88d52d
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551941"
---
# <a name="ca2243-attribute-string-literals-should-parse-correctly"></a>CA2243: Literały ciągu atrybutu powinny być analizowane poprawnie

|||
|-|-|
|TypeName|AttributeStringLiteralsShouldParseCorrectly|
|CheckId|CA2243|
|Kategoria|Microsoft.Usage|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Parametr literału ciągu atrybutu nie analizuje poprawnie adresu URL, identyfikator GUID lub wersji.

## <a name="rule-description"></a>Opis reguły
 Ponieważ atrybuty są uzyskiwane z <xref:System.Attribute?displayProperty=fullName>i atrybuty są używane w czasie kompilacji, tylko wartości stałych można przekazać do ich konstruktory. Parametry atrybutów reprezentujące musi adresy URL, identyfikatory GUID i wersji nie może być typizowana jako <xref:System.Uri?displayProperty=fullName>, <xref:System.Guid?displayProperty=fullName>, i <xref:System.Version?displayProperty=fullName>, ponieważ te typy nie może być reprezentowana jako stałe. Zamiast tego musi być reprezentowana przez parametry.

 Ponieważ parametru zostanie podana jako ciąg znaków, jest możliwe, że w czasie kompilacji można przekazać parametr niepoprawnie sformatowany.

 Ta reguła używa heurystyki nazewnictwa w celu odnalezienia parametry, które reprezentują jednolity identyfikator zasobów (URI), globalnie unikatowy identyfikator (GUID) lub wersji i sprawdza, czy przekazana wartość jest poprawna.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Zmień ciąg parametru na poprawnie sformułowany adres URL, identyfikator GUID lub wersji.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Jest bezpieczne pominąć ostrzeżenie od tej reguły, jeśli parametr nie reprezentuje adres URL, identyfikator GUID lub wersji.

## <a name="example"></a>Przykład
 Poniższy przykład zawiera kod dla AssemblyFileVersionAttribute, który narusza tę regułę.

 [!code-csharp[FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly#1](../code-quality/codesnippet/CSharp/ca2243-attribute-string-literals-should-parse-correctly_1.cs)]

 Reguła jest wyzwalana przez następujące parametry:

- Parametry, które zawierają "version" i nie można przeanalizować System.Version.

- Parametry, które zawierają "guid" i nie można przeanalizować System.Guid.

- Parametry, które zawierają "uri", "urn" lub "url" i nie można przeanalizować na System.Uri.

## <a name="see-also"></a>Zobacz także

- [CA1054: Parametry identyfikatora URI nie powinny być ciągami](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)