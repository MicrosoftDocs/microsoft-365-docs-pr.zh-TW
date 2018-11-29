---
title: Microsoft 受管理電腦中更新的處理方式
description: 保持最新的 Microsoft 受管理的桌上型電腦是速度和穩定性的平衡。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 513e03b7d703e0a9f78281ddac764d8a29ed5c8f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866225"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a><span data-ttu-id="0c9af-104">Microsoft 受管理電腦中更新的處理方式</span><span class="sxs-lookup"><span data-stu-id="0c9af-104">How updates are handled in Microsoft Managed Desktop</span></span>


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

<span data-ttu-id="0c9af-p101">Microsoft 受管理的桌上型電腦連接至現代雲端式基礎結構的所有裝置。保持 Windows、 Office、 發行的驅動程式、 韌體和 Microsoft 存放區商務應用程式更新的最新是速度和穩定性的平衡。部署鈴響會用來確保 OS 和原則導安全的方式。</span><span class="sxs-lookup"><span data-stu-id="0c9af-p101">Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure. Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business application updates up to date is a balance of speed and stability. Deployment rings will be used to ensure OS and policies are rolled out in a safe manner.</span></span> 

## <a name="update-rings"></a><span data-ttu-id="0c9af-108">更新鈴響</span><span class="sxs-lookup"><span data-stu-id="0c9af-108">Update rings</span></span>

<span data-ttu-id="0c9af-109">Microsoft 受管理的桌上型電腦管理更新使用 Azure AD 的四個群組：</span><span class="sxs-lookup"><span data-stu-id="0c9af-109">Microsoft Managed Desktop uses four Azure AD groups to manage updates:</span></span>

- <span data-ttu-id="0c9af-110">測試： 測試及驗證的客戶租用戶中所做的變更只設計測試響鈴。</span><span class="sxs-lookup"><span data-stu-id="0c9af-110">Test: The test ring is only designed for test and validation of changes made in the customer tenant.</span></span>  
- <span data-ttu-id="0c9af-111">第一個： 第一次的目的是使用有限的 tech 知識願意早期安裝軟體並遵循某些預先發行更新的使用者才初期測試響鈴。</span><span class="sxs-lookup"><span data-stu-id="0c9af-111">First: First is intended to be an early test ring with limited tech savvy users that are willing to install software early and be subject to some pre-release updates.</span></span>
- <span data-ttu-id="0c9af-p102">Fast: Fast 響鈴為其中我們預期想大型一組使用者。 此響鈴的目標是保留裝置更新和安全與軟體傳遞快速速度。</span><span class="sxs-lookup"><span data-stu-id="0c9af-p102">Fast: The fast ring is where we would expect a large set of users.  The goal for this ring is to keep devices updated and secure with a quick pace of software delivery.</span></span>  
- <span data-ttu-id="0c9af-p103">廣泛： 慢速響鈴為平衡的傳統 roll 超出品質和功能的更新。 品質更新仍會在 fast 傳遞的腳步，但不是會立即。</span><span class="sxs-lookup"><span data-stu-id="0c9af-p103">Broad: The slow ring is a balanced conservative roll out of quality and feature updates.  Quality updates are still delivered at a fast pace, but not immediately.</span></span> 

<span data-ttu-id="0c9af-116">響鈴系統中的更新可分類為 「 品質，或更新的功能：</span><span class="sxs-lookup"><span data-stu-id="0c9af-116">The updates in the ring system are categorized as quality, or feature updates:</span></span>
- <span data-ttu-id="0c9af-p104">品質更新包括安全性、 critical、 和驅動程式更新。 這些是通常是每月的更新。</span><span class="sxs-lookup"><span data-stu-id="0c9af-p104">Quality updates include security, critical, and driver updates.  These are usually monthly updates.</span></span> 
- <span data-ttu-id="0c9af-119">功能的更新中包含不僅安全性及品質修訂但還重要功能新增及變更;他們是分號每年發行。</span><span class="sxs-lookup"><span data-stu-id="0c9af-119">Feature updates contain not only security and quality revisions, but also significant feature additions and changes; they are released semi-annually.</span></span> 

