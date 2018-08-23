---
title: Registerassembly — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#RegisterAssembly
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, RegisterAssembly task
- RegisterAssembly task [MSBuild]
ms.assetid: ba5f19ac-6764-4d28-9b79-a86de58f8987
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b5bbca089b15979df11c4eda73a46c6a6436b53d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685618"
---
# <a name="registerassembly-task"></a>RegisterAssembly — Zadanie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [registerassembly — zadanie](https://docs.microsoft.com/visualstudio/msbuild/registerassembly-task).  
  
  
Odczytuje metadane w określonym zestawie i dodaje niezbędne wpisy do rejestru, co umożliwia klientom COM utworzyć [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] klasy w sposób niewidoczny dla użytkownika. Zachowanie to zadanie jest podobne, ale nie są identyczne, z [Regasm.exe (narzędzie rejestracji zestawów)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb).  
  
## <a name="parameters"></a>Parametry  
 W poniższej tabeli opisano parametry `RegisterAssembly` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`Assemblies`|Wymagany parametr interfejsu <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Określa zestawy, które mają być zarejestrowane przy użyciu modelu COM.|  
|`AssemblyListFile`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Zawiera informacje na temat stanu między `RegisterAssembly` zadań i [unregisterassembly —](../msbuild/unregisterassembly-task.md) zadania. Zapobiega to `UnregisterAssembly` zadanie z próbą wyrejestrowanie zestawie, do którego nie można zarejestrować w `RegisterAssembly` zadania.|  
|`CreateCodeBase`|Opcjonalnie `Boolean` parametru.<br /><br /> Jeśli `true`, tworzy wpis codebase w rejestrze, który określa ścieżkę pliku dla zestawu, który nie jest zainstalowany w globalnej pamięci podręcznej. Nie należy określać tej opcji, jeśli później instalowany będzie zestaw, który jest rejestrowany w globalnej pamięci podręcznej zestawów.|  
|`TypeLibFiles`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Określa plik biblioteki typów do wygenerowania z określonego zestawu. Biblioteka wygenerowany typ zawiera definicje dostępnych typów zdefiniowanych w zestawie. Biblioteka typów jest generowany tylko w sytuacji, gdy jest spełniony jeden z następujących czynności:<br /><br /> -Bibliotekę typów o takiej nazwie nie istnieje w tej lokalizacji.<br />— Biblioteka typów istnieje, ale jest starszy niż zestaw przekazywany.<br /><br /> Jeśli biblioteka typów jest nowsza niż zestaw przekazywana, nie zostaną utworzone nowe konto, ale nadal będzie można zarejestrować zestawu.<br /><br /> Jeśli ten parametr jest określony, musi mieć taką samą liczbę elementów jako `Assemblies` parametru lub zadanie zakończy się niepowodzeniem. Jeśli nie określono żadnych danych wejściowych, zadanie będzie domyślnie nazwa zestawu i zmień rozszerzenie elementu .tlb.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów wymienionych powyżej, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto `RegisterAssembly` zadanie, aby zarejestrować zestaw określony przez `MyAssemblies` elementu kolekcji.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyAssemblies Include="MyAssembly.dll" />  
    <ItemGroup>  
  
    <Target Name="RegisterAssemblies">  
        <RegisterAssembly  
            Assemblies="@(MyAssemblies)" >  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)



