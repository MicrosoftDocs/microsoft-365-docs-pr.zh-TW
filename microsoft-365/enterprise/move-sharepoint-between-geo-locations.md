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
ms.openlocfilehash: e96c422b1d2685c9fe3d4c8c45aa8437a6776621
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688237"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a><span data-ttu-id="af431-103">將 SharePoint 網站移至不同的地理位置</span><span class="sxs-lookup"><span data-stu-id="af431-103">Move a SharePoint site to a different geo location</span></span>

<span data-ttu-id="af431-104">利用 Sharepoint 網站地理移動，您可以將 SharePoint 網站移至您多地理環境內的其他地理位置。</span><span class="sxs-lookup"><span data-stu-id="af431-104">With SharePoint site geo move, you can move SharePoint sites to other geo locations within your multi-geo environment.</span></span>

<span data-ttu-id="af431-105">您可以在地理位置之間移動下列類型的網站：</span><span class="sxs-lookup"><span data-stu-id="af431-105">The following types of site can be moved between geo locations:</span></span>

- <span data-ttu-id="af431-106">Microsoft 365 群組連線網站</span><span class="sxs-lookup"><span data-stu-id="af431-106">Microsoft 365 Group-connected sites</span></span>
- <span data-ttu-id="af431-107">沒有 Microsoft 365 群組關聯的新式網站</span><span class="sxs-lookup"><span data-stu-id="af431-107">Modern sites without a Microsoft 365 Group association</span></span>
- <span data-ttu-id="af431-108">傳統 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="af431-108">Classic SharePoint sites</span></span>
- <span data-ttu-id="af431-109">通訊網站</span><span class="sxs-lookup"><span data-stu-id="af431-109">Communication sites</span></span>

<span data-ttu-id="af431-110">您必須是全域系統管理員或 SharePoint 系統管理員，才能在地理位置之間移動網站。</span><span class="sxs-lookup"><span data-stu-id="af431-110">You must be a Global Administrator or SharePoint Administrator to move a site between geo locations.</span></span>

<span data-ttu-id="af431-111">SharePoint 網站地理移動會有大約 4 到 6 小時的唯讀時段，視網站內容而定。</span><span class="sxs-lookup"><span data-stu-id="af431-111">There is a read-only window during the SharePoint site geo move of approximately 4-6 hours, depending on site contents.</span></span>
 
## <a name="best-practices"></a><span data-ttu-id="af431-112">最佳做法</span><span class="sxs-lookup"><span data-stu-id="af431-112">Best practices</span></span>

- <span data-ttu-id="af431-113">請在測試網站上嘗試進行 SharePoint 網站移動，以便熟悉此程序。</span><span class="sxs-lookup"><span data-stu-id="af431-113">Try a SharePoint site move on a test site to get familiar with the procedure.</span></span> 
- <span data-ttu-id="af431-114">在排程或執行移動之前驗證是否可以移動該網站。</span><span class="sxs-lookup"><span data-stu-id="af431-114">Validate whether the site can be moved prior to scheduling or performing the move.</span></span> 
- <span data-ttu-id="af431-115">若可能，將跨地理位置網站排程在非上班時段，以減少對使用者的影響。</span><span class="sxs-lookup"><span data-stu-id="af431-115">When possible schedule cross-geo sites moves for outside business hours to reduce user impact.</span></span>
- <span data-ttu-id="af431-116">在網站移動之前，與受影響的使用者溝通。</span><span class="sxs-lookup"><span data-stu-id="af431-116">Communicate with impacted users prior to the sites move.</span></span> 

## <a name="communicating-to-your-users"></a><span data-ttu-id="af431-117">與使用者溝通</span><span class="sxs-lookup"><span data-stu-id="af431-117">Communicating to your users</span></span>

<span data-ttu-id="af431-118">在地理位置之間移動 SharePoint 網站時，請務必與網站使用者 (一般是指能夠編輯網站的使用者) 溝通預期將發生的事。</span><span class="sxs-lookup"><span data-stu-id="af431-118">When moving SharePoint sites between geo locations, it's important to communicate to the sites' users (generally anyone with the ability to edit the site) what to expect.</span></span> <span data-ttu-id="af431-119">這有助於減少使用者疑惑並打電話給您的技術服務人員。</span><span class="sxs-lookup"><span data-stu-id="af431-119">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="af431-120">在移動之前傳送電子郵件給您的網站使用者，讓他們知道下列資訊：</span><span class="sxs-lookup"><span data-stu-id="af431-120">Email your sites' users before the move and let them know the following information:</span></span>

