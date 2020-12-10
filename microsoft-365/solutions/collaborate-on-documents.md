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
description: 在本文中，您將瞭解如何在 SharePoint 和 OneDrive 的檔中與客人共同作業。
ms.openlocfilehash: bb97beaacf6a433e4fc5c38a897327d1e359ffb1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613511"
---
# <a name="collaborate-with-guests-on-a-document"></a>在文件上與來賓共同作業

如果您需要與組織外部的人員共同作業 SharePoint 或 OneDrive 中的檔，您可以將檔的共用連結傳送給他們。 在本文中，我們將逐步檢查必要的 Microsoft 365 設定步驟，以設定 SharePoint 和 OneDrive 組織需求的共用連結。

## <a name="video-demonstration"></a>影片示範

這段影片顯示本檔所述的設定步驟。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Azure 組織關聯性設定

Microsoft 365 中的共用可透過 [Azure Active Directory 中的組織關聯設定](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)受到最高層級的制約。 如果 Azure AD 中已停用或限制來賓共用，此設定會覆寫您在 Microsoft 365 中設定的任何共用設定。

檢查 [組織關聯] 設定，以確保未封鎖與來賓共用。

![Azure Active Directory 組織關聯性設定頁面的螢幕擷取畫面](../media/azure-ad-organizational-relationships-settings.png)

設定組織關聯設定

設定外部協同作業設定

1. 登入 Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com) 。
2. 在左功能窗格中，按一下 [ **Azure Active Directory**]。
3. 按一下 [ **外部** 身分識別]。
4. 在 [ **快速入門** ] 畫面上，按一下左功能窗格中的 [ **外部協同作業設定**]。
5. 確定 **guest 和 guest inviter role 中的系統管理員和使用者都可以邀請** 和 **成員可以邀請** 皆設定為 **[是]**。
6. 如果您做了任何變更，請按一下 [儲存]。

請記下 [ **協同限制** ] 區段中的設定。 確定您要與之來賓進行共同作業的網域不會遭到封鎖。

如果您與多個組織的客人合作，您可能想要限制其存取目錄資料的能力。 這可防止使用者看到目錄中的客人。 若要執行此動作，請在 [ **來賓使用者訪問限制**] 底下，選取 [來賓使用者對內容的 **存取權受到限制** ]，或 **[來賓使用者存取許可權制于自身目錄物件的屬性和成員資格]** 設定。

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 組織層級的共用設定

為了讓組織外部人員能夠存取 SharePoint 或 OneDrive 中的檔，SharePoint 和 OneDrive 組織層級的共用設定必須允許與組織外部的人員共用。

SharePoint 的組織層級設定會決定個別 SharePoint 網站可使用的設定。 網站設定不能超過組織層級設定的許可。 OneDrive 的組織層級設定會決定使用者 OneDrive 庫中可使用的共用層級。

若要 SharePoint 和 OneDrive，如果您想要允許未驗證的檔案和資料夾共用，請選擇 [ **任何人**]。 若要確定您組織外部的人員必須進行驗證，請選擇 [ **新增] 和 [現有來賓**]。 [*任何人*] 連結是最簡單的共用方式：貴組織外部的人員可以在未驗證的情況下開啟連結，而且可以隨意將其傳遞給其他人。

若為 SharePoint，請選擇您組織中的任何網站所需的功能最寬鬆設定。

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


設定 SharePoint 組織層級的共用設定

1. 在 Microsoft 365 系統管理中心的左功能窗格中，按一下 [系統 **管理中心**] 底下的 [ **SharePoint**]。
2. 在 [SharePoint 系統管理中心] 的左功能窗格中，按一下 [ **原則**] 底下的 [ **共用**]。
3. 確定 SharePoint 或 OneDrive 的外部共用已設定為 **任何人** 或 **新的和現有的客人**。  (請注意，OneDrive 設定不能超過 SharePoint 設定的容許數目。 ) 
4. 如果您做了任何變更，請按一下 [儲存]。

## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint 組織層級的預設連結設定

