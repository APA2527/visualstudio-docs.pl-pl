---
title: Include — element | Microsoft Docs
description: Element include określa plik, który może znajdować się w podanej ścieżce include do wstawienia do bieżącego pliku.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- Include
helpviewer_keywords:
- Include element (VSCT XML schema)
- VSCT XML schema elements, Include
ms.assetid: c923dfe6-084a-4105-aec1-f0a3f8399c54
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 6d718178bf7490d29c0668d892add4c302b8925a
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99893636"
---
# <a name="include-element"></a>Include — element
Element include określa plik, który może znajdować się w podanej ścieżce include do wstawienia do bieżącego pliku.  Wszystkie zdefiniowane symbole i typy staną się częścią skompilowanego wyniku.

## <a name="syntax"></a>Składnia

```csharp
<Include href="stdidcmd.h" />
```

## <a name="attributes-and-elements"></a>Atrybuty i elementy
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.

### <a name="attributes"></a>Atrybuty

|Atrybut|Opis|
|---------------|-----------------|
|Tag|Wymagane. Ścieżka do pliku nagłówkowego:<br /><br /> href = "Stdidcmd. h"|
|Warunek|Opcjonalny. Zobacz [atrybuty warunkowe](../extensibility/vsct-xml-schema-conditional-attributes.md).|

### <a name="child-elements"></a>Elementy podrzędne

|Element|Opis|
|-------------|-----------------|
|Brak.|Brak.|

### <a name="parent-elements"></a>Elementy nadrzędne

|Element|Opis|
|-------------|-----------------|
|[Element polecenia](../extensibility/commandtable-element.md)|Definiuje wszystkie elementy, które reprezentują polecenia — czyli elementy menu, menu, paski narzędzi i pola kombi, które pakietu VSPackage zapewnia IDE.|

## <a name="example"></a>Przykład

```
<Include href="PackagePlacements.vsct"/>
```

## <a name="see-also"></a>Zobacz także
- [Pliki tabeli poleceń programu Visual Studio (. vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
