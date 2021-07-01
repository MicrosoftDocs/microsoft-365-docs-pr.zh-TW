---
title: 判斷集中式部署的增益集是否適用于您的組織
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: 判斷您的承租人和使用者是否符合需求，讓您可以使用集中式部署來部署 Office 增益集。
ms.openlocfilehash: 5d6f225acb56d1ec092046297d708444bb8d93d2
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227953"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>判斷集中式部署的增益集是否適用于您的組織

「集中部署」是大多數客戶將 Office 增益集部署至組織內之使用者和群組的建議和功能最豐富的方法。 如果您是系統管理員，請使用此指導方針判斷您的組織和使用者是否符合需求，以便您可以使用集中式部署。

[集中式部署] 提供下列優點：

- 全域管理員可以將增益集直接指派給使用者、透過群組將增益集指派給多個使用者，或為組織中的每個人指派增益集。

- 當相關的 Office 應用程式啟動時，增益集就會自動下載。 如果增益集支援增益集命令，增益集會自動出現在 Office 應用程式中的功能區。

- 如果系統管理員關閉或刪除增益集，或從 Azure Active Directory 或將增益集指派給的群組中移除使用者，則使用者不再出現增益集。

集中式部署支援三種桌面平臺 Windows、Mac 和線上 Office 應用程式。 集中式部署也會支援 iOS 和 Android (Outlook 僅限行動增益集) 。

增益集最多可能需要24小時才能顯示所有使用者的用戶端。

## <a name="before-you-begin"></a>開始之前

