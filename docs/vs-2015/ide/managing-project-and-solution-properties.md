---
title: Zarządzanie właściwościami projektów i rozwiązań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d727efc0-1096-4ede-84b6-31a65da22ac0
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 43b46fc40da93352c4748662b66df91f0d25802b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49290553"
---
# <a name="managing-project-and-solution-properties"></a>Zarządzanie właściwościami projektów i rozwiązań
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Projekty mają właściwości, które zarządzają wiele aspektów kompilacji, debugowanie, testowanie i wdrażanie. Niektóre właściwości są wspólne dla wszystkich typów projektów, a niektóre są unikatowe dla określonych języków lub platform. Masz dostępu do właściwości projektu, kliknij prawym przyciskiem myszy węzeł projektu w Eksploratorze rozwiązań i wybierając pozycję właściwości lub wpisując właściwości w **szybkiego uruchamiania** pola wyszukiwania na pasku menu.  
  
 ![Menu kontekstowego projektu](../ide/media/vs2015-proj-prop-menu.gif "vs2015_proj_prop_menu")  
  
 Projekty .NET także mieć węzeł właściwości w drzewie projektu, sam.  
  
 ![Właściwości węzła w drzewie Eksploratora rozwiązań](../ide/media/vs2015-props-se.png "VS2015_Props_SE")  
  
> [!TIP]
>  Rozwiązania mają kilka właściwości, a więc elementy; projektu te właściwości są dostępne w [okno właściwości](../ide/reference/properties-window.md), a nie **projektanta projektu**.  
  
## <a name="project-properties"></a>Właściwości projektu  
 Właściwości projektu są zorganizowane w grupy każda grupa ma swoją własną stronę właściwości i strony mogą być różne dla różnych języków i typów projektów.  
  
### <a name="c-and-visual-basic-projects"></a>Projekty języka C# i Visual Basic  
 W projektach C# i Visual Basic, właściwości są widoczne w **projektanta projektu**. Poniższa ilustracja przedstawia na stronie właściwości kompilacji dla projektu WPF w języku C#:  
  
 ![Projektant projektu programu Visual Studio](../ide/media/vs2015-proppage-build.png "VS2015_PropPage_Build")  
  
 Aby uzyskać informacje o poszczególnych stron właściwości w Projektancie projektu, zobacz [odwołanie do właściwości projektu](../ide/reference/project-properties-reference.md).  
  
### <a name="c-and-javascript-projects"></a>Projekty języka C++ i JavaScript  
 Projekty języka C++ i JavaScript mają inny użytkownik za pomocą interfejsu zarządzania właściwości projektu. Ta ilustracja przedstawia strony właściwości projektu C++ (strony w języku JavaScript są podobne):  
  
 ![Program Visual C&#43; &#43; właściwości projektu](../ide/media/vs2015-projprops-cpp.png "VS2015_ProjProps_cpp")  
  
 Aby uzyskać informacji na temat właściwości projektu C++, zobacz [Praca z właściwościami projektu](http://msdn.microsoft.com/library/9b0d6f8b-7d4e-4e61-aa75-7d14944816cd). Aby uzyskać więcej informacji na temat właściwości kodu JavaScript, zobacz [strony właściwości, JavaScript](../ide/reference/property-pages-javascript.md).  
  
## <a name="solution-properties"></a>Właściwości rozwiązania  
 Aby uzyskać dostęp do właściwości rozwiązania, kliknij prawym przyciskiem myszy węzeł rozwiązania w **Eksploratora rozwiązań** i wybierz polecenie **właściwości**. W oknie dialogowym możesz ustawić konfiguracje projektu do debugowania lub wydania kompilacji, wybierz, które projekty (s) powinna być projekt startowy, po naciśnięciu klawisza F5 i ustaw opcje analizy kodu.  
  
## <a name="see-also"></a>Zobacz też  
 [Rozwiązania i projekty w programie Visual Studio](../ide/solutions-and-projects-in-visual-studio.md)



