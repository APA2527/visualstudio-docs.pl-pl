---
title: Nowy plik — Polecenie
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.newfile
helpviewer_keywords:
- File.NewFile command
- New File command
ms.assetid: 767868d6-a525-425b-a43b-2198f636ab6b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b4d68f53343b2523347f89977fe2bd602d64742
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/20/2018
ms.locfileid: "39179960"
---
# <a name="new-file-command"></a>Nowy plik — Polecenie
Tworzy nowy plik i otwiera go. Plik pojawi się w folderze różne pliki.

## <a name="syntax"></a>Składnia

```cmd
File.NewFile [filename] [/t:templatename] [/editor:editorname]
```

## <a name="arguments"></a>Argumenty
 `filename`

 Opcjonalna. Nazwa pliku. Jeśli nazwa nie zostanie podany, zostanie podana nazwa domyślna. Jeśli nazwa szablonu nie ma na liście, zostanie utworzony plik tekstowy.

## <a name="switches"></a>Przełączniki
 t:`templatename`

 Opcjonalna. Określa typ pliku ma zostać utworzony.

 T:`templatename` argument składni odzwierciedla informacji znajdujących się w oknie dialogowym Nowy plik. Wprowadź nazwę kategorii, a następnie znakiem ukośnika odwrotnego (`\`) i szablonu, nazwy i ująć cały ciąg w cudzysłowie.

 Na przykład, aby utworzyć nową [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] pliku źródłowego, należy wprowadzić następujące t:`templatename` argumentu.

```cmd
/t:"Visual C++\C++ File (.cpp)"
```

 W powyższym przykładzie, wskazuje, czy szablon pliku C++ znajduje się w kategorii Visual C++ w **nowy plik** okno dialogowe.

 / e:`editorname`

 Opcjonalna. Nazwa edytora, w którym będzie można otworzyć pliku. Jeśli argument jest określony, ale nazwa edytora nie został podany, **Otwórz za pomocą** pojawi się okno dialogowe.

 / E:`editorname` argument składni używa nazw edytora, w jakiej występują w Otwórz za pomocą okno dialogowe, ujęta w znaki cudzysłowu.

 Na przykład, aby otworzyć plik w edytorze kodu źródłowego, należy wprowadzić następujące / e:`editorname` argumentu.

```cmd
/e:"Source Code (text) Editor"
```

## <a name="example"></a>Przykład
 W tym przykładzie tworzy nową stronę sieci web "test1.htm" i otwiera go w edytorze kodu źródłowego.

```cmd
>File.NewFile test1 /t:"General\HTML Page" /e:"Source Code (text) Editor"
```

## <a name="see-also"></a>Zobacz też

- [Visual Studio — polecenia](../../ide/reference/visual-studio-commands.md)
- [Okno Polecenie](../../ide/reference/command-window.md)
- [Okno bezpośrednie](../../ide/reference/immediate-window.md)
- [Znajdź/Command — pole](../../ide/find-command-box.md)
- [Visual Studio — aliasy poleceń](../../ide/reference/visual-studio-command-aliases.md)