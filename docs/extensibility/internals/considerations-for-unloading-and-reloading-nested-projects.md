---
title: Zwalnianie i ponowne ładowanie zagnieżdżonych projektów
description: Zapoznaj się z dodatkowymi krokami, które należy wykonać podczas zwalniania i ponownego ładowania zagnieżdżonych projektów w programie Visual Studio.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- nested projects, unloading and reloading
- projects [Visual Studio SDK], unloading and reloading nested
ms.assetid: 06c3427e-c874-45b1-b9af-f68610ed016c
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: ed91ac56929682205937122a4521ad7233af675f
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99884653"
---
# <a name="considerations-for-unloading-and-reloading-nested-projects"></a>Zagadnienia dotyczące zwalniania i ponownego ładowania zagnieżdżonych projektów

Podczas implementowania zagnieżdżonych typów projektów należy wykonać dodatkowe czynności podczas zwalniania i ponownego ładowania projektów. Aby poprawnie powiadomić odbiorniki do zdarzeń rozwiązania, należy prawidłowo podnieść `OnBeforeUnloadProject` `OnAfterLoadProject` zdarzenia i.

Jedną z przyczyn podniesienia tych zdarzeń jest kontrola kodu źródłowego (SCC). Nie chcesz, aby SCC usunął elementy z serwera, a następnie dodać je ponownie jako *nowe* , jeśli istnieje `Get` operacja z SCC. W takim przypadku nowy plik zostanie załadowany z SCC. Musisz zwolnić i załadować ponownie wszystkie pliki, jeśli są różne.

Wywołania kontroli kodu źródłowego `ReloadItem` . Zaimplementuj <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> interfejs, aby wywołać `OnBeforeUnloadProject` i `OnAfterLoadProject` usunąć projekt i utworzyć go ponownie. Po zaimplementowaniu interfejsu w ten sposób, SCC zostanie poinformowany o tym, że projekt został tymczasowo usunięty i ponownie dodany. W związku z tym SCC nie działa w projekcie tak, jakby projekt został *rzeczywiście* usunięty i dodany do niego.

## <a name="reload-projects"></a>Załaduj ponownie projekty

Aby obsługiwać ponowne ładowanie zagnieżdżonych projektów, należy zaimplementować <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> metodę. W implementacji programu `ReloadItem` można zamknąć zagnieżdżone projekty, a następnie utworzyć je ponownie.

Zwykle po ponownym załadowaniu projektu środowisko IDE wywołuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeUnloadProject%2A> <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> zdarzenia i. Jednak w przypadku projektów zagnieżdżonych, które są usuwane i ponownie ładowane, projekt nadrzędny inicjuje proces, a nie IDE. Ponieważ projekt nadrzędny nie zgłasza zdarzeń rozwiązania, a IDE nie ma informacji o inicjalizacji procesu, zdarzenia nie są zgłaszane.

Aby obsłużyć ten proces, projekt nadrzędny jest wywoływany przez ten `QueryInterface` <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> interfejs. `IVsFireSolutionEvents` Program zawiera funkcje, które informują IDE o podniesieniu `OnBeforeUnloadProject` zdarzenia w celu zwolnienia projektu zagnieżdżonego, a następnie podniesienia `OnAfterLoadProject` zdarzenia w celu ponownego załadowania tego samego projektu.

## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>
- [Zagnieżdżanie projektów](../../extensibility/internals/nesting-projects.md)
