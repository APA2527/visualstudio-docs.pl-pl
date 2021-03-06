---
title: Programowe Znajdowanie adresu e-mail w kontaktach
description: Dowiedz się, jak za pomocą programu Visual Studio programowo znaleźć adres e-mail w kontaktach programu Microsoft Outlook.
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- e-mail [Office development in Visual Studio], searching
- contacts [Office development in Visual Studio], searching
- searching contacts
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 43baafee82cf38dfd346ebe50e9b348857a3fdc4
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99920458"
---
# <a name="how-to-programmatically-search-for-an-email-address-in-contacts"></a>Instrukcje: programowe wyszukiwanie adresu e-mail w kontaktach
  Ten przykład przeszukuje folder Contact dla kontaktów, które mają nazwę domeny **example.com** w swoich adresach e-mail.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Przykład
 [!code-csharp[Trin_OL_SearchEmail#1](../vsto/codesnippet/CSharp/Trin_OL_SearchEmail/thisaddin.cs#1)]

## <a name="compile-the-code"></a>Kompiluj kod
 Ten przykład wymaga:

- Kontakty, które mają nazwę domeny **example.com** w swoich adresach e-mail (na przykład `somebody@example.com` ), i które mają imiona i nazwiska.

## <a name="see-also"></a>Zobacz też
- [Pracuj z elementami kontaktów](../vsto/working-with-contact-items.md)
- [Instrukcje: Programowane wysyłanie wiadomości e-mail](../vsto/how-to-programmatically-send-e-mail-programmatically.md)
- [Instrukcje: programowe uzyskiwanie dostępu do kontaktów programu Outlook](../vsto/how-to-programmatically-access-outlook-contacts.md)
- [Instrukcje: programowe Dodawanie wpisu do kontaktów programu Outlook](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md)
