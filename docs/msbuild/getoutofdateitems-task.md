---
title: Zadanie GetOutOfDateItems | Dokumentacja firmy Microsoft
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.getoutofdateitems
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), GetOutOfDateItems task
- GetOutOfDateItems task (MSBuild (Visual C++))
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 668dddcd0854869c9ede7bf96c092d415f41dd17
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2019
ms.locfileid: "58071134"
---
# <a name="getoutofdateitems-task"></a>GetOutOfDateItems task

Zadanie pomocnika, które odczytuje tlogs stare, zapisuje nowe tlogs i zwraca zestaw elementów, które nie są aktualne.

## <a name="parameters"></a>Parametry

W poniższej tabeli opisano parametry **GetOutOfDateItems** zadania.

|Parametr|Opis|
|---------------|-----------------|
|**CheckForInterdependencies**|Opcjonalnie **bool** parametru.|
|**CommandMetadataName**|Opcjonalnie **ciąg** parametru.|
|**DependenciesMetadataName**|Opcjonalnie **ciąg** parametru.|
|**HasInterdependencies**|Opcjonalnie **bool** parametr wyjściowy.|
|**OutOfDateSources**|Opcjonalnie **[] ITaskItem** parametr wyjściowy.|
|**OutputsMetadataName**|Wymagane **ciąg** parametru.|
|**Źródła**|Opcjonalnie **[] ITaskItem** parametru.|
|**TLogDirectory**|Wymagane **ciąg** parametru.|
|**TLogNamePrefix**|Wymagane **ciąg** parametru.|

## <a name="see-also"></a>Zobacz także

[Odwołanie do zadania](../msbuild/msbuild-task-reference.md)