---
title: ADDRESS_KIND | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- ADDRESS_KIND
helpviewer_keywords:
- ADDRESS_KIND enumeration
ms.assetid: 3a12fbec-7088-4cf9-8f6f-ad8ddec6009a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 53c93cb8e7d2c021c95c4b11047b5d699f7ae1c4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="addresskind"></a>ADDRESS_KIND
Określa typy adresów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
enum enum_ADDRESS_KIND {  
   ADDRESS_KIND_NATIVE                  = 0x0001,  
   ADDRESS_KIND_UNMANAGED_THIS_RELATIVE = 0x0002,  
   ADDRESS_KIND_UNMANAGED_PHYSICAL      = 0x0005,  
   ADDRESS_KIND_METADATA_METHOD         = 0x0010,  
   ADDRESS_KIND_METADATA_FIELD          = 0x0011,  
   ADDRESS_KIND_METADATA_LOCAL          = 0x0012,  
   ADDRESS_KIND_METADATA_PARAM          = 0x0013,  
   ADDRESS_KIND_METADATA_ARRAYELEM      = 0x0014,  
   ADDRESS_KIND_METADATA_RETVAL         = 0x0015,  
};  
typedef DWORD ADDRESS_KIND;  
```  
  
```csharp  
public enum enum_ADDRESS_KIND {  
   ADDRESS_KIND_NATIVE                  = 0x0001,  
   ADDRESS_KIND_UNMANAGED_THIS_RELATIVE = 0x0002,  
   ADDRESS_KIND_UNMANAGED_PHYSICAL      = 0x0005,  
   ADDRESS_KIND_METADATA_METHOD         = 0x0010,  
   ADDRESS_KIND_METADATA_FIELD          = 0x0011,  
   ADDRESS_KIND_METADATA_LOCAL          = 0x0012,  
   ADDRESS_KIND_METADATA_PARAM          = 0x0013,  
   ADDRESS_KIND_METADATA_ARRAYELEM      = 0x0014,  
   ADDRESS_KIND_METADATA_RETVAL         = 0x0015,  
};  
```  
  
## <a name="terms"></a>Warunki  
 ADDRESS_KIND_NATIVE  
 Adresu natywnego reprezentowany przez [NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md) struktury.  
  
 ADDRESS_KIND_UNMANAGED_THIS_RELATIVE  
 Niezarządzane adres względem `this` (`Me` w języku Visual Basic) wskaźnik i reprezentowany przez [UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md) struktury.  
  
 ADDRESS_KIND_UNMANAGED_PHYSICAL  
 Niezarządzane adresu fizycznego reprezentowany przez [UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md) struktury.  
  
 ADDRESS_KIND_METHOD  
 Metoda klasy reprezentowany przez [METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md) struktury.  
  
 ADDRESS_KIND_FIELD  
 To pole klasy reprezentowany przez [METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md) struktury.  
  
 ADDRESS_KIND_LOCAL  
 Ten adres jest zmienną lokalną i jest reprezentowany przez [METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md) struktury.  
  
 ADDRESS_KIND_PARAM  
 Metody lub funkcji parametru reprezentowanego przez [METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md) struktury.  
  
 ADDRESS_KIND_ARRAYELEM  
 Element tablicy reprezentowany przez [METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md) struktury.  
  
 ADDRESS_KIND_RETVAL  
 Wartość zwracaną, reprezentowany przez [METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md) struktury.  
  
## <a name="remarks"></a>Uwagi  
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) metoda zwraca [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) strukturę, która zawiera Unię możliwe struktur [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) struktury. `dwKind` Pole `DEBUG_ADDRESS_UNION` struktury blokad `ADDRESS_KIND` wartości i opisuje jak interpretować pole Unii.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Wyliczenia](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)