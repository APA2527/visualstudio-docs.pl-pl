---
title: IDiaLoadCallback2::RestrictReferencePathAccess | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLoadCallback2::RestrictReferencePathAccess method
ms.assetid: e20cb45c-0360-4ff0-a92c-b1b6f76d6e85
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4800ab08f1fba65f3b40564a789630f370d21ac1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="idialoadcallback2restrictreferencepathaccess"></a>IDiaLoadCallback2::RestrictReferencePathAccess
Określa, czy wyszukiwanie plik PDB jest dozwolone w ścieżce, w którym znajduje się plik .exe.  
  
## <a name="syntax"></a>Składnia  
  
```C++  
HRESULT RestrictReferencePathAccess();  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Inne niż powrotnych kodu `S_OK` zapobiegające szuka pliku .pdb w ścieżce, w którym znajduje się plik .exe.  
  
## <a name="see-also"></a>Zobacz też  
 [Idialoadcallback2 —](../../debugger/debug-interface-access/idialoadcallback2.md)