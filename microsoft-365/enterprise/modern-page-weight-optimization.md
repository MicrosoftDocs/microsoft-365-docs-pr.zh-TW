---
title: 在 SharePoint Online 新式網站頁面中最佳化頁面權數
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: 瞭解如何使用頁面診斷工具，在 SharePoint 線上新式網站頁面中優化頁面重量。
ms.openlocfilehash: 64fb3c90db78a23c7f1c3fcfe604c8ef58703be0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688305"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="fbbf8-103">在 SharePoint Online 新式網站頁面中最佳化頁面權數</span><span class="sxs-lookup"><span data-stu-id="fbbf8-103">Optimize page weight in SharePoint Online modern site pages</span></span>

<span data-ttu-id="fbbf8-104">SharePoint Online 新式網站頁面包含轉譯頁面的頁面內容所需的序列化代碼，頁面內容包括瀏覽/命令列底下內容區域中的影像、文字、物件，以及形成頁面架構的其他 HTML 程式碼。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-104">SharePoint Online modern site pages contain serialized code that is required to render page content of the page, including images, text, objects in the content area underneath navigation/command bars and other HTML code that forms the framework of the page.</span></span> <span data-ttu-id="fbbf8-105">頁面權數是這個 HTML 程式碼的度量，應加以限制，以確保最佳的頁面載入時間。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-105">Page weight is a measurement of this HTML code, and should be limited to ensure optimal page load times.</span></span>

<span data-ttu-id="fbbf8-106">本文可協助您了解如何在新式網站頁面中減少頁面權數。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-106">This article will help you understand how to reduce page weight in your modern site pages.</span></span>

