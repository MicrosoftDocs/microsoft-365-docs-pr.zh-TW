---
title: 針對 Linux 上的 Microsoft Defender for Endpoint 進行 cloud connectivity 問題的疑難排解
ms.reviewer: ''
description: 針對 Linux 上的 Microsoft Defender for Endpoint 進行 cloud connectivity 問題的疑難排解
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，cloud，connectivity，通訊
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0345d7f88d147abb750e66a5e61f516abf38d553
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933106"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="8a29c-104">針對 Linux 上的 Microsoft Defender for Endpoint 進行 cloud connectivity 問題的疑難排解</span><span class="sxs-lookup"><span data-stu-id="8a29c-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8a29c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8a29c-105">**Applies to:**</span></span>
- [<span data-ttu-id="8a29c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8a29c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8a29c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a29c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8a29c-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8a29c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8a29c-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="8a29c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a><span data-ttu-id="8a29c-110">執行連線測試</span><span class="sxs-lookup"><span data-stu-id="8a29c-110">Run the connectivity test</span></span>

<span data-ttu-id="8a29c-111">若要測試 Linux 上的 Endpoint for Endpoint 是否可以使用目前的網路設定與雲端通訊，請從命令列執行連線測試：</span><span class="sxs-lookup"><span data-stu-id="8a29c-111">To test if Defender for Endpoint on Linux can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="8a29c-112">期望的輸出：</span><span class="sxs-lookup"><span data-stu-id="8a29c-112">expected output:</span></span>

```output
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

<span data-ttu-id="8a29c-113">如果連線測試失敗，請檢查裝置是否有網際網路存取權，以及是否有 [任何產品需要的端點](microsoft-defender-endpoint-linux.md#network-connections) ，以供 proxy 或防火牆封鎖。</span><span class="sxs-lookup"><span data-stu-id="8a29c-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-linux.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="8a29c-114">失敗的情況下，錯誤35或60，表示憑證鎖定拒絕。</span><span class="sxs-lookup"><span data-stu-id="8a29c-114">Failures with curl error 35 or 60, indicate certificate pinning rejection.</span></span> <span data-ttu-id="8a29c-115">請檢查連接是否低於 SSL 或 HTTPS 檢查。</span><span class="sxs-lookup"><span data-stu-id="8a29c-115">Please check if the connection is under SSL or HTTPS inspection.</span></span> <span data-ttu-id="8a29c-116">如果是，請將 Microsoft Defender for 端點新增至允許清單。</span><span class="sxs-lookup"><span data-stu-id="8a29c-116">If so, add Microsoft Defender for Endpoint to the allow list.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a><span data-ttu-id="8a29c-117">沒有 proxy 或透明 proxy 環境的疑難排解步驟</span><span class="sxs-lookup"><span data-stu-id="8a29c-117">Troubleshooting steps for environments without proxy or with transparent proxy</span></span>

<span data-ttu-id="8a29c-118">若要測試在沒有 proxy 或透明 proxy 的環境中，未封鎖連線，請在 terminal 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8a29c-118">To test that a connection is not blocked in an environment without a proxy or with a transparent proxy, run the following command in the terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="8a29c-119">此命令的輸出應類似下列所示：</span><span class="sxs-lookup"><span data-stu-id="8a29c-119">The output from this command should be similar to:</span></span>

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a><span data-ttu-id="8a29c-120">使用靜態 proxy 環境的疑難排解步驟</span><span class="sxs-lookup"><span data-stu-id="8a29c-120">Troubleshooting steps for environments with static proxy</span></span>

> [!WARNING]
> <span data-ttu-id="8a29c-121">不支援 PAC、WPAD 及已驗證的 proxy。</span><span class="sxs-lookup"><span data-stu-id="8a29c-121">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="8a29c-122">確定只使用靜態 proxy 或透明 proxy。</span><span class="sxs-lookup"><span data-stu-id="8a29c-122">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="8a29c-123">出於安全性原因，也不支援 SSL 檢查和截取 proxy。</span><span class="sxs-lookup"><span data-stu-id="8a29c-123">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="8a29c-124">設定 SSL 檢查和 proxy 伺服器的例外狀況，以直接將來自 Linux 之 Defender 的資料傳遞至相關的 URLs，而不需截獲。</span><span class="sxs-lookup"><span data-stu-id="8a29c-124">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="8a29c-125">將您的截取憑證新增至全域存放區將不允許截取。</span><span class="sxs-lookup"><span data-stu-id="8a29c-125">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="8a29c-126">若需要靜態 proxy，請將 proxy 參數新增至上述命令，其中會 `proxy_address:port` 對應至 proxy 位址及通訊埠：</span><span class="sxs-lookup"><span data-stu-id="8a29c-126">If a static proxy is required, add a proxy parameter to the above command, where `proxy_address:port` correspond to the proxy address and port:</span></span>

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="8a29c-127">確定您使用的是檔案中所設定的相同 proxy 位址及埠 `/lib/system/system/mdatp.service` 。</span><span class="sxs-lookup"><span data-stu-id="8a29c-127">Ensure that you use the same proxy address and port as configured in the `/lib/system/system/mdatp.service` file.</span></span> <span data-ttu-id="8a29c-128">如果上述命令有錯誤，請檢查您的 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="8a29c-128">Check your proxy configuration if there are errors from the above commands.</span></span>

> [!WARNING]
> <span data-ttu-id="8a29c-129">靜態 proxy 無法透過全系統 `HTTPS_PROXY` 環境變數進行設定。</span><span class="sxs-lookup"><span data-stu-id="8a29c-129">The static proxy cannot be configured through a system-wide `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="8a29c-130">相反地，請確定檔案 `HTTPS_PROXY` 中已正確設定 `/lib/system/system/mdatp.service` 。</span><span class="sxs-lookup"><span data-stu-id="8a29c-130">Instead, ensure that `HTTPS_PROXY` is properly set in the `/lib/system/system/mdatp.service` file.</span></span>

<span data-ttu-id="8a29c-131">若要使用靜態 proxy， `mdatp.service` 必須修改檔案。</span><span class="sxs-lookup"><span data-stu-id="8a29c-131">To use a static proxy, the `mdatp.service` file must be modified.</span></span> <span data-ttu-id="8a29c-132">確定 `#` 已移除前導，以取消注釋下行中的下列各項 `/lib/systemd/system/mdatp.service` ：</span><span class="sxs-lookup"><span data-stu-id="8a29c-132">Ensure the leading `#` is removed to uncomment the following line from `/lib/systemd/system/mdatp.service`:</span></span>

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

<span data-ttu-id="8a29c-133">此外，請確定已填入正確的靜態 proxy 位址進行取代 `address:port` 。</span><span class="sxs-lookup"><span data-stu-id="8a29c-133">Also ensure that the correct static proxy address is filled in to replace `address:port`.</span></span>

<span data-ttu-id="8a29c-134">如果此檔案是正確的，請嘗試在此終端中執行下列命令，在 Linux 上為端點重新載入 Defender，然後傳播設定：</span><span class="sxs-lookup"><span data-stu-id="8a29c-134">If this file is correct, try running the following command in the terminal to reload Defender for Endpoint on Linux and propagate the setting:</span></span>

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

<span data-ttu-id="8a29c-135">成功時，請從命令列嘗試另一個連線測試：</span><span class="sxs-lookup"><span data-stu-id="8a29c-135">Upon success, attempt another connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="8a29c-136">如果問題持續發生，請與客戶支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="8a29c-136">If the problem persists, contact customer support.</span></span>

## <a name="resources"></a><span data-ttu-id="8a29c-137">資源</span><span class="sxs-lookup"><span data-stu-id="8a29c-137">Resources</span></span>

- <span data-ttu-id="8a29c-138">如需如何將產品設定為使用靜態 proxy 的詳細資訊，請參閱 [Configure Microsoft Defender for a Endpoint for static proxy discovery](linux-static-proxy-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="8a29c-138">For more information about how to configure the product to use a static proxy, see [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span></span>
