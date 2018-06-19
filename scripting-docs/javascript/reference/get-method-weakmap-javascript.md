---
title: Get — metoda (WeakMap) (JavaScript) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d922c55d-486d-4feb-aedc-1f4867c417d2
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29decb7e6a050188b75639eb7cf4f27494b31da2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790456"
---
# <a name="get-method-weakmap-javascript"></a>get — Metoda (WeakMap) (JavaScript)
Zwraca określony element z `WeakMap` obiektu.  
  
## <a name="syntax"></a>Składnia  
  
```JavaScript  
weakmapObj.get(key)  
```  
  
#### <a name="parameters"></a>Parametry  
 `weakmapObj`  
 Wymagany. A `WeakMap` obiektu.  
  
 `key`  
 Wymagany. Klucz elementu w `WeakMap`.  
  
## <a name="property-valuereturn-value"></a>Wartość właściwości/Zwracana wartość  
 Zwraca obiekt skojarzony z kluczem. Jeśli `WeakMap` nie zawiera klucza, ta metoda zwraca `undefined` wartość.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak można pobrać elementów członkowskich z `WeakMap` obiektu.  
  
```JavaScript  
var dog = {  
    breed: "yorkie"  
}  
  
var cat = {  
    breed: "burmese"  
}  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
wm.set(cat, "pepper");  
  
document.write(wm.get(dog) + ": ");  
document.write(dog.breed);  
document.write("<br />");  
document.write(wm.get(cat) + ": ");  
document.write(cat.breed);  
  
// Output:  
// fido: yorkie  
// pepper: burmese  
  
```  
  
## <a name="requirements"></a>Wymagania  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]