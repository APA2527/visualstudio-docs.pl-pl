---
title: Odwołanie zestawu reguł analizy kodu
ms.date: 04/04/2018
description: Dowiedz się więcej na temat wbudowanych zestawów reguł w programie Visual Studio w starszej wersji. Zobacz zasoby w zestawach reguł. Dowiedz się, jak używać tych zestawów w niestandardowych zestawach reguł.
ms.custom: SEO-VS-2020
ms.topic: reference
helpviewer_keywords:
- code analysis, rule sets reference
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: cead2d51a13ce4ec137edcd55c7db91d84b04f7f
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99867779"
---
# <a name="code-analysis-rule-set-reference"></a>Odwołanie zestawu reguł analizy kodu

Podczas konfigurowania starszej analizy dla projektów kodu zarządzanego w programie Visual Studio można wybrać jedną z listy wbudowanych *zestawów reguł*. Niektóre reguły są zawarte w więcej niż jednym z wbudowanych zestawów reguł, na przykład zestaw reguł prawidłowości podstawowych reguł poprawności zawiera reguły, które znajdują się w zestawie reguł zarządzanych zalecanych reguł.

> [!NOTE]
> Zestawy reguł w tej sekcji odnoszą się do starszej analizy. Aby uzyskać informacje o zestawach reguł dostępnych dla pakietów analizatora kodu, zobacz [Korzystanie z zestawów reguł z analizami kodu](/dotnet/fundamentals/code-analysis/code-quality-rule-options).

Można użyć jednego z tych wbudowanych zestawów reguł lub [dostosować zestaw reguł](../code-quality/how-to-create-a-custom-rule-set.md) tak, aby odpowiadał wymaganiom projektu. W przypadku dołączania wielu zestawów reguł, które zawierają tę samą regułę w zestawie reguł niestandardowych, ta reguła występuje tylko raz w zestawie reguł niestandardowych.

W tematach w tej sekcji opisano wbudowane zestawy reguł oraz reguły (lub ostrzeżenia), które zawierają.

| Zestaw reguł | Uwzględnione reguły |
| - | - |
| [Wszystkie reguły](all-rules-rule-set.md) | Zawiera wszystkie dostępne reguły zarządzane i C++ |
| [Podstawowe reguły poprawności](basic-correctness-rules-rule-set-for-managed-code.md) | Obejmuje zarządzane zalecane reguły oraz reguły dla błędów logiki i użycia struktury |
| [Rozszerzone reguły poprawności](extended-correctness-rules-rule-set-for-managed-code.md) | Zawiera podstawowe reguły poprawności (w tym zarządzane zalecane reguły) oraz więcej reguł dla błędów logiki i użycia struktury |
| [Podstawowe reguły wskazówek dotyczących projektowania](basic-design-guideline-rules-rule-set-for-managed-code.md) | Obejmuje zarządzane zalecane reguły oraz reguły zapewniające, że można łatwo odczytywać, zrozumieć i konserwować kod |
| [Rozszerzone reguły wskazówek dotyczących projektowania](extended-design-guidelines-rules-rule-set-for-managed-code.md) | Zawiera podstawowe reguły dotyczące projektowania (w tym zarządzane zalecane reguły) oraz bardziej szczegółowe reguły, które koncentrują się na nazewnictwie |
| [Reguły globalizacji](globalization-rules-rule-set-for-managed-code.md) | Zawiera reguły dotyczące problemów z globalizacją |
| [Minimalne reguły kodu zarządzanego](managed-minimum-rules-rule-set-for-managed-code.md) | Zawiera cztery reguły dotyczące krytycznych problemów z kodem zarządzanym |
| [Zalecane reguły kodu zarządzanego](managed-recommended-rules-rule-set-for-managed-code.md) | Obejmuje zarządzane reguły minimalne oraz więcej reguł dotyczących krytycznych problemów z kodem zarządzanym |
| [Minimalne reguły kodu mieszanego](mixed-minimum-rules-rule-set.md) | Zawiera reguły dotyczące krytycznych problemów w kodzie C++ dla środowiska CLR |
| [Zalecane reguły kodu mieszanego](mixed-recommended-rules-rule-set.md) | Zawiera mieszane reguły minimalne oraz więcej reguł dotyczących krytycznych problemów w kodzie C++ dla środowiska CLR |
| [Minimalne reguły kodu natywnego](native-minimum-rules-rule-set.md) | Zawiera reguły dotyczące krytycznych problemów w kodzie natywnym |
| [Zalecane reguły kodu natywnego](native-recommended-rules-rule-set.md) | Zawiera natywne reguły minimalne i więcej reguł dotyczących krytycznych problemów w kodzie natywnym |
| [Reguły zabezpieczeń](security-rules-rule-set-for-managed-code.md) | Zawiera reguły dotyczące znajdowania luk w zabezpieczeniach |