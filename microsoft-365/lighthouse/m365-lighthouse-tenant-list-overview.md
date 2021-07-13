---
title: Microsoft 365 Lighthouse 租使用者清單概覽
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 針對受管理的服務提供者 (MSPs) 使用 Microsoft 365 Lighthouse，瞭解租使用者清單。
ms.openlocfilehash: 05c6bf6c1b9529d05fac04c2d5c43802280cfbc9
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395068"
---
# <a name="microsoft-365-lighthouse-tenant-list-overview"></a><span data-ttu-id="9c409-103">Microsoft 365 Lighthouse 租使用者清單概覽</span><span class="sxs-lookup"><span data-stu-id="9c409-103">Microsoft 365 Lighthouse tenant list overview</span></span>

> [!NOTE]
> <span data-ttu-id="9c409-104">本文所述的功能都是在預覽中進行變更，而且只有符合 [需求](m365-lighthouse-requirements.md)的合作夥伴才能使用。</span><span class="sxs-lookup"><span data-stu-id="9c409-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="9c409-105">如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。</span><span class="sxs-lookup"><span data-stu-id="9c409-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="9c409-106">Microsoft 365 Lighthouse 租使用者清單可深入瞭解您具有合約的不同承租人，包括與 Microsoft 365 Lighthouse 相關的承租人上架狀態。</span><span class="sxs-lookup"><span data-stu-id="9c409-106">The Microsoft 365 Lighthouse tenant list provides insights into the different tenants you have a contract with, including tenant onboarding status relative to Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="9c409-107">租使用者清單也可讓您標示承租人，以在 Microsoft 365 Lighthouse 中提供不同的篩選，並深入瞭解特定租使用者的詳細資訊及其部署計畫的狀態。</span><span class="sxs-lookup"><span data-stu-id="9c409-107">The tenant list also lets you tag tenants to provide different filters throughout Microsoft 365 Lighthouse, and drill down to learn more about a given tenant and the status of their deployment plan.</span></span>

<span data-ttu-id="9c409-108">當租使用者符合 [Microsoft 365 Lighthouse 上架需求](m365-lighthouse-requirements.md)之後，其狀態會在租使用者 **清單中顯示** 為作用中。</span><span class="sxs-lookup"><span data-stu-id="9c409-108">After your tenants meet the [Microsoft 365 Lighthouse onboarding requirements](m365-lighthouse-requirements.md), their status will show as **Active** in the tenant list.</span></span>

<span data-ttu-id="9c409-109">若要在 Microsoft 365 Lighthouse 中存取租使用者清單，請在左側流覽窗格中，選取 [**承租人**]，以開啟承租人頁面。</span><span class="sxs-lookup"><span data-stu-id="9c409-109">To access the tenant list in Microsoft 365 Lighthouse, select **Tenants** in the left navigation pane to open the Tenants page.</span></span>

## <a name="tenant-status"></a><span data-ttu-id="9c409-110">租使用者狀態</span><span class="sxs-lookup"><span data-stu-id="9c409-110">Tenant status</span></span>

<span data-ttu-id="9c409-111">下表顯示不同的狀態郵件及其意義。</span><span class="sxs-lookup"><span data-stu-id="9c409-111">The following table shows the different status messages and their meaning.</span></span><br><br>

