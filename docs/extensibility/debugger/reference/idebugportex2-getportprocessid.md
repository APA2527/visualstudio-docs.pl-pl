---
title: IDebugPortEx2::GetPortProcessId | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortEx2::GetPortProcessId
helpviewer_keywords:
- IDebugPortEx2::GetPortProcessId
ms.assetid: be85be66-47e6-415f-b0ca-24599aa5f13c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 40135e1b6f9eee192dfa35ac7cae6a80a693f840
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49818968"
---
# <a name="idebugportex2getportprocessid"></a>IDebugPortEx2::GetPortProcessId
Pobiera identyfikator procesu samego portu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetPortProcessId (   
   DWORD* pdwProcessId  
);  
```  
  
```csharp  
int GetPortProcessId (   
   out uint pdwProcessId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwProcessId`  
 [out] Zwraca identyfikator procesu fizyczny port sam.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 W środowisku uruchomieniowym Win32 na przykład tej metody zwykle wywołuje funkcję Win32 `GetCurrentProcessId` można pobrać identyfikatora procesu fizycznych.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)