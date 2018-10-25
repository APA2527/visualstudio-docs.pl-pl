---
title: Rozszerzanie projektów SharePoint | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 56e714f910a2421a909cba6714e65d21b66991ce
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49835842"
---
# <a name="extend-sharepoint-projects"></a>Rozszerzanie projektów SharePoint
  Tworzenie rozszerzenia projektu, jeśli chcesz dostosować funkcje na poziomie projektu dla projektów programu SharePoint. Na przykład można dodać właściwości niestandardowe projektu lub reagowania na zdarzenia na poziomie projektu, które są wywoływane, gdy użytkownik rozwija rozwiązania programu SharePoint w programie Visual Studio.  
  
## <a name="create-project-extensions"></a>Utwórz projekt rozszerzenia
 Tworzenie zestawu rozszerzeń programu Visual Studio, który implementuje rozszerzenie elementu projektu, <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> interfejsu. Aby uzyskać więcej informacji, zobacz [porady: Tworzenie rozszerzenia projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
 Podczas tworzenia rozszerzenia projektu, można również dodać następujące funkcje do projektów SharePoint:  
  
- Dodawanie pozycji menu skrótów. Element menu pojawia się po otwarciu menu skrótów dla węzła projektu programu SharePoint w **Eksploratora rozwiązań** przez kliknięcie prawym przyciskiem myszy węzeł lub wybierając go, a następnie wybierając **Shift** +  **F10** kluczy. Aby uzyskać więcej informacji, zobacz [porady: Dodawanie pozycji menu skrótów do projektów SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md).  
  
- Dodawanie właściwości niestandardowej. Właściwość pojawia się w **właściwości** okna po wybraniu projektu programu SharePoint w **Eksploratora rozwiązań**. Aby uzyskać więcej informacji, zobacz [porady: Dodawanie właściwości do projektów SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md).  
  
  Aby uzyskać wskazówki, które pokazuje, jak tworzenie, wdrażanie i testowanie rozszerzenia projektu, zobacz [wskazówki: Tworzenie rozszerzenia projektu SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md).  
  
## <a name="understand-the-relationship-between-project-extensions-and-project-instances"></a>Zrozumienie relacji między rozszerzeniami projektu i wystąpień projektu
 Podczas tworzenia rozszerzenia projektu rozszerzenia ładuje po otwarciu dowolnego rodzaju projektu programu SharePoint w [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] zawiera kilka szablonów projektu programu SharePoint, takich jak definicje list, typy zawartości i odbiorcy zdarzeń. Dostępna jest tylko jeden typ projektu programu SharePoint. Typy projektów, które pojawiają się w **nowy projekt** okno dialogowe są tylko te szablony, które powiązać razem jeden lub więcej elementów projektu programu SharePoint. Ponieważ istnieje tylko jeden typ projektu programu SharePoint, rozszerzeń utworzonych dla jednego projektu mają zastosowanie do wszystkich projektów programu SharePoint. Nie na przykład można utworzyć rozszerzenia, które dotyczą tylko **typu zawartości** projektu.  
  
 Dostęp do wystąpienia określonego projektu, obsługę jednej z <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents> zdarzenia *projectService* parametru w danej implementacji <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> metody. Na przykład, aby określić, gdy projekt SharePoint jest dodawany do rozwiązania, należy obsługiwać <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectAdded> zdarzeń. Aby uzyskać więcej informacji, zobacz [porady: Tworzenie rozszerzenia projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
## <a name="see-also"></a>Zobacz także
 [Porady: Tworzenie rozszerzenia projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [Porady: Dodawanie pozycji menu skrótów do projektów SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)   
 [Porady: Dodawanie właściwości do projektów SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [Wskazówki: Tworzenie rozszerzenia projektu SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)   
 [Definiowanie niestandardowych typów elementów projektu SharePoint](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Rozszerzanie elementów projektu programu SharePoint](../sharepoint/extending-sharepoint-project-items.md)   
 [Rozszerzanie pakowania i wdrażania SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Rozszerzanie systemu projektu SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)  
  
  
