---
title: Komentowanie kodu w starszej wersji usługi językowej | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- comments, supporting in language services [managed package framework]
- language services [managed package framework], commenting code
ms.assetid: 9600d6f0-e2b6-4fe0-b935-fb32affb97a4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3a4215d3ea841f8e7c7c9f057535d9585682dcfa
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39510465"
---
# <a name="comment-code-in-a-legacy-language-service"></a>Komentarz kodu w starszej wersji usługi językowej
Języki programowania zwykle zapewniają oznacza dodawać adnotacje i komentarze kodu. Komentarz to sekcja tekst, który zawiera dodatkowe informacje o kodzie, ale jest ignorowany podczas kompilacji lub interpretacji.  
  
 Pakiet zarządzanych klas framework (MPF) zapewniają obsługę komentowania i Trwa usuwanie komentarza do zaznaczonego tekstu.  
  
## <a name="comment-styles"></a>Style komentarz  
Istnieją dwa ogólne style komentarza:  
   
1.  Komentarze wiersza, gdzie jest komentarz w jednym wierszu.  
  
2.  Komentarze bloku, gdzie komentarz może obejmować wiele wierszy.  
  

Wiersz komentarze zazwyczaj mają znak początkowy (lub znaków), podczas komentarze bloku znaków zarówno rozpoczęcia i zakończenia. Na przykład w języku C# wiersz komentarza rozpoczyna się od `//`, i zaczyna się komentarza blokowego `/*` i kończy `*/`.  
  
Gdy użytkownik wybierze polecenie **Dodaj komentarz do zaznaczenia** z **Edytuj** > **zaawansowane** menu polecenie jest kierowany do <xref:Microsoft.VisualStudio.Package.Source.CommentSpan%2A> metody <xref:Microsoft.VisualStudio.Package.Source> klasy. Gdy użytkownik wybierze polecenie **Usuń komentarz zaznaczenia**, polecenie jest kierowany do <xref:Microsoft.VisualStudio.Package.Source.UncommentSpan%2A> metody.  
  
## <a name="support-code-comments"></a>Komentarze w kodzie obsługi  
 Możesz mieć swoje komentarze kodu języka usługi pomocy technicznej przez `EnableCommenting` o nazwie parametru <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> . To ustawienie <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCommenting%2A> właściwość <xref:Microsoft.VisualStudio.Package.LanguagePreferences> klasy. Aby uzyskać więcej informacji o ustawianiu funkcje usługi w języka, zobacz [rejestrowanie starszej wersji usługi językowej](../../extensibility/internals/registering-a-legacy-language-service1.md).  
  
 Konieczne jest również przesłonięcie <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> metodę, aby zwrócić <xref:Microsoft.VisualStudio.Package.CommentInfo> strukturę znaki komentarza dla danego języka. C# — znaków komentarza wierszu stylu są domyślne.  
  
### <a name="example"></a>Przykład  
 Poniżej przedstawiono przykład implementacji <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> metody.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
  
namespace MyLanguagePackage  
{  
    class MySource : Source  
    {  
        public override CommentInfo GetCommentFormat() {  
            CommentInfo info = new CommentInfo();  
            info.LineStart       = "//";  
            info.BlockStart      = "/*";  
            info.BlockEnd        = "*/";  
            info.UseLineComments = true;  
            return info;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Funkcje usługi starszego języka](../../extensibility/internals/legacy-language-service-features1.md)   
 [Rejestrowanie starszej wersji usługi językowej](../../extensibility/internals/registering-a-legacy-language-service1.md)