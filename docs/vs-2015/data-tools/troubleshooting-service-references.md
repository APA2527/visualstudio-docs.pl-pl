---
title: Rozwiązywanie problemów z odwołaniami usługi | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- msvse_wcf.Err.ReferenceGroup_NamespaceConflictsOther
- msvse_wcf.Err.AddSvcRefDlg_NothingSelectedOnGo
- msvse_wcf.Err.ErrorOnOK
- msvse_wcf.cfg.ConfigurationErrorsException
helpviewer_keywords:
- service references [Visual Studio], troubleshooting
- WCF services, troubleshooting
ms.assetid: 3b531120-1325-4734-90c6-6e6113bd12ac
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 696c6f2a0e738d965b5992e3df52a77831ab27a0
ms.sourcegitcommit: 71218ffc33da325cc1b886f69ff2ca50d44f5f33
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2018
ms.locfileid: "48880893"
---
# <a name="troubleshooting-service-references"></a>Rozwiązywanie problemów z odwołaniami usługi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Rozwiązywanie problemów z odwołaniami usługi](https://docs.microsoft.com/visualstudio/data-tools/troubleshooting-service-references).

Ten temat zawiera listę typowych problemów, które mogą wystąpić podczas pracy z [!INCLUDE[vsindigo](../includes/vsindigo-md.md)] lub [!INCLUDE[ssAstoria](../includes/ssastoria-md.md)] przywoływane w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].

## <a name="error-returning-data-from-a-service"></a>Wystąpił błąd podczas zwracania danych z usługi
 Po powrocie `DataSet` lub `DataTable` z usługi, może pojawić się wyjątek "przydział maksymalny rozmiar dla komunikatów przychodzących został przekroczony". Domyślnie `MaxReceivedMessageSize` właściwość niektóre powiązania jest ustawiony na stosunkowo małej wartości, aby ograniczyć narażenie na ataki typu "odmowa usługi". Można zwiększyć tę wartość, aby zapobiec wyjątku.

 Aby naprawić ten błąd:

1.  W **Eksploratora rozwiązań**, kliknij dwukrotnie plik app.config, aby go otworzyć.

2.  Znajdź `MaxReceivedMessageSize` właściwości i zmień ją na większą wartość.

## <a name="cannot-find-a-service-in-my-solution"></a>Nie można odnaleźć usługi w Moje rozwiązanie
 Po kliknięciu **odnajdź** znajdujący się w **Dodawanie odwołań do usług** okno dialogowe, co najmniej jeden projekt biblioteki usługi WCF w rozwiązaniu nie są wyświetlane na liście usług. Może to występować, jeśli biblioteka usług został dodany do rozwiązania, ale jeszcze nie został skompilowany.

 Aby naprawić ten błąd:

-   W **Eksploratora rozwiązań**, kliknij prawym przyciskiem myszy projekt biblioteki usługi WCF i kliknij przycisk **kompilacji**.

## <a name="error-accessing-a-service-over-a-remote-desktop"></a>Błąd podczas uzyskiwania dostępu do usługi za pośrednictwem pulpitu zdalnego
 Gdy użytkownik uzyskuje dostęp do usługi WCF hostowanej w sieci Web za pośrednictwem połączenia pulpitu zdalnego i użytkownik nie ma uprawnienia administracyjne, zostanie użyte uwierzytelnianie NTLM. Jeśli użytkownik nie ma uprawnienia administracyjne, użytkownik może zostać wyświetlony następujący komunikat o błędzie: "żądanie HTTP nie ma autoryzacji przez schemat uwierzytelniania klienta"Anonymous". Nagłówek uwierzytelnienia otrzymany z serwera była "NTLM"."

 Aby naprawić ten błąd:

1.  Projekt witryny sieci Web otwórz **właściwości** stron.

2.  Na **opcje uruchamiania** kartę, usuń zaznaczenie **uwierzytelniania NTLM** pole wyboru.

    > [!NOTE]
    > Należy wyłączyć uwierzytelnianie NTLM tylko w przypadku witryn sieci Web, zawierające wyłącznie usługi WCF. Zabezpieczenia usług WCF odbywa się za pośrednictwem konfiguracji w pliku web.config. To sprawia, że uwierzytelnianie NTLM niepotrzebne.

