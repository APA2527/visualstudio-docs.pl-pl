---
title: XslTransformation Task | Microsoft Docs
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
- MSBuild, XslTransformation task
- XslTransformation task [MSBuild]
ms.assetid: 6f3a7d81-3ae3-4703-9a06-870b32b69d80
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9a18dff58b38dc80eade3ef030b4156b040cc8ce
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233077"
---
# <a name="xsltransformation-task"></a>XslTransformation — zadanie
Przekształcenia na XML danych wejściowych za pomocą XSLT lub skompilowane XSLT i dane wyjściowe do wyjścia urządzenia lub pliku.  
  
## <a name="parameters"></a>Parametry  
 W poniższej tabeli opisano parametry `XslTransformation` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`OutputPaths`|Wymagany parametr interfejsu <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Określa pliki wyjściowe transformacji XML.|  
|`Parameters`|Opcjonalnie `String` parametru.<br /><br /> Określa parametry do dokumentu XSLT w danych wejściowych.|  
|`XmlContent`|Opcjonalnie `String` parametru.<br /><br /> Określa dane wejściowe XML jako ciąg.|  
|`XmlInputPaths`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Określa pliki danych wejściowych XML.|  
|`XslCompiledDllPath`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Określa skompilowanych XSLT.|  
|`XslContent`|Opcjonalnie `String` parametru.<br /><br /> Określa dane wejściowe XSLT jako ciąg.|  
|`XslInputPath`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Określa wejściowy plik XSLT.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów, które są wymienione w tabeli, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)