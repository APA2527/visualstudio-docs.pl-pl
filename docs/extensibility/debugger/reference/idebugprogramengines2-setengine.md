---
title: 'IDebugProgramEngines2:: SetEngine | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramEngines2::SetEngine
helpviewer_keywords:
- IDebugProgramEngines2::SetEngine
ms.assetid: c05857ee-89cf-455e-8f1e-300cce4a2eab
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5ecdf136e40dc4227b8f6378409cb7fe43f6659d
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99898887"
---
# <a name="idebugprogramengines2setengine"></a>IDebugProgramEngines2::SetEngine
Informuje program lub węzeł programu, który aparat debugowania (DE) ma używać do debugowania tego programu.

## <a name="syntax"></a>Składnia

```cpp
HRESULT SetEngine( 
   REFGUID guidEngine
);
```

```csharp
int SetEngine( 
   ref Guid guidEngine
);
```

## <a name="parameters"></a>Parametry
`guidEngine`\
podczas Identyfikator GUID DE.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca kod błędu.

## <a name="see-also"></a>Zobacz też
- [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)
