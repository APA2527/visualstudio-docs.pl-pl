---
title: 'CA1043: Używaj argumentu integral lub string dla indeksatorów | Dokumentacja firmy Microsoft'
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
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: db2b365626efc1a5735adf986d1b49ac52c2c72b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49951564"
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043: Dla indeksatorów używaj argumentów integral lub string
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseIntegralOrStringArgumentForIndexers|
|CheckId|CA1043|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Typ publiczny lub chroniony zawiera publiczny lub chroniony indeksatora, który używa innego niż typ indeksu <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, lub <xref:System.String?displayProperty=fullName>.

## <a name="rule-description"></a>Opis reguły
 Indeksatory, oznacza to, że właściwości indeksowanych powinny używać typu integer lub string dla indeksu. Te typy są zwykle używane do indeksowania struktur danych i zwiększyć użyteczność biblioteki. Korzystanie z <xref:System.Object> typu powinny być ograniczone do tych przypadków, w którym określonego typu integer lub string nie można określić w czasie projektowania. Jeśli projekt wymaga innych typów dla indeksu, ponowne rozpatrzenie czy typ reprezentuje magazyn danych logicznych. Jeśli nie stanowi w magazynie danych logicznych, należy użyć metody.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, Zmień indeks typu integer lub string, lub użyć metody zamiast indeksatora.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Pomijaj ostrzeżeń dla tej reguły tylko po dokładnego rozważenia potrzebę niestandardowe indeksatora.

## <a name="example"></a>Przykład
 W poniższym przykładzie pokazano działanie indeksatora, który używa <xref:System.Int32> indeksu.

 [!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.IntegralOrStringIndexers/cpp/FxCop.Design.IntegralOrStringIndexers.cpp#1)]
 [!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.IntegralOrStringIndexers/cs/FxCop.Design.IntegralOrStringIndexers.cs#1)]
 [!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.IntegralOrStringIndexers/vb/FxCop.Design.IntegralOrStringIndexers.vb#1)]

## <a name="related-rules"></a>Powiązane reguły
 [CA1023: Indeksatory nie powinny być wielowymiarowe](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)

 [CA1024: Używaj właściwości wszędzie tam, gdzie jest to odpowiednie](../code-quality/ca1024-use-properties-where-appropriate.md)



