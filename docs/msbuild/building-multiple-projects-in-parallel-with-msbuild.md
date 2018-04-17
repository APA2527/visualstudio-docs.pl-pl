---
title: Tworzenie wielu projektów równolegle przy użyciu programu MSBuild | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- parallel project builds
- building multiple projects in parallel
- msbuild, building projects in parallel
ms.assetid: c8c9aadc-33ad-4aa1-b07d-b879e9eabda0
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f1ef276ef16f7bdb72c4dc3211ab994553a92e0e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="building-multiple-projects-in-parallel-with-msbuild"></a>Równoległe tworzenie wielu projektów za pomocą narzędzia MSBuild
Można użyć programu MSBuild do kompilacji wielu projektów przez uruchomienie ich równolegle. Aby uruchomić kompilacje równolegle, należy użyć następujących ustawień na komputerze z wieloma procesorami lub procesorem o wielu rdzeniach:  
  
-   Należy użyć przełącznika `/maxcpucount` w wierszu polecenia.  
  
-   Parametr zadania <xref:Microsoft.Build.Tasks.MSBuild.BuildInParallel%2A> w zadaniu programu MSBuild.  
  
> [!NOTE]
>  **/Verbosity** (**/v**) przełącznik w wierszu polecenia można również wpływać na wydajność kompilacji. Wydajność kompilacji może spaść jeśli szczegółowość informacji dziennika kompilacji jest ustawiona na szczegóły lub diagnostyka, które są używane w celu rozwiązania problemów. Aby uzyskać więcej informacji, zobacz [uzyskiwanie dzienników kompilacji](../msbuild/obtaining-build-logs-with-msbuild.md) i [dotyczące wiersza polecenia](../msbuild/msbuild-command-line-reference.md).  
  
## <a name="maxcpucount-switch"></a>Przełącznik /maxcpucount  
 Podczas używania przełącznika `/maxcpucount`, lub `/m` w skrócie, program MSBuild może utworzyć określoną liczbę procesów MSBuild.exe, które mogą być wykonywane równolegle. Procesy te są nazywane także „procesami roboczymi”. Każdy proces roboczy używa oddzielnego rdzenia procesora, jeśli jakieś są dostępne, do kompilacji projektu a w tym samym czasie inne dostępne procesory mogą kompilować inne projekty. Na przykład ustawienie tego parametru na wartość „4” spowoduje, że program MSBuild utworzy cztery procesy robocze w celu skompilowania projektu.  
  
 Jeśli przełącznik `/maxcpucount` zostanie dołączony, bez określenia wartości, program MSBuild użyje maksymalnie wartości równej liczbie procesorów w komputerze.  
  
 Aby uzyskać więcej informacji na temat tego przełącznika, którą wprowadzono w MSBuild 3.5, zobacz [dotyczące wiersza polecenia](../msbuild/msbuild-command-line-reference.md).  
  
 Poniższy przykład powoduje, że program MSBuild będzie używać trzech procesów roboczych. Jeśli używana jest ta konfiguracja, program MSBuild może kompilować trzy projekty w tym samym czasie.  
  
```  
msbuild.exe myproj.proj /maxcpucount:3   
```  
  
## <a name="buildinparallel-task-parameter"></a>Parametr zadania BuildInParallel  
 `BuildInParallel` to opcjonalny parametr typu boolean w zadaniu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Gdy `BuildInParallel` ustawiono `true` (jego wartość domyślna to `false`), wiele procesów roboczych są generowane w celu kompilacji w wielu projektów w tym samym czasie, jak to możliwe. Do poprawnego działania przełącznik `/maxcpucount` musi być ustawiony na wartość większą niż 1, a system musi posiadać co najmniej dwa procesory lub procesor dwurdzeniowy.  
  
 Oto przykład, pobrany z microsoft.common.targets ilustrujący, jak ustawić parametr `BuildInParallel`.  
  
```  
<PropertyGroup>  
    <BuildInParallel Condition="'$(BuildInParallel)' ==   
        ''">true</BuildInParallel>  
</PropertyGroup>  
<MSBuild  
    Projects="@(_MSBuildProjectReferenceExistent)"  
    Targets="GetTargetPath"  
    BuildInParallel="$(BuildInParallel)"  
    Properties="%(_MSBuildProjectReferenceExistent.SetConfiguration);   
        %(_MSBuildProjectReferenceExistent.SetPlatform)"  
    Condition="'@(NonVCProjectReference)'!='' and   
        ('$(BuildingSolutionFile)' == 'true' or   
        '$(BuildingInsideVisualStudio)' == 'true' or   
        '$(BuildProjectReferences)' != 'true') and     
        '@(_MSBuildProjectReferenceExistent)' != ''"  
    ContinueOnError="!$(BuildingProject)">  
    <Output TaskParameter="TargetOutputs"   
        ItemName="_ResolvedProjectReferencePaths"/>  
</MSBuild>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Użycie wielu procesorów w projektach kompilacji](../msbuild/using-multiple-processors-to-build-projects.md)   
 [Zapisywanie rejestratorów kilku-procesorów obsługujących](../msbuild/writing-multi-processor-aware-loggers.md)   
 [Dostrajanie blogu równoległości kompilacji C++](http://go.microsoft.com/fwlink/?LinkId=251457)
