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
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a><span data-ttu-id="cff3f-103">將 OneDrive 網站移至不同的地理位置</span><span class="sxs-lookup"><span data-stu-id="cff3f-103">Move a OneDrive site to a different geo location</span></span> 

<span data-ttu-id="cff3f-p101">使用 OneDrive 地理位置移動，您可以將使用者的 OneDrive 移至不同的地理位置。OneDrive 地理位置移動由 SharePoint Online 系統管理員或 Microsoft 365 全域管理員執行。在您開始 OneDrive 地理位置移動之前，請務必通知使用者其 OneDrive 已移動，並建議使用者在移動期間關閉所有檔案。 (如果使用者在移動期間使用 Office 用戶端開啟檔，則在移動完成時，將需要將檔儲存到新的位置。 ) 如有需要，可以排程未來時間的移動。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p101">With OneDrive geo move, you can move a user's OneDrive to a different geo location. OneDrive geo move is performed by the SharePoint Online administrator or the Microsoft 365 global administrator. Before you start a OneDrive geo move, be sure to notify the user whose OneDrive is being moved and recommend they close all files for the duration of the move. (If the user has a document open using the Office client during the move, then upon move completion the document will need to be saved to the new location.) The move can be scheduled for a future time, if desired.</span></span>

<span data-ttu-id="cff3f-p102">OneDrive 服務使用 Azure Blob 儲存來儲存內容。與使用者的 OneDrive 相關聯的儲存區，將會從來源移至目的地地理位置，40在目的地 OneDrive 可供使用者使用。當目的地 OneDrive 可用時，就會立即還原使用者 OneDrive 的存取權。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p102">The OneDrive service uses Azure Blob Storage to store content. The Storage blob associated with the user's OneDrive will be moved from the source to destination geo location within 40 days of destination OneDrive being available to the user. The access to the user's OneDrive will be restored as soon as the destination OneDrive is available.</span></span>

<span data-ttu-id="cff3f-p103">在 OneDrive 異地移動期間 (大約 2-6 小時)，使用者的 OneDrive 會設為唯讀狀態。使用者仍可以透過 OneDrive 同步處理用戶端或 SharePoint Online 中的 OneDrive 網站存取檔案。在完成 OneDrive 異地移動後，若使用者瀏覽至 Microsoft 365 應用程式啟動器中的 OneDrive，將會自動連線到位於目的地理位置的 OneDrive。同步處理用戶端將自動開始新位置的同步處理。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p103">During OneDrive geo move window (about 2-6 hours) the user's OneDrive is set to read-only. The user can still access their files via the OneDrive sync client or their OneDrive site in SharePoint Online. After OneDrive geo move is complete, the user will be automatically connected to their OneDrive at the destination geo location when they navigate to OneDrive in the Microsoft 365 app launcher. The sync client will automatically begin syncing from the new location.</span></span>

