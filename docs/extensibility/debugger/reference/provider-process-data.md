---
title: PROVIDER_PROCESS_DATA | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROVIDER_PROCESS_DATA
helpviewer_keywords:
- PROVIDER_PROCESS_DATA structure
ms.assetid: ec2362ed-4a0c-4a09-9d66-8ff04e4f41ee
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5845ce7f512a24d341f73afa9f9905339dda87cb
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99922969"
---
# <a name="provider_process_data"></a>PROVIDER_PROCESS_DATA
Ta struktura zawiera informacje dotyczące procesów uruchomionych na komputerze.

## <a name="syntax"></a>Składnia

```cpp
typedef struct tagPROVIDER_PROCESS_DATA {
   PROVIDER_FIELDS    Fields;
   PROGRAM_NODE_ARRAY ProgramNodes;
   BOOL               fIsDebuggerPresent;
} PROVIDER_PROCESS_DATA;
```

```csharp
public struct PROVIDER_PROCESS_DATA {
   public uint               Fields;
   public PROGRAM_NODE_ARRAY ProgramNodes;
   public int                fIsDebuggerPresent;
}
```

## <a name="members"></a>Elementy członkowskie
 `Fields`\
 Kombinacja flag z wyliczenia [PROVIDER_FIELDS](../../../extensibility/debugger/reference/provider-fields.md) , wskazującą, które pola są wypełnione.

 `ProgramNodes`\
 Struktura [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md) , która zawiera tablicę węzłów programu.

 `fIsDebuggerPresent`\
 Niezerowe ( `TRUE` ) Jeśli [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] debuger jest uruchomiony, zero ( `FALSE` ), jeśli nie jest.

## <a name="remarks"></a>Uwagi
 Ta struktura jest przenoszona do metody [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) , gdzie jest wypełniona.

## <a name="requirements"></a>Wymagania
 Nagłówek: Msdbg. h

 Przestrzeń nazw: Microsoft. VisualStudio. Debugger. Interop

 Zestaw: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Zobacz też
- [Struktury i związki](../../../extensibility/debugger/reference/structures-and-unions.md)
- [PROVIDER_FIELDS](../../../extensibility/debugger/reference/provider-fields.md)
- [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md)
- [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)
