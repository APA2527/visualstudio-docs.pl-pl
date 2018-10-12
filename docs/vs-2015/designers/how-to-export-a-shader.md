---
title: 'Porady: eksport cieniowania | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bd48bf4-9792-4456-a545-e462a2be668d
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e8c3a6ea90b43caeb1140cbb9ab7c699bdb09c3e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49213294"
---
# <a name="how-to-export-a-shader"></a>Porady: eksport cieniowania
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

W tym dokumencie pokazano, jak wyeksportować modułu cieniującego kierowane wykres modułu cieniującego języka (DGSL) służy w swojej aplikacji za pomocą projektanta modułu cieniującego.  
  
 W tym dokumencie przedstawiono to działanie:  
  
-   Eksportowanie cieniowania  
  
## <a name="exporting-a-shader"></a>Eksportowanie cieniowania  
 Po utworzeniu modułu cieniującego, przy użyciu narzędzia Projektant programu do cieniowania i przed użyciem w swojej aplikacji, należy go wyeksportować w formacie, który rozumie interfejsu API grafiki. Możesz wyeksportować modułu cieniującego na różne sposoby do potrzeb różnych.  
  
#### <a name="to-export-a-shader"></a>Aby wyeksportować modułu cieniującego  
  
1.  W [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], otwórz **wizualny wykres modułu cieniującego (.dgsl)** pliku.  
  
     Jeśli nie masz **wizualny wykres modułu cieniującego (.dgsl)** plik, aby otworzyć, utwórz je, zgodnie z opisem w [porady: tworzenie cieniowania koloru podstawowego](../designers/how-to-create-a-basic-color-shader.md).  
  
2.  Na **Shader Designer** narzędzi, wybierz **zaawansowane**, **wyeksportować**, **Eksportuj jako**. **Eksportowania modułu cieniującego** zostanie wyświetlone okno dialogowe.  
  
3.  W **Zapisz jako typ** listy rozwijanej wybierz format, który chcesz wyeksportować.  
  
     Poniżej przedstawiono formaty, które można wybrać:  
  
     **Program do cieniowania pikseli HLSL (\*.hlsl)**  
     Eksportuje programu do cieniowania w postaci kodu źródłowego wysokiej Level Shader Language (HLSL). Ta opcja umożliwia później zmodyfikować cieniowanie tak, nawet w przypadku, po jej wdrożeniu w aplikacji. To może ułatwić debugowanie i poprawki kodu, w oparciu problemy użytkowników końcowych, ale również ułatwia użytkownikowi modyfikowanie modułu cieniującego niechciane — na przykład, aby uzyskać nienależną przewagę w grze przewagę. Ponadto może to zwiększyć czas ładowania modułu cieniującego.  
  
     **Skompilowany program do cieniowania pikseli (\*.cso)**  
     Eksportuje programu do cieniowania w postaci kodu bajtowego języka HLSL. Ta opcja powoduje, że istnieje możliwość modyfikowania programu do cieniowania później, nawet w przypadku, po jej wdrożeniu w aplikacji. To może ułatwić debugowanie i poprawki kodu, w oparciu problemy użytkowników końcowych, ale ponieważ programu do cieniowania jest wstępnie skompilowanym, go nie są naliczane dodatkowe środowiska uruchomieniowego obciążenie podczas ładowania programu do cieniowania za pomocą aplikacji. Wystarczająco doświadczeni użytkownicy mogą modyfikować programu do cieniowania w sposób niepożądane, ale kompilowanie programu do cieniowania sprawia, że to znacznie trudniejsze.  
  
     **Nagłówek języka C++ (\*.h)**  
     Eksportuje programu do cieniowania w postaci nagłówek stylu C, który definiuje tablica bajtów, która zawiera kod bajtowy HLSL. Tej opcji można tworzyć bardziej czasochłonne debugować i poprawki kodu, w oparciu problemy użytkowników końcowych, ponieważ aplikacja musi ponownie skompilowana, aby przetestować poprawki. Jednak ponieważ dzięki temu jest trudne, chociaż nie jest to niemożliwe, aby zmodyfikować cieniowanie tak, po jej wdrożeniu w aplikacji, stanowi trudności w większości użytkownikowi, który chce się zmodyfikować cieniowanie tak, w sposób niepożądane.  
  
4.  W **nazwy pliku** pola kombi, określ nazwę dla eksportowanego programu do cieniowania, a następnie wybierz **Zapisz** przycisku.  
  
## <a name="see-also"></a>Zobacz też  
 [Porady: tworzenie cieniowania koloru podstawowego](../designers/how-to-create-a-basic-color-shader.md)   
 [Projektant cieniowania](../designers/shader-designer.md)



