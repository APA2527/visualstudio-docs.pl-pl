---
title: 'IDebugProgram2:: Attach | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::Attach
helpviewer_keywords:
- IDebugProgram2::Attach
ms.assetid: de069fbf-a565-4905-b102-f5658c55aacd
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f42aa8ff646a62f7314887df4b38c648e2d84b31
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99931451"
---
# <a name="idebugprogram2attach"></a>IDebugProgram2::Attach
Dołącza do programu.

## <a name="syntax"></a>Składnia

```cpp
HRESULT Attach( 
   IDebugEventCallback2* pCallback
);
```

```csharp
int Attach( 
   IDebugEventCallback2 pCallback
);
```

## <a name="parameters"></a>Parametry
`pCallback`\
podczas Obiekt [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) , który ma być używany do powiadamiania o zdarzeniach debugowania.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca kod błędu. W poniższej tabeli przedstawiono niektóre możliwe kody błędów.

|Wartość|Opis|
|-----------|-----------------|
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|Określony program jest już dołączony do debugera.|
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|Podczas procedury Attach wystąpiło naruszenie zabezpieczeń.|
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|Nie można dołączyć programu klasycznego do debugera.|

## <a name="remarks"></a>Uwagi
 Aparat debugowania (DE) nigdy nie wywołuje tej metody w celu dołączenia do programu. Jeśli nie działa w przestrzeni adresowej programu, wywoływana jest metoda [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) . Jeśli nie działa w przestrzeni adresowej Menedżera debugowania sesji (SDM), wywoływana jest metoda [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) .

## <a name="see-also"></a>Zobacz też
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)
- [Dołącz](../../../extensibility/debugger/reference/idebugengine2-attach.md)
