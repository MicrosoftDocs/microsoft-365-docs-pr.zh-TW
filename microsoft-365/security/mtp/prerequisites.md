---
title: Microsoft 365 Defender 必要條件
description: 深入瞭解 Microsoft 365 Defender 的授權、硬體和軟體需求，以及其他設定設定
keywords: 需求，必要條件，硬體，軟體，瀏覽器，MTP，M365，授權，E5，A5，EMS，購買
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: afa5cd42545eddafb1d0ec1a6d88eb0903e07820
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454548"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="81e46-104">Microsoft 365 Defender 必要條件</span><span class="sxs-lookup"><span data-stu-id="81e46-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="81e46-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="81e46-105">**Applies to:**</span></span>
- <span data-ttu-id="81e46-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81e46-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="81e46-107">深入瞭解布建和使用 [Microsoft 365 Defender](microsoft-threat-protection.md)的其他需求。</span><span class="sxs-lookup"><span data-stu-id="81e46-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="81e46-108">授權需求</span><span class="sxs-lookup"><span data-stu-id="81e46-108">Licensing requirements</span></span>
<span data-ttu-id="81e46-109">這些授權中的任何一種可讓您存取 microsoft 365 security center 中的 Microsoft 365 Defender 功能，而不需要額外成本：</span><span class="sxs-lookup"><span data-stu-id="81e46-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="81e46-110">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="81e46-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="81e46-111">Microsoft 365 E5 Security 或 A5 Security</span><span class="sxs-lookup"><span data-stu-id="81e46-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="81e46-112">Windows 10 企業版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="81e46-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="81e46-113">Enterprise 可移動性 + Security (EMS) E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="81e46-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="81e46-114">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="81e46-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="81e46-115">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="81e46-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="81e46-116">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="81e46-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="81e46-117">Microsoft 雲端應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="81e46-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="81e46-118">適用于 Office 的 Defender 365 (方案 2) </span><span class="sxs-lookup"><span data-stu-id="81e46-118">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="81e46-119">如需詳細資訊，請 [查看 Microsoft 365 企業版服務方案](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="81e46-119">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="81e46-120">還沒有授權？</span><span class="sxs-lookup"><span data-stu-id="81e46-120">Don't have license yet?</span></span> [<span data-ttu-id="81e46-121">試用或購買 Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="81e46-121">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="81e46-122">檢查您現有的授權</span><span class="sxs-lookup"><span data-stu-id="81e46-122">Check your existing  licenses</span></span>
<span data-ttu-id="81e46-123">移至 Microsoft 365 系統管理中心 ([admin.microsoft.com](https://admin.microsoft.com/)) 以查看您現有的授權。</span><span class="sxs-lookup"><span data-stu-id="81e46-123">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="81e46-124">在系統管理中心中，移至 **[帳單]** >  **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="81e46-124">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="81e46-125">您必須被指派至 [AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)的 **帳務系統管理員** 或 **全域讀取** 者角色，才能看到授權資訊。</span><span class="sxs-lookup"><span data-stu-id="81e46-125">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="81e46-126">如果您遭遇存取的問題，請與全域管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="81e46-126">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="81e46-127">必要的權限</span><span class="sxs-lookup"><span data-stu-id="81e46-127">Required permissions</span></span>
<span data-ttu-id="81e46-128">您必須是 **全域系統管理員** 或 Azure Active Directory 中的 **安全性系統管理員** ，才可開啟 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="81e46-128">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="81e46-129">如需使用 Microsoft 365 Defender 所需的角色清單，以及如何管制資料存取的相關資訊，請參閱 [管理 Microsoft 365 Defender 的存取](mtp-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="81e46-129">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="81e46-130">瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="81e46-130">Browser requirements</span></span>
<span data-ttu-id="81e46-131">使用 Microsoft Edge、Internet Explorer 11 或任何與 HTML 5 相容的網頁瀏覽器，存取 microsoft 365 security center 中的 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="81e46-131">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="81e46-132">可供美國 GCC、GCC 高及其他美國政府機構供貨</span><span class="sxs-lookup"><span data-stu-id="81e46-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="81e46-133">目前 *無法* 使用 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="81e46-133">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="81e46-134">美國政府社區雲端 (GCC) </span><span class="sxs-lookup"><span data-stu-id="81e46-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="81e46-135">美國政府社區雲端高 (GCC 高) </span><span class="sxs-lookup"><span data-stu-id="81e46-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="81e46-136">美國國防部</span><span class="sxs-lookup"><span data-stu-id="81e46-136">US Department of Defense</span></span>
- <span data-ttu-id="81e46-137">具有商業授權的所有美國政府機構</span><span class="sxs-lookup"><span data-stu-id="81e46-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="81e46-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="81e46-138">Related topics</span></span>
- [<span data-ttu-id="81e46-139">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="81e46-139">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="81e46-140">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81e46-140">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="81e46-141">管理存取權和許可權</span><span class="sxs-lookup"><span data-stu-id="81e46-141">Manage access and permissions</span></span>](mtp-permissions.md)
