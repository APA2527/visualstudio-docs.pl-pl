---
title: PROCESS_INFO_FLAGS | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6e95e9f66b804fed102c0d51aa17a1bfe4f51ca5
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2018
---
# <a name="processinfoflags"></a>PROCESS_INFO_FLAGS

W tym artykule opisano lub określa właściwości procesu.

## <a name="syntax"></a>Składnia

```cpp
enum enum_PROCESS_INFO_FLAGS { 
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,
   PIFLAG_PROCESS_STOPPED   = 0x00000004,
   PIFLAG_PROCESS_RUNNING   = 0x00000008,
};
typedef DWORD PROCESS_INFO_FLAGS;
```

```csharp
enum enum_PROCESS_INFO_FLAGS { 
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,
   PIFLAG_PROCESS_STOPPED   = 0x00000004,
   PIFLAG_PROCESS_RUNNING   = 0x00000008,
};
```

## <a name="members"></a>Elementy członkowskie

PIFLAG_SYSTEM_PROCESS  
Wskazuje, że proces jest proces systemowy.

PIFLAG_DEBUGGER_ATTACHED  
Wskazuje, że proces jest debugowany przez debuger. Być może jest ona [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] debugera, lub może być niektóre inne debugera, na przykład WinDbg.

PIFLAG_PROCESS_STOPPED  
Wskazuje, że proces jest zatrzymany. Prawidłowe tylko wtedy, gdy `PIFLAG_DEBUGGER_ATTACHED` jest określona. Jest dostępna w programie Visual Studio 2005 i nowszej.

PIFLAG_PROCESS_RUNNING  
Wskazuje, że proces jest uruchomiony. Prawidłowe tylko wtedy, gdy `PIFLAG_DEBUGGER_ATTACHED` jest określona. Jest dostępna w programie Visual Studio 2005 i nowszej.

## <a name="remarks"></a>Uwagi

Używany do `Flags` członkiem [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktury.

Te flagi mogą być łączone z bitowego `OR`.

## <a name="requirements"></a>Wymagania

Nagłówek: msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Zobacz też

[Wyliczenia](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)