---
title: IDebugExpressionEvaluator::GetMethodProperty | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugExpressionEvaluator::GetMethodProperty
helpviewer_keywords:
- IDebugExpressionEvaluator::GetMethodProperty method
ms.assetid: c394fe4d-eeb6-4feb-828c-098d84a6f1ba
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: def1f66be288574dc27af3b4685a008eb0c14ee3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630463"
---
# <a name="idebugexpressionevaluatorgetmethodproperty"></a>IDebugExpressionEvaluator::GetMethodProperty
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [IDebugExpressionEvaluator::GetMethodProperty](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty).  
  
Ta metoda pobiera obiekt właściwości, który zawiera zmienne, argumenty i inne właściwości, metody.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT GetMethodProperty(   
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   BOOL                  fIncludeHiddenLocals,  
   IDebugProperty2**     ppProperty  
);  
```  
  
```csharp  
int GetMethodProperty(  
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   int                  fIncludeHiddenLocals,   
   out IDebugProperty2  ppProperty  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pSymbolProvider`  
 [in] Dostawca symboli, które ma być używany, wyrażone jako [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) obiektu.  
  
 `pAddress`  
 [in] Adres w kodzie, wyrażone jako [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) obiektu, które powinny zostać rozwiązane do najbliższej zawierającego funkcję.  
  
 `pBinder`  
 [in] Obiekt wiążący, który ma być używany, wyrażone jako [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) obiektu.  
  
 `fIncludeHiddenLocals`  
 [in] Wartość różną od zera (`TRUE`) oznacza, że zawierają ukryte elementy lokalne; wartość zero (`FALSE`) oznacza, że Opuść ukryte elementy lokalne  
  
 `ppProperty`  
 [out] Zwraca [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) obiekt, który reprezentuje metodę.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Ukryte elementy lokalne są zwykle zmienne, które są generowane przez kompilator.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)   
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)

