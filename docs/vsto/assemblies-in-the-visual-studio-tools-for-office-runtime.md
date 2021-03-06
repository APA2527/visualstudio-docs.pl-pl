---
title: Zestawy w Visual Studio Tools dla środowiska uruchomieniowego pakietu Office
description: Dowiedz się, że program Visual Studio automatycznie dodaje odwołania do Visual Studio Tools dla zestawów środowiska uruchomieniowego pakietu Office.
ms.custom: SEO-VS-2020
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Studio Tools for Office runtime, assemblies
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 600408231e5085009e5edc546535ca8e5110fc6e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99882560"
---
# <a name="assemblies-in-the-visual-studio-tools-for-office-runtime"></a>Zestawy w Visual Studio Tools dla środowiska uruchomieniowego pakietu Office
  Podczas tworzenia projektu pakietu Office Program Visual Studio automatycznie dodaje odwołania do [!INCLUDE[vsto_runtime](includes/vsto-runtime-md.md)] zestawów, które są używane dla typu projektu i docelowego .NET Framework projektu. Istnieją różne zestawy w rozszerzeniach pakietu Office dla .NET Framework 3,5, [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] i [!INCLUDE[net_v45](includes/net-v45-md.md)] . Aby uzyskać więcej informacji o rozszerzeniach pakietu Office, zobacz [Visual Studio Tools dla środowiska uruchomieniowego pakietu Office](visual-studio-tools-for-office-runtime-overview.md).

