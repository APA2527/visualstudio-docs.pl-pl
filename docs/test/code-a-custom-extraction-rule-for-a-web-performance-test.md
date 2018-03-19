---
title: "Kodowanie niestandardowej reguły wyodrębniania dla testów wydajności sieci web w programie Visual Studio | Dokumentacja firmy Microsoft"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- extraction rules
- Web performance tests, creating custom extraction rules
- extraction rules, creating custom
ms.assetid: 6bcc5712-6cc6-4f59-8933-6e8078318c45
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: fdc2f2209ccd0aae555783b9fbc9630983731b73
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2018
---
# <a name="coding-a-custom-extraction-rule-for-a-web-performance-test"></a>Kodowanie niestandardowej reguły wyodrębniania dla testów wydajności sieci Web

Użytkownicy mogą tworzyć własne reguły wyodrębniania. W tym celu należy utworzyć własne reguły jako pochodne wybranej klasy reguł wyodrębniania. Reguły wyodrębniania pochodzą od klasy bazowej <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule>.

> [!NOTE]
> Można również tworzyć niestandardowe reguły sprawdzania poprawności. Aby uzyskać więcej informacji, zobacz [Tworzenie niestandardowych kodów i wtyczek dla testów obciążenia](../test/create-custom-code-and-plug-ins-for-load-tests.md).

## <a name="to-create-a-custom-extraction-rule"></a>Aby utworzyć niestandardową regułę wyodrębniania

1.  Otwórz projekt Test zawierający test wydajności sieci Web.

2.  (Opcjonalnie) Utwórz oddzielny projekt Biblioteka klas, w którym będzie przechowywana reguła wyodrębniania.

    > [!IMPORTANT]
    > Klasę można utworzyć w tym samym projekcie, w którym znajdują się testy. Jednak chcąc używać zdefiniowanej reguły do różnych testów, najlepiej utworzyć oddzielny projekt Biblioteki klas i w nim przechowywać regułę. W przypadku utworzenia oddzielnego projektu należy wykonać opcjonalne kroki podane w tej procedurze.

3.  (Opcjonalnie) W projekcie Biblioteka klas dodaj odwołanie do biblioteki dll Microsoft.VisualStudio.QualityTools.WebTestFramework.

4.  Utwórz klasę pochodną od klasy <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule>. Zaimplementuj elementy członkowskie <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule.Extract*> i <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule.RuleName*>.

5.  (Opcjonalnie) Skompiluj nowy projekt Biblioteka klas.

6.  (Opcjonalnie) W projekcie Test dodaj odwołanie do projektu Biblioteka klas zawierającego niestandardową regułę wyodrębniania.

7.  W projekcie Test, otwórz testu wydajności sieci Web w **edytora testów wydajności sieci Web**.

8.  Aby dodać niestandardowej reguły wyodrębniania, kliknij prawym przyciskiem myszy żądania testu wydajności sieci Web, a następnie wybierz **Dodawanie reguły wyodrębniania**.

     **Dodawanie reguły wyodrębniania** zostanie wyświetlone okno dialogowe. Zostanie wyświetlony z niestandardowej reguły walidacji w **wybierz regułę** listy wraz z reguł sprawdzania poprawności wstępnie zdefiniowane. Wybierz reguły wyodrębniania niestandardowego, a następnie wybierz pozycję **OK**.

9. Wykonaj test wydajności sieci Web.

## <a name="example"></a>Przykład

Poniższy kod pokazuje implementację niestandardowej reguły wyodrębniania. Ta reguła wyodrębnia wartość ze wskazanego pola wejściowego. Przykładu należy użyć jako punktu wyjścia dla tworzenia własnych niestandardowych reguł wyodrębniania.

```csharp
using System;
using System.Collections.Generic;
using Microsoft.VisualStudio.TestTools.WebTesting;
using System.Globalization;

namespace ClassLibrary2
{
    //-------------------------------------------------------------------------
    // This class creates a custom extraction rule named "Custom Extract Input"
    // The user of the rule specifies the name of an input field, and the
    // rule attempts to extract the value of that input field.
    //-------------------------------------------------------------------------
    public class CustomExtractInput : ExtractionRule
    {
        /// Specify a name for use in the user interface.
        /// The user sees this name in the Add Extraction dialog box.
        //---------------------------------------------------------------------
        public override string RuleName
        {
            get { return "Custom Extract Input"; }
        }

        /// Specify a description for use in the user interface.
        /// The user sees this description in the Add Extraction dialog box.
        //---------------------------------------------------------------------
        public override string RuleDescription
        {
            get { return "Extracts the value from a specified input field"; }
        }

        // The name of the desired input field
        private string NameValue;
        public string Name
        {
            get { return NameValue; }
            set { NameValue = value; }
        }

        // The Extract method.  The parameter e contains the web performance test context.
        //---------------------------------------------------------------------
        public override void Extract(object sender, ExtractionEventArgs e)
        {
            if (e.Response.HtmlDocument != null)
            {
                foreach (HtmlTag tag in e.Response.HtmlDocument.GetFilteredHtmlTags(new string[] { "input" }))
                {
                    if (String.Equals(tag.GetAttributeValueAsString("name"), Name, StringComparison.InvariantCultureIgnoreCase))
                    {
                        string formFieldValue = tag.GetAttributeValueAsString("value");
                        if (formFieldValue == null)
                        {
                            formFieldValue = String.Empty;
                        }

                        // add the extracted value to the web performance test context
                        e.WebTest.Context.Add(this.ContextParameterName, formFieldValue);
                        e.Success = true;
                        return;
                    }
                }
            }
            // If the extraction fails, set the error text that the user sees
            e.Success = false;
            e.Message = String.Format(CultureInfo.CurrentCulture, "Not Found: {0}", Name);
        }
    }
}
```

