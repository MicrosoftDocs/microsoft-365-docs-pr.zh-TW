---
title: 疑難排解電子文件探索保留錯誤
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 疑難排解在核心 eDiscovery 中套用至保管人和非 custodial 資料來源的法律封存相關錯誤。
ms.openlocfilehash: b101bf92c6a304262b3886a4ce0280f427a4a847
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538468"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="d0fed-103">疑難排解電子文件探索保留錯誤</span><span class="sxs-lookup"><span data-stu-id="d0fed-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="d0fed-104">本文討論 eDiscovery 保留可能發生的常見問題，以及如何解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="d0fed-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="d0fed-105">本文也包含建議的做法，可協助您緩解或避免這些問題。</span><span class="sxs-lookup"><span data-stu-id="d0fed-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="d0fed-106">建議的做法</span><span class="sxs-lookup"><span data-stu-id="d0fed-106">Recommended practices</span></span>

<span data-ttu-id="d0fed-107">若要減少與 eDiscovery 保留相關的錯誤數，建議採用下列做法：</span><span class="sxs-lookup"><span data-stu-id="d0fed-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="d0fed-108">如果保留分配仍處於擱置狀態，且狀態為 [ `On (Pending)` 或] `Off (Pending)` ，請等到保留分配完成之後，再進行進一步的更新。</span><span class="sxs-lookup"><span data-stu-id="d0fed-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="d0fed-109">在進行任何進一步的更新之前，請先檢查保留原則是否已擱置。</span><span class="sxs-lookup"><span data-stu-id="d0fed-109">Check whether a hold policy is pending before you make any further updates to it.</span></span> <span data-ttu-id="d0fed-110">執行下列命令，或將它們儲存至 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="d0fed-110">Run the following commands or save them to a PowerShell script.</span></span>

    ```powershell
    $status = Get-CaseHoldPolicy -Identity <policyname> 
    if($status.DistributionStatus -ne "Pending"){
        # policy no longer pending
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user1
    }else{
        # policy still pending
        Write-Host "Hold policy still pending."
    }
   ```

