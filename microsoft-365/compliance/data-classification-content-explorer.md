---
title: 開始使用內容總管 (預覽)
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
description: 內容總管可讓您本機檢視已套用標籤的項目。
ms.openlocfilehash: 3d1c938d3a9d7ff25bb66a5b344cfbb29eace84c
ms.sourcegitcommit: fa6a1e432747e150df945050a3744b4408ceb2d9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "43957263"
---
# <a name="get-started-with-content-explorer-preview"></a><span data-ttu-id="5de86-103">開始使用內容總管 (預覽)</span><span class="sxs-lookup"><span data-stu-id="5de86-103">Get started with content explorer (preview)</span></span>

<span data-ttu-id="5de86-104">資料分類內容總管可讓您本機檢視概觀頁面中摘要的項目。</span><span class="sxs-lookup"><span data-stu-id="5de86-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5de86-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="5de86-105">Prerequisites</span></span>

<span data-ttu-id="5de86-106">每個存取並使用活動總管的帳戶，都必須有從下列其中一個訂閱中指派的授權：</span><span class="sxs-lookup"><span data-stu-id="5de86-106">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="5de86-107">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="5de86-107">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="5de86-108">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="5de86-108">Office 365 (E5)</span></span>
- <span data-ttu-id="5de86-109">進階合規性 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="5de86-109">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="5de86-110">進階威脅情報 (E5) 附加元件</span><span class="sxs-lookup"><span data-stu-id="5de86-110">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="content-explorer"></a><span data-ttu-id="5de86-111">內容總管</span><span class="sxs-lookup"><span data-stu-id="5de86-111">Content explorer</span></span>

<span data-ttu-id="5de86-112">內容總管會顯示具有敏感度標籤、保留標籤或已分類為貴組織敏感性資訊類型之項目的目前快照。</span><span class="sxs-lookup"><span data-stu-id="5de86-112">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="5de86-113">敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="5de86-113">Sensitive information types</span></span>

<span data-ttu-id="5de86-114">[DLP 原則](data-loss-prevention-policies.md)有助於保護敏感性資訊 (已定義為**敏感性資訊類型**)。</span><span class="sxs-lookup"><span data-stu-id="5de86-114">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="5de86-115">Microsoft 365 包括涵蓋許多不同區域的[許多常見敏感性資訊類型的定義](what-the-sensitive-information-types-look-for.md)，可供您使用。</span><span class="sxs-lookup"><span data-stu-id="5de86-115">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="5de86-116">例如，信用卡號碼、銀行帳戶號碼、國家/地區識別碼和 Windows Live ID 服務號碼。</span><span class="sxs-lookup"><span data-stu-id="5de86-116">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="5de86-117">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="5de86-117">Sensitivity labels</span></span>

