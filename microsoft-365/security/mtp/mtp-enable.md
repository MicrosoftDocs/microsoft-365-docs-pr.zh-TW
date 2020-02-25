---
title: 在 Microsoft 365 安全性中心中開啟 Microsoft 威脅防護
description: 了解如何啟用 Microsoft 威脅防護，並開始整合您的安全性事件和回應。
keywords: 快速入門，啟用 MTP、 Microsoft 威脅防護、 M365、 安全性、 資料位置、 必要權限、 授權資格、 設定] 頁面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 73f76dee8a59229138f906e593a84220c7f70aee
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235212"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="a2f27-104">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a2f27-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="a2f27-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a2f27-105">**Applies to:**</span></span>
- <span data-ttu-id="a2f27-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a2f27-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="a2f27-107">Microsoft 威脅防護整合了您的事件回應流程，方法是整合跨 Microsoft Defender 進階威脅防護 (ATP)、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的重要功能。</span><span class="sxs-lookup"><span data-stu-id="a2f27-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="a2f27-108">此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。</span><span class="sxs-lookup"><span data-stu-id="a2f27-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="a2f27-109">請檢查授權資格及必要的權限</span><span class="sxs-lookup"><span data-stu-id="a2f27-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="a2f27-110">使用 Microsoft 365 E5、 Microsoft 365 E5 安全性或對等組合的授權的客戶可以使用 Microsoft Threat Protection。</span><span class="sxs-lookup"><span data-stu-id="a2f27-110">Customers with Microsoft 365 E5, Microsoft 365 E5 Security, or an equivalent combination of licenses can use Microsoft Threat Protection.</span></span> <span data-ttu-id="a2f27-111">如需詳細資訊，請[閱讀授權需求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="a2f27-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

<span data-ttu-id="a2f27-112">您必須是**全域系統管理員**或[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)以開啟 [Microsoft 威脅防護中的**安全性系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="a2f27-112">You must be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to turn on Microsoft Threat Protection.</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="a2f27-113">開始使用服務</span><span class="sxs-lookup"><span data-stu-id="a2f27-113">Start using the service</span></span>
<span data-ttu-id="a2f27-114">Microsoft 威脅防護彙總資料從各種的整合式服務。</span><span class="sxs-lookup"><span data-stu-id="a2f27-114">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="a2f27-115">它會處理程序，並儲存資料集中以識別新的深入資訊，並讓集中式的回應系統工作流程。</span><span class="sxs-lookup"><span data-stu-id="a2f27-115">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="a2f27-116">開啟服務之前，請在 Microsoft 365 安全性中心 ([security.microsoft.com](https://security.microsoft.com)) 不會顯示**事件**和**重要訊息中心**選項功能窗格中。</span><span class="sxs-lookup"><span data-stu-id="a2f27-116">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) doesn't show the **Incidents** and the **Action center** options in the navigation pane.</span></span>

<span data-ttu-id="a2f27-117">![Microsoft 365 安全性中心沒有 Microsoft 威脅防護功能的導覽窗格影像](../../media/mtp-off.png)
*Microsoft 365 安全中心與 Microsoft Threat Protection 關閉*</span><span class="sxs-lookup"><span data-stu-id="a2f27-117">![Image of Microsoft 365 security center navigation pane without Microsoft Threat Protection features](../../media/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="a2f27-118">若要開啟 Microsoft 威脅防護，請選取 [在功能窗格中的**設定**。</span><span class="sxs-lookup"><span data-stu-id="a2f27-118">To turn on Microsoft Threat Protection, select **Settings** in the navigation pane.</span></span> <span data-ttu-id="a2f27-119">在**[設定] 頁面](https://security.microsoft.com/settings)** 上，移至**Microsoft 威脅防護** > **加入 / 退出**。</span><span class="sxs-lookup"><span data-stu-id="a2f27-119">In the **[Settings page](https://security.microsoft.com/settings)**, go to **Microsoft Threat Protection** > **Opt-in / Opt-out**.</span></span>

>[!NOTE]
><span data-ttu-id="a2f27-120">如果您沒有看到**設定**功能窗格中，或無法存取] 頁面上，檢查您的權限和授權。</span><span class="sxs-lookup"><span data-stu-id="a2f27-120">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="a2f27-121">選取的資料中心位置</span><span class="sxs-lookup"><span data-stu-id="a2f27-121">Select data center location</span></span>
<span data-ttu-id="a2f27-122">如果已為您的組織佈建 Microsoft Defender ATP，則資料將會儲存在為[您的 Microsoft Defender ATP 資料](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)選取的相同資料中心位置中。</span><span class="sxs-lookup"><span data-stu-id="a2f27-122">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="a2f27-123">如果您沒有 Microsoft Defender ATP，系統會要求您選擇專用於 Microsoft 威脅防護的新資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="a2f27-123">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="a2f27-124">您必須提供同意才能服務之間共用和彙總資料。</span><span class="sxs-lookup"><span data-stu-id="a2f27-124">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="a2f27-125">確認服務已開啟</span><span class="sxs-lookup"><span data-stu-id="a2f27-125">Confirm that the service is on</span></span>
<span data-ttu-id="a2f27-126">服務一旦佈建，它會新增：</span><span class="sxs-lookup"><span data-stu-id="a2f27-126">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="a2f27-127">事件管理</span><span class="sxs-lookup"><span data-stu-id="a2f27-127">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="a2f27-128">用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="a2f27-128">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="a2f27-129">現有 [搜捕]\*\*\*\* 頁面的[進階搜捕](advanced-hunting-overview.md)功能</span><span class="sxs-lookup"><span data-stu-id="a2f27-129">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="a2f27-130">![Microsoft 365 安全性中心與 Microsoft Threat Protection 功能的導覽窗格影像](../../media/mtp-on.png)
*Microsoft 365 安全性中心事件管理和其他 Microsoft 威脅防護功能*</span><span class="sxs-lookup"><span data-stu-id="a2f27-130">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="a2f27-131">取得 Azure ATP 資料</span><span class="sxs-lookup"><span data-stu-id="a2f27-131">Getting Azure ATP data</span></span>
<span data-ttu-id="a2f27-132">若要使用 Microsoft 威脅防護共用 Azure ATP 資料，請確認已開啟 Microsoft Cloud App Security 和 Azure ATP 整合。</span><span class="sxs-lookup"><span data-stu-id="a2f27-132">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="a2f27-133">深入了解此整合</span><span class="sxs-lookup"><span data-stu-id="a2f27-133">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="a2f27-134">關閉 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a2f27-134">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="a2f27-135">若要停止使用 Microsoft 威脅防護，請移至 Microsoft 365 安全性中心的 [設定]\*\*\*\*  >  [Microsoft 威脅防護]\*\*\*\*  >  [選擇加入/選擇退出]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2f27-135">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="a2f27-136">取消選取 [開啟 Microsoft 威脅防護]\*\*\*\* 並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="a2f27-136">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="a2f27-137">資料將會永久刪除和對應的功能將會移除在 Microsoft 365 安全性中心。</span><span class="sxs-lookup"><span data-stu-id="a2f27-137">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="a2f27-138">取得協助</span><span class="sxs-lookup"><span data-stu-id="a2f27-138">Get assistance</span></span>

<span data-ttu-id="a2f27-139">Microsoft 支援人員可以幫助佈建或 deprovision 之服務與相關的資源上您的租用戶。</span><span class="sxs-lookup"><span data-stu-id="a2f27-139">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="a2f27-140">如需協助，請選取 [**需要協助嗎？** Microsoft 365 安全性中心。</span><span class="sxs-lookup"><span data-stu-id="a2f27-140">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="a2f27-141">連絡支援時, 提及 Microsoft Threat Protection。</span><span class="sxs-lookup"><span data-stu-id="a2f27-141">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2f27-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="a2f27-142">Related topics</span></span>

- [<span data-ttu-id="a2f27-143">Microsoft 威脅防護更新概觀</span><span class="sxs-lookup"><span data-stu-id="a2f27-143">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="a2f27-144">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="a2f27-144">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="a2f27-145">Microsoft Defender ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="a2f27-145">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="a2f27-146">Office 365 ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="a2f27-146">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="a2f27-147">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="a2f27-147">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="a2f27-148">Azure ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="a2f27-148">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="a2f27-149">Microsoft Defender ATP 資料儲存</span><span class="sxs-lookup"><span data-stu-id="a2f27-149">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
