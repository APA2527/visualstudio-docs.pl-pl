---
title: Metoda IActiveScriptSiteUIControl::GetUIBehavior | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 9a944335-856a-4c6b-b2bc-8872542941b7
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 917fe2ca3328b0a177e517ac2a7e721676f32cf2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2017
ms.locfileid: "24793600"
---
# <a name="iactivescriptsiteuicontrolgetuibehavior-method"></a>Metoda IActiveScriptSiteUIControl::GetUIBehavior
Pobiera [wyliczenie SCRIPTUICHANDLING](../../winscript/reference/scriptuichandling-enumeration.md) reprezentujący sposób obsługi formantów interfejsu użytkownika.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetUIBehavior(     [in] SCRIPTUICITEM UicItem,     [out] SCRIPTUICHANDLING * pUicHandling );   
```  
  
#### <a name="parameters"></a>Parametry  
 `UicItem`  
 Typ formantu.  
  
 `pUicHandling`  
 Powinien zostać obsłużony sposób formantu.