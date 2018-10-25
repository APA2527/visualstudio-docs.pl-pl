---
title: 'CA1506: Unikaj nadmiernego sprzężenia klas | Dokumentacja firmy Microsoft'
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
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 488d00b3277f4bf8cdc857f9c389348092f55bab
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49939387"
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506: Unikaj nadmiernego sprzężenia klas
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidExcessiveClassCoupling|
|CheckId|CA1506|
|Kategoria|Microsoft.Maintainability|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Typ lub metoda jest sprzężona z wielu innych typów.

## <a name="rule-description"></a>Opis reguły
 Ta reguła mierzy sprzęgnięcie klasy przez liczenie unikatowych odwołań typów, które zawiera typ lub metoda.

 Typy i metody, które mają wysokim stopniu sprzężenia klas mogą być trudne w utrzymaniu. Jest dobrą praktyką, typów i metod, które wykazują sprzężenia niski i wysoki spójności.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby rozwiązać problem to naruszenie, spróbuj zmienić układ typu lub metody w celu zmniejszenia liczby typów, do których jest sprzężona.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Wyklucz to ostrzeżenie, gdy typ lub metoda jest nadal uważana za łatwego w utrzymaniu pomimo dużej liczby zależności od innych typów.

## <a name="see-also"></a>Zobacz też
 [Ostrzeżenia dotyczące utrzymania](../code-quality/maintainability-warnings.md) [mierzenie złożoności i łatwości konserwacji zarządzanego kodu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)



