---
title: 'CA1040: Unikaj pustych interfejsów'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: d5c23a52e65d04b5cc8d147cc0ec3bd7c12bde3c
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45548344"
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040: Unikaj pustych interfejsów

|||
|-|-|
|TypeName|AvoidEmptyInterfaces|
|CheckId|CA1040|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Interfejs zadeklarować wszystkie elementy Członkowskie lub nie implementuje dwa lub więcej interfejsów.

## <a name="rule-description"></a>Opis reguły
 Interfejsy definiują elementy członkowskie, które zapewniają zachowanie lub użycie kontraktu. Funkcjonalność opisana przez interfejs może zostać przyjęta przez dowolny typ, niezależnie od tego, gdzie ten typ się pojawia w hierarchii dziedziczenia. Typ implementuje interfejs, dostarczając implementacje dla jego elementów członkowskich. Pusty interfejs nie definiuje żadnych elementów członkowskich. W związku z tym nie definiuje kontraktu, który może być implementowana.

 Jeśli projekt zawiera pusty powinny implementować interfejsy, które typy, prawdopodobnie używasz interfejsu jako znacznik lub do identyfikowania grupy typów. Jeśli ten identyfikator będzie występować w czasie wykonywania, prawidłowym sposobem, aby osiągnąć ten cel jest używać atrybutu niestandardowego. Użyj obecności lub braku atrybutu lub właściwości atrybutu, aby zidentyfikować typów docelowych. Jeśli identyfikator musi wystąpić w czasie kompilacji, a następnie dopuszcza się użycia pusty interfejs.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Usuń interfejs lub dodać członków do niego. Jeśli pusty interfejs jest używany jako etykieta zestaw typów, Zamień niestandardowy atrybut interfejsu.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Jest bezpieczne pominąć ostrzeżenie od tej reguły, jeśli ten interfejs jest używany do identyfikowania zestaw typów w czasie kompilacji.

## <a name="example"></a>Przykład
 Poniższy przykład pokazuje pusty interfejs.

 [!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CSharp/ca1040-avoid-empty-interfaces_1.cs)]
 [!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CPP/ca1040-avoid-empty-interfaces_1.cpp)]
 [!code-vb[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/VisualBasic/ca1040-avoid-empty-interfaces_1.vb)]