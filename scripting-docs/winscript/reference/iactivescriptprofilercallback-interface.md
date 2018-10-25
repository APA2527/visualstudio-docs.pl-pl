---
title: Interfejs IActiveScriptProfilerCallback | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 76f9164b-b086-4b29-ac79-76f9c76f1d11
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2511b3e622dfa977c0ed05212203ad59fb0e71bd
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49912626"
---
# <a name="iactivescriptprofilercallback-interface"></a>Interfejs IActiveScriptProfilerCallback
Udostępnia metody, które są używane przez silnik wykonywania skryptów, aby powiadomić obiekt profiler, po wystąpieniu zdarzenia. Ten interfejs jest implementowany przez obiekt profiler.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md)|Wywoływane w celu zainicjowania obiektu profiler, zawsze wtedy, gdy rozpoczęto profilowanie na silnik wykonywania skryptów.|  
|[IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)|Wywołuje się, by bezpłatnych i wersji obiektu profilera po każdym zatrzymaniu profilowania na silnik wykonywania skryptów.|  
|[IActiveScriptProfilerCallback::ScriptCompiled](../../winscript/reference/iactivescriptprofilercallback-scriptcompiled.md)|Powiadamia program profilujący, że obiekt, który aparat skryptów skompilowany skrypt.|  
|[IActiveScriptProfilerCallback::FunctionCompiled](../../winscript/reference/iactivescriptprofilercallback-functioncompiled.md)|Powiadamia program profilujący, że obiekt, który aparat skryptów napotkał funkcję, podczas kompilacji skryptu.|  
|[IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)|Powiadamia obiekt profiler, który ma wykonać wywołanie funkcji, która nie jest wywołaniem do modelu DOM (Document Object) silnik wykonywania skryptów.|  
|[IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)|Powiadamia program profilujący obiekt czy aparat skryptów zakończono wykonywanie funkcji wywołaniu, które nie jest wywołanie DOM.|  
  
## <a name="remarks"></a>Uwagi  
 Powiadomienie o wywołania funkcji do modelu DOM (Document Object) są dostarczane przez [interfejs IActiveScriptProfilerCallback2](../../winscript/reference/iactivescriptprofilercallback2-interface.md).  
  
> [!NOTE]
>  Dodanie możliwości do uruchamiania i zatrzymywania profilowania, gdy skrypt jest uruchamiany, wywołaj następujące metody. Korzystając z tych metod, można uzyskać pełny stos wywołań, jeśli [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] jest uruchomiona, uruchomienie lub zatrzymanie profilowania.  
> 
> - Wywołaj [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md) powiadomić profiler rozpoczęto profilowanie.  
>   -   Wywołaj [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md) powiadomić profiler zostanie wkrótce zatrzymania profilowania.  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy profilera aktywnego skryptu](../../winscript/reference/active-script-profiler-interfaces.md)