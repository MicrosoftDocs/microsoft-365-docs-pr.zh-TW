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
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999566"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>使用入口網站啟動計畫程式啟動入口網站

您可以先驗證租使用者管理員為新入口網站設定聲波的能力，以啟動入口網站的入口網站啟動程式。 然後，系統管理員可以根據主動無線電波中的使用者是否存在，來驗證要求重新定向。

如需有關啟動成功入口網站的詳細資訊，請遵循 [建立、啟動及維護健康入口網站](https://go.microsoft.com/fwlink/?linkid=2105838)的基本原則、作法和建議。 

## <a name="app-setup"></a>應用程式設定
1. 如果有現有 `Microsoft.Online.SharePoint.PowerShell` 從您的機器透過控制台，請卸載。
2. 在 PowerShell 通過 `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` 。

## <a name="connect-to-sharepoint-online"></a>連線至 SharePoint Online
1. 在 Windows 中開啟 [SharePoint 線上管理命令](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 介面。
2. 以系統管理員身分連線到您的租使用者。
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  出現提示時提供您的密碼。

## <a name="command-to-get-an-existing-setup"></a>用於取得現有安裝程式的命令

若要查看現有的入口網站啟動設定：

1. 傳遞 `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` 。
2. `-DisplayFormat Raw`如果您想要看到格式化為原始輸入格式的 wave 集合，請傳遞其他參數。

## <a name="commands-for-bi-directional-redirection"></a>雙向重新定向的命令

若要以分段方式將舊網站使用者遷移至新網站，請執行下列動作：

1. 建立入口網站啟動無線電波。
   - 這僅適用于早期版本測試階段。
   - 若要立即測試變更的影響，請確定第一個波形 `LaunchDateUtc` 已設定為目前日期。 如果您沒有提供此旗標，則會收到錯誤訊息。 發生此錯誤的原因是，在實際執行中的啟動必須預先排程至少7天。

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 完整驗證。
  - 重新導向必須花5分鐘的時間才能完成整個服務的設定，因此請稍候，再繼續進行。
  - 如果您以指定的使用者登入 `WaveOverrideUsers` ，則不會有任何變更。 您應該在所流覽的網站上進行。
  - 登入 *SG1 觀眾* 的使用者。
    - 流覽至舊的網站，您應該重新導向至新的網站。
    - 流覽至新的網站，您應該保留在新的網站。
    - 使用 *查看者 SG2* 中的使用者登入，並流覽至舊的網站，並停留在舊網站。
    - 流覽至新的網站，您應該重新導向至舊的網站。

3. 暫停入口網站啟動。
  - 如果您需要暫停啟動波形，您可以將其暫停為 "x" 天。 將旗標設定 `Status` 為 pause 可避免所有即將到來的 wave progressions。 
  - `Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - 這會驗證所有使用者都已重新導向到舊網站。

4. 重新開機入口網站啟動進展。 
  - `Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - 驗證重新定向現在已還原。

5. 刪除入口網站啟動設定。
  - `Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.
  - 驗證所有使用者都不會進行重新導向。

## <a name="commands-for-redirection-to-temporary-page"></a>重新導向至暫存頁面的命令

如果您沒有舊版網站，而且想要在新的入口網站頁面上忽略不在 wave 中的使用者，請遵循下列步驟。

若要在任何網站中建立暫存頁面：

1. 建立入口網站啟動 Wave。
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 完整驗證。

  - 請等候五分鐘之後繼續，因為動作可能需要最多五分鐘才能完成。
  - 使用 [ *查看者* ] 的一部分使用者記錄 SG1 及：
     - 流覽至新的網站，您應該保留在新的網站。
     - 流覽至 [temp] 頁面，您應該停留在 [temp] 頁面上。
  - 記錄屬於 [ *查看者] SG2* 的使用者，並：
     - 流覽至新的網站，您應該重新導向至 [temp] 頁面。
     - 流覽至 [temp] 頁面，您應該停留在 [temp] 頁面上。

3. 刪除入口網站啟動設定。
  - `Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - 驗證所有使用者都不會進行重新導向。

## <a name="learn-more"></a>深入了解
[在 SharePoint Online 中規劃您的入口網站啟動向外推廣計畫](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)