---
title: Zastępowanie ustawień ToolsVersion | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, overriding ToolsVersion setting
- MSBuild, building solutions with
ms.assetid: ccd42c07-0fb6-4e8b-9ebb-a6a6db18aa2e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dea73a4f21a36907e3252530f68263e1a63a8819
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39153920"
---
# <a name="override-toolsversion-settings"></a>Zastępowanie ustawień ToolsVersion
Możesz zmienić zestaw narzędzi dla projektów i rozwiązań w jednym z trzech sposobów:  
  
1.  Za pomocą `/ToolsVersion` przełącznika (lub `/tv`, w skrócie) podczas budowania projektu lub rozwiązania z wiersza polecenia.  
  
2.  Ustawiając `ToolsVersion` parametru zadana programu MSBuild.  
  
3.  Ustawiając `$(ProjectToolsVersion)` właściwości projektu w ramach rozwiązania. Dzięki temu można skompilować projektu w rozwiązaniu za pomocą narzędzi w wersji, która różni się od innych projektów.  
  
## <a name="override-the-toolsversion-settings-of-projects-and-solutions-on-command-line-builds"></a>Zastąp ustawienia ToolsVersion projektów i rozwiązań w systemie kompilacji z wiersza polecenia  
 Chociaż projekty programu Visual Studio zazwyczaj tworzą wersję narzędzi określoną w pliku projektu, możesz użyć `/ToolsVersion` (lub `/tv`) przejdź w wierszu polecenia, aby zastąpić tę wartość i Kompiluj wszystko projektów i ich projektu do projektu zależności za pomocą innego zestawu narzędzi. Na przykład:  
  
