---
title: 'Porady: Dodawanie pliku zasobu | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- resource files [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, resource files
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0091054c0c0d2cfb7f19f2ca46839cfdcf47832b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49861192"
---
# <a name="how-to-add-a-resource-file"></a>Porady: Dodawanie pliku zasobu
  Polecenia służące do dodawania plików zasobów znajduje się w menu skrótów dla węzła rozwiązania i funkcja węzły w Eksploratorze rozwiązań. Aby uzyskać więcej informacji, zobacz [rozwiązań SharePoint lokalizowanie](../sharepoint/localizing-sharepoint-solutions.md).  
  
### <a name="to-add-a-global-resource-file-to-a-sharepoint-solution"></a>Aby dodać plik globalnych zasobów do rozwiązania programu SharePoint  
  
1. W [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otwórz rozwiązanie programu SharePoint.  
  
2. W **Eksploratora rozwiązań**, wybierz węzeł projektu programu SharePoint, a następnie na pasku menu wybierz **projektu** > **Dodaj nowy element**.  
  
3. W **Dodaj nowy element** okna dialogowego wybierz **plik zasobów globalnych** szablonu, a następnie wybierz **Dodaj** przycisku.  
  
   > [!NOTE]  
   >  Plik zasobów globalnych szablonu elementu projektu pojawia się tylko w przypadku wybrania elementu projektu programu SharePoint.  
  
4. W **Dodaj zasób** okna dialogowego Wybierz kulturę pliku zasobów, takich jak angielski (Stany Zjednoczone).  
  
    Ten krok powoduje dodanie plik globalnych zasobów do swojego rozwiązania w formacie Resource_x_**.** <em>kultury</em><strong>.</strong> Program resx, takich jak *Resource1.en US.resx*.  
  
5. Gdy **Edytor zasobów** zostanie otwarty w [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], dodać zasoby do pliku zasobów.  
  
### <a name="to-add-a-feature-resource-file-to-a-sharepoint-feature"></a>Aby dodać plik zasobów funkcji do funkcji SharePoint  
  
1.  Jeśli rozwiązania programu SharePoint nie jest już otwarty w [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otwórz rozwiązanie.  
  
2.  W **Eksploratora rozwiązań**, otwórz menu skrótów dla nazwy funkcji w obszarze **funkcji** węzła, a następnie wybierz **Dodaj zasób funkcji**.  
  
     Ten krok powoduje dodanie pliku zasobu do funkcji w formacie _Nazwaplikuzasobów_**.** _kultury_**resx**, takich jak *Feature1.en US.resx*.  
  
3.  Gdy **Edytor zasobów** zostanie otwarty w [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], dodać zasoby do pliku zasobów.  
  
## <a name="see-also"></a>Zobacz także
 [Opracowywanie rozwiązań SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
 
