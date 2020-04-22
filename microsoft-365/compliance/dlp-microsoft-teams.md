---
title: 資料遺失防護和 Microsoft 團隊
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 您現在可以將 DLP 原則套用至 Microsoft 團隊聊天和頻道。 請閱讀本文以深入瞭解其運作方式。
ms.openlocfilehash: 290e1e7a7c3fd395c1f7e1739b08eba64c8d2d8d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633052"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>資料遺失防護和 Microsoft 團隊

> [!NOTE]
> 針對已取得 Office 365 進階合規性授權的使用者，系統最近將資料外洩防護功能新增至 Microsoft Teams 聊天和頻道訊息，該功能可作為獨立選項提供，並包含在 Office 365 E5 和 Microsoft 365 E5 合規性中。 Office 365 和 Microsoft 365 E3 包含 DLP protection，供 SharePoint 線上、OneDrive 和 Exchange Online。 這也包括透過團隊共用的檔案，因為小組會使用 SharePoint 線上及 OneDrive 共用檔案。
支援小組中的 DLP 保護聊天需要 E5。
若要深入了解授權需求，請參閱 [Microsoft 365 租用戶層級服務授權指導方針](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)

## <a name="overview-of-dlp-for-microsoft-teams"></a>Microsoft 小組的 DLP 簡介

最近，[資料遺失防護](data-loss-prevention-policies.md)（DLP）功能已擴充，可包含 Microsoft 團隊聊天和通道訊息。

> [!NOTE]
> 目前不支援 DLP 專用通道訊息。

如果您的組織有 DLP，您現在可以定義原則，以防止人員在 Microsoft 小組通道或聊天會話中共用機密資訊。 以下是此保護運作方式的一些範例：

