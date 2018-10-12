---
title: Przykładowy interfejs komunikatora programu Excel | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1dbf1090-762c-4824-82dd-2d7c2c6f00b6
caps.latest.revision: 13
ms.author: gewarren
manager: douge
ms.openlocfilehash: 1ffbfe7c8d69ecca2ff90dc1d01af2eb15d7d277
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49194444"
---
# <a name="sample-excel-communicator-interface"></a>Interfejs komunikatora programu Excel
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Przykład `IExcelUICommunication` interfejs jest używany w `ExcelUICommunicator` obiektu `ExcelAddIn` projektu.  
  
## <a name="iexceluicommunication-interface"></a>Interfejs IExcelUICommunication  
 Ten interfejs definiuje punkty komunikacji między `CodedUIExtension`, które są uruchamiane w procesie kodowanego testu interfejsu użytkownika i `ExcelCodedUIAddIn`, które są uruchamiane [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] procesu.  
  
 `ExcelCodedUIAddinHelper` Zestaw ma `ExcelUICommunicator` klasa pochodzi od tego interfejsu, która używa modelu obiektów programu Excel do przetwarzania metody.  
  
 Niektóre metody pobrać żądanych informacji z programu Excel, a następnie tworzenie i zwracają jeden informacji obiekty, takie jak `CellInformation` obiektu.  
  
 Inne metody użyć obiektu podanych informacji, Znajdź odpowiedni formant w programie Excel i wykonać niektóre procesy dla kontrolki. Na przykład `ScrollIntoView` metoda Przewija arkusz tak, aby wyznaczonym komórki jest widoczna.  
  
## <a name="codeduiextensibilitysample-and-excelcodeduiaddinhelper-communication"></a>CodedUIExtensibilitySample i komunikacja ExcelCodedUIAddinHelper  
 `ExcelCodedUIAddinHelper` Zestawu działa w procesie programu Excel i ma `UICommunicator` klasę, która implementuje `IExcelUITestCommunication` interfejsu i pobiera lub ustawia wymagane informacje bezpośrednio z poziomu interfejsu użytkownika programu Excel.  
  
 `CodedUIExtensibilitySample` Zestawu, który jest uruchamiany w procesie programu Visual Studio kodowanego testu interfejsu użytkownika. Ten zestaw zawiera `Communicator` klasy otworzy kanał wywołaniem funkcji zdalnych .NET, która zapewnia `Instance` właściwość, która używa `IExcelUICommunication` interfejsu, aby `UICommunicator` obiektu `ExcelCodedUIAddinHelper` zestawu do przekazania żądania i informacje obiekty, takie jak `CellInformation` obiektu i z powrotem między dwa zestawy.  
  
## <a name="see-also"></a>Zobacz też  
 [Rozszerzanie kodowanych testów interfejsu użytkownika i rejestrowanie akcji obsługujących program Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)   
 [Przykładowy dodatek programu Excel dla kodowanych testów UI](../test/sample-excel-add-in-for-coded-ui-testing.md)   
 [Przykładowe rozszerzenie kodowanych testów interfejsu użytkownika dla programu Excel](../test/sample-coded-ui-test-extension-for-excel.md)



