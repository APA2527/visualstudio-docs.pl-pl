---
title: DISASSEMBLY_STREAM_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DISASSEMBLY_STREAM_FIELDS
helpviewer_keywords:
- DISASSEMBLY_STREAM_FIELDS enumeration
ms.assetid: cfc9b4de-c756-4844-bea7-d9f186a51d1b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d10f2143cbefa86442e4087ac098020f5f2bd6ac
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "80737355"
---
# <a name="disassembly_stream_fields"></a>DISASSEMBLY_STREAM_FIELDS
Określa informacje, które mają zostać pobrane dla pola demontażu.

## <a name="syntax"></a>Składnia

```cpp
enum enum_DISASSEMBLY_STREAM_FIELDS {
    DSF_ADDRESS          = 0x00000001,
    DSF_ADDRESSOFFSET    = 0x00000002,
    DSF_CODEBYTES        = 0x00000004,
    DSF_OPCODE           = 0x00000008,
    DSF_OPERANDS         = 0x00000010,
    DSF_SYMBOL           = 0x00000020,
    DSF_CODELOCATIONID   = 0x00000040,
    DSF_POSITION         = 0x00000080,
    DSF_DOCUMENTURL      = 0x00000100,
    DSF_BYTEOFFSET       = 0x00000200,
    DSF_FLAGS            = 0x00000400,
    DSF_OPERANDS_SYMBOLS = 0x00010000,
    DSF_ALL              = 0x000107ff
};
typedef DWORD DISASSEMBLY_STREAM_FIELDS;
```

```csharp
public enum enum_DISASSEMBLY_STREAM_FIELDS {
    DSF_ADDRESS          = 0x00000001,
    DSF_ADDRESSOFFSET    = 0x00000002,
    DSF_CODEBYTES        = 0x00000004,
    DSF_OPCODE           = 0x00000008,
    DSF_OPERANDS         = 0x00000010,
    DSF_SYMBOL           = 0x00000020,
    DSF_CODELOCATIONID   = 0x00000040,
    DSF_POSITION         = 0x00000080,
    DSF_DOCUMENTURL      = 0x00000100,
    DSF_BYTEOFFSET       = 0x00000200,
    DSF_FLAGS            = 0x00000400,
    DSF_OPERANDS_SYMBOLS = 0x00010000,
    DSF_ALL              = 0x000107ff
};
```

## <a name="fields"></a>Pola
`DSF_ADDRESS`\
Zainicjuj/Użyj `bstrAddress` pola.

`DSF_ADDRESSOFFSET`\
Zainicjuj/Użyj `bstrAddressOffset` pola.

`DSF_CODEBYTES`\
Zainicjuj/Użyj `bstrCodeBytes` pola.

`DSF_OPCODE`\
Zainicjuj/Użyj `bstrOpCode` pola.

`DSF_OPERANDS`\
Zainicjuj/Użyj `bstrOperands` pola.

`DSF_SYMBOL`\
Zainicjuj/Użyj `bstrSymbol` pola.

`DSF_CODELOCATIONID`\
Zainicjuj/Użyj `uCodeLocationId` pola.

`DSF_POSITION`\
Inicjowanie/używanie `posBeg` pól i `posEnd` .

`DSF_DOCUMENTURL`\
Zainicjuj/Użyj `bstrDocumentUrl` pola.

`DSF_BYTEOFFSET`\
Zainicjuj/Użyj `dwByteOffset` pola.

`DSF_FLAGS`\
Zainicjuj/Użyj `dwFlags` pola ([DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)).

`DSF_OPERANDS_SYMBOLS`\
Dołącz nazwy symboli w `bstrOperands` polu.

`DSF_ALL`\
Określa wszystkie pola dla strumienia rozasemblera.

## <a name="remarks"></a>Uwagi
Przekazuje jako parametr do metody [Read](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) , aby wskazać, które pola struktury [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) mają być inicjowane.

Używane dla `dwFields` składowej struktury, `DisassemblyData` Aby wskazać, które pola są używane i są ważne podczas zwracania struktury.

Te wartości mogą być połączone z bitową `OR` .

## <a name="requirements"></a>Wymagania
Nagłówek: Msdbg. h

Przestrzeń nazw: Microsoft. VisualStudio. Debugger. Interop

Zestaw: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Zobacz też
- [Wyliczenia](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)
- [Odczyt](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)
- [DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)
