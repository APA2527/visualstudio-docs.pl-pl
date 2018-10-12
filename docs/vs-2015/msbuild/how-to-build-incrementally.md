---
title: 'Porady: kompilacja przyrostowa | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, incremental builds
- incremental builds
- MSBuild, building incrementally
ms.assetid: 8d82d7d8-a2f1-4df6-9d2f-80b9e0cb3ac3
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8fba24434b10a9606c800c1453d31d7d3b52b234
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49275057"
---
# <a name="how-to-build-incrementally"></a>Porady: kompilacja przyrostowa
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Podczas kompilowania dużych projektów, ważne jest, że poprzednio skompilowane składniki, które są nadal aktualne nie są odbudowany. Jeśli wszystkie elementy docelowe są tworzone za każdym razem, gdy, każda kompilacja potrwa długo. Aby włączyć kompilacje przyrostowe (kompilacji, w którym tylko te obiekty docelowe, które nie zostały skompilowane zanim lub który jest przeznaczony dla są nieaktualne, są ponownie skompilowany), [!INCLUDE[vstecmsbuildengine](../includes/vstecmsbuildengine-md.md)] ([!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]) można porównać ze znacznikami czasu plików wyjściowych znacznikami czasu plików wejściowych i określenia, czy pominąć, tworzenie lub częściowo odbudować obiektu docelowego. Jednakże musi być mapowanie jeden do jednego między dane wejściowe i wyjściowe. Można użyć transformacji umożliwiające obiekty docelowe zidentyfikować ten bezpośredniego mapowania. Aby uzyskać więcej informacji na temat przekształceń, zobacz [przekształca](../msbuild/msbuild-transforms.md).  
  
## <a name="specifying-inputs-and-outputs"></a>Określanie dane wejściowe i wyjściowe  
 Obiekt docelowy może kompilowana przyrostowo, jeśli dane wejściowe i wyjściowe są określone w pliku projektu.  
  
#### <a name="to-specify-inputs-and-outputs-for-a-target"></a>Aby określić dane wejściowe i wyjściowe dla elementu docelowego  
  
-   Użyj `Inputs` i `Outputs` atrybuty `Target` elementu. Na przykład:  
  
    ```  
    <Target Name="Build"  
        Inputs="@(CSFile)"  
        Outputs="hello.exe">  
    ```  
  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] można porównać ze znacznikami czasu plików wyjściowych znacznikami czasu plików wejściowych i określenia, czy pominąć, tworzenie lub częściowo odbudować obiektu docelowego. W poniższym przykładzie, jeśli dowolny plik w `@(CSFile)` listy elementów jest nowszy niż plik hello.exe [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] uruchomi element docelowy; w przeciwnym razie zostanie pominięte:  
  
```  
<Target Name="Build"   
    Inputs="@(CSFile)"   
    Outputs="hello.exe">  
  
    <Csc  
        Sources="@(CSFile)"   
        OutputAssembly="hello.exe"/>  
</Target>  
```  
  
 Jeśli dane wejściowe i wyjściowe są określone w elemencie docelowym, każdy dane wyjściowe można mapować tylko jeden zestaw danych wejściowych lub może być bez bezpośredniego mapowania między dane wejściowe i dane wyjściowe. W ciągu poprzednich [CSC — zadanie](../msbuild/csc-task.md), na przykład danych wyjściowych, hello.exe, nie można mapować do pojedynczej udziału — jest to uzależnione od wszystkich z nich.  
  
