---
title: 將非 custodial 資料來源新增至高級 eDiscovery 案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 您可以將非 custodial 資料來源新增至高級 eDiscovery 案例，並在資料來源上保留。 非 custodial 的資料來源是重新編制索引的，所以被視為已部分索引的任何內容都會重新處理，以讓它完全且快速可供搜尋。
ms.openlocfilehash: 2009a8cc82dc9407e9871409e85cdcd321ea9bb0
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024743"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="f8647-104">將非 custodial 資料來源新增至高級 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="f8647-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="f8647-105">在高級 eDiscovery 案例中，它不一定會符合您在案例中建立 Microsoft 365 資料來源與系統管理員的需求。</span><span class="sxs-lookup"><span data-stu-id="f8647-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="f8647-106">不過，您可能還需要將該資料與案例產生關聯，以便進行搜尋、將其新增至審閱集，以及加以審閱。</span><span class="sxs-lookup"><span data-stu-id="f8647-106">But you may still need to associate that data with a case so that you search it, add it to review set, and review it.</span></span> <span data-ttu-id="f8647-107">新功能稱為「*非 custodial 資料來源*」，可讓您將資料新增至案例，而不必將資料關聯至保管人。</span><span class="sxs-lookup"><span data-stu-id="f8647-107">The new feature called *non-custodial data sources* lets you add data to a case without having to associate the data to a custodian.</span></span> <span data-ttu-id="f8647-108">它也會將相同的高級 eDiscovery 功能套用至可用於與保管人相關聯之資料的非 custodial 資料。</span><span class="sxs-lookup"><span data-stu-id="f8647-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="f8647-109">您可以套用至非 custodial 資料的兩個最實用功能是保留，並使用[高級索引](indexing-custodian-data.md)處理。</span><span class="sxs-lookup"><span data-stu-id="f8647-109">Two of the most useful features that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="f8647-110">新增非 custodial 的資料來源</span><span class="sxs-lookup"><span data-stu-id="f8647-110">Add a non-custodial data source</span></span>

<span data-ttu-id="f8647-111">請遵循下列步驟，在高級 eDiscovery 案例中新增及管理非 custodial 的資料來源。</span><span class="sxs-lookup"><span data-stu-id="f8647-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="f8647-112">在「**高級 eDiscovery**首頁」上，按一下您要新增資料的案例。</span><span class="sxs-lookup"><span data-stu-id="f8647-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="f8647-113">在 [**來源**] 頁面上，按一下 [**資料位置**] 索引標籤，然後按一下 [**新增資料位置**]。</span><span class="sxs-lookup"><span data-stu-id="f8647-113">On the **Sources** page, click the **Data locations** tab, and then click **Add data location**.</span></span>

3. <span data-ttu-id="f8647-114">按一下 [**新增資料位置**]，然後選擇您想要新增至案例的資料來源。</span><span class="sxs-lookup"><span data-stu-id="f8647-114">Click **Add data location** and choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="f8647-115">您可以新增多個信箱和網站。</span><span class="sxs-lookup"><span data-stu-id="f8647-115">You can add multiple mailboxes and sites.</span></span>

4. <span data-ttu-id="f8647-116">在嚮導的 [**選擇位置**] 頁面上，將信箱或網站（或兩者）新增為案例的非 custodial 資料來源。</span><span class="sxs-lookup"><span data-stu-id="f8647-116">On the **Choose locations** page in the wizard, add mailboxes or sites (or both) as non-custodial data sources to the case.</span></span>

5. <span data-ttu-id="f8647-117">新增資料來源之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f8647-117">After adding the data sources, click **Next**.</span></span>

6. <span data-ttu-id="f8647-118">在 [**就地保留**] 頁面上，選取或取消選取相關的核取方塊，以選擇要保留的資料來源。</span><span class="sxs-lookup"><span data-stu-id="f8647-118">On the **Place holds** page, choose which data sources you want to place on hold by selecting or unselecting the associated checkbox.</span></span>

7. <span data-ttu-id="f8647-119">確認 [保留] 選項，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="f8647-119">Verify the hold selections and then click **Submit**.</span></span>

   <span data-ttu-id="f8647-120">您新增的每個非 custodial 資料來源都會列在 [**資料來源**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="f8647-120">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span>

   <span data-ttu-id="f8647-121">此外，在案例的 [**工作**] 索引標籤上會建立並顯示名為 [*索引] 非 custodial 資料*的工作。</span><span class="sxs-lookup"><span data-stu-id="f8647-121">Also, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="f8647-122">在建立工作之後，起始的高級索引處理常式和資料來源都會重新編制索引。</span><span class="sxs-lookup"><span data-stu-id="f8647-122">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="managing-the-hold-on-non-custodial-data-sources"></a><span data-ttu-id="f8647-123">在非 custodial 資料來源上管理保留</span><span class="sxs-lookup"><span data-stu-id="f8647-123">Managing the hold on non-custodial data sources</span></span>

<span data-ttu-id="f8647-124">在非 custodial 資料來源上進行保留後，會自動建立包含案例所有非 custodial 資料來源的保留原則。</span><span class="sxs-lookup"><span data-stu-id="f8647-124">After you place a hold on a non-custodial data source, a hold policy that contains all non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="f8647-125">當您放置其他非 custodial 資料來源時，會將它們新增至此保留原則。</span><span class="sxs-lookup"><span data-stu-id="f8647-125">When you place additional non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="f8647-126">在案例的**首頁**上，按一下 [**保留**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f8647-126">On the **Home** page of the case, click the **Holds** tab.</span></span>

2. <span data-ttu-id="f8647-127">在 [**保留**] 頁面上，按一下 [ \*\* \<GUID\> NCDSHOLD\*\*]，其中 GUID 值是唯一的案例。</span><span class="sxs-lookup"><span data-stu-id="f8647-127">On the **Holds** page, and click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

3. <span data-ttu-id="f8647-128">在飛入頁面上，按一下 [**編輯保留**]，以查看保留中的所有非 custodial 資料來源。</span><span class="sxs-lookup"><span data-stu-id="f8647-128">On the flyout page, click **Edit hold** to view all the non-custodial data sources that are placed on hold.</span></span>

<span data-ttu-id="f8647-129">您可以在非 custodial 資料來源上執行下列管理工作：</span><span class="sxs-lookup"><span data-stu-id="f8647-129">You can perform the following management task on non-custodial data sources:</span></span>

- <span data-ttu-id="f8647-130">您可以編輯 [保留]，以在案例中建立套用至所有非 custodial 資料來源的查詢型保留。</span><span class="sxs-lookup"><span data-stu-id="f8647-130">You can edit the hold to create a query-based hold that is applied to all non-custodial data sources in the case.</span></span>

- <span data-ttu-id="f8647-131">您可以從保留中釋放非 custodial 的資料來源。</span><span class="sxs-lookup"><span data-stu-id="f8647-131">You can release a non-custodial data source from the hold.</span></span> <span data-ttu-id="f8647-132">釋放資料來源並不會從案例中移除非 custodial 資料來源。</span><span class="sxs-lookup"><span data-stu-id="f8647-132">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="f8647-133">它只會移除放在資料來源上的保留。</span><span class="sxs-lookup"><span data-stu-id="f8647-133">It only removes the hold that was placed on the data source.</span></span>
