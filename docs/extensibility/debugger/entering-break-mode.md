---
title: Wchodzenie do trybu przerwania | Microsoft Docs
description: Dowiedz się więcej na temat procesu, który występuje dla punktu przerwania w funkcji, działającego w wierszu kodu źródłowego w kursorze lub w punkcie przerwania.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- break mode
- debugging [Debugging SDK], entering break mode
ms.assetid: e9a8a241-cd21-4d4e-999a-283554c288b1
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: d3ec09994f6998f87daafc690b1908b31e54706b
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99840655"
---
# <a name="enter-break-mode"></a>Przejdź do trybu przerwania
Poniższe informacje opisują proces, który występuje, gdy punkt przerwania zostanie napotkany po przejściu do funkcji, działający w wierszu kodu źródłowego, który zawiera kursor lub działa do punktu przerwania.

## <a name="break-mode-process"></a>Proces trybu przerwania

1. Aparat debugowania (DE) wysyła [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md)lub wszystkie inne zdarzenia zatrzymujące, aby spowodować, że IDE przekroczy tryb przerwania.

2. Model SDM pobiera informacje o stosie wywołań z wątku w następujący sposób:

    - [IDebugThread2::EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)

    - [IEnumDebugFrameInfo2::GetCount](../../extensibility/debugger/reference/ienumdebugframeinfo2-getcount.md)

    - [IEnumDebugFrameInfo2::Next](../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)

    - [IDebugStackFrame2:: GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) w celu uzyskania informacji o kodzie źródłowym

    - [IDebugDocumentContext2:: GetName](../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md) , aby uzyskać nazwę pliku

    - [IDebugDocumentContext2:: GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md) w celu pobrania zakresu instrukcji

    - [IDebugStackFrame2:: GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md) w celu uzyskania informacji o pamięci

## <a name="see-also"></a>Zobacz też
- [Wywoływanie zdarzeń debugera](../../extensibility/debugger/calling-debugger-events.md)
