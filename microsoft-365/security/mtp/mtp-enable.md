---
title: 在 Microsoft 365 安全性中心中開啟 Microsoft 威脅防護
description: 了解如何啟用 Microsoft 威脅防護，並開始整合您的安全性事件和回應。
keywords: 開始, MTP, Microsoft 威脅防護, M365, 安全性, 資料位置
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 7790e079d4b39b5d41961a26bb17009adb1bec1d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808448"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="dc2f8-104">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="dc2f8-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="dc2f8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="dc2f8-105">**Applies to:**</span></span>
- <span data-ttu-id="dc2f8-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="dc2f8-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="dc2f8-107">Microsoft 威脅防護整合了您的事件回應流程，方法是整合跨 Microsoft Defender 進階威脅防護 (ATP)、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的重要功能。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="dc2f8-108">此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-your-eligibility"></a><span data-ttu-id="dc2f8-109">檢查您的資格</span><span class="sxs-lookup"><span data-stu-id="dc2f8-109">Check your eligibility</span></span>
<span data-ttu-id="dc2f8-110">擁有 Microsoft 365 E5 或同等授權的客戶可以使用 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-110">Customers with a Microsoft 365 E5 or equivalent license can use Microsoft Threat Protection.</span></span> <span data-ttu-id="dc2f8-111">如需詳細資訊，請[閱讀授權需求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="dc2f8-112">開始使用服務</span><span class="sxs-lookup"><span data-stu-id="dc2f8-112">Start using the service</span></span>
<span data-ttu-id="dc2f8-113">開啟 Microsoft 威脅防護服務會彙總來自各種整合服務的資料。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-113">Turning on the Microsoft Threat Protection service aggregates data from the various integrated services.</span></span> <span data-ttu-id="dc2f8-114">系統將處理資料並集中儲存，以找出新的深入資訊，並使得集中式回應工作流程變得可能。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-114">The data will be processed and stored centrally to identify new insights and to make centralized response workflows possible.</span></span>

<span data-ttu-id="dc2f8-115">在您開啟服務前，Microsoft 365 安全性中心 ([security.microsoft.com](https://security.microsoft.com)) 不會在功能表上顯示 [事件]\*\*\*\* 和 [重要訊息中心]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-115">Before you turn the service on, Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) does not show the **Incidents** and the **Action center** options on the menu.</span></span>

<span data-ttu-id="dc2f8-116">![不含 Microsoft 威脅防護功能的 Microsoft 365 安全性中心功能表的影像](../images/mtp-off.png)
*已關閉 Microsoft 威脅防護的 Microsoft 365 安全性中心*</span><span class="sxs-lookup"><span data-stu-id="dc2f8-116">![Image of Microsoft 365 security center menu without Microsoft Threat Protection features](../images/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="dc2f8-117">若要開啟 Microsoft 威脅防護服務，請移至 Microsoft 365 安全性中心的 [設定]\*\*\*\*  >  [Microsoft 威脅防護]\*\*\*\*  >  [選擇加入/選擇退出]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-117">To turn the Microsoft Threat Protection service on, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="dc2f8-118">若要執行此工作，您必須是 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 中的全域系統管理員或安全性系統管理員。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-118">You will need to be a global administrator or a security administrator in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to perform this task.</span></span>

<span data-ttu-id="dc2f8-119">如果已為您的組織佈建 Microsoft Defender ATP，則資料將會儲存在為[您的 Microsoft Defender ATP 資料](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)選取的相同資料中心位置中。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-119">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="dc2f8-120">如果您沒有 Microsoft Defender ATP，系統會要求您選擇專用於 Microsoft 威脅防護的新資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-120">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> <span data-ttu-id="dc2f8-121">在服務之間共用資料與彙總之前，您必須先提供同意。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-121">You will need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="dc2f8-122">確認服務已開啟</span><span class="sxs-lookup"><span data-stu-id="dc2f8-122">Confirm that the service is on</span></span>
<span data-ttu-id="dc2f8-123">服務一旦佈建，它會新增：</span><span class="sxs-lookup"><span data-stu-id="dc2f8-123">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="dc2f8-124">事件管理</span><span class="sxs-lookup"><span data-stu-id="dc2f8-124">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="dc2f8-125">用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="dc2f8-125">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="dc2f8-126">現有 [搜捕]\*\*\*\* 頁面的[進階搜捕](advanced-hunting-overview.md)功能</span><span class="sxs-lookup"><span data-stu-id="dc2f8-126">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="dc2f8-127">![含有 Microsoft 威脅防護功能的 Microsoft 365 安全性中心功能表的影像](../images/mtp-on.png)
*具有事件管理和其他 Microsoft 威脅防護功能的 Microsoft 365 安全性中心*</span><span class="sxs-lookup"><span data-stu-id="dc2f8-127">![Image of Microsoft 365 security center menu with Microsoft Threat Protection features](../images/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection features*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="dc2f8-128">取得 Azure ATP 資料</span><span class="sxs-lookup"><span data-stu-id="dc2f8-128">Getting Azure ATP data</span></span>
<span data-ttu-id="dc2f8-129">若要使用 Microsoft 威脅防護共用 Azure ATP 資料，請確認已開啟 Microsoft Cloud App Security 和 Azure ATP 整合。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-129">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="dc2f8-130">深入了解此整合</span><span class="sxs-lookup"><span data-stu-id="dc2f8-130">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="dc2f8-131">關閉 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="dc2f8-131">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="dc2f8-132">若要停止使用 Microsoft 威脅防護，請移至 Microsoft 365 安全性中心的 [設定]\*\*\*\*  >  [Microsoft 威脅防護]\*\*\*\*  >  [選擇加入/選擇退出]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-132">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="dc2f8-133">取消選取 [開啟 Microsoft 威脅防護]\*\*\*\* 並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-133">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="dc2f8-134">系統將會永久刪除資料，且將對應的功能從 Microsoft 365 安全性中心中移除。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-134">Data will be permanently deleted and corresponding features will be removed from Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="dc2f8-135">取得協助</span><span class="sxs-lookup"><span data-stu-id="dc2f8-135">Get assistance</span></span>

<span data-ttu-id="dc2f8-136">Microsoft 人員可協助您佈建或取消佈建您租用戶上的服務與相關資源。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-136">Microsoft staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="dc2f8-137">如需協助，請[連絡頂級支援](https://go.microsoft.com/fwlink/?LinkID=733758)。</span><span class="sxs-lookup"><span data-stu-id="dc2f8-137">For assistance, [contact premier support](https://go.microsoft.com/fwlink/?LinkID=733758).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc2f8-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="dc2f8-138">Related topics</span></span>

- [<span data-ttu-id="dc2f8-139">Microsoft 威脅防護更新概觀</span><span class="sxs-lookup"><span data-stu-id="dc2f8-139">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="dc2f8-140">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="dc2f8-140">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="dc2f8-141">Microsoft Defender ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="dc2f8-141">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="dc2f8-142">Office 365 ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="dc2f8-142">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="dc2f8-143">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="dc2f8-143">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="dc2f8-144">Azure ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="dc2f8-144">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="dc2f8-145">Microsoft Defender ATP 資料儲存</span><span class="sxs-lookup"><span data-stu-id="dc2f8-145">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
