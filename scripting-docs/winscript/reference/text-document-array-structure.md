---
title: Struktura TEXT_DOCUMENT_ARRAY | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- TEXT_DOCUMENT_ARRAY Structure
ms.assetid: 47c08f23-981b-4105-9240-6dfffc6cb91b
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 03ed7f13b4e57f9e44ca147810614f980b24b9a5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2017
ms.locfileid: "24796384"
---
# <a name="textdocumentarray-structure"></a>Struktura TEXT_DOCUMENT_ARRAY
Tablica [interfejs IDebugDocumentText](../../winscript/reference/idebugdocumenttext-interface.md) obiektów. Elementy członkowskie są przydzielane z CoTaskMemAlloc.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef struct tagTEXT_DOCUMENT_ARRAY{    DWORD dwCount;    [size_is(dwCount)] IDebugDocumentText **Members;} TEXT_DOCUMENT_ARRAY;  
```  
  
## <a name="members"></a>Elementy członkowskie  
 `dwCount`  
 Liczba dokumentów.  
  
 `Members`  
 Zestaw dokumentów.  
  
## <a name="see-also"></a>Zobacz też  
 [Stałe debugera aktywnego skryptu, wyliczenia i struktury](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)