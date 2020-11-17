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
ms.openlocfilehash: a7a007fdd95638109830a8e3689232060f2b9d8b
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123580"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>使用入口網站啟動計畫程式啟動入口網站

入口網站是您內部網路上的 SharePoint 網站，擁有大量網站檢視者在該網站上取用內容。 以波形的式啟動入口網站是確保使用者能夠存取新 SharePoint 線上入口網站的流暢且具能力的經驗的重要部分。 

以聲波發射是一種重要方式，可讓您在 [線上 SharePoint 中規劃入口網站發佈的計畫](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)，以逐步展示您的入口網站。 入口網站啟動排程程式的設計目的是為了協助您追蹤新入口網站的重新導向，以進行波形/逐步化方法。 在每個波形期間，您可以在每個部署浪潮期間收集使用者意見反應並監控效能。 這具有逐步引入入口網站的優勢，讓您可以選擇暫停及解決問題，再繼續進行下一個浪潮，最後確保使用者的取得積極的經驗。 

重新導向的類型有兩種： 
- 雙向：啟動新的現代 SharePoint 線上入口網站以取代現有的 SharePoint 傳統或新式入口網站 
- 暫時頁面重新導向：使用沒有現有 SharePoint 入口網站的新新式 SharePoint 線上入口網站啟動

入口網站啟動排程器僅可用於啟動新式 SharePoint 線上入口網站，例如通訊網站和現代小組網站。 啟動時間必須預先排程至少7天。 所需的無線電波數目取決於預期的使用者數目。 在排程入口網站之前，必須執行 [SharePoint 工具的頁面診斷](https://aka.ms/perftool) ，以驗證入口網站上的首頁狀況良好。 在入口網站的最後一開始，所有具有網站許可權的使用者都可以存取新網站。 

如需有關啟動成功入口網站的詳細資訊，請遵循 [建立、啟動及維護健康入口網站](https://docs.microsoft.com/sharepoint/portal-health)的基本原則、作法和建議。 

> [!NOTE]
> 這項功能不適用於 Office 365 德國、由世紀運作的 Office 365 (中國) 或 Microsoft 365 美國政府方案。

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>應用程式安裝並聯機至 SharePoint 線上
1. [下載最新的 SharePoint Online 管理命令介面](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

    > [!NOTE]
    > 如果您安裝的是舊版 SharePoint Online 管理命令介面，請移至 [新增或移除程式]，並解除安裝 [SharePoint Online 管理命令介面]。<br>在下載中心頁面上，選擇您的語言，然後按一下 [下載] 按鈕。 系統會請您選擇下載 x64 或 x86 .msi 檔案。 如果您執行的是 64 位元版本的 Windows，請下載 x64 檔案；或如果您執行的是 32 位元版本，請下載 x86 檔案。 如果您不知道，請參閱[我正在執行哪個版本的 Windows 作業系統？](https://support.microsoft.com/help/13443/windows-which-operating-system)。 下載檔案之後，請執行檔案，並按照安裝精靈中的步驟進行。

2. 在 Microsoft 365 以[全域系統管理員或 SharePoint 管理員](/sharepoint/sharepoint-admin-role)的身分登入。 若要了解如何進行，請參閱[開始使用 SharePoint Online 管理命令介面](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。


## <a name="view-any-existing-portal-launch-setups"></a>查看任何現有的入口網站啟動設置

若要查看是否有現有的入口網站啟動設定：

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>在網站上排程入口網站啟動

所需的波形數目取決於您預期的啟動大小。 
- 小於10k 使用者：1個波形
- 10k 至30k 使用者：3波浪 
- 30k + 至100k 使用者：5無線電波
- 超過100k 的使用者：5無線電波，並與您的 Microsoft 帳戶小組聯繫

### <a name="steps-for-bi-directional-redirection"></a>雙向重新定向的步驟

雙向重新導向包括啟動新的現代 SharePoint Online 入口網站取代現有的 SharePoint 傳統或新式入口網站。 主動波形中的使用者將會重新導向至新網站，不論其流覽的是舊的還是新的網站。 嘗試存取新網站的非啟動浪潮中的使用者，將會重新導向至舊網站，直到其 wave 啟動為止。 若要讓系統管理員或擁有者必須存取舊的和新的網站，而不重新導向，請確定它們是以 `WaveOverrideUsers` 參數列出。 

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

### <a name="steps-for-redirection-to-temporary-page"></a>重定向至暫存頁面的步驟

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
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>暫停或重新開機網站上的入口網站啟動

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

## <a name="delete-a-portal-launch-on-the-site"></a>在網站上刪除入口網站啟動
1. 建立入口網站啟動 Wave。
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 執行下列命令，以刪除針對網站排程或進行中的入口網站啟動。

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. 驗證所有使用者都不會進行重新導向。

## <a name="learn-more"></a>深入了解
[在 SharePoint Online 中規劃您的入口網站啟動向外推廣計畫](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
