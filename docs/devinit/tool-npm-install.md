---
title: npm-install
description: devinit narzędzie npm — Zainstaluj.
ms.date: 11/20/2020
ms.topic: reference
author: andysterland
ms.author: andster
manager: jmartens
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.prod: visual-studio-windows
ms.technology: devinit
ms.openlocfilehash: 4ed32fba72a50adf8c657cc34de9cd61d01e7abc
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99874527"
---
# <a name="npm-install"></a>npm-install

`npm-install`Narzędzie to może służyć do instalowania pakietów [npm](https://www.npmjs.com/) .

## <a name="usage"></a>Użycie

Jeśli obie `input` właściwości i `additionalOptions` zostaną pominięte lub puste, narzędzie nie będzie niczego robić.

| Nazwa                                             | Typ   | Wymagane | Wartość                                                                                                          |
|--------------------------------------------------|--------|----------|----------------------------------------------------------------------------------------------------------------|
| **komentarz**                                     | ciąg | Nie       | Opcjonalna Właściwość komentarzy. Nie używany.                                                                          |
| [**klawiatur**](#input)                              | ciąg | Nie       | Pakiet do zainstalowania. Aby uzyskać szczegółowe informacje, zobacz poniższe [dane wejściowe](#input) .                                                 |
| [**additionalOptions**](#additional-options)     | ciąg | Nie       | Dodatkowe opcje do przekazania do narzędzia. Aby uzyskać szczegółowe informacje, zobacz [dodatkowe opcje](#additional-options) poniżej.       |

### <a name="input"></a>Dane wejściowe

`input`Właściwość służy do określenia nazwy pakietu do zainstalowania (na przykład "Mongo").

### <a name="additional-options"></a>Opcje dodatkowe

Dodatkowe opcje konfiguracji mogą być przesyłane jako wartość `additionalOptions` . Te argumenty są bezpośrednim przekazywaniem do argumentów używanych przez [instalację npm](https://docs.npmjs.com/cli/install).

### <a name="default-behavior"></a>Zachowanie domyślne

Domyślne zachowanie `npm-install` narzędzia jest uruchamiane `npm install` bez argumentów. Opis tego zachowania można znaleźć [w dokumentacji npm](https://docs.npmjs.com/cli/v6/commands/npm-install) .

## <a name="example-usage"></a>Przykład użycia
Poniżej znajduje się przykład sposobu uruchamiania `npm-install` przy użyciu `.devinit.json` .

#### <a name="devinitjson-that-will-install-mongo"></a>.devinit.js, na którym zostanie zainstalowany program Mongo:
```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-3.0",
    "run": [
        {
            "tool": "npm-install",
            "input": "mongo",
        }
    ]
}
```
