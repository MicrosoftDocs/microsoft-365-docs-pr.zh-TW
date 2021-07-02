---
title: 建立檔案的指示器
ms.reviewer: ''
description: 為定義實體的偵測、預防和排除的檔案雜湊，建立指示器。
keywords: file，hash，manage，允許，封鎖，封鎖，clean，惡意，檔案雜湊，ip 位址，url，網域
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256912"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="55357-104">建立檔案的指示器</span><span class="sxs-lookup"><span data-stu-id="55357-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55357-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="55357-105">**Applies to:**</span></span>
- [<span data-ttu-id="55357-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="55357-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="55357-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55357-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="55357-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="55357-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="55357-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="55357-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="55357-110">Banning 潛在的惡意檔案或可疑惡意程式碼，以防止進一步傳播您組織中的攻擊。</span><span class="sxs-lookup"><span data-stu-id="55357-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="55357-111">如果您知道可能是惡意遷移的可執行檔 (PE) file，您可以將它封鎖。</span><span class="sxs-lookup"><span data-stu-id="55357-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="55357-112">此作業可防止在組織中的裝置上讀取、寫入或執行此作業。</span><span class="sxs-lookup"><span data-stu-id="55357-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="55357-113">您可以透過三種方式來建立檔案的指示器：</span><span class="sxs-lookup"><span data-stu-id="55357-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="55357-114">透過 [設定] 頁面建立指示器</span><span class="sxs-lookup"><span data-stu-id="55357-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="55357-115">使用 [檔案詳細資料] 頁面中的 [新增指示器] 按鈕建立上下文指示器</span><span class="sxs-lookup"><span data-stu-id="55357-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="55357-116">透過[指示器 API](ti-indicator.md)建立指示器</span><span class="sxs-lookup"><span data-stu-id="55357-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="55357-117">開始之前</span><span class="sxs-lookup"><span data-stu-id="55357-117">Before you begin</span></span>

<span data-ttu-id="55357-118">在建立檔案的指示器之前，請務必先瞭解下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="55357-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="55357-119">如果您的組織使用 **Microsoft Defender 防毒軟體 (使用中) 模式**，且 **已啟用雲端型防護**，則可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="55357-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="55357-120">如需詳細資訊，請參閱 [管理以雲端為基礎的保護](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="55357-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="55357-121">反惡意軟體用戶端版本必須是4.18.1901 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="55357-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="55357-122">請參閱 [每月平臺和引擎版本](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="55357-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="55357-123">在具有 Windows 10 版本1703或更新版本的裝置上支援 Windows Server 2016 和2019。</span><span class="sxs-lookup"><span data-stu-id="55357-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="55357-124">若要開始封鎖檔，您必須先在設定中 [開啟「封鎖或允許」功能](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="55357-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="55357-125">這項功能的設計是為了防止可疑的惡意程式碼 (或可能的惡意檔案) 從網頁下載。</span><span class="sxs-lookup"><span data-stu-id="55357-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="55357-126">它目前支援可遷移的可執行檔 (PE) 檔案（包括 .exe 和 .dll 檔案）。</span><span class="sxs-lookup"><span data-stu-id="55357-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="55357-127">覆蓋範圍會隨著時間擴充。</span><span class="sxs-lookup"><span data-stu-id="55357-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="55357-128">從 [設定] 頁面建立檔案的指標</span><span class="sxs-lookup"><span data-stu-id="55357-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="55357-129">在功能窗格中，選取 [ **設定 >** 指標]。</span><span class="sxs-lookup"><span data-stu-id="55357-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="55357-130">選取 [檔案 **雜湊**] 索引標籤   。</span><span class="sxs-lookup"><span data-stu-id="55357-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="55357-131">選取 [ **新增指示器**]。</span><span class="sxs-lookup"><span data-stu-id="55357-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="55357-132">指定下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="55357-132">Specify the following details:</span></span>
    - <span data-ttu-id="55357-133">標記-指定實體詳細資料並定義指示器的到期期限。</span><span class="sxs-lookup"><span data-stu-id="55357-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="55357-134">Action-指定要採取的動作並提供描述。</span><span class="sxs-lookup"><span data-stu-id="55357-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="55357-135">Scope-定義裝置群組的範圍。</span><span class="sxs-lookup"><span data-stu-id="55357-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="55357-136">在 [摘要] 索引標籤中查看詳細資料，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="55357-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="55357-137">從 [檔案詳細資料] 頁面建立上下文指示器</span><span class="sxs-lookup"><span data-stu-id="55357-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="55357-138">對檔案採取 [回應動作](respond-file-alerts.md)的其中一個選項   是為檔案新增標記。</span><span class="sxs-lookup"><span data-stu-id="55357-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="55357-139">當您為檔案新增指示器雜湊時，您可以選擇每當組織中的設備嘗試執行時，就會引發警示並封鎖檔案。</span><span class="sxs-lookup"><span data-stu-id="55357-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="55357-140">標記自動封鎖的檔案不會出現在檔案的動作中心，但提醒仍會顯示在 [警示] 佇列中。</span><span class="sxs-lookup"><span data-stu-id="55357-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="55357-141">通常會在幾分鐘內強制執行並移除檔區塊，但可長達30分鐘。</span><span class="sxs-lookup"><span data-stu-id="55357-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> 
>- <span data-ttu-id="55357-142">如果有相同的強制類型和目標的衝突檔案 IoC 原則，則會套用更安全的雜湊原則。</span><span class="sxs-lookup"><span data-stu-id="55357-142">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure hash will be applied.</span></span> <span data-ttu-id="55357-143">SHA-256 檔案雜湊 IoC 原則會透過 SHA-1 檔案雜湊 IoC 原則進行贏取，如果雜湊類型定義同一個檔案，該原則將會贏取 MD5 的檔案雜湊 IoC 原則。</span><span class="sxs-lookup"><span data-stu-id="55357-143">An SHA-256 file hash IoC policy will win over an SHA-1 file hash IoC policy, which will win over an MD5 file hash IoC policy if the hash types define the same file.</span></span> <span data-ttu-id="55357-144">不論裝置群組為何，此值都是如此。</span><span class="sxs-lookup"><span data-stu-id="55357-144">This is always true regardless of the device group.</span></span> 
>   <span data-ttu-id="55357-145">在所有其他情況下，如果與相同強制目標的衝突檔案 IoC 原則套用至所有裝置和裝置群組，則裝置群組中的原則會獲勝。</span><span class="sxs-lookup"><span data-stu-id="55357-145">In all other cases, if conflicting file IoC policies with the same enforcement target are applied to all devices and to the device’s group, then for a device, the policy in the device group will win.</span></span> 
>   
>- <span data-ttu-id="55357-146">如果停用 EnableFileHashComputation 群組原則，則會降低檔 IoC 的封鎖精確度。</span><span class="sxs-lookup"><span data-stu-id="55357-146">If the EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="55357-147">不過，啟用 `EnableFileHashComputation` 可能會影響裝置效能。</span><span class="sxs-lookup"><span data-stu-id="55357-147">However, enabling `EnableFileHashComputation` may impact device performance.</span></span> <span data-ttu-id="55357-148">例如，將網路共用中的大型檔案複製到您的本機裝置（特別是透過 VPN 連線）時，可能會對裝置效能產生影響。</span><span class="sxs-lookup"><span data-stu-id="55357-148">For example, copying large files from a network share onto your local device, especially over a VPN connection, might have an effect on device performance.</span></span>
>
>   <span data-ttu-id="55357-149">如需 EnableFileHashComputation 群組原則的詳細資訊，請參閱 [DEFENDER CSP](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="55357-149">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="55357-150">原則衝突處理</span><span class="sxs-lookup"><span data-stu-id="55357-150">Policy conflict handling</span></span>  

<span data-ttu-id="55357-151">Cert 和檔案 IoC 原則處理衝突會依照下列順序進行：</span><span class="sxs-lookup"><span data-stu-id="55357-151">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="55357-152">如果 Windows Defender 應用程式控制和 AppLocker 強制執行模式原則/原則不允許檔案，則 **封鎖**</span><span class="sxs-lookup"><span data-stu-id="55357-152">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="55357-153">否則，如果 Microsoft Defender 防毒軟體的排除允許檔案，則 **允許**</span><span class="sxs-lookup"><span data-stu-id="55357-153">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="55357-154">否則，如果檔遭到封鎖或警告檔或 IoC，則封鎖 **/警告**</span><span class="sxs-lookup"><span data-stu-id="55357-154">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="55357-155">否則，如果 allow file IoC 原則允許檔案，則 **允許**</span><span class="sxs-lookup"><span data-stu-id="55357-155">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="55357-156">如果是由 ASR 規則、共同體、AV、SmartScreen 封鎖檔案，則為 Else，然後 **封鎖**</span><span class="sxs-lookup"><span data-stu-id="55357-156">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="55357-157">否則 **(** Windows Defender 應用程式控制 & AppLocker 原則，則不會對其套用 IoC 規則) </span><span class="sxs-lookup"><span data-stu-id="55357-157">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="55357-158">如果有相同的強制類型和目標的相互衝突的檔 IoC 原則，則更安全 (的原則會套用較長) 雜湊。</span><span class="sxs-lookup"><span data-stu-id="55357-158">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="55357-159">例如，如果兩個雜湊類型都定義相同的檔案，SHA-256 檔案雜湊 IoC 原則會在 MD5 檔案雜湊 IoC 原則上贏取。</span><span class="sxs-lookup"><span data-stu-id="55357-159">For example, an SHA-256 file hash IoC policy will win over an MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="55357-160">威脅和弱點管理的封鎖漏洞應用程式功能會使用檔案 IoCs 進行強制執行，並遵循上述衝突處理順序。</span><span class="sxs-lookup"><span data-stu-id="55357-160">Threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="55357-161">範例</span><span class="sxs-lookup"><span data-stu-id="55357-161">Examples</span></span>

|<span data-ttu-id="55357-162">元件</span><span class="sxs-lookup"><span data-stu-id="55357-162">Component</span></span> |<span data-ttu-id="55357-163">元件強制執行</span><span class="sxs-lookup"><span data-stu-id="55357-163">Component enforcement</span></span> |<span data-ttu-id="55357-164">檔標記動作</span><span class="sxs-lookup"><span data-stu-id="55357-164">File indicator Action</span></span> |<span data-ttu-id="55357-165">結果</span><span class="sxs-lookup"><span data-stu-id="55357-165">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="55357-166">攻擊面減少檔路徑排除</span><span class="sxs-lookup"><span data-stu-id="55357-166">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="55357-167">允許</span><span class="sxs-lookup"><span data-stu-id="55357-167">Allow</span></span> |<span data-ttu-id="55357-168">封鎖</span><span class="sxs-lookup"><span data-stu-id="55357-168">Block</span></span> |<span data-ttu-id="55357-169">封鎖</span><span class="sxs-lookup"><span data-stu-id="55357-169">Block</span></span>
|<span data-ttu-id="55357-170">攻擊面減少規則</span><span class="sxs-lookup"><span data-stu-id="55357-170">Attack surface reduction rule</span></span> |<span data-ttu-id="55357-171">封鎖</span><span class="sxs-lookup"><span data-stu-id="55357-171">Block</span></span> |<span data-ttu-id="55357-172">允許</span><span class="sxs-lookup"><span data-stu-id="55357-172">Allow</span></span> |<span data-ttu-id="55357-173">允許</span><span class="sxs-lookup"><span data-stu-id="55357-173">Allow</span></span>
|<span data-ttu-id="55357-174">Windows Defender 應用程式控制</span><span class="sxs-lookup"><span data-stu-id="55357-174">Windows Defender Application Control</span></span> |<span data-ttu-id="55357-175">允許</span><span class="sxs-lookup"><span data-stu-id="55357-175">Allow</span></span> |<span data-ttu-id="55357-176">封鎖</span><span class="sxs-lookup"><span data-stu-id="55357-176">Block</span></span> |<span data-ttu-id="55357-177">允許</span><span class="sxs-lookup"><span data-stu-id="55357-177">Allow</span></span> |
|<span data-ttu-id="55357-178">Windows Defender 應用程式控制</span><span class="sxs-lookup"><span data-stu-id="55357-178">Windows Defender Application Control</span></span> |<span data-ttu-id="55357-179">封鎖</span><span class="sxs-lookup"><span data-stu-id="55357-179">Block</span></span> |<span data-ttu-id="55357-180">允許</span><span class="sxs-lookup"><span data-stu-id="55357-180">Allow</span></span> |<span data-ttu-id="55357-181">封鎖</span><span class="sxs-lookup"><span data-stu-id="55357-181">Block</span></span>
|<span data-ttu-id="55357-182">Microsoft Defender 防毒軟體排除</span><span class="sxs-lookup"><span data-stu-id="55357-182">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="55357-183">允許</span><span class="sxs-lookup"><span data-stu-id="55357-183">Allow</span></span> |<span data-ttu-id="55357-184">封鎖</span><span class="sxs-lookup"><span data-stu-id="55357-184">Block</span></span> |<span data-ttu-id="55357-185">允許</span><span class="sxs-lookup"><span data-stu-id="55357-185">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="55357-186">另請參閱</span><span class="sxs-lookup"><span data-stu-id="55357-186">See also</span></span>

- [<span data-ttu-id="55357-187">建立指示器</span><span class="sxs-lookup"><span data-stu-id="55357-187">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="55357-188">建立 IP 和 URL/網域的指示器</span><span class="sxs-lookup"><span data-stu-id="55357-188">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="55357-189">根據憑證建立指示器</span><span class="sxs-lookup"><span data-stu-id="55357-189">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="55357-190">管理指示器</span><span class="sxs-lookup"><span data-stu-id="55357-190">Manage indicators</span></span>](indicator-manage.md)
