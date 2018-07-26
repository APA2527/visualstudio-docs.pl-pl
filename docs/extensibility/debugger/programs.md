---
title: Programy | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], programs
- programs, debugging
ms.assetid: e1f955d8-95da-493b-837e-e97741a26d7e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d8bd34f72f54fe068ff39b752ddbd6348e4970db
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/25/2018
ms.locfileid: "39252378"
---
# <a name="programs"></a>Programy
W architekturze debugera *program*:  
  
-   To kontener dla zestawu wątków i zestaw modułów. Program nie ma żadnych pojedynczego odpowiednio w systemie operacyjnym Windows.  
  
     Program jest rodzajem proces podrzędny. Na przykład podczas debugowania witryny sieci Web, skrypt może być traktowany jako program. Podczas uruchamiania skryptu w procesie aparatu obsługi skryptów, niezależnie od innych skryptów również ma swój własny zestaw wątków. Aparat debugowania (DE) dołącza do programu, a nie proces lub wątek.  
  
-   Można zidentyfikować wraz z procesu, który jest uruchomiony w. Program można dołączyć zostać odłączony od oraz opisano DE, w której został utworzony, jeśli istnieje. Program można również wykonać, Zatrzymaj, kontynuować i można zakończony.  
  
-   Można wyliczyć wszystkich wątków. Program można również podać własną strumienia dezasemblacji i można wyliczyć wszystkie konteksty kodu pozycji danego dokumentu.  
  
-   Jest reprezentowany przez [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) interfejsu, utworzonych przed program jest dołączona lub jako część procesu dołączania w zależności od implementacji. Gdy port wylicza programy procesu, każdy program zostanie utworzony zgodnie z odpowiednią [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) interfejsu przekazywany jako argument do [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Aparaty debugowania również tworzyć `IDebugProgram2` interfejsy do reprezentowania programy, te programy nie są tworzone zgodnie z węzła programu. `IDebugProgramNode2` Interfejsów utworzone przez DE służą do debugowania rzeczywiste utworzone przez port są używane tylko w przypadku odnajdywania, które programy działają w ramach procesu.  
  
## <a name="see-also"></a>Zobacz także  
 [Procesy](../../extensibility/debugger/processes.md)   
 [Węzły programu](../../extensibility/debugger/program-nodes.md)   
 [Moduły](../../extensibility/debugger/modules.md)   
 [Pojęcia dotyczące debugera](../../extensibility/debugger/debugger-concepts.md)   
 [Aparat debugowania](../../extensibility/debugger/debug-engine.md)   
 [Położenie dokumentu](../../extensibility/debugger/document-position.md)   
 [Kontekst kodu](../../extensibility/debugger/code-context.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)