---
title: Idiasymbol::get_isltcg — | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isLTCG method
ms.assetid: 5f7f05b8-6b71-4958-9e1e-e4924ef9c59b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7eb1d7308eb03d396ca8a08f915a294ec1debd82
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49877741"
---
# <a name="idiasymbolgetisltcg"></a>IDiaSymbol::get_isLTCG
Pobiera flagę określającą, czy [compiland —](../../debugger/debug-interface-access/compiland.md) została połączona z przełącznikiem konsolidatora [opcję/LTCG (Generowanie kodu Link-time)](/cpp/build/reference/ltcg-link-time-code-generation), która pomaga w optymalizacji całego programu. Ten przełącznik dotyczy tylko kodu zarządzanego.  
  
## <a name="syntax"></a>Składnia  
  
```C++  
HRESULT get_iSLTCG(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pFlag  
 [out] Zwraca `TRUE` Jeśli `compiland` został połączony z przełącznikiem konsolidatora opcję/LTCG; w przeciwnym razie zwraca `FALSE`.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca `S_FALSE` albo kod błędu.  
  
> [!NOTE]
>  Zwracana wartość wynosząca `S_FALSE` oznacza, że właściwość nie jest dostępna dla symbolu.  
  
## <a name="requirements"></a>Wymagania  
  
|Wymaganie|Opis|  
|-----------------|-----------------|  
|Nagłówek:|dia2.h|  
|Wersja:|DIA SDK w wersji 8.0|  
  
## <a name="see-also"></a>Zobacz też  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)