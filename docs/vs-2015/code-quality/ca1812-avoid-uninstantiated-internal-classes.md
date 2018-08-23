---
title: 'CA1812: Unikaj klas wewnętrznych bez wystąpień | Dokumentacja firmy Microsoft'
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
- CA1812
- AvoidUninstantiatedInternalClasses
helpviewer_keywords:
- AvoidUninstantiatedInternalClasses
- CA1812
ms.assetid: 1bb92a42-322a-44cc-98a8-8858212c1e1f
caps.latest.revision: 28
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6e9eac3243cefd3b429423020d4dfc17af38f562
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627851"
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812: Unikaj wewnętrznych klas bez wystąpień
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1812: Unikaj klas wewnętrznych bez wystąpień](https://docs.microsoft.com/visualstudio/code-quality/ca1812-avoid-uninstantiated-internal-classes).  
  
Element TypeName | AvoidUninstantiatedInternalClasses |  
| CheckId | CA1812 |  
| Kategoria | Microsoft.Performance|  
| Zmiana powodująca niezgodność | Bez podziału |  
  
## <a name="cause"></a>Przyczyna  
 Wystąpienie typu na poziomie zestawu nie jest tworzone przez kod w zestawie.  
  
## <a name="rule-description"></a>Opis reguły  
 Ta zasada próbuje zlokalizować wywołań do jednego z konstruktorów typu i zgłasza naruszenie, jeśli brak wywołania zostanie znaleziony.  
  
 Następujące typy nie są sprawdzane przez tę regułę:  
  
-   Typy wartości  
  
-   Typy abstrakcyjne  
  
-   Wyliczenia  
  
-   Delegaty  
  
-   Typy tablic emitowane przez kompilator  
  
-   Typy, którego nie można utworzyć wystąpienia i definiują `static` (`Shared` w języku Visual Basic) tylko metody.  
  
 Jeśli zastosujesz <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName> do zestawu, który jest analizowana, ta zasada zostanie przeprowadzona na żadnych konstruktorów, które są oznaczone jako `internal` , ponieważ nie można sprawdzić, czy pole jest używany przez inny `friend` zestawu.  
  
 Mimo że nie można obejść to ograniczenie w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] analizy kodu zewnętrznego autonomicznego programu FxCop wystąpi na wewnętrzny konstruktory co `friend` zestawu znajduje się w analizie.  
  
## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia  
 Aby naprawić naruszenie tej zasady, Usuń typ lub Dodaj kod, który korzysta z niego. Jeśli typ zawiera tylko metody statyczne, Dodaj jedną z następujących do typu, aby uniemożliwić kompilatorowi emitowania publiczne wystąpienia domyślnego konstruktora:  
  
-   Konstruktor prywatny dla typów, których platformą docelową [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] w wersjach 1.0 i 1.1.  
  
-   `static` (`Shared` w języku Visual Basic) modyfikator dla typów, których platformą docelową [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)].  
  
## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia  
 Jest bezpieczne pominąć ostrzeżenie od tej reguły. Firma Microsoft zaleca, aby pominąć to ostrzeżenie w następujących sytuacjach:  
  
-   Klasa jest tworzona za pośrednictwem metody z późnym wiązaniem odbicia, takich jak <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>.  
  
-   Klasa jest tworzony automatycznie w czasie wykonywania lub [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]. Na przykład klas, które implementują <xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName> lub <xref:System.Web.IHttpHandler?displayProperty=fullName>.  
  
-   Klasa jest przekazywany jako parametr typu ogólnego, który ma nowe ograniczenie. Na przykład poniższy przykład zgłosi tej reguły.  
  
    ```csharp  
    internal class MyClass  
    {     
        public DoSomething()     
        {  
        }  
    }   
    public class MyGeneric<T> where T : new()  
    {  
        public T Create()  
        {  
            return new T();     
        }  
    }  
    // [...]   
    MyGeneric<MyClass> mc = new MyGeneric<MyClass>();  
    mc.Create();  
    ```  
  
 W takich przypadkach zaleca się, że pominąć to ostrzeżenie.  
  
## <a name="related-rules"></a>Powiązane reguły  
 [CA1811: Unikaj niewywoływanego kodu prywatnego](../code-quality/ca1811-avoid-uncalled-private-code.md)  
  
 [CA1801: Przejrzyj nieużywane parametry](../code-quality/ca1801-review-unused-parameters.md)  
  
 [CA1804: Usuń nieużywane zmienne lokalne](../code-quality/ca1804-remove-unused-locals.md)



