---
title: 'CA2121: Konstruktory statyczne powinny być prywatne | Dokumentacja firmy Microsoft'
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
- CA2121
- StaticConstructorsShouldBePrivate
helpviewer_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
ms.assetid: ee93c620-8fc1-4e47-866c-d389c3ca9f2e
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 9e6c35d0bd7f5b325ba56bdfc62bd7f1a72096a3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684752"
---
# <a name="ca2121-static-constructors-should-be-private"></a>CA2121: Konstruktory statyczne powinny być prywatne
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA2121: konstruktory statyczne powinny być prywatne](https://docs.microsoft.com/visualstudio/code-quality/ca2121-static-constructors-should-be-private).  
  
Element TypeName | StaticConstructorsShouldBePrivate |  
| CheckId | CA2121 |  
| Kategoria | Microsoft.Security|  
| Zmiana powodująca niezgodność | Przerwanie |  
  
## <a name="cause"></a>Przyczyna  
 Typ ma statyczny Konstruktor, który nie jest prywatny.  
  
## <a name="rule-description"></a>Opis reguły  
 Statyczny Konstruktor, znany także jako konstruktora klasy, jest używany do inicjowania typu. System wywołuje statyczny konstruktor przed utworzeniem pierwszego wystąpienia typu lub przed odwołaniem do któregokolwiek ze statycznych elementów członkowskich. Użytkownik nie ma kontroli nad kiedy wywoływany jest konstruktor statyczny. Jeśli konstruktor statyczny nie jest prywatny, może być wywołany przez kod inny niż system. W zależności od operacji, które są wykonywane w konstruktorze, może to spowodować nieoczekiwane zachowanie.  
  
 Ta zasada jest wymuszana przez kompilatory języków C# i Visual Basic .NET.  
  
## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia  
 Naruszenia zwykle są spowodowane przez jedną z następujących czynności:  
  
-   Zdefiniowany Konstruktor statyczny dla danego typu i nie wykonał on prywatnych.  
  
-   Kompilator języka programowania dodany statyczny Konstruktor do typu, a nie wykonał on prywatnych.  
  
 Aby rozwiązać pierwszy rodzaj naruszenie, upewnij konstruktora statycznego prywatnego. Aby rozwiązać drugi rodzaj, Dodaj Konstruktor statyczny prywatny do danego typu.  
  
## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia  
 Nie pomijaj te naruszenia. Jeśli projekt oprogramowania wymaga jawnym wywołaniem statyczny Konstruktor, jest prawdopodobne, że projekt zawiera poważne wady i powinna zostać przejrzana pod.



