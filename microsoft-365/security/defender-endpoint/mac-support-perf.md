---
title: 疑難排解 Microsoft Defender for Mac 的性能問題
description: 疑難排解 Microsoft Defender for Mac 中的效能問題。
keywords: microsoft、defender、atp、mac、效能
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
ms.openlocfilehash: 87190d9e0bb62d42642374bd7c9f6f3acad3c80a
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379380"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="6456b-104">疑難排解 Microsoft Defender for Mac 的性能問題</span><span class="sxs-lookup"><span data-stu-id="6456b-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6456b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="6456b-105">**Applies to:**</span></span>

- [<span data-ttu-id="6456b-106">Mac 版適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6456b-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="6456b-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6456b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6456b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6456b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6456b-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6456b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6456b-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="6456b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6456b-111">本主題提供一些一般步驟，可用來縮小 Microsoft Defender for Mac 之相關的效能問題。</span><span class="sxs-lookup"><span data-stu-id="6456b-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="6456b-112">即時保護 (RTP) 是適用于 Mac 的 Microsoft Defender 端點的功能，可持續監視和保護您的裝置免受威脅。</span><span class="sxs-lookup"><span data-stu-id="6456b-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="6456b-113">它包含檔案和程式監視及其他試探法。</span><span class="sxs-lookup"><span data-stu-id="6456b-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="6456b-114">視您執行的應用程式和裝置特性而定，當您執行 Microsoft Defender for Mac 時，可能會遇到效能效能。</span><span class="sxs-lookup"><span data-stu-id="6456b-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="6456b-115">特別是，透過簡短的 timespan 存取許多資源的應用程式或系統進程，可能會導致 Microsoft Defender for Mac 中的效能問題。</span><span class="sxs-lookup"><span data-stu-id="6456b-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="6456b-116">下列步驟可用於疑難排解及緩解下列問題：</span><span class="sxs-lookup"><span data-stu-id="6456b-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="6456b-117">使用下列其中一種方法來停用即時保護，並觀察效能是否提高。</span><span class="sxs-lookup"><span data-stu-id="6456b-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="6456b-118">這種方法可協助縮小 Microsoft Defender for Mac 是否對效能問題造成的影響。</span><span class="sxs-lookup"><span data-stu-id="6456b-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

    <span data-ttu-id="6456b-119">如果您的裝置不是由您的組織管理，則可以使用下列其中一個選項停用即時保護：</span><span class="sxs-lookup"><span data-stu-id="6456b-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="6456b-120">從使用者介面。</span><span class="sxs-lookup"><span data-stu-id="6456b-120">From the user interface.</span></span> <span data-ttu-id="6456b-121">開啟 Mac 版的 Microsoft Defender 端點，並流覽至 [ **管理設定**]。</span><span class="sxs-lookup"><span data-stu-id="6456b-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![管理即時保護螢幕擷取畫面](images/mdatp-36-rtp.png)

    - <span data-ttu-id="6456b-123">從終端。</span><span class="sxs-lookup"><span data-stu-id="6456b-123">From the Terminal.</span></span> <span data-ttu-id="6456b-124">基於安全性的考慮，此作業需要提升。</span><span class="sxs-lookup"><span data-stu-id="6456b-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    <span data-ttu-id="6456b-125">如果您的裝置是由您的組織管理，您的系統管理員可以使用 [Microsoft Defender For Mac 的設定偏好設定](mac-preferences.md)中的指示，停用即時保護。</span><span class="sxs-lookup"><span data-stu-id="6456b-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

2. <span data-ttu-id="6456b-126">開啟 Finder，並流覽至 **應用程式**  >  **公用程式**。</span><span class="sxs-lookup"><span data-stu-id="6456b-126">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="6456b-127">開啟 **活動監視器** 並分析哪些應用程式正在使用您系統上的資源。</span><span class="sxs-lookup"><span data-stu-id="6456b-127">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="6456b-128">典型範例包括軟體 updaters 及編譯器。</span><span class="sxs-lookup"><span data-stu-id="6456b-128">Typical examples include software updaters and compilers.</span></span>

3. <span data-ttu-id="6456b-129">針對影響效能問題及重新啟用即時保護的處理常式或磁片位置，針對 Mac 設定 Microsoft Defender for Mac 的排除專案。</span><span class="sxs-lookup"><span data-stu-id="6456b-129">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="6456b-130">如需詳細資訊，請參閱 [設定及驗證 Microsoft Defender For Mac 的排除](mac-exclusions.md) 專案。</span><span class="sxs-lookup"><span data-stu-id="6456b-130">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
