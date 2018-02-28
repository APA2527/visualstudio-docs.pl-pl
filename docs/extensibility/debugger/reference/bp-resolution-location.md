---
title: BP_RESOLUTION_LOCATION | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BP_RESOLUTION_LOCATION
helpviewer_keywords:
- BP_RESOLUTION_LOCATION structure
ms.assetid: 21dc5246-69c1-43e3-855c-9cd4e596c0e6
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a85c6c097867aea17be4b4aeca1431a05c74903a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="bpresolutionlocation"></a>BP_RESOLUTION_LOCATION
Określa struktury rozwiązania lokalizacji punktu przerwania.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
struct _BP_RESOLUTION_LOCATION {  
   BP_TYPE bpType;  
   union {  
      BP_RESOLUTION_CODE bpresCode;  
      BP_RESOLUTION_DATA bpresData;  
      int                unused;  
   } bpResLocation;  
} BP_RESOLUTION_LOCATION;  
```  
  
```csharp  
public struct BP_RESOLUTION_LOCATION {  
   public uint bpType;  
   public IntPtr unionmember1;  
   public IntPtr unionmember2;  
   public IntPtr unionmember3;  
   public uint   unionmember4;  
};  
```  
  
## <a name="members"></a>Elementy członkowskie  
 `bpType`  
 Wartość z zakresu od [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md) wyliczenia, która określa sposób interpretowania `bpResLocation` Unii lub `unionmemberX` elementów członkowskich.  
  
 `bpResLocation.bpresCode`  
 [Tylko C++] Zawiera [BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md) struktury, jeśli `bpType`  =  `BPT_CODE`.  
  
 `bpResLocation.bpresData`  
 [Tylko C++] Zawiera [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md) struktury, jeśli `bpType`  =  `BPT_DATA`.  
  
 `bpResLocation.unused`  
 [Tylko C++] Symbol zastępczy.  
  
 `unionmember1`  
 [C# tylko] Zobacz uwagi na temat sposobu interpretacji.  
  
 `unionmember2`  
 [C# tylko] Zobacz uwagi na temat sposobu interpretacji.  
  
 `unionmember3`  
 [C# tylko] Zobacz uwagi na temat sposobu interpretacji.  
  
 `unionmember4`  
 [C# tylko] Zobacz uwagi na temat sposobu interpretacji.  
  
## <a name="remarks"></a>Uwagi  
 Ta struktura jest elementem członkowskim [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) i [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) struktury.  
  
 [C# tylko] `unionmemberX` Elementy członkowskie będą interpretowane zgodnie z poniższą tabelą. Szukaj w lewej kolumnie dla `bpType` w poprzek następnie wartość do określenia, jakie każdego `unionmemberX` reprezentuje element członkowski i kierowanie `unionmemberX` odpowiednio. Zobacz przykład sposobu interpretowania tej struktury w języku C#.  
  
|`bpLocationType`|`unionmember1`|`unionmember2`|`unionmember3`|`unionmember4`|  
|----------------------|--------------------|--------------------|--------------------|--------------------|  
|`BPT_CODE`|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|-|-|-|  
|`BPT_DATA`|`string`(dane wyrażenie)|`string`(nazwa funkcji)|`string`(nazwa obrazu)|`enum_BP_RES_DATA_FLAGS`|  
  
## <a name="example"></a>Przykład  
 W tym przykładzie pokazano, jak interpretować `BP_RESOLUTION_LOCATION` struktury w języku C#.  
  
```csharp  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(BP_RESOLUTION_LOCATION bprl)  
        {  
            if (bprl.bpType == (uint)enum_BP_TYPE.BPT_CODE)  
            {  
                 IDebugCodeContext2 pContext = (IDebugCodeContext2)Marshal.GetObjectForIUnknown(bp.unionmember1);  
            }  
            else if (bprl.bpType == (uint)enum_BP_TYPE.BPT_DATA)  
            {  
                 string dataExpression = Marshal.PtrToStringBSTR(bp.unionmember3);  
                 string functionName = Marshal.PtrToStringBSTR(bp.unionmember2);  
                 string imageName = Marshal.PtrToStringBSTR(bp.unionmember3);  
                 enum_BP_RES_DATA_FLAGS numElements = (enum_BP_RES_DATA_FLAGS)bp.unionmember4;  
            }  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Zestaw: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Struktury i Unii](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md)   
 [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)   
 [BP_RES_DATA_FLAGS](../../../extensibility/debugger/reference/bp-res-data-flags.md)