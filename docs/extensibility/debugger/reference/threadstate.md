---
title: THREADSTATE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- THREADSTATE
helpviewer_keywords:
- THREADSTATE enumeration
ms.assetid: 62efdd7c-25b1-4fd3-9d06-ac1830a418a9
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1b291cc1668b2b867729da11d4c561f74567f257
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "80713337"
---
# <a name="threadstate"></a>THREADSTATE
Określa stan wątku.

## <a name="syntax"></a>Składnia

```cpp
enum enum_THREADSTATE { 
   THREADSTATE_RUNNING = 0x0001,
   THREADSTATE_STOPPED = 0x0002,
   THREADSTATE_FRESH   = 0x0003,
   THREADSTATE_DEAD    = 0x0004,
   THREADSTATE_FROZEN  = 0x0005
};
typedef DWORD THREADSTATE;
```

```csharp
public enum enum_THREADSTATE { 
   THREADSTATE_RUNNING = 0x0001,
   THREADSTATE_STOPPED = 0x0002,
   THREADSTATE_FRESH   = 0x0003,
   THREADSTATE_DEAD    = 0x0004,
   THREADSTATE_FROZEN  = 0x0005
};
```

## <a name="fields"></a>Pola
 `THREADSTATE_RUNNING`\
 Wskazuje, że wątek jest uruchomiony.

 `THREADSTATE_STOPPED`\
 Wskazuje, że wątek został zatrzymany ze względu na punkt przerwania.

 `THREADSTATE_FRESH`\
 Wskazuje, że wątek został utworzony, ale nie jest jeszcze uruchomiony kod.

 `THREADSTATE_DEAD`\
 Wskazuje, że wątek jest martwy.

 `THREADSTATE_FROZEN`\
 Wskazuje, że wątek jest zablokowany (nie można wykonać wykonywania).

## <a name="remarks"></a>Uwagi
 Używane dla `dwThreadState` pola struktury [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) .

## <a name="requirements"></a>Wymagania
 Nagłówek: Msdbg. h

 Przestrzeń nazw: Microsoft. VisualStudio. Debugger. Interop

 Zestaw: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Zobacz też
- [Wyliczenia](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)
