---
title: Raport śledzenia zdarzeń systemu Windows (ETW) | Microsoft Docs
description: Przeczytaj o raporcie śledzenie zdarzeń systemu Windows (ETW), który zawiera listę zdarzeń ETW, które zostały zarejestrowane w sesji wydajności programu Visual Studio narzędzia profilowania.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Event tracing for Windows profiling report
- ETW profiling report
ms.assetid: 81e88162-b88a-40b6-8b85-a232c8096a47
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: e7167f2fb5c78a6fa8c3d83fb56c2c2eba217516
ms.sourcegitcommit: 589d96700208bf22c8da9e26a1d2041fbf39b8f9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98801416"
---
# <a name="event-tracing-for-windows-etw-report"></a>Raport śledzenia zdarzeń systemu Windows (ETW)
Raport śledzenie zdarzeń systemu Windows (ETW) zawiera listę zdarzeń ETW, które zostały zarejestrowane w sesji wydajności [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] narzędzia profilowania. Dane ETW są zbierane w postaci binarnej (.*ETL*).

> [!NOTE]
> Nie można wyświetlać raportów ETW w [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] interfejsie.

- Aby uzyskać informacje dotyczące sposobu zbierania funkcji ETW przy użyciu narzędzia profilowania z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] interfejsu, zobacz [jak: zbierać dane śledzenia zdarzeń dla systemu Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).

- Informacje o sposobie zbierania danych ETW przy użyciu narzędzi wiersza polecenia [VSPerfCmd](../profiling/vsperfcmd.md) można znaleźć w temacie [Events (zdarzenia](../profiling/events-vsperfcmd.md)).

- Raport ETW jest generowany przy użyciu polecenia **VSReport/Summary: ETW** . Aby uzyskać więcej informacji, zobacz [VSPerfReport](../profiling/vsperfreport.md).

|Kolumna|Opis|
|------------|-----------------|
|**Znacznik czasu**|Identyfikuje czas wystąpienia zdarzenia.|
|**Identyfikator procesu**|Identyfikuje proces, który wygenerował zdarzenie.|
|**Identyfikator wątku**|Identyfikuje wątek, który wygenerował zdarzenie.|
|**Opis**|Identyfikuje dostawcę zdarzeń.|
|**Typ**|Identyfikuje typ zdarzenia.|
|**Właściwości**|Właściwości zdarzenia. Każde zdarzenie jest rozdzielaną przecinkami parą par nazwa-wartość, która jest ujęta w nawiasy klamrowe.|
