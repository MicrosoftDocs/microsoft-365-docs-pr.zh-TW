---
title: 在 Microsoft 365 安全中心開啟 Microsoft 365 Defender
description: 瞭解如何啟用 Microsoft 365 Defender，並開始整合您的安全性事件與回應。
keywords: 入門、啟用 Microsoft 365 defender、Microsoft 365 Defender、M365、security、data location、必要許可權、授權資格、設定頁面
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
ms.openlocfilehash: 3f05cc8c9b2509f8c95b802f56905e2859221cd2
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861596"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="ea105-104">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea105-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ea105-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ea105-105">**Applies to:**</span></span>
- <span data-ttu-id="ea105-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea105-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ea105-107">[Microsoft 365 defender](microsoft-365-defender.md)會整合您的事件回應程式，方法是在 microsoft defender for Endpoint、microsoft defender for Office 365、Microsoft Cloud App Security 和 Microsoft defender 身分識別上整合重要功能。</span><span class="sxs-lookup"><span data-stu-id="ea105-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="ea105-108">此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。</span><span class="sxs-lookup"><span data-stu-id="ea105-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="ea105-109">Microsoft 365當具備必要許可權的合格客戶 Microsoft 365 安全性中心時，Defender 會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="ea105-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="ea105-110">請閱讀本文以瞭解各種必要條件，以及如何布建 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="ea105-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="ea105-111">檢查授權資格和必要許可權</span><span class="sxs-lookup"><span data-stu-id="ea105-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="ea105-112">Microsoft 365 安全性產品的授權，通常是您可以在 Microsoft 365 安全性中心使用 Microsoft 365 Defender，而不需要額外授權成本。</span><span class="sxs-lookup"><span data-stu-id="ea105-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="ea105-113">我們建議您取得 Microsoft 365 E5，E5 security，A5，或 a5 安全性授權或有效的授權組合，可提供所有支援服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="ea105-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="ea105-114">如需詳細的授權資訊，請 [閱讀授權要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="ea105-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="ea105-115">檢查您的角色</span><span class="sxs-lookup"><span data-stu-id="ea105-115">Check your role</span></span>

<span data-ttu-id="ea105-116">您必須是 **全域系統管理員** 或 Azure Active Directory 中的 **安全性系統管理員**，才可開啟 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="ea105-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="ea105-117">在 Azure AD 中查看您的角色</span><span class="sxs-lookup"><span data-stu-id="ea105-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="ea105-118">支援的服務</span><span class="sxs-lookup"><span data-stu-id="ea105-118">Supported services</span></span>

