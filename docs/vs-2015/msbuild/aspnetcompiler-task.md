---
title: Aspnetcompiler — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#AspNetCompiler
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, AspNetCompiler task
- AspNetCompiler task [MSBuild]
ms.assetid: f811c019-a67b-4d54-82e6-e29549496f6e
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9e6e483d0267e9f267919940b85e33a355552543
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686026"
---
# <a name="aspnetcompiler-task"></a>AspNetCompiler — Zadanie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [przy użyciu aspnetcompiler — zadanie wstępnej kompilacji aplikacji ASP.NET](https://docs.microsoft.com/visualstudio/msbuild/aspnetcompiler-task).  
  
  
`AspNetCompiler` Zadań opakowuje aspnet_compiler.exe, narzędzie wstępnej kompilacji [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] aplikacji.  
  
## <a name="task-parameters"></a>Parametry zadania  
 W poniższej tabeli opisano parametry `AspNetCompiler` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`AllowPartiallyTrustedCallers`|Opcjonalnie `Boolean` parametru.<br /><br /> Jeśli ten parametr ma `true`,, zestawu o silnej nazwie umożliwi częściowo zaufanych wywołań.|  
|`Clean`|Opcjonalnie `Boolean` parametru<br /><br /> Jeśli ten parametr jest `true`, zostanie utworzona czyszczenie wstępnie skompilowanej aplikacji. Wszystkie składniki skompilowane wcześniej zostaną ponownie skompilowane. Wartość domyślna to `false`. Ten parametr odnosi się do **- c** Włącz aspnet_compiler.exe.|  
|`Debug`|Opcjonalnie `Boolean` parametru.<br /><br /> Jeśli ten parametr jest `true`, informacje o debugowaniu (. Plik PDB) są emitowane podczas kompilacji. Wartość domyślna to `false`. Ten parametr odnosi się do **-d** Włącz aspnet_compiler.exe.|  
|`DelaySign`|Opcjonalnie `Boolean` parametru.<br /><br /> Jeśli ten parametr jest `true`, zestaw jest niecałkowicie podpisany podczas tworzenia.|  
|`FixedNames`|Opcjonalnie `Boolean` parametru.<br /><br /> Jeśli ten parametr jest `true`, skompilowanych zestawów będzie mieć stałe nazwy...|  
|`Force`|Opcjonalnie `Boolean` parametru<br /><br /> Jeśli ten parametr jest `true`, zadania spowoduje zastąpienie katalog docelowy, jeśli już istnieje. Istniejąca zawartość zostanie utracona. Wartość domyślna to `false`. Ten parametr odnosi się do **-f** Włącz aspnet_compiler.exe.|  
|`KeyContainer`|Opcjonalnie `String` parametru.<br /><br /> Określa kontener klucza silnej nazwy.|  
|`KeyFile`|Opcjonalnie `String` parametru.<br /><br /> Określa ścieżkę fizyczną do pliku klucza silnej nazwy...|  
|`MetabasePath`|Opcjonalnie `String` parametru.<br /><br /> Określa pełną ścieżkę metabazy usług IIS aplikacji. Ten parametr nie może być łączone z `VirtualPath` lub `PhysicalPath` parametrów. Ten parametr odnosi się do **-m** Włącz aspnet_compiler.exe.|  
|`PhysicalPath`|Opcjonalnie `String` parametru.<br /><br /> Określa ścieżkę fizyczną aplikacji do skompilowania. Jeśli ten parametr jest Brak, metabazy usług IIS jest używana do lokalizowania aplikacji. Ten parametr odnosi się do **-p** Włącz aspnet_compiler.exe.|  
|`TargetFrameworkMoniker`|Opcjonalnie `String` parametru.<br /><br /> Określa TargetFrameworkMoniker wskazujący, która wersja środowiska .NET Framework aspnet_compiler.exe należy używać. Akceptuje tylko krótkie nazwy .NET Framework.|  
|`TargetPath`|Opcjonalnie `String` parametru.<br /><br /> Określa ścieżkę fizyczną, do której aplikacja jest kompilowana. Jeśli nie zostanie określony, aplikacja jest wstępnie skompilowaną w miejscu.|  
|`Updateable`|Opcjonalnie `Boolean` parametru.<br /><br /> Jeśli ten parametr jest `true`, wstępnie skompilowanej aplikacji będzie można aktualizować.  Wartość domyślna to `false`. Ten parametr odnosi się do **-u** Włącz aspnet_compiler.exe.|  
|`VirtualPath`|Opcjonalnie `String` parametru.<br /><br /> Ścieżka wirtualna aplikacja jest kompilowana. Jeśli `PhysicalPath` określony, ścieżkę fizyczną jest używana do lokalizowania aplikacji. W przeciwnym razie metabazy usług IIS jest używana, a aplikacja będzie traktowana jako w domyślnej witrynie. Ten parametr odnosi się do **- v** Włącz aspnet_compiler.exe.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów wymienionych powyżej, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.ToolTaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.ToolTask> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [tooltaskextension — klasa bazowa](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu wykorzystuje `AspNetCompiler` zadania wstępnej kompilacji [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] aplikacji.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="PrecompileWeb">  
        <AspNetCompiler  
            VirtualPath="/MyWebSite"  
            PhysicalPath="c:\inetpub\wwwroot\MyWebSite\"  
            TargetPath="c:\precompiledweb\MyWebSite\"  
            Force="true"  
            Debug="true"  
        />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)



