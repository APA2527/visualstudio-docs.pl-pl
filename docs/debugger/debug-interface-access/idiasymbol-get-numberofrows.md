---
title: 'IDiaSymbol:: get_numberOfRows | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
ms.assetid: cf3eb110-d07f-4995-b68b-08290aa67d6f
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 9a7c083d41bce916c9ab7745a25d2fbf0450688c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99862865"
---
# <a name="idiasymbolget_numberofrows"></a>IDiaSymbol::get_numberOfRows
Pobiera liczbę wierszy w macierzy.

## <a name="syntax"></a>Składnia

```C++
HRESULT get_numberOfRows(
   DWORD* pRetVal);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

określoną Wskaźnik do obiektu `DWORD` , który przechowuje liczbę wierszy w macierzy.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca `S_FALSE` lub kod błędu.

## <a name="see-also"></a>Zobacz też
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)