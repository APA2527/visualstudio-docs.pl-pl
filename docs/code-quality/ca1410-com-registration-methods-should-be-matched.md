---
title: 'CA1410: Metody rejestracji COM powinny być dopasowane'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 1d4cbff52a5b5b5ef5fc46ef0b2f93926f097485
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550900"
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410: Metody rejestracji COM powinny być dopasowane

|||
|-|-|
|TypeName|ComRegistrationMethodsShouldBeMatched|
|CheckId|CA1410|
|Kategoria|Microsoft.Interoperability|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Typ deklaruje metodę, która jest oznaczona za pomocą <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> atrybutu, ale nie deklaruje metody oznaczonej za pomocą <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> atrybut, lub na odwrót.

## <a name="rule-description"></a>Opis reguły
 Dla klientów Component Object Model (COM), aby utworzyć [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] typu, należy zarejestrować tego typu. Jeśli jest dostępna, metody, która jest oznaczona za pomocą <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> atrybutu jest wywoływana podczas procesu rejestracji, aby uruchomić kod określony przez użytkownika. Odpowiedniej metody, która jest oznaczona za pomocą <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> atrybutu jest wywoływana podczas proces wyrejestrowania w celu odwrócenia operacji metodę rejestracji.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, należy dodać odpowiadającej rejestracji lub metodę wyrejestrowania.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 Poniższy przykład pokazuje typ, który narusza regułę. Komentarze kod przedstawia poprawkę dotyczącą naruszenia.

 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/CSharp/ca1410-com-registration-methods-should-be-matched_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/VisualBasic/ca1410-com-registration-methods-should-be-matched_1.vb)]

## <a name="related-rules"></a>Powiązane reguły
 [CA1411: Metody rejestracji modelu COM nie powinny być widoczne](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)

## <a name="see-also"></a>Zobacz także

- <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>
- [Rejestrowanie zestawów do użycia z modelem COM](/dotnet/framework/interop/registering-assemblies-with-com)
- [Regasm.exe (narzędzie rejestracji zestawów)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)