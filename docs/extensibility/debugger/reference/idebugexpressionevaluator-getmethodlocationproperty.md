---
title: 'IDebugExpressionEvaluator:: GetMethodLocationProperty | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty
helpviewer_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty method
ms.assetid: 52c42a2e-f144-476b-8bef-442464c8fe8e
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 13759bc8598c4739fbb9d2263dd8dc7d1b84c16e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99930424"
---
# <a name="idebugexpressionevaluatorgetmethodlocationproperty"></a>IDebugExpressionEvaluator::GetMethodLocationProperty
Ta metoda konwertuje lokalizację metody i przesunięcie na adres pamięci.

## <a name="syntax"></a>Składnia

```cpp
HRESULT GetMethodLocationProperty( 
   LPCOLESTR             upstrFullyQualifiedMethodPlusOffset,
   IDebugSymbolProvider* pSymbolProvider,
   IDebugAddress*        pAddress,
   IDebugBinder*         pBinder,
   IDebugProperty2**     ppProperty
);
```

```csharp
int GetMethodLocationProperty(
   string               upstrFullyQualifiedMethodPlusOffset,
   IDebugSymbolProvider pSymbolProvider,
   IDebugAddress        pAddress,
   IDebugBinder         pBinder,
   out IDebugProperty2  ppProperty
);
```

## <a name="parameters"></a>Parametry
`upstrFullyQualifiedMethodPlusOffset`\
podczas Lokalizacja metody i przesunięcie wyrażone jako ciąg.

`pSymbolProvider`\
podczas Dostawca symboli wyrażony jako obiekt [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) .

`pAddress`\
podczas Adres w ramach metody wyrażony jako obiekt [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) .

`pBinder`\
podczas Spinacz wyrażony jako obiekt [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) .

`ppProperty`\
określoną Zwraca interfejs [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) , który reprezentuje adres pamięci.

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca kod błędu.

## <a name="remarks"></a>Uwagi
 Zwrócony adres może służyć do ustawiania punktu przerwania, na przykład.

 Pomimo nazwy `upstrFullyQualifiedMethodPlusOffset` , ten parametr można przesłać częściowo kwalifikowaną nazwę metody. W takim przypadku wybrana metoda jest tą, która znajduje się w tej samej metodzie `pAddress` . Sposób interpretacji tego parametru jest do implementacji ewaluatora wyrażeń i obsługiwanego przez niego języka.

## <a name="see-also"></a>Zobacz też
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)
