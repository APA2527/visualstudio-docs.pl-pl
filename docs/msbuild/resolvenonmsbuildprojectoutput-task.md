---
title: ResolveNonMSBuildProjectOutput — — Zadanie | Microsoft Docs
description: Dowiedz się, w jaki sposób MSBuild używa zadania ResolveNonMSBuildProjectOutput — do określenia plików wyjściowych dla odwołań projektu innych niż MSBuild.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ResolveNonMSBuildProjectOutput task
- ResolveNonMSBuildProjectOutput task [MSBuild]
ms.assetid: a0b8fcec-8c8d-4867-85ac-5304c5108e5e
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 98d8e483b8ad03f02283620f65ec0351d9d64051
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99912450"
---
# <a name="resolvenonmsbuildprojectoutput-task"></a>ResolveNonMSBuildProjectOutput — zadanie

Określa pliki wyjściowe dla odwołań projektu innych niż MSBuild.

## <a name="parameters"></a>Parametry

 W poniższej tabeli opisano parametry `ResolveNonMSBuildProjectOutput` zadania.

|Parametr|Opis|
|---------------|-----------------|
|`PreresolvedProjectOutputs`|Opcjonalny `String` parametr.<br /><br /> Określa ciąg XML, który zawiera rozpoznane dane wyjściowe projektu.|
|`ProjectReferences`|Wymagany parametr interfejsu <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Określa odwołania do projektu.|
|`ResolvedOutputPaths`|Opcjonalny <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Zawiera listę rozwiązanych ścieżek odwołań (i zachowuje pierwotne atrybuty odwołania projektu).|
|`UnresolvedProjectReferences`|Opcjonalny <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Zawiera listę elementów odwołań projektu, których nie można rozpoznać przy użyciu prewiązanej listy danych wyjściowych.<br /><br /> Ponieważ program Visual Studio rozpoznaje tylko wstępnie projekty programów innych niż MSBuild, oznacza to, że odwołania do projektu na tej liście są w formacie MSBuild.|

## <a name="remarks"></a>Uwagi

 Oprócz parametrów, które są wymienione w tabeli, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasy, która sama dziedziczy z <xref:Microsoft.Build.Utilities.Task> klasy. Aby zapoznać się z listą tych dodatkowych parametrów i ich opisów, zobacz [TaskExtension Base Class](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Zobacz też

- [Zadania](../msbuild/msbuild-tasks.md)
- [Dokumentacja zadań](../msbuild/msbuild-task-reference.md)