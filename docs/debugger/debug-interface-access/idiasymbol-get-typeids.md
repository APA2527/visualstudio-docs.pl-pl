---
title: IDiaSymbol::get_typeIds | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_typeIds method
ms.assetid: 5166e647-fde5-4efe-92bf-77f8ae3fbc9b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6f1ad4aae54096ea2fdcbcac1a68d32fc3b386ad
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
ms.locfileid: "31470673"
---
# <a name="idiasymbolgettypeids"></a>IDiaSymbol::get_typeIds
Pobiera tablicę wartości identyfikatora typu kompilatora specyficzne dla tego symbolu.  
  
## <a name="syntax"></a>Składnia  
  
```C++  
HRESULT get_typeIds (   
   DWORD  cTypeIds,  
   DWORD* pcTypeIds,  
   DWORD  typeIds[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cTypeIds`  
 [in] Rozmiar buforu do przechowywania danych.  
  
 `pcTypeIds`  
 [out] Zwraca liczbę `typeIds` zapisywane, lub jeśli `typeIds` jest `NULL`, następnie łączna liczba dostępnych identyfikatorów typu.  
  
 `typeIds[]`  
 [out] Tablica, która ma zostać wypełnione identyfikatory typów.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca `S_FALSE` lub kod błędu.  
  
> [!NOTE]
>  Zwracana wartość `S_FALSE` oznacza, że właściwość nie jest dostępna symbolu.  
  
## <a name="see-also"></a>Zobacz też  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)