---
title: 'IDebugSymbolProvider:: GetAddressesFromContext | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromContext
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromContext method
ms.assetid: a3124883-a255-4543-a5ec-e1c7a97beb69
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a9a7b3f9096bbbef1c4de2161c6bb3b6a4c59e4d
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99897201"
---
# <a name="idebugsymbolprovidergetaddressesfromcontext"></a>IDebugSymbolProvider::GetAddressesFromContext
Ta metoda mapuje kontekst dokumentu na tablicę adresów debugowania.

## <a name="syntax"></a>Składnia

```cpp
HRESULT GetAddressesFromContext( 
   IDebugDocumentContext2* pDocContext,
   BOOL                    fStatmentOnly,
   IEnumDebugAddresses**   ppEnumBegAddresses,
   IEnumDebugAddresses**   ppEnumEndAddresses
);
```

```csharp
int GetAddressesFromContext(
   IDebugDocumentContext2  pDocContext,
   bool                    fStatmentOnly,
   out IEnumDebugAddresses ppEnumBegAddresses,
   out IEnumDebugAddresses ppEnumEndAddresses
);
```

## <a name="parameters"></a>Parametry
`pDocContext`\
podczas Kontekst dokumentu.

`fStatmentOnly`\
podczas W przypadku wartości TRUE program ogranicza adresy debugowania do pojedynczej instrukcji.

`ppEnumBegAddresses`\
określoną Zwraca moduł wyliczający dla początkowych adresów debugowania skojarzonych z tą instrukcją lub wierszem.

`ppEnumEndAddresses`\
określoną Zwraca moduł wyliczający [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) dla końcowych adresów debugowania skojarzonych z tą instrukcją lub wierszem.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca kod błędu.

## <a name="remarks"></a>Uwagi
 Kontekst dokumentu zwykle wskazuje zakres wierszy źródłowych. Ta metoda zapewnia początkową i końcową adresy debugowania skojarzone z tymi wierszami. Niektóre języki umożliwiają stosowanie instrukcji obejmujących wiele wierszy lub wierszy zawierających więcej niż jedną instrukcję. Ta metoda zapewnia flagę, aby ograniczyć adresy debugowania do pojedynczej instrukcji.

 Istnieje możliwość, że pojedyncza instrukcja ma wiele adresów debugowania, tak jak w przypadku szablonów.

## <a name="see-also"></a>Zobacz też
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)
- [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)
