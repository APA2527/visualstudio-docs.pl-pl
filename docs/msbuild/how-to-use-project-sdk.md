---
title: 'Porady: odwołanie do zestawu SDK projektu MSBuild | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 01/25/2018
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, SDKs, SDK
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: abc61f0e07ed1e22d0ec3b2c8fb15d66c9eea3cd
ms.sourcegitcommit: d462dd10746624ad139f1db04edd501e7737d51e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2018
ms.locfileid: "50220452"
---
# <a name="how-to-use-msbuild-project-sdks"></a>Porady: projektu programu MSBuild z użycia zestawów SDK

[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 15.0 wprowadzono pojęcie "Projekt zestawu SDK", która upraszcza przy użyciu software development kit, które wymagają właściwości i elementy docelowe do zaimportowania.

```xml
<Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
        <TargetFramework>net46</TargetFramework>
    </PropertyGroup>
</Project>
```

Podczas obliczania wartości projektu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] dodaje niejawne imports u góry i u dołu projektu:

```xml
<Project>
    <!-- Implicit top import -->
    <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />

    <PropertyGroup>
        <TargetFramework>net46</TargetFramework>
    </PropertyGroup>

    <!-- Implicit bottom import -->
    <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

## <a name="reference-a-project-sdk"></a>Odwoływać się do projektu zestawu SDK

 Istnieją trzy sposoby, aby odwoływać się do projektu zestawu SDK:

1. Użyj `Sdk` atrybutu na `<Project/>` elementu:

    ```xml
    <Project Sdk="My.Custom.Sdk">
        ...
    </Project>
    ```

    Niejawne import jest dodawany do górnej i dolnej części projektu, zgodnie z powyższym opisem.  Format `Sdk` atrybut jest `Name[/Version]` gdzie wersja jest opcjonalne.  Na przykład można określić `My.Custom.Sdk/1.2.3`.

    > [!NOTE]
    > Ta funkcja jest obecnie jedynym sposobem obsługiwanych, aby odwoływać się do projektu zestawu SDK w programie Visual Studio dla komputerów Mac.

2. Użyj najwyższego poziomu `<Sdk/>` elementu:

    ```xml
    <Project>
        <Sdk Name="My.Custom.Sdk" Version="1.2.3" />
        ...
    </Project>
   ```

   Niejawne import jest dodawany do górnej i dolnej części projektu, zgodnie z powyższym opisem.  `Version` Atrybut nie jest wymagana.

3. Użyj `<Import/>` element w dowolnym miejscu w projekcie:

    ```xml
    <Project>
        <PropertyGroup>
            <MyProperty>Value</MyProperty>
        </PropertyGroup>
        <Import Project="Sdk.props" Sdk="My.Custom.Sdk" />
        ...
        <Import Project="Sdk.targets" Sdk="My.Custom.Sdk" />
    </Project>
   ```

   Jawnemu dołączeniu polecenie importuje w projekcie umożliwia pełną kontrolę nad kolejności.

   Korzystając z `<Import/>` elementu, można określić opcjonalny `Version` także atrybutu.  Na przykład można określić `<Import Project="Sdk.props" Sdk="My.Custom.Sdk" Version="1.2.3" />`.

## <a name="how-project-sdks-are-resolved"></a>Jak są rozwiązywane projektów zestawów SDK

Podczas obliczania importu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] dynamicznie jest rozpoznawana jako ścieżkę projektu zestawu SDK na podstawie nazwy i wersji określonego.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] zawiera również listę zarejestrowanych mechanizmów rozpoznawania zestawu SDK, będące wtyczek, które zlokalizować projektu zestawy SDK na maszynie.  Te dodatki obejmują:

1. Rozpoznawania oparte na pakietach NuGet, który odpytuje skonfigurowanego pakietu źródła pakietów NuGet, zgodne z Identyfikatorem i wersją zestawu SDK określonej.<br/>
   Ten mechanizm rozpoznawania jest aktywny tylko wtedy, jeśli określona wersja opcjonalne i może służyć do niestandardowego zestawu SDK projektu.  
2. Mechanizm rozpoznawania do wiersza polecenia platformy .NET, który jest rozpoznawany jako zestawy SDK, które są instalowane przy użyciu interfejsu wiersza polecenia platformy .NET.<br/>
   Ten mechanizm rozpoznawania lokalizuje zestawy SDK projektu, takich jak `Microsoft.NET.Sdk` i `Microsoft.NET.Sdk.Web` będące częścią produktu.
3. Mechanizm rozpoznawania do domyślnego, który jest rozpoznawany jako zestawy SDK, które zostały zainstalowane za pomocą narzędzia MSBuild.

Program rozpoznawania nazw oparty na pakietach NuGet zestawu SDK obsługuje określanie wersji w Twojej [global.json](https://docs.microsoft.com/dotnet/core/tools/global-json) pozwala kontrolować wersję zestawu SDK projektu w jednym miejscu, a nie w każdego indywidualnego projektu:

```json
{
    "msbuild-sdks": {
        "My.Custom.Sdk": "5.0.0",
        "My.Other.Sdk": "1.0.0-beta"
    }
}
```

Tylko jedną wersję każdego projektu, zestaw SDK może służyć podczas kompilacji.  Jeśli odwołujesz się dwie różne wersje tego samego zestawu SDK projektu, program MSBuild będzie emituje ostrzeżenia.  Zaleca się **nie** Określ wersję w projektach, jeśli określono wersję w swojej *global.json*.  

## <a name="see-also"></a>Zobacz także

 [Pojęcia dotyczące programu MSBuild](../msbuild/msbuild-concepts.md)   
 [Dostosowywanie kompilacji](../msbuild/customize-your-build.md)   
 [Pakiety, metadane i platform](/dotnet/core/packages)   
 [Dodatki do formatu csproj dla platformy .NET Core](/dotnet/core/tools/csproj)
