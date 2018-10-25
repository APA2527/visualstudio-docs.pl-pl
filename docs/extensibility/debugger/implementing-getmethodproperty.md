---
title: Implementowanie metody GetMethodProperty | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- GetMethodProperty method
- IDebugExpressionEvaluator2 property
ms.assetid: 6305874f-a2c4-4432-834c-07530ea84bff
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5638ab3d65280755de405e19a725336e4102ae2b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49868511"
---
# <a name="implement-getmethodproperty"></a>Implementowanie metody GetMethodProperty
> [!IMPORTANT]
>  W programie Visual Studio 2015 ten sposób implementowania ewaluatory wyrażeń jest przestarzały. Uzyskać informacji o implementowaniu ewaluatory wyrażeń CLR, zobacz [ewaluatory wyrażeń CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) i [przykładowe ewaluatora wyrażeń zarządzane](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Program Visual Studio wywołuje aparat debugowania (DE) [GetDebugProperty](../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md), który z kolei wywołuje [metody GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) Aby uzyskać informacje na temat metody bieżące ramce stosu.  
  
 Ta implementacja `IDebugExpressionEvaluator::GetMethodProperty` wykonuje następujące zadania:  
  
1.  Wywołania [GetContainerField](../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md), przekazując [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) obiektu. Dostawca symboli (SP) zwraca [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) reprezentujący metodę, która zawiera podany adres.  
  
2.  Uzyskuje [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) z `IDebugContainerField`.  
  
3.  Tworzy klasę (o nazwie `CFieldProperty` w tym przykładzie), który zawiera [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) interfejs i zawiera `IDebugMethodField` obiekt zwrócony od PS.  
  
4.  Zwraca `IDebugProperty2` interfejs z `CFieldProperty` obiektu.  
  
## <a name="managed-code"></a>Kod zarządzany  
 Ten przykład pokazuje implementację `IDebugExpressionEvaluator::GetMethodProperty` w kodzie zarządzanym.  
  
```csharp  
namespace EEMC  
{  
    [GuidAttribute("462D4A3D-B257-4AEE-97CD-5918C7531757")]  
    public class EEMCClass : IDebugExpressionEvaluator  
    {  
        public HRESULT GetMethodProperty(  
                IDebugSymbolProvider symbolProvider,  
                IDebugAddress        address,  
                IDebugBinder         binder,  
                int                  includeHiddenLocals,  
            out IDebugProperty2      property)   
        {  
            IDebugContainerField containerField = null;  
            IDebugMethodField methodField       = null;  
            property = null;  
  
            // Get the containing method field.  
            symbolProvider.GetContainerField(address, out containerField);  
            methodField = (IDebugMethodField) containerField;  
  
            // Return the property of method field.  
            property = new CFieldProperty(symbolProvider, address, binder, methodField);  
            return COM.S_OK;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>Niezarządzany kod  
 Ten przykład pokazuje implementację `IDebugExpressionEvaluator::GetMethodProperty` w niezarządzanym kodzie.  
  
```  
[CPP]  
STDMETHODIMP CExpressionEvaluator::GetMethodProperty(  
        in IDebugSymbolProvider *pprovider,  
        in IDebugAddress        *paddress,  
        in IDebugBinder         *pbinder,  
        in BOOL                  includeHiddenLocals,  
        out IDebugProperty2    **ppproperty  
    )  
{  
    if (pprovider == NULL)  
        return E_INVALIDARG;  
  
    if (ppproperty == NULL)  
        return E_INVALIDARG;  
    else  
        *ppproperty = 0;  
  
    HRESULT hr;  
    IDebugContainerField* pcontainer = NULL;  
  
    hr = pprovider->GetContainerField(paddress, &pcontainer);  
    if (FAILED(hr))  
        return hr;  
  
    IDebugMethodField*    pmethod    = NULL;  
    hr = pcontainer->QueryInterface( IID_IDebugMethodField,  
            reinterpret_cast<void**>(&pmethod));  
    pcontainer->Release();  
    if (FAILED(hr))  
        return hr;  
  
    CFieldProperty* pfieldProperty = new CFieldProperty( pprovider,  
                                                         paddress,  
                                                         pbinder,  
                                                         pmethod );  
    pmethod->Release();  
    if (!pfieldProperty)  
        return E_OUTOFMEMORY;  
  
    hr = pfieldProperty->Init();  
    if (FAILED(hr))  
    {  
        pfieldProperty->Release();  
        return hr;  
    }  
  
    hr = pfieldProperty->QueryInterface( IID_IDebugProperty2,  
            reinterpret_cast<void**>(ppproperty));  
    pfieldProperty->Release();  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Przykłady implementacji zmiennych lokalnych](../../extensibility/debugger/sample-implementation-of-locals.md)