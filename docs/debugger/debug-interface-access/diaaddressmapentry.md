---
title: DiaAddressMapEntry — | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 05475d2e6d48e7a8dacea834e5d7ca18c71d3260
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99857308"
---
# <a name="diaaddressmapentry"></a>DiaAddressMapEntry
Opisuje wpis w mapie adresowej.

## <a name="syntax"></a>Składnia

```C++
struct DiaAddressMapEntry {
    DWORD rva,
    DWORD rvaTo
};
```

## <a name="elements"></a>Elementy
`rva` Względny adres wirtualny (RVA) w obrazie A.

`rvaTo` Względny adres wirtualny `rva` jest mapowany na obraz B.

## <a name="remarks"></a>Uwagi
Mapa adresów zapewnia tłumaczenie z jednego układu obrazu (A) na inny (B). Tablica `DiaAddressMapEntry` struktur posortowana według `rva` definicji mapowania adresów.

Aby przetłumaczyć adres, `addrA` w obrazie A na adres, `addrB` w obrazie B wykonaj następujące czynności:

1. Przeszukaj mapę dla wpisu, `e` z największą `rva` mniejszą lub równą `addrA` .

2. Ustaw `delta = addrA - e.rva` .

3. Ustaw `addrB = e.rvaTo + delta` .

    Tablica `DiaAddressMapEntry` struktur jest przenoszona do metody [IDiaAddressMap:: set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) .

## <a name="requirements"></a>Wymagania
Nagłówek: dia2. h

## <a name="see-also"></a>Zobacz też
- [Wyliczenia i struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)
