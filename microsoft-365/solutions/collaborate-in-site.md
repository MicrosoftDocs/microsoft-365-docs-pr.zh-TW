---
title: 在網站中與來賓共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: 深入瞭解設定 SharePoint 網站與來賓共同作業所需的 Microsoft 365 設定步驟。
ms.openlocfilehash: df9068ef4b4eb35f946b78d8f7fefa01c254c79c
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49029990"
---
# <a name="collaborate-with-guests-in-a-site"></a>在網站中與來賓共同作業

如果您需要跨檔、資料和清單共同處理來賓，您可以使用 SharePoint 網站。 新式 SharePoint 網站會連線至 Microsoft 365 群組，並可管理網站成員資格，並提供其他共同作業工具，例如共用信箱和行事曆。

在本文中，我們將逐步完成設定 SharePoint 網站與來賓共同作業所需的 Microsoft 365 設定步驟。

## <a name="video-demonstration"></a>影片示範

這段影片顯示本檔所述的設定步驟。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 外部協同作業設定

Microsoft 365 中的共用可透過 [Azure Active Directory 中的組織關聯設定](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)受到最高層級的制約。 如果 Azure AD 中已停用或限制來賓共用，此設定會覆寫您在 Microsoft 365 中設定的任何共用設定。

檢查外部共同作業設定，以確保未封鎖與來賓共用。

![Azure Active Directory 外部協同作業設定頁面的螢幕擷取畫面](../media/azure-ad-organizational-relationships-settings.png)

設定外部協同作業設定

1. 登入 Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com) 。
2. 在左功能窗格中，按一下 [ **Azure Active Directory** ]。
3. 按一下 [ **外部** 身分識別]。
4. 在 [ **快速入門** ] 畫面上，按一下左功能窗格中的 [ **外部協同作業設定** ]。
5. 確定 **guest 和 guest inviter role 中的系統管理員和使用者都可以邀請** 和 **成員可以邀請** 皆設定為 **[是]** 。
6. 如果您做了任何變更，請按一下 [儲存]。

請記下 [ **協同限制** ] 區段中的設定。 確定您要與之來賓進行共同作業的網域不會遭到封鎖。

如果您與多個組織的客人合作，您可能想要限制其存取目錄資料的能力。 這可防止使用者看到目錄中的客人。 若要執行此動作，請在 [ **來賓使用者訪問限制** ] 底下，選取 [來賓使用者對內容的 **存取權受到限制** ]，或 **[來賓使用者存取許可權制于自身目錄物件的屬性和成員資格]** 設定。

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 群組來賓設定

新式 SharePoint 網站使用 Microsoft 365 群組來控制網站存取。 為了讓 SharePoint 網站中的來賓存取能夠運作，必須開啟 Microsoft 365 群組來賓設定。

![Microsoft 365 系統管理中心中 Microsoft 365 群組來賓設定的螢幕擷取畫面](../media/office-365-groups-guest-settings.png)

設定 Microsoft 365 群組來賓設定

1. 在 Microsoft 365 系統管理中心的左功能窗格中，展開 [ **設定** ]。
2. 按一下 [ **組織設定** ]。
3. 在清單中，按一下 [ **Microsoft 365 群組** ]。
4. 確定 **允許群組擁有者將組織外部的人員新增至 Microsoft 365 群組做為來賓** ，並 **讓 [允許來賓群組成員存取群組內容** ] 核取方塊皆已勾選。
5. 如果您進行變更，請按一下 [ **儲存變更** ]。

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 組織層級的共用設定

為了讓來賓能夠存取 SharePoint 網站，SharePoint 組織層級的共用設定必須允許與來賓共用。

組織層級設定會決定可用於個別網站的設定。 網站設定不能超過組織層級設定的許可。

如果您想要允許未驗證的檔案和資料夾共用，請選擇 [ **任何人** ]。 若要確定您組織外部的人員必須進行驗證，請選擇 [ **新增] 和 [現有來賓** ]。 選擇您的組織中的任何網站所需的功能最寬鬆設定。

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


設定 SharePoint 組織層級的共用設定

