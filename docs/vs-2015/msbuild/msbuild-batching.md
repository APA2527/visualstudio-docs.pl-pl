---
title: Przetwarzanie wsadowe MSBuild | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, batching
ms.assetid: d35c085b-27b8-49d7-b6f8-8f2f3a0eec38
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d868beddd498b112fa2f5a4de52f473c8ba3041
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682197"
---
# <a name="msbuild-batching"></a>Przetwarzanie wsadowe w programie MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [MSBuild dzielenia na partie](https://docs.microsoft.com/visualstudio/msbuild/msbuild-batching).  
  
  
[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] ma możliwość podzielić listy elementów na różnych kategorii lub serii, na podstawie metadanych elementu i uruchom docelowego lub zadanie jeden raz z każdej partii.  
  
## <a name="task-batching"></a>Przetwarzanie wsadowe zadań  
 Przetwarzanie wsadowe zadań umożliwia uproszczenie plików projektu, umożliwiając podzielić listy elementów na różnych partii i przekazanie każdego wskaźnika tych partii w zadanie oddzielnie. Oznacza to, że plik projektu tylko trzeba zadania i jego atrybutów zadeklarowany raz, nawet kilka razy może zostać uruchomione.  
  
 Określ, czy program [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] do wykonywania przetwarzania wsadowego za pomocą zadania przy użyciu %(*ItemMetaDataName*) Notacja w jeden z atrybutów zadania. Poniższy przykład dzieli `Example` na podstawie listy elementów w partie `Color` wartość metadanych elementu i przekazuje partii do `MyTask` zadań oddzielnie.  
  
> [!NOTE]
>  Jeśli użytkownik nie odwołują się do listy elementów w innym miejscu w atrybutach zadania lub nazwa metadanych może być niejednoznaczna, możesz użyć %(*ItemCollection.ItemMetaDataName*) Notacja do pełnej kwalifikacji wartość elementu metadanych na potrzeby przetwarzania wsadowego.  
  
```  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 Aby uzyskać bardziej szczegółowe przykłady przetwarzania wsadowego, zobacz [metadane elementu w przetwarzaniu wsadowym zadań](../msbuild/item-metadata-in-task-batching.md).  
  
## <a name="target-batching"></a>Przetwarzaniu wsadowym obiektów docelowych  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] sprawdza, jeśli dane wejściowe i wyjściowe, obiektu docelowego są aktualne przed uruchomieniem element docelowy. Jeśli zarówno dane wejściowe i wyjściowe są aktualne, element docelowy jest pomijany. Jeśli zadanie w celu korzysta z dzielenia na partie, [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] potrzebuje do ustalenia, czy dane wejściowe i wyjściowe dla każdego zestawu elementów jest aktualny. W przeciwnym razie element docelowy jest wykonywane za każdym razem, gdy jego osiągnięciu.  
  
 W poniższym przykładzie przedstawiono `Target` element, który zawiera `Outputs` atrybutem %(*ItemMetaDataName*) notacji. [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] Dzieli `Example` na podstawie listy elementów w partie `Color` elementu metadanych i analizowanie znacznikami czasu plików wyjściowych dla każdej partii. Jeśli dane wyjściowe z usługi batch nie są aktualne, element docelowy zostanie uruchomiony. W przeciwnym razie element docelowy jest pomijany.  
  
```  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask"  
        Inputs="@(Example)"  
        Outputs="%(Color)\MyFile.txt">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 Aby uzyskać inny przykład przetwarzaniu wsadowym obiektów docelowych, zobacz [metadane elementu w przetwarzaniu wsadowym obiektów docelowych](../msbuild/item-metadata-in-target-batching.md).  
  
## <a name="property-functions-using-metadata"></a>Funkcje właściwości przy użyciu metadanych  
 Przetwarzanie wsadowe mogą być kontrolowane przez funkcje właściwości, które zawierają metadane. Na przykład  
  
 `$([System.IO.Path]::Combine($(RootPath),%(Compile.Identity)))`  
  
 używa <xref:System.IO.Path.Combine%2A> połączyć ścieżka do folderu głównego, przy użyciu ścieżki elementu kompilacji.  
  
 Funkcje właściwości nie może występować w wartości metadanych.  Na przykład  
  
 `%(Compile.FullPath.Substring(0,3))`  
  
 nie jest dozwolone.  
  
 Aby uzyskać więcej informacji na temat funkcji właściwości, zobacz [funkcji właściwości](../msbuild/property-functions.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Itemmetadata — Element (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)   
 [Pojęcia dotyczące programu MSBuild](../msbuild/msbuild-concepts.md)   
 [Odwołanie do narzędzia MSBuild](../msbuild/msbuild-reference.md)   
 [Pojęcia zaawansowane](../msbuild/msbuild-advanced-concepts.md)



