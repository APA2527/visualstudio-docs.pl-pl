---
title: ProjectType — Element (szablony Visual Studio) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectType
helpviewer_keywords:
- ProjectType element [Visual Studio project templates]
ms.assetid: ccf9d83f-c7f3-49c7-a31f-e1f22bec004c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bb16116994648ec70c770af7ca4932cd1443bd30
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="projecttype-element-visual-studio-templates"></a>ProjectType — Element (szablony Visual Studio)
Kategoryzuje szablon projektu, aby był on wyświetlany w obszarze określonej grupy w **nowy projekt** lub **Dodaj nowy element** okno dialogowe.  
  
> [!WARNING]
>  Szablony projektu są obsługiwane dla języka C++ w programie Visual Studio 2012. Nie są obsługiwane dla języka C++ w Visual Studio 2010 i wcześniejszych wersjach.  
  
 \<VSTemplate>  
 \<TemplateData >  
 \<Typ projektu >  
  
## <a name="syntax"></a>Składnia  
  
```  
<ProjectType> CSharp/VisualBasic/VC/Web </ProjectType>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybut, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Kategoryzuje szablonu i definiuje sposób wyświetlania albo **nowy projekt** lub **Dodaj nowy element** okno dialogowe.|  
  
## <a name="text-value"></a>Wartość tekstowa  
 Wartość tekstowa jest wymagana.  
  
 Ta wartość określa typ projektu szablonu zostanie utworzony i musi zawierać jeden z następujących wartości:  
  
-   `CSharp`: Określa, czy szablon tworzy [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projektów lub elementów.  
  
-   `VisualBasic`: Określa, czy szablon tworzy [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projektów lub elementów.  
  
-   `Web`: Określa, czy szablon tworzy projekt sieci Web lub elementów. Jeśli `ProjectType` element zawiera tę wartość, język projektu lub elementu jest zdefiniowany w [projectsubtype — Element (szablony Visual Studio)](../extensibility/projectsubtype-element-visual-studio-templates.md).  
  
## <a name="remarks"></a>Uwagi  
 `ProjectType` jest elementem podrzędnym wymagane `TemplateData`.  
  
 Wartość `ProjectType` element określa lokalizację szablonu w **nowy projekt** lub **Dodaj nowy element** okno dialogowe. Na przykład szablon z `ProjectType` wartość `CSharp` jest wyświetlany w obszarze **Visual C#** w węźle **nowy projekt** okno dialogowe.  
  
 Podtyp szablonu można określić za pomocą [projectsubtype —](../extensibility/projectsubtype-element-visual-studio-templates.md) elementu.  
  
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
 [ProjectSubType, element (szablony Visual Studio)](../extensibility/projectsubtype-element-visual-studio-templates.md)