- <span data-ttu-id="af431-121">預計何時將開始移動，並預計需要多久</span><span class="sxs-lookup"><span data-stu-id="af431-121">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="af431-122">其網站將前往的新地理位置以及存取新位置的 URL</span><span class="sxs-lookup"><span data-stu-id="af431-122">What geo location their site is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="af431-123">他們應該關閉檔案，並且不要在移動期間編輯檔案。</span><span class="sxs-lookup"><span data-stu-id="af431-123">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="af431-124">檔案權限和共用不會因為移動而變更。</span><span class="sxs-lookup"><span data-stu-id="af431-124">File permissions and sharing will not change because of the move.</span></span>
- <span data-ttu-id="af431-125">在多地理位置環境中的使用者體驗將有何不同</span><span class="sxs-lookup"><span data-stu-id="af431-125">What to expect from the user experience in a multi-geo environment</span></span>

<span data-ttu-id="af431-126">移動成功完成後，請務必傳送電子郵件給網站的使用者，通知他們可以在其網站中繼續工作。</span><span class="sxs-lookup"><span data-stu-id="af431-126">Be sure to send your sites' users an email when the move has successfully completed informing them that they can resume working on their sites.</span></span>

## <a name="scheduling-sharepoint-site-moves"></a><span data-ttu-id="af431-127">排程 SharePoint 網站移動</span><span class="sxs-lookup"><span data-stu-id="af431-127">Scheduling SharePoint site moves</span></span>

<span data-ttu-id="af431-128">您可以事先排程 SharePoint 網站移動 (本文稍後將描述)。</span><span class="sxs-lookup"><span data-stu-id="af431-128">You can schedule SharePoint site moves in advance (described later in this article).</span></span> <span data-ttu-id="af431-129">您可以如下所示排程移動：</span><span class="sxs-lookup"><span data-stu-id="af431-129">You can schedule moves as follows:</span></span>

- <span data-ttu-id="af431-130">您一次最多可以排定 4,000 個移動。</span><span class="sxs-lookup"><span data-stu-id="af431-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="af431-131">您可以在移動開始時排定更多移動，並將最多 4,000 個擱置移動排入佇列和任何指定的時間。</span><span class="sxs-lookup"><span data-stu-id="af431-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
 
<span data-ttu-id="af431-132">若要排程在稍後的時間進行 SharePoint 網站地理移動，當您開始移動時請包含下列其中一個參數：</span><span class="sxs-lookup"><span data-stu-id="af431-132">To schedule a SharePoint site geo move for a later time, include one of the following parameters when you start the move:</span></span>
- <span data-ttu-id="af431-133">`PreferredMoveBeginDate`：移動將可能在這個指定的時間開始。</span><span class="sxs-lookup"><span data-stu-id="af431-133">`PreferredMoveBeginDate` – The move will likely begin at this specified time.</span></span>
- <span data-ttu-id="af431-134">`PreferredMoveEndDate`：移動將可能在指定的時間、基於最大努力原則來完成。</span><span class="sxs-lookup"><span data-stu-id="af431-134">`PreferredMoveEndDate` – The move will likely be completed by this specified time, on a best effort basis.</span></span> 

<span data-ttu-id="af431-135">這兩個參數都必須以國際標準時間 (UTC) 來指定時間。</span><span class="sxs-lookup"><span data-stu-id="af431-135">Time must be specified in Coordinated Universal Time (UTC) for both parameters.</span></span>

## <a name="moving-the-site"></a><span data-ttu-id="af431-136">移動網站</span><span class="sxs-lookup"><span data-stu-id="af431-136">Moving the site</span></span>

<span data-ttu-id="af431-137">SharePoint 網站地理移動要求您從網站所在地理位置中的 SharePoint 系統管理員 URL 連線並執行移動。</span><span class="sxs-lookup"><span data-stu-id="af431-137">SharePoint site geo move requires that you connect and perform the move from the SharePoint Admin URL in the geo location where the site is.</span></span>

