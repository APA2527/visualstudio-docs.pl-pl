---
title: IDebugPortEx2::LaunchSuspended | Dokumentacja firmy Microsoft
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
- IDebugPortEx2::LaunchSuspended
helpviewer_keywords:
- IDebugPortEx2::LaunchSuspended
ms.assetid: 34b2cf99-2e52-4757-8969-1d12ac517ec0
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2ee2a93f10aa912ba1619342d814817c8abd5307
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42679239"
---
# <a name="idebugportex2launchsuspended"></a>IDebugPortEx2::LaunchSuspended
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [IDebugPortEx2::LaunchSuspended](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportex2-launchsuspended).  
  
Uruchamia plik wykonywalny.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT LaunchSuspended(   
   LPCOLESTR        pszExe,  
   LPCOLESTR        pszArgs,  
   LPCOLESTR        pszDir,  
   BSTR             bstrEnv,  
   DWORD            hStdInput,  
   DWORD            hStdOutput,  
   DWORD            hStdError,  
   IDebugProcess2** ppPortProcess  
);  
```  
  
```csharp  
int LaunchSuspended(   
   string             pszExe,  
   string             pszArgs,  
   string             pszDir,  
   string             bstrEnv,  
   uint               hStdInput,  
   uint               hStdOutput,  
   uint               hStdError,  
   out IDebugProcess2 ppPortProcess  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszExe`  
 [in] Nazwa pliku wykonywalnego do uruchomienia. Może to być pełna ścieżka lub względna do katalogu roboczego, określone w `pszDir` parametru.  
  
 `pszArgs`  
 [in] Argumenty do przekazania do pliku wykonywalnego. Może być wartością null, jeśli nie wymaga argumentów.  
  
 `pszDir`  
 [in] Nazwa katalogu roboczego używane przez plik wykonywalny. Może być wartością null, jeśli katalog roboczy nie jest wymagana.  
  
 `bstrEnv`  
 [in] Blok środowiska ciągów zakończony znakiem null, następuje dodatkowe terminator o wartości NULL.  
  
 `hStdInput`  
 [in] Dojście do alternatywnego strumienia wejściowego. Może być równa 0, jeśli przekierowanie nie jest wymagana.  
  
 `hStdOutput`  
 [in] Dojście do strumienia wyjściowego alternatywne. Może być równa 0, jeśli przekierowanie nie jest wymagana.  
  
 `hStdError`  
 [in] Dojście do błędu alternatywnego strumienia wyjściowego. Może być równa 0, jeśli przekierowanie nie jest wymagana.  
  
 `ppPortProcess`  
 [out] Zwraca [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) obiekt, który reprezentuje uruchomienie procesu.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Ta metoda powinna Uruchom proces, że jest zawieszony, a nie działa każdy kod. [ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md) metoda jest wywoływana, aby wznowić proces.  
  
 Program można także uruchomić z aparatu debugowania. Aby uzyskać więcej informacji, zobacz [uruchamianie programu](../../../extensibility/debugger/launching-a-program.md).  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)   
 [Uruchamianie programu](../../../extensibility/debugger/launching-a-program.md)

