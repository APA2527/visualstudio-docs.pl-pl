---
title: 'CA2207: Typu wartości Inicjuj pola statyczne bezpośrednio | Dokumentacja firmy Microsoft'
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
ms.openlocfilehash: b473dd1a7e19e92858f9bd504ea24da03cca726a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49204675"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207: Inicjowanie pól statycznych typu wartościowego
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
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



