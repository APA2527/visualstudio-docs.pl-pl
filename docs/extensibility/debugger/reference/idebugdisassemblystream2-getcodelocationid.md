---
title: IDebugDisassemblyStream2::GetCodeLocationId | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDisassemblyStream2::GetCodeLocationId
helpviewer_keywords: IDebugDisassemblyStream2::GetCodeLocationId
ms.assetid: 567adfb8-2f54-499a-a027-e4ecb82277ef
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2757130ec88cee8d9bdfe28008a8e19834f9f8fb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="idebugdisassemblystream2getcodelocationid"></a>IDebugDisassemblyStream2::GetCodeLocationId
Zwraca identyfikator lokalizacji kodu dla kontekstu określonego kodu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCodeLocationId(   
   IDebugCodeContext2* pCodeContext,  
   UINT64*             puCodeLocationId  
);  
```  
  
```csharp  
int GetCodeLocationId(   
   IDebugCodeContext2 pCodeContext,  
   out ulong          puCodeLocationId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCodeContext`  
 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) obiekt ma zostać przekonwertowany na identyfikator.  
  
 `puCodeLocationId`  
 [out] Zwraca identyfikator lokalizacji kodu. Zobacz uwagi.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu. Zwraca `E_CODE_CONTEXT_OUT_OF_SCOPE` jeśli kontekst kodu jest prawidłowy, ale poza zakresem.  
  
## <a name="remarks"></a>Uwagi  
 Identyfikator lokalizacji kodu jest specyficzne dla aparatu debugowania (DE), obsługa dezasemblacji. Ten identyfikator lokalizacji jest używana wewnętrznie przez DE śledzenie pozycji w kodzie i jest zwykle adres lub przesunięcie określonego rodzaju. Jedynym wymaganiem jest to, że jeśli kontekst kodu z jednej lokalizacji jest mniejsza niż kontekst kodu w innej lokalizacji, a następnie odpowiedni kod lokalizacji identyfikator pierwszego kontekst kodu również musi być mniejsza niż identyfikator lokalizacji kodu drugi kontekst kodu.  
  
 Aby pobrać kontekst kodu identyfikatora lokalizacji kodu, należy wywołać [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md) metody.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)