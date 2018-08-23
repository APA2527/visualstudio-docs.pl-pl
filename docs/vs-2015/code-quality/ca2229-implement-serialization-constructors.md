---
title: 'CA2229: Zaimplementuj konstruktory serializacji | Dokumentacja firmy Microsoft'
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
- CA2229
- ImplementSerializationConstructors
helpviewer_keywords:
- CA2229
- ImplementSerializationConstructors
ms.assetid: 8e04d5fe-dfad-445a-972e-0648324fac45
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 815e2ad834e806e79391664e0576fad8f8ab9bd0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633414"
---
# <a name="ca2229-implement-serialization-constructors"></a>CA2229: Należy zaimplementować konstruktory serializacji
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA2229: zaimplementuj konstruktory serializacji](https://docs.microsoft.com/visualstudio/code-quality/ca2229-implement-serialization-constructors).  
  
Element TypeName | ImplementSerializationConstructors |  
| CheckId | CA2229 |  
| Kategoria | Microsoft.Usage|  
| Zmiana powodująca niezgodność | Inne niż powodująca niezgodność |  
  
## <a name="cause"></a>Przyczyna  
 Typ implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> interfejsu, nie jest delegat lub interfejsu i jest spełniony jeden z następujących warunków:  
  
-   Typ nie ma konstruktora przyjmującego <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> obiektu i <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> obiektu (podpis konstruktora serializacji).  
  
-   Niezapieczętowany typ i modyfikator dostępu dla jego konstruktora serializacji nie jest chroniony (rodzina).  
  
-   Typ nie jest zapieczętowany i nie jest prywatny modyfikator dostępu dla jego konstruktora serializacji.  
  
## <a name="rule-description"></a>Opis reguły  
 Ta reguła ma znaczenie dla typów, które obsługują niestandardowej serializacji. Typ obsługuje niestandardowej serializacji, jeśli implementuje <xref:System.Runtime.Serialization.ISerializable> interfejsu. Konstruktor serializacji jest wymagany do deserializacji lub ponownie utworzyć obiekty, które zostały zserializowanym przy użyciu <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> metody.  
  
## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia  
 Aby naprawić naruszenie tej zasady, należy zaimplementować konstruktora serializacji. Dla zamkniętej klasy należy ustawić konstruktor prywatny; w przeciwnym razie powinien być chroniony.  
  
## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia  
 Nie pomijaj naruszenie reguły. Typ nie będzie można ich zdeserializować i nie będzie działać w wielu scenariuszach.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje typ, który spełnia reguły.  
  
 [!code-csharp[FxCop.Usage.ISerializableCtor#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.ISerializableCtor/cs/FxCop.Usage.ISerializableCtor.cs#1)]  
  
## <a name="related-rules"></a>Powiązane reguły  
 [CA2237: Oznacz typy ISerializable za pomocą atrybutu SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>



