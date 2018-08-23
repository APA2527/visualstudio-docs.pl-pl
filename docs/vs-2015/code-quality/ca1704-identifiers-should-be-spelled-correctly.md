---
title: 'CA1704: Identyfikatory powinny być zapisane poprawnie | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
helpviewer_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
ms.assetid: f2c7a44d-1690-44ca-9cd0-681b04b12b2a
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f8b46075a1ca9058f111f33b9b1354613a54e88d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689158"
---
# <a name="ca1704-identifiers-should-be-spelled-correctly"></a>CA1704: Identyfikatory powinny być napisane poprawnie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1704: identyfikatory powinny być zapisane poprawnie](https://docs.microsoft.com/visualstudio/code-quality/ca1704-identifiers-should-be-spelled-correctly).  
  
Element TypeName | IdentifiersShouldBeSpelledCorrectly |  
| CheckId | CA1704 |  
| Kategoria | Microsoft.Naming|  
| Zmiana powodująca niezgodność | Przerwanie |  
  
## <a name="cause"></a>Przyczyna  
 Nazwa identyfikatora zawiera jeden lub więcej wyrazów, które nie są rozpoznawane przez bibliotekę sprawdzania pisowni Microsoft. Ta zasada nie Sprawdź konstruktorów lub członków o nazwie specjalne, takie jak pobieranie i ustaw metod dostępu do właściwości.  
  
## <a name="rule-description"></a>Opis reguły  
 Ta reguła analizuje identyfikator na tokeny oraz sprawdzając pisownię każdego tokenu. Algorytm analizy wykonuje następujące przekształcenia:  
  
-   Wielkie litery uruchomić nowy token. Na przykład MyNameIsJoe tokenizes "Mój", "Name", "Is", "Jan".  
  
-   Wiele wielkich liter ostatni wielką literą rozpoczyna się nowy token. Na przykład GUIEditor tokenizes do "Graficznym interfejsem użytkownika", "Editor".  
  
-   Początkowe i końcowe apostrofy są usuwane. Na przykład "nadawca" tokenizes do "sender".  
  
-   Podkreślenia oznaczającego koniec token i są usuwane. Na przykład Hello_world tokenizes do "Hello", "world".  
  
-   Takie osadzone znaki zostaną usunięte. Na przykład w przypadku & mat tokenizes do "format".  
  
 Domyślnie używany jest język angielski (en) wersję modułu sprawdzania pisowni. Nie słowników językowych są obecnie dostępne.  
  
## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia  
 Aby naprawić naruszenie tej zasady, Popraw pisownię wyrazu, lub Dodaj ten wyraz do słownika niestandardowego, który nosi nazwę CustomDictionary.xml. Umieść słowniku, w katalogu instalacji narzędzia do katalogu projektu lub katalogu, który jest skojarzony z narzędzia w ramach profilu użytkownika (%USERPROFILE%\Application danych\\...). Aby dowiedzieć się, jak dodać słownika niestandardowego do projektu w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], zobacz [porady: dostosowywanie słownika analizy kodu](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
  
-   Dodaj wyrazy, które nie powinny powodować naruszenie w ścieżce słów/słownik/Recognized.  
  
-   Dodawanie wyrazów, która powinna powodować naruszenie w ścieżce słów/słownik/nierozpoznane.  
  
-   Dodaj wyrazy, które powinny zostać oznaczone jako przestarzałe w ścieżce słów/słownik/przestarzały. Zobacz temat powiązane reguły [CA1726: Używaj preferowanych terminów](../code-quality/ca1726-use-preferred-terms.md)Aby uzyskać więcej informacji.  
  
-   Dodać wyjątki do reguł stosowania wielkości liter akronim ścieżkę akronimów/słownik/CasingExceptions.  
  
 Oto przykład struktury pliku słownika niestandardowego.  
  
```  
<Dictionary>  
   <Words>  
      <Unrecognized>  
         <Word>cb</Word>  
      </Unrecognized>  
      <Recognized>  
         <Word>stylesheet</Word>  
         <Word>GotDotNet</Word>  
      </Recognized>  
      <Deprecated>  
         <Term PreferredAlternate="EnterpriseServices">ComPlus</Term>  
      </Deprecated>  
   </Words>  
   <Acronyms>  
      <CasingExceptions>  
         <Acronym>CJK</Acronym>  
         <Acronym>Pi</Acronym>  
      </CasingExceptions>  
   </Acronyms>  
</Dictionary>  
```  
  
## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia  
 Pomijaj ostrzeżeń dla tej reguły, tylko wtedy, gdy dane słowo jest celowo błędnie napisane słowa mają zastosowanie do ograniczonego zestawu biblioteki. Poprawnie właściwej słów skrócić czas nauki, które jest wymagane nowe biblioteki oprogramowania.  
  
## <a name="related-rules"></a>Powiązane reguły  
 [CA2204: Literały powinny być zapisane poprawnie](../code-quality/ca2204-literals-should-be-spelled-correctly.md)  
  
 [CA1703: Ciągi zasobu powinny być zapisane poprawnie](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)  
  
 [CA1709: Identyfikatory powinny mieć prawidłową wielkość liter](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Identyfikatory powinny różnić się nie tylko wielkością liter](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: Identyfikatory nie powinny zawierać podkreśleń](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)  
  
 [CA1726: Używaj preferowanych terminów](../code-quality/ca1726-use-preferred-terms.md)  
  
## <a name="see-also"></a>Zobacz też  
 [Instrukcje: Dostosowywanie słownika analizy kodu](../code-quality/how-to-customize-the-code-analysis-dictionary.md)



