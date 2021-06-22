---
title: 使用者報告的郵件設定
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
ms.openlocfilehash: e990721dacaa373b6782ee916f051e4753f3edfd
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055118"
---
# <a name="user-reported-message-settings"></a>使用者報告的郵件設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 具有 Exchange Online 信箱的組織中，您可以指定信箱以接收使用者報告為惡意或非惡意的郵件。 當使用者使用各種報告選項報告郵件時，您可以使用此信箱來截取郵件 (只) 或接收郵件副本 (傳送至自訂信箱和 Microsoft) 。 這項功能可搭配下列郵件報告選項使用：

- [報告訊息增益集](enable-the-report-message-add-in.md)
- [報表網路釣魚增益集](enable-the-report-phish-add-in.md)
- [協力廠商報表工具](#third-party-reporting-tools)

將使用者報告的郵件傳送至自訂信箱，而不直接傳送至 Microsoft，可讓您的系統管理員選擇性地使用系統 [管理員提交](admin-submission.md)將郵件報告給 Microsoft。 這些設定以前稱為使用者提交原則。

  > [!NOTE]
  > 如果[Outlook 網頁版中已停用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)報告，則在這裡啟用使用者報告的訊息將會覆寫該設定，並且讓使用者能夠在 Outlook 網頁版中重新報告郵件。

## <a name="custom-mailbox-prerequisites"></a>自訂信箱必要條件

使用下列文章來設定必要的必要條件，讓使用者報告的郵件進入您的自訂信箱：

- 建立 exchange 郵件流程規則以設定垃圾郵件信賴等級，以略過自訂信箱上的垃圾郵件篩選。 請參閱 [使用 EAC 建立郵件流程規則，](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 設定郵件的 scl 設定為將 scl 設定為 **略過垃圾郵件篩選**。

- [建立保管庫附件原則](set-up-safe-attachments-policies.md)，其中包含關閉保管庫附件掃描的自訂信箱 (**保管庫附件未知惡意程式碼回應** 區段 \> **off**) 。

- [建立保管庫連結原則](set-up-safe-links-policies.md)，其中包含關閉保管庫連結掃描的自訂信箱 (**選取 [郵件中未知潛在惡意 URLs 的動作**] 區段中的 \> ) 。

- 建立包含自訂信箱的 [反惡意程式碼原則](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)，其中會關閉惡意程式碼的零小時自動清除 (ZAP)  (**保護設定**] 區段 \> 。) 未選取惡意程式碼的 **自動清除** 功能。

- [建立反垃圾郵件原則](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) ，其中包含的自訂信箱，針對網路釣魚使用的垃圾郵件和 zap 會關閉 (**0 小時自動清除** 區段 \> **已啟用零小時自動清除** ]。 (不會) 選取 ZAP) 。

- 停用自訂信箱中的垃圾郵件規則。 使用 [[設定 Exchange Online 信箱上的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)] 以停用垃圾郵件規則。 停用之後，EOP 無法根據垃圾郵件篩選判定動作將郵件移至 [垃圾郵件] 資料夾。 **將郵件移至垃圾郵件資料夾** 或信箱上的安全清單集合。

在您確認您的信箱符合所有適用的先決條件後，您可以使用本文中的程式來設定使用者認可信箱。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您於 <https://security.microsoft.com/> 開啟 Microsoft 365 Defender 入口網站。 若要直接移至 [ **提交** ] 頁面，請使用 <https://security.microsoft.com/reportsubmission> 。

- 若要修改使用者提交的設定，您必須是下列其中一個角色群組的成員：

  - [Microsoft 365 Defender 入口網站](permissions-in-the-security-and-compliance-center.md)中的 **組織管理** 或 **安全性管理員**。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)中的 **組織管理**。

- 您需要 Exchange Online PowerShell 的存取權。 如果您嘗試使用的帳戶不具備 Exchange Online PowerShell 的存取權，當您指定提交信箱時，您會收到如下的錯誤訊息：

  > 在您的網域中指定電子郵件地址

  如需啟用或停用 Exchange Online PowerShell 存取權的詳細資訊，請參閱下列主題：

  - [啟用或停用 Exchange Online PowerShell 的存取權](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Exchange Online 中的用戶端存取規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>使用 Microsoft 365 Defender 入口網站設定使用者提交信箱

1. 在 Microsoft 365 Defender 入口網站中，移至 [**原則] & 規則** \> **威脅** 原則 \> **其他**] 區段 \> **使用者報告的郵件設定** \> **使用者提交**。

