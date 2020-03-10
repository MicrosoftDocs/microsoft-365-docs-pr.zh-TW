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
ms.openlocfilehash: 3e18759387525ec600c24f74c96d6cddf206fc82
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569039"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="49ada-104">Microsoft 威脅防護先決條件</span><span class="sxs-lookup"><span data-stu-id="49ada-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="49ada-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="49ada-105">**Applies to:**</span></span>
- <span data-ttu-id="49ada-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="49ada-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="49ada-107">瞭解授權、硬體和軟體需求，以及其他設定，以提供和使用 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="49ada-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="49ada-108">授權需求</span><span class="sxs-lookup"><span data-stu-id="49ada-108">Licensing requirements</span></span>
<span data-ttu-id="49ada-109">若要使用 Microsoft 威脅防護，您需要下列*其中一個*授權或授權組合：</span><span class="sxs-lookup"><span data-stu-id="49ada-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="49ada-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="49ada-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="49ada-111">Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="49ada-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="49ada-112">Office 365 E5 和「Enterprise 可移動性 + Security E5 （EMS E5）」和 Windows E5</span><span class="sxs-lookup"><span data-stu-id="49ada-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="49ada-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="49ada-113">Microsoft 365 A5</span></span>

<span data-ttu-id="49ada-114">如需詳細資訊，請[查看 Microsoft 365 企業版服務方案](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="49ada-114">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="49ada-115">還沒有授權？</span><span class="sxs-lookup"><span data-stu-id="49ada-115">Don't have license yet?</span></span> [<span data-ttu-id="49ada-116">試用或購買 Microsoft 365 訂閱</span><span class="sxs-lookup"><span data-stu-id="49ada-116">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="49ada-117">檢查您現有的授權</span><span class="sxs-lookup"><span data-stu-id="49ada-117">Check your existing  licenses</span></span>
<span data-ttu-id="49ada-118">移至 Microsoft 365 系統管理中心（[admin.microsoft.com](https://admin.microsoft.com/)）以查看您現有的授權。</span><span class="sxs-lookup"><span data-stu-id="49ada-118">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="49ada-119">在系統管理中心中，移至 **[帳單]** >  **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="49ada-119">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="49ada-120">您必須被指派至[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)的**帳務系統管理員**或**全域讀取**者角色，才能看到授權資訊。</span><span class="sxs-lookup"><span data-stu-id="49ada-120">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="49ada-121">如果您遭遇存取的問題，請與全域管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="49ada-121">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="49ada-122">瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="49ada-122">Browser requirements</span></span>
<span data-ttu-id="49ada-123">使用 Microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 標準的網頁瀏覽器，存取 microsoft 365 security center 中的 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="49ada-123">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="49ada-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="49ada-124">Related topics</span></span>
- [<span data-ttu-id="49ada-125">Microsoft 威脅防護概觀</span><span class="sxs-lookup"><span data-stu-id="49ada-125">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="49ada-126">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="49ada-126">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
