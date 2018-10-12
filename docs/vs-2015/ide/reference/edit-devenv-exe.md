---
title: -Edytuj (devenv.exe) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Devenv, /edit switch
- /Edit Devenv swtich
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bbe3adb8967c7571a320bcdf840df6f511c42a7f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49242135"
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Otwiera określony plik w istniejącym wystąpieniu programu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="syntax"></a>Składnia  
  
```  
Devenv /edit [file1[ file2]]  
```  
  
## <a name="arguments"></a>Argumenty  
 `file1`  
 Opcjonalna. Plik aby otworzyć w istniejącym wystąpieniu programu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Jeśli żadne wystąpienie elementu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] istnieje, jest tworzone nowe wystąpienie o uproszczonym układzie okna, a `file1` jest otwarty w nowym wystąpieniu.  
  
 `file2`  
 Opcjonalna. Jeden lub więcej dodatkowych plików do otwierania w istniejącym wystąpieniu programu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="remarks"></a>Uwagi  
 Jeśli plik nie jest określony, a istniejącego wystąpienia programu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], istniejące wystąpienie programu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] zostanie ustawiony fokus. Jeśli plik nie jest określona i nie żadne istniejące wystąpienie [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], nowe wystąpienie klasy [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] jest tworzona przy użyciu uproszczonym układzie okna.  
  
 Jeśli istniejące wystąpienie programu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] jest w stanie modalne, na przykład, jeśli [okno dialogowe Opcje](../../ide/reference/options-dialog-box-visual-studio.md) jest otwarty, będzie plik open w istniejącym wystąpieniu kiedy [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] kończy stan modalny.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie otwiera plik `MyFile.cs` w istniejącym wystąpieniu programu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] lub otwiera plik w nowym wystąpieniu programu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Jeśli już nie istnieje.  
  
```  
devenv /edit MyFile.cs  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Przełączniki wiersza polecenia Devenv](../../ide/reference/devenv-command-line-switches.md)



