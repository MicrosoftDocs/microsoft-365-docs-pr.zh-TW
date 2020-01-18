---
title: 使用資料分類活動總管
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
ms.openlocfilehash: ab80de0e1be3a164da8414ef3791fb9717bcc190
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233694"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="815de-103">檢視套用標籤的內容上的活動 (預覽)</span><span class="sxs-lookup"><span data-stu-id="815de-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="815de-104">資料分類概觀和內容總管索引標籤可讓您查看已探索和套用標籤的內容，以及內容的位置。</span><span class="sxs-lookup"><span data-stu-id="815de-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="815de-105">活動總管透過讓您監視對已套用標籤的內容執行的工作，從而完善此功能套件。</span><span class="sxs-lookup"><span data-stu-id="815de-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="815de-106">活動總管提供歷程記錄的檢視。</span><span class="sxs-lookup"><span data-stu-id="815de-106">Activity explorer provides a historical view.</span></span>

![預留位置螢幕擷取畫面概觀活動總管](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="815de-108">您可以依照下列方式篩選資料：</span><span class="sxs-lookup"><span data-stu-id="815de-108">You can filter the data by:</span></span>

- <span data-ttu-id="815de-109">日期範圍</span><span class="sxs-lookup"><span data-stu-id="815de-109">date range</span></span>
- <span data-ttu-id="815de-110">活動類型</span><span class="sxs-lookup"><span data-stu-id="815de-110">activity type</span></span>
- <span data-ttu-id="815de-111">位置</span><span class="sxs-lookup"><span data-stu-id="815de-111">location</span></span>
- <span data-ttu-id="815de-112">使用者</span><span class="sxs-lookup"><span data-stu-id="815de-112">user</span></span>
- <span data-ttu-id="815de-113">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="815de-113">sensitivity label</span></span>
- <span data-ttu-id="815de-114">保留標籤</span><span class="sxs-lookup"><span data-stu-id="815de-114">retention label</span></span>


<span data-ttu-id="815de-115">您可以以清單或橫條圖的形式檢視資料。</span><span class="sxs-lookup"><span data-stu-id="815de-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="815de-116">必要條件</span><span class="sxs-lookup"><span data-stu-id="815de-116">Prerequisites</span></span>

<span data-ttu-id="815de-117">每個存取並使用活動總管的帳戶，都必須有從下列其中一個訂閱中指派的授權：</span><span class="sxs-lookup"><span data-stu-id="815de-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="815de-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="815de-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="815de-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="815de-119">Office 365 E5</span></span>
- <span data-ttu-id="815de-120">進階合規性 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="815de-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="815de-121">進階威脅情報 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="815de-121">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="815de-122">進階威脅防護 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="815de-122">Advanced Threat Protection (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="815de-123">活動類型</span><span class="sxs-lookup"><span data-stu-id="815de-123">Activity type</span></span>

<span data-ttu-id="815de-124">Microsoft 365 會監視和報告 SharePoint Online、OneDrive 和端點中的 12 種活動類型。</span><span class="sxs-lookup"><span data-stu-id="815de-124">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="815de-125">端點是執行 Windows 10 的使用者裝置。</span><span class="sxs-lookup"><span data-stu-id="815de-125">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="815de-126">已建立檔案</span><span class="sxs-lookup"><span data-stu-id="815de-126">File created</span></span>
- <span data-ttu-id="815de-127">已修改檔案</span><span class="sxs-lookup"><span data-stu-id="815de-127">File modified</span></span>
- <span data-ttu-id="815de-128">已重新命名檔案</span><span class="sxs-lookup"><span data-stu-id="815de-128">File renamed</span></span>
- <span data-ttu-id="815de-129">檔案已複製到雲端</span><span class="sxs-lookup"><span data-stu-id="815de-129">File copied to cloud</span></span>
- <span data-ttu-id="815de-130">檔案已遭不允許的應用程式存取</span><span class="sxs-lookup"><span data-stu-id="815de-130">File accessed by unallowed app</span></span>
- <span data-ttu-id="815de-131">已列印檔案</span><span class="sxs-lookup"><span data-stu-id="815de-131">File printed</span></span>
- <span data-ttu-id="815de-132">檔案已複製到抽取式媒體</span><span class="sxs-lookup"><span data-stu-id="815de-132">File copied to removable media</span></span>
- <span data-ttu-id="815de-133">檔案已複製到網路共用</span><span class="sxs-lookup"><span data-stu-id="815de-133">File copied to network share</span></span>
- <span data-ttu-id="815de-134">已讀取檔案</span><span class="sxs-lookup"><span data-stu-id="815de-134">File read</span></span>
- <span data-ttu-id="815de-135">檔案已複製到剪貼簿</span><span class="sxs-lookup"><span data-stu-id="815de-135">file copied to clipboard</span></span>
- <span data-ttu-id="815de-136">已套用標籤</span><span class="sxs-lookup"><span data-stu-id="815de-136">Label applied</span></span>
- <span data-ttu-id="815de-137">已變更標籤 (升級、降級或移除)</span><span class="sxs-lookup"><span data-stu-id="815de-137">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="815de-138">了解對套用標籤的敏感性內容執行動作的價值在於，您可以看到已實施的[資料外洩防護原則](data-loss-prevention-policies.md)等控制措施是否有效。</span><span class="sxs-lookup"><span data-stu-id="815de-138">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="815de-139">如果無效，或者如果您發現一些意外情況 (例如大量加上`highly confidential`標籤並降級為`general`的項目)，則可以管理各種原則並採取新動作來限制不需要的行為。</span><span class="sxs-lookup"><span data-stu-id="815de-139">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="815de-140">設定篩選條件後，您可以：</span><span class="sxs-lookup"><span data-stu-id="815de-140">Once your filters are set, you can:</span></span>

- <span data-ttu-id="815de-141">將游標暫留在橫條圖的某一段上方，以查看該類別中的項目數量 ![活動總管將游標暫留在](media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="815de-141">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="815de-142">匯出資料</span><span class="sxs-lookup"><span data-stu-id="815de-142">export the data</span></span>
- <span data-ttu-id="815de-143">從清單中選取任何指定的項目，並在飛出中檢視動作的詳細資料</span><span class="sxs-lookup"><span data-stu-id="815de-143">select any given item from the list and view the details of the action in the fly-out</span></span>

![活動總管詳細資料飛出](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="815de-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="815de-145">See also</span></span>
- [<span data-ttu-id="815de-146">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="815de-146">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="815de-147">保留標籤</span><span class="sxs-lookup"><span data-stu-id="815de-147">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="815de-148">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="815de-148">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="815de-149">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="815de-149">Overview of retention policies</span></span>](retention-policies.md)