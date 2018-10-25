---
title: Implementowanie ewaluatora wyrażeń | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expression evaluators
- debugging [Debugging SDK], expression evaluators
ms.assetid: e9ada7be-845e-4baa-bf8f-e4890e7ba490
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6c5bf8b782d34cb1375f4357cd33f6e47cc22988
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49908460"
---
# <a name="implement-an-expression-evaluator"></a>Implementowanie ewaluatora wyrażeń
> [!IMPORTANT]
>  W programie Visual Studio 2015 ten sposób implementowania ewaluatory wyrażeń jest przestarzały. Uzyskać informacji o implementowaniu ewaluatory wyrażeń CLR, zobacz [ewaluatory wyrażeń CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) i [przykładowe ewaluatora wyrażeń zarządzane](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Obliczenia wyrażenia jest wzajemne oddziaływania wykresów złożonych aparat debugowania (DE), dostawca symboli (SP), obiekt integratora i Ewaluator wyrażeń (EE). Te cztery składniki są połączone za interfejsów implementowanych przez jeden składnik i używane przez inny.  
  
 EE pobiera wyrażenie DE w postaci ciągu i analizuje ani nie ocenia je. EE uruchamia następujące interfejsy, które są używane przez DE:  
  
- [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)  
  
- [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md)  
  
  EE wywołuje obiekt integratora dostarczonych przez DE, aby uzyskać wartość symboli i obiektów. EE wykorzystuje następujące interfejsy, które są implementowane przez DE:  
  
- [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
- [IDebugArrayObject](../../extensibility/debugger/reference/idebugarrayobject.md)  
  
- [IDebugFunctionObject](../../extensibility/debugger/reference/idebugfunctionobject.md)  
  
- [IDebugPointerObject](../../extensibility/debugger/reference/idebugpointerobject.md)  
  
- [IDebugManagedObject](../../extensibility/debugger/reference/idebugmanagedobject.md)  
  
- [IEnumDebugObjects](../../extensibility/debugger/reference/ienumdebugobjects.md)  
  
- [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)  
  
  Uruchamia EE [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md). `IDebugProperty2` udostępnia mechanizm do opisywania wynikiem oceny wyrażenia, takie jak zmienna lokalna, podstawowy lub obiektu w programie Visual Studio, który następnie wyświetla odpowiednie informacje w **lokalne**, **wyrażenie kontrolne** , lub **bezpośrednie** okna.  
  
  PS otrzymuje EE przez DE podczas jego poprosi o podanie informacji. PS uruchamia interfejsy, które opisują adresów i pola, takie jak następujące interfejsy i ich pochodne:  
  
- [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)  
  
- [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)  
  
- [IDebugField](../../extensibility/debugger/reference/idebugfield.md)  
  
  EE zużywa wszystkich tych interfejsów.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Strategia implementacji ewaluatora wyrażeń](../../extensibility/debugger/expression-evaluator-implementation-strategy.md)  
 Definiuje proces trzech kroków strategia implementacji ewaluatora (EE) wyrażeń.  
  
## <a name="see-also"></a>Zobacz także  
 [Pisanie ewaluatora wyrażeń środowiska CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)