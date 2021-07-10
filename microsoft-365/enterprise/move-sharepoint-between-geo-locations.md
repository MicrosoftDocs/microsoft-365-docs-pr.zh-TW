---
title: 將 SharePoint 網站移至不同的地理位置
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: 瞭解如何將 SharePoint 網站移至多地理位置環境中的不同地理位置，並溝通對使用者所做的變更。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5a49098045dbce94ef1c474497b8da1b397ac0b0
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362351"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a>將 SharePoint 網站移至不同的地理位置

利用 Sharepoint 網站地理移動，您可以將 SharePoint 網站移至您多地理環境內的其他地理位置。

您可以在地理位置之間移動下列類型的網站：

- Microsoft 365群組連線的網站，包括與 Microsoft Teams 相關聯的網站
- 沒有 Microsoft 365 群組關聯的新式網站
- 傳統 SharePoint 網站
- 通訊網站

您必須是全域系統管理員或 SharePoint 系統管理員，才能在地理位置之間移動網站。

SharePoint 網站地理移動會有大約 4 到 6 小時的唯讀時段，視網站內容而定。

## <a name="best-practices"></a>最佳做法

- 請在測試網站上嘗試進行 SharePoint 網站移動，以便熟悉此程序。
- 在排程或執行移動之前驗證是否可以移動該網站。
- 若可能，將跨地理位置網站排程在非上班時段，以減少對使用者的影響。
- 在網站移動之前，與受影響的使用者溝通。

## <a name="communicating-to-your-users"></a>與使用者溝通

在地理位置之間移動 SharePoint 網站時，請務必與網站使用者 (一般是指能夠編輯網站的使用者) 溝通預期將發生的事。 這有助於減少使用者疑惑並打電話給您的技術服務人員。 在移動之前傳送電子郵件給您的網站使用者，讓他們知道下列資訊：

- 預計何時將開始移動，並預計需要多久
- 其網站將前往的新地理位置以及存取新位置的 URL
- 他們應該關閉檔案，並且不要在移動期間編輯檔案。
- 檔案權限和共用不會因為移動而變更。
- 在多地理位置環境中的使用者體驗將有何不同

移動成功完成後，請務必傳送電子郵件給網站的使用者，通知他們可以在其網站中繼續工作。

## <a name="scheduling-sharepoint-site-moves"></a>排程 SharePoint 網站移動

您可以事先排程 SharePoint 網站移動 (本文稍後將描述)。 您可以如下所示排程移動：

- 您一次最多可以排定 4,000 個移動。
- 您可以在移動開始時排定更多移動，並將最多 4,000 個擱置移動排入佇列和任何指定的時間。

若要排程在稍後的時間進行 SharePoint 網站地理移動，當您開始移動時請包含下列其中一個參數：

- `PreferredMoveBeginDate`：移動將可能在這個指定的時間開始。
- `PreferredMoveEndDate`：移動將可能在指定的時間、基於最大努力原則來完成。

這兩個參數都必須以國際標準時間 (UTC) 來指定時間。

## <a name="moving-the-site"></a>移動網站

SharePoint 網站地理移動要求您從網站所在地理位置中的 SharePoint 系統管理員 URL 連線並執行移動。

