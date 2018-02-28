---
title: IDebugNoSymbolsEvent2 | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugNoSymbolsEvent2 interface
ms.assetid: f6fb6388-47f6-4385-9ad5-95d62f9a7592
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4c103cdfec8d93c8b43106d5e2b3757750ffda70
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="idebugnosymbolsevent2"></a>IDebugNoSymbolsEvent2
Sygnały [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] debugera interfejsu użytkownika z ostrzeżeniem, że symboli nie można zlokalizować dla uruchomionego pliku wykonywalnego.  
  
## <a name="syntax"></a>Składnia  
  
```  
IDebugNoSymbolsEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji  
 Implementowany przez aparaty debugowania i używane przez [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] debugera interfejsu użytkownika.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Zestaw: Microsoft.VisualStudio.Debugger.Interop.dll