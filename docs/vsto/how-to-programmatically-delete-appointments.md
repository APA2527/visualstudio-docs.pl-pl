---
title: 'Instrukcje: programowe usuwanie terminów'
description: Dowiedz się, jak można programowo usunąć apppointments w programie Microsoft Outlook. Ten przykład powoduje usunięcie jednego wystąpienia terminu cyklicznego.
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- calendars [Office development in Visual Studio], deleting appointments
- deleting appointments
- appointments [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 56bd9876fa24610412d66e71800a24b413dac576
ms.sourcegitcommit: 4bd2b770e60965fc0843fc25318a7e1b46137875
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2020
ms.locfileid: "97526799"
---
# <a name="how-to-programmatically-delete-appointments"></a>Instrukcje: programowe usuwanie terminów
  Ten przykład powoduje usunięcie jednego wystąpienia terminu cyklicznego. W przykładzie założono, że wystąpienie cyklicznego terminu występuje w dniu 28 czerwca 2006, o 08:00.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Przykład
 [!code-vb[Trin_Outlook_RL_DeleteAppointment#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_RL_DeleteAppointment/thisaddin.vb#1)]
 [!code-csharp[Trin_Outlook_RL_DeleteAppointment#1](../vsto/codesnippet/CSharp/Trin_Outlook_RL_DeleteAppointment/thisaddin.cs#1)]

## <a name="see-also"></a>Zobacz także
- [Pracuj z elementami kalendarza](../vsto/working-with-calendar-items.md)
- [Wprowadzenie do programowania dodatków narzędzi VSTO](../vsto/getting-started-programming-vsto-add-ins.md)
- [Instrukcje: Programowane tworzenie terminów](../vsto/how-to-programmatically-create-appointments.md)
- [Instrukcje: programowe tworzenie kalendarza niestandardowego](../vsto/how-to-programmatically-create-a-custom-calendar.md)
- [Instrukcje: programowe tworzenie żądania spotkania](../vsto/how-to-programmatically-create-a-meeting-request.md)
