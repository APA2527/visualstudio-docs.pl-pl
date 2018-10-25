---
title: 'Porady: Ustawianie informacji o konfiguracji dla rozwiązań pakietu Office'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], configuration files
- configuration files [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f0557301c00285a93cc173e872459d812c61fdca
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49949464"
---
# <a name="how-to-set-up-configuration-information-for-an-office-solution"></a>Porady: Ustawianie informacji o konfiguracji dla rozwiązań pakietu Office
  Pliki konfiguracji można użyć do konfigurowania ustawień, które są specyficzne dla rozwiązania pakietu Office. Można określić ustawienia, takie jak zasady tworzenia powiązań zestawów, obiekty usług zdalnych, debugowania i ustawienia śledzenia.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-configuration-file-to-your-office-project"></a>Aby dodać plik konfiguracji do projektu pakietu Office  
  
1. Na **projektu** menu, kliknij przycisk **Dodaj nowy element**.  
  
2. W **kategorie** okienku kliknij **ogólne**.  
  
3. W **szablony** okienku wybierz **pliku konfiguracji aplikacji**.  
  
4. W **nazwa** wpisz taką samą nazwę jak zestawu oraz rozszerzenie *.config*. Na przykład plik konfiguracji dla zestawu projektu programu Excel o nazwie *ExcelWorkbook1.dll* będą miały postać *ExcelWorkbook1.dll.config*.  
  
5. Kliknij przycisk **Dodaj**.  
  
6. Utwórz plik konfiguracji zgodnie z schemat pliku konfiguracji aplikacji. Aby uzyskać więcej informacji, zobacz [schemat pliku konfiguracji dla programu .NET Framework](/dotnet/framework/configure-apps/file-schema/index).  
  
   Nie istnieją żadne specjalne uwagi dotyczące za pomocą plików konfiguracji przy użyciu projektów pakietu Office.  
  
## <a name="see-also"></a>Zobacz także  
 [Schemat pliku konfiguracji dla programu .NET Framework](/dotnet/framework/configure-apps/file-schema/index)   
 [Projektowanie i tworzenie rozwiązań pakietu Office](../vsto/designing-and-creating-office-solutions.md)   
 [Wdrażanie rozwiązania do pakietu Office](../vsto/deploying-an-office-solution.md)  
  
  