---
title: Element Task elementu UsingTask (MSBuild) | Microsoft Docs
description: Dowiedz się więcej o elemencie Task UsingTask programu MSBuild zawierającym dane, które są przesyłane do UsingTask TaskFactory.
ms.custom: SEO-VS-2020
ms.date: 03/13/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Task element [MSBuild]
- <Task> element [MSBuild]
ms.assetid: 49d8741b-f1ea-4470-94fd-a1ac27341a6a
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f99452021b0efef1e5df305e984c684f3f446905
ms.sourcegitcommit: 1a36533f385e50c05f661f440380fda6386ed3c1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "93047897"
---
# <a name="task-element-of-usingtask-msbuild"></a>Element Task elementu UsingTask (MSBuild)

Zawiera dane, które są przesyłane do `UsingTask` `TaskFactory` . Aby uzyskać więcej informacji, zobacz [UsingTask element (MSBuild)](../msbuild/usingtask-element-msbuild.md).

 \<Project> \<UsingTask>
 \<Task>

## <a name="syntax"></a>Składnia

```xml
<Task Evaluate="true/false" />
```

## <a name="attributes-and-elements"></a>Atrybuty i elementy

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.

### <a name="attributes"></a>Atrybuty

|Atrybut|Opis|
|---------------|-----------------|
|`Evaluate`|Opcjonalny atrybut Boolean.<br /><br /> Jeśli `true` , MSBuild ocenia wszystkie elementy wewnętrzne i rozszerza elementy i właściwości przed przekazaniem informacji do `TaskFactory` momentu wystąpienia zadania.|

### <a name="child-elements"></a>Elementy podrzędne

|Element|Opis|
|-------------|-----------------|
|Dane|Tekst między `Task` tagami jest wysyłany Verbatim do `TaskFactory` .|

### <a name="parent-elements"></a>Elementy nadrzędne

| Element | Opis |
| - | - |
| [UsingTask](../msbuild/usingtask-element-msbuild.md) | Zapewnia sposób rejestrowania zadań w programie MSBuild. W projekcie może istnieć zero lub więcej `UsingTask` elementów. |

## <a name="example"></a>Przykład

 Poniższy przykład pokazuje, jak używać `Task` elementu z `Evaluate` atrybutem.

```xml
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">
       <ParameterGroup>
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>
              ...
</ParameterGroup>
       <Task Evaluate="true">
       ... Task factory-specific data ...
       </Task>
</UsingTask>
```

## <a name="see-also"></a>Zobacz też

- [Zadania](../msbuild/msbuild-tasks.md)
- [Dokumentacja zadań](../msbuild/msbuild-task-reference.md)
- [Odwołanie do schematu pliku projektu](../msbuild/msbuild-project-file-schema-reference.md)
