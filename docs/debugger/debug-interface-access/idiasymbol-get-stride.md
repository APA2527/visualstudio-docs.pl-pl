---
title: 'IDiaSymbol:: get_stride | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
ms.assetid: 4264742a-3d91-44b9-9d14-87adbc77f0f0
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: ab4fae7c0e2816fa8c69e239cc96df82b9e805d7
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99853598"
---
# <a name="idiasymbolget_stride"></a>IDiaSymbol::get_stride
Pobiera krok macierzy lub tablicy krokowej.

## <a name="syntax"></a>Składnia

```C++
HRESULT get_stride(
   DWORD* pRetVal);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

określoną Wskaźnik do elementu `DWORD` , który zawiera krok.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca `S_FALSE` lub kod błędu.

## <a name="see-also"></a>Zobacz też
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)