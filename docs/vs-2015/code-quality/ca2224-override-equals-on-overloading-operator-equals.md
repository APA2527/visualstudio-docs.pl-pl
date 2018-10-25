---
title: 'CA2224: Przesłoń metodę equals przeciążając operator equals | Dokumentacja firmy Microsoft'
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
- CA2224
- OverrideEqualsOnOverloadingOperatorEquals
- OverrideEqualsOnOverridingOperatorEquals
helpviewer_keywords:
- OverrideEqualsOnOverloadingOperatorEquals
- CA2224
ms.assetid: 7312afd9-84ba-417f-923e-7a159b53bf70
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 66f4b4bcc7c2c1d359f5d8fa91227fb51a27adc4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49815237"
---
# <a name="ca2224-override-equals-on-overloading-operator-equals"></a>CA2224: Przesłoń metodę equals, przeciążając operator equals
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|OverrideEqualsOnOverloadingOperatorEquals|
|CheckId|CA2224|
|Kategoria|Microsoft.Usage|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Typ publiczny implementuje operator równości, ale nie przesłania <xref:System.Object.Equals%2A?displayProperty=fullName>.

## <a name="rule-description"></a>Opis reguły
 Operator równości ma być syntaktycznie wygodny sposób uzyskać dostęp do funkcji <xref:System.Object.Equals%2A> metody. W przypadku zastosowania operatora równości swojej logiki musi być taka sama jak w przypadku <xref:System.Object.Equals%2A>.

 Kompilator języka C# generuje ostrzeżenie, jeśli kod narusza tę regułę.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, należy albo usuń implementacja operatora równości lub zastąpić <xref:System.Object.Equals%2A> i mieć dwie metody zwracają takie same wartości. Operator równości nie wprowadza niespójne zachowanie, można naprawić naruszenia, zapewniając implementację <xref:System.Object.Equals%2A> wywołująca <xref:System.Object.Equals%2A> metody w klasie bazowej.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Bezpiecznie Pomijaj ostrzeżeń dla tej reguły, jeśli operatora równości zwraca taką samą wartość jak dziedziczona implementacja <xref:System.Object.Equals%2A>. Sekcja przykład zawiera typ, który można bezpiecznie Pomijaj ostrzeżeń dla tej reguły.

## <a name="examples-of-inconsistent-equality-definitions"></a>Przykłady definicje niespójne równości

### <a name="description"></a>Opis
 Poniższy przykład pokazuje typ z definicjami niespójne równości. `BadPoint` zmienia znaczenie równości, zapewniając implementację niestandardową operatora równości, lecz nie przesłania <xref:System.Object.Equals%2A> tak, aby zachowuje się tak samo.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.OperatorEqualsRequiresEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OperatorEqualsRequiresEquals/cs/FxCop.Usage.OperatorEqualsRequiresEquals.cs#1)]

## <a name="example"></a>Przykład
 Poniższy kod sprawdza zachowanie `BadPoint`.

 [!code-csharp[FxCop.Usage.TestOperatorEqualsRequiresEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.TestOperatorEqualsRequiresEquals/cs/FxCop.Usage.TestOperatorEqualsRequiresEquals.cs#1)]

 Ten przykład generuje następujące dane wyjściowe.

 **= (1,1 [0]) i b = (2,2 [1]) są takie same? Nie**
 **== b? Nie**
**a1 i są równe? Tak**
**a1 ==? Tak**
**b i bcopy są takie same? Nie**
**b == bcopy? Tak**
## <a name="example"></a>Przykład
 Poniższy przykład pokazuje typ, który z technicznego punktu widzenia narusza tę regułę, ale nie zachowywać się w sposób niezgodny.

 [!code-csharp[FxCop.Usage.ValueTypeEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.ValueTypeEquals/cs/FxCop.Usage.ValueTypeEquals.cs#1)]

## <a name="example"></a>Przykład
 Poniższy kod sprawdza zachowanie `GoodPoint`.

 [!code-csharp[FxCop.Usage.TestValueTypeEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.TestValueTypeEquals/cs/FxCop.Usage.TestValueTypeEquals.cs#1)]

 Ten przykład generuje następujące dane wyjściowe.

 **= (1,1) a, b = (2,2) są takie same? Nie**
 **== b? Nie**
**a1 i są równe? Tak**
**a1 ==? Tak**
**b i bcopy są takie same? Tak**
**b == bcopy? Tak**
## <a name="class-example"></a>Przykład klasy

### <a name="description"></a>Opis
 Poniższy przykład przedstawia klasę (typ odwołania), która narusza tę regułę.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.OverrideEqualsClassViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsClassViolation/cs/FxCop.Usage.OverrideEqualsClassViolation.cs#1)]

## <a name="example"></a>Przykład
 Poniższy przykład naprawia naruszenia przez zastąpienie <xref:System.Object.Equals%2A?displayProperty=fullName>.

 [!code-csharp[FxCop.Usage.OverrideEqualsClassFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsClassFixed/cs/FxCop.Usage.OverrideEqualsClassFixed.cs#1)]

## <a name="structure-example"></a>Przykład struktury

### <a name="description"></a>Opis
 Poniższy przykład pokazuje strukturę (typ wartości), która narusza tę regułę.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.OverrideEqualsStructViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsStructViolation/cs/FxCop.Usage.OverrideEqualsStructViolation.cs#1)]

## <a name="example"></a>Przykład
 Poniższy przykład naprawia naruszenia przez zastąpienie <xref:System.ValueType.Equals%2A?displayProperty=fullName>.

 [!code-csharp[FxCop.Usage.OverrideEqualsStructFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsStructFixed/cs/FxCop.Usage.OverrideEqualsStructFixed.cs#1)]

## <a name="related-rules"></a>Powiązane reguły
 [CA1046: Nie przeciążaj operatora równości w typach referencyjnych](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225: Przeciążenia operatora mają nazwane alternatywy](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2226: Operatory powinny mieć symetryczne przeciążenia](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2218: Przesłoń metodę GetHashCode przy przesłanianiu metody Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231: Przeciążaj operator równości w przypadku przesłaniania metody ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)



