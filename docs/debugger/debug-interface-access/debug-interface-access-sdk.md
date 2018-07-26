---
title: Zestaw SDK dostępu do interfejsu debugowania | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 07/24/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [DIA SDK]
- debugger [DIA SDK]
- DIA SDK
ms.assetid: 4c0abe53-11d3-4b7a-bdc7-b054f85aaf40
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 279f5b883ca359c38ad8d357d153d02ea022b9da
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251669"
---
# <a name="debug-interface-access-sdk"></a>Zestaw SDK dostępu do interfejsu debugowania

Microsoft debugowanie interfejsu dostępu Software Development Kit (DIA SDK) zapewnia dostęp do debugowania informacje przechowywane w plikach bazy danych (PDB) program wygenerowanych przez postcompiler narzędzi firmy Microsoft. Ponieważ format pliku PDB wygenerowany za pomocą narzędzi postcompiler ulega stałej poprawki, udostępnianie format jest niepraktyczne. Za pomocą interfejsu API DIA, można tworzyć aplikacje, które wyszukiwać i przeglądać informacje debugowania przechowywane w pliku .pdb. Takie aplikacje można na przykład zgłaszania informacji dotyczących zdarzenia sprzed stosu i analizowanie danych dotyczących wydajności.

## <a name="in-this-section"></a>W tej sekcji

[Wprowadzenie](../../debugger/debug-interface-access/getting-started-debug-interface-access-sdk.md)  
Zawiera omówienie DIA SDK funkcji oraz określa, gdzie DIA SDK jest zainstalowany, a także wymagany nagłówek i pliki biblioteki.

[Używanie zapytań dotyczących pliku .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
Instrukcje dotyczące sposobu używania interfejsu API DIA pliku .pdb kwerendy.

[Symbole i tagi symboli](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)  
W tym artykule omówiono sposób symbole i tagi symboli są używane w interfejsie API DIA.

[Dokumentacja](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)  
Zawiera interfejsy, metody, wyliczenia i struktury DIA interfejsu API.

[Dia2dump — przykład](../../debugger/debug-interface-access/dia2dump-sample.md)  
Ilustruje sposób wyszukiwać i przeglądać informacje o debugowaniu za pomocą interfejsu API DIA.
