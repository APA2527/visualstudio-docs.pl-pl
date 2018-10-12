---
title: Projectextensions — Element (MSBuild) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ProjectExtensions
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <ProjectExtensions> element [MSBuild]
- ProjectExtensions element [MSBuild]
ms.assetid: f95f312f-ff92-41eb-9469-ad99e236a307
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 41b3ed5fc742f95cde3c834e5d8612daafef5d6d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49189114"
---
# <a name="projectextensions-element-msbuild"></a>ProjectExtensions — Element (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Umożliwia [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] pliki, aby zawierała non - projektu[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] informacji. Wszystko wewnątrz elementu `ProjectExtensions` element zostanie zignorowana przez [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)].  
  
 \<Project>  
 \<Projectextensions — >  
  
## <a name="syntax"></a>Składnia  
  
```  
<ProjectExtensions>  
    Non-MSBuild information to include in file.  
</ProjectExtensions>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
 Brak  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Element główny wymagany [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] pliku projektu.|  
  
## <a name="remarks"></a>Uwagi  
 Tylko jeden `ProjectExtensions` element może być używany w [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] projektu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu pokazuje informacje z zintegrowanego środowiska programistycznego znajdujących się w `ProjectExtensions` elementu.  
  
```  
<ProjectExtensions>  
    <VSIDE>  
        <External>  
            <!--  
            Raw XML passed to the IDE by an external source  
            -->  
        </External>  
    </VSIDE>  
</ProjectExtensions>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do schematu pliku projektu](../msbuild/msbuild-project-file-schema-reference.md)  
 [MSBuild](msbuild.md)