<span data-ttu-id="af431-138">例如，如果網站 URL 是 https://contosohealthcare.sharepoint.com/sites/Turbines，請連線到位於 https://contosohealthcare-admin.sharepoint.com: 的 SharePoint 系統管理員 URL</span><span class="sxs-lookup"><span data-stu-id="af431-138">For example, if the site URL is https://contosohealthcare.sharepoint.com/sites/Turbines, connect to the SharePoint Admin URL at https://contosohealthcare-admin.sharepoint.com:</span></span>

`Connect-SPOService -url https://contosohealthcare-admin.sharepoint.com`

![](../media/move-onedrive-between-geo-locations-image1.png)
 
### <a name="validating-the-environment"></a><span data-ttu-id="af431-139">驗證環境</span><span class="sxs-lookup"><span data-stu-id="af431-139">Validating the environment</span></span>

<span data-ttu-id="af431-140">建議您在排程任何網站移動之前先進行驗證，以確保可以移動該網站。</span><span class="sxs-lookup"><span data-stu-id="af431-140">We recommend that before scheduling any site move, you perform a validation to ensure that the site can be moved.</span></span>

<span data-ttu-id="af431-141">我們不支援移動具有下列項目的網站：</span><span class="sxs-lookup"><span data-stu-id="af431-141">We do not support moving sites with:</span></span>
-    <span data-ttu-id="af431-142">Business Connectivity Services</span><span class="sxs-lookup"><span data-stu-id="af431-142">Business Connectivity Services</span></span>
-    <span data-ttu-id="af431-143">InfoPath 表單</span><span class="sxs-lookup"><span data-stu-id="af431-143">InfoPath forms</span></span> 
- <span data-ttu-id="af431-144">套用的資訊版權管理 (IRM) 範本</span><span class="sxs-lookup"><span data-stu-id="af431-144">Information Rights Management (IRM) templates applied</span></span>

<span data-ttu-id="af431-145">若要確保所有地理位置相容，請執行 `Get-SPOGeoMoveCrossCompatibilityStatus`。</span><span class="sxs-lookup"><span data-stu-id="af431-145">To ensure all geo locations are compatible, run `Get-SPOGeoMoveCrossCompatibilityStatus`.</span></span> <span data-ttu-id="af431-146">這會顯示您的所有地理位置，以及環境是否與目的地地理位置相容。</span><span class="sxs-lookup"><span data-stu-id="af431-146">This will display all your geo locations and whether the environment is compatible with the destination geo location.</span></span>

<span data-ttu-id="af431-147">若要在您的網站上執行僅限驗證的狀態檢查，請使用 `Start-SPOSiteContentMove` 搭配 `-ValidationOnly` 參數來驗證是否可以移動該網站。</span><span class="sxs-lookup"><span data-stu-id="af431-147">To perform a validation-only check on your site, use `Start-SPOSiteContentMove` with the `-ValidationOnly` parameter to validate if the site is able to be moved.</span></span> <span data-ttu-id="af431-148">例如：</span><span class="sxs-lookup"><span data-stu-id="af431-148">For example:</span></span>

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

<span data-ttu-id="af431-149">如果可以移動網站，則傳回 *Success*，或如果有任何會封鎖的情況，則傳回 *Fail*。</span><span class="sxs-lookup"><span data-stu-id="af431-149">This will return *Success* if the site is ready to be moved or *Fail* if any of blocked conditions are present.</span></span>

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a><span data-ttu-id="af431-150">為沒有任何相關聯 Microsoft 365 群組的網站開始 SharePoint 網站地理移動</span><span class="sxs-lookup"><span data-stu-id="af431-150">Start a SharePoint site geo move for a site with no associated Microsoft 365 Group</span></span>

<span data-ttu-id="af431-151">根據預設，網站的初始 URL 會變更為目的地地理位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="af431-151">By default, initial URL for the site will change to the URL of the destination geo location.</span></span> <span data-ttu-id="af431-152">例如：</span><span class="sxs-lookup"><span data-stu-id="af431-152">For example:</span></span>

