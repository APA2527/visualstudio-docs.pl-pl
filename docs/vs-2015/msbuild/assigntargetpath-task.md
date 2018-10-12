---
title: AssignTargetPath, zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 0e830e31-3bcf-4259-b2a8-a5df49b92d51
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 667725da8006e99e8eba4d4d4cd18e101ae1dd4e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49189467"
---
# <a name="assigntargetpath-task"></a>AssignTargetPath — Zadanie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
To zadanie akceptuje listę plików i dodaje `<TargetPath>` atrybuty, jeśli nie są już określone.  
  
## <a name="task-parameters"></a>Parametry zadania  
 W poniższej tabeli opisano parametry `AssignTargetPath` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`RootFolder`|Opcjonalnie `string` parametr wejściowy.<br /><br /> Zawiera ścieżkę do folderu, który zawiera łącza miejsc docelowych.|  
|`Files`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wejściowy.<br /><br /> Zawiera przychodzącą listę plików.|  
|`AssignedFiles`|Optional<br /><br /> <xref:Microsoft.Build.Framework.ITaskItem> `[]` Parametr wyjściowy.<br /><br /> Zawiera uzyskaną listę plików.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów wymienionych powyżej, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład wykonuje `AssignTargetPath` zadanie, aby skonfigurować projekt.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="MyProject">  
        <AssignTargetPath  
RootFolder="Resources"  
            Files="@(ResourceFiles)"  
            <Output TaskParameter="AssignedFiles"  
                ItemName="OutAssignedFiles"/>  
        </AssignTargetPath>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)



