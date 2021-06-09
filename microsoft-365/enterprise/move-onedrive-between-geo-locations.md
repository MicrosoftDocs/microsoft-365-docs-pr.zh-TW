---
title: 將 OneDrive 網站移至不同的地理位置
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: 尋找將 OneDrive 網站移至不同地理位置的相關資訊，包括如何排程網站移動，以及如何將期望傳遞給使用者。
ms.openlocfilehash: 59b3fb47fd195967e7af056c7a71fb4e736471d1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688231"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a>將 OneDrive 網站移至不同的地理位置 

使用 OneDrive 地理位置移動，您可以將使用者的 OneDrive 移至不同的地理位置。 OneDrive 地理位置移動由 SharePoint 線上管理員或 Microsoft 365 全域管理員執行。 在您開始 OneDrive 地理位置移動之前，請務必通知使用者其 OneDrive 已移動，並建議使用者在移動期間關閉所有檔案。  (如果使用者在移動期間使用 Office 用戶端開啟了檔，則在移動完成時，將需要將檔儲存到新的位置。 ) 如果需要，可以為未來的時間排程移動。

OneDrive 服務使用 Azure Blob 儲存體來儲存內容。 與使用者 OneDrive 相關聯的儲存體 blob 將會從來源移至目的地地理位置 OneDrive 的40天內，以供使用者使用。 當目的地 OneDrive 可用時，就會立即還原使用者 OneDrive 的存取權。

在 OneDrive 異地移動期間 (大約 2-6 小時)，使用者的 OneDrive 會設為唯讀狀態。使用者仍可以透過 OneDrive 同步處理用戶端或 SharePoint Online 中的 OneDrive 網站存取檔案。在完成 OneDrive 異地移動後，若使用者瀏覽至 Microsoft 365 應用程式啟動器中的 OneDrive，將會自動連線到位於目的地理位置的 OneDrive。同步處理用戶端將自動開始新位置的同步處理。

本文所述的程序需要 [Microsoft SharePoint Online PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=35588)。

## <a name="communicating-to-your-users"></a>與使用者溝通

在地理位置之間移動 OneDrive 網站時，請務必將預期要發生的事傳達給使用者。這可以幫助減少使用者的困惑和技術支援中心的電話。在移動前發送電子郵件給使用者，並讓他們知道以下資訊：

- 預計何時將開始移動，並預計需要多久
- OneDrive 新的地理位置以及存取新位置的 URL
- 他們應該關閉文件，並且不要在移動期間編輯檔案
- 檔案權限和共用不會因為移動而變更
- [在多地理位置環境中的使用者體驗](multi-geo-user-experience.md)將有何不同

移動成功完成後，請務必向用戶發送電子郵件，通知他們可以在 OneDrive 中繼續工作。

## <a name="scheduling-onedrive-site-moves"></a>排定 OneDrive 網站移動

您可以事先排定 OneDrive 網站移動 (如本文稍後所述)。建議您從一小群使用者開始驗證工作流程和通訊策略。熟悉此程序後，您就可以如下所述排定移動：

- 您一次最多可以排定 4,000 個移動。
- 您可以在移動開始時排定更多移動，並將最多 4,000 個擱置移動排入佇列和任何指定的時間。
- 可移動的 OneDrive 大小上限為 1 TB。

## <a name="moving-a-onedrive-site"></a>移動 OneDrive 網站

若要執行 OneDrive 地理移動，租使用者管理員必須先將使用者的慣用資料位置 (PDL) 設定為適當的地理位置。 設定 pdl 後，請至少等候24小時，以供 PDL 更新在開始 OneDrive 地理位置移動之前于整個地理位置進行同步處理。

使用 geo 移動指令程式時，請使用下列語法，在使用者目前 OneDrive 地理位置連接至 SPO 服務：

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

