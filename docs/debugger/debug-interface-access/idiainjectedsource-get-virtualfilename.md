---
title: 'IDiaInjectedSource:: get_virtualFilename | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_virtualFilename method
ms.assetid: b9977075-8fd1-4b11-bfff-d87e9f2586dc
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 78bb087f7e5b66d68e24d66315d9edcd15b06544
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99864874"
---
# <a name="idiainjectedsourceget_virtualfilename"></a>IDiaInjectedSource::get_virtualFilename
Pobiera nazwę nadaną dla kodu źródłowego niezwiązanego z plikiem; oznacza to, że kod został wstrzyknięty.

## <a name="syntax"></a>Składnia

```C++
HRESULT get_virtualFilename ( 
   BSTR* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

określoną Zwraca nazwę nadaną do wstrzykniętego kodu źródłowego, który nie jest plikiem.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` . Zwraca wartość, `S_FALSE` Jeśli ta właściwość nie jest obsługiwana. W przeciwnym razie zwraca kod błędu.

## <a name="see-also"></a>Zobacz też
- [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)