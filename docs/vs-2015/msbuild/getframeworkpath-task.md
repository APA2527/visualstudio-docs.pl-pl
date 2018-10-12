---
title: Getframeworkpath — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkPath task [MSBuild]
- MSBuild, GetFrameworkPath task
ms.assetid: 5b7bcdd7-d4a0-442d-af29-8aadb3b10598
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dcad656c058fffaf3f075b195cb1f105079a8e5d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49248602"
---
# <a name="getframeworkpath-task"></a>GetFrameworkPath — Zadanie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Pobiera ścieżkę do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] zestawów.  
  
## <a name="task-parameters"></a>Parametry zadania  
 W poniższej tabeli opisano parametry `GetFrameworkPath` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`FrameworkVersion11Path`|Opcjonalnie `String` parametr wyjściowy.<br /><br /> Zawiera ścieżkę do zestawów framework w wersji 1.1, jeśli jest obecny. W przeciwnym razie zwraca `null`.|  
|`FrameworkVersion20Path`|Opcjonalnie `String` parametr wyjściowy.<br /><br /> Zawiera ścieżkę do zestawów framework w wersji 2.0, jeśli jest obecny. W przeciwnym razie zwraca `null`.|  
|`FrameworkVersion30Path`|Opcjonalnie `String` parametr wyjściowy.<br /><br /> Zawiera ścieżkę do zestawów framework w wersji 3.0 lub nowszej, jeśli jest obecny. W przeciwnym razie zwraca `null`.|  
|`FrameworkVersion35Path`|Opcjonalnie `String` parametr wyjściowy.<br /><br /> Zawiera ścieżkę do zestawów w wersji 3.5 framework, jeśli jest obecny. W przeciwnym razie zwraca `null`.|  
|`FrameworkVersion40Path`|Opcjonalnie `String` parametr wyjściowy.<br /><br /> Zawiera ścieżkę do zestawów framework w wersji 4.0 lub nowszej, jeśli jest obecny. W przeciwnym razie zwraca `null`.|  
|`Path`|Opcjonalnie `String` parametr wyjściowy.<br /><br /> Zawiera ścieżkę do najnowszych zestawów framework, jeśli są dostępne. W przeciwnym razie zwraca `null`.|  
  
## <a name="remarks"></a>Uwagi  
 Jeśli różne wersje programu [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] są zainstalowane, to zadanie zwraca informacje o wersji, [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] jest przeznaczony do działania.  
  
 Oprócz parametrów wymienionych powyżej, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto `GetFrameworkPath` zadania do ścieżki do przechowywania [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] w `FrameworkPath` właściwości.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="FrameworkPath" />  
        </GetFrameworkPath>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)



