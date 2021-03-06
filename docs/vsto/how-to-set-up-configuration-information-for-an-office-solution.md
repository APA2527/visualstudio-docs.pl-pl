---
title: Konfigurowanie informacji o konfiguracji dla rozwiązania pakietu Office
description: Dowiedz się, jak za pomocą plików konfiguracji skonfigurować ustawienia specyficzne dla rozwiązań Microsoft Office.
ms.custom: SEO-VS-2020
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], configuration files
- configuration files [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: da3a08ad9b3f6c78a10891e7d8ef2093ab46305d
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99927707"
---
# <a name="how-to-set-up-configuration-information-for-an-office-solution"></a>Instrukcje: Konfigurowanie informacji o konfiguracji dla rozwiązania pakietu Office
  Za pomocą plików konfiguracji można skonfigurować ustawienia specyficzne dla rozwiązań pakietu Office. Można określić ustawienia, takie jak zasady powiązań zestawu, obiekty zdalne, debugowanie i ustawienia śledzenia.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

### <a name="to-add-a-configuration-file-to-your-office-project"></a>Aby dodać plik konfiguracji do projektu pakietu Office

1. W menu **projekt** kliknij polecenie **Dodaj nowy element**.

2. W okienku **Kategorie** kliknij pozycję **Ogólne**.

3. W okienku **Szablony** wybierz pozycję **plik konfiguracji aplikacji**.

4. W polu **Nazwa** wpisz taką samą nazwę, jak zestaw i rozszerzenie *. config*. Na przykład plik konfiguracyjny zestawu projektu programu Excel o nazwie *ExcelWorkbook1.dll* zostałby nazwany *ExcelWorkbook1.dll.config*.

5. Kliknij pozycję **Dodaj**.

6. Utwórz plik konfiguracji zgodnie ze schematem pliku konfiguracji aplikacji. Aby uzyskać więcej informacji, zobacz [Schemat pliku konfiguracji dla .NET Framework](/dotnet/framework/configure-apps/file-schema/index).

   Nie ma specjalnych zagadnień dotyczących używania plików konfiguracji z projektami pakietu Office.

## <a name="see-also"></a>Zobacz też
- [Schemat pliku konfiguracji dla .NET Framework](/dotnet/framework/configure-apps/file-schema/index)
- [Projektowanie i tworzenie rozwiązań pakietu Office](../vsto/designing-and-creating-office-solutions.md)
- [Wdróż rozwiązanie pakietu Office](../vsto/deploying-an-office-solution.md)
