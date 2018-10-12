---
title: Określanie Namespace domyślnego projektu | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom tools, computing default namespace
ms.assetid: 6d890676-7016-458c-8a6a-95cc0a068612
caps.latest.revision: 13
manager: douge
ms.openlocfilehash: a456b9b48ce9ba0817070fb5f04b5c9f80ffb149
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49223330"
---
# <a name="determining-the-default-namespace-of-a-project"></a>Określanie Namespace domyślnego projektu
Dla [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], jeśli `CustomToolNamespace` właściwość jest ustawiona w pliku wejściowego, a następnie wartość `CustomToolNamespace` staje się wartością domyślnego parametru przestrzeni nazw, przekazana do <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> metody. W przeciwnym razie `wszDefaultNamespace` parametr przekazany do `Generate` jest zawsze równa głównej przestrzeni nazw. Aby uzyskać więcej informacji na temat przestrzenie nazw, zobacz [słowa kluczowe Namespace](http://msdn.microsoft.com/library/091a66eb-b10d-4f54-9102-5ac0d4bdb84b).  
  
 [!INCLUDE[csprcs](../includes/csprcs-md.md)] używa przestrzeni nazw opartych na folder. Oznacza to, że przestrzeń nazw składa się z głównego obszaru nazw, a także nazwy dowolnego folderu zawierającego narzędzie niestandardowe. Każda nazwa folderu jest konwertowana na prawidłowy identyfikator i okresy oddzielić wszystkie nazwy. Na przykład, jeśli plik wejściowy jest FolderA\FolderB\FolderC\MyInput.txt oraz główna przestrzeń nazw jest CL9 obliczanej domyślny obszar nazw będzie **CL9. FolderA.FolderB.FolderC**.  
  
 Wyjątkiem od tej reguły występuje, gdy łańcucha hierarchii zawiera folder odwołania sieci Web. Na przykład jeśli:  
  
-   FolderC były folder odwołania sieci Web, przestrzeń nazw będzie **CL9. FolderC**.  
  
-   FolderB były folder odwołania sieci Web, przestrzeń nazw będzie **CL9. FolderB.FolderC**.  
  
 Oznacza to, że przestrzeń nazw posługuje się następującym formatem:  
  
```  
rootNamespace.webReferenceFolder.containedFolder.containedFolder ...  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Implementowanie generatorów jednoplikowych](../extensibility/internals/implementing-single-file-generators.md)   
 [Rejestrowanie generatorów jednoplikowych](../extensibility/internals/registering-single-file-generators.md)   
 [Udostępnianie typów dla projektantów wizualnych](../extensibility/internals/exposing-types-to-visual-designers.md)