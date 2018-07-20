---
title: Wywoływanie zdarzeń debugera | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: b3440ac3-80af-40c6-bef4-cbf00fa67885
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3ae37a6f6ed180d13623a04afd357efcc109039f
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39153036"
---
# <a name="call-debugger-events"></a>Wywoływanie zdarzeń debugera
Zdarzenia w sesji debugowania występują w określonej kolejności.  
  
## <a name="discussion"></a>Dyskusja  
 Aby poznać wzorzec wywołań między aparat debugowania (DE), a Menedżer debugowania sesji (SDM), następujące reprezentuje kolejność wywoływania zdarzeń występujących w Typowa sesja debugowania:  
  
1.  [Dołączanie i odłączanie do programu](../../extensibility/debugger/attaching-and-detaching-to-a-program.md)  
  
2.  [Uruchamianie debugera](../../extensibility/debugger/launching-the-debugger.md)  
  
3.  [Kończenie programu](../../extensibility/debugger/terminating-a-program.md)  
  
4.  [Tworzenie punktu przerwania](../../extensibility/debugger/creating-a-breakpoint.md)  
  
5.  [Gdy powiązanie punktu przerwania lub staje się niepowiązanych](../../extensibility/debugger/when-a-breakpoint-binds-or-becomes-unbound.md)  
  
6.  [Błędy punktu przerwania](../../extensibility/debugger/breakpoint-errors.md)  
  
7.  [Aktywacja punktu przerwania](../../extensibility/debugger/hitting-a-breakpoint.md)  
  
8.  [Usuwanie punktu przerwania](../../extensibility/debugger/deleting-a-breakpoint.md)  
  
9. [Przejście do trybu break](../../extensibility/debugger/entering-break-mode.md)  
  
10. [Wykonywanie krokowe w trybie przerwania](../../extensibility/debugger/stepping-in-break-mode.md)  
  
11. [Obliczanie wyrażenia w trybie przerwania](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
12. [Obsługa wyjątków](../../extensibility/debugger/exception-handling-visual-studio-sdk.md)  
  
## <a name="see-also"></a>Zobacz także  
 [Tworzenie niestandardowego aparatu debugowania](../../extensibility/debugger/creating-a-custom-debug-engine.md)