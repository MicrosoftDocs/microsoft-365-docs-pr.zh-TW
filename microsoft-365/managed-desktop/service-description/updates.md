---
title: 如何在 Microsoft 受管理的電腦中處理更新
description: 將 Microsoft 管理的桌面保持在最新狀態，可平衡速度和穩定性。
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7e7889cb1540cb2cb164cbbd44e9ec0e480a6fd5
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678691"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="aeac2-104">如何在 Microsoft 受管理的電腦中處理更新</span><span class="sxs-lookup"><span data-stu-id="aeac2-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="aeac2-105">Microsoft 受管理的桌面會將所有裝置連接至新式雲端架構基礎結構。</span><span class="sxs-lookup"><span data-stu-id="aeac2-105">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure.</span></span> <span data-ttu-id="aeac2-106">保持最新的 Windows、Office、驅動程式、固件及 Microsoft Store for Business 應用程式是速度和穩定性的平衡。</span><span class="sxs-lookup"><span data-stu-id="aeac2-106">Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business applications up to date is a balance of speed and stability.</span></span> <span data-ttu-id="aeac2-107">部署群組將用來確保作業系統更新及原則以安全的方式推出。</span><span class="sxs-lookup"><span data-stu-id="aeac2-107">Deployment groups will be used to ensure operating system updates and policies are rolled out in a safe manner.</span></span> <span data-ttu-id="aeac2-108">如需詳細資訊，請參閱影片[Microsoft 受管理的桌面變更和發行處理](https://www.microsoft.com/videoplayer/embed/RE4mWqP)程式。</span><span class="sxs-lookup"><span data-stu-id="aeac2-108">For more about this, see the video [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).</span></span>

<span data-ttu-id="aeac2-109">Microsoft 所發行的更新會累計，而且會分類為品質或功能更新。</span><span class="sxs-lookup"><span data-stu-id="aeac2-109">Updates released by Microsoft are cumulative and are categorized as quality or feature updates.</span></span>
<span data-ttu-id="aeac2-110">如需詳細資訊，請參閱[Windows update For Business： Update types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)。</span><span class="sxs-lookup"><span data-stu-id="aeac2-110">For more information, see [Windows Update for Business: Update types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types).</span></span> 

## <a name="update-groups"></a><span data-ttu-id="aeac2-111">更新群組</span><span class="sxs-lookup"><span data-stu-id="aeac2-111">Update groups</span></span>

<span data-ttu-id="aeac2-112">Microsoft 受管理的桌面會使用四個 Azure AD 群組來管理更新：</span><span class="sxs-lookup"><span data-stu-id="aeac2-112">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="aeac2-113">**測試**：用於驗證 Microsoft 受管理的桌面原則變更、作業系統更新、功能更新和其他已推入租使用者的變更。</span><span class="sxs-lookup"><span data-stu-id="aeac2-113">**Test**: Used to validate Microsoft Managed Desktop policy changes, operating system updates, feature updates, and other changes pushed to the tenant.</span></span> <span data-ttu-id="aeac2-114">不應該有任何使用者放置在測試群組中。</span><span class="sxs-lookup"><span data-stu-id="aeac2-114">There should not be any end users placed in the test group.</span></span> <span data-ttu-id="aeac2-115">測試群組免除任何已建立的服務等級協定和使用者支援。</span><span class="sxs-lookup"><span data-stu-id="aeac2-115">The test group is exempt from any established service level agreements and end-user support.</span></span> <span data-ttu-id="aeac2-116">此群組可用於驗證應用程式與新原則或作業系統變更的相容性。</span><span class="sxs-lookup"><span data-stu-id="aeac2-116">This group is available for use to validate compatibility of applications with new policy or operating system changes.</span></span>  
- <span data-ttu-id="aeac2-117">**First**：包含早期的軟體採納者和裝置，其可能會受發行前更新的制約。</span><span class="sxs-lookup"><span data-stu-id="aeac2-117">**First**: Contains early software adopters and devices that could be subject to pre-release updates.</span></span> <span data-ttu-id="aeac2-118">如果有測試環中測試期間未涵蓋的情況，則此群組中的裝置可能會遇到中斷問題。</span><span class="sxs-lookup"><span data-stu-id="aeac2-118">Devices in this group might experience outages if there are scenarios which were not covered during testing in the test ring.</span></span>
- <span data-ttu-id="aeac2-119">**Fast**：優先執行速度高於穩定性。</span><span class="sxs-lookup"><span data-stu-id="aeac2-119">**Fast**: Prioritizes speed over stability.</span></span> <span data-ttu-id="aeac2-120">用於偵測品質問題，再將其提供給廣泛的群組。</span><span class="sxs-lookup"><span data-stu-id="aeac2-120">Useful for detecting quality issues before they are offered to the Broad group.</span></span> <span data-ttu-id="aeac2-121">這個群組是做為下一個驗證層，但通常比測試和第一個群組更穩定。</span><span class="sxs-lookup"><span data-stu-id="aeac2-121">This group serves as a next layer of validation but is generally more stable than the Test and First groups.</span></span> 
- <span data-ttu-id="aeac2-122">**廣泛**：上一個群組可提供功能和品質更新。</span><span class="sxs-lookup"><span data-stu-id="aeac2-122">**Broad**: Last group to have feature and quality updates available.</span></span> <span data-ttu-id="aeac2-123">此群組包含租使用者中大部分的使用者，因此在部署時比速度更有利於穩定性。</span><span class="sxs-lookup"><span data-stu-id="aeac2-123">This group contains the majority of users in the tenant, and therefore favors stability over speed in deployment.</span></span> <span data-ttu-id="aeac2-124">在環境最穩定的情況時，應該在這裡進行應用程式的測試。</span><span class="sxs-lookup"><span data-stu-id="aeac2-124">Testing of apps should be done here as the environment is most stable.</span></span> 

> [!NOTE]
> <span data-ttu-id="aeac2-125">如果您需要將使用者移至不同的更新群組，請提交支援要求。</span><span class="sxs-lookup"><span data-stu-id="aeac2-125">If you need to move a user to a different update group, submit a support request.</span></span> <span data-ttu-id="aeac2-126">如需提交支援要求的詳細資訊，請參閱[Microsoft Managed Desktop 的支援](support.md)。</span><span class="sxs-lookup"><span data-stu-id="aeac2-126">See [Support for Microsoft Managed Desktop](support.md) for more information on submitting support requests.</span></span> <span data-ttu-id="aeac2-127">如果您自行移動使用者，移動將會還原。</span><span class="sxs-lookup"><span data-stu-id="aeac2-127">If you move a user yourself, the move will be reverted.</span></span>

<span data-ttu-id="aeac2-128">如需這些部署群組的詳細資訊，請參閱[Microsoft 受管理的桌面角色和責任](../intro/roles-and-responsibilities.md)</span><span class="sxs-lookup"><span data-stu-id="aeac2-128">For more information roles and responsibilities with these deployment groups, see [Microsoft Managed Desktop Roles and responsibilities](../intro/roles-and-responsibilities.md)</span></span>

<span data-ttu-id="aeac2-129">更新部署的運作方式：</span><span class="sxs-lookup"><span data-stu-id="aeac2-129">How update deployment works:</span></span>
- <span data-ttu-id="aeac2-130">Microsoft 受管理的桌面會根據下列指定的排程，部署新的功能或品質更新。</span><span class="sxs-lookup"><span data-stu-id="aeac2-130">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="aeac2-131">在部署期間，Microsoft 受管理的桌面監視器會針對失敗或中斷的跡象（根據診斷資料和使用者支援系統）進行標記。</span><span class="sxs-lookup"><span data-stu-id="aeac2-131">During deployment, Microsoft Managed Desktop monitors for signs of failure or disruption (based on diagnostic data and the end-user support system).</span></span> <span data-ttu-id="aeac2-132">如果偵測到任何，則會立即暫停部署至所有目前和未來的群組。</span><span class="sxs-lookup"><span data-stu-id="aeac2-132">If any are detected, then the deployment to all current and future groups is immediately paused.</span></span>
    - <span data-ttu-id="aeac2-133">範例：如果在部署第一個群組的品質更新時會發現問題，則在解決問題之前，先將部署更新為第一個、快速和廣泛的部署。</span><span class="sxs-lookup"><span data-stu-id="aeac2-133">Example: if an issue is discovered while deploying a quality update to the First group, then update deployments to First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="aeac2-134">您可以在 Microsoft Managed Desktop Admin 入口網站中將票證歸檔，以報告相容性問題。</span><span class="sxs-lookup"><span data-stu-id="aeac2-134">Compatibility issues can be reported by filing a ticket in the Microsoft Managed Desktop Admin portal.</span></span>
- <span data-ttu-id="aeac2-135">會獨立暫停功能和品質更新。</span><span class="sxs-lookup"><span data-stu-id="aeac2-135">Feature and quality updates are paused independently.</span></span> <span data-ttu-id="aeac2-136">預設情況下，Pause 會生效于35天，但可根據問題是否已修正，加以縮短或擴充。</span><span class="sxs-lookup"><span data-stu-id="aeac2-136">Pause is in effect for 35 days by default, but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="aeac2-137">當群組未暫停時，部署會依照下列排程繼續進行。</span><span class="sxs-lookup"><span data-stu-id="aeac2-137">Once the groups are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="aeac2-138">此部署程式會同時適用于功能和品質更新，不過每個階段的時程表各有不同。</span><span class="sxs-lookup"><span data-stu-id="aeac2-138">This deployment process applies to both feature and quality updates, though the timeline varies for each.</span></span>




<table>
<tr><th colspan="5"><span data-ttu-id="aeac2-139">更新部署設定</span><span class="sxs-lookup"><span data-stu-id="aeac2-139">Update deployment settings</span></span></th></tr>
<tr><th><span data-ttu-id="aeac2-140">更新類型</span><span class="sxs-lookup"><span data-stu-id="aeac2-140">Update type</span></span></th><th><span data-ttu-id="aeac2-141">測試</span><span class="sxs-lookup"><span data-stu-id="aeac2-141">Test</span></span></th><th><span data-ttu-id="aeac2-142">名字</span><span class="sxs-lookup"><span data-stu-id="aeac2-142">First</span></span></th><th><span data-ttu-id="aeac2-143">快速</span><span class="sxs-lookup"><span data-stu-id="aeac2-143">Fast</span></span></th><th><span data-ttu-id="aeac2-144">廣泛</span><span class="sxs-lookup"><span data-stu-id="aeac2-144">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="aeac2-145">作業系統的品質更新</span><span class="sxs-lookup"><span data-stu-id="aeac2-145">Quality updates for operating system</span></span></td><td><span data-ttu-id="aeac2-146">0天</span><span class="sxs-lookup"><span data-stu-id="aeac2-146">0 days</span></span></td><td><span data-ttu-id="aeac2-147">0天</span><span class="sxs-lookup"><span data-stu-id="aeac2-147">0 days</span></span></td><td><span data-ttu-id="aeac2-148">0天</span><span class="sxs-lookup"><span data-stu-id="aeac2-148">0 days</span></span></td><td><span data-ttu-id="aeac2-149">3天</span><span class="sxs-lookup"><span data-stu-id="aeac2-149">3 days</span></span></td></tr>
<tr><td><span data-ttu-id="aeac2-150">作業系統的功能更新</span><span class="sxs-lookup"><span data-stu-id="aeac2-150">Feature updates for operating system</span></span></td><td><span data-ttu-id="aeac2-151">0天</span><span class="sxs-lookup"><span data-stu-id="aeac2-151">0 days</span></span></td><td><span data-ttu-id="aeac2-152">30 天</span><span class="sxs-lookup"><span data-stu-id="aeac2-152">30 days</span></span></td><td><span data-ttu-id="aeac2-153">60 天</span><span class="sxs-lookup"><span data-stu-id="aeac2-153">60 days</span></span></td><td><span data-ttu-id="aeac2-154">90 天</span><span class="sxs-lookup"><span data-stu-id="aeac2-154">90 days</span></span></td></tr>
<tr><td><span data-ttu-id="aeac2-155">驅動程式/固件</span><span class="sxs-lookup"><span data-stu-id="aeac2-155">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="aeac2-156">遵循品質更新的排程</span><span class="sxs-lookup"><span data-stu-id="aeac2-156">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="aeac2-157">防病毒定義</span><span class="sxs-lookup"><span data-stu-id="aeac2-157">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="aeac2-158">更新每個掃描</span><span class="sxs-lookup"><span data-stu-id="aeac2-158">Updated with each scan</span></span></td></tr>
<tr><td><span data-ttu-id="aeac2-159">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="aeac2-159">Microsoft 365 Apps for enterprise</span></span></td><td colspan="4"><span data-ttu-id="aeac2-160">遵循 Office 的目前通道</span><span class="sxs-lookup"><span data-stu-id="aeac2-160">Follows Office's Current Channel</span></span>
</table>

<span data-ttu-id="aeac2-161">如需適用于企業的 Microsoft 365 應用程式目前通道的詳細資訊，請參閱[microsoft 365 應用程式的更新通道概述](https://docs.microsoft.com/deployoffice/overview-update-channels)。</span><span class="sxs-lookup"><span data-stu-id="aeac2-161">For more information about Current Channel for Microsoft 365 Apps for enterprise, see [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span>

>[!NOTE]
><span data-ttu-id="aeac2-162">這些延期期間是特意設計，以確保所有使用者的高安全性和效能標準。</span><span class="sxs-lookup"><span data-stu-id="aeac2-162">These deferral periods are intentionally designed to ensure high security and performance standards for all users.</span></span> <span data-ttu-id="aeac2-163">此外，根據在所有 Microsoft 受管理的桌面裝置上收集的資料，以及更新的範圍和影響，Microsoft 受管理的桌面保留可靈活修改任何和所有部署群組的上述延遲週期長度。</span><span class="sxs-lookup"><span data-stu-id="aeac2-163">Furthermore, based on data gathered across all Microsoft Managed Desktop devices and the varying scope and impact of updates, Microsoft Managed Desktop reserves flexibility to modify the length of the above deferral periods for any and all deployment groups on an ad hoc basis.</span></span>
>
><span data-ttu-id="aeac2-164">Microsoft 受管理的桌面會針對每個 Windows 功能版本執行獨立評估，以評估其必要和對其受管理承租人的有用性。</span><span class="sxs-lookup"><span data-stu-id="aeac2-164">Microsoft Managed Desktop conducts an independent assessment of each Windows feature release to evaluate its necessity and usefulness to its managed tenants.</span></span> <span data-ttu-id="aeac2-165">因此，Microsoft 受管理的桌面可能會或不會部署所有 Windows 功能更新。</span><span class="sxs-lookup"><span data-stu-id="aeac2-165">Consequently, Microsoft Managed Desktop might or might not deploy all Windows feature updates.</span></span> 

## <a name="windows-insider-program"></a><span data-ttu-id="aeac2-166">Windows 測試人員計畫</span><span class="sxs-lookup"><span data-stu-id="aeac2-166">Windows Insider Program</span></span>

<span data-ttu-id="aeac2-167">Microsoft 受管理的桌面不支援屬於 Windows 預覽體驗計畫的裝置。</span><span class="sxs-lookup"><span data-stu-id="aeac2-167">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program.</span></span> <span data-ttu-id="aeac2-168">Windows 有問必答計畫是用來驗證預先發行的 Windows 軟體，其適用于並非要徑任務的裝置。</span><span class="sxs-lookup"><span data-stu-id="aeac2-168">The Windows Insider program is used to validate pre-release Windows software and is intended for devices that aren't mission critical.</span></span> <span data-ttu-id="aeac2-169">雖然這是一個重要的 Microsoft 倡議，但不是要在實際執行環境中進行廣泛的部署。</span><span class="sxs-lookup"><span data-stu-id="aeac2-169">While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="aeac2-170">任何找到 Windows 測試人員組建的裝置，都可能會放入測試群組，且不會從 Microsoft Managed Desktop 的更新服務等級協定和使用者支援中免除。</span><span class="sxs-lookup"><span data-stu-id="aeac2-170">Any devices found with Windows Insider builds might be put into the Test group and will be exempt from update service level agreements and end-user support from Microsoft Managed Desktop.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="aeac2-171">頻寬管理</span><span class="sxs-lookup"><span data-stu-id="aeac2-171">Bandwidth management</span></span>

<span data-ttu-id="aeac2-172">我們使用[傳遞優化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)來進行所有作業系統及驅動程式更新。</span><span class="sxs-lookup"><span data-stu-id="aeac2-172">We use [Delivery Optimization](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) for all operating system and driver updates.</span></span> <span data-ttu-id="aeac2-173">這可透過從公司網路中的對等機器尋找更新，將 Windows Update service 的下載大小降到最低。</span><span class="sxs-lookup"><span data-stu-id="aeac2-173">This minimizes the download size from the Windows Update service by seeking updates from peers within the corporate network.</span></span>


