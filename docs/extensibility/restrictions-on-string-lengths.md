---
title: Ograniczenia dotyczące długości ciągu | Microsoft Docs
description: Dowiedz się więcej na temat limitów długości ciągów używanych przez różne funkcje narzucone przez interfejs API dodatku plug-in kontroli źródła.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, restrictions on string lengths
ms.assetid: 877173d2-ca27-43b3-b1f4-8379f7c5e268
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: bd1720553592b0cfbac8be412002ef1b39bfd5bf
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99836959"
---
# <a name="restrictions-on-string-lengths"></a>Ograniczenia długości ciągu
Interfejs API wtyczki kontroli źródła ogranicza długość ciągów używanych w różnych funkcjach.

## <a name="string-length-values"></a>Wartości długości ciągu

|Stała|Wartość|
|--------------|-----------|
|`SCC_NAME_LEN`|31|
|`SCC_AUXLABEL_LEN`|31|
|`SCC_USER_LEN`|31|
|`SCC_PRJPATH_LEN`|300|

> [!NOTE]
> Długość nie obejmuje zakończenia `null` . Inne stałe z sufiksem "_SIZE" zamiast "_LEN" obejmują miejsce dla zakończenia `null` .

|Stała|Wartość|
|--------------|-----------|
|SCC_NAME_SIZE|32|
|SCC_AUXLABEL_SIZE|32|
|SCC_USER_SIZE|32|
|SCC_PRJPATH_SIZE|301|

## <a name="see-also"></a>Zobacz też
- [Wtyczki kontroli źródła](../extensibility/source-control-plug-ins.md)
