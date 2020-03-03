---
title: 判斷是否增益集的集中式部署適用於您的組織
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: 決定您的 Office 365 租用戶和使用者是否符合需求，以便您可以使用集中式部署來部署 Office 增益集。
ms.openlocfilehash: 78d87c5539daa77c2babb7ffa36967c5f27e3c10
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362128"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>判斷是否增益集的集中式部署適用於您的組織

若要將 Office 增益集部署到 Office 365 組織中的使用者和群組，[集中式部署] 是建議大多數客戶採用且功能最豐富的方法。 如果您是系統管理員，使用此指導方針來決定如果您的租用戶和使用者符合需求，讓您可以使用集中式部署。
集中式的部署支援 Windows、 Mac、 iOS、 Android 和線上 Office 應用程式。
可能需要增益集的所有使用者的用戶端上顯示最多 12 小時。
  
## <a name="requirements"></a>需求

集中式的部署的增益集需要的使用者都使用 Office 365 專業增強版 （並登入 Office 使用其組織識別碼），並有 Exchange Online 和作用中的 Exchange Online 信箱。 您的訂閱會目錄中，必須是或 Azure Active directory 同盟。
您可以檢視特定的需求適用於 Office 和 Exchange 下，或使用[Office 365 集中式部署相容性檢查程式](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)。

[集中式部署] 不支援下列項目：
  
- 目標鎖定為 Office 2013 中的 Word、Excel 或 PowerPoint 的增益集
    
- 內部部署目錄服務
    
- 將增益集部署到 SharePoint  

- Teams 應用程式
   
- 部署元件物件模型 (COM) 或 Visual Studio Tools for Office (VSTO) 增益集
    
- 不包含 Exchange 的 Office 365 部署，例如 Office 365 商務版

### <a name="office-requirements"></a>Office 需求

- Word、 Excel 及 PowerPoint 增益集，您的使用者必須使用下列其中一項：
  - 在 Windows 裝置上，版本 1704年或更新版本的 Office 365 專業增強版。
  - 在 Mac、 15.34 或更新版本。
      - 在 iOS 上 （僅限 ipad 版），版本 2.9.18010804 或更新版本。
- 針對 Outlook，您的使用者必須使用下列其中一項： 
  - 版本 1701年或更新版本的 Office 365 專業增強版。
  - 版本 1808年或更新版本的 Office 專業增強版 2019年或 Office 標準 2019年。
  - 版本 16.0.4494.1000 或更新版本的 Office Professional Plus 2016 (MSI) 或 Office 標準 2016年 (MSI)\*
  - 版本 15.0.4937.1000 或更新版本的 Office Professional Plus 2013 (MSI) 或 Office Standard 2013 (MSI)\*
  - 版本 16.0.9318.1000 或更新版本的 Mac 版 Office 2016 
- 版本 2.75.0 或更新版本的 iOS 的 Outlook mobile 
- 版本 2.2.145 或更新版本的 Outlook mobile for Android 
    
    * MSI 版本的 Outlook 顯示系統管理員安裝增益集在適當的 Outlook 功能區中，沒有 「 我增益集 」 一節。
    

#### <a name="find-out-if-office-365-proplus-is-installed"></a>確認是否已安裝 Office 365 專業增強版

