---
title: 'IDebugObject2:: isuserdata | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::IsUserData
helpviewer_keywords:
- IDebugObject2::IsUserData method
ms.assetid: 6ffa0d0e-f742-496d-acc7-db74c248bc45
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ce4a7035ac3786f0cc1644e2ebbb0c142167e2b0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "80726089"
---
# <a name="idebugobject2isuserdata"></a>IDebugObject2::IsUserData
Określa, czy obiekt reprezentuje dane użytkownika.

## <a name="syntax"></a>Składnia

```cpp
HRESULT IsUserData(
   BOOL* pfUser
);
```

```csharp
int IsUserData(
   out int pfUser
);
```

## <a name="parameters"></a>Parametry
`pfUser`\
określoną Zwraca wartość `TRUE` różną od zera (), jeśli obiekt reprezentuje dane użytkownika; zero ( `FALSE` ), jeśli nie.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca S_OK; w przeciwnym razie zwraca kod błędu.

## <a name="remarks"></a>Uwagi
 Dane użytkownika to każdy obiekt, który jest częścią modułu wyznaczono jako JustMyCode (opcja konfigurowalną przez użytkownika, która oznacza moduł jako kod użytkownika i dlatego widoczny w śladzie stosu).

## <a name="see-also"></a>Zobacz też
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)
