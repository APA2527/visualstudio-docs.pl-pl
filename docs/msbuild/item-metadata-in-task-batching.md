---
title: Metadane elementu w przetwarzaniu wsadowym zadań | Microsoft Docs
description: Dowiedz się, w jaki sposób MSBuild korzysta z metadanych elementów w partiach zadań, aby podzielić listy elementów na różne kategorie lub partie, a następnie uruchamiać zadanie jednokrotnie przy każdej partii.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, batching
- task batching [MSBuild]
- MSBuild, task batching
ms.assetid: 31e480f8-fe4d-4633-8c54-8ec498e2306d
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 28451b9bf317c33e1aff52a62247374ea2b6871e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99913878"
---
# <a name="item-metadata-in-task-batching"></a>Metadane elementu w przetwarzaniu wsadowym zadań

Program MSBuild ma możliwość dzielenia list elementów na różne kategorie lub partie, na podstawie metadanych elementów i uruchamiania zadania jeden raz z każdą partią. Może być myląca, aby dokładnie zrozumieć, jakie elementy są przesyłane, z których partiami. W tym temacie opisano następujące typowe scenariusze związane z przetwarzaniem wsadowym.

- Dzielenie listy elementów na partie

- Dzielenie kilku list elementów na partie

- Wsadowe pojedyncze elementy w czasie

- Filtrowanie list elementów

Aby uzyskać więcej informacji o przetwarzaniu wsadowym przy użyciu programu MSBuild, zobacz [Batching](../msbuild/msbuild-batching.md).

## <a name="divide-an-item-list-into-batches"></a>Dzielenie listy elementów na partie

Przetwarzanie wsadowe umożliwia dzielenie listy elementów na różne partie na podstawie metadanych elementów i przekazywanie poszczególnych partii do zadania oddzielnie. Jest to przydatne w przypadku tworzenia zestawów satelickich.

Poniższy przykład pokazuje, jak podzielić listę elementów na partie na podstawie metadanych elementu. `ExampColl`Lista elementów jest podzielona na trzy partie na podstawie `Number` metadanych elementu. Obecność `%(ExampColl.Number)` w `Text` atrybucie powiadamia program MSBuild, że należy wykonać przetwarzanie wsadowe. `ExampColl`Lista elementów jest podzielona na trzy partie na podstawie `Number` metadanych, a każda partia jest przenoszona osobno do zadania.

```xml
<Project
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <ItemGroup>
        <ExampColl Include="Item1">
            <Number>1</Number>
        </ExampColl>
        <ExampColl Include="Item2">
            <Number>2</Number>
        </ExampColl>
        <ExampColl Include="Item3">
            <Number>3</Number>
        </ExampColl>
        <ExampColl Include="Item4">
            <Number>1</Number>
        </ExampColl>
        <ExampColl Include="Item5">
            <Number>2</Number>
        </ExampColl>
        <ExampColl Include="Item6">
            <Number>3</Number>
        </ExampColl>
    </ItemGroup>

    <Target Name="ShowMessage">
        <Message
            Text = "Number: %(ExampColl.Number) -- Items in ExampColl: @(ExampColl)"/>
    </Target>

</Project>
```

W oknie [komunikatu](../msbuild/message-task.md) są wyświetlane następujące informacje:

`Number: 1 -- Items in ExampColl: Item1;Item4`

`Number: 2 -- Items in ExampColl: Item2;Item5`

`Number: 3 -- Items in ExampColl: Item3;Item6`

## <a name="divide-several-item-lists-into-batches"></a>Dzielenie kilku list elementów na partie

Program MSBuild może podzielić wiele list elementów na partie na podstawie tych samych metadanych. Dzięki temu można łatwo podzielić różne listy elementów na partie, aby skompilować wiele zestawów. Na przykład można mieć listę elementów plików *CS* podzieloną na partię aplikacji i partię zestawu oraz listę elementów zasobów podzieloną na partię aplikacji i partię zestawu. Następnie można użyć usługi Batch, aby przekazać te listy elementów do jednego zadania i skompilować aplikację i zestaw.

> [!NOTE]
> Jeśli lista elementów przenoszona do zadania nie zawiera żadnych elementów z metadanymi, do których się odwołuje, każdy element na liście elementów jest przesyłany do każdej partii.

Poniższy przykład pokazuje, jak podzielić wiele list elementów na partie na podstawie metadanych elementu. `ExampColl` `ExampColl2` Listy elementów i są podzielone na trzy partie na podstawie `Number` metadanych elementu. Obecność `%(Number)` w `Text` atrybucie powiadamia program MSBuild, że należy wykonać przetwarzanie wsadowe. `ExampColl` `ExampColl2` Listy elementów i są podzielone na trzy partie na podstawie `Number` metadanych, a każda partia jest przenoszona osobno do zadania.

