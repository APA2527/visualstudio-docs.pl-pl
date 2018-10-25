---
title: Dołączanie i odłączanie programu | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, attaching to programs
- debug engines, detaching from programs
ms.assetid: 79dcbb9b-c7f8-40fc-8a00-f37fe1934f51
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bd47e214492f0888d7780f8aef5944cdcdeb2591
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49949737"
---
# <a name="attaching-and-detaching-to-a-program"></a>Dołączanie i odłączanie do programu
Dołączanie debugera wymaga wysyłania odpowiedniej kolejności metod i zdarzeń z odpowiednich atrybutów.  
  
## <a name="sequence-of-methods-and-events"></a>Sekwencja metody i zdarzenia  
  
1. Menedżer debugowania sesji (SDM) wywołuje [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metody.  
  
    Na podstawie modelu procesu aparatu (DE) debugowania, `IDebugProgramNodeAttach2::OnAttach` metoda zwraca jedną z następujących metod, które określa, co dzieje się potem.  
  
    Jeśli `S_FALSE` ma zostać zwrócona, aparat debugowania pomyślnie został dołączony do programu. W przeciwnym razie [Dołącz](../../extensibility/debugger/reference/idebugengine2-attach.md) metoda jest wywoływana w celu ukończenia procesu dołączania.  
  
    Jeśli `S_OK` ma zostać zwrócona, Niemcy, które ma być ładowane w tym samym procesie co SDM. SDM wykonuje następujące zadania:  
  
   1.  Wywołania [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) można pobrać informacji o aparacie programu DE.  
  
   2.  Wspólnie tworzy DE.  
  
   3.  Wywołania [dołączyć](../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
2. Wysyła DE [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) do SDM z `EVENT_SYNC` atrybutu.  
  
3. Wysyła DE [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) do SDM z `EVENT_SYNC` atrybutu. 
  
4. Wysyła DE [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) do SDM z `EVENT_SYNC_STOP` atrybutu.  
  
   Odłączanie programu jest proste, dwuetapowy proces:  
  
5. Wywołania SDM [Odłącz](../../extensibility/debugger/reference/idebugprogram2-detach.md).  
  
6. Wysyła DE [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Wywoływanie zdarzeń debugera](../../extensibility/debugger/calling-debugger-events.md)