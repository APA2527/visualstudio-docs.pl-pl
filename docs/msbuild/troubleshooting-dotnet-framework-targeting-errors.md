---
title: Rozwiązywanie problemów dotyczących błędów .NET Framework Microsoft Docs
description: Informacje o błędach programu MSBuild, które mogą wystąpić z powodu problemów z odwołaniami i sposobu ich rozwiązywania.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.FrameworkTargetingErrors
- MSBuild.ResolveAssemblyReference.FailedToResolveReferenceBecausePrimaryAssemblyInExclusionList
helpviewer_keywords:
- targeting .NET Framework version [Visual Studio]
- versions [Visual Studio], .NET Framework Client Profile
- multi-targeting
- multitargeting
- .NET Framework Client Profile
ms.assetid: 830e3e45-9a93-4279-a249-75b84599aefb
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- dotnet
ms.openlocfilehash: 7b4e6f14eb5ba771ff83b0aa5fedc8ae261ca69d
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99902636"
---
# <a name="troubleshoot-net-framework-targeting-errors"></a>Rozwiązywanie problemów z błędami obiektów docelowych programu .NET Framework

W tym temacie opisano błędy programu MSBuild, które mogą wystąpić z powodu problemów z odwołaniami i sposobu ich rozwiązywania.

## <a name="you-have-referenced-a-project-or-assembly-that-targets-a-different-version-of-the-net-framework"></a>Odwołuje się do projektu lub zestawu, który jest przeznaczony dla innej wersji .NET Framework

 Można tworzyć aplikacje odwołujące się do projektów lub zestawów przeznaczonych dla różnych wersji .NET Framework. Na przykład można utworzyć aplikację, która jest przeznaczona dla profilu klienta dla .NET Framework 4, ale odwołuje się do zestawu, który jest przeznaczony dla .NET Framework 2,0. Jeśli jednak tworzysz projekt, który jest przeznaczony dla starszej wersji .NET Framework, nie możesz ustawić odwołania w tym projekcie do projektu lub zestawu, który jest przeznaczony dla profilu klienta dla .NET Framework 4 lub .NET Framework 4. Aby rozwiązać ten problem, upewnij się, że aplikacja jest ukierunkowana na profil lub profile, które są zgodne z profilem, który jest przeznaczony dla projektów lub zestawów, do których odwołuje się aplikacja.

## <a name="you-have-re-targeted-a-project-to-a-different-version-of-the-net-framework"></a>Projekt zostanie zmieniony na inną wersję .NET Framework

 Jeśli zmienisz wersję docelową .NET Framework aplikacji, program Visual Studio zmieni niektóre odwołania, ale może być konieczne ręczne zaktualizowanie odwołań. Na przykład jeden z wymienionych wyżej błędów może wystąpić, jeśli zmienisz aplikację na docelową .NET Framework 3,5 z dodatkiem Service Pack 1, a ta aplikacja ma zasoby lub ustawienia zależne od profilu klienta dla .NET Framework 4.

 Aby obejść ustawienia aplikacji, Otwórz **Eksplorator rozwiązań**, wybierz opcję **Pokaż wszystkie pliki**, a następnie edytuj plik *app.config* w edytorze XML programu Visual Studio. Zmień wersję w ustawieniach, aby dopasować ją do odpowiedniej wersji .NET Framework. Na przykład można zmienić ustawienie wersji z 4.0.0.0 na 2.0.0.0. Podobnie w przypadku aplikacji, która dodała zasoby, Otwórz **Eksplorator rozwiązań**, wybierz przycisk **Pokaż wszystkie pliki** , rozwiń **mój projekt** (Visual Basic) lub **Właściwości** (C#), a następnie edytuj plik *resources. resx* w edytorze XML programu Visual Studio. Zmień ustawienie wersji z 4.0.0.0 na 2.0.0.0.

 Jeśli aplikacja zawiera zasoby, takie jak ikony lub mapy bitowe lub ustawienia, takie jak parametry połączenia danych, można również rozwiązać ten problem, usuwając wszystkie elementy na stronie **Ustawienia** **projektanta projektu** , a następnie ponownie dodając wymagane ustawienia.

## <a name="you-have-re-targeted-a-project-to-a-different-version-of-the-net-framework-and-references-do-not-resolve"></a>Projekt zostanie zmieniony na inną wersję .NET Framework i odwołania nie są rozpoznawane

 Jeśli przekierujesz projekt do innej wersji .NET Framework, odwołania w niektórych przypadkach mogą nie zostać poprawnie rozwiązane. Jawne w pełni kwalifikowane odwołania do zestawów często powodują ten problem, ale można je rozwiązać, usuwając odwołania, które nie są rozpoznawane, a następnie dodając je z powrotem do projektu. Alternatywnie można edytować plik projektu, aby zastąpić odwołania. Najpierw należy usunąć odwołania do następującej postaci:

```xml
<Reference Include="System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089, processorArchitecture=MSIL" />
```

 Następnie zastąp je prostą formą:

```xml
<Reference Include="System.ServiceModel" />
```

> [!NOTE]
> Po zamknięciu i ponownym otwarciu projektu należy również ponownie skompilować go, aby upewnić się, że wszystkie odwołania zostały poprawnie rozwiązane.

## <a name="see-also"></a>Zobacz też

- [Instrukcje: docelowa wersja .NET Framework](../ide/visual-studio-multi-targeting-overview.md)
- [.NET Framework profilu klienta](/dotnet/framework/deployment/client-profile)
- [Omówienie określania celu platformy](../ide/visual-studio-multi-targeting-overview.md)
- [Wielowersyjność kodu](../msbuild/msbuild-multitargeting-overview.md)
