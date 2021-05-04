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
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860384"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="db1df-103">疑難排解電子文件探索保留錯誤</span><span class="sxs-lookup"><span data-stu-id="db1df-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="db1df-104">本文討論 eDiscovery 保留可能發生的常見問題，以及如何解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="db1df-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="db1df-105">本文也包含建議的做法，可協助您緩解或避免這些問題。</span><span class="sxs-lookup"><span data-stu-id="db1df-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="db1df-106">建議的做法</span><span class="sxs-lookup"><span data-stu-id="db1df-106">Recommended practices</span></span>

<span data-ttu-id="db1df-107">若要減少與 eDiscovery 保留相關的錯誤數，建議採用下列做法：</span><span class="sxs-lookup"><span data-stu-id="db1df-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="db1df-108">如果保留分配仍處於擱置狀態，且狀態為 [ `On (Pending)` 或] `Off (Pending)` ，請等到保留分配完成之後，再進行進一步的更新。</span><span class="sxs-lookup"><span data-stu-id="db1df-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="db1df-109">將更新合併到單一大量要求中的 eDiscovery 保留，而不是針對每個交易重複更新保留原則。</span><span class="sxs-lookup"><span data-stu-id="db1df-109">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="db1df-110">例如，若要使用 [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) Cmdlet 將多個使用者信箱新增至現有的保留原則，請執行命令 (或新增為腳本) 的程式碼區塊，使其只執行一次，才能新增多個使用者。</span><span class="sxs-lookup"><span data-stu-id="db1df-110">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="db1df-111">**正確**</span><span class="sxs-lookup"><span data-stu-id="db1df-111">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="db1df-112">**不正確**</span><span class="sxs-lookup"><span data-stu-id="db1df-112">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="db1df-113">在上述錯誤的範例中，Cmdlet 會執行五個不同的時間來完成任務。</span><span class="sxs-lookup"><span data-stu-id="db1df-113">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="db1df-114">如需將使用者新增至保留原則的建議作法的詳細資訊，請參閱 [more information](#more-information) 一節。</span><span class="sxs-lookup"><span data-stu-id="db1df-114">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="db1df-115">在取得 eDiscovery 保留問題的 Microsoft 支援服務之前，請遵循 [錯誤/問題中的步驟： [保留未同步](#errorissue-holds-dont-sync) 處理] 區段以重試保留發佈。</span><span class="sxs-lookup"><span data-stu-id="db1df-115">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="db1df-116">此處理程式通常會解決暫時問題，包括內部伺服器錯誤。</span><span class="sxs-lookup"><span data-stu-id="db1df-116">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="db1df-117">錯誤/問題：保留未同步處理</span><span class="sxs-lookup"><span data-stu-id="db1df-117">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="db1df-118">如果您在將保管人和資料來源置於保留狀態時看到下列錯誤訊息，請使用解決步驟來對問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="db1df-118">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="db1df-119">資源：部署原則所花費的時間超過預期。</span><span class="sxs-lookup"><span data-stu-id="db1df-119">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="db1df-120">更新最終部署狀態可能需要另外2小時，所以請在幾小時內回來查看。</span><span class="sxs-lookup"><span data-stu-id="db1df-120">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="db1df-121">由於暫時性的 Office 365 資料中心問題，無法將原則部署至內容來源。</span><span class="sxs-lookup"><span data-stu-id="db1df-121">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="db1df-122">目前的原則不會套用到來源中的任何內容，因此不會影響已封鎖的部署。</span><span class="sxs-lookup"><span data-stu-id="db1df-122">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="db1df-123">若要修正此問題，請嘗試重新部署原則。</span><span class="sxs-lookup"><span data-stu-id="db1df-123">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="db1df-124">對不起，由於暫時性的內部伺服器錯誤，我們無法對原則執行所要求的變更。</span><span class="sxs-lookup"><span data-stu-id="db1df-124">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="db1df-125">請在30分鐘後再試一次。</span><span class="sxs-lookup"><span data-stu-id="db1df-125">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="db1df-126">解決方案</span><span class="sxs-lookup"><span data-stu-id="db1df-126">Resolution</span></span>

1. <span data-ttu-id="db1df-127">連線至[安全性 & 規範中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)並執行 eDiscovery hold 的下列命令：</span><span class="sxs-lookup"><span data-stu-id="db1df-127">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="db1df-128">檢查 *DistributionDetail* 參數中的值。</span><span class="sxs-lookup"><span data-stu-id="db1df-128">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="db1df-129">尋找如下的錯誤：</span><span class="sxs-lookup"><span data-stu-id="db1df-129">Look for errors like the following:</span></span>

   > <span data-ttu-id="db1df-130">錯誤：資源：部署原則所花費的時間超過預期。</span><span class="sxs-lookup"><span data-stu-id="db1df-130">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="db1df-131">更新最終部署狀態可能需要另外2小時，所以請在幾小時內回來查看。</span><span class="sxs-lookup"><span data-stu-id="db1df-131">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="db1df-132">嘗試在有問題的保留原則上執行 **Set-CaseHoldPolicy RetryDistribution** 命令;例如：</span><span class="sxs-lookup"><span data-stu-id="db1df-132">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a><span data-ttu-id="db1df-133">其他資訊</span><span class="sxs-lookup"><span data-stu-id="db1df-133">More information</span></span>

- <span data-ttu-id="db1df-134">在「建議的做法」一節中，針對多位使用者更新保留原則的指導，是由系統封鎖保留原則同時更新所產生的結果。</span><span class="sxs-lookup"><span data-stu-id="db1df-134">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="db1df-135">這表示當更新的保留原則套用至新的內容位置，且保留原則處於擱置狀態時，無法將其他內容位置新增至保留原則。</span><span class="sxs-lookup"><span data-stu-id="db1df-135">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="db1df-136">以下是一些您應記住的事項，以協助您緩解此問題：</span><span class="sxs-lookup"><span data-stu-id="db1df-136">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
  - <span data-ttu-id="db1df-137">每次更新保留更新時，就會立即進入暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="db1df-137">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="db1df-138">[擱置狀態] 狀態表示正在將保留套用至內容位置。</span><span class="sxs-lookup"><span data-stu-id="db1df-138">The pending state status means the hold is being applied to content locations.</span></span>
  
  - <span data-ttu-id="db1df-139">如果您有執行迴圈的腳本，並將各位置新增至原則一 (類似于「建議做法」) 一節中所示的錯誤範例），第一個內容位置 (例如，使用者信箱) 會啟動觸發擱置狀態的同步處理常式。</span><span class="sxs-lookup"><span data-stu-id="db1df-139">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="db1df-140">這表示在後續的迴圈中新增至原則的其他使用者會產生錯誤。</span><span class="sxs-lookup"><span data-stu-id="db1df-140">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
  - <span data-ttu-id="db1df-141">如果您的組織使用執行迴圈的腳本來更新保留原則的內容位置，您必須更新腳本，讓它更新單一大量作業 (中的位置，如「建議的做法」) 一節中所示的正確範例中所示。</span><span class="sxs-lookup"><span data-stu-id="db1df-141">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
