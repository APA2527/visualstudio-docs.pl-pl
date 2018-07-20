---
title: Metadane dobrze znanego elementu MSBuild | Dokumentacja firmy Microsoft
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
- MSBuild, item metadata
- MSBuild, well-known item metadata
ms.assetid: b5e791b5-c68f-4978-ad8a-9247d03bb6c0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3d1ec2d2ade7162f08db954d8a7bebe059a21878
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39154563"
---
# <a name="msbuild-well-known-item-metadata"></a>Metadane dobrze znanego elementu MSBuild
Poniższa tabela opisuje metadane przypisywane do każdego elementu przy utworzeniu. W każdym przykładzie użyto następującej deklaracji elementu dołączenie pliku *C:\MyProject\Source\Program.cs* w projekcie.  
  
```xml  
<ItemGroup>  
    <MyItem Include="Source\Program.cs" />  
</ItemGroup>  
```  
  
|Metadane elementu|Opis|  
|-------------------|-----------------|  
|%(FullPath)|Zawiera pełną ścieżkę elementu. Na przykład:<br /><br /> *C:\MyProject\Source\Program.CS*|  
|%(RootDir)|Zawiera katalog główny elementu. Na przykład:<br /><br /> *C:\\*|  
|%(Filename)|Zawiera nazwę pliku bez rozszerzenia elementu. Na przykład:<br /><br /> *Program*|  
|%(Extension)|Zawiera rozszerzenie nazwy pliku elementu. Na przykład:<br /><br /> *.CS*|  
|%(RelativeDir)|Zawiera ścieżkę określoną w `Include` atrybutu do końcowej kreski ułamkowej odwróconej (\\). Na przykład:<br /><br /> *Źródło\\*|  
|%(Directory)|Zawiera katalog elementu, bez katalogu głównego. Na przykład:<br /><br /> *MyProject\\źródła\\*|  
|%(RecursiveDir)|Jeśli `Include` atrybut zawiera symbol wieloznaczny \* \*, te metadane określają część ścieżki, która zastępuje symbol wieloznaczny. Aby uzyskać więcej informacji na temat symboli wieloznacznych, zobacz [porady: Wybieranie plików do kompilacji](../msbuild/how-to-select-the-files-to-build.md).<br /><br /> Jeśli folder *C:\MySolution\MyProject\Source\\*  zawiera plik *Program.cs*, a jeśli plik projektu zawiera ten element:<br /><br /> `<ItemGroup>`<br /><br /> `<MyItem Include="C:\**\Program.cs" />`<br /><br /> `</ItemGroup>`<br /><br /> następnie wartość `%(MyItem.RecursiveDir)` będzie *MySolution\MyProject\Source\\*.|  
|%(Identity)|Element określony w `Include` atrybutu... Na przykład:<br /><br /> *Source\Program.CS*|  
|%(ModifiedTime)|Zawiera sygnaturę czasową od czasu, gdy zmodyfikowano element. Na przykład:<br /><br /> `2004-07-01 00:21:31.5073316`|  
|%(CreatedTime)|Zawiera sygnaturę czasową od utworzenia elementu. Na przykład:<br /><br /> `2004-06-25 09:26:45.8237425`|  
|%(AccessedTime)|Zawiera sygnaturę czasową od czasu, gdy uzyskano dostęp do elementu.<br /><br /> `2004-08-14 16:52:36.3168743`|  
  
## <a name="see-also"></a>Zobacz także  
 [Elementy](../msbuild/msbuild-items.md)   
 [Przetwarzanie wsadowe](../msbuild/msbuild-batching.md)   
 [Odwołanie do narzędzia MSBuild](../msbuild/msbuild-reference.md)