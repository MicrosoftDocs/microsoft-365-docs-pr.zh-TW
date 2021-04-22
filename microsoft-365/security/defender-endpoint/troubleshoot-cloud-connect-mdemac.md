---
title: 疑難排解 macOS 上的 Microsoft Defender for Endpoint 的 cloud connectivity 問題
description: 本主題說明如何針對 macOS 上的 Microsoft Defender for Endpoint 進行 cloud connectivity 問題疑難排解
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，安裝，部署，卸載，intune，jamf，macos，catalina，mojave，高塞拉里昂
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 291cd3016dcb4e1a321f39b4d2731ce2068b6544
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935206"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="cfc9e-104">疑難排解 macOS 上的 Microsoft Defender for Endpoint 的 cloud connectivity 問題</span><span class="sxs-lookup"><span data-stu-id="cfc9e-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cfc9e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="cfc9e-105">**Applies to:**</span></span>
- [<span data-ttu-id="cfc9e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cfc9e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cfc9e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cfc9e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="cfc9e-108">**平臺** macOS</span><span class="sxs-lookup"><span data-stu-id="cfc9e-108">**Platform** macOS</span></span>

<span data-ttu-id="cfc9e-109">本主題說明如何針對 macOS 中的 Microsoft Defender for Endpoint 進行 cloud connectivity 問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-109">This topic describes how to Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="run-the-connectivity-test"></a><span data-ttu-id="cfc9e-110">執行連線測試</span><span class="sxs-lookup"><span data-stu-id="cfc9e-110">Run the connectivity test</span></span>
<span data-ttu-id="cfc9e-111">若要測試 Mac 上的 Endpoint for Endpoint 是否可以使用目前的網路設定與雲端通訊，請從命令列執行連線測試：</span><span class="sxs-lookup"><span data-stu-id="cfc9e-111">To test if Defender for Endpoint on Mac can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```Bash
mdatp connectivity test
```

<span data-ttu-id="cfc9e-112">期望的輸出：</span><span class="sxs-lookup"><span data-stu-id="cfc9e-112">expected output:</span></span>
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

<span data-ttu-id="cfc9e-113">如果連線測試失敗，請檢查裝置是否有網際網路存取權，以及是否有 [任何產品需要的端點](microsoft-defender-endpoint-mac.md#network-connections) ，以供 proxy 或防火牆封鎖。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-mac.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="cfc9e-114">失敗，包含彎曲錯誤35或60指出憑證鎖定拒絕，這表示 SSL 或 HTTPS 檢查的潛在問題。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-114">Failures with curl error 35 or 60 indicate certificate pinning rejection, which indicates a potential issue with SSL or HTTPS inspection.</span></span> <span data-ttu-id="cfc9e-115">請參閱下列有關 SSL 檢查設定的指示。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-115">See instructions below regarding SSL inspection configuration.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a><span data-ttu-id="cfc9e-116">在沒有 proxy 或 Proxy 自動設定 (PAC) 或使用 Web Proxy 自動探索通訊協定 (WPAD) 的情況下疑難排解步驟</span><span class="sxs-lookup"><span data-stu-id="cfc9e-116">Troubleshooting steps for environments without proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD)</span></span>
<span data-ttu-id="cfc9e-117">請使用下列程式來測試：在沒有 proxy 或 Proxy 自動 (PAC) 或使用 Web Proxy 自動探索通訊協定 (WPAD) 的環境中，未封鎖連線。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-117">Use the following procedure to test that a connection is not blocked in an environment without a proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD).</span></span>

<span data-ttu-id="cfc9e-118">如果 proxy 或防火牆封鎖匿名流量，請確定先前所列的 URLs 允許匿名流量。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-118">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="cfc9e-119">不支援已驗證的 proxy。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-119">Authenticated proxies are not supported.</span></span> <span data-ttu-id="cfc9e-120">確定只使用 PAC、WPAD 或靜態 proxy。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-120">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span> <span data-ttu-id="cfc9e-121">出於安全性原因，也不支援 SSL 檢查和截取 proxy。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-121">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="cfc9e-122">設定 SSL 檢查和 proxy 伺服器的例外狀況，以直接透過 Microsoft Defender for Endpoint for Endpoint URLs to to to to to to to to macOS，而不需要截獲。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-122">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="cfc9e-123">將您的截取憑證新增至全域存放區將不允許截取。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-123">Adding your interception certificate to the global store will not allow for interception.</span></span>
<span data-ttu-id="cfc9e-124">若要測試是否未封鎖連線：在 Microsoft Edge for Mac 或 Safari 開啟和中的瀏覽器 https://x.cp.wd.microsoft.com/api/report 中 https://cdn.x.cp.wd.microsoft.com/ping 。</span><span class="sxs-lookup"><span data-stu-id="cfc9e-124">To test that a connection is not blocked: In a browser such as Microsoft Edge for Mac or Safari open https://x.cp.wd.microsoft.com/api/report and https://cdn.x.cp.wd.microsoft.com/ping.</span></span>

<span data-ttu-id="cfc9e-125">（選用）在 [終端] 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cfc9e-125">Optionally, in Terminal, run the following command:</span></span>

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

<span data-ttu-id="cfc9e-126">此命令的輸出應類似下列所示：</span><span class="sxs-lookup"><span data-stu-id="cfc9e-126">The output from this command should be similar to:</span></span>
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
