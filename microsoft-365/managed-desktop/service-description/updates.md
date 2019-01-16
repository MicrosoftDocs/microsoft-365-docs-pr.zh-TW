---
title: Microsoft 受管理電腦中更新的處理方式
description: 保持最新的 Microsoft 受管理的桌上型電腦是速度和穩定性的平衡。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.openlocfilehash: bee6381b0f2b7b1e2d929329c3cf628ab7657678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866225"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="49f97-104">Microsoft 受管理電腦中更新的處理方式</span><span class="sxs-lookup"><span data-stu-id="49f97-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="49f97-p101">Microsoft 受管理的桌上型電腦連接至現代雲端式基礎結構的所有裝置。保持 Windows、 Office、 發行的驅動程式、 韌體和 Microsoft 存放區商務應用程式更新的最新是速度和穩定性的平衡。部署鈴響會用來確保 OS 和原則導安全的方式。</span><span class="sxs-lookup"><span data-stu-id="49f97-p101">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure. Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business application updates up to date is a balance of speed and stability. Deployment rings will be used to ensure OS and policies are rolled out in a safe manner.</span></span> 

## <a name="update-groups"></a><span data-ttu-id="49f97-108">更新群組</span><span class="sxs-lookup"><span data-stu-id="49f97-108">Update groups</span></span>

<span data-ttu-id="49f97-109">Microsoft 受管理的桌上型電腦管理更新使用 Azure AD 的四個群組：</span><span class="sxs-lookup"><span data-stu-id="49f97-109">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="49f97-p102">測試： 對非實際執行裝置用來驗證變更前的租用戶其餘跨部署所做的變更。在此響鈴的裝置已超出範圍所記載的使用者支援。</span><span class="sxs-lookup"><span data-stu-id="49f97-p102">Test: Non-production devices intended to validate changes prior to deploying the changes across the rest of the tenant. Devices in this ring are out of scope for documented end user support.</span></span> 
- <span data-ttu-id="49f97-112">第一個： 包含早期的軟體採用者和裝置可能會受限於發行前更新。</span><span class="sxs-lookup"><span data-stu-id="49f97-112">First: Contains early software adopters, and devices may be subject to pre-release updates.</span></span>
- <span data-ttu-id="49f97-p103">Fast： 設定與穩定性優先順序速度。適用於偵測品質問題之前所提供的廣泛的群組。</span><span class="sxs-lookup"><span data-stu-id="49f97-p103">Fast: Prioritizes speed over stability. Useful for detecting quality issues before they are offered to the Broad group.</span></span> 
- <span data-ttu-id="49f97-p104">列出： 有可用的功能和品質更新的最後一個群組。此群組包含使用者的承租人，讓大多數與因此偏重穩定性透過在部署的速度。</span><span class="sxs-lookup"><span data-stu-id="49f97-p104">Broad: Last group to have feature and quality updates available. This group contains the majority of users in the tenant, and therefore favors stability over speed in deployment.</span></span>

