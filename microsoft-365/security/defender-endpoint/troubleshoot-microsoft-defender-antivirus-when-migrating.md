---
title: 從協力廠商解決方案進行遷移時疑難排解 Microsoft Defender 防毒程式
description: 將遷移至 Microsoft Defender 防毒程式時的常見錯誤疑難排解
keywords: 事件、錯誤代碼、記錄、疑難排解、microsoft defender 防毒程式、windows defender 防毒程式、遷移
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2ca486b86c24e18ae08753b5e88f2eb42986dddf
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690191"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a><span data-ttu-id="0634a-104">從協力廠商解決方案進行遷移時疑難排解 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="0634a-104">Troubleshoot Microsoft Defender Antivirus while migrating from a third-party solution</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0634a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0634a-105">**Applies to:**</span></span>

- [<span data-ttu-id="0634a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0634a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="0634a-107">如果您在從協力廠商安全性解決方案遷移至 Microsoft Defender 防病毒時遇到問題，您可以在這裡找到 [說明]。</span><span class="sxs-lookup"><span data-stu-id="0634a-107">You can find help here if you encounter issues while migrating from a third-party security solution to Microsoft Defender Antivirus.</span></span>

## <a name="review-event-logs"></a><span data-ttu-id="0634a-108">審閱事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="0634a-108">Review event logs</span></span>

<span data-ttu-id="0634a-109">在工作列中選取 **搜尋** 圖示，然後搜尋 [ *事件檢視器*]，以開啟 [事件檢視器] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="0634a-109">Open the Event viewer app by selecting the **Search** icon in the taskbar, and searching for *event viewer*.</span></span>

<span data-ttu-id="0634a-110">您可以在 [**應用程式及服務記錄**]  >  **microsoft**  >  **windows**  >  **windows Defender** 底下找到 microsoft Defender 防病毒的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0634a-110">Information about Microsoft Defender Antivirus can be found under  **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender**.</span></span> 

<span data-ttu-id="0634a-111">從那裡，選取 [在 **運作** 下 **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="0634a-111">From there, select **Open** underneath **Operational**.</span></span>

<span data-ttu-id="0634a-112">從 [詳細資料] 窗格選取事件，將會在 [一般] 和 **[** **詳細資料** ] 索引標籤底下的下部窗格中顯示事件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0634a-112">Selecting an event from the details pane will show you more information about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

## <a name="microsoft-defender-antivirus-wont-start"></a><span data-ttu-id="0634a-113">無法啟動 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="0634a-113">Microsoft Defender Antivirus won't start</span></span>

<span data-ttu-id="0634a-114">此問題的資訊清單可能是數個不同的事件 IDs，所有這些事件都具有相同的基本原因。</span><span class="sxs-lookup"><span data-stu-id="0634a-114">This issue can manifest in the form of  several different event IDs, all of which have the same underlying cause.</span></span>

### <a name="associated-event-ids"></a><span data-ttu-id="0634a-115">關聯的事件 IDs</span><span class="sxs-lookup"><span data-stu-id="0634a-115">Associated event IDs</span></span>

 <span data-ttu-id="0634a-116">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="0634a-116">Event ID</span></span> | <span data-ttu-id="0634a-117">記錄檔名稱</span><span class="sxs-lookup"><span data-stu-id="0634a-117">Log name</span></span> | <span data-ttu-id="0634a-118">描述</span><span class="sxs-lookup"><span data-stu-id="0634a-118">Description</span></span> | <span data-ttu-id="0634a-119">來源</span><span class="sxs-lookup"><span data-stu-id="0634a-119">Source</span></span>
-|-|-|-
<span data-ttu-id="0634a-120">15 </span><span class="sxs-lookup"><span data-stu-id="0634a-120">15</span></span> | <span data-ttu-id="0634a-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="0634a-121">Application</span></span> | <span data-ttu-id="0634a-122">已順利更新 Windows Defender 狀態，以 SECURITY_PRODUCT_STATE_OFF。</span><span class="sxs-lookup"><span data-stu-id="0634a-122">Updated Windows Defender status successfully to SECURITY_PRODUCT_STATE_OFF.</span></span> | <span data-ttu-id="0634a-123">安全中心</span><span class="sxs-lookup"><span data-stu-id="0634a-123">Security Center</span></span>
<span data-ttu-id="0634a-124">5007</span><span class="sxs-lookup"><span data-stu-id="0634a-124">5007</span></span> | <span data-ttu-id="0634a-125">Microsoft-windows-Windows Defender/運作性</span><span class="sxs-lookup"><span data-stu-id="0634a-125">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="0634a-126">Windows Defender 防病毒設定已經變更。</span><span class="sxs-lookup"><span data-stu-id="0634a-126">Windows Defender Antivirus Configuration has changed.</span></span>  <span data-ttu-id="0634a-127">如果這是未預期的事件，您應該檢查設定，因為這可能是惡意程式碼的結果。</span><span class="sxs-lookup"><span data-stu-id="0634a-127">If this is an unexpected event you should review the settings as this may be the result of malware.</span></span><br /><br /><span data-ttu-id="0634a-128">**舊值：** Default\IsServiceRunning = 0x0</span><span class="sxs-lookup"><span data-stu-id="0634a-128">**Old value:** Default\IsServiceRunning = 0x0</span></span><br /><span data-ttu-id="0634a-129">**新值：** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span><span class="sxs-lookup"><span data-stu-id="0634a-129">**New value:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span></span> | <span data-ttu-id="0634a-130">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="0634a-130">Windows Defender</span></span>
<span data-ttu-id="0634a-131">5010</span><span class="sxs-lookup"><span data-stu-id="0634a-131">5010</span></span> | <span data-ttu-id="0634a-132">Microsoft-windows-Windows Defender/運作性</span><span class="sxs-lookup"><span data-stu-id="0634a-132">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="0634a-133">停用對間諜軟體和其他可能有害軟體的 Windows Defender 防病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="0634a-133">Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled.</span></span> | <span data-ttu-id="0634a-134">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="0634a-134">Windows Defender</span></span>

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a><span data-ttu-id="0634a-135">如何判斷 Microsoft Defender 防病毒是否因安裝協力廠商防病毒而無法啟動</span><span class="sxs-lookup"><span data-stu-id="0634a-135">How to tell if Microsoft Defender Antivirus won't start because a third-party antivirus is installed</span></span>

<span data-ttu-id="0634a-136">在 Windows 10 裝置上，如果您不是使用 Microsoft Defender for Endpoint，且已安裝協力廠商的防毒軟體，則會自動關閉 Microsoft Defender 防病毒功能。</span><span class="sxs-lookup"><span data-stu-id="0634a-136">On a Windows 10 device, if you are not using Microsoft Defender for Endpoint, and you have a third-party antivirus installed, then Microsoft Defender Antivirus will be automatically turned off.</span></span> <span data-ttu-id="0634a-137">如果您使用的是 Microsoft Defender for Endpoint，且已安裝協力廠商防毒軟體，則 Microsoft Defender 防毒程式會以被動式模式啟動，但功能會變少。</span><span class="sxs-lookup"><span data-stu-id="0634a-137">If you are using Microsoft Defender for Endpoint with a third-party antivirus installed, Microsoft Defender Antivirus will start in passive mode, with reduced functionality.</span></span>

> [!TIP]
> <span data-ttu-id="0634a-138">剛才所述的案例只適用于 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="0634a-138">The scenario just described applies only to Windows 10.</span></span> <span data-ttu-id="0634a-139">其他版本的 Windows 對 Microsoft Defender 防毒軟體所執行的 [回應不同](microsoft-defender-antivirus-compatibility.md) 于協力廠商的安全性軟體。</span><span class="sxs-lookup"><span data-stu-id="0634a-139">Other versions of Windows have [different responses](microsoft-defender-antivirus-compatibility.md) to Microsoft Defender Antivirus being run alongside third-party security software.</span></span>

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a><span data-ttu-id="0634a-140">使用服務應用程式檢查是否已關閉 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="0634a-140">Use Services app to check if Microsoft Defender Antivirus is turned off</span></span>

<span data-ttu-id="0634a-141">若要開啟服務應用程式，請從工作列選取 **搜尋** 圖示，然後搜尋 *服務*。</span><span class="sxs-lookup"><span data-stu-id="0634a-141">To open the Services app, select the **Search** icon from the taskbar and search for *services*.</span></span> <span data-ttu-id="0634a-142">您也可以輸入 *services.msc*，從命令列開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="0634a-142">You can also open the app from the command-line by typing *services.msc*.</span></span>

<span data-ttu-id="0634a-143">**Windows defender** 可運作的服務應用程式中會列出 Microsoft Defender 防毒軟體的相關資訊  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0634a-143">Information about Microsoft Defender Antivirus will be listed within the Services app under **Windows Defender** > **Operational**.</span></span> <span data-ttu-id="0634a-144">防病毒服務名稱為 *Windows Defender 防病毒服務*。</span><span class="sxs-lookup"><span data-stu-id="0634a-144">The antivirus service name is *Windows Defender Antivirus Service*.</span></span>

<span data-ttu-id="0634a-145">檢查應用程式時，您可能會看到 *Windows Defender 防病毒服務* 已設為手動，但是當您嘗試手動啟動此服務時，會收到一則警告，指出 *本機電腦上的 Windows Defender 防病毒服務服務已啟動，然後停止。有些服務不會因為其他服務或程式而自動停止使用。*</span><span class="sxs-lookup"><span data-stu-id="0634a-145">While checking the app, you may see that *Windows Defender Antivirus Service* is set to manual — but when you try to start this service manually, you get a warning stating, *The Windows Defender Antivirus Service service on Local Computer started and then stopped. Some services stop automatically if they are not in use by other services or programs.*</span></span>

<span data-ttu-id="0634a-146">這表示 Microsoft Defender 防病毒已自動關閉，以保留與協力廠商防病毒的相容性。</span><span class="sxs-lookup"><span data-stu-id="0634a-146">This indicates that Microsoft Defender Antivirus has been automatically turned off to preserve compatibility with a third-party antivirus.</span></span>

#### <a name="generate-a-detailed-report"></a><span data-ttu-id="0634a-147">產生詳細報告</span><span class="sxs-lookup"><span data-stu-id="0634a-147">Generate a detailed report</span></span>

<span data-ttu-id="0634a-148">您可以在 [以系統 **管理員模式執行** ] 中開啟命令提示字元，然後輸入下列命令，以產生目前作用中群組原則的詳細報告：</span><span class="sxs-lookup"><span data-stu-id="0634a-148">You can generate a detailed report about currently active group policies by opening a command prompt in **Run as admin** mode, then entering the following command:</span></span>

```powershell
GPresult.exe /h gpresult.html
```

<span data-ttu-id="0634a-149">這會產生位於 at */gpresult.html* 的報告。</span><span class="sxs-lookup"><span data-stu-id="0634a-149">This will generate a report located at *./gpresult.html*.</span></span> <span data-ttu-id="0634a-150">開啟此檔案，視 Microsoft Defender 防毒軟體關閉的方式而定，您可能會看到下列結果。</span><span class="sxs-lookup"><span data-stu-id="0634a-150">Open this file and you might see the following results, depending on how Microsoft Defender Antivirus was turned off.</span></span>

##### <a name="group-policy-results"></a><span data-ttu-id="0634a-151">群組原則結果</span><span class="sxs-lookup"><span data-stu-id="0634a-151">Group policy results</span></span>

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a><span data-ttu-id="0634a-152">若安全設定是透過「群組原則」來實施，請 (網域或本地層級的 GPO) ，或是 System center configuration manager (SCCM) </span><span class="sxs-lookup"><span data-stu-id="0634a-152">If security settings are implemented via group policy (GPO) at the domain or local level, or though System center configuration manager (SCCM)</span></span>

<span data-ttu-id="0634a-153">在 GPResults 報告中的標題、 *Windows 元件/Windows Defender 防病毒* 程式下，您可能會看到類似下列的專案，表示已關閉 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="0634a-153">Within the GPResults report, under the heading, *Windows Components/Windows Defender Antivirus*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="0634a-154">原則</span><span class="sxs-lookup"><span data-stu-id="0634a-154">Policy</span></span> | <span data-ttu-id="0634a-155">設定</span><span class="sxs-lookup"><span data-stu-id="0634a-155">Setting</span></span> | <span data-ttu-id="0634a-156">入選 GPO</span><span class="sxs-lookup"><span data-stu-id="0634a-156">Winning GPO</span></span>
-|-|-
<span data-ttu-id="0634a-157">關閉 Windows Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="0634a-157">Turn off Windows Defender Antivirus</span></span> | <span data-ttu-id="0634a-158">Enabled</span><span class="sxs-lookup"><span data-stu-id="0634a-158">Enabled</span></span> | <span data-ttu-id="0634a-159">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="0634a-159">Win10-Workstations</span></span>

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a><span data-ttu-id="0634a-160">如果透過群組原則首選項來執行安全性設定 (GPP) </span><span class="sxs-lookup"><span data-stu-id="0634a-160">If security settings are implemented via Group policy preference (GPP)</span></span>

<span data-ttu-id="0634a-161">在標題、登錄 *專案 (機碼路徑： HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender、值名稱： DisableAntiSpyware)* 中，您可能會看到類似下列的專案，表示已關閉 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="0634a-161">Under the heading, *Registry item (Key path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Value name: DisableAntiSpyware)*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="0634a-162">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="0634a-162">DisableAntiSpyware</span></span> | -
-|-
<span data-ttu-id="0634a-163">入選 GPO</span><span class="sxs-lookup"><span data-stu-id="0634a-163">Winning GPO</span></span> | <span data-ttu-id="0634a-164">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="0634a-164">Win10-Workstations</span></span>
<span data-ttu-id="0634a-165">結果：成功</span><span class="sxs-lookup"><span data-stu-id="0634a-165">Result: Success</span></span> | 
<span data-ttu-id="0634a-166">**一般**</span><span class="sxs-lookup"><span data-stu-id="0634a-166">**General**</span></span> | 
<span data-ttu-id="0634a-167">動作</span><span class="sxs-lookup"><span data-stu-id="0634a-167">Action</span></span> | <span data-ttu-id="0634a-168">Update</span><span class="sxs-lookup"><span data-stu-id="0634a-168">Update</span></span>
<span data-ttu-id="0634a-169">**屬性**</span><span class="sxs-lookup"><span data-stu-id="0634a-169">**Properties**</span></span> | 
<span data-ttu-id="0634a-170">蜂巢</span><span class="sxs-lookup"><span data-stu-id="0634a-170">Hive</span></span> | <span data-ttu-id="0634a-171">HKEY_LOCAL_MACHINE</span><span class="sxs-lookup"><span data-stu-id="0634a-171">HKEY_LOCAL_MACHINE</span></span>
<span data-ttu-id="0634a-172">機碼路徑</span><span class="sxs-lookup"><span data-stu-id="0634a-172">Key path</span></span> | <span data-ttu-id="0634a-173">SOFTWARE\Policies\Microsoft\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="0634a-173">SOFTWARE\Policies\Microsoft\Windows Defender</span></span>
<span data-ttu-id="0634a-174">數值名稱</span><span class="sxs-lookup"><span data-stu-id="0634a-174">Value name</span></span> | <span data-ttu-id="0634a-175">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="0634a-175">DisableAntiSpyware</span></span>
<span data-ttu-id="0634a-176">值類型</span><span class="sxs-lookup"><span data-stu-id="0634a-176">Value type</span></span> | <span data-ttu-id="0634a-177">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0634a-177">REG_DWORD</span></span>
<span data-ttu-id="0634a-178">數值資料</span><span class="sxs-lookup"><span data-stu-id="0634a-178">Value data</span></span> | <span data-ttu-id="0634a-179">0x1 (1) </span><span class="sxs-lookup"><span data-stu-id="0634a-179">0x1 (1)</span></span>

###### <a name="if-security-settings-are-implemented-via-registry-key"></a><span data-ttu-id="0634a-180">如果透過登錄機碼來執行安全性設定</span><span class="sxs-lookup"><span data-stu-id="0634a-180">If security settings are implemented via registry key</span></span>

<span data-ttu-id="0634a-181">此報告可能會包含下列文字，表示 Microsoft Defender 防病毒已關閉：</span><span class="sxs-lookup"><span data-stu-id="0634a-181">The report may contain the following text, indicating that Microsoft Defender Antivirus is turned off:</span></span>
 
> <span data-ttu-id="0634a-182">Registry (regedit.exe) </span><span class="sxs-lookup"><span data-stu-id="0634a-182">Registry (regedit.exe)</span></span>
>
> <span data-ttu-id="0634a-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (十六進位) </span><span class="sxs-lookup"><span data-stu-id="0634a-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span></span>

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a><span data-ttu-id="0634a-184">如果在 Windows 或 Windows Server 映射中設定安全性設定</span><span class="sxs-lookup"><span data-stu-id="0634a-184">If security settings are set in Windows or your Windows Server image</span></span>

<span data-ttu-id="0634a-185">您的 imagining 系統管理員可能已透過 *GPEdit.exe*、 *LGPO.exe* 或在其任務順序中修改登錄，將安全性原則 **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**、從本機設定。</span><span class="sxs-lookup"><span data-stu-id="0634a-185">Your imagining admin might have set the security policy, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, locally via *GPEdit.exe*, *LGPO.exe*, or by modifying the registry in their task sequence.</span></span> <span data-ttu-id="0634a-186">您可以為 Microsoft Defender 防病毒 [設定信任的影像識別碼](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) 。</span><span class="sxs-lookup"><span data-stu-id="0634a-186">You can [configure a Trusted Image Identifier](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) for Microsoft Defender Antivirus.</span></span>

### <a name="turn-microsoft-defender-antivirus-back-on"></a><span data-ttu-id="0634a-187">重新開啟 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="0634a-187">Turn Microsoft Defender Antivirus back on</span></span>

<span data-ttu-id="0634a-188">如果目前沒有任何其他使用中的反病毒，Microsoft Defender 防病毒將會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="0634a-188">Microsoft Defender Antivirus will automatically turn on if no other antivirus is currently active.</span></span> <span data-ttu-id="0634a-189">您需要完全關閉協力廠商防病毒，以確保 Microsoft Defender 防病毒可以使用完整功能執行。</span><span class="sxs-lookup"><span data-stu-id="0634a-189">You'll need to turn the third-party antivirus completely off to ensure Microsoft Defender Antivirus can run with full functionality.</span></span>

> [!WARNING]
> <span data-ttu-id="0634a-190">解決方案建議您在 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services 中為 *wdboot*、 *wdfilter*、 *wdnisdrv*、 *wdnissvc* 和 *windefend* 編輯 *Windows Defender* 開始值時，可能會強制您重新影像您的系統。</span><span class="sxs-lookup"><span data-stu-id="0634a-190">Solutions suggesting that you edit the *Windows Defender* start values for *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc*, and *windefend* in  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services are unsupported, and may force you to re-image your system.</span></span>

<span data-ttu-id="0634a-191">當您開始使用 Microsoft Defender for Endpoint 和協力廠商的防毒軟體搭配 Microsoft Defender 防病毒時，就可以使用被動模式。</span><span class="sxs-lookup"><span data-stu-id="0634a-191">Passive mode is available if you start using Microsoft Defender for Endpoint and a third-party antivirus together with Microsoft Defender Antivirus.</span></span> <span data-ttu-id="0634a-192">被動式模式可讓 Microsoft Defender 掃描檔案並自行更新，但不會修正威脅。</span><span class="sxs-lookup"><span data-stu-id="0634a-192">Passive mode allows Microsoft Defender to scan files and update itself, but it will not remediate threats.</span></span> <span data-ttu-id="0634a-193">此外，透過 [即時保護](configure-real-time-protection-microsoft-defender-antivirus.md) 進行的行為監視無法在被動模式下使用，除非部署了 [端點資料遺失防護 (DLP) ](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) 。</span><span class="sxs-lookup"><span data-stu-id="0634a-193">In addition, behavior monitoring via [Real Time Protection](configure-real-time-protection-microsoft-defender-antivirus.md) is not available under passive mode, unless [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) is deployed.</span></span>

<span data-ttu-id="0634a-194">當 Microsoft Defender 防病毒已設定為自動關閉時，使用者就可以使用另一個功能（也稱為 [有限的定期掃描](limited-periodic-scanning-microsoft-defender-antivirus.md)）。</span><span class="sxs-lookup"><span data-stu-id="0634a-194">Another feature, known as [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md), is available to end-users when Microsoft Defender Antivirus is set to automatically turn off.</span></span> <span data-ttu-id="0634a-195">這項功能可讓 Microsoft Defender 防毒程式使用有限的偵測數目，定期掃描協力廠商防病毒的檔案。</span><span class="sxs-lookup"><span data-stu-id="0634a-195">This feature allows Microsoft Defender Antivirus to scan files periodically alongside a third-party antivirus, using a limited number of detections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0634a-196">在企業環境中不建議使用有限的定期掃描。</span><span class="sxs-lookup"><span data-stu-id="0634a-196">Limited periodic scanning is not recommended in enterprise environments.</span></span> <span data-ttu-id="0634a-197">在此模式中執行 Microsoft Defender 防毒程式時，可使用的偵測、管理與報告功能會隨著使用中模式而縮短。</span><span class="sxs-lookup"><span data-stu-id="0634a-197">The detection, management and reporting capabilities available when running Microsoft Defender Antivirus in this mode are reduced as compared to active mode.</span></span>

### <a name="see-also"></a><span data-ttu-id="0634a-198">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0634a-198">See also</span></span>

* [<span data-ttu-id="0634a-199">Microsoft Defender 防毒程式相容性</span><span class="sxs-lookup"><span data-stu-id="0634a-199">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
* [<span data-ttu-id="0634a-200">Windows 安全性應用程式中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="0634a-200">Microsoft Defender Antivirus in the Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)