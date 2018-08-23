---
title: Odwołanie do schematu pliku projektu MSBuild | Dokumentacja firmy Microsoft
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
- MSBuild, file schema
ms.assetid: d9a68146-1f43-4621-ac78-2c8c3f400936
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 134a66a38886201a9f53ed5d15dda009b095d72f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632373"
---
# <a name="msbuild-project-file-schema-reference"></a>Odwołanie do schematu pliku projektu MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [odwołanie do schematu pliku projektu MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference).  
  
  
Zawiera spis wszystkich [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] elementów schematu XML z ich dostępne atrybuty i elementy podrzędne.  
  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] używa plików projektu, aby nakazać aparat kompilacji, co do kompilacji i jak ją skompilować. [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] pliki projektu są plikami XML, które będą zgodne [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] schematu XML. W tej sekcji omówiono plik (XSD) definicji schematu XML dla [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)].  
  
## <a name="msbuild-xml-schema-elements"></a>Elementy schematu MSBuild XML  
 Poniższa tabela zawiera listę wszystkich [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] elementy schematu XML wraz z ich elementów podrzędnych i atrybutów.  
  
|Element|Elementy podrzędne|Atrybuty|  
|-------------|--------------------|----------------|  
|[Choose, element (MSBuild)](../msbuild/choose-element-msbuild.md)|W przeciwnym razie<br /><br /> Kiedy|--|  
|[Import, element (MSBuild)](../msbuild/import-element-msbuild.md)|--|Warunek<br /><br /> Projekt|  
|[ImportGroup, element](../msbuild/importgroup-element.md)|{1&gt;Importuj&lt;1}|Warunek|  
|[Item, element (MSBuild)](../msbuild/item-element-msbuild.md)|*ItemMetaData*|Warunek<br /><br /> Wyklucz<br /><br /> Uwzględnij<br /><br /> Usuń|  
|[ItemDefinitionGroup, element (MSBuild)](../msbuild/itemdefinitiongroup-element-msbuild.md)|*Element*|Warunek|  
|[ItemGroup, element (MSBuild)](../msbuild/itemgroup-element-msbuild.md)|*Element*|Warunek|  
|[ItemMetadata, element (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)|*Element*|Warunek|  
|[OnError, element (MSBuild)](../msbuild/onerror-element-msbuild.md)|--|Warunek<br /><br /> ExecuteTargets|  
|[Otherwise, element (MSBuild)](../msbuild/otherwise-element-msbuild.md)|Wybierz<br /><br /> ItemGroup<br /><br /> PropertyGroup|--|  
|[Output, element (MSBuild)](../msbuild/output-element-msbuild.md)|--|Warunek<br /><br /> Nazwa elementu<br /><br /> PropertyName<br /><br /> TaskParameter|  
|[Parameter, element](../msbuild/parameter-element.md)|--|Dane wyjściowe<br /><br /> Zgodność<br /><br /> Wymagane|  
|[ParameterGroup, element](../msbuild/parametergroup-element.md)|*Parametr*|--|  
|[Project, element (MSBuild)](../msbuild/project-element-msbuild.md)|Wybierz<br /><br /> {1&gt;Importuj&lt;1}<br /><br /> ItemGroup<br /><br /> Projectextensions —<br /><br /> PropertyGroup<br /><br /> Docelowy<br /><br /> UsingTask|Defaulttargets —<br /><br /> InitialTargets<br /><br /> ToolsVersion<br /><br /> TreatAsLocalProperty<br /><br /> xmlns|  
|[ProjectExtensions, element (MSBuild)](../msbuild/projectextensions-element-msbuild.md)|--|--|  
|[Property, element (MSBuild)](../msbuild/property-element-msbuild.md)|--|Warunek|  
|[PropertyGroup, element (MSBuild)](../msbuild/propertygroup-element-msbuild.md)|*Property*|Warunek|  
|[Target, element (MSBuild)](../msbuild/target-element-msbuild.md)|OnError<br /><br /> *Zadanie*|AfterTargets<br /><br /> BeforeTargets<br /><br /> Warunek<br /><br /> DependsOnTargets<br /><br /> Dane wejściowe<br /><br /> KeepDuplicateOutputs<br /><br /> Nazwa<br /><br /> Dane wyjściowe<br /><br /> Zwraca|  
|[Task, element (MSBuild)](../msbuild/task-element-msbuild.md)|Dane wyjściowe|Warunek<br /><br /> ContinueOnError<br /><br /> *Parametr*|  
|[TaskBody, element (MSBuild)](../msbuild/taskbody-element-msbuild.md)|*Dane*|Oceń|  
|[UsingTask, element (MSBuild)](../msbuild/usingtask-element-msbuild.md)|ParameterGroup<br /><br /> Taskbody —|AssemblyFile<br /><br /> AssemblyName<br /><br /> Warunek<br /><br /> TaskFactory<br /><br /> TaskName|  
|[When, element (MSBuild)](../msbuild/when-element-msbuild.md)|Wybierz<br /><br /> ItemGroup<br /><br /> PropertyGroup|Warunek|  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)   
 [Warunki](../msbuild/msbuild-conditions.md)   
 [Odwołanie do narzędzia MSBuild](../msbuild/msbuild-reference.md)  
 [MSBuild](msbuild.md)


