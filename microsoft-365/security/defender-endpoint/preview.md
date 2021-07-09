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
ms.openlocfilehash: 0b6edbdcda61eaf402275ae0b6dc9a38c5fe19f7
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339487"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="62693-104">Microsoft Defender for Endpoint preview 功能</span><span class="sxs-lookup"><span data-stu-id="62693-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="62693-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="62693-105">**Applies to:**</span></span>
- [<span data-ttu-id="62693-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="62693-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="62693-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62693-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="62693-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="62693-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="62693-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="62693-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="62693-110">Endpoint service 的 Defender 服務不斷更新，以包含新功能增強功能及功能。</span><span class="sxs-lookup"><span data-stu-id="62693-110">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="62693-111">深入瞭解 Defender for Endpoint preview 發行版本中的新功能，並在第一次嘗試使用預覽體驗的情況中嘗試後續的功能。</span><span class="sxs-lookup"><span data-stu-id="62693-111">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="62693-112">在更新此頁面時，請將下列 URL 複製並貼上至您的摘要讀取器以取得通知： `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="62693-112">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="62693-113">如需一般可用之新功能的詳細資訊，請參閱 [在 Defender 的最近更新中的端點](whats-new-in-microsoft-defender-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="62693-113">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="62693-114">您需要瞭解的事項</span><span class="sxs-lookup"><span data-stu-id="62693-114">What you need to know</span></span>

<span data-ttu-id="62693-115">在使用 public preview 中的功能時，這些功能包括：</span><span class="sxs-lookup"><span data-stu-id="62693-115">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="62693-116">可能具有限制或有限的功能。</span><span class="sxs-lookup"><span data-stu-id="62693-116">May have restricted or limited functionality.</span></span> <span data-ttu-id="62693-117">例如，此功能可能只適用于一個平臺。</span><span class="sxs-lookup"><span data-stu-id="62693-117">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="62693-118">一般會透過功能變更， (正式) 使用。</span><span class="sxs-lookup"><span data-stu-id="62693-118">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="62693-119">Microsoft 完全支援。</span><span class="sxs-lookup"><span data-stu-id="62693-119">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="62693-120">只能在選取的地理區域或雲端環境中使用。</span><span class="sxs-lookup"><span data-stu-id="62693-120">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="62693-121">例如，該功能可能不存在於政府雲端中。</span><span class="sxs-lookup"><span data-stu-id="62693-121">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="62693-122">預覽中的個別功能可能會有更多的使用和支援限制。</span><span class="sxs-lookup"><span data-stu-id="62693-122">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="62693-123">如果是的話，此資訊通常會注明在功能檔中。</span><span class="sxs-lookup"><span data-stu-id="62693-123">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="62693-124">預覽版本會以標準的支援層級提供，並且可用於實際執行環境。</span><span class="sxs-lookup"><span data-stu-id="62693-124">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="turn-on-preview-features"></a><span data-ttu-id="62693-125">開啟預覽功能</span><span class="sxs-lookup"><span data-stu-id="62693-125">Turn on preview features</span></span>

<span data-ttu-id="62693-126">您將可以存取即將推出的功能，您可以在其中提供意見反應，以協助改善整體體驗，使其成為一般可用功能。</span><span class="sxs-lookup"><span data-stu-id="62693-126">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="62693-127">開啟預覽體驗設定，成為第一批嘗試即將推出的功能的人。</span><span class="sxs-lookup"><span data-stu-id="62693-127">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="62693-128">在功能窗格中，選取 [**設定**  >  **高級功能**  >  **預覽功能**]。</span><span class="sxs-lookup"><span data-stu-id="62693-128">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="62693-129">**在 [開啟**] 和 [**關閉**] 間切換設定，然後選取 [**儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="62693-129">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="62693-130">預覽功能</span><span class="sxs-lookup"><span data-stu-id="62693-130">Preview features</span></span>

<span data-ttu-id="62693-131">預覽版包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="62693-131">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="62693-132">Web 內容篩選</span><span class="sxs-lookup"><span data-stu-id="62693-132">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="62693-133">Web 內容篩選是 Microsoft Defender for Endpoint 中的 web 保護功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="62693-133">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="62693-134">它可讓您的組織根據其內容類別別來追蹤和控制網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="62693-134">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="62693-135">許多這類網站雖然並非惡意，但因相容性法規、頻寬使用量或其他考慮而可能會造成問題。</span><span class="sxs-lookup"><span data-stu-id="62693-135">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="62693-136">裝置健康情況與合規性報告</span><span class="sxs-lookup"><span data-stu-id="62693-136">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="62693-137">裝置健康情況和合規性報告可提供組織中裝置的高層級資訊。</span><span class="sxs-lookup"><span data-stu-id="62693-137">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="62693-138">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="62693-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="62693-139">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="62693-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
