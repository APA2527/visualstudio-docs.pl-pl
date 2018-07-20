---
title: Odwołanie do zadania MSBuild WPF | Dokumentacja firmy Microsoft
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
- WPF MSBuild task reference [WPF MSBuild], term/definition table
- build tasks [WPF MSBuild], Microsoft build engine
- build tasks using the Microsoft build engine [WPF MSBuild], compile markup and process resources
- WPF MSBuild task reference [WPF MSBuild]
ms.assetid: 96df0370-e50f-4ffc-9771-b12fb8721143
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 53f723644744001e39967186d0eeec74bf7d3bd7
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39153803"
---
# <a name="wpf-msbuild-task-reference"></a>Odwołanie do zadania WPF MSBuild
Proces kompilacji Windows Presentation Foundation (WPF) Microsoft build engine (MSBuild) rozszerza możliwości za sprawą dodatkowego zestawu zadań kompilacji, w tym zadania, aby skompilować i zasobów procesowych.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [FileClassifier](../msbuild/fileclassifier-task.md)  
 Klasyfikuje zestaw zasobów źródłowego, jak te, które zostaną osadzone w zestawie. Jeśli zasób nie jest możliwych do zlokalizowania, jest osadzony w głównym zestawem aplikacji; w przeciwnym razie jest osadzony w zestawie satelickim.  
  
 [Generatetemporarytargetassembly —](../msbuild/generatetemporarytargetassembly-task.md)  
 Generuje zestaw, jeśli co najmniej jeden [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] strony w projekcie odwołuje się do typu, który jest zadeklarowany lokalnie w tym projekcie. Wygenerowanego zestawu jest usuwany po zakończeniu procesu kompilacji, czy Proces kompilacji zakończy się niepowodzeniem.  
  
 [GetWinFXPath](../msbuild/getwinfxpath-task.md)  
 Zwraca katalog bieżącego [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)] środowiska uruchomieniowego.  
  
 [MarkupCompilePass1](../msbuild/markupcompilepass1-task.md)  
 Konwertuje niemożliwe do zlokalizowania [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] pliki na skompilowany format binarny projektu.  
  
 [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md)  
 Przeprowadza korektę znaczników kompilacji na [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] pliki, które odwołują się typy w tym samym projekcie.  
  
 [Mergelocalizationdirectives —](../msbuild/mergelocalizationdirectives-task.md)  
 Scala atrybuty lokalizacji i komentarze, co najmniej jednego [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] plików binarnych w jeden plik dla całego zestawu.  
  
 [ResourcesGenerator](../msbuild/resourcesgenerator-task.md)  
 Osadza co najmniej jeden zasób (*.jpg*, *.ico*, *.bmp*, [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] w formacie binarnym, a inne typy rozszerzeń) do *Resources*pliku.  
  
 [UidManager](../msbuild/uidmanager-task.md)  
 Sprawdza, czy, aktualizuje lub usuwa unikatowe identyfikatory (UID), aby zlokalizować wszystkie [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] elementy, które znajdują się w źródle [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] plików.  
  
 [UpdateManifestForBrowserApplication](../msbuild/updatemanifestforbrowserapplication-task.md)  
 Dodaje  **\<hostInBrowser / >** elementu w manifeście aplikacji (*\<nazwa_projektu >. exe.manifest*) podczas [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)] projekt został skompilowany.  
  
## <a name="see-also"></a>Zobacz także  
 [MSBuild](../msbuild/msbuild.md)