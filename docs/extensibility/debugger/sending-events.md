---
title: Wysyłanie zdarzeń | Microsoft Docs
description: Dowiedz się, w jaki sposób debuger i aparat debugowania wykorzystują model zdarzeń oparty na modelu DCOM. Zdarzenia są wysyłane jako obiekty COM.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0262868ae442bfdd8b99c16f59e000f4ebfc35c5
ms.sourcegitcommit: ce85cff795df29e2bd773b4346cd718dccda5337
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "96847913"
---
# <a name="send-events"></a>Wysyłanie zdarzeń
Mechanizm komunikacji między debugerem a aparatem debugowania (DE) jest modelem zdarzeń opartym na modelu DCOM. Zdarzenia są wysyłane jako obiekty COM, a każde zdarzenie ma parametry, które określają:

- DE, która wywołała zdarzenie.

- Opis tego, co się stało.

- Informacje o procesie, programie i wątku, które identyfikują kontekst, w którym wystąpiło zdarzenie. Proces nie jest wysyłany dla zdarzeń wysyłanych z elementu DE.

- Typ zdarzenia, który wskazuje, czy zdarzenie jest synchroniczne, czy asynchroniczne.

  Wszystkie zdarzenia debugowania są wysyłane przy użyciu metody [IDebugEventCallback2:: Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md).

## <a name="in-this-section"></a>W tej sekcji
 [Źródła zdarzeń](../../extensibility/debugger/event-sources-visual-studio-sdk.md) Wyjaśnia dwa źródła zdarzeń: aparat debugowania (DE) i Menedżer debugowania sesji (SDM).

 [Obsługiwane typy zdarzeń](../../extensibility/debugger/supported-event-types.md) Omawia aktualnie obsługiwane typy zdarzeń: asynchroniczne i synchroniczne.

 [Opisy zdarzeń](../../extensibility/debugger/event-descriptions.md) Definiuje zdarzenia i przyczyny ich użycia.

## <a name="related-sections"></a>Sekcje pokrewne
 [Tworzenie niestandardowego aparatu debugowania](../../extensibility/debugger/creating-a-custom-debug-engine.md) Opisuje, jak DE współpracuje z interpreterem lub systemem operacyjnym w celu zapewnienia usług debugowania.
