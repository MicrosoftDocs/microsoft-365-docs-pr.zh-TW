---
title: Microsoft Defender for Endpoint preview 功能
description: 瞭解如何存取 Microsoft Defender 以取得端點預覽功能。
keywords: 預覽、預覽經驗、Microsoft Defender for 端點、功能、更新
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6c77762de4dbd70922eb5623f801837bf6454ec7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842359"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="b3ccf-104">Microsoft Defender for Endpoint preview 功能</span><span class="sxs-lookup"><span data-stu-id="b3ccf-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="b3ccf-105">預覽版本不會提供任何服務等級協定，不建議用於實際執行工作負載。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="b3ccf-106">某些功能可能不受支援，或可能具有有限的功能。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="b3ccf-107">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b3ccf-107">**Applies to:**</span></span>
- [<span data-ttu-id="b3ccf-108">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b3ccf-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b3ccf-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3ccf-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b3ccf-110">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b3ccf-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b3ccf-111">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="b3ccf-112">Endpoint service 的 Defender 服務不斷更新，以包含新功能增強功能及功能。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="b3ccf-113">深入瞭解 Defender for Endpoint preview 發行版本中的新功能，並在第一次嘗試使用預覽體驗的情況中嘗試後續的功能。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-113">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="b3ccf-114">在更新此頁面時，請將下列 URL 複製並貼上至您的摘要讀取器以取得通知： `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="b3ccf-114">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="b3ccf-115">如需一般可用之新功能的詳細資訊，請參閱 [在 Defender 的最近更新中的端點](whats-new-in-microsoft-defender-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-115">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="b3ccf-116">開啟預覽功能</span><span class="sxs-lookup"><span data-stu-id="b3ccf-116">Turn on preview features</span></span>

<span data-ttu-id="b3ccf-117">您將可以存取即將推出的功能，您可以在其中提供意見反應，以協助改善整體體驗，使其成為一般可用功能。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-117">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="b3ccf-118">開啟預覽體驗設定，成為第一批嘗試即將推出的功能的人。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-118">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="b3ccf-119">在功能窗格中，選取 [**設定**  >  **高級功能**  >  **預覽功能**]。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-119">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="b3ccf-120">**在 [開啟**] 和 [**關閉**] 間切換設定，然後選取 [**儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-120">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="b3ccf-121">預覽功能</span><span class="sxs-lookup"><span data-stu-id="b3ccf-121">Preview features</span></span>

<span data-ttu-id="b3ccf-122">預覽版包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="b3ccf-122">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="b3ccf-123">裝置探索</span><span class="sxs-lookup"><span data-stu-id="b3ccf-123">Device discovery</span></span>](device-discovery.md) <br> <span data-ttu-id="b3ccf-124">協助您找出連接至公司網路的非管理裝置，不需要額外裝置或繁瑣的處理常式變更。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-124">Helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span> <span data-ttu-id="b3ccf-125">使用架裝置，您可以在網路中尋找未受管理的裝置，並評估漏洞和風險。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-125">Using onboarded devices, you can find unmanaged devices in your network and assess vulnerabilities and risks.</span></span> <span data-ttu-id="b3ccf-126">然後，您可以將已探索的裝置上架，以降低網路中具有非受管理端點的相關風險。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-126">You can then onboard discovered devices to reduce risks associated with having unmanaged endpoints in your network.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b3ccf-127">Standard discovery 會成為從2021年7月19日開始之所有客戶的預設模式。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-127">Standard discovery will be the default mode for all customers starting July 19, 2021.</span></span> <span data-ttu-id="b3ccf-128">您可以選擇透過 [設定] 頁面保留基本模式。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-128">You can choose to retain the basic mode through the settings page.</span></span> 


- [<span data-ttu-id="b3ccf-129">Web 內容篩選</span><span class="sxs-lookup"><span data-stu-id="b3ccf-129">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="b3ccf-130">Web 內容篩選是 Microsoft Defender for Endpoint 中的 web 保護功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-130">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b3ccf-131">它可讓您的組織根據其內容類別別來追蹤和控制網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-131">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="b3ccf-132">許多這類網站雖然並非惡意，但因相容性法規、頻寬使用量或其他考慮而可能會造成問題。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-132">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="b3ccf-133">裝置健康情況和符合性報告</span><span class="sxs-lookup"><span data-stu-id="b3ccf-133">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="b3ccf-134">裝置健康情況和合規性報告可提供組織中裝置的高層級資訊。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-134">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="b3ccf-135">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b3ccf-135">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b3ccf-136">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b3ccf-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
