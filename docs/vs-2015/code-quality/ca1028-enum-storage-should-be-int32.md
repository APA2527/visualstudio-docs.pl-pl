---
title: 'CA1028: Pamięć wyliczenia powinna być Int32 | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1028
- EnumStorageShouldBeInt32
helpviewer_keywords:
- EnumStorageShouldBeInt32
- CA1028
ms.assetid: 87160825-9f39-4142-8d7f-a31fe7ac7b84
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 305bd87a72de1e3ad22b8cf689f10ad49939a34b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49304502"
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028: Pamięć wyliczenia powinna być Int32
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|EnumStorageShouldBeInt32|
|CheckId|CA1028|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Nie jest podstawowym typem wyliczenia publiczne <xref:System.Int32?displayProperty=fullName>.

## <a name="rule-description"></a>Opis reguły
 Wyliczenie to typ wartości, który definiuje zestaw powiązanych, nazwanych stałych. Domyślnie <xref:System.Int32?displayProperty=fullName> typ danych jest używany do przechowywania wartości stałej. Mimo że możesz to zmienić, typ podstawowy, nie jest wymagane lub zalecane w przypadku większości scenariuszy. Należy pamiętać, że żadnych korzyści istotnie poprawiającą wydajność odbywa się za pomocą typu danych, który jest mniejszy niż <xref:System.Int32>. Jeśli nie możesz użyć domyślnego typu danych, należy użyć jednej wspólnej systemu Language (CLS)-zgodnych typów całkowitych <xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32>, lub <xref:System.Int64> aby upewnić się, że wszystkie wartości wyliczenia mogą być reprezentowane w Zgodne ze specyfikacją CLS języków programowania.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej reguły, chyba że występują problemy z rozmiar lub zgodność, należy użyć <xref:System.Int32>. W sytuacjach, gdzie <xref:System.Int32> nie jest wystarczająco duży, aby przechowywać wartości, użyj <xref:System.Int64>. Jeśli zgodność ze starszymi wersjami wymaga mniejszych typów danych, należy użyć <xref:System.Byte> lub <xref:System.Int16>.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Pomijaj ostrzeżeń dla tej reguły, tylko wtedy, gdy problemy ze zgodnością z poprzednimi wersjami tego wymagają. W aplikacjach Niezachowanie zgodności z tą regułą, zazwyczaj nie powoduje problemów. W bibliotekach, gdy wymagana jest współdziałanie języków, brak zgodności z tą regułą może niekorzystnie wpłynąć na użytkowników.

## <a name="example-of-a-violation"></a>Przykładem naruszenia

### <a name="description"></a>Opis
 Poniższy przykład przedstawia dwa wyliczenia, które nie korzystają z zalecanych odpowiedniego typu danych.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Design.EnumIntegralType#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralType/cs/FxCop.Design.EnumIntegralType.cs#1)]
 [!code-vb[FxCop.Design.EnumIntegralType#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralType/vb/FxCop.Design.EnumIntegralType.vb#1)]

## <a name="example-of-how-to-fix"></a>Przykład działania do naprawy

### <a name="description"></a>Opis
 Poniższy przykład naprawia wcześniejszego naruszenia praw, zmieniając odpowiedniego typu danych w celu <xref:System.Int32>.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralTypeFixed/cs/FxCop.Design.EnumIntegralTypeFixed.cs#1)]
 [!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralTypeFixed/vb/FxCop.Design.EnumIntegralTypeFixed.vb#1)]

## <a name="related-rules"></a>Powiązane reguły
 [CA1008: Wyliczenia powinny zawierać wartość zero](../code-quality/ca1008-enums-should-have-zero-value.md)

 [CA1027: Oznacz typy wyliczeniowe atrybutem Flags](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Nie oznaczaj wyliczeń za pomocą atrybutu FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

 [CA1700: Nie nadawaj wartościom wyliczenia nazwy „Reserved”](../code-quality/ca1700-do-not-name-enum-values-reserved.md)

 [CA1712: Nie poprzedzaj wartości wyliczenia nazwą typu](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

## <a name="see-also"></a>Zobacz też
 <xref:System.Byte?displayProperty=fullName><xref:System.Int16?displayProperty=fullName>
 <xref:System.Int32?displayProperty=fullName>
 <xref:System.Int64?displayProperty=fullName>



