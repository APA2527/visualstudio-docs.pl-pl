---
title: Rejestrowanie niestandardowego aparat debugowania | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, registering
ms.assetid: 9984cd3d-d34f-4662-9ace-31766499abf5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c3203382b33184edf5618daecd9d3dc9102e2ca6
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251653"
---
# <a name="register-a-custom-debug-engine"></a>Rejestrowanie niestandardowego aparatu debugowania
Aparat debugowania musi zarejestrować się jako fabrykę klas następujących konwencji COM także zarejestrować przy użyciu programu Visual Studio za pomocą podklucza rejestru programu Visual Studio.  
  
> [!NOTE]
>  Można znaleźć przykład sposobu rejestrowania aparat debugowania, w tym przykładzie TextInterpreter powstała jako część [samouczek: tworzenie aparatu debugowania, korzystając z modelu COM ATL](http://msdn.microsoft.com/en-us/9097b71e-1fe7-48f7-bc00-009e25940c24).  
  
## <a name="dll-server-process"></a>Proces serwera biblioteki DLL  
 Aparat debugowania jest zazwyczaj konfigurowane w jego własnej biblioteki DLL jako serwera COM. W efekcie aparat debugowania należy zarejestrować identyfikator CLSID jego fabryki klas z modelem COM programu Visual Studio do niego dostęp. Następnie aparat debugowania musi zarejestrować się przy użyciu programu Visual Studio można ustanowić właściwości (w przeciwnym razie znane jako metryki) debugowania aparatu obsługuje. Wybór metryki zapisywane do podklucza rejestru programu Visual Studio, zależy od funkcje, które obsługuje aparatu debugowania.  
  
 [Pomocnicy zestawu SDK do debugowania](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) opisuje nie tylko w lokalizacji rejestru należy zarejestrować aparatu debugowania; opisano w nim również *dbgmetric.lib* biblioteki, która zawiera wiele przydatnych funkcji i deklaracje dla deweloperów C++, które manipulowanie łatwiejsze rejestru.  
  
### <a name="example"></a>Przykład  
 Poniższy przykład (z próbki TextInterpreter) pokazuje, jak używać `SetMetric` — funkcja (z *dbgmetric.lib*), aby zarejestrować aparatu debugowania za pomocą programu Visual Studio. Metryki są przekazywane są również określone w *dbgmetric.lib*.  
  
> [!NOTE]
>  TextInterpreter to aparat debugowania podstawowego; nieskonfigurowanym wypychaniem — i dlatego nie rejestruje — inne funkcje. Bardziej kompletny aparat debugowania miałby całą listę `SetMetric` wywołania lub ich odpowiednika obsługuje jeden dla każdej funkcji aparatu debugowania.  
  
```  
// Define base registry subkey to Visual Studio.  
static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0";  
  
HRESULT CTextInterpreterModule::RegisterServer(BOOL bRegTypeLib, const CLSID * pCLSID)  
{  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricName, L"Text File", false, strRegistrationRoot);  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricCLSID, CLSID_Engine, false, strRegistrationRoot);  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricProgramProvider, CLSID_MsProgramProvider, false, strRegistrationRoot);  
  
    return base::RegisterServer(bRegTypeLib, pCLSID);  
}  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Tworzenie niestandardowego aparatu debugowania](../../extensibility/debugger/creating-a-custom-debug-engine.md)   
 [Pomocnicy zestawu SDK do debugowania](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Samouczek: Tworzenie aparatu debugowania, korzystając z modelu COM ATL](http://msdn.microsoft.com/en-us/9097b71e-1fe7-48f7-bc00-009e25940c24)