- <span data-ttu-id="d0fed-111">將更新合併到單一大量要求中的 eDiscovery 保留，而不是針對每個交易重複更新保留原則。</span><span class="sxs-lookup"><span data-stu-id="d0fed-111">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="d0fed-112">例如，若要使用 [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) Cmdlet 將多個使用者信箱新增至現有的保留原則，請執行命令 (或新增為腳本) 的程式碼區塊，使其只執行一次，才能新增多個使用者。</span><span class="sxs-lookup"><span data-stu-id="d0fed-112">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="d0fed-113">**正確**</span><span class="sxs-lookup"><span data-stu-id="d0fed-113">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="d0fed-114">**不正確**</span><span class="sxs-lookup"><span data-stu-id="d0fed-114">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="d0fed-115">在上述錯誤的範例中，Cmdlet 會執行五個不同的時間來完成任務。</span><span class="sxs-lookup"><span data-stu-id="d0fed-115">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="d0fed-116">如需將使用者新增至保留原則的建議作法的詳細資訊，請參閱 [more information](#more-information) 一節。</span><span class="sxs-lookup"><span data-stu-id="d0fed-116">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="d0fed-117">在取得 eDiscovery 保留問題的 Microsoft 支援服務之前，請遵循 [錯誤/問題中的步驟： [保留未同步](#errorissue-holds-dont-sync) 處理] 區段以重試保留發佈。</span><span class="sxs-lookup"><span data-stu-id="d0fed-117">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="d0fed-118">此處理程式通常會解決暫時問題，包括內部伺服器錯誤。</span><span class="sxs-lookup"><span data-stu-id="d0fed-118">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="d0fed-119">錯誤/問題：保留未同步處理</span><span class="sxs-lookup"><span data-stu-id="d0fed-119">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="d0fed-120">如果您在將保管人和資料來源置於保留狀態時看到下列錯誤訊息，請使用解決步驟來對問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="d0fed-120">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="d0fed-121">資源：部署原則所花費的時間超過預期。</span><span class="sxs-lookup"><span data-stu-id="d0fed-121">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="d0fed-122">更新最終部署狀態可能需要另外2小時，所以請在幾小時內回來查看。</span><span class="sxs-lookup"><span data-stu-id="d0fed-122">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="d0fed-123">由於暫時性的 Office 365 資料中心問題，無法將原則部署至內容來源。</span><span class="sxs-lookup"><span data-stu-id="d0fed-123">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="d0fed-124">目前的原則不會套用到來源中的任何內容，因此不會影響已封鎖的部署。</span><span class="sxs-lookup"><span data-stu-id="d0fed-124">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="d0fed-125">若要修正此問題，請嘗試重新部署原則。</span><span class="sxs-lookup"><span data-stu-id="d0fed-125">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="d0fed-126">對不起，由於暫時性的內部伺服器錯誤，我們無法對原則執行所要求的變更。</span><span class="sxs-lookup"><span data-stu-id="d0fed-126">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="d0fed-127">請在30分鐘後再試一次。</span><span class="sxs-lookup"><span data-stu-id="d0fed-127">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="d0fed-128">解決方案</span><span class="sxs-lookup"><span data-stu-id="d0fed-128">Resolution</span></span>

1. <span data-ttu-id="d0fed-129">連線至[安全性 & 規範中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)並執行 eDiscovery hold 的下列命令：</span><span class="sxs-lookup"><span data-stu-id="d0fed-129">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="d0fed-130">檢查 *DistributionDetail* 參數中的值。</span><span class="sxs-lookup"><span data-stu-id="d0fed-130">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="d0fed-131">尋找如下的錯誤：</span><span class="sxs-lookup"><span data-stu-id="d0fed-131">Look for errors like the following:</span></span>

   > <span data-ttu-id="d0fed-132">錯誤：資源：部署原則所花費的時間超過預期。</span><span class="sxs-lookup"><span data-stu-id="d0fed-132">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="d0fed-133">更新最終部署狀態可能需要另外2小時，所以請在幾小時內回來查看。</span><span class="sxs-lookup"><span data-stu-id="d0fed-133">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="d0fed-134">嘗試在有問題的保留原則上執行 **Set-CaseHoldPolicy RetryDistribution** 命令;例如：</span><span class="sxs-lookup"><span data-stu-id="d0fed-134">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a><span data-ttu-id="d0fed-135">錯誤： SharePoint 網站是唯讀或無法存取</span><span class="sxs-lookup"><span data-stu-id="d0fed-135">Error: The SharePoint site is read-only or not accessible</span></span>

<span data-ttu-id="d0fed-136">如果您在將保管人和資料來源置於保留狀態時看到下列錯誤訊息，這表示您組織的[全域管理員或 SharePoint 管理員](/sharepoint/sharepoint-admin-role)已鎖定網站。</span><span class="sxs-lookup"><span data-stu-id="d0fed-136">If you see the following error message when putting custodians and data sources on hold, it means that your organization's [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) has locked the site.</span></span> <span data-ttu-id="d0fed-137">鎖定的網站會封鎖 eDiscovery 在網站上的保留功能。</span><span class="sxs-lookup"><span data-stu-id="d0fed-137">A locked site blocks eDiscovery from placing a hold on the site.</span></span>

> <span data-ttu-id="d0fed-138">SharePoint 網站是唯讀或無法存取。</span><span class="sxs-lookup"><span data-stu-id="d0fed-138">The SharePoint site is read-only or not accessible.</span></span> <span data-ttu-id="d0fed-139">請聯繫網站管理員讓網站成為可寫入的網站，然後重新部署此原則。</span><span class="sxs-lookup"><span data-stu-id="d0fed-139">Please contact the site administrator to make the site writable, and then redeploy this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="d0fed-140">解決方案</span><span class="sxs-lookup"><span data-stu-id="d0fed-140">Resolution</span></span>

<span data-ttu-id="d0fed-141">請解除鎖定網站 (或要求系統管理員解除) 以解決此問題。</span><span class="sxs-lookup"><span data-stu-id="d0fed-141">Unlock the site (or ask an admin to unlock it) to resolve this issue.</span></span> <span data-ttu-id="d0fed-142">若要深入瞭解如何變更網站的鎖定狀態，請參閱 [鎖定和解除鎖定網站](/sharepoint/manage-lock-status)。</span><span class="sxs-lookup"><span data-stu-id="d0fed-142">To learn more about how to change the lock state for a site, see [Lock and unlock sites](/sharepoint/manage-lock-status).</span></span>

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a><span data-ttu-id="d0fed-143">錯誤：信箱或 SharePoint 網站可能不存在</span><span class="sxs-lookup"><span data-stu-id="d0fed-143">Error: The mailbox or SharePoint site may not exist</span></span>

<span data-ttu-id="d0fed-144">如果您在將保管人和資料來源置於保留狀態時看到下列錯誤訊息，請使用解決步驟來對問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="d0fed-144">If you see the following error message when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="d0fed-145">信箱或 SharePoint 網站可能不存在。</span><span class="sxs-lookup"><span data-stu-id="d0fed-145">The mailbox or SharePoint site may not exist.</span></span>  <span data-ttu-id="d0fed-146">如果這不正確，請與 Microsoft 支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="d0fed-146">If this is incorrect, please contact Microsoft support.</span></span>  <span data-ttu-id="d0fed-147">否則，請從這個原則中移除。</span><span class="sxs-lookup"><span data-stu-id="d0fed-147">Otherwise, please remove it from this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="d0fed-148">解決方案</span><span class="sxs-lookup"><span data-stu-id="d0fed-148">Resolution</span></span>

- <span data-ttu-id="d0fed-149">在 Exchange Online PowerShell 中執行[Get-Mailbox](/powershell/module/exchange/get-mailbox) ，檢查您的組織中是否存在使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="d0fed-149">Run the [Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell to check if the user mailbox exists in your organization.</span></span>

- <span data-ttu-id="d0fed-150">在 SharePoint 線上 PowerShell 中執行[Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) Cmdlet，以檢查您的組織中是否有該網站。</span><span class="sxs-lookup"><span data-stu-id="d0fed-150">Run the [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) cmdlet in SharePoint Online PowerShell to check if the site exists in your organization.</span></span>

- <span data-ttu-id="d0fed-151">請檢查網站 URL 是否已變更。</span><span class="sxs-lookup"><span data-stu-id="d0fed-151">Check to see if the site URL has changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="d0fed-152">其他資訊</span><span class="sxs-lookup"><span data-stu-id="d0fed-152">More information</span></span>

<span data-ttu-id="d0fed-153">在「建議的做法」一節中，針對多位使用者更新保留原則的指導，是由系統封鎖保留原則同時更新所產生的結果。</span><span class="sxs-lookup"><span data-stu-id="d0fed-153">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="d0fed-154">這表示當更新的保留原則套用至新的內容位置，且保留原則處於擱置狀態時，無法將其他內容位置新增至保留原則。</span><span class="sxs-lookup"><span data-stu-id="d0fed-154">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="d0fed-155">以下是一些您應記住的事項，以協助您緩解此問題：</span><span class="sxs-lookup"><span data-stu-id="d0fed-155">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
- <span data-ttu-id="d0fed-156">每次更新保留更新時，就會立即進入暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="d0fed-156">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="d0fed-157">[擱置狀態] 狀態表示正在將保留套用至內容位置。</span><span class="sxs-lookup"><span data-stu-id="d0fed-157">The pending state status means the hold is being applied to content locations.</span></span>
  
- <span data-ttu-id="d0fed-158">如果您有執行迴圈的腳本，並將各位置新增至原則一 (類似于「建議做法」) 一節中所示的錯誤範例），第一個內容位置 (例如，使用者信箱) 會啟動觸發擱置狀態的同步處理常式。</span><span class="sxs-lookup"><span data-stu-id="d0fed-158">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="d0fed-159">這表示在後續的迴圈中新增至原則的其他使用者會產生錯誤。</span><span class="sxs-lookup"><span data-stu-id="d0fed-159">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
- <span data-ttu-id="d0fed-160">如果您的組織使用執行迴圈的腳本來更新保留原則的內容位置，您必須更新腳本，讓它更新單一大量作業 (中的位置，如「建議的做法」) 一節中所示的正確範例中所示。</span><span class="sxs-lookup"><span data-stu-id="d0fed-160">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
