---
title: EditorConfig a analizatory
ms.date: 03/11/2019
description: Dowiedz się więcej na temat analizy kodu na podstawie .NET Compiler Platform w programie Visual Studio. Zobacz odpowiedzi na pytania dotyczące plików EditorConfig, zestawów reguł i innych tematów.
ms.custom: SEO-VS-2020
ms.topic: conceptual
helpviewer_keywords:
- analyzers, faq
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 6d67471027f36d0e22c055f4306ce2137d972463
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99843751"
---
# <a name="code-analysis-faq"></a>Analiza kodu — często zadawane pytania

Ta strona zawiera odpowiedzi na kilka często zadawanych pytań dotyczących analizy kodu na podstawie .NET Compiler Platform w programie Visual Studio.

## <a name="code-analysis-versus-editorconfig"></a>Analiza kodu w porównaniu z EditorConfig

**P**: czy należy użyć analizy kodu lub EditorConfig do sprawdzania stylu kodu?

Odp **.: Analiza** kodu i pliki EditorConfig są dostępne w ręku. Podczas definiowania stylów kodu [w pliku EditorConfig](/dotnet/fundamentals/code-analysis/code-style-rule-options) lub na stronie [Opcje edytora tekstu](../ide/code-styles-and-code-cleanup.md) , można faktycznie skonfigurować analizatory kodu, które są wbudowane w program Visual Studio. Pliki EditorConfig mogą służyć do włączania lub wyłączania reguł analizatora, a także do konfigurowania pakietów analizatora NuGet.

## <a name="editorconfig-versus-rule-sets"></a>EditorConfig a zestawy reguł

**P**: czy należy skonfigurować moje analizatory przy użyciu zestawu reguł lub pliku EditorConfig?

Odp **.: zestawy** reguł i pliki EditorConfig mogą współistnieć i mogą być używane do konfigurowania analizatorów. Zarówno pliki EditorConfig, jak i zestawy reguł umożliwiają włączanie i wyłączanie reguł oraz ustawianie ich ważności.

Jednak pliki EditorConfig oferują dodatkowe sposoby konfigurowania reguł:

- W przypadku analizatorów jakości kodu platformy .NET pliki EditorConfig umożliwiają [Definiowanie typów kodu do analizy](/dotnet/fundamentals/code-analysis/code-quality-rule-options).
- W przypadku analizatorów stylu kodu platformy .NET wbudowanych w program Visual Studio pliki EditorConfig umożliwiają [Definiowanie preferowanych stylów kodu](/dotnet/fundamentals/code-analysis/code-style-rule-options) dla bazy kodu.

