---
title: 在 Microsoft 365 security center 中開啟 Microsoft 365 Defender
description: 瞭解如何啟用 Microsoft 365 Defender，並開始整合您的安全性事件與回應。
keywords: 開始使用，啟用 MTP，Microsoft 威脅防護，M365，安全性，資料位置，必要許可權，授權資格，設定頁面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 18564b2a5a47b2cf4a8bbd94a3e3a315c8f269ec
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200254"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="71715-104">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71715-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="71715-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="71715-105">**Applies to:**</span></span>
- <span data-ttu-id="71715-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71715-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="71715-107">[Microsoft 365 Defender](microsoft-365-defender.md) 整合您的事件回應程式，方法是在 microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security 和 microsoft Defender for Identity 中整合重要功能。</span><span class="sxs-lookup"><span data-stu-id="71715-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="71715-108">此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。</span><span class="sxs-lookup"><span data-stu-id="71715-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="71715-109">Microsoft 365 Defender 會在具備必要許可權的合格客戶造訪 Microsoft 365 的安全性中心時自動開啟。</span><span class="sxs-lookup"><span data-stu-id="71715-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="71715-110">請閱讀本文以瞭解各種必要條件，以及如何布建 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="71715-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="71715-111">檢查授權資格和必要許可權</span><span class="sxs-lookup"><span data-stu-id="71715-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="71715-112">Microsoft 365 安全性產品的授權一般會使您在 Microsoft 365 的安全性中心使用 Microsoft 365 Defender，而不需要額外授權成本。</span><span class="sxs-lookup"><span data-stu-id="71715-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="71715-113">我們建議您取得 Microsoft 365 E5、E5 或 A5 安全授權或有效的授權組合，以提供所有支援服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="71715-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="71715-114">如需詳細的授權資訊，請 [閱讀授權要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="71715-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="71715-115">檢查您的角色</span><span class="sxs-lookup"><span data-stu-id="71715-115">Check your role</span></span>

<span data-ttu-id="71715-116">您必須是 **全域系統管理員** 或 Azure Active Directory 中的 **安全性系統管理員** ，才可開啟 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="71715-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="71715-117">在 Azure AD 中查看您的角色</span><span class="sxs-lookup"><span data-stu-id="71715-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="71715-118">支援的服務</span><span class="sxs-lookup"><span data-stu-id="71715-118">Supported services</span></span>

<span data-ttu-id="71715-119">Microsoft 365 Defender 會匯總您已部署之各種支援服務的資料。</span><span class="sxs-lookup"><span data-stu-id="71715-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="71715-120">它會集中處理及儲存資料，以識別新的洞察力，並可讓集中式回應工作流程成為可能。</span><span class="sxs-lookup"><span data-stu-id="71715-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="71715-121">這樣做不會影響現有的部署、設定或與整合服務相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="71715-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="71715-122">若要取得最佳保護，並優化 Microsoft 365 Defender，我們建議在您的網路上部署所有適用的受支援服務。</span><span class="sxs-lookup"><span data-stu-id="71715-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="71715-123">如需詳細資訊，請 [參閱部署支援的服務](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="71715-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="71715-124">服務的板載</span><span class="sxs-lookup"><span data-stu-id="71715-124">Onboard to the service</span></span>
<span data-ttu-id="71715-125">上架至 Microsoft 365 Defender 非常簡單。</span><span class="sxs-lookup"><span data-stu-id="71715-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="71715-126">從 [流覽] 功能表中，選取 [端點] 區段下的任何專案，例如「事件」、「搜尋」、「動作中心」或「威脅分析」，以啟動上架程式。</span><span class="sxs-lookup"><span data-stu-id="71715-126">From the navigation menu, select any item under the Endpoints section, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="71715-127">資料中心位置</span><span class="sxs-lookup"><span data-stu-id="71715-127">Data center location</span></span>

<span data-ttu-id="71715-128">Microsoft 365 Defender 會將資料儲存並處理于 [Microsoft Defender For Endpoint 所使用的相同位置](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="71715-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="71715-129">如果您沒有 Microsoft Defender for Endpoint，會根據使用中 Microsoft 365 安全性服務的位置，自動選取新的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="71715-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="71715-130">選取的資料中心位置會顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="71715-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="71715-131">在 Microsoft 365 的安全性中心中，選取 [ **需要協助** ]，以與 microsoft 支援部門聯繫，以在不同的資料中心位置布建 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="71715-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="71715-132">Microsoft Defender for Endpoint 會在歐盟 (歐盟透過 Azure Defender 開啟時) 資料中心。</span><span class="sxs-lookup"><span data-stu-id="71715-132">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="71715-133">Microsoft 365 Defender 會在相同的歐盟資料中心，針對以這種方式布建 Defender 的客戶自動布建。</span><span class="sxs-lookup"><span data-stu-id="71715-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="71715-134">確認服務已開啟</span><span class="sxs-lookup"><span data-stu-id="71715-134">Confirm that the service is on</span></span>

<span data-ttu-id="71715-135">服務一旦佈建，它會新增：</span><span class="sxs-lookup"><span data-stu-id="71715-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="71715-136">事件管理</span><span class="sxs-lookup"><span data-stu-id="71715-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="71715-137">警示佇列</span><span class="sxs-lookup"><span data-stu-id="71715-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="71715-138">用於管理[自動化調查和回應](m365d-autoir.md)的重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="71715-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="71715-139">[高級搜尋](advanced-hunting-overview.md) 功能</span><span class="sxs-lookup"><span data-stu-id="71715-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="71715-140">威脅分析</span><span class="sxs-lookup"><span data-stu-id="71715-140">Threat analytics</span></span>

<span data-ttu-id="71715-141">![Microsoft 365 security center 導覽窗格與 Microsoft 365 Defender 的影像功能 ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 security center with 事件管理和其他 Microsoft 365 Defender 功能*</span><span class="sxs-lookup"><span data-stu-id="71715-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="71715-142">取得 Microsoft Defender 的身分識別資料</span><span class="sxs-lookup"><span data-stu-id="71715-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="71715-143">若要啟用與 Microsoft Cloud App 安全性的整合，您必須至少登入 Microsoft Cloud App Security （至少一次）。</span><span class="sxs-lookup"><span data-stu-id="71715-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="71715-144">取得協助</span><span class="sxs-lookup"><span data-stu-id="71715-144">Get assistance</span></span>

<span data-ttu-id="71715-145">若要取得有關開啟 Microsoft 365 Defender 的最常見問題的答案，請 [參閱常見問題](m365d-enable-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="71715-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="71715-146">Microsoft 支援人員可協助您布建或取消設定租使用者上的服務和相關資源。</span><span class="sxs-lookup"><span data-stu-id="71715-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="71715-147">如需協助，請選取 [Microsoft 365 security center] 中的 [ **需要協助？** ]。</span><span class="sxs-lookup"><span data-stu-id="71715-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="71715-148">當您聯繫支援時，請提及 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="71715-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="71715-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="71715-149">Related topics</span></span>

- [<span data-ttu-id="71715-150">常見問題集</span><span class="sxs-lookup"><span data-stu-id="71715-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="71715-151">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="71715-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="71715-152">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="71715-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="71715-153">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="71715-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="71715-154">Microsoft Defender for Endpoint 簡介</span><span class="sxs-lookup"><span data-stu-id="71715-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="71715-155">適用于 Office 的 Defender 365 簡介</span><span class="sxs-lookup"><span data-stu-id="71715-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="71715-156">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="71715-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="71715-157">Microsoft Defender 身分識別概述</span><span class="sxs-lookup"><span data-stu-id="71715-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="71715-158">Microsoft Defender for Endpoint data storage</span><span class="sxs-lookup"><span data-stu-id="71715-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
