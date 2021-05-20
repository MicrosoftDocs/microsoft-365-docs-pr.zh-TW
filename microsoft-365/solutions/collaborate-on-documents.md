---
title: 在文件上與來賓共同作業
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
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: 在本文中，您將瞭解如何在 SharePoint 和 OneDrive 的檔中與客人共同作業。
ms.openlocfilehash: 338c7f32944bccb766ed923c12a9fceee4d81db8
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537832"
---
# <a name="collaborate-with-guests-on-a-document"></a>在文件上與來賓共同作業

如果您需要與組織外部的人員共同作業 SharePoint 或 OneDrive 中的檔，您可以將檔的共用連結傳送給他們。 在本文中，我們將逐步完成必要的 Microsoft 365 設定步驟，為您的組織的需求設定 SharePoint 和 OneDrive 的共用連結。

## <a name="video-demonstration"></a>影片示範

這段影片顯示本文件中所述的設定步驟。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 外部協同作業設定

Microsoft 365 中的共用是由 [Azure Active Directory 中 B2B 外部共同作業設定](/azure/active-directory/external-identities/delegate-invitations) 的最高層級所控管。 如果 Azure AD 中已停用或限制來賓共用，此設定會覆寫您在 Microsoft 365 中設定的任何共用設定。

檢查 B2B 的外部共同作業設定，以確保不會封鎖與來賓共用。

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

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 組織層級的共用設定

為了讓組織外部人員能夠存取 SharePoint 或 OneDrive 中的檔，SharePoint 和 OneDrive 組織層級的共用設定必須允許與組織外部的人員共用。

SharePoint 的組織層級設定會決定個別 SharePoint 網站可使用的設定。 網站設定不能比組織層級設定更寬鬆。 OneDrive 的組織層級設定會決定使用者 OneDrive 庫中可使用的共用層級。

若要 SharePoint 和 OneDrive，如果您想要允許未驗證的檔案和資料夾共用，請選擇 [**任何人**]。 若要確定您組織外部的人員必須進行驗證，請選擇 [ **新增] 和 [現有來賓**]。 [*任何人*] 連結是最簡單的共用方式：貴組織外部的人員可以在未驗證的情況下開啟連結，而且可以隨意將其傳遞給其他人。

若為 SharePoint，請選擇您組織中的任何網站所需的功能最寬鬆設定。

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


設定 SharePoint 組織層級共用設定

1. 在 Microsoft 365 系統管理中心的左側瀏覽窗格中，在 **系統管理中心** 下，按一下 **SharePoint**。
2. 在 [SharePoint 系統管理中心] 的左功能窗格中，按一下 [**原則**] 底下的 [**共用**]。
3. 確定 SharePoint 或 OneDrive 的外部共用已設定為 **任何人** 或 **新的和現有的客人**。  (請注意，OneDrive 設定不能超過 SharePoint 設定的容許數目。 ) 
4. 如果您做了任何變更，請按一下 **儲存**。

## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint 組織層級的預設連結設定

預設檔案和資料夾連結設定會決定當使用者共用檔案或資料夾時，預設會向使用者顯示的連結選項。 如有需要，使用者可以在共用前，將連結類型變更為其中一個其他選項。

請記住，此設定會影響組織中 SharePoint 網站和 OneDrive。

選擇下列任何類型的連結，當使用者共用檔案和資料夾時，預設會選取此連結：

- **任何具有連結的使用者** -如果您想要進行許多未驗證的檔案和資料夾共用，請選擇此選項。 如果您想要允許 *任何人* 連結，但擔心意外的未驗證共用，請考慮將其中一個其他選項設為預設值。 此連結類型只有在您已啟用 **任何人** 共用時才能使用。
- **只有貴組織中的人員** - 如果您預期大部分檔案和資料夾共用都是與組織內部人員共用，請選擇此選項。
- **特定人員** - 如果您預期要與來賓共用許多檔案和資料夾，請考慮使用此選項。 這種類型的連結適用於來賓，且需要他們進行驗證。
 
![SharePoint 組織層級檔案和資料夾共用設定的螢幕擷取畫面](../media/sharepoint-organization-files-folders-sharing-settings.png)


設定 SharePoint，並 OneDrive 組織層級的預設連結設定

1. 瀏覽至 SharePoint 系統管理中心的共用頁面。
2. 在 **檔案與資料夾連結** 下，選取您想要使用的預設共用連結。
3. 如果您做了任何變更，請按一下 **儲存**。

若要設定共用連結的許可權，請在 **[選擇預設為共用連結所選取的許可權**] 底下。

1. 如果您不想讓未驗證的使用者變更檔案和資料夾，請選取 [View] （ **查看** ）。
2. 如果您想要允許未驗證的使用者對檔案和資料夾進行變更，請選取 [ **編輯** ]。

請注意，上述兩個 premission-選項不僅可以套用於來賓/外部使用者，也可以套用至內部使用者。 您選擇的許可權選項是由自我判斷決定。

設定允許與任何人共用的連結許可權

1. 在 [ **這些連結可提供下列許可權：** ] 子窗格中， 
    1. 從 [ **檔案** ] 下拉式清單中， 
        - 如果您想要允許未驗證的使用者變更檔案，請選取 [ **查看] 和 [編輯** ]。
        - 如果您不想讓未驗證的使用者變更檔，請選取 [View] （ **查看** ）。
    2. 從 [ **資料夾** ] 下拉式清單中，
        - 如果您想要允許未驗證的使用者對資料夾進行變更，請選取 **[查看]、[編輯] 及 [上傳** ]。
        - 如果您不想讓未驗證的使用者對資料夾進行變更，請選取 [View] （ **查看** ）。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 網站層級共用設定

如果您要共用 SharePoint 網站中的檔案與資料夾，您也需要檢查該網站的網站層級共用設定。

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

設定網站層級共用設定

1. 在 SharePoint 管理中心中，在左側導覽窗格中展開 **網站**，然後按一下 **使用中網站**。
2. 選取您要與來賓共用檔案和資料夾的網站。
3. 向右滾動選取的網站所在的列 () 然後按一下 [ **外部共用** ] 欄中的任何地方。
4. 在彈出的頁面上，按一下 [ **原則** ] 索引標籤。
5. 在 [ **外部共用** ] 窗格中，按一下 [ **編輯**]。
6. 請確認共用設為 **任何人** 或 **新的及現有的來賓**。
7. 如果您做了任何變更，請按一下 **儲存**。

## <a name="invite-users"></a>邀請使用者

現在已設定來賓共用設定;所以使用者現在可以與組織外部的人員共用檔案和資料夾。 如需詳細資訊，請參閱[共用 OneDrive 檔案和資料夾](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07)及[共用 SharePoint 檔案或資料夾](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)。

## <a name="see-also"></a>另請參閱

[與未驗證使用者共用檔案和資料夾的最佳做法](best-practices-anonymous-sharing.md)

[與來賓共用時限制意外暴露檔案](share-limit-accidental-exposure.md)

[SharePoint 和 OneDrive 與 Azure AD B2B 整合](/sharepoint/sharepoint-azureb2b-integration-preview)