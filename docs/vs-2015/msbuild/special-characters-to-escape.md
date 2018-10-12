---
title: Znaki specjalne wyjścia | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- special characters to escape
- msbuild, special characters to escape
ms.assetid: 5b5172c3-41e4-4f38-a16f-2aeac831a5fc
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c851c6968418356626a69830ea89a918edc2cadf
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49251228"
---
# <a name="special-characters-to-escape"></a>Znaki specjalne wyjścia
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Tylko wtedy, gdy mają one specjalnego znaczenia w kontekście, w którym są one używane, należy użyć znaków ucieczki znaków specjalnych. Na przykład znak gwiazdki (*) jest znakiem specjalnym, tylko w atrybutach "Include" i "Wyklucz" definicji elementu lub w wywołaniu <xref:Microsoft.Build.Tasks.CreateItem>. We wszystkich innych przypadkach gwiazdka jest traktowany jako literał gwiazdki. Gdy jest konieczne ucieczki gwiazdki wszędzie, gdzie w plikach projektu, to to samo dotyczy żadnych szkód.  
  
 Użyj % notacji*xx* zamiast znaki specjalne, gdzie *xx* reprezentuje wartości szesnastkowej znaku ASCII. Na przykład, aby użyć gwiazdki (*) jako znak literałowy, użyj wartości `%2A`.  
  
 Pełną listę znaki specjalne wyjścia są następujące:  
  
|Znak|Opis|  
|---------------|-----------------|  
|%|Używany znak procentu, aby odwoływać się do metadanych.|  
|$|Znak dolara, używany do odwoływać się do właściwości.|  
|@|Znak używany do odwoływać się do elementu listy.|  
|(|Nawiasem otwierającym używane na listach.|  
|)|Nawiasu zamykającego używane na listach.|  
|`|Apostrof (lub znacznika) używane w warunkach i inne wyrażenia.|  
|;|Średnik jest separatorem listy.|  
|?|Znak zapytania, symbolu wieloznacznego w opisie specyfikacji pliku, w sekcji uwzględniania/wykluczania elementów.|  
|*|Gwiazdka jest symbolem wieloznacznym podczas opisywania specyfikacji pliku, w sekcji uwzględniania/wykluczania elementów.|  
  
## <a name="see-also"></a>Zobacz też  
 [Porady: znaki specjalne ucieczki w MSBuild](../msbuild/how-to-escape-special-characters-in-msbuild.md)   
 [Odwołanie do narzędzia MSBuild](../msbuild/msbuild-reference.md)



