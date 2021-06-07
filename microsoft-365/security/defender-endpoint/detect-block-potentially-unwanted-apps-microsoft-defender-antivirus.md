---
title: 使用 MMicrosoft Defender 防毒軟體封鎖潛在的垃圾應用程式
description: 啟用潛在的垃圾應用程式（PUA）防毒功能封鎖垃圾軟體，例如廣告軟體。
keywords: PUA，啟用，垃圾軟體，垃圾應用程式，廣告軟體，瀏覽器工具列，偵測，封鎖，Windows Defender 防毒軟體
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: mimilone, julih
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/02/2021
ms.openlocfilehash: d7f411c81e839d3929d4aa1a52fda29399c59dca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772374"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="f1f4b-104">偵測並封鎖潛在的垃圾應用程式</span><span class="sxs-lookup"><span data-stu-id="f1f4b-104">Detect and block potentially unwanted applications</span></span>

<span data-ttu-id="f1f4b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f1f4b-105">**Applies to:**</span></span>

- [<span data-ttu-id="f1f4b-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f1f4b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="f1f4b-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f1f4b-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="f1f4b-108">潛在的垃圾應用程式（PUA）是一類軟體，可能導致您的機器執行速度緩慢、顯示非預期的廣告、或者最壞的情況是安裝其他非預期或不想要的軟體。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="f1f4b-109">PUA 並非病毒、惡意軟體或其他類型的威脅，但它可能在端點上執行會對端點效能或使用產生不良影響的動作。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="f1f4b-110">由於某些不良行為，經由 Microsoft Defender 進階威脅防護進行評估，術語 *PUA* 也可以指聲譽不佳的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="f1f4b-111">範例如下：</span><span class="sxs-lookup"><span data-stu-id="f1f4b-111">Here are some examples:</span></span>

- <span data-ttu-id="f1f4b-112">用於顯示廣告或促銷的 **廣告軟體**，包括將廣告插入網頁的軟體。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="f1f4b-113">用於安裝未由同一實體進行數位簽章的其他軟體的 **統合軟體**。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="f1f4b-114">另外，用於安裝其他符合 PUA 要求的軟體的軟體。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="f1f4b-115">積極嘗試逃避安全性產品偵測的 **逃避軟體**，包括在有安全性產品的情況下，行為會不同的軟體。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="f1f4b-116">若需要更多範例以及關於我們用來標籤應用程式以從安全性功能中特別注意的準則的討論，請參閱 [Microsoft 如何識別惡意軟體和潛在的垃圾應用程式](/windows/security/threat-protection/intelligence/criteria)。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="f1f4b-117">潛在的垃圾應用程式可能會增加網路被實際惡意軟體感染的風險、使惡意軟體感染難以識別，或者浪費 IT 資源來清理它們。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="f1f4b-118">Windows 10、Windows Server 2019 和 Windows Server 2016　均支援 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="f1f4b-119">在 Windows 10 (2004 及更新版本) 的預設情況下，Microsoft Defender 防毒軟體會封鎖被視為企業 (E5) 裝置 PUA 的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="f1f4b-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f1f4b-120">Microsoft Edge</span></span>

<span data-ttu-id="f1f4b-121">基於 Chromium 的 [新 Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea) 可以封鎖潛在的垃圾應用程式下載和相關的資源 URL。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="f1f4b-122">透過 [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 提供此功能。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="f1f4b-123">在基於 Chromium 的 Microsoft Edge 中啟用 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="f1f4b-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="f1f4b-124">儘管 Microsoft Edge (基於 Chromium ,版本 80.0.361.50) 中的潛在的垃圾應用程式保護預設為關閉狀態，但可以輕鬆地從瀏覽器中開啟它。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="f1f4b-125">在您的 Edge 瀏覽器中，選取省略符號，然後選擇 **[設定]**。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="f1f4b-126">選取 **隱私、搜尋和服務**。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="f1f4b-127">在 **[安全性]** 章節下，開啟 **[封鎖潛在的垃圾應用程式]**。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="f1f4b-128">如果您在執行 Microsoft Edge (基於 Chromium)，透過在其中一個 [[Microsoft Defender SmartScreen 示範頁面]](https://demo.smartscreen.msft.net/) 進行測試，您可以安全地探索 PUA 保護的 URL 封鎖功能。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="f1f4b-129">使用 Microsoft Defender SmartScreen 封鎖 URL</span><span class="sxs-lookup"><span data-stu-id="f1f4b-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="f1f4b-130">在啟用了 PUA 保護的基於Chromium 的 Edge 中，Microsoft Defender SmartScreen 可以保護您免受 PUA 關聯的 URL 的侵害。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="f1f4b-131">安全性管理員可以 [設定](/DeployEdge/configure-microsoft-edge) Microsoft Edge 和 Microsoft Defender SmartScreen 如何共同工作，以保護使用者群組免受與PUA 相關的 URL 的侵害。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="f1f4b-132">有幾種明確適用於 Microsoft Defender SmartScreen 的 [群組原則設定](/DeployEdge/microsoft-edge-policies#smartscreen-settings)，其中包括一種 [用於封鎖 PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled) 的原則設定。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="f1f4b-133">此外，使用群組原則設定開啟或關閉 Microsoft Defender SmartScreen，管理員可以整體 [設定 Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="f1f4b-134">雖然 Microsoft Defender 進階威脅防護根據 Microsoft 管理的資料集有自己的封鎖清單，您可以根據自己的威脅情報來自訂這個清單。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="f1f4b-135">如果您在 Microsoft Defender 進階威脅防護入口網站中 [建立和管理指標](manage-indicators.md)，則 Microsoft Defender SmartScreen 將遵守新設定。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="f1f4b-136">Microsoft Defender 防毒軟體和 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="f1f4b-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="f1f4b-137">Microsoft Defender 防毒軟體中的潛在的垃圾應用程式 (PUA) 保護功能可以偵測並封鎖網路中端點上的 PUA。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="f1f4b-138">Windows 10、Windows Server 2019 和 Windows Server 2016　均支援該功能。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="f1f4b-139">Microsoft Defender 防毒軟體封鎖偵測到的 PUA 檔案以及任和下載、移動、執行或安裝它們的嘗試。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="f1f4b-140">已封鎖的 PUA 檔案會被移至隔離。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="f1f4b-141">當在端點上偵測到 PUA 檔案時，Microsoft Defender 防毒軟體會以與其他威脅偵測相同的格式，向使用者發送通知 ([除非已停用通知](configure-notifications-microsoft-defender-antivirus.md))。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="f1f4b-142">通知以 `PUA:` 開頭以表示其內容。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="f1f4b-143">通知將顯示在慣例的 [Windows 安全性應用程式隔離清單](microsoft-defender-security-center-antivirus.md)中。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="f1f4b-144">在 Microsoft Defender 防毒軟體設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="f1f4b-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="f1f4b-145">您可以使用 [Microsoft Intune](/mem/intune/protect/device-protect)、[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection)、[群組原則](/azure/active-directory-domain-services/manage-group-policy)，或者透過 [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps) 來啟用 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="f1f4b-146">您也可以在稽核模式使用 PUA 保護以偵測潛在的垃圾應用程式而不封鎖它們。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="f1f4b-147">偵測會被 Windows 事件記錄擷取。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="f1f4b-148">請造訪 Microsoft Defender 進階威脅防護的示範網站: [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep)，以確認該功能正常運行，並看它如何運作。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="f1f4b-149">如果貴公司正在進行內部軟體安全性合規性檢查，並且希望避免任何誤報，稽核模式的 PUA 保護很實用。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="f1f4b-150">使用 Intune 來設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="f1f4b-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="f1f4b-151">請參閱 [《在 Microsoft Intune 中設定裝置限制設定》](/intune/device-restrictions-configure) 及 [《Windows 10 中 Intune 的 Microsoft Defender 防毒軟體裝置限制設定》](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 了解詳情。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="f1f4b-152">使用 Configuration Manager 來設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="f1f4b-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="f1f4b-153">Microsoft 端點管理員 (目前分支) 中會預設啟用 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="f1f4b-154">請參閱 [《如何建立和部署反惡意程式碼原則: 亦排程的掃描設定》](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) 深入了解 Microsoft 端點管理員 (目前分支) 的設定。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="f1f4b-155">針對 System Center 2012 Configuration Manager，請參閱 [如何在 Configuration Manager 中為端點保護部署潛在的垃圾應用程式保護原則](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="f1f4b-156">Microsoft Defender 防毒軟體封鎖的 PUA 事件會在 Windows 事件檢視器中舉報，而不是在 Microsoft Endpoint Configuration Manager 中。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="f1f4b-157">使用群組原則來設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="f1f4b-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="f1f4b-158">下載並安裝 [Windows 10 的系統管理範本 (.admx) 2020 年 10 月更新 (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="f1f4b-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="f1f4b-159">在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="f1f4b-160">選取您想設定的群組原則物件，然後選擇 **編制**。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="f1f4b-161">在 **[群組原則管理編輯器]** 中，移至 **[電腦設定]** 然後選取 **[系統管理範本]**。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="f1f4b-162">展開 **Windows 元件** > **Microsoft Defender 防毒軟體** 的樹狀結構。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="f1f4b-163">按兩下以 **設定潛在的垃圾應用程式 (PUA) 的偵測**。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="f1f4b-164">選取 **[啟用]** 來啟用 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="f1f4b-165">在 **[選項]**，選取 **[封鎖]** 來封鎖潛在的垃圾應用程式，或選取 **[稽核模式]** 來測試您環境中的設定如何運作。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="f1f4b-166">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-166">Select **OK**.</span></span>

9. <span data-ttu-id="f1f4b-167">如常部署您的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="f1f4b-168">使用 PowerShell Cmdlet 來設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="f1f4b-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="f1f4b-169">啟用 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="f1f4b-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="f1f4b-170">將此 Cmdlet 的值設定為 `Enabled`，會開啟已被停用的功能。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="f1f4b-171">將 PUSA 保護設定到稽核模式</span><span class="sxs-lookup"><span data-stu-id="f1f4b-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="f1f4b-172">設定 `AuditMode` 可以偵測 PUA 但不封鎖它們。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="f1f4b-173">停用 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="f1f4b-173">To disable PUA protection</span></span>

<span data-ttu-id="f1f4b-174">我們推薦持續開啟 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="f1f4b-175">不過，如果您可以使用下列 Cmdlet 來關閉它:</span><span class="sxs-lookup"><span data-stu-id="f1f4b-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="f1f4b-176">將此 Cmdlet 的值設定為 `Disabled`，會關閉已被啟用的功能。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="f1f4b-177">要深入了解，請參閱 [《使用 PowerShell Cmdlets 設定和執行 Microsoft Defender 防毒軟體》](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlets](/powershell/module/defender/index)。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="f1f4b-178">使用 PowerShell 檢視 PUA 事件</span><span class="sxs-lookup"><span data-stu-id="f1f4b-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="f1f4b-179">在 Windows 事件檢視器中舉報 PUA 事件，但在　Microsoft Endpoint Manager 或 Intune 中則不舉報。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="f1f4b-180">您也可以使用 `Get-MpThreat` Cmdlet 來檢視 Microsoft Defender 防毒軟體已經處理的威脅。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="f1f4b-181">以下為範例:</span><span class="sxs-lookup"><span data-stu-id="f1f4b-181">Here's an example:</span></span>

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="f1f4b-182">收取關於 PUA 偵測的電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="f1f4b-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="f1f4b-183">您開業開啟電子郵件通知以接收關於 PUA 偵測的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="f1f4b-184">關於檢視 Microsoft Defender 防毒軟體事件的詳細資料，請參閲 [《疑難排解事件識別碼》](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="f1f4b-185">PUA 事件記錄在事件識別碼 **1160** 下。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="f1f4b-186">使用進階搜捕檢視 PUA 事件</span><span class="sxs-lookup"><span data-stu-id="f1f4b-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="f1f4b-187">如果您使用 [Microsoft Defender 進階威脅防護](microsoft-defender-endpoint.md)，則可以使用進階搜捕查詢來檢視 PUA 事件。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="f1f4b-188">以下為範例查詢:</span><span class="sxs-lookup"><span data-stu-id="f1f4b-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName = tostring(x.ThreatName), WasExecutingWhileDetected = tostring(x.WasExecutingWhileDetected), WasRemediated = tostring(x.WasRemediated)
| where ThreatName startswith_cs 'PUA:'
```

<span data-ttu-id="f1f4b-189">深入了解進階搜捕，請參閲 [《使用進階搜捕主動搜捕威脅》](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="f1f4b-190">排除來自 PUA 保護的檔案</span><span class="sxs-lookup"><span data-stu-id="f1f4b-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="f1f4b-191">有時一個檔案會不小心被 PUA 保護封鎖，或者需要 PUA 的功能來完成一個工作。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="f1f4b-192">在這些情況下，檔案可以新增到排除項目清單。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="f1f4b-193">如需詳細資訊，請參閱 [《設定及驗證基於檔案副檔名和資料夾位置的排除》](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="f1f4b-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f1f4b-194">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f1f4b-194">See also</span></span>

- [<span data-ttu-id="f1f4b-195">新一代保護</span><span class="sxs-lookup"><span data-stu-id="f1f4b-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="f1f4b-196">設定行為、啟發學習法和即時保護</span><span class="sxs-lookup"><span data-stu-id="f1f4b-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)