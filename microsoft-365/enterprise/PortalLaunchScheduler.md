---
title: 使用入口網站啟動計畫程式啟動入口網站
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: 本文說明如何使用入口網站啟動排程器來啟動入口網站
ms.openlocfilehash: fdf92f2bbdfb673f1db446b562e941d61679fa9a
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694350"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a>使用 SharePoint 入口網站啟動計畫程式啟動入口網站

入口網站是內部網路上的 SharePoint 通訊網站，它是高流量–一部星期內從10000到100000查看者的網站。 使用入口網站啟動排程器啟動您的入口網站，以確保使用者在存取新的 SharePoint 入口網站時有光滑的觀賞體驗。
<br>
<br>
入口網站啟動排程器的設計目的是為了協助您遵循分階段的處理常式，並以波形方式批次處理檢視器並管理新入口網站的 URL 重新導向。 在啟動每個 wave 時，您可以收集使用者意見反應、監控入口效能，並暫停啟動以解決問題，再繼續進行下一個波形。 深入瞭解如何[在 SharePoint 中規劃入口網站啟動](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)。 

**有兩種類型的重定向：**

- **雙向**：啟動新的現代 SharePoint 入口網站以取代現有的 SharePoint 傳統或新式入口網站
- 重新 **導向至暫存頁面**：啟動新的現代 SharePoint 入口網站（沒有現有的 SharePoint 入口網站）

在發射過程中，網站許可權必須與波形分開設定。 例如，如果您要發行整個組織的入口網站，您可以將許可權設定為「外部使用者以外的所有人」，然後使用安全性群組將您的使用者分隔成波形。 將安全性群組新增至 wave 不會讓該安全性群組存取網站。 


