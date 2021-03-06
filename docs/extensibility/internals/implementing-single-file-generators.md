---
title: Implementowanie generatorów Single-File | Microsoft Docs
description: Dowiedz się, jak używać niestandardowego narzędzia, które implementuje interfejs IVsSingleFileGenerator, aby rozszerzając systemy projektów Visual Basic i Visual C# w programie Visual Studio.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- custom tools, implementing
- projects [Visual Studio SDK], extensibility
- projects [Visual Studio SDK], managed custom tools
ms.assetid: fe9ef6b6-4690-4c2c-872c-301c980d17fe
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: e353101c7932e06042b451360b7ca040adcb303f
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99839953"
---
# <a name="implementing-single-file-generators"></a>Implementowanie generatorów jednoplikowych
Niestandardowe narzędzie — czasami nazywane generatorem pojedynczego pliku — może służyć do rozbudowania [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] systemów i projektów w programie [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] . Narzędzie niestandardowe jest składnikiem COM, który implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> interfejs. Korzystając z tego interfejsu, narzędzie niestandardowe przekształca pojedynczy plik wejściowy w jeden plik wyjściowy. Wynikiem przekształcenia może być kod źródłowy lub inne dane wyjściowe, które są użyteczne. Dwa przykłady niestandardowych plików kodu generowanego przez narzędzie to kod generowany w odpowiedzi na zmiany w projektancie wizualnym i pliki generowane przy użyciu Web Services Description Language (WSDL).

 Po załadowaniu niestandardowego narzędzia lub zapisaniu pliku wejściowego system projektu wywołuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> metodę i przekazuje odwołanie do <xref:Microsoft.VisualStudio.Shell.Interop.IVsGeneratorProgress> interfejsu wywołania zwrotnego, zgodnie z którym narzędzie może zgłosić postęp użytkownikowi.

 Plik wyjściowy, który generuje narzędzie niestandardowe, jest dodawany do projektu z zależnością od pliku wejściowego. System projektu automatycznie określa nazwę pliku wyjściowego na podstawie ciągu zwracanego przez implementację niestandardowego narzędzia <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A> .

 Narzędzie niestandardowe musi implementować <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> interfejs. Opcjonalnie narzędzia niestandardowe obsługują <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite> interfejs do pobierania informacji ze źródeł innych niż plik wejściowy. W każdym przypadku, zanim będzie można użyć narzędzia niestandardowego, należy zarejestrować je w systemie lub w [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] rejestrze lokalnym. Aby uzyskać więcej informacji na temat rejestrowania narzędzi niestandardowych, zobacz [Rejestrowanie generatorów pojedynczych plików](../../extensibility/internals/registering-single-file-generators.md).

## <a name="see-also"></a>Zobacz też
- [Udostępnianie typów dla projektantów wizualnych](../../extensibility/internals/exposing-types-to-visual-designers.md)
