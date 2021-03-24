---
title: 在 Microsoft 365 Defender advanced 搜尋中使用共用查詢
description: 立即開始威脅搜捕，並使用預先定義的共用查詢。 將您的查詢與大眾或您的組織共用。
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，自訂偵測，schema，kusto，github 儲存機制，我的查詢，共用查詢
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f153e438465d4cacf5293cd6e834e85783601c89
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056693"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="9a9f2-105">在進階搜捕中使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="9a9f2-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9a9f2-106">適用於：</span><span class="sxs-lookup"><span data-stu-id="9a9f2-106">**Applies to:**</span></span>
- <span data-ttu-id="9a9f2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a9f2-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="9a9f2-108">您可以在同一個組織的多位使用者之間共用[進階搜捕](advanced-hunting-overview.md)查詢。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="9a9f2-109">您也可以在 GitHub 尋找公開的查詢。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="9a9f2-110">這些查詢可讓您快速地執行特定威脅搜捕案例，而不需要從頭開始撰寫查詢。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![共用查詢的影像](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="9a9f2-112">儲存、修改及共用查詢</span><span class="sxs-lookup"><span data-stu-id="9a9f2-112">Save, modify, and share a query</span></span>
<span data-ttu-id="9a9f2-113">您可以儲存新的或現有的查詢，以便只有組織中的其他使用者能存取或共用。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="9a9f2-114">建立或修改查詢。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="9a9f2-115">按一下 [儲存查詢] 下拉式按鈕，然後選取 [另存新檔]。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="9a9f2-116">輸入查詢的名稱。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-116">Enter a name for the query.</span></span> 

   ![儲存查詢的影像](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="9a9f2-118">選取您要儲存查詢的資料夾。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="9a9f2-119">**共用的查詢** — 與組織的所有使用者共用</span><span class="sxs-lookup"><span data-stu-id="9a9f2-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="9a9f2-120">**我的查詢** —只有您可以存取</span><span class="sxs-lookup"><span data-stu-id="9a9f2-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="9a9f2-121">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="9a9f2-122">刪除或重新命名查詢</span><span class="sxs-lookup"><span data-stu-id="9a9f2-122">Delete or rename a query</span></span>
1. <span data-ttu-id="9a9f2-123">以滑鼠右鍵按一下您要重新命名或刪除的查詢。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-123">Right-click on a query you want to rename or delete.</span></span>

    ![刪除查詢的影像](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="9a9f2-125">選取 [刪除] 並確認刪除。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="9a9f2-126">或選取 [重新命名]，並為查詢提供新名稱。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="9a9f2-127">建立查詢的直接連結</span><span class="sxs-lookup"><span data-stu-id="9a9f2-127">Create a direct link to a query</span></span>
<span data-ttu-id="9a9f2-128">若要產生連結，以直接在高級搜尋查詢編輯器中開啟查詢，請完成查詢並選取 [ **共用] 連結**。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="9a9f2-129">存取 GitHub 儲存庫中的查詢</span><span class="sxs-lookup"><span data-stu-id="9a9f2-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="9a9f2-130">Microsoft 安全研究人員會定期在 [GitHub 上的指定公開儲存庫](https://aka.ms/hunting-queries)中共用進階搜捕查詢。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="9a9f2-131">這個儲存庫開放個人提出貢獻。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-131">This repository is open to contributions.</span></span> <span data-ttu-id="9a9f2-132">若要貢獻，請[免費加入 GitHub ](https://github.com/)。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="9a9f2-133">Microsoft 安全研究人員也會提供進階搜捕查詢，您可以用來尋找與新興威脅相關聯的活動和指標。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="9a9f2-134">這些查詢是由 Microsoft Defender 安全性中心中的[威脅分析](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)報告提供。</span><span class="sxs-lookup"><span data-stu-id="9a9f2-134">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a9f2-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="9a9f2-135">Related topics</span></span>
- [<span data-ttu-id="9a9f2-136">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="9a9f2-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9a9f2-137">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="9a9f2-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9a9f2-138">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="9a9f2-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="9a9f2-139">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="9a9f2-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9a9f2-140">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="9a9f2-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9a9f2-141">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="9a9f2-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)