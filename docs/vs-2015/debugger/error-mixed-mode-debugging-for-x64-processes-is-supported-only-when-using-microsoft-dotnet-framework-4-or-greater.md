---
title: 'Błąd: Trybu mieszanego debugowania x64 procesów jest obsługiwana tylko w przypadku korzystania z programu Microsoft .NET Framework 4 lub nowszego | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: e4b0216c-7006-4832-883f-08e982ba8d3f
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82440d378e34c5808e9bcb250172f6c1abfbfdf6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49239242"
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>Błąd: debugowanie w trybie mieszanym dla procesów x64 jest obsługiwane tylko w przypadku korzystania z programu Microsoft .NET Framework 4 lub nowszej wersji
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Aby debugować kod mieszany natywnych i zarządzanych w procesie 64-bitowym, konieczne jest posiadanie [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] w wersji 4. Debugowanie trybu mieszanego procesów 64-bitowe o [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] w wersji wcześniejszej niż 4 nie jest obsługiwane.  
  
### <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Wykonaj jedną z następujących czynności:  
  
    -   Uaktualnij swoje [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] do wersji 4.  
  
    -   Twórz 32-bitowej wersji aplikacji do debugowania.  
  
## <a name="see-also"></a>Zobacz też  
 [Konfigurowanie narzędzi zdalnych na urządzeniu](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)



