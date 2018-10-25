---
title: Wiele języków DSL w jednym rozwiązaniu | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e668620-6217-4e87-aea7-e9036776c8e4
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 8bf5e3d69b67cf51c1e70ec8ffe9e91d87a1dcbe
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49820177"
---
# <a name="multiple-dsls-in-one-solution"></a>Wiele języków DSL w jednym rozwiązaniu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Można spakować kilka języków DSL w ramach jednego rozwiązania, tak, aby zainstalować je ze sobą.  
  
 Kilka technik umożliwia integrowanie wiele języków DSL. Aby uzyskać więcej informacji, zobacz [integrowanie modeli za pomocą programu Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md) i [porady: Dodawanie obsługi przeciągania i upuszczania](../modeling/how-to-add-a-drag-and-drop-handler.md) i [Dostosowywanie zachowania dotyczącego kopiowania](../modeling/customizing-copy-behavior.md).  
  
### <a name="to-build-more-than-one-dsl-in-the-same-solution"></a>Aby utworzyć więcej niż jednym języku DSL w tym samym rozwiązaniu  
  
1. Tworzenie dwóch lub więcej rozwiązań DSL i projekt VSIX, a następnie dodaj wszystkie projekty do jednego rozwiązania.  
  
   -   Aby utworzyć nowy projekt VSIX: W **nowy projekt** okno dialogowe, wybierz opcję **Visual C#**, **rozszerzalności**, **projekt VSIX**.  
  
   -   Utwórz dwa lub więcej rozwiązań DSL w katalogu rozwiązania VSIX.  
  
        Dla każdego języka DSL Otwórz nowe wystąpienie programu Visual Studio. Utwórz nowy język DSL i określić ten sam folder rozwiązania jako rozwiązania VSIX.  
  
        Upewnij się, tworzenie każdego DSL z rozszerzeniem innej nazwy pliku.  
  
   -   Zmiany nazw **Dsl** i **DslPackage** projektów, tak aby były różne. Na przykład: `Dsl1`, `DslPackage1`, `Dsl2`, `DslPackage2`.  
  
   -   W każdym **DslPackage\*\source.extension.tt**, zaktualizować ten wiersz do poprawnej nazwy projektu Dsl:  
  
        `string dslProjectName = "Dsl2";`  
  
   -   W przypadku rozwiązania VSIX Dodaj Dsl * i DslPackage\* projektów.  
  
        Warto umieścić każdej pary w jego własnym folderze rozwiązania.  
  
2. Łączenie języków DSL manifesty VSIX:  
  
   1.  Otwórz _YourVsixProject_**\source.extension.manifest**.  
  
   2.  Dla każdego języka DSL, wybierz **Dodaj zawartość** i Dodaj:  
  
       -   `Dsl*` projekt jako **składnik MEF**  
  
       -   `DslPackage*` projekt jako **składnik MEF**  
  
       -   `DslPackage*` projekt jako **pakietu programu VS**  
  
3. Skompiluj rozwiązanie.  
  
   Wynikowy VSIX zainstaluje zarówno językami DSL. Można je przetestować, naciskając klawisz F5 lub wdrożyć _YourVsixProject_**\bin\Debug\\\*.vsix**.  
  
## <a name="see-also"></a>Zobacz też  
 [Integrowanie modeli za pomocą programu Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md)   
 [Porady: Dodawanie obsługi przeciągania i upuszczania](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Dostosowywanie zachowania dotyczącego kopiowania](../modeling/customizing-copy-behavior.md)



