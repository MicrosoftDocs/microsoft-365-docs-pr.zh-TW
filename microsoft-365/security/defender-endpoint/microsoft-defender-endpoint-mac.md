---
title: Mac 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 瞭解如何在 Mac 上安裝、設定、更新及使用 Microsoft Defender for Endpoint。
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，安裝，deploy，卸載，intune，jamf，macos，big sur，catalina，mojave，mde for mac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b5af93e82f72bac900682b2e231453e448b267d9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934186"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="efaa1-104">Mac 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="efaa1-104">Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="efaa1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="efaa1-105">**Applies to:**</span></span>
- [<span data-ttu-id="efaa1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="efaa1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="efaa1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="efaa1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="efaa1-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="efaa1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="efaa1-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="efaa1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="efaa1-110">本主題說明如何在 Mac 上安裝、設定、更新和使用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="efaa1-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="efaa1-111">在 Mac 上執行其他協力廠商端點保護產品及 Microsoft Defender for Mac 時，可能會造成效能問題和不可預測的副作用。</span><span class="sxs-lookup"><span data-stu-id="efaa1-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="efaa1-112">若非 Microsoft endpoint protection 是您環境中的絕對需求，則在將防病毒功能設定為以 [被動式模式](mac-preferences.md#enable--disable-passive-mode)執行之前，您仍然可以安全地利用適用于 Mac EDR 功能的 Defender。</span><span class="sxs-lookup"><span data-stu-id="efaa1-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Mac EDR functionality after configuring the antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="efaa1-113">最新版本中的新功能</span><span class="sxs-lookup"><span data-stu-id="efaa1-113">What’s new in the latest release</span></span>

[<span data-ttu-id="efaa1-114">適用於端點的 Microsoft Defender 新功能</span><span class="sxs-lookup"><span data-stu-id="efaa1-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="efaa1-115">Mac 版端點的 Microsoft Defender 新增功能</span><span class="sxs-lookup"><span data-stu-id="efaa1-115">What's new in Microsoft Defender for Endpoint on Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="efaa1-116">如果您有任何您想要分享的意見反應，請在您的裝置上開啟 Microsoft Defender for Mac 上的端點，然後流覽以 **協助**  >  **傳送意見** 反應，以提交。</span><span class="sxs-lookup"><span data-stu-id="efaa1-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint on Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="efaa1-117">若要取得最新的功能，包括預覽功能 (例如 Mac 裝置的端點偵測和回應) ，請將執行 Microsoft Defender for Endpoint 的 macOS 裝置設定為「有問必答」裝置。</span><span class="sxs-lookup"><span data-stu-id="efaa1-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="efaa1-118">如何在 Mac 上為端點安裝 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="efaa1-118">How to install Microsoft Defender for Endpoint on Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="efaa1-119">必要條件</span><span class="sxs-lookup"><span data-stu-id="efaa1-119">Prerequisites</span></span>

- <span data-ttu-id="efaa1-120">用於端點訂閱和 Microsoft Defender Security Center 入口網站存取權的 Defender</span><span class="sxs-lookup"><span data-stu-id="efaa1-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="efaa1-121">macOS 和 BASH 腳本中的初級層級體驗</span><span class="sxs-lookup"><span data-stu-id="efaa1-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="efaa1-122">當手動部署時，裝置上的系統管理許可權 () </span><span class="sxs-lookup"><span data-stu-id="efaa1-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="efaa1-123">安裝指示</span><span class="sxs-lookup"><span data-stu-id="efaa1-123">Installation instructions</span></span>

<span data-ttu-id="efaa1-124">您可以使用數種方法和部署工具，在 Mac 上為端點安裝和設定 Defender。</span><span class="sxs-lookup"><span data-stu-id="efaa1-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint on Mac.</span></span>

- <span data-ttu-id="efaa1-125">協力廠商管理工具：</span><span class="sxs-lookup"><span data-stu-id="efaa1-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="efaa1-126">Microsoft Intune 型部署</span><span class="sxs-lookup"><span data-stu-id="efaa1-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="efaa1-127">以 JAMF 為基礎的部署</span><span class="sxs-lookup"><span data-stu-id="efaa1-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="efaa1-128">其他 MDM 產品</span><span class="sxs-lookup"><span data-stu-id="efaa1-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="efaa1-129">命令列工具：</span><span class="sxs-lookup"><span data-stu-id="efaa1-129">Command-line tool:</span></span>
    - [<span data-ttu-id="efaa1-130">手動部署</span><span class="sxs-lookup"><span data-stu-id="efaa1-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="efaa1-131">系統需求</span><span class="sxs-lookup"><span data-stu-id="efaa1-131">System requirements</span></span>

<span data-ttu-id="efaa1-132">這三個最新的 macOS 主要版本都支援。</span><span class="sxs-lookup"><span data-stu-id="efaa1-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efaa1-133">在 macOS 11 (Big Sur) 上，Microsoft Defender for Endpoint 需要其他設定設定檔。</span><span class="sxs-lookup"><span data-stu-id="efaa1-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="efaa1-134">如果您是現有的客戶從舊版的 macOS 升級，請務必在 [MacOS Catalina 及更新版本的 macOS](mac-sysext-policies.md)上部署所列于新設定設定檔的其他設定檔。</span><span class="sxs-lookup"><span data-stu-id="efaa1-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efaa1-135">MacOS 10.13 (高的塞拉里昂) 已于2021時終止。</span><span class="sxs-lookup"><span data-stu-id="efaa1-135">Support for macOS 10.13 (High Sierra) has been discontinued as of February 15th, 2021.</span></span>

- <span data-ttu-id="efaa1-136">11 (Big Sur) ，10.15 (Catalina) ，10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="efaa1-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span></span>
- <span data-ttu-id="efaa1-137">磁碟空間：1GB</span><span class="sxs-lookup"><span data-stu-id="efaa1-137">Disk space: 1GB</span></span>

<span data-ttu-id="efaa1-138">不支援 Beta 版本的 macOS。</span><span class="sxs-lookup"><span data-stu-id="efaa1-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="efaa1-139">不支援具有 M1 處理器的 macOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="efaa1-139">macOS devices with M1 processors are not supported.</span></span>

<span data-ttu-id="efaa1-140">在您啟用服務之後，您可能需要設定網路或防火牆，以允許它和您的端點之間的輸出連線。</span><span class="sxs-lookup"><span data-stu-id="efaa1-140">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="efaa1-141">授權需求</span><span class="sxs-lookup"><span data-stu-id="efaa1-141">Licensing requirements</span></span>

<span data-ttu-id="efaa1-142">Mac 版上的 microsoft Defender Endpoint 需要下列其中一項 Microsoft 大量授權：</span><span class="sxs-lookup"><span data-stu-id="efaa1-142">Microsoft Defender for Endpoint on Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="efaa1-143">Microsoft 365 E5 (M365 E5) </span><span class="sxs-lookup"><span data-stu-id="efaa1-143">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="efaa1-144">Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="efaa1-144">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="efaa1-145">Microsoft 365 A5 (M365 A5) </span><span class="sxs-lookup"><span data-stu-id="efaa1-145">Microsoft 365 A5 (M365 A5)</span></span>

> [!NOTE]
> <span data-ttu-id="efaa1-146">合格授權的使用者最多可在最多五個並行裝置上使用 Microsoft Defender 端點。</span><span class="sxs-lookup"><span data-stu-id="efaa1-146">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="efaa1-147">Microsoft Defender for Endpoint 也可從雲端解決方案供應商購買 (CSP) 。</span><span class="sxs-lookup"><span data-stu-id="efaa1-147">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="efaa1-148">透過 CSP 購買時，不需要列出 Microsoft 大量授權提供者。</span><span class="sxs-lookup"><span data-stu-id="efaa1-148">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="efaa1-149">網路連線</span><span class="sxs-lookup"><span data-stu-id="efaa1-149">Network connections</span></span>

<span data-ttu-id="efaa1-150">下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。</span><span class="sxs-lookup"><span data-stu-id="efaa1-150">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="efaa1-151">您應確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取，否則您可能需要為他們建立一個 *允許* 規則。</span><span class="sxs-lookup"><span data-stu-id="efaa1-151">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="efaa1-152">**網域清單的試算表**</span><span class="sxs-lookup"><span data-stu-id="efaa1-152">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="efaa1-153">**描述**</span><span class="sxs-lookup"><span data-stu-id="efaa1-153">**Description**</span></span>|
|:-----|:-----|
|![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/>  | <span data-ttu-id="efaa1-155">服務位置、地理位置和作業系統的特定 DNS 記錄試算表。</span><span class="sxs-lookup"><span data-stu-id="efaa1-155">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="efaa1-156">在這裡下載試算表： [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="efaa1-156">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="efaa1-157">Microsoft Defender for Endpoint 可使用下列探索方法探索 proxy 伺服器：</span><span class="sxs-lookup"><span data-stu-id="efaa1-157">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="efaa1-158">Proxy 自動設定 (PAC) </span><span class="sxs-lookup"><span data-stu-id="efaa1-158">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="efaa1-159">Web Proxy 自動探索通訊協定 (WPAD) </span><span class="sxs-lookup"><span data-stu-id="efaa1-159">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="efaa1-160">手動靜態 proxy 設定</span><span class="sxs-lookup"><span data-stu-id="efaa1-160">Manual static proxy configuration</span></span>

<span data-ttu-id="efaa1-161">如果 proxy 或防火牆封鎖匿名流量，請確定先前所列的 URLs 允許匿名流量。</span><span class="sxs-lookup"><span data-stu-id="efaa1-161">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="efaa1-162">不支援已驗證的 proxy。</span><span class="sxs-lookup"><span data-stu-id="efaa1-162">Authenticated proxies are not supported.</span></span> <span data-ttu-id="efaa1-163">確定只使用 PAC、WPAD 或靜態 proxy。</span><span class="sxs-lookup"><span data-stu-id="efaa1-163">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="efaa1-164">出於安全性原因，也不支援 SSL 檢查和截取 proxy。</span><span class="sxs-lookup"><span data-stu-id="efaa1-164">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="efaa1-165">設定 SSL 檢查和 proxy 伺服器的例外狀況，以直接透過 Microsoft Defender for Endpoint for Endpoint URLs to to to to to to to to macOS，而不需要截獲。</span><span class="sxs-lookup"><span data-stu-id="efaa1-165">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="efaa1-166">將您的截取憑證新增至全域存放區將不允許截取。</span><span class="sxs-lookup"><span data-stu-id="efaa1-166">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="efaa1-167">若要測試連接未封鎖，請 [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) 在瀏覽器中開啟和。</span><span class="sxs-lookup"><span data-stu-id="efaa1-167">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="efaa1-168">如果您傾向使用命令列，您也可以在終端中執行下列命令，以檢查連線：</span><span class="sxs-lookup"><span data-stu-id="efaa1-168">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="efaa1-169">此命令的輸出應類似下列所示：</span><span class="sxs-lookup"><span data-stu-id="efaa1-169">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="efaa1-170">建議您在用戶端裝置上啟用 [系統完整性保護](https://support.apple.com/en-us/HT204899) (SIP) 。</span><span class="sxs-lookup"><span data-stu-id="efaa1-170">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="efaa1-171">SIP 是內建的 macOS 安全性功能，可防止對作業系統的低層級篡改，且預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="efaa1-171">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="efaa1-172">安裝 Microsoft Defender for Endpoint 後，可在 Terminal 中執行下列命令來驗證連線：</span><span class="sxs-lookup"><span data-stu-id="efaa1-172">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="efaa1-173">如何在 Mac 上更新 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="efaa1-173">How to update Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="efaa1-174">Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。</span><span class="sxs-lookup"><span data-stu-id="efaa1-174">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="efaa1-175">若要在 Mac 上更新 Microsoft Defender for Endpoint，使用名為 Microsoft AutoUpdate (MAU) 的程式。</span><span class="sxs-lookup"><span data-stu-id="efaa1-175">To update Microsoft Defender for Endpoint on Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="efaa1-176">若要深入瞭解，請參閱 [在 Mac 上部署 Microsoft Defender For Endpoint 的更新](mac-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="efaa1-176">To learn more, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="efaa1-177">如何在 Mac 上為端點設定 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="efaa1-177">How to configure Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="efaa1-178">有關如何在企業環境中設定產品的指引，可于 [Mac 上的 Microsoft Defender For Endpoint 的 [設定偏好設定](mac-preferences.md)] 中取得。</span><span class="sxs-lookup"><span data-stu-id="efaa1-178">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="efaa1-179">macOS 內核和系統擴充</span><span class="sxs-lookup"><span data-stu-id="efaa1-179">macOS kernel and system extensions</span></span>

<span data-ttu-id="efaa1-180">在與 macOS 演變對齊時，我們正在準備使用系統擴充（而非核心擴充）的 Microsoft Defender for Mac 更新的端點。</span><span class="sxs-lookup"><span data-stu-id="efaa1-180">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="efaa1-181">如需相關詳細資料，請參閱 Mac 版的 [Microsoft Defender For Endpoint 中的新功能](mac-whatsnew.md)。</span><span class="sxs-lookup"><span data-stu-id="efaa1-181">For relevant details, see [What's new in Microsoft Defender for Endpoint on Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="efaa1-182">資源</span><span class="sxs-lookup"><span data-stu-id="efaa1-182">Resources</span></span>

- <span data-ttu-id="efaa1-183">如需有關記錄、卸載或其他主題的詳細資訊，請參閱 [Mac 上 Microsoft Defender For Endpoint 的資源](mac-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="efaa1-183">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint on Mac](mac-resources.md).</span></span>

- <span data-ttu-id="efaa1-184">[Mac 上的 Microsoft Defender For Endpoint 的隱私權](mac-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="efaa1-184">[Privacy for Microsoft Defender for Endpoint on Mac](mac-privacy.md).</span></span>
