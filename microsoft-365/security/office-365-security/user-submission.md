---
title: 使用者提交原則
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以瞭解如何設定信箱，以收集使用者所報告的垃圾郵件和網路釣魚電子郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d86c79f0f0ab74d1dfbb88e7803f4ee4d691ea73
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501175"
---
# <a name="user-submissions-policy"></a>使用者提交原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在使用 Exchange Online 信箱的 Microsoft 365 組織中，您可以指定信箱以接收使用者報告為惡意或非惡意的郵件。 當使用者使用各種報告選項送出郵件時，您可以使用此信箱來截取郵件 (只) 或接收郵件副本 (傳送至自訂信箱和 Microsoft) 。 這項功能可搭配下列郵件報告選項使用：

- [報告訊息增益集](enable-the-report-message-add-in.md)

- [報表網路釣魚增益集](enable-the-report-phish-add-in.md)

- [Outlook 網頁版中 (的內建報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) （以前稱為 Outlook web App）) 

- [Outlook 中用於 iOS 和 Android 的內建報告](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > 如果 [在網頁上的 outlook 中已停用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)報告，讓使用者在這裡提交，將會覆寫該設定，讓使用者再次在 Outlook 的 outlook 中報告郵件。

您也可以設定協力廠商郵件報告工具，將郵件轉寄至您指定的信箱。

將使用者報告的郵件傳送至自訂信箱，而不直接傳送至 Microsoft，可讓您的系統管理員選擇性地使用系統 [管理員提交](admin-submission.md)將郵件報告給 Microsoft。

## <a name="custom-mailbox-prerequisites"></a>自訂信箱必要條件

使用下列文章來設定必要的必要條件，讓使用者報告的郵件進入您的自訂信箱：

- 建立 exchange 郵件流程規則以設定垃圾郵件信賴等級，以略過自訂信箱上的垃圾郵件篩選。 請參閱 [使用 EAC 建立郵件流程規則，將郵件的 scl](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 設定為將 scl 設定為 **-1**。

- 關閉自訂信箱中的惡意程式碼的掃描附件。 使用 [在 Office 365 中設定安全附件](set-up-safe-attachments-policies.md)原則，以建立安全附件原則，**關閉****安全附件未知惡意程式碼回應**。

- 在自訂信箱的郵件上關閉 URL 掃描。 使用 [在 Office 365 中的 [設定安全連結原則](set-up-safe-links-policies.md) ] 來建立安全連結原則，設定為 [關閉] 時，請選取 [ **關閉** ]，以 **在郵件中選取未知的可能惡意 URLs 動作**。

- 建立反惡意程式碼原則，關閉惡意程式碼零小時自動清除。 請參閱 [使用安全性 & 規範中心建立反惡意程式碼原則](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，將 **惡意軟體設定為零小時自動清除** **。**

- 建立垃圾郵件篩選原則，以停用自訂信箱中垃圾郵件和網路釣魚的零小時自動清除 (ZAP) 。 請參閱 [使用安全性 & 規範中心建立反垃圾郵件原則](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，並清除 **垃圾郵件 Zap** 和 **網路釣魚 zap** 的 **On** 核取方塊。

- 停用自訂信箱中的垃圾郵件規則。 使用 [ [設定 Exchange Online 信箱上的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md) ] 以停用垃圾郵件規則。 停用之後，EOP 無法根據垃圾郵件篩選判定動作將郵件移至垃圾郵件資料夾。 **將郵件移至垃圾郵件資料夾** 或信箱上的安全清單集合。

在您確認您的信箱符合所有適用的先決條件後，請 [使用安全性 & 合規性中心，設定本文中的使用者提交信箱](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) () 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [ **使用者報送** ] 頁面，請使用 <https://protection.office.com/userSubmissionsReportMessage> 。

- 若要修改使用者提交的設定，您必須是下列其中一個角色群組的成員：

  - **組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **組織管理**。

- 您需要存取 Exchange Online PowerShell。 如果您嘗試使用的帳戶無法存取 Exchange Online PowerShell，當您指定提交信箱時，您會收到如下的錯誤訊息：

  > 在您的網域中指定電子郵件地址

  如需啟用或停用 Exchange Online PowerShell 存取權的詳細資訊，請參閱下列主題：

  - [啟用或停用存取 Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Exchange Online 中的用戶端存取規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>使用安全性 & 規範中心設定使用者提交信箱

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**] \> **使用者報送**。

2. 在出現的 [ **使用者提交** ] 頁面中，選取下列其中一個選項：

      1. **啟用 (建議) 的 Outlook 報告郵件功能**：若您使用報表訊息增益集、網頁型 outlook 中的報表網路釣魚增益集或內建報告，請選取此選項，然後設定下列設定：

    - **自訂使用者確認訊息**：按一下此連結。 在出現的 [ **自訂確認訊息** ] 浮出視窗中，設定下列設定：

        - **提交之前**：在 [ **標題** ] 和 [ **確認訊息** ] 方塊中，輸入使用者在使用報告訊息增益集或報告網路釣魚增益集報告郵件之前看到的描述性文字。 您可以使用變數% type%，以包含提交類型 (垃圾郵件、非垃圾郵件、網路釣魚網路等等 ) 。

            如所述，如果您選取將報告的郵件傳送給 Microsoft 的選項，下列文字也會新增至通知：

        > 您的電子郵件會向 Microsoft 提交，以進行分析。 有些電子郵件可能包含個人或機密資訊。

        - **提交後**：按一下 [ ![ 展開圖示] ](../../media/scc-expand-icon.png) 。 在 [ **標題** ] 和 [ **確認訊息** ] 方塊中，輸入使用者在使用報告訊息增益集或報告網路釣魚增益集報告訊息之後所看到的描述性文字。 您可以使用變數% type% 來包含提交類型。

      完成後，請按一下 **[儲存]**。 若要清除這些值，請按一下 [**使用者報送**] 頁面上的 [**還原** 回來]。
    
    - **自訂最終使用者報告選項**：按一下此連結。 在出現的 [ **自訂最終使用者報告選項** ] 浮出控制項中，輸入垃圾郵件報告選項的描述性文字。 
在 **報告訊息時顯示** 的 [選項] 底下，在下列選項中至少選取一個選項：
        - **傳送報告之前向我提問**
        - **自動傳送報告**
        -  **從不傳送報告** \
   完成後，請按一下 **[儲存]**。
              - **將報告的郵件傳送至**：進行下列其中一項選擇：
              - **Microsoft (建議)**：不使用使用者提交信箱 (所有報告的郵件都移至 Microsoft) 。
              - **Microsoft 和自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。 不允許通訊群組。 使用者送出會同時移至 Microsoft 進行分析，以及您的系統管理員或安全性作業小組的自訂信箱進行分析。
              - **僅限自訂信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。 不允許通訊群組。 如果您只想要將郵件移至系統管理員或安全性作業小組進行分析，請使用此選項。 除非系統管理員自行轉寄，否則郵件不會移至 Microsoft。

        > [!NOTE]
        > 美國政府組織 (GCC、GCC 和 DoD) 只能設定 **自訂信箱**。 其他兩個選項會停用。

        > [!NOTE]
        > 如果組織已設定為僅傳送至自訂信箱，將不會傳送報告的郵件以進行重新掃描，而且使用者報告的郵件入口網站將永遠會是空的。

      完成後，請按一下 [ **確認**]。

      > [!CAUTION]
      > 如果您已在使用 Outlook 的網頁信箱原則上使用 Outlook 在 [outlook 中停用 [垃圾郵件報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) ]，但您設定上述任一設定將郵件報告給 microsoft，使用者就可以使用報告訊息增益集或報告網路釣魚增益集，在網頁型 outlook 中向 microsoft 報告郵件。


    1. **停用 Outlook 的報告郵件功能**：若您使用協力廠商報告工具（而非報告郵件增益集），請在網頁型 Outlook 中使用協力廠商的報表工具，或內建的報告，然後設定下列設定：

          選取 [ **使用此自訂信箱以接收使用者報告的提交**]。 在出現的方塊中，輸入已存在於 Office 365 的現有信箱的電子郵件地址。 這必須是 Exchange Online 中可接收電子郵件的現有信箱。

          完成後，請按一下 [ **確認**]。

## <a name="message-submission-format"></a>郵件提交格式

傳送至自訂信箱的郵件必須遵循特定提交郵件格式。 提交的主旨 (信封標題) 應該使用下列格式：

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

其中，SafetyAPIAction 是下列其中一個整數值：

- 1：垃圾郵件
- 2：非垃圾郵件
- 3：網路釣魚

在下列範例中：

- 將郵件報告為網路釣魚。
- 網路消息識別碼是49871234-6dc6-43e8-abcd-08d797f20abe。
- 寄件者 IP 為167.220.232.101。
- [寄件者] 位址為 test@contoso.com。
- 郵件的主旨行是「測試網路釣魚提交」

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

不遵循此格式的郵件將無法在提交入口網站中正確顯示。
