---
title: Odwołanie do schematu pliku projektu MSBuild | Dokumentacja firmy Microsoft
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
- MSBuild, file schema
ms.assetid: d9a68146-1f43-4621-ac78-2c8c3f400936
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2794c88ad3a0d14705d536aa26142745d0fc0597
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2018
ms.locfileid: "31571965"
---
# <a name="msbuild-project-file-schema-reference"></a>Odwołanie do schematu pliku projektu MSBuild
Zawiera spis wszystkich [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] elementów schematu XML z dostępne atrybuty i elementy podrzędne.  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] używa plików projektu aby nakazać co aparatu kompilacji do kompilacji i sposobie jego tworzenia. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] pliki projektu będą stosować się do plików XML [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] schematu XML. W tej sekcji omówiono plik definicji (XSD) schematu XML dla [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].  
  
## <a name="msbuild-xml-schema-elements"></a>Elementy schematu XML programu MSBuild  
 W poniższej tabeli wymieniono wszystkie [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] elementów schematu XML wraz z ich elementów podrzędnych i atrybutów.  
  
|Element|Elementy podrzędne|Atrybuty|  
|-------------|--------------------|----------------|  
|[Choose, element (MSBuild)](../msbuild/choose-element-msbuild.md)|w przeciwnym razie<br /><br /> Kiedy|--|  
|[Import, element (MSBuild)](../msbuild/import-element-msbuild.md)|--|Warunek<br /><br /> Projekt|  
|[ImportGroup, element](../msbuild/importgroup-element.md)|{1&gt;Importuj&lt;1}|Warunek|  
|[Item, element (MSBuild)](../msbuild/item-element-msbuild.md)|*ItemMetaData*|Warunek<br /><br /> Wyklucz<br /><br /> Uwzględnij<br /><br /> Usuń|  
|[ItemDefinitionGroup, element (MSBuild)](../msbuild/itemdefinitiongroup-element-msbuild.md)|*Element*|Warunek|  
|[ItemGroup, element (MSBuild)](../msbuild/itemgroup-element-msbuild.md)|*Element*|Warunek|  
|[ItemMetadata, element (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)|*Element*|Warunek|  
|[OnError, element (MSBuild)](../msbuild/onerror-element-msbuild.md)|--|Warunek<br /><br /> ExecuteTargets|  
|[Otherwise, element (MSBuild)](../msbuild/otherwise-element-msbuild.md)|Wybierz<br /><br /> ItemGroup<br /><br /> PropertyGroup|--|  
|[Output, element (MSBuild)](../msbuild/output-element-msbuild.md)|--|Warunek<br /><br /> Nazwa elementu<br /><br /> PropertyName<br /><br /> TaskParameter|  
|[Parameter, element](../msbuild/parameter-element.md)|--|Dane wyjściowe<br /><br /> ParameterType<br /><br /> Wymagane|  
|[ParameterGroup, element](../msbuild/parametergroup-element.md)|*Parametr*|--|  
|[Project, element (MSBuild)](../msbuild/project-element-msbuild.md)|Wybierz<br /><br /> {1&gt;Importuj&lt;1}<br /><br /> ItemGroup<br /><br /> ProjectExtensions<br /><br /> PropertyGroup<br /><br /> docelowy<br /><br /> UsingTask|Defaulttargets —<br /><br /> InitialTargets<br /><br /> ToolsVersion<br /><br /> TreatAsLocalProperty<br /><br /> xmlns|  
|[ProjectExtensions, element (MSBuild)](../msbuild/projectextensions-element-msbuild.md)|--|--|  
|[Property, element (MSBuild)](../msbuild/property-element-msbuild.md)|--|Warunek|  
|[PropertyGroup, element (MSBuild)](../msbuild/propertygroup-element-msbuild.md)|*Właściwość*|Warunek|  
|[Sdk, element (MSBuild)](../msbuild/sdk-element-msbuild.md)|--|Nazwa<br /><br /> Wersja|  
|[Target, element (MSBuild)](../msbuild/target-element-msbuild.md)|OnError —<br /><br /> *Zadanie*|AfterTargets<br /><br /> BeforeTargets<br /><br /> Warunek<br /><br /> DependsOnTargets<br /><br /> Dane wejściowe<br /><br /> KeepDuplicateOutputs<br /><br /> Nazwa<br /><br /> Dane wyjściowe<br /><br /> Zwraca|  
|[Task, element (MSBuild)](../msbuild/task-element-msbuild.md)|Dane wyjściowe|Warunek<br /><br /> ContinueOnError<br /><br /> *Parametr*|  
|[TaskBody, element (MSBuild)](../msbuild/taskbody-element-msbuild.md)|*Dane*|Ocena|  
|[UsingTask, element (MSBuild)](../msbuild/usingtask-element-msbuild.md)|ParameterGroup<br /><br /> Taskbody —|AssemblyFile<br /><br /> AssemblyName<br /><br /> Warunek<br /><br /> Fabryka zadań<br /><br /> TaskName|  
|[When, element (MSBuild)](../msbuild/when-element-msbuild.md)|Wybierz<br /><br /> ItemGroup<br /><br /> PropertyGroup|Warunek|  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)   
 [Warunki](../msbuild/msbuild-conditions.md)   
 [Odwołanie do narzędzia MSBuild](../msbuild/msbuild-reference.md)  
 [MSBuild](../msbuild/msbuild.md)
