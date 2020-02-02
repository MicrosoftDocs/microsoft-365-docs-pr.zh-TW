---
title: 使用資料分類內容總管 (預覽)
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
ms.openlocfilehash: c2bf73a5e6b9076d9c5f42c40f0d1f2f33cd1ee8
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661901"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="fbea1-103">使用資料分類內容總管 (預覽)</span><span class="sxs-lookup"><span data-stu-id="fbea1-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="fbea1-104">資料分類內容總管可讓您本機檢視概觀頁面中摘要的項目。</span><span class="sxs-lookup"><span data-stu-id="fbea1-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="fbea1-105">內容總管</span><span class="sxs-lookup"><span data-stu-id="fbea1-105">Content explorer</span></span>

<span data-ttu-id="fbea1-106">內容總管會顯示具有敏感度標籤、保留標籤或已分類為貴組織敏感性資訊類型之項目的目前快照。</span><span class="sxs-lookup"><span data-stu-id="fbea1-106">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="fbea1-107">敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="fbea1-107">Sensitive information types</span></span>

<span data-ttu-id="fbea1-108">[DLP 原則](data-loss-prevention-policies.md)有助於保護敏感性資訊 (已定義為**敏感性資訊類型**)。</span><span class="sxs-lookup"><span data-stu-id="fbea1-108">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="fbea1-109">Microsoft 365 包括涵蓋許多不同區域的[許多常見敏感性資訊類型的定義](what-the-sensitive-information-types-look-for.md)，可供您使用。</span><span class="sxs-lookup"><span data-stu-id="fbea1-109">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="fbea1-110">例如，信用卡號碼、銀行帳戶號碼、國家/地區識別碼和 Windows Live ID 服務號碼。</span><span class="sxs-lookup"><span data-stu-id="fbea1-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="fbea1-111">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="fbea1-111">Sensitivity labels</span></span>

<span data-ttu-id="fbea1-112">[敏感度標籤](sensitivity-labels.md)只是一個標記，指出您組織的項目值。</span><span class="sxs-lookup"><span data-stu-id="fbea1-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="fbea1-113">可手動或自動套用。</span><span class="sxs-lookup"><span data-stu-id="fbea1-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="fbea1-114">一旦套用，即會將它內嵌在文件中，並在所有的位置追蹤。</span><span class="sxs-lookup"><span data-stu-id="fbea1-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="fbea1-115">敏感性標籤會啟用各種防護行為，例如強制浮水印或加密。</span><span class="sxs-lookup"><span data-stu-id="fbea1-115">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="fbea1-116">啟用端點保護後，您甚至可以防止項目離開組織控制。</span><span class="sxs-lookup"><span data-stu-id="fbea1-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="fbea1-117">SharePoint 和 OneDrive 中的檔案必須啟用敏感度標籤，以便在資料分類頁面中顯示對應資料。</span><span class="sxs-lookup"><span data-stu-id="fbea1-117">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="fbea1-118">如需詳細資訊，請參閱[對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤 (公開預覽)](sensitivity-labels-sharepoint-onedrive-files.md) (英文版)。</span><span class="sxs-lookup"><span data-stu-id="fbea1-118">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="fbea1-119">保留標籤</span><span class="sxs-lookup"><span data-stu-id="fbea1-119">Retention labels</span></span>

<span data-ttu-id="fbea1-120">[保留標籤](labels.md)可讓您定義保留標記的項目的時間長度，以及刪除它之前要採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="fbea1-120">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="fbea1-121">它們會透過原則來手動或自動套用。</span><span class="sxs-lookup"><span data-stu-id="fbea1-121">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="fbea1-122">它們可以在協助您組織保持遵守法律和法規需求方面扮演一個角色。</span><span class="sxs-lookup"><span data-stu-id="fbea1-122">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![內容總管摺疊的螢幕擷取畫面](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="fbea1-124">權限</span><span class="sxs-lookup"><span data-stu-id="fbea1-124">Permissions</span></span>

<span data-ttu-id="fbea1-125">有兩個角色可以將存取權授與內容瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="fbea1-125">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="fbea1-126">**內容瀏覽器清單檢視器**：這個角色群組的成員資格可讓您查看每個項目及其位置。</span><span class="sxs-lookup"><span data-stu-id="fbea1-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location.</span></span> <span data-ttu-id="fbea1-127">`data classification list viewer` 角色已預先指派給此角色群組。</span><span class="sxs-lookup"><span data-stu-id="fbea1-127">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="fbea1-128">**內容瀏覽器內容檢視器**：這個角色群組的成員資格可讓您檢視清單中每個項目的內容。</span><span class="sxs-lookup"><span data-stu-id="fbea1-128">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="fbea1-129">`data classification content viewer` 角色已預先指派給此角色群組。</span><span class="sxs-lookup"><span data-stu-id="fbea1-129">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="fbea1-130">您用來存取內容瀏覽器的帳戶必須屬於其中一個或兩個角色群組。</span><span class="sxs-lookup"><span data-stu-id="fbea1-130">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="fbea1-131">這些是獨立的角色群組，不會累計。</span><span class="sxs-lookup"><span data-stu-id="fbea1-131">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="fbea1-132">例如，如果您想要授與某個帳戶只能檢視項目及其位置的權限，請授與「內容瀏覽器清單檢視器」權限。</span><span class="sxs-lookup"><span data-stu-id="fbea1-132">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="fbea1-133">如果您想要讓該相同帳戶也能夠檢視清單中項目的內容，也請授與「內容瀏覽器內容檢視器」權限。</span><span class="sxs-lookup"><span data-stu-id="fbea1-133">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="fbea1-134">您也可以將一個或兩個角色指派給自訂角色群組，以量身打造內容瀏覽器的存取權。</span><span class="sxs-lookup"><span data-stu-id="fbea1-134">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="fbea1-135">如何使用內容總管</span><span class="sxs-lookup"><span data-stu-id="fbea1-135">How to use content explorer</span></span>

1. <span data-ttu-id="fbea1-136">開啟 **Microsoft 365 合規性中心**  > **資料分類** > **內容總管**。</span><span class="sxs-lookup"><span data-stu-id="fbea1-136">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="fbea1-137">如果您知道標籤的名稱或敏感性資訊類型，便可在搜尋方塊中輸入。</span><span class="sxs-lookup"><span data-stu-id="fbea1-137">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="fbea1-138">您也可以展開標籤類型，然後從清單選取標籤來瀏覽項目，以下顯示的是清單保留標籤部分中的項目。</span><span class="sxs-lookup"><span data-stu-id="fbea1-138">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="fbea1-139">在 **[所有位置]** 底下選取位置，並向下切入資料夾結構至項目。</span><span class="sxs-lookup"><span data-stu-id="fbea1-139">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="fbea1-140">按兩下以在內容總管中於機開啟項目。</span><span class="sxs-lookup"><span data-stu-id="fbea1-140">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbea1-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fbea1-141">See also</span></span>

- [<span data-ttu-id="fbea1-142">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="fbea1-142">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="fbea1-143">保留標籤</span><span class="sxs-lookup"><span data-stu-id="fbea1-143">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="fbea1-144">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="fbea1-144">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="fbea1-145">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="fbea1-145">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="fbea1-146">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="fbea1-146">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