<span data-ttu-id="ea105-119">Microsoft 365Defender 會匯總您已部署之各種支援服務的資料。</span><span class="sxs-lookup"><span data-stu-id="ea105-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="ea105-120">它會集中處理及儲存資料，以識別新的洞察力，並可讓集中式回應工作流程成為可能。</span><span class="sxs-lookup"><span data-stu-id="ea105-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="ea105-121">這樣做不會影響現有的部署、設定或與整合服務相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="ea105-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="ea105-122">若要取得最佳保護，並優化 Microsoft 365 Defender，我們建議您在網路上部署所有適用的受支援服務。</span><span class="sxs-lookup"><span data-stu-id="ea105-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="ea105-123">如需詳細資訊，請 [參閱部署支援的服務](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ea105-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="ea105-124">服務的板載</span><span class="sxs-lookup"><span data-stu-id="ea105-124">Onboard to the service</span></span>
<span data-ttu-id="ea105-125">上架至 Microsoft 365 Defender 很簡單。</span><span class="sxs-lookup"><span data-stu-id="ea105-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="ea105-126">從 [流覽] 功能表中，選取任何 Microsoft 365 的 Defender 專案（例如事件、搜尋、動作中心或威脅分析）以啟動上架處理常式。</span><span class="sxs-lookup"><span data-stu-id="ea105-126">From the navigation menu, select any Microsoft 365 Defender items, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="ea105-127">資料中心位置</span><span class="sxs-lookup"><span data-stu-id="ea105-127">Data center location</span></span>

<span data-ttu-id="ea105-128">Microsoft 365Defender 會儲存和處理[Microsoft Defender For Endpoint 所使用的相同位置](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)中的資料。</span><span class="sxs-lookup"><span data-stu-id="ea105-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="ea105-129">如果您沒有 Microsoft Defender for Endpoint，會根據作用中 Microsoft 365 安全性服務的位置，自動選取新的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="ea105-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="ea105-130">選取的資料中心位置會顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="ea105-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="ea105-131">在 [Microsoft 365 的安全性中心] 中，選取 [**需要協助**]，以與 Microsoft 支援部門聯繫，以在不同的資料中心位置布建 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="ea105-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="ea105-132">過去，在歐洲同盟 (歐盟) 資料中心透過 Azure Defender 開啟時，會自動布建 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="ea105-132">In the past, Microsoft Defender for Endpoint automatically provisioned in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="ea105-133">Microsoft 365在相同的歐盟資料中心內，為了以這種方式在過去為端點布建的客戶，Defender 會自動布建。</span><span class="sxs-lookup"><span data-stu-id="ea105-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner in the past.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="ea105-134">確認服務已開啟</span><span class="sxs-lookup"><span data-stu-id="ea105-134">Confirm that the service is on</span></span>

<span data-ttu-id="ea105-135">服務一旦佈建，它會新增：</span><span class="sxs-lookup"><span data-stu-id="ea105-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="ea105-136">事件管理</span><span class="sxs-lookup"><span data-stu-id="ea105-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="ea105-137">警示佇列</span><span class="sxs-lookup"><span data-stu-id="ea105-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="ea105-138">用於管理[自動化調查和回應](m365d-autoir.md)的重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="ea105-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="ea105-139">[高級搜尋](advanced-hunting-overview.md) 功能</span><span class="sxs-lookup"><span data-stu-id="ea105-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="ea105-140">威脅分析</span><span class="sxs-lookup"><span data-stu-id="ea105-140">Threat analytics</span></span>

<span data-ttu-id="ea105-141">![Microsoft 365 security center 導覽窗格的圖像，具有 Microsoft 365 Defender 功能 ](../../media/overview-incident.png)
 *Microsoft 365 安全性中心與事件管理和其他 Microsoft 365 Defender 功能*</span><span class="sxs-lookup"><span data-stu-id="ea105-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/overview-incident.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="ea105-142">取得 Microsoft Defender 的身分識別資料</span><span class="sxs-lookup"><span data-stu-id="ea105-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="ea105-143">若要啟用與 Microsoft Cloud App Security 的整合，您必須至少登入 Microsoft Cloud App Security 一次。</span><span class="sxs-lookup"><span data-stu-id="ea105-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="ea105-144">取得協助</span><span class="sxs-lookup"><span data-stu-id="ea105-144">Get assistance</span></span>

<span data-ttu-id="ea105-145">若要取得有關開啟 Microsoft 365 Defender 的最常見問題的答案，請[參閱常見問題](m365d-enable-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="ea105-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="ea105-146">Microsoft 支援人員可協助您布建或取消設定租使用者上的服務和相關資源。</span><span class="sxs-lookup"><span data-stu-id="ea105-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="ea105-147">如需協助，請選取 [Microsoft 365 的安全性中心] 中的 [**需要協助**]。</span><span class="sxs-lookup"><span data-stu-id="ea105-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="ea105-148">當您聯繫支援時，請提及 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="ea105-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ea105-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="ea105-149">Related topics</span></span>

- [<span data-ttu-id="ea105-150">常見問題集</span><span class="sxs-lookup"><span data-stu-id="ea105-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="ea105-151">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="ea105-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="ea105-152">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="ea105-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="ea105-153">Microsoft 365Defender 概述</span><span class="sxs-lookup"><span data-stu-id="ea105-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="ea105-154">Microsoft Defender for Endpoint 簡介</span><span class="sxs-lookup"><span data-stu-id="ea105-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="ea105-155">Office 365 的 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="ea105-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="ea105-156">Microsoft 雲端 App 安全性概觀</span><span class="sxs-lookup"><span data-stu-id="ea105-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="ea105-157">Microsoft Defender 身分識別概述</span><span class="sxs-lookup"><span data-stu-id="ea105-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="ea105-158">Microsoft Defender for Endpoint data storage</span><span class="sxs-lookup"><span data-stu-id="ea105-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
