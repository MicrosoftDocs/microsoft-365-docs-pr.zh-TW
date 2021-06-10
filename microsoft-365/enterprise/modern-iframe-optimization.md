---
title: 在 SharePoint Online 新式與傳統發佈網站頁面中最佳化 iFrame
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
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: 深入了解如何在 SharePoint Online 新式與傳統發佈網站頁面中最佳化 iFrame 的效能。
ms.openlocfilehash: d6e9aefa23972589c752540959b17f5d20ed0889
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923052"
---
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="26ced-103">在 SharePoint Online 新式與傳統發佈網站頁面中最佳化 iFrame</span><span class="sxs-lookup"><span data-stu-id="26ced-103">Optimize iFrames in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="26ced-104">iFrame 對於預覽多種格式的內容 (例如影面或其他媒體) 而言相當有用。</span><span class="sxs-lookup"><span data-stu-id="26ced-104">iFrames can be useful for previewing rich content such as videos or other media.</span></span> <span data-ttu-id="26ced-105">不過，因為 iFrame 會在 SharePoint 網站頁面內載入個別頁面，所以在 iFrame 中載入的內容可能包含大量影像、影片或其他元素，以上項目都會影響整體頁面載入時間，而且您無法在頁面上進行控制。</span><span class="sxs-lookup"><span data-stu-id="26ced-105">However, because iFrames load a separate page within the SharePoint site page, content loaded in the iFrame could contain large images, videos or other elements that can contribute to overall page load times and that you cannot control on the page.</span></span> <span data-ttu-id="26ced-106">本文可協助您了解如何判斷頁面中的 iFrame 如何影響使用者察覺延遲，以及如何修復常見問題。</span><span class="sxs-lookup"><span data-stu-id="26ced-106">This article will help you understand how to determine how iFrames in your pages affect user perceived latency, and how to remediate common issues.</span></span>

>[!NOTE]
><span data-ttu-id="26ced-107">如需有關 SharePoint Online 新式網站效能的詳細資訊，請參閱 [SharePoint 新式體驗中的效能](/sharepoint/modern-experience-performance)。</span><span class="sxs-lookup"><span data-stu-id="26ced-107">For more information about performance in SharePoint Online modern sites, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a><span data-ttu-id="26ced-108">使用「適用於 SharePoint 的頁面診斷」工具，透過 iFrame 來分析網頁組件</span><span class="sxs-lookup"><span data-stu-id="26ced-108">Use the Page Diagnostics for SharePoint tool to analyze web parts using iFrames</span></span>

<span data-ttu-id="26ced-109">適用於 SharePoint 的頁面診斷工具是全新 Microsoft Edge (https://www.microsoft.com/edge) 和 Chrome 瀏覽器的擴充功能，可以用來分析 SharePoint Online 新式入口網站與傳統發佈網站頁面。</span><span class="sxs-lookup"><span data-stu-id="26ced-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="26ced-110">該工具會針對每個分析頁面提供一份報告，顯示頁面如何針對定義的效能準則組執行。</span><span class="sxs-lookup"><span data-stu-id="26ced-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="26ced-111">若要安裝及了解「適用於 SharePoint 的頁面診斷」工具，請造訪[使用適用於 SharePoint Online 的頁面診斷工具](page-diagnostics-for-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="26ced-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="26ced-112">網頁診斷工具只能用於 SharePoint Online，且無法在 SharePoint 系統頁面使用。</span><span class="sxs-lookup"><span data-stu-id="26ced-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="26ced-113">當您使用「適用於 SharePoint 的頁面診斷」工具分析 SharePoint 網站頁面時，您可以在 [診斷測試] 窗格中看到包含 iFrame 的網頁組件相關資訊。</span><span class="sxs-lookup"><span data-stu-id="26ced-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about web parts containing iFrames in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="26ced-114">新式頁面與傳統頁面的基準計量是相同的。</span><span class="sxs-lookup"><span data-stu-id="26ced-114">The baseline metric is the same for modern and classic pages.</span></span>

<span data-ttu-id="26ced-115">可能的結果包括：</span><span class="sxs-lookup"><span data-stu-id="26ced-115">Possible results include:</span></span>

- <span data-ttu-id="26ced-116">**需要注意** (紅色)：頁面包含 **三個以上** 使用 iFrame 的網頁組件</span><span class="sxs-lookup"><span data-stu-id="26ced-116">**Attention required** (red): The page contains **three or more** web parts using iFrames</span></span>
- <span data-ttu-id="26ced-117">**改善機會** (黃色)：頁面包含 **一個或兩個** 使用 iFrame 的網頁組件</span><span class="sxs-lookup"><span data-stu-id="26ced-117">**Improvement opportunities** (yellow): The page contains **one or two** web parts using iFrames</span></span>
- <span data-ttu-id="26ced-118">**不需要任何動作** (綠色)：頁面不包含任何使用 iFrame 的網頁組件</span><span class="sxs-lookup"><span data-stu-id="26ced-118">**No action required** (green): The page contains no web parts using iFrames</span></span>

<span data-ttu-id="26ced-119">如果 [偵測到使用 iFrame 的網頁組件] 結果顯示在 [改善機會] 或 [需要注意] 區段中，您可以按一下結果以查看包含 iFrame 的網頁組件。</span><span class="sxs-lookup"><span data-stu-id="26ced-119">If the **Web parts using iFrames detected** result appears in either the **Improvement opportunities** or **Attention required)** section of the results, you can click the result to see the web parts that contain iFrames.</span></span>

