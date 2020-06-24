---
title: Microsoft 威脅防護先決條件
description: 了解 Microsoft 威脅防護的相關授權、硬體和軟體需求，以及其他組態設定
keywords: 需求，必要條件，硬體，軟體，瀏覽器，MTP，M365，授權，E5，A5，EMS，購買
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c64adf870d3669b983e11093196f59c82b1f59e0
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844903"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="cdc68-104">Microsoft 威脅防護先決條件</span><span class="sxs-lookup"><span data-stu-id="cdc68-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="cdc68-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="cdc68-105">**Applies to:**</span></span>
- <span data-ttu-id="cdc68-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="cdc68-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="cdc68-107">深入瞭解布建和使用[Microsoft 威脅防護](microsoft-threat-protection.md)的其他需求。</span><span class="sxs-lookup"><span data-stu-id="cdc68-107">Learn about licensing and other requirements for provisioning and using [Microsoft Threat Protection](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="cdc68-108">授權需求</span><span class="sxs-lookup"><span data-stu-id="cdc68-108">Licensing requirements</span></span>
<span data-ttu-id="cdc68-109">這些授權中的任何一種可讓您存取 microsoft 365 安全中心的 Microsoft 威脅防護功能，而不需要額外成本：</span><span class="sxs-lookup"><span data-stu-id="cdc68-109">Any of these licenses gives you access to Microsoft Threat Protection features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="cdc68-110">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="cdc68-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="cdc68-111">Microsoft 365 E5 Security 或 A5 Security</span><span class="sxs-lookup"><span data-stu-id="cdc68-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="cdc68-112">Windows 10 企業版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="cdc68-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="cdc68-113">Enterprise 可移動性 + Security （EMS） E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="cdc68-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="cdc68-114">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="cdc68-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="cdc68-115">Microsoft Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="cdc68-115">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="cdc68-116">Azure 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="cdc68-116">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="cdc68-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cdc68-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="cdc68-118">Office 365 高級威脅防護（方案2）</span><span class="sxs-lookup"><span data-stu-id="cdc68-118">Office 365 Advanced Threat Protection (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="cdc68-119">Office 365 的試用版授權目前不提供 Microsoft 威脅防護的存取權。</span><span class="sxs-lookup"><span data-stu-id="cdc68-119">Trial licenses for Office 365 currently do not provide access to Microsoft Threat Protection.</span></span>

<span data-ttu-id="cdc68-120">如需詳細資訊，請[查看 Microsoft 365 企業版服務方案](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="cdc68-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="cdc68-121">還沒有授權？</span><span class="sxs-lookup"><span data-stu-id="cdc68-121">Don't have license yet?</span></span> [<span data-ttu-id="cdc68-122">試用或購買 Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="cdc68-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="cdc68-123">檢查您現有的授權</span><span class="sxs-lookup"><span data-stu-id="cdc68-123">Check your existing  licenses</span></span>
<span data-ttu-id="cdc68-124">移至 Microsoft 365 系統管理中心（[admin.microsoft.com](https://admin.microsoft.com/)）以查看您現有的授權。</span><span class="sxs-lookup"><span data-stu-id="cdc68-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="cdc68-125">在系統管理中心中，移至 **[帳單]** >  **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="cdc68-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="cdc68-126">您必須被指派至[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)的**帳務系統管理員**或**全域讀取**者角色，才能看到授權資訊。</span><span class="sxs-lookup"><span data-stu-id="cdc68-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="cdc68-127">如果您遭遇存取的問題，請與全域管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="cdc68-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="cdc68-128">必要的權限</span><span class="sxs-lookup"><span data-stu-id="cdc68-128">Required permissions</span></span>
<span data-ttu-id="cdc68-129">您必須是**全域系統管理員**或 Azure Active Directory 中的**安全性系統管理員**，才可開啟 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="cdc68-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> <span data-ttu-id="cdc68-130">如需使用 Microsoft 威脅防護所需的角色清單，以及如何管制資料存取的相關資訊，請參閱[管理 Microsoft 威脅防護的存取](mtp-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc68-130">For the list of roles required to use Microsoft Threat Protection and information on how access to data is regulated, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="cdc68-131">瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="cdc68-131">Browser requirements</span></span>
<span data-ttu-id="cdc68-132">使用 Microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 標準的網頁瀏覽器，存取 microsoft 365 security center 中的 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="cdc68-132">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="cdc68-133">可供美國 GCC、GCC 高及其他美國政府機構供貨</span><span class="sxs-lookup"><span data-stu-id="cdc68-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="cdc68-134">目前，Microsoft 威脅防護*無法*用於：</span><span class="sxs-lookup"><span data-stu-id="cdc68-134">Currently, Microsoft Threat Protection is *not* available to:</span></span>
- <span data-ttu-id="cdc68-135">美國政府社區雲端（GCC）</span><span class="sxs-lookup"><span data-stu-id="cdc68-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="cdc68-136">美國政府社區雲端高（GCC 高）</span><span class="sxs-lookup"><span data-stu-id="cdc68-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="cdc68-137">美國國防部</span><span class="sxs-lookup"><span data-stu-id="cdc68-137">US Department of Defense</span></span>
- <span data-ttu-id="cdc68-138">具有商業授權的所有美國政府機構</span><span class="sxs-lookup"><span data-stu-id="cdc68-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="cdc68-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="cdc68-139">Related topics</span></span>
- [<span data-ttu-id="cdc68-140">Microsoft 威脅防護概觀</span><span class="sxs-lookup"><span data-stu-id="cdc68-140">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="cdc68-141">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="cdc68-141">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="cdc68-142">管理存取權和許可權</span><span class="sxs-lookup"><span data-stu-id="cdc68-142">Manage access and permissions</span></span>](mtp-permissions.md)
