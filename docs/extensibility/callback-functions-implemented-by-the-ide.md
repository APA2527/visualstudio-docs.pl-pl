---
title: Funkcje wywołania zwrotnego implementowane przez środowisko IDE | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, callback functions
- callback functions, source control plug-ins
ms.assetid: 4a8833f0-6ac0-4ea7-9400-8275aa991468
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c76a9ef3ab81cf764d5f82fdfb9c8d6a86f24bee
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2018
ms.locfileid: "39232484"
---
# <a name="callback-functions-implemented-by-the-ide"></a>Funkcje wywołania zwrotnego implementowane przez środowisko IDE
Aby Integracja z usługą zintegrowanego środowiska programistycznego (IDE) jako Bezproblemowa, jak to możliwe i w celu zapewnienia ujednoliconego końcowego wtyczka do kontroli źródła można użyć funkcji wywołania zwrotnego, które są implementowane przez środowisko IDE. Wtyczka może wywołać te funkcje w odpowiednim czasie podczas operacji kontroli źródła do przekazywania informacji do IDE; IDE może następnie wyświetlić te informacje jako elementy osadzone w ich natywnym interfejsem użytkownika. Użytkownik ma zmniejszenie fragmentacji środowisko, w tym scenariuszu niż Jeśli wtyczka zatrudnionych własnego interfejsu użytkownika.  
  
 Plik nagłówka wymagane jest *scc.h*. Domyślna lokalizacja to *\Program Files\VSIP 8.0\EnvSDK\common\inc\\*. Jest również folder VSIP, który zawiera przykładowe wtyczki kontroli źródła na *\Program Files\VSIP 8.0\MSSCCI\\*.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 Zawiera opis funkcji wywołania zwrotnego, który jest używany przez [SccOpenProject](../extensibility/sccopenproject-function.md) umożliwiające wyświetlanie komunikatów z kontroli źródła wtyczek za pośrednictwem środowiska IDE.  
  
 [POPLISTFUNC](../extensibility/poplistfunc.md)  
 Zawiera opis funkcji wywołania zwrotnego, który jest używany przez [SccPopulateList](../extensibility/sccpopulatelist-function.md) gdy IDE nie ma pełny dostęp do informacji, która jest dostępna tylko dla wtyczka do kontroli źródła, takich jak kompletna lista plików w systemie kontroli wersji.  
  
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)  
 Zawiera opis funkcji wywołania zwrotnego, który jest używany przez [SccQueryChanges](../extensibility/sccquerychanges-function.md) operacji.  
  
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)  
 Zawiera opis funkcji wywołania zwrotnego, który jest używany przez [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) operacji.  
  
 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)  
 W tym artykule opisano ustawiony przez wywołanie do funkcji wywołania zwrotnego [SccSetOption](../extensibility/sccsetoption-function.md) umożliwiającej wtyczka do kontroli źródła do komunikowania się zmiany nazwy z powrotem do środowiska IDE.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [SccOpenProject](../extensibility/sccopenproject-function.md)  
 Zostanie otwarty projekt.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 Sprawdza, czy lista plików dla ich bieżący stan. Ponadto używa `pfnPopulate` funkcję, aby powiadomić obiekt wywołujący, gdy plik jest niezgodny z kryteriami, które dla `nCommand`.  
  
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)  
 Sprawdza, czy lista katalogów i plików w projekcie, lub projekty, które są pod kontrolą źródła. Każdy katalog oraz nazwę pliku znaleziono jest przekazywany do funkcji wywołania zwrotnego.  
  
 [SccQueryChanges](../extensibility/sccquerychanges-function.md)  
 Sprawdza, czy zmiany nazwy, które zostały wprowadzone do listy plików. Każda nazwa pliku jest przekazywany do funkcji wywołania zwrotnego, razem ze statusem zmiany.  
  
 [SccSetOption](../extensibility/sccsetoption-function.md)  
 Ustawia szeroką gamę opcji. Każda opcja zaczyna się od `SCC_OPT_xxx` i ma swój własny zestaw zdefiniowanych wartości.  
  
 [Wtyczki kontroli źródła](../extensibility/source-control-plug-ins.md)  
 W tym artykule opisano zawartość sekcji odwołanie do zestawu SDK wtyczki kontroli źródła.