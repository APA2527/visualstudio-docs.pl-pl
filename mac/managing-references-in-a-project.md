---
title: Zarządzanie odwołaniami w projekcie
description: W tym artykule opisano sposób zarządzania odwołaniami w projekcie w Visual Studio dla komputerów Mac
author: jmatthiesen
ms.author: jomatthi
ms.date: 11/09/2020
ms.assetid: 4AD51385-B0A8-4BA7-B2D4-BF2BD167A142
ms.topic: overview
ms.openlocfilehash: 41d49fe6b23818f3cb9de8dec72462d4b2029bb6
ms.sourcegitcommit: 2cf3a03044592367191b836b9d19028768141470
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94493520"
---
# <a name="managing-references-in-a-project"></a>Zarządzanie odwołaniami w projekcie

Visual Studio dla komputerów Mac zapewnia dwa sposoby dodawania dodatkowych odwołań do projektu:

![Informacje o projekcie](media/projects-and-solutions-image10.png)

Są to:

* Odwołania
* Pakiety NuGet (dodane za pośrednictwem folderu Packages)

Ponadto odwołania sieci Web i natywne odwołania można także dodać do każdego projektu.

## <a name="assembly-references"></a>Odwołania do zestawów

Każda struktura w programie Xamarin jest dostarczana z użyciem dziesiątych zestawów. Nie wszystkie te pakiety zestawów są domyślnie przywoływane w projekcie.

Aby edytować pakiety, do których odwołuje się projekt, użyj okna dialogowego **Edytowanie odwołań** , które może być wyświetlane przez dwukrotne kliknięcie folderu References lub wybranie opcji **Edytuj odwołania** w jego akcjach menu kontekstowego:

![Odwołanie do zestawu — okno dialogowe](media/projects-and-solutions-image11.png)

Aby uzyskać informacje na temat zestawów dostępnych dla poszczególnych platform Xamarin, zapoznaj się z przewodnikiem dotyczącym [dostępnych zestawów](https://developer.xamarin.com/guides/cross-platform/advanced/available-assemblies/) .

## <a name="nuget"></a>NuGet

Pakiet NuGet jest najpopularniejszym menedżerem pakietów na potrzeby programowania na platformie .NET. Obsługa NuGet Visual Studio dla komputerów Mac umożliwia wyszukiwanie pakietów, które mają zostać dodane do projektu.

W tym celu kliknij prawym przyciskiem myszy folder **Package** w oknie rozwiązanie, a następnie wybierz pozycję Dodaj pakiety.

Więcej informacji na temat korzystania z pakietu NuGet znajduje się w temacie [zawierającym pakiet NuGet w](nuget-walkthrough.md) przewodniku po projekcie.

## <a name="see-also"></a>Zobacz też

- [Zarządzanie odwołaniami (Visual Studio w systemie Windows)](/visualstudio/ide/managing-references-in-a-project)
- [Dodawanie odwołań przy użyciu narzędzia NuGet w porównaniu z zestawem SDK (Visual Studio w systemie Windows)](/visualstudio/ide/adding-references-using-nuget-versus-an-extension-sdk)