<span data-ttu-id="5de86-118">[敏感度標籤](sensitivity-labels.md)只是一個標記，指出您組織的項目值。</span><span class="sxs-lookup"><span data-stu-id="5de86-118">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="5de86-119">可手動或自動套用。</span><span class="sxs-lookup"><span data-stu-id="5de86-119">It can be applied manually, or automatically.</span></span> <span data-ttu-id="5de86-120">一旦套用，即會將它內嵌在文件中，並在所有的位置追蹤。</span><span class="sxs-lookup"><span data-stu-id="5de86-120">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="5de86-121">敏感性標籤會啟用各種防護行為，例如強制浮水印或加密。</span><span class="sxs-lookup"><span data-stu-id="5de86-121">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="5de86-122">啟用端點保護後，您甚至可以防止項目離開組織控制。</span><span class="sxs-lookup"><span data-stu-id="5de86-122">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="5de86-123">SharePoint 和 OneDrive 中的檔案必須啟用敏感度標籤，以便在資料分類頁面中顯示對應資料。</span><span class="sxs-lookup"><span data-stu-id="5de86-123">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="5de86-124">如需詳細資訊，請參閱[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="5de86-124">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="5de86-125">保留標籤</span><span class="sxs-lookup"><span data-stu-id="5de86-125">Retention labels</span></span>

<span data-ttu-id="5de86-126">[保留標籤](labels.md)可讓您定義保留標記的項目的時間長度，以及刪除它之前要採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="5de86-126">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="5de86-127">它們會透過原則來手動或自動套用。</span><span class="sxs-lookup"><span data-stu-id="5de86-127">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="5de86-128">它們可以在協助您組織保持遵守法律和法規需求方面扮演一個角色。</span><span class="sxs-lookup"><span data-stu-id="5de86-128">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![內容總管摺疊的螢幕擷取畫面](../media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="5de86-130">權限</span><span class="sxs-lookup"><span data-stu-id="5de86-130">Permissions</span></span>

<span data-ttu-id="5de86-131">有兩個角色可以將存取權授與內容瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="5de86-131">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="5de86-132">**內容瀏覽器清單檢視器**：這個角色群組的成員資格可讓您查看每個項目及其位置。</span><span class="sxs-lookup"><span data-stu-id="5de86-132">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location.</span></span> <span data-ttu-id="5de86-133">`data classification list viewer` 角色已預先指派給此角色群組。</span><span class="sxs-lookup"><span data-stu-id="5de86-133">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="5de86-134">**內容瀏覽器內容檢視器**：這個角色群組的成員資格可讓您檢視清單中每個項目的內容。</span><span class="sxs-lookup"><span data-stu-id="5de86-134">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="5de86-135">`data classification content viewer` 角色已預先指派給此角色群組。</span><span class="sxs-lookup"><span data-stu-id="5de86-135">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="5de86-136">您用來存取內容瀏覽器的帳戶必須屬於其中一個或兩個角色群組。</span><span class="sxs-lookup"><span data-stu-id="5de86-136">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="5de86-137">這些是獨立的角色群組，不會累計。</span><span class="sxs-lookup"><span data-stu-id="5de86-137">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="5de86-138">例如，如果您想要授與某個帳戶只能檢視項目及其位置的權限，請授與「內容瀏覽器清單檢視器」權限。</span><span class="sxs-lookup"><span data-stu-id="5de86-138">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="5de86-139">如果您想要讓該相同帳戶也能夠檢視清單中項目的內容，也請授與「內容瀏覽器內容檢視器」權限。</span><span class="sxs-lookup"><span data-stu-id="5de86-139">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="5de86-140">您也可以將一個或兩個角色指派給自訂角色群組，以量身打造內容瀏覽器的存取權。</span><span class="sxs-lookup"><span data-stu-id="5de86-140">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="5de86-141">全域系統管理員、合規性系統管理員或資料系統管理員可以指派必要的內容總管清單檢視器和內容總管內容檢視器角色群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="5de86-141">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="5de86-142">如何使用內容總管</span><span class="sxs-lookup"><span data-stu-id="5de86-142">How to use content explorer</span></span>

1. <span data-ttu-id="5de86-143">開啟 **Microsoft 365 合規性中心**  > **資料分類** > **內容總管**。</span><span class="sxs-lookup"><span data-stu-id="5de86-143">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="5de86-144">如果您知道標籤的名稱或敏感性資訊類型，便可在搜尋方塊中輸入。</span><span class="sxs-lookup"><span data-stu-id="5de86-144">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="5de86-145">您也可以展開標籤類型，然後從清單選取標籤來瀏覽項目，以下顯示的是清單保留標籤部分中的項目。</span><span class="sxs-lookup"><span data-stu-id="5de86-145">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="5de86-146">在 **[所有位置]** 底下選取位置，並向下切入資料夾結構至項目。</span><span class="sxs-lookup"><span data-stu-id="5de86-146">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="5de86-147">按兩下以在內容總管中於機開啟項目。</span><span class="sxs-lookup"><span data-stu-id="5de86-147">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="5de86-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5de86-148">See also</span></span>

- [<span data-ttu-id="5de86-149">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="5de86-149">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="5de86-150">保留標籤</span><span class="sxs-lookup"><span data-stu-id="5de86-150">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="5de86-151">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="5de86-151">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="5de86-152">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="5de86-152">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="5de86-153">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="5de86-153">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
