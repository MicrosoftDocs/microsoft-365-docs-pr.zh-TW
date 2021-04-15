---
title: 排程 Microsoft Defender 防病毒防護更新
description: 排程應下載保護更新的日期、時間和間隔
keywords: 更新、安全性基準、排程更新
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 327974c4db4166301820cf148811aceda1700513
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765344"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="59273-104">管理應下載及套用防護更新的排程</span><span class="sxs-lookup"><span data-stu-id="59273-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="59273-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="59273-105">**Applies to:**</span></span>

- [<span data-ttu-id="59273-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="59273-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="59273-107">Microsoft Defender 防病毒可讓您決定何時應尋找並下載更新。</span><span class="sxs-lookup"><span data-stu-id="59273-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="59273-108">您可以依下列方式排程端點的更新：</span><span class="sxs-lookup"><span data-stu-id="59273-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="59273-109">指定每週的哪一天檢查保護更新</span><span class="sxs-lookup"><span data-stu-id="59273-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="59273-110">指定檢查保護更新的間隔</span><span class="sxs-lookup"><span data-stu-id="59273-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="59273-111">指定檢查保護更新的時間</span><span class="sxs-lookup"><span data-stu-id="59273-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="59273-112">您也可以隨機化每個端點檢查和下載保護更新的時間。</span><span class="sxs-lookup"><span data-stu-id="59273-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="59273-113">如需詳細資訊，請參閱 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 主題。</span><span class="sxs-lookup"><span data-stu-id="59273-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="59273-114">使用 Configuration Manager 來排程保護更新</span><span class="sxs-lookup"><span data-stu-id="59273-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="59273-115">在您的 Microsoft 端點管理員主控台上，開啟您要變更的反惡意程式碼原則 (按一下左側功能窗格中的 [**資產和符合性**]，然後展開樹狀目錄，以 **瞭解**  >  **Endpoint Protection**  >  **反惡意程式碼原則**) </span><span class="sxs-lookup"><span data-stu-id="59273-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="59273-116">移至 [ **安全性情報更新** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="59273-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="59273-117">若要在特定時間檢查及下載更新：</span><span class="sxs-lookup"><span data-stu-id="59273-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="59273-118">將 [ **檢查 Endpoint Protection 安全性情報更新] 設定為 [在特定時間間隔 ...** ] 設定為 **0**。</span><span class="sxs-lookup"><span data-stu-id="59273-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="59273-119">將 [ **每日檢查的 Endpoint Protection 安全性情報更新** ] 設定為 [每日 ...]。</span><span class="sxs-lookup"><span data-stu-id="59273-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="59273-120">個</span><span class="sxs-lookup"><span data-stu-id="59273-120">3</span></span>
4. <span data-ttu-id="59273-121">若要連續檢查和下載更新，請將 [ **檢查 Endpoint Protection 安全性情報更新于特定的時間間隔 ...** ] 設定為應該在更新之間進行的小時數。</span><span class="sxs-lookup"><span data-stu-id="59273-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="59273-122">[照常部署更新的原則](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="59273-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="59273-123">使用群組原則來排程保護更新</span><span class="sxs-lookup"><span data-stu-id="59273-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59273-124">根據預設，Microsoft Defender 防毒程式會在任何排程的掃描時間之前，先檢查是否有15分鐘的更新。</span><span class="sxs-lookup"><span data-stu-id="59273-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="59273-125">啟用這些設定將覆寫該預設值。</span><span class="sxs-lookup"><span data-stu-id="59273-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="59273-126">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="59273-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="59273-127">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="59273-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="59273-128">按一下 [ **原則** 然後是系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="59273-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="59273-129">將樹狀目錄展開為 **Windows 元件**  >  **Microsoft Defender 防病毒**  >  **簽名智慧更新** 並設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="59273-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="59273-130">按兩下 [ **指定要檢查安全性智慧更新的星期幾** ] 設定，並將此選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="59273-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="59273-131">輸入星期幾以檢查更新。</span><span class="sxs-lookup"><span data-stu-id="59273-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="59273-132">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="59273-132">Click **OK**.</span></span>
    2. <span data-ttu-id="59273-133">按兩下 [ **指定檢查安全性智慧更新的間隔** ] 設定，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="59273-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="59273-134">輸入更新之間的小時數。</span><span class="sxs-lookup"><span data-stu-id="59273-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="59273-135">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="59273-135">Click **OK**.</span></span>
    3. <span data-ttu-id="59273-136">按兩下 [ **指定檢查安全性智慧更新的時間** ] 設定，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="59273-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="59273-137">輸入應檢查更新的時間。</span><span class="sxs-lookup"><span data-stu-id="59273-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="59273-138">時間是以端點的當地時間為基礎。</span><span class="sxs-lookup"><span data-stu-id="59273-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="59273-139">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="59273-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="59273-140">使用 PowerShell Cmdlet 來排程保護更新</span><span class="sxs-lookup"><span data-stu-id="59273-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="59273-141">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="59273-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="59273-142">如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md)  程式和 [Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="59273-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="59273-143">使用 Windows Management 指令 (WMI) 來排程保護更新</span><span class="sxs-lookup"><span data-stu-id="59273-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="59273-144">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="59273-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="59273-145">如需詳細資訊及允許的參數，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="59273-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="59273-146">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="59273-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="59273-147">相關文章</span><span class="sxs-lookup"><span data-stu-id="59273-147">Related articles</span></span>

- [<span data-ttu-id="59273-148">部署 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="59273-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="59273-149">管理 Microsoft Defender 防病毒更新並套用基準</span><span class="sxs-lookup"><span data-stu-id="59273-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="59273-150">管理已過期端點的更新</span><span class="sxs-lookup"><span data-stu-id="59273-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="59273-151">管理以事件為基礎的強制更新</span><span class="sxs-lookup"><span data-stu-id="59273-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="59273-152">管理移動裝置和虛擬機器 (Vm 的更新) </span><span class="sxs-lookup"><span data-stu-id="59273-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="59273-153">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="59273-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)