![頁面診斷工具結果](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a><span data-ttu-id="26ced-121">修復 iFrame 效能問題</span><span class="sxs-lookup"><span data-stu-id="26ced-121">Remediate iFrame performance issues</span></span>

<span data-ttu-id="26ced-122">使用 [頁面診斷] 工具中的 [偵測到使用 iFrame 的網頁組件] 結果，以判斷哪些網頁組件包含 iFrame，且可能造成頁面載入時間變慢。</span><span class="sxs-lookup"><span data-stu-id="26ced-122">Use the **Web parts using iFrames detected** result in the Page Diagnostic tool to determine which web parts contain iFrames and may be contributing to slow page load times.</span></span>

<span data-ttu-id="26ced-123">iFrame 原本就相當緩慢，因為它們會載入個別外部頁面，包括所有相關聯內容，例如 javascript、CSS 及架構元素，其中兩個以上的元素可能會增加網站頁面的負載。</span><span class="sxs-lookup"><span data-stu-id="26ced-123">iFrames are inherently slow because they load a separate external page including all associated content such as javascript, CSS and framework elements, potentially increasing the overhead of the site page by a factor of two or more.</span></span>

<span data-ttu-id="26ced-124">請依照以下指導方針，以確保您能最佳地使用 iFrame。</span><span class="sxs-lookup"><span data-stu-id="26ced-124">Follow the guidance below to ensure optimal use of iFrames.</span></span>

- <span data-ttu-id="26ced-125">如果預覽是可開始的小型影像或者非互動式，盡可能使用影像而不是使用 iFrame。</span><span class="sxs-lookup"><span data-stu-id="26ced-125">When possible, use images instead of iFrames if the preview is small to begin with or non-interactive.</span></span>
- <span data-ttu-id="26ced-126">如果必須使用 iFrame，將數量降至最低及/或將它們移出檢視區。</span><span class="sxs-lookup"><span data-stu-id="26ced-126">If iFrames must be used, minimize the number and/or move them out of the viewport.</span></span>
- <span data-ttu-id="26ced-127">內嵌 Office 檔案 (例如 Word、Excel 和 PowerPoint) 是互動式的，但是載入速度緩慢。</span><span class="sxs-lookup"><span data-stu-id="26ced-127">Embedded Office files like Word, Excel and PowerPoint are interactive, but are slow to load.</span></span> <span data-ttu-id="26ced-128">具有完整文件連結的影像縮圖，通常有更好的效果。</span><span class="sxs-lookup"><span data-stu-id="26ced-128">Image thumbnails with a link to the full document will often perform better.</span></span>
- <span data-ttu-id="26ced-129">內嵌 YouTube 影片和 Twitter 摘要在 iFrame 中能夠執行地更好，但是請謹慎地使用這些類型的內嵌。</span><span class="sxs-lookup"><span data-stu-id="26ced-129">Embedded YouTube videos and Twitter feeds tend to perform better in iFrames, but use these kinds of embeds judiciously.</span></span>
- <span data-ttu-id="26ced-130">隔離的網頁組件是合理的例外，但是請將它們的數量降至最低並且避免放在檢視區中。</span><span class="sxs-lookup"><span data-stu-id="26ced-130">Isolated web parts are a reasonable exception, but minimize their number and placement in the viewport.</span></span>
- <span data-ttu-id="26ced-131">如果 iFrame 位於檢視區外，請考量使用 _IntersectionObserver_ 以延遲轉譯 iFrame，直到它出現在檢視中。</span><span class="sxs-lookup"><span data-stu-id="26ced-131">If an iFrame is located out of the viewport, consider using an _IntersectionObserver_ to delay rendering the iFrame until it comes into view.</span></span>

<span data-ttu-id="26ced-132">在您進行頁面修訂以修復效能問題之前，請記下分析結果中的頁面載入時間。</span><span class="sxs-lookup"><span data-stu-id="26ced-132">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="26ced-133">在修訂後再次執行工具，以查看新結果是否在基準標準內，並檢查新頁面的載入時間，以查看是否有改善。</span><span class="sxs-lookup"><span data-stu-id="26ced-133">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![頁面載入時間結果](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="26ced-135">頁面載入時間會因為各種因素而有所不同，例如網路負載、一天的時間及其他暫時條件。</span><span class="sxs-lookup"><span data-stu-id="26ced-135">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="26ced-136">您應該在進行變更前後測試幾次頁面載入時間，以協助您計算結果的平均值。</span><span class="sxs-lookup"><span data-stu-id="26ced-136">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="26ced-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="26ced-137">Related topics</span></span>

[<span data-ttu-id="26ced-138">調整 SharePoint Online 效能</span><span class="sxs-lookup"><span data-stu-id="26ced-138">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="26ced-139">調整 Office 365 效能</span><span class="sxs-lookup"><span data-stu-id="26ced-139">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="26ced-140">SharePoint 新式體驗中的效能</span><span class="sxs-lookup"><span data-stu-id="26ced-140">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)