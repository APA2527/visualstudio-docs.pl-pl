---
title: 'Porady: Tworzenie dokumentu XML na podstawie schematu XSD | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 193b195f-e918-4c79-a1a1-8096a1433bde
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bbecacc0729c936489c05d3bb59260341a08d314
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49884228"
---
# <a name="how-to-create-an-xml-document-based-on-an-xsd-schema"></a>Porady: Tworzenie dokumentu XML na podstawie schematu XSD
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
**Generowanie XML przykładowe** funkcja generuje przykładowy plik XML na podstawie pliku schematu XML (XSD).  
  
 Tej opcji można użyć w następujących scenariuszach:  
  
- Aby poznać użycie różnych konstrukcji w schemacie.  
  
- Aby upewnić się, że schemat wykonuje co ma na celu.  
  
  **Generowanie XML przykładowe** funkcja jest dostępna tylko na elementy globalne i wymaga prawidłowego zestawu schematu XML.  
  
  Ta funkcja generuje zwykle ważnych dokumentów XML. Jednakże, jeśli schemat zawiera co najmniej jeden z następujących czynności, próbki mogą być nieprawidłowe:  
  
- `xs:key`, `xs:keyref`, I `xs:unique` ograniczenia tożsamości.  
  
- `xs:pattern` zestawy reguł.  
  
- Wyliczenia o `xs:QName` typu.  
  
- `xs:ENTITY`, `xs:ENTITIES`, i `xs:NOTATION` typów.  
  
  Ponadto należy pamiętać, że `xs:base64Binary` zawartość zostanie wygenerowany tylko wtedy, gdy wyliczenia występują w schematu dla tego typu.  
  
### <a name="to-generate-an-xml-instance-document-based-on-the-xsd-file"></a>Można wygenerować wystąpienia dokumentu XML na podstawie pliku XSD  
  
1.  Postępuj zgodnie z instrukcjami w [porady: tworzenie i edytowanie pliku schematu XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).  
  
2.  W [Eksploratora schematu XML](../xml-tools/xml-schema-explorer.md), kliknij prawym przyciskiem myszy `PurchaseOrder` element globalny. Wybierz **wygenerować przykładowy kod XML**.  
  
     Po wybraniu tej opcji, plik PurchaseOrder.xml o następującej zawartości XML przykładowych zostanie wygenerowany i otwartego w edytorze XML:  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <PurchaseOrder OrderDate="1900-01-01" xmlns="http://tempuri.org/PurchaseOrderSchema.xsd">  
      <ShipTo country="US">  
        <name>name1</name>  
        <street>street1</street>  
        <city>city1</city>  
        <state>state1</state>  
        <zip>1</zip>  
      </ShipTo>  
      <ShipTo country="US">  
        <name>name2</name>  
        <street>street2</street>  
        <city>city2</city>  
        <state>state2</state>  
        <zip>-79228162514264337593543950335</zip>  
      </ShipTo>  
      <BillTo country="US">  
        <name>name1</name>  
        <street>street1</street>  
        <city>city1</city>  
        <state>state1</state>  
        <zip>1</zip>  
      </BillTo>  
    </PurchaseOrder>  
    ```  
  
## <a name="see-also"></a>Zobacz też  
 [Praca z danymi XML](../xml-tools/working-with-xml-data.md)



