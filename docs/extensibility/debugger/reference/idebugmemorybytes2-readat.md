---
title: IDebugMemoryBytes2::ReadAt | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMemoryBytes2::ReadAt
helpviewer_keywords:
- IDebugMemoryBytes2::ReadAt method
- ReadAt method
ms.assetid: b413684d-4155-4bd4-ae30-ffa512243b5f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3e3989ef8c79e4304e3bda3e99418da1973e6e0a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49912951"
---
# <a name="idebugmemorybytes2readat"></a>IDebugMemoryBytes2::ReadAt
Odczytuje sekwencji bajtów, zaczynając od danej lokalizacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ReadAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory,  
   DWORD*                pdwRead,  
   DWORD*                pdwUnreadable  
);  
```  
  
```csharp  
int ReadAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory,  
   out uint             pdwRead,  
   ref uint             pdwUnreadable  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pStartContext`  
 [in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) obiekt, który określa, gdzie należy rozpocząć odczyt bajtów.  
  
 `dwCount`  
 [in] Liczba bajtów do odczytania. Również określa długość `rgbMemory` tablicy.  
  
 `rgbMemory`  
 [out w] Tablica wypełniona Bajty odczytane.  
  
 `pdwRead`  
 [out] Zwraca liczbę bajtów ciągłych odczytane.  
  
 `pdwUnreadable`  
 [out w] Zwraca liczbę bajtów nie można go odczytać. Może być wartością null, jeśli klient jest zainteresowany liczbę bajtów nie można go odczytać.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca wartość S_OK; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli wymagane są 100 bajtów i 50 pierwszych można odczytać, następnych 20 są nieczytelne i pozostałe 30 do odczytu, Metoda ta zwraca:  
  
 *`pdwRead` = 50  
  
 *`pdwUnreadable` = 20  
  
 W tym przypadku ponieważ `*pdwRead + *pdwUnreadable < dwCount`, obiekt wywołujący musi wywoływania dodatkowych odczytu pozostałe bajty 30 oryginalnego 100, żądane i [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) obiekt przekazany w `pStartContext` parametru musi być zaawansowane za 70.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)