```xml
<Project
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <ItemGroup>

        <ExampColl Include="Item1">
            <Number>1</Number>
        </ExampColl>
        <ExampColl Include="Item2">
            <Number>2</Number>
        </ExampColl>
        <ExampColl Include="Item3">
            <Number>3</Number>
        </ExampColl>

        <ExampColl2 Include="Item4">
            <Number>1</Number>
        </ExampColl2>
        <ExampColl2 Include="Item5">
            <Number>2</Number>
        </ExampColl2>
        <ExampColl2 Include="Item6">
            <Number>3</Number>
        </ExampColl2>

    </ItemGroup>

    <Target Name="ShowMessage">
        <Message
            Text = "Number: %(Number) -- Items in ExampColl: @(ExampColl) ExampColl2: @(ExampColl2)"/>
    </Target>

</Project>
```

W oknie [komunikatu](../msbuild/message-task.md) są wyświetlane następujące informacje:

`Number: 1 -- Items in ExampColl: Item1 ExampColl2: Item4`

`Number: 2 -- Items in ExampColl: Item2 ExampColl2: Item5`

`Number: 3 -- Items in ExampColl: Item3 ExampColl2: Item6`

## <a name="batch-one-item-at-a-time"></a>Wsadowe pojedyncze elementy

Przetwarzanie wsadowe może również odbywać się w przypadku metadanych o dobrze znanych elementach, które są przypisywane do każdego elementu podczas tworzenia. Gwarantuje to, że każdy element w kolekcji będzie miał metadane do użycia na potrzeby przetwarzania wsadowego. `Identity`Wartość metadanych jest unikatowa dla każdego elementu i jest przydatna do dzielenia każdego elementu na liście elementów na osobną partię. Aby uzyskać pełną listę metadanych dobrze znanych elementów, zobacz [dobrze znane metadane elementu](../msbuild/msbuild-well-known-item-metadata.md).

Poniższy przykład pokazuje, jak pojedynczo wsadowo poszczególne elementy z listy elementów. Ponieważ `Identity` wartość metadanych każdego elementu jest unikatowa, `ExampColl` Lista elementów jest podzielona na sześć partii, każda partia zawierająca jeden element listy elementów. Obecność `%(Identity)` w `Text` atrybucie powiadamia program MSBuild, że należy wykonać przetwarzanie wsadowe.

```xml
<Project
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <ItemGroup>

        <ExampColl Include="Item1"/>
        <ExampColl Include="Item2"/>
        <ExampColl Include="Item3"/>
        <ExampColl Include="Item4"/>
        <ExampColl Include="Item5"/>
        <ExampColl Include="Item6"/>

    </ItemGroup>

    <Target Name="ShowMessage">
        <Message
            Text = "Identity: '%(Identity)' -- Items in ExampColl: @(ExampColl)"/>
    </Target>

</Project>
```

W oknie [komunikatu](../msbuild/message-task.md) są wyświetlane następujące informacje:

```output
Identity: 'Item1' -- Items in ExampColl: Item1
Identity: 'Item2' -- Items in ExampColl: Item2
Identity: 'Item3' -- Items in ExampColl: Item3
Identity: 'Item4' -- Items in ExampColl: Item4
Identity: 'Item5' -- Items in ExampColl: Item5
Identity: 'Item6' -- Items in ExampColl: Item6
```

## <a name="filter-item-lists"></a>Filtruj listy elementów

Przy użyciu operacji wsadowych można odfiltrować niektóre elementy z listy elementów przed przekazaniem jej do zadania. Na przykład filtrowanie `Extension` wartości metadanych dobrze znanego elementu umożliwia uruchamianie zadania tylko dla plików o określonym rozszerzeniu.

Poniższy przykład pokazuje, jak podzielić listę elementów na partie na podstawie metadanych elementu, a następnie odfiltrować te partie, gdy są one przesyłane do zadania. `ExampColl`Lista elementów jest podzielona na trzy partie na podstawie `Number` metadanych elementu. `Condition`Atrybut zadania określa, że tylko partie z `Number` wartością metadanych elementu `2` będą przesyłane do zadania

```xml
<Project
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <ItemGroup>

        <ExampColl Include="Item1">
            <Number>1</Number>
        </ExampColl>
        <ExampColl Include="Item2">
            <Number>2</Number>
        </ExampColl>
        <ExampColl Include="Item3">
            <Number>3</Number>
        </ExampColl>
        <ExampColl Include="Item4">
            <Number>1</Number>
        </ExampColl>
        <ExampColl Include="Item5">
            <Number>2</Number>
        </ExampColl>
        <ExampColl Include="Item6">
            <Number>3</Number>
        </ExampColl>

    </ItemGroup>

    <Target Name="Exec">
        <Message
            Text = "Items in ExampColl: @(ExampColl)"
            Condition="'%(Number)'=='2'"/>
    </Target>

</Project>
```

W oknie [komunikatu](../msbuild/message-task.md) są wyświetlane następujące informacje:

```
Items in ExampColl: Item2;Item5
```

## <a name="see-also"></a>Zobacz też

- [Metadane dobrze znanego elementu](../msbuild/msbuild-well-known-item-metadata.md)
- [Item — element (MSBuild)](../msbuild/item-element-msbuild.md)
- [ItemMetadata —, element (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)
- [Przetwarzanie wsadowe](../msbuild/msbuild-batching.md)
- [Pojęcia dotyczące programu MSBuild](../msbuild/msbuild-concepts.md)
- [Dokumentacja programu MSBuild](../msbuild/msbuild-reference.md)