> [!NOTE]
>  Obiekt docelowy, w którym znajduje się bez bezpośredniego mapowania między wejściami i wyjściami zawsze Kompiluj częściej niż docelowy, w którym każdy dane wyjściowe można mapować tylko jeden zestaw danych wejściowych ponieważ [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] nie może określić, której dane wyjściowe, należy ponownie utworzyć Jeśli niektóre dane wejściowe zostały zmienione .  
  
 Zadania, w których można zidentyfikować bezpośrednie mapowanie między danych wyjściowych i wejściowych, takich jak [LC — zadanie](../msbuild/lc-task.md), są najbardziej odpowiednie dla kompilacje przyrostowe, w przeciwieństwie do zadań, takich jak `Csc` i [Vbc](../msbuild/vbc-task.md), które produktu jeden wyjściowy zestawu z danych wejściowych.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto projektu, który tworzy plików pomocy dla hipotetycznego system pomocy. Projekt polega na konwertowaniu pliki txt źródła w .content pośrednie pliki, które następnie są łączone z plikami metadane XML, aby wygenerować plik .help końcowe używane przez system pomocy. Projekt używa hipotetyczny następujące zadania:  
  
-   `GenerateContentFiles`: Konwertuje pliki txt .content plików.  
  
-   `BuildHelp`: Łączy .content pliki i pliki metadanych XML do tworzenia pliku .help końcowej.  
  
 Projekt używa przekształceń w celu utworzenia mapowanie jeden do jednego między dane wejściowe i dane wyjściowe w `GenerateContentFiles` zadania. Aby uzyskać więcej informacji, zobacz [przekształca](../msbuild/msbuild-transforms.md). Ponadto `Output` element jest ustawiony na wartość automatycznie korzystają z danych wyjściowych z `GenerateContentFiles` zadanie jako dane wejściowe dla `BuildHelp` zadania.  
  
 Ten plik projektu zawiera zarówno `Convert` i `Build` elementów docelowych. `GenerateContentFiles` i `BuildHelp` zadania są umieszczane w `Convert` i `Build` jest przeznaczony dla odpowiednio, tak aby w każdym obiekcie docelowym może być kompilowana przyrostowo. Za pomocą `Output` element, dane wyjściowe `GenerateContentFiles` zadania są umieszczane w `ContentFile` listy elementów, gdzie mogą być używane jako dane wejściowe dla `BuildHelp` zadania. Za pomocą `Output` element w ten sposób automatycznie udostępnia dane wyjściowe z jednego zadania jako dane wejściowe dla innego zadania tak, aby nie miały wyświetlić listę pojedynczych elementów lub elementów listy ręcznie w każdym zadaniu.  
  
> [!NOTE]
>  Mimo że `GenerateContentFiles` docelowych można kompilować przyrostowo, zawsze wszystkie dane wyjściowe, z których obiektem docelowym są wymagane jako dane wejściowe dla `BuildHelp` docelowej. [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] automatycznie zapewnia wszystkie dane wyjściowe z jeden element docelowy jako dane wejściowe dla innego elementu docelowego gdy używasz `Output` elementu.  
  
```  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <ItemGroup>  
        <TXTFile Include="*.txt"/>  
        <XMLFile Include="\metadata\*.xml"/>  
    </ItemGroup>  
  
    <Target Name = "Convert"  
        Inputs="@(TXTFile)"  
        Outputs="@(TXTFile->'%(Filename).content')">  
  
        <GenerateContentFiles  
            Sources = "@(TXTFile)">  
            <Output TaskParameter = "OutputContentFiles"  
                ItemName = "ContentFiles"/>  
        </GenerateContentFiles>  
    </Target>  
  
    <Target Name = "Build" DependsOnTargets = "Convert"  
        Inputs="@(ContentFiles);@(XMLFiles)"  
        Outputs="$(MSBuildProjectName).help">  
  
        <BuildHelp  
            ContentFiles = "@(ContentFiles)"  
            MetadataFiles = "@(XMLFile)"  
            OutputFileName = "$(MSBuildProjectName).help"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Obiekty docelowe](../msbuild/msbuild-targets.md)   
 [TARGET — Element (MSBuild)](../msbuild/target-element-msbuild.md)   
 [Przekształcenia](../msbuild/msbuild-transforms.md)   
 [CSC — zadanie](../msbuild/csc-task.md)   
 [Vbc, zadanie](../msbuild/vbc-task.md)



