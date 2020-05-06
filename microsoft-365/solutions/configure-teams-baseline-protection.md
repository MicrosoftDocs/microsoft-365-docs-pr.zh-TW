---
title: 為小組設定基準保護
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
description: 了解如何使用基準層級的保護來部署小組。
ms.openlocfilehash: 2ab91e28135f05fb7f315ca8869f937f3433099a
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003756"
---
# <a name="configure-teams-with-baseline-protection"></a>為小組設定基準保護

在本文中，我們將說明如何使用基準層級的保護來部署小組。 此層級可讓使用者獲得廣泛的共同作業選項，同時又能增強權限管理功能並針對過度共用提供基本防護。 這個層級的建議保護包括身分識別和裝置存取原則，以及惡意程式碼防護。 此外，您也可以視需要套用條件式存取原則和資料外洩防護。

## <a name="initial-protections"></a>初始保護

我們所建議的第一個步驟是設定基本身分識別和裝置存取原則。 如需詳細資訊，請參閱[用來保護 Teams 聊天、群組和檔案的原則建議](https://docs.microsoft.com/microsoft-365/enterprise/teams-access-policies)。

我們也建議您開啟基本的進階威脅防護功能，以防範文件、附件和連結中的惡意程式碼。 建議您開啟下表中的每個選項。

|選項|資訊|
|:------|:-----------|
|適用於 SPO、OneDrive 和 Teams 的 ATP 安全附件|[Office 365 ATP 安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br>[適用於 SharePoint、OneDrive 及 Microsoft Teams 的 Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)|
|ATP 安全文件|[Office 365 進階威脅防護中的安全文件](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)|
|Teams 的 ATP 安全連結|[Teams 中的 Office 365 安全連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams)<br>[Office 365 ATP 安全連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)|

## <a name="teams-guest-sharing"></a>Teams 來賓共用

在每一層中，我們都有可讓您與組織外部的人員共用的選項。 針對敏感度和高敏感度層，我們會有選項可供您使用敏感度標籤在小組層級關閉來賓共用。 但必須開啟組織層級的來賓共用設定，才能讓來賓共用在 Teams 中完全生效。

![Teams 來賓存取切換的螢幕擷取畫面](../media/teams-guest-access-toggle-on.png)

設定 Teams 來賓存取設定

1. 登入 [https://admin.microsoft.com](https://admin.microsoft.com) 的 Microsoft 365 系統管理中心。
2. 在左側導覽窗格中，按一下 [顯示全部]****。
3. 在 [系統管理中心]**** 底下，按一下 [Teams]****。
4. 在 Teams 系統管理中心的左側導覽中展開 [全組織設定]****，然後按一下 [來賓存取]****。
5. 確定 [在 Teams 中允許來賓存取]**** 已設定為 [開啟]****。
6. 對其他來賓設定進行所需的變更，然後按一下 [儲存]****。

> [!NOTE]
> Teams 來賓設定在開啟後，最慢可能需要 24 小時才會生效。

Office 365 群組和 SharePoint 預設會開啟來賓共用功能，但是如果您先前已變更組織的任何來賓共用設定，則建議您檢閱[在小組中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)，以確保 Teams 中可以使用來賓共用。

## <a name="site-and-file-sharing"></a>網站和檔案共用

為了降低不小心與組織外的人員共用檔案和資料夾的風險，建議您將 SharePoint 的預設共用連結變更為 [只有貴組織中的人員]**。 (如果使用者需要對外共用，且您已啟用來賓共用，其仍可在共用時變更連結類型)。

變更預設的共用連結
1. 開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。
2. 在 [原則]**** 底下，按一下 [共用]****。
3. 在 [檔案與資料夾連結]**** 下，選取 [只有貴組織中的人員]****。
4. 按一下 [儲存]****。

為了獲得最佳的來賓共用體驗，建議您啟用 [SharePoint 和 OneDrive 與 Azure AD B2B 整合](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)。

## <a name="create-a-team"></a>建立小組

在與小組相關聯的 SharePoint 網站中，還會執行另外的基準層級保護設定。 請先[建立公用或私人小組](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)，再繼續進行下一節。

## <a name="site-sharing-settings"></a>網站共用設定

根據預設，SharePoint 網站的成員可以邀請其他人加入網站。 當網站屬於小組時，小組成員便會納入為網站成員。 不過，直接新增至網站的人員無法存取小組的其他資源。 因此，建議您透過小組來專門管理權限。

為了有助於管理權限，建議您將相關聯的網站設定為只允許擁有者可自行共用網站。 這可簡化權限管理工作，並有助於防止有人在小組擁有者不知情的情況下進行存取。 請為需要基準保護的每個小組執行此動作。

更新網站共用設定
1. 在小組的工具列中，按一下 [檔案]****。
2. 按一下 [在 SharePoint 中開啟]****。
3. 在 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]****。
4. 在 [網站權限]**** 窗格的 [共用設定]**** 之下，按一下 [變更共用設定]****。
5. 在 [共用權限]**** 底下，選擇 [網站擁有者和成員，以及擁有編輯權限的人員可以共用檔案與資料夾，但只有網站擁有者可以共用網站]****，然後按一下 [儲存]****。

## <a name="additional-protections"></a>其他保護

Microsoft 365 提供了其他方法來保護您的內容。 請想想下列選項是否有助於改善貴組織的安全性。

- 讓您的來賓使用者同意[使用規定](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)。
- 為來賓設定[工作階段逾時原則](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)。
- 建立[敏感資訊類型](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)，並使用[資料外洩防護](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) 來設定關於存取敏感資訊的原則。

## <a name="see-also"></a>另請參閱

[管理 Teams 中的會議原則](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)

[開始使用測試人員風險管理](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure)
