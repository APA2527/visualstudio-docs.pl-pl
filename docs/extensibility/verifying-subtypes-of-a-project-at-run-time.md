---
title: Weryfikowanie podtypów projektu w czasie wykonywania | Microsoft Docs
description: Dowiedz się, jak mieć pakietu VSPackage weryfikują obecność określonego niestandardowego podtypu projektu, od którego zależy.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project subtypes
- check subtypes
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 519366fabed855c7ef3cb7c62d39a4743d890f1e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99926046"
---
# <a name="verify-subtypes-of-a-project-at-run-time"></a>Weryfikuj podtypy projektu w czasie wykonywania
Pakietu VSPackage, który zależy od niestandardowego podtypu projektu, powinien zawierać logikę do wyszukania tego podtypu, aby można było bezpiecznie kończyć się niepowodzeniem, jeśli podtyp nie jest obecny. Poniższa procedura pokazuje, jak sprawdzić obecność określonego podtypu.

### <a name="to-verify-the-presence-of-a-subtype"></a>Aby zweryfikować obecność podtypu

1. Pobierz hierarchię projektu z obiektów projektu i rozwiązania jako obiekt, <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> dodając następujący kod do pakietu VSPackage.

    ```csharp
    EnvDTE.DTE dte;
    dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));

    EnvDTE.Project project;
    project = dte.Solution.Projects.Item(1);

    IVsSolution solution;
    solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));

    IVsHierarchy hierarchy;
    hierarchy = solution.GetProjectOfUniqueName(project.UniqueName);

    ```

2. Rzutowanie hierarchii do <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected> interfejsu.

    ```csharp
    IVsAggregatableProjectCorrected AP;
    AP = hierarchy as IVsAggregatableProjectCorrected;

    ```

3. Pobierz listę identyfikatorów GUID typu projektu, wywołując <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected.GetAggregateProjectTypeGuids%2A> .

    ```csharp
    string projTypeGuids = AP.GetAggregateProjectTypeGuids().ToUpper();

    ```

4. Sprawdź listę identyfikatorów GUID określonego podtypu.

    ```csharp
    // Replace the string "MyGUID" with the GUID of the subtype.
    string guidMySubtype = "MyGUID";
    if (projTypeGuids.IndexOf(guidMySubtype) > 0)
    {
        // The specified subtype is present.
    }
    ```

## <a name="see-also"></a>Zobacz też
- [Podtypy projektu](../extensibility/internals/project-subtypes.md)
- [Projekt podtypów projektu](../extensibility/internals/project-subtypes-design.md)
- [Właściwości i metody rozszerzane przez podtypy projektów](../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)
