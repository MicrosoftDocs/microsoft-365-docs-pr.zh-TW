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
ms.openlocfilehash: c482e46cf51cbf11960c02663221df0c136b067c
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857176"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="bfc26-104">Microsoft 威脅防護先決條件</span><span class="sxs-lookup"><span data-stu-id="bfc26-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="bfc26-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="bfc26-105">**Applies to:**</span></span>
- <span data-ttu-id="bfc26-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bfc26-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="bfc26-107">瞭解授權、硬體和軟體需求，以及其他設定，以提供和使用 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="bfc26-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="bfc26-108">授權需求</span><span class="sxs-lookup"><span data-stu-id="bfc26-108">Licensing requirements</span></span>
<span data-ttu-id="bfc26-109">若要使用 Microsoft 威脅防護，您必須是單一授權或授權組合。</span><span class="sxs-lookup"><span data-stu-id="bfc26-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span>

### <a name="single-license"></a><span data-ttu-id="bfc26-110">單一授權</span><span class="sxs-lookup"><span data-stu-id="bfc26-110">Single license</span></span>
<span data-ttu-id="bfc26-111">您可以使用下列*其中一個*授權：</span><span class="sxs-lookup"><span data-stu-id="bfc26-111">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="bfc26-112">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="bfc26-112">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="bfc26-113">Microsoft 365 E5 Security 或 A5 Security</span><span class="sxs-lookup"><span data-stu-id="bfc26-113">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="bfc26-114">授權組合</span><span class="sxs-lookup"><span data-stu-id="bfc26-114">Combination of licenses</span></span>
<span data-ttu-id="bfc26-115">您也可以在 Office 365、 *Enterprise 可移動性 + Security （EMS）* 和 Windows 中使用代表 E5 或 A5 訂閱的授權組合。</span><span class="sxs-lookup"><span data-stu-id="bfc26-115">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="bfc26-116">授權組合必須包含下列*所有*授權：</span><span class="sxs-lookup"><span data-stu-id="bfc26-116">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="bfc26-117">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="bfc26-117">Office 365 E5 or A5</span></span>
- <span data-ttu-id="bfc26-118">*企業行動 + 安全性（EMS）* E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="bfc26-118">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="bfc26-119">Windows E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="bfc26-119">Windows E5 or A5</span></span>

<span data-ttu-id="bfc26-120">如需詳細資訊，請[查看 Microsoft 365 企業版服務方案](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="bfc26-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="bfc26-121">還沒有授權？</span><span class="sxs-lookup"><span data-stu-id="bfc26-121">Don't have license yet?</span></span> [<span data-ttu-id="bfc26-122">試用或購買 Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="bfc26-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="bfc26-123">檢查您現有的授權</span><span class="sxs-lookup"><span data-stu-id="bfc26-123">Check your existing  licenses</span></span>
<span data-ttu-id="bfc26-124">移至 Microsoft 365 系統管理中心（[admin.microsoft.com](https://admin.microsoft.com/)）以查看您現有的授權。</span><span class="sxs-lookup"><span data-stu-id="bfc26-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="bfc26-125">在系統管理中心中，移至 **[帳單]** >  **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="bfc26-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="bfc26-126">您必須被指派至[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)的**帳務系統管理員**或**全域讀取**者角色，才能看到授權資訊。</span><span class="sxs-lookup"><span data-stu-id="bfc26-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="bfc26-127">如果您遭遇存取的問題，請與全域管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="bfc26-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="bfc26-128">瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="bfc26-128">Browser requirements</span></span>
<span data-ttu-id="bfc26-129">使用 Microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 標準的網頁瀏覽器，存取 microsoft 365 security center 中的 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="bfc26-129">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="bfc26-130">適用于美國政府社區 Cloud 和 US 政府社區的 Microsoft 威脅防護。雲端高（GCC High）客戶</span><span class="sxs-lookup"><span data-stu-id="bfc26-130">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="bfc26-131">目前，我們的 GCC 和 GCC 的高客戶無法使用 Microsoft 威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="bfc26-131">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="bfc26-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="bfc26-132">Related topics</span></span>
- [<span data-ttu-id="bfc26-133">Microsoft 威脅防護概觀</span><span class="sxs-lookup"><span data-stu-id="bfc26-133">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="bfc26-134">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bfc26-134">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
