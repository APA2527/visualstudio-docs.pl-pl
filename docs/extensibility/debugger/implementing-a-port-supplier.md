---
title: Implementowanie dostawcy portów | Microsoft Docs
description: Dowiedz się więcej na temat implementowania dostawcy portów, który jest konieczny podczas debugowania na komputerze nienależącym do modelu DCOM lub gdy nowe urządzenie wymaga obsługi.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 72963660e4f50a72cdbc04bab4833b397d15fc27
ms.sourcegitcommit: bbed6a0b41ac4c4a24e8581ff3b34d96345ddb00
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "96560671"
---
# <a name="implement-a-port-supplier"></a>Implementowanie dostawcy portu
Dostawca portu dostarcza porty na żądanie do Menedżera debugowania sesji (SDM). Dostawca portu musi być zaimplementowany podczas debugowania na komputerze nienależącym do modelu DCOM lub w przypadku, gdy nowe urządzenie wymaga obsługi. Na przykład w celu zapewnienia debugowania na telefonie komórkowym można skonfigurować dostawcę portu, który udostępnia porty, które nawiązują połączenie z telefonem komórkowym (prawdopodobnie przez połączenie IR lub z komórką) i wylicza procesy i programy uruchomione na telefonie.

 W przypadku debugowania programów na maszynach z systemem Windows (w tym debugowanie zdalne) program Visual Studio udostępnia dostawcy portów dla procesów natywnego i środowiska uruchomieniowego języka wspólnego (CLR), więc nie ma potrzeby konfigurowania własnego dostawcy portów w takich przypadkach.

## <a name="in-this-section"></a>W tej sekcji
 [Implementowanie i rejestrowanie dostawcy portu](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md) Omawia, w jaki sposób model SDM współdziała z dostawcą portów i jego portami.

 [Wymagane interfejsy dostawcy portów](../../extensibility/debugger/required-port-supplier-interfaces.md) Dokumentuje interfejsy, które należy zaimplementować w celu uzyskania dostawcy portów.

## <a name="related-sections"></a>Sekcje pokrewne
 [Pojęcia dotyczące debugera](../../extensibility/debugger/debugger-concepts.md) Opisuje główne koncepcje dotyczące architektury debugowania.

## <a name="see-also"></a>Zobacz także
 [Rozszerzalność debugera programu Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)
