---
title: 將 Microsoft Defender AV 保護更新套用至日期結束端點
description: 定義何時及如何針對尚未更新的端點套用更新。
keywords: 更新、保護、過期、過期、舊、追趕
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4199f55488ef0dc5989af88e8be83a3d51190d1f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275057"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="15303-104">管理 Microsoft Defender 防毒軟體更新和掃描已過時的端點</span><span class="sxs-lookup"><span data-stu-id="15303-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="15303-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="15303-105">**Applies to:**</span></span>

- [<span data-ttu-id="15303-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="15303-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="15303-107">Microsoft Defender 防毒軟體可讓您定義端點可以避免更新的時間長短，或在需要更新及掃描自身之前所能錯過的掃描數目。</span><span class="sxs-lookup"><span data-stu-id="15303-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="15303-108">這在裝置通常不會連接到公司或外部網路或每日未使用的裝置的環境中特別有用。</span><span class="sxs-lookup"><span data-stu-id="15303-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="15303-109">例如，使用特定電腦的員工會在中斷三天，而不會在該時間登入其電腦。</span><span class="sxs-lookup"><span data-stu-id="15303-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="15303-110">當使用者回到工作並登入其電腦時，Microsoft Defender 防毒軟體會立即檢查並下載最新的保護更新，並執行掃描。</span><span class="sxs-lookup"><span data-stu-id="15303-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="15303-111">針對尚未更新的端點，設定追趕防護更新</span><span class="sxs-lookup"><span data-stu-id="15303-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="15303-112">如果 Microsoft Defender 防毒軟體在指定的期間內沒有下載保護更新，您可以將其設定為在下次登入時自動檢查和下載最新的更新。</span><span class="sxs-lookup"><span data-stu-id="15303-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="15303-113">如果您已 [在啟動時以全域方式停用自動更新下載](manage-event-based-updates-microsoft-defender-antivirus.md)，這會很有用。</span><span class="sxs-lookup"><span data-stu-id="15303-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="15303-114">使用 Configuration Manager 來設定追趕保護更新</span><span class="sxs-lookup"><span data-stu-id="15303-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="15303-115">在您的 Microsoft 端點管理員主控台上，開啟您想要變更的反惡意軟體原則 (按一下左側功能窗格中的 **[\*\*\*\*資產和符合性**]，然後展開樹狀目錄  >  **Endpoint Protection**  >  **反惡意軟體原則**) </span><span class="sxs-lookup"><span data-stu-id="15303-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="15303-116">移至 [ **安全性情報更新** ] 區段，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="15303-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="15303-117">**如果用戶端電腦離線時，有兩個以上的連續排程更新** 為 **[是]**，則設定強制安全性智慧更新。</span><span class="sxs-lookup"><span data-stu-id="15303-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="15303-118">**如果是使用 Configuration manager 做為安全性智慧更新的來源**，請指定設定管理員所傳遞的保護更新應視為過期的時間。</span><span class="sxs-lookup"><span data-stu-id="15303-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="15303-119">這會根據定義的 [回退來源順序](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)，使下一個更新位置成為使用。</span><span class="sxs-lookup"><span data-stu-id="15303-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="15303-120">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="15303-120">Click **OK**.</span></span>

4.  <span data-ttu-id="15303-121">[照常部署更新的原則](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="15303-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="15303-122">使用群組原則來啟用及設定追趕更新功能</span><span class="sxs-lookup"><span data-stu-id="15303-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="15303-123">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="15303-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="15303-124">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="15303-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="15303-125">按一下 [ **原則** 然後是系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="15303-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="15303-126">展開樹狀目錄， **Windows 元件 > Microsoft Defender 防毒軟體 > 簽名更新**。</span><span class="sxs-lookup"><span data-stu-id="15303-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="15303-127">按兩下 [ **定義需要彌補安全性的智慧更新之前的天數** ] 設定，並將此選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="15303-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="15303-128">輸入您想要 Microsoft Defender AV 檢查的天數，並下載最新的保護更新。</span><span class="sxs-lookup"><span data-stu-id="15303-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="15303-129">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="15303-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="15303-130">使用 PowerShell Cmdlet 來設定追趕防護更新</span><span class="sxs-lookup"><span data-stu-id="15303-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="15303-131">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="15303-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="15303-132">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="15303-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="15303-133">使用 Windows 管理指令 (WMI) 設定追趕防護更新</span><span class="sxs-lookup"><span data-stu-id="15303-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="15303-134">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="15303-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="15303-135">如需詳細資訊及允許的參數，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="15303-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="15303-136">Windows DefenderWMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="15303-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="15303-137">設定將保護報告為過期前的天數</span><span class="sxs-lookup"><span data-stu-id="15303-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="15303-138">您也可以指定會將 Microsoft Defender 防毒軟體保護視為舊或過期的天數。</span><span class="sxs-lookup"><span data-stu-id="15303-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="15303-139">在指定天數後，用戶端會將其本身報告為過期，並對電腦使用者顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="15303-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="15303-140">這可能也會導致 Microsoft Defender 防毒軟體嘗試根據定義的[回退來源順序](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)) 從其他來源 (下載更新，例如，將 WSUS 或 Microsoft update 設定為第一個來源後，使用 MMPC 做為次要來源。</span><span class="sxs-lookup"><span data-stu-id="15303-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="15303-141">使用群組原則指定保護視為過期前的天數</span><span class="sxs-lookup"><span data-stu-id="15303-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="15303-142">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="15303-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="15303-143">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="15303-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="15303-144">按一下 [ **原則** 然後是系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="15303-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="15303-145">展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 >** 簽章更新，並設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="15303-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="15303-146">按兩下 **[定義間諜軟體定義視為過時的天數** ]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="15303-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="15303-147">輸入您想要 Microsoft Defender AV 將間諜軟體安全性情報視為過期的天數。</span><span class="sxs-lookup"><span data-stu-id="15303-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="15303-148">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="15303-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="15303-149">按兩下 **[定義病毒定義視為過時的天數** ]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="15303-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="15303-150">輸入您想要讓 Microsoft Defender AV 將病毒安全性情報視為過期的天數。</span><span class="sxs-lookup"><span data-stu-id="15303-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="15303-151">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="15303-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="15303-152">針對尚未掃描的端點，設定追趕掃描</span><span class="sxs-lookup"><span data-stu-id="15303-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="15303-153">您可以在 Microsoft Defender 防毒軟體會強制進行掃描之前，設定可錯過的連續排程掃描數目。</span><span class="sxs-lookup"><span data-stu-id="15303-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="15303-154">啟用此功能的程式為：</span><span class="sxs-lookup"><span data-stu-id="15303-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="15303-155">設定至少一個排程掃描 (請參閱 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 主題) 。</span><span class="sxs-lookup"><span data-stu-id="15303-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="15303-156">啟用 [追趕掃描] 功能。</span><span class="sxs-lookup"><span data-stu-id="15303-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="15303-157">定義在進行追趕掃描之前可略過的掃描數目。</span><span class="sxs-lookup"><span data-stu-id="15303-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="15303-158">這項功能可同時啟用完整和快速掃描。</span><span class="sxs-lookup"><span data-stu-id="15303-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="15303-159">使用群組原則來啟用及設定追趕掃描功能</span><span class="sxs-lookup"><span data-stu-id="15303-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="15303-160">確定您已設定至少一個排程掃描。</span><span class="sxs-lookup"><span data-stu-id="15303-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="15303-161">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="15303-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="15303-162">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="15303-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="15303-163">按一下 [ **原則** 然後是系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="15303-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="15303-164">展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 > 掃描** 及設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="15303-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="15303-165">如果您已設定排程快速掃描，請按兩下 [ **開啟追趕快速掃描** ] 設定，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="15303-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="15303-166">如果您已設定排程完整掃描，請按兩下 [ **開啟追趕完整掃描** ] 設定，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="15303-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="15303-167">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="15303-167">Click **OK**.</span></span>
    3. <span data-ttu-id="15303-168">按兩下 [ **定義強制進行追趕掃描的天數之後的天數** ] 設定，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="15303-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="15303-169">輸入當使用者下一次登入電腦時，系統會自動執行掃描之前，可錯過的掃描數目。</span><span class="sxs-lookup"><span data-stu-id="15303-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="15303-170">所執行的掃描類型是由 **指定用於排程掃描的掃描類型** 所決定 (請參閱 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 主題) 。</span><span class="sxs-lookup"><span data-stu-id="15303-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="15303-171">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="15303-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="15303-172">群組原則設定標題是指天數。</span><span class="sxs-lookup"><span data-stu-id="15303-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="15303-173">不過，此設定會套用至執行追趕掃描之前 (天數) 中的掃描數目。</span><span class="sxs-lookup"><span data-stu-id="15303-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="15303-174">使用 PowerShell Cmdlet 來設定追趕掃描</span><span class="sxs-lookup"><span data-stu-id="15303-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="15303-175">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="15303-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="15303-176">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet to manage Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="15303-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="15303-177">使用 Windows 管理指令 (WMI) 設定追趕掃描</span><span class="sxs-lookup"><span data-stu-id="15303-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="15303-178">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="15303-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="15303-179">如需詳細資訊及允許的參數，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="15303-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="15303-180">Windows DefenderWMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="15303-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="15303-181">使用 Configuration Manager 來設定追趕掃描</span><span class="sxs-lookup"><span data-stu-id="15303-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="15303-182">在您的 Microsoft 端點管理員主控台上，開啟您想要變更的反惡意軟體原則 (按一下左側功能窗格中的 **[\*\*\*\*資產和符合性**]，然後展開樹狀目錄  >  **Endpoint Protection**  >  **反惡意軟體原則**) </span><span class="sxs-lookup"><span data-stu-id="15303-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="15303-183">移至 [ **排程掃描** ] 區段，並在 **用戶端電腦離線時，強制掃描選取的掃描類型** ... 為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="15303-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="15303-184">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="15303-184">Click **OK**.</span></span>

4.  <span data-ttu-id="15303-185">[照常部署更新的原則](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="15303-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="15303-186">相關文章</span><span class="sxs-lookup"><span data-stu-id="15303-186">Related articles</span></span>

- [<span data-ttu-id="15303-187">部署 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="15303-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="15303-188">管理 Microsoft Defender 防毒軟體更新及套用基準</span><span class="sxs-lookup"><span data-stu-id="15303-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="15303-189">管理應下載及套用防護更新的時間</span><span class="sxs-lookup"><span data-stu-id="15303-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="15303-190">管理事件型強制更新</span><span class="sxs-lookup"><span data-stu-id="15303-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="15303-191">管理行動裝置和虛擬機器 (VM) 的更新</span><span class="sxs-lookup"><span data-stu-id="15303-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="15303-192">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="15303-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)