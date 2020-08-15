---
title: Microsoft 365 搜尋中的租用戶隔離
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，會找到有關租使用者隔離如何在 Microsoft 365 搜尋中個別租使用者資料運作方式的說明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9b204e9c1f3ef459852900f3403a21f7ea40541f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688274"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a><span data-ttu-id="43187-103">Microsoft 365 搜尋中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="43187-103">Tenant Isolation in Microsoft 365 Search</span></span>

<span data-ttu-id="43187-104">SharePoint 線上搜尋使用租使用者分隔模型，它會平衡共用資料結構的效率，防範租使用者之間的資訊洩漏。</span><span class="sxs-lookup"><span data-stu-id="43187-104">SharePoint Online search uses a tenant separation model that balances the efficiency of shared data structures with protection against information leaking between tenants.</span></span> <span data-ttu-id="43187-105">使用此模型，我們避免搜尋功能：</span><span class="sxs-lookup"><span data-stu-id="43187-105">With this model, we prevent the Search features from:</span></span>

- <span data-ttu-id="43187-106">傳回包含其他承租人檔的查詢結果</span><span class="sxs-lookup"><span data-stu-id="43187-106">Returning query results that contain documents from other tenants</span></span>
- <span data-ttu-id="43187-107">在查詢結果中公開足夠的資訊，訓練有素的使用者可能會推斷其他承租人的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="43187-107">Exposing sufficient information in query results that a skilled user could infer information about other tenants</span></span>
- <span data-ttu-id="43187-108">顯示其他租使用者的架構或設定</span><span class="sxs-lookup"><span data-stu-id="43187-108">Showing schema or settings from another tenant</span></span>
- <span data-ttu-id="43187-109">將承租人或存放區產生的分析處理資訊與錯誤的承租人混淆</span><span class="sxs-lookup"><span data-stu-id="43187-109">Mixing analytics processing information between tenants or store results in the wrong tenant</span></span>
- <span data-ttu-id="43187-110">使用來自其他租使用者的字典專案</span><span class="sxs-lookup"><span data-stu-id="43187-110">Using dictionary entries from another tenant</span></span>

<span data-ttu-id="43187-111">對於每一種租使用者資料類型，我們會在程式碼中使用一或多個保護層級，以防意外洩漏資訊。</span><span class="sxs-lookup"><span data-stu-id="43187-111">For each type of tenant data, we use one or more layers of protection in the code to prevent accidental leaking of information.</span></span> <span data-ttu-id="43187-112">最重要的資料具有最多層的保護，可確保單一的缺陷不會導致實際或感覺的資訊洩漏。</span><span class="sxs-lookup"><span data-stu-id="43187-112">The most critical data has the most layers of protection to make sure that a single defect doesn't result in actual or perceived information leakage.</span></span>

## <a name="tenant-separation-for-the-search-index"></a><span data-ttu-id="43187-113">搜尋索引的承租人分隔</span><span class="sxs-lookup"><span data-stu-id="43187-113">Tenant Separation for the Search Index</span></span>

<span data-ttu-id="43187-114">搜尋索引會儲存在磁片上主控索引元件的伺服器上，而承租人則會共用索引檔案。</span><span class="sxs-lookup"><span data-stu-id="43187-114">The search index is stored on disk in the servers hosting the index components and the tenants share the index files.</span></span> <span data-ttu-id="43187-115">租使用者的索引檔只對該承租人的查詢可見。</span><span class="sxs-lookup"><span data-stu-id="43187-115">A tenant's indexed documents are visible only for queries for that tenant.</span></span> <span data-ttu-id="43187-116">三個獨立的機制會防止資訊洩漏：</span><span class="sxs-lookup"><span data-stu-id="43187-116">Three independent mechanisms prevent information leakage:</span></span>

- <span data-ttu-id="43187-117">租使用者識別碼篩選</span><span class="sxs-lookup"><span data-stu-id="43187-117">Tenant ID filtering</span></span>
- <span data-ttu-id="43187-118">租使用者識別碼字詞的首碼</span><span class="sxs-lookup"><span data-stu-id="43187-118">Tenant ID term prefixing</span></span>
- <span data-ttu-id="43187-119">ACL 檢查</span><span class="sxs-lookup"><span data-stu-id="43187-119">ACL checks</span></span>

