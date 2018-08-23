---
title: Korzystanie z atrybutu DebuggerTypeProxy | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- attributes [C#], debugger
- DebuggerTypeProxyAttribute class
- DebuggerTypeProxy attribute
ms.assetid: 943f3bb1-993e-4800-a47e-0af78b063014
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa4b5d363366f61b9001a3ac7f476804c0c2de19
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631917"
---
# <a name="using-debuggertypeproxy-attribute"></a>Korzystanie z atrybutu DebuggerTypeProxy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [przy użyciu atrybutu DebuggerTypeProxy](https://docs.microsoft.com/visualstudio/debugger/using-debuggertypeproxy-attribute).  
  
Debuggertypeproxyattribute —] (assetId:///T:System.Diagnostics.DebuggerTypeProxyAttribute?qualifyHint=False & autoUpgrade = True) Określa serwer proxy lub podstawiony dla typu i zmiany sposobu typu jest wyświetlana w oknach debugera. Po wyświetleniu zmiennej, która ma serwer proxy serwera proxy oznacza oryginalnego typu w **wyświetlić**. W oknie zmiennych debugera zostaną wyświetlone tylko publiczne składowe typ serwera proxy. Prywatne elementy członkowskie nie są wyświetlane.  
  
 Ten atrybut można zastosować do:  
  
-   Struktury  
  
-   Klasy  
  
-   Zestawy  
  
 Klasa proxy typu musi mieć konstruktora, który przyjmuje argument typu, który zastąpi serwer proxy. Debuger tworzy nowe wystąpienie klasy proxy typu za każdym razem, gdy wymaganych, aby wyświetlić zmienną typu docelowego. Może to mieć wpływ na wydajność. W rezultacie nie należy przeprowadzać więcej pracy w Konstruktorze niż jest to absolutnie konieczne.  
  
 Aby zminimalizować spadku wydajności, Ewaluator wyrażeń nie analizuje atrybuty na serwerze proxy wyświetlania tego typu, chyba że typ jest rozwinięta, użytkownika, klikając pozycję + symboli w oknie debugera lub przy użyciu <xref:System.Diagnostics.DebuggerBrowsableAttribute>. W związku z tym nie należy umieszczać atrybutów na sam typ wyświetlania. Atrybuty można i powinny być używane w treści typ wyświetlania.  
  
 Dobrym rozwiązaniem dla obiektu pośredniczącego typu jako prywatne klasa zagnieżdżona w klasie, docelowe atrybuty. Dzięki temu można łatwo dostęp do wewnętrznych składowych.  
  
 Jeśli <xref:System.Diagnostics.DebuggerTypeProxyAttribute> jest używana na poziomie zestawu `Target` parametr określa typ, który zastąpi serwer proxy.  
  
 Aby uzyskać przykład sposobu użycia tego atrybutu, wraz z <xref:System.Diagnostics.DebuggerDisplayAttribute> i <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, zobacz[korzystanie z atrybutu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md).  
  
## <a name="using-generics-with-debuggertypeproxy"></a>Za pomocą typów ogólnych za pomocą DebuggerTypeProxy  
 Obsługa typów ogólnych jest ograniczona. Dla języka C# `DebuggerTypeProxy` obsługuje tylko Otwórz typy. Typem otwartym, jest określana skrótem typu unconstructed jest typ ogólny, który nie utworzono wystąpienia z argumentami dla jego parametrów typu. Zamknięte typy, nazywany również typy utworzone, nie są obsługiwane.  
  
 Składnia służąca do typu otwartego wygląda następująco:  
  
 `Namespace.TypeName<,>`  
  
 Jeśli używasz typu ogólnego jako cel w `DebuggerTypeProxy`, należy użyć następującej składni. `DebuggerTypeProxy` Mechanizm wnioskuje parametrów typu dla Ciebie.  
  
 Aby uzyskać więcej informacji o typach otwarte i zamknięte w języku C# zobacz [specyfikacji języka C#](http://msdn.microsoft.com/library/e5d5a5cc-636b-4bff-b9c8-a8edc6207c22), otwórz sekcję 20.5.2 i zamknięte typy.  
  
 Visual Basic nie ma składni typu otwartego, więc nie możesz zrobić to samo w języku Visual Basic. Zamiast tego należy użyć ciąg reprezentujący nazwę typu otwartego.  
  
 `"Namespace.TypeName'2"`  
  
## <a name="see-also"></a>Zobacz też  
 [Korzystanie z atrybutu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)   
  [Udoskonalanie debugowania za pomocą atrybutów wyświetlania debugera](http://msdn.microsoft.com/library/72bb7aa9-459b-42c4-9163-9312fab4c410)



