---
title: ItemMetadata — — element (MSBuild) | Microsoft Docs
description: Dowiedz się więcej na temat elementu MSBuild ItemMetadata —, który zawiera klucz metadanych elementu zdefiniowanego przez użytkownika, który ma wartość metadanych.
ms.custom: SEO-VS-2020
ms.date: 03/13/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemMetadata Element [MSBuild]
- <ItemMetadata> Element [MSBuild]
ms.assetid: e3db5122-202d-43a9-b2f4-3e0ec4ed3d08
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 9f48c57769ff6f969e68a50418b017d9928149fd
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99913823"
---
# <a name="itemmetadata-element-msbuild"></a>ItemMetadata —, element (MSBuild)

Zawiera klucz metadanych elementu zdefiniowanego przez użytkownika, który zawiera wartość metadanych elementu. Element może mieć dowolną liczbę par klucz-wartość metadanych.

 \<Project> \<ItemGroup>
 \<Item>

## <a name="syntax"></a>Składnia

```xml
<ItemMetadataName> Item Metadata value</ItemMetadataName>
```

## <a name="attributes-and-elements"></a>Atrybuty i elementy

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.

### <a name="attributes"></a>Atrybuty

|Atrybut|Opis|
|---------------|-----------------|
|`Condition`|Atrybut opcjonalny.<br /><br /> Warunek do obliczenia. Aby uzyskać więcej informacji, zobacz [warunki](../msbuild/msbuild-conditions.md).|

### <a name="child-elements"></a>Elementy podrzędne

 Brak.

### <a name="parent-elements"></a>Elementy nadrzędne

|Element|Opis|
|-------------|-----------------|
|[Element](../msbuild/item-element-msbuild.md)|Element zdefiniowany przez użytkownika, który definiuje dane wejściowe dla procesu kompilacji.|

## <a name="text-value"></a>Wartość tekstowa

 Wartość tekstowa jest opcjonalna.

 Ten tekst Określa wartość metadanych elementu, która może być tekstem lub XML.

## <a name="example"></a>Przykład

 Poniższy przykład kodu pokazuje, jak dodać `Culture` metadane z wartością `fr` do elementu `CSFile` .

```xml
<ItemGroup>
    <CSFile Include="main.cs" >
        <Culture>fr</Culture>
    </CSFile>
</ItemGroup>
```

## <a name="see-also"></a>Zobacz też

- [Odwołanie do schematu pliku projektu](../msbuild/msbuild-project-file-schema-reference.md)
- [Elementy](../msbuild/msbuild-items.md)