<span data-ttu-id="43187-120">所有三種機制都必須失敗，搜尋才能將檔返還錯誤的承租人。</span><span class="sxs-lookup"><span data-stu-id="43187-120">All three mechanisms would have to fail for Search to return documents to the wrong tenant.</span></span>

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a><span data-ttu-id="43187-121">租使用者識別碼篩選和租使用者識別碼條款前面</span><span class="sxs-lookup"><span data-stu-id="43187-121">Tenant ID Filtering and Tenant ID Term Prefixing</span></span>

<span data-ttu-id="43187-122">搜尋會以租使用者識別碼為全文檢索索引中的每個字詞建立索引首碼。</span><span class="sxs-lookup"><span data-stu-id="43187-122">Search prefixes every term that is indexed in the full-text index with the tenant ID.</span></span> <span data-ttu-id="43187-123">例如，如果為識別碼為 "*123*" 的承租人編制索引字詞 "*foo*"，全文檢索索引中的專案就是 "*123foo"。*</span><span class="sxs-lookup"><span data-stu-id="43187-123">For example, when the term "*foo*" is indexed for a tenant with an ID of "*123*", the entry in the full-text index is "*123foo.*"</span></span>

<span data-ttu-id="43187-124">每個查詢都會轉換成包含租使用者識別碼，使用稱為租使用者識別碼篩選的處理常式。</span><span class="sxs-lookup"><span data-stu-id="43187-124">Every query is converted to include the tenant ID using a process called tenant ID filtering.</span></span> <span data-ttu-id="43187-125">例如，查詢 "*foo*" 會轉換成 "<*guid*>。*foo\*\*TenantID*： <*guid*> "，其中 <*guid*> 代表執行查詢的承租人。</span><span class="sxs-lookup"><span data-stu-id="43187-125">For example, the query "*foo*" is converted to "<*guid*>.*foo* AND *tenantID*:<*guid*>", where <*guid*> represents the tenant performing the query.</span></span> <span data-ttu-id="43187-126">這項查詢轉換會在每個索引節點內發生，而且查詢和內容處理都不會影響。</span><span class="sxs-lookup"><span data-stu-id="43187-126">This query conversion occurs within each index node and neither query nor content processing can influence it.</span></span> <span data-ttu-id="43187-127">因為租使用者識別碼會新增至每個查詢，所以無法透過查看一個承租人中的最佳相符排名來推斷其他承租人中的字詞頻率。</span><span class="sxs-lookup"><span data-stu-id="43187-127">Because the tenant ID is added to every query, the frequency of a term in other tenants can't be inferred by looking at best match ranking in one tenant.</span></span>

<span data-ttu-id="43187-128">租使用者識別碼字詞的首碼只會出現在全文檢索索引中。</span><span class="sxs-lookup"><span data-stu-id="43187-128">Tenant ID term prefixing occurs only in the full-text index.</span></span> <span data-ttu-id="43187-129">欄位搜尋，例如 "*title： foo*"，移至綜合搜尋索引，其中的字詞不是以租使用者識別碼做為首碼。</span><span class="sxs-lookup"><span data-stu-id="43187-129">Fielded searches, such as "*title:foo*", go to a synthetic search index where terms aren't prefixed by tenant ID.</span></span> <span data-ttu-id="43187-130">相反地，欄位搜尋會加上功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="43187-130">Instead, fielded searches are prefixed with the field name.</span></span> <span data-ttu-id="43187-131">例如，查詢「*title： foo*」會轉換成「*欄位。 TITLE： foo AND fields。 tenantID*： <*guid*>。」</span><span class="sxs-lookup"><span data-stu-id="43187-131">For example, the query "*title:foo*" is converted to "*fields.title:foo AND fields.tenantID*:<*guid*>."</span></span> <span data-ttu-id="43187-132">因為字詞的頻率不會影響綜合搜尋索引中的點擊排名，所以不需要租使用者依字詞首碼來分隔。</span><span class="sxs-lookup"><span data-stu-id="43187-132">Because the frequency of a term doesn't influence ranking of hits in the synthetic search index, there's no need for tenant separation by term prefixing.</span></span> <span data-ttu-id="43187-133">對於欄位搜尋（如 "*title： foo*"），租使用者內容分隔取決於租使用者識別碼篩選依查詢轉換。</span><span class="sxs-lookup"><span data-stu-id="43187-133">For a fielded search like "*title:foo*", tenant content separation depends on tenant ID filtering by query conversion.</span></span>

