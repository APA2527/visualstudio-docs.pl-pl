---
title: Uidmanager — zadanie | Dokumentacja firmy Microsoft
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
- UidManager task [WPF MSBuild]
- UidManager task [WPF MSBuild], parameters
- managing UIDs when localizing XAML elements [WPF MSBuild]
- localizing XAML elements [WPF MSBuild], managing UIDs
- checking UIDs when localizing XAML elements [WPF MSBuild]
ms.assetid: 4fc7b5a5-11b0-46ca-9656-8c2a0b08d1fe
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0e56cfe5e3c7c8c4142babe920746ae7c0a5f229
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39154680"
---
# <a name="uidmanager-task"></a>Uidmanager — zadanie
<xref:Microsoft.Build.Tasks.Windows.UidManager> Zadanie sprawdza, aktualizuje lub usuwa unikatowe identyfikatory (UID), aby zlokalizować wszystkie [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] elementy, które znajdują się w źródle [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] plików.  
  
## <a name="task-parameters"></a>Parametry zadania  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`IntermediateDirectory`|Opcjonalnie **ciąg** parametru.<br /><br /> Określa katalog, który służy do tworzenia kopii zapasowej źródła [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] pliki, które są określone przez **MarkupFiles** parametru.|  
|`MarkupFiles`|Wymagane **[] ITaskItem** parametru.<br /><br /> Określa źródło [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] pliki do dołączenia do UID sprawdzania, aktualizowania lub usuwania.|  
|`Task`|Wymagane **ciąg** parametru.<br /><br /> Określa zadanie zarządzania UID, które chcesz wykonać. Prawidłowe opcje to **Sprawdź**, **aktualizacji**, lub **Usuń**.|  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:Microsoft.Build.Tasks.Windows.UidManager> zadania, aby sprawdzić, czy określone źródło [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] pliki zawierają [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] elementy, które mają odpowiednie UID.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.UidManager"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="UidManagerTask">  
    <UidManager  
      Task="Check"  
      MarkupFiles="Page1.xaml;Page2.xaml"  
      IntermediateDirectory="c:\UidManagerIntermediateDirectory" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Odwołanie do WPF MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Odwołanie do zadania](../msbuild/wpf-msbuild-task-reference.md)   
 [Odwołanie do narzędzia MSBuild](../msbuild/msbuild-reference.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)   
 [Kompilowanie aplikacji WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)   
 [Porady: lokalizowanie aplikacji](/dotnet/framework/wpf/advanced/how-to-localize-an-application)