```cmd  
msbuild.exe someproj.proj /tv:12.0 /p:Configuration=Debug  
```  
  
 W tym przykładzie wszystkie projekty są kompilowane przy użyciu narzędzi w wersji 12.0. (Jednak, zobacz sekcję [priorytetu](#order-of-precedence) w dalszej części tego tematu.)  
  
 Korzystając z `/tv` Przejdź w wierszu polecenia, można opcjonalnie używać `$(ProjectToolsVersion)` właściwości w poszczególnych projektach, aby budować je z inną wartością ToolsVersion niż inne projekty w rozwiązaniu.  
  
## <a name="override-the-toolsversion-settings-using-the-toolsversion-parameter-of-the-msbuild-task"></a>Zastąp ustawienia ToolsVersion przy użyciu parametru ToolsVersion zadania MSBuild  
 Zadanie MSBuild to podstawowy sposób dla jednego projektu do innej kompilacji. Aby włączyć zadanie MSBuild w celu konstruowania projektu z innym ToolsVersion niż określona w projekcie, zapewnia parametr opcjonalny o nazwie `ToolsVersion`. Poniższy przykład pokazuje, jak używać tego parametru:  
  
1.  Utwórz plik o nazwie *projectA.proj* i zawierający poniższy kod:  
  
    ```xml  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
    ToolsVersion="12.0">  
  
        <Target Name="go" >   
            <Message Text="projectA.proj" />  
            <Message Text="MSBuildToolsVersion: $(MSBuildToolsVersion)" />  
            <Message Text="MSBuildToolsPath:    $(MSBuildToolsPath)" />  
  
            <MSBuild Projects="projectB.proj"  
                ToolsVersion="2.0"  
                Targets="go" />  
        </Target>  
    </Project>  
    ```  
  
2.  Utwórz inny plik o nazwie *projectB.proj* i zawierający poniższy kod:  
  
    ```xml  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
    ToolsVersion="12.0">  
  
        <Target Name="go">  
            <Message Text="projectB.proj" />  
            <Message Text="MSBuildToolsVersion: $(MSBuildToolsVersion)" />  
            <Message Text="MSBuildToolsPath:    $(MSBuildToolsPath)" />  
        </Target>  
    </Project>  
    ```  
  
3.  Wprowadź następujące polecenie w wierszu polecenia:  
  
    ```cmd  
    msbuild projectA.proj /t:go /toolsversion:3.5  
    ```  
  
4.  Zostanie wyświetlone następujące dane wyjściowe. Aby uzyskać `projectA`, `/toolsversion:3.5` ustawienie w wierszu polecenia zastępuje `ToolsVersion=12.0` ustawienie w `Project` tagu.  
  
     `ProjectB` jest wywoływane przez zadanie w `projectA`. To zadanie ma `ToolsVersion=2.0`, który zastępuje inne `ToolsVersion` ustawienia `projectB`.  
  
    ```  
    Output:  
      projectA.proj  
      MSBuildToolsVersion: 3.5  
      MSBuildToolsPath:    C:\Windows\Microsoft.NET\Framework\v3.5  
  
      projectB.proj  
      MSBuildToolsVersion: 2.0  
      MSBuildToolsPath:    C:\Windows\Microsoft.NET\Framework\v2.0.50727  
    ```  
  
## <a name="order-of-precedence"></a>Hierarchia ważności  
 Kolejność pierwszeństwa od najwyższego do najniższego, używana do określania `ToolsVersion` jest:  
  
1.  `ToolsVersion` Atrybut zadana programu MSBuild, użyty w celu skonstruowania projektu, jeśli istnieje.  
  
2.  `/toolsversion` (Lub `/tv`) przełącznik, który jest używany w poleceniu msbuild.exe, jeśli istnieje.  
  
3.  Jeśli zmienna środowiskowa `MSBUILDTREATALLTOOLSVERSIONSASCURRENT` jest ustawiona, a następnie użyj bieżącego `ToolsVersion`.  
  
4.  Jeśli zmienna środowiskowa `MSBUILDTREATHIGHERTOOLSVERSIONASCURRENT` ustawiono i `ToolsVersion` zdefiniowane w projekcie, plik jest większy niż bieżąca `ToolsVersion`, Użyj bieżącego `ToolsVersion`.  
  
5.  Jeśli zmienna środowiskowa `MSBUILDLEGACYDEFAULTTOOLSVERSION` jest ustawiona, lub jeśli `ToolsVersion` nie jest ustawiona, używane są następujące czynności:  
  
    1.  `ToolsVersion` Atrybutu [projektu](../msbuild/project-element-msbuild.md) elementu w pliku projektu. Jeśli ten atrybut nie istnieje, zakłada się w bieżącej wersji.  
  
    2.  Domyślna wersja narzędzi w *pliku MSBuild.exe.config* pliku.  
  
    3.  Domyślna wersja narzędzi w rejestrze. Aby uzyskać więcej informacji, zobacz [standardowe i niestandardowe konfiguracje zestawu narzędzi](../msbuild/standard-and-custom-toolset-configurations.md).  
  
6.  Jeśli zmienna środowiskowa `MSBUILDLEGACYDEFAULTTOOLSVERSION` nie jest ustawiona, używane są następujące czynności:  
  
    1.  Jeśli zmienna środowiskowa `MSBUILDDEFAULTTOOLSVERSION` ustawiono `ToolsVersion` , istnieje, użyj go.  
  
    2.  Jeśli `DefaultOverrideToolsVersion` jest ustawiana w *pliku MSBuild.exe.config*, jej używać.  
  
    3.  Jeśli `DefaultOverrideToolsVersion` jest ustawiony w rejestrze, użyj go.  
  
    4.  W przeciwnym razie Użyj bieżącego `ToolsVersion`.  
  
## <a name="see-also"></a>Zobacz także  
 [Wielowersyjności kodu w programie](../msbuild/msbuild-multitargeting-overview.md)   
 [Pojęcia dotyczące programu MSBuild](../msbuild/msbuild-concepts.md)   
 [Zestaw narzędzi (ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md)   
 [Standardowe i niestandardowe konfiguracje zestawu narzędzi](../msbuild/standard-and-custom-toolset-configurations.md)