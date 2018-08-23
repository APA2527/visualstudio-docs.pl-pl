---
title: Fragmenty kodu | Dokumentacja firmy Microsoft
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
- vs.ExpansionManagerImport
- vs.codesnippetmanager
helpviewer_keywords:
- code snippets, replacement parameters
- code snippets, surround with
- replacement parameters
- code snippets, expansion
- surround with
- code snippets
ms.assetid: 85976ad9-4c9a-4e7b-896e-66ec6f955199
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 29087da38fe7c89936e3823b43e591116396e432
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633598"
---
# <a name="code-snippets"></a>Wstawki kodu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [fragmenty kodu](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
Fragmenty kodu pochodzą małych blokach kodu wielokrotnego użytku, które mogą być wstawiane w pliku kodu za pomocą polecenia menu kontekstowego lub kombinacji klawiszy dostępu. Zawierają one zazwyczaj bloki kodu często używane, takich jak try-finally, lub if-else bloków, ale może służyć do wstawienia całej klasy lub metody.  
  
## <a name="expansion-snippets-and-surround-with-snippets"></a>Fragmenty rozszerzeń i fragmentów Otocz przez  
 W programie Visual Studio, istnieją dwa rodzaje fragmentu kodu: fragmenty kodu rozszerzenia, które są dodawane w punkcie wstawiania określonego i mogą zastąpić skrótów fragmentu kodu, i z funkcji Otocz przez fragmentów kodu (C# i C++ tylko), które są dodawane wokół zaznaczonego bloku kodu.  
  
 Przykład wstawiania fragmentu kodu: w języku C# tryf skrótu służy do wstawiania blok try-finally:  
  
```  
try  
{  
  
}  
finally  
{  
  
}  
  
```  
  
 Ten fragment kodu można wstawić, klikając **Wstaw fragment kodu** w menu kontekstowe okna kodu, następnie **Visual C#**, a następnie wpisz `tryf`, karty lub użytkownik może wpisać `tryf` i naciśnij klawisz TAB + TAB.  
  
 Przykład fragmentu kodu z funkcji Otocz przez: w języku C++ skrót `if` może służyć jako fragment wstawiania lub z funkcji Otocz przez fragment kodu. Jeśli wybierzesz wiersz kodu (na przykład `return FALSE;`), a następnie kliknij przycisk **Otocz**, następnie **Jeśli**, fragment kodu jest rozwinięty wokół linii:  
  
```  
if (true)  
{  
    return FALSE;  
}  
  
```  
  
## <a name="snippet-replacement-parameters"></a>Parametry zamiany fragmentu kodu  
 Fragmenty mogą zawierać zastąpienia parametrów, które są symbolami zastępczymi, które należy zastąpić do pisania kodu dokładne dopasowania. W poprzednim przykładzie `true` parametr zastąpienia, należy zastąpić za pomocą odpowiedniego warunku. Wprowadzone zastąpienia jest powtarzany dla każdego wystąpienia parametru zastępowania we fragmencie kodu.  
  
 Na przykład w języku Visual Basic istnieje fragment kodu, który wstawia właściwości. Kliknij przycisk **Wstaw fragment kodu** w menu kontekstowym okna kodu, następnie **wzorców kodu**, następnie **właściwości, procedury, zdarzenia**, następnie zdefiniuj właściwość. Poniższy kod dodaje się:  
  
```  
Private newPropertyValue As String  
Public Property NewProperty() As String  
    Get  
        Return newPropertyValue  
    End Get  
    Set(ByVal value As String)  
        newPropertyValue = value  
    End Set  
End Property  
  
```  
  
 Jeśli zmienisz `newPropertyValue` do `m_property`, następnie każde wystąpienie `newPropertyValue` zostanie zmieniony. Jeśli zmienisz `String` do `Int` w deklaracji właściwości, następnie wartość w metodzie zestaw jest również zmienić `Int`.  
  
## <a name="code-snippet-manager"></a>Menedżera fragmentów kodu  
 Można wyświetlić wszystkie fragmenty kodu, które są aktualnie zainstalowane, a także ich lokalizacji na dysku, klikając **narzędzia/Manager wstawek kodu**. Fragmenty kodu są wyświetlane w języku.  
  
 Można dodawać i usuwać katalogów fragmentu kodu przy użyciu **Dodaj** i **Usuń** przycisków w **Menedżera wstawek kodu** okna dialogowego. Aby dodać poszczególne fragmenty kodu, należy użyć **importu** przycisku.  
  
## <a name="see-also"></a>Zobacz też  
 [Wskazówki: Tworzenie wstawek kodu](../ide/walkthrough-creating-a-code-snippet.md)   
 [Porady: rozprowadzanie wstawek kodu](../ide/how-to-distribute-code-snippets.md)   
 [Najlepsze rozwiązania dotyczące korzystania z fragmentów kodu](../ide/best-practices-for-using-code-snippets.md)   
 [Rozwiązywanie problemów z fragmentów kodu](../ide/troubleshooting-snippets.md)   
 [Fragmenty kodu Visual C#](../ide/visual-csharp-code-snippets.md)   
 [Fragmenty kodu Visual C++](../ide/visual-cpp-code-snippets.md)   
 [Fragmenty kodu — informacje o schemacie](../ide/code-snippets-schema-reference.md)



