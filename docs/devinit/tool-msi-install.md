---
title: msi-install
description: Narzędzie devinit dla narzędzia Msiexec.
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
ms.openlocfilehash: 9b177d63ceabd8162c5ddd77e87c68d4a820b00a
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99896239"
---
# <a name="msi-install"></a>msi-install

`msi-install`Narzędzie służy do instalowania `.msi` formatów plików pakietu przy użyciu polecenia [msiexec](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec).

## <a name="usage"></a>Użycie

Jeśli `input` parametr zostanie pominięty lub pusty, narzędzie wyświetli błąd.

| Nazwa                                         | Typ   | Wymagane | Wartość                                                                             |
|----------------------------------------------|--------|----------|-----------------------------------------------------------------------------------|
| **komentarz**                                 | ciąg | Nie       | Opcjonalna Właściwość komentarzy. Nie używany.                                             |
| [**klawiatur**](#input)                          | ciąg | Tak      | `msi`Do zainstalowania. Aby uzyskać szczegółowe informacje, zobacz poniższe [dane wejściowe](#input) .                      |
| [**additionalOptions**](#additional-options) | ciąg | Nie       | Aby uzyskać szczegółowe informacje, zobacz [dodatkowe opcje](#additional-options) poniżej.                  |

### <a name="input"></a>Dane wejściowe

Właściwość Input służy do określania ścieżki lub adresu URL do `.msi` pliku, który zostanie zainstalowany. Jeśli ścieżka do `.msi` jest niepoprawna lub adres URL nie wskazuje `.msi` bezpośrednio, oznacza to, `msi-install` że nie można otworzyć pakietu instalacyjnego.

### <a name="additional-options"></a>Opcje dodatkowe

Dodatkowe opcje konfiguracji mogą być przesyłane jako wartość additionalOptions. Te argumenty są bezpośrednim przekazywaniem do argumentów używanych przez `msiexec` i są zdefiniowane w `msiexec` [dokumentacji](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec).

### <a name="built-in-options"></a>Wbudowane opcje

Narzędzie MSI-Install ustawia liczbę `msiexec` argumentów wiersza polecenia, aby upewnić się, że plik msi może działać jako bezobsługowy. Te argumenty są wymienione poniżej i dokumentacja na nich znajduje się w `msiexec` [dokumentacji](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec).

| Nazwa          | Opis                                                                                                                                                                                   |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| /i            | Uruchamia normalną instalację                                                                                                                                                                    |
| /quiet        | Określa tryb cichy bez interakcji użytkownika                                                                                                                                        |
| /Qn           | Określa, że podczas procesu instalacji nie ma interfejsu użytkownika                                                                                                                                           |
| /Passive      | Określa tryb instalacji nienadzorowanej, w którym tylko pokazuje pasek postępu                                                                                                                    |
| /l * V          | Włącza rejestrowanie i rejestruje wszystkie informacje, łącznie z pełnymi informacjami, do `devinit.log` pliku w lokalnym folderze tymczasowym maszyny. Jeśli narzędzie się nie powiedzie, zostanie wyświetlona ścieżka pliku dziennika.      |
| /norestart    | Powoduje zatrzymanie ponownego uruchomienia komputera po zakończeniu instalacji, ale zwróci kod zakończenia 3010, jeśli jest wymagany ponowny rozruch                                                                  |

### <a name="default-behavior"></a>Zachowanie domyślne

Domyślne zachowanie `msi-install` narzędzia jest błędem, ponieważ `input` Właściwość jest wymagana.

## <a name="example-usage"></a>Przykład użycia
Poniżej znajduje się przykład sposobu uruchamiania `msi-install` przy użyciu `.devinit.json` .

#### <a name="devinitjson-that-will-install-the-7-zip-msi"></a>.devinit.js, na którym zostanie zainstalowany plik MSI 7-Zip:
```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-4.0",
    "run": [
        {
            "tool": "msi-install",
            "input": "https://www.7-zip.org/a/7z1900.msi"
        }
    ]
}
```
