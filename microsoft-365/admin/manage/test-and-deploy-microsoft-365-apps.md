---
title: 測試及部署整合式應用程式入口網站中的合作夥伴的 Microsoft 365 應用程式
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 針對組織中的使用者和群組，從 Microsoft 365 系統管理中心的整合式應用程式入口網站，尋找、測試及部署 Microsoft 和 Microsoft 合作夥伴應用程式。
ms.openlocfilehash: da67cbe5f8b6e5f2da42e1f4b57a55d7d4a768fb
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644473"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>測試及部署整合式應用程式入口網站中的合作夥伴的 Microsoft 365 應用程式

Microsoft 365 系統管理中心可讓您靈活地從單一位置部署單一存放區應用程式、自訂業務線和 Microsoft 365 夥伴應用程式。 您可以在 Microsoft 系統管理中心 > 設定 > 整合型應用程式中存取位置。 透過 Microsoft 合作夥伴從整合的應用程式入口網站尋找、測試及完整部署已購買和授權的應用程式，可提供您組織所需的便利性和優點，讓商務服務定期更新並有效地運作。

如需從組織的合作夥伴購買及授權 Microsoft 365 應用程式的詳細資訊，請參閱 [從 microsoft 365 系統管理中心管理及部署 microsoft 365 應用程式](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)。

如需合作夥伴如何建立這些應用程式的詳細資訊，請參閱 how [to plan a SaaS plan for the 商業性 marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)

整合式應用程式入口網站只有全域系統管理員才能存取，僅供全球範圍的客戶使用。 以及主權和政府雲彩不提供此功能。

整合式應用程式入口網站會顯示應用程式的清單，其中包含部署組織之協力廠商的單一應用程式和 Microsoft 365 應用程式。 只會列出 web 應用程式、SPFx 應用程式、Office 增益集和團隊應用程式。 針對 web 應用程式，我們可以看到2種應用程式。

- SaaS appsource.microsoft.com 中提供的應用程式，並可由系統管理員用來代表組織授與部署。
- 使用 office 增益集連結的 SAML 畫廊應用程式。

## <a name="manage-apps-in-the-integrated-apps-portal"></a>在整合式應用程式入口網站中管理應用程式

您可以從合作夥伴管理已購買及授權的 Microsoft 365 應用程式的測試和部署。

1. 在系統管理中心的左側導覽中，選擇 [ **設定**]，然後選擇 [ **整合式應用程式**]。

2. 選擇 [**可供** 使用的應用程式]**狀態** 的應用程式，以開啟 [**管理**] 窗格。 **可供使用的更多應用程式** 狀態，可讓您知道還有其他尚未部署的 isv 的整合。

3. 在 [ **一覽** ] 索引標籤上，選取 [ **部署**]。 某些應用程式會要求您先新增使用者，才能選擇 [部署]。

4. 選取 [  **使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織**]、[ **特定使用者/群組** ] 或 [ **僅自己**]。 如果您想要等待將應用程式部署至整個組織，也可以選擇 [ **測試部署** ]。 特定的使用者或群組可以是 Microsoft 365 群組、安全性群組或通訊群組。

5. 選取 [ **更新** ]，然後 **完成**。 您現在可以在 [概覽] 索引標籤上選取 [部署]。

6. 查看應用程式資訊，然後選取 [ **部署**]。

7. 在 [部署已完成] 頁面上，選取 [ **完成** ]，並在 [ **概覽** ] 索引標籤上複查測試或完整部署的詳細資料。

8. 若應用程式狀態為 [ **待處理的更新**]，您可以按一下應用程式以開啟 [管理] 窗格，然後更新應用程式。

## <a name="find-published-apps-for-testing-and-full-deployment"></a>尋找已發佈的應用程式進行測試和完整部署

您可以在 [整合式應用程式] 頁面上，找出未出現在清單中的已發佈應用程式，並加以測試及完全部署。 透過從系統管理中心購買及授權應用程式，您可以從單一位置將 Microsoft 和 Microsoft 合作夥伴應用程式新增至您的清單。

1. 在系統管理中心的左側導覽中，選擇 [ **設定**]，然後選擇 [ **整合式應用程式**]。

2. 選取 [ **取得應用** 程式] 以取得應用程式的視圖。

