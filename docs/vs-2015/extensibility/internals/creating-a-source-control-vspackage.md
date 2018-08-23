---
title: Tworzenie pakietu VSPackage kontroli źródła | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], creating source control packages
- source control packages
ms.assetid: cca0a9ed-48ff-409f-8036-ed8db0f7533e
caps.latest.revision: 24
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e67d21fe906dd6bc2a1da0a7a483ee78aa0fe2db
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678568"
---
# <a name="creating-a-source-control-vspackage"></a>Tworzenie pakietu VSPackage kontroli kodu źródłowego
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [tworzenia VSPackage kontroli kodu](https://docs.microsoft.com/visualstudio/extensibility/internals/creating-a-source-control-vspackage).  
  
Ta dokumentacja zawiera linki do omówienia architektury pakietu kontroli źródła, zintegrowana z usługą [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], interfejs API, który jest definiowany przez interfejsy, które mają być wdrożone i usług, które mają być używane, a przykład ilustrujący proste źródła Pakiet implementację formantu.  
  
 Za pomocą pakietu VSPackage z kontroli źródła, można utworzyć ścieżkę głęboka Integracja kontroli źródła zintegrować z usługą [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Umożliwia ona pakiet do obejścia kontroli źródła domyślnego interfejsu użytkownika pracujących [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], odpowiadanie na żądania kontroli źródła z projektu systemu i interakcji z [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] składniki, takie jak **Eksploratora rozwiązań**. [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] Upoważnia [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] w ramach której partnerzy z mechanizmem do utworzenia pakietu VSPackage, który można zintegrować z [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] przy użyciu modelu usługi.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Wprowadzenie](../../extensibility/internals/getting-started-with-source-control-vspackages.md)  
 W tym artykule omówiono pakiet kontroli źródła, który jest bardziej zaawansowanych alternatywą do kontroli źródła wtyczek do implementowania funkcji kontroli źródła w [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 [Architektura](../../extensibility/internals/source-control-vspackage-architecture.md)  
 Przedstawia informacje o diagramie i wyjaśniono składniki pakietu kontroli źródła.  
  
 [Funkcje](../../extensibility/internals/source-control-vspackage-features.md)  
 W tym artykule opisano różne funkcje pakietu kontroli źródła.  
  
 [Elementy projektu](../../extensibility/internals/source-control-vspackage-design-elements.md)  
 W tym artykule opisano Struktura pakietu VSPackage, który pakiet kontrolki źródła musi implementować do zaawansowanej integracji.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Tworzenie wtyczki kontroli kodu źródłowego](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 W tym artykule omówiono sposób tworzenia wtyczki kontroli źródła dostarczającego funkcji kontroli źródła w [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] interfejsu użytkownika kontroli źródła (UI).  
  
 [Kontrola kodu źródłowego](../../extensibility/internals/source-control.md)  
 W tym artykule omówiono opcje implementowania kontroli źródła jako zintegrowaną funkcją [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].

