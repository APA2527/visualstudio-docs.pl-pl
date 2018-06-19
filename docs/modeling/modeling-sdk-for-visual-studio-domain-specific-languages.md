---
title: Modelowanie SDK dla Visual Studio — języki specyficzne dla domeny
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools
- Domain-Specific Language
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6dc87ba31e1f693559384977588471af753738e7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31950845"
---
# <a name="modeling-sdk-for-visual-studio---domain-specific-languages"></a>Modelowanie SDK dla Visual Studio — języki specyficzne dla domeny
Przy użyciu zestawu SDK modelowania dla [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], można utworzyć narzędzia wydajne programowanie oparte na modelu, które można zintegrować [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. W ten sam sposób można utworzyć co najmniej jedną definicję modelu i zintegrować ją w zestaw narzędzi.

 Centralnym elementem zestawu MSDK jest definicja modelu tworzona w celu przedstawienia koncepcji z obszaru biznesowego. Należy otoczyć modelu przy użyciu różnych narzędzi, takich jak podającą widoku, możliwość wygenerowania kodu i innych artefaktów polecenia do przekształcania modelu i możliwość interakcji z kodem i innych obiektów w programie [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Podczas opracowywania modelu można połączyć go z innymi modelami i narzędziami w celu utworzenia zestawu narzędzi o dużych możliwościach, który będzie wspomagał proces projektowania.

 Zestaw MSDK umożliwia szybkie opracowanie modelu z użyciem języka specyficznego dla domeny (DSL). Należy rozpocząć od użycia specjalnego edytora w celu zdefiniowania schematu lub abstrakcyjnej składni wraz z notacją graficzną. Na podstawie tej definicji zestaw VMSDK generuje następujące elementy:

-   Implementacja modelu z silnie typizowanym interfejsem API, który działa w magazynie opartym na transakcjach.

-   Eksplorator oparty na drzewie.

-   Edytor graficzny, w którym użytkownicy mogą wyświetlać zdefiniowany model lub jego części.

-   Metody serializacji zapisujące modele w przystosowanych do odczytu plikach XML.

-   Możliwości generowania kodu programu i innych artefaktów przy użyciu funkcji tworzenia szablonów tekstu.

 Wszystkie te funkcje można dostosowywać i rozszerzać. Rozszerzenia są integrowane w taki sposób, że można aktualizować definicję DSL oraz ponownie generować funkcje bez utraty używanych rozszerzeń.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

 [Wpisy na blogu pokrewne](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)

 Aby uzyskać wskazówki dotyczące zaawansowanych technik i rozwiązywania problemów, odwiedź stronę [forum programu Visual Studio DSL & rozszerzalności modelowania narzędzia](http://go.microsoft.com/fwlink/?LinkID=186074).

## <a name="in-this-section"></a>W tej sekcji
 [Wprowadzenie do języków specyficznych dla domeny](../modeling/getting-started-with-domain-specific-languages.md)

 [Opis modeli, klas i relacji](../modeling/understanding-models-classes-and-relationships.md)

 [Instrukcje: Definiowanie języka właściwego dla domeny](../modeling/how-to-define-a-domain-specific-language.md)

 [Dostosowywanie i rozszerzanie języka specyficznego dla domeny](../modeling/customizing-and-extending-a-domain-specific-language.md)

 [Walidacja w języku specyficznym dla domeny](../modeling/validation-in-a-domain-specific-language.md)

 [Pisanie kodu pod kątem dostosowywania języka specyficznego dla domeny](../modeling/writing-code-to-customise-a-domain-specific-language.md)

 [Generowanie kodu z języka specyficznego dla domeny](../modeling/generating-code-from-a-domain-specific-language.md)

 [Znajomość kodu DSL](../modeling/understanding-the-dsl-code.md)

 [Dostosowywanie przechowywania plików i serializacji XML](../modeling/customizing-file-storage-and-xml-serialization.md)

 [Wdrażanie rozwiązań dla języka specyficznego dla domeny](../modeling/deploying-domain-specific-language-solutions.md)

 [Tworzenie języka specyficznego dla domeny opartego na modelu Windows Forms](../modeling/creating-a-windows-forms-based-domain-specific-language.md)

 [Tworzenie języka specyficznego dla domeny opartego na podsystemie WPF](../modeling/creating-a-wpf-based-domain-specific-language.md)

 [Instrukcje: Rozszerzanie projektanta języka specyficznego dla domeny](../modeling/how-to-extend-the-domain-specific-language-designer.md)

 [Wersje programu Visual Studio obsługiwane przez zestaw Visualization and Modeling SDK](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md)

 [Instrukcje: Migracja języka specyficznego dla domeny do nowej wersji](../modeling/how-to-migrate-a-domain-specific-language-to-a-new-version.md)

 [Odwołania API do modelowania SDK dla Visual Studio](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)