| <span data-ttu-id="9c409-112">狀態訊息</span><span class="sxs-lookup"><span data-stu-id="9c409-112">Status message</span></span> | <span data-ttu-id="9c409-113">描述</span><span class="sxs-lookup"><span data-stu-id="9c409-113">Description</span></span> |
|--|--|
| <span data-ttu-id="9c409-114">作用中</span><span class="sxs-lookup"><span data-stu-id="9c409-114">Active</span></span> | <span data-ttu-id="9c409-115">上架和資料流程已開始。</span><span class="sxs-lookup"><span data-stu-id="9c409-115">Onboarding and data flow has started.</span></span> |
| <span data-ttu-id="9c409-116">處理中</span><span class="sxs-lookup"><span data-stu-id="9c409-116">In process</span></span> | <span data-ttu-id="9c409-117">已探索租使用者，但未完全架。</span><span class="sxs-lookup"><span data-stu-id="9c409-117">Tenant discovered, but not fully onboarded.</span></span> |
| <span data-ttu-id="9c409-118">不合格、一起</span><span class="sxs-lookup"><span data-stu-id="9c409-118">Ineligible, DAP</span></span> | <span data-ttu-id="9c409-119">委派的系統管理員許可權 (需要) 設定。</span><span class="sxs-lookup"><span data-stu-id="9c409-119">Delegated Admin Privileges (DAP) setup is required.</span></span> |
| <span data-ttu-id="9c409-120">不合格，使用者計數</span><span class="sxs-lookup"><span data-stu-id="9c409-120">Ineligible, user count</span></span> | <span data-ttu-id="9c409-121">租使用者的使用者數目超過允許的數目。</span><span class="sxs-lookup"><span data-stu-id="9c409-121">Tenant has more users than allowed.</span></span> |
| <span data-ttu-id="9c409-122">不合格，授權</span><span class="sxs-lookup"><span data-stu-id="9c409-122">Ineligible, license</span></span> | <span data-ttu-id="9c409-123">承租人沒有必要的授權。</span><span class="sxs-lookup"><span data-stu-id="9c409-123">Tenant does not have required license.</span></span> |
| <span data-ttu-id="9c409-124">非作用中</span><span class="sxs-lookup"><span data-stu-id="9c409-124">Inactive</span></span> | <span data-ttu-id="9c409-125">租使用者不再使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="9c409-125">Tenant is no longer active.</span></span> |

<span data-ttu-id="9c409-126">一旦停用租使用者，您就無法在承租人上採取動作，Microsoft 365 Lighthouse 完成 inactivation 程式。</span><span class="sxs-lookup"><span data-stu-id="9c409-126">Once you inactivate a tenant, you can't take action on the tenant while Microsoft 365 Lighthouse completes the inactivation process.</span></span> <span data-ttu-id="9c409-127">Inactivation 最多可能需要48個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="9c409-127">It may take up to 48 hours for inactivation to complete.</span></span>

<span data-ttu-id="9c409-128">如果您決定重新啟用租使用者，可能需要長達48小時的資料重新顯示。</span><span class="sxs-lookup"><span data-stu-id="9c409-128">If you decide to reactivate a tenant, it may take up to 48 hours for data to reappear.</span></span>

## <a name="tenant-tags"></a><span data-ttu-id="9c409-129">承租人標記</span><span class="sxs-lookup"><span data-stu-id="9c409-129">Tenant tags</span></span>

<span data-ttu-id="9c409-130">您可以在 Microsoft 365 Lighthouse 內使用自訂標籤標記客戶承租人。</span><span class="sxs-lookup"><span data-stu-id="9c409-130">You can tag your customer tenants with a custom label within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="9c409-131">這些標記可用來組織您的承租人，也可協助您輕鬆篩選現有的視圖和洞察力，以供相關的客戶承租人集合使用。</span><span class="sxs-lookup"><span data-stu-id="9c409-131">These tags can be used to organize your tenants and can also help you easily filter the existing views and insights available to relevant sets of customer tenants.</span></span> <span data-ttu-id="9c409-132">您也可以在承租人頁面上管理您的標記以及所指派的承租人。</span><span class="sxs-lookup"><span data-stu-id="9c409-132">You can also manage your tags and which tenants they're assigned to from the Tenants page.</span></span>

## <a name="related-content"></a><span data-ttu-id="9c409-133">相關內容</span><span class="sxs-lookup"><span data-stu-id="9c409-133">Related content</span></span>

<span data-ttu-id="9c409-134">Microsoft 365 Lighthouse (文章) [的需求](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="9c409-134">[Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (article)\</span></span>
<span data-ttu-id="9c409-135">[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="9c409-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>