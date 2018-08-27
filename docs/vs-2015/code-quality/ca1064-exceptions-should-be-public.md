---
title: 'CA1064: Wyjątki powinny być publiczne | Dokumentacja firmy Microsoft'
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
- CA1064
- ExceptionsShouldBePublic
helpviewer_keywords:
- ExceptionsShouldBePublic
- CA1064
ms.assetid: 83eb224c-2456-4368-acf4-3b3378e67759
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c35906c41a4c39557b2f72c83308b25cf650f676
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902306"
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064: Wyjątki powinny być publiczne
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1064: wyjątki powinny być publiczne](https://docs.microsoft.com/visualstudio/code-quality/ca1064-exceptions-should-be-public).

|||
|-|-|
|TypeName|ExceptionsShouldBePublic|
|CheckId|CA1064|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Wyjątek niepublicznych pochodzi bezpośrednio z <xref:System.Exception>, <xref:System.SystemException>, lub <xref:System.ApplicationException>.

## <a name="rule-description"></a>Opis reguły
 Wyjątek wewnętrzny jest widoczna tylko wewnątrz własnego zakresu wewnętrznego. W przypadku wystąpienia wyjątku poza zakresem wewnętrznym tylko wyjątek podstawowy może zostać użyty do jego przechwycenia. Jeśli wyjątek wewnętrzny jest dziedziczony z <xref:System.Exception>, <xref:System.SystemException>, lub <xref:System.ApplicationException>, kod zewnętrzny nie ma wystarczające informacje, aby wiedzieli, co należy zrobić z wyjątkiem.

 Ale, jeśli kod ma publiczny wyjątek, który później jest używany jako podstawa dla wewnętrznego wyjątku, można zasadnie przyjęto założenie, że kod dalsze się będzie mógł czymś inteligentne z wyjątkiem podstawowej. Wyjątek publicznego mają więcej informacji, niż dostarczanych przez T:System.Exception, T:System.SystemException lub T:System.ApplicationException.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Upublicznić wyjątku lub pochodzi z wewnętrznego wyjątku z publicznych wyjątek, który nie jest <xref:System.Exception>, <xref:System.SystemException>, lub <xref:System.ApplicationException>.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Wiadomości od tej reguły należy pominąć, jeśli masz pewność, we wszystkich przypadkach, w ramach własnego zakresu wewnętrznego zostanie przechwycony wyjątek prywatnych.

## <a name="example"></a>Przykład
 Ta reguła jest uruchamiana na pierwszej metody przykład FirstCustomException, ponieważ pochodzi bezpośrednio z wyjątkiem klasy wyjątku, a wewnętrznej. Reguła nie zostanie wywołane w klasie SecondCustomException, ponieważ mimo, że klasa również pochodzi bezpośrednio z wyjątków, klasa jest zadeklarowany jako publiczny. Klasa innych również nie jest wyzwalana, reguły, ponieważ nie pochodzi bezpośrednio z <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, lub <xref:System.ApplicationException?displayProperty=fullName>.

 [!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.design.exceptionsshouldbepublic.ca1064/cs/ca1064 - exceptionsshouldbepublic.cs#1)]