預設的檔案和資料夾連結設定會決定在使用者共用檔案或資料夾時，預設會向使用者顯示的連結選項。 如有需要，使用者可以在共用之前將連結類型變更為其他選項之一。

請記住，此設定會影響組織中 SharePoint 網站和 OneDrive。

選擇下列任何類型的連結，當使用者共用檔案和資料夾時，預設會選取此連結：

- **任何具有連結的使用者** -如果您想要進行許多未驗證的檔案和資料夾共用，請選擇此選項。 如果您想要允許 *任何人* 的連結，但擔心意外的共用驗證，請將其中一個其他選項視為預設值。 只有在您已啟用 **任何** 共用時，才可使用此連結類型。
- **僅限貴組織中的人員** -如果您預期大多數的檔案和資料夾共用與組織內的人員有關，請選擇此選項。
- **特定人員** -如果您想要對來賓執行大量檔案和資料夾共用，請考慮此選項。 這種連結類型與來賓搭配使用，需要驗證。
 
![SharePoint 組織層級檔案和資料夾共用設定的螢幕擷取畫面](../media/sharepoint-organization-files-folders-sharing-settings.png)


設定 SharePoint，並 OneDrive 組織層級的預設連結設定

1. 流覽至 SharePoint 系統管理中心的 [共用] 頁面。
2. 在 [檔案 **和資料夾連結**] 底下，選取您要使用的預設共用連結。
3. 如果您做了任何變更，請按一下 [儲存]。

若要設定共用連結的許可權，請在 **[選擇預設為共用連結所選取的許可權**] 底下。

1. 如果您不想讓未驗證的使用者變更檔案和資料夾，請選取 [View] （ **查看** ）。
2. 如果您想要允許未驗證的使用者對檔案和資料夾進行變更，請選取 [ **編輯** ]。

請注意，上述兩個 premission-選項不僅可以套用於來賓/外部使用者，也可以套用至內部使用者。 您選擇的許可權選項是由自我判斷決定。

設定允許與任何人共用的連結許可權

1. 在 [ **這些連結可提供下列許可權：** ] 子窗格中， 
    1. 從 [ **檔案** ] 下拉式清單中， 
        1. 如果您想要允許未驗證的使用者變更檔案，請選取 [ **查看] 和 [編輯** ]。
        2. 如果您不想讓未驗證的使用者變更檔，請選取 [View] （ **查看** ）。
    2. 從 [ **資料夾** ] 下拉式清單中，
        1. 如果您想要允許未驗證的使用者對資料夾進行變更，請選取 **[查看]、[編輯] 及 [上傳** ]。
        2. 如果您不想讓未驗證的使用者對資料夾進行變更，請選取 [View] （ **查看** ）。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 網站層級共用設定

如果您要共用 SharePoint 網站中的檔案與資料夾，您也需要檢查該網站的網站層級共用設定。

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

設定網站層級共用設定

1. 在 SharePoint 系統管理中心的左功能窗格中，展開 [ **網站** ]，然後按一下 [作用中的 **網站**]。
2. 選取您要與來賓共用檔案和資料夾的網站。
3. 向右滾動選取的網站所在的列 () 然後按一下 [ **外部共用** ] 欄中的任何地方。
4. 在彈出的頁面上，按一下 [ **原則** ] 索引標籤。
5. 在 [ **外部共用** ] 窗格中，按一下 [ **編輯**]。
6. 確定 [共用] 設定為 [ **任何人** ] 或 [ **現有來賓**]。
7. 如果您做了任何變更，請按一下 [儲存]。

## <a name="invite-users"></a>邀請使用者

現在已設定來賓共用設定;所以使用者現在可以與組織外部的人員共用檔案和資料夾。 如需詳細資訊，請參閱 [共用 OneDrive 檔案和資料夾](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) 及 [共用 SharePoint 檔案或資料夾](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) 。

## <a name="see-also"></a>另請參閱

[與未驗證使用者共用檔案和資料夾的最佳做法](best-practices-anonymous-sharing.md)

[與來賓共用時限制意外暴露檔案](share-limit-accidental-exposure.md)

[與 Azure AD B2B 的 SharePoint 和 OneDrive 整合](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
