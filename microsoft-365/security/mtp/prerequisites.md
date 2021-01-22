---
title: Microsoft 365 Defender 先決條件
description: 瞭解 Microsoft 365 Defender 的授權、硬體與軟體需求，以及其他設定設定
keywords: 需求、先決條件、硬體、軟體、瀏覽器、MTP、M365、授權、E5、A5、EMS、購買
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
ms.openlocfilehash: ee1777debdb91a6ac73737db2db48e434ed3e2e2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930087"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="ab1f0-104">Microsoft 365 Defender 先決條件</span><span class="sxs-lookup"><span data-stu-id="ab1f0-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ab1f0-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="ab1f0-105">**Applies to:**</span></span>
- <span data-ttu-id="ab1f0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab1f0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ab1f0-107">瞭解提供和使用 [Microsoft 365 Defender](microsoft-threat-protection.md)的授權與其他需求。</span><span class="sxs-lookup"><span data-stu-id="ab1f0-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="ab1f0-108">授權需求</span><span class="sxs-lookup"><span data-stu-id="ab1f0-108">Licensing requirements</span></span>
<span data-ttu-id="ab1f0-109">上述任何授權都提供您 Microsoft 365 資訊安全中心 Microsoft 365 Defender 功能的存取權，無需支付額外費用：</span><span class="sxs-lookup"><span data-stu-id="ab1f0-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="ab1f0-110">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="ab1f0-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="ab1f0-111">Microsoft 365 E5 安全性或 A5 安全性</span><span class="sxs-lookup"><span data-stu-id="ab1f0-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="ab1f0-112">Windows 10 企業版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="ab1f0-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="ab1f0-113">Enterprise Mobility + Security (EMS) E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="ab1f0-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="ab1f0-114">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="ab1f0-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="ab1f0-115">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ab1f0-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="ab1f0-116">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ab1f0-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="ab1f0-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ab1f0-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="ab1f0-118">Office 365 方案 2 (的後) </span><span class="sxs-lookup"><span data-stu-id="ab1f0-118">Defender for Office 365 (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="ab1f0-119">Office 365 試用版授權目前無法提供 Microsoft 365 Defender 的存取權。</span><span class="sxs-lookup"><span data-stu-id="ab1f0-119">Trial licenses for Office 365 currently do not provide access to Microsoft 365 Defender.</span></span>

<span data-ttu-id="ab1f0-120">詳細資訊請參閱 [Microsoft 365 企業版服務方案](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="ab1f0-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="ab1f0-121">還沒有授權嗎？</span><span class="sxs-lookup"><span data-stu-id="ab1f0-121">Don't have license yet?</span></span> [<span data-ttu-id="ab1f0-122">試用或購買 Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="ab1f0-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="ab1f0-123">檢查您現有的授權</span><span class="sxs-lookup"><span data-stu-id="ab1f0-123">Check your existing  licenses</span></span>
<span data-ttu-id="ab1f0-124">請前往 Microsoft 365 系統管理中心 [ (admin.microsoft.com) ](https://admin.microsoft.com/) 您現有的授權。</span><span class="sxs-lookup"><span data-stu-id="ab1f0-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="ab1f0-125">在系統管理中心中，移至 **[帳單]** >  **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="ab1f0-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="ab1f0-126">您必須在 [Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 中指派帳單系統管理員或 **全域** 讀取者角色，才能看到授權資訊。</span><span class="sxs-lookup"><span data-stu-id="ab1f0-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="ab1f0-127">如果您遭遇存取的問題，請與全域管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="ab1f0-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="ab1f0-128">必要的權限</span><span class="sxs-lookup"><span data-stu-id="ab1f0-128">Required permissions</span></span>
<span data-ttu-id="ab1f0-129">您必須是 **Azure** Active Directory 中的全域系統管理員或安全性系統管理員，才能開啟 Microsoft 365 Defender。 </span><span class="sxs-lookup"><span data-stu-id="ab1f0-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="ab1f0-130">若要瞭解使用 Microsoft 365 Defender 所需角色的清單，以及如何規範資料存取，請參閱如何管理[Microsoft 365 Defender 存取權。](mtp-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="ab1f0-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="ab1f0-131">瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="ab1f0-131">Browser requirements</span></span>
<span data-ttu-id="ab1f0-132">在 Microsoft 365 資訊安全中心使用 Microsoft Edge、Internet Explorer 11 或任何 HTML 5 相容網頁瀏覽器存取 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="ab1f0-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="ab1f0-133">可在美國 GCC、GCC High 及其他美國政府機關使用</span><span class="sxs-lookup"><span data-stu-id="ab1f0-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="ab1f0-134">目前，Microsoft 365 Defender *無法* 用於：</span><span class="sxs-lookup"><span data-stu-id="ab1f0-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="ab1f0-135">美國政府社群雲端 (GCC) </span><span class="sxs-lookup"><span data-stu-id="ab1f0-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="ab1f0-136">美國政府社群雲端 High (GCC High) </span><span class="sxs-lookup"><span data-stu-id="ab1f0-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="ab1f0-137">美國商務部</span><span class="sxs-lookup"><span data-stu-id="ab1f0-137">US Department of Defense</span></span>
- <span data-ttu-id="ab1f0-138">所有擁有商業授權之美國政府機關</span><span class="sxs-lookup"><span data-stu-id="ab1f0-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab1f0-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="ab1f0-139">Related topics</span></span>
- [<span data-ttu-id="ab1f0-140">Microsoft 365 Defender 概觀</span><span class="sxs-lookup"><span data-stu-id="ab1f0-140">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="ab1f0-141">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab1f0-141">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="ab1f0-142">管理存取與許可權</span><span class="sxs-lookup"><span data-stu-id="ab1f0-142">Manage access and permissions</span></span>](mtp-permissions.md)
