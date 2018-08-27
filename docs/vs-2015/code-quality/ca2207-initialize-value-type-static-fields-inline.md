---
title: 'CA2207: Typu wartości Inicjuj pola statyczne bezpośrednio | Dokumentacja firmy Microsoft'
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
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 0f90e52ed5d80c9b3e97415e920d7d6f4f0972fc
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902270"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207: Inicjowanie pól statycznych typu wartościowego
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA2207: Zainicjuj wbudowane pola statyczne typu wartości](https://docs.microsoft.com/visualstudio/code-quality/ca2207-initialize-value-type-static-fields-inline).

|||
|-|-|
|TypeName|InitializeValueTypeStaticFieldsInline|
|CheckId|CA2207|
|Kategoria|Microsoft.Usage|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Typ wartości deklaruje jawny, statyczny Konstruktor.

## <a name="rule-description"></a>Opis reguły
 Gdy typ wartości jest zadeklarowany, wewnętrzny ulega inicjowanie domyślne, gdzie wszystkie pola typu wartości są ustawione na zero, a wszystkie pola typu odwołania są ustawione na `null` (`Nothing` w języku Visual Basic). Jawny, statyczny Konstruktor tylko jest gwarantowane do uruchomienia przed w konstruktorze wystąpienia lub statyczną składową typu jest wywoływana. W związku z tym jeśli typ jest tworzony bez wywoływania konstruktora wystąpienia, Konstruktor statyczny nie jest gwarantowane do uruchomienia.

 Jeśli wszystkie dane statyczne są wbudowane zainicjowane, a nie jawny, statyczny Konstruktor jest zadeklarowany, Kompilatory języka C# i Visual Basic Dodaj `beforefieldinit` flagi do definicji klasy MSIL. Kompilatory również dodać Konstruktor statyczny prywatny, zawierający kod inicjowania statycznych. Ten konstruktor statyczny prywatny jest gwarantowane, zanim wszystkie pola statyczne typu są dostępne.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady Zainicjuj wszystkie dane statyczne, gdy jest zadeklarowany i Usuń Konstruktor statyczny.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="related-rules"></a>Powiązane reguły
 [CA1810: Inicjuj pola statyczne typu referencyjnego śródwierszowo](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)



