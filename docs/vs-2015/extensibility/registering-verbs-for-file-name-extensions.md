---
title: Rejestrowanie zleceń dla rozszerzeń nazw plików | Dokumentacja firmy Microsoft
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
- verbs, registering
ms.assetid: 81a58e40-7cd0-4ef4-a475-c4e1e84d6e06
caps.latest.revision: 17
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b6c42b1682c7f599513b9894646b30dee029740e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683119"
---
# <a name="registering-verbs-for-file-name-extensions"></a>Rejestrowanie zleceń dla rozszerzeń nazw plików
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [rejestrowanie zleceń dla rozszerzeń nazw plików](https://docs.microsoft.com/visualstudio/extensibility/registering-verbs-for-file-name-extensions).  
  
Skojarzenie rozszerzenia nazwy pliku z aplikacją zazwyczaj ma preferowanego akcję, która występuje po dwukrotnym kliknięciu pliku. Preferowane to, że akcja jest połączony z czasownika, na przykład otwarty, która odnosi się do akcji.  
  
 Możesz zarejestrować zlecenia, które są skojarzone z identyfikator programowy (ProgID) dla rozszerzenia, przy użyciu klawisza powłoki, znajduje się w kluczu HKEY_CLASSES_ROOT\\*progid*\shell. Aby uzyskać więcej informacji, zobacz [typów plików](http://msdn.microsoft.com/library/windows/desktop/cc144148\(v=vs.85\).aspx).  
  
## <a name="registering-standard-verbs"></a>Rejestrowanie zleceń standardowych  
 System operacyjny rozpoznaje następujących zleceń standardowych:  
  
-   Otwarcie  
  
-   Edytowanie  
  
-   Odtwarzanie  
  
-   Drukuj  
  
-   Wersja zapoznawcza  
  
 Jeśli to możliwe, należy zarejestrować standardowy czasownika. Najbardziej typowe to Open zlecenie. Czasownik edycji należy użyć tylko wtedy, gdy istnieje wyraźna różnica pomiędzy otwierania pliku i edytowania pliku. Na przykład otwieranie pliku .htm wyświetla go w przeglądarce, natomiast edycji pliku .htm uruchamia edytora HTML. Zleceń standardowych są lokalizowane za pomocą ustawień regionalnych systemu operacyjnego.  
  
> [!NOTE]
>  Podczas rejestrowania zleceń standardowych, nie należy ustawiać wartość domyślna dla otworzyć klucza. Wartość domyślna zawiera ciąg wyświetlany w menu. System operacyjny dostarcza ten ciąg dla zleceń standardowych.  
  
 Pliki projektu powinien być zarejestrowany w Uruchom nowe wystąpienie klasy [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] po użytkownik otwiera plik. W poniższym przykładzie pokazano standardowy czasownika rejestracja [!INCLUDE[csprcs](../includes/csprcs-md.md)] projektu.  
  
```  
[HKEY_CLASSES_ROOT\.csproj]  
@="VisualStudio.csproj.8.0"  
  
[HKEY_CLASSES_ROOT\.csproj\OpenWithList]  
[HKEY_CLASSES_ROOT\.csproj\OpenWithList\VSLauncher.exe]  
@=""  
  
[HKEY_CLASSES_ROOT\.csproj\OpenWithProgids]  
"VisualStudio.csproj.8.0"=""  
  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe]  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell]  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell\Open]  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell\Open\Command]  
@="C:\\Program Files\\Common Files\\Microsoft Shared\\MSEnv\\VSLauncher.exe \"%1\""  
  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0]  
@="C# Project file"  
  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\DefaultIcon]  
@="C:\\VisualStudioPath\\VC#\\VCSPackages\\csproj.dll,0"  
  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell]  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell\Open]  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell\Open\Command]  
@="\"C:\\Program Files\\Common Files\\Microsoft Shared\\MSEnv\\VSLauncher.exe\" \"%1\""  
```  
  
 Aby otworzyć plik w istniejącym wystąpieniu programu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], zarejestruj DDEEXEC klucza. W poniższym przykładzie pokazano standardowy czasownika rejestracja [!INCLUDE[csprcs](../includes/csprcs-md.md)] pliku CS.  
  
```  
[HKEY_CLASSES_ROOT\.cs]  
@="VisualStudio.cs.8.0"  
  
[HKEY_CLASSES_ROOT\.cs\OpenWithList]  
[HKEY_CLASSES_ROOT\.cs\OpenWithList\devenv.exe]  
@=""  
  
[HKEY_CLASSES_ROOT\.cs\OpenWithProgids]  
"VisualStudio.cs.8.0"=""  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0]  
@="C# Source file"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\DefaultIcon]  
@="C:\\VisualStudioPath\\VC#\\VCSPackages\\csproj.dll,1"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell]  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open]  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\Command]  
@="\"C:\\VisualStudioPath\\Common7\\IDE\\devenv.exe\" /dde \"%1\""  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec]  
@="Open(\"%1\")"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec\Application]  
@="VisualStudio.8.0"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec\Topic]  
@="system"  
```  
  
## <a name="setting-the-default-verb"></a>Ustawienie zlecenie domyślne  
 Polecenie domyślne jest akcja, która jest wykonywana po dwukrotnym kliknięciu pliku w Eksploratorze Windows. Polecenie domyślne jest określone jako wartość domyślną dla HKEY_CLASSES_ROOT zlecenie\\*progid*\Shell klucza. Jeśli wartość nie zostanie określona, polecenie domyślne jest określone w kluczu HKEY_CLASSES_ROOT zlecenie pierwszy\\*progid*\Shell listy kluczy.  
  
> [!NOTE]
>  Jeśli zamierzasz zmienić domyślne zlecenie rozszerzenia w ramach wdrożenia side-by-side, należy wziąć pod uwagę wpływ na instalacji i usuwania. Podczas instalacji zostanie zastąpiona oryginalna wartość domyślną.  
  
## <a name="see-also"></a>Zobacz też  
 [Zarządzanie równoległymi skojarzeniami plików](../extensibility/managing-side-by-side-file-associations.md)

