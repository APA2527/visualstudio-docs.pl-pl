---
title: '&lt;postActions — &gt; element (Programowanie Office)'
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <postActions> element
- postActions element
- <postActions> element
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: da0c3ee640d7ae4ec1b61df7a60893a7e1428cd2
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99879439"
---
# <a name="ltpostactionsgt-element-office-development"></a>&lt;postActions — &gt; element (Programowanie Office)
  `postActions`Element `vstav3` przestrzeni nazw zawiera wszystkie `postAction` elementy opisujące akcje po wdrożeniu, które są uruchamiane po zainstalowaniu rozwiązań pakietu Office.

## <a name="syntax"></a>Składnia

```xml
<postActions>
  <postAction>
    <entryPoint>
    </entryPoint>
    <postActionData>
    </postActionData>
  </postAction>
</postActions>
```

## <a name="elements-and-attributes"></a>Elementy i atrybuty
 `postActions`Element jest opcjonalny i znajduje się w `vstav3` przestrzeni nazw. `postActions`W manifeście aplikacji jest zdefiniowany tylko jeden element.

 `postActions`Element nie ma żadnych atrybutów.

 `postActions` ma następujący element.

### <a name="postaction"></a>postAction
 Opcjonalny. Rola `postAction` elementu w `vstav3` przestrzeni nazw jest definiowana w [&#60;postAction&#62; elementu &#40;programowanie Office w&#41;programu Visual Studio ](../vsto/postaction-element-office-development-in-visual-studio.md).

## <a name="post-deployment-action-example"></a>Przykład akcji wykonywanej po wdrożeniu

### <a name="description"></a>Opis
 Poniższy przykład kodu ilustruje `postActions` element w manifeście aplikacji dla rozwiązania pakietu Office wdrożonego za pomocą programu [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] . Ten przykład kodu jest częścią większego przykładu dostępnego w [manifestach aplikacji dla rozwiązań pakietu Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kod

```xml
<vstav3:postActions>
  <vstav3:postAction>
    <vstav3:entryPoint
      class="PostDeploymentAction.PostDeploymentActionSample">
      <assemblyIdentity
        name="PostDeploymentAction"
        version="1.0.0.0"
        language="neutral"
        processorArchitecture="msil" />
    </vstav3:entryPoint>
    <vstav3:postActionData>
    </vstav3:postActionData>
  </vstav3:postAction>
</vstav3:postActions>
```

## <a name="see-also"></a>Zobacz też

- [Manifesty aplikacji dla rozwiązań pakietu Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty wdrożenia dla rozwiązań pakietu Office](../vsto/deployment-manifests-for-office-solutions.md)
- [Manifest aplikacji ClickOnce](../deployment/clickonce-application-manifest.md)
