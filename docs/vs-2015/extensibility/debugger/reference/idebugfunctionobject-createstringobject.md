---
title: IDebugFunctionObject::CreateStringObject | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugFunctionObject::CreateStringObject
helpviewer_keywords:
- IDebugFunctionObject::CreateStringObject method
ms.assetid: fd6070ab-07d4-4ea1-8d71-b16592d6f1a7
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5d8fa1f17031d6b59156a1e4ce807cc48846f2bc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49888180"
---
# <a name="idebugfunctionobjectcreatestringobject"></a>IDebugFunctionObject::CreateStringObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tworzy obiekt ciągu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT CreateStringObject(   
   LPCOLESTR      pcstrString,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateStringObject(  
   string      pcstrString,   
   out IDebugObject ppOjbect  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pcstrString`  
 [in] Wartość ciągu z obiektem ciągu.  
  
 `ppObject`  
 [out] Zwraca [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) obiekt, który reprezentuje obiekt ciągu nowo utworzony.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca wartość S_OK; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Wywołaj tę metodę, aby utworzyć obiekt, który reprezentuje ciąg, który jest parametr do funkcji, która jest reprezentowana przez [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) interfejsu.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)