例如：若要移動使用者 ' Matt@contosoenergy.onmicrosoft.com ' 的 OneDrive，請在使用者的 OneDrive 位於 eur 地理位置時，連接到 eur SharePoint 系統管理中心：

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![顯示 connect-sposervice Cmdlet的 PowerShell 視窗螢幕擷取畫面](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a>驗證環境

在您開始 OneDrive 異地移動之前，我們建議您先驗證環境。

若要確保所有地理位置相容，請執行：

`Get-SPOGeoMoveCrossCompatibilityStatus`

您會看到地理位置清單，而是否可以在其中移動內容會標示為「相容」。 如果命令傳回「不相容」，請之後再重新驗證狀態。

如果 OneDrive 包含子網站，就無法移動。 您可以使用 Start-SPOUserAndContentMove Cmdlet 以及 -ValidationOnly 參數驗證 OneDrive 是否可以移動：

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

如果 OneDrive 已準備好要移動會傳回成功，如果有防止移動的法務保存狀態或子網站，則會傳回失敗。在您已驗證 OneDrive 移動準備就緒之後，就可以開始移動。

## <a name="start-a-onedrive-geo-move"></a>啟動 OneDrive 異地移動

若要啟動移動，請執行：  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

使用下列參數：

-   _UserPrincipalName_ – OneDrive 即將移動的使用者 UPN。

-   _DestinationDataLocation_ – Geo-Location OneDrive 需要移動的位置。 這應該與使用者的慣用資料位置相同。

比方說，若要將 matt@contosoenergy.onmicrosoft.com 的 OneDrive 從 EUR 移動到 AUS，請執行：

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![顯示 Start-SPOUserAndContentMove Cmdlet 的 PowerShell 視窗螢幕擷取畫面](../media/move-onedrive-between-geo-locations-image2.png)

若要排程稍後進行異地移動，請使用下列參數的其中一個：

-   _PreferredMoveBeginDate_ – 移動會在指定的時間開始。必須以國際標準時間 (UTC) 來指定時間。

-   _PreferredMoveEndDate_ – 移動會以最佳方式在指定的時間前完成。必須以國際標準時間 (UTC) 來指定時間。 

## <a name="cancel-a-onedrive-geo-move"></a>取消 OneDrive 異地移動 

您可以停止地理位置移動使用者的 OneDrive，但前提是移動並未進行中或已完成使用 Cmdlet：

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

其中 _UserPrincipalName_ 是您要停止的 OneDrive 移動之使用者 UPN。

## <a name="determining-current-status"></a>判斷目前狀態

您可以使用 Get-SPOUserAndContentMoveState Cmdlet，檢查您所連接之地理位置的 OneDrive 異地移入或移出的狀態。

下表說明移動狀態。

<table>
<thead>
<tr class="header">
<th align="left"><strong>狀態</strong></th>
<th align="left"><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">NotStarted</td>
<td align="left">移動尚未啟動。</td>
</tr>
<tr class="even">
<td align="left">InProgress (<em>n</em>/4)</td>
<td align="left">移動正在進行中，可能是下列其中一種狀態：驗證 (1/4)、備份 (2/4)、還原 (3/4)、清除 (4/4)。</td>
</tr>
<tr class="odd">
<td align="left">成功</td>
<td align="left">已成功完成移動。</td>
</tr>
<tr class="even">
<td align="left">失敗</td>
<td align="left">移動失敗。</td>
</tr>
</tbody>
</table>

若要尋找特定使用者移動的狀態，請使用 UserPrincipalName 參數：

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

若要尋找您所連接之地理位置的所有移動狀態，請使用 MoveState 參數搭配下列其中一個值： NotStarted、InProgress、成功、失敗、全部。

`Get-SPOUserAndContentMoveState -MoveState <value>`

您也可以新增 `-Verbose` 參數，以取得移動狀態更詳細的說明。

## <a name="user-experience"></a>使用者體驗

如果 OneDrive 移到不同的地理位置，OneDrive 使用者應注意是否有服務中斷。除了在移動期間會發生簡短的唯讀狀態，在移動完成後，現有的連結和權限會如預期般繼續運作。

### <a name="onedrive-for-business"></a>商務用 OneDrive

進行移動時，使用者的 OneDrive 會設定為唯讀。 移動完成之後，當使用者流覽 OneDrive Microsoft 365 應用程式啟動器或網頁瀏覽器時，會將他們的 OneDrive 導向至新的地理位置。

### <a name="permissions-on-onedrive-content"></a>OneDrive 內容的權限

在移動期間和完成後，具有 OneDrive 內容許可權的使用者仍可存取內容。

### <a name="onedrive-sync-client"></a>OneDrive 同步處理用戶端 

OneDrive 異地移動完成後，OneDrive 同步處理用戶端會自動偵測並順暢地傳輸同步處理至 OneDrive 的新位置。使用者不必重新登入或採取任何其他動作。(同步處理用戶端需要 17.3.6943.0625 版或更新的版本。)

如果使用者在進行 OneDrive 異地移動時更新檔案，同步處理用戶端會告知使用者，進行異地移動時上傳的檔案會擱置。

### <a name="sharing-links"></a>共用連結 

在 OneDrive 異地移動完成後，移動的檔案之現有共用連結將會自動重新導向至新的地理位置。

### <a name="onenote-experience"></a>OneNote 體驗 

OneDrive 異地移動完成後，OneNote win32 用戶端和 UWP (通用) 應用程式會自動偵測並順暢地將筆記本同步處理到 OneDrive 的新位置。使用者不必重新登入或採取任何其他動作。使用者唯一可見的指標是，若 OneDrive 異地移動正在進行時，筆記本同步處理會失敗。此體驗適用於下列 OneNote 用戶端版本：

-   OneNote win32 – 版本 16.0.8326.2096 (及更新版本)

-   OneNote UWP – 版本 16.0.8431.1006 (及更新版本)

-   OneNote 行動應用程式 – 版本 16.0.8431.1011 (及更新版本)

### <a name="teams-app"></a>Teams 應用程式

OneDrive 異地移動完成後，使用者可以在 Teams 應用程式上存取其 OneDrive 檔案。此外，在異地移動之前從 OneDrive 透過 Teams 交談共用的檔案，在移動完成後將會繼續運作。

### <a name="onedrive-for-business-mobile-app-ios"></a>商務用 OneDrive 行動應用程式 (iOS) 

在 OneDrive 異地移動完成後，使用者必須在 iOS 行動應用程式上登出並重新登入，以同步處理到 OneDrive 的新位置。

### <a name="existing-followed-groups-and-sites"></a>現有的已追蹤群組和網站

已遵循的網站和群組會顯示在使用者的 OneDrive，不論其地理位置為何。 位於其他地理位置的網站和群組會在個別的索引標籤中開啟。

### <a name="delve-geo-url-updates"></a>Delve地理 URL 更新

只有在將使用者的 OneDrive 移至新的地理位置之後，才會將使用者傳送至其 PDL 的 Delve 地理位置。
