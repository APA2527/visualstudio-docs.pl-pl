---
title: IDebugQueryEngine2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugQueryEngine2
helpviewer_keywords:
- IDebugQueryEngine2 interface
ms.assetid: 8f0e1838-a818-4459-9138-a3dceb7408de
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: b555ac218ceee1d376c9f7cf3c9df87f7c2e2da0
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99909772"
---
# <a name="idebugqueryengine2"></a>IDebugQueryEngine2
Ten interfejs umożliwia menedżerowi debugowania sesji (SDM) pobranie interfejsu, który reprezentuje aparat debugowania (DE).

## <a name="syntax"></a>Składnia

```
IDebugQueryEngine2 : IUnknown
```

## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji
 DE implementuje ten interfejs na obiektach implementujących najpopularniejsze DE Interfaces (takich jak [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md), [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)i [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)) w celu umożliwienia dostępu do interfejsu [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) samego siebie.

## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania
 Wywołaj metodę [QueryInterface](/cpp/atl/queryinterface) na typowym de interfejsie, aby uzyskać ten interfejs.

## <a name="methods-in-vtable-order"></a>Metody w kolejności tablic wirtualnych
 W poniższej tabeli przedstawiono metody `IDebugQueryEngine2` .

|Metoda|Opis|
|------------|-----------------|
|[GetEngineInterface](../../../extensibility/debugger/reference/idebugqueryengine2-getengineinterface.md)|Pobiera niestandardowy interfejs aparatu debugowania.|

## <a name="remarks"></a>Uwagi
 Ten interfejs jest zwykle implementowany w obiekcie, który implementuje interfejs [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) , aby obsługiwał przyczynę przechodzenie przez funkcje; oznacza to, że gdy debuger nie wykonuje funkcji, następna funkcja do wykonania nie może być poprzednią funkcją na stosie, ale funkcją w innym wątku. Definicję "przyczynę" można znaleźć w [słowniku debugera programu Visual Studio](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md).

## <a name="requirements"></a>Wymagania
 Nagłówek: Msdbg. h

 Przestrzeń nazw: Microsoft. VisualStudio. Debugger. Interop

 Zestaw: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Zobacz też
- [Interfejsy podstawowe](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
