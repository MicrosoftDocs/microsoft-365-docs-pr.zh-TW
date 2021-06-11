---
title: 使用群組原則排程防病毒掃描
description: 使用群組原則設定防病毒掃描
keywords: 快速掃描、完整掃描、排程、群組原則、防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6f6018ec8b514234ab4f98e3d5416b472ff88739
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879693"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a><span data-ttu-id="2af49-104">使用群組原則排程防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-104">Schedule antivirus scans using Group Policy</span></span>

<span data-ttu-id="2af49-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2af49-105">**Applies to:**</span></span>

- [<span data-ttu-id="2af49-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2af49-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2af49-107">本文說明如何使用「群組原則」設定排程掃描。</span><span class="sxs-lookup"><span data-stu-id="2af49-107">This article describes how to configure scheduled scans using Group Policy.</span></span> <span data-ttu-id="2af49-108">若要深入瞭解排程掃描及掃描類型的相關資訊，請參閱[設定排程快速或完整 Microsoft Defender 防毒軟體掃描](schedule-antivirus-scans.md)。</span><span class="sxs-lookup"><span data-stu-id="2af49-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="configure-antivirus-scans-using-group-policy"></a><span data-ttu-id="2af49-109">使用群組原則設定防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-109">Configure antivirus scans using Group Policy</span></span>

1. <span data-ttu-id="2af49-110">在您的群組原則管理電腦上，在 [群組原則編輯器] 中，移至 [電腦設定]**系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **掃描**]。</span><span class="sxs-lookup"><span data-stu-id="2af49-110">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="2af49-111">以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2af49-111">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="2af49-112">指定「群組原則」物件的設定，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2af49-112">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="2af49-113">針對每個您要設定的設定，請重複步驟1-4。</span><span class="sxs-lookup"><span data-stu-id="2af49-113">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="2af49-114">照常部署您的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="2af49-114">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="2af49-115">如果您需要「群組原則」物件的協助，請參閱 [建立群組原則物件](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。</span><span class="sxs-lookup"><span data-stu-id="2af49-115">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

> [!TIP]
> <span data-ttu-id="2af49-116">請參閱 [管理應下載及套用保護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) ，並 [防止或允許使用者在本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主題。</span><span class="sxs-lookup"><span data-stu-id="2af49-116">See the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="group-policy-settings-for-scheduling-scans"></a><span data-ttu-id="2af49-117">排程掃描的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="2af49-117">Group Policy settings for scheduling scans</span></span>

| <span data-ttu-id="2af49-118">位置</span><span class="sxs-lookup"><span data-stu-id="2af49-118">Location</span></span> | <span data-ttu-id="2af49-119">設定</span><span class="sxs-lookup"><span data-stu-id="2af49-119">Setting</span></span> | <span data-ttu-id="2af49-120">描述</span><span class="sxs-lookup"><span data-stu-id="2af49-120">Description</span></span> | <span data-ttu-id="2af49-121">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="2af49-121">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="2af49-122">掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-122">Scan</span></span> | <span data-ttu-id="2af49-123">指定用於排程掃描的掃描類型</span><span class="sxs-lookup"><span data-stu-id="2af49-123">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="2af49-124">快速掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-124">Quick scan</span></span> |
| <span data-ttu-id="2af49-125">掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-125">Scan</span></span> | <span data-ttu-id="2af49-126">指定一周中的哪一天執行排程掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-126">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="2af49-127">指定 [天] (或 [永不) ] 執行掃描。</span><span class="sxs-lookup"><span data-stu-id="2af49-127">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="2af49-128">從來不需要</span><span class="sxs-lookup"><span data-stu-id="2af49-128">Never</span></span> |
| <span data-ttu-id="2af49-129">掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-129">Scan</span></span> | <span data-ttu-id="2af49-130">指定一天中執行排程掃描的時間</span><span class="sxs-lookup"><span data-stu-id="2af49-130">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="2af49-131">指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) 。</span><span class="sxs-lookup"><span data-stu-id="2af49-131">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="2af49-132">淩晨2點</span><span class="sxs-lookup"><span data-stu-id="2af49-132">2 a.m.</span></span> |
| <span data-ttu-id="2af49-133">根</span><span class="sxs-lookup"><span data-stu-id="2af49-133">Root</span></span> | <span data-ttu-id="2af49-134">隨機化排程的任務時間</span><span class="sxs-lookup"><span data-stu-id="2af49-134">Randomize scheduled task times</span></span> |<span data-ttu-id="2af49-135">在 Microsoft Defender 防毒軟體中，將掃描的開始時間隨機化為從0到4小時的任何間隔。</span><span class="sxs-lookup"><span data-stu-id="2af49-135">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="2af49-136">在 [SCEP](/mem/intune/protect/certificates-scep-configure)中，隨機化掃描任何間隔加上或減30分鐘。</span><span class="sxs-lookup"><span data-stu-id="2af49-136">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="2af49-137">這對虛擬機器或 VDI 部署很有用。</span><span class="sxs-lookup"><span data-stu-id="2af49-137">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="2af49-138">啟用</span><span class="sxs-lookup"><span data-stu-id="2af49-138">Enabled</span></span> |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="2af49-139">在端點未使用時進行排程掃描的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="2af49-139">Group Policy settings for scheduling scans for when an endpoint is not in use</span></span>

| <span data-ttu-id="2af49-140">位置</span><span class="sxs-lookup"><span data-stu-id="2af49-140">Location</span></span> | <span data-ttu-id="2af49-141">設定</span><span class="sxs-lookup"><span data-stu-id="2af49-141">Setting</span></span> | <span data-ttu-id="2af49-142">描述</span><span class="sxs-lookup"><span data-stu-id="2af49-142">Description</span></span> | <span data-ttu-id="2af49-143">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="2af49-143">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="2af49-144">掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-144">Scan</span></span> | <span data-ttu-id="2af49-145">僅當電腦已開啟但未在使用中時啟動排程掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-145">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="2af49-146">除非電腦已開啟但未在使用中，否則不會執行排程掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-146">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="2af49-147">啟用</span><span class="sxs-lookup"><span data-stu-id="2af49-147">Enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="2af49-148">當您排程掃描時未使用端點時，掃描功能不會服從 CPU 節流設定，而且將充分利用可讓您盡可能快地完成掃描的資源。</span><span class="sxs-lookup"><span data-stu-id="2af49-148">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a><span data-ttu-id="2af49-149">排程修正的群組原則設定-必要的掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-149">Group Policy settings for scheduling remediation-required scans</span></span>

| <span data-ttu-id="2af49-150">位置</span><span class="sxs-lookup"><span data-stu-id="2af49-150">Location</span></span> | <span data-ttu-id="2af49-151">設定</span><span class="sxs-lookup"><span data-stu-id="2af49-151">Setting</span></span> | <span data-ttu-id="2af49-152">描述</span><span class="sxs-lookup"><span data-stu-id="2af49-152">Description</span></span> | <span data-ttu-id="2af49-153">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="2af49-153">Default setting (if not configured)</span></span> |
|---|---|---|---|
| <span data-ttu-id="2af49-154">修復</span><span class="sxs-lookup"><span data-stu-id="2af49-154">Remediation</span></span> | <span data-ttu-id="2af49-155">指定一周中的哪幾天執行排程完整掃描以完成修復</span><span class="sxs-lookup"><span data-stu-id="2af49-155">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="2af49-156">指定 [天] (或 [永不) ] 執行掃描。</span><span class="sxs-lookup"><span data-stu-id="2af49-156">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="2af49-157">從來不需要</span><span class="sxs-lookup"><span data-stu-id="2af49-157">Never</span></span> |
| <span data-ttu-id="2af49-158">修復</span><span class="sxs-lookup"><span data-stu-id="2af49-158">Remediation</span></span> | <span data-ttu-id="2af49-159">指定一天中執行計畫完整掃描以完成修復的時間</span><span class="sxs-lookup"><span data-stu-id="2af49-159">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="2af49-160">指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) </span><span class="sxs-lookup"><span data-stu-id="2af49-160">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="2af49-161">淩晨2點</span><span class="sxs-lookup"><span data-stu-id="2af49-161">2 a.m.</span></span> |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a><span data-ttu-id="2af49-162">排程每日掃描的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="2af49-162">Group Policy settings for scheduling daily scans</span></span>

| <span data-ttu-id="2af49-163">位置</span><span class="sxs-lookup"><span data-stu-id="2af49-163">Location</span></span> | <span data-ttu-id="2af49-164">設定</span><span class="sxs-lookup"><span data-stu-id="2af49-164">Setting</span></span> | <span data-ttu-id="2af49-165">描述</span><span class="sxs-lookup"><span data-stu-id="2af49-165">Description</span></span> | <span data-ttu-id="2af49-166">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="2af49-166">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="2af49-167">掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-167">Scan</span></span> | <span data-ttu-id="2af49-168">指定每天執行快速掃描的間隔</span><span class="sxs-lookup"><span data-stu-id="2af49-168">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="2af49-169">指定下一個快速掃描之前所應經過的小時數。</span><span class="sxs-lookup"><span data-stu-id="2af49-169">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="2af49-170">例如，若要每兩個小時執行一次，請輸入 **2** 一天一次，輸入 **24**。</span><span class="sxs-lookup"><span data-stu-id="2af49-170">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="2af49-171">輸入 **0** ，永遠不執行每日快速掃描。</span><span class="sxs-lookup"><span data-stu-id="2af49-171">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="2af49-172">從來不需要</span><span class="sxs-lookup"><span data-stu-id="2af49-172">Never</span></span> |
| <span data-ttu-id="2af49-173">掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-173">Scan</span></span> | <span data-ttu-id="2af49-174">指定每日快速掃描的時間</span><span class="sxs-lookup"><span data-stu-id="2af49-174">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="2af49-175">指定午夜後的分鐘數 (例如，輸入 **60** a.m. ) </span><span class="sxs-lookup"><span data-stu-id="2af49-175">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="2af49-176">淩晨2點</span><span class="sxs-lookup"><span data-stu-id="2af49-176">2 a.m.</span></span> |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a><span data-ttu-id="2af49-177">保護更新後進行排程掃描的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="2af49-177">Group Policy settings for scheduling scans after protection updates</span></span>

| <span data-ttu-id="2af49-178">位置</span><span class="sxs-lookup"><span data-stu-id="2af49-178">Location</span></span> | <span data-ttu-id="2af49-179">設定</span><span class="sxs-lookup"><span data-stu-id="2af49-179">Setting</span></span> | <span data-ttu-id="2af49-180">描述</span><span class="sxs-lookup"><span data-stu-id="2af49-180">Description</span></span> | <span data-ttu-id="2af49-181">預設設定 (（如果未設定）) </span><span class="sxs-lookup"><span data-stu-id="2af49-181">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
| <span data-ttu-id="2af49-182">特徵碼更新</span><span class="sxs-lookup"><span data-stu-id="2af49-182">Signature updates</span></span> | <span data-ttu-id="2af49-183">在安全性智慧更新後開啟掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-183">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="2af49-184">下載新的保護更新後會立即進行掃描</span><span class="sxs-lookup"><span data-stu-id="2af49-184">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="2af49-185">啟用</span><span class="sxs-lookup"><span data-stu-id="2af49-185">Enabled</span></span> |

