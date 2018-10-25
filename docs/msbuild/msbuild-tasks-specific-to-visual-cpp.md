---
title: Program MSBuild zadania właściwe dla Visual C++ | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 06/27/2018
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, tasks specific to Visual C++
ms.assetid: 05410f0c-7356-4692-bc00-20664421c9ff
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 2caacec2412ea0c188d9b987ae8a6e52a89fbe9b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49906757"
---
# <a name="msbuild-tasks-specific-to-visual-c"></a>Zadania programu MSBuild specyficzne dla języka Visual C++
Zadania zapewniają kod, który jest uruchamiany w procesie kompilacji. Po zainstalowaniu programu Visual C++, następujące zadania są dostępne, oprócz tych, które są instalowane z [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Aby uzyskać więcej informacji, zobacz [Przegląd MSBuild (Visual C++)](/cpp/build/msbuild-visual-cpp-overview).  

 Oprócz parametrów dla każdego zadania każde zadanie ma następujące parametry.  


| Parametr | Opis |
|-------------------| - |
| `Condition` | Opcjonalnie `String` parametru.<br /><br /> A `Boolean` wyrażenia, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] aparat używa do określenia, czy to zadanie zostanie wykonany. Aby uzyskać informacje o warunkach, które są obsługiwane przez [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], zobacz [warunki](../msbuild/msbuild-conditions.md). |
| `ContinueOnError` | Parametr opcjonalny. Może zawierać jedną z następujących wartości:<br /><br /> -   **WarnAndContinue** lub **true**. Jeśli zadanie nie powiedzie się, kolejne zadania w [docelowej](../msbuild/target-element-msbuild.md) elementu i kompilacja będą wykonywane, a wszystkie błędy z zadania są traktowane jako ostrzeżenia<br />-   **ErrorAndContinue**. Jeśli zadanie nie powiedzie się, kolejne zadania w `Target` elementu i kompilacja będą wykonywane, a wszystkie błędy z zadania są traktowane jako błędy.<br />-   **ErrorAndStop** lub **false** (ustawienie domyślne). Jeśli zadanie nie powiedzie się, kolejnych zadań na`Target` elementu i kompilacja nie są wykonywane i całą `Target` elementu i kompilacja są traktowane jako zakończone niepowodzeniem.<br /><br /> Wersje programu .NET Framework przed 4.5 obsługiwane tylko `true` i `false` wartości.<br /><br /> Aby uzyskać więcej informacji, zobacz [porady: ignorowanie błędów w zadaniach](../msbuild/how-to-ignore-errors-in-tasks.md). |

### <a name="related-topics"></a>Tematy pokrewne  

|Tytuł|Opis|  
|-----------|-----------------|  
|[Bscmake — zadanie](../msbuild/bscmake-task.md)|Opakowuje Microsoft Przeglądaj informacje narzędzie konserwacji (*bscmake.exe*).|  
|[Cl — zadanie](../msbuild/cl-task.md)|Opakowuje narzędzia kompilatora Visual C++ (*cl.exe*).|  
|[Cppclean — zadanie](../msbuild/cppclean-task.md)|Usuwa pliki tymczasowe, utworzone przez program MSBuild podczas kompilowania projektu Visual C++.|  
|[Lib — zadanie](../msbuild/lib-task.md)|Opakowuje narzędzie Microsoft 32-bitowy Library Manager (*lib.exe*).|  
|[Link — zadanie](../msbuild/link-task.md)|Opakowuje narzędzia konsolidatora Visual C++ (*link.exe*).|  
|[MIDL — zadanie](../msbuild/midl-task.md)|Opakowuje narzędzie kompilatora języka definicji interfejsu Microsoft (MIDL) (*midl.exe*).|  
|[MT — zadanie](../msbuild/mt-task.md)|Opakowuje narzędziu manifestu firmy Microsoft (*mt.exe*).|  
|[RC — zadanie](../msbuild/rc-task.md)|Opakowuje narzędzie kompilatora zasobów systemu Microsoft Windows (*rc.exe*).|  
|[SETENV — zadanie](../msbuild/setenv-task.md)|Ustawia lub usuwa wartość określonej zmiennej środowiskowej.|  
|[Vcmessage — zadanie](../msbuild/vcmessage-task.md)|Dzienniki ostrzeżenie wiadomości i komunikaty o błędach podczas kompilacji. (Nie rozszerzalne. Wyłącznie do użytku wewnętrznego.)|  
|[Xdcmake — zadanie](../msbuild/xdcmake-task.md)|Opakowuje narzędzie dokumentacji XML (*xdcmake.exe*), który scala komentarza dokumentu XML (*.xdc*) pliki do *.xml* pliku.|  
|[XSD — zadanie](../msbuild/xsd-task.md)|Opakowuje narzędzie definicji schematu XML (*xsd.exe*), które generuje pliki schematu lub klasa ze źródła. *Zobacz uwagi poniżej.*|  
|[Odwołanie do narzędzia MSBuild](../msbuild/msbuild-reference.md)|Opisano elementy systemu MSBuild.|  
|[Zadania](../msbuild/msbuild-tasks.md)|W tym artykule opisano zadania, które są jednostkami kod, który można łączyć, aby utworzyć kompilację.|  
|[Wpisywanie zadania](../msbuild/task-writing.md)|W tym artykule opisano sposób tworzenia zadania.|

> [!NOTE]
> Projekt w programie Visual Studio 2017, obsługa C++ *xsd.exe* jest przestarzała. Można nadal używać **Microsoft.VisualC.CppCodeProvider** interfejsów API, ręcznie dodając *CppCodeProvider.dll* w pamięci GAC.