- **範例1：保護郵件中的機密資訊**。 假設有人嘗試與客人（外部使用者）共用小組聊天或管道中的機密資訊。 如果您已定義 DLP 原則以避免發生這種情況，就會刪除郵件，其中包含傳送給外部使用者的敏感資訊。 這會根據您設定 DLP 原則的方式，自動進行，並在幾秒內進行。

    > [!NOTE]
    > 當與具有下列專案的 Microsoft 團隊使用者共用時，Microsoft 小組的 DLP 會封鎖機密內容：<br/>- 小組和頻道中的[來賓存取權](https://docs.microsoft.com/MicrosoftTeams/guest-access);或<br/>- 會議和聊天會話中的[外部存取](https://docs.microsoft.com/MicrosoftTeams/manage-external-access)。 <p>如果寄件者和收件者都只是在 [僅限小組] 模式中，且使用[Microsoft 團隊原生同盟](https://docs.microsoft.com/microsoftteams/manage-external-access)，則僅適用于外部聊天會話。 當商務用 Skype 或非原生同盟聊天會話時，小組的 DLP 不會封鎖[interop](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)中的郵件。

- **範例2：保護檔中的機密資訊**。 假設有人嘗試與 Microsoft 小組通道或聊天中的客人共用檔，而且檔中包含機密資訊。 如果您定義了 DLP 原則以避免發生這種情況，則不會對這些使用者開啟檔。 請注意，在這種情況下，您的 DLP 原則必須包括 SharePoint 和 OneDrive，才可就地保護。 （這是適用于 Microsoft 小組的 SharePoint 的 DLP 範例，因此需要使用者授權使用 Office 365 DLP （包含在 Office 365 E3 中），但不需要使用者授權 Office 365 的高級規範。）

## <a name="policy-tips-help-educate-users"></a>原則提示有助於教育使用者

與 DLP 在 Exchange 中的運作方式相同， [outlook、網頁上的 outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)、 [SharePoint Online、商務用 OneDrive](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)，以及[Office 桌面用戶端](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)，當動作與 DLP 原則衝突時，就會出現原則提示。 以下是原則提示的範例：

![小組中的封鎖郵件通知](../media/dlp-teams-blockedmessage-notification.png)

在此情況下，寄件者嘗試在 Microsoft 小組通道中共用社會安全號碼。 **我可以做什麼？** link 開啟對話方塊，為寄件者提供選項，以解決問題。 請注意，在此情況下，寄件者可以選擇覆寫原則，或通知系統管理員複查並解決。

![解析封鎖郵件的選項](../media/dlp-teams-blockedmessage-possibleactions.png)

在您的組織中，您可以選擇允許使用者覆寫 DLP 原則。 而且，當您設定 DLP 原則時，您可以使用預設原則提示，或[自訂群組織的原則提示](#to-customize-policy-tips)。

傳回我們的範例（即寄件者在小組頻道中共用社會保險號碼），以下是收件者看到的功能：

![封鎖郵件](../media/dlp-teams-blockedmessage-notification-to-user.png)

[**這是什麼？** ] 連結會開啟有關 DLP 原則的[文章](data-loss-prevention-policies.md)，協助說明郵件封鎖的原因。

### <a name="to-customize-policy-tips"></a>自訂原則提示

若要執行這種工作，您必須被指派具有編輯 DLP 原則許可權的角色。 若要深入瞭解，請參閱[許可權](data-loss-prevention-policies.md#permissions)。

1. 移至安全性 & 規範中心（[https://protection.office.com](https://protection.office.com)）並登入。

2. 選擇 [**資料遺失防護** > ]**原則**。

3. 選取原則，然後按一下 [**原則設定**] 旁的 [**編輯**]。

4. 請建立新的規則，或編輯原則的現有規則。<br/>![編輯原則的規則](../media/dlp-teams-editrule.png)<br/>

5. 在 [**使用者通知**] 索引標籤上，選取 [**自訂電子郵件文字**和/或**自訂原則提示文字**選項]。<br/>![自訂使用者通知和原則提示](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 指定您要用於電子郵件通知和/或原則提示的文字，然後選擇 [**儲存**]。

7. 在 [**原則設定**] 索引標籤上，選擇 [**儲存**]。

針對您的變更，允許大約一小時以透過您的資料中心進行，並同步處理至使用者帳戶。
 <!-- why are these syncing to user accounts? -->
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>將 Microsoft 團隊新增為現有 DLP 原則的位置

若要執行這種工作，您必須被指派具有編輯 DLP 原則許可權的角色。 若要深入瞭解，請參閱[許可權](data-loss-prevention-policies.md#permissions)。

1. 移至安全性 & 規範中心（[https://protection.office.com](https://protection.office.com)）並登入。

2. 選擇 [**資料遺失防護** > ]**原則**。

3. 選取原則，並查看 [**位置**] 底下的值。 如果您看到**小組聊天及通道訊息**，您就會全部設定。 如果不是，請按一下 [**編輯**]。<br/>![現有原則的位置](../media/dlp-teams-editexistingpolicy.png)<br/>

4. 在 [**狀態**] 欄中，為**小組聊天和頻道訊息**開啟原則。<br/>![適用于小組聊天和頻道的 DLP](../media/dlp-teams-addteamschatschannels.png)<br/>

5. 保留所有帳戶的預設設定，或指定要包含或排除的帳戶。

6. 按一下 [儲存]****。

針對您的變更，允許大約一小時以透過您的資料中心進行，並同步處理至使用者帳戶。
<!-- again, why user accounts? -->
## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>定義新的 Microsoft 團隊 DLP 原則

若要執行這種工作，您必須被指派具有編輯 DLP 原則許可權的角色。 若要深入瞭解，請參閱[許可權](data-loss-prevention-policies.md#permissions)。

1. 移至安全性 & 規範中心（[https://protection.office.com](https://protection.office.com)）並登入。

2. 選擇 [**資料遺失防護** > **原則** > **+ 建立原則**]。

3. 選擇[範本](data-loss-prevention-policies.md#dlp-policy-templates)，然後選擇 **[下一步]**。<br/>在我們的範例中，我們選擇美國個人身分識別資訊資料範本。<br/>![DLP 原則的隱私權範本](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. 在 [**命名您的原則**] 索引標籤上，指定原則的名稱和描述，然後選擇 **[下一步]**。

5. 在 [**選擇位置**] 索引標籤上，保留 [所有位置] 的預設設定，或選取 [**讓我選擇特定位置**]，然後選擇 **[下一步**]。<br/>如果您選擇了特定位置，請為您的 DLP 原則選取這些位置，然後選擇 **[下一步]**。<br/>![DLP 原則位置](../media/dlp-teams-selectlocationsnewpolicy.png)<br/>
    > [!NOTE]
    > 如果您想要確定包含機密資訊的檔沒有適當地共用，請確定已開啟**SharePoint 網站**和**OneDrive 帳戶**，以及**小組聊天及通道訊息**。
    > Microsoft 小組中的通道強烈取決於 Exchange Online 功能。 確定針對通道內容應該套用的原則，也會啟用**Exchange 電子郵件**位置。  
<br/>

6. 在 [**原則設定**] 索引標籤的 **[自訂您要保護的內容類型**] 底下，保留預設的簡單設定，或選擇 [**使用高級設定**]，然後選擇 [**下一步]**。 如果您選擇 [高級設定]，您可以建立或編輯原則的規則。 （若要取得此相關協助，請參閱[簡易設定與高級設定](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)。）

7.  在 [**原則設定**] 索引標籤的 [**如果偵測到機密資訊，您要做什麼？**] 中，複查設定。 （您可以在這裡選擇保留預設[原則提示和電子郵件通知](use-notifications-and-policy-tips.md)，或加以自訂）。<br/>![具有提示與通知的 DLP 原則設定](../media/dlp-teams-policysettings-tipsemails.png)<br/>完成複查或編輯設定後，請選擇 **[下一步]**。

8. 在 [**原則設定**] 索引標籤上的 [**您要先開啟原則或測試內容嗎？**] 中，選擇是否要開啟原則、[先進行測試](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)，或是現在保持關閉狀態，然後選擇 **[下一步]**。<br/>![指定是否要開啟原則](../media/dlp-teams-policysettings-turnonnow.png)<br/>

9. 在 [**複查您的設定**] 索引標籤上，複查新原則的設定。 選擇 [**編輯**] 進行變更。 完成作業後，請選擇 [**建立**]。

針對您的新原則，允許大約一小時以透過您的資料中心進行，並同步處理至使用者帳戶。

## <a name="related-articles"></a>相關文章

[建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)

[針對 DLP 原則傳送電子郵件通知並顯示原則提示](use-notifications-and-policy-tips.md)
