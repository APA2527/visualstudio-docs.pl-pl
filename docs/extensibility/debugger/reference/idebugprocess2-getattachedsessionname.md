---
title: IDebugProcess2::GetAttachedSessionName | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 34e404fe33858c1db7d9dfb103df7b4e0bb9fb91
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
Pobiera nazwę sesji, która jest debugowanie tego procesu. IDE można wyświetlić te informacje użytkownikowi, który jest debugowanie określonego procesu na określonym komputerze.  
  
> [!NOTE]
>  Ta metoda jest przestarzała i jej wdrożenia należy zawsze zwracają `E_NOTIMPL`.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetAttachedSessionName(  
   BSTR* pbstrSessionName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrSessionName`  
  
## <a name="return-value"></a>Wartość zwracana  
 Ta metoda zawsze powinna zwrócić `E_NOTIMPL`.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)