## <a name="assemblies-in-the-office-extensions-for-the-net-framework-4-and-the-net_v45"></a>Zestawy w rozszerzeniach pakietu Office dla .NET Framework 4 i [!INCLUDE[net_v45](includes/net-v45-md.md)]
 Poniższa tabela zawiera listę zestawów uwzględnionych w rozszerzeniach pakietu Office dla programów [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] i [!INCLUDE[net_v45](includes/net-v45-md.md)] . Aby uzyskać dokumentację dotyczącą przestrzeni nazw i typów w tych zestawach, zobacz [Managed reference &#40;Development Office w programie Visual Studio&#41;](managed-reference-office-development-in-visual-studio.md).

|Nazwa zestawu|Opis|
|-------------------|-----------------|
|Microsoft.Office.Tools.Common.dll|Program udostępnia następujące typy:<br /><br /> -Typy do tworzenia dostosowań Wstążki i tagów inteligentnych. **Uwaga:**      Tagi inteligentne są przestarzałe w [!INCLUDE[Excel_14_short](includes/excel-14-short-md.md)] i [!INCLUDE[Word_14_short](includes/word-14-short-md.md)] .<br />-Typy do tworzenia okienek akcji w dostosowaniach na poziomie dokumentu i niestandardowych okienkach zadań w dodatkach narzędzi VSTO.|
|Microsoft.Office.Tools.Excel.dll|Udostępnia interfejsy, które reprezentują elementy hosta i kontrolki hosta dla projektów programu Excel i typy pomocnicze. Aby uzyskać więcej informacji, zobacz [Automatyzowanie programu Excel za pomocą obiektów rozszerzonych](automating-excel-by-using-extended-objects.md).|
|Microsoft.Office.Tools.Outlook.dll|Zawiera typy, których można użyć do tworzenia niestandardowych regionów formularzy w dodatkach VSTO programu Outlook.|
|Microsoft.Office.Tools.Word.dll|Udostępnia interfejsy, które reprezentują elementy hosta i kontrolki hosta dla projektów programu Word i typy pomocnicze. Aby uzyskać więcej informacji, zobacz [Automatyzowanie programu Word za pomocą obiektów rozszerzonych](automating-word-by-using-extended-objects.md).|
|Microsoft.Office.Tools.v4.0.Framework.dll|Program udostępnia następujące typy:<br /><br /> -Wyjątki, które mogą być zgłaszane przez Visual Studio Tools dla środowiska uruchomieniowego pakietu Office.<br />— Atrybuty, których można używać podczas tworzenia regionów formularzy programu Outlook.|
|Microsoft.Office.Tools.dll|Zawiera typy, które są częścią Visual Studio Tools dla infrastruktury środowiska uruchomieniowego pakietu Office i nie są przeznaczone do użycia bezpośrednio w kodzie.|
|Microsoft.VisualStudio.Tools.Applications.Runtime.dll|Program udostępnia następujące typy:<br /><br /> - <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> Atrybut i <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType> interfejs, za pomocą którego można buforować obiekty danych w dostosowywaniu na poziomie dokumentu. Aby uzyskać więcej informacji, zobacz [cache Data](caching-data.md).<br />- <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> Interfejs, który można zaimplementować w celu uruchomienia dodatkowych kroków instalacji jako ostatni krok Instalatora ClickOnce dla rozwiązania pakietu Office. Aby uzyskać więcej informacji, zobacz [wdrażanie rozwiązania pakietu Office przy użyciu technologii ClickOnce](deploying-an-office-solution-by-using-clickonce.md).<br />-Wyjątki, które mogą być zgłaszane przez Visual Studio Tools dla środowiska uruchomieniowego pakietu Office.<br />-Inne typy, które są częścią Visual Studio Tools dla infrastruktury środowiska uruchomieniowego pakietu Office i nie są przeznaczone do użycia bezpośrednio w kodzie.|
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll|Program udostępnia następujące typy:<br /><br /> - <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> Klasa, której można użyć do dołączania zestawów dostosowania do dokumentów i uzyskiwania dostępu do danych w pamięci podręcznej w dokumentach. Aby uzyskać więcej informacji, zobacz [Zarządzanie dokumentami na serwerze za pomocą klasy ServerDocument](managing-documents-on-a-server-by-using-the-serverdocument-class.md).<br />-Kilka klas, które reprezentują hierarchię danych w pamięci podręcznej w dostosowaniu na poziomie dokumentu. Aby uzyskać więcej informacji, zobacz [dostęp do danych w dokumentach na serwerze](accessing-data-in-documents-on-the-server.md).|

 Projekty przeznaczone dla [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] lub [!INCLUDE[net_v45](includes/net-v45-md.md)] odwołują się również do następujących zestawów. Te zestawy nie są częścią [!INCLUDE[vsto_runtime](includes/vsto-runtime-md.md)] pakietu redystrybucyjnego. Zamiast tego są to zestawy zależne, które muszą zostać wdrożone wraz z rozwiązaniem. Domyślnie są one kopiowane do folderu danych wyjściowych kompilacji dla projektu (Właściwość **copy Local** dla tych zestawów jest ustawiona na **wartość true**). Jeśli projekt zostanie wdrożony przy użyciu technologii ClickOnce, te zestawy zostaną uwzględnione w wygenerowanym pakiecie.

|Nazwa zestawu|Opis|
|-------------------|-----------------|
|Microsoft.Office.Tools.Common.v4.0.Utilities.dll|Udostępnia klasy bazowe dla wygenerowanej `ThisAddIn` klasy w programie VSTO Add-In projekty i wygenerowaną klasę wstążki we wszystkich projektach.|
|Microsoft.Office.Tools.Excel.v4.0.Utilities.dll|Program udostępnia następujące typy:<br /><br /> -Klasy bazowe dla wygenerowanych `ThisWorkbook` i `Sheet` klas w projektach na poziomie dokumentu dla programu Excel.<br />-Windows Forms kontrolki, których można używać w arkuszach w projektach programu Excel.|
|Microsoft.Office.Tools.Outlook.v4.0.Utilities.dll|Udostępnia klasy bazowe dla `ThisAddIn` klas i regionów formularzy wygenerowanych i w projektach programu Outlook.|
|Microsoft.Office.Tools.Word.v4.0.Utilities.dll|Program udostępnia następujące typy:<br /><br /> -Klasy bazowe dla wygenerowanej `ThisDocument` klasy w projektach na poziomie dokumentu dla programu Word.<br />-Windows Forms kontrolki, których można używać na dokumentach w projektach programu Word.|

## <a name="assemblies-in-the-office-extensions-for-the-net-framework-35"></a>Zestawy w rozszerzeniach pakietu Office dla .NET Framework 3,5
 Poniższa tabela zawiera listę zestawów uwzględnionych w rozszerzeniach pakietu Office dla .NET Framework 3,5. Aby uzyskać dokumentację dotyczącą przestrzeni nazw i klas w tych zestawach, zobacz następującą sekcję referencyjną w dokumentacji programu Visual Studio 2008: [http://go.microsoft.com/fwlink/?LinkId=160658](managed-reference-office-development-in-visual-studio.md) .

|Nazwa zestawu|Opis|
|-------------------|-----------------|
|Microsoft.Office.Tools.Common.v9.0.dll|Program udostępnia następujące typy:<br /><br /> — Klasa bazowa Microsoft. Office. Tools. AddIn dla dodatków narzędzi VSTO.<br />-Klasy do tworzenia dostosowań Wstążki i tagów inteligentnych. **Uwaga:**      Tagi inteligentne są przestarzałe w [!INCLUDE[Excel_14_short](includes/excel-14-short-md.md)] i [!INCLUDE[Word_14_short](includes/word-14-short-md.md)] .<br />-Klasy do tworzenia okienek akcji w dostosowaniach na poziomie dokumentu i niestandardowych okienkach zadań w dodatkach narzędzi VSTO.|
|Microsoft.Office.Tools.Excel.v9.0.dll|Udostępnia elementy hosta i kontrolki hosta dla rozwiązań programu Excel. Aby uzyskać więcej informacji, zobacz [Automatyzowanie programu Excel za pomocą obiektów rozszerzonych](automating-excel-by-using-extended-objects.md).|
|Microsoft.Office.Tools.Outlook.v9.0.dll|Zawiera klasy, których można użyć do tworzenia niestandardowych regionów formularzy w dodatkach VSTO programu Outlook.|
|Microsoft.Office.Tools.Word.v9.0.dll|Udostępnia elementy hosta i kontrolki hosta dla rozwiązań programu Word. Aby uzyskać więcej informacji, zobacz [Automatyzowanie programu Word za pomocą obiektów rozszerzonych](automating-word-by-using-extended-objects.md).|
|Microsoft.Office.Tools.v9.0.dll|Program udostępnia następujące typy:<br /><br /> -Klasa [RemoteBindableComponent](/previous-versions/visualstudio/visual-studio-2008/bb546360(v=vs.90)) , która zapewnia możliwości powiązań danych dla formantów hosta w dostosowaniach na poziomie dokumentu.<br />-Inne typy, które są częścią Visual Studio Tools dla infrastruktury środowiska uruchomieniowego pakietu Office i nie są przeznaczone do użycia bezpośrednio w kodzie.|
|Microsoft.VisualStudio.Tools.Applications.Runtime.v9.0.dll|Program udostępnia następujące typy:<br /><br /> - <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> Atrybut i <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType> interfejs, za pomocą którego można buforować obiekty danych w dostosowywaniu na poziomie dokumentu. Aby uzyskać więcej informacji, zobacz [cache Data](caching-data.md).<br />-Wyjątki, które mogą być zgłaszane przez Visual Studio Tools dla środowiska uruchomieniowego pakietu Office.<br />-Inne typy, które są częścią Visual Studio Tools dla infrastruktury środowiska uruchomieniowego pakietu Office i nie są przeznaczone do użycia bezpośrednio w kodzie.|
|Microsoft.VisualStudio.Tools.Applications.Runtime.v10.0.dll|Udostępnia <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> interfejs, który można zaimplementować w celu uruchomienia dodatkowych kroków instalacji jako ostatni krok Instalatora ClickOnce dla rozwiązania pakietu Office. Aby uzyskać więcej informacji, zobacz [zaawansowane wdrażanie rozwiązań pakietu Office](/previous-versions/visualstudio/visual-studio-2010/dd234217(v=vs.100)).|
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.v10.0.dll|Program udostępnia następujące typy:<br /><br /> - <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> Klasa, której można użyć do programistycznego dołączania zestawów dostosowania do dokumentów i uzyskiwania dostępu do danych w pamięci podręcznej w dokumentach. Aby uzyskać więcej informacji, zobacz [Zarządzanie dokumentami na serwerze za pomocą klasy ServerDocument](managing-documents-on-a-server-by-using-the-serverdocument-class.md).<br />-Kilka klas, które reprezentują hierarchię danych w pamięci podręcznej w dostosowaniu na poziomie dokumentu. Aby uzyskać więcej informacji, zobacz [dostęp do danych w dokumentach na serwerze](accessing-data-in-documents-on-the-server.md).|
|Microsoft.VisualStudio.Tools.Office.Runtime.v10.0.dll|Program udostępnia następujące typy:<br /><br /> — Klasy Microsoft. VisualStudio. Tools. Office. Runtime. Security. AddInSecurityEntry i Microsoft. VisualStudio. Tools. Office. Runtime. Security. UserInclusionList, których można użyć do tworzenia wpisów listy dołączania użytkowników w celu udzielenia zaufania do rozwiązań pakietu Office przeznaczonych dla .NET Framework 3,5.<br />-Inne typy, które są częścią Visual Studio Tools dla infrastruktury środowiska uruchomieniowego pakietu Office i nie są przeznaczone do użycia bezpośrednio w kodzie.|

## <a name="see-also"></a>Zobacz też
- [Visual Studio Tools dla środowiska uruchomieniowego pakietu Office — omówienie](visual-studio-tools-for-office-runtime-overview.md)
- [Visual Studio Tools dla scenariuszy instalacji środowiska uruchomieniowego pakietu Office](visual-studio-tools-for-office-runtime-installation-scenarios.md)
