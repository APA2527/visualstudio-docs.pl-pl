---
title: 'IDebugAlias:: GetICorDebugValue | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fd01785fee7ce65296bac940fb19819415139d53
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "80736477"
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
Pobiera interfejs kodu zarządzanego, który reprezentuje wartość skojarzoną z tym aliasem.

## <a name="syntax"></a>Składnia

```cpp
HRESULT GetICorDebugValue(
   IUnknown** ppUnk
);
```

```csharp
int GetICorDebugValue(
   out object ppUnk
);
```

## <a name="parameters"></a>Parametry
`ppUnk`\
[out] `IUnknown` Interfejs, który reprezentuje wartość skojarzoną z tym aliasem. Ten interfejs może być badany dla `ICorDebugValue` interfejsu.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca S_OK; w przeciwnym razie zwraca kod błędu.

## <a name="remarks"></a>Uwagi
 Ta metoda ma zastosowanie tylko do wartości zarządzanych ( `ICorDebugValue` jest interfejsem dostępnym w .NET Framework i jest zdefiniowany w .NET Framework SDK w pliku CorDebug. idl).

## <a name="see-also"></a>Zobacz też
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)
