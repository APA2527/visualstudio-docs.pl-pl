---
title: "Project — Element (szablony Visual Studio) | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#Project
helpviewer_keywords:
- Project element [Visual Studio Templates]
- <Project> element [Visual Studio Templates]
ms.assetid: 1da15ea6-26e2-462b-a03e-584ef4996579
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6b4a60bdd81d2e6428d0fdafa6547227a496f862
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="project-element-visual-studio-templates"></a>Project — Element (szablony Visual Studio)
Określa plików lub katalogów do dodania do projektu.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Projekt >  
  
## <a name="syntax"></a>Składnia  
  
```  
<Project  
    File="MyProject.proj"  
    TargetFileName="MyTargetProject.proj"  
    ReplaceParameters="true/false">  
    IgnoreProjectParameter="$myCustomParameter$"  
        ...  
</Project>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybut, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`File`|Atrybut wymagany.<br /><br /> Określa nazwę pliku projektu w pliku zip szablonu.|  
|`ReplaceParameters`|Atrybut opcjonalny.<br /><br /> Wartość logiczna określająca, czy plik projektu ma wartości parametrów, które muszą zostać zastąpione podczas projektu jest tworzona na podstawie szablonu. Wartość domyślna to `false`.|  
|`TargetFileName`|Atrybut opcjonalny.<br /><br /> Określa nazwę pliku projektu, gdy projekt jest tworzony na podstawie szablonu.|  
|`IgnoreProjectParameter`|Atrybut opcjonalny.<br /><br /> Określa, czy projekt powinien zostać dodany do bieżącego rozwiązania. Jeśli wartość parametru niestandardowego "$*myCustomParameter*$" istnieje w pliku zamienny parametr projektu jest utworzony, ale nie dodać jako część aktualnie otwartego rozwiązania.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[Folder](../extensibility/folder-element-visual-studio-project-templates.md)|Element opcjonalny.<br /><br /> Określa folder do dodania do projektu.|  
|[ProjectItem](../extensibility/projectitem-element-visual-studio-project-templates.md)|Element opcjonalny.<br /><br /> Określa plik, aby dodać do projektu.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Element wymagany.|  
  
## <a name="remarks"></a>Uwagi  
 `Project`jest elementem podrzędnym opcjonalne `TemplateContent`.  
  
 `Project` Element jest używany do zmiennoprzecinkową projektu i w związku z tym jest prawidłowy tylko w szablonach projektu.  
  
 `Project`elementy mogą mieć [folderu](../extensibility/folder-element-visual-studio-project-templates.md) elementów podrzędnych lub [ProjectItem](../extensibility/projectitem-element-visual-studio-project-templates.md) elementów podrzędnych, ale nie ich kombinacjami `Folder` i `ProjectItem` elementów podrzędnych.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]automatycznie zmienia nazwę pliku projektu, na podstawie nazwy wprowadzony przez użytkownika w **nowy projekt** okno dialogowe. Użyj `TargetFileName` atrybut, jeśli chcesz podać nazwę pliku alternatywnego plików projektu utworzonych na podstawie tego szablonu.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie przedstawiono metadane szablonu projektu dla [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] aplikacji.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyStarterKit.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do schematu szablonu Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Tworzenie szablony projektów i elementów](../ide/creating-project-and-item-templates.md)   
 [Projectitem — Element (szablony projektu Visual Studio)](../extensibility/projectitem-element-visual-studio-project-templates.md)   
 [Folder — Element (szablony projektu Visual Studio)](../extensibility/folder-element-visual-studio-project-templates.md)