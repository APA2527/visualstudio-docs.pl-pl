---
title: IDebugModule2::ReloadSymbols_Deprecated | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugModule2::ReloadSymbols
helpviewer_keywords:
- IDebugModule2::ReloadSymbols method
ms.assetid: 0f9f0133-7d58-4cd9-a6ca-1141e095749d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dcd383130c1af1765014adfa438482543c336ede
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmodule2reloadsymbolsdeprecated"></a>IDebugModule2::ReloadSymbols_Deprecated
OBSOLETE. NIE UŻYWAJ. Ponownie ładuje symbole dla tego modułu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ReloadSymbols(   
   LPCOLESTR pszUrlToSymbols,  
   BSTR*     pbstrDebugMessage  
);  
```  
  
```csharp  
int ReloadSymbols(   
   string     pszUrlToSymbols,  
   out string pbstrDebugMessage  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszUrlToSymbols`  
 [in] Ścieżka do magazynu symboli.  
  
 `pbstrDebugMessage`  
 [out] Zwraca komunikat informacyjny, takich jak stan albo komunikatu o błędzie, który jest wyświetlany po prawej stronie nazwy modułu w oknie moduły.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu. Aparat debugowania zawsze powinna zwrócić `E_FAIL`.  
  
## <a name="remarks"></a>Uwagi  
 Ta metoda nie jest już obsługiwana. Implementowanie [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md) metody zamiast tego.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)