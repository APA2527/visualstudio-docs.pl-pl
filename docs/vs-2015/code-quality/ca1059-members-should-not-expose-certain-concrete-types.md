---
title: 'CA1059: Składowe nie powinny ujawniać niektórych typów konkretnych | Dokumentacja firmy Microsoft'
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
- CA1059
- MembersShouldNotExposeCertainConcreteTypes
helpviewer_keywords:
- MembersShouldNotExposeCertainConcreteTypes
- CA1059
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 073d55a9a5ae6caa573a2c3db282aaa5e5ea4e57
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902747"
---
# <a name="ca1059-members-should-not-expose-certain-concrete-types"></a>CA1059: Elementy członkowskie nie powinny uwidaczniać pewnych typów konkretnych
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1059: składowe nie powinny ujawniać niektórych typów konkretnych](https://docs.microsoft.com/visualstudio/code-quality/ca1059-members-should-not-expose-certain-concrete-types).

|||
|-|-|
|TypeName|MembersShouldNotExposeCertainConcreteTypes|
|CheckId|CA1059|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Widoczne na zewnątrz elementu członkowskiego jest określonego typu konkretnego udostępnia pewnych typów konkretnych za pomocą jednego z jego parametrów lub zwróć wartość. Obecnie ta zasada zgłasza narażenia następujących typów konkretnych:

-   Typ pochodzący od <xref:System.Xml.XmlNode?displayProperty=fullName>.

## <a name="rule-description"></a>Opis reguły
 Konkretny typ jest typem posiadającym pełną implementację i dlatego może zostać utworzone jego wystąpienie. Aby umożliwić powszechne użycie elementu członkowskiego, Zamień konkretny typ sugerowanego interfejsu. Dzięki temu elementu członkowskiego akceptować dowolny typ, który implementuje interfejs lub można użyć, gdzie oczekiwany jest typ, który implementuje interfejs.

 W poniższej tabeli wymieniono docelowych konkretne typy i ich sugerowane zamiany.

|Konkretny typ|Zastępczy|
|-------------------|-----------------|
|<xref:System.Xml.XPath.XPathDocument>|<xref:System.Xml.XPath.IXPathNavigable?displayProperty=fullName>.<br /><br /> Przy użyciu interfejsu oddziela element członkowski z określonej implementacji źródła danych XML.|

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, należy zmienić konkretny typ do sugerowanego interfejsu.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Jest bezpieczne pominąć komunikat od tej reguły, jeśli określone funkcje zapewniane przez konkretny typ jest wymagany.

## <a name="related-rules"></a>Powiązane reguły
 [CA1011: Rozważ przekazanie typów podstawowych jako parametrów](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)



