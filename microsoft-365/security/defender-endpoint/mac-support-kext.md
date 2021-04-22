---
title: 疑難排解 macOS 中的 Microsoft Defender for Endpoint 的內核擴充問題
description: 疑難排解 macOS 中的 Microsoft Defender for Endpoint 中的內核擴充相關問題。
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，內核，分機
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
ms.openlocfilehash: 9dc3ee17d79972b5d36c5fff58fbe4cc486027bd
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934270"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="a05fd-104">疑難排解 macOS 中的 Microsoft Defender for Endpoint 的內核擴充問題</span><span class="sxs-lookup"><span data-stu-id="a05fd-104">Troubleshoot kernel extension issues in Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a05fd-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a05fd-105">**Applies to:**</span></span>

- [<span data-ttu-id="a05fd-106">macOS 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a05fd-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="a05fd-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a05fd-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a05fd-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a05fd-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a05fd-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="a05fd-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a05fd-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a05fd-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a05fd-111">本文提供如何疑難排解在 macOS 的 Microsoft Defender for Endpoint 中安裝之核心擴充問題的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a05fd-111">This article provides information on how to troubleshoot issues with the kernel extension that is installed as part of Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="a05fd-112">從 macOS 高的塞拉里昂 (10.13) 開始，macOS 需要明確核准所有內核擴充，才能允許在裝置上執行。</span><span class="sxs-lookup"><span data-stu-id="a05fd-112">Starting with macOS High Sierra (10.13), macOS requires all kernel extensions to be explicitly approved before they're allowed to run on the device.</span></span>

<span data-ttu-id="a05fd-113">如果您未在 macOS 上部署/安裝 Microsoft Defender for Endpoint 時核准核心擴充，應用程式會顯示橫幅，提示您加以啟用：</span><span class="sxs-lookup"><span data-stu-id="a05fd-113">If you didn't approve the kernel extension during the deployment/installation of Microsoft Defender for Endpoint on macOS, the application displays a banner prompting you to enable it:</span></span>

   ![RTP 停用的螢幕擷取畫面](images/mdatp-32-main-app-fix.png)

<span data-ttu-id="a05fd-115">您也可以執行 ```mdatp health``` 。</span><span class="sxs-lookup"><span data-stu-id="a05fd-115">You can also run ```mdatp health```.</span></span> <span data-ttu-id="a05fd-116">它會報告是否已啟用即時保護，但無法使用。</span><span class="sxs-lookup"><span data-stu-id="a05fd-116">It reports if real-time protection is enabled but not available.</span></span> <span data-ttu-id="a05fd-117">這表示未核准在您的裝置上執行內核擴充。</span><span class="sxs-lookup"><span data-stu-id="a05fd-117">This indicates that the kernel extension isn't approved to run on your device.</span></span>

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

<span data-ttu-id="a05fd-118">下列各節提供如何解決此問題的指引，取決於您用來在 macOS 上部署 Microsoft Defender for Endpoint 的方法。</span><span class="sxs-lookup"><span data-stu-id="a05fd-118">The following sections provide guidance on how to address this issue, depending on the method that you used to deploy Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="managed-deployment"></a><span data-ttu-id="a05fd-119">受管理的部署</span><span class="sxs-lookup"><span data-stu-id="a05fd-119">Managed deployment</span></span>

<span data-ttu-id="a05fd-120">請參閱您用來部署產品的管理工具對應的指示：</span><span class="sxs-lookup"><span data-stu-id="a05fd-120">See the instructions corresponding to the management tool that you used to deploy the product:</span></span>

- [<span data-ttu-id="a05fd-121">以 JAMF 為基礎的部署</span><span class="sxs-lookup"><span data-stu-id="a05fd-121">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
- [<span data-ttu-id="a05fd-122">Microsoft Intune 型部署</span><span class="sxs-lookup"><span data-stu-id="a05fd-122">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a><span data-ttu-id="a05fd-123">手動部署</span><span class="sxs-lookup"><span data-stu-id="a05fd-123">Manual deployment</span></span>

<span data-ttu-id="a05fd-124">若自產品安裝後超過30分鐘，請流覽至 [**系統偏好** 設定  >  **安全性] & 隱私權**，您必須從開發人員「Microsoft Corporation」**允許** 系統軟體。</span><span class="sxs-lookup"><span data-stu-id="a05fd-124">If less than 30 minutes have passed since the product was installed, navigate to **System Preferences** > **Security & Privacy**, where you have to **Allow** system software from developers "Microsoft Corporation".</span></span>

<span data-ttu-id="a05fd-125">如果您未看到此提示，表示已超過30分鐘或更多分鐘，且尚未核准內核擴充，無法在您的裝置上執行：</span><span class="sxs-lookup"><span data-stu-id="a05fd-125">If you don't see this prompt, it means that 30 or more minutes have passed, and the kernel extension still not been approved to run on your device:</span></span>

![提示到期的螢幕擷取畫面之後的安全性和隱私權視窗](images/mdatp-33-securityprivacysettings-noprompt.png)

<span data-ttu-id="a05fd-127">在此情況下，您必須執行下列步驟，以再次觸發核准流程。</span><span class="sxs-lookup"><span data-stu-id="a05fd-127">In this case, you need to perform the following steps to trigger the approval flow again.</span></span>

1. <span data-ttu-id="a05fd-128">在終端中，嘗試安裝驅動程式。</span><span class="sxs-lookup"><span data-stu-id="a05fd-128">In Terminal, attempt to install the driver.</span></span> <span data-ttu-id="a05fd-129">下列作業將會失敗，因為未核准在裝置上執行內核擴充。</span><span class="sxs-lookup"><span data-stu-id="a05fd-129">The following operation will fail, because the kernel extension wasn't approved to run on the device.</span></span> <span data-ttu-id="a05fd-130">不過，它會再次觸發核准流程。</span><span class="sxs-lookup"><span data-stu-id="a05fd-130">However, it will trigger the approval flow again.</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. <span data-ttu-id="a05fd-131">從功能表開啟 **系統偏好** 設定  >  **安全性 & 隱私權**。</span><span class="sxs-lookup"><span data-stu-id="a05fd-131">Open **System Preferences** > **Security & Privacy** from the menu.</span></span> <span data-ttu-id="a05fd-132"> (先關閉它（如果已開啟）。 ) </span><span class="sxs-lookup"><span data-stu-id="a05fd-132">(Close it first, if it's opened.)</span></span>

3. <span data-ttu-id="a05fd-133">**允許** 開發人員「Microsoft Corporation」的系統軟體</span><span class="sxs-lookup"><span data-stu-id="a05fd-133">**Allow** system software from developers "Microsoft Corporation"</span></span>

4. <span data-ttu-id="a05fd-134">在 [終端] 中重新安裝驅動程式。</span><span class="sxs-lookup"><span data-stu-id="a05fd-134">In Terminal, install the driver again.</span></span> <span data-ttu-id="a05fd-135">這次作業會成功：</span><span class="sxs-lookup"><span data-stu-id="a05fd-135">This time the operation will succeed:</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    <span data-ttu-id="a05fd-136">橫幅應該會從 Defender 應用程式中消失， ```mdatp health``` 現在應報告即時保護已啟用且可供使用：</span><span class="sxs-lookup"><span data-stu-id="a05fd-136">The banner should disappear from the Defender application, and ```mdatp health``` should now report that real-time protection is both enabled and available:</span></span>

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
