---
title: Niezakończony komentarz | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT1016
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d4286315-814b-4966-b4c4-1ee19d796eff
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9fde5d5edd7e81060b088e4940d752aa05e65ded
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49868108"
---
# <a name="unterminated-comment"></a>Niezakończony komentarz
Rozpoczęto blok komentarzy wielowierszowych, ale nie prawidłowo zakończyć je. Wielowierszowe komentarze zaczynają się od "/ *" połączenie oraz kończyć się odwrotnej "\*/" kombinacji. Oto przykład:  
  
```JavaScript  
/* This is a comment  
This is another part of the same comment.*/  
```  
  
### <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Pamiętaj zakończyć Komentarze wielowierszowe "* /".  
  
## <a name="see-also"></a>Zobacz też  
 [Instrukcje komentarzy](../../javascript/reference/comment-statements-javascript.md)