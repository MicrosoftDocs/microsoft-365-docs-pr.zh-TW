---
title: Microsoft 威脅防護先決條件
description: 了解 Microsoft 威脅防護的相關授權、硬體和軟體需求，以及其他組態設定
keywords: 需求、 必要條件、 硬體、 軟體、 瀏覽器中，具有 mtp 之、 M365，授權
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
ms.openlocfilehash: d3f24e8615f5b11b0853d7f1e36b49eb0cf2424f
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661919"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="bc984-104">Microsoft 威脅防護先決條件</span><span class="sxs-lookup"><span data-stu-id="bc984-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="bc984-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="bc984-105">**Applies to:**</span></span>
- <span data-ttu-id="bc984-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bc984-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="bc984-107">了解授權、 硬體及軟體需求及其他組態設定，以佈建並使用 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="bc984-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="bc984-108">授權需求</span><span class="sxs-lookup"><span data-stu-id="bc984-108">Licensing requirements</span></span>
<span data-ttu-id="bc984-109">若要使用 Microsoft 威脅防護，您需要下列其中一個下列授權的組合：</span><span class="sxs-lookup"><span data-stu-id="bc984-109">To use Microsoft Threat Protection, you need one of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="bc984-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bc984-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="bc984-111">Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="bc984-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="bc984-112">Office 365 E5、Enterprise Mobility + Security E5 和 Windows E5</span><span class="sxs-lookup"><span data-stu-id="bc984-112">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

[<span data-ttu-id="bc984-113">檢視 Microsoft 365 企業版服務計劃</span><span class="sxs-lookup"><span data-stu-id="bc984-113">View Microsoft 365 Enterprise service plans</span></span>](https://www.microsoft.com/en-us/licensing/product-licensing/microsoft-365-enterprise)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="bc984-114">檢查您現有的授權</span><span class="sxs-lookup"><span data-stu-id="bc984-114">Check your existing  licenses</span></span>
<span data-ttu-id="bc984-115">移至 Microsoft 365 系統管理中心 ([admin.microsoft.com](https://admin.microsoft.com/)) 來檢視現有的授權。</span><span class="sxs-lookup"><span data-stu-id="bc984-115">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="bc984-116">在系統管理中心中，移至 **[帳單]** >  **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="bc984-116">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="bc984-117">您必須獲指派**計費系統管理員**或**全域助讀程式**[在 Azure AD 中的角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)能夠查看授權資訊。</span><span class="sxs-lookup"><span data-stu-id="bc984-117">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="bc984-118">如果您遭遇存取的問題，請與全域管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="bc984-118">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="bc984-119">瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="bc984-119">Browser requirements</span></span>
<span data-ttu-id="bc984-120">使用 Microsoft Edge、 Internet Explorer 11 或任何 HTML 5 相容的網頁瀏覽器在 Microsoft 365 安全中心存取 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="bc984-120">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bc984-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="bc984-121">Related topics</span></span>
- [<span data-ttu-id="bc984-122">Microsoft 威脅防護概觀</span><span class="sxs-lookup"><span data-stu-id="bc984-122">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="bc984-123">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bc984-123">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)