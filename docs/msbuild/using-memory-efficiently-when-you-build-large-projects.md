---
title: Wydajne używanie pamięci podczas kompilowania dużych projektów | Microsoft Docs
description: Dowiedz się, w jaki sposób program MSBuild automatycznie zarządza pamięcią, na przykład zwalniając starsze wersje i pobierając pamięci podręczne podczas kompilowania dużych projektów.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 61bfa09bf91b49c163e47bbf71c0d192b6950160
ms.sourcegitcommit: 1a36533f385e50c05f661f440380fda6386ed3c1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "93047607"
---
# <a name="use-memory-efficiently-when-you-build-large-projects"></a>Wydajne używanie pamięci podczas kompilowania dużych projektów

Duże projekty często zawierają wiele podprojektów i innych zależności, które mogą zużywać dużą ilość pamięci systemowej w czasie kompilacji. Po zmniejszeniu dostępnej pamięci systemowej może ulec również obniżenie wydajności systemu. Starsze wersje projektów programu MSBuild pozostawały w pamięci. W wersji 3,5 usunięto starsze wersje projektów, ale zachowane wyniki kompilacji są przechowywane w pamięci podręcznej na potrzeby późniejszego pobierania.

 Wersja 4,0 obsługuje automatyczne zarządzanie pamięcią, dzięki czemu zapisywanie projektów nie będzie miało zastosowania właściwości takich jak  `UnloadProjectsOnCompletion` i `UseResultsCache` .

### <a name="see-also"></a>Zobacz też

- [Równoległe kompilowanie wielu projektów](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)
