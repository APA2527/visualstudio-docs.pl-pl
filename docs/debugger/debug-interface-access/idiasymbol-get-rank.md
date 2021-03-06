---
title: 'IDiaSymbol:: get_rank | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_rank method
ms.assetid: 14cc9c4b-a5ec-414a-b01f-4a142c17b7cc
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: da00422a5a12a12f99cf706b0bf7bb2ce623d76f
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99853682"
---
# <a name="idiasymbolget_rank"></a>IDiaSymbol::get_rank
Pobiera rangę (liczbę wymiarów) Pascal wielowymiarowej tablicy.

## <a name="syntax"></a>Składnia

```C++
HRESULT get_rank ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

określoną Zwraca liczbę wymiarów w wielowymiarowej tablicy Pascal.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca `S_FALSE` lub kod błędu.

> [!NOTE]
> Wartość zwracana przez `S_FALSE` oznacza, że właściwość nie jest dostępna dla symbolu.

## <a name="remarks"></a>Uwagi
 Ranga odnosi się do liczby wymiarów w tablicy, w której jest zadeklarowana tablica `myarray[1,2,3]` . Ten przykład ma rangę 3 i 3 Wymiary. Ranga nie ma zastosowania do języka C++, który używa koncepcji tablicy tablic dla każdego wymiaru (to oznacza, `myarray[1][2][3]` ).

## <a name="see-also"></a>Zobacz też
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)