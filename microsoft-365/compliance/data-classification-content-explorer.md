---
title: 使用資料分類內容總管 (預覽)
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
ms.openlocfilehash: 9e9ad76d2bdd7f74368121346f7e04d1208803ff
ms.sourcegitcommit: 99d759d5c4e7d81266c3ebc087eaa37486cc0bc1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2019
ms.locfileid: "39818855"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="86c5b-103">使用資料分類內容總管 (預覽)</span><span class="sxs-lookup"><span data-stu-id="86c5b-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="86c5b-104">資料分類內容總管可讓您本機檢視概觀頁面中摘要的項目。</span><span class="sxs-lookup"><span data-stu-id="86c5b-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="86c5b-105">內容總管</span><span class="sxs-lookup"><span data-stu-id="86c5b-105">Content explorer</span></span>

<span data-ttu-id="86c5b-106">內容總管會顯示具有敏感度標籤、保留標籤或已分類為貴組織敏感性資訊類型之項目的目前快照。</span><span class="sxs-lookup"><span data-stu-id="86c5b-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="86c5b-107">敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="86c5b-107">Sensitive information types</span></span>

<span data-ttu-id="86c5b-108">[DLP 原則](data-loss-prevention-policies.md)有助於保護敏感性資訊 (已定義為**敏感性資訊類型**)。</span><span class="sxs-lookup"><span data-stu-id="86c5b-108">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="86c5b-109">Microsoft 365 包括涵蓋許多不同區域的[許多常見敏感性資訊類型的定義](what-the-sensitive-information-types-look-for.md)，可供您使用。</span><span class="sxs-lookup"><span data-stu-id="86c5b-109">Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> <span data-ttu-id="86c5b-110">例如，信用卡號碼、銀行帳戶號碼、國家/地區識別碼和 Windows Live ID 服務號碼。</span><span class="sxs-lookup"><span data-stu-id="86c5b-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="86c5b-111">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="86c5b-111">Sensitivity labels</span></span>

<span data-ttu-id="86c5b-112">[敏感度標籤](sensitivity-labels.md)只是一個標記，指出您組織的項目值。</span><span class="sxs-lookup"><span data-stu-id="86c5b-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="86c5b-113">可手動或自動套用。</span><span class="sxs-lookup"><span data-stu-id="86c5b-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="86c5b-114">一旦套用，即會將它內嵌在文件中，並在所有的位置追蹤。</span><span class="sxs-lookup"><span data-stu-id="86c5b-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="86c5b-115">敏感性標籤會啟用各種防護行為，例如強制浮水印或加密。</span><span class="sxs-lookup"><span data-stu-id="86c5b-115">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="86c5b-116">啟用端點保護後，您甚至可以防止項目離開組織控制。</span><span class="sxs-lookup"><span data-stu-id="86c5b-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="86c5b-117">保留標籤</span><span class="sxs-lookup"><span data-stu-id="86c5b-117">Retention labels</span></span>

<span data-ttu-id="86c5b-118">[保留標籤](labels.md)可讓您定義保留標記的項目的時間長度，以及刪除它之前要採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="86c5b-118">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="86c5b-119">它們會透過原則來手動或自動套用。</span><span class="sxs-lookup"><span data-stu-id="86c5b-119">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="86c5b-120">它們可以在協助您組織保持遵守法律和法規需求方面扮演一個角色。</span><span class="sxs-lookup"><span data-stu-id="86c5b-120">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![內容總管摺疊的螢幕擷取畫面](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="86c5b-122">權限</span><span class="sxs-lookup"><span data-stu-id="86c5b-122">Permissions</span></span>

<span data-ttu-id="86c5b-123">有兩個角色可以將存取權授與內容瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="86c5b-123">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="86c5b-124">**內容瀏覽器清單檢視器**：這個角色的成員資格可讓您查看每個項目及其位置。</span><span class="sxs-lookup"><span data-stu-id="86c5b-124">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="86c5b-125">**內容瀏覽器內容檢視器**：這個角色的成員資格可讓您檢視清單中每個項目的內容。</span><span class="sxs-lookup"><span data-stu-id="86c5b-125">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="86c5b-126">您用來存取內容瀏覽器的帳戶必須屬於其中一個或兩個角色。</span><span class="sxs-lookup"><span data-stu-id="86c5b-126">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="86c5b-127">這些是獨立的角色，不會累計。</span><span class="sxs-lookup"><span data-stu-id="86c5b-127">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="86c5b-128">例如，如果您想要授與某個帳戶只能檢視項目及其位置的權限，請授與「內容瀏覽器清單檢視器」權限。</span><span class="sxs-lookup"><span data-stu-id="86c5b-128">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="86c5b-129">如果您想要讓該相同帳戶也能夠檢視清單中項目的內容，也請授與「內容瀏覽器內容檢視器」權限。</span><span class="sxs-lookup"><span data-stu-id="86c5b-129">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="86c5b-130">如何使用內容總管</span><span class="sxs-lookup"><span data-stu-id="86c5b-130">How to use content explorer</span></span>

1. <span data-ttu-id="86c5b-131">開啟 **Microsoft 365 合規性中心**  > **資料分類** > **內容總管**。</span><span class="sxs-lookup"><span data-stu-id="86c5b-131">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="86c5b-132">如果您知道標籤的名稱或敏感性資訊類型，便可在搜尋方塊中輸入。</span><span class="sxs-lookup"><span data-stu-id="86c5b-132">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="86c5b-133">您也可以展開標籤類型，然後從清單選取標籤來瀏覽項目，以下顯示的是清單保留標籤部分中的項目。</span><span class="sxs-lookup"><span data-stu-id="86c5b-133">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="86c5b-134">在 **[所有位置]** 底下選取位置，並向下切入資料夾結構至項目。</span><span class="sxs-lookup"><span data-stu-id="86c5b-134">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="86c5b-135">按兩下以在內容總管中於機開啟項目。</span><span class="sxs-lookup"><span data-stu-id="86c5b-135">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="86c5b-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="86c5b-136">See also</span></span>

- [<span data-ttu-id="86c5b-137">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="86c5b-137">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="86c5b-138">保留標籤</span><span class="sxs-lookup"><span data-stu-id="86c5b-138">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="86c5b-139">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="86c5b-139">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="86c5b-140">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="86c5b-140">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="86c5b-141">資料外洩防護概觀</span><span class="sxs-lookup"><span data-stu-id="86c5b-141">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