```vb
Imports System
Imports System.Collections.Generic
Imports Microsoft.VisualStudio.TestTools.WebTesting
Imports System.Globalization

Namespace ClassLibrary2

    '-------------------------------------------------------------------------
    ' This class creates a custom extraction rule named "Custom Extract Input"
    ' The user of the rule specifies the name of an input field, and the
    ' rule attempts to extract the value of that input field.
    '-------------------------------------------------------------------------
    Public Class CustomExtractInput
        Inherits ExtractionRule

        ' Specify a name for use in the user interface.
        ' The user sees this name in the Add Extraction dialog box.
        '---------------------------------------------------------------------
        Public Overrides ReadOnly Property RuleName() As String
            Get
                Return "Custom Extract Input"
            End Get
        End Property

        ' Specify a description for use in the user interface.
        ' The user sees this description in the Add Extraction dialog box.
        '---------------------------------------------------------------------
        Public Overrides ReadOnly Property RuleDescription() As String
            Get
                Return "Extracts the value from a specified input field"
            End Get
        End Property

        ' The name of the desired input field
        Private NameValue As String
        Public Property Name() As String
            Get
                Return NameValue
            End Get
            Set(ByVal value As String)
                NameValue = value
            End Set
        End Property

        ' The Extract method.  The parameter e contains the web performance test context.
        '---------------------------------------------------------------------
        Public Overrides Sub Extract(ByVal sender As Object, ByVal e As ExtractionEventArgs)

            If Not e.Response.HtmlDocument Is Nothing Then

                For Each tag As HtmlTag In e.Response.HtmlDocument.GetFilteredHtmlTags(New String() {"input"})

                    If String.Equals(tag.GetAttributeValueAsString("name"), Name, StringComparison.InvariantCultureIgnoreCase) Then

                        Dim formFieldValue As String = tag.GetAttributeValueAsString("value")
                        If formFieldValue Is Nothing Then

                            formFieldValue = String.Empty
                        End If

                        ' add the extracted value to the web performance test context
                        e.WebTest.Context.Add(Me.ContextParameterName, formFieldValue)
                        e.Success = True
                        Return
                    End If
                Next
            End If
            ' If the extraction fails, set the error text that the user sees
            e.Success = False
            e.Message = String.Format(CultureInfo.CurrentCulture, "Not Found: {0}", Name)
        End Sub
    End Class
End Namespace
```

Metoda <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule.Extract*> zawiera podstawowe funkcje reguły wyodrębniania. Metoda <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule.Extract*> w poprzednim przykładzie przyjmuje jako wartość element <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionEventArgs>, który dostarcza odpowiedzi generowane przez żądanie objęte regułą wyodrębniania. Odpowiedź zawiera element <xref:Microsoft.VisualStudio.TestTools.WebTesting.HtmlDocument>, w którym znajdują się wszystkie znaczniki odpowiedzi. Znaczniki wejściowe są odfiltrowywane z elementu <xref:Microsoft.VisualStudio.TestTools.WebTesting.HtmlDocument>. Każdy znacznik wejściowy jest pod kątem atrybutu o nazwie `name` którego wartość jest równa użytkownika podana wartość `Name` właściwości. Jeśli zostanie znaleziony tagu z tym atrybutem dopasowania, aby wyodrębnić wartości, który jest zawarty w podejmowana jest próba `value` atrybut, jeśli istnieje atrybut wartości. Jeśli istnieje, nazwa i wartość znacznika są wyodrębniane i dodawane do kontekstu testu wydajności sieci Web. Reguła wyodrębniania zadziałała pomyślnie.

## <a name="see-also"></a>Zobacz także

- <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractAttributeValue>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractFormField>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractHttpHeader>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractRegularExpression>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractText>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractHiddenFields>
- [Kodowanie niestandardowej reguły walidacji dla testów wydajności sieci web](../test/code-a-custom-validation-rule-for-a-web-performance-test.md)