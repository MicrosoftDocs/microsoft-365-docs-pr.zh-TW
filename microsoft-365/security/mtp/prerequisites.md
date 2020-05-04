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
ms.openlocfilehash: dfc2136f04ed128fc655386c6eef7b91c5e5ef3a
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011267"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="3af10-104">Microsoft 威脅防護先決條件</span><span class="sxs-lookup"><span data-stu-id="3af10-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="3af10-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="3af10-105">**Applies to:**</span></span>
- <span data-ttu-id="3af10-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="3af10-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3af10-107">瞭解授權、硬體和軟體需求，以及其他設定，以提供和使用 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="3af10-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="3af10-108">授權需求</span><span class="sxs-lookup"><span data-stu-id="3af10-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="3af10-109">從2020年5月3日開始，Microsoft 將逐步推出有關授權需求的新的優化體驗，並[開啟 Microsoft 威脅防護](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="3af10-109">Starting May 3, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="3af10-110">在這段期間內，有些客戶會開始查看其門戶體驗的變更。</span><span class="sxs-lookup"><span data-stu-id="3af10-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="3af10-111">有關全新經驗的資訊已在本文中標示**新經驗**。</span><span class="sxs-lookup"><span data-stu-id="3af10-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="3af10-112">若要使用 Microsoft 威脅防護，您必須是單一授權或授權組合。</span><span class="sxs-lookup"><span data-stu-id="3af10-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="3af10-113">這些授權或授權組合可讓您存取 Microsoft 威脅防護功能，而不需要額外成本。</span><span class="sxs-lookup"><span data-stu-id="3af10-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="3af10-114">單一授權</span><span class="sxs-lookup"><span data-stu-id="3af10-114">Single license</span></span>
<span data-ttu-id="3af10-115">您可以使用下列*其中一個*授權：</span><span class="sxs-lookup"><span data-stu-id="3af10-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="3af10-116">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="3af10-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="3af10-117">Microsoft 365 E5 Security 或 A5 Security</span><span class="sxs-lookup"><span data-stu-id="3af10-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="3af10-118">授權組合</span><span class="sxs-lookup"><span data-stu-id="3af10-118">Combination of licenses</span></span>
<span data-ttu-id="3af10-119">您也可以在 Office 365、 *Enterprise 可移動性 + Security （EMS）* 和 Windows 中使用代表 E5 或 A5 訂閱的授權組合。</span><span class="sxs-lookup"><span data-stu-id="3af10-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="3af10-120">授權組合必須包含下列*所有*授權：</span><span class="sxs-lookup"><span data-stu-id="3af10-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="3af10-121">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="3af10-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="3af10-122">*企業行動 + 安全性（EMS）* E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="3af10-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="3af10-123">Windows 10 企業版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="3af10-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="3af10-124">如需詳細資訊，請[查看 Microsoft 365 企業版服務方案](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="3af10-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="3af10-125">還沒有授權？</span><span class="sxs-lookup"><span data-stu-id="3af10-125">Don't have license yet?</span></span> [<span data-ttu-id="3af10-126">試用或購買 Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="3af10-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="3af10-127">**新經驗：** 從2020年5月3日起，客戶會逐漸收到這種經驗的變更。</span><span class="sxs-lookup"><span data-stu-id="3af10-127">**New experience:** Starting May 3, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="3af10-128">針對具有全新經驗的使用者，使用下列任何一種授權的*客戶都可*使用開啟 Microsoft 威脅防護的選項：</span><span class="sxs-lookup"><span data-stu-id="3af10-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="3af10-129">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="3af10-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="3af10-130">Microsoft 365 E5 Security 或 A5 Security</span><span class="sxs-lookup"><span data-stu-id="3af10-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="3af10-131">Windows 10 企業版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="3af10-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="3af10-132">Enterprise 可移動性 + Security （EMS） E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="3af10-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="3af10-133">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="3af10-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="3af10-134">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="3af10-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="3af10-135">Azure 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="3af10-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="3af10-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3af10-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="3af10-137">Office 365 高級威脅防護（方案2）</span><span class="sxs-lookup"><span data-stu-id="3af10-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="3af10-138">檢查您現有的授權</span><span class="sxs-lookup"><span data-stu-id="3af10-138">Check your existing  licenses</span></span>
<span data-ttu-id="3af10-139">移至 Microsoft 365 系統管理中心（[admin.microsoft.com](https://admin.microsoft.com/)）以查看您現有的授權。</span><span class="sxs-lookup"><span data-stu-id="3af10-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="3af10-140">在系統管理中心中，移至 **[帳單]** >  **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="3af10-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="3af10-141">您必須被指派至[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)的**帳務系統管理員**或**全域讀取**者角色，才能看到授權資訊。</span><span class="sxs-lookup"><span data-stu-id="3af10-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="3af10-142">如果您遭遇存取的問題，請與全域管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="3af10-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="3af10-143">瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="3af10-143">Browser requirements</span></span>
<span data-ttu-id="3af10-144">使用 Microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 標準的網頁瀏覽器，存取 microsoft 365 security center 中的 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="3af10-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="3af10-145">適用于美國政府社區 Cloud 和 US 政府社區的 Microsoft 威脅防護。雲端高（GCC High）客戶</span><span class="sxs-lookup"><span data-stu-id="3af10-145">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="3af10-146">目前，我們的 GCC 和 GCC 的高客戶無法使用 Microsoft 威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="3af10-146">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="3af10-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="3af10-147">Related topics</span></span>
- [<span data-ttu-id="3af10-148">Microsoft 威脅防護概觀</span><span class="sxs-lookup"><span data-stu-id="3af10-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="3af10-149">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="3af10-149">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
