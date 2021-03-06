---
title: N-warstwowe aplikacje do obsługi danych — omówienie
description: Przeczytaj Omówienie wielowarstwowej aplikacji do obsługi danych. Nazywane również aplikacjami rozproszonymi lub aplikacjami wielowarstwowymi, są to aplikacje danych rozdzielone na wiele warstw.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: overview
helpviewer_keywords:
- presentation tier
- middle tier
- data tier
- n-tier applications, about n-tier applications
ms.assetid: 1020581d-eaaa-41a2-aca4-bf4c212895f6
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- data-storage
ms.openlocfilehash: c4a25cc340216e3410e0ca4b6cfabec77a73662e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99866687"
---
# <a name="n-tier-data-applications-overview"></a>N-warstwowe aplikacje do obsługi danych — omówienie
*N-warstwowe* aplikacje danych to aplikacje danych, które są rozdzielone na wiele *warstw*. Nazywana również "aplikacjami rozproszonymi" i "aplikacjami wielowarstwowymi", aplikacje n-warstwowe dzielą przetwarzanie na dyskretne warstwy dystrybuowane między klientem a serwerem. Podczas tworzenia aplikacji uzyskujących dostęp do danych należy jednoznacznie odseparować różne warstwy tworzące aplikację.

Typowa aplikacja n-warstwowa zawiera warstwę prezentacji, warstwę środkową i warstwę danych. Najłatwiejszym sposobem rozdzielenia różnych warstw w n-warstwowej aplikacji jest utworzenie dyskretnych projektów dla każdej warstwy, która ma się znaleźć w aplikacji. Na przykład warstwą prezentacji może być aplikacja środowiska Windows Forms, podczas gdy logiką dostępu do danych może być biblioteka klas umieszczona w warstwie środkowej. Ponadto warstwa prezentacji może komunikować się z logiką dostępu do danych w warstwie środkowej za pomocą usługi, takiej jak usługa sieci Web. Rozdzielanie składników aplikacji w oddzielne warstwy ułatwia konserwację i zwiększa skalowalność aplikacji. Wynika to z możliwości łatwiejszego wprowadzania nowych technologii do poszczególnych warstw, bez konieczności zmiany projektu całego rozwiązania. Dodatkowo zazwyczaj n-warstwowe aplikacje przechowują wrażliwe informacje w środkowej warstwie, która utrzymuje izolację od warstwy prezentacji.

Program Visual Studio zawiera kilka funkcji, które ułatwiają deweloperom tworzenie aplikacji n-warstwowych:

- Zestaw danych zawiera właściwość **projektu DataSet** , która umożliwia rozdzielenie zestawu danych (warstwy jednostek danych) i TableAdapters (warstwa dostępu do danych) na projekty dyskretne.

- [Narzędzia LINQ to SQL w programie Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md) udostępniają ustawienia umożliwiające wygenerowanie elementów DataContext i Data w oddzielnych obszarach nazw. Takie rozwiązania pozwala logicznie rozdzielić warstwy dostępu do danych i jednostek danych.

- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) udostępnia <xref:System.Data.Linq.Table%601.Attach%2A> metodę, która umożliwia łączenie DataContext z różnych warstw w aplikacji. Aby uzyskać więcej informacji, zobacz [aplikacje N-warstwowe i zdalne za pomocą LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql).

## <a name="presentation-tier"></a>Warstwa prezentacji
*Warstwa prezentacji* to warstwa, w której użytkownicy współpracują z aplikacją. Często zawiera także dodatkową logikę aplikacji. Oto typowe składniki warstwy prezentacji:

- Składniki powiązania danych, takie jak <xref:System.Windows.Forms.BindingSource> i <xref:System.Windows.Forms.BindingNavigator>.

- Obiektowe reprezentacje danych, takie jak klasy jednostek [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) do użycia w warstwie prezentacji.

Warstwa prezentacji zwykle uzyskuje dostęp do warstwy środkowej przy użyciu odwołania do usługi (na przykład [Windows Communication Foundation usług i WCF Data Services w aplikacji Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) ). Warstwa prezentacji nie uzyskuje bezpośredniego dostępu do warstwy danych. Warstwa prezentacji komunikuje się z warstwą danych za pomocą składnika dostępu do danych w warstwie środkowej.

## <a name="middle-tier"></a>Warstwa środkowa
*Warstwa środkowa* jest warstwą, której warstwa prezentacji i warstwa danych używają do komunikacji ze sobą. Oto typowe składniki warstwy środkowej:

- Logika biznesowa, taka jak reguły biznesowe i mechanizmy sprawdzania poprawności danych.

- Składniki i logika dostępu do danych, w tym:

  - [TableAdapters](create-and-configure-tableadapters.md) oraz [dataadaptery i DataReader](/dotnet/framework/data/adonet/dataadapters-and-datareaders).

  - Obiektowe reprezentacje danych, takie jak klasy jednostek [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) .

  - Wspólne usługi aplikacji, takie jak uwierzytelnianie, autoryzacja i personalizacja.

Na ilustracji poniżej widać funkcje i technologie, które są dostępne w programie Visual Studio i mogą być umieszczone w środkowej warstwie aplikacji n-warstwowej.

![Warstwa środkowa komponentów warstwy środkowej ](../data-tools/media/ntiermid.png)

Warstwa środkowa zazwyczaj łączy się z warstwą danych przy użyciu połączenia danych. To połączenie danych jest zazwyczaj przechowywane w składniku dostępu do danych.

## <a name="data-tier"></a>Warstwa danych
*Warstwa danych* jest zasadniczo serwerem, w którym są przechowywane dane aplikacji (na przykład serwer z uruchomionym SQL Server).

Na ilustracji poniżej widać funkcje i technologie, które są dostępne w programie Visual Studio i mogą być umieszczone w warstwie danych aplikacji n-warstwowej.

![Warstwa danych składników warstwy danych ](../data-tools/media/ntierdatatier.png)

Warstwa danych nie może być dostępna bezpośrednio z klienta w warstwie prezentacji. Zamiast tego składnik dostępu do danych w warstwie środkowej obsługuje komunikację między warstwami prezentacji i danych.

## <a name="help-for-n-tier-development"></a>Pomoc dla tworzenia aplikacji n-warstwowych
Poniższe tematy zawierają informacje dotyczące pracy z aplikacjami n-warstwowymi:

[Rozdzielanie zestawów danych i adapterów TableAdapter do różnych projektów](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)

[Przewodnik: Tworzenie wielowarstwowej aplikacji danych](../data-tools/walkthrough-creating-an-n-tier-data-application.md)

[Aplikacje N-warstwowe i zdalne z LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)

## <a name="see-also"></a>Zobacz też

- [Przewodnik: Tworzenie wielowarstwowej aplikacji danych](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [Aktualizacja hierarchiczna](../data-tools/hierarchical-update.md)
- [Narzędzia zestawów danych w programie Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
- [Uzyskiwanie dostępu do danych w programie Visual Studio](../data-tools/accessing-data-in-visual-studio.md)
