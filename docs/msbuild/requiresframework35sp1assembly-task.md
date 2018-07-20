---
title: Requiresframework35sp1assembly — zadanie | Dokumentacja firmy Microsoft
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
- RequiresFramework35SP1Assembly task [MSBuild]
- MSBuild, RequiresFramework35SP1Assembly task
ms.assetid: 755c018a-8a8b-4c94-8aee-3f171fc419e5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5297d1a573542fecc55fa90983befa43df8f3f3d
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39155369"
---
# <a name="requiresframework35sp1assembly-task"></a>RequiresFramework35SP1Assembly — zadanie
Określa, czy aplikacja wymaga .NET Framework 3.5 SP1.  
  
## <a name="parameters"></a>Parametry  
 W poniższej tabeli opisano parametry `RequiresFramework35SP1Assembly` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`Assemblies`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Określa zestawy, do których istnieją odwołania w aplikacji.|  
|`CreateDesktopShortcut`|Opcjonalnie `Boolean` parametru.<br /><br /> Jeśli `true`, tworzy ikonę skrótu na pulpicie podczas instalacji.|  
|`DeploymentManifestEntryPoint`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Określa nazwę pliku manifestu aplikacji.|  
|`EntryPoint`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Określa zestaw, który ma być wykonany po uruchomieniu aplikacji.|  
|`ErrorReportUrl`|Opcjonalnie `String` parametru.<br /><br /> Określa witryny sieci Web, która jest wyświetlana w oknach dialogowych, które zostaną napotkane podczas instalacji ClickOnce.|  
|`Files`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Określa listę plików, które zostaną wdrożone, gdy aplikacja została opublikowana.|  
|`ReferencedAssemblies`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Określa zestawy, do których istnieją odwołania w projekcie.|  
|`RequiresMinimumFramework35SP1`|Opcjonalnie `Boolean` parametr wyjściowy.<br /><br /> Jeśli `true`, aplikacja wymaga .NET Framework 3.5 SP1.|  
|`SigningManifests`|Opcjonalnie `Boolean` parametr wyjściowy.<br /><br /> Jeśli `true`, manifesty ClickOnce są podpisane.|  
|`SuiteName`|Opcjonalnie `String` parametru.<br /><br /> Określa nazwę folderu na **Start** menu, w którym aplikacja zostanie zainstalowana.|  
|`TargetFrameworkVersion`|Opcjonalnie `String` parametru.<br /><br /> Określa wersję programu .NET, że cele aplikacji.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów, które są wymienione w tabeli, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)