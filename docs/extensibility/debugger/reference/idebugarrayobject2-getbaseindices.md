---
title: 'IDebugArrayObject2:: GetBaseIndices | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetBaseIndices
- IDebugArrayObject2::GetBaseIndices
ms.assetid: 882951a2-3da0-49bf-8d1e-7daedd13ffe6
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 074bc97bab80e09d6b720d23e9d617cdfcdc6350
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99870054"
---
# <a name="idebugarrayobject2getbaseindices"></a>IDebugArrayObject2::GetBaseIndices
Pobiera indeksy podstawowe (dolne granice) dla każdego indeksu z określoną liczbą wymiarów w tablicy.

## <a name="syntax"></a>Składnia

```cpp
HRESULT GetBaseIndices (
   DWORD  dwRank,
   DWORD* dwIndices
);
```

```csharp
int GetBaseIndices (
   uint       dwRank,
   out uint[] dwIndices
);
```

## <a name="parameters"></a>Parametry
`dwRank`\
podczas Liczba wymiarów (ranga) tablicy.

`dwIndices`\
określoną Indeksy podstawowe (dolne granice) dla tablicy.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca kod błędu.

## <a name="remarks"></a>Uwagi
 Na przykład ta funkcja zwróci wartość "5" dla tablicy utworzonej przy użyciu następującego kodu w języku C#:

```
int[] lengths = { 12 };
int[] lowerbounds = { 5 };
Array.CreateInstance(typeof(int), lengths, lowerbounds);
```

## <a name="see-also"></a>Zobacz też
- [IDebugArrayObject2](../../../extensibility/debugger/reference/idebugarrayobject2.md)
