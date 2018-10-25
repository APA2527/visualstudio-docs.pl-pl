---
title: 'CA2106: Zabezpiecz asercje | Dokumentacja firmy Microsoft'
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
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6ca37a7bdcad290f9ab0c6d54814615731f6678c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49864741"
---
# <a name="ca2106-secure-asserts"></a>CA2106: Potwierdzanie zabezpieczeń
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Metoda potwierdza uprawnienia i żadne sprawdzenia zabezpieczeń nie są wykonywane na obiekcie wywołującym.

## <a name="rule-description"></a>Opis reguły
 Potwierdzanie uprawnienia zabezpieczeń bez sprawdzania zabezpieczeń może pozostawić zdatną do wykorzystania słabość zabezpieczeń w kodzie. Przeszukiwania stosu zabezpieczeń zatrzymuje, gdy jest potwierdzone uprawnienia zabezpieczeń. Jeśli uprawnienie jest assert bez wykonywania jakiejkolwiek kontroli obiekt wywołujący i obiekt wywołujący pośrednio wykonanie kodu przy użyciu uprawnień. Potwierdza bez sprawdzania zabezpieczeń są dopuszczalne, tylko gdy masz pewność, że asercja nie można używać w szkodliwy sposób. Asercja jest nieszkodliwe, jeśli kod, który można wywołać jest nieszkodliwe lub użytkownicy nie mogła przekazywać dowolne informacje do kodu, który można wywoływać.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, należy dodać żądania zabezpieczeń do metody lub jej typ deklarujący.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Pomijaj ostrzeżeń dla tej reguły tylko po weryfikacji zabezpieczeń zachowania ostrożność.

## <a name="see-also"></a>Zobacz też
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> [Wytyczne dotyczące bezpiecznego programowania](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)



