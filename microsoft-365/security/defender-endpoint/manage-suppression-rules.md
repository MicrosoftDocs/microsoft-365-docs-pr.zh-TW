---
title: 管理 Microsoft Defender for Endpoint 抑制規則
description: 您可能需要使用抑制規則，防止警示出現在入口網站中。 瞭解如何在 Microsoft Defender ATP 中管理抑制規則。
keywords: 管理抑制、規則、規則名稱、範圍、動作、警示、開啟、關閉
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d2ff8fa1f07f82c3cc719f49f50ee25937aea243
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187562"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="0f88f-105">管理抑制規則</span><span class="sxs-lookup"><span data-stu-id="0f88f-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0f88f-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0f88f-106">**Applies to:**</span></span>
- [<span data-ttu-id="0f88f-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0f88f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0f88f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0f88f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0f88f-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="0f88f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0f88f-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="0f88f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="0f88f-111">在某些情況下，您可能需要抑制出現在入口網站中的提醒。</span><span class="sxs-lookup"><span data-stu-id="0f88f-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="0f88f-112">您可以針對已知的特殊警示（如組織中的已知工具或處理常式），建立抑制規則。</span><span class="sxs-lookup"><span data-stu-id="0f88f-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="0f88f-113">如需如何抑制提醒的詳細資訊，請參閱 [抑制警示](manage-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="0f88f-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="0f88f-114">您可以查看所有抑制規則的清單，並在一個位置進行管理。</span><span class="sxs-lookup"><span data-stu-id="0f88f-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="0f88f-115">您也可以開啟或關閉警示抑制規則。</span><span class="sxs-lookup"><span data-stu-id="0f88f-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="0f88f-116">在功能窗格中，選取 [**設定**  >  **警示抑制**]。</span><span class="sxs-lookup"><span data-stu-id="0f88f-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="0f88f-117">組織中使用者所建立的隱藏規則清單隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="0f88f-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="0f88f-118">按一下規則名稱旁邊的核取方塊，以選取規則。</span><span class="sxs-lookup"><span data-stu-id="0f88f-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="0f88f-119">按一下 [ **開啟規則**]、[ **編輯規則**] 或 [  **刪除規則**]。</span><span class="sxs-lookup"><span data-stu-id="0f88f-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="0f88f-120">當您變更規則時，您可以選擇發行已經取消的警示，不論這些警示是否符合新的準則。</span><span class="sxs-lookup"><span data-stu-id="0f88f-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="0f88f-121">查看抑制規則的詳細資料</span><span class="sxs-lookup"><span data-stu-id="0f88f-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="0f88f-122">在功能窗格中，選取 [**設定**  >  **警示抑制**]。</span><span class="sxs-lookup"><span data-stu-id="0f88f-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="0f88f-123">組織中使用者所建立的隱藏規則清單隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="0f88f-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="0f88f-124">按一下規則名稱。</span><span class="sxs-lookup"><span data-stu-id="0f88f-124">Click on a rule name.</span></span> <span data-ttu-id="0f88f-125">會顯示規則的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0f88f-125">Details of the rule is displayed.</span></span> <span data-ttu-id="0f88f-126">您將會看到 [狀態]、[範圍]、[動作]、[建立者]、[建立者] 和 [建立規則] 日期等規則詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0f88f-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="0f88f-127">您也可以查看相關聯的警示和規則條件。</span><span class="sxs-lookup"><span data-stu-id="0f88f-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0f88f-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="0f88f-128">Related topics</span></span>

- [<span data-ttu-id="0f88f-129">管理提醒</span><span class="sxs-lookup"><span data-stu-id="0f88f-129">Manage alerts</span></span>](manage-alerts.md)
