---
title: 使用 Microsoft Defender 防毒軟體封鎖可能有害的應用程式
description: 啟用可能有害的應用程式 (PUA) 防病毒功能，以封鎖廣告軟體等不需要的軟體。
keywords: pua、啟用、不想要的軟體、有害的應用程式、廣告軟體、瀏覽器工具列、偵測、封鎖、Microsoft Defender 防毒程式
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bee92dfa998596578c27bda579a86776bc77c07b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690231"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="d3d7f-104">偵測並封鎖可能有害的應用程式</span><span class="sxs-lookup"><span data-stu-id="d3d7f-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d3d7f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d3d7f-105">**Applies to:**</span></span>

- [<span data-ttu-id="d3d7f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d3d7f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="d3d7f-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d3d7f-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> <span data-ttu-id="d3d7f-108">可能有害的應用程式 (PUA) 是一種軟體類別，可導致您的機器執行緩慢、顯示未預期的廣告，或是最壞的軟體安裝可能是意外或不需要的軟體。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> <span data-ttu-id="d3d7f-109">依預設，在 Windows 10 (版本2004和更新版本) 中，Microsoft Defender 防毒程式會封鎖視為 PUA 的應用程式，適用于 Enterprise (E5) 裝置。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-109">By default in Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA, for Enterprise (E5) devices.</span></span>

<span data-ttu-id="d3d7f-110">可能不需要的應用程式 (PUA) 不會被視為病毒、惡意程式碼或其他類型的威脅，但他們可能會對不會影響端點效能或使用的端點執行動作。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-110">Potentially unwanted applications (PUA) are not considered viruses, malware, or other types of threats, but they might perform actions on endpoints which adversely affect endpoint performance or use.</span></span> <span data-ttu-id="d3d7f-111">_PUA_ 也可以參考具有不良信譽的應用程式，因為這種不良行為會因某些類型的不良行為而評估。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-111">_PUA_ can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="d3d7f-112">以下為一些範例：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-112">Here are some examples:</span></span>

- <span data-ttu-id="d3d7f-113">顯示廣告或促銷的 **廣告軟體**，包含將廣告插入網頁的軟體。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-113">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="d3d7f-114">**搭售軟體** ，以安裝不是由相同實體進行數位簽署的其他軟體。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-114">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="d3d7f-115">此外，也就是提供安裝其他符合 PUA 之軟體的軟體。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-115">Also, software that offers to install other software that qualify as PUA.</span></span>
- <span data-ttu-id="d3d7f-116">**規避軟體** ，會積極企圖規避安全性產品的偵測，包括在安全性產品存在時，行為會不同的軟體。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-116">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="d3d7f-117">如需更多範例，以及我們用於標示應用程式以特別注意安全性功能的準則，請參閱 [Microsoft 如何識別惡意程式碼和潛在的有害應用程式](/windows/security/threat-protection/intelligence/criteria)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-117">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="d3d7f-118">可能有害的應用程式可能會增加網路受到實際惡意程式碼感染的風險，使惡意程式碼感染難於識別，或浪費 IT 資源以加以清除。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-118">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="d3d7f-119">Windows 10、Windows Server 2019 及 Windows Server 2016 都支援 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-119">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="d3d7f-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d3d7f-120">Microsoft Edge</span></span>

<span data-ttu-id="d3d7f-121">[新的 Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)會以 Chromium 為基礎，封鎖可能有害的應用程式下載和相關聯的資源 URLs。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="d3d7f-122">這項功能是透過 [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)所提供。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="d3d7f-123">在以 Chromium 為基礎的 Microsoft Edge 中啟用 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="d3d7f-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="d3d7f-124">雖然 Microsoft Edge 中可能有害的應用程式保護 (以 Chromium 為基礎的版本 80.0.361.50) 會預設為關閉，但是可以從瀏覽器中輕鬆地開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="d3d7f-125">選取省略號，然後選擇 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-125">Select the ellipses, and then choose **Settings**.</span></span>
2. <span data-ttu-id="d3d7f-126">選取 [ **隱私權]、[搜尋] 及 [服務**]。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-126">Select **Privacy, search, and services**.</span></span>
3. <span data-ttu-id="d3d7f-127">在 [ **安全性** ] 區段中，開啟 [ **封鎖可能有害的應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="d3d7f-128">如果您正在執行 Microsoft Edge (以 Chromium 為基礎的) ，您可以在其中一個 [Microsoft Defender SmartScreen 示範頁面](https://demo.smartscreen.msft.net/)上進行測試，以安全地探索 PUA 保護的 URL 封鎖功能。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="d3d7f-129">使用 Microsoft Defender SmartScreen 封鎖 URLs</span><span class="sxs-lookup"><span data-stu-id="d3d7f-129">Blocking URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="d3d7f-130">在開啟 PUA 保護的 Chromium 型 Edge 中，Microsoft Defender SmartScreen 會從 PUA 關聯的 URLs 中保護您。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="d3d7f-131">安全性管理員可以 [設定](/DeployEdge/configure-microsoft-edge) microsoft Edge 和 Microsoft Defender SmartScreen 如何共同運作，以保護使用者群組免受 PUA 關聯的 URLs。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="d3d7f-132">有幾個 [群組原則設定](/DeployEdge/microsoft-edge-policies#smartscreen-settings) 會明確用於 Microsoft Defender SmartScreen，包括 [一個用於封鎖 PUA 的](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="d3d7f-133">此外，系統管理員可以使用「群組原則」設定將 microsoft defender SmartScreen 開啟或關閉，以整體 [設定 Microsoft defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) 。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="d3d7f-134">雖然 Microsoft Defender for Endpoint 有其自己的封鎖清單是根據 Microsoft 所管理的資料集而定，您可以根據您自己的威脅情報來自訂此清單。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-134">Although Microsoft Defender for Endpoint has its own block list based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="d3d7f-135">如果您在 Microsoft Defender for Endpoint 入口網站中 [建立及管理指示器](/microsoft-365/security/defender-endpoint/manage-indicators) ，microsoft defender SmartScreen 會尊重新設定。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-135">If you [create and manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus"></a><span data-ttu-id="d3d7f-136">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d3d7f-136">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="d3d7f-137">Microsoft Defender 防毒軟體中可能有害的 application (PUA) protection 功能可偵測並封鎖您網路中端點的 PUAs。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUAs on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="d3d7f-138">這項功能可在 Windows 10、Windows Server 2019 及 Windows Server 2016 中取得。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="d3d7f-139">Microsoft Defender 防病毒封鎖偵測到 PUA 檔案，以及任何嘗試下載、移動、執行或安裝這些檔案。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="d3d7f-140">封鎖的 PUA 檔案會移至隔離區。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="d3d7f-141">在端點上偵測到 PUA 檔案時， [除非已停用通知，否則](configure-notifications-microsoft-defender-antivirus.md) Microsoft Defender 防病毒會傳送通知給使用者 (，) 與其他威脅偵測的格式相同。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="d3d7f-142">通知會 `PUA:` 以指示其內容的開頭。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="d3d7f-143">通知會出現在 [Windows 安全性應用程式內的一般隔離清單](microsoft-defender-security-center-antivirus.md)中。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="d3d7f-144">設定 Microsoft Defender 防毒軟體中的 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="d3d7f-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="d3d7f-145">您可以使用 [Microsoft Intune](/mem/intune/protect/device-protect)、 [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection)、 [群組原則](/azure/active-directory-domain-services/manage-group-policy)或透過 [PowerShell Cmdlet](/powershell/module/defender/?preserve-view=true&view=win10-ps)來啟用 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="d3d7f-146">您也可以在稽核模式中使用 PUA 保護，以偵測可能有害的應用程式，而不加以封鎖。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="d3d7f-147">在 Windows 事件記錄檔中捕獲偵測。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="d3d7f-148">在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) 流覽 Microsoft Defender for Endpoint 示範網站，以確認該功能是否正常運作，並將其顯示在 [動作] 中。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="d3d7f-149">如果貴公司正在進行內部軟體安全性符合性檢查，且您想要避免任何誤報，請 PUA protection 模式中的 [保護] 功能非常有用。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

#### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="d3d7f-150">使用 Intune 設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="d3d7f-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="d3d7f-151">如需詳細資訊，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure) 及 [Intune 中 Windows 10 的 Microsoft Defender 防病毒裝置限制設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

#### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="d3d7f-152">使用 Configuration Manager 來設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="d3d7f-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="d3d7f-153">PUA 目前的分支) 中的 Microsoft 端點管理員 (預設會啟用 [保護]。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="d3d7f-154">請參閱 [如何建立及部署反惡意程式碼原則：排程的掃描設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) ，以取得設定 Microsoft 端點管理員 (目前分支) 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="d3d7f-155">如需 System Center 2012 Configuration Manager，請參閱 [如何在 Configuration manager 中為 Endpoint Protection 部署可能不需要的應用程式保護原則](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="d3d7f-156">PUA 由 Microsoft Defender 防病毒封鎖的事件會在 Windows 事件檢視器中報告，而不會在 Microsoft 端點 Configuration Manager 中報告。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

#### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="d3d7f-157">使用群組原則來設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="d3d7f-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="d3d7f-158">下載及安裝 [Windows 10 十月 2020 Update (20H2) 的系統管理範本 ( admx) ](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="d3d7f-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="d3d7f-159">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="d3d7f-160">選取您要設定的群組原則物件，然後選擇 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="d3d7f-161">在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後選取 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="d3d7f-162">將樹狀目錄展開為  >  **microsoft Defender 防毒軟體** 的 Windows 元件。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="d3d7f-163">按兩下 [ **設定可能有害之應用程式的偵測**]。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="d3d7f-164">選取 [ **啟用** ] 以啟用 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="d3d7f-165">在 [ **選項**] 中，選取 [ **封鎖** ] 以封鎖可能不需要的應用程式，或選取 [ **核查模式]** 以測試設定在您的環境中的運作</span><span class="sxs-lookup"><span data-stu-id="d3d7f-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="d3d7f-166">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-166">Select **OK**.</span></span>

9. <span data-ttu-id="d3d7f-167">像往常一樣部署您的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-167">Deploy your Group Policy object as you usually do.</span></span>

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="d3d7f-168">使用 PowerShell Cmdlet 來設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="d3d7f-168">Use PowerShell cmdlets to configure PUA protection</span></span>

##### <a name="to-enable-pua-protection"></a><span data-ttu-id="d3d7f-169">啟用 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="d3d7f-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="d3d7f-170">設定此 Cmdlet 的值可 `Enabled` 在已停用時開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-170">Setting the value for this cmdlet to `Enabled` turns the feature on if it has been disabled.</span></span>

##### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="d3d7f-171">將 PUA 防護設定為稽核模式</span><span class="sxs-lookup"><span data-stu-id="d3d7f-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="d3d7f-172">設定 `AuditMode` 偵測 PUAs 但不加以封鎖。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

##### <a name="to-disable-pua-protection"></a><span data-ttu-id="d3d7f-173">停用 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="d3d7f-173">To disable PUA protection</span></span>

<span data-ttu-id="d3d7f-174">建議您保持 PUA 保護開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="d3d7f-175">不過，您可以使用下列 Cmdlet 來關閉它：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="d3d7f-176">設定此 Cmdlet 的值，以 `Disabled` 關閉該功能（如果已啟用）。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-176">Setting the value for this cmdlet to `Disabled` turns the feature off if it has been enabled.</span></span>

<span data-ttu-id="d3d7f-177">如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/index) 。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-177">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="view-pua-events"></a><span data-ttu-id="d3d7f-178">View PUA 事件</span><span class="sxs-lookup"><span data-stu-id="d3d7f-178">View PUA events</span></span>

<span data-ttu-id="d3d7f-179">PUA 事件會在 Windows 事件檢視器中報告，但不會在 Microsoft 端點管理員或 Intune 中報告。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="d3d7f-180">您也可以使用 `Get-MpThreat` Cmdlet 來查看 Microsoft Defender 防病毒處理的威脅。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="d3d7f-181">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="d3d7f-181">Here's an example:</span></span>

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

<span data-ttu-id="d3d7f-182">您可以開啟電子郵件通知，以接收 PUA 偵測的郵件。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-182">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="d3d7f-183">如需查看 Microsoft Defender 防病毒事件的詳細資訊，請參閱 [事件 IDs 疑難排解](troubleshoot-microsoft-defender-antivirus.md) 。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-183">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="d3d7f-184">PUA 事件會記錄在事件識別碼 **1160** 底下。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-184">PUA events are recorded under event ID **1160**.</span></span>

## <a name="excluding-files"></a><span data-ttu-id="d3d7f-185">排除檔案</span><span class="sxs-lookup"><span data-stu-id="d3d7f-185">Excluding files</span></span>

<span data-ttu-id="d3d7f-186">有時，PUA 保護會錯誤地封鎖檔案，或需要 PUA 的功能才能完成任務。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-186">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="d3d7f-187">在這些情況下，您可以將檔案新增至排除清單。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-187">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="d3d7f-188">如需詳細資訊，請參閱 [根據副檔名和資料夾位置設定及驗證排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d7f-188">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3d7f-189">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d3d7f-189">See also</span></span>

- [<span data-ttu-id="d3d7f-190">新一代保護技術</span><span class="sxs-lookup"><span data-stu-id="d3d7f-190">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d3d7f-191">設定行為、啟發式和即時保護</span><span class="sxs-lookup"><span data-stu-id="d3d7f-191">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)