---
title: 'CA1722: Identyfikatory powinny mieć poprawny prefiks'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotHaveIncorrectPrefix
- CA1722
helpviewer_keywords:
- CA1722
- IdentifiersShouldNotHaveIncorrectPrefix
ms.assetid: c3313c51-d004-4f9a-a0d1-6c4c4a1fb1e6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3ff21b8f3c12cfa9fb3dc3ef03ca2ba2040f3769
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49857621"
---
# <a name="ca1722-identifiers-should-not-have-incorrect-prefix"></a>CA1722: Identyfikatory powinny mieć poprawny prefiks

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectPrefix|
|CheckId|CA1722|
|Kategoria|Microsoft.Naming|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Identyfikator ma niepoprawny prefiks.

## <a name="rule-description"></a>Opis reguły
 Zgodnie z konwencją, tylko niektóre elementy programowania mają nazwy rozpoczynające się od określonego prefiksu.

 Nazwy typów nie ma określonego prefiksu i nie powinien być poprzedzony "C". Ta zasada zgłasza naruszenia nazwy typów, takich jak "CMyClass" i nie raportuje naruszenia nazwy typów, takich jak "Pamięci podręcznej".

 Konwencje nazewnictwa Obejmij wygląd wspólnych bibliotek obiektu docelowego środowiska uruchomieniowego języka wspólnego. Ten spójności zmniejsza nauki, wymagana na nowe biblioteki oprogramowania, która zwiększa poziom zaufania klientów, że biblioteka został opracowany przez osobę, która ma doświadczenie w tworzenie kodu zarządzanego.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Usuń prefiks z identyfikatorem.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="related-rules"></a>Powiązane reguły
 [CA1715: Identyfikatory powinny mieć poprawny prefiks](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)