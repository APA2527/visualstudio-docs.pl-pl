---
title: 'CA2006: Używaj klasy SafeHandle w celu hermetyzacji zasobów natywnych | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2006
- UseSafeHandleToEncapsulateNativeResources
helpviewer_keywords:
- UseSafeHandleToEncapsulateNativeResources
- CA2006
ms.assetid: a71950bd-bcc1-463d-b1f2-5233bc451456
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 88d53d90d00f58706e366b54dfa78b59e499bc24
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49935383"
---
# <a name="ca2006-use-safehandle-to-encapsulate-native-resources"></a>CA2006: Użyj SafeHandle, aby hermetyzować zasoby natywne
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseSafeHandleToEncapsulateNativeResources|
|CheckId|CA2006|
|Kategoria|Microsoft.Reliability|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Zarządzany kod używa <xref:System.IntPtr> dostęp do zasobów natywnych.

## <a name="rule-description"></a>Opis reguły
 Korzystanie z `IntPtr` w kodzie zarządzanym może wskazywać na potencjalny problem zabezpieczeń i niezawodności. Wszystkie przypadki użycia `IntPtr` muszą być przejrzane w celu określenia czy użytkowania <xref:System.Runtime.InteropServices.SafeHandle> , lub podobnej technologii jest wymagany w tym miejscu. Problemy z wystąpi `IntPtr` reprezentuje niektóre zasobu natywnego, takich jak pamięć, dojścia do pliku lub gniazdo, że kod zarządzany jest uważany za własne. Jeśli kod zarządzany jest właścicielem zasobu, jego również zwolnić macierzystymi zasobami, które są skojarzone z nią, ponieważ niewykonanie tej czynności mogłoby spowodować wycieki zasobów.

 W takich przypadkach problemy z zabezpieczeniami lub niezawodność będą dostępne są także jeśli dostęp do wielu wątków może być `IntPtr` i sposób przy zwalnianiu zasobów, który jest reprezentowany przez `IntPtr` podano. Te problemy obejmują recyklingu `IntPtr` wartość w wersji zasobu w trakcie jednoczesne użycie zasobów w innym wątku. Może to spowodować sytuacje wyścigu, gdzie jeden wątek może odczytu lub zapisu danych, który jest skojarzony z niewłaściwego zasobu. Na przykład, jeśli danego typu przechowuje dojście systemu operacyjnego jako `IntPtr` . Umożliwia ono użytkownikom wywołać oba **Zamknij** i innych metod, które używa dojścia równocześnie, jak i bez pewnego rodzaju synchronizacji, kod ma uchwyt odtwarzania Wystąpił problem.

 Tego dojścia do odtwarzania problem może spowodować uszkodzenie danych, a często luki w zabezpieczeniach. `SafeHandle` i jego klasa element równorzędny <xref:System.Runtime.InteropServices.CriticalHandle> mechanizm do hermetyzacji natywnych dojście do zasobu, dzięki czemu można uniknąć tych problemów wątków. Ponadto można użyć `SafeHandle` i jego klasa element równorzędny `CriticalHandle` dla innych wątków problemów, na przykład dokładnie kontrolować okres istnienia zarządzanych obiektów, które zawierają kopię uchwyt macierzysty za pośrednictwem wywołania metod natywnych. W takiej sytuacji można często wyeliminować wywołania `GC.KeepAlive`. Zaangażować obciążenie wydajności, wiąże się, gdy używasz `SafeHandle` i w mniejszym stopniu `CriticalHandle`, często można zmniejszyć za pomocą zachowania ostrożności podczas projektowania.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Konwertuj `IntPtr` wykorzystania `SafeHandle` bezpieczne zarządzanie dostępem do zasobów natywnych. Zobacz <xref:System.Runtime.InteropServices.SafeHandle> temat referencyjny dotyczący przykłady.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie należy pominąć to ostrzeżenie.

## <a name="see-also"></a>Zobacz też
 <xref:System.IDisposable>



