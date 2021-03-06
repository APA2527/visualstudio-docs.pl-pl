---
title: Plik konfiguracji devinit
description: Dokumentacja .devinit.jsw pliku manifestu dla devinit.
ms.date: 11/02/2020
ms.topic: reference
author: andysterland
ms.author: andster
manager: jmartens
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.prod: visual-studio-windows
ms.technology: devinit
ms.openlocfilehash: 47859d00861c2361ed03931bf1417e22425d6e68
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99908118"
---
# <a name="devinit-configuration-file"></a>plik konfiguracji devinit

`.devinit.json`Plik definiuje zależności systemowe, których potrzebuje aplikacja, aby można było uruchomić i skompilować. Zależności w całym systemie są takie jak Node.js, SQL Server, IIS, RabbitMQ, Docker itp. Są to sortowanie elementów, które zwykle instalujesz w polu dev, które nie są instalowane przez określone repozytorium. Nie jest to miejsce do definiowania zależności specyficznych dla aplikacji, takich jak w przypadku menedżerów pakietów, takich jak NuGet lub NPM. Istnieje jednak możliwość zdefiniowania potrzeb tych menedżerów pakietów.

## <a name="file-location"></a>Lokalizacja pliku

`devinit init`Polecenie jest realizowane za pośrednictwem `.devinit.json` pliku. Domyślnie program `devinit` szuka pliku w następujących lokalizacjach:

* {Current-Directory} \\.devinit.jsna
* {Current-Directory} \\devinit.jsna
* {Current-Directory} \\ . devinit \\.devinit.jsna
* {Current-Directory} \\ . devinit \\devinit.jsna
* {Current-Directory} \\ devinit \\.devinit.jsna
* {Current-Directory} \\ devinit \\devinit.jsna
* {Current-Directory} \\ . devcontainer \\.devinit.jsna
* {Current-Directory} \\ . devcontainer \\devinit.jsna

> [!NOTE]
> Jeśli zostanie znalezionych wiele plików domyślnych, devinit użyje pliku, który jest wyświetlany w pierwszej kolejności na powyższej liście.

`.devinit.json`Plik można również jawnie określić za pomocą `--file` / `-f` opcji.

### <a name="directories-and-relative-paths"></a>Katalogi i ścieżki względne

Ścieżki są względne dla lokalizacji, w której działa devinit. Jest to zazwyczaj bieżący katalog roboczy, z którego `devinit` wykonano.

## <a name="file-format"></a>Format pliku
W programie `.devinit.json` można określić więcej niż jedno narzędzie do uruchomienia. W `run` sekcji można umieścić dowolną liczbę obiektów. Przykład jest widoczny w naszym przykładzie [.devinit.jsna](sample-all-tool.md) wszystkich naszych narzędziach.

```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-3.0",
    "comments": "string",
    "run": [
        {
            "comments": "string",
            "tool": "string",
            "input": "string|null|undefined",
            "additionalOptions": "string|null|undefined"
        }
    ]
}
```

### <a name="property-values"></a>Wartości właściwości

| Nazwa         | Typ   | Wymagane | Wartość                              |
|--------------|--------|----------|------------------------------------|
| **komentarz** | ciąg | Nie       | Komentarze do pliku.             |
| **wykonane**      | array  | Tak      | [Obiekt RunTool](#run-tool-object) |

#### <a name="run-tool-object"></a>Uruchom obiekt narzędzia

| Nazwa                  | Typ   | Wymagane | Wartość                                                                                                      |
|-----------------------|--------|----------|------------------------------------------------------------------------------------------------------------|
| **komentarz**          | ciąg | Nie       | Komentarze dotyczące wpisu narzędzia.                                                                               |
| **narzędziem**              | ciąg | Tak      | Nazwa narzędzia. Zobacz `devinit list` polecenie, aby uzyskać listę dostępnych narzędzi.                            |
| **klawiatur**             | ciąg | Nie       | Dane wejściowe narzędzia. Różni się według narzędzia. Na przykład wymagana wersja, identyfikator pakietu, nazwa pliku lub folder.|
| **additionalOptions** | ciąg | Nie       | Dodatkowe argumenty wiersza polecenia, które mają zostać przekazane do narzędzia.                                                |

## <a name="examples"></a>Przykłady

Aby uzyskać więcej przykładów użycia devinit, zobacz [sekcję Samples (przykłady](sample-readme.md)).
