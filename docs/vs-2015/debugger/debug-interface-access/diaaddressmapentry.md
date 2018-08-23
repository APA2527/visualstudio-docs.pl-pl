---
title: Diaaddressmapentry — | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a6d5075917c49be66d030846cdc186b0fa5e50a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685508"
---
# <a name="diaaddressmapentry"></a>DiaAddressMapEntry
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [diaaddressmapentry —](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/diaaddressmapentry).  
  
W tym artykule opisano wpis z mapy adresów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
struct DiaAddressMapEntry {   
   DWORD rva,  
   DWORD rvaTo  
};  
```  
  
## <a name="elements"></a>Elementy  
 `rva`  
 Względny adres wirtualny (RVA) obraz A.  
  
 `rvaTo`  
 Względny adres wirtualny `rva` jest mapowany na obrazie B.  
  
## <a name="remarks"></a>Uwagi  
 Mapa adres udostępnia tłumaczenia z jednego obrazu układu (A) do innego (B). Tablica `DiaAddressMapEntry` struktur, posortowane według `rva` definiuje mapę adresu.  
  
 Do translacji adresów `addrA`, na ilustracji A adres `addrB`, na ilustracji B, wykonaj następujące czynności:  
  
1.  Wyszukaj mapy dla wpisu, `e`, za pomocą największej `rva` mniejsze niż lub równe `addrA`.  
  
2.  Ustaw `delta = addrA – e.rva`.  
  
3.  Ustaw `addrB = e.rvaTo + delta`.  
  
 Tablica `DiaAddressMapEntry` struktury jest przekazywany do [idiaaddressmap::set_addressmap —](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) metody.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: dia2.h  
  
## <a name="see-also"></a>Zobacz też  
 [Wyliczenia i struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)



