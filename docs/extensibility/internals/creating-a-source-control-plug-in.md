---
title: Tworzenie wtyczki kontroli źródła | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- plug-ins, source control
- source control plug-ins
- source control [Visual Studio SDK], plug-ins
ms.assetid: c7e69fa4-150e-469a-a6fc-fa1260bdbb07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 361ad46c781f9e29c7c99fa4340433583571d811
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497891"
---
# <a name="create-a-source-control-plug-in"></a>Tworzenie wtyczki kontroli źródła
Visual Studio SDK zawiera zasoby, które umożliwiają dodawanie możliwości kontroli źródła [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zintegrowanego środowiska programistycznego (IDE). Dzięki temu można użyć biblioteki DLL w dodatku plug-in, który jest zgodny z interfejsu API wtyczki kontroli źródła opisane w tej dokumentacji.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Wprowadzenie](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)  
 W tym artykule opisano sposób instalowania wtyczki kontroli źródła i wyróżnienie obecnie dostępnych wersji interfejsu API wtyczki kontroli źródła.  
  
 [Architektura](../../extensibility/internals/source-control-plug-in-architecture.md)  
 Używa diagram architektury, aby wyjaśnić integracji wtyczka do kontroli źródła przy użyciu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 [Przewodnik po testowym](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)  
 Zawiera wskazówki dotyczące sposobu testowania instalacji i działania wtyczki kontroli źródła.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Tworzenie pakietu VSPackage kontroli źródła](../../extensibility/internals/creating-a-source-control-vspackage.md)  
 W tym artykule omówiono sposób tworzenia kontroli źródła pakietu VSPackage, który nie tylko zapewnia funkcji kontroli źródła, lecz zastępuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] źródłowej kontrolki interfejsu użytkownika.  
  
 [Wtyczek kontroli kodu źródłowego](../../extensibility/source-control-plug-ins.md)  
 Zawiera pełną listę wszystkich elementów w interfejsie API wtyczki kontroli źródła.  
  
 [Kontrola źródła](../../extensibility/internals/source-control.md)  
 W tym artykule omówiono opcje implementowania kontroli źródła jako zintegrowaną funkcją [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].
