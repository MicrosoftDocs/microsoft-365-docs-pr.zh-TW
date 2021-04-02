---
title: 在 Microsoft Defender ATP 中查看及管理自訂偵測規則
ms.reviewer: ''
description: 瞭解如何查看及管理自訂偵測規則
keywords: 自訂偵測、view、manage、警示、編輯、按需執行、偵測規則、高級搜尋、搜尋、查詢、回應動作、mdatp、microsoft defender atp
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
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498749"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="f2753-104">查看及管理自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="f2753-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f2753-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f2753-105">**Applies to:**</span></span>
- [<span data-ttu-id="f2753-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f2753-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f2753-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2753-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f2753-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f2753-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f2753-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f2753-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="f2753-110">管理您現有的 [自訂偵測規則](custom-detection-rules.md) ，以確保它們有效地尋找威脅並採取動作。</span><span class="sxs-lookup"><span data-stu-id="f2753-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="f2753-111">探索如何查看規則清單、檢查先前的執行，並複查其觸發的警示。</span><span class="sxs-lookup"><span data-stu-id="f2753-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="f2753-112">您也可以根據需要執行規則，並加以修改。</span><span class="sxs-lookup"><span data-stu-id="f2753-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="f2753-113">必要權限</span><span class="sxs-lookup"><span data-stu-id="f2753-113">Required permissions</span></span>

<span data-ttu-id="f2753-114">若要建立或管理自訂的偵測， [您的角色](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) 必須具有「 **管理安全性設定** 」許可權。</span><span class="sxs-lookup"><span data-stu-id="f2753-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="f2753-115">查看現有規則</span><span class="sxs-lookup"><span data-stu-id="f2753-115">View existing rules</span></span>

<span data-ttu-id="f2753-116">若要查看所有現有的自訂偵測規則，請流覽至 [**設定**  >  **自訂** 偵測]。</span><span class="sxs-lookup"><span data-stu-id="f2753-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="f2753-117">頁面會列出具有下列執行資訊的所有規則：</span><span class="sxs-lookup"><span data-stu-id="f2753-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="f2753-118">**上次執行** 時間-最後一次執行規則以檢查查詢符合專案並產生警示</span><span class="sxs-lookup"><span data-stu-id="f2753-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="f2753-119">**上次執行狀態**—是否已成功執行規則</span><span class="sxs-lookup"><span data-stu-id="f2753-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="f2753-120">**下一次執行**（下一個排程的執行）</span><span class="sxs-lookup"><span data-stu-id="f2753-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="f2753-121">**狀態**—是否已開啟或關閉規則</span><span class="sxs-lookup"><span data-stu-id="f2753-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="f2753-122">View rule details、modify rule 及 run rule</span><span class="sxs-lookup"><span data-stu-id="f2753-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="f2753-123">若要查看自訂偵測規則的完整資訊，請從 [**設定**  >  **自訂** 偵測] 中的規則清單中，選取規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="f2753-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="f2753-124">關於選取之規則的頁面會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="f2753-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="f2753-125">規則的一般資訊，包括警示、執行狀態和範圍的詳細資料</span><span class="sxs-lookup"><span data-stu-id="f2753-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="f2753-126">觸發警示的清單</span><span class="sxs-lookup"><span data-stu-id="f2753-126">List of triggered alerts</span></span>
- <span data-ttu-id="f2753-127">觸發動作清單</span><span class="sxs-lookup"><span data-stu-id="f2753-127">List of triggered actions</span></span>

<span data-ttu-id="f2753-128">![自訂偵測規則頁面](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="f2753-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="f2753-129">*自訂偵測規則頁面*</span><span class="sxs-lookup"><span data-stu-id="f2753-129">*Custom detection rule page*</span></span>

<span data-ttu-id="f2753-130">您也可以在此頁面上對規則採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="f2753-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="f2753-131">**Run**-立即執行規則。</span><span class="sxs-lookup"><span data-stu-id="f2753-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="f2753-132">此動作也會重設下一個執行的間隔。</span><span class="sxs-lookup"><span data-stu-id="f2753-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="f2753-133">**編輯**—修改規則但不變更查詢</span><span class="sxs-lookup"><span data-stu-id="f2753-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="f2753-134">**修改查詢**-在高級搜尋中編輯查詢</span><span class="sxs-lookup"><span data-stu-id="f2753-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="f2753-135">**開啟**  / **關閉**—啟用規則或停止執行</span><span class="sxs-lookup"><span data-stu-id="f2753-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="f2753-136">**刪除**—關閉規則並加以移除</span><span class="sxs-lookup"><span data-stu-id="f2753-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="f2753-137">若要快速查看資訊，並對表格中的專案採取動作，請使用表格左邊的選取範圍欄 [&#10003;]。</span><span class="sxs-lookup"><span data-stu-id="f2753-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2753-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="f2753-138">Related topics</span></span>
- [<span data-ttu-id="f2753-139">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="f2753-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="f2753-140">建立偵測規則</span><span class="sxs-lookup"><span data-stu-id="f2753-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="f2753-141">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="f2753-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f2753-142">查看和組織提醒</span><span class="sxs-lookup"><span data-stu-id="f2753-142">View and organize alerts</span></span>](alerts-queue.md)
