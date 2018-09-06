---
title: Fragmenty kodu dla języka R
description: Fragmenty kodu dla języka R w programie Visual Studio zapewniają skrótów szybko wstawiać bloki kodu o dowolnej długości, pomaga to uniknąć konieczności ponownego wpisywania podobny kod wiele razy.
ms.date: 01/24/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 0c9db243b3903ddcbaa310bbf5ba3fd911eee7fc
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "35667733"
---
# <a name="code-snippets"></a>Fragmenty kodu

Fragmenty kodu w programie Visual Studio zapewniają skrótów szybko wstawiać bloki kodu o dowolnej długości, pomaga to uniknąć konieczności ponownego wpisywania podobny kod wiele razy. R Tools for Visual Studio (RTVS) Dodaj dziesiątek, jak przydatne fragmentów R do kolekcji programu Visual Studio.

Aby wstawić fragment, typ skrócona Nazwa fragmentu kodu (IntelliSense pod warunkiem), naciśnij klawisz **kartę** do wstawienia.

Kilka prostych przykładów:

- Typ `=` następnie kartę i RTVS rozwija się `<-` operator przypisania.
- Typ `>` następnie kartę i RTVS rozszerza ją `%>%` operator potoku.

Fragmenty kodu można znacznie więcej niż tylko znak zakończenia znaków. Fragment kodu dotyczący Odczyt pliku CSV przy użyciu `read.csv` funkcji, na przykład można zwalnia Cię z trzeba pamiętać nazwy i parametry:

![Animacja przy użyciu fragmentu kodu można wstawić wywołanie read.csv](media/code-snippet-expansion.gif)

W takim przypadku podczas wpisywania `readc`, IntelliSense wyświetla listy uzupełniania. Wybranie tego uzupełnianie listy rozwijanej, a następnie naciskając klawisz **kartę** wybiera `readc`i naciskając klawisz **kartę** ponownie rozszerza ten fragment kodu. (Z tego powodu rozszerzenia fragmentu kodu jest często traktować jako "wpisz ten fragment kodu i naciśnij klawisz TAB dwa razy"). W większości przypadków pierwszej karcie kończy Wybór technologii IntelliSense, i drugiej karcie wyzwala rozszerzenie.

Aby wyświetlić wszystkie dostępne fragmenty kodu, otwórz **narzędzia** > **Menedżera wstawek kodu** okno dialogowe (**Ctrl**+**K**,**B**) i wybierz **R** dla **języka**. Rozwiń grupy i wybrać poszczególnych fragmentów kodu, aby wyświetlić opis i tekst skrótu:

![Okno dialogowe fragmentów kodu dla języka R](media/code-snippet-dialog.png)

Do tworzenia niestandardowych fragmentach kodu, postępując zgodnie z instrukcjami [wskazówki: Tworzenie fragmentu kodu](../ide/walkthrough-creating-a-code-snippet.md). Ostatecznie fragment kodu jest po prostu plikiem XML. Na przykład, poniższy kod jest fragment kodu dla tej operacji potoku (skrót `>`):

```xml
<?xml version="1.0" encoding="utf-8" ?>
<CodeSnippets  xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
  <CodeSnippet Format="1.0.0">
    <Header>
      <Title>Dplyr pipe</Title>
      <Shortcut>&gt;</Shortcut>
      <Description>Code snippet for '%&gt;%' operator</Description>
      <Author>Microsoft Corporation</Author>
      <SnippetTypes>
        <SnippetType>Expansion</SnippetType>
       </SnippetTypes>
    </Header>
    <Snippet>
      <Code Language="R">
        <![CDATA[ %>% $end$]]>
      </Code>
    </Snippet>
  </CodeSnippet>
</CodeSnippets>
```

Pliki XML wszystkie fragmenty kodu są instalowane z RTVS; **lokalizacji** pole **Menedżera wstawek kodu** zawiera ścieżkę. Można również znaleźć w kodzie źródłowym RTVS w usłudze GitHub w ramach [src/pakietu/Impl/fragmentów](https://github.com/Microsoft/RTVS/tree/master/src/Package/Impl/Snippets).