<span data-ttu-id="af431-153">https://Contoso.sharepoint.com/sites/projectx 到 https://ContosoEUR.sharepoint.com/sites/projectx</span><span class="sxs-lookup"><span data-stu-id="af431-153">https://Contoso.sharepoint.com/sites/projectx to https://ContosoEUR.sharepoint.com/sites/projectx</span></span>

<span data-ttu-id="af431-154">針對沒有 Microsoft 365 群組關聯的網站，您也可以使用 `-DestinationUrl` 參數來將網站重新命名。</span><span class="sxs-lookup"><span data-stu-id="af431-154">For sites with no Microsoft 365 Group association, you can also rename the site by using the `-DestinationUrl` parameter.</span></span> <span data-ttu-id="af431-155">例如：</span><span class="sxs-lookup"><span data-stu-id="af431-155">For example:</span></span>

<span data-ttu-id="af431-156">https://Contoso.sharepoint.com/sites/projectx 到 https://ContosoEUR.sharepoint.com/sites/projecty</span><span class="sxs-lookup"><span data-stu-id="af431-156">https://Contoso.sharepoint.com/sites/projectx to https://ContosoEUR.sharepoint.com/sites/projecty</span></span>

<span data-ttu-id="af431-157">若要開始網站移動，請執行：</span><span class="sxs-lookup"><span data-stu-id="af431-157">To start the site move, run:</span></span>

`Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>`

