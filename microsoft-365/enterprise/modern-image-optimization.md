---
title: 在 SharePoint Online 新式網站頁面中最佳化影像
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
description: 瞭解如何使用 SharePoint Online 中所包含的工具，在 SharePoint 線上新式網站頁面中優化圖像。
ms.openlocfilehash: a4f2def86e1378a9fb76ae9ecbe6a55da75ecffc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923013"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="ee85f-103">在 SharePoint Online 新式網站頁面中最佳化影像</span><span class="sxs-lookup"><span data-stu-id="ee85f-103">Optimize images in SharePoint Online modern site pages</span></span>

<span data-ttu-id="ee85f-104">本文可協助您了解如何在 SharePoint Online 新式網站頁面中最佳化影像。</span><span class="sxs-lookup"><span data-stu-id="ee85f-104">This article will help you understand how to optimize images in SharePoint Online modern site pages.</span></span>

<span data-ttu-id="ee85f-105">如需最佳化傳統發布網站中的影像的詳細資訊，請參閱[ SharePoint Online 的影像最佳化](image-optimization-for-sharepoint-online.md)</span><span class="sxs-lookup"><span data-stu-id="ee85f-105">For information about optimizing images in classic publishing sites, see [Image optimization for SharePoint Online](image-optimization-for-sharepoint-online.md)..</span></span>

>[!NOTE]
><span data-ttu-id="ee85f-106">如需有關 SharePoint Online 新式入口網站效能的詳細資訊，請參閱 [SharePoint 新式體驗中的效能](/sharepoint/modern-experience-performance)。</span><span class="sxs-lookup"><span data-stu-id="ee85f-106">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a><span data-ttu-id="ee85f-107">使用「適用於 SharePoint 的頁面診斷」工具來分析影像最佳化</span><span class="sxs-lookup"><span data-stu-id="ee85f-107">Use the Page Diagnostics for SharePoint tool to analyze image optimization</span></span>

<span data-ttu-id="ee85f-108">適用於 SharePoint 的頁面診斷工具是全新 Microsoft Edge (https://www.microsoft.com/edge) 和 Chrome 瀏覽器的擴充功能，可以用來分析 SharePoint Online 新式入口網站與傳統發佈網站頁面。</span><span class="sxs-lookup"><span data-stu-id="ee85f-108">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="ee85f-109">該工具會針對每個分析頁面提供一份報告，顯示頁面如何針對定義的效能準則組執行。</span><span class="sxs-lookup"><span data-stu-id="ee85f-109">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="ee85f-110">若要安裝及了解「適用於 SharePoint 的頁面診斷」工具，請造訪[使用適用於 SharePoint Online 的頁面診斷工具](page-diagnostics-for-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="ee85f-110">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="ee85f-111">網頁診斷工具只能用於 SharePoint Online，且無法在 SharePoint 系統頁面使用。</span><span class="sxs-lookup"><span data-stu-id="ee85f-111">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="ee85f-112">當您使用「適用於 SharePoint 的頁面診斷」工具分析 SharePoint 新式網站時，您可以在 [診斷測試] 窗格中看到大型影像的資訊。</span><span class="sxs-lookup"><span data-stu-id="ee85f-112">When you analyze a SharePoint modern site with the Page Diagnostics for SharePoint tool, you can see information about large images in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="ee85f-113">可能的結果包括：</span><span class="sxs-lookup"><span data-stu-id="ee85f-113">Possible results include:</span></span>

- <span data-ttu-id="ee85f-114">**需要注意** (紅色)：頁面包含 [一或多個] 大小超過 300KB 的影像</span><span class="sxs-lookup"><span data-stu-id="ee85f-114">**Attention required** (red): The page contains **one or more** images over 300KB in size</span></span>
- <span data-ttu-id="ee85f-115">**不需要採取動作** (紅色)：頁面未包含大小超過 300KB 的影像</span><span class="sxs-lookup"><span data-stu-id="ee85f-115">**No action required** (green): The page contains no images over 300KB in size</span></span>

<span data-ttu-id="ee85f-116">如果大型影像的偵測結果顯示在結果的 [需要注意] 區段，您可以按一下結果來查看其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ee85f-116">If the **Large images detected** result appears in the **Attention required** section of the results, you can click the result to see additional details.</span></span>

![頁面診斷工具結果](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a><span data-ttu-id="ee85f-118">修正大型影像問題</span><span class="sxs-lookup"><span data-stu-id="ee85f-118">Remediate large image issues</span></span>

<span data-ttu-id="ee85f-119">如果頁面的影像大小超過 300KB，請選取 [偵測到大型影像] 結果，以查看哪些影像太大。</span><span class="sxs-lookup"><span data-stu-id="ee85f-119">If a page contains images over 300KB in size, select the **Large images detected** result to see which images are too large.</span></span> <span data-ttu-id="ee85f-120">在新式 SharePoint Online 頁面中，系統會自動提供影像的轉譯，並根據瀏覽器視窗的大小和用戶端監視器的解析度來調整影像大小。</span><span class="sxs-lookup"><span data-stu-id="ee85f-120">In modern SharePoint Online pages, renditions of images are automatically provided and sized depending on the size of the browser window and the resolution of the client monitor.</span></span> <span data-ttu-id="ee85f-121">在上傳至 SharePoint Online 之前，您應隨時最佳化網頁使用的影像。</span><span class="sxs-lookup"><span data-stu-id="ee85f-121">You should always optimize images for web use prior to upload to SharePoint Online.</span></span> <span data-ttu-id="ee85f-122">系統會自動縮小過大的影像和解析度，這可能會導致非預期的轉譯特性。</span><span class="sxs-lookup"><span data-stu-id="ee85f-122">Very large images will be automatically reduced in size and resolution which can result in unexpected rendering characteristics.</span></span>

<span data-ttu-id="ee85f-123">在您進行頁面修訂以修復效能問題之前，請記下分析結果中的頁面載入時間。</span><span class="sxs-lookup"><span data-stu-id="ee85f-123">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="ee85f-124">在修訂後再次執行工具，以查看新結果是否在基準標準內，並檢查新頁面的載入時間，以查看是否有改善。</span><span class="sxs-lookup"><span data-stu-id="ee85f-124">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![頁面載入時間結果](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="ee85f-126">頁面載入時間會因為各種因素而有所不同，例如網路負載、一天的時間及其他暫時條件。</span><span class="sxs-lookup"><span data-stu-id="ee85f-126">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="ee85f-127">您應該在進行變更前後測試幾次頁面載入時間，以協助您計算結果的平均值。</span><span class="sxs-lookup"><span data-stu-id="ee85f-127">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ee85f-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="ee85f-128">Related topics</span></span>

[<span data-ttu-id="ee85f-129">調整 SharePoint Online 效能</span><span class="sxs-lookup"><span data-stu-id="ee85f-129">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="ee85f-130">調整 Office 365 效能</span><span class="sxs-lookup"><span data-stu-id="ee85f-130">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="ee85f-131">SharePoint 新式體驗中的效能</span><span class="sxs-lookup"><span data-stu-id="ee85f-131">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="ee85f-132">內容傳遞網路</span><span class="sxs-lookup"><span data-stu-id="ee85f-132">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="ee85f-133">使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ee85f-133">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)