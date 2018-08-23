---
title: Zagadnienia dotyczące zabezpieczeń podczas pracy z danymi XML | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce2b708-1aef-454f-be59-52b76f359351
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9acd701c4e279d02cae874768b18a3d89b58203d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677921"
---
# <a name="security-considerations-when-working-with-xml-data"></a>Zagadnienia dotyczące zabezpieczeń podczas pracy z danymi XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [zagadnienia dotyczące zabezpieczeń podczas pracy z danymi XML](https://docs.microsoft.com/visualstudio/xml-tools/security-considerations-when-working-with-xml-data).  
  
  
W tym temacie omówiono problemy z zabezpieczeniami, które należy znać podczas pracy z edytorem XML lub debugerze XSLT.  
  
## <a name="xml-editor"></a>Edytor XML  
 Edytor XML opiera się na edytorze tekstu programu Visual Studio. Opiera się na <xref:System.Xml> i <xref:System.Xml.Xsl> klasy do obsługi wielu procesów XML.  
  
-   Przekształcenia XSLT są wykonywane w nowej domenie aplikacji. Przekształcenia XSLT są *piaskownicy*; oznacza to, że zasady zabezpieczeń dostępu kodu komputera służy do określania ograniczone uprawnienia oparte na którym znajduje się arkusza stylów XSLT. Na przykład arkusze stylów z lokalizacji internetowej mieć najbardziej ograniczone uprawnienia, a arkusze stylów skopiowany na dysk twardy, uruchom z pełnego zaufania.  
  
-   <xref:System.Xml.Xsl.XslCompiledTransform> Klasa jest używana do kompilowania XSLT do języka pośredniego firmy Microsoft, aby zwiększyć wydajność w czasie wykonywania.  
  
-   Schematy, prowadzące do lokalizacji zewnętrznej w pliku wykazu są automatycznie pobierane po pierwszym załadowaniu edytora XML. <xref:System.Xml.Schema.XmlSchemaSet> Klasa jest używana do kompilowania schematów. Plik wykazu, który jest dostarczany za pomocą edytora XML nie ma łącza do zewnętrznych schematów. Użytkownik musi jawnie dodać odwołanie do zewnętrznych schematu przed edytora XML pliki do pobrania pliku schematu. Pobieranie HTTP można wyłączyć za pomocą **różne opcje narzędzi** strony edytora XML.  
  
-   Edytor XML używa <xref:System.Net> klasy do pobrania schematów  
  
## <a name="xslt-debugger"></a>Debuger XSLT  
 Debuger XSLT korzysta z aparatu debugowania zarządzanego programu Visual Studio i klas z <xref:System.Xml> i <xref:System.Xml.Xsl> przestrzeni nazw.  
  
-   Debuger XSLT uruchamia każde przekształcenie XSLT w domenie aplikacji w trybie piaskownicy. Zasady zabezpieczeń dostępu kodu na komputerze jest używana do określania ograniczonych uprawnień oparte na którym znajduje się arkusza stylów XSLT. Na przykład arkusze stylów z lokalizacji internetowej mieć najbardziej ograniczone uprawnienia, a arkusze stylów skopiowany na dysk twardy, uruchom z pełnego zaufania.  
  
-   Arkusz stylów XSLT jest skompilowana przy użyciu <xref:System.Xml.Xsl.XslCompiledTransform> klasy.  
  
-   Ewaluator wyrażeń XSLT jest ładowany przez aparat debugowania zarządzanego. Aparat debugowania zarządzanego przyjęto założenie, że cały kod jest uruchamiany z komputera lokalnego użytkownika. W związku z tym <xref:System.Xml.Xsl.XslCompiledTransform> klasy pobiera plik XSLT do użytkownika komputera lokalnego. Możliwość, że podwyższenie poziomu w uprawnień do wykonywania może wystąpić skuteczność została osłabiona przez wykonywanie wszystkie przekształcenia XSLT w nowej domeny aplikacji z ograniczonymi uprawnieniami  
  
## <a name="see-also"></a>Zobacz też  
 [Domeny aplikacji](http://msdn.microsoft.com/en-us/39e57d07-a740-4cd4-ae82-e119ea3856c1)