例如，如果網站 URL 是 <https://contosohealthcare.sharepoint.com/sites/Turbines> ，請在下列位置連接至 SharePoint 管理 URL <https://contosohealthcare-admin.sharepoint.com> ：

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint顯示 Connect-SPOService 命令的線上管理命令介面視窗](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a>驗證環境

建議您在排程任何網站移動之前先進行驗證，以確保可以移動該網站。

我們不支援移動具有下列項目的網站：

- Business Connectivity Services
- InfoPath 表單
- 套用的資訊版權管理 (IRM) 範本

若要確保所有地理位置相容，請執行 `Get-SPOGeoMoveCrossCompatibilityStatus`。 這會顯示您的所有地理位置，以及環境是否與目的地地理位置相容。

若要在您的網站上執行僅限驗證的狀態檢查，請使用 `Start-SPOSiteContentMove` 搭配 `-ValidationOnly` 參數來驗證是否可以移動該網站。 例如：

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

如果可以移動網站，則傳回 *Success*，或如果有任何會封鎖的情況，則傳回 *Fail*。

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a>為沒有任何相關聯 Microsoft 365 群組的網站開始 SharePoint 網站地理移動

根據預設，網站的初始 URL 會變更為目的地地理位置的 URL。 例如：

<https://Contoso.sharepoint.com/sites/projectx> 到 <https://ContosoEUR.sharepoint.com/sites/projectx>

針對沒有 Microsoft 365 群組關聯的網站，您也可以使用 `-DestinationUrl` 參數來將網站重新命名。 例如：

<https://Contoso.sharepoint.com/sites/projectx> 到 <https://ContosoEUR.sharepoint.com/sites/projecty>

若要開始網站移動，請執行：

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![顯示 Start-SPOSiteContentMove Cmdlet 的 PowerShell 視窗螢幕擷取畫面](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a>為 Microsoft 365 群組連線網站進行 SharePoint 網站地理移動

若要移動 Office 365 群組連線網站，全域系統管理員或 SharePoint 系統管理員必須先變更 Office 365 群組的慣用資料位置 (PDL) 屬性。

若要為 Microsoft 365 群組設定 PDL：

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

更新 PDL 之後，您就可以開始進行網站移動：

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a>取消 SharePoint 網站地理移動

只要移動非正在進行或已完成，您即可使用 `Stop-SPOSiteContentMove` Cmdlet 來停止 SharePoint 網站地理移動。

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a>判斷 SharePoint 網站地理移動的狀態

您可以使用下列 Cmdlet 來判斷您所連線的地理位置中網站移動的狀態：

- [Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (非群組連線網站)
- [SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (群組連線的網站) 

使用 `-SourceSiteUrl` 參數來指定您要查看移動狀態的網站。

下表說明移動狀態。

****

|狀態|描述|
|---|---|
|準備好觸發|移動尚未開始。|
|已排程|移動在佇列中，但尚未開始。|
|進行中 (n/4)|移動正在進行中，可能是下列其中一種狀態：驗證 (1/4)、備份 (2/4)、還原 (3/4)、清除 (4/4)。|
|成功|已成功完成移動。|
|失敗|移動失敗。|
|

您也可以套用 `-Verbose` 選項，以查看有關移動的其他資訊。

## <a name="user-experience"></a>使用者體驗

網站使用者應該會在網站移動到不同的地理位置時，注意到些微的中斷。 除了在移動期間的短暫唯讀狀態，移動完成後，現有的連結和權限將繼續如預期般運作。

### <a name="site"></a>網站

移動進行時，網站會設為唯讀狀態。 移動完成後，當使用者按一下書籤或其他網站的連結時，即會將使用者導向新地理位置中的新網站。

### <a name="permissions"></a>權限

具有網站權限的使用者將在移動期間和移動完成後繼續擁有網站的存取權。

### <a name="sync-app"></a>同步處理應用程式

完成網站移動之後，同步處理應用程式會自動偵測同步處理至新的網站位置。 使用者不需重新登入，或採取任何其他動作。 需要 (版本17.3.6943.0625 或更新的同步處理應用程式。 ) 

如果使用者在移動時更新檔案，同步處理應用程式會通知他們在移動進行中時，檔案上傳已擱置。

### <a name="sharing-links"></a>共用連結

當 SharePoint 網站地理移動完成後，移動的檔案之現有共用連結將會自動重新導向至新的地理位置。

### <a name="most-recently-used-files-in-office-mru"></a>Office 中最近用過的檔案 (MRU)

移動完成後，MRU 服務的網站 URL 和其內容 URL 即會更新。 這適用於 Word、Excel 和 PowerPoint。

### <a name="onenote-experience"></a>OneNote 體驗

在網站移動完成後，OneNote win32 用戶端和 UWP (通用) App 將自動偵測並順暢地將筆記本同步處理到新位置。 使用者不需重新登入，或採取任何其他動作。 對使用者顯示的唯一指標為，當網站移動進行時，筆記本同步處理會失敗。 此體驗會在下列 OneNote 用戶端版本上提供：

- OneNote win32 – 版本 16.0.8326.2096 (及更新版本)
- OneNote UWP – 版本 16.0.8431.1006 (及更新版本)
- OneNote 行動應用程式 – 版本 16.0.8431.1011 (及更新版本)

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>Teams (適用於 Microsoft 365 群組連線網站)

SharePoint 網站地理移動完成後，使用者將能在 Teams App 上存取其 Microsoft 365 群組網站的檔案。 此外，於地理移動之前從其網站透過 Teams 聊天共用的檔案，在移動完成後，將繼續運作。

### <a name="sharepoint-mobile-app-iosandroid"></a>SharePoint 行動裝置 App (iOS/Android)

SharePoint 行動裝置 App 可跨地理位置相容，且能偵測網站的新地理位置。

### <a name="sharepoint-workflows"></a>SharePoint 工作流程

網站移動後需要重新發佈 SharePoint 2013 工作流程。 SharePoint 2010 工作流程應該會繼續正常運作。

### <a name="apps"></a>App

如果您要移動的網站具有 App，您必須在網站的新地理位置將 App 重新具現化，因為 App 和其連線在目的地理位置中可能無法使用。

### <a name="flow"></a>流程

在多數情況下，在 SharePoint 網站地理移動後，流程將繼續運作。 建議您在移動完成後先測試這些流程。

### <a name="powerapps"></a>PowerApps

需要在目的地位置重新建立 PowerApps。

### <a name="data-movement-between-geo-locations"></a>地理位置之間的資料移動

SharePoint 將內容放置在 Azure Blob 儲存體，而將與網站和其檔案相關聯的中繼資料則儲存在 SharePoint 內。 在將網站從來源地理位置移動到目的地地理位置後，服務也將移動其相關聯的 Blob 儲存體。 Blob 儲存體移動大約需要 40 天才能完成。