---
title: 'Błąd: zależność &#39;pliku&#39; w projekcie &#39;projektu&#39; nie można skopiować do katalogu uruchomienia, ponieważ spowodowałoby to konflikt z zależnością &#39;pliku&#39; | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.tasklisterror.copy_version_conflict
ms.assetid: cd7de1eb-7d58-4e2c-9811-a7201f7817be
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: douge
ms.openlocfilehash: 0a8d6fe7440a39fc207d8d9a1b56bea06547e273
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49274303"
---
# <a name="error-the-dependency-39file39-in-project-39project39-cannot-be-copied-to-the-run-directory-because-it-would-conflict-with-dependency-39file39"></a>Błąd: zależność &#39;pliku&#39; w projekcie &#39;projektu&#39; nie można skopiować do katalogu uruchomienia, ponieważ spowodowałoby to konflikt z zależnością &#39;pliku&#39;
Istnieje konflikt między references; więcej niż jednej zależności distinct z tą samą nazwą pliku, które są kopiowane do katalogu bin aplikacji do uruchomienia. Katalog przebiegu nie może rozwiązać konflikt, ponieważ żaden z zależności podstawowego odwołania.  
  
 Ten błąd spowoduje, że kompilacja nie powiedzie się.  
  
 Dwukrotne kliknięcie ten element listy zadań spowoduje przejście do węzła odwołania do projektu, w którym występuje konflikt.  
  
 **Aby naprawić ten błąd**  
  
-   Określ jeden z zestawów bezpośrednio odwoływać się do projektu. Możliwe wadą tego podejścia jest nie gwarantuje zestawu wybranych do pracy z zestawów, które wymagają inna wersja przywoływanego zestawu.  
  
     \- lub —  
  
-   Upewnij się, że obie kopie zestawu o silnej nazwie i w globalnej pamięci podręcznej. Eliminuje to potrzebę skopiować te zestawy do katalogu bin.  
  
## <a name="see-also"></a>Zobacz też  
 [Zarządzanie odwołaniami w projekcie](../ide/managing-references-in-a-project.md)   
 [Globalna pamięć podręczna zestawów](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202)   
 [Zestawy o silnych nazwach](http://msdn.microsoft.com/library/d4a80263-f3e0-4d81-9b61-f0cbeae3797b)   
 [Przechowywanie wersji zestawu](http://msdn.microsoft.com/library/775ad4fb-914f-453c-98ef-ce1089b6f903)   
 [Instrukcje: Tworzenie i usuwanie zależności projektu](../ide/how-to-create-and-remove-project-dependencies.md)