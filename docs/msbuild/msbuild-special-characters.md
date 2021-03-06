---
title: Znaki specjalne MSBuild | Microsoft Docs
description: Dowiedz się więcej na temat znaków zarezerwowanych programu MSBuild do użytku specjalnego w określonych kontekstach oraz sposobu i sposobu ucieczki tych znaków.
ms.custom: SEO-VS-2020
ms.date: 06/12/2019
ms.topic: conceptual
helpviewer_keywords:
- escape characters
- escape
- MSBuild Escape Characters
ms.assetid: 545e6a59-1093-4514-935e-78679a46fb3c
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: c5db0b870e050a9235f719d83710747101b95c3c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99922532"
---
# <a name="msbuild-special-characters"></a>Znaki specjalne w programie MSBuild

Program MSBuild rezerwuje kilka znaków do użytku specjalnego w określonych kontekstach. Musisz tylko wypróbować takie znaki, jeśli chcesz ich używać dosłownie w kontekście, w którym są zarezerwowane. Na przykład gwiazdka ma specjalne znaczenie tylko w `Include` `Exclude` atrybutach i definicji elementu oraz w wywołaniach do `CreateItem` . Jeśli chcesz, aby gwiazdka była wyświetlana jako gwiazdka w jednym z tych kontekstów, musisz ją wypróbować. W każdym innym kontekście wystarczy wpisać gwiazdkę, w której ma się pojawić.

 Aby wprowadzić znak specjalny, użyj składni% \<xx> , gdzie \<xx> reprezentuje wartość szesnastkową ASCII znaku. Aby uzyskać więcej informacji, zobacz [jak: znaki specjalne ucieczki w MSBuild](../msbuild/how-to-escape-special-characters-in-msbuild.md).

## <a name="special-characters"></a>Znaki specjalne

 W poniższej tabeli wymieniono znaki specjalne MSBuild:

|**Znak**|**ASCII**|**Użycie zarezerwowane**|
|-------------------|---------------|------------------------|
|%|%25|Odwołania do metadanych|
|$|%24|Właściwości odwołania|
|@|%40|Odwołania do list elementów|
|'|%27|Warunki i inne wyrażenia|
|;|% 3B|Separator listy|
|?|% 3F|Symbol wieloznaczny dla nazw plików w `Include` `Exclude` atrybutach i|
|*|%2A|Symbol wieloznaczny do użycia w nazwach plików w `Include` `Exclude` atrybutach i|

## <a name="see-also"></a>Zobacz też

- [Pojęcia zaawansowane](../msbuild/msbuild-advanced-concepts.md)
- [Elementy](../msbuild/msbuild-items.md)
