---
title: Zapisywanie zestawu danych jako XML | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML [Visual Basic], datasets
- data [Visual Studio], saving as XML
- datasets [Visual Basic], saving as XML
- saving data
ms.assetid: 68b8327c-ae05-49ff-b9ba-99183e70b52c
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: c6176b1d7e9f18ce08fddf21f199cd21304ca8a4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="save-a-dataset-as-xml"></a>Zapisywanie zestawu danych jako XML
Dane XML w zestawie danych są dostępne przez wywołanie metody XML dostępne w zestawie danych. Aby zapisać dane w formacie XML, należy wywołać albo <xref:System.Data.DataSet.GetXml%2A> metody lub <xref:System.Data.DataSet.WriteXml%2A> metody <xref:System.Data.DataSet>.  
  
 Wywoływanie <xref:System.Data.DataSet.GetXml%2A> metoda zwraca ciąg zawierający dane ze wszystkich tabel danych w zestawie danych, która jest w formacie XML.  
  
 Wywoływanie <xref:System.Data.DataSet.WriteXml%2A> metoda wysyła dane w formacie XML w pliku, który określisz.  
  
### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-variable"></a>Zapisanie danych w zestawie danych jako XML do zmiennej  
  
-   <xref:System.Data.DataSet.GetXml%2A> Metoda zwraca <xref:System.String>. Oznacza to, że można zadeklarować zmiennej typu <xref:System.String> i przypisz mu wyniki <xref:System.Data.DataSet.GetXml%2A> metody.  
  
     [!code-vb[VbRaddataSaving#12](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_1.vb)]
     [!code-csharp[VbRaddataSaving#12](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_1.cs)]  
  
### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-file"></a>Aby zapisać danych w zestawie danych jako XML w pliku  
  
-   <xref:System.Data.DataSet.WriteXml%2A> Metoda ma kilka przeciążeń. Poniższy kod przedstawia sposób zapisywania danych do pliku. Deklaruje zmienną i jej przypisanie prawidłową ścieżkę do zapisania pliku.  
  
     [!code-vb[VbRaddataSaving#13](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_2.vb)]
     [!code-csharp[VbRaddataSaving#13](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_2.cs)]  
  
## <a name="see-also"></a>Zobacz też  
 [Zapisywanie danych z powrotem w bazie danych](../data-tools/save-data-back-to-the-database.md)