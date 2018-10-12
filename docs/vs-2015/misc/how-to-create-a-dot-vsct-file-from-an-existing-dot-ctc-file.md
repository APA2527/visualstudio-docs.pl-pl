---
title: 'Porady: tworzenie. Plik Vsct z istniejącej. Plik CTC | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSCT files, creating based on a .ctc file
ms.assetid: 700e80a4-c1e1-4178-af53-45e86dd2c08b
caps.latest.revision: 9
manager: douge
ms.openlocfilehash: e159fea34dc395ce2d7bded813f2d8feaa453006
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49303488"
---
# <a name="how-to-create-a-vsct-file-from-an-existing-ctc-file"></a>Porady: tworzenie. Plik Vsct z istniejącej. Plik CTC
Można utworzyć pliku vsct oparty na składni XML z istniejącego pliku źródłowego .ctc tabeli poleceń. Dzięki temu możesz korzystać z zalet nowego opartego na języku XML [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] format kompilatora tabeli (VSCT) polecenia.  
  
### <a name="to-create-a-vsct-file-from-a-ctc-file"></a>Do utworzenia pliku vsct z pliku .ctc  
  
1.  Uzyskaj kopię programu języka Perl.  
  
2.  Uzyskaj kopię skryptu Perl ConvertCTCToVSCT.pl, zazwyczaj znajduje się w  *\<ścieżka instalacji programu Visual Studio SDK >* \VisualStudioIntegration\Tools\bin folderu.  
  
3.  Uzyskaj kopię pliku źródłowego .ctc, który ma zostać przekonwertowany.  
  
4.  Umieść pliki w tym samym katalogu.  
  
5.  W [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] polecenia monitu okna, przejdź do katalogu.  
  
6.  Typ  
  
    ```  
    perl.exe ConvertCTCtoVSCT.pl PkgCmd.ctc PkgCmd.vsct  
    ```  
  
     gdzie PkgCmd.ctc jest nazwą pliku .ctc a PkgCmd.vsct jest nazwą pliku vsct, który chcesz utworzyć.  
  
     Spowoduje to utworzenie nowego vsct polecenia tabeli źródłowego pliku XML. Plik można kompilować przy użyciu Vsct.exe, kompilator VSCT, tak jak dowolnego innego pliku vsct.  
  
    > [!NOTE]
    >  Można zwiększyć czytelność pliku vsct przez ponowne formatowanie komentarze XML.  
  
## <a name="see-also"></a>Zobacz też  
 [Porady: tworzenie. Pliku Vsct](../extensibility/internals/how-to-create-a-dot-vsct-file.md)   
 [Tabela poleceń programu Visual Studio (pliki Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)