<span data-ttu-id="cff3f-115">本文所述的程序需要 [Microsoft SharePoint Online PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=35588)。</span><span class="sxs-lookup"><span data-stu-id="cff3f-115">The procedures in this article require the [Microsoft SharePoint Online PowerShell Module](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="cff3f-116">與使用者溝通</span><span class="sxs-lookup"><span data-stu-id="cff3f-116">Communicating to your users</span></span>

<span data-ttu-id="cff3f-p104">在地理位置之間移動 OneDrive 網站時，請務必將預期要發生的事傳達給使用者。這可以幫助減少使用者的困惑和技術支援中心的電話。在移動前發送電子郵件給使用者，並讓他們知道以下資訊：</span><span class="sxs-lookup"><span data-stu-id="cff3f-p104">When moving OneDrive sites between geo locations, it's important to communicate to your users what to expect. This can help reduce user confusion and calls to your help desk. Email your users before the move and let them know the following information:</span></span>

- <span data-ttu-id="cff3f-120">預計何時將開始移動，並預計需要多久</span><span class="sxs-lookup"><span data-stu-id="cff3f-120">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="cff3f-121">OneDrive 新的地理位置以及存取新位置的 URL</span><span class="sxs-lookup"><span data-stu-id="cff3f-121">What geo location their OneDrive is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="cff3f-122">他們應該關閉文件，並且不要在移動期間編輯檔案</span><span class="sxs-lookup"><span data-stu-id="cff3f-122">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="cff3f-123">檔案權限和共用不會因為移動而變更</span><span class="sxs-lookup"><span data-stu-id="cff3f-123">File permissions and sharing will not change as a result of the move.</span></span>
- <span data-ttu-id="cff3f-124">[在多地理位置環境中的使用者體驗](multi-geo-user-experience.md)將有何不同</span><span class="sxs-lookup"><span data-stu-id="cff3f-124">What to expect from the [user experience in a multi-geo environment](multi-geo-user-experience.md)</span></span>

<span data-ttu-id="cff3f-125">移動成功完成後，請務必向用戶發送電子郵件，通知他們可以在 OneDrive 中繼續工作。</span><span class="sxs-lookup"><span data-stu-id="cff3f-125">Be sure to send your users an email when the move has successfully completed informing them that they can resume working in OneDrive.</span></span>

## <a name="scheduling-onedrive-site-moves"></a><span data-ttu-id="cff3f-126">排定 OneDrive 網站移動</span><span class="sxs-lookup"><span data-stu-id="cff3f-126">Scheduling OneDrive site moves</span></span>

<span data-ttu-id="cff3f-p105">您可以事先排定 OneDrive 網站移動 (如本文稍後所述)。建議您從一小群使用者開始驗證工作流程和通訊策略。熟悉此程序後，您就可以如下所述排定移動：</span><span class="sxs-lookup"><span data-stu-id="cff3f-p105">You can schedule OneDrive site moves in advance (described later in this article). We recommend that you start with a small number of users to validate your workflows and communication strategies. Once you are comfortable with the process, you can schedule moves as follows:</span></span>

- <span data-ttu-id="cff3f-130">您一次最多可以排定 4,000 個移動。</span><span class="sxs-lookup"><span data-stu-id="cff3f-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="cff3f-131">您可以在移動開始時排定更多移動，並將最多 4,000 個擱置移動排入佇列和任何指定的時間。</span><span class="sxs-lookup"><span data-stu-id="cff3f-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
- <span data-ttu-id="cff3f-132">可移動的 OneDrive 大小上限為 1 TB。</span><span class="sxs-lookup"><span data-stu-id="cff3f-132">The maximum size of a OneDrive that can be moved is 1 terabyte (1 TB).</span></span>

## <a name="moving-a-onedrive-site"></a><span data-ttu-id="cff3f-133">移動 OneDrive 網站</span><span class="sxs-lookup"><span data-stu-id="cff3f-133">Moving a OneDrive site</span></span>

<span data-ttu-id="cff3f-p106">若要執行 OneDrive 地理移動，租使用者管理員必須先將使用者的慣用資料位置 (PDL) 設定為適當的地理位置。設定 PDL 後，請至少等候24小時，以供 PDL 更新在開始 OneDrive 地理位置移動之前于整個地理位置進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p106">To perform a OneDrive geo move, the tenant administrator must first set the user's Preferred Data Location (PDL) to the appropriate geo location. Once the PDL is set, wait for at least 24 hours for the PDL update to sync across the geo locations before starting the OneDrive geo move.</span></span>

<span data-ttu-id="cff3f-136">使用 geo 移動指令程式時，請使用下列語法，在使用者目前 OneDrive 地理位置連接至 SPO 服務：</span><span class="sxs-lookup"><span data-stu-id="cff3f-136">When using the geo move cmdlets, connect to SPO Service at the user's current OneDrive geo location, using the following syntax:</span></span>

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

<span data-ttu-id="cff3f-137">例如：若要移動使用者 ' Matt@contosoenergy.onmicrosoft.com ' 的 OneDrive，請在使用者的 OneDrive 位於 EUR 地理位置時，連接到 EUR SharePoint 系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="cff3f-137">For example: To move OneDrive of user 'Matt@contosoenergy.onmicrosoft.com', connect to EUR SharePoint Admin center as the user's OneDrive is in EUR geo location:</span></span>

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![顯示 connect-sposervice Cmdlet的 PowerShell 視窗螢幕擷取畫面](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a><span data-ttu-id="cff3f-139">驗證環境</span><span class="sxs-lookup"><span data-stu-id="cff3f-139">Validating the environment</span></span>

<span data-ttu-id="cff3f-140">在您開始 OneDrive 異地移動之前，我們建議您先驗證環境。</span><span class="sxs-lookup"><span data-stu-id="cff3f-140">Before you start a OneDrive geo move, we recommend that you validate the environment.</span></span>

<span data-ttu-id="cff3f-141">若要確保所有地理位置相容，請執行：</span><span class="sxs-lookup"><span data-stu-id="cff3f-141">To ensure that all geo locations are compatible, run:</span></span>

`Get-SPOGeoMoveCrossCompatibilityStatus`

<span data-ttu-id="cff3f-142">您會看到地理位置清單，而是否可以在其中移動內容會標示為「相容」。</span><span class="sxs-lookup"><span data-stu-id="cff3f-142">You will see a list of your geo locations and whether content can be moved between will be denoted as "Compatible".</span></span> <span data-ttu-id="cff3f-143">如果命令傳回「不相容」，請之後再重新驗證狀態。</span><span class="sxs-lookup"><span data-stu-id="cff3f-143">If the command returns "Incompatible" please retry validating the status at a later date.</span></span>

<span data-ttu-id="cff3f-144">如果 OneDrive 包含子網站，就無法移動。</span><span class="sxs-lookup"><span data-stu-id="cff3f-144">If a OneDrive contains a subsite, for example, it cannot be moved.</span></span> <span data-ttu-id="cff3f-145">您可以使用 Start-SPOUserAndContentMove Cmdlet 以及 -ValidationOnly 參數驗證 OneDrive 是否可以移動：</span><span class="sxs-lookup"><span data-stu-id="cff3f-145">You can use the Start-SPOUserAndContentMove cmdlet with the -ValidationOnly parameter to validate if the OneDrive is able to be moved:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

<span data-ttu-id="cff3f-p109">如果 OneDrive 已準備好要移動會傳回成功，如果有防止移動的法務保存狀態或子網站，則會傳回失敗。在您已驗證 OneDrive 移動準備就緒之後，就可以開始移動。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p109">This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move. Once you have validated that the OneDrive is ready to move, you can start the move.</span></span>

## <a name="start-a-onedrive-geo-move"></a><span data-ttu-id="cff3f-148">啟動 OneDrive 異地移動</span><span class="sxs-lookup"><span data-stu-id="cff3f-148">Start a OneDrive geo move</span></span>

<span data-ttu-id="cff3f-149">若要啟動移動，請執行：</span><span class="sxs-lookup"><span data-stu-id="cff3f-149">To start the move, run:</span></span>  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

<span data-ttu-id="cff3f-150">使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="cff3f-150">Using these parameters:</span></span>

-   <span data-ttu-id="cff3f-151">_UserPrincipalName_ – OneDrive 即將移動的使用者 UPN。</span><span class="sxs-lookup"><span data-stu-id="cff3f-151">_UserPrincipalName_ – UPN of the user whose OneDrive is being moved.</span></span>

-   <span data-ttu-id="cff3f-p110">_DestinationDataLocation_ –需要移動 OneDrive 地理位置。這應該與使用者的慣用資料位置相同。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p110">_DestinationDataLocation_ – Geo-Location where the OneDrive needs to be moved. This should be same as the user's preferred data location.</span></span>

<span data-ttu-id="cff3f-154">比方說，若要將 matt@contosoenergy.onmicrosoft.com 的 OneDrive 從 EUR 移動到 AUS，請執行：</span><span class="sxs-lookup"><span data-stu-id="cff3f-154">For example, to move the OneDrive of matt@contosoenergy.onmicrosoft.com from EUR to AUS, run:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![顯示 Start-SPOUserAndContentMove Cmdlet 的 PowerShell 視窗螢幕擷取畫面](../media/move-onedrive-between-geo-locations-image2.png)

<span data-ttu-id="cff3f-156">若要排程稍後進行異地移動，請使用下列參數的其中一個：</span><span class="sxs-lookup"><span data-stu-id="cff3f-156">To schedule a geo move for a later time, use one of the following parameters:</span></span>

-   <span data-ttu-id="cff3f-p111">_PreferredMoveBeginDate_ – 移動會在指定的時間開始。必須以國際標準時間 (UTC) 來指定時間。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p111">_PreferredMoveBeginDate_ – The move will likely begin at this specified time. Time must be specified in Coordinated Universal Time (UTC).</span></span>

-   <span data-ttu-id="cff3f-p112">_PreferredMoveEndDate_ – 移動會以最佳方式在指定的時間前完成。必須以國際標準時間 (UTC) 來指定時間。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p112">_PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis. Time must be specified in Coordinated Universal Time (UTC).</span></span> 

## <a name="cancel-a-onedrive-geo-move"></a><span data-ttu-id="cff3f-161">取消 OneDrive 異地移動</span><span class="sxs-lookup"><span data-stu-id="cff3f-161">Cancel a OneDrive geo move</span></span> 

<span data-ttu-id="cff3f-162">您可以停止地理位置移動使用者的 OneDrive，但前提是移動並未進行中或已完成使用 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="cff3f-162">You can stop the geo move of a user's OneDrive, provided the move is not in progress or completed by using the cmdlet:</span></span>

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

<span data-ttu-id="cff3f-163">其中 _UserPrincipalName_ 是您要停止的 OneDrive 移動之使用者 UPN。</span><span class="sxs-lookup"><span data-stu-id="cff3f-163">Where _UserPrincipalName_ is the UPN of the user whose OneDrive move you want to stop.</span></span>

## <a name="determining-current-status"></a><span data-ttu-id="cff3f-164">判斷目前狀態</span><span class="sxs-lookup"><span data-stu-id="cff3f-164">Determining current status</span></span>

<span data-ttu-id="cff3f-165">您可以使用 Get-SPOUserAndContentMoveState Cmdlet，檢查您所連接之地理位置的 OneDrive 異地移入或移出的狀態。</span><span class="sxs-lookup"><span data-stu-id="cff3f-165">You can check the status of a OneDrive geo move in or out of the geo that you're connected to by using the Get-SPOUserAndContentMoveState cmdlet.</span></span>

<span data-ttu-id="cff3f-166">下表說明移動狀態。</span><span class="sxs-lookup"><span data-stu-id="cff3f-166">The move statuses are described in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cff3f-167"><strong>狀態</strong></span><span class="sxs-lookup"><span data-stu-id="cff3f-167"><strong>Status</strong></span></span></th>
<th align="left"><span data-ttu-id="cff3f-168"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cff3f-168"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cff3f-169">NotStarted</span><span class="sxs-lookup"><span data-stu-id="cff3f-169">NotStarted</span></span></td>
<td align="left"><span data-ttu-id="cff3f-170">移動尚未啟動。</span><span class="sxs-lookup"><span data-stu-id="cff3f-170">The move has not started.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cff3f-171">InProgress (<em>n</em>/4)</span><span class="sxs-lookup"><span data-stu-id="cff3f-171">InProgress (<em>n</em>/4)</span></span></td>
<td align="left"><span data-ttu-id="cff3f-172">移動正在進行中，可能是下列其中一種狀態：驗證 (1/4)、備份 (2/4)、還原 (3/4)、清除 (4/4)。</span><span class="sxs-lookup"><span data-stu-id="cff3f-172">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cff3f-173">成功</span><span class="sxs-lookup"><span data-stu-id="cff3f-173">Success</span></span></td>
<td align="left"><span data-ttu-id="cff3f-174">已成功完成移動。</span><span class="sxs-lookup"><span data-stu-id="cff3f-174">The move has completed successfully.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cff3f-175">失敗</span><span class="sxs-lookup"><span data-stu-id="cff3f-175">Failed</span></span></td>
<td align="left"><span data-ttu-id="cff3f-176">移動失敗。</span><span class="sxs-lookup"><span data-stu-id="cff3f-176">The move failed.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cff3f-177">若要尋找特定使用者移動的狀態，請使用 UserPrincipalName 參數：</span><span class="sxs-lookup"><span data-stu-id="cff3f-177">To find the status of a specific user's move, use the UserPrincipalName parameter:</span></span>

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

<span data-ttu-id="cff3f-178">若要尋找您所連接之地理位置的所有移動狀態，請使用 MoveState 參數搭配下列其中一個值： NotStarted、InProgress、成功、失敗、全部。</span><span class="sxs-lookup"><span data-stu-id="cff3f-178">To find the status of all of the moves in or out of the geo location that you're connected to, use the MoveState parameter with one of the following values: NotStarted, InProgress, Success, Failed, All.</span></span>

`Get-SPOUserAndContentMoveState -MoveState <value>`

<span data-ttu-id="cff3f-179">您也可以新增 `-Verbose` 參數，以取得移動狀態更詳細的說明。</span><span class="sxs-lookup"><span data-stu-id="cff3f-179">You can also add the `-Verbose` parameter for more verbose descriptions of the move state.</span></span>

## <a name="user-experience"></a><span data-ttu-id="cff3f-180">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="cff3f-180">User Experience</span></span>

<span data-ttu-id="cff3f-p113">如果 OneDrive 移到不同的地理位置，OneDrive 使用者應注意是否有服務中斷。除了在移動期間會發生簡短的唯讀狀態，在移動完成後，現有的連結和權限會如預期般繼續運作。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p113">Users of OneDrive should notice minimal disruption if their OneDrive is moved to a different geo location. Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="cff3f-183">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="cff3f-183">OneDrive for Business</span></span>

<span data-ttu-id="cff3f-p114">進行移動時，使用者的 OneDrive 會設定為唯讀。移動完成之後，當使用者流覽 OneDrive Microsoft 365 應用程式啟動器或網頁瀏覽器時，會將他們的 OneDrive 導向新的地理位置。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p114">While the move is in progress the user's OneDrive is set to read-only. Once the move is completed, the user is directed to their OneDrive in the new geo location when they navigate to OneDrive the Microsoft 365 app launcher or a web browser.</span></span>

### <a name="permissions-on-onedrive-content"></a><span data-ttu-id="cff3f-186">OneDrive 內容的權限</span><span class="sxs-lookup"><span data-stu-id="cff3f-186">Permissions on OneDrive content</span></span>

<span data-ttu-id="cff3f-187">在移動期間和完成後，具有 OneDrive 內容許可權的使用者仍可存取內容。</span><span class="sxs-lookup"><span data-stu-id="cff3f-187">Users with permissions to OneDrive content will continue to have access to the content during the move and after it's complete.</span></span>

### <a name="onedrive-sync-client"></a><span data-ttu-id="cff3f-188">OneDrive 同步處理用戶端</span><span class="sxs-lookup"><span data-stu-id="cff3f-188">OneDrive Sync Client</span></span> 

<span data-ttu-id="cff3f-p115">OneDrive 異地移動完成後，OneDrive 同步處理用戶端會自動偵測並順暢地傳輸同步處理至 OneDrive 的新位置。使用者不必重新登入或採取任何其他動作。(同步處理用戶端需要 17.3.6943.0625 版或更新的版本。)</span><span class="sxs-lookup"><span data-stu-id="cff3f-p115">The OneDrive sync client will automatically detect and seamlessly transfer syncing to the new OneDrive location once the OneDrive geo move is complete. The user does not need to sign-in again or take any other action.  (Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="cff3f-192">如果使用者在進行 OneDrive 異地移動時更新檔案，同步處理用戶端會告知使用者，進行異地移動時上傳的檔案會擱置。</span><span class="sxs-lookup"><span data-stu-id="cff3f-192">If a user updates a file while the OneDrive geo move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="cff3f-193">共用連結</span><span class="sxs-lookup"><span data-stu-id="cff3f-193">Sharing links</span></span> 

<span data-ttu-id="cff3f-194">在 OneDrive 異地移動完成後，移動的檔案之現有共用連結將會自動重新導向至新的地理位置。</span><span class="sxs-lookup"><span data-stu-id="cff3f-194">Upon OneDrive geo move completion, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="cff3f-195">OneNote 體驗</span><span class="sxs-lookup"><span data-stu-id="cff3f-195">OneNote Experience</span></span> 

<span data-ttu-id="cff3f-p116">OneDrive 異地移動完成後，OneNote win32 用戶端和 UWP (通用) 應用程式會自動偵測並順暢地將筆記本同步處理到 OneDrive 的新位置。使用者不必重新登入或採取任何其他動作。使用者唯一可見的指標是，若 OneDrive 異地移動正在進行時，筆記本同步處理會失敗。此體驗適用於下列 OneNote 用戶端版本：</span><span class="sxs-lookup"><span data-stu-id="cff3f-p116">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new OneDrive location once OneDrive geo move is complete. The user does not need to sign-in again or take any other action. The only visible indicator to the user is notebook sync would fail when OneDrive geo move is in progress. This experience is available on the following OneNote client versions:</span></span>

-   <span data-ttu-id="cff3f-200">OneNote win32 – 版本 16.0.8326.2096 (及更新版本)</span><span class="sxs-lookup"><span data-stu-id="cff3f-200">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>

-   <span data-ttu-id="cff3f-201">OneNote UWP – 版本 16.0.8431.1006 (及更新版本)</span><span class="sxs-lookup"><span data-stu-id="cff3f-201">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>

-   <span data-ttu-id="cff3f-202">OneNote 行動應用程式 – 版本 16.0.8431.1011 (及更新版本)</span><span class="sxs-lookup"><span data-stu-id="cff3f-202">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-app"></a><span data-ttu-id="cff3f-203">Teams 應用程式</span><span class="sxs-lookup"><span data-stu-id="cff3f-203">Teams app</span></span>

<span data-ttu-id="cff3f-p117">OneDrive 異地移動完成後，使用者可以在 Teams 應用程式上存取其 OneDrive 檔案。此外，在異地移動之前從 OneDrive 透過 Teams 交談共用的檔案，在移動完成後將會繼續運作。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p117">Upon OneDrive geo move completion, users will have access to their OneDrive files on the Teams app. Additionally, files shared via Teams chat from their OneDrive prior to geo move will continue to work after move is complete.</span></span>

### <a name="onedrive-for-business-mobile-app-ios"></a><span data-ttu-id="cff3f-206">商務用 OneDrive 行動應用程式 (iOS)</span><span class="sxs-lookup"><span data-stu-id="cff3f-206">OneDrive for Business Mobile App (iOS)</span></span> 

<span data-ttu-id="cff3f-207">在 OneDrive 異地移動完成後，使用者必須在 iOS 行動應用程式上登出並重新登入，以同步處理到 OneDrive 的新位置。</span><span class="sxs-lookup"><span data-stu-id="cff3f-207">Upon OneDrive geo move completion, the user would need to sign out and sign in again on the iOS Mobile App to sync to the new OneDrive location.</span></span>

### <a name="existing-followed-groups-and-sites"></a><span data-ttu-id="cff3f-208">現有的已追蹤群組和網站</span><span class="sxs-lookup"><span data-stu-id="cff3f-208">Existing followed groups and sites</span></span>

<span data-ttu-id="cff3f-p118">已遵循的網站和群組會顯示在使用者的 OneDrive，不論其地理位置為何。位於其他地理位置的網站和群組會在個別的索引標籤中開啟。</span><span class="sxs-lookup"><span data-stu-id="cff3f-p118">Followed sites and groups will show up in the user's OneDrive regardless of their geo location. Sites and groups hosted in another geo location will open in a separate tab.</span></span>

### <a name="delve-geo-url-updates"></a><span data-ttu-id="cff3f-211">Delve 地理 URL 更新</span><span class="sxs-lookup"><span data-stu-id="cff3f-211">Delve Geo URL updates</span></span>

<span data-ttu-id="cff3f-212">只有在將使用者的 OneDrive 移至新的地理位置之後，使用者才會傳送至其 PDL 的 Delve 地理對應的 Delve 地理位置。</span><span class="sxs-lookup"><span data-stu-id="cff3f-212">Users will be sent to the Delve geo corresponding to their PDL only after their OneDrive has been moved to the new geo.</span></span>