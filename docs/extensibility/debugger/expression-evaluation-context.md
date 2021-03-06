---
title: Kontekst oceny wyrażenia | Microsoft Docs
description: Informacje o kontekście oceny wyrażeń, który reprezentuje kontekst oceny wyrażenia i istnieje, gdy program został zatrzymany w punkcie przerwania.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 127746b06ef09496ef8f50aa874ff32e2f983f65
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99921535"
---
# <a name="expression-evaluation-context"></a>Kontekst oceny wyrażenia
W [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] debugowaniu **kontekst oceny wyrażenia**:

- Reprezentuje kontekst oceny wyrażenia. Ogólnie rzecz biorąc, kontekst oceny odnosi się do zakresu leksykalnego, w którym można ocenić zmienne, parametry, funkcje i metody. Na przykład kontekst oceny wyrażenia skojarzonego z ramką stosu zapewni kontekst do oceny zmiennych lokalnych, parametrów metody i elementów członkowskich klasy (jeśli dotyczy).

- Istnieje, gdy program został zatrzymany w punkcie przerwania. Samo wyrażenie jest strukturą danych reprezentującą przeanalizowane wyrażenie, które jest gotowe do powiązania i oceny w danym kontekście.

     W bardziej szczegółowym przypadku wyrażenia są tworzone przy użyciu metody [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) . Gdy wyrażenie jest oceniane, generuje ciąg drukowalny zawierający nazwę i typ zmiennej lub argumentu oraz jego wartość. Ten ciąg jest wyświetlany w okno wyrażeń kontrolnych lub w oknie zmiennych środowiska IDE.

     Za pomocą `BSTR` i interfejsu [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) aparat debugowania (de) może utworzyć interfejs [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) przez analizowanie wyrażenia. `IDebugExpression2`Za pomocą interfejsu, można uzyskać wartość przez obliczenie wyrażenia synchronicznego lub asynchronicznego. Ta wartość oraz nazwa i typ zmiennej lub argumentu są wysyłane do IDE w celu wyświetlenia.

## <a name="see-also"></a>Zobacz też
- [Interfejsy oceny wyrażeń](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [Konteksty debugera](../../extensibility/debugger/debugger-contexts.md)
