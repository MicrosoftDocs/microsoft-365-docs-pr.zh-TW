---
title: Microsoft 受管理電腦中更新的處理方式
description: 保持最新 Microsoft 受管理的電腦是權衡方式速度與穩定性。
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c2ab48c87f1239c21e6620ea00640bb3dabbdd45
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981634"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="75f4e-104">Microsoft 受管理電腦中更新的處理方式</span><span class="sxs-lookup"><span data-stu-id="75f4e-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="75f4e-105">Microsoft 受管理的電腦會將所有的裝置連接到新式的基於雲端的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="75f4e-105">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure.</span></span> <span data-ttu-id="75f4e-106">保持 Windows、 Office、 驅動程式、 韌體和 Microsoft 網上商店商務應用程式的最新狀態是權衡方式速度與穩定性。</span><span class="sxs-lookup"><span data-stu-id="75f4e-106">Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business applications up to date is a balance of speed and stability.</span></span> <span data-ttu-id="75f4e-107">部署群組將會用來確保作業系統更新，原則會導入安全的方式。</span><span class="sxs-lookup"><span data-stu-id="75f4e-107">Deployment groups will be used to ensure operating system updates and policies are rolled out in a safe manner.</span></span> 

<span data-ttu-id="75f4e-108">由 Microsoft 發行的更新是累加的並可分類為 「 品質] 或 [功能更新。</span><span class="sxs-lookup"><span data-stu-id="75f4e-108">Updates released by Microsoft are cumulative and are categorized as quality or feature updates.</span></span>
<span data-ttu-id="75f4e-109">如需詳細資訊，請參閱[適用於企業的 Windows 更新： 更新類型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)。</span><span class="sxs-lookup"><span data-stu-id="75f4e-109">For more information, see [Windows Update for Business: Update types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types).</span></span> 

## <a name="update-groups"></a><span data-ttu-id="75f4e-110">更新群組</span><span class="sxs-lookup"><span data-stu-id="75f4e-110">Update groups</span></span>

<span data-ttu-id="75f4e-111">Microsoft 受管理的電腦使用四個 Azure AD 群組管理更新：</span><span class="sxs-lookup"><span data-stu-id="75f4e-111">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="75f4e-112">**測試**： 用來驗證 Microsoft 受管理電腦原則變更，作業系統系統更新功能更新，以及其他變更推送至租用戶。</span><span class="sxs-lookup"><span data-stu-id="75f4e-112">**Test**: Used to validate Microsoft Managed Desktop policy changes, operating system updates, feature updates, and other changes pushed to the tenant.</span></span> <span data-ttu-id="75f4e-113">不應該放置在測試群組中任何使用者。</span><span class="sxs-lookup"><span data-stu-id="75f4e-113">There should not be any end users placed in the test group.</span></span> <span data-ttu-id="75f4e-114">測試群組是免除任何已建立的服務等級協定和使用者支援。</span><span class="sxs-lookup"><span data-stu-id="75f4e-114">The test group is exempt from any established service level agreements and end-user support.</span></span> <span data-ttu-id="75f4e-115">此群組適用於驗證的新原則] 或 [作業系統 hanges 應用程式相容性。</span><span class="sxs-lookup"><span data-stu-id="75f4e-115">This group is available for use to validate compatibility of applications with new policy or operating system hanges.</span></span>  
- <span data-ttu-id="75f4e-116">**第一個**： 包含早期軟體採納者和可能受到搶鮮版更新的裝置。</span><span class="sxs-lookup"><span data-stu-id="75f4e-116">**First**: Contains early software adopters and devices that could be subject to pre-release updates.</span></span> <span data-ttu-id="75f4e-117">如果有程式以測試環狀測試期間未深入涵蓋的案例，此群組中的裝置可能會遇到中斷。</span><span class="sxs-lookup"><span data-stu-id="75f4e-117">Devices in this group might experience outages if there are scenarios which were not covered during testing in the test ring.</span></span>
- <span data-ttu-id="75f4e-118">**Fast**： 來透過穩定性的優先順序速度。</span><span class="sxs-lookup"><span data-stu-id="75f4e-118">**Fast**: Prioritizes speed over stability.</span></span> <span data-ttu-id="75f4e-119">適用於偵測品質問題，其提供給廣泛群組之前。</span><span class="sxs-lookup"><span data-stu-id="75f4e-119">Useful for detecting quality issues before they are offered to the Broad group.</span></span> <span data-ttu-id="75f4e-120">此群組做為下一個圖層的驗證，但通常更穩定，比測試與第一個群組。</span><span class="sxs-lookup"><span data-stu-id="75f4e-120">This group serves as a next layer of validation but is generally more stable than the Test and First groups.</span></span> 
- <span data-ttu-id="75f4e-121">**廣泛**： 有可用的功能和品質更新的最後一個群組。</span><span class="sxs-lookup"><span data-stu-id="75f4e-121">**Broad**: Last group to have feature and quality updates available.</span></span> <span data-ttu-id="75f4e-122">此群組包含大多數的租用戶中的使用者，並因此偏好穩定性使用透過部署中的速度。</span><span class="sxs-lookup"><span data-stu-id="75f4e-122">This group contains the majority of users in the tenant, and therefore favors stability over speed in deployment.</span></span> <span data-ttu-id="75f4e-123">應執行的應用程式的測試環境是最穩定在這裡。</span><span class="sxs-lookup"><span data-stu-id="75f4e-123">Testing of apps should be done here as the environment is most stable.</span></span> 

> [!NOTE]
> <span data-ttu-id="75f4e-124">如果您需要將使用者移至不同的更新群組，提交支援要求。</span><span class="sxs-lookup"><span data-stu-id="75f4e-124">If you need to move a user to a different update group, submit a support request.</span></span> <span data-ttu-id="75f4e-125">如需提交支援要求的詳細資訊，請參閱[Microsoft 受管理電腦的支援](support.md)。</span><span class="sxs-lookup"><span data-stu-id="75f4e-125">See [Support for Microsoft Managed Desktop](support.md) for more information on submitting support requests.</span></span> <span data-ttu-id="75f4e-126">如果您自行移動使用者，將還原移動。</span><span class="sxs-lookup"><span data-stu-id="75f4e-126">If you move a user yourself, the move will be reverted.</span></span>

<span data-ttu-id="75f4e-127">如需詳細資訊的角色與責任與這些部署群組，請參閱[Microsoft 受管理的桌上型電腦角色和責任](../intro/roles-and-responsibilities.md)</span><span class="sxs-lookup"><span data-stu-id="75f4e-127">For more information roles and responsibilities with these deployment groups, see [Microsoft Managed Desktop Roles and responsibilities](../intro/roles-and-responsibilities.md)</span></span>

<span data-ttu-id="75f4e-128">如何更新部署的運作：</span><span class="sxs-lookup"><span data-stu-id="75f4e-128">How update deployment works:</span></span>
- <span data-ttu-id="75f4e-129">Microsoft 受管理電腦部署根據以下指定的排程的新功能或品質更新。</span><span class="sxs-lookup"><span data-stu-id="75f4e-129">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="75f4e-130">部署期間，Microsoft 受管理的電腦會監視的失敗或中斷 （根據診斷資料和使用者支援系統）。</span><span class="sxs-lookup"><span data-stu-id="75f4e-130">During deployment, Microsoft Managed Desktop monitors for signs of failure or disruption (based on diagnostic data and the end-user support system).</span></span> <span data-ttu-id="75f4e-131">如果任何偵測到，會立即暫停部署，以目前和未來的所有群組。</span><span class="sxs-lookup"><span data-stu-id="75f4e-131">If any are detected, then the deployment to all current and future groups is immediately paused.</span></span>
    - <span data-ttu-id="75f4e-132">範例： 如果發現問題時，同時部署品質更新的第一個群組，然後更新部署至名字]、 [Fast 和 [廣泛將所有暫停，直到問題解決為止。</span><span class="sxs-lookup"><span data-stu-id="75f4e-132">Example: if an issue is discovered while deploying a quality update to the First group, then update deployments to First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="75f4e-133">可由 Microsoft 受管理的桌上型電腦系統管理入口網站中歸檔票證報告相容性問題。</span><span class="sxs-lookup"><span data-stu-id="75f4e-133">Compatibility issues can be reported by filing a ticket in the Microsoft Managed Desktop Admin portal.</span></span>
- <span data-ttu-id="75f4e-134">功能和品質更新獨立暫停。</span><span class="sxs-lookup"><span data-stu-id="75f4e-134">Feature and quality updates are paused independently.</span></span> <span data-ttu-id="75f4e-135">暫停是作用中的預設值，為 35 天但是可以降低或根據是否已修復此問題： 延伸。</span><span class="sxs-lookup"><span data-stu-id="75f4e-135">Pause is in effect for 35 days by default, but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="75f4e-136">一旦群組未暫停，部署會繼續根據下列的排程。</span><span class="sxs-lookup"><span data-stu-id="75f4e-136">Once the groups are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="75f4e-137">此部署程序適用於功能和品質更新，但是時間表而異每個。</span><span class="sxs-lookup"><span data-stu-id="75f4e-137">This deployment process applies to both feature and quality updates, though the timeline varies for each.</span></span>




<table>
<tr><th colspan="5"><span data-ttu-id="75f4e-138">更新部署設定</span><span class="sxs-lookup"><span data-stu-id="75f4e-138">Update deployment settings</span></span></th></tr>
<tr><th><span data-ttu-id="75f4e-139">更新類型</span><span class="sxs-lookup"><span data-stu-id="75f4e-139">Update type</span></span></th><th><span data-ttu-id="75f4e-140">測試</span><span class="sxs-lookup"><span data-stu-id="75f4e-140">Test</span></span></th><th><span data-ttu-id="75f4e-141">名字</span><span class="sxs-lookup"><span data-stu-id="75f4e-141">First</span></span></th><th><span data-ttu-id="75f4e-142">快速</span><span class="sxs-lookup"><span data-stu-id="75f4e-142">Fast</span></span></th><th><span data-ttu-id="75f4e-143">廣泛</span><span class="sxs-lookup"><span data-stu-id="75f4e-143">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="75f4e-144">作業系統的品質更新</span><span class="sxs-lookup"><span data-stu-id="75f4e-144">Quality updates for operating system</span></span></td><td><span data-ttu-id="75f4e-145">0 天</span><span class="sxs-lookup"><span data-stu-id="75f4e-145">0 days</span></span></td><td><span data-ttu-id="75f4e-146">0 天</span><span class="sxs-lookup"><span data-stu-id="75f4e-146">0 days</span></span></td><td><span data-ttu-id="75f4e-147">0 天</span><span class="sxs-lookup"><span data-stu-id="75f4e-147">0 days</span></span></td><td><span data-ttu-id="75f4e-148">3 天</span><span class="sxs-lookup"><span data-stu-id="75f4e-148">3 days</span></span></td></tr>
<tr><td><span data-ttu-id="75f4e-149">作業系統功能更新</span><span class="sxs-lookup"><span data-stu-id="75f4e-149">Feature updates for operating system</span></span></td><td><span data-ttu-id="75f4e-150">0 天</span><span class="sxs-lookup"><span data-stu-id="75f4e-150">0 days</span></span></td><td><span data-ttu-id="75f4e-151">30 天</span><span class="sxs-lookup"><span data-stu-id="75f4e-151">30 days</span></span></td><td><span data-ttu-id="75f4e-152">60 天</span><span class="sxs-lookup"><span data-stu-id="75f4e-152">60 days</span></span></td><td><span data-ttu-id="75f4e-153">90 天</span><span class="sxs-lookup"><span data-stu-id="75f4e-153">90 days</span></span></td></tr>
<tr><td><span data-ttu-id="75f4e-154">驅動程式/韌體</span><span class="sxs-lookup"><span data-stu-id="75f4e-154">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="75f4e-155">遵循品質更新的排程</span><span class="sxs-lookup"><span data-stu-id="75f4e-155">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="75f4e-156">防毒定義</span><span class="sxs-lookup"><span data-stu-id="75f4e-156">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="75f4e-157">更新每個掃描</span><span class="sxs-lookup"><span data-stu-id="75f4e-157">Updated with each scan</span></span></td></tr>
<tr><td><span data-ttu-id="75f4e-158">Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="75f4e-158">Office 365 ProPlus</span></span></td><td colspan="4"><span data-ttu-id="75f4e-159">採用 Office 的每月通道</span><span class="sxs-lookup"><span data-stu-id="75f4e-159">Follows Office's Monthly Channel</span></span>
</table>

<span data-ttu-id="75f4e-160">Office 365 專業增強版每月通道的相關資訊，請參閱[Office 365 專業增強版更新通道的概觀](https://docs.microsoft.com/deployoffice/overview-of-update-channels-for-office-365-proplus)。</span><span class="sxs-lookup"><span data-stu-id="75f4e-160">For more information about the Monthly Channel for Office 365 ProPlus, see [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-of-update-channels-for-office-365-proplus).</span></span>

>[!NOTE]
><span data-ttu-id="75f4e-161">這些延期期間刻意為了確保高的安全性和效能標準的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="75f4e-161">These deferral periods are intentionally designed to ensure high security and performance standards for all users.</span></span> <span data-ttu-id="75f4e-162">此外，跨所有 Microsoft 受管理的電腦裝置和不同範圍及更新的影響所收集的資料為基礎，Microsoft 受管理的電腦會保留彈性，可修改 ad 上的任何及所有部署群組的上述延期期間的長度特別為基礎。</span><span class="sxs-lookup"><span data-stu-id="75f4e-162">Furthermore, based on data gathered across all Microsoft Managed Desktop devices and the varying scope and impact of updates, Microsoft Managed Desktop reserves flexibility to modify the length of the above deferral periods for any and all deployment groups on an ad hoc basis.</span></span>
>
><span data-ttu-id="75f4e-163">Microsoft 受管理的電腦進行獨立評估的每個要評估其和實用性至其受管理的租用戶的 Windows 功能版本。</span><span class="sxs-lookup"><span data-stu-id="75f4e-163">Microsoft Managed Desktop conducts an independent assessment of each Windows feature release to evaluate its necessity and usefulness to its managed tenants.</span></span> <span data-ttu-id="75f4e-164">因此，Microsoft 受管理的電腦可能或可能不會部署所有的 Windows 功能更新。</span><span class="sxs-lookup"><span data-stu-id="75f4e-164">Consequently, Microsoft Managed Desktop might or might not deploy all Windows feature updates.</span></span> 

## <a name="windows-insider-program"></a><span data-ttu-id="75f4e-165">Windows 測試人員計畫</span><span class="sxs-lookup"><span data-stu-id="75f4e-165">Windows Insider Program</span></span>

<span data-ttu-id="75f4e-166">Microsoft 受管理的電腦不支援 Windows 測試人員計畫的一部分的裝置。</span><span class="sxs-lookup"><span data-stu-id="75f4e-166">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program.</span></span> <span data-ttu-id="75f4e-167">Windows 測試人員計畫用來驗證搶鮮版 Windows 軟體，僅適用於不重要的裝置。</span><span class="sxs-lookup"><span data-stu-id="75f4e-167">The Windows Insider program is used to validate pre-release Windows software and is intended for devices that aren't mission critical.</span></span> <span data-ttu-id="75f4e-168">雖然這是很重要的 Microsoft 計劃，但它不是實際執行環境中的廣泛部署。</span><span class="sxs-lookup"><span data-stu-id="75f4e-168">While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="75f4e-169">與 Windows 測試人員組建找到任何裝置可能會放入測試群組，而且會是免除更新的服務等級協定及從 Microsoft 受管理電腦的使用者支援。</span><span class="sxs-lookup"><span data-stu-id="75f4e-169">Any devices found with Windows Insider builds might be put into the Test group and will be exempt from update service level agreements and end-user support from Microsoft Managed Desktop.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="75f4e-170">頻寬管理</span><span class="sxs-lookup"><span data-stu-id="75f4e-170">Bandwidth management</span></span>

<span data-ttu-id="75f4e-171">我們所有的作業系統和驅動程式更新使用[傳遞最佳化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)。</span><span class="sxs-lookup"><span data-stu-id="75f4e-171">We use [Delivery Optimization](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) for all operating system and driver updates.</span></span> <span data-ttu-id="75f4e-172">這將最小化的搜尋從公司網路內的對等的更新從 Windows Update 服務的下載大小。</span><span class="sxs-lookup"><span data-stu-id="75f4e-172">This minimizes the download size from the Windows Update service by seeking updates from peers within the corporate network.</span></span>


