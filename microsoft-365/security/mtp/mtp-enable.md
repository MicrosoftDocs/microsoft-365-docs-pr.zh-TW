---
title: 在 Microsoft 365 安全性中心中開啟 Microsoft 威脅防護
description: 了解如何啟用 Microsoft 威脅防護，並開始整合您的安全性事件和回應。
keywords: 開始使用，啟用 MTP，Microsoft 威脅防護，M365，安全性，資料位置，必要許可權，授權資格，設定頁面
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
ms.openlocfilehash: 9a57929e42f08db8abda170c889441d3a50ade72
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209244"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="a128c-104">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a128c-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="a128c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a128c-105">**Applies to:**</span></span>
- <span data-ttu-id="a128c-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a128c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a128c-107">Microsoft 威脅防護整合了您的事件回應流程，方法是整合跨 Microsoft Defender 進階威脅防護 (ATP)、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的重要功能。</span><span class="sxs-lookup"><span data-stu-id="a128c-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="a128c-108">此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。</span><span class="sxs-lookup"><span data-stu-id="a128c-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="a128c-109">若要取得最佳保護，並優化 Microsoft 威脅防護，我們建議您在網路上部署所有適用的受支援服務。</span><span class="sxs-lookup"><span data-stu-id="a128c-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="a128c-110">如需詳細資訊，請[參閱部署支援的服務](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="a128c-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="a128c-111">檢查授權資格和必要許可權</span><span class="sxs-lookup"><span data-stu-id="a128c-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="a128c-112">Microsoft 365 E5，E5 Security，A5，或 A5 安全性授權或有效的授權組合提供支援服務的存取權，且您可以在 Microsoft 365 安全性中心使用 Microsoft 威脅防護，而不需要額外授權成本。</span><span class="sxs-lookup"><span data-stu-id="a128c-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span>

