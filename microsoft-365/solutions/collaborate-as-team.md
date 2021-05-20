---
title: 在團隊中與來賓共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: 了解所需的 Microsoft 365 設定步驟，以在 Teams 中成立團隊並與來賓進行工作、交談和文件共同作業。
ms.openlocfilehash: c17732705c1d88ff70e56f5d26d9e268e3ff7c19
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539260"
---
# <a name="collaborate-with-guests-in-a-team"></a>在團隊中與來賓共同作業

如果您需要跨文件、工作及交談與來賓共同作業，建議您使用 Microsoft Teams。 Teams 提供 Office 和 SharePoint 中具備的所有共同作業功能，搭配持續聊天及一組可自訂且可擴展的共同作業工具，進而提供一致的使用者體驗。

在本文中，我們會完成所需的 Microsoft 365 設定步驟，以成立團隊並與來賓進行共同作業。 設定來賓存取權後，您可以遵循 [在 Teams 中新增來賓至團隊](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f) 的步驟來邀請來賓加入團隊。

## <a name="video-demonstration"></a>影片示範

這段影片顯示本文件中所述的設定步驟。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 外部共同作業設定

Microsoft 365 中的共用是由 [Azure Active Directory 中 B2B 外部共同作業設定](/azure/active-directory/external-identities/delegate-invitations) 的最高層級所控管。 如果在 Azure AD 中停用或限制來賓共用，此設定會覆寫您於 Microsoft 365 中設定的任何共用設定。

檢查 B2B 外部共同作業設定，以確保不會封鎖與來賓共用。

![Azure Active Directory 組織關聯性設定頁面的螢幕擷取畫面](../media/azure-ad-organizational-relationships-settings.png)

設定外部共同作業設定