<span data-ttu-id="0c9af-120">撥打升級的運作方式：</span><span class="sxs-lookup"><span data-stu-id="0c9af-120">How ring promotion works:</span></span>
- <span data-ttu-id="0c9af-121">Microsoft 受管理的桌上型電腦部署根據下列指定的排程的新功能或品質更新。</span><span class="sxs-lookup"><span data-stu-id="0c9af-121">Microsoft Managed Desktop deploys a new feature or quality update according the schedule specified below.</span></span>
- <span data-ttu-id="0c9af-122">在部署期間 Microsoft 受管理的桌上型電腦監視的失敗或其他中斷 （透過遙測有空與我們使用者支援系統）;如果任何偵測再部署至所有目前和未來鈴響立即暫停。</span><span class="sxs-lookup"><span data-stu-id="0c9af-122">During deployment, Microsoft Managed Desktop monitors for signs of failure or other disruption (via telemetry signals and our end-user support system); if any are detected, then the deployment to all current and future rings is immediately paused.</span></span>
    - <span data-ttu-id="0c9af-123">範例： 時的品質更新部署至第一個環發現問題時，然後先、 Fast、 及列出將所有暫停直到問題已解決。</span><span class="sxs-lookup"><span data-stu-id="0c9af-123">Example: if an issue is discovered while deploying a quality update to the First ring, then First, Fast, and Broad will all be paused until the issue is resolved.</span></span>
    - <span data-ttu-id="0c9af-124">可能會回報的歸檔票證 Microsoft 受管理的桌上型電腦 IT 管理員入口網站中的相容性問題。</span><span class="sxs-lookup"><span data-stu-id="0c9af-124">Compatibility issues may be reported by filing a ticket in the Microsoft Managed Desktop IT Admin portal.</span></span>
- <span data-ttu-id="0c9af-p105">功能和品質更新單獨暫停。 暫停作用中的預設為 35 天但是可以降低或延伸根據是否會在於問題。</span><span class="sxs-lookup"><span data-stu-id="0c9af-p105">Feature and quality updates are paused independently.  Pause is in effect for 35 days by default but can be reduced or extended depending on whether the issue is remediated.</span></span>
- <span data-ttu-id="0c9af-127">一旦鈴響未暫停，部署繼續根據以下的排程。</span><span class="sxs-lookup"><span data-stu-id="0c9af-127">Once the rings are un-paused, deployment resumes according to the schedule below.</span></span>
- <span data-ttu-id="0c9af-128">此升級程序但是時間表而異各項功能和品質更新適用於。</span><span class="sxs-lookup"><span data-stu-id="0c9af-128">This promotion process applies to both feature and quality updates, though the timeline varies for each.</span></span>

