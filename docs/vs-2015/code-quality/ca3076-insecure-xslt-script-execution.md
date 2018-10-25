---
title: 'CA3076: Niezabezpieczone wykonywanie skryptu XSLT | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53cb7a46-c564-488f-bc51-0e210a7853c9
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 39aebc0e7681b139e021c48c12a87d4b060cc7af
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49911476"
---
# <a name="ca3076-insecure-xslt-script-execution"></a>CA3076: Niezabezpieczone wykonywanie skryptu XSLT
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|InsecureXSLTScriptExecution|
|CheckId|CA3076|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Jeśli zostanie wykonana [Extensible arkuszy stylów języka przekształcenia (XSLT)](https://support.microsoft.com/en-us/kb/313997) w aplikacjach .NET insecurely, procesor może [rozwiązać niezaufanych identyfikatora URI odwołania](http://msdn.microsoft.com/en-us/ba3e4d4f-1ee7-4226-a51a-78a1f1b5bd8a) , może ujawnić poufne informacje do osoby atakujące, co prowadzi do ataków typu "odmowa usługi" i między lokacjami.

## <a name="rule-description"></a>Opis reguły
 [XSLT](http://msdn.microsoft.com/en-us/6377ce5f-3c45-42a6-b7a9-ec8da588b60c) jest standardem World Wide Web Consortium (W3C) do przekształcania danych XML. XSLT zazwyczaj używany do zapisywania arkuszy stylów do przekształcania danych XML do innych formatów, takich jak HTML, stała długość tekstu, tekst rozdzielany przecinkami lub w innym formacie XML. Mimo że będzie to zabronione przez domyślne, można ją włączyć dla Twojego projektu.

 Aby upewnić się, nie jest ujawniany obszar narażony na ataki, ta zasada wyzwala zawsze, gdy XslCompiledTransform.<xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> odbiera wystąpień kombinacji niezabezpieczone <xref:System.Xml.Xsl.XsltSettings> i <xref:System.Xml.XmlResolver>, która pozwala na przetwarzanie złośliwy skrypt.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia

-   Zastąp niezabezpieczone argument XsltSettings XsltSettings.<xref:System.Xml.Xsl.XsltSettings.Default%2A> lub z wystąpieniem, wyłączył możliwość wykonywania funkcji i skryptów dokumentu.

-   Zastąp <xref:System.Xml.XmlResolver> argumentu o wartości null lub <xref:System.Xml.XmlSecureResolver> wystąpienia.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Jeśli nie masz pewności, że dane wejściowe jest znany jako z zaufanego źródła, nie Pomijaj reguły z tego ostrzeżenia.

## <a name="pseudo-code-examples"></a>Przykłady pseudo-kodu

### <a name="violation"></a>Naruszenie zasad

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
         void TestMethod()
        {
             XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
             var settings = XsltSettings.TrustedXslt;
             var resolver = new XmlUrlResolver();
             xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn
        }
    }
} 
```

### <a name="solution"></a>Rozwiązanie

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        void TestMethod()
        {
            XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
            var settings = XsltSettings.Default;
            var resolver = new XmlUrlResolver();
            xslCompiledTransform.Load("testStylesheet", settings, resolver);
        }
    }
}
```

### <a name="violation"></a>Naruszenie zasad

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod(XsltSettings settings)
        {
            try
            {
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn
            }
            catch { throw; }
            finally { }
        }
    }
}
```

### <a name="solution"></a>Rozwiązanie

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod(XsltSettings settings)
        {
            try
            {
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                settings.EnableDocumentFunction = false;
                settings.EnableScript = false;
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver);
            }
            catch { throw; }
            finally { }
        }
    }
}
```



