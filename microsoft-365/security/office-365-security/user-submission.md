---
title: 使用者提交原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以瞭解如何設定信箱，以收集使用者所報告的垃圾郵件和網路釣魚電子郵件。
ms.openlocfilehash: c4792958d1e59cefd8b56c05b5e159f50be80c8b
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600478"
---
# <a name="user-submissions-policy"></a>使用者提交原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 信箱的 Microsoft 365 組織中，您可以指定信箱以接收使用者報告為惡意或非惡意的郵件。 當使用者使用各種報告選項送出郵件時，您可以使用此信箱來截取郵件 (只) 或接收郵件副本 (傳送至自訂信箱和 Microsoft) 。 這項功能可搭配下列郵件報告選項使用：

- [報告訊息增益集](enable-the-report-message-add-in.md)

- [Outlook 網頁版中 (的內建報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) （以前稱為 Outlook web App）) 

- [Outlook 中用於 iOS 和 Android 的內建報告](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > 如果 [在網頁上的 outlook 中已停用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)報告，讓使用者在這裡提交，將會覆寫該設定，讓使用者再次在 Outlook 的 outlook 中報告郵件。

您也可以設定協力廠商郵件報告工具，將郵件轉寄至您指定的信箱。

將使用者報告的郵件傳送至自訂信箱，而不直接傳送至 Microsoft，可讓您的系統管理員選擇性地使用系統 [管理員提交](admin-submission.md)將郵件報告給 Microsoft。

## <a name="custom-mailbox-prerequisites"></a>自訂信箱必要條件

使用下列文章來設定必要的必要條件，讓使用者報告的郵件進入您的自訂信箱：

- 建立 exchange 郵件流程規則以設定垃圾郵件信賴等級，以略過自訂信箱上的垃圾郵件篩選。 請參閱 [使用 EAC 建立郵件流程規則，將郵件的 scl](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 設定為將 scl 設定為 **-1**。

- 關閉自訂信箱中的惡意程式碼的掃描附件。 使用[設定 Office 365 ATP 中的安全附件原則](set-up-atp-safe-attachments-policies.md)，以建立安全附件原則，**關閉****安全附件未知惡意程式碼回應**。

- 在自訂信箱的郵件上關閉 URL 掃描。 使用 [ [設定 Office 365 ATP 中的安全連結原則](set-up-atp-safe-links-policies.md) ] 以建立安全連結原則，設定為 [關閉] 時，請選取 [ **關閉** ]，以 **在郵件中選取未知的潛在惡意 URLs 動作**。

- 建立反惡意程式碼原則，關閉惡意程式碼零小時自動清除。 請參閱[使用安全性 & 規範中心建立反惡意程式碼原則](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，將**惡意軟體設定為零小時自動清除** **。**

- 建立垃圾郵件篩選原則，以停用自訂信箱中垃圾郵件和網路釣魚的零小時自動清除 (ZAP) 。 請參閱[使用安全性 & 規範中心建立反垃圾郵件原則](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，並清除**垃圾郵件 Zap**和**網路釣魚 zap**的**On**核取方塊。

- 停用自訂信箱中的垃圾郵件規則。 使用 [ [設定 Exchange Online 信箱上的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md) ] 以停用垃圾郵件規則。 停用之後，EOP 無法根據垃圾郵件篩選判定動作將郵件移至垃圾郵件資料夾。 **將郵件移至垃圾郵件資料夾** 或信箱上的安全清單集合。

在您確認您的信箱符合所有適用的先決條件後，請 [使用安全性 & 合規性中心，設定本文中的使用者提交信箱](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) () 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [ **使用者報送** ] 頁面，請使用 <https://protection.office.com/userSubmissionsReportMessage> 。

- 若要修改使用者提交的設定，您必須是下列其中一個角色群組的成員：

  - **組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的**組織管理**。

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>使用安全性 & 規範中心設定使用者提交信箱

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**] \> **使用者報送**。

2. 在出現的 [ **使用者提交** ] 頁面中，選取下列其中一個選項：

   1. **啟用 (建議) 的 Outlook 報告郵件功能 **：若您在網頁型 outlook 中使用報表訊息增益集或內建報告，請選取此選項，然後設定下列設定：

      - **自訂使用者確認訊息**：按一下此連結。 在出現的 [ **自訂確認訊息** ] 浮出視窗中，設定下列設定：

      - **提交之前**：在 [ **標題** ] 和 [ **確認訊息** ] 方塊中，輸入使用者在使用「報告郵件增益集」報告郵件之前看到的描述性文字。 您可以使用變數% type%，以包含提交類型 (垃圾郵件、非垃圾郵件、網路釣魚網路等等 ) 。

        如所述，如果您選取將報告的郵件傳送給 Microsoft 的選項，下列文字也會新增至通知：

        > 您的電子郵件會向 Microsoft 提交，以進行分析。 有些電子郵件可能包含個人或機密資訊。

      - **提交後**：按一下 [ ![ 展開圖示] ](../../media/scc-expand-icon.png) 。 在 [ **標題** ] 和 [ **確認訊息** ] 方塊中，輸入使用者在使用「報告訊息增益集」報告訊息之後所看到的描述性文字。 您可以使用變數% type% 來包含提交類型。

      完成後，按一下 [儲存]****。 若要清除這些值，請按一下 [**使用者報送**] 頁面上的 [**還原**回來]。

      - **將報告的郵件傳送至**：進行下列其中一項選擇：

        - **Microsoft (建議) **：不使用使用者提交信箱 (所有報告的郵件都移至 Microsoft) 。

        - **Microsoft 和自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。 不允許通訊群組。 使用者送出會同時移至 Microsoft 進行分析，以及您的系統管理員或安全性作業小組的自訂信箱進行分析。

        - **自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。 不允許通訊群組。 如果您只想要將郵件移至系統管理員或安全性作業小組進行分析，請使用此選項。 除非系統管理員自行轉寄，否則郵件不會移至 Microsoft。

        > [!NOTE]
        > 美國政府組織 (GCC、GCC 和 DoD) 只能設定 **自訂信箱**。 其他兩個選項會停用。 

      完成後，請按一下 [ **確認**]。

      > [!CAUTION]
      > 如果您已在 Outlook 網頁版 outlook 上使用 Outlook 來 [停用 outlook 中的垃圾郵件報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) ，但您設定上述任一設定將郵件報告給 microsoft，使用者就可以使用報告訊息增益集，在網頁型 outlook 中將郵件報告給 microsoft。

   - **停用 Outlook 的報告郵件功能**：如果您使用協力廠商的報表工具，而不是在 web 上的 Outlook 中使用協力廠商的報表工具或內建的報表，請選取這個選項，然後設定下列設定：

      選取 [ **使用此自訂信箱以接收使用者報告的提交**]。 在出現的方塊中，輸入已存在於 Office 365 的現有信箱的電子郵件地址。 這必須是 Exchange Online 中可接收電子郵件的現有信箱。

      完成後，請按一下 [ **確認**]。

## <a name="message-submission-format"></a>郵件提交格式

傳送至自訂信箱的郵件必須遵循特定提交郵件格式。 提交的主旨 (信封標題) 應該使用下列格式：

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

其中，SafetyAPIAction 是下列其中一個整數值：

- 1：垃圾郵件
- 2： NotJunk
- 3：網路釣魚

在下列範例中：

- 將郵件報告為網路釣魚。
- 網路消息識別碼是49871234-6dc6-43e8-abcd-08d797f20abe。
- 寄件者 IP 為167.220.232.101。
- [寄件者] 位址為 test@contoso.com。
- 郵件的主旨行是「測試網路釣魚提交」

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

不遵循此格式的郵件將無法在提交入口網站中正確顯示。