<table>
<tr><th colspan="5"><span data-ttu-id="0c9af-129">鈴響和延期設定</span><span class="sxs-lookup"><span data-stu-id="0c9af-129">Rings and deferral settings</span></span></th></tr>
<tr><th><span data-ttu-id="0c9af-130">更新類型</span><span class="sxs-lookup"><span data-stu-id="0c9af-130">Update type</span></span></th><th><span data-ttu-id="0c9af-131">測試響鈴</span><span class="sxs-lookup"><span data-stu-id="0c9af-131">Test ring</span></span></th><th><span data-ttu-id="0c9af-132">第一個</span><span class="sxs-lookup"><span data-stu-id="0c9af-132">First</span></span></th><th><span data-ttu-id="0c9af-133">快速</span><span class="sxs-lookup"><span data-stu-id="0c9af-133">Fast</span></span></th><th><span data-ttu-id="0c9af-134">廣泛</span><span class="sxs-lookup"><span data-stu-id="0c9af-134">Broad</span></span></th></tr>
<tr><td><span data-ttu-id="0c9af-135">作業系統的品質更新</span><span class="sxs-lookup"><span data-stu-id="0c9af-135">Quality updates for operating system</span></span></td><td><span data-ttu-id="0c9af-136">0 天</span><span class="sxs-lookup"><span data-stu-id="0c9af-136">0 days</span></span></td><td><span data-ttu-id="0c9af-137">0 天</span><span class="sxs-lookup"><span data-stu-id="0c9af-137">0 days</span></span></td><td><span data-ttu-id="0c9af-138">1 天</span><span class="sxs-lookup"><span data-stu-id="0c9af-138">1 day</span></span></td><td><span data-ttu-id="0c9af-139">5 天</span><span class="sxs-lookup"><span data-stu-id="0c9af-139">5 days</span></span></td></tr>
<tr><td><span data-ttu-id="0c9af-140">作業系統的功能更新</span><span class="sxs-lookup"><span data-stu-id="0c9af-140">Feature updates for operating system</span></span></td><td><span data-ttu-id="0c9af-141">半年度通道 （目標） + 0 天</span><span class="sxs-lookup"><span data-stu-id="0c9af-141">Semi-annual channel (targeted) + 0 days</span></span></td><td><span data-ttu-id="0c9af-142">半年度通道 （目標） + 30 天</span><span class="sxs-lookup"><span data-stu-id="0c9af-142">Semi-annual channel (targeted) + 30 days</span></span></td><td><span data-ttu-id="0c9af-143">半年度通道 （目標） + 60 天</span><span class="sxs-lookup"><span data-stu-id="0c9af-143">Semi-annual channel (targeted) + 60 days</span></span></td><td><span data-ttu-id="0c9af-144">半年度通道 + 30 天</span><span class="sxs-lookup"><span data-stu-id="0c9af-144">Semi-annual channel + 30 days</span></span></td></tr>
<tr><td><span data-ttu-id="0c9af-145">發行的驅動程式/韌體</span><span class="sxs-lookup"><span data-stu-id="0c9af-145">Drivers/firmware</span></span></td><td colspan="4"><span data-ttu-id="0c9af-146">遵循品質更新的排程</span><span class="sxs-lookup"><span data-stu-id="0c9af-146">Follows the schedule for quality updates</span></span></td></tr>
<tr><td><span data-ttu-id="0c9af-147">防毒定義</span><span class="sxs-lookup"><span data-stu-id="0c9af-147">Anti-virus definition</span></span></td><td colspan="4"><span data-ttu-id="0c9af-148">更新的每個掃描</span><span class="sxs-lookup"><span data-stu-id="0c9af-148">Updated with each scan</span></span></td></tr>
<tr><td><span data-ttu-id="0c9af-149">若要執行的 office 親加號 click</span><span class="sxs-lookup"><span data-stu-id="0c9af-149">Office Pro-Plus click to run</span></span></td><td colspan="4"><span data-ttu-id="0c9af-150">對齊半年度通道</span><span class="sxs-lookup"><span data-stu-id="0c9af-150">Aligned with semi-annual channel</span></span></td></tr>
</table>


## <a name="windows-insider-program"></a><span data-ttu-id="0c9af-151">Windows 內部程式</span><span class="sxs-lookup"><span data-stu-id="0c9af-151">Windows Insider Program</span></span>

<span data-ttu-id="0c9af-p106">Microsoft 受管理的桌上型電腦不支援 Windows 內部程式的一部分的裝置。此程式用來驗證測試版 Windows 軟體與適用於非關鍵性關鍵裝置的。雖然這是重要的 Microsoft 計劃，它不是廣泛實際執行環境中部署。</span><span class="sxs-lookup"><span data-stu-id="0c9af-p106">Microsoft Managed Desktop does not support devices that are part of the Windows Insider program. This program is used to validate pre-release Windows software and is intended for non-mission critical devices. While this is an important Microsoft initiative, it is not intended for broad deployment in production environments.</span></span> 

<span data-ttu-id="0c9af-155">與 Windows 內部組建找到任何裝置將會放入測試響鈴而且無法供更新 Sla。</span><span class="sxs-lookup"><span data-stu-id="0c9af-155">Any devices found with Windows Insider builds will be put into the Test ring and not be included for update SLAs.</span></span>

## <a name="bandwidth-management"></a><span data-ttu-id="0c9af-156">頻寬管理</span><span class="sxs-lookup"><span data-stu-id="0c9af-156">Bandwidth management</span></span>

<span data-ttu-id="0c9af-p107">傳遞最佳化適用於所有作業系統的系統與驅動程式更新。它將最小化所希望從公司網路內的對等更新下載大小從 Windows Update (WU) 服務。</span><span class="sxs-lookup"><span data-stu-id="0c9af-p107">Delivery optimization is used for all operating system and driver updates. It minimizes the download size from the Windows Update (WU) service by seeking updates from peers within the corporate network.</span></span>


