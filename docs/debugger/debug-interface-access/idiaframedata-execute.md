---
title: 'IDiaFrameData:: Execute | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::execute method
ms.assetid: 7a6c7d03-1ff1-4059-bd54-5f407eeebc26
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 00cc4ba3f7ba3f54df4dd8687996fa72d27e91fb
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99855999"
---
# <a name="idiaframedataexecute"></a>IDiaFrameData::execute
Wykonuje odwinięcia stosu i zwraca wyniki w interfejsie przeszukiwania stosu.

## <a name="syntax"></a>Składnia

```C++
HRESULT execute ( 
   IDiaStackWalkFrame* frame
);
```

#### <a name="parameters"></a>Parametry
 `frame`

podczas Obiekt [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md) , który przechowuje stan rejestrów ramek.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca kod błędu. W poniższej tabeli przedstawiono możliwe wartości zwracane dla tej metody.

|Wartość|Opis|
|-----------|-----------------|
|E_DIA_INPROLOG|Nie można wykonać ramki stosu w kodzie prologu.|
|E_DIA_SYNTAX|Napotkano błąd analizy w programie ramowym.|
|E_DIA_FRAME_ACCESS|Nie można uzyskać dostępu do rejestrów lub pamięci.|
|E_DIA_VALUE|Wystąpił błąd podczas obliczania wartości (na przykład dzielenia przez zero).|

## <a name="remarks"></a>Uwagi
 Ta metoda jest wywoływana podczas debugowania w celu odwinięcia stosu. Obiekt [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md) jest implementowany przez aplikację kliencką w celu otrzymywania aktualizacji rejestrów i dostarczania metod używanych przez `execute` metodę.

## <a name="see-also"></a>Zobacz też
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)