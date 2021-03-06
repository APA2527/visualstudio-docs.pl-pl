---
title: CV_access_e | Microsoft Docs
description: Pobierz informacje o typie wyliczeniowy CV_access_e, który określa zakres widoczności (poziom dostępu) członków w zestawie SDK dostępu do interfejsu debugowania.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 68dc8ca76e9250cd06009a990c0136912b0d31e3
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99857378"
---
# <a name="cv_access_e"></a>CV_access_e
Określa zakres widoczności (poziom dostępu) funkcji składowych i zmiennych.

## <a name="syntax"></a>Składnia

```C++
typedef enum CV_access_e {
    CV_private   = 1,
    CV_protected = 2,
    CV_public    = 3
} CV_access_e;
```

## <a name="elements"></a>Elementy
Członek CV_private ma dostęp prywatny.

Członek CV_protected ma chroniony dostęp.

Członek CV_public ma dostęp publiczny.

## <a name="remarks"></a>Uwagi
`friend`Specyfikator dostępu nie jest uwzględniony w tym miejscu, ponieważ jest zazwyczaj używany przez funkcje nieczłonkowskie, które mają dostęp zarówno do prywatnych, jak i chronionych elementów klasy. Użyj metody [IDiaSymbol:: get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) , aby znaleźć symbole z `SymTagFriend` dostępem.

## <a name="requirements"></a>Wymagania
Nagłówek: cvconst. h

## <a name="see-also"></a>Zobacz też
- [Wyliczenia i struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)
- [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)
