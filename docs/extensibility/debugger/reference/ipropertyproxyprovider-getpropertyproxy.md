---
title: 'IPropertyProxyProvider:: GetPropertyProxy | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyProvider::GetPropertyProxy
helpviewer_keywords:
- IPropertyProxyProvider::GetPropertyProxy
ms.assetid: 3ebb7515-5bfe-48f4-9b8d-721b8f664eb6
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 35c23fc56c883845bdb7fb73daa60a845ee5e21a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "80714828"
---
# <a name="ipropertyproxyprovidergetpropertyproxy"></a>IPropertyProxyProvider::GetPropertyProxy
Pobiera interfejs proxy właściwości dla podanego identyfikatora serwera proxy.

## <a name="syntax"></a>Składnia

```cpp
HRESULT GetPropertyProxy(
   DWORD                  dwID,
   IPropertyProxyEESide** proxy
);
```

```csharp
int GetPropertyProxy(
   uint                     dwID,
   out IPropertyProxyEESide proxy
);
```

## <a name="parameters"></a>Parametry
`dwID`\
podczas Identyfikator żądanego serwera proxy właściwości.

`proxy`\
określoną Zwraca obiekt [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) .

## <a name="return-value"></a>Wartość zwracana
 Jeśli powiedzie się, zwraca `S_OK` ; w przeciwnym razie zwraca kod błędu.

## <a name="remarks"></a>Uwagi
 Aby zapewnić obsługę wizualizatorów typu zewnętrznego, ta metoda zwykle przekazuje wywołanie do metody [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md) . Zobacz [wizualizowanie i wyświetlanie danych](../../../extensibility/debugger/visualizing-and-viewing-data.md) , aby uzyskać szczegółowe informacje na temat sposobu uzyskiwania IEEVisualizerService.

## <a name="see-also"></a>Zobacz też
- [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md)
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)
- [Wizualizacja i wyświetlanie danych](../../../extensibility/debugger/visualizing-and-viewing-data.md)
