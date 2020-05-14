---
title: 為使用者提交的垃圾郵件和網路釣魚郵件指定信箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何設定信箱，以收集使用者所報告的垃圾郵件和網路釣魚電子郵件。
ms.openlocfilehash: 38fa16b5270273813b4549b0c3c9baaa1b05b098
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224550"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>在 Exchange Online 中指定使用者提交垃圾郵件和網路釣魚郵件的信箱

在使用 Exchange Online 信箱的 Microsoft 365 組織中，您可以指定信箱以接收使用者報告為惡意或非惡意的郵件。 當使用者使用各種報告選項提交郵件時，您可以使用此信箱來攔截郵件（只傳送至自訂信箱），或接收郵件的副本（傳送至自訂信箱和 Microsoft）。 這項功能可搭配下列郵件報告選項使用：

- [報告訊息增益集](enable-the-report-message-add-in.md)

- [Outlook 網頁版中的內建報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)（以前稱為 Outlook web App）

  > [!NOTE]
  > 如果[在網頁上的 outlook 中已停用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)報告，讓使用者在這裡提交，將會覆寫該設定，讓使用者再次在 Outlook 的 outlook 中報告郵件。

您也可以設定協力廠商郵件報告工具，將郵件轉寄至您指定的信箱。

將使用者報告的郵件傳送至自訂信箱，而不直接傳送至 Microsoft，可讓您的系統管理員選擇性地使用系統[管理員提交](admin-submission.md)將郵件報告給 Microsoft。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [**使用者報送**] 頁面，請使用 <https://protection.office.com/userSubmissionsReportMessage> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連線至獨立 EOP PowerShell，請參閱[connect To Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派權限，才能執行這些程序。 若要設定使用者提交的信箱，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。 如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>使用安全性 & 規範中心設定使用者提交信箱

1. 在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> **原則**] \> **使用者報送**。

2. 在出現的 [**使用者提交**] 頁面中，選取下列其中一個選項：

   - **啟用 outlook 的報告郵件功能（建議）**：如果您在網頁型 outlook 中使用報表訊息增益集或內建報告，請選取此選項，然後設定下列設定：

     - **自訂使用者確認訊息**：按一下此連結。 在出現的 [**自訂確認訊息**] 浮出視窗中，設定下列設定：

       - **提交之前**：在 [**標題**] 和 [**確認訊息**] 方塊中，輸入使用者在使用「報告郵件增益集」報告郵件之前看到的描述性文字。 您可以使用變數% type% 來包含提交類型（垃圾郵件、非垃圾郵件網路釣魚等等）。

         如前文所述，下列文字也會新增至通知：

         > 您的電子郵件會向 Microsoft 提交，以進行分析。 有些電子郵件可能包含個人或機密資訊。

       - **提交後**：按一下 [ ![ 展開圖示] ](../../media/scc-expand-icon.png) 。 在 [**標題**] 和 [**確認訊息**] 方塊中，輸入使用者在使用「報告訊息增益集」報告訊息之後所看到的描述性文字。 您可以使用變數% type% 來包含提交類型。

      完成後，按一下 [儲存]****。 若要清除這些值，請按一下 [**使用者報送**] 頁面上的 [**還原**回來]。

   - **將報告的郵件傳送至**：進行下列其中一項選擇：

     - **Microsoft （建議使用）**：不使用使用者提交信箱（所有報告的郵件都會移至 Microsoft）。

     - **Microsoft 和自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。 不允許通訊群組。

     - **自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。 不允許通訊群組。

     完成後，請按一下 [**確認**]。

     ![將報告的郵件傳送至 Microsoft 和自訂信箱](../../media/user-submission-enable-outlook-report-message.png)

   - **停用 Outlook 的報告郵件功能**：如果您使用協力廠商的報表工具，而不是在 web 上的 Outlook 中使用協力廠商的報表工具或內建的報表，請選取這個選項，然後設定下列設定：

     選取 [**使用此自訂信箱以接收使用者報告的提交**]。 在出現的方塊中，輸入現有信箱的電子郵件地址，或您要建立之信箱的電子郵件地址。

     完成後，請按一下 [**確認**]。

     ![使用協力廠商工具將報告的郵件傳送至自訂信箱](../../media/user-submission-disable-outlook-report-message.png)