1. 在 Microsoft 365 系統管理中心的左功能窗格中，按一下 [系統 **管理中心** ] 底下的 [ **SharePoint** ]。
2. 在 [SharePoint 系統管理中心] 的左功能窗格中，按一下 [ **原則** ] 底下的 [ **共用** ]。
3. 確定 SharePoint 的外部共用已設定為 **任何人** 或 **新的和現有的客人** 。
4. 如果您做了任何變更，請按一下 [儲存]。

## <a name="create-a-site"></a>建立網站

下一步是建立您計畫用以與來賓合作的網站。

若要建立網站
1. 在 SharePoint 系統管理中心的 **[網站]** 底下，按一下 **[使用中網站]** 。
2. 按一下 **[建立]** 。
3. 按一下 [ **小組網站** ]。
4. 輸入網站名稱，並為群組擁有者 (網站擁有者) 輸入名稱。
5. 在 [ **高級設定** ] 底下，選擇您是否要將此網站設為公用或私人網站。
6. 按 [下一步]。
7. 按一下 **[完成]** 。

我們稍後會邀請使用者。 接下來，請務必檢查此網站的網站層級共用設定。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 網站層級共用設定

請檢查網站層級的共用設定，以確定其允許您要用於此網站的訪問類型。 例如，如果您將組織層級設定設定為 [ **任何人** ]，但您希望所有來賓都對此網站進行驗證，請確定網站層級共用設定已設定為 [ **新增] 和 [現有來賓** ]。

請注意，網站無法與未驗證的人員共用 ( **任何人** 設定) ，但是個別的檔案和資料夾可以。

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

設定網站層級共用設定
1. 在 SharePoint 管理中心中，在左側導覽窗格中展開 [網站]，然後按一下 [使用中網站]。
2. 選取您要共用的網站。
3. 按一下 [...]，然後按一下 [ **共用** ]。
4. 確定 [共用] 設定為 [ **任何人** ] 或 [ **現有來賓** ]。
5. 如果您做了任何變更，請按一下 [儲存]。

## <a name="invite-users"></a>邀請使用者

現在已設定來賓共用設定，因此您可以開始將內部使用者和來賓新增至您的網站。 網站存取是透過相關的 Microsoft 365 群組來控制，因此我們將會在那裡新增使用者。

邀請內部使用者加入群組
1. 流覽至您要新增使用者的網站。
2. 按一下右上方的 [ **成員** ] 連結，表示成員計數。
3. 按一下 [新增成員]。
4. 輸入您要邀請加入網站之使用者的名稱或電子郵件地址，然後按一下 [ **儲存** ]。

無法從網站新增來賓使用者。 您必須使用 Outlook 網頁版來新增這些檔案。 因此，若要新增並邀請來賓至群組，請按一下 [ **url**  ] 欄中的網站 url，以流覽至網站特有的頁面。 在此頁面上，按一下 **應用程式啟動器** 圖示，然後選取 [ **Outlook** ]。 您可以從該畫面邀請客人加入群組，其程式如下所述。

若要邀請客人加入群組
1. 在 [ **群組** ] 下，按一下您要邀請來賓的群組。
2. 開啟群組連絡人卡片，按一下右上方的 [ **成員** ] 連結 (表示成員計數) 的連結。
3. 按一下 [ **新增成員** ]。
4. 輸入您要邀請之來賓的電子郵件地址，然後按一下 [ **新增** ]。
5. 按一下 **[關閉]** 。
請注意，只有當您不是群組的擁有者時，才需要按一下 [ **關閉** ]，因此不允許將來賓新增至群組。 在這種情況下，將來賓加入群組的要求會轉給群組擁有者以供核准。

## <a name="see-also"></a>另請參閱

[與未驗證使用者共用檔案和資料夾的最佳做法](best-practices-anonymous-sharing.md)

[與來賓共用時限制意外暴露檔案](share-limit-accidental-exposure.md)

[建立安全的來賓共用環境](create-secure-guest-sharing-environment.md)

[使用受管理來賓建立 B2B 外部網路](b2b-extranet.md)

[與 Azure AD B2B 的 SharePoint 和 OneDrive 整合](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
