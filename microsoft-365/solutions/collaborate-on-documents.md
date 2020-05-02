---
title: 在文件上與來賓共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
ms.custom:
- M365solutions
localization_priority: Normal
f1.keywords: NOCSH
description: 瞭解如何使用 SharePoint 和 OneDrive 中的檔與客人進行共同作業。
ms.openlocfilehash: 33d9300343b23702d5024ac0b489930ac815be7e
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002262"
---
# <a name="collaborate-with-guests-on-a-document"></a>在文件上與來賓共同作業

如果您需要與組織外部的人員共同作業 SharePoint 或 OneDrive 中的檔，您可以將檔的共用連結傳送給他們。 在本文中，我們將逐步完成設定 SharePoint 的共用連結，以及組織需求 OneDrive 所需的 Microsoft 365 設定步驟。

## <a name="video-demonstration"></a>影片示範

這段影片顯示本檔所述的設定步驟。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Azure 組織關聯性設定

Microsoft 365 中的共用可透過 Azure Active Directory 中的組織關聯設定受到最高層級的制約。 如果 Azure AD 中已停用來賓共用或已限制來賓共用，這會覆寫您在 Microsoft 365 中設定的任何共用設定。

檢查 [組織關聯] 設定，以確保未封鎖與來賓共用。

![Azure Active Directory 組織關聯性設定頁面的螢幕擷取畫面](../media/azure-ad-organizational-relationships-settings.png)

設定組織關聯設定

1. 登入 Microsoft Azure，網址[https://portal.azure.com](https://portal.azure.com)為。
2. 在左側導覽中，按一下 [ **Azure Active Directory**]。
3. 在 [**一覽表**] 窗格中，按一下 [**組織關聯**性]。
4. 在 [**組織關聯**] 窗格中，按一下 [**設定**]。
5. 確定**guest 和 guest inviter role 中的系統管理員和使用者都可以邀請**和**成員可以邀請**皆設定為 **[是]**。
6. 如果您做了任何變更，請按一下 [儲存]****。

請記下 [**協同限制**] 區段中的設定。 確定您要與之來賓進行共同作業的網域不會遭到封鎖。

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 組織層級共用設定

為了讓組織外部人員能夠存取 SharePoint 或 OneDrive 中的檔，SharePoint 和 OneDrive 組織層級的共用設定必須允許與組織外部的人員共用。

SharePoint 的組織層級設定會決定個別 SharePoint 網站可使用的設定。 網站設定不能超過組織層級設定的許可。 OneDrive 的組織層級設定決定使用者 OneDrive 庫中可使用的共用層級。

若要 SharePoint 和 OneDrive，如果您想要允許未驗證的檔案和資料夾共用，請選擇 [**任何人**]。 若要確定您組織外部的人員必須進行驗證，請選擇 [**新增] 和 [現有來賓**]。 [*任何人*] 連結是最簡單的共用方式：您組織外部的人員可以在未驗證的情況下開啟連結，而且可以隨意將其傳遞給其他人。

若為 SharePoint，請選擇您組織中的任何網站所需的功能最寬鬆設定。

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


設定 SharePoint 組織層級共用設定

1. 在 Microsoft 365 系統管理中心的左側導覽中，按一下 [系統**管理中心**] 底下的 [ **SharePoint**]。
2. 在 SharePoint 管理中心中，按一下左側導覽窗格中的 [共用]****。
3. 確定 SharePoint 或 OneDrive 的外部共用已設定為**任何人**或**新的和現有的客人**。 （請注意，[OneDrive] 設定不能超過 SharePoint 設定的許可。）
4. 如果您做了任何變更，請按一下 [儲存]****。

## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint 組織層級的預設連結設定

預設的檔案和資料夾連結設定會決定使用者在共用檔案或資料夾時，預設會向使用者顯示的連結選項。 如有需要，使用者可以在共用之前將連結類型變更為其他選項之一。

請記住，此設定會影響組織中 SharePoint 網站和 OneDrive。

選擇當使用者共用檔案和資料夾時，預設會選取的連結類型：

- **任何具有連結的使用者**-如果您想要進行許多未驗證的檔案和資料夾共用，請選擇此選項。 如果您想要允許*任何人*的連結，但擔心意外的共用驗證，請將其中一個其他選項視為預設值。 只有在您已啟用**任何**共用時，才可使用此連結類型。
- **僅限貴組織中的人員**-如果您預期大多數的檔案和資料夾共用與組織內的人員有關，請選擇此選項。
- **特定人員**-如果您想要對來賓執行大量檔案和資料夾共用，請考慮此選項。 這種連結類型與來賓搭配使用，需要驗證。
 
![SharePoint 組織層級檔案和資料夾共用設定的螢幕擷取畫面](../media/sharepoint-organization-files-folders-sharing-settings.png)


設定 SharePoint 和 OneDrive 組織層級的預設連結設定

1. 流覽至 SharePoint 系統管理中心的 [共用] 頁面。
2. 在 [檔案**和資料夾連結**] 底下，選取您要使用的預設共用連結。
3. 如果您做了任何變更，請按一下 [儲存]****。

## <a name="sharepoint-site-level-sharing-settings"></a>網站層級共用設定 SharePoint

如果您要共用 SharePoint 網站中的檔案和 fodlers，您也需要檢查該網站的網站層級共用設定。

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

設定網站層級共用設定
1. 在 SharePoint 管理中心中，在左側導覽窗格中展開 [網站]****，然後按一下 [使用中網站]****。
2. 選取您剛建立的網站。
3. 在功能區中，按一下 [共用]****。
4. 確定 [共用] 設定為 [**任何人**] 或 [**現有來賓**]。
5. 如果您做了任何變更，請按一下 [儲存]****。

## <a name="invite-users"></a>邀請使用者

現在已設定來賓共用設定，因此使用者現在可以與組織外部的人員共用檔案和資料夾。 如需詳細資訊，請參閱[共用 OneDrive 檔案和資料夾](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07)及[共用 SharePoint 檔案或資料夾](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)。

## <a name="see-also"></a>另請參閱

[與未驗證使用者共用檔案和資料夾的最佳做法](best-practices-anonymous-sharing.md)

[與來賓共用時限制意外暴露檔案](share-limit-accidental-exposure.md)