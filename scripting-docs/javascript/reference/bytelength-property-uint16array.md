---
title: byteLength właściwość (Uint16Array) | Dokumentacja firmy Microsoft
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
ms.assetid: a8c9229b-8ee3-4af9-9b6e-7728260c7faf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: afb43b848732137917c7a5aef406176b21e0139b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789007"
---
# <a name="bytelength-property-uint16array"></a>byteLength Właściwość (Uint16Array)
Tylko do odczytu. Ustalona podczas tworzenia długość (w bajtach) tej tablicy od początku jej ArrayBuffer.  
  
## <a name="syntax"></a>Składnia  
  
```JavaScript  
var arrayByteLength = uint16Array.byteLength;  
```  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia, jak pobrać długość tablicy.  
  
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
            alert(intArr.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Wymagania  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]