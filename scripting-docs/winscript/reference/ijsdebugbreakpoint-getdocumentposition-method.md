---
title: IJsDebugBreakPoint::GetDocumentPosition — metoda | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJSDebugBreakPoint.GetDocumentPosition
apilocation:
- jscript9diag.dll
ms.assetid: 886df8ba-a59a-48a7-87f2-3b669e71528f
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c33751b0173626814f042fdc54a7d496b644573
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794437"
---
# <a name="ijsdebugbreakpointgetdocumentposition-method"></a>IJsDebugBreakPoint::GetDocumentPosition — Metoda
Zwraca pozycję instrukcji, gdzie został powiązany punkt przerwania.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetDocumentPosition(  
   UINT64 *pDocumentId,  
   DWORD *pCharacterOffset,  
   DWORD *pStatementCharCount  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pDocumentId`  
 [out] Unikatowy identyfikator dla dokumentu źródłowego (wskaźnik do IDebugDocumentText).  
  
 `pCharacterOffset`  
 [out] Przesunięcie znaku liczony od zera na początku skryptu.  
  
 `pStatementCharCount`  
 [out] Długość bieżącej instrukcji, która rozpoczyna się od * pCharacterOffset w znakach.  
  
## <a name="return-value"></a>Wartość zwracana  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** jscript9diag.h  
  
## <a name="see-also"></a>Zobacz też  
 [Ijsdebugbreakpoint — interfejs](../../winscript/reference/ijsdebugbreakpoint-interface.md)