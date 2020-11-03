---
title: Microsoft 365 Defender 必要條件
description: 深入瞭解 Microsoft 365 Defender 的授權、硬體和軟體需求，以及其他設定設定
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844773"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="79214-104">Microsoft 365 Defender 必要條件</span><span class="sxs-lookup"><span data-stu-id="79214-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="79214-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="79214-105">**Applies to:**</span></span>
- <span data-ttu-id="79214-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79214-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="79214-107">深入瞭解布建和使用 [Microsoft 365 Defender](microsoft-threat-protection.md)的其他需求。</span><span class="sxs-lookup"><span data-stu-id="79214-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="79214-108">授權需求</span><span class="sxs-lookup"><span data-stu-id="79214-108">Licensing requirements</span></span>
<span data-ttu-id="79214-109">這些授權中的任何一種可讓您存取 microsoft 365 security center 中的 Microsoft 365 Defender 功能，而不需要額外成本：</span><span class="sxs-lookup"><span data-stu-id="79214-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="79214-110">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="79214-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="79214-111">Microsoft 365 E5 Security 或 A5 Security</span><span class="sxs-lookup"><span data-stu-id="79214-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="79214-112">Windows 10 企業版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="79214-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="79214-113">Enterprise 可移動性 + Security (EMS) E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="79214-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="79214-114">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="79214-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="79214-115">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="79214-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="79214-116">適用於身分識別的 Microsoft Defender </span><span class="sxs-lookup"><span data-stu-id="79214-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="79214-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="79214-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="79214-118">適用于 Office 的 Defender 365 (方案 2) </span><span class="sxs-lookup"><span data-stu-id="79214-118">Defender for Office 365 (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="79214-119">Office 365 的試用版授權目前不提供 Microsoft 365 Defender 的存取權。</span><span class="sxs-lookup"><span data-stu-id="79214-119">Trial licenses for Office 365 currently do not provide access to Microsoft 365 Defender.</span></span>

<span data-ttu-id="79214-120">如需詳細資訊，請 [查看 Microsoft 365 企業版服務方案](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="79214-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="79214-121">還沒有授權？</span><span class="sxs-lookup"><span data-stu-id="79214-121">Don't have license yet?</span></span> [<span data-ttu-id="79214-122">試用或購買 Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="79214-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="79214-123">檢查您現有的授權</span><span class="sxs-lookup"><span data-stu-id="79214-123">Check your existing  licenses</span></span>
<span data-ttu-id="79214-124">移至 Microsoft 365 系統管理中心 ([admin.microsoft.com](https://admin.microsoft.com/)) 以查看您現有的授權。</span><span class="sxs-lookup"><span data-stu-id="79214-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="79214-125">在系統管理中心中，移至 **[帳單]** >  **[授權]** 。</span><span class="sxs-lookup"><span data-stu-id="79214-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="79214-126">您必須被指派至 [AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)的 **帳務系統管理員** 或 **全域讀取** 者角色，才能看到授權資訊。</span><span class="sxs-lookup"><span data-stu-id="79214-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="79214-127">如果您遭遇存取的問題，請與全域管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="79214-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="79214-128">必要的權限</span><span class="sxs-lookup"><span data-stu-id="79214-128">Required permissions</span></span>
<span data-ttu-id="79214-129">您必須是 **全域系統管理員** 或 Azure Active Directory 中的 **安全性系統管理員** ，才可開啟 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="79214-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="79214-130">如需使用 Microsoft 365 Defender 所需的角色清單，以及如何管制資料存取的相關資訊，請參閱 [管理 Microsoft 365 Defender 的存取](mtp-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="79214-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="79214-131">瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="79214-131">Browser requirements</span></span>
<span data-ttu-id="79214-132">使用 Microsoft Edge、Internet Explorer 11 或任何與 HTML 5 相容的網頁瀏覽器，存取 microsoft 365 security center 中的 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="79214-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="79214-133">可供美國 GCC、GCC 高及其他美國政府機構供貨</span><span class="sxs-lookup"><span data-stu-id="79214-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="79214-134">目前 *無法* 使用 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="79214-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="79214-135">美國政府社區雲端 (GCC) </span><span class="sxs-lookup"><span data-stu-id="79214-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="79214-136">美國政府社區雲端高 (GCC 高) </span><span class="sxs-lookup"><span data-stu-id="79214-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="79214-137">美國國防部</span><span class="sxs-lookup"><span data-stu-id="79214-137">US Department of Defense</span></span>
- <span data-ttu-id="79214-138">具有商業授權的所有美國政府機構</span><span class="sxs-lookup"><span data-stu-id="79214-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="79214-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="79214-139">Related topics</span></span>
- [<span data-ttu-id="79214-140">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="79214-140">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="79214-141">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79214-141">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="79214-142">管理存取權和許可權</span><span class="sxs-lookup"><span data-stu-id="79214-142">Manage access and permissions</span></span>](mtp-permissions.md)
