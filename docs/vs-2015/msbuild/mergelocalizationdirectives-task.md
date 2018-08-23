---
title: Mergelocalizationdirectives — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
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
helpviewer_keywords:
- localizing XAML [WPF MSBuild], moving comments and attributes to a separate file
- MergeLocalizationDirectives task [WPF MSBuild], parameters
- MergeLocalizationDirectives task [WPF MSBuild]
- moving localization comments and attributes to a separate file [WPF MSBuild]
ms.assetid: 9095b4f1-88da-4194-914b-ee1456826830
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 773ff1accce2a6399515f56aa65be61d6673c934
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688659"
---
# <a name="mergelocalizationdirectives-task"></a>MergeLocalizationDirectives — Zadanie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [MergeLocalizationDirectives, zadanie](https://docs.microsoft.com/visualstudio/msbuild/mergelocalizationdirectives-task).  
  
  
<xref:Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives> Zadań scala atrybuty lokalizacji i komentarze, co najmniej jednego [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] plików binarnych w jeden plik dla całego zestawu.  
  
## <a name="task-parameters"></a>Parametry zadania  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`GeneratedLocalizationFiles`|Wymagane **[] ITaskItem** parametru.<br /><br /> Określa listę plików dyrektywy lokalizacji dla poszczególnych plików w [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] format binarny.|  
|`OutputFile`|Wymagane **ciąg** parametr wyjściowy.<br /><br /> Określa ścieżkę wyjściową zestawu skompilowanego dyrektywy lokalizacji.|  
  
## <a name="remarks"></a>Uwagi  
 Możesz dodać atrybuty lokalizacji i komentarze, aby [!INCLUDE[TLA#tla_xaml](../includes/tlasharptla-xaml-md.md)] zawartości. Za pomocą [!INCLUDE[TLA#tla_wpf](../includes/tlasharptla-wpf-md.md)] obsługi lokalizacji można odłączenia lokalizacja atrybutów i komentarzy i umieść je w pliku .loc, który jest oddzielony od wygenerowanego zestawu. Można to zrobić za pomocą **LocalizationPropertyStorage** atrybutu. Aby uzyskać więcej informacji na temat atrybuty lokalizacji i komentarze a **LocalizationPropertyStorage**, zobacz [lokalizacja atrybutów i komentarzy](http://msdn.microsoft.com/library/ead2d9ac-b709-4ec1-a924-39927a29d02f).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład scala lokalizacji kilku [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] plików binarnych do .loc pojedynczego pliku.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MergeLocalizationDirectivesTask">  
    <MergeLocalizationDirectives   
      GeneratedLocalizationFiles="obj\debug\page1.loc;obj\debug\page2.loc;obj\debug\page3.loc"  
      OutputFile="obj\debug\WPFMSBuildSample.loc" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do WPF MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Odwołanie do zadania](../msbuild/wpf-msbuild-task-reference.md)   
 [Odwołanie do narzędzia MSBuild](../msbuild/msbuild-reference.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)   
 [Kompilowanie aplikacji WPF (WPF)](http://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)



