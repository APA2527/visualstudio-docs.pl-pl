---
title: 'IDebugEngine2:: setlocale | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::SetLocale
helpviewer_keywords:
- IDebugEngine2::SetLocale
ms.assetid: cd0d2cf1-2aac-43da-a830-4bb3d696c219
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 3e43d8d13f34b8477ab870c80842ff33eef72a7f
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99878919"
---
# <a name="idebugengine2setlocale"></a>IDebugEngine2::SetLocale
Ustawia ustawienia regionalne aparatu debugowania (Niemcy).

## <a name="syntax"></a>Składnia

```cpp
HRESULT SetLocale( 
   WORD wLangID
);
```

```csharp
int SetLocale( 
   ushort wLangID
);
```

## <a name="parameters"></a>Parametry
`wLangID`\
podczas Określa ustawienia regionalne języka. Na przykład 1033 w języku angielskim.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca kod błędu.

## <a name="remarks"></a>Uwagi
 Ta metoda jest wywoływana przez Menedżera debugowania sesji (SDM) do propagowania ustawień regionalnych IDE, dzięki czemu ciągi zwracane przez DE są prawidłowo zlokalizowane.

## <a name="see-also"></a>Zobacz też
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