>[!NOTE]
><span data-ttu-id="fbbf8-107">如需有關 SharePoint Online 新式入口網站效能的詳細資訊，請參閱 [SharePoint 新式體驗中的效能](https://docs.microsoft.com/sharepoint/modern-experience-performance)。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-107">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a><span data-ttu-id="fbbf8-108">使用「適用於 SharePoint 的頁面診斷」工具來分析頁面權數</span><span class="sxs-lookup"><span data-stu-id="fbbf8-108">Use the Page Diagnostics for SharePoint tool to analyze page weight</span></span>

<span data-ttu-id="fbbf8-109">適用於 SharePoint 的頁面診斷工具是全新 Microsoft Edge (https://www.microsoft.com/edge) 和 Chrome 瀏覽器的擴充功能，可以用來分析 SharePoint Online 新式入口網站與傳統發佈網站頁面。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="fbbf8-110">該工具會針對每個分析頁面提供一份報告，顯示頁面如何針對定義的效能準則組執行。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="fbbf8-111">若要安裝及了解「適用於 SharePoint 的頁面診斷」工具，請造訪[使用適用於 SharePoint Online 的頁面診斷工具](page-diagnostics-for-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="fbbf8-112">網頁診斷工具只能用於 SharePoint Online，且無法在 SharePoint 系統頁面使用。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="fbbf8-113">當您使用「適用於 SharePoint 的頁面診斷」工具分析 SharePoint 網站頁面時，您可以在 [診斷測試]__ 窗格的 [頁面權數低於 500KB]\*\*\*\* 結果中看到關於頁面的資訊。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about page in the **Page weight under 500KB** result of the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="fbbf8-114">如果頁面權數低於基準值，則結果會顯示為綠色，如果頁面權數超過基準值，則會顯示為紅色。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-114">The result will appear in green if the page weight is under the baseline value, and red if the page weight exceeds the baseline value.</span></span>

<span data-ttu-id="fbbf8-115">可能的結果包括：</span><span class="sxs-lookup"><span data-stu-id="fbbf8-115">Possible results include:</span></span>

- <span data-ttu-id="fbbf8-116">**需要注意** (紅色)：頁面權數超過 500KB</span><span class="sxs-lookup"><span data-stu-id="fbbf8-116">**Attention required** (red): Page weight exceeds 500KB</span></span>
- <span data-ttu-id="fbbf8-117">**不需要任何動作** (綠色)：頁面權數低於 500KB</span><span class="sxs-lookup"><span data-stu-id="fbbf8-117">**No action required** (green): Page weight is under 500KB</span></span>

<span data-ttu-id="fbbf8-118">如果 [頁面權數低於 500KB]\*\*\*\* 結果顯示在 [需要注意]\*\*\*\* 區段中，您可以按一下結果以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-118">If the **Page weight under 500KB** result appears in the **Attention required** section, you can click the result for details.</span></span>

![對 SharePoint 的要求結果](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a><span data-ttu-id="fbbf8-120">修復頁面權數問題</span><span class="sxs-lookup"><span data-stu-id="fbbf8-120">Remediate page weight issues</span></span>

<span data-ttu-id="fbbf8-121">如果頁面權數超過 500KB，您可以藉由減少網頁組件的數量，並將頁面內容限制在適當的程度，以改善整體頁面載入時間。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-121">If page weight exceeds 500KB, you can improve overall page load time by reducing the number of web parts and limiting page content to an appropriate degree.</span></span>

<span data-ttu-id="fbbf8-122">降低頁面權數的一般指導方針包括：</span><span class="sxs-lookup"><span data-stu-id="fbbf8-122">General guidance for reducing page weight includes:</span></span>

- <span data-ttu-id="fbbf8-123">將頁面內容限制為合理的數量，並且對相關內容使用多個頁面。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-123">Limit the page content to a reasonable amount and use multiple pages for related content.</span></span>
- <span data-ttu-id="fbbf8-124">將具有大型屬性包的網頁組件使用降至最低。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-124">Minimize the use of web parts that have large property bags.</span></span>
- <span data-ttu-id="fbbf8-125">盡可能使用非互動式彙總檢視。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-125">Use non-interactive rollup views when possible.</span></span>
- <span data-ttu-id="fbbf8-126">您可以使用壓縮的影像格式並確保是從 CDN 下載，以適當地調整影像大小。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-126">Optimize image sizes by sizing images appropriately, using compressed image formats and ensuring that they are downloaded from a CDN.</span></span>

<span data-ttu-id="fbbf8-127">您可以在下列文章中找到更多關於限制頁面權數的指導方針：</span><span class="sxs-lookup"><span data-stu-id="fbbf8-127">You can find additional guidance for limiting page weight in the following article:</span></span>

- <span data-ttu-id="fbbf8-128">[在 SharePoint 中最佳化頁面效能](https://docs.microsoft.com/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint) (英文)</span><span class="sxs-lookup"><span data-stu-id="fbbf8-128">[Optimize page performance in SharePoint](https://docs.microsoft.com/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)</span></span>

<span data-ttu-id="fbbf8-129">在您進行頁面修訂以修復效能問題之前，請記下分析結果中的頁面載入時間。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-129">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="fbbf8-130">在修訂後再次執行工具，以查看新結果是否在基準標準內，並檢查新頁面的載入時間，以查看是否有改善。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-130">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![頁面載入時間結果](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="fbbf8-132">頁面載入時間會因為各種因素而有所不同，例如網路負載、一天的時間及其他暫時條件。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-132">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="fbbf8-133">您應該在進行變更前後測試幾次頁面載入時間，以協助您計算結果的平均值。</span><span class="sxs-lookup"><span data-stu-id="fbbf8-133">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fbbf8-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="fbbf8-134">Related topics</span></span>

[<span data-ttu-id="fbbf8-135">調整 SharePoint Online 效能</span><span class="sxs-lookup"><span data-stu-id="fbbf8-135">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="fbbf8-136">調整 Office 365 效能</span><span class="sxs-lookup"><span data-stu-id="fbbf8-136">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="fbbf8-137">SharePoint 新式體驗中的效能</span><span class="sxs-lookup"><span data-stu-id="fbbf8-137">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="fbbf8-138">內容傳遞網路</span><span class="sxs-lookup"><span data-stu-id="fbbf8-138">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="fbbf8-139">使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fbbf8-139">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)