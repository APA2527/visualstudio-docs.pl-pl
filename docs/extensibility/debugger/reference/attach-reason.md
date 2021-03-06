---
title: ATTACH_REASON | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ATTACH_REASON
helpviewer_keywords:
- ATTACH_REASON enumeration
ms.assetid: 159fb70b-a344-4ba6-9115-b7eaa16e228f
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ca871d9dac2b6f37018af925eece5c1a6f3d1585
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "80738122"
---
# <a name="attach_reason"></a>ATTACH_REASON
Określa przyczynę, z którą aparat debugowania ma zostać dołączony do węzła programu.

## <a name="syntax"></a>Składnia

```cpp
enum enum_ATTACH_REASON {
    ATTACH_REASON_LAUNCH = 0x0001,
    ATTACH_REASON_USER   = 0x0002,
    ATTACH_REASON_AUTO   = 0x0003
};
typedef DWORD ATTACH_REASON;
```

```csharp
public enum enum_ATTACH_REASON {
    ATTACH_REASON_LAUNCH = 0x0001,
    ATTACH_REASON_USER   = 0x0002,
    ATTACH_REASON_AUTO   = 0x0003
};
```

## <a name="fields"></a>Pola
`ATTACH_REASON_AUTO`\
Dołącz, ponieważ proces jest obecnie w trybie debugowania.

`ATTACH_REASON_LAUNCH`\
Dołącz, ponieważ proces został uruchomiony.

`ATTACH_REASON_USER`\
Dołącz ze względu na żądanie użytkownika.

## <a name="remarks"></a>Uwagi
Te wartości są używane jako parametr w metodach [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) i [Attach](../../../extensibility/debugger/reference/idebugprogramex2-attach.md) .

## <a name="requirements"></a>Wymagania
Nagłówek: Msdbg. h

Przestrzeń nazw: Microsoft. VisualStudio. Debugger. Interop

Zestaw: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Zobacz też
- [Wyliczenia](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [Dołącz](../../../extensibility/debugger/reference/idebugengine2-attach.md)
- [Dołącz](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)