2. 在 [**使用者** 送出] 頁面上，您所看到的內容取決於 [ **Microsoft Outlook 報告**] [訊息] 按鈕設定為 [**關閉**] 或 [**開啟**]。

   - **Microsoft Outlook 報告訊息按鈕** \>**開啟** ![開啟切換 ](../../media/scc-toggle-on.png) ：如果您使用報告訊息增益集、報告中 Outlook 網頁版的報告網路釣魚增益集或內建報告，請選取這個選項，然後設定下列設定：
     - **將報告的郵件傳送至**：選取下列其中一個選項：
       - **Microsoft**：不使用使用者送出信箱 (所有報告的郵件都會移至 Microsoft) 。
       - **Microsoft 和我的組織信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。 不允許通訊群組。 使用者送出會同時移至 Microsoft 進行分析，以及您的系統管理員或安全性作業小組的自訂信箱進行分析。
       - **我的組織信箱**：在出現的方塊中，輸入現有 Exchange Online 信箱的電子郵件地址。 不允許通訊群組。 如果您只想要將郵件移至系統管理員或安全性作業小組進行分析，請使用此選項。 除非系統管理員自行轉寄，否則郵件不會移至 Microsoft。

          > [!IMPORTANT]
          >
          > 美國政府組織 (GCC、GCC 高及 DoD) 只能設定 **我的組織的信箱**。 其他兩個選項會停用。
          >
          > 如果組織已設定為僅傳送至自訂信箱，將不會傳送報告的郵件以進行重新掃描，而且使用者報告的郵件入口網站將永遠會是空的。

       不論您選取要 **傳送報告的郵件** 值，都可以使用下列設定：

       - **讓使用者選擇是否要將其郵件報告給 Microsoft**
       - **選取 [使用者可使用的報告選項** ] 區段：請至少選取下列選項中的一個：
         - **傳送郵件之前向我提問**
         - **無條件報告訊息**
         - **從不報告訊息**

          > [!CAUTION]
          > 如果您已在使用 Outlook 網頁版信箱原則[的 Outlook 網頁版中停用垃圾郵件報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)，但您設定了先前的任何設定將郵件報告給 microsoft，使用者就可以使用報告訊息增益集或報告網路釣魚增益集，在 Outlook 網頁版中向 microsoft 報告郵件。

     - **使用者報告經驗區段**
       - 在 [**報告**] 索引卷 **標** 中：在 [標題] 和 [**訊息**] 方塊中，輸入使用者在使用報告郵件增益集或報表網路釣魚增益集報告郵件之前看到的描述性文字。 您可以使用變數% type%，以包含提交類型 (垃圾郵件、非垃圾郵件、網路釣魚網路等等 ) 。
       - 在 [**報告**] 索引卷 **標** 中：在 [標題] 和 [**確認訊息**] 方塊中，輸入使用者在使用報告訊息增益集或報表網路釣魚增益集報告訊息之後所看到的描述性文字。 您可以使用變數% type% 來包含提交類型。

       如頁面上所示，如果您選取將報告的郵件傳送給 Microsoft 的選項，下列文字也會新增至通知：

          > 您的電子郵件會向 Microsoft 提交，以進行分析。 有些電子郵件可能包含個人或機密資訊。

   - **Microsoft Outlook 報告訊息按鈕** \>**關閉** ![關閉切換 ](../../media/scc-toggle-off.png) ：如果您使用協力廠商報告工具，而不是報告郵件增益集、報告網路釣魚增益集或 Outlook 網頁版中內建的報告，請選取這個選項，然後設定下列設定：
     - 選取 [ **使用此自訂信箱以接收使用者報告的提交**]。 在出現的方塊中，輸入可接收電子郵件之現有 Exchange Online 信箱的電子郵件地址。

   完成後，請按一下 [ **確認**]。 若要清除這些值，請按一下 [**還原**]

## <a name="third-party-reporting-tools"></a>協力廠商報表工具

您可以設定協力廠商郵件報告工具，將報告的郵件傳送至自訂信箱。 為此，您可以將 [ **Microsoft Outlook Report Message 按鈕**] 設定為 [**關閉**]，然後將 [**我的組織] 信箱** 設定為您所選擇的 Office 365 信箱。

唯一的需求是原始郵件會包含為。.EML 或。MSG 附件 (在傳送至自訂信箱的郵件中) 壓縮， (不要只將原始郵件轉寄至自訂信箱) 。

郵件格式設定需求會在下一節中說明。 格式設定是選用的，但如果它不遵循指定的格式，則會永遠以網路釣魚提交報告。

## <a name="message-submission-format"></a>郵件提交格式

若要正確識別原始附加郵件，傳送至自訂信箱的郵件需要特定格式。 如果郵件未使用此格式，則原始附加郵件會永遠識別為網路釣魚提交。

為了正確識別原始附加郵件，傳送至自訂信箱的郵件必須針對主旨 (信封標題) 使用下列語法：

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

其中，SafetyAPIAction 是下列其中一個整數值：

- 1：垃圾郵件
- 2：非垃圾郵件
- 3：網路釣魚

本範例會使用下列值：

- 將郵件報告為網路釣魚。
- 網路消息識別碼是49871234-6dc6-43e8-abcd-08d797f20abe。
- 寄件者 IP 為167.220.232.101。
- [寄件者] 位址為 test@contoso.com。
- 郵件的主旨行是「測試網路釣魚提交」

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

未遵循此格式的郵件將無法在提交入口網站中正確顯示。
