---
title: Usuń informacje o kontroli źródła z plików. proj i. sln
description: W interfejsie API wtyczki kontroli źródła informacje o SCC są przechowywane w MSSCCPRJ. Plik SCC zamiast plików projektu i rozwiązania.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, .sln and .proj files
ms.assetid: 7b06883f-35de-41e2-9a9e-d3edba236f17
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 03b1c3f6e2c1cc6852ea443788bb336a03c3330f
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99905810"
---
# <a name="removal-of-source-control-information-from-proj-and-sln-files"></a>Usuwanie informacji o kontroli źródła z plików. proj i. sln

W wersji 1,2 interfejsu API dodatku plug-in kontroli źródła informacje o SCC są przechowywane w MSSCCPRJ. Plik SCC. Zaletą MSSCCPRJ. Plik SCC to informacja, że informacje SCC nie są kontrolowane przez źródło, takie jak w plikach. proj i. sln.

## <a name="version-12-changes"></a>Zmiany w wersji 1,2

 W wtyczkach kontroli źródła, które są oparte na interfejsie API wtyczki kontroli źródła w wersji 1,1, informacje o kontroli źródła są przechowywane w plikach projektu (. proj) i rozwiązania (. sln). Lokalizacja bazy danych informacji o kontroli źródła jest określana przez AuxPath, a określona lokalizacja w bazie danych jest określana przez Projname. Takie zachowanie może spowodować problemy po operacji rozgałęzienia, rozwidlenia lub kopiowania, ponieważ Projname zwykle jest nieważny po którejkolwiek z tych operacji.

 W interfejsie API dodatku plug-in kontroli źródła w wersji 1,1 środowisko IDE używane ~ SAK pliki do wykrycia, czy wtyczka obsługuje MSSCCPRJ. Metoda SCC przechowująca informacje o kontroli źródła. Interfejs API wtyczki kontroli źródła w wersji 1,2 oferuje nową funkcję wykrywania obsługi MSSCCPRJ. Plik SCC bez użycia pliku ~ SAK. Aby uzyskać więcej informacji, zobacz [eliminacja plików ~ SAK](../../extensibility/internals/elimination-of-tilde-sak-files.md).

## <a name="see-also"></a>Zobacz też

- [Nowości dotyczące wtyczki kontroli kodu źródłowego w interfejsie API w wersji 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)
