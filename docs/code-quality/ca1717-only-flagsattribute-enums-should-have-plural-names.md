---
title: 'CA1717: Tylko typy wyliczeniowe FlagsAttribute powinny mieć nazwy w liczbie mnogiej'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1717
- OnlyFlagsEnumsShouldHavePluralNames
helpviewer_keywords:
- OnlyFlagsEnumsShouldHavePluralNames
- CA1717
ms.assetid: a6855d8b-d78a-42c1-834e-61c31f5572ed
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1f923949b628d1ad5a3884acd17601daddd83460
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49889731"
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717: Tylko typy wyliczeniowe FlagsAttribute powinny mieć nazwy w liczbie mnogiej

|||
|-|-|
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|
|CheckId|CA1717|
|Kategoria|Microsoft.Naming|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Nazwa widocznego na zewnątrz wyliczenie kończy się w liczbie mnogiej programu word i wyliczenia nie jest oznaczony atrybutem <xref:System.FlagsAttribute?displayProperty=fullName> atrybutu.

## <a name="rule-description"></a>Opis reguły
 Nazwa w liczbie mnogiej dla wyliczenia wskazuje, jednocześnie określono więcej niż jedną wartość wyliczenia zgodnie z konwencjami nazewnictwa. <xref:System.FlagsAttribute> Kompilatory informuje, że wyliczenia powinny być traktowane jako pola bitowe, które umożliwia wykonywanie operacji bitowa na wyliczeniu.

 Jeśli tylko jedna z wartości wyliczenia można określić jednocześnie, nazwa wyliczenia powinna być pojedynczą programu word. Na przykład wyliczenie definiujące dni tygodnia, może być przeznaczona do użycia w aplikacji, której można określić wiele dni. To wyliczenie powinny mieć <xref:System.FlagsAttribute> i może być wywoływana "Dni". Podobne wyliczenie, które umożliwia określenie tylko jednego dnia nie miałoby atrybutu i może być o nazwie "Day".

 Konwencje nazewnictwa Obejmij wygląd wspólnych bibliotek obiektu docelowego środowiska uruchomieniowego języka wspólnego. Zmniejsza to czas, który jest wymagany, aby dowiedzieć się nowa Biblioteka oprogramowania i zwiększa poziom zaufania klientów, że biblioteka został opracowany przez osobę, która ma doświadczenie w tworzenie kodu zarządzanego.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Wprowadź nazwę wyliczenia pojedynczej programu word lub dodać <xref:System.FlagsAttribute>.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Jest bezpieczne pominąć ostrzeżenie z reguły, jeśli nazwa kończy się na pojedynczej programu word.

## <a name="related-rules"></a>Powiązane reguły
 [CA1714: Wyliczenia flag powinny mieć nazwy w liczbie mnogiej](../code-quality/ca1714-flags-enums-should-have-plural-names.md)

 [CA1027: Oznacz typy wyliczeniowe atrybutem Flags](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Nie oznaczaj wyliczeń za pomocą atrybutu FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Zobacz także

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [Projekt wyliczeń](/dotnet/standard/design-guidelines/enum)