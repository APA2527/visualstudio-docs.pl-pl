---
title: 'CA2101: Określ marshaling dla argumentów ciągu P-Invoke | Dokumentacja firmy Microsoft'
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
- SpecifyMarshalingForPInvokeStringArguments
- CA2101
helpviewer_keywords:
- CA2101
- SpecifyMarshalingForPInvokeStringArguments
ms.assetid: 9d1abfc3-d320-41e0-9f6e-60cefe6ffe1b
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2cc137c2b086de5507082be34726c3eb3a9294f2
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900553"
---
# <a name="ca2101-specify-marshaling-for-pinvoke-string-arguments"></a>CA2101: Należy określić marshaling dla argumentów typu string P/Invoke
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA2101: należy określić marshaling dla argumentów ciągu P-Invoke](https://docs.microsoft.com/visualstudio/code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments).

|||
|-|-|
|TypeName|SpecifyMarshalingForPInvokeStringArguments|
|CheckId|CA2101|
|Kategoria|Microsoft.Globalization|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Wywołania platformy elementu członkowskiego umożliwia częściowo zaufanych wywołań, ma parametr typu ciąg, a nie kieruje jawnie tego ciągu.

## <a name="rule-description"></a>Opis reguły
 Podczas konwersji z Unicode ANSI jest to możliwe, że nie wszystkie znaki Unicode mogą być reprezentowane w określonej strony kodowej ANSI. *Mapowanie najlepszego dopasowania* próbuje rozwiązać ten problem, zastępując znak znak, który nie może być reprezentowana. Używanie tej funkcji może spowodować potencjalne luki w zabezpieczeniach, ponieważ nie można kontrolować znak, który jest wybierany. Na przykład złośliwy kod celowo utworzyć ciąg Unicode, który zawiera znaki, które nie znajdują się na stronie konkretnego kodu, które są konwertowane na system plików, znaków specjalnych, takich jak ".." lub "/". Należy zauważyć, że sprawdzanie zabezpieczeń dla znaków specjalnych często występują przed ten ciąg jest konwertowany na ANSI.

 Mapowanie najlepszego dopasowania jest ustawieniem domyślnym dla niezarządzanych konwersji WChar do MBajtów. Chyba że jawnie wyłącz mapowanie najlepszego dopasowania, Twój kod może zawierać luki w zabezpieczeniach możliwe do wykorzystania z powodu tego problemu.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, kieruje jawnie tego ciągu typów danych.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 Poniższy przykład przedstawia metodę, która narusza tę regułę, a następnie pokazano, jak naprawić naruszenia.

 [!code-csharp[FxCop.Security.PinvokeAnsiUnicode#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.PinvokeAnsiUnicode/cs/FxCop.Security.PinvokeAnsiUnicode.cs#1)]