## <a name="access-level-for-generated-classes-setting-has-no-effect"></a>Poziom dostępu do wygenerowanych klas ustawienie nie ma wpływu
 Ustawienie **poziom do wygenerowanych klas dostępu** opcji **Konfigurowanie odwołania do usług** okno dialogowe **wewnętrzne** lub **Friend** może czasem nie działać. Nawet jeśli opcja jest wyświetlana w oknie dialogowym, wynikowa klasy obsługi zostanie wygenerowany z poziomem dostępu `Public`.

 Jest to znane ograniczenie określonych typów, takich jak zserializowanym przy użyciu <xref:System.Xml.Serialization.XmlSerializer>.

## <a name="error-debugging-service-code"></a>Błąd podczas debugowania kodu usługi
 W przypadku wkroczyć do kodu dla usługi WCF z poziomu kodu klienta, może pojawić się błąd związany Brak symboli. Taka sytuacja może wystąpić, gdy usługi, które było częścią rozwiązania został przeniesiony lub usunięty z rozwiązania.

 Po dodaniu odwołania do usługi WCF, która jest częścią bieżącego rozwiązania, między projektami usługi i projekt klienta usługi zostanie dodana zależność jawną kompilację. Gwarantuje to, czy klient zawsze ma dostęp do plików binarnych usługi aktualne, który jest szczególnie ważne w przypadku debugowania scenariuszy, takich jak przechodzenie z poziomu kodu klienta do kodu usługi.

 Jeśli projekt usługi zostanie usunięty z rozwiązania, zostaje unieważniony tę zależność jawną kompilację. Programu Visual Studio może nie jest już zagwarantować, że zostanie ponownie skompilowany projekt usługi w razie.

 Aby naprawić ten błąd, należy ręcznie ponownie skompilować projekt usługi:

1.  Na **narzędzia** menu, kliknij przycisk **opcje**.

2.  W **opcje** okna dialogowego rozwiń **projekty i rozwiązania**, a następnie wybierz pozycję **ogólne**.

3.  Upewnij się, że **Pokaż zaawansowane konfiguracje kompilacji** pole wyboru jest zaznaczone, a następnie kliknij przycisk **OK**.

4.  Załaduj projekt usługi WCF. Aby uzyskać więcej informacji, zobacz [NIB jak: tworzenie rozwiązań dotyczących wielu projektów](http://msdn.microsoft.com/en-us/02ecd6dd-0114-46fe-b335-ba9c5e3020d6).

5.  W **programu Configuration Manager** okno dialogowe, zestaw **Konfiguracja rozwiązania aktywnego** do **debugowania**. Aby uzyskać więcej informacji, zobacz [porady: tworzenie i edytowanie konfiguracji](../ide/how-to-create-and-edit-configurations.md).

6.  W **Eksploratora rozwiązań**, wybierz projekt usługi WCF.

7.  Na **kompilacji** menu, kliknij przycisk **odbudować** Aby ponownie skompilować projekt usługi WCF.

## <a name="wcf-data-services-do-not-display-in-the-browser"></a>Usługi danych WCF nie są wyświetlane w przeglądarce
 Podczas próby wyświetlenia Reprezentacja XML danych w [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)], Internet Explorer mogą błędnie interpretuje dane jako źródła danych RSS. Należy się upewnić, że opcja wyświetlania źródeł danych RSS jest wyłączona.

 Aby naprawić ten błąd, należy wyłączyć źródła danych RSS:

1.  W programie Internet Explorer na **narzędzia** menu, kliknij przycisk **Opcje internetowe**.

2.  Na **zawartości** na karcie **źródła** kliknij **ustawienia**.

3.  W **ustawienia źródła danych** okno dialogowe wyczyść **Włączanie źródła danych w widoku do czytania** pole wyboru, a następnie kliknij przycisk **OK**.

4.  Kliknij przycisk **OK** zamknąć **Opcje internetowe** okno dialogowe.

## <a name="see-also"></a>Zobacz także

- [Usługi Windows Communication Foundation i usługi danych WCF w programie Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)