---
title: MOVE — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Move task
- Move task [MSBuild]
ms.assetid: d1405347-1309-4f18-b565-905408093d59
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3aaa9d7113d27acd3d5d30292fba2c6564fe3290
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077263"
---
# <a name="move-task"></a>Move — Zadanie
Przenosi pliki do nowej lokalizacji.  
  
## <a name="parameters"></a>Parametry  
 W następujących tabeli przedstawiono parametry `Move` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`DestinationFiles`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Określa listę plików, aby przenieść pliki źródłowe do. Ta lista powinna być zmapowana do listy, który jest określony w `SourceFiles` parametru. Oznacza to, że pierwszy plik określony w `SourceFiles` zostaną przeniesione do pierwszej lokalizacji określonej w `DestinationFiles`, i tak dalej.|  
|`DestinationFolder`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Określa katalog, do której chcesz umieścić pliki.|  
|`MovedFiles`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Zawiera elementy, które zostały prawidłowo przeniesione.|  
|`OverwriteReadOnlyFiles`|Opcjonalnie `Boolean` parametru.<br /><br /> Jeśli `true`, zastępuje pliki, nawet wtedy, gdy są one oznaczone jako pliki tylko do odczytu.|  
|`SourceFiles`|Wymagany parametr interfejsu <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Określa pliki, aby przenieść.|  
  
## <a name="remarks"></a>Uwagi  
 Albo `DestinationFolder` parametru lub `DestinationFiles` parametr musi być określony, ale nie oba. W razie podania obu parametrów zadanie nie powiedzie się i zostanie zarejestrowany błąd.  

 `Move` Zadanie tworzy foldery zgodnie z wymaganiami dla docelowej lokalizacji plików.

 Oprócz parametrów, które są wymienione w tabeli, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)