3. 在 [ **Microsoft 365 應用程式** 發佈的應用程式] 頁面上，選擇您想要部署的應用程式，請選擇 [ **立即取得**]。 顯示的應用程式主要是以 SharePoint 架構技術) 為基礎的 Word、PowerPoint、Excel、Outlook 增益集、小組應用程式和 SharePoint 應用程式 (。 接受許可權，然後選取 [ **繼續**]。

5. 在頁面頂端的頁面上，選取 [ **部署** ] 參照為等待部署的郵件。

    如果選取的應用程式連結到 ISV 所提供的 SaaS，則 [設定] 頁面上會出現屬於此連結提供之部分的所有其他應用程式。 如果您選擇部署所有應用程式，請選取 **[下一步]**。 否則，請選取 [ **編輯**]，然後選擇您要部署的應用程式。 某些應用程式會要求您先新增使用者，才能選擇 [ **部署**]。

6. 選取 [ **新增使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織** ] 或 [ **特定使用者/群組** ] 或 [ **僅自己**]。

    特定使用者/群組可以是 Microsoft 365 群組、安全性群組或分散式群組。 如果您想要等待將應用程式部署至整個組織，也可以選擇 [ **測試部署** ]。

7. 選取 **[下一步]** 進入 [ **接受許可權要求** ] 頁面。 列出每個應用程式的應用程式功能和許可權。 若應用程式需要同意，請選取 [ **接受許可權**]。 只有全域系統管理員可以授與同意。

8. 選取 **[下一步** ] 複查部署，然後選擇 **[完成部署]**。 您可以選擇 [**查看此部署**]，從 [**一覽**] 索引標籤中查看部署。 在 Microsoft 365 系統管理中心中，您可以看到每個已部署應用程式的狀態，以及您部署應用程式的日期。

> [!NOTE]
> 若應用程式先前部署自整合的應用程式入口網站，則 **部署類型** 是 **自訂的。**

## <a name="unsupported-scenarios"></a>不支援的案例

在下列情況下，您將無法從整合式應用程式入口網站中的合作夥伴部署單一 store 應用程式或 Microsoft 365 應用程式。

- 同一個增益集會連結至多個 SaaS 提供。
- SaaS 提供會連結至增益集，但不會與 Microsoft Graph 整合，也不會提供任何 AAD 應用程式識別碼。
- SaaS 提供會連結至增益集，但是提供給 Microsoft Graph 整合的 AAD 應用程式識別碼是跨多個 SaaS 提供共用的。

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>上傳自訂的商務應用程式，以進行測試及完整部署

1. 在系統管理中心的左側導覽中，選擇 [ **設定** ]，然後選擇 [ **整合式應用程式**]。

2. 選取 **[上傳自訂應用程式**]。 只支援自訂行的應用程式（適用于 Word、PowerPoint、Excel 和 Outlook）。

3. 上傳裝置中的資訊清單檔案，或加入 URL 連結。 某些應用程式會要求您先新增使用者，才能選擇 [部署]。

4. 選取 [ **新增使用者**]，選擇 [ **這是測試部署**]，然後選擇 [ **整個組織** ] 或 [ **特定使用者/群組** ] 或 [ **僅自己**]。

    特定使用者/群組可以是 Microsoft 365 群組、安全性群組或分散式群組。 如果您想要等待將應用程式部署到整個組織，您也可以選擇 [ **測試部署** ]。

5. 選取 **[下一步]** 進入 [ **接受許可權要求** ] 頁面。 列出應用程式的應用程式功能和許可權。 若應用程式需要同意，請選取 [ **接受許可權**]。 只有全域系統管理員可以授與同意。

6. 選取 **[下一步** ] 複查部署，然後選擇 **[完成部署]**。 您可以選擇 [**查看此部署**]，從 [**一覽**] 索引標籤中查看部署。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>我需要哪些系統管理員角色才能存取整合式應用程式？

只有全域管理員才能存取整合式應用程式。 在其他系統管理員的左側導覽中，整合式應用程式不會顯示。

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>為什麼我會在左導覽的 [設定] 底下看到增益集，但不是集成應用程式？

原因如下：

- 登入的系統管理員是 Exchange admininstrator。
- 客戶位於以及主權雲端，但整合型應用程式體驗可供以及主權雲端客戶使用。

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>我可以從整合式應用程式部署哪些應用程式？

整合式應用程式允許部署 Web 應用程式、小組應用程式、Excel、PowerPoint、Word、Outlook 增益集及 SPFx 應用程式。 針對增益集，整合式應用程式支援部署 Exchange online 信箱，而非內部部署 Exchange 信箱。

### <a name="can-administrators-delete-or-remove-apps"></a>管理員可以刪除或移除應用程式嗎？

是。 全域管理員可以刪除或移除應用程式。

- 從清單視圖中選取應用程式。 **在 [設定**] 索引標籤上，選取要移除的應用程式。  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>以及主權雲端中是否有整合式應用程式？

否。 無法以及主權 cloud 客戶的整合式應用程式。

### <a name="is-integrated-apps-available-in-government-clouds"></a>政府雲端中是否有整合式應用程式？

否。 政府雲端客戶無法使用整合式應用程式。
