---
title: Microsoft 威脅防護先決條件
description: 了解 Microsoft 威脅防護的相關授權、硬體和軟體需求，以及其他組態設定
keywords: 需求、先決條件、硬體、軟體、瀏覽器
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: b136dfcb11265e9ab19328d6ad0b3c515f7fc86f
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910949"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="063cd-104">Microsoft 威脅防護先決條件</span><span class="sxs-lookup"><span data-stu-id="063cd-104">Microsoft Threat Protection</span></span>

<span data-ttu-id="063cd-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="063cd-105">**Applies to:**</span></span>
- <span data-ttu-id="063cd-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="063cd-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="063cd-107">了解授權、硬體和軟體需求，以及其他組態設定以執行和使用 Microsoft 365 安全性。</span><span class="sxs-lookup"><span data-stu-id="063cd-107">Learn about the licensing, hardware and software requirements, and other configuration settings to run and use the Microsoft 365 security.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="063cd-108">授權需求</span><span class="sxs-lookup"><span data-stu-id="063cd-108">Licensing requirements</span></span>
<span data-ttu-id="063cd-109">Microsoft 365 安全性需要以下其中一種授權：</span><span class="sxs-lookup"><span data-stu-id="063cd-109">Microsoft 365 security requires one of the following licenses:</span></span>

- <span data-ttu-id="063cd-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="063cd-110">Microsoft 365 E5</span></span> 
- <span data-ttu-id="063cd-111">Office 365 E5、Enterprise Mobility + Security E5 和 Windows E5</span><span class="sxs-lookup"><span data-stu-id="063cd-111">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

<span data-ttu-id="063cd-112">您可以從 [Microsoft 365 企業版頁面](https://www.microsoft.com/en-us/microsoft-365/enterprise)取得這些授權。</span><span class="sxs-lookup"><span data-stu-id="063cd-112">You can acquire these licenses from the [Microsoft 365 enterprise page](https://www.microsoft.com/en-us/microsoft-365/enterprise).</span></span>

### <a name="check-your-existing--licenses"></a><span data-ttu-id="063cd-113">檢查您現有的授權</span><span class="sxs-lookup"><span data-stu-id="063cd-113">Check your existing  licenses</span></span>
<span data-ttu-id="063cd-114">移至 [admin.microsoft.com](https://admin.microsoft.com/) 的 Microsoft 365 系統管理中心，以檢視您現有的授權。</span><span class="sxs-lookup"><span data-stu-id="063cd-114">Go to Microsoft 365 admin center at [admin.microsoft.com](https://admin.microsoft.com/) to view your existing licenses.</span></span> <span data-ttu-id="063cd-115">在系統管理中心中，移至 **[帳單]** >  **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="063cd-115">In the Yammer admin center, go to **Users**  >  **Remove Users**.</span></span>

<span data-ttu-id="063cd-116">您必須將 **[帳單系統管理員]** 或 **[全域讀取器]** 指派為 [[Azure AD 中的角色]](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)，才能查看授權資訊。</span><span class="sxs-lookup"><span data-stu-id="063cd-116">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see licensing information.</span></span> <span data-ttu-id="063cd-117">如果您遭遇存取的問題，請與全域管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="063cd-117">If you encounter access problems, contact a global admin.</span></span>  

## <a name="browser-requirements"></a><span data-ttu-id="063cd-118">瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="063cd-118">Browser requirements</span></span>
<span data-ttu-id="063cd-119">Microsoft 365 安全中心的存取必須透過瀏覽器才能完成。</span><span class="sxs-lookup"><span data-stu-id="063cd-119">Access to Microsoft 365 security center is done through a browser.</span></span> <span data-ttu-id="063cd-120">支援 Internet Explorer 和 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="063cd-120">Internet Explorer and Microsoft Edge is supported.</span></span> <span data-ttu-id="063cd-121">也支援任何符合 HTML5 規範的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="063cd-121">Any HTML5 compliant browsers are also supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="063cd-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="063cd-122">Related topics</span></span>
- [<span data-ttu-id="063cd-123">Microsoft 威脅防護概觀</span><span class="sxs-lookup"><span data-stu-id="063cd-123">Microsoft Advanced Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="063cd-124">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="063cd-124">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)