若要使用 Office 365 專業增強版，使用者必須具有 Office 365 帳戶，且必須已獲指派授權。 如需詳細資訊，請參閱 [Office 365 專業增強版概觀](https://go.microsoft.com/fwlink/p/?linkid=846328)。

偵測如果使用者具有 Office 365 專業增強版安裝，並對它具有最近使用過的最簡單方式是使用 Microsoft Office 啟用報告，其中會出現在 Microsoft 365 系統管理中心內。 報告提供已在最近 7 天、30 天、90 天或 180 天內啟用 Office 365 專業增強版之所有使用者的清單。 對於集中式部署用途而言，Windows 或 Mac 的電腦版啟用數是報告中的重要欄。 您可以將報告匯出到 Excel。 如需有關報告的詳細資訊，請參閱[系統管理中心的 Office 365 報告 - Microsoft Office 啟用](../activity-reports/microsoft-office-activations.md)。
  
如果您不想使用 「 啟用 」 報告，您可以要求使用者開啟 Office 應用程式，例如在其電腦上的 Word，然後選擇 [**檔案** \> **帳戶**。 Under **Product Information**, you should see **Subscription Product** and **Microsoft Office 365 ProPlus**, as shown in the following image.

![Office 應用程式中的產品資訊](../../media/4bff2bb8-0690-4d22-ac1f-b8881807fa39.png)
  
如需 Office 365 專業增強版的相關說明，請參閱 [Office 365 專業增強版的疑難排解提示](https://go.microsoft.com/fwlink/p/?linkid=846339)。


### <a name="exchange-online-requirements"></a>Exchange Online 的需求

Microsoft Exchange 會將增益集資訊清單儲存在貴組織的租用戶中。 部署增益集和收到這些增益集的使用者的系統管理員必須位於 Exchange Online 支援 OAuth 驗證的版本。
  
請洽詢貴組織的 Exchange 系統管理員，確認現正使用的設定。您可以使用 [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell Cmdlet，驗證每個使用者的 OAuth 連線。 


### <a name="office-365-centralized-deployment-compatibility-checker"></a>Office 365 集中式部署相容性檢查程式

使用 Office 365 集中式部署相容性檢查程式，即可確認您租用戶中的使用者是否已設定完畢，可使用適用於 Word、Excel 和 PowerPoint 的集中式部署。相容性檢查程式不需要 Outlook 支援。請在[這裡](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) (英文) 下載相容性檢查程式。
  
#### <a name="run-the-compatibility-checker"></a>執行相容性檢查程式
  
1. 啟動較高的 PowerShell.exe 視窗。
    
2. 執行下列命令：

```powershell
Import-Module O365CompatibilityChecker
```
    
3. 執行**Invoke CompatabilityCheck**命令：

```powershell
Invoke-CompatibilityCheck
```
   會出現提示要求您的*_輸入_*(例如， *TailspinToysIncorporated.onmicrosoft。</span>com*) 與*_TenantAdmin_* 認證 （使用全域系統管理員認證），而且再要求同意。
    
> [!NOTE]
> 根據您租用戶中的使用者人數而定，檢查程式可能需要花費幾分鐘至幾小時。 
  
檢查程式執行完畢後，會產生一個逗號分隔 (.csv) 格式的輸出檔案。 根據預設，檔案會儲存到**C:\windows\system32** 。 輸出檔案中包含下列資訊：
  
- 使用者名稱
    
- 使用者識別碼 (該使用者的電子郵件地址)
    
- 已準備好使用集中式部署 (如果其餘項目之值皆為 true)
    
- Office 方案的 Office sku 授權的計畫
    
- Office 已啟用 (如果該使用者已啟用 Office)
    
- 支援的信箱 (如果該使用者擁有啟用 OAuth 的信箱)


  
## <a name="user-and-group-assignments"></a>使用者和群組指派

[集中式部署] 功能目前支援 Azure Active Directory 支援的大多數群組，包括 Office 365 群組、通訊群組清單和安全性群組。
  
> [!NOTE]
> 目前不支援未啟用郵件功能的安全性群組。 
  
集中式的部署支援指派個別使用者、 群組及所有人租用戶中。 [集中式部署] 支援頂層群組或無父項群組之群組中的使用者，但不支援巢狀群組或有父項群組之群組中的使用者。
   
看看下列範例，其中晨怡、欣雯和銷售部門群組已被指派增益集。由於西岸銷售部門是巢狀群組，誠雄和又倫未被指派增益集。
  
![銷售部門的圖表](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>確認群組是否包含巢狀群組

The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook. 如果您輸入的電子郵件**到**欄位中的群組名稱，然後選取群組名稱解析時，它會顯示包含使用者或巢狀的群組。 In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups. 
  
![Outlook 連絡人卡片的 [成員] 索引標籤](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group. 
  
![成員資格] 索引標籤的 [Outlook 連絡人卡片](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
或者，您也可以使用 Azure Active Directory 圖形 API 來執行查詢，尋找群組中的群組清單。如需詳細資訊，請參閱[群組上的作業 | 圖形 API 參考](https://go.microsoft.com/fwlink/p/?linkid=846342)。
  
### <a name="contacting-microsoft-for-support"></a>連絡 Microsoft 以取得支援

如果您或您的使用者遇到問題時使用 Office 應用程式 （Word、 Excel、 等），在網頁載入增益集集中部署，您可能需要連絡 Microsoft 支援服務 ([了解如何](../contact-support-for-business-products.md))。 並且在支援票證中提供有關您 Office 365 環境的以下資訊。
  
|**平台**|**偵錯資訊**|
|:-----|:-----|
|辦公室  <br/> | Charles/Fiddler 記錄檔  <br/>  租用戶識別碼 ( [了解做法](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))  <br/>  相互關聯識別碼。 檢視的其中一個 office 頁面的來源和尋找相互關聯識別碼值並將其傳送至支援：  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|豐富型用戶端 (Windows、Mac)  <br/> | Charles/Fiddler 記錄檔  <br/>  建立用戶端應用程式的數字 （最好是**檔案/帳戶**的螢幕擷取畫面）  <br/> |
   