<span data-ttu-id="a128c-113">如需詳細的授權資訊，請[閱讀授權要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="a128c-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="a128c-114">檢查您的角色</span><span class="sxs-lookup"><span data-stu-id="a128c-114">Check your role</span></span>
<span data-ttu-id="a128c-115">您必須是**全域系統管理員**或 Azure Active Directory 中的**安全性系統管理員**，才可開啟 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="a128c-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="a128c-116">在 Azure AD 中查看您的角色</span><span class="sxs-lookup"><span data-stu-id="a128c-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="a128c-117">開始使用服務</span><span class="sxs-lookup"><span data-stu-id="a128c-117">Start using the service</span></span>

>[!IMPORTANT]
><span data-ttu-id="a128c-118">從2020年5月12日開始，Microsoft 將逐步推出有關[授權需求](prerequisites.md#licensing-requirements)的新的優化體驗，並開啟 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="a128c-118">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around [licensing requirements](prerequisites.md#licensing-requirements) and turning on Microsoft Threat Protection.</span></span> <span data-ttu-id="a128c-119">在這段期間內，有些客戶會開始查看其門戶體驗的變更。</span><span class="sxs-lookup"><span data-stu-id="a128c-119">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="a128c-120">有關全新經驗的資訊已在本文中標示**新經驗**。</span><span class="sxs-lookup"><span data-stu-id="a128c-120">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="a128c-121">Microsoft 威脅防護會匯總各種整合服務中的資料。</span><span class="sxs-lookup"><span data-stu-id="a128c-121">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="a128c-122">它會集中處理及儲存資料，以識別新的洞察力，並可讓集中式回應工作流程成為可能。</span><span class="sxs-lookup"><span data-stu-id="a128c-122">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="a128c-123">這樣做不會影響現有的部署、設定或與整合服務相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="a128c-123">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="a128c-124">在您開啟服務之前，當您從功能窗格中選取 [**事件**]、[**動作中心**] 或 [**搜尋**] 時，microsoft 365 安全中心（[security.microsoft.com](https://security.microsoft.com)）會顯示 microsoft 威脅防護歡迎頁面。</span><span class="sxs-lookup"><span data-stu-id="a128c-124">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="a128c-125">如果您不具備使用 Microsoft 威脅防護的資格，就不會顯示這些流覽選項。</span><span class="sxs-lookup"><span data-stu-id="a128c-125">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="a128c-126">![顯示 microsoft ](../../media/mtp-welcome.png)
 *365 security center 中*microsoft 威脅防護歡迎頁面上的 microsoft 威脅防護功能，顯示 microsoft 威脅防護歡迎頁面的圖像</span><span class="sxs-lookup"><span data-stu-id="a128c-126">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="a128c-127">若要開啟 Microsoft 威脅防護，只需從歡迎頁面完成此程式。</span><span class="sxs-lookup"><span data-stu-id="a128c-127">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="a128c-128">您也可以在功能窗格中存取**設定**（[security.microsoft.com/settings](https://security.microsoft.com/settings)），並選取 [ **microsoft 威脅防護**]，以開啟 microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="a128c-128">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="a128c-129">如果您在功能窗格中看不到**設定**或無法存取頁面，請檢查您的許可權和授權。</span><span class="sxs-lookup"><span data-stu-id="a128c-129">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="a128c-130">選取資料中心位置</span><span class="sxs-lookup"><span data-stu-id="a128c-130">Select data center location</span></span>
<span data-ttu-id="a128c-131">如果已為您的組織佈建 Microsoft Defender ATP，則資料將會儲存在為[您的 Microsoft Defender ATP 資料](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)選取的相同資料中心位置中。</span><span class="sxs-lookup"><span data-stu-id="a128c-131">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="a128c-132">如果您沒有 Microsoft Defender ATP，系統會要求您選擇專用於 Microsoft 威脅防護的新資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="a128c-132">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 
 
<span data-ttu-id="a128c-133">您必須先提供同意，才可在服務和匯總間共用資料。</span><span class="sxs-lookup"><span data-stu-id="a128c-133">You need to provide consent before data is shared between services and aggregated.</span></span>

<span data-ttu-id="a128c-134">**新經驗：** 從2020年5月12日起，客戶會逐漸收到這種經驗的變更。</span><span class="sxs-lookup"><span data-stu-id="a128c-134">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="a128c-135">針對具有全新經驗的使用者，服務會根據您現有的 Microsoft 365 安全性服務，自動為匯總資料選取最佳的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="a128c-135">For those with the new experience, the service automatically selects the optimal data center location for your aggregated data based on your existing Microsoft 365 security services.</span></span> <span data-ttu-id="a128c-136">選取的資料中心位置會顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="a128c-136">The selected data center location is shown in the screen.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="a128c-137">確認服務已開啟</span><span class="sxs-lookup"><span data-stu-id="a128c-137">Confirm that the service is on</span></span>
<span data-ttu-id="a128c-138">服務一旦佈建，它會新增：</span><span class="sxs-lookup"><span data-stu-id="a128c-138">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="a128c-139">事件管理</span><span class="sxs-lookup"><span data-stu-id="a128c-139">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="a128c-140">用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="a128c-140">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="a128c-141">[高級搜尋](advanced-hunting-overview.md)功能</span><span class="sxs-lookup"><span data-stu-id="a128c-141">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="a128c-142">![Microsoft 365 security center 導覽窗格與 Microsoft 威脅防護的影像功能 ](../../media/mtp-on.png)
 *microsoft 365 security center with 事件管理和其他 Microsoft 威脅防護功能*</span><span class="sxs-lookup"><span data-stu-id="a128c-142">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="a128c-143">取得 Azure ATP 資料</span><span class="sxs-lookup"><span data-stu-id="a128c-143">Getting Azure ATP data</span></span>
<span data-ttu-id="a128c-144">若要使用 Microsoft 威脅防護共用 Azure ATP 資料，請確認已開啟 Microsoft Cloud App Security 和 Azure ATP 整合。</span><span class="sxs-lookup"><span data-stu-id="a128c-144">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="a128c-145">深入了解此整合</span><span class="sxs-lookup"><span data-stu-id="a128c-145">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="a128c-146">關閉 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a128c-146">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="a128c-147">若要停止使用 Microsoft 威脅防護，請移至 Microsoft 365 安全性中心的 [設定]\*\*\*\*  >  [Microsoft 威脅防護]\*\*\*\*  >  [選擇加入/選擇退出]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a128c-147">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="a128c-148">取消選取 [開啟 Microsoft 威脅防護]\*\*\*\* 並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="a128c-148">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="a128c-149">對應的功能將會從 Microsoft 365 的安全性中心移除。</span><span class="sxs-lookup"><span data-stu-id="a128c-149">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="a128c-150">取得協助</span><span class="sxs-lookup"><span data-stu-id="a128c-150">Get assistance</span></span>

<span data-ttu-id="a128c-151">Microsoft 支援人員可協助您布建或取消設定租使用者上的服務和相關資源。</span><span class="sxs-lookup"><span data-stu-id="a128c-151">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="a128c-152">如需協助，請選取 [Microsoft 365 security center] 中的 [**需要協助？** ]。</span><span class="sxs-lookup"><span data-stu-id="a128c-152">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="a128c-153">當您聯繫支援時，請提及 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="a128c-153">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a128c-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="a128c-154">Related topics</span></span>

- [<span data-ttu-id="a128c-155">Microsoft 威脅防護更新概觀</span><span class="sxs-lookup"><span data-stu-id="a128c-155">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="a128c-156">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="a128c-156">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="a128c-157">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="a128c-157">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="a128c-158">Microsoft Defender ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="a128c-158">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="a128c-159">Office 365 ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="a128c-159">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="a128c-160">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="a128c-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="a128c-161">Azure ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="a128c-161">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="a128c-162">Microsoft Defender ATP 資料儲存</span><span class="sxs-lookup"><span data-stu-id="a128c-162">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)