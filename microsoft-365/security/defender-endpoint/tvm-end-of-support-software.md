---
title: 規劃支援終止的軟體和軟體版本
description: 探索並規劃不再支援的軟體和軟體版本，而且不會收到安全性更新。
keywords: 威脅和弱點管理，Microsoft Defender for Endpoint tvm security 建議，cybersecurity 建議，可操作的安全性建議
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
ms.openlocfilehash: 8e8fc228b8856df03b580e748bf00efc8d4333c3
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934126"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="91fcb-104">使用威脅和弱點管理，規劃支援終止軟體和軟體版本</span><span class="sxs-lookup"><span data-stu-id="91fcb-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="91fcb-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="91fcb-105">**Applies to:**</span></span>

- [<span data-ttu-id="91fcb-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="91fcb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="91fcb-107">威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="91fcb-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="91fcb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91fcb-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="91fcb-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="91fcb-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="91fcb-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="91fcb-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="91fcb-111">支援終止的 (EOS) （也稱為生命週期結束 (EOL) ）軟體或軟體版本表示其不再支援或服務，且不會收到安全性更新。</span><span class="sxs-lookup"><span data-stu-id="91fcb-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="91fcb-112">當您使用已結束支援的軟體或軟體版本時，您會公開組織面臨安全性弱點、法律和財務風險。</span><span class="sxs-lookup"><span data-stu-id="91fcb-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="91fcb-113">重要的是要讓安全性和 IT 系統管理員共同運作，並確定組織的軟體清查已設定為取得最佳結果、規範，以及狀況良好的網路生態系統。</span><span class="sxs-lookup"><span data-stu-id="91fcb-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="91fcb-114">他們應該檢查選項，以移除或取代已到達支援終止的應用程式，以及已不再支援之更新版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="91fcb-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="91fcb-115">在支援日期結束之前，最好 **先** 建立及實施方案。</span><span class="sxs-lookup"><span data-stu-id="91fcb-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="91fcb-116">尋找已不再支援的軟體或軟體版本</span><span class="sxs-lookup"><span data-stu-id="91fcb-116">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="91fcb-117">從 [威脅和弱點管理] 功能表中，流覽至 [ [**安全性建議**](tvm-security-recommendation.md)]。</span><span class="sxs-lookup"><span data-stu-id="91fcb-117">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="91fcb-118">移至 [ **篩選** ] 面板，然後尋找 [標記] 區段。</span><span class="sxs-lookup"><span data-stu-id="91fcb-118">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="91fcb-119">選取一個或多個 EOS 標記選項。</span><span class="sxs-lookup"><span data-stu-id="91fcb-119">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="91fcb-120">然後 **套用**。</span><span class="sxs-lookup"><span data-stu-id="91fcb-120">Then **Apply**.</span></span>

    ![顯示 EOS 軟體、EOS 版本及近期 EOS 版本的螢幕擷取畫面標記。](images/tvm-eos-tag.png)

3. <span data-ttu-id="91fcb-122">您將會看到軟體的相關建議清單，其中包含結束支援、軟體版本（支援終止），或有即將推出的支援終止版本。</span><span class="sxs-lookup"><span data-stu-id="91fcb-122">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="91fcb-123">這些標記也會顯示在 [ [軟體清查](tvm-software-inventory.md) ] 頁面中。</span><span class="sxs-lookup"><span data-stu-id="91fcb-123">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![EOS 標記的建議。](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="91fcb-125">版本清單及日期</span><span class="sxs-lookup"><span data-stu-id="91fcb-125">List of versions and dates</span></span>

<span data-ttu-id="91fcb-126">若要查看已到達支援終止的版本清單，或不久的 [結束] 或 [支援]，以及這些日期，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="91fcb-126">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="91fcb-127">在已到達支援終止版本的軟體的安全性建議浮出性中，會顯示一則訊息，否則即將提供支援終止。</span><span class="sxs-lookup"><span data-stu-id="91fcb-127">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![版本發佈連結的螢幕擷取畫面。](images/eos-upcoming-eos.png)

2. <span data-ttu-id="91fcb-129">選取 [ **版本發行** 連結]，以移至軟體深入查看頁面。</span><span class="sxs-lookup"><span data-stu-id="91fcb-129">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="91fcb-130">在此，您可以看見篩選過的版本清單，並將標記識別為終止支援或即將推出的支援結束。</span><span class="sxs-lookup"><span data-stu-id="91fcb-130">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![支援軟體的軟體深入分析頁面的螢幕擷取畫面。](images/software-drilldown-eos.png)

3. <span data-ttu-id="91fcb-132">選取表格中要開啟的其中一個版本。</span><span class="sxs-lookup"><span data-stu-id="91fcb-132">Select one of the versions in the table to open.</span></span> <span data-ttu-id="91fcb-133">例如，版本10.0.18362.1。</span><span class="sxs-lookup"><span data-stu-id="91fcb-133">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="91fcb-134">浮出的浮出狀態會出現在 [支援日期結束]。</span><span class="sxs-lookup"><span data-stu-id="91fcb-134">A flyout will appear with the end of support date.</span></span>

    ![支援日期結束的螢幕擷取畫面。](images/version-eos-date.png)

<span data-ttu-id="91fcb-136">一旦您識別出受支援終止的軟體和軟體版本，您必須決定是否要從組織更新或移除。</span><span class="sxs-lookup"><span data-stu-id="91fcb-136">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="91fcb-137">這樣做會降低組織面臨的漏洞和高級持續威脅。</span><span class="sxs-lookup"><span data-stu-id="91fcb-137">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="91fcb-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="91fcb-138">Related topics</span></span>

- [<span data-ttu-id="91fcb-139">威脅和弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="91fcb-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="91fcb-140">安全性建議</span><span class="sxs-lookup"><span data-stu-id="91fcb-140">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="91fcb-141">軟體庫存</span><span class="sxs-lookup"><span data-stu-id="91fcb-141">Software inventory</span></span>](tvm-software-inventory.md)
