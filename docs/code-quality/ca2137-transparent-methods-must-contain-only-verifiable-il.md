---
title: 'CA2137: Jawne metody muszą zawierać tylko weryfikowalne IL'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 131824b22291acb0b83af6ff24e9751a98db3ed1
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49845346"
---
# <a name="ca2137-transparent-methods-must-contain-only-verifiable-il"></a>CA2137: Jawne metody muszą zawierać tylko weryfikowalne IL

|||
|-|-|
|TypeName|TransparentMethodsMustBeVerifiable|
|CheckId|CA2137|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Metoda zawiera nieweryfikowalny kod lub zwraca typ przez odwołanie.

## <a name="rule-description"></a>Opis reguły
 Ta reguła jest uruchamiana podczas próby wykonywania przez kod przezroczysty pod względem zabezpieczeń nieweryfikowalnego MSIL (Microsoft Intermediate Language). Jednak reguła nie zawiera pełnej weryfikacji IL i używa heurystyki do wykrywania większości naruszeń weryfikacji MSIL.

 Aby mieć pewność, że Twój kod zawiera tylko weryfikowalny MSIL, uruchom [Peverify.exe (narzędzie PEVerify)](/dotnet/framework/tools/peverify-exe-peverify-tool) w swoim zestawie. Uruchom PEVerify z **/ przezroczyste** opcję, która ogranicza dane wyjściowe do tylko nieweryfikowalnego przezroczyste metod, które mogłyby spowodować wystąpienie błędu. Jeśli / opcja przezroczystego nie jest używana, PEVerify sprawdza również krytycznych metod, które mogą zawierać zweryfikowanie kodu.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, należy oznaczyć metody <xref:System.Security.SecurityCriticalAttribute> lub <xref:System.Security.SecuritySafeCriticalAttribute> atrybut lub usuń zweryfikowanie kodu.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 Metody, w tym przykładzie używa nieweryfikowalny kod i powinien być oznaczony przez <xref:System.Security.SecurityCriticalAttribute> lub <xref:System.Security.SecuritySafeCriticalAttribute> atrybutu.

 [!code-csharp[FxCop.Security.CA2137.TransparentMethodsMustBeVerifiable#1](../code-quality/codesnippet/CSharp/ca2137-transparent-methods-must-contain-only-verifiable-il_1.cs)]