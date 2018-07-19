---
title: 'Porady: wyświetlanie listy elementów rozdzielanych przecinkami | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, separating items with semicolons
- MSBuild, formatting item collections
ms.assetid: 3cae844c-7c6d-4144-82dc-efad10ba458f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 10ff36702f4fba2ed5093e866ac57a099fbbc904
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2018
ms.locfileid: "39081813"
---
# <a name="how-to-display-an-item-list-separated-with-commas"></a>Porady: wyświetlanie listy elementów rozdzielanych przecinkami
Podczas pracy z elementu listy w [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]), czasami jest to przydatne do wyświetlania zawartości listy tych elementów w sposób, który jest łatwy do odczytania. Lub możesz mieć do zadań, która przyjmuje listę elementów oddzielonych specjalne separatora. W obu przypadkach można określić ciąg separatora listy elementów.  
  
## <a name="separate-items-in-a-list-with-commas"></a>Oddzielne elementy na liście przecinkami  
 Domyślnie [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] używa średników do oddzielania elementów listy. Na przykład, rozważmy `Message` element z następujących wartości:  
  
 `<Message Text="This is my list of TXT files: @(TXTFile)"/>`  
  
 Gdy `@(TXTFile)` listy elementów zawiera elementy *App1.txt*, *App2.txt*, i *App3.txt*, komunikat:  
  
 `This is my list of TXT files: App1.txt;App2.txt;App3.txt`  
  
 Jeśli chcesz zmienić domyślne zachowanie, możesz określić własne separatora. Składnia określająca element separatora listy jest następująca:  
  
 `@(ItemListName, '<separator>')`  
  
 Separator może być pojedynczy znak lub ciąg, a musi być ujęta w apostrofy.  
  
#### <a name="to-insert-a-comma-and-a-space-between-items"></a>Aby wstawić przecinek i spację między elementami  
  
-   Notacja elementu podobny do następującego:  
  
     `@(TXTFile, ', ')`  
  
## <a name="example"></a>Przykład  
 W tym przykładzie [Exec](../msbuild/exec-task.md) zadanie jest uruchamiane narzędzie findstr, aby znaleźć ciągów tekstowych określonej w pliku *Phrases.txt*. W poleceniu findstr literałów ciągów znaków są wskazywane przez **/c:** przełączyć, więc separator elementów `/c:` jest wstawiany między elementami w `@(Phrase)` listy elementów.  
  
 W tym przykładzie jest równoważne wiersza polecenia:  
  
 `findstr /i /c:hello /c:world /c:msbuild phrases.txt`  
  
```xml  
<Project DefaultTargets = "Find"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <ItemGroup>  
        <Phrase Include="hello"/>  
        <Phrase Include="world"/>  
        <Phrase Include="msbuild"/>  
    </ItemGroup>  
  
    <Target Name = "Find">  
        <!-- Find some strings in a file -->  
        <Exec Command="findstr /i /c:@(Phrase, ' /c:') phrases.txt"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Odwołanie do narzędzia MSBuild](../msbuild/msbuild-reference.md)   
 [Elementy](../msbuild/msbuild-items.md)