![顯示 Start-SPOSiteContentMove Cmdlet 的 PowerShell 視窗螢幕擷取畫面](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a><span data-ttu-id="af431-159">為 Microsoft 365 群組連線網站進行 SharePoint 網站地理移動</span><span class="sxs-lookup"><span data-stu-id="af431-159">Start a SharePoint site geo move for a Microsoft 365 Group-connected site</span></span>

<span data-ttu-id="af431-160">若要移動 Office 365 群組連線網站，全域系統管理員或 SharePoint 系統管理員必須先變更 Office 365 群組的慣用資料位置 (PDL) 屬性。</span><span class="sxs-lookup"><span data-stu-id="af431-160">To move an Office 365 Group-connected site, the Global Administrator or SharePoint Administrator must first change the Preferred Data Location (PDL) attribute for the Office 365 Group.</span></span>

<span data-ttu-id="af431-161">若要為 Microsoft 365 群組設定 PDL：</span><span class="sxs-lookup"><span data-stu-id="af431-161">To set the PDL for a Microsoft 365 Group:</span></span>

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```
<span data-ttu-id="af431-162">更新 PDL 之後，您就可以開始進行網站移動：</span><span class="sxs-lookup"><span data-stu-id="af431-162">Once you have updated the PDL, you can start the site move:</span></span> 

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a><span data-ttu-id="af431-163">取消 SharePoint 網站地理移動</span><span class="sxs-lookup"><span data-stu-id="af431-163">Cancel a SharePoint site geo move</span></span>

<span data-ttu-id="af431-164">只要移動非正在進行或已完成，您即可使用 `Stop-SPOSiteContentMove` Cmdlet 來停止 SharePoint 網站地理移動。</span><span class="sxs-lookup"><span data-stu-id="af431-164">You can stop a SharePoint site geo move, provided the move is not in progress or completed by using the `Stop-SPOSiteContentMove` cmdlet.</span></span>

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a><span data-ttu-id="af431-165">判斷 SharePoint 網站地理移動的狀態</span><span class="sxs-lookup"><span data-stu-id="af431-165">Determining the status of a SharePoint site geo move</span></span>

<span data-ttu-id="af431-166">您可以使用下列 Cmdlet 來判斷您所連線的地理位置中網站移動的狀態：</span><span class="sxs-lookup"><span data-stu-id="af431-166">You can determine the status of a site move in our out of the geo that you are connected to by using the following cmdlets:</span></span>

- <span data-ttu-id="af431-167">[Get-SPOSiteContentMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositecontentmovestate) (非群組連線網站)</span><span class="sxs-lookup"><span data-stu-id="af431-167">[Get-SPOSiteContentMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositecontentmovestate) (non-Group-connected sites)</span></span>
- <span data-ttu-id="af431-168">Get-SPOUnifiedGroupMoveState (群組連線網站)</span><span class="sxs-lookup"><span data-stu-id="af431-168">Get-SPOUnifiedGroupMoveState (Group-connected sites)</span></span>

<span data-ttu-id="af431-169">使用 `-SourceSiteUrl` 參數來指定您要查看移動狀態的網站。</span><span class="sxs-lookup"><span data-stu-id="af431-169">Use the `-SourceSiteUrl` parameter to specify the site for which you want to see move status.</span></span>

<span data-ttu-id="af431-170">下表說明移動狀態。</span><span class="sxs-lookup"><span data-stu-id="af431-170">The move statuses are described in the following table.</span></span>

|<span data-ttu-id="af431-171">狀態</span><span class="sxs-lookup"><span data-stu-id="af431-171">Status</span></span>|<span data-ttu-id="af431-172">描述</span><span class="sxs-lookup"><span data-stu-id="af431-172">Description</span></span>|
|:-----|:----------|
|<span data-ttu-id="af431-173">準備好觸發</span><span class="sxs-lookup"><span data-stu-id="af431-173">Ready to Trigger</span></span>|<span data-ttu-id="af431-174">移動尚未開始。</span><span class="sxs-lookup"><span data-stu-id="af431-174">The move has not started.</span></span>|
|<span data-ttu-id="af431-175">已排程</span><span class="sxs-lookup"><span data-stu-id="af431-175">Scheduled</span></span>|<span data-ttu-id="af431-176">移動在佇列中，但尚未開始。</span><span class="sxs-lookup"><span data-stu-id="af431-176">The move is in queue but has not yet started.</span></span>|
|<span data-ttu-id="af431-177">進行中 (n/4)</span><span class="sxs-lookup"><span data-stu-id="af431-177">InProgress (n/4)</span></span>|<span data-ttu-id="af431-178">移動正在進行中，可能是下列其中一種狀態：驗證 (1/4)、備份 (2/4)、還原 (3/4)、清除 (4/4)。</span><span class="sxs-lookup"><span data-stu-id="af431-178">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span>|
|<span data-ttu-id="af431-179">成功</span><span class="sxs-lookup"><span data-stu-id="af431-179">Success</span></span>|<span data-ttu-id="af431-180">已成功完成移動。</span><span class="sxs-lookup"><span data-stu-id="af431-180">The move has completed successfully.</span></span>|
|<span data-ttu-id="af431-181">失敗</span><span class="sxs-lookup"><span data-stu-id="af431-181">Failed</span></span>|<span data-ttu-id="af431-182">移動失敗。</span><span class="sxs-lookup"><span data-stu-id="af431-182">The move failed.</span></span>|

<span data-ttu-id="af431-183">您也可以套用 `-Verbose` 選項，以查看有關移動的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="af431-183">You can also apply the `-Verbose` option to see additional information about the move.</span></span>

## <a name="user-experience"></a><span data-ttu-id="af431-184">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="af431-184">User experience</span></span>

<span data-ttu-id="af431-185">網站使用者應該會在網站移動到不同的地理位置時，注意到些微的中斷。</span><span class="sxs-lookup"><span data-stu-id="af431-185">Site users should notice minimal disruption when their site is moved to a different geo location.</span></span> <span data-ttu-id="af431-186">除了在移動期間的短暫唯讀狀態，移動完成後，現有的連結和權限將繼續如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="af431-186">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="site"></a><span data-ttu-id="af431-187">網站</span><span class="sxs-lookup"><span data-stu-id="af431-187">Site</span></span>

<span data-ttu-id="af431-188">移動進行時，網站會設為唯讀狀態。</span><span class="sxs-lookup"><span data-stu-id="af431-188">While the move is in progress the site is set to read-only.</span></span> <span data-ttu-id="af431-189">移動完成後，當使用者按一下書籤或其他網站的連結時，即會將使用者導向新地理位置中的新網站。</span><span class="sxs-lookup"><span data-stu-id="af431-189">Once the move is completed, the user is directed to the new site in the new geo location when they click on bookmarks or other links to the site.</span></span>

### <a name="permissions"></a><span data-ttu-id="af431-190">權限</span><span class="sxs-lookup"><span data-stu-id="af431-190">Permissions</span></span>

<span data-ttu-id="af431-191">具有網站權限的使用者將在移動期間和移動完成後繼續擁有網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="af431-191">Users with permissions to site will continue to have access to the site during the move and after it's complete.</span></span>

### <a name="sync-client"></a><span data-ttu-id="af431-192">同步處理用戶端</span><span class="sxs-lookup"><span data-stu-id="af431-192">Sync Client</span></span>

<span data-ttu-id="af431-193">網站移動完成後，同步處理用戶端會自動偵測並順暢地對新網站位置傳輸同步處理。</span><span class="sxs-lookup"><span data-stu-id="af431-193">The sync client will automatically detect and seamlessly transfer syncing to the new site location once the site move is complete.</span></span> <span data-ttu-id="af431-194">使用者不需重新登入，或採取任何其他動作。</span><span class="sxs-lookup"><span data-stu-id="af431-194">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="af431-195">(需要版本 17.3.6943.0625 或更新版本的同步處理用戶端。)</span><span class="sxs-lookup"><span data-stu-id="af431-195">(Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="af431-196">如果使用者在移動時更新檔案，同步處理用戶端會告知使用者，進行移動時檔案上傳會擱置。</span><span class="sxs-lookup"><span data-stu-id="af431-196">If a user updates a file while the move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="af431-197">共用連結</span><span class="sxs-lookup"><span data-stu-id="af431-197">Sharing links</span></span>

<span data-ttu-id="af431-198">當 SharePoint 網站地理移動完成後，移動的檔案之現有共用連結將會自動重新導向至新的地理位置。</span><span class="sxs-lookup"><span data-stu-id="af431-198">When the SharePoint site geo move completes, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="most-recently-used-files-in-office-mru"></a><span data-ttu-id="af431-199">Office 中最近用過的檔案 (MRU)</span><span class="sxs-lookup"><span data-stu-id="af431-199">Most Recently Used files in Office (MRU)</span></span>

<span data-ttu-id="af431-200">移動完成後，MRU 服務的網站 URL 和其內容 URL 即會更新。</span><span class="sxs-lookup"><span data-stu-id="af431-200">The MRU service is updated with the site url and its content URLs once the move completes.</span></span> <span data-ttu-id="af431-201">這適用於 Word、Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="af431-201">This applies to Word, Excel, and PowerPoint.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="af431-202">OneNote 體驗</span><span class="sxs-lookup"><span data-stu-id="af431-202">OneNote experience</span></span>

<span data-ttu-id="af431-203">在網站移動完成後，OneNote win32 用戶端和 UWP (通用) App 將自動偵測並順暢地將筆記本同步處理到新位置。</span><span class="sxs-lookup"><span data-stu-id="af431-203">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new site location once site move is complete.</span></span> <span data-ttu-id="af431-204">使用者不需重新登入，或採取任何其他動作。</span><span class="sxs-lookup"><span data-stu-id="af431-204">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="af431-205">對使用者顯示的唯一指標為，當網站移動進行時，筆記本同步處理會失敗。</span><span class="sxs-lookup"><span data-stu-id="af431-205">The only visible indicator to the user is notebook sync would fail when site move is in progress.</span></span> <span data-ttu-id="af431-206">此體驗會在下列 OneNote 用戶端版本上提供：</span><span class="sxs-lookup"><span data-stu-id="af431-206">This experience is available on the following OneNote client versions:</span></span>

- <span data-ttu-id="af431-207">OneNote win32 – 版本 16.0.8326.2096 (及更新版本)</span><span class="sxs-lookup"><span data-stu-id="af431-207">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>
- <span data-ttu-id="af431-208">OneNote UWP – 版本 16.0.8431.1006 (及更新版本)</span><span class="sxs-lookup"><span data-stu-id="af431-208">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>
- <span data-ttu-id="af431-209">OneNote 行動應用程式 – 版本 16.0.8431.1011 (及更新版本)</span><span class="sxs-lookup"><span data-stu-id="af431-209">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a><span data-ttu-id="af431-210">Teams (適用於 Microsoft 365 群組連線網站)</span><span class="sxs-lookup"><span data-stu-id="af431-210">Teams (applicable to Microsoft 365 Group connected sites)</span></span>

<span data-ttu-id="af431-211">SharePoint 網站地理移動完成後，使用者將能在 Teams App 上存取其 Microsoft 365 群組網站的檔案。</span><span class="sxs-lookup"><span data-stu-id="af431-211">When the SharePoint site geo move completes, users will have access to their Microsoft 365 Group site files on the Teams app.</span></span> <span data-ttu-id="af431-212">此外，於地理移動之前從其網站透過 Teams 聊天共用的檔案，在移動完成後，將繼續運作。</span><span class="sxs-lookup"><span data-stu-id="af431-212">Additionally, files shared via Teams chat from their site prior to geo move will continue to work after move is complete.</span></span>

### <a name="sharepoint-mobile-app-iosandroid"></a><span data-ttu-id="af431-213">SharePoint 行動裝置 App (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="af431-213">SharePoint Mobile App (iOS/Android)</span></span>

<span data-ttu-id="af431-214">SharePoint 行動裝置 App 可跨地理位置相容，且能偵測網站的新地理位置。</span><span class="sxs-lookup"><span data-stu-id="af431-214">The SharePoint Mobile App is cross geo compatible and able to detect the site's new geo location.</span></span>

### <a name="sharepoint-workflows"></a><span data-ttu-id="af431-215">SharePoint 工作流程</span><span class="sxs-lookup"><span data-stu-id="af431-215">SharePoint workflows</span></span>

<span data-ttu-id="af431-216">網站移動後需要重新發佈 SharePoint 2013 工作流程。</span><span class="sxs-lookup"><span data-stu-id="af431-216">SharePoint 2013 workflows need to be republished after the site move.</span></span> <span data-ttu-id="af431-217">SharePoint 2010 工作流程應該會繼續正常運作。</span><span class="sxs-lookup"><span data-stu-id="af431-217">SharePoint 2010 workflows should continue to function normally.</span></span>

### <a name="apps"></a><span data-ttu-id="af431-218">App</span><span class="sxs-lookup"><span data-stu-id="af431-218">Apps</span></span>

<span data-ttu-id="af431-219">如果您要移動的網站具有 App，您必須在網站的新地理位置將 App 重新具現化，因為 App 和其連線在目的地理位置中可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="af431-219">If you are moving a site with apps, you must re-instantiate the app in the site's new geo location as the app and its connections may not be available in the destination geo location.</span></span>

### <a name="flow"></a><span data-ttu-id="af431-220">流程</span><span class="sxs-lookup"><span data-stu-id="af431-220">Flow</span></span>

<span data-ttu-id="af431-221">在多數情況下，在 SharePoint 網站地理移動後，流程將繼續運作。</span><span class="sxs-lookup"><span data-stu-id="af431-221">In most cases Flows will continue to work after a SharePoint site geo move.</span></span> <span data-ttu-id="af431-222">建議您在移動完成後先測試這些流程。</span><span class="sxs-lookup"><span data-stu-id="af431-222">We recommend that you test them once the move has completed.</span></span>

### <a name="powerapps"></a><span data-ttu-id="af431-223">PowerApps</span><span class="sxs-lookup"><span data-stu-id="af431-223">PowerApps</span></span>

<span data-ttu-id="af431-224">需要在目的地位置重新建立 PowerApps。</span><span class="sxs-lookup"><span data-stu-id="af431-224">PowerApps need to be recreated in the destination location.</span></span>

### <a name="data-movement-between-geo-locations"></a><span data-ttu-id="af431-225">地理位置之間的資料移動</span><span class="sxs-lookup"><span data-stu-id="af431-225">Data movement between geo locations</span></span>

<span data-ttu-id="af431-226">SharePoint 將內容放置在 Azure Blob 儲存體，而將與網站和其檔案相關聯的中繼資料則儲存在 SharePoint 內。</span><span class="sxs-lookup"><span data-stu-id="af431-226">SharePoint uses Azure Blob storage for its content, while the metadata associated with sites and its files is stored within SharePoint.</span></span> <span data-ttu-id="af431-227">在將網站從來源地理位置移動到目的地地理位置後，服務也將移動其相關聯的 Blob 儲存體。</span><span class="sxs-lookup"><span data-stu-id="af431-227">After the site is moved from its source geo location to its destination geo location, the service will also move its associated Blob Storage.</span></span> <span data-ttu-id="af431-228">Blob 儲存體移動大約需要 40 天才能完成。</span><span class="sxs-lookup"><span data-stu-id="af431-228">Blob Storage moves complete in approximately 40 days.</span></span> 
