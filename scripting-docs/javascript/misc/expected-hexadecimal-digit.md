---
title: Oczekiwana cyfra szesnastkowa | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: error-reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 67a86df7-49f9-43cb-99c6-99b1a427827a
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8c6be5302c0c4c6565884fa800da7cb9a002d151
ms.sourcegitcommit: e38419bb842d587fd9e37c24b6cf3fc5c2e74817
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91861936"
---
# <a name="expected-hexadecimal-digit"></a>Oczekiwano liczby szestnastkowej
Utworzono nieprawidłową sekwencję ucieczki Unicode. Sekwencje ucieczki Unicode zaczynają się od \u, po których następuje dokładnie cztery cyfry szesnastkowe (nie więcej i nie mniej). Cyfry szesnastkowe Unicode mogą zawierać tylko cyfry 0-9, wielkie litery A-F i małe litery a-f. Poniższy przykład ilustruje poprawnie sformułowaną sekwencję ucieczki w formacie Unicode.  
  
```JavaScript  
z = "\u1A5F";  
```  
  
### <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Upewnij się, że cyfry szesnastkowe Unicode zaczynają się od \u, zawierają tylko cyfry 0-9, wielkie litery A-F, małe litery a-f; i są pogrupowane w cztery cyfry.  
  
    > [!NOTE]
    > Jeśli chcesz użyć literału Text \u w ciągu, użyj dwóch ukośników odwrotnych-( \\ \u)-jeden do ucieczki pierwszego ukośnika odwrotnego.  
  
## <a name="see-also"></a>Zobacz też  
 [Typy danych](https://developer.mozilla.org/docs/Web/JavaScript/Data_structures)