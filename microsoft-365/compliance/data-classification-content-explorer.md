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
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268469"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="ea58f-103">使用資料分類內容總管 (預覽)</span><span class="sxs-lookup"><span data-stu-id="ea58f-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="ea58f-104">資料分類內容總管可讓您本機檢視概觀頁面中摘要的項目。</span><span class="sxs-lookup"><span data-stu-id="ea58f-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="ea58f-105">內容總管</span><span class="sxs-lookup"><span data-stu-id="ea58f-105">Content explorer</span></span>

<span data-ttu-id="ea58f-106">內容總管是具有敏感度標籤、保留標籤或已分類為貴組織敏感性資訊類型之項目的目前快照。</span><span class="sxs-lookup"><span data-stu-id="ea58f-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

![內容總管摺疊的螢幕擷取畫面](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="ea58f-108">權限</span><span class="sxs-lookup"><span data-stu-id="ea58f-108">Permissions</span></span>

<span data-ttu-id="ea58f-109">有兩個角色可以將存取權授與內容瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="ea58f-109">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="ea58f-110">**內容瀏覽器清單檢視器**：這個角色的成員資格可讓您查看每個項目及其位置。</span><span class="sxs-lookup"><span data-stu-id="ea58f-110">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="ea58f-111">**內容瀏覽器內容檢視器**：這個角色的成員資格可讓您檢視清單中每個項目的內容。</span><span class="sxs-lookup"><span data-stu-id="ea58f-111">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="ea58f-112">您用來存取內容瀏覽器的帳戶必須屬於其中一個或兩個角色。</span><span class="sxs-lookup"><span data-stu-id="ea58f-112">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="ea58f-113">這些是獨立的角色，不會累計。</span><span class="sxs-lookup"><span data-stu-id="ea58f-113">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="ea58f-114">例如，如果您想要授與某個帳戶只能檢視項目及其位置的權限，請授與「內容瀏覽器清單檢視器」權限。</span><span class="sxs-lookup"><span data-stu-id="ea58f-114">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="ea58f-115">如果您想要讓該相同帳戶也能夠檢視清單中項目的內容，也請授與「內容瀏覽器內容檢視器」權限。</span><span class="sxs-lookup"><span data-stu-id="ea58f-115">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="ea58f-116">如何使用內容總管</span><span class="sxs-lookup"><span data-stu-id="ea58f-116">How to use content explorer</span></span>

1. <span data-ttu-id="ea58f-117">開啟 **Microsoft 365 合規性中心**  > **資料分類** > **內容總管**。</span><span class="sxs-lookup"><span data-stu-id="ea58f-117">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="ea58f-118">如果您知道標籤的名稱或敏感性資訊類型，便可在搜尋方塊中輸入。</span><span class="sxs-lookup"><span data-stu-id="ea58f-118">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="ea58f-119">您也可以展開標籤類型，然後從清單選取標籤來瀏覽項目，以下顯示的是清單保留標籤部分中的項目。</span><span class="sxs-lookup"><span data-stu-id="ea58f-119">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="ea58f-120">在 **[所有位置]** 底下選取位置，並向下切入資料夾結構至項目。</span><span class="sxs-lookup"><span data-stu-id="ea58f-120">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="ea58f-121">按兩下以在內容總管中於本機開啟項目。</span><span class="sxs-lookup"><span data-stu-id="ea58f-121">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea58f-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ea58f-122">See also</span></span>

- [<span data-ttu-id="ea58f-123">敏感性標籤</span><span class="sxs-lookup"><span data-stu-id="ea58f-123">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="ea58f-124">保留標籤</span><span class="sxs-lookup"><span data-stu-id="ea58f-124">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="ea58f-125">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="ea58f-125">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="ea58f-126">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="ea58f-126">Overview of retention policies</span></span>](retention-policies.md)
