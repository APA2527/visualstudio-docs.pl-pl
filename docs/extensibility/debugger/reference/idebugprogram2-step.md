---
title: 'IDebugProgram2:: Step | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::Step
helpviewer_keywords:
- IDebugProgram2::Step
ms.assetid: e4c2ffce-9810-4088-8162-eac9ef04f2a9
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 544ca22d263a3fca47f9484ac126031e83cde4e0
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99911909"
---
# <a name="idebugprogram2step"></a>IDebugProgram2::Step
Wykonuje krok.

> [!NOTE]
> Ta metoda jest przestarzała. Zamiast tego użyj metody [Step](../../../extensibility/debugger/reference/idebugprocess3-step.md) .

## <a name="syntax"></a>Składnia

```cpp
HRESULT Step( 
   IDebugThread2*  pThread,
   STEPKIND        sk,
   STEPUNIT        step
);
```

```csharp
int Step( 
   IDebugThread2  pThread,
   enum_STEPKIND  sk,
   enum_STEPUNIT  step
);
```

## <a name="parameters"></a>Parametry
`pThread`\
podczas Obiekt [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) , który reprezentuje poddany wątek.

`sk`\
podczas Wartość z wyliczenia [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) , która określa rodzaj kroku.

`step`\
podczas Wartość z wyliczenia [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) , która określa jednostkę kroku (na przykład przez instrukcję lub instrukcję).

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca kod błędu.

## <a name="remarks"></a>Uwagi
 W przypadku gdy istnieje jakakolwiek synchronizacja wątków lub komunikacja między wątkami, inne wątki w programie powinny być uruchamiane, gdy określony wątek działa.

> [!WARNING]
> Nie wysyłaj zdarzenia zatrzymania ani bezpośredniego (synchronicznego) zdarzenia do [zdarzenia](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) podczas obsługi tego wywołania; w przeciwnym razie debuger może przestać odpowiadać.

## <a name="see-also"></a>Zobacz też
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)
- [Zdarzenie](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
