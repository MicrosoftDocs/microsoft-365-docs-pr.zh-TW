---
title: 開始使用活動總管
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 活動總管透過讓您查看和篩選使用者對套用標籤的內容執行的操作，來完善資料分類功能。
ms.openlocfilehash: 5cb6a8dbfa570b3b0e0d1ce39648d12050d2af81
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327839"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="84813-103">開始使用活動總管</span><span class="sxs-lookup"><span data-stu-id="84813-103">Get started with activity explorer</span></span>

<span data-ttu-id="84813-104">資料分類概觀和內容總管索引標籤可讓您查看已探索和套用標籤的內容，以及內容的位置。</span><span class="sxs-lookup"><span data-stu-id="84813-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="84813-105">活動總管透過讓您監視對已套用標籤的內容執行的工作，從而完善此功能套件。</span><span class="sxs-lookup"><span data-stu-id="84813-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="84813-106">活動總管提供歷程記錄的檢視。</span><span class="sxs-lookup"><span data-stu-id="84813-106">Activity explorer provides a historical view.</span></span>

![預留位置螢幕擷取畫面概觀活動總管](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="84813-108">有超過 30 個不同的篩選可使用，其中包括：</span><span class="sxs-lookup"><span data-stu-id="84813-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="84813-109">日期範圍</span><span class="sxs-lookup"><span data-stu-id="84813-109">date range</span></span>
- <span data-ttu-id="84813-110">活動類型</span><span class="sxs-lookup"><span data-stu-id="84813-110">activity type</span></span>
- <span data-ttu-id="84813-111">位置</span><span class="sxs-lookup"><span data-stu-id="84813-111">location</span></span>
- <span data-ttu-id="84813-112">使用者</span><span class="sxs-lookup"><span data-stu-id="84813-112">user</span></span>
- <span data-ttu-id="84813-113">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="84813-113">sensitivity label</span></span>
- <span data-ttu-id="84813-114">保留標籤</span><span class="sxs-lookup"><span data-stu-id="84813-114">retention label</span></span>
- <span data-ttu-id="84813-115">檔案路徑</span><span class="sxs-lookup"><span data-stu-id="84813-115">file path</span></span>
- <span data-ttu-id="84813-116">DLP 原則</span><span class="sxs-lookup"><span data-stu-id="84813-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="84813-117">必要條件</span><span class="sxs-lookup"><span data-stu-id="84813-117">Prerequisites</span></span>

<span data-ttu-id="84813-118">每個存取並使用資料分類的帳戶，都必須有從下列其中一個訂閱中指派的授權：</span><span class="sxs-lookup"><span data-stu-id="84813-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="84813-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="84813-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="84813-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="84813-120">Office 365 (E5)</span></span>
- <span data-ttu-id="84813-121">進階合規性 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="84813-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="84813-122">進階威脅情報 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="84813-122">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="84813-123">權限</span><span class="sxs-lookup"><span data-stu-id="84813-123">Permissions</span></span>

 <span data-ttu-id="84813-124">若要存取活動總管索引標籤，帳戶必須在其中任一角色或角色群組中獲派成員資格。</span><span class="sxs-lookup"><span data-stu-id="84813-124">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="84813-125">**Microsoft 365 角色群組**</span><span class="sxs-lookup"><span data-stu-id="84813-125">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="84813-126">全域管理員</span><span class="sxs-lookup"><span data-stu-id="84813-126">Global administrator</span></span>
- <span data-ttu-id="84813-127">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="84813-127">Compliance administrator</span></span>
- <span data-ttu-id="84813-128">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="84813-128">Security administrator</span></span>
- <span data-ttu-id="84813-129">合規性資料管理員</span><span class="sxs-lookup"><span data-stu-id="84813-129">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="84813-130">活動類型</span><span class="sxs-lookup"><span data-stu-id="84813-130">Activity type</span></span>

<span data-ttu-id="84813-131">Microsoft 365 會監視和報告 SharePoint Online 和 OneDrive 中的下列活動類型：</span><span class="sxs-lookup"><span data-stu-id="84813-131">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="84813-132">已套用標籤</span><span class="sxs-lookup"><span data-stu-id="84813-132">label applied</span></span>
- <span data-ttu-id="84813-133">已變更標籤 (升級、降級或移除)</span><span class="sxs-lookup"><span data-stu-id="84813-133">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="84813-134">自動加上標籤模擬</span><span class="sxs-lookup"><span data-stu-id="84813-134">auto-labeling simulation</span></span>

<span data-ttu-id="84813-135">了解對套用標籤的敏感性內容執行動作的價值在於，您可以看到已實施的[資料外洩防護原則](data-loss-prevention-policies.md)等控制措施是否有效。</span><span class="sxs-lookup"><span data-stu-id="84813-135">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="84813-136">如果無效，或者如果您發現一些意外情況 (例如大量加上`highly confidential`標籤並降級為`general`的項目)，則可以管理各種原則並採取新動作來限制不需要的行為。</span><span class="sxs-lookup"><span data-stu-id="84813-136">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="84813-137">活動總管目前未監視 Exchange Online 的保留活動。</span><span class="sxs-lookup"><span data-stu-id="84813-137">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="84813-138">請參閱</span><span class="sxs-lookup"><span data-stu-id="84813-138">See also</span></span>
- [<span data-ttu-id="84813-139">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="84813-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="84813-140">保留標籤</span><span class="sxs-lookup"><span data-stu-id="84813-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="84813-141">敏感性資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="84813-141">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="84813-142">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="84813-142">Overview of retention policies</span></span>](retention-policies.md)
