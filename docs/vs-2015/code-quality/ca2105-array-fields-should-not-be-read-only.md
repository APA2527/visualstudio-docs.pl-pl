---
title: 'CA2105: Pola tablicy nie odczytywane tylko | Dokumentacja firmy Microsoft'
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
- CA2105
- ArrayFieldsShouldNotBeReadOnly
helpviewer_keywords:
- ArrayFieldsShouldNotBeReadOnly
- CA2105
ms.assetid: 0bdc3421-3ceb-4182-b30c-a992fbfcc35d
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 073e86963aee40c0e781f1096ac4e9a93b14287a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677008"
---
# <a name="ca2105-array-fields-should-not-be-read-only"></a>CA2105: Pola tablicy nie powinny być tylko do odczytu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA2105: pola tablicy nie można odczytać tylko](https://docs.microsoft.com/visualstudio/code-quality/ca2105-array-fields-should-not-be-read-only).  
  
Element TypeName | ArrayFieldsShouldNotBeReadOnly |  
| CheckId | CA2105 |  
| Kategoria | Microsoft.Security|  
| Zmiana powodująca niezgodność | Przerwanie |  
  
## <a name="cause"></a>Przyczyna  
 Pole publiczne lub chronione, który zawiera tablicę jest zadeklarowany tylko do odczytu.  
  
## <a name="rule-description"></a>Opis reguły  
 Po zastosowaniu `readonly` (`ReadOnly` w [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) modyfikatora pola, które zawiera tablicę, pola nie można zmienić do odwoływania się do innej tablicy. Można jednak zmienić elementy tablicy, które są przechowywane w polu tylko do odczytu. Kod, który podejmuje decyzje lub wykonuje operacje, które są oparte na elementach tablicy tylko do odczytu, które są publicznie dostępne mogą zawierać luki w zabezpieczeniach kończona.  
  
 Należy pamiętać, że mających publiczne pole również narusza regułę projektowania [CA1051: nie deklaruj widocznych pól wystąpień](../code-quality/ca1051-do-not-declare-visible-instance-fields.md).  
  
## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia  
 Aby rozwiązać problem luki w zabezpieczeniach, która jest identyfikowana przez tę regułę, nie należy polegać na zawartości tablicy tylko do odczytu, które są publicznie dostępne. Zdecydowanie zaleca się korzystanie z jednej z następujących procedur:  
  
-   Zastąp tablicy silnie typizowaną kolekcją, której nie można zmienić. Aby uzyskać więcej informacji, zobacz <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>.  
  
-   Zastąp pole publiczne metody, która zwróci klon tablicy prywatnej. Ponieważ kod nie polega na klonie, nie ma ryzyka, jeśli elementy są modyfikowane.  
  
 Jeśli została wybrana opcja drugiej metody, nie zastępują pola z właściwością; właściwości zwracające tablice niekorzystnie wpłynąć na wydajność. Aby uzyskać więcej informacji, zobacz [CA1819: właściwości nie powinny zwracać tablic](../code-quality/ca1819-properties-should-not-return-arrays.md).  
  
## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia  
 Wykluczenie ostrzeżenie od tej reguły jest zdecydowanie odradzane. Niemal żadnych scenariuszy wystąpić, gdy zawartość pola tylko do odczytu nie są ważne. Jeśli jest to w przypadku danego scenariusza, należy usunąć `readonly` modyfikator zamiast wiadomości z wyjątkiem.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie pokazano niebezpieczeństwa naruszenie tej zasady. Pierwsza część zawiera biblioteki przykładu, który ma typ, `MyClassWithReadOnlyArrayField`, która zawiera dwa pola (`grades` i `privateGrades`), które nie są bezpieczne. Pole `grades` publicznej i w związku z tym narażony na dowolny obiekt wywołujący. Pole `privateGrades` jest prywatny, ale jest nadal podatne, ponieważ jest on zwracany do wywoływania przez `GetPrivateGrades` metody. `securePrivateGrades` Pole jest widoczne w bezpieczny sposób przez `GetSecurePrivateGrades` metody. Jest zadeklarowany jako prywatny dobrego projektowania rozwiązań. Druga część zawiera kod, który zmienia wartości przechowywane w `grades` i `privateGrades` elementów członkowskich.  
  
 Biblioteka klas przykład pojawia się w następującym przykładzie.  
  
 [!code-csharp[FxCop.Security.ArrayFieldsNotReadOnly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.ArrayFieldsNotReadOnly/cs/FxCop.Security.ArrayFieldsNotReadOnly.cs#1)]  
  
## <a name="example"></a>Przykład  
 W poniższym kodzie użyto przykład biblioteki klas, aby zilustrować problemy z zabezpieczeniami tablicy tylko do odczytu.  
  
 [!code-csharp[FxCop.Security.TestArrayFieldsRead#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TestArrayFieldsRead/cs/FxCop.Security.TestArrayFieldsRead.cs#1)]  
  
 Dane wyjściowe z tego przykładu są:  
  
 **Przed naruszeniem: klas: 90, 90, 90 stopni prywatne: 90, 90, 90 Secure klas, 90, 90, 90**  
**Po naruszeniu: klas: 90, 555, 90 stopni prywatne: 90, 555, 90 Secure klas, 90, 90, 90**   
## <a name="see-also"></a>Zobacz też  
 <xref:System.Array?displayProperty=fullName>   
 <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>



