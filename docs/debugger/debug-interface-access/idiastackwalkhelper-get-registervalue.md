---
title: IDiaStackWalkHelper::get_registerValue | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::get_registerValue method
ms.assetid: 46ac5eee-73a3-44a1-8635-6c58ba193cb6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af5f68aaf5b2caed50d28a1a53022a095d478e60
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49887920"
---
# <a name="idiastackwalkhelpergetregistervalue"></a>IDiaStackWalkHelper::get_registerValue
Pobiera wartość rejestru.  
  
## <a name="syntax"></a>Składnia  
  
```C++  
HRESULT get_registerValue (   
   DWORD      index,  
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `index`  
 [in] Wartość z zakresu od [cv_hreg_e — wyliczenie](../../debugger/debug-interface-access/cv-hreg-e.md) wyliczenie opisujące który Zarejestruj, aby pobrać wartość z.  
  
 `pRetVal`  
 [out] Zwraca bieżącą wartość rejestru.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Niezależnie od rozmiaru `pRetVal` parametru, co rejestru zwykle zawiera jedynie implementację powinny być przechowywane. Na przykład rejestr 8-bitowy przechowuje tylko najniższy 8 bitów danej wartości. Ta wartość 8-bitową można rozszerzyć, aby 64-bitowego, gdy zwracany z tej metody.  
  
## <a name="see-also"></a>Zobacz też  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [CV_HREG_e, wyliczenie](../../debugger/debug-interface-access/cv-hreg-e.md)