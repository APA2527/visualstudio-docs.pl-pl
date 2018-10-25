---
title: Porty | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ports
- debugging [Debugging SDK], ports
ms.assetid: 1d7f3aa7-7eff-4cab-bc53-0a566b1a9363
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f54ec931bc34f854d1c9f1a85961f5af65a56264
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49936345"
---
# <a name="ports"></a>Porty
W architekturze debugera *portu*:  
  
- Kontener dla zestawu procesów działa na serwerze. Na przykład port może reprezentować połączenie urządzenia z systemem Windows CE, za pomocą kabla szeregowego lub maszyną sieciowych bez DCOM. Jeden port specjalny port lokalny, nazywany zawiera wszystkie procesy, które są uruchomione na komputerze lokalnym.  
  
- Można zidentyfikować sama nazwa lub identyfikator.  
  
- Można wyliczyć wszystkie procesy uruchomione na porcie uruchomienie i zakończenie tych procesów.  
  
- Jest reprezentowany przez [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) interfejs, który jest tworzony przez przekazanie [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) argument [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md).  
  
  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] dostarcza domyślnego portu, obsługująca wszystkich oparte na Windows procesów, natywnych i zarządzanych. Port niestandardowy można ustawić dla połączeń przy użyciu urządzeń zewnętrznych, które nie są oparte na Windows. Podać takie niestandardowych portów, należy skonfigurować dostawcy niestandardowego portu.  
  
## <a name="see-also"></a>Zobacz także  
 [Serwery](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [Procesy](../../extensibility/debugger/processes.md)   
 [Pojęcia dotyczące debugera](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)   
 [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)