---
title: 'IDebugClassField:: EnumNestedEnums | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumNestedEnums
helpviewer_keywords:
- IDebugClassField::EnumNestedEnums method
ms.assetid: 90fd0cef-9145-4de6-91d4-6c881df39d6e
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b9c283d4b07458368a4ea5f143dc83bf13453302
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99912015"
---
# <a name="idebugclassfieldenumnestedenums"></a>IDebugClassField::EnumNestedEnums
Tworzy moduł wyliczający dla zagnieżdżonych modułów wyliczających tej klasy.

## <a name="syntax"></a>Składnia

```cpp
HRESULT EnumNestedEnums(
    IEnumDebugFields** ppEnum
);
```

```csharp
int EnumNestedEnums(
    out IEnumDebugFields ppEnum
);
```

## <a name="parameters"></a>Parametry
`ppEnum`\
określoną Zwraca obiekt [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) reprezentujący listę zagnieżdżonych wyliczeń. Zwraca wartość null, jeśli nie ma żadnych zagnieżdżonych wyliczeń.

## <a name="return-value"></a>Wartość zwracana
Jeśli to się powiedzie, zwraca S_OK lub zwraca S_FALSE, jeśli nie ma zagnieżdżonych modułów wyliczających. W przeciwnym razie zwraca kod błędu.

## <a name="remarks"></a>Uwagi
Każdy element wyliczenia jest obiektem [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) opisującym Wyliczenie zagnieżdżone.

Wyliczenie zadeklarowane wewnątrz klasy jest uznawane za zagnieżdżone Wyliczenie. Na przykład:

```
class RootClass {
    enum NestedEnum { EnumValue = 0 }
};
```

`EnumNestedEnums`Metoda zwróci obiekt [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) , który zawiera jeden obiekt [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) , który reprezentuje `NestedEnum` Wyliczenie.

## <a name="see-also"></a>Zobacz też
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
