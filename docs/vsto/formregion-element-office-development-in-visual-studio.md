---
title: '&lt;elementu formRegion&gt; — element (Office development w programie Visual Studio)'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <formRegion> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4fc98e66cd16298839e79f25c95e256f10398c49
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "35677484"
---
# <a name="ltformregiongt-element-office-development-in-visual-studio"></a>&lt;elementu formRegion&gt; — element (Office development w programie Visual Studio)
  `formRegion` Elementu `vstov4` obszar nazw identyfikuje programu Microsoft Office Outlook regionu formularza, który jest skojarzony z dodatku narzędzi VSTO.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<formRegion  
  name>  
  <messageClass  
    name/>  
</formRegion>  
```  
  
## <a name="elements-and-attributes"></a>Atrybuty i elementy  
 `formRegion` Elementu `vstov4` obszar nazw identyfikuje region formularza, który jest skojarzony z dodatku narzędzi VSTO dla programu Outlook. Jest wymagane tylko dla dodatków narzędzi VSTO dla programu Outlook, obejmujących regionów formularza.  
  
 Może istnieć wiele `formRegion` elementy zdefiniowane wewnątrz `formRegions` element dla pojedynczego dodatku narzędzi VSTO.  
  
 `formRegion` Element ma atrybut.  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`name`|Wymagane. Określa nazwę regionu formularza.|  
  
 `formRegion` Element ma następujących elementów podrzędnych.  
  
### <a name="messageclass"></a>Klasa_wiadomości  
 `messageClass` Element identyfikuje formularza programu Outlook, który jest skojarzony z regionu formularza.  
  
 `messageClass` Element ma atrybut.  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`name`|Wymagane. Identyfikuje formularz, który jest skojarzony z regionu formularza.|  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie kodu pokazano `formRegion` elementu w manifeście aplikacji dla dodatku narzędzi VSTO dla programu Outlook wdrażane za pomocą [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Istnieją trzy klasy wiadomości, skojarzone z tym regionem jeden formularz. Ten przykład kodu jest częścią większego przykładu przewidzianego w [manifesty aplikacji dla rozwiązań pakietu Office](../vsto/application-manifests-for-office-solutions.md).  
  
```xml  
<vstov4:formRegion  
    name="OutlookAddIn1.FormRegion1">  
  <vstov4:messageClass name="IPM.Note" />  
  <vstov4:messageClass name="IPM.Contact" />  
  <vstov4:messageClass name="IPM.Appointment" />  
</vstov4:formRegion>  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Tworzenie regionów formularzy programu Outlook](../vsto/creating-outlook-form-regions.md)   
 [Manifesty aplikacji dla rozwiązań pakietu Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty wdrożenia dla rozwiązań pakietu Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [Manifest aplikacji ClickOnce](/visualstudio/deployment/clickonce-application-manifest)  
  
  