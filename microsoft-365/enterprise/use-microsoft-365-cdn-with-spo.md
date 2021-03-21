---
title: '在線上 SharePoint 使用 Office 365 內容傳遞網路 (CDN) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: 瞭解如何使用 Office 365 內容傳遞網路 (CDN) 以加速 SharePoint 線上資產的傳遞。
ms.openlocfilehash: 6b740fc1429613627e0597dc6ecf2e150c015989
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924813"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="5ebec-103">使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5ebec-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="5ebec-104">您可以使用內建的 Office 365 內容傳遞網路 (CDN) 來主控靜態資產，為您的 SharePoint網頁提供更佳的效能。</span><span class="sxs-lookup"><span data-stu-id="5ebec-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="5ebec-105">Office 365 CDN 透過將靜態資產快取到更靠近提出要求之瀏覽器的位置 (這有助於加速下載以及減少延遲)，藉此改善效能。</span><span class="sxs-lookup"><span data-stu-id="5ebec-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="5ebec-106">此外，Office 365 CDN 使用 [HTTP/2 通訊協定](https://en.wikipedia.org/wiki/HTTP/2) ，以提升壓縮和 HTTP 流水線。</span><span class="sxs-lookup"><span data-stu-id="5ebec-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="5ebec-107">Office 365 CDN 服務包含在 SharePoint Online 訂閱的一部分。</span><span class="sxs-lookup"><span data-stu-id="5ebec-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="5ebec-108">Office 365 CDN 只適用于世界) 雲端的 **實際** 執行 (中的承租人。</span><span class="sxs-lookup"><span data-stu-id="5ebec-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="5ebec-109">美國政府、中國和德國雲彩中的承租人目前不支援 Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="5ebec-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="5ebec-110">Office 365 CDN 是由可讓您在多個位置或 _來源_ 主控靜態資產的多個 CDN 組成，並透過全球高速網路提供資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="5ebec-111">根據您要在 Office 365 CDN 中主控的內容類型而定，您可以新增 **公用** 來源、**私人** 來源或兩者。</span><span class="sxs-lookup"><span data-stu-id="5ebec-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="5ebec-112">請參閱 [選擇是否每個來源都應該是公開或私人](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) 的，如需公開和私人來源之間差異的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5ebec-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="5ebec-113">![Office 365 CDN 概念圖表](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN 概念圖表")</span><span class="sxs-lookup"><span data-stu-id="5ebec-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="5ebec-114">如果您已熟悉 Cdn 的運作方式，您只需要完成少數幾個步驟即可為您的租使用者啟用 Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="5ebec-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="5ebec-115">本主題說明如何進行。</span><span class="sxs-lookup"><span data-stu-id="5ebec-115">This topic describes how.</span></span> <span data-ttu-id="5ebec-116">如需如何開始主控靜態資產的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="5ebec-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="5ebec-117">有其他 Microsoft 主控的 Cdn 可搭配 Office 365 用來進行特殊的使用案例，但在本主題中不會討論這些，因為它們超出 Office 365 CDN 的範圍。</span><span class="sxs-lookup"><span data-stu-id="5ebec-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="5ebec-118">如需詳細資訊，請參閱 [其他 Microsoft cdn](content-delivery-networks.md#other-microsoft-cdns)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="5ebec-119">**回到 [Office 365 的網路規劃和效能調整](./network-planning-and-performance.md)。**</span><span class="sxs-lookup"><span data-stu-id="5ebec-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="5ebec-120">在 SharePoint Online 中使用 Office 365 CDN 的概述</span><span class="sxs-lookup"><span data-stu-id="5ebec-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="5ebec-121">若要為您的組織設定 Office 365 CDN，請遵循下列基本步驟：</span><span class="sxs-lookup"><span data-stu-id="5ebec-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="5ebec-122">規劃 Office 365 CDN 的部署</span><span class="sxs-lookup"><span data-stu-id="5ebec-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="5ebec-123">[決定您要在 CDN 上裝載的靜態資產](use-microsoft-365-cdn-with-spo.md#CDNAssets)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="5ebec-124">[決定您要儲存資產的位置](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="5ebec-125">此位置可以是 SharePoint 網站、文件庫或資料夾，也稱為 _來源_。</span><span class="sxs-lookup"><span data-stu-id="5ebec-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="5ebec-126">[選擇每個原產地應為 public 或 private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="5ebec-127">您可以新增公用及私人類型的多個來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="5ebec-128">使用 PowerShell 或 SharePoint 線上 CLI 安裝及設定 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="5ebec-129">使用 SharePoint Online 管理命令介面來安裝及設定 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="5ebec-130">使用 PnP PowerShell 安裝及設定 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="5ebec-131">使用 Office 365 CLI 安裝及設定 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="5ebec-132">當您完成此步驟後，您將會有：</span><span class="sxs-lookup"><span data-stu-id="5ebec-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="5ebec-133">已為您的組織啟用 CDN。</span><span class="sxs-lookup"><span data-stu-id="5ebec-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="5ebec-134">新增您的來源，將每個原產地識別為 public 或 private。</span><span class="sxs-lookup"><span data-stu-id="5ebec-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="5ebec-135">完成安裝後，您可以依下列方式 [管理 Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) ：</span><span class="sxs-lookup"><span data-stu-id="5ebec-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="5ebec-136">新增、更新及移除資產</span><span class="sxs-lookup"><span data-stu-id="5ebec-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="5ebec-137">新增及移除來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-137">Adding and removing origins</span></span>
+ <span data-ttu-id="5ebec-138">設定 CDN 原則</span><span class="sxs-lookup"><span data-stu-id="5ebec-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="5ebec-139">如有必要，停用 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="5ebec-140">最後，請參閱 [使用 cdn 資產](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) 以瞭解從公用和私人來源存取 cdn 資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="5ebec-141">如需解決常見問題的指導，請參閱 [疑難排解 Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) 。</span><span class="sxs-lookup"><span data-stu-id="5ebec-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="5ebec-142">規劃 Office 365 CDN 的部署</span><span class="sxs-lookup"><span data-stu-id="5ebec-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-143">在您部署 Office 365 租使用者的 Office 365 CDN 之前，您應該考慮下列因素作為規劃程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="5ebec-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="5ebec-144">決定要在 CDN 上裝載的靜態資產</span><span class="sxs-lookup"><span data-stu-id="5ebec-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="5ebec-145">決定您要儲存資產的位置</span><span class="sxs-lookup"><span data-stu-id="5ebec-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="5ebec-146">選擇每個原產地應該是公用還是私人</span><span class="sxs-lookup"><span data-stu-id="5ebec-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="5ebec-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="5ebec-148">決定要在 CDN 上裝載的靜態資產</span><span class="sxs-lookup"><span data-stu-id="5ebec-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="5ebec-149">一般說來，Cdn 對於主控 _靜態資產_ 或不經常變更的資產會最為有效。</span><span class="sxs-lookup"><span data-stu-id="5ebec-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="5ebec-150">合理的經驗法則是找出符合部分或所有條件的檔案：</span><span class="sxs-lookup"><span data-stu-id="5ebec-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="5ebec-151">內嵌在頁面中的靜態檔案 (像是腳本和影像) 可能會對頁面載入時間產生重大的增量影響</span><span class="sxs-lookup"><span data-stu-id="5ebec-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="5ebec-152">類似可執行檔和安裝檔案的大型檔案</span><span class="sxs-lookup"><span data-stu-id="5ebec-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="5ebec-153">支援用戶端程式代碼的資源庫</span><span class="sxs-lookup"><span data-stu-id="5ebec-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="5ebec-154">例如，重複要求的小型檔案（如網站影像和腳本）可大幅改善網站轉譯效能，並在您將 SharePoint 線上網站新增至 CDN 來源時，以增量方式減少其負載。</span><span class="sxs-lookup"><span data-stu-id="5ebec-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="5ebec-155">您可以從 CDN 下載較大的檔案，例如安裝可執行檔，在 SharePoint Online 網站上的負載會帶來積極效能的影響，而且後續的負載也會降低，即使不經常存取。</span><span class="sxs-lookup"><span data-stu-id="5ebec-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="5ebec-156">每個檔案的效能提升都取決於許多因素，包括用戶端接近最接近的 CDN 端點、本機網路上的暫時性情況等等。</span><span class="sxs-lookup"><span data-stu-id="5ebec-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="5ebec-157">許多靜態檔案都很小，而且可以從 Office 365 下載（不只是一秒鐘）。</span><span class="sxs-lookup"><span data-stu-id="5ebec-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="5ebec-158">不過，網頁上可能會包含許多內嵌檔案，且累計下載時間為數秒。</span><span class="sxs-lookup"><span data-stu-id="5ebec-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="5ebec-159">從 CDN 服務這些檔案可大幅減少整體頁面載入時間。</span><span class="sxs-lookup"><span data-stu-id="5ebec-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="5ebec-160">請參閱 [CDN 可提供什麼效能提升？](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) 如需範例。</span><span class="sxs-lookup"><span data-stu-id="5ebec-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="5ebec-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="5ebec-162">決定您要儲存資產的位置</span><span class="sxs-lookup"><span data-stu-id="5ebec-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="5ebec-163">CDN 會從一個稱為 _來源_ 的位置提取您的資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="5ebec-164">來源可以是可透過 URL 存取的 SharePoint 網站、文件庫或資料夾。</span><span class="sxs-lookup"><span data-stu-id="5ebec-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="5ebec-165">當您為組織指定來源時，具有極大的彈性。</span><span class="sxs-lookup"><span data-stu-id="5ebec-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="5ebec-166">例如，您可以指定多個來源或單一原始位置，以放置您的所有 CDN 資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="5ebec-167">您可以選擇同時包含組織的公開來源或私人來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="5ebec-168">大多陣列織會選擇實現兩者的組合。</span><span class="sxs-lookup"><span data-stu-id="5ebec-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="5ebec-169">您可以為您的來源（例如資料夾或文件庫）建立新的容器，並新增您要從 CDN 中提供的檔案。</span><span class="sxs-lookup"><span data-stu-id="5ebec-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="5ebec-170">如果您有想要從 CDN 取得的特定資產集，且想要將一組 CDN 資產限制為僅限容器中的檔案，這是一種很好的方法。</span><span class="sxs-lookup"><span data-stu-id="5ebec-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="5ebec-171">您也可以將現有的網站集合、網站、文件庫或資料夾設定為來源，使該容器中的所有合格資產都可供 CDN 使用。</span><span class="sxs-lookup"><span data-stu-id="5ebec-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="5ebec-172">在您將現有的容器新增為來源之前，請務必確定您已知道其內容和許可權，這樣就不會無意公開資產給匿名存取或未經授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="5ebec-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="5ebec-173">您可以定義 _cdn 原則_ ，以從 CDN 中排除來源的內容。</span><span class="sxs-lookup"><span data-stu-id="5ebec-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="5ebec-174">CDN 原則會透過諸如 _檔案類型_ 和 _網站分類_ 等屬性，將資產公開或私人來源，套用至您在原則中指定的 CdnType (私人或公開) 中的所有來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="5ebec-175">例如，如果您新增包含多個子網站之網站的私人來源，您可以定義一個原則，以排除標示為 **機密** 的網站，這樣就不會從 CDN 為已套用該分類的網站提供內容。</span><span class="sxs-lookup"><span data-stu-id="5ebec-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="5ebec-176">原則會套用至您已新增至 CDN 的 _所有_ 私人來源內容。</span><span class="sxs-lookup"><span data-stu-id="5ebec-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="5ebec-177">請記住，「來源」越多，CDN 服務處理要求的時間就會越大。</span><span class="sxs-lookup"><span data-stu-id="5ebec-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="5ebec-178">建議您盡可能限制來源數量。</span><span class="sxs-lookup"><span data-stu-id="5ebec-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="5ebec-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="5ebec-180">選擇每個原產地應該是公用還是私人</span><span class="sxs-lookup"><span data-stu-id="5ebec-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="5ebec-181">當您識別來源時，請指定是否應該 _公開_ 或 _私密_。</span><span class="sxs-lookup"><span data-stu-id="5ebec-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="5ebec-182">公用來源存取 CDN 資產是匿名的，而私人來源的 CDN 內容則是透過動態產生的權杖來保護，以獲得較高的安全性。</span><span class="sxs-lookup"><span data-stu-id="5ebec-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="5ebec-183">不論您選擇哪個選項，當您負責管理 CDN 本身時，Microsoft 都會執行所有繁重的動作。</span><span class="sxs-lookup"><span data-stu-id="5ebec-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="5ebec-184">此外，您還可以在您設定 CDN 並識別來源之後，再變更您的想法。</span><span class="sxs-lookup"><span data-stu-id="5ebec-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="5ebec-185">公用和私人選項都提供類似的效能提升，但各項都有獨特的屬性和優點。</span><span class="sxs-lookup"><span data-stu-id="5ebec-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="5ebec-186">Office 365 CDN 內的 **公開** 來源可以匿名方式存取，且具有資產 URL 的任何人都可以存取主控資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="5ebec-187">因為對公用來源中內容的存取是匿名的，您應該只使用公用來源來快取非敏感性的一般內容，例如 javascript 檔案、指令碼、圖示和影像。</span><span class="sxs-lookup"><span data-stu-id="5ebec-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as javascript files, scripts, icons and images.</span></span>

<span data-ttu-id="5ebec-188">Office 365 CDN 內的 **私人** 來源可提供使用者內容的私人存取權，例如 SharePoint 線上文件庫、網站和專有影像。</span><span class="sxs-lookup"><span data-stu-id="5ebec-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="5ebec-189">存取私人來源中的內容是以動態產生的標記來保護，所以只有具有原始文件庫或儲存位置許可權的使用者可以存取私人來源中的內容。</span><span class="sxs-lookup"><span data-stu-id="5ebec-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="5ebec-190">Office 365 CDN 中的私人來源僅可用於 SharePoint 線上內容，而且您只能透過從 SharePoint Online 租使用者重新導向，存取私人來源中的資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="5ebec-191">您可以深入瞭解如何 [使用私人](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)來源中的資產，對私人來源中的資產進行 CDN 存取的方式。</span><span class="sxs-lookup"><span data-stu-id="5ebec-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="5ebec-192">在公用來源中主控資產的屬性與優點</span><span class="sxs-lookup"><span data-stu-id="5ebec-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="5ebec-193">公用來源中公開的資產可供任何人匿名存取。</span><span class="sxs-lookup"><span data-stu-id="5ebec-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="5ebec-194">您絕對不應該放置包含使用者資訊或被視為對您的組織敏感的公用來源中的資源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>
+ <span data-ttu-id="5ebec-195">如果您移除公用來源中的資產，該資產可持續從快取的30天內可用;不過，我們會在15分鐘內使 CDN 中的資產連結無效。</span><span class="sxs-lookup"><span data-stu-id="5ebec-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>
+ <span data-ttu-id="5ebec-196">當您主控樣式表單 (CSS 檔案) 公用來源中，您可以使用相對路徑，並在程式碼中 URIs。</span><span class="sxs-lookup"><span data-stu-id="5ebec-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="5ebec-197">這表示您可以參照背景圖像的位置，以及與呼叫它之資產所在位置相關的其他物件。</span><span class="sxs-lookup"><span data-stu-id="5ebec-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>
+ <span data-ttu-id="5ebec-198">雖然您可以建立公用來源的 URL，但是請務必小心，並確定您使用頁面內容屬性，並遵循執行此動作的指導方針。</span><span class="sxs-lookup"><span data-stu-id="5ebec-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="5ebec-199">原因是，如果對 CDN 的存取功能變成無法使用，則 URL 不會自動解析為 SharePoint Online 中的組織，而且可能會造成中斷連結和其他錯誤。</span><span class="sxs-lookup"><span data-stu-id="5ebec-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="5ebec-200">URL 也會變更 wich，原因是它不應該只是硬編碼成目前的值。</span><span class="sxs-lookup"><span data-stu-id="5ebec-200">The URL is also subject to change wich is why it should not just be hard coded to its current value.</span></span>
+ <span data-ttu-id="5ebec-201">Public 來源包含的預設檔案類型為： .css，eot，.gif，.ico，jpeg，.jpg，.js，.map，.map，ttf，，woff 與 woff2。）。</span><span class="sxs-lookup"><span data-stu-id="5ebec-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="5ebec-202">您可以指定其他檔案類型。</span><span class="sxs-lookup"><span data-stu-id="5ebec-202">You can specify additional file types.</span></span>
+ <span data-ttu-id="5ebec-203">您可以設定原則，以排除已由您指定之網站分類所識別的資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="5ebec-204">例如，您可以選擇排除標記為「機密」或「限制」的所有資產，即使這些資產是允許的檔案類型，而且位於公用來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="5ebec-205">主控資產私人來源的屬性與優點</span><span class="sxs-lookup"><span data-stu-id="5ebec-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="5ebec-206">私人來源僅可用於 SharePoint 線上資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-206">Private origins can only be used for SharePoint Online assets.</span></span>
+ <span data-ttu-id="5ebec-207">如果使用者具有存取容器的許可權，則使用者只能存取其私人來源中的資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="5ebec-208">禁止匿名存取這些資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-208">Anonymous access to these assets is prevented.</span></span>
+ <span data-ttu-id="5ebec-209">私人來源中的資產必須從 SharePoint Online 租使用者參考。</span><span class="sxs-lookup"><span data-stu-id="5ebec-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="5ebec-210">對私人 CDN 資產的直接存取無法運作。</span><span class="sxs-lookup"><span data-stu-id="5ebec-210">Direct access to private CDN assets does not work.</span></span>
+ <span data-ttu-id="5ebec-211">如果您移除私人來源中的資產，該資產可能會持續從快取的一小時內可用;不過，我們會在移除資產的15分鐘內，使 CDN 中的資源連結無效。</span><span class="sxs-lookup"><span data-stu-id="5ebec-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>
+ <span data-ttu-id="5ebec-212">私人來源包含的預設檔案類型為 .gif、.ico、.gif、.jpg、.js 和 .png。</span><span class="sxs-lookup"><span data-stu-id="5ebec-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="5ebec-213">您可以指定其他檔案類型。</span><span class="sxs-lookup"><span data-stu-id="5ebec-213">You can specify additional file types.</span></span>
+ <span data-ttu-id="5ebec-214">就像公開來源一樣，您可以設定原則，以排除已透過網站分類識別的資產，即使您使用萬用字元包含資料夾或文件庫中的所有資產也是一樣。</span><span class="sxs-lookup"><span data-stu-id="5ebec-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="5ebec-215">如需有關如何使用 Office 365 CDN、一般 CDN 概念及其他 Microsoft Cdn （您可以搭配 Office 365 租使用者使用）的詳細資訊，請參閱 [Content 傳遞網路](content-delivery-networks.md)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="5ebec-216">預設 CDN 來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-216">Default CDN origins</span></span>

<span data-ttu-id="5ebec-217">除非您另外指定，否則 Office 365 會在您啟用 Office 365 CDN 時，為您設定某些預設來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="5ebec-218">如果您最初選擇不進行布建，您可以在完成安裝後新增這些來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="5ebec-219">除非您瞭解略過設定預設來源的結果，並有特定原因要執行此操作，否則您應允許在啟用 CDN 時建立這些結果。</span><span class="sxs-lookup"><span data-stu-id="5ebec-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="5ebec-220">預設私人 CDN 來源：</span><span class="sxs-lookup"><span data-stu-id="5ebec-220">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="5ebec-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="5ebec-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="5ebec-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="5ebec-222">\*/siteassets</span></span>

<span data-ttu-id="5ebec-223">預設公用 CDN 來源：</span><span class="sxs-lookup"><span data-stu-id="5ebec-223">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="5ebec-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="5ebec-224">\*/masterpage</span></span>
+ <span data-ttu-id="5ebec-225">\*/style 程式庫</span><span class="sxs-lookup"><span data-stu-id="5ebec-225">\*/style library</span></span>
+ <span data-ttu-id="5ebec-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="5ebec-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="5ebec-227">_clientsideassets_ 是預設公用來源，已新增至12月2017中的 OFFICE 365 CDN 服務。</span><span class="sxs-lookup"><span data-stu-id="5ebec-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="5ebec-228">此來源必須存在，使 CDN 中的 SharePoint 架構解決方案能夠運作。</span><span class="sxs-lookup"><span data-stu-id="5ebec-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="5ebec-229">如果您已在十二月2017之前啟用 Office 365 CDN，或在啟用 CDN 時略過設定預設來源，則可以手動新增此來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="5ebec-230">如需詳細資訊，請參閱 [我的用戶端網頁元件或 SharePoint 架構解決方案無法運作](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="5ebec-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="5ebec-232">使用 SharePoint 線上管理命令介面來設定和設定 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="5ebec-233">本節中的程式需要您使用 SharePoint 線上管理命令介面，連線至 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="5ebec-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="5ebec-234">如需相關指示，請參閱 [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="5ebec-235">完成下列步驟，以使用 SharePoint 線上管理命令介面，設定 CDN 以在 SharePoint Online 中主控您的資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="5ebec-236">按一下以展開</span><span class="sxs-lookup"><span data-stu-id="5ebec-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="5ebec-237">讓您的組織使用 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-238">在您變更租使用者 CDN 設定之前，您應該先在 Office 365 租使用者中取得私人 CDN 設定的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="5ebec-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="5ebec-239">使用 SharePoint Online 管理命令介面來連線至您的租使用者：</span><span class="sxs-lookup"><span data-stu-id="5ebec-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="5ebec-240">現在使用 **SPOTenantCdnEnabled 指令程式** ，從租使用者中取得 CDN 狀態設定：</span><span class="sxs-lookup"><span data-stu-id="5ebec-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="5ebec-241">指定之 CdnType 的 CDN 狀態會輸出至螢幕。</span><span class="sxs-lookup"><span data-stu-id="5ebec-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="5ebec-242">使用 **SPOTenantCdnEnabled** Cmdlet 可讓您的組織使用 OFFICE 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="5ebec-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="5ebec-243">您可以讓組織同時使用公用來源、私人來源或同時使用這兩者。</span><span class="sxs-lookup"><span data-stu-id="5ebec-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="5ebec-244">您也可以設定 CDN，在啟用時略過預設來源的設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="5ebec-245">您可以隨時依照本主題所述新增這些來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-245">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="5ebec-246">在 Windows Powershell 中 SharePoint Online：</span><span class="sxs-lookup"><span data-stu-id="5ebec-246">In Windows Powershell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="5ebec-247">例如，若要讓您的組織同時使用公用和私人來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="5ebec-248">若要讓您的組織同時使用公用和私人來源，但略過設定預設來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="5ebec-249">請參閱 [預設 CDN 來源](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) ，以取得啟用 OFFICE 365 CDN 時預設會布建之來源的相關資訊，以及略過設定預設來源的潛在影響。</span><span class="sxs-lookup"><span data-stu-id="5ebec-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="5ebec-250">若要讓您的組織使用公用來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-250">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="5ebec-251">若要讓您的組織使用私人來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-251">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="5ebec-252">如需此 Cmdlet 的詳細資訊，請參閱 [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="5ebec-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="5ebec-254">變更要包含在 Office 365 CDN (選用) 中的檔案類型清單</span><span class="sxs-lookup"><span data-stu-id="5ebec-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="5ebec-255">當您使用 **SPOTenantCdnPolicy** 指令程式來定義檔案類型時，會覆寫目前定義的清單。</span><span class="sxs-lookup"><span data-stu-id="5ebec-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="5ebec-256">如果您想要將其他檔案類型新增至清單，請先使用 Cmdlet 來找出已允許的檔案類型，並將其包含在清單中，以及新的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="5ebec-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="5ebec-257">使用 **SPOTenantCdnPolicy 指令程式** ，定義可由 CDN 中的公用和私人來源主控的靜態檔案類型。</span><span class="sxs-lookup"><span data-stu-id="5ebec-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="5ebec-258">根據預設，允許一般資產類型，例如 .css、.gif、.jpg 和 .js。</span><span class="sxs-lookup"><span data-stu-id="5ebec-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="5ebec-259">在 Windows PowerShell 中 SharePoint Online：</span><span class="sxs-lookup"><span data-stu-id="5ebec-259">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="5ebec-260">例如，若要讓 CDN 能夠裝載 .css 和 .png 檔案，您可以輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="5ebec-261">若要查看 CDN 目前允許的檔案類型，請使用 **SPOTenantCdnPolicies** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5ebec-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="5ebec-262">如需這些 Cmdlet 的詳細資訊，請參閱 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) 和 [SPOTenantCdnPolicies](/powershell/module/sharepoint-online/)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="5ebec-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="5ebec-264">變更您想要從 Office 365 CDN 中排除的網站分類清單 (選用) </span><span class="sxs-lookup"><span data-stu-id="5ebec-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="5ebec-265">當您使用 **SPOTenantCdnPolicy** 指令程式排除網站分類時，會覆寫目前定義的清單。</span><span class="sxs-lookup"><span data-stu-id="5ebec-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="5ebec-266">如果您想要排除其他網站分類，請先使用 Cmdlet 來找出已排除的分類，然後將其新增至新的分類。</span><span class="sxs-lookup"><span data-stu-id="5ebec-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="5ebec-267">使用 **SPOTenantCdnPolicy 指令程式** 來排除您不想透過 CDN 使用的網站分類。</span><span class="sxs-lookup"><span data-stu-id="5ebec-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="5ebec-268">根據預設，不會排除任何網站分類。</span><span class="sxs-lookup"><span data-stu-id="5ebec-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="5ebec-269">在 Windows PowerShell 中 SharePoint Online：</span><span class="sxs-lookup"><span data-stu-id="5ebec-269">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="5ebec-270">若要查看目前限制的網站分類，請使用 **SPOTenantCdnPolicies** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5ebec-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="5ebec-271">將傳回的屬性為 _IncludeFileExtensions_、 _ExcludeRestrictedSiteClassifications_ 及 _ExcludeIfNoScriptDisabled_。</span><span class="sxs-lookup"><span data-stu-id="5ebec-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="5ebec-272">_IncludeFileExtensions_ 屬性包含將從 CDN 提供服務的副檔名清單。</span><span class="sxs-lookup"><span data-stu-id="5ebec-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="5ebec-273">預設副檔名在 public 和 private 之間是不同的。</span><span class="sxs-lookup"><span data-stu-id="5ebec-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="5ebec-274">_ExcludeRestrictedSiteClassifications_ 屬性包含您要從 CDN 中排除的網站分類。</span><span class="sxs-lookup"><span data-stu-id="5ebec-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="5ebec-275">例如，您可以排除標示為 **機密** 的網站，以便不會從 CDN 為已套用分類的網站提供內容。</span><span class="sxs-lookup"><span data-stu-id="5ebec-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="5ebec-276">_ExcludeIfNoScriptDisabled_ 屬性會根據網站層級 _NoScript_ 屬性設定，排除 CDN 的內容。</span><span class="sxs-lookup"><span data-stu-id="5ebec-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="5ebec-277">根據預設，會將 _NoScript_ 屬性設定為 _新式_ 網站 **啟用**，並針對 _傳統_ 網站 **停用**。</span><span class="sxs-lookup"><span data-stu-id="5ebec-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="5ebec-278">這取決於您的租使用者設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="5ebec-279">如需這些 Cmdlet 的詳細資訊，請參閱 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) 和 [SPOTenantCdnPolicies](/powershell/module/sharepoint-online/)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="5ebec-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="5ebec-281">新增資產來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-281">Add an origin for your assets</span></span>

<span data-ttu-id="5ebec-282">使用 **SPOTenantCdnOrigin 指令程式** 來定義原點。</span><span class="sxs-lookup"><span data-stu-id="5ebec-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="5ebec-283">您可以定義多個來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-283">You can define multiple origins.</span></span> <span data-ttu-id="5ebec-284">來源是指向包含您要由 CDN 主控之資產的 SharePoint 文件庫或資料夾的 URL。</span><span class="sxs-lookup"><span data-stu-id="5ebec-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5ebec-285">您絕對不應該放置包含使用者資訊或被視為對您的組織敏感的公用來源中的資源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="5ebec-286">_Path_ 的值是包含資產之文件庫或資料夾的相對路徑。</span><span class="sxs-lookup"><span data-stu-id="5ebec-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="5ebec-287">除了相對路徑之外，您還可以使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="5ebec-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="5ebec-288">來源支援在 URL 前面加上萬用字元。</span><span class="sxs-lookup"><span data-stu-id="5ebec-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="5ebec-289">這可讓您建立跨越多個網站的來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="5ebec-290">例如，若要將所有網站的所有資產都包含在 CDN 中的公用來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="5ebec-291">萬用字元修飾符 \* **/** 只能在路徑的開頭使用，而且會比對指定之 url 底下的所有 URL 段。</span><span class="sxs-lookup"><span data-stu-id="5ebec-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="5ebec-292">路徑可以指向文件庫、資料夾或網站。</span><span class="sxs-lookup"><span data-stu-id="5ebec-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="5ebec-293">例如，路徑 _\*/site1_ 會比對網站底下的所有文件庫。</span><span class="sxs-lookup"><span data-stu-id="5ebec-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="5ebec-294">您可以使用特定的相對路徑來新增原點。</span><span class="sxs-lookup"><span data-stu-id="5ebec-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="5ebec-295">您無法使用完整路徑新增原點。</span><span class="sxs-lookup"><span data-stu-id="5ebec-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="5ebec-296">在這個範例中，會在特定網站上新增 siteassets 程式庫的私人來源：</span><span class="sxs-lookup"><span data-stu-id="5ebec-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="5ebec-297">在這個範例中，會在網站集合的網站資產庫中新增 _folder1_ 資料夾的私人來源：</span><span class="sxs-lookup"><span data-stu-id="5ebec-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="5ebec-298">如果路徑中有空格，您可以使用雙引號括住路徑，也可以使用 URL 編碼 %20 取代空格。</span><span class="sxs-lookup"><span data-stu-id="5ebec-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="5ebec-299">下列範例會在網站集合的 [網站資產] 文件庫中新增 _資料夾 1_ 資料夾的私人來源：</span><span class="sxs-lookup"><span data-stu-id="5ebec-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="5ebec-300">如需此命令及其語法的詳細資訊，請參閱 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="5ebec-301">在 [私人來源] 中，從來源共用的資產必須先發行主要版本，然後才能從 CDN 存取。</span><span class="sxs-lookup"><span data-stu-id="5ebec-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="5ebec-302">當您執行此命令之後，系統會同步處理整個資料中心的設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="5ebec-303">這最多可能需要15分鐘。</span><span class="sxs-lookup"><span data-stu-id="5ebec-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="5ebec-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="5ebec-305">範例：針對線上 SharePoint 設定主版頁面和樣式庫的公開來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="5ebec-306">一般來說，當您啟用 Office 365 CDN 時，會預設為您設定這些來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="5ebec-307">不過，如果您想要手動啟用它們，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="5ebec-307">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="5ebec-308">使用 **SPOTenantCdnOrigin 指令程式** ，將樣式庫定義為公用來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="5ebec-309">使用 **SPOTenantCdnOrigin 指令程式** ，將主版頁面定義為公用來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="5ebec-310">如需此命令及其語法的詳細資訊，請參閱 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="5ebec-311">當您執行此命令之後，系統會同步處理整個資料中心的設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="5ebec-312">這最多可能需要15分鐘。</span><span class="sxs-lookup"><span data-stu-id="5ebec-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="5ebec-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="5ebec-314">範例：針對線上 SharePoint 設定網站資產、網站頁面及發佈影像的私人來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="5ebec-315">使用 **SPOTenantCdnOrigin 指令程式** ，將「網站資產」資料夾定義為專用來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="5ebec-316">使用 **SPOTenantCdnOrigin 指令程式** ，將「網站頁面」資料夾定義為專用來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="5ebec-317">使用 **SPOTenantCdnOrigin 指令程式** ，將 [發佈影像] 資料夾定義為專用來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="5ebec-318">如需此命令及其語法的詳細資訊，請參閱 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="5ebec-319">當您執行此命令之後，系統會同步處理整個資料中心的設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="5ebec-320">這最多可能需要15分鐘。</span><span class="sxs-lookup"><span data-stu-id="5ebec-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="5ebec-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="5ebec-322">範例：設定 SharePoint Online 之網站集合的私人來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="5ebec-323">使用 **SPOTenantCdnOrigin 指令程式** ，將網站集合定義為私人來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="5ebec-324">例如：</span><span class="sxs-lookup"><span data-stu-id="5ebec-324">For example:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="5ebec-325">如需此命令及其語法的詳細資訊，請參閱 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>
  
<span data-ttu-id="5ebec-326">當您執行此命令之後，系統會同步處理整個資料中心的設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="5ebec-327">在連線至 CDN 服務的 SharePoint Online 租使用者時，您可能會看到預期的設定 _擱置_ 郵件。</span><span class="sxs-lookup"><span data-stu-id="5ebec-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="5ebec-328">這最多可能需要15分鐘。</span><span class="sxs-lookup"><span data-stu-id="5ebec-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="5ebec-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="5ebec-330">管理 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-331">在您設定 CDN 後，您可以在更新內容或需要變更時變更設定，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="5ebec-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="5ebec-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="5ebec-333">新增、更新或移除 Office 365 CDN 中的資產</span><span class="sxs-lookup"><span data-stu-id="5ebec-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-334">完成設定步驟之後，您就可以新增資產，並隨時更新或移除現有的資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="5ebec-335">您只需對您識別為原產地的資料夾或 SharePoint 文件庫中的資產進行變更。</span><span class="sxs-lookup"><span data-stu-id="5ebec-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="5ebec-336">如果您新增資產，可立即透過 CDN 使用。</span><span class="sxs-lookup"><span data-stu-id="5ebec-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="5ebec-337">不過，如果您更新資產，最多需要15分鐘的時間，新的副本才會傳播並變得可用於 CDN。</span><span class="sxs-lookup"><span data-stu-id="5ebec-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="5ebec-338">如果您需要取得原始位置，您可以使用 **SPOTenantCdnOrigins** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ebec-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="5ebec-339">如需如何使用此 Cmdlet 的詳細資訊，請參閱 [SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="5ebec-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="5ebec-341">從 Office 365 CDN 移除原產地</span><span class="sxs-lookup"><span data-stu-id="5ebec-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-342">您可以移除您識別為原產地的資料夾或 SharePoint 程式庫的存取權。</span><span class="sxs-lookup"><span data-stu-id="5ebec-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="5ebec-343">若要這麼做，請使用 **SPOTenantCdnOrigin** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ebec-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="5ebec-344">如需如何使用此 Cmdlet 的詳細資訊，請參閱 [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="5ebec-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="5ebec-346">在 Office 365 CDN 中修改來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-347">您無法修改您已建立的來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="5ebec-348">請改為移除原始位置，然後新增一個新的位置。</span><span class="sxs-lookup"><span data-stu-id="5ebec-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="5ebec-349">如需詳細資訊，請參閱 [從 Office 365 CDN 移除原點](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) 及 [新增資產來源](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="5ebec-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="5ebec-351">停用 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-352">使用 **SPOTenantCdnEnabled 指令程式** 為您的組織停用 CDN。</span><span class="sxs-lookup"><span data-stu-id="5ebec-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="5ebec-353">如果您已啟用 CDN 的公開和私人來源，則需要執行 Cmdlet 兩次，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="5ebec-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="5ebec-354">若要停用 CDN 中的公用來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-354">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="5ebec-355">若要停用 CDN 中的私人來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="5ebec-356">如需此 Cmdlet 的詳細資訊，請參閱 [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="5ebec-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="5ebec-358">使用 PnP 來設定及設定 Office 365 CDN PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ebec-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="5ebec-359">本節中的程式需要您使用 PnP PowerShell 連線至 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="5ebec-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="5ebec-360">如需相關指示，請參閱 [PnP PowerShell 快速](https://github.com/SharePoint/PnP-PowerShell#getting-started)入門。</span><span class="sxs-lookup"><span data-stu-id="5ebec-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="5ebec-361">完成這些步驟，使用 PnP PowerShell，設定並設定 CDN，以在 SharePoint 線上中主控您的資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="5ebec-362">按一下以展開</span><span class="sxs-lookup"><span data-stu-id="5ebec-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="5ebec-363">讓您的組織使用 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-364">在您變更租使用者 CDN 設定之前，您應該先在 Office 365 租使用者中取得私人 CDN 設定的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="5ebec-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="5ebec-365">使用 PnP 連接至您的租使用者 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5ebec-365">Connect to your tenant using PnP PowerShell:</span></span>

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="5ebec-366">現在使用 **PnPTenantCdnEnabled 指令程式** ，從租使用者中取得 CDN 狀態設定：</span><span class="sxs-lookup"><span data-stu-id="5ebec-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="5ebec-367">指定之 CdnType 的 CDN 狀態會輸出至螢幕。</span><span class="sxs-lookup"><span data-stu-id="5ebec-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="5ebec-368">使用 **PnPTenantCdnEnabled** Cmdlet 可讓您的組織使用 OFFICE 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="5ebec-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="5ebec-369">您可以讓組織同時使用公用來源、私人來源或兩者同時使用。</span><span class="sxs-lookup"><span data-stu-id="5ebec-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="5ebec-370">您也可以設定 CDN，在啟用時略過預設來源的設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="5ebec-371">您可以隨時依照本主題所述新增這些來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-371">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="5ebec-372">PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5ebec-372">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="5ebec-373">例如，若要讓您的組織同時使用公用和私人來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="5ebec-374">若要讓您的組織同時使用公用和私人來源，但略過設定預設來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="5ebec-375">請參閱 [預設 CDN 來源](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) ，以取得啟用 OFFICE 365 CDN 時預設會布建之來源的相關資訊，以及略過設定預設來源的潛在影響。</span><span class="sxs-lookup"><span data-stu-id="5ebec-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="5ebec-376">若要讓您的組織使用公用來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-376">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="5ebec-377">若要讓您的組織使用私人來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-377">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="5ebec-378">如需此 Cmdlet 的詳細資訊，請參閱 [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="5ebec-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="5ebec-380">變更要包含在 Office 365 CDN (選用) 中的檔案類型清單</span><span class="sxs-lookup"><span data-stu-id="5ebec-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="5ebec-381">當您使用 **PnPTenantCdnPolicy** 指令程式來定義檔案類型時，會覆寫目前定義的清單。</span><span class="sxs-lookup"><span data-stu-id="5ebec-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="5ebec-382">如果您想要將其他檔案類型新增至清單，請先使用 Cmdlet 來找出已允許的檔案類型，並將其包含在清單中，以及新的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="5ebec-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="5ebec-383">使用 **PnPTenantCdnPolicy 指令程式** ，定義可由 CDN 中的公用和私人來源主控的靜態檔案類型。</span><span class="sxs-lookup"><span data-stu-id="5ebec-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="5ebec-384">根據預設，允許一般資產類型，例如 .css、.gif、.jpg 和 .js。</span><span class="sxs-lookup"><span data-stu-id="5ebec-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="5ebec-385">PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5ebec-385">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="5ebec-386">例如，若要讓 CDN 能夠裝載 .css 和 .png 檔案，您可以輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="5ebec-387">若要查看 CDN 目前允許的檔案類型，請使用 **PnPTenantCdnPolicies** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5ebec-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="5ebec-388">如需這些 Cmdlet 的詳細資訊，請參閱 [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) 和 [PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="5ebec-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="5ebec-390">變更您想要從 Office 365 CDN 中排除的網站分類清單 (選用) </span><span class="sxs-lookup"><span data-stu-id="5ebec-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="5ebec-391">當您使用 **PnPTenantCdnPolicy** 指令程式排除網站分類時，會覆寫目前定義的清單。</span><span class="sxs-lookup"><span data-stu-id="5ebec-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="5ebec-392">如果您想要排除其他網站分類，請先使用 Cmdlet 來找出已排除的分類，然後將其新增至新的分類。</span><span class="sxs-lookup"><span data-stu-id="5ebec-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="5ebec-393">使用 **PnPTenantCdnPolicy 指令程式** 來排除您不想透過 CDN 使用的網站分類。</span><span class="sxs-lookup"><span data-stu-id="5ebec-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="5ebec-394">根據預設，不會排除任何網站分類。</span><span class="sxs-lookup"><span data-stu-id="5ebec-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="5ebec-395">PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5ebec-395">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="5ebec-396">若要查看目前限制的網站分類，請使用 **PnPTenantCdnPolicies** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5ebec-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="5ebec-397">將傳回的屬性為 _IncludeFileExtensions_、 _ExcludeRestrictedSiteClassifications_ 及 _ExcludeIfNoScriptDisabled_。</span><span class="sxs-lookup"><span data-stu-id="5ebec-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="5ebec-398">_IncludeFileExtensions_ 屬性包含將從 CDN 提供服務的副檔名清單。</span><span class="sxs-lookup"><span data-stu-id="5ebec-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="5ebec-399">預設副檔名在 public 和 private 之間是不同的。</span><span class="sxs-lookup"><span data-stu-id="5ebec-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="5ebec-400">_ExcludeRestrictedSiteClassifications_ 屬性包含您要從 CDN 中排除的網站分類。</span><span class="sxs-lookup"><span data-stu-id="5ebec-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="5ebec-401">例如，您可以排除標示為 **機密** 的網站，以便不會從 CDN 為已套用分類的網站提供內容。</span><span class="sxs-lookup"><span data-stu-id="5ebec-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="5ebec-402">_ExcludeIfNoScriptDisabled_ 屬性會根據網站層級 _NoScript_ 屬性設定，排除 CDN 的內容。</span><span class="sxs-lookup"><span data-stu-id="5ebec-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="5ebec-403">根據預設，會將 _NoScript_ 屬性設定為 _新式_ 網站 **啟用**，並針對 _傳統_ 網站 **停用**。</span><span class="sxs-lookup"><span data-stu-id="5ebec-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="5ebec-404">這取決於您的租使用者設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="5ebec-405">如需這些 Cmdlet 的詳細資訊，請參閱 [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) 和 [PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="5ebec-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="5ebec-407">新增資產來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-407">Add an origin for your assets</span></span>

<span data-ttu-id="5ebec-408">使用 **PnPTenantCdnOrigin 指令程式** 來定義原點。</span><span class="sxs-lookup"><span data-stu-id="5ebec-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="5ebec-409">您可以定義多個來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-409">You can define multiple origins.</span></span> <span data-ttu-id="5ebec-410">來源是指向包含您要由 CDN 主控之資產的 SharePoint 文件庫或資料夾的 URL。</span><span class="sxs-lookup"><span data-stu-id="5ebec-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5ebec-411">您絕對不應該放置包含使用者資訊或被視為對您的組織敏感的公用來源中的資源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="5ebec-412">_Path_ 的值是包含資產之文件庫或資料夾的相對路徑。</span><span class="sxs-lookup"><span data-stu-id="5ebec-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="5ebec-413">除了相對路徑之外，您還可以使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="5ebec-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="5ebec-414">來源支援在 URL 前面加上萬用字元。</span><span class="sxs-lookup"><span data-stu-id="5ebec-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="5ebec-415">這可讓您建立跨越多個網站的來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="5ebec-416">例如，若要將所有網站的所有資產都包含在 CDN 中的公用來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="5ebec-417">萬用字元修飾符 \* **/** 只能在路徑的開頭使用，而且會比對指定之 url 底下的所有 URL 段。</span><span class="sxs-lookup"><span data-stu-id="5ebec-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="5ebec-418">路徑可以指向文件庫、資料夾或網站。</span><span class="sxs-lookup"><span data-stu-id="5ebec-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="5ebec-419">例如，路徑 _\*/site1_ 會比對網站底下的所有文件庫。</span><span class="sxs-lookup"><span data-stu-id="5ebec-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="5ebec-420">您可以使用特定的相對路徑來新增原點。</span><span class="sxs-lookup"><span data-stu-id="5ebec-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="5ebec-421">您無法使用完整路徑新增原點。</span><span class="sxs-lookup"><span data-stu-id="5ebec-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="5ebec-422">本範例會在特定網站上新增網站資產庫的私人來源：</span><span class="sxs-lookup"><span data-stu-id="5ebec-422">This example adds a private origin of the site assets library on a specific site:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="5ebec-423">在這個範例中，會在網站集合的網站資產庫中新增 _folder1_ 資料夾的私人來源：</span><span class="sxs-lookup"><span data-stu-id="5ebec-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="5ebec-424">如果路徑中有空格，您可以使用雙引號括住路徑，也可以使用 URL 編碼 %20 取代空格。</span><span class="sxs-lookup"><span data-stu-id="5ebec-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="5ebec-425">下列範例會在網站集合的 [網站資產] 文件庫中新增 _資料夾 1_ 資料夾的私人來源：</span><span class="sxs-lookup"><span data-stu-id="5ebec-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="5ebec-426">如需此命令及其語法的詳細資訊，請參閱 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="5ebec-427">在 [私人來源] 中，從來源共用的資產必須先發行主要版本，然後才能從 CDN 存取。</span><span class="sxs-lookup"><span data-stu-id="5ebec-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="5ebec-428">當您執行此命令之後，系統會同步處理整個資料中心的設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="5ebec-429">這最多可能需要15分鐘。</span><span class="sxs-lookup"><span data-stu-id="5ebec-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="5ebec-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="5ebec-431">範例：針對線上 SharePoint 設定主版頁面和樣式庫的公開來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="5ebec-432">一般來說，當您啟用 Office 365 CDN 時，會預設為您設定這些來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="5ebec-433">不過，如果您想要手動啟用它們，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="5ebec-433">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="5ebec-434">使用 **PnPTenantCdnOrigin 指令程式** ，將樣式庫定義為公用來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="5ebec-435">使用 **PnPTenantCdnOrigin 指令程式** ，將主版頁面定義為公用來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="5ebec-436">如需此命令及其語法的詳細資訊，請參閱 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="5ebec-437">當您執行此命令之後，系統會同步處理整個資料中心的設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="5ebec-438">這最多可能需要15分鐘。</span><span class="sxs-lookup"><span data-stu-id="5ebec-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="5ebec-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="5ebec-440">範例：針對線上 SharePoint 設定網站資產、網站頁面及發佈影像的私人來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="5ebec-441">使用 **PnPTenantCdnOrigin 指令程式** ，將「網站資產」資料夾定義為專用來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="5ebec-442">使用 **PnPTenantCdnOrigin 指令程式** ，將「網站頁面」資料夾定義為專用來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="5ebec-443">使用 **PnPTenantCdnOrigin 指令程式** ，將 [發佈影像] 資料夾定義為專用來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="5ebec-444">如需此命令及其語法的詳細資訊，請參閱 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="5ebec-445">當您執行此命令之後，系統會同步處理整個資料中心的設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="5ebec-446">這最多可能需要15分鐘。</span><span class="sxs-lookup"><span data-stu-id="5ebec-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="5ebec-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="5ebec-448">範例：設定 SharePoint Online 之網站集合的私人來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="5ebec-449">使用 **PnPTenantCdnOrigin 指令程式** ，將網站集合定義為私人來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="5ebec-450">例如：</span><span class="sxs-lookup"><span data-stu-id="5ebec-450">For example:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="5ebec-451">如需此命令及其語法的詳細資訊，請參閱 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="5ebec-452">當您執行此命令之後，系統會同步處理整個資料中心的設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="5ebec-453">在連線至 CDN 服務的 SharePoint Online 租使用者時，您可能會看到預期的設定 _擱置_ 郵件。</span><span class="sxs-lookup"><span data-stu-id="5ebec-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="5ebec-454">這最多可能需要15分鐘。</span><span class="sxs-lookup"><span data-stu-id="5ebec-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="5ebec-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="5ebec-456">管理 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-457">在您設定 CDN 後，您可以在更新內容或需要變更時變更設定，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="5ebec-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="5ebec-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="5ebec-459">新增、更新或移除 Office 365 CDN 中的資產</span><span class="sxs-lookup"><span data-stu-id="5ebec-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-460">完成設定步驟之後，您就可以新增資產，並隨時更新或移除現有的資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="5ebec-461">您只需對您識別為原產地的資料夾或 SharePoint 文件庫中的資產進行變更。</span><span class="sxs-lookup"><span data-stu-id="5ebec-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="5ebec-462">如果您新增資產，可立即透過 CDN 使用。</span><span class="sxs-lookup"><span data-stu-id="5ebec-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="5ebec-463">不過，如果您更新資產，最多需要15分鐘的時間，新的副本才會傳播並變得可用於 CDN。</span><span class="sxs-lookup"><span data-stu-id="5ebec-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="5ebec-464">如果您需要取得原始位置，您可以使用 **PnPTenantCdnOrigin** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ebec-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="5ebec-465">如需如何使用此 Cmdlet 的詳細資訊，請參閱 [PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="5ebec-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="5ebec-467">從 Office 365 CDN 移除原產地</span><span class="sxs-lookup"><span data-stu-id="5ebec-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-468">您可以移除您識別為原產地的資料夾或 SharePoint 程式庫的存取權。</span><span class="sxs-lookup"><span data-stu-id="5ebec-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="5ebec-469">若要這麼做，請使用 **PnPTenantCdnOrigin** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ebec-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="5ebec-470">如需如何使用此 Cmdlet 的詳細資訊，請參閱 [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="5ebec-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="5ebec-472">在 Office 365 CDN 中修改來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-473">您無法修改您已建立的來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="5ebec-474">請改為移除原始位置，然後新增一個新的位置。</span><span class="sxs-lookup"><span data-stu-id="5ebec-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="5ebec-475">如需詳細資訊，請參閱 [從 Office 365 CDN 移除原點](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) 及 [新增資產來源](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="5ebec-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="5ebec-477">停用 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-478">使用 **PnPTenantCdnEnabled 指令程式** 為您的組織停用 CDN。</span><span class="sxs-lookup"><span data-stu-id="5ebec-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="5ebec-479">如果您已啟用 CDN 的公開和私人來源，則需要執行 Cmdlet 兩次，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="5ebec-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="5ebec-480">若要停用 CDN 中的公用來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-480">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="5ebec-481">若要停用 CDN 中的私人來源，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ebec-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="5ebec-482">如需此 Cmdlet 的詳細資訊，請參閱 [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="5ebec-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="5ebec-484">使用 Office 365 CLI 安裝和設定 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="5ebec-485">本節中的程式需要您已安裝 [Office 365 CLI](https://aka.ms/o365cli)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="5ebec-486">接下來，使用 [登](https://pnp.github.io/office365-cli/cmd/login/) 入命令連線到您的 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="5ebec-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="5ebec-487">完成這些步驟，使用 Office 365 CLI，設定並設定 CDN，以在 SharePoint Online 中主控您的資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="5ebec-488">按一下以展開</span><span class="sxs-lookup"><span data-stu-id="5ebec-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="5ebec-489">啟用 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-490">您可以使用 [spo CDN 組](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) 命令，在租使用者中管理 OFFICE 365 CDN 的狀態。</span><span class="sxs-lookup"><span data-stu-id="5ebec-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="5ebec-491">若要在租使用者中啟用 Office 365 公用 CDN，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="5ebec-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```sh
spo cdn set --type Public --enabled true
```

<span data-ttu-id="5ebec-492">若要啟用 Office 365 SharePoint CDN，請執行：</span><span class="sxs-lookup"><span data-stu-id="5ebec-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="5ebec-493">查看 Office 365 CDN 的目前狀態</span><span class="sxs-lookup"><span data-stu-id="5ebec-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-494">若要檢查是否已啟用或停用特定類型的 Office 365 CDN，請使用 [spo CDN get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) 命令。</span><span class="sxs-lookup"><span data-stu-id="5ebec-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="5ebec-495">若要檢查是否已啟用 Office 365 公用 CDN，請執行：</span><span class="sxs-lookup"><span data-stu-id="5ebec-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="5ebec-496">查看 Office 365 CDN 來源</span><span class="sxs-lookup"><span data-stu-id="5ebec-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="5ebec-497">若要查看目前設定的 Office 365 公用 CDN 來源執行：</span><span class="sxs-lookup"><span data-stu-id="5ebec-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```sh
spo cdn origin list --type Public
```

<span data-ttu-id="5ebec-498">請參閱 [預設 CDN 來源](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) ，以取得啟用 OFFICE 365 CDN 時預設會提供之來源的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5ebec-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="5ebec-499">新增 Office 365 CDN 原始</span><span class="sxs-lookup"><span data-stu-id="5ebec-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ebec-500">在設定為公用來源的 SharePoint 文件庫中，絕對不應將被視為敏感的資源放入組織中。</span><span class="sxs-lookup"><span data-stu-id="5ebec-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="5ebec-501">使用 [spo cdn 原始的 add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) 命令來定義 cdn 來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="5ebec-502">您可以定義多個來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-502">You can define multiple origins.</span></span> <span data-ttu-id="5ebec-503">來源是指向包含您要由 CDN 主控之資產的 SharePoint 文件庫或資料夾的 URL。</span><span class="sxs-lookup"><span data-stu-id="5ebec-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="5ebec-504">其中 `path` 是包含資產之資料夾的相對路徑。</span><span class="sxs-lookup"><span data-stu-id="5ebec-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="5ebec-505">除了相對路徑之外，您還可以使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="5ebec-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="5ebec-506">若要將所有網站的 **主版頁面圖庫** 中的所有資產都包含為公用來源，請執行：</span><span class="sxs-lookup"><span data-stu-id="5ebec-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```sh
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="5ebec-507">若要設定特定網站集合的私人來源，請執行：</span><span class="sxs-lookup"><span data-stu-id="5ebec-507">To configure a private origin for a specific site collection, execute:</span></span>

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="5ebec-508">新增 CDN 來源後，最多可能需要15分鐘的時間，您才可以透過 CDN 服務來取得檔案。</span><span class="sxs-lookup"><span data-stu-id="5ebec-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="5ebec-509">您可以使用 [spo cdn 原始清單](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 命令，確認是否已啟用特定來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="5ebec-510">移除 Office 365 CDN 原始</span><span class="sxs-lookup"><span data-stu-id="5ebec-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="5ebec-511">使用 [spo cdn 原始移除](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) 命令，為指定的 cdn 類型移除 cdn 來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="5ebec-512">若要從 CDN 設定移除公用來源，請執行：</span><span class="sxs-lookup"><span data-stu-id="5ebec-512">To remove a public origin from the CDN configuration, execute:</span></span>

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="5ebec-513">移除 CDN 原始檔不會影響與該來源相符的任何文件庫中儲存的檔案。</span><span class="sxs-lookup"><span data-stu-id="5ebec-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="5ebec-514">如果這些資產已使用 SharePoint URL 參考，SharePoint 會自動切換回指向文件庫的原始 URL。</span><span class="sxs-lookup"><span data-stu-id="5ebec-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="5ebec-515">不過，如果資產已使用公用 CDN URL 參考，則移除該來源會中斷連結，您必須手動變更。</span><span class="sxs-lookup"><span data-stu-id="5ebec-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="5ebec-516">修改 Office 365 CDN 原始</span><span class="sxs-lookup"><span data-stu-id="5ebec-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="5ebec-517">不可能修改現有的 CDN 來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="5ebec-518">相反地，您應該使用命令移除先前定義的 CDN 來源 `spo cdn origin remove` ，並使用命令新增新的 CDN 來源 `spo cdn origin add` 。</span><span class="sxs-lookup"><span data-stu-id="5ebec-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="5ebec-519">變更要包含在 Office 365 CDN 中的檔案類型</span><span class="sxs-lookup"><span data-stu-id="5ebec-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-520">根據預設，下列檔案類型會包含在 CDN： _.css、eot、.gif、.ico、.gif、.jpg、.js、.map、.gif、.jpg、ttf、woff 和 woff2_ 中。</span><span class="sxs-lookup"><span data-stu-id="5ebec-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="5ebec-521">如果您需要在 CDN 中包含其他檔案類型，您可以使用 [spo CDN 原則組](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) 命令變更 cdn 設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="5ebec-522">變更檔案類型的清單時，會覆寫目前定義的清單。</span><span class="sxs-lookup"><span data-stu-id="5ebec-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="5ebec-523">如果您想要包含其他檔案類型，請先使用 [spo cdn 原則清單](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 命令，找出目前設定的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="5ebec-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="5ebec-524">若要將 _JSON_ 檔案類型新增至公用 CDN 中所包含之檔案類型的預設清單，請執行：</span><span class="sxs-lookup"><span data-stu-id="5ebec-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="5ebec-525">變更您要從 Office 365 CDN 中排除的網站分類清單</span><span class="sxs-lookup"><span data-stu-id="5ebec-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-526">使用 [spo cdn 原則組](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) 命令，以排除您不想讓 CDN 在 cdn 上使用的網站分類。</span><span class="sxs-lookup"><span data-stu-id="5ebec-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="5ebec-527">根據預設，不會排除任何網站分類。</span><span class="sxs-lookup"><span data-stu-id="5ebec-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="5ebec-528">變更排除的網站分類清單時，會覆寫目前定義的清單。</span><span class="sxs-lookup"><span data-stu-id="5ebec-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="5ebec-529">若要排除其他分類，請先使用 [spo cdn 原則清單](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) 命令，找出目前設定的分類。</span><span class="sxs-lookup"><span data-stu-id="5ebec-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="5ebec-530">若要從公用 CDN 中排除歸類為 _HBI_ 的網站，請執行</span><span class="sxs-lookup"><span data-stu-id="5ebec-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="5ebec-531">停用 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-532">若要停用 Office 365 CDN `spo cdn set` ，請使用命令，例如：</span><span class="sxs-lookup"><span data-stu-id="5ebec-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="5ebec-533">使用 CDN 資產</span><span class="sxs-lookup"><span data-stu-id="5ebec-533">Using your CDN assets</span></span>

<span data-ttu-id="5ebec-534">現在，您已啟用 CDN 和設定的來源及原則，您可以開始使用 CDN 資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="5ebec-535">本節將協助您瞭解如何在 SharePoint 頁面和內容中使用 CDN URLs，以 SharePoint 將公用和私人來源資產的要求重新導向至 CDN。</span><span class="sxs-lookup"><span data-stu-id="5ebec-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="5ebec-536">更新 CDN 資產的連結</span><span class="sxs-lookup"><span data-stu-id="5ebec-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="5ebec-537">使用公用來源中的資產</span><span class="sxs-lookup"><span data-stu-id="5ebec-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="5ebec-538">使用私人來源的資產</span><span class="sxs-lookup"><span data-stu-id="5ebec-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="5ebec-539">如需如何使用 CDN 來主控用戶端網頁元件的詳細資訊，請參閱 [從 Office 365 CDN (Hello World 第 4) 中的用戶端網頁元件 ](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="5ebec-540">如果您將 _ClientSideAssets_ 資料夾新增至 **私人** CDN 來源清單，則會無法轉譯 CDN 裝載的自訂網頁元件。</span><span class="sxs-lookup"><span data-stu-id="5ebec-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="5ebec-541">SPFX 網頁元件使用的檔案只能利用公用 CDN，而 ClientSideAssets 資料夾是公用 CDN 的預設來源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="5ebec-542">更新 CDN 資產的連結</span><span class="sxs-lookup"><span data-stu-id="5ebec-542">Updating links to CDN assets</span></span>

<span data-ttu-id="5ebec-543">若要使用您已新增至來源的資產，您只需以原始檔案的路徑來更新原始檔案的連結。</span><span class="sxs-lookup"><span data-stu-id="5ebec-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="5ebec-544">編輯包含您已新增至來源之資產連結的頁面或內容。</span><span class="sxs-lookup"><span data-stu-id="5ebec-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="5ebec-545">您也可以使用其中一種方法，在 [輸入網站或網站集合] 中全域搜尋和取代連結，如果您想要在任何位置更新指定資產的連結。</span><span class="sxs-lookup"><span data-stu-id="5ebec-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="5ebec-546">針對來源中資源的每個連結，以 CDN 原始檔的路徑取代路徑。</span><span class="sxs-lookup"><span data-stu-id="5ebec-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="5ebec-547">您可以使用相對路徑。</span><span class="sxs-lookup"><span data-stu-id="5ebec-547">You can use relative paths.</span></span>
+ <span data-ttu-id="5ebec-548">儲存頁面或內容。</span><span class="sxs-lookup"><span data-stu-id="5ebec-548">Save the page or content.</span></span>

<span data-ttu-id="5ebec-549">例如，請考慮您已複製到文件庫資料夾 _/site/CDN_origins/public/_ 的影像 _/site/SiteAssets/images/image.png_。</span><span class="sxs-lookup"><span data-stu-id="5ebec-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="5ebec-550">若要使用 CDN 資產，請將原始路徑取代為來源路徑的圖像檔案位置，讓新的 URL _/site/CDN_origins/public/image.png_。</span><span class="sxs-lookup"><span data-stu-id="5ebec-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="5ebec-551">如果您想要使用完整的 URL 來代替相對路徑，請建立如下的連結：</span><span class="sxs-lookup"><span data-stu-id="5ebec-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="5ebec-552">一般說來，您不應該直接對 CDN 中的資產進行硬編碼 URLs。</span><span class="sxs-lookup"><span data-stu-id="5ebec-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="5ebec-553">不過，您可以視需要，以手動方式為公用來源中的資產建立 URLs。</span><span class="sxs-lookup"><span data-stu-id="5ebec-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="5ebec-554">如需詳細資訊，請參閱 [HARDCODING CDN URLs 的公開資產](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="5ebec-555">若要瞭解如何驗證資產是否從 CDN 服務，請參閱如何在[疑難排解 Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)一節中，[確認 CDN 是由 cdn 所服務](use-microsoft-365-cdn-with-spo.md#CDNConfirm)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in the [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) section.</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="5ebec-556">使用公用來源中的資產</span><span class="sxs-lookup"><span data-stu-id="5ebec-556">Using assets in public origins</span></span>

<span data-ttu-id="5ebec-557">SharePoint Online 中的 **發佈功能** 會自動將儲存在公用來源中的資產 URLs 修正成其 CDN 對等專案，如此才能從 cdn 服務（而非 SharePoint）提供資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="5ebec-558">如果您的來源位於啟用發佈功能的網站中，且您想要將其轉移至 CDN 的資產屬於下列其中一個類別，則 SharePoint 會為來源中的資產自動重寫 URLs，但前提是該資產尚未由 CDN 原則排除。</span><span class="sxs-lookup"><span data-stu-id="5ebec-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="5ebec-559">以下是 SharePoint 發佈功能會自動重新寫入連結的概覽：</span><span class="sxs-lookup"><span data-stu-id="5ebec-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="5ebec-560">傳統發佈頁面 HTML 回應中的 IMG/LINK/CSS URLs</span><span class="sxs-lookup"><span data-stu-id="5ebec-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="5ebec-561">這包括網頁的 HTML 內容中作者所新增的影像</span><span class="sxs-lookup"><span data-stu-id="5ebec-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="5ebec-562">圖片庫幻燈片] 網頁元件影像 URLs</span><span class="sxs-lookup"><span data-stu-id="5ebec-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="5ebec-563">SPList REST API (RenderListDataAsStream) 結果中的影像欄位</span><span class="sxs-lookup"><span data-stu-id="5ebec-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="5ebec-564">使用新屬性 _ImageFieldsToTryRewriteToCdnUrls_ 提供以逗號分隔的欄位清單</span><span class="sxs-lookup"><span data-stu-id="5ebec-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="5ebec-565">支援 hyperlink 欄位及 PublishingImage 欄位</span><span class="sxs-lookup"><span data-stu-id="5ebec-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="5ebec-566">SharePoint 影像轉譯</span><span class="sxs-lookup"><span data-stu-id="5ebec-566">SharePoint image renditions</span></span>

<span data-ttu-id="5ebec-567">下圖說明 SharePoint 接收公用來源中包含資產之頁面的要求時的工作流程。</span><span class="sxs-lookup"><span data-stu-id="5ebec-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="5ebec-568">![工作流程圖表：從公用來源檢索 Office 365 CDN 資產](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "工作流程：從公用來源檢索 Office 365 CDN 資產")</span><span class="sxs-lookup"><span data-stu-id="5ebec-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="5ebec-569">如果您想要對頁面上的特定 URLs 停用自動重新寫入，您可以取出頁面並新增查詢字串參數 **？NoAutoReWrites = true** 表示您要停用的每個連結的結尾。</span><span class="sxs-lookup"><span data-stu-id="5ebec-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="5ebec-570">為公用資產建立 CDN URLs</span><span class="sxs-lookup"><span data-stu-id="5ebec-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="5ebec-571">如果公開來源未啟用 _發佈_ 功能，或資產並非 CDN 服務之自動重新寫入功能支援的連結類型之一，則可以手動構造資產的 cdn 位置的 URLs，並在內容中使用這些 URLs。</span><span class="sxs-lookup"><span data-stu-id="5ebec-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="5ebec-572">您無法對私人來源中的資產硬編碼或建立 CDN URLs，因為在要求資源時，會產生表單最後一個區段所要求的訪問權杖。</span><span class="sxs-lookup"><span data-stu-id="5ebec-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="5ebec-573">您可以建立公用 CDN 的 URL，而 URL 不應該是變更的方式。</span><span class="sxs-lookup"><span data-stu-id="5ebec-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="5ebec-574">若為公用 CDN 資產，URL 格式會類似如下：</span><span class="sxs-lookup"><span data-stu-id="5ebec-574">For public CDN assets, the URL format will look like the following:</span></span>

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="5ebec-575">將 **TenantHostName** 取代為您的租使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="5ebec-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="5ebec-576">範例：</span><span class="sxs-lookup"><span data-stu-id="5ebec-576">Example:</span></span>

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```
> [!NOTE]
> <span data-ttu-id="5ebec-577">頁面內容屬性應該用來建立前置詞，而不是硬編碼 " https://publiccdn.sharepointonline.com "。</span><span class="sxs-lookup"><span data-stu-id="5ebec-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="5ebec-578">URL 可能會變更，而且不應該是硬式編碼。</span><span class="sxs-lookup"><span data-stu-id="5ebec-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="5ebec-579">如果您使用的顯示範本與傳統的 SharePoint 線上，您可以使用顯示範本中的屬性 "window._spPageCoNtextInfo publicCdnBaseUrl" 來輸入 URL 的首碼。</span><span class="sxs-lookup"><span data-stu-id="5ebec-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="5ebec-580">如果您要 SPFx 適用于新式和經典 SharePoint 的網頁元件，您可以使用屬性「pageCoNtext legacyPageCoNtext publicCdnBaseUrl」。</span><span class="sxs-lookup"><span data-stu-id="5ebec-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="5ebec-581">這將會提供前置詞，以便在變更後，您的實施會與其一起更新。</span><span class="sxs-lookup"><span data-stu-id="5ebec-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="5ebec-582">作為 SPFx 的範例，URL 可以使用 the the the pageCoNtext the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the</span><span class="sxs-lookup"><span data-stu-id="5ebec-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="5ebec-583">請參閱在第[1 賽季效能系列](https://aka.ms/sppnp-perfvideos)[中使用 CDN 的用戶端程式代碼](https://youtu.be/IH1RbQlbhIA)</span><span class="sxs-lookup"><span data-stu-id="5ebec-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="5ebec-584">使用私人來源的資產</span><span class="sxs-lookup"><span data-stu-id="5ebec-584">Using assets in private origins</span></span>

<span data-ttu-id="5ebec-585">若要使用私人來源的資產，不需要進行其他設定。</span><span class="sxs-lookup"><span data-stu-id="5ebec-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="5ebec-586">SharePoint 線上針對私人來源中的資產自動重寫 URLs，因此這些資產的要求永遠會從 CDN 服務。</span><span class="sxs-lookup"><span data-stu-id="5ebec-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="5ebec-587">您無法以私人來源手動建立 CDN 資產的 URLs，因為這些 URLs 包含在要求資產時 SharePoint 線上時必須自動產生的權杖。</span><span class="sxs-lookup"><span data-stu-id="5ebec-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="5ebec-588">存取私人來源資產的方法是根據原始的使用者權限，以使用者權限來保護，並在下列各節中說明的忠告。</span><span class="sxs-lookup"><span data-stu-id="5ebec-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="5ebec-589">使用者必須至少具備 CDN 的「 **讀取** 」存取權，才能呈現內容。</span><span class="sxs-lookup"><span data-stu-id="5ebec-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="5ebec-590">下圖說明 SharePoint 收到來自私人來源之資產的頁面要求時的工作流程。</span><span class="sxs-lookup"><span data-stu-id="5ebec-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="5ebec-591">![工作流程圖表：從私人來源檢索 Office 365 CDN 資產](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "工作流程：從私人來源檢索 Office 365 CDN 資產")</span><span class="sxs-lookup"><span data-stu-id="5ebec-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="5ebec-592">私人來源中以權杖為基礎的授權</span><span class="sxs-lookup"><span data-stu-id="5ebec-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="5ebec-593">在 Office 365 CDN 中存取私人來源的資產是由 SharePoint Online 所產生的權杖所授。</span><span class="sxs-lookup"><span data-stu-id="5ebec-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="5ebec-594">已有權存取原始位置所指定之資料夾或文件庫的使用者，會自動授與允許使用者根據其許可權層級存取該檔案的權杖。</span><span class="sxs-lookup"><span data-stu-id="5ebec-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="5ebec-595">這些存取權杖在產生後會有效30到90分鐘，以協助防止權杖重新顯示攻擊。</span><span class="sxs-lookup"><span data-stu-id="5ebec-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="5ebec-596">當存取權杖產生之後，SharePoint 線上傳回自訂 URI 至包含兩個授權參數的用戶端，將會 _吃_ (edge authorization token) 和 _oat_ (來源授權權杖) 。</span><span class="sxs-lookup"><span data-stu-id="5ebec-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="5ebec-597">每個權杖的結構是 _以時段格式「>__< ' 安全簽名」 >< 的到期時間_。</span><span class="sxs-lookup"><span data-stu-id="5ebec-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="5ebec-598">例如：</span><span class="sxs-lookup"><span data-stu-id="5ebec-598">For example:</span></span>

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="5ebec-599">擁有該權杖的任何人都可以存取 CDN 中的資源。</span><span class="sxs-lookup"><span data-stu-id="5ebec-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="5ebec-600">不過，包含這些存取權杖的 URLs 只會透過 HTTPS 共用，除非使用者在權杖到期之前明確共用該 URL，否則無法存取未授權使用者的資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="5ebec-601">私人來源的資產不支援專案層級許可權</span><span class="sxs-lookup"><span data-stu-id="5ebec-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="5ebec-602">請務必注意，SharePoint Online 不支援私人來源資產的專案層級許可權。</span><span class="sxs-lookup"><span data-stu-id="5ebec-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="5ebec-603">例如，對於位於的檔案 `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` ，使用者會在發生下列情況時，具有檔案的有效存取權：</span><span class="sxs-lookup"><span data-stu-id="5ebec-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="5ebec-604">使用者</span><span class="sxs-lookup"><span data-stu-id="5ebec-604">User</span></span>  |<span data-ttu-id="5ebec-605">權限</span><span class="sxs-lookup"><span data-stu-id="5ebec-605">Permissions</span></span>  |<span data-ttu-id="5ebec-606">有效的存取</span><span class="sxs-lookup"><span data-stu-id="5ebec-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="5ebec-607">使用者1</span><span class="sxs-lookup"><span data-stu-id="5ebec-607">User 1</span></span>     |<span data-ttu-id="5ebec-608">可以存取 folder1</span><span class="sxs-lookup"><span data-stu-id="5ebec-608">Has access to folder1</span></span>         |<span data-ttu-id="5ebec-609">可以從 CDN 存取 image1.jpg</span><span class="sxs-lookup"><span data-stu-id="5ebec-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="5ebec-610">使用者 2</span><span class="sxs-lookup"><span data-stu-id="5ebec-610">User 2</span></span>     |<span data-ttu-id="5ebec-611">無權存取 folder1</span><span class="sxs-lookup"><span data-stu-id="5ebec-611">Does not have access to folder1</span></span>         |<span data-ttu-id="5ebec-612">無法從 CDN 存取 image1.jpg</span><span class="sxs-lookup"><span data-stu-id="5ebec-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="5ebec-613">使用者 3</span><span class="sxs-lookup"><span data-stu-id="5ebec-613">User 3</span></span>     |<span data-ttu-id="5ebec-614">無權存取 folder1，但會授與在線上 SharePoint 中存取 image1.jpg 的明確許可權。</span><span class="sxs-lookup"><span data-stu-id="5ebec-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="5ebec-615">可以直接從線上 SharePoint 存取資產 image1.jpg，但不能從 CDN 存取。</span><span class="sxs-lookup"><span data-stu-id="5ebec-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="5ebec-616">使用者 4</span><span class="sxs-lookup"><span data-stu-id="5ebec-616">User 4</span></span>     |<span data-ttu-id="5ebec-617">可以存取 folder1，但已明確拒絕 SharePoint 線上中 image1.jpg 的存取權</span><span class="sxs-lookup"><span data-stu-id="5ebec-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="5ebec-618">無法從 SharePoint 線上存取資產，但是可以存取 CDN 的資產，但不會拒絕存取 SharePoint 線上中的檔案。</span><span class="sxs-lookup"><span data-stu-id="5ebec-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="5ebec-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="5ebec-620">疑難排解 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="5ebec-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="5ebec-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="5ebec-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="5ebec-622">如何確認 CDN 是否正在服務資產？</span><span class="sxs-lookup"><span data-stu-id="5ebec-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="5ebec-623">將 CDN 資產的連結新增至頁面後，您可以流覽至頁面，在圖像呈現及檢查影像 URL 後，以滑鼠右鍵按一下，以確認資產是否正在從 CDN 服務。</span><span class="sxs-lookup"><span data-stu-id="5ebec-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="5ebec-624">您也可以使用瀏覽器的開發人員工具，查看頁面上每個資產的 URL，或使用協力廠商網路追蹤工具。</span><span class="sxs-lookup"><span data-stu-id="5ebec-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="5ebec-625">如果您使用 Fiddler 等網路工具在從 SharePoint 頁面轉譯資產之外測試資產，您必須手動將 referer 標頭 "Referer： `https://yourdomain.sharepoint.com` " 新增至 GET 要求，其中 URL 是您 SharePoint Online 租使用者的根 url。</span><span class="sxs-lookup"><span data-stu-id="5ebec-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="5ebec-626">您無法直接在網頁瀏覽器中測試 CDN URLs，因為您必須具有來自 SharePoint 線上的 referer。</span><span class="sxs-lookup"><span data-stu-id="5ebec-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="5ebec-627">不過，如果您將 CDN 資產 URL 新增至 SharePoint 頁面，然後在瀏覽器中開啟頁面，您會看到頁面上所呈現的 CDN 資產。</span><span class="sxs-lookup"><span data-stu-id="5ebec-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="5ebec-628">如需使用 Microsoft Edge browser 中的開發人員工具的詳細資訊，請參閱 [Microsoft Edge Developer tools](/microsoft-edge/devtools-guide)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="5ebec-629">若要觀看 [SharePoint 開發人員模式和作法](https://aka.ms/sppnp-videos) 中所主控的簡短影片 YouTube 通道示範如何驗證 cdn 是否正常運作，請參閱 [驗證 cdn 使用方式和確保最佳的網路連線能力](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)。</span><span class="sxs-lookup"><span data-stu-id="5ebec-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="5ebec-630">為何無法使用來自新原始來源的資產？</span><span class="sxs-lookup"><span data-stu-id="5ebec-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="5ebec-631">新的來源中的資產不會立即可供使用，因為註冊透過 CDN 傳播所需的時間，而且資產若要從來源上傳至 CDN 儲存區。</span><span class="sxs-lookup"><span data-stu-id="5ebec-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="5ebec-632">在 CDN 中提供資產所需的時間取決於多少資產和檔案大小。</span><span class="sxs-lookup"><span data-stu-id="5ebec-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="5ebec-633">我的用戶端網頁元件或 SharePoint 架構解決方案無法運作</span><span class="sxs-lookup"><span data-stu-id="5ebec-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="5ebec-634">當您為公用來源啟用 Office 365 CDN 時，CDN 服務會自動建立下列預設來源：</span><span class="sxs-lookup"><span data-stu-id="5ebec-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="5ebec-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="5ebec-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="5ebec-636">\*/STYLE 程式庫</span><span class="sxs-lookup"><span data-stu-id="5ebec-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="5ebec-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="5ebec-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="5ebec-638">如果缺少 \*/clientsideassets 原創，SharePoint 架構解決方案將會失敗，而且不會產生警告或錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="5ebec-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="5ebec-639">因為啟用 _-NoDefaultOrigins_ 參數設定為 **$true**，或已手動刪除來源，所以此來源可能遺失。</span><span class="sxs-lookup"><span data-stu-id="5ebec-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="5ebec-640">您可以使用下列 PowerShell 命令來查看存在哪些來源：</span><span class="sxs-lookup"><span data-stu-id="5ebec-640">You can check to see which origins are present with the following PowerShell command:</span></span>

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="5ebec-641">您也可以使用 Office 365 CLI 進行檢查：</span><span class="sxs-lookup"><span data-stu-id="5ebec-641">Or you can check with the Office 365 CLI:</span></span>

``` powershell
spo cdn origin list
```

<span data-ttu-id="5ebec-642">若要在 PowerShell: 中新增原點</span><span class="sxs-lookup"><span data-stu-id="5ebec-642">To add the origin in PowerShell:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="5ebec-643">若要在 Office 365 CLI 中新增來源：</span><span class="sxs-lookup"><span data-stu-id="5ebec-643">To add the origin in the Office 365 CLI:</span></span>

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="5ebec-644">我需要哪些 PowerShell 模組和 CLI shell 才能搭配 Office 365 CDN 使用？</span><span class="sxs-lookup"><span data-stu-id="5ebec-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="5ebec-645">您可以選擇使用 **SharePoint 線上管理命令** 介面 PowerShell 模組或 **Office 365 CLI** 來搭配 office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="5ebec-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="5ebec-646">開始使用 SharePoint Online 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="5ebec-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="5ebec-647">安裝 Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="5ebec-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="5ebec-648">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5ebec-648">See also</span></span>

[<span data-ttu-id="5ebec-649">內容傳遞網路</span><span class="sxs-lookup"><span data-stu-id="5ebec-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="5ebec-650">Office 365 的網路規劃和效能調整</span><span class="sxs-lookup"><span data-stu-id="5ebec-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="5ebec-651">SharePoint 效能系列-Office 365 CDN 影片系列</span><span class="sxs-lookup"><span data-stu-id="5ebec-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)