---
title: 'Instrukcje: pokazywanie błędów interfejsu użytkownika dodatku'
description: Dowiedz się, jak za pomocą programu Visual Studio programowo pokazać błędy interfejsu użytkownika dodatku VTSO w aplikacjach Microsoft Office.
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], user interface errors
- errors [Office development in Visual Studio], user interface errors
- user interfaces [Office development in Visual Studio], errors
- application-level add-ins [Office development in Visual Studio], user interface errors
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 29e07e49d901b44b534d9d274e5535be663e97ef
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99927681"
---
# <a name="how-to-show-add-in-user-interface-errors"></a>Instrukcje: pokazywanie błędów interfejsu użytkownika dodatku
  Domyślnie, jeśli dodatek narzędzi VSTO próbuje manipulować interfejsem użytkownika Microsoft Office i nie powiedzie się, zostanie wyświetlony komunikat o błędzie. Można jednak skonfigurować aplikacje Microsoft Office do wyświetlania komunikatów o błędach, które odnoszą się do interfejsu użytkownika. Za pomocą tych komunikatów można określić, dlaczego nie pojawia się wstążka niestandardowa lub dlaczego wyświetlana jest wstążka, ale nie są wyświetlane żadne kontrolki.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

## <a name="to-show-vsto-add-in-user-interface-errors"></a>Aby wyświetlić błędy interfejsu użytkownika dodatku VSTO

1. Uruchom aplikację.

2. Kliknij kartę **plik** .

3. Kliknij pozycję **Opcje**.

4. W okienku kategorie kliknij pozycję **Zaawansowane**.

5. W okienku szczegółów wybierz pozycję **Pokaż błędy interfejsu użytkownika dodatku VSTO**, a następnie kliknij przycisk **OK**.

    > [!NOTE]
    > W przypadku programu Outlook pole wyboru **Pokaż błędy interfejsu użytkownika dodatku VSTO** znajduje się w sekcji **deweloper** okienka szczegółów. W przypadku innych aplikacji pole wyboru znajduje się w sekcji **Ogólne** okienka szczegółów.

## <a name="see-also"></a>Zobacz też
- [Dostosowywanie interfejsu użytkownika pakietu Office](../vsto/office-ui-customization.md)
- [Tworzenie regionów formularzy programu Outlook](../vsto/creating-outlook-form-regions.md)
- [Omówienie wstążki](../vsto/ribbon-overview.md)
- [Przegląd okienka Akcje](../vsto/actions-pane-overview.md)
