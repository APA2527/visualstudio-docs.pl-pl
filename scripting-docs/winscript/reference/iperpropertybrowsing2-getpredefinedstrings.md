---
title: IPerPropertyBrowsing2::GetPredefinedStrings | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.GetPredefinedStrings
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::GetPredefinedStrings
ms.assetid: d2fa30f7-a566-4dbd-8b47-ffdc00419771
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e07d52eca9434acc7e54f3b35b111cf12af0a871
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794929"
---
# <a name="iperpropertybrowsing2getpredefinedstrings"></a>IPerPropertyBrowsing2::GetPredefinedStrings
Umożliwia obiekt wywołujący, aby wypełnić pole listy zliczona tablicy wskaźników ciągów, które reprezentują potencjalnych wartości dla tej właściwości.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetPredefinedStrings(  
   DISPID  dispid,  
   CALPOLESTR*  pCaStrings,  
   CADWORD*  pCaCookies  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dispid`  
 [in] Identyfikator wysyłania właściwości, dla którego obiekt wywołujący żąda lista ciągów.  
  
 `pCaStrings`  
 [out] Wskaźnik do struktura przydzielone przez obiekt wywołujący, są one uwzględniane tablicy, która zawiera element count i adres przydzielone Metoda tablicy wskaźników ciągu. Jeśli metoda nie powiedzie się, nie jest rezerwowana pamięć, a zawartość struktury jest niezdefiniowany.  
  
 `pCaCookies`  
 [out] Wskaźnik do struktury tablicy przydzielone przez obiekt wywołujący, są one uwzględniane zawierający element count i adres przydzielone Metoda tablicy dane DWORD. Jeśli metoda nie powiedzie się, nie jest rezerwowana pamięć, a zawartość struktury jest niezdefiniowany.  
  
## <a name="return-value"></a>Wartość zwracana  
 Zwraca prawidłową `HRESULT`, zwykle `S_OK`.  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejs IPerPropertyBrowsing2 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)