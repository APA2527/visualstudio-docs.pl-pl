---
title: Neutralny język zasobów do lokalizacji
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- localization [Visual Studio], resources
- NeutralResourcesLanguageAttribute class
- globalization [Visual Studio], resources
- resources [Visual Studio], fallback system
- culture, locating resources
- neutral resources
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 192b78df4f0d1f579fb9a08c913c84e5a1e2fc71
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31943296"
---
# <a name="neutral-resources-languages-for-localization"></a>Neutralny język zasobów do lokalizacji

<xref:System.Resources.NeutralResourcesLanguageAttribute> Klasy określa kulturę zasobów zawarte w zestawie głównym. Ten atrybut służy jako zwiększenie wydajności, dzięki czemu <xref:System.Resources.ResourceManager> obiektu nie wyszukuje zasoby, które znajdują się w zestawie głównym.

 Poniższy kod przedstawia sposób ustawić język neutralne zasoby. Kod można umieścić w skrypcie kompilacji lub plik AssemblyInfo.vb lub AssemblyInfo.cs.

```vb
' Set neutral resources language for assembly.
<Assembly: NeutralResourcesLanguageAttribute("en")>

```

```csharp
// Set neutral resources language for assembly.
[assembly: NeutralResourcesLanguageAttribute("en")]
```

## <a name="see-also"></a>Zobacz także

- <xref:System.Resources.ResourceManager>
- [Wprowadzenie do aplikacji międzynarodowych opartych na programie .NET Framework](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)
- [Hierarchiczna organizacja zasobów do lokalizacji](../ide/hierarchical-organization-of-resources-for-localization.md)
- [Lokalizowanie aplikacji](../ide/localizing-applications.md)
- [Globalizowanie i lokalizowanie aplikacji](../ide/globalizing-and-localizing-applications.md)