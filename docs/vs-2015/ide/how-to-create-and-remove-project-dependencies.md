---
title: 'Porady: tworzenie i usuwanie zależności projektu | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ProjectDependenciesDlg
helpviewer_keywords:
- vs.build.projectdependencies
- project dependencies
- builds [Visual Studio], setting up
- project build configurations, dependencies
- dependencies, project
- projects [Visual Studio], dependencies
ms.assetid: e2a0a8ff-dae7-40a8-b774-b88aa5235183
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3626cc4c13600b0a6f20cc40713bd77f4527a3ce
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682568"
---
# <a name="how-to-create-and-remove-project-dependencies"></a>Porady: tworzenie lub usuwanie zależności projektu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [porady: tworzenie i usuwanie zależności projektu](https://docs.microsoft.com/visualstudio/ide/how-to-create-and-remove-project-dependencies).  
  
Podczas kompilowania rozwiązania, które zawiera wiele projektów, może być konieczne do tworzenia niektórych projektów najpierw, aby wygenerować kod używany przez inne projekty. Gdy projekt korzysta z kodu wykonywalnego, generowane przez inny projekt, projekt, który generuje kod nazywa się zależności projektu, projektu, który wykorzystuje kod. Takie relacji zależności można zdefiniować w **zależności projektu** okno dialogowe.  
  
### <a name="to-assign-dependencies-to-projects"></a>Aby przypisać zależności do projektów  
  
1.  W Eksploratorze rozwiązań wybierz projekt.  
  
2.  Na **projektu** menu, wybierz **zależności projektu**.  
  
     **Zależności projektu** zostanie otwarte okno dialogowe.  
  
    > [!NOTE]
    >  **Zależności projektu** opcja jest dostępna tylko w rozwiązaniu z więcej niż jeden projekt.  
  
3.  Na **zależności** , a następnie wybierz projekt z **projektu** menu rozwijanego.  
  
4.  W **zależy od** pól, zaznacz pole wyboru w innych projektów, które należy utworzyć przed tego projektu.  
  
 Rozwiązanie musi składać się z więcej niż jeden projekt, aby można było utworzyć zależności projektu.  
  
### <a name="to-remove-dependencies-from-projects"></a>Aby usunąć zależności z projektów  
  
1.  W Eksploratorze rozwiązań wybierz projekt.  
  
2.  Na **projektu** menu, wybierz **zależności projektu**.  
  
     **Zależności projektu** zostanie otwarte okno dialogowe.  
  
    > [!NOTE]
    >  **Zależności projektu** opcja jest dostępna tylko w rozwiązaniu z więcej niż jeden projekt.  
  
3.  Na **zależności** , a następnie wybierz projekt z **projektu** menu rozwijanego.  
  
4.  W **zależy od** pola, wyczyść pole wyboru obok pozycji inne projekty, które nie są już zależności dla tego projektu.  
  
## <a name="see-also"></a>Zobacz też  
 [Kompilowanie oraz Oczyszczanie projektów i rozwiązań w programie Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Kompilowanie i tworzenie](../ide/compiling-and-building-in-visual-studio.md)   
 [Ogólne informacje o konfiguracjach kompilacji](../ide/understanding-build-configurations.md)   
 [NIB porady: modyfikowanie właściwości projektu i ustawień konfiguracji](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)



