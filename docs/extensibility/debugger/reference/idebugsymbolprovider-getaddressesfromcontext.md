---
title: IDebugSymbolProvider::GetAddressesFromContext | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromContext
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromContext method
ms.assetid: a3124883-a255-4543-a5ec-e1c7a97beb69
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 94920e72b7d83e45fc7d7e49849f3c1983b180ef
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49931522"
---
# <a name="idebugsymbolprovidergetaddressesfromcontext"></a>IDebugSymbolProvider::GetAddressesFromContext
Ta metoda mapuje kontekstu dokumentu na tablicę adresów debugowania.  
  
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
  
#### <a name="parameters"></a>Parametry  
 `pDocContext`  
 [in] Kontekst dokumentu.  
  
 `fStatmentOnly`  
 [in] W przypadku opcji TRUE ogranicza adresy debugowania do pojedynczej instrukcji.  
  
 `ppEnumBegAddresses`  
 [out] Zwraca moduł wyliczający dla wyjścia adresów debugowania skojarzone z tym instrukcja lub wiersza.  
  
 `ppEnumEndAddresses`  
 [out] Zwraca [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) modułu wyliczającego dla końcowy adresów debugowania skojarzone z tym instrukcja lub wiersza.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Kontekst dokumentu zazwyczaj wskazuje zakres wierszy źródłowych. Ta metoda zapewnia początkowy i końcowy adres debugowania powiązanych z tymi wierszami. W niektórych językach umożliwiają instrukcji, które rozciągają się wiele wierszy lub wiersze, które zawiera więcej niż jedną instrukcję. Ta metoda zapewnia flagi, aby ograniczyć adresy debugowania do pojedynczej instrukcji.  
  
 Istnieje możliwość dla pojedynczej instrukcji wielu adresów debugowania, tak jak w przypadku szablonów.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)