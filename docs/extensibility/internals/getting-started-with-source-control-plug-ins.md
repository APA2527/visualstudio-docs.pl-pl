---
title: Wprowadzenie do wtyczek kontroli kodu źródłowego | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, getting started
- getting started, source control plug-ins
ms.assetid: 46ac1f9f-4ecc-4a72-88d3-4c7e1647e1cb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2f1eb4f76616f6a5f6791cbcd1b8a5770d1dcabb
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39498103"
---
# <a name="get-started-with-source-control-plug-ins"></a>Wprowadzenie do wtyczek kontroli kodu źródłowego
Aby utworzyć kontroli źródła wtyczek, należy utworzyć bibliotekę DLL, która implementuje funkcje zdefiniowane w interfejsie API wtyczki kontroli źródła, a następnie zarejestruj plik DLL za pomocą [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aby stał się dostępny do użytku w kontroli wersji kodu źródłowego.  
  
 Trzy wersje interfejsu API wtyczki kontroli źródła (w wersji 1.1 i 1.2, 1.3) są dostępne dla wtyczek kontroli kodu źródłowego. API wtyczki kontroli źródła opisane tutaj jest w wersji 1.3. Została zaprojektowana pod kątem pełnej zgodności z wtyczek kontroli kodu źródłowego obsługi wersji 1.1 i 1.2. [What's new in źródła kontrolki wtyczki interfejsu API w wersji 1.3](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md) szczegółowo opisano nowe funkcje, które są obsługiwane w najnowszej wersji interfejsu API wtyczki kontroli źródła.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Porady: Instalowanie wtyczki kontroli źródła](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)  
 W tym artykule opisano, jak utworzyć wpisy rejestru, które są wymagane do wtyczki kontroli źródła biblioteki DLL.  
  
 [What's new in źródła kontrolki wtyczki interfejsu API w wersji 1.3](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md)  
 Krótkie omówienie zmiany wprowadzone do interfejsu API wtyczki kontroli źródła w wersji 1.3.  
  
 [What's new in źródła kontrolki wtyczki API wersji 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)  
 Krótkie omówienie zmiany wprowadzone do interfejsu API wtyczki kontroli źródła w wersji 1.2.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Wtyczek kontroli kodu źródłowego](../../extensibility/source-control-plug-ins.md)  
 Zawiera pełną listę wszystkich elementów w interfejsie API wtyczki kontroli źródła.  
  
 [Tworzenie wtyczki kontroli źródła](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 Definiuje zestaw SDK wtyczki kontroli źródła i opisuje dołączone zasoby.