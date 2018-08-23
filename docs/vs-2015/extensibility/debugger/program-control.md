---
title: Program kontrolki | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], control of execution
ms.assetid: 6be80904-e66c-4cae-8891-1113b799fb01
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b213ee6eca5d132c663e86d6829b688952d150d4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682409"
---
# <a name="program-control"></a>Kontrola programu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [kontroli programu](https://docs.microsoft.com/visualstudio/extensibility/debugger/program-control).  
  
W programie Visual Studio debugowanie wszystkich następujących przechodzenie krok po kroku i kontynuowanie procedury wykonywane na poziomie programu:  
  
-   Oznacza to, że ustawienie następnej instrukcji, ustawienia komputera do następnej instrukcji do wykonania w środowisku określonego ramki  
  
-   Wykonywanie, oznacza to, w dalszym ciągu wyjście z trybu przechodzenia krok po kroku  
  
-   Przechodzenie do następnej instrukcji  
  
-   Kontynuując bieżący tryb wykonywania krokowego  
  
-   Zawieszanie wątków zawarte przez program  
  
-   Wznawianie wątków zawarte przez program  
  
> [!NOTE]
>  Wyświetlanie stosu wywołań jest wdrażany na poziomie wątku. Aby wyliczyć informacji o ramce, podczas wyświetlania stos wywołań dla wątku, należy zaimplementować wszystkie metody [IEnumDebugFrameInfo2](../../extensibility/debugger/reference/ienumdebugframeinfo2.md) interfejsu.  
  
## <a name="methods-of-program-control"></a>Metody kontroli programu  
 W poniższej tabeli przedstawiono metody [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) musi zostać wdrożone dla aparatu debugowania minimalny zestaw funkcjonalności (DE) i kontrola wykonywania.  
  
|Metoda|Opis|  
|------------|-----------------|  
|[IDebugProgram2::Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md)|Nadal uruchomione wszystkie wątki zawarte przez program w stanie zatrzymania. Wymagane do wykonywania kontroli.|  
|[IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md)|Nadal uruchomione wszystkie wątki zawarte przez program w stanie zatrzymania. Wymagane do wykonywania kontroli.|  
|[IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md)|Wykonuje krok dla danego wątku. Nadal uruchomione inne wątki zawartych w programie. Wymagane do wykonywania kontroli.|  
  
 W przypadku programów wielowątkowych, należy także zaimplementować [IDebugProgram2::EnumThreads](../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) metody i wszystkie metody [IEnumDebugThreads2](../../extensibility/debugger/reference/ienumdebugthreads2.md) interfejsu.  
  
## <a name="see-also"></a>Zobacz też  
 [Kontrola wykonywania i ocena stanu](../../extensibility/debugger/execution-control-and-state-evaluation.md)

