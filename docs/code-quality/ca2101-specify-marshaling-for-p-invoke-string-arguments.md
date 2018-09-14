---
title: 'CA2101: Określ marshaling dla argumentów ciągu wywołania P-Invoke'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyMarshalingForPInvokeStringArguments
- CA2101
helpviewer_keywords:
- CA2101
- SpecifyMarshalingForPInvokeStringArguments
ms.assetid: 9d1abfc3-d320-41e0-9f6e-60cefe6ffe1b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b560f2be6cad77bd4381d9ca9968c42c37b462ab
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45548349"
---
# <a name="ca2101-specify-marshaling-for-pinvoke-string-arguments"></a>CA2101: Należy określić marshaling dla argumentów typu string P/Invoke
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

 [!code-csharp[FxCop.Security.PinvokeAnsiUnicode#1](../code-quality/codesnippet/CSharp/ca2101-specify-marshaling-for-p-invoke-string-arguments_1.cs)]