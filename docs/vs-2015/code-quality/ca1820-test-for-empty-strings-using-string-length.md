---
title: 'CA1820: Testuj obecność pustych ciągów przy użyciu długości ciągu | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 17def2bda544a188d6144affc9d7fccb24c3b079
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902536"
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820: Zbadaj pod kątem ciągów pustych przy użyciu długości ciągu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1820: Test na obecność pustych ciągów przy użyciu długości ciągu](https://docs.microsoft.com/visualstudio/code-quality/ca1820-test-for-empty-strings-using-string-length).

|||
|-|-|
|TypeName|TestForEmptyStringsUsingStringLength|
|CheckId|CA1820|
|Kategoria|Microsoft.Performance|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Ciąg jest porównywana do pustego ciągu za pomocą <xref:System.Object.Equals%2A?displayProperty=fullName>.

## <a name="rule-description"></a>Opis reguły
 Porównywanie ciągów za pomocą <xref:System.String.Length%2A?displayProperty=fullName> właściwości lub <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName> metoda jest znacznie szybsze niż użycie <xref:System.Object.Equals%2A>. Jest to spowodowane <xref:System.Object.Equals%2A> wykonuje znacznie więcej instrukcji MSIL niż albo <xref:System.String.IsNullOrEmpty%2A> lub liczbę instrukcji wykonywane w celu pobrania <xref:System.String.Length%2A> właściwości wartość i porównać go na wartość zero.

 Należy pamiętać, że <xref:System.Object.Equals%2A> i <xref:System.String.Length%2A> == 0 zachowywać się inaczej dla ciągów o wartości null. Jeśli użytkownik próbuje pobrać wartość <xref:System.String.Length%2A> właściwości na pusty ciąg, środowisko uruchomieniowe języka wspólnego generuje <xref:System.NullReferenceException?displayProperty=fullName>. Jeśli wykonywane jest porównanie pusty ciąg pusty ciąg, środowisko uruchomieniowe języka wspólnego nie zgłasza wyjątku; Zwraca wynik porównania `false`. Testowanie pod kątem wartości null nie znacząco wpływa na względnej wydajności dwóm metodom. Podczas określania wartości [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)], użyj <xref:System.String.IsNullOrEmpty%2A> metody. W przeciwnym razie użyj <xref:System.String.Length%2A> == porównania, jeśli to możliwe.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, należy zmienić wartość porównania do użycia <xref:System.String.Length%2A> właściwość i testowanie pusty ciąg. Jeśli celem [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)], użyj <xref:System.String.IsNullOrEmpty%2A> metody.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Jest bezpieczne pominąć ostrzeżenie od tej reguły, jeśli wydajność nie ma problemu.

## <a name="example"></a>Przykład
 Poniższy przykład ilustruje różne techniki, które są używane do wyszukania pusty ciąg.

 [!code-csharp[FxCop.Performance.StringTest#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.StringTest/cs/FxCop.Performance.StringTest.cs#1)]



