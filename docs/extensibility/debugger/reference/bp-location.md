---
title: BP_LOCATION | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BP_LOCATION
helpviewer_keywords:
- BP_LOCATION union
ms.assetid: ed1e874c-f289-4c31-8b6c-04dde03ad0f5
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6e268d809442b0101d5d520ca7bdd5f5c37fb62b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="bplocation"></a>BP_LOCATION
Określa typ struktury, używane do opisywania lokalizacji punktu przerwania.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct _BP_LOCATION {  
   BP_LOCATION_TYPE bpLocationType;  
   union {  
      BP_LOCATION_CODE_FILE_LINE   bplocCodeFileLine;  
      BP_LOCATION_CODE_FUNC_OFFSET bplocCodeFuncOffset;  
      BP_LOCATION_CODE_CONTEXT     bplocCodeContext;  
      BP_LOCATION_CODE_STRING      bplocCodeString;  
      BP_LOCATION_CODE_ADDRESS     bplocCodeAddress;  
      BP_LOCATION_DATA_STRING      bplocDataString;  
      BP_LOCATION_RESOLUTION       bplocResolution;  
      DWORD                        unused;  
   } bpLocation;  
} BP_LOCATION;  
```  
  
```csharp  
public struct BP_LOCATION {  
   public uint   bpLocationType;  
   public IntPtr unionmember1;  
   public IntPtr unionmember2;  
   public IntPtr unionmember3;  
   public IntPtr unionmember4;  
};  
```  
  
## <a name="members"></a>Elementy członkowskie  
 `bpLocationType`  
 Wartość z zakresu od [BP_LOCATION_TYPE](../../../extensibility/debugger/reference/bp-location-type.md) wyliczenie sposób interpretowania `bpLocation` Unii lub `unionmemberX` elementów członkowskich.  
  
 `bpLocation`.`bplocCodeFileLine`  
 [Tylko C++] Zawiera [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md) struktury, jeśli `bpLocationType`  =  `BPLT_CODE_FILE_LINE`.  
  
 `bpLocation.bplocCodeFuncOffset`  
 [Tylko C++] Zawiera [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) struktury, jeśli `bpLocationType`  =  `BPLT_CODE_FUNC_OFFSET`.  
  
 `bpLocation.bplocCodeContext`  
 [Tylko C++] Zawiera [BP_LOCATION_CODE_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md) struktury, jeśli `bpLocationType`  =  `BPLT_CODE_CONTEXT`.  
  
 `bpLocation.bplocCodeString`  
 [Tylko C++] Zawiera [BP_LOCATION_CODE_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md) struktury, jeśli `bpLocationType`  =  `BPLT_CODE_STRING`.  
  
 `bpLocation.bplocCodeAddress`  
 [Tylko C++] Zawiera [BP_LOCATION_CODE_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md) struktury, jeśli `bpLocationType`  =  `BPLT_CODE_ADDRESS`.  
  
 `bpLocation.bplocDataString`  
 [Tylko C++] Zawiera [BP_LOCATION_DATA_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md) struktury, jeśli `bpLocationType`  =  `BPLT_DATA_STRING`.  
  
 `bpLocation.bplocResolution`  
 [Tylko C++] Zawiera [BP_LOCATION_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md) struktury, jeśli `bpLocationType`  =  `BPLT_RESOLUTION`.  
  
 `unionmember1`  
 [C# tylko] Zobacz uwagi na temat sposobu interpretacji.  
  
 `unionmember2`  
 [C# tylko] Zobacz uwagi na temat sposobu interpretacji.  
  
 `unionmember3`  
 [C# tylko] Zobacz uwagi na temat sposobu interpretacji.  
  
 `unionmember4`  
 [C# tylko] Zobacz uwagi na temat sposobu interpretacji.  
  
## <a name="remarks"></a>Uwagi  
 Ta struktura jest elementem członkowskim [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) i [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.  
  
 [C# tylko] `unionmemberX` Elementy członkowskie będą interpretowane zgodnie z poniższą tabelą. Szukaj w lewej kolumnie dla `bpLocationType` wartość, a następnie sprawdź w kolumnach, aby ustalić, jakie każdego `unionmemberX` reprezentuje element członkowski i kierowanie `unionmemberX` odpowiednio. Zobacz przykład sposobu interpretowania część tej struktury w języku C#.  
  
|`bpLocationType`|`unionmember1`|`unionmember2`|`unionmember3`|`unionmember4`|  
|----------------------|--------------------|--------------------|--------------------|--------------------|  
|`BPLT_CODE_FILE_LINE`|`string`(context)|[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)|-|-|  
|`BPLT_CODE_FUNC_OFFSET`|`string`(context)|[IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)|-|-|  
|`BPLT_CODE_CONTEXT`|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|-|-|-|  
|`BPLT_CODE_STRING`|`string`(context)|`string`(wyrażenia warunkowego)|-|-|  
|`BPLT_CODE_ADDRESS`|`string`(context)|`string`(adres URL modułu)|`string`(nazwa funkcji)|`string`(adres)|  
|`BPLT_DATA_STRING`|[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)|`string`(context)|`string`(dane wyrażenie)|`uint`(liczba elementów)|  
|`BPLT_RESOLUTION`|[IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)|-|-|-|  
  
## <a name="example"></a>Przykład  
 W tym przykładzie pokazano, jak interpretować `BP_LOCATION` struktury w języku C# dla `BPLT_DATA_STRING` typu. Tego typu pokazano, jak interpretować wszystkie cztery `unionmemberX` należących do wszystkich możliwych formatów (obiekt ciągu i numer).  
  
```csharp  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(BP_LOCATION bp)  
        {  
            if (bp.bpLocationType == (uint)enum_BP_LOCATION_TYPE.BPLT_DATA_STRING)  
            {  
                 IDebugThread2 pThread = (IDebugThread2)Marshal.GetObjectForIUnknown(bp.unionmember1);  
                 string context = Marshal.PtrToStringBSTR(bp.unionmember2);  
                 string dataExpression = Marshal.PtrToStringBSTR(bp.unionmember3);  
                 uint numElements = (uint)Marshal.ReadInt32(bp.unionmember4);  
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
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)   
 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)   
 [BP_LOCATION_CODE_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md)   
 [BP_LOCATION_CODE_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md)   
 [BP_LOCATION_CODE_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md)   
 [BP_LOCATION_DATA_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md)   
 [BP_LOCATION_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md)