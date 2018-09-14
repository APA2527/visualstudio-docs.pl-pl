---
title: 'CA2123: Przesłonięcia żądań konsolidacji powinny być identyczne z bazowym'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2123
- OverrideLinkDemandsShouldBeIdenticalToBase
helpviewer_keywords:
- OverrideLinkDemandsShouldBeIdenticalToBase
- CA2123
ms.assetid: 4538ecd5-fc6f-4480-ab00-90b2ce4730db
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ebb37743f9259390aba400a5d89d24b5f41a0d49
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546983"
---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123: Przesłonięcia żądań konsolidacji powinny być identyczne z bazowym

|||
|-|-|
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|
|CheckId|CA2123|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Metoda publiczna lub chroniona w typie publicznym zastępuje metody lub implementuje interfejs i nie ma takie same [zapotrzebowania na łącza](/dotnet/framework/misc/link-demands) jako interfejs lub metoda wirtualna.

## <a name="rule-description"></a>Opis reguły
 Ta reguła dopasowuje metodę do jej metody podstawowej, która jest interfejsem lub metodą wirtualną innego typu, a następnie porównuje zapotrzebowania na łącza na każdym z nich. Naruszenie zasad jest zgłaszany, jeśli metoda lub metoda podstawowa ma zapotrzebowania na łącza, a drugi nie.

 Jeśli zasada ta jest naruszona, złośliwy wywołujący może pominąć zapotrzebowanie na łącza przez wywołanie niezabezpieczonej metody.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, dotyczą tego samego zapotrzebowania na łącza metodę przesłaniającą lub implementacji. Jeśli nie jest to możliwe, oznacz metodę z pełnego żądania lub całkowicie Usuń atrybut.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 Poniższy przykład pokazuje różne naruszenie tej zasady.

 [!code-csharp[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]

## <a name="see-also"></a>Zobacz także

- [Wytyczne dotyczące bezpiecznego programowania](/dotnet/standard/security/secure-coding-guidelines)
- [Zapotrzebowanie na łącza](/dotnet/framework/misc/link-demands)