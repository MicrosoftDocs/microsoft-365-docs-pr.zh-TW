---
title: Microsoft Defender ATP 預覽功能
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
ms.openlocfilehash: 4aab7f12b250c1415ad65a9e706edf6b68050b2f
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222646"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="015a1-104">Microsoft Defender for Endpoint preview 功能</span><span class="sxs-lookup"><span data-stu-id="015a1-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="015a1-105">預覽版本不會提供任何服務等級協定，不建議用於實際執行工作負載。</span><span class="sxs-lookup"><span data-stu-id="015a1-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="015a1-106">某些功能可能不受支援，或可能具有有限的功能。</span><span class="sxs-lookup"><span data-stu-id="015a1-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="015a1-107">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="015a1-107">**Applies to:**</span></span>
- [<span data-ttu-id="015a1-108">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="015a1-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="015a1-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="015a1-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="015a1-110">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="015a1-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="015a1-111">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="015a1-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="015a1-112">Endpoint service 的 Defender 服務不斷更新，以包含新功能增強功能及功能。</span><span class="sxs-lookup"><span data-stu-id="015a1-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="015a1-113">深入瞭解 Defender for Endpoint preview 發行版本中的新功能，並在第一次嘗試使用預覽體驗的情況中嘗試後續的功能。</span><span class="sxs-lookup"><span data-stu-id="015a1-113">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="015a1-114">在更新此頁面時，請將下列 URL 複製並貼上至您的摘要讀取器以取得通知： `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span><span class="sxs-lookup"><span data-stu-id="015a1-114">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span></span>

<span data-ttu-id="015a1-115">如需一般可用之新功能的詳細資訊，請參閱 [在 Defender 的最近更新中的端點](whats-new-in-microsoft-defender-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="015a1-115">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="015a1-116">開啟預覽功能</span><span class="sxs-lookup"><span data-stu-id="015a1-116">Turn on preview features</span></span>

<span data-ttu-id="015a1-117">您將可以存取即將推出的功能，您可以在其中提供意見反應，以協助改善整體體驗，使其成為一般可用功能。</span><span class="sxs-lookup"><span data-stu-id="015a1-117">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="015a1-118">開啟預覽體驗設定，成為第一批嘗試即將推出的功能的人。</span><span class="sxs-lookup"><span data-stu-id="015a1-118">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="015a1-119">在功能窗格中，選取 [**設定**] [  >  **高級功能**  >  **預覽功能**]。</span><span class="sxs-lookup"><span data-stu-id="015a1-119">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="015a1-120">**在 [開啟**] 和 [**關閉**] 間切換設定，然後選取 [**儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="015a1-120">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="015a1-121">預覽功能</span><span class="sxs-lookup"><span data-stu-id="015a1-121">Preview features</span></span>

<span data-ttu-id="015a1-122">預覽版包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="015a1-122">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="015a1-123">Web 內容篩選</span><span class="sxs-lookup"><span data-stu-id="015a1-123">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="015a1-124">Web 內容篩選是 Microsoft Defender for Endpoint 中的 web 保護功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="015a1-124">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="015a1-125">它可讓您的組織根據其內容類別別來追蹤和控制網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="015a1-125">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="015a1-126">許多這類網站雖然並非惡意，但因相容性法規、頻寬使用量或其他考慮而可能會造成問題。</span><span class="sxs-lookup"><span data-stu-id="015a1-126">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="015a1-127">裝置健康情況和符合性報告</span><span class="sxs-lookup"><span data-stu-id="015a1-127">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="015a1-128">裝置健康情況和合規性報告可提供組織中裝置的高層級資訊。</span><span class="sxs-lookup"><span data-stu-id="015a1-128">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="015a1-129">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="015a1-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="015a1-130">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="015a1-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