## <a name="document-access-control-list-checks"></a><span data-ttu-id="43187-134">檔存取控制清單檢查</span><span class="sxs-lookup"><span data-stu-id="43187-134">Document Access Control List Checks</span></span>

<span data-ttu-id="43187-135">搜尋會透過儲存在搜尋索引中的 ACLs，控制對檔的存取。</span><span class="sxs-lookup"><span data-stu-id="43187-135">Search controls access to documents through ACLs that are saved in the search index.</span></span> <span data-ttu-id="43187-136">每個專案都會以特殊 ACL 欄位中的一組字詞編制索引。</span><span class="sxs-lookup"><span data-stu-id="43187-136">Every item is indexed with a set of terms in a special ACL field.</span></span> <span data-ttu-id="43187-137">ACL 欄位包含每個群組或使用者可以查看檔的一個字詞。</span><span class="sxs-lookup"><span data-stu-id="43187-137">The ACL field contains one term per group or user that can view the document.</span></span> <span data-ttu-id="43187-138">每個查詢都會擴充 (ACE) 字詞的存取控制專案清單，其中一個是驗證使用者所屬的群組。</span><span class="sxs-lookup"><span data-stu-id="43187-138">Every query is augmented with a list of access control entry (ACE) terms, one for each group to which the authenticated user belongs.</span></span>

<span data-ttu-id="43187-139">例如，像 "<*guid*> 的查詢。*FOO 和 tenantID*： "<*guid*>" 變成： "<*guid*>。*foo 和 tenantID*： <*guid* >  *和* (*docACL：* < *ace1* >  *或 docACL*： <*ace2* >  *or docACL*： <*ace3* >  *...*) "</span><span class="sxs-lookup"><span data-stu-id="43187-139">For example, a query like "<*guid*>.*foo AND tenantID*:<*guid*>" becomes: "<*guid*>.*foo AND tenantID*:<*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*:<*ace2*> *OR docACL*:<*ace3*> *...*)"</span></span>

<span data-ttu-id="43187-140">由於使用者和群組識別碼（因此 Ace）是唯一的，因此會為只對某些使用者顯示之檔的承租人提供額外的安全性層級。</span><span class="sxs-lookup"><span data-stu-id="43187-140">Because user and group identifiers and hence ACEs are unique, this provides an extra level of security between tenants for documents that are only visible to some users.</span></span> <span data-ttu-id="43187-141">這種情況也是特殊的「外部使用者以外的所有人」 ACE 的案例，可將存取權授與租使用者中的一般使用者。</span><span class="sxs-lookup"><span data-stu-id="43187-141">The same is the case for the special "Everyone except external users" ACE that grants access to regular users in the tenant.</span></span> <span data-ttu-id="43187-142">不過，由於 "Everyone" 的 Ace 對於所有承租人都是相同的，所以公用檔的承租人分隔取決於租使用者識別碼篩選。</span><span class="sxs-lookup"><span data-stu-id="43187-142">But since ACEs for "Everyone" are the same for all tenants, tenant separation for public documents depends on tenant ID filtering.</span></span> <span data-ttu-id="43187-143">也支援「拒絕」 Ace。</span><span class="sxs-lookup"><span data-stu-id="43187-143">Deny ACEs are also supported.</span></span> <span data-ttu-id="43187-144">當與 deny ACE 相符時，查詢充實會新增一個子句，該子句會從結果中移除檔。</span><span class="sxs-lookup"><span data-stu-id="43187-144">The query augmentation adds a clause that removes a document from the result when there is a match with a deny ACE.</span></span>

<span data-ttu-id="43187-145">在 Exchange Online 搜尋中，索引會分割個別使用者信箱的信箱 ID，而不是租使用者識別碼 (訂閱識別碼) 如 SharePoint Online 中所示。</span><span class="sxs-lookup"><span data-stu-id="43187-145">In Exchange Online search, the index is partitioned on mailbox ID for individual user's mailboxes instead of tenant ID (subscription ID) as in SharePoint Online.</span></span> <span data-ttu-id="43187-146">分割機制與 SharePoint 線上，但沒有 ACL 篩選。</span><span class="sxs-lookup"><span data-stu-id="43187-146">The partitioning mechanism is the same as SharePoint Online, but there is no ACL filtering.</span></span>
