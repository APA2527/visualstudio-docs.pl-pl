---
title: Nowy plik — polecenie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- file.newfile
helpviewer_keywords:
- File.NewFile command
- New File command
ms.assetid: 767868d6-a525-425b-a43b-2198f636ab6b
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1043dc600d339e2a0989bb71fc7e8a09e712e102
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49264098"
---
# <a name="new-file-command"></a>Nowy plik — Polecenie
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Tworzy nowy plik i otwiera go. Plik pojawi się w folderze różne pliki.  
  
## <a name="syntax"></a>Składnia  
  
```  
File.NewFile [filename] [/t:templatename] [/editor:editorname]  
```  
  
## <a name="arguments"></a>Argumenty  
 `filename`  
 Opcjonalna. Nazwa pliku. Jeśli nazwa nie zostanie podany, zostanie podana nazwa domyślna. Jeśli nazwa szablonu nie ma na liście, zostanie utworzony plik tekstowy.  
  
## <a name="switches"></a>Przełączniki  
 t:`templatename`  
 Opcjonalna. Określa typ pliku ma zostać utworzony.  
  
 T:`templatename` argument składni odzwierciedla informacji znajdujących się w oknie dialogowym Nowy plik. Wprowadź nazwę kategorii, a następnie znakiem ukośnika odwrotnego (`\`) i szablonu, nazwy i ująć cały ciąg w cudzysłowie.  
  
 Na przykład, aby utworzyć nową [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] pliku źródłowego, należy wprowadzić następujące t:`templatename` argumentu.  
  
```  
/t:"Visual C++\C++ File (.cpp)"  
```  
  
 W powyższym przykładzie, wskazuje, czy szablon pliku C++ znajduje się w kategorii Visual C++ w **nowy plik** okno dialogowe.  
  
 / e:`editorname`  
 Opcjonalna. Nazwa edytora, w którym będzie można otworzyć pliku. Jeśli argument jest określony, ale nazwa edytora nie został podany, **Otwórz za pomocą** pojawi się okno dialogowe.  
  
 / E:`editorname` argument składni używa nazw edytora, w jakiej występują w Otwórz za pomocą okno dialogowe, ujęta w znaki cudzysłowu.  
  
 Na przykład, aby otworzyć plik w edytorze kodu źródłowego, należy wprowadzić następujące / e:`editorname` argumentu.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="example"></a>Przykład  
 W tym przykładzie tworzy nową stronę sieci Web "test1.htm" i otwiera go w edytorze kodu źródłowego.  
  
```  
>File.NewFile test1 /t:"General\HTML Page" /e:"Source Code (text) Editor"  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Visual Studio — polecenia](../../ide/reference/visual-studio-commands.md)   
 [Okno polecenia](../../ide/reference/command-window.md)   
 [Okno bezpośrednie](../../ide/reference/immediate-window.md)   
 [Znajdź/Command — pole](../../ide/find-command-box.md)   
 [Visual Studio — aliasy poleceń](../../ide/reference/visual-studio-command-aliases.md)



