---
title: Bytes_per_element — stała (Uint16Array) | Dokumentacja firmy Microsoft
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
ms.assetid: 4e5e8a70-f8b9-4e3c-b9f3-0d1249963c28
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a437564d98120a74e43df81670ade92dadba792
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789124"
---
# <a name="bytesperelement-constant-uint16array"></a>BYTES_PER_ELEMENT — Stała [Uint16Array]
Rozmiar w bajtach każdego elementu w tablicy.  
  
## <a name="syntax"></a>Składnia  
  
```JavaScript  
var arraySize = uint16Array.BYTES_PER_ELEMENT;  
```  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia, jak pobrać rozmiar elementów tablicy.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Uint16Array(buffer.byteLength / 2);  
            alert(intArr.BYTES_PER_ELEMENT);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Wymagania  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]