1. 登入 Azure Active Directory，網址為：[https://aad.portal.azure.com](https://aad.portal.azure.com)。
2. 在左側瀏覽窗格中，按一下 **Azure Active Directory**。
3. 按一下 **外部身分識別**。
4. 在左側瀏覽窗格的 **開始** 畫面中，按一下 **外部共同作業設定**。
5. 請確保 **系統管理員和來賓邀請者角色中的使用者可邀請** 及 **成員可邀請** 都設定為 **是**。
6. 如果您做了任何變更，請按一下 **儲存**。

記下 **共同作業限制** 區段中的設定。 請確定您想要共同作業之來賓的網域未封鎖。

如果您與多個組織的來賓合作，建議您限制他們存取目錄資料的能力。 這可防止他們查看目錄中還有誰是來賓。 若要執行這項操作，請在 **來賓使用者存取限制** 下，選取 **來賓使用者對屬性及目錄物件設定的成員資格存取受限** 或 **來賓使用者存取受限於他們自己的目錄物件的屬性及成員資格**。

## <a name="teams-guest-access-settings"></a>Teams 來賓存取設定

Teams 具備來賓存取的主開啟/關閉開關，以及各種設定，可用於控制來賓可在團隊中執行哪些工作。 主開關 **在 Teams 中允許來賓存取** 必須為 **開啟** ，來賓才有存取權在 Teams 中工作。

檢查並確保 Teams 中已啟用來賓存取，並根據您的業務需求調整來賓設定。請記住，這些設定會影響所有團隊。

![Teams 來賓存取切換的螢幕擷取畫面](../media/teams-guest-access-toggle-on.png)

設定 Teams 來賓存取設定

1. 登入 [https://admin.microsoft.com](https://admin.microsoft.com) 的 Microsoft 365 系統管理中心。
2. 在左側瀏覽窗格中，按一下 **顯示全部**。
3. 在 **系統管理中心** 下，按一下 **Teams**。
4. 在 Teams 系統管理中心的左側瀏覽窗格中展開 **全組織設定**，然後按一下 **來賓存取**。
5. 確定 [在 Teams 中允許來賓存取] 已設定為 [開啟]。
6. 對其他來賓設定進行所需的變更，然後按一下 [儲存]。

開啟 Teams 來賓存取後，您可以選擇性地使用敏感度標籤，以控制個別團隊及其相關聯 SharePoint 網站的來賓存取。 如需詳細資訊，請參閱[使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)。

> [!NOTE]
> Teams 來賓設定在開啟後，最慢可能需要 24 小時才會生效。

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 群組來賓設定

Teams 使用 Microsoft 365 群組作為團隊成員資格。必須開啟 Microsoft 365 群組來賓設定，才能使用 Teams 中的來賓存取。

![Microsoft 365 系統管理中心的 Microsoft 365 群組來賓設定螢幕擷取畫面](../media/office-365-groups-guest-settings.png)

設定 Microsoft 365 群組來賓設定

1. 在 Microsoft 365 系統管理中心左側的瀏覽窗格中，展開 **設定**。
2. 按一下 **組織設定**。
3. 在清單中，按一下 **Microsoft 365 群組**。
4. 請確認已核取 **讓群組擁有者將組織外部人員新增到 Microsoft 365 群組作為來賓** 及 **讓來賓群組成員存取群組內容** 核取方塊。
5. 如果您做了任何變更，請按一下 **儲存變更**。


## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 組織層級共用設定

Teams 內容 (例如檔案、資料夾和清單) 全部都儲存在 SharePoint 中。 為了讓來賓能夠存取 Teams 中的這些專案，SharePoint 組織層級共用設定必須允許與來賓共用。

組織層級設定會決定個別網站可用的設定，包括與團隊相關聯的網站。 網站設定不能比組織層級設定更寬鬆。

如果您想要允許與未驗證人員共用檔案和資料夾，請選擇 **任何人**。 如果您想要確保所有來賓都經過驗證，請選擇 **新的及現有的來賓**。 選擇組織中任何網站所需的最寬鬆設定。

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


設定 SharePoint 組織層級共用設定

1. 在 Microsoft 365 系統管理中心的左側瀏覽窗格中，在 **系統管理中心** 下，按一下 **SharePoint**。
2. 在 SharePoint 系統管理中心的左側瀏覽窗格中，展開 **原則** ，然後按一下 **共用**。
3. 確定 SharePoint 的外部共用已設定為 **任何人** 或 **新的及現有的來賓**。
4. 如果您做了任何變更，請按一下 **儲存**。


## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint 組織層級的預設連結設定

預設檔案和資料夾連結設定會決定當使用者共用檔案或資料夾時，預設會向使用者顯示的連結選項。 如有需要，使用者可以在共用前，將連結類型變更為其中一個其他選項。

請記住，此設定會影響貴組織的所有團隊和 SharePoint 網站。

選擇下列任一連結類型，使用者共用檔案和資料夾時，預設會加以選取：

- **擁有連結的任何人** - 如果您預期要共用許多未經驗證的檔案和資料夾，請選擇此選項。 如果您想要允許 *任何人* 連結，但擔心意外的未驗證共用，請考慮將其中一個其他選項設為預設值。 此連結類型只有在您已啟用 **任何人** 共用時才能使用。
- **只有貴組織中的人員** - 如果您預期大部分檔案和資料夾共用都是與組織內部人員共用，請選擇此選項。
- **特定人員** - 如果您預期要與來賓共用許多檔案和資料夾，請考慮使用此選項。 這種類型的連結適用於來賓，且需要他們進行驗證。
 
![SharePoint 組織層級檔案和資料夾共用設定的螢幕擷取畫面](../media/sharepoint-organization-files-folders-sharing-settings.png)


設定 SharePoint 組織層級的預設連結設定

1. 瀏覽至 SharePoint 系統管理中心的共用頁面。
2. 在 **檔案與資料夾連結** 下，選取您想要使用的預設共用連結。
3. 如果您做了任何變更，請按一下 **儲存**。

## <a name="create-a-team"></a>建立團隊

下一個步驟是建立您計畫用於與來賓共同作業的團隊。

建立團隊
1. 在 Teams 中，於 **Teams** 索引標籤左窗格底部按一下 **加入或建立團隊**。
2. 按一下 **建立團隊**。
3. 按一下 **從頭建立團隊**。
4. 選擇 **私人** 或 **公用**。
5. 輸入團隊的名稱和描述，然後按一下 **建立**。
6. 按一下 **略過**。

我們稍後會邀請使用者。接下來，檢查與團隊相關聯之 SharePoint 網站的網站層級共用設定，這點非常重要。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 網站層級共用設定

檢查網站層級共用設定，確定它們允許你所要的此團隊存取類型。 例如，如果您將組織層級設定設為 **任何人**，但您希望所有來賓都為此團隊進行驗證，則請確定網站層級共用設定已設為 **新的及現有的來賓**。

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

設定網站層級共用設定
1. 在 SharePoint 管理中心中，在左側導覽窗格中展開 **網站**，然後按一下 **使用中網站**。
2. 為您剛建立的團隊選取網站。
3. 按一下 [...] 然後選擇 **共用**。
4. 請確認共用設為 **任何人** 或 **新的及現有的來賓**。
5. 如果您做了任何變更，請按一下 **儲存**。

## <a name="invite-users"></a>邀請使用者

來賓共用設定現已設定，因此您可以開始將內部使用者和來賓新增到您的團隊。 

邀請內部使用者加入團隊
1. 在該團隊中，按一下 **更多選項** (**\*\*\***)，然後按一下 **新增成員**。
2. 輸入要邀請的人員名稱。
3. 按一下 **新增**，然後按一下 **關閉**。

邀請來賓加入團隊
1. 在該團隊中，按一下 **更多選項** (**\*\*\***)，然後按一下 **新增成員**。
2. 輸入要邀請之來賓的電子郵件地址。
3. 按一下 **編輯來賓資訊**。
4. 輸入來賓的全名，然後按一下核取方塊。
5. 按一下 **新增**，然後按一下 **關閉**。

## <a name="see-also"></a>請參閱

[與未驗證使用者共用檔案和資料夾的最佳做法](best-practices-anonymous-sharing.md)

[與來賓共用時限制意外暴露檔案](share-limit-accidental-exposure.md)

[建立安全的來賓共用環境](create-secure-guest-sharing-environment.md)

[使用受管理來賓建立 B2B 外部網路](b2b-extranet.md)

[SharePoint 和 OneDrive 與 Azure AD B2B 整合](/sharepoint/sharepoint-azureb2b-integration-preview)

[從 SharePoint 或 OneDrive 共用時，共用選項會以灰色顯示](/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)