---
title: Moduł wyliczający kod stanu katalogu | Microsoft Docs
description: Moduł wyliczający SccDirStatus zawiera nazwane wartości stałe, które określają stan katalogu w systemie kontroli źródła i jest używany przez SccDirQueryInfo.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: af72b9e14695cb954084abebc3a3c336c90af73d
ms.sourcegitcommit: d10f37dfdba5d826e7451260c8370fd1efa2c4e4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2020
ms.locfileid: "96996126"
---
# <a name="directory-status-code-enumerator"></a>Moduł wyliczający kod stanu katalogu
`SccDirStatus`Moduł wyliczający zawiera nazwane wartości stałe, które określają stan katalogu w systemie kontroli źródła. To wyliczenie jest używane przez [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md). Została wprowadzona w wersji 1,2 interfejsu API dodatku plug-in kontroli źródła.

## <a name="syntax"></a>Składnia

```
enum SccDirStatus {
   SCC_DIRSTATUS_INVALID       = -1L,
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L
};
```

## <a name="members"></a>Elementy członkowskie
 Nie można uzyskać stanu SCC_DIRSTATUS_INVALID; nie należy polegać na nim.

 Katalog SCC_DIRSTATUS_NOTCONTROLLED nie znajduje się pod kontrolą źródła.

 Katalog SCC_DIRSTATUS_CONTROLLED jest pod kontrolą źródła.

 SCC_DIRSTATUS_EMPTYPROJ projekt odpowiadający temu katalogowi jest pusty.

## <a name="see-also"></a>Zobacz też
- [Wtyczki kontroli źródła](../extensibility/source-control-plug-ins.md)
- [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)
