---
title: 'CA1058: Typy nie powinny rozszerzać niektórych typów podstawowych | Dokumentacja firmy Microsoft'
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
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 0a4ffbe3b359f2c58f8e301b9176981a2037c17f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49912438"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: Typy nie powinny rozszerzać pewnych typów bazowych
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Typ widoczny na zewnątrz rozszerza niektóre typy podstawowe. Obecnie ta zasada zgłasza typów wyprowadzonych z następujących typów:

-   <xref:System.ApplicationException?displayProperty=fullName>

-   <xref:System.Xml.XmlDocument?displayProperty=fullName>

-   <xref:System.Collections.CollectionBase?displayProperty=fullName>

-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>

-   <xref:System.Collections.Queue?displayProperty=fullName>

-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

-   <xref:System.Collections.SortedList?displayProperty=fullName>

-   <xref:System.Collections.Stack?displayProperty=fullName>

## <a name="rule-description"></a>Opis reguły
 Aby uzyskać [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] wersji 1 zalecano do wyprowadzenia nowego wyjątki od <xref:System.ApplicationException>. Zalecenie został zmieniony i nowych wyjątków powinien pochodzić od <xref:System.Exception?displayProperty=fullName> lub jedna z jej podklasach w <xref:System> przestrzeni nazw.

 Nie należy tworzyć podklasą <xref:System.Xml.XmlDocument> Jeśli chcesz utworzyć widok XML z bazowego źródła danych lub modelu obiektu.

### <a name="non-generic-collections"></a>Kolekcje ogólne
 Użyj i/lub rozszerzyć kolekcje ogólne, jeśli to możliwe. Kolekcje ogólne w kodzie, nie zostanie rozszerzony, chyba że wcześniej wysłane.

 **Przykłady nieprawidłowe użycie**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

 **Przykłady poprawne użycie**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, pobierają typ z innym typem bazowym lub kolekcję ogólną.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły za naruszenia o <xref:System.ApplicationException>. Bezpiecznie Pomijaj ostrzeżeń dla tej reguły za naruszenia o <xref:System.Xml.XmlDocument>. Jest bezpieczne pominąć ostrzeżenie dotyczące nieogólna kolekcja, jeśli kod został wydany wcześniej.



