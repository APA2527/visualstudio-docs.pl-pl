---
title: Project — Element (MSBuild) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Project
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ToolsVersion attribute [MSBuild]
- <Project> element [MSBuild]
- Project element [MSBuild]
ms.assetid: d1cda56a-dbef-4109-9201-39e962e3f653
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4191ed9d34c48ab0aefd1198dd868a91c19ffabc
ms.sourcegitcommit: 71218ffc33da325cc1b886f69ff2ca50d44f5f33
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2018
ms.locfileid: "48879996"
---
# <a name="project-element-msbuild"></a>Project — element (MSBuild)
Element główny wymagany [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] pliku projektu.  

## <a name="syntax"></a>Składnia  

```xml  
<Project InitialTargets="TargetA;TargetB"  
         DefaultTargets="TargetC;TargetD"  
         TreatAsLocalProperty="PropertyA;PropertyB"  
         ToolsVersion=<version number>
         Sdk="name[/version]"
         xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Sdk... />
    <Choose>... </Choose>  
    <PropertyGroup>... </PropertyGroup>  
    <ItemGroup>... </ItemGroup>  
    <Target>... </Target>  
    <UsingTask.../>  
    <ProjectExtensions>... </ProjectExtensions>  
    <Import... />  
</Project>  
```  

## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  

### <a name="attributes"></a>Atrybuty  

|Atrybut|Opis|  
|---------------|-----------------|  
|`DefaultTargets`|Atrybut opcjonalny.<br /><br /> Domyślny element docelowy lub cele, które mają być punktem wejścia kompilacji, jeśli żadne miejsce docelowe nie zostało określone. Wiele elementów docelowych są rozdzielonych średnikami (;) rozdzielonych.<br /><br /> Jeśli określono nie domyślnego obiektu docelowego w jednym `DefaultTargets` atrybutu lub [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] wiersza polecenia, aparat wykonuje pierwszego obiektu docelowego w pliku projektu po [importu](../msbuild/import-element-msbuild.md) elementy zostały ocenione.|  
|`InitialTargets`|Atrybut opcjonalny.<br /><br /> Początkowa docelowego lub obiekty docelowe do uruchomienia przed obiektów docelowych określonych w `DefaultTargets` atrybutu lub w wierszu polecenia. Wiele elementów docelowych są rozdzielonych średnikami (;) rozdzielonych.|  
|`Sdk`|Atrybut opcjonalny. <br /><br /> Nazwa zestawu SDK i opcjonalnie wersja służące do tworzenia niejawne zaimportuj instrukcje, które są dodawane do pliku .proj. Jeśli wersja nie jest określona, program MSBuild będzie podejmować próby rozwiązania domyślnej wersji.  Na przykład `<Project Sdk="Microsoft.NET.Sdk" />` lub `<Project Sdk="My.Custom.Sdk/1.0.0" />`.|  
|`ToolsVersion`|Atrybut opcjonalny.<br /><br /> Można określić wartości dla $(MSBuildBinPath) i $(MSBuildToolsPath) korzysta z wersji programu MSBuild zestawu narzędzi.|  
|`TreatAsLocalProperty`|Atrybut opcjonalny.<br /><br /> Nazwy właściwości, które nie były uznawane za będzie globalnym. Ten atrybut zapobiega zastępowanie wartości właściwości, które są ustawione w pliku projektu lub miejsc docelowych i wszystkie Importy kolejnych określonych właściwości wiersza polecenia. Wiele właściwości są rozdzielonych średnikami (;) rozdzielonych.<br /><br /> Zwykle globalne właściwości zastępują wartości właściwości, które są ustawione w pliku projektu lub miejsc docelowych. Jeśli właściwość jest wymieniona w `TreatAsLocalProperty` wartość, wartość właściwości globalnej nie zastępuje wartości właściwości, które są ustawiane w pliku i wszystkie Importy kolejne. Aby uzyskać więcej informacji, zobacz [porady: kompilacja tych samych plików źródłowych przy użyciu różnych opcji](../msbuild/how-to-build-the-same-source-files-with-different-options.md). **Uwaga:** ustawić globalne właściwości w wierszu polecenia, używając **— właściwość** (lub **-p**) przełącznika. Możesz również ustawić lub zmodyfikować globalnych właściwości dla projektów podrzędnych w kompilacji wielu projektów za pomocą `Properties` atrybut zadanie programu MSBuild. Aby uzyskać więcej informacji, zobacz [zadanie MSBuild](../msbuild/msbuild-task.md).|  
|`Xmlns`|Atrybut opcjonalny.<br /><br /> Jeśli zostanie określony, `xmlns` atrybut musi mieć wartość `http://schemas.microsoft.com/developer/msbuild/2003`.|  

### <a name="child-elements"></a>Elementy podrzędne  

|Element|Opis|  
|-------------|-----------------|  
|[Wybierz opcję](../msbuild/choose-element-msbuild.md)|Element opcjonalny.<br /><br /> Ocenia elementy podrzędne, aby wybrać jeden zestaw `ItemGroup` elementy i/lub `PropertyGroup` elementy do oceny.|  
|[Importujuj](../msbuild/import-element-msbuild.md)|Element opcjonalny.<br /><br /> Umożliwia pliku projektu zaimportować innego pliku projektu. Może wynosić zero lub więcej `Import` elementy w projekcie.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|Element opcjonalny.<br /><br /> Element grouping dla poszczególnych elementów. Elementy określone za pomocą [elementu](../msbuild/item-element-msbuild.md) elementu. Może wynosić zero lub więcej `ItemGroup` elementy w projekcie.|  
|[ProjectExtensions](../msbuild/projectextensions-element-msbuild.md)|Element opcjonalny.<br /><br /> Zapewnia sposób, aby utrwalić non -[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] informacje zawarte w [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] pliku projektu. Może mieć zero lub jeden `ProjectExtensions` elementy w projekcie.|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|Element opcjonalny.<br /><br /> Element grouping dla poszczególnych właściwości. Właściwości są określane za pomocą [właściwość](../msbuild/property-element-msbuild.md) elementu. Może wynosić zero lub więcej `PropertyGroup` elementy w projekcie.|
|[Sdk](../msbuild/sdk-element-msbuild.md)|Element opcjonalny.<br /><br /> Odwołania [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekt zestawu SDK.  Ten element może służyć jako alternatywę do atrybutu zestawu Sdk.|  
|[Docelowy](../msbuild/target-element-msbuild.md)|Element opcjonalny.<br /><br /> Zawiera zestaw zadań dla [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] do wykonania po kolei. Zadania są określone za pomocą [zadań](../msbuild/task-element-msbuild.md) elementu. Może wynosić zero lub więcej `Target` elementy w projekcie.|  
|[UsingTask](../msbuild/usingtask-element-msbuild.md)|Element opcjonalny.<br /><br /> Zapewnia sposób zarejestrować zadań w [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Może wynosić zero lub więcej `UsingTask` elementy w projekcie.|  

### <a name="parent-elements"></a>Elementy nadrzędne  
 Brak.  

## <a name="see-also"></a>Zobacz także  
 [Porady: Określ, która docelowa do tworzenia najpierw](../msbuild/how-to-specify-which-target-to-build-first.md)   
 [Informacje dotyczące wiersza polecenia](../msbuild/msbuild-command-line-reference.md)   
 [Odwołanie do schematu pliku projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [MSBuild](../msbuild/msbuild.md)
