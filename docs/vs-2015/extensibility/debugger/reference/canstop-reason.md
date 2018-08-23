---
title: CANSTOP_REASON | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CANSTOP_REASON
helpviewer_keywords:
- CANSTOP_REASON enumeration
ms.assetid: 6da944eb-36cd-4a8c-8d71-544c775cfcc1
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6ea8242e4c7bdd820dd30cfb2c86cde60cda8bcd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685233"
---
# <a name="canstopreason"></a>CANSTOP_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CANSTOP_REASON](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/canstop-reason).  
  
Używany do określenia, jeśli program zatrzymać wykonywanie po osiągnięciu określonego punktu w realizacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
typedef DWORD CANSTOP_REASON;  
```  
  
```csharp  
public enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
```  
  
## <a name="members"></a>Elementy członkowskie  
 CANSTOP_ENTRYPOINT  
 Określa punkt wejścia w danym programu.  
  
 CANSTOP_STEPIN  
 Określa, przechodzenie krok po kroku do funkcji.  
  
## <a name="remarks"></a>Uwagi  
 Przekazywany jako argument do [getreason —](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) metodę, aby potwierdzić z sesji debugowania Manager (SDM), jeśli ma nic złego zatrzymać po osiągnięciu punktu wejścia programu, lub po przejściu do funkcji lub metody.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Wyliczenia](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Getreason —](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)

