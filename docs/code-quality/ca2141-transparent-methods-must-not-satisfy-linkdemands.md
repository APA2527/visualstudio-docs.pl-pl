---
title: Metody CA2141:Transparent nie mogą spełniać LinkDemands
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2141
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a11c5bdf6cd5d2c1e278d7e8943aa672621672cd
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551652"
---
# <a name="ca2141transparent-methods-must-not-satisfy-linkdemands"></a>Metody CA2141:Transparent nie mogą spełniać LinkDemands
|||
|-|-|
|TypeName|TransparentMethodsMustNotSatisfyLinkDemands|
|CheckId|CA2141|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Metoda przezroczysta pod względem bezpieczeństwa wywołuje metodę w zestawie, który nie jest oznaczony atrybutem <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atrybutu (APTCA) lub metoda przezroczysta pod względem zabezpieczeń spełnia <xref:System.Security.Permissions.SecurityAction> `.LinkDemand` dla typu lub metody.

## <a name="rule-description"></a>Opis reguły
 Spełnia LinkDemand jest poufnych operacji zabezpieczeń, który może spowodować niezamierzone podniesienie uprawnień. Przezroczysty kod zabezpieczeń nie mogą spełniać LinkDemands, ponieważ nie podlega ona te same wymagania inspekcji zabezpieczeń, jak kodu krytycznego dla zabezpieczeń. Metody w zestawy poziomu 1 zestaw reguł zabezpieczeń spowoduje, że wszystkie LinkDemands, że spełniają one do przekonwertowania w pełnych żądań w czasie wykonywania, co może powodować problemy z wydajnością. W zestawy poziomu 2 zestaw reguł zabezpieczeń metody przezroczyste zakończy się niepowodzeniem skompilować w kompilator just-in-time (JIT), przy próbie spełnia LinkDemand.

 W zestawach, które korzystają z zabezpieczeń na poziomie 2 próby ustalenia przez metoda przezroczysta pod względem zabezpieczeń spełnia żądanie LinkDemand lub wywołanie metody w zestawie APTCA nie zgłasza <xref:System.MethodAccessException>; w zestawach poziomu 1 żądanie LinkDemand staje się pełnego żądania.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, należy oznaczyć metody uzyskiwania dostępu do <xref:System.Security.SecurityCriticalAttribute> lub <xref:System.Security.SecuritySafeCriticalAttribute> atrybut lub Usuń żądanie LinkDemand z metody dostępu.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 W tym przykładzie metoda przezroczysta pod względem próbuje wywołać metodę, która ma żądanie LinkDemand. Ta reguła zostanie zastosowana dla tego kodu.

 [!code-csharp[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../code-quality/codesnippet/CSharp/ca2141-transparent-methods-must-not-satisfy-linkdemands_1.cs)]