---
title: IDebugEvent2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 6ff87d79d45c90a3307d5f28a2aa6109033f4a59
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99933339"
---
# <a name="idebugevent2"></a>IDebugEvent2
Ten interfejs jest używany do przekazywania zarówno krytycznych informacji debugowania, takich jak zatrzymywanie w punkcie przerwania, jak i informacje niekrytyczne, takie jak komunikat debugowania.

## <a name="syntax"></a>Składnia

```
IDebugEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji
 Aparat debugowania (DE) i dostawca portu niestandardowego implementują ten interfejs na tym samym obiekcie co wszystkie inne interfejsy zdarzeń.

## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania
 Przy użyciu argumentu identyfikatora interfejsu (IID) dla [zdarzenia](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) lub [zdarzenia](../../../extensibility/debugger/reference/idebugportevents2-event.md), Menedżer debugowania sesji (SDM) wywołuje polecenie [QueryInterface](/cpp/atl/queryinterface) w `IDebugEvent2` interfejsie, aby uzyskać odpowiedni interfejs zdarzenia.

## <a name="methods-in-vtable-order"></a>Metody w kolejności tablic wirtualnych
 W poniższej tabeli przedstawiono metody `IDebugEvent2` .

|Metoda|Opis|
|------------|-----------------|
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|Pobiera atrybuty dla tego zdarzenia debugowania.|

## <a name="remarks"></a>Uwagi
 Bardziej specyficzne interfejsy zdarzeń, takie jak [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md), nie pochodzą z interfejsu IDebugEvent2, ale zamiast tego są implementowane jako osobny interfejs w tym samym obiekcie co `IDebugEvent2` .

## <a name="requirements"></a>Wymagania
 Nagłówek: Msdbg. h

 Przestrzeń nazw: Microsoft. VisualStudio. Debugger. Interop

 Zestaw: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Zobacz też
- [Interfejsy podstawowe](../../../extensibility/debugger/reference/core-interfaces.md)
- [Zdarzenie](../../../extensibility/debugger/reference/idebugportevents2-event.md)
- [Zdarzenie](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
