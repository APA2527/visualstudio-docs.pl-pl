---
title: Writecodefragment — zadanie | Dokumentacja firmy Microsoft
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
- MSBuild, WriteCodeFragment task
- WriteCodeFragment task [MSBuild]
ms.assetid: 1d2514b4-5bef-43bb-bebe-496da8ef063c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6246c66299bb713c8b024feefa12eb883e2c0c76
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2018
ms.locfileid: "39231096"
---
# <a name="writecodefragment-task"></a>WriteCodeFragment — zadanie
Generuje plik tymczasowy kod z fragmentu określonego wygenerowanego kodu. Nie powoduje usunięcia pliku.  
  
## <a name="parameters"></a>Parametry  
 W poniższej tabeli opisano parametry `WriteCodeFragment` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`AssemblyAttributes`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Opis atrybutów do zapisania. Element `Include` wartość jest pełna nazwa typu atrybutu, na przykład "System.AssemblyVersionAttribute".<br /><br /> Każdy metadane są pary nazwa wartość parametru, który musi być typu `String`. Niektóre atrybuty zezwalać tylko argumenty pozycyjne konstruktora. Jednak można użyć takich argumentach w dowolny atrybut. Aby ustawić atrybuty Konstruktor pozycyjne, użyj nazwy metadanych, które przypominają "_Parameter1", "_Parameter2" i tak dalej.<br /><br /> Indeks parametru nie może zostać pominięte.|  
|`Language`|Wymagane `String` parametru.<br /><br /> Określa język kodu do wygenerowania.<br /><br /> `Language` może być dowolnego języka, dla którego dostawcy CodeDom jest dostępna, na przykład, "C#" lub "VisualBasic". Emitowany plik będzie miał rozszerzenie nazwy pliku domyślnego dla tego języka.|  
|`OutputDirectory`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Określa folder docelowy dla wygenerowanego kodu zwykle pośrednich folderu.|  
|`OutputFile`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametr wyjściowy.<br /><br /> Określa ścieżkę do pliku, który został wygenerowany. Jeśli ten parametr ma wartość przy użyciu nazwy pliku, folder docelowy jest dołączony do nazwy pliku. Jeśli została ustawiona za pomocą głównego, folder docelowy jest ignorowana.<br /><br /> Jeśli ten parametr nie jest ustawiona, nazwa pliku wyjściowego jest folder docelowy, nazwę dowolnego pliku i rozszerzenie nazwy pliku domyślnego dla określonego języka.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów, które są wymienione w tabeli, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)