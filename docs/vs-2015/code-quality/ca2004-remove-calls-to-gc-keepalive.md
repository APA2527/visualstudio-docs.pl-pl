---
title: 'CA2004: Usuń wywołania do GC. KeepAlive | Dokumentacja firmy Microsoft'
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
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 944862f742e96ef061c3c425bb28c0addcb4fb4e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49829069"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: Usuń wywołania do GC.KeepAlive
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|Kategoria|Microsoft.Reliability|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Użyj klasy `SafeHandle` , ale nadal zawiera wywołania `GC.KeepAlive`.

## <a name="rule-description"></a>Opis reguły
 Jeśli są konwertowane na `SafeHandle` użycia, usunąć wszystkie wywołania `GC.KeepAlive` (obiekt). W tym przypadku klasy nie powinny wywołać `GC.KeepAlive`, zakładając, że nie ma finalizatora, ale korzystają z `SafeHandle` do ukończenia dojście systemu operacyjnego dla nich.  Chociaż koszt pozostawienie w wywołaniu `GC.KeepAlive` może być niewielkie, mierzony wydajność, wrażenie, wywołanie `GC.KeepAlive` jest konieczne lub wystarczające, aby rozwiązać problem, który może już nie istnieć sprawia, że kod jest trudniejsze okres istnienia Obsługa.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Usuń wywołania `GC.KeepAlive`.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Można pominąć to ostrzeżenie, tylko wtedy, gdy nie jest technicznie poprawny do przekonwertowania na `SafeHandle` użycia w klasie.