> [!NOTE]
> - 從 2021 2021 年5月開始的目標版本客戶的「**設定** SharePoint 面板」首頁，可以存取這項功能，並將在年7月後取得給所有客戶使用。
> - 目前可以使用此工具的 PowerShell 版本
> - 這項功能只可用於現代的 SharePoint 通訊網站上
> - 您必須具有網站的網站擁有者許可權，才可自訂及排程入口網站的啟動
> - 啟動之前必須至少排程7天，且每個波形可以持續1到7天
> - 所需的波形數目會根據預期的使用者數目自動決定 
> - 在排程入口網站啟動之前，必須執行[SharePoint 工具的頁面診斷](https://aka.ms/perftool)，以確認網站的首頁健康情況良好
> - 在啟動結束時，具有網站許可權的所有使用者都可以存取新網站
> - 如果您的組織使用的是[Viva](https://docs.microsoft.com/SharePoint/viva-connections)連線，使用者可能會在 Microsoft Teams 應用程式欄中看到您組織的圖示，但是當圖示已選取時，使用者將無法存取入口網站，直到其 wave 啟動為止
> - 這項功能不適用於 Office 365 德國、由世紀 (中國) Office 365 運作，或 Microsoft 365 美國政府方案。

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a>瞭解入口網站啟動排程器選項之間的差異：

原來的入口網站啟動只能透過 SharePoint PowerShell 排程。 現在，您有兩個選項可協助您排程和管理入口網站的啟動。 深入瞭解這兩種工具之間的主要差異：

**SharePointPowerShell 版本：**

- 需要有系統管理員認證，才能使用[SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) 
- 一個波形的最低需求 
- 根據協調世界時 (UTC) 時區排程您的啟動

**產品內版本：**

- 需要網站擁有者認證 
- 雙波浪的基本需求
- 根據 [區域設定] 中所示的入口網站時區，排程您的啟動



## <a name="get-started-using-the-portal-launch-scheduler"></a>開始使用入口網站啟動調度程式

1.  在使用入口網站啟動排程器工具之前，請先新增需要透過 **網站** 擁有者、網站成員或訪客 [存取此網站的所有使用者](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658)。

2.  接著，以下列其中一種方式存取入口網站啟動排程器，以開始排程入口網站的啟動：

    **選項 1**：在首頁版本3.0 之前，您可以編輯或重新發佈首頁或更新至首頁，直到首頁版本-您將會收到使用入口網站啟動排程器工具的提示。 選取 [排程 **啟動** ]，以排程。 或選取 [重新 **發佈** ] 以重新發佈您的頁面編輯，而不排程啟動。
    
    ![重新發佈首頁時，提示使用入口網站啟動排程器的影像](../media/portal-launch-republish-2.png)
    
    **選項 2**：您可以在任何時候流覽至 SharePoint 的通訊網站首頁，選取 [**設定**]，然後 **排程網站啟動** 以排程入口網站的啟動。
    
    ![[設定] 窗格的圖像，其排程網站啟動已反白顯示](../media/portal-launch-settings-2.png)

3.  接下來，請先確認入口網站的健康情況分數，並在需要時使用 [SharePoint 工具的頁面診斷](https://aka.ms/perftool)，對入口網站進行改進，直到您的入口網站收到 **良好** 的分數為止。 然後，選取 **[下一步]**。

    ![入口網站啟動調度程式工具的影像](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > 無法從入口網站啟動排程器編輯網站名稱和描述，但可以從首頁上選取 [**設定**]，然後選取 [**網站資訊**] 以加以變更。
 
4.  從下拉式清單中選取 **期望的使用者數目** 。 此圖代表最可能需要網站存取權的使用者人數。 入口網站啟動排程器會根據預期的使用者，自動判斷波形數目的理想專案如下：
    
    - 小於10k 使用者：兩個波浪
    - 10k 至30k 使用者：三聲波 
    - 30k + 至100k 使用者：五台聲波
    - 超過100k 的使用者：5個無線電波，您透過使用啟動入口網站中所列的步驟，與您的 Microsoft 聯繫一節。 

5.  然後，判斷所需的重新 **導向類型** ：

    **選項1：將使用者傳送至現有的 SharePoint 頁面 (雙向)** –使用此選項啟動新的現代 SharePoint 入口網站以取代現有的 SharePoint 入口網站。 主動波形中的使用者將會重新導向至新網站，不論其流覽的是舊的還是新的網站。 嘗試存取新網站的非啟動浪潮中的使用者，將會重新導向至舊網站，直到其 wave 啟動為止。
    
    > [!NOTE] 
    > 使用雙向選項時，排程啟動的人員也必須具有其他 SharePoint 入口網站的網站擁有者許可權。
       
    **選項2：將使用者傳送至自動產生的暫存頁面 (暫時頁面** 重新導向) –若不存在現有的 SharePoint 入口網站，應使用暫存頁面重新導向。 使用者會被導向至新的現代 SharePoint 入口網站，而且如果使用者處於尚未啟動的 wave，將會重新導向至暫存頁面。
    
    **選項3：將使用者傳送至外部頁面** –在使用者的 wave 啟動之前，提供暫時登陸頁面體驗的外部 URL。
    
6.  將您的物件分解成波形。 每個浪潮新增最多20個安全性群組。 在每次聲波啟動之前，可以編輯波形詳細資料。 每個浪潮至少可以一天 (24 小時) 至少7天。 這可讓 SharePoint 和您的技術環境有機會 acclimate 及擴充至大量的網站使用者。 當您透過 UI 排程啟動時，時區是以網站的區域設定為基礎。 

    >[!NOTE] 
    > - 入口網站啟動排程器的預設值會自動設為至少2個波形。 不過，此工具的 PowerShell 版本將允許1個波形。
    >  - 此版本的入口網站啟動計畫程式不支援 Microsoft 365 群組。

7. 決定誰需要立即查看網站，並將其資訊輸入 [豁免的 **使用者** ] 欄位。 這些使用者會從波形中排除，不會在發射之前、期間或之後重新導向。

8.  確認入口網站啟動詳細資料並選取 **排程**。 開始排程後，對 SharePoint 入口網站首頁所做的任何變更，都必須先接收正常的診斷結果，再繼續進行入口網站啟動。

### <a name="launch-portal-with-over-100k-users"></a>使用超過100k 使用者的啟動入口網站

如果您打算移轉超過 100TB，請按照以下列出的步驟提交支援要求。 請確認包含所有要求的資訊。

請遵循下列步驟：
1. 瀏覽到 https://admin.microsoft.com
2. 確定您使用新的系統管理中心預覽。
3. 在左側瀏覽窗格中，選取 [支援]，然後選取 [新增服務要求]。 


   這會在您的畫面右側啟動「需要協助嗎？」窗格。

4.  在 [**簡短描述您的問題**] 區域中，輸入「使用100k 使用者的發行 SharePoint 入口網站」。</br>
5. 選取 [連絡支援部門]。
6. 在 [**描述**] 底下，輸入「啟動含100k 使用者的 SharePoint 入口網站」。 
7. 填寫其餘資訊，然後選取 [與我聯繫]。
8. 建立票證之後，請確定提供支援代理人以下資訊：
- 啟動入口網站 URL 
- 預期的使用者人數
- 預估啟動時間 

## <a name="make-changes-to-a-scheduled-portal-launch"></a>對已排程的入口網站啟動進行變更

您可以針對每個波浪形編輯啟動詳細資料，直到波形的啟動日期為止。 

1.  若要編輯入口網站啟動詳細資料，請流覽至 **設定**，然後選取 [**排程網站啟動**]。
2.  然後，選取 [ **編輯**]。
3.  完成編輯後，請選取 [ **更新**]。


## <a name="delete-a-scheduled-portal-launch"></a>刪除排程的入口網站啟動

您可以在任何時間（即使已啟動某些聲波）使用入口網站啟動排程工具，也可以取消或刪除啟動排程。

1.  若要取消入口網站的啟動，請流覽至 [**設定** 及 **排程網站啟動**]。

2.  然後，選取 [ **刪除** ]，當您看到下列的訊息時，請選取 **[刪除]** 。

    ![入口網站啟動調度程式工具的影像](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a>使用 PowerShell 入口網站啟動排程器

SharePoint 入口網站啟動排程器工具最初隻可透過[SharePoint](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)取得，PowerShell 而且會繼續透過 PowerShell 使用此方法的客戶取得支援。 本文開頭的相同附注適用于這兩個版本的入口網站啟動排程器。 

>[!NOTE]
> 您必須具有系統管理員許可權，才能使用 SharePoint PowerShell。
> 在 PowerShell 中建立的入口網站啟動詳細資料將會出現，而且可以在 SharePoint 中的新入口網站啟動排程器工具中管理。


### <a name="app-setup-and-connecting-to-sharepoint-online"></a>應用程式安裝並聯機至 SharePoint 線上
1. [下載最新的 SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

    > [!NOTE]
    > 如果您安裝的是舊版 SharePoint Online 管理命令介面，請移至 [新增或移除程式]，並解除安裝 [SharePoint Online 管理命令介面]。<br>在下載中心頁面上，選擇您的語言，然後按一下 [下載] 按鈕。 系統會請您選擇下載 x64 或 x86 .msi 檔案。 如果您執行的是 64 位元版本的 Windows，請下載 x64 檔案；或如果您執行的是 32 位元版本，請下載 x86 檔案。 如果您不知道，請參閱[我正在執行哪個版本的 Windows 作業系統？](https://support.microsoft.com/help/13443/windows-which-operating-system)。 下載檔案之後，請執行檔案，並按照安裝精靈中的步驟進行。

2. 在 Microsoft 365 以[全域系統管理員或 SharePoint 管理員](/sharepoint/sharepoint-admin-role)的身分登入。 若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。


### <a name="view-any-existing-portal-launch-setups"></a>查看任何現有的入口網站啟動設置

若要查看是否有現有的入口網站啟動設定：

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a>在網站上排程入口網站啟動

所需的波形數目取決於您預期的啟動大小。 
- 小於10k 使用者：一個波形
- 10k 至30k 使用者：三聲波 
- 30k + 至100k 使用者：五台聲波
- 超過100k 的使用者：五台聲波，並與您的 Microsoft 帳戶小組聯繫

#### <a name="steps-for-bidirectional-redirection"></a>雙向重新定向的步驟

雙向重新導向包括啟動新的現代 SharePoint Online 入口網站取代現有的 SharePoint 傳統或新式入口網站。 主動波形中的使用者將會重新導向至新網站，不論其流覽的是舊的還是新的網站。 嘗試存取新網站的非啟動浪潮中的使用者，將會重新導向至舊網站，直到其 wave 啟動為止。 

我們只支援舊網站上的預設首頁與新網站上的預設首頁之間的重定向。 若要讓系統管理員或擁有者必須存取舊的和新的網站，而不重新導向，請確定它們是以 `WaveOverrideUsers` 參數列出。

若要以分段方式將現有的 SharePoint 網站中的使用者遷移至新的 SharePoint 網站，請執行下列動作：

1. 執行下列命令以指定入口啟動波形。
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   範例：

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. 完整驗證。 重新導向會花5-10 分鐘的時間來完成整個服務的設定。 

#### <a name="steps-for-redirection-to-temporary-page"></a>重定向至暫存頁面的步驟

當不存在現有的 SharePoint 入口網站時，應使用暫存頁面重新導向。 使用者會以分段的方式，將使用者導向至新的現代 SharePoint Online 入口網站。 如果使用者處於尚未啟動的 wave，將會重新導向至臨時頁面 (任何 URL) 。 

1. 執行下列命令以指定入口啟動波形。
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   範例：

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. 完整驗證。 重新導向會花5-10 分鐘的時間來完成整個服務的設定。 

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a>暫停或重新開機網站上的入口網站啟動

1. 若要暫停進行中的入口網站啟動，並暫時避免發生即將進行的 wave progressions，請執行下列命令：

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. 驗證是否所有使用者都已重新導向到舊網站。 

3. 若要重新開機已暫停的入口網站啟動，請執行下列命令：

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. 驗證重新定向現在已還原。 

### <a name="delete-a-portal-launch-on-the-site"></a>在網站上刪除入口網站啟動

1. 執行下列命令，以刪除針對網站排程或進行中的入口網站啟動。

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. 驗證所有使用者都不會進行重新導向。

## <a name="learn-more"></a>深入了解

[在 SharePoint Online 中規劃您的入口網站啟動向外推廣計畫](./planportallaunchroll-out.md)

[規劃您的通訊網站](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
