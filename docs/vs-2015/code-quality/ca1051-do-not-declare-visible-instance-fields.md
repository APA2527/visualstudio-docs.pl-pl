---
title: 'CA1051: Nie deklaruj widocznych pól wystąpień | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 691f5fe87d775d2bff2fc15ff15ca8022478b3a2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49910553"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: Nie deklaruj widocznych pól wystąpień
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Typ widoczny na zewnątrz ma pola wystąpienia widoczne na zewnątrz.

## <a name="rule-description"></a>Opis reguły
 Głównym zastosowaniem pola powinno być to, co szczegółowo opisuje implementacja. Pola powinny być `private` lub `internal` i powinien być udostępniany przy użyciu właściwości. Jest to łatwe do dostępu do właściwości jest dostępu do pola i kod w metody dostępu właściwości można zmieniać funkcje typu rozwiń bez wprowadzania przełomowych zmian. Właściwości, które po prostu zwracają wartość pola prywatne lub wewnętrzne są zoptymalizowanych pod kątem podłączonego do uzyskiwania dostępu do pola; bardzo mało wydajne jest skojarzony z użyciem pól widocznego na zewnątrz za pośrednictwem właściwości.

 Widoczne na zewnątrz odwołuje się do `public`, `protected`, i `protected internal` (`Public`, `Protected`, i `Protected Friend` w języku Visual Basic) poziomów ułatwień dostępu.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, Przekształć pole `private` lub `internal` i udostępnić ją za pomocą właściwości widocznego na zewnątrz.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły. Widoczne na zewnątrz pola nie oferuje żadnych korzyści, które są niedostępne dla właściwości. Ponadto pola publiczne nie mogą być chronione przez [zapotrzebowania na łącza](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d). Zobacz [CA2112: typy zabezpieczone nie powinny ujawniać pól](../code-quality/ca2112-secured-types-should-not-expose-fields.md).

## <a name="example"></a>Przykład
 W poniższym przykładzie pokazano typu (`BadPublicInstanceFields`) który narusza tę regułę. `GoodPublicInstanceFields` Wyświetla poprawiony kod.

 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TypesPublicInstanceFields/cs/FxCop.Design.TypesPublicInstanceFields.cs#1)]

## <a name="related-rules"></a>Powiązane reguły
 [CA2112: Typy zabezpieczone nie powinny ujawniać pól](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>Zobacz też
 [Zapotrzebowanie na łącza](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)



