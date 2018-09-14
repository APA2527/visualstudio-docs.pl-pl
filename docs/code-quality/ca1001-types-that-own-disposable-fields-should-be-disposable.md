---
title: 'CA1001: Typy, które posiadają pola usuwalne, powinny być usuwalne'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
helpviewer_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
ms.assetid: c85c126c-2b16-4505-940a-b5ddf873fb22
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a73acee1c01aba7a638d27c0e772e4fbf5e19384
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546955"
---
# <a name="ca1001-types-that-own-disposable-fields-should-be-disposable"></a>CA1001: Typy, które posiadają pola usuwalne, powinny być usuwalne

|||
|-|-|
|TypeName|TypesThatOwnDisposableFieldsShouldBeDisposable|
|CheckId|CA1001|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Bez podziału — Jeśli typ nie jest widoczna spoza zestawu.<br /><br /> Przerywanie — Jeśli typ jest widoczna spoza zestawu.|

## <a name="cause"></a>Przyczyna
 Klasa deklaruje i implementuje pole wystąpienia, która jest <xref:System.IDisposable?displayProperty=fullName> typ i klasa nie implementuje <xref:System.IDisposable>.

## <a name="rule-description"></a>Opis reguły
 Klasa implementuje <xref:System.IDisposable> interfejsu do usuwania niezarządzanych zasobów, w których jest właścicielem. Pole wystąpienia, która jest <xref:System.IDisposable> typu wskazuje, że pole posiada niezarządzany zasób. Klasa, która deklaruje <xref:System.IDisposable> pola pośrednio posiada niezarządzany zasób i powinna implementować <xref:System.IDisposable> interfejsu. Jeśli klasa bezpośrednio nie ma żadnych niezarządzanych zasobów, nie należy implementować finalizatora.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, należy zaimplementować <xref:System.IDisposable> i <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> wywołania metody <xref:System.IDisposable.Dispose%2A> metody pól.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 W poniższym przykładzie pokazano klasę, która narusza regułę określającą oraz klasę, która spełnia regułę poprzez implementację <xref:System.IDisposable>. Klasa nie implementuje finalizator, ponieważ klasa nie posiada bezpośrednio wszelkie niezarządzane zasoby.

 [!code-vb[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/VisualBasic/ca1001-types-that-own-disposable-fields-should-be-disposable_1.vb)]
 [!code-csharp[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/CSharp/ca1001-types-that-own-disposable-fields-should-be-disposable_1.cs)]

## <a name="related-rules"></a>Powiązane reguły
 [CA2213: Pola możliwe do likwidacji powinny zostać zlikwidowane](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

 [CA2216: Typy możliwe do likwidacji powinny deklarować finalizator](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

 [CA2215: Metody Dispose powinny wywoływać metodę Dispose klasy podstawowej](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)

 [CA1049: Typy z zasobami natywnymi powinny być możliwe do likwidacji](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)