---
title: 建立 IP 和 URL/網域的指示器
ms.reviewer: ''
description: 為 IPs 及定義實體的偵測、預防和排除的 URLs/網域建立指示器。
keywords: ip，url，domain，manage，允許，封鎖，封鎖，clean，惡意，檔雜湊，ip 位址，url，網域
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
ms.openlocfilehash: e7dc11fe709a6d04b6309706df90f0ebbc177e25
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841063"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="086d3-104">建立 IP 和 URL/網域的指示器</span><span class="sxs-lookup"><span data-stu-id="086d3-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="086d3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="086d3-105">**Applies to:**</span></span>
- [<span data-ttu-id="086d3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="086d3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="086d3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="086d3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="086d3-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="086d3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="086d3-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="086d3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="086d3-110">Defender for Endpoint 可以透過 microsoft browser 的 Windows Defender SmartScreen，以及透過瀏覽器以外的非 Microsoft 瀏覽器或通話的網路保護，封鎖 microsoft 認為是惡意的 IPs/URLs。</span><span class="sxs-lookup"><span data-stu-id="086d3-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="086d3-111">其威脅情報資料集是由 Microsoft 所管理。</span><span class="sxs-lookup"><span data-stu-id="086d3-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="086d3-112">透過為 IPs 和 URLs 或網域建立指示器，您現在可以根據自己的威脅情報，允許或封鎖 IPs、URLs 或網域。</span><span class="sxs-lookup"><span data-stu-id="086d3-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="086d3-113">您可以透過 [設定] 頁面或電腦群組來執行這項操作，如果您認為某些群組比其他群組的風險多或少。</span><span class="sxs-lookup"><span data-stu-id="086d3-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="086d3-114">不支援以無類別 Inter-Domain 路由 (CIDR) 表示的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="086d3-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="086d3-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="086d3-115">Before you begin</span></span>
<span data-ttu-id="086d3-116">在建立 IPS、URLs 或網域的指示器之前，請務必先瞭解下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="086d3-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="086d3-117">URL/IP 允許和封鎖依賴在封鎖模式中啟用的 Defender for Endpoint component 網路保護。</span><span class="sxs-lookup"><span data-stu-id="086d3-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="086d3-118">如需網路保護和設定指示的詳細資訊，請參閱 [Enable Network Protection](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="086d3-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="086d3-119">反惡意軟體用戶端版本必須是4.18.1906 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="086d3-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="086d3-120">在 Windows 10 版本1709或更新版本上支援的機器上。</span><span class="sxs-lookup"><span data-stu-id="086d3-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="086d3-121">確定 **設定 > 的高級功能 Microsoft Defender 資訊安全中心 >** 中已啟用 **自訂網路指示器**。</span><span class="sxs-lookup"><span data-stu-id="086d3-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="086d3-122">如需詳細資訊，請參閱 [高級功能](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="086d3-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="086d3-123">如需 iOS 的指示器支援，請參閱 [Configure custom 指示器](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)。</span><span class="sxs-lookup"><span data-stu-id="086d3-123">For support of indicators on iOS, see [Configure custom indicators](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="086d3-124">只有外部 Ip 可以新增至 [標記] 清單。</span><span class="sxs-lookup"><span data-stu-id="086d3-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="086d3-125">無法為內部 Ip 建立指示器。</span><span class="sxs-lookup"><span data-stu-id="086d3-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="086d3-126">在 web 保護案例中，建議您在 Microsoft Edge 中使用內建功能。</span><span class="sxs-lookup"><span data-stu-id="086d3-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="086d3-127">Microsoft Edge 會利用[網路保護](network-protection.md)檢查網路流量，並允許 TCP、HTTP 及 HTTPS (TLS) 的封鎖。</span><span class="sxs-lookup"><span data-stu-id="086d3-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="086d3-128">如果有衝突的 URL 指示器原則，則會套用較長的路徑。</span><span class="sxs-lookup"><span data-stu-id="086d3-128">If there are conflicting URL indicator policies, the longer path is applied.</span></span> <span data-ttu-id="086d3-129">例如，URL 指示器原則的 `https:\\support.microsoft.com/en-us/office` 優先順序會高於 url 指示器原則 `https:\\support.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="086d3-129">For example, the URL indicator policy `https:\\support.microsoft.com/en-us/office` takes precedence over the URL indicator policy `https:\\support.microsoft.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="086d3-130">對於所有其他程式，web 保護案例會利用網路保護進行檢查及強制執行：</span><span class="sxs-lookup"><span data-stu-id="086d3-130">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> 
> - <span data-ttu-id="086d3-131">所有三種通訊協定都支援 IP</span><span class="sxs-lookup"><span data-stu-id="086d3-131">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="086d3-132"> (沒有 CIDR 區塊或 IP 範圍，只支援單一 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="086d3-132">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="086d3-133">已加密 URLs (完整路徑) 只能在第一方瀏覽器 (Internet Explorer，Edge) </span><span class="sxs-lookup"><span data-stu-id="086d3-133">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="086d3-134">加密的 URL (僅限 FQDN) 可以封鎖于第一方瀏覽器以外的地方 (Internet Explorer，Edge) </span><span class="sxs-lookup"><span data-stu-id="086d3-134">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="086d3-135">完整 URL 路徑區塊可以套用於網域層級和所有未加密的 URLs</span><span class="sxs-lookup"><span data-stu-id="086d3-135">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="086d3-136">最多可以有2小時的延遲 (會在採取動作的時間與要封鎖的 URL 和 IP 之間) 少。</span><span class="sxs-lookup"><span data-stu-id="086d3-136">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="086d3-137">從 [設定] 頁面建立 IPs、URLs 或網域的指示器</span><span class="sxs-lookup"><span data-stu-id="086d3-137">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="086d3-138">在功能窗格中，選取 [**設定**  >  **指示器**]。</span><span class="sxs-lookup"><span data-stu-id="086d3-138">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="086d3-139">選取 [ **IP 位址] 或 [URLs/網域** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="086d3-139">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="086d3-140">選取 [ **新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="086d3-140">Select **Add item**.</span></span>

4. <span data-ttu-id="086d3-141">指定下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="086d3-141">Specify the following details:</span></span>
   - <span data-ttu-id="086d3-142">標記-指定實體詳細資料並定義指示器的到期期限。</span><span class="sxs-lookup"><span data-stu-id="086d3-142">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="086d3-143">Action-指定要採取的動作並提供描述。</span><span class="sxs-lookup"><span data-stu-id="086d3-143">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="086d3-144">Scope-定義機器群組的範圍。</span><span class="sxs-lookup"><span data-stu-id="086d3-144">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="086d3-145">在 [摘要] 索引標籤中查看詳細資料，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="086d3-145">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="086d3-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="086d3-146">Related topics</span></span>
- [<span data-ttu-id="086d3-147">建立指示器</span><span class="sxs-lookup"><span data-stu-id="086d3-147">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="086d3-148">建立檔案的指示器</span><span class="sxs-lookup"><span data-stu-id="086d3-148">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="086d3-149">根據憑證建立指示器</span><span class="sxs-lookup"><span data-stu-id="086d3-149">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="086d3-150">管理指示器</span><span class="sxs-lookup"><span data-stu-id="086d3-150">Manage indicators</span></span>](indicator-manage.md)
