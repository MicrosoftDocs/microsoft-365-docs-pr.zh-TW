---
title: 在進階搜捕中使用共用查詢
description: 立即開始威脅搜捕，並使用預先定義的共用查詢。 將您的查詢與大眾或您的組織共用。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、自訂偵測、架構、kusto、github 儲存庫、我的查詢、共用查詢
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 78a532167e4256e3453803f1a0b4a9e4875771cf
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499430"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="535f0-105">在進階搜捕中使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="535f0-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="535f0-106">適用於：</span><span class="sxs-lookup"><span data-stu-id="535f0-106">**Applies to:**</span></span>
- [<span data-ttu-id="535f0-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="535f0-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="535f0-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="535f0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="535f0-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="535f0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="535f0-110">您可以在同一個組織的多位使用者之間共用[進階搜捕](advanced-hunting-overview.md)查詢。</span><span class="sxs-lookup"><span data-stu-id="535f0-110">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="535f0-111">您也可以在 GitHub 尋找公開的查詢。</span><span class="sxs-lookup"><span data-stu-id="535f0-111">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="535f0-112">這些查詢可讓您快速地執行特定威脅搜捕案例，而不需要從頭開始撰寫查詢。</span><span class="sxs-lookup"><span data-stu-id="535f0-112">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![共用查詢的影像](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="535f0-114">儲存、修改及共用查詢</span><span class="sxs-lookup"><span data-stu-id="535f0-114">Save, modify, and share a query</span></span>
<span data-ttu-id="535f0-115">您可以儲存新的或現有的查詢，以便只有組織中的其他使用者能存取或共用。</span><span class="sxs-lookup"><span data-stu-id="535f0-115">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span>

1. <span data-ttu-id="535f0-116">輸入新的查詢或從 [ **共用查詢** ] 或 [我的 **查詢**] 中載入現有的查詢。</span><span class="sxs-lookup"><span data-stu-id="535f0-116">Type a new query or load an existing one from under **Shared queries** or **My queries**.</span></span>

2. <span data-ttu-id="535f0-117">選取 **[儲存]** 或 [ **另** 存新檔] 選項。</span><span class="sxs-lookup"><span data-stu-id="535f0-117">Select **Save** or **Save as** from the save options.</span></span> <span data-ttu-id="535f0-118">若要避免覆寫現有的查詢，請選擇 [ **另存** 新檔]。</span><span class="sxs-lookup"><span data-stu-id="535f0-118">To avoid overwriting an existing query, choose **Save as**.</span></span>

3. <span data-ttu-id="535f0-119">輸入查詢的名稱。</span><span class="sxs-lookup"><span data-stu-id="535f0-119">Enter a name for the query.</span></span>

   ![儲存查詢的影像](images/advanced-hunting-save-query.png)

4. <span data-ttu-id="535f0-121">選取您要儲存查詢的資料夾。</span><span class="sxs-lookup"><span data-stu-id="535f0-121">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="535f0-122">**共用查詢** -共用給組織中的所有使用者</span><span class="sxs-lookup"><span data-stu-id="535f0-122">**Shared queries** — shared to all users in your organization</span></span>
    - <span data-ttu-id="535f0-123">**我的查詢** —只有您可以存取</span><span class="sxs-lookup"><span data-stu-id="535f0-123">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="535f0-124">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="535f0-124">Select **Save**.</span></span>

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="535f0-125">刪除或重新命名查詢</span><span class="sxs-lookup"><span data-stu-id="535f0-125">Delete or rename a query</span></span>
1. <span data-ttu-id="535f0-126">以滑鼠右鍵按一下您要重新命名或刪除的查詢。</span><span class="sxs-lookup"><span data-stu-id="535f0-126">Right-click on a query you want to rename or delete.</span></span>

    ![刪除查詢的影像](images/atp_advanced_hunting_delete_rename.png)

2. <span data-ttu-id="535f0-128">選取 [刪除] 並確認刪除。</span><span class="sxs-lookup"><span data-stu-id="535f0-128">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="535f0-129">或選取 [重新命名]，並為查詢提供新名稱。</span><span class="sxs-lookup"><span data-stu-id="535f0-129">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="535f0-130">建立查詢的直接連結</span><span class="sxs-lookup"><span data-stu-id="535f0-130">Create a direct link to a query</span></span>
<span data-ttu-id="535f0-131">若要產生連結，以直接在高級搜尋查詢編輯器中開啟查詢，請完成查詢並選取 [ **共用] 連結**。</span><span class="sxs-lookup"><span data-stu-id="535f0-131">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="535f0-132">存取 GitHub 儲存庫中的查詢</span><span class="sxs-lookup"><span data-stu-id="535f0-132">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="535f0-133">Microsoft 安全研究人員會定期在 [GitHub 上的指定公開儲存庫](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)中共用進階搜捕查詢。</span><span class="sxs-lookup"><span data-stu-id="535f0-133">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span> <span data-ttu-id="535f0-134">這個儲存庫開放個人提出貢獻。</span><span class="sxs-lookup"><span data-stu-id="535f0-134">This repository is open to contributions.</span></span> <span data-ttu-id="535f0-135">若要貢獻，請[免費加入 GitHub ](https://github.com/)。</span><span class="sxs-lookup"><span data-stu-id="535f0-135">To contribute, [join GitHub for free](https://github.com/).</span></span> 

>[!TIP]
><span data-ttu-id="535f0-136">Microsoft 安全研究人員也會提供進階搜捕查詢，您可以用來尋找與新興威脅相關聯的活動和指標。</span><span class="sxs-lookup"><span data-stu-id="535f0-136">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="535f0-137">這些查詢是由 Microsoft Defender 安全性中心中的[威脅分析](threat-analytics.md)報告提供。</span><span class="sxs-lookup"><span data-stu-id="535f0-137">These queries are provided as part of the [threat analytics](threat-analytics.md) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="535f0-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="535f0-138">Related topics</span></span>
- [<span data-ttu-id="535f0-139">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="535f0-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="535f0-140">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="535f0-140">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="535f0-141">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="535f0-141">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="535f0-142">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="535f0-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="535f0-143">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="535f0-143">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="535f0-144">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="535f0-144">Custom detections overview</span></span>](overview-custom-detections.md)
