---
title: IDebugMethodField::EnumAllLocals | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMethodField::EnumAllLocals
helpviewer_keywords: IDebugMethodField::EnumAllLocals method
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2c8208b0d803dc5cbf6333f15cbda5b0f34bbd16
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmethodfieldenumalllocals"></a>IDebugMethodField::EnumAllLocals
Tworzy moduł wyliczający dla wszystkich zmiennych lokalnych metody, włącznie z wygenerowanymi przez kompilator wewnętrznie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EnumAllLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumAllLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pAddress`  
 [in] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) obiekt reprezentujący adres debugowania, w metodzie określonym zakresie lub kontekście.  
  
 `ppLocals`  
 [out] Zwraca [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) obiekt reprezentujący listę wszystkich zmiennych lokalnych w określonym zakresie; w przeciwnym razie zwraca wartość null, wskazując nie zmiennych lokalnych.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca wartość S_OK lub zwraca wartości S_FALSE, jeśli nie ma żadnych zmiennych lokalnych. W przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Wyliczane są tylko zmienne zdefiniowane w bloku, zawierający adres danego debugowania. Ta metoda obejmuje zmiennych lokalnych generowane przez kompilator. Jeśli wszystkie, które jest wymagane są lokalne jawnie zdefiniowane w źródle wywołania [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) metody.  
  
 Metoda może zawierać wielu kontekstów lub bloków zakresu.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)