---
title: 'IDebugProcess2:: CauseBreak | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::CauseBreak
helpviewer_keywords:
- IDebugProcess2::CauseBreak
ms.assetid: efda8865-2319-4d53-90bf-6d9d74cd5195
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1094b3a214629c027f2574127d74cff7f0ea119c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99874116"
---
# <a name="idebugprocess2causebreak"></a>IDebugProcess2::CauseBreak
Żąda, aby następny program, który uruchomił kod w tym procesie, zatrzymał i wysłał obiekt zdarzenia [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) .

## <a name="syntax"></a>Składnia

```cpp
HRESULT CauseBreak( 
   void
);
```

```csharp
int CauseBreak();
```

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca kod błędu.

## <a name="see-also"></a>Zobacz też
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
