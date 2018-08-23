---
title: Zastąp w plikach — polecenie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- edit.replaceinfiles
helpviewer_keywords:
- Edit.ReplaceInFiles command
- Replace In Files command
- ReplaceInFiles command
ms.assetid: f116066a-4f65-4f2c-94ef-12cbd8cfb598
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8df474b7ca65983d7bf7203e2d3e2146fbede6f3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691717"
---
# <a name="replace-in-files-command"></a>Zastąp w plikach — Polecenie
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Zastąp w plikach — polecenie](https://docs.microsoft.com/visualstudio/ide/reference/replace-in-files-command).  
  
  
Zastępuje tekst w plikach za pomocą podzestawu opcji dostępnych w **Zamień w plikach** karcie **Znajdź i Zamień** okna.  
  
## <a name="syntax"></a>Składnia  
  
```  
Edit.ReplaceinFiles findwhat replacewith [/all] [/case]  
[/ext:extensions] [/keep] [/lookin:searchpath] [/options] [/regex]  
[/reset] [/stop] [/sub] [/text2] [/wild] [/word]  
```  
  
## <a name="arguments"></a>Argumenty  
 `findwhat`  
 Wymagane. Tekst do dopasowania.  
  
 `replacewith`  
 Wymagane. Tekst do podstawienia w dopasowany tekst.  
  
## <a name="switches"></a>Przełączniki  
 / all lub /a  
 Opcjonalna. Zamienia wszystkie wystąpienia tekstu wyszukiwania tekst zastępczy.  
  
 /Case lub /c  
 Opcjonalna. Dopasowuje występują tylko wtedy, gdy po wielkich i małych liter dokładnie odpowiadać określone w `findwhat` argumentu.  
  
 /ext: `extensions`  
 Opcjonalna. Określa rozszerzenia plików dla plików do przeszukania.  
  
 /Keep lub /k  
 Opcjonalna. Określa, że wszystkie zmodyfikowane pliki są pozostawione otwarte.  
  
 /lookin: `searchpath`  
 Opcjonalna. Katalog do przeszukania. Jeśli ścieżka zawiera spacje, należy ująć w znaki cudzysłowu pełną ścieżkę.  
  
 / Options lub/t  
 Opcjonalna. Wyświetla listę bieżących ustawień opcji wyszukiwania, a nie wyszukiwania.  
  
 /regex lub/r  
 Opcjonalna. Używa wstępnie zdefiniowanych znaków specjalnych w `findwhat` argument jako notacji, które reprezentują wzorców tekstu, a nie jako znaki literału. Aby uzyskać pełną listę znaki wyrażenia regularnego, zobacz [wyrażeń regularnych](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 / Reset i/e  
 Opcjonalna. Zwraca opcje wyszukiwania do ustawień domyślnych, a nie wyszukiwania.  
  
 / stop  
 Opcjonalna. Zatrzymuje bieżącą operację wyszukiwania, jeśli jest w toku. Zastąp ignoruje wszystkie inne argumenty po `/stop` została określona. Na przykład aby zatrzymać zastąpienie bieżącego wprowadziłbyś następujące czynności:  
  
```  
>Edit.ReplaceinFiles /stop  
```  
  
 / Sub lub /s  
 Opcjonalna. Wyszukuje podfoldery znajdujące się w katalogu wskazanym na /lookin:`searchpath` argumentu.  
  
 /text2 lub /2  
 Opcjonalna. Wyświetla wyniki zastąpienia w **Znajdź wyniki 2** okna.  
  
 /Wild lub/l  
 Opcjonalna. Używa wstępnie zdefiniowanych znaków specjalnych w `findwhat` argument jako notacji do reprezentowania znaku lub sekwencji znaków.  
  
 opcji lub Wn  
 Opcjonalna. Wyszukiwanie tylko całe wyrazy.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie wyszukuje `btnCancel` i zastępuje go tekstem `btnReset` w .cls wszystkie pliki znajdujące się w folderze "Moje projekty programu visual studio" i wyświetla informacje dotyczące zastępowania w **Znajdź wyniki 2** okna.  
  
```  
>Edit.ReplaceinFiles btnCancel btnReset /lookin:"c:/my visual studio projects" /ext:.cls /text2  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Znajdowanie i zastępowanie tekstu](../../ide/finding-and-replacing-text.md)   
 [Zastąp w plikach](../../ide/replace-in-files.md)   
 [Okno polecenia](../../ide/reference/command-window.md)   
 [Znajdź/Command — pole](../../ide/find-command-box.md)   
 [Visual Studio — polecenia](../../ide/reference/visual-studio-commands.md)   
 [Visual Studio — aliasy poleceń](../../ide/reference/visual-studio-command-aliases.md)