Oprócz zestawów reguł i plików EditorConfig Niektóre analizatory są konfigurowane przy użyciu plików tekstowych oznaczonych jako [dodatkowe pliki](../ide/build-actions.md#build-action-values) dla kompilatorów C# i VB.

> [!NOTE]
> - Plików EditorConfig można używać tylko do włączania reguł i ustawiania ich ważności w programie Visual Studio 2019 w wersji 16,3 lub nowszej.
> - Nie można używać plików EditorConfig do konfigurowania starszej analizy, natomiast zestawy reguł mogą.

## <a name="code-analysis-in-ci-builds"></a>Analiza kodu w kompilacjach CI

**P**: czy analiza kodu oparta na .NET compiler platform jest zgodna z kompilacjami ciągłej integracji (ci)?

Odp **.: tak**. W przypadku analizatorów instalowanych z pakietu NuGet te reguły są [wymuszane w czasie kompilacji](roslyn-analyzers-overview.md#build-errors), w tym w trakcie kompilacji elementu konfiguracji. Analizatory używane w kompilacjach CI respektują konfigurację reguły z obu zestawów reguł i plików EditorConfig. Obecnie analizatory kodu, które są wbudowane w program Visual Studio, nie są dostępne jako pakiet NuGet, dlatego te reguły nie są wymuszane w kompilacji CI.

## <a name="ide-analyzers-versus-stylecop"></a>Analizatory IDE a StyleCop

**P**: Jaka jest różnica między analizatorami kodu IDE programu Visual Studio i analizatorami StyleCop?

Odp **.: środowisko IDE programu Visual** Studio zawiera wbudowane analizatory, które szukają zarówno stylu kodu, jak i problemów z jakością. Te reguły ułatwiają korzystanie z nowych funkcji języka w miarę ich wprowadzania i zwiększają łatwość utrzymania kodu. Analizatory IDE są stale aktualizowane wraz z każdą wersją programu Visual Studio.

[Analizatory StyleCop](https://github.com/DotNetAnalyzers/StyleCopAnalyzers) to analizatory innych firm, które są instalowane jako pakiet NuGet, który sprawdza spójność stylu w kodzie. Ogólnie rzecz biorąc, reguły StyleCop umożliwiają ustawianie osobistych preferencji dla bazy kodu bez zalecania stosowania stylu na innym.

## <a name="code-analyzers-versus-legacy-analysis"></a>Analizatory kodu i analiza starszej wersji

**P**: Jaka jest różnica między starszą analizą a analizą kodu opartą na .NET compiler platform?

Odp **.: Analiza kodu oparta na .NET compiler platform** analizuje kod źródłowy w czasie rzeczywistym i podczas kompilacji, natomiast Starsza analiza analizuje pliki binarne po zakończeniu kompilacji. Aby uzyskać więcej informacji, zobacz [Analiza oparta na .NET compiler platformach i analiza starszej wersji](../code-quality/net-analyzers-faq.md#whats-the-difference-between-legacy-fxcop-and-net-analyzers).

## <a name="fxcop-analyzers-versus-net-analyzers"></a>Analizatory FxCopów a analizatory .NET

**P**: Jaka jest różnica między analizatorami FxCop i analizatorami .NET?

Odp **.: zarówno** analizatory FxCopy, jak i analizatorze .NET odnoszą się .NET compiler platform do implementacji usługi FxCop dla usługi Roslyn. W systemach starszych niż Visual Studio 2019 16,8 i .NET 5,0 te analizatory są dostarczane jako `Microsoft.CodeAnalysis.FxCopAnalyzers` [pakiet NuGet](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers). Począwszy od programu Visual Studio 2019 16,8 i .NET 5,0, te analizatory są [dołączone do zestawu .NET SDK](/dotnet/fundamentals/code-analysis/overview). Są one również dostępne jako `Microsoft.CodeAnalysis.NetAnalyzers` [pakiet NuGet](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers). Rozważ [przeprowadzenie migracji z analizatorów FxCop do analizatorów platformy .NET](migrate-from-fxcop-analyzers-to-net-analyzers.md).

## <a name="treat-warnings-as-errors"></a>Traktuj ostrzeżenia jako błędy

**P**: mój projekt używa opcji Build, aby traktować ostrzeżenia jako błędy. Po przeprowadzeniu migracji ze starszej wersji analizy do analizy kodu źródłowego wszystkie ostrzeżenia analizy kodu są teraz wyświetlane jako błędy. Jak mogę to zapobiec?

Odp **.: aby** zapobiec potraktowaniu ostrzeżeń analizy kodu jako błędów, wykonaj następujące czynności:

  1. Utwórz plik. props o następującej zawartości:

     ```xml
     <Project>
        <PropertyGroup>
           <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
        </PropertyGroup>
     </Project>
     ```

  2. Dodaj wiersz do pliku projektu. csproj lub. vbproj, aby zaimportować plik. props, który został utworzony w poprzednim kroku. Ten wiersz musi być umieszczony przed wszystkimi wierszami, które zaimportują Analizator. props Files. Na przykład, jeśli plik. props ma nazwę CodeAnalysis. props:

     ```xml
     ...
     <Import Project="..\..\codeanalysis.props" Condition="Exists('..\..\codeanalysis.props')" />
     <Import Project="..\packages\Microsoft.CodeAnalysis.NetAnalyzers.5.0.0\build\Microsoft.CodeAnalysis.NetAnalyzers.props" Condition="Exists('..\packages\Microsoft.CodeAnalysis.NetAnalyzers.5.0.0\build\Microsoft.CodeAnalysis.NetAnalyzers.props')" />
     ...
     ```

## <a name="code-analysis-solution-property-page"></a>Strona właściwości rozwiązania analizy kodu

**P**: gdzie jest stroną właściwości analizy kodu dla rozwiązania?

Odp **.: Strona** właściwości Analiza kodu na poziomie rozwiązania została usunięta na korzyść grupy wspólnych właściwości. Aby zarządzać analizą kodu na poziomie projektu, Strona właściwości Analiza kodu jest nadal dostępna. (W przypadku projektów zarządzanych zalecamy także Migrowanie z zestawów reguł do EditorConfig dla konfiguracji reguł).  W celu udostępniania zestawów reguł w wielu/wszystkich projektach w rozwiązaniu lub repozytorium zaleca się zdefiniowanie grupy właściwości z właściwością [CodeAnalysisRuleSet](../code-quality/using-rule-sets-to-group-code-analysis-rules.md#specify-a-rule-set-for-a-project) w udostępnionym pliku props/targets lub *katalogu. props/Directory. targets* . Jeśli nie masz takich wspólnych właściwości lub obiektów docelowych, które zostały zaimportowane przez wszystkie projekty, rozważ dodanie takiej grupy właściwości do [katalogu. props lub pliku Directory. targets](../msbuild/customize-your-build.md) w katalogu rozwiązania najwyższego poziomu, który jest automatycznie importowany we wszystkich plikach projektu zdefiniowanych w katalogu lub jego podkatalogach.

## <a name="see-also"></a>Zobacz też

- [Przegląd analizatorów](roslyn-analyzers-overview.md)
- [Ustawienia konwencji kodowania .NET dla EditorConfig](/dotnet/fundamentals/code-analysis/code-style-rule-options)