[！注意] 增益集的集中式部署需要使用者使用 Microsoft 365 企業版 SKUs： E3/E5/F3 或商務 SKUs：商務基本、商務標準、商務進階版 (並使用組織識別碼 Office 登入) ，並具有 Exchange Online 和使用中 Exchange Online 信箱。 您的訂閱目錄必須是 in 或同盟 to Azure Active Directory。
您可以在下列 Office 和 Exchange 中查看特定需求，或使用[集中式部署相容性檢查](#centralized-deployment-compatibility-checker)程式。

[集中式部署] 不支援下列項目：

- 目標鎖定為 Office 2013 中的 Word、Excel 或 PowerPoint 的增益集
- 內部部署目錄服務
- 增益集部署至 Exchange 部署信箱
- 將增益集部署到 SharePoint
- Teams 應用程式
-  (COM) 或 Visual Studio Tools for Office (VSTO) 增益集的元件物件模型部署。
- 不包含 Exchange Online 的 Microsoft 365 部署，例如 SKUs： Microsoft 365 Apps for Business 及 Microsoft 365 Apps Enterprise。

### <a name="office-requirements"></a>Office要求

- 若為 Word、Excel 及 PowerPoint 增益集，您的使用者必須使用下列其中一項：
  - 在 Windows 裝置上，版本1704或更新版本的 Microsoft 365 企業版 SKUs： E3/E5/F3 或商務 SKUs：商務基本、商務標準、商務進階版。
  - 在 Mac 上，版本15.34 或更新版本。

- 若為 Outlook，您的使用者必須使用下列其中一項：
  - 版本1701或更新版本 Microsoft 365 企業版 SKUs： E3/E5/F3 或商務 SKUs：商務基本、商務標準、商務進階版。
  - 版本1808或更新版本 Office 專業增強版2019或 Office 標準版2019。
  - 版本16.0.4494.1000 或更新版本 Office 專業增強版 2016 (msi) 或 Office 標準版 2016 (msi) \*
  - 版本15.0.4937.1000 或更新版本 Office 專業增強版 2013 (msi) 或 Office 標準版 2013 (MSI) \*
  - 版本16.0.9318.1000 或更新版本 Mac 版 Office 2016
- Outlook iOS 的行動的版本2.75.0 或更新版本
- 2.2.145 或更新版本的 Outlook mobile for Android

    * MSI 版本的 Outlook 會在適當的 Outlook 功能區中顯示系統管理員安裝的增益集，而不是「我的增益集」一節。

### <a name="exchange-online-requirements"></a>Exchange Online 需求

Microsoft Exchange 會將增益集資訊清單儲存在貴組織的租用戶中。 部署增益集的系統管理員和接收這些增益集的使用者，必須在支援 OAuth 驗證的 Exchange Online 版本上。

請洽詢貴組織的 Exchange 系統管理員，確認現正使用的設定。您可以使用 [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell Cmdlet，驗證每個使用者的 OAuth 連線。


### <a name="centralized-deployment-compatibility-checker"></a>集中式部署相容性檢查程式

您可以使用集中式部署相容性檢查程式，確認您租使用者上的使用者是否已設定為使用 Word 的集中式部署，Excel 和 PowerPoint。 相容性檢查程式不需要 Outlook 支援。 下載 [相容性檢查](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)程式。

#### <a name="run-the-compatibility-checker"></a>執行相容性檢查程式

1. 啟動提升的 PowerShell.exe 視窗。

2. 執行下列命令：

   ```powershell
   Import-Module O365CompatibilityChecker
   ```

3. 執行 **CompatabilityCheck** 命令：

   ```powershell
   Invoke-CompatibilityCheck
   ```
   這個命令會提示您輸入  *_TenantDomain_* (例如， *TailspinToysIncorporated </span> 。com*) 和  *_TenantAdmin_* 認證 (使用您的全域系統管理員認證) ，然後要求同意。

   > [!NOTE]
   > 根據您租用戶中的使用者人數而定，檢查程式可能需要花費幾分鐘至幾小時。

檢查程式執行完畢後，會產生一個逗號分隔 (.csv) 格式的輸出檔案。 預設會將檔案儲存為 **C:\windows\system32** 。 輸出檔案中包含下列資訊：

- 使用者名稱

- 使用者識別碼 (該使用者的電子郵件地址)

- 已準備好使用集中式部署 (如果其餘項目之值皆為 true)

- Office plan-授權的 Office 計畫

- Office 已啟用 (如果該使用者已啟用 Office)

- 支援的信箱 (如果該使用者擁有啟用 OAuth 的信箱)

> [!NOTE]
> 使用集中式部署 PowerShell 模組時，不支援多重要素驗證。 模組只適用于基本驗證。

## <a name="user-and-group-assignments"></a>使用者和群組指派

[集中式部署] 功能目前支援 Azure Active Directory 所支援的大部分群組，包括 Microsoft 365 群組、通訊群組清單和安全性群組。

> [!NOTE]
> 目前不支援未啟用郵件功能的安全性群組。

集中式部署支援對承租人中個別使用者、群組和所有人的工作分派。 [集中式部署] 支援頂層群組或無父項群組之群組中的使用者，但不支援巢狀群組或有父項群組之群組中的使用者。

看看下列範例，其中晨怡、欣雯和銷售部門群組已被指派增益集。由於西岸銷售部門是巢狀群組，誠雄和又倫未被指派增益集。

![銷售部門圖表](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)


### <a name="find-out-if-a-group-contains-nested-groups"></a>確認群組是否包含巢狀群組

The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook. 如果您在電子郵件的 [ **至** ] 欄位中輸入組名，然後在解析時選取組名，它會顯示其是否包含使用者或嵌套的群組。 In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.

![Outlook 連絡人卡片的 [成員] 索引標籤](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.

![Outlook 連絡人卡片的 [成員資格] 索引標籤](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

或者，您也可以使用 Azure Active Directory 圖形 API 來執行查詢，尋找群組中的群組清單。如需詳細資訊，請參閱[群組上的作業 | 圖形 API 參考](/previous-versions/azure/ad/graph/api/groups-operations)。

### <a name="contacting-microsoft-for-support"></a>連絡 Microsoft 以取得支援

如果您或您的使用者在載入增益集時遇到問題，使用 Office 的 web 應用程式 (Word、Excel 等 ) （已集中部署），您可能需要與 Microsoft 支援部門聯繫 (才能[瞭解](../../business-video/get-help-support.md)) 。 在支援票證中提供下列與 Microsoft 365 環境相關的資訊。

|**平台**|**偵錯資訊**|
|:-----|:-----|
|Office  <br/> | Charles/Fiddler 記錄檔  <br/>  租使用者識別碼 ([瞭解](/onedrive/find-your-office-365-tenant-id))   <br/>  CorrelationID。 查看其中一個 office 頁面的來源，並尋找 [相關性識別碼] 值並傳送給支援：  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|豐富型用戶端 (Windows、Mac)  <br/> | Charles/Fiddler 記錄檔  <br/>  用戶端應用程式的組建編號 (最好是檔案 **/帳戶** 的螢幕擷取畫面)   <br/> |

## <a name="related-content"></a>相關內容

[在系統管理中心中部署增益集](../manage/manage-deployment-of-add-ins.md) (文章) \
[在系統管理中心管理增益集](manage-addins-in-the-admin-center.md) (文章) \
[集中式部署常見問題](../manage/centralized-deployment-faq.md) (文章) \
[將您的商務使用者 Microsoft 365 升級至最新的 Office 用戶端](../setup/upgrade-users-to-latest-office-client.md) (文章) 
 