<span data-ttu-id="49f97-p105">在 Microsoft 發行的更新累計且可能會歸類為品質或功能的更新。如需詳細資訊，請參閱[Windows Update： 常見問題集](https://support.microsoft.com/help/12373/windows-update-faq)。</span><span class="sxs-lookup"><span data-stu-id="49f97-p105">Updates released by Microsoft are cumulative and may be categorized as quality or feature updates. For more information, see [Windows Update: FAQ](https://support.microsoft.com/help/12373/windows-update-faq).</span></span> 

<span data-ttu-id="49f97-119">如何更新部署的運作：</span><span class="sxs-lookup"><span data-stu-id="49f97-119">How update deployment works:</span></span>
- <span data-ttu-id="49f97-120">Microsoft 受管理的桌上型電腦部署根據下列指定的排程的新功能或品質更新。</span><span class="sxs-lookup"><span data-stu-id="49f97-120">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="49f97-p106">在部署期間 Microsoft 受管理的桌上型電腦監視的失敗或中斷 （根據遙測信號和使用者支援系統）。如果任何偵測再部署至所有目前和未來群組立即暫停。</span><span class="sxs-lookup"><span data-stu-id="49f97-p106">During deployment, Microsoft Managed Desktop monitors for signs of failure or disruption (based on telemetry signals and end-user support system). If any are detected, then the deployment to all current and future groups is immediately paused.</span></span>
    - <span data-ttu-id="49f97-123">範例： 時部署的第一個群組的品質更新發現問題時，然後更新部署至第一個、 Fast、 及列出將所有暫停，直到問題已解決。</span><span class="sxs-lookup"><span data-stu-id="49f97-123">Example: if an issue is discovered while deploying a quality update to the First group, then update deployments to First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="49f97-124">可能會回報的歸檔票證 Microsoft 受管理的桌上型電腦 IT 管理員入口網站中的相容性問題。</span><span class="sxs-lookup"><span data-stu-id="49f97-124">Compatibility issues may be reported by filing a ticket in the Microsoft Managed Desktop IT Admin portal.</span></span>
- <span data-ttu-id="49f97-p107">功能和品質更新單獨暫停。暫停作用中的預設 35 天但是可以降低或延伸根據是否會在於問題。</span><span class="sxs-lookup"><span data-stu-id="49f97-p107">Feature and quality updates are paused independently. Pause is in effect for 35 days by default, but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="49f97-127">一旦群組未暫停，部署繼續根據以下的排程。</span><span class="sxs-lookup"><span data-stu-id="49f97-127">Once the groups are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="49f97-128">此部署程序但是時間表而異各項功能和品質更新適用於。</span><span class="sxs-lookup"><span data-stu-id="49f97-128">This deployment process applies to both feature and quality updates, though the timeline varies for each.</span></span>

<table>
<tr><th colspan="5"><span data-ttu-id="49f97-129">更新部署設定</span><span class="sxs-lookup"><span data-stu-id="49f97-129">Update deployment settings</span></span></th></tr>
<tr><th><span data-ttu-id="49f97-130">更新類型</span><span class="sxs-lookup"><span data-stu-id="49f97-130">Update type</span></span></th><th><span data-ttu-id="49f97-131">測試</span><span class="sxs-lookup"><span data-stu-id="49f97-131">Test</span></span></th><th><span data-ttu-id="49f97-132">第一個</span><span class="sxs-lookup"><span data-stu-id="49f97-132">First</span></span></th><th><span data-ttu-id="49f97-133">快速</span><span class="sxs-lookup"><span data-stu-id="49f97-133">Fast</span></span></th><th><span data-ttu-id="49f97-134">廣泛</span><span class="sxs-lookup"><span data-stu-id="49f97-134">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="49f97-135">作業系統的品質更新</span><span class="sxs-lookup"><span data-stu-id="49f97-135">Quality updates for operating system</span></span></td><td><span data-ttu-id="49f97-136">0 天</span><span class="sxs-lookup"><span data-stu-id="49f97-136">0 days</span></span></td><td><span data-ttu-id="49f97-137">0 天</span><span class="sxs-lookup"><span data-stu-id="49f97-137">0 days</span></span></td><td><span data-ttu-id="49f97-138">0 天</span><span class="sxs-lookup"><span data-stu-id="49f97-138">0 days</span></span></td><td><span data-ttu-id="49f97-139">為 3 天</span><span class="sxs-lookup"><span data-stu-id="49f97-139">3 days</span></span></td></tr>
<tr><td><span data-ttu-id="49f97-140">作業系統的功能更新</span><span class="sxs-lookup"><span data-stu-id="49f97-140">Feature updates for operating system</span></span></td><td><span data-ttu-id="49f97-141">0 天</span><span class="sxs-lookup"><span data-stu-id="49f97-141">0 days</span></span></td><td><span data-ttu-id="49f97-142">30 天</span><span class="sxs-lookup"><span data-stu-id="49f97-142">30 days</span></span></td><td><span data-ttu-id="49f97-143">60 天</span><span class="sxs-lookup"><span data-stu-id="49f97-143">60 days</span></span></td><td><span data-ttu-id="49f97-144">90 天</span><span class="sxs-lookup"><span data-stu-id="49f97-144">90 days</span></span></td></tr>
<tr><td><span data-ttu-id="49f97-145">發行的驅動程式/韌體</span><span class="sxs-lookup"><span data-stu-id="49f97-145">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="49f97-146">遵循品質更新的排程</span><span class="sxs-lookup"><span data-stu-id="49f97-146">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="49f97-147">防毒定義</span><span class="sxs-lookup"><span data-stu-id="49f97-147">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="49f97-148">更新的每個掃描</span><span class="sxs-lookup"><span data-stu-id="49f97-148">Updated with each scan</span></span></td></tr>
</table>

<span data-ttu-id="49f97-p108">刻意設計這些延期期間被用來確保高的安全性與效能標準 （英文） 的所有使用者。此外，跨所有 Microsoft 受管理的桌上型電腦裝置不同範圍與更新的影響收集的資料為基礎，Microsoft 受管理的桌上型電腦會保留彈性，可修改任何及所有部署 ad 群組的上述延期期間的長度臨機操作基礎。</span><span class="sxs-lookup"><span data-stu-id="49f97-p108">These deferral periods are intentionally designed to ensure high security and performance standards for all users. Furthermore, based on data gathered across all Microsoft Managed Desktop devices and the varying scope and impact of updates, Microsoft Managed Desktop reserves flexibility to modify the length of the above deferral periods for any and all deployment groups on an ad hoc basis.</span></span>

## <a name="windows-insider-program"></a><span data-ttu-id="49f97-151">Windows 內部程式</span><span class="sxs-lookup"><span data-stu-id="49f97-151">Windows Insider Program</span></span>

<span data-ttu-id="49f97-p109">Microsoft 受管理的桌上型電腦不支援 Windows 內部程式的一部分的裝置。Windows 內部程式用來驗證測試版 Windows 軟體與適用於非關鍵性關鍵裝置的。雖然這是重要的 Microsoft 計劃，它不是廣泛實際執行環境中部署。</span><span class="sxs-lookup"><span data-stu-id="49f97-p109">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program. The Windows Insider program is used to validate pre-release Windows software and is intended for non-mission critical devices. While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="49f97-155">與 Windows 內部組建找到任何裝置將會放入測試群組而且無法供更新服務等級協定 (Sla。</span><span class="sxs-lookup"><span data-stu-id="49f97-155">Any devices found with Windows Insider builds will be put into the Test group and not be included for update service level agreements (SLAs.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="49f97-156">頻寬管理</span><span class="sxs-lookup"><span data-stu-id="49f97-156">Bandwidth management</span></span>

<span data-ttu-id="49f97-p110">傳遞最佳化適用於所有作業系統的系統與驅動程式更新。它將最小化所希望從公司網路內的對等更新下載大小從 Windows Update (WU) 服務。</span><span class="sxs-lookup"><span data-stu-id="49f97-p110">Delivery optimization is used for all operating system and driver updates. It minimizes the download size from the Windows Update (WU) service by seeking updates from peers within the corporate network.</span></span>


