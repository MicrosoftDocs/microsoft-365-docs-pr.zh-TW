---
title: 從協力廠商解決方案移轉時疑難排解 Microsoft Defender 防毒軟體
description: 在遷移至 Microsoft Defender 防毒軟體時疑難排解常見的錯誤
keywords: 事件、錯誤代碼、記錄、疑難排解、microsoft defender 防毒程式、windows defender 防毒程式、遷移
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3fcc79e767edb533a20402a2f92ba4abc7d8386a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764588"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a><span data-ttu-id="71ced-104">從協力廠商解決方案移轉時疑難排解 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="71ced-104">Troubleshoot Microsoft Defender Antivirus while migrating from a third-party solution</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="71ced-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="71ced-105">**Applies to:**</span></span>

- [<span data-ttu-id="71ced-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="71ced-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="71ced-107">如果您在從協力廠商安全性解決方案 Microsoft Defender 防毒軟體進行遷移時遇到問題，您可以在這裡找到 [說明]。</span><span class="sxs-lookup"><span data-stu-id="71ced-107">You can find help here if you encounter issues while migrating from a third-party security solution to Microsoft Defender Antivirus.</span></span>

## <a name="review-event-logs"></a><span data-ttu-id="71ced-108">審閱事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="71ced-108">Review event logs</span></span>

<span data-ttu-id="71ced-109">在工作列中選取 **搜尋** 圖示，然後搜尋 [ *事件檢視器*]，以開啟 [事件檢視器] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="71ced-109">Open the Event viewer app by selecting the **Search** icon in the taskbar, and searching for *event viewer*.</span></span>

<span data-ttu-id="71ced-110">您可以在 [**應用程式及服務記錄**] [  >  **Microsoft**  >  **Windows**  >  **Windows Defender**] 底下找到 Microsoft Defender 防毒軟體的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="71ced-110">Information about Microsoft Defender Antivirus can be found under  **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender**.</span></span> 

<span data-ttu-id="71ced-111">從那裡，選取 [在 **運作** 下 **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="71ced-111">From there, select **Open** underneath **Operational**.</span></span>

<span data-ttu-id="71ced-112">從 [詳細資料] 窗格選取事件，將會在 [一般] 和 **[** **詳細資料** ] 索引標籤底下的下部窗格中顯示事件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="71ced-112">Selecting an event from the details pane will show you more information about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

## <a name="microsoft-defender-antivirus-wont-start"></a><span data-ttu-id="71ced-113">Microsoft Defender 防毒軟體不會啟動</span><span class="sxs-lookup"><span data-stu-id="71ced-113">Microsoft Defender Antivirus won't start</span></span>

<span data-ttu-id="71ced-114">此問題的資訊清單可能是數個不同的事件 IDs，所有這些事件都具有相同的基本原因。</span><span class="sxs-lookup"><span data-stu-id="71ced-114">This issue can manifest in the form of  several different event IDs, all of which have the same underlying cause.</span></span>

### <a name="associated-event-ids"></a><span data-ttu-id="71ced-115">關聯的事件 IDs</span><span class="sxs-lookup"><span data-stu-id="71ced-115">Associated event IDs</span></span>

 <span data-ttu-id="71ced-116">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="71ced-116">Event ID</span></span> | <span data-ttu-id="71ced-117">記錄檔名稱</span><span class="sxs-lookup"><span data-stu-id="71ced-117">Log name</span></span> | <span data-ttu-id="71ced-118">描述</span><span class="sxs-lookup"><span data-stu-id="71ced-118">Description</span></span> | <span data-ttu-id="71ced-119">來源</span><span class="sxs-lookup"><span data-stu-id="71ced-119">Source</span></span>
-|-|-|-
<span data-ttu-id="71ced-120">8</span><span class="sxs-lookup"><span data-stu-id="71ced-120">15</span></span> | <span data-ttu-id="71ced-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="71ced-121">Application</span></span> | <span data-ttu-id="71ced-122">SECURITY_PRODUCT_STATE_OFF 成功更新 Windows Defender 狀態。</span><span class="sxs-lookup"><span data-stu-id="71ced-122">Updated Windows Defender status successfully to SECURITY_PRODUCT_STATE_OFF.</span></span> | <span data-ttu-id="71ced-123">安全中心</span><span class="sxs-lookup"><span data-stu-id="71ced-123">Security Center</span></span>
<span data-ttu-id="71ced-124">5007</span><span class="sxs-lookup"><span data-stu-id="71ced-124">5007</span></span> | <span data-ttu-id="71ced-125">Microsoft Windows Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="71ced-125">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="71ced-126">Windows Defender 防毒軟體設定已經變更。</span><span class="sxs-lookup"><span data-stu-id="71ced-126">Windows Defender Antivirus Configuration has changed.</span></span>  <span data-ttu-id="71ced-127">如果這是未預期的事件，您應該檢查設定，因為這可能是惡意程式碼的結果。</span><span class="sxs-lookup"><span data-stu-id="71ced-127">If this is an unexpected event you should review the settings as this may be the result of malware.</span></span><br /><br /><span data-ttu-id="71ced-128">**舊值：** Default\IsServiceRunning = 0x0</span><span class="sxs-lookup"><span data-stu-id="71ced-128">**Old value:** Default\IsServiceRunning = 0x0</span></span><br /><span data-ttu-id="71ced-129">**新值：** HKLM\SOFTWARE\Microsoft\ Windows Defender \IsServiceRunning = 0x1</span><span class="sxs-lookup"><span data-stu-id="71ced-129">**New value:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span></span> | <span data-ttu-id="71ced-130">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="71ced-130">Windows Defender</span></span>
<span data-ttu-id="71ced-131">5010</span><span class="sxs-lookup"><span data-stu-id="71ced-131">5010</span></span> | <span data-ttu-id="71ced-132">Microsoft Windows Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="71ced-132">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="71ced-133">已停用對間諜軟體和其他可能有害軟體的 Windows Defender 防毒軟體掃描。</span><span class="sxs-lookup"><span data-stu-id="71ced-133">Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled.</span></span> | <span data-ttu-id="71ced-134">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="71ced-134">Windows Defender</span></span>

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a><span data-ttu-id="71ced-135">如何判斷 Microsoft Defender 防毒軟體是否因安裝協力廠商防毒程式而無法啟動</span><span class="sxs-lookup"><span data-stu-id="71ced-135">How to tell if Microsoft Defender Antivirus won't start because a third-party antivirus is installed</span></span>

<span data-ttu-id="71ced-136">在 Windows 10 裝置上，如果您不是使用 Microsoft Defender for Endpoint，而您已安裝協力廠商的防毒軟體，則 Microsoft Defender 防毒軟體會自動關閉。</span><span class="sxs-lookup"><span data-stu-id="71ced-136">On a Windows 10 device, if you are not using Microsoft Defender for Endpoint, and you have a third-party antivirus installed, then Microsoft Defender Antivirus will be automatically turned off.</span></span> <span data-ttu-id="71ced-137">如果您使用的是 Microsoft Defender for Endpoint，且已安裝協力廠商防毒軟體，則 Microsoft Defender 防毒軟體會以被動式模式開始，但功能會變少。</span><span class="sxs-lookup"><span data-stu-id="71ced-137">If you are using Microsoft Defender for Endpoint with a third-party antivirus installed, Microsoft Defender Antivirus will start in passive mode, with reduced functionality.</span></span>

> [!TIP]
> <span data-ttu-id="71ced-138">剛才所述的案例只適用于 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="71ced-138">The scenario just described applies only to Windows 10.</span></span> <span data-ttu-id="71ced-139">其他版本的 Windows 對 Microsoft Defender 防毒軟體所執行的回應和協力廠商的安全性軟體的[回應有所不同](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="71ced-139">Other versions of Windows have [different responses](microsoft-defender-antivirus-compatibility.md) to Microsoft Defender Antivirus being run alongside third-party security software.</span></span>

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a><span data-ttu-id="71ced-140">使用服務應用程式檢查 Microsoft Defender 防毒軟體是否關閉</span><span class="sxs-lookup"><span data-stu-id="71ced-140">Use Services app to check if Microsoft Defender Antivirus is turned off</span></span>

<span data-ttu-id="71ced-141">若要開啟服務應用程式，請從工作列選取 **搜尋** 圖示，然後搜尋 *服務*。</span><span class="sxs-lookup"><span data-stu-id="71ced-141">To open the Services app, select the **Search** icon from the taskbar and search for *services*.</span></span> <span data-ttu-id="71ced-142">您也可以輸入 *services.msc*，從命令列開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="71ced-142">You can also open the app from the command-line by typing *services.msc*.</span></span>

<span data-ttu-id="71ced-143">Microsoft Defender 防毒軟體的相關資訊會列在服務應用程式中 **Windows Defender**  >  **運作** 中。</span><span class="sxs-lookup"><span data-stu-id="71ced-143">Information about Microsoft Defender Antivirus will be listed within the Services app under **Windows Defender** > **Operational**.</span></span> <span data-ttu-id="71ced-144">防病毒服務名稱是 *Windows Defender 防毒軟體服務*。</span><span class="sxs-lookup"><span data-stu-id="71ced-144">The antivirus service name is *Windows Defender Antivirus Service*.</span></span>

<span data-ttu-id="71ced-145">檢查應用程式時，您可能會看到 *Windows Defender 防毒軟體服務* 設定為手動，但是當您嘗試手動啟動此服務時，會收到一則警告，指出 *本機電腦上的 Windows Defender 防毒軟體 service 服務已啟動，且已停止。有些服務不會因為其他服務或程式而自動停止使用。*</span><span class="sxs-lookup"><span data-stu-id="71ced-145">While checking the app, you may see that *Windows Defender Antivirus Service* is set to manual — but when you try to start this service manually, you get a warning stating, *The Windows Defender Antivirus Service service on Local Computer started and then stopped. Some services stop automatically if they are not in use by other services or programs.*</span></span>

<span data-ttu-id="71ced-146">這表示 Microsoft Defender 防毒軟體已自動關閉，以保留與協力廠商防病毒的相容性。</span><span class="sxs-lookup"><span data-stu-id="71ced-146">This indicates that Microsoft Defender Antivirus has been automatically turned off to preserve compatibility with a third-party antivirus.</span></span>

#### <a name="generate-a-detailed-report"></a><span data-ttu-id="71ced-147">產生詳細報告</span><span class="sxs-lookup"><span data-stu-id="71ced-147">Generate a detailed report</span></span>

<span data-ttu-id="71ced-148">您可以在 [以系統 **管理員模式執行** ] 中開啟命令提示字元，然後輸入下列命令，以產生目前作用中群組原則的詳細報告：</span><span class="sxs-lookup"><span data-stu-id="71ced-148">You can generate a detailed report about currently active group policies by opening a command prompt in **Run as admin** mode, then entering the following command:</span></span>

```powershell
GPresult.exe /h gpresult.html
```

<span data-ttu-id="71ced-149">這會產生位於 at */gpresult.html* 的報告。</span><span class="sxs-lookup"><span data-stu-id="71ced-149">This will generate a report located at *./gpresult.html*.</span></span> <span data-ttu-id="71ced-150">開啟此檔案，視 Microsoft Defender 防毒軟體關閉的方式而定，您可能會看到下列結果。</span><span class="sxs-lookup"><span data-stu-id="71ced-150">Open this file and you might see the following results, depending on how Microsoft Defender Antivirus was turned off.</span></span>

##### <a name="group-policy-results"></a><span data-ttu-id="71ced-151">群組原則結果</span><span class="sxs-lookup"><span data-stu-id="71ced-151">Group policy results</span></span>

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a><span data-ttu-id="71ced-152">若安全設定是透過「群組原則」來實施，請 (網域或本地層級的 GPO) ，或是 System center configuration manager (SCCM) </span><span class="sxs-lookup"><span data-stu-id="71ced-152">If security settings are implemented via group policy (GPO) at the domain or local level, or though System center configuration manager (SCCM)</span></span>

<span data-ttu-id="71ced-153">在 GPResults 報告中，在標題底下 *Windows 元件/Windows Defender 防毒軟體*，您可能會看到類似下列的專案，表示 Microsoft Defender 防毒軟體已關閉。</span><span class="sxs-lookup"><span data-stu-id="71ced-153">Within the GPResults report, under the heading, *Windows Components/Windows Defender Antivirus*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="71ced-154">原則</span><span class="sxs-lookup"><span data-stu-id="71ced-154">Policy</span></span> | <span data-ttu-id="71ced-155">設定</span><span class="sxs-lookup"><span data-stu-id="71ced-155">Setting</span></span> | <span data-ttu-id="71ced-156">入選 GPO</span><span class="sxs-lookup"><span data-stu-id="71ced-156">Winning GPO</span></span>
-|-|-
<span data-ttu-id="71ced-157">關閉 Windows Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="71ced-157">Turn off Windows Defender Antivirus</span></span> | <span data-ttu-id="71ced-158">啟用</span><span class="sxs-lookup"><span data-stu-id="71ced-158">Enabled</span></span> | <span data-ttu-id="71ced-159">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="71ced-159">Win10-Workstations</span></span>

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a><span data-ttu-id="71ced-160">如果透過群組原則首選項來執行安全性設定 (GPP) </span><span class="sxs-lookup"><span data-stu-id="71ced-160">If security settings are implemented via Group policy preference (GPP)</span></span>

<span data-ttu-id="71ced-161">在標題、登錄 *專案 (機碼路徑： HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender、值名稱： DisableAntiSpyware)* 中，您可能會看到類似下列的專案，表示 Microsoft Defender 防毒軟體已關閉。</span><span class="sxs-lookup"><span data-stu-id="71ced-161">Under the heading, *Registry item (Key path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Value name: DisableAntiSpyware)*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="71ced-162">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="71ced-162">DisableAntiSpyware</span></span> | -
-|-
<span data-ttu-id="71ced-163">入選 GPO</span><span class="sxs-lookup"><span data-stu-id="71ced-163">Winning GPO</span></span> | <span data-ttu-id="71ced-164">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="71ced-164">Win10-Workstations</span></span>
<span data-ttu-id="71ced-165">結果：成功</span><span class="sxs-lookup"><span data-stu-id="71ced-165">Result: Success</span></span> | 
<span data-ttu-id="71ced-166">**一般**</span><span class="sxs-lookup"><span data-stu-id="71ced-166">**General**</span></span> | 
<span data-ttu-id="71ced-167">動作</span><span class="sxs-lookup"><span data-stu-id="71ced-167">Action</span></span> | <span data-ttu-id="71ced-168">Update</span><span class="sxs-lookup"><span data-stu-id="71ced-168">Update</span></span>
<span data-ttu-id="71ced-169">**屬性**</span><span class="sxs-lookup"><span data-stu-id="71ced-169">**Properties**</span></span> | 
<span data-ttu-id="71ced-170">蜂巢</span><span class="sxs-lookup"><span data-stu-id="71ced-170">Hive</span></span> | <span data-ttu-id="71ced-171">HKEY_LOCAL_MACHINE</span><span class="sxs-lookup"><span data-stu-id="71ced-171">HKEY_LOCAL_MACHINE</span></span>
<span data-ttu-id="71ced-172">機碼路徑</span><span class="sxs-lookup"><span data-stu-id="71ced-172">Key path</span></span> | <span data-ttu-id="71ced-173">SOFTWARE\Policies\Microsoft\ Windows Defender</span><span class="sxs-lookup"><span data-stu-id="71ced-173">SOFTWARE\Policies\Microsoft\Windows Defender</span></span>
<span data-ttu-id="71ced-174">數值名稱</span><span class="sxs-lookup"><span data-stu-id="71ced-174">Value name</span></span> | <span data-ttu-id="71ced-175">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="71ced-175">DisableAntiSpyware</span></span>
<span data-ttu-id="71ced-176">值類型</span><span class="sxs-lookup"><span data-stu-id="71ced-176">Value type</span></span> | <span data-ttu-id="71ced-177">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="71ced-177">REG_DWORD</span></span>
<span data-ttu-id="71ced-178">數值資料</span><span class="sxs-lookup"><span data-stu-id="71ced-178">Value data</span></span> | <span data-ttu-id="71ced-179">0x1 (1) </span><span class="sxs-lookup"><span data-stu-id="71ced-179">0x1 (1)</span></span>

###### <a name="if-security-settings-are-implemented-via-registry-key"></a><span data-ttu-id="71ced-180">如果透過登錄機碼來執行安全性設定</span><span class="sxs-lookup"><span data-stu-id="71ced-180">If security settings are implemented via registry key</span></span>

<span data-ttu-id="71ced-181">報告中可能會包含下列文字，表示 Microsoft Defender 防毒軟體已關閉：</span><span class="sxs-lookup"><span data-stu-id="71ced-181">The report may contain the following text, indicating that Microsoft Defender Antivirus is turned off:</span></span>
 
> <span data-ttu-id="71ced-182">Registry (regedit.exe) </span><span class="sxs-lookup"><span data-stu-id="71ced-182">Registry (regedit.exe)</span></span>
>
> <span data-ttu-id="71ced-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (十六進位) </span><span class="sxs-lookup"><span data-stu-id="71ced-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span></span>

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a><span data-ttu-id="71ced-184">在 Windows 或您的 Windows 伺服器映射中設定安全性設定</span><span class="sxs-lookup"><span data-stu-id="71ced-184">If security settings are set in Windows or your Windows Server image</span></span>

<span data-ttu-id="71ced-185">您的 imagining 系統管理員可能已透過 *GPEdit.exe*、 *LGPO.exe* 或在其任務順序中修改登錄，將安全性原則 **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**、從本機設定。</span><span class="sxs-lookup"><span data-stu-id="71ced-185">Your imagining admin might have set the security policy, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, locally via *GPEdit.exe*, *LGPO.exe*, or by modifying the registry in their task sequence.</span></span> <span data-ttu-id="71ced-186">您可以為 Microsoft Defender 防毒軟體[設定信任的影像識別碼](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender)。</span><span class="sxs-lookup"><span data-stu-id="71ced-186">You can [configure a Trusted Image Identifier](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) for Microsoft Defender Antivirus.</span></span>

### <a name="turn-microsoft-defender-antivirus-back-on"></a><span data-ttu-id="71ced-187">重新開啟 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="71ced-187">Turn Microsoft Defender Antivirus back on</span></span>

<span data-ttu-id="71ced-188">如果目前沒有任何使用中的反病毒，Microsoft Defender 防毒軟體會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="71ced-188">Microsoft Defender Antivirus will automatically turn on if no other antivirus is currently active.</span></span> <span data-ttu-id="71ced-189">您必須完全關閉協力廠商防病毒，以確保 Microsoft Defender 防毒軟體可以使用完整功能執行。</span><span class="sxs-lookup"><span data-stu-id="71ced-189">You'll need to turn the third-party antivirus completely off to ensure Microsoft Defender Antivirus can run with full functionality.</span></span>

> [!WARNING]
> <span data-ttu-id="71ced-190">我們建議您在 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services 中編輯 *wdboot*、 *wdfilter*、 *wdnisdrv*、 *wdnissvc* 和 *windefend* 的 *Windows Defender* start 值都不受支援，並且可能會強制您重新影像您的系統。</span><span class="sxs-lookup"><span data-stu-id="71ced-190">Solutions suggesting that you edit the *Windows Defender* start values for *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc*, and *windefend* in  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services are unsupported, and may force you to re-image your system.</span></span>

<span data-ttu-id="71ced-191">如果您開始使用 Microsoft Defender for Endpoint 和協力廠商的防毒軟體搭配 Microsoft Defender 防毒軟體，便可使用被動模式。</span><span class="sxs-lookup"><span data-stu-id="71ced-191">Passive mode is available if you start using Microsoft Defender for Endpoint and a third-party antivirus together with Microsoft Defender Antivirus.</span></span> <span data-ttu-id="71ced-192">被動式模式可讓 Microsoft Defender 掃描檔案並自行更新，但不會修正威脅。</span><span class="sxs-lookup"><span data-stu-id="71ced-192">Passive mode allows Microsoft Defender to scan files and update itself, but it will not remediate threats.</span></span> <span data-ttu-id="71ced-193">此外，透過 [即時保護](configure-real-time-protection-microsoft-defender-antivirus.md) 進行的行為監視無法在被動模式下使用，除非部署了 [端點資料遺失防護 (DLP) ](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) 。</span><span class="sxs-lookup"><span data-stu-id="71ced-193">In addition, behavior monitoring via [Real Time Protection](configure-real-time-protection-microsoft-defender-antivirus.md) is not available under passive mode, unless [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) is deployed.</span></span>

<span data-ttu-id="71ced-194">當 Microsoft Defender 防毒軟體設定為自動關閉時，使用者就可以使用另一個功能（也稱為[有限的定期掃描](limited-periodic-scanning-microsoft-defender-antivirus.md)）。</span><span class="sxs-lookup"><span data-stu-id="71ced-194">Another feature, known as [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md), is available to end-users when Microsoft Defender Antivirus is set to automatically turn off.</span></span> <span data-ttu-id="71ced-195">這項功能可讓 Microsoft Defender 防毒軟體使用有限的偵測數目，在協力廠商防病毒的情況下定期掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="71ced-195">This feature allows Microsoft Defender Antivirus to scan files periodically alongside a third-party antivirus, using a limited number of detections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71ced-196">在企業環境中不建議使用有限的定期掃描。</span><span class="sxs-lookup"><span data-stu-id="71ced-196">Limited periodic scanning is not recommended in enterprise environments.</span></span> <span data-ttu-id="71ced-197">在此模式下執行 Microsoft Defender 防毒軟體時可用的偵測、管理與報告功能，會隨著與使用中的模式而降低。</span><span class="sxs-lookup"><span data-stu-id="71ced-197">The detection, management and reporting capabilities available when running Microsoft Defender Antivirus in this mode are reduced as compared to active mode.</span></span>

### <a name="see-also"></a><span data-ttu-id="71ced-198">另請參閱</span><span class="sxs-lookup"><span data-stu-id="71ced-198">See also</span></span>

* [<span data-ttu-id="71ced-199">Microsoft Defender 防毒軟體相容性</span><span class="sxs-lookup"><span data-stu-id="71ced-199">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
* [<span data-ttu-id="71ced-200">Windows 安全性應用程式中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="71ced-200">Microsoft Defender Antivirus in the Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)