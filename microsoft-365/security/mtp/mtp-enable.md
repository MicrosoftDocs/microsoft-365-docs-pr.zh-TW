---
title: 在 Microsoft 365 資訊安全中心開啟 Microsoft 365 Defender
description: 瞭解如何啟用 Microsoft 365 Defender 並開始整合您的安全性事件和回應。
keywords: 開始使用，啟用 MTP，Microsoft Threat Protection， M365， 安全性， 資料位置， 必要的許可權， 授權資格， 設定頁面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930219"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="0c226-104">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c226-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0c226-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0c226-105">**Applies to:**</span></span>
- <span data-ttu-id="0c226-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c226-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0c226-107">[Microsoft 365 Defender](microsoft-threat-protection.md) 整合了端點的 Microsoft Defender、Office 365 的 Microsoft Defender、Microsoft Cloud App 安全性及 Microsoft Defender 的身分識別等重要功能，以完成您的事件回應程式。</span><span class="sxs-lookup"><span data-stu-id="0c226-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="0c226-108">此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。</span><span class="sxs-lookup"><span data-stu-id="0c226-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="0c226-109">當具有所需許可權的合格客戶流覽 Microsoft 365 資訊安全中心時，Microsoft 365 Defender 會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="0c226-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="0c226-110">請閱讀本文以瞭解各種先決條件，以及 Microsoft 365 Defender 的提供方式。</span><span class="sxs-lookup"><span data-stu-id="0c226-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="0c226-111">檢查授權資格和必要的許可權</span><span class="sxs-lookup"><span data-stu-id="0c226-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="0c226-112">Microsoft 365 安全性產品授權通常可讓您在 Microsoft 365 安全性中心使用 Microsoft 365 Defender，而無需支付額外的授權成本。</span><span class="sxs-lookup"><span data-stu-id="0c226-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="0c226-113">建議您取得 Microsoft 365 E5、E5 安全性、A5 或 A5 安全性授權，或是提供所有支援服務存取權的有效授權組合。</span><span class="sxs-lookup"><span data-stu-id="0c226-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="0c226-114">有關授權的詳細資訊， [請閱讀授權需求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="0c226-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="0c226-115">檢查您的角色</span><span class="sxs-lookup"><span data-stu-id="0c226-115">Check your role</span></span>

<span data-ttu-id="0c226-116">您必須是 **Azure** Active Directory 中的全域系統管理員或安全性系統管理員，才能開啟 Microsoft 365 Defender。 </span><span class="sxs-lookup"><span data-stu-id="0c226-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="0c226-117">在 Azure AD 中查看您的角色</span><span class="sxs-lookup"><span data-stu-id="0c226-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="0c226-118">支援服務</span><span class="sxs-lookup"><span data-stu-id="0c226-118">Supported services</span></span>

<span data-ttu-id="0c226-119">Microsoft 365 Defender 會匯總您部署的各種支援服務的資料。</span><span class="sxs-lookup"><span data-stu-id="0c226-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="0c226-120">它會集中處理和儲存資料，以識別新的深入見解，並盡可能讓集中式回應工作流程。</span><span class="sxs-lookup"><span data-stu-id="0c226-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="0c226-121">此功能不會影響現有的部署、設定，或與整合式服務相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="0c226-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="0c226-122">若要獲得最佳保護並優化 Microsoft 365 Defender，建議您在您的網路上部署所有適用的支援服務。</span><span class="sxs-lookup"><span data-stu-id="0c226-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="0c226-123">詳細資訊請參閱 [如何部署支援服務](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="0c226-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="0c226-124">在啟動服務之前</span><span class="sxs-lookup"><span data-stu-id="0c226-124">Before starting the service</span></span>

<span data-ttu-id="0c226-125">在您開啟服務之前，當您從功能窗格中選取了事件、控制中心或搜尋時，Microsoft 365 資訊安全中心 ([security.microsoft.com](https://security.microsoft.com)) 會顯示 Microsoft 365 \*\*\*\* Defender 設定頁面。 </span><span class="sxs-lookup"><span data-stu-id="0c226-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="0c226-126">如果您不符合使用 Microsoft 365 Defender 資格，將不會顯示這些流覽專案。</span><span class="sxs-lookup"><span data-stu-id="0c226-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="0c226-127">![如果 Microsoft 365 資訊安全中心中未開啟 Microsoft 365 Defender 設定，則顯示的 ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender* 設定頁面圖像</span><span class="sxs-lookup"><span data-stu-id="0c226-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="0c226-128">啟動服務</span><span class="sxs-lookup"><span data-stu-id="0c226-128">Starting the service</span></span>

<span data-ttu-id="0c226-129">若要開啟 Microsoft 365 Defender，只要選取開啟 **Microsoft 365 Defender** 並申請變更。</span><span class="sxs-lookup"><span data-stu-id="0c226-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="0c226-130">您也可以選取流覽窗格中的 (security.microsoft.com/settings) 選項，[](https://security.microsoft.com/settings)然後選取 **Microsoft 365 Defender 來存取此選項**。 </span><span class="sxs-lookup"><span data-stu-id="0c226-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="0c226-131">如果您在流覽 **窗格中看不到設定** 或無法存取頁面，請檢查您的許可權和授權。</span><span class="sxs-lookup"><span data-stu-id="0c226-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="0c226-132">資料中心位置</span><span class="sxs-lookup"><span data-stu-id="0c226-132">Data center location</span></span>

<span data-ttu-id="0c226-133">Microsoft 365 Defender 會儲存及處理與 Microsoft Defender for Endpoint 相同 [位置的資料](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="0c226-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="0c226-134">如果您沒有 Microsoft Defender for Endpoint，就會根據使用中的 Microsoft 365 安全性服務位置自動選取新的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="0c226-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="0c226-135">畫面上會顯示選取的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="0c226-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="0c226-136">選取需要協助嗎？在 Microsoft 365 資訊安全中心中，與 Microsoft 支援服務聯繫，以在不同的資料中心位置提供 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="0c226-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="0c226-137">透過 Azure Defender 開啟時，Microsoft Defender for Endpoint (歐盟) 資料中心自動提供。</span><span class="sxs-lookup"><span data-stu-id="0c226-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="0c226-138">Microsoft 365 Defender 將針對已使用這種方式提供端點後置備的客戶，自動在同一個歐盟資料中心進行提供。</span><span class="sxs-lookup"><span data-stu-id="0c226-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="0c226-139">確認服務已開啟</span><span class="sxs-lookup"><span data-stu-id="0c226-139">Confirm that the service is on</span></span>

<span data-ttu-id="0c226-140">服務一旦佈建，它會新增：</span><span class="sxs-lookup"><span data-stu-id="0c226-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="0c226-141">事件管理</span><span class="sxs-lookup"><span data-stu-id="0c226-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="0c226-142">用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="0c226-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="0c226-143">[進位搜尋](advanced-hunting-overview.md) 功能</span><span class="sxs-lookup"><span data-stu-id="0c226-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="0c226-144">![Microsoft 365 資訊安全中心流覽窗格的影像，以及具有事件管理和其他 ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender 功能的 Microsoft 365* 資訊安全中心功能</span><span class="sxs-lookup"><span data-stu-id="0c226-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="0c226-145">取得 Microsoft Defender 以取得身分識別資料</span><span class="sxs-lookup"><span data-stu-id="0c226-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="0c226-146">若要與 Microsoft 365 Defender 共用 Microsoft Defender 的身分識別資料，請確定已開啟 Microsoft Cloud App 安全性和身分識別整合的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="0c226-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="0c226-147">[深入瞭解這項整合](https://docs.microsoft.com/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="0c226-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="0c226-148">取得協助</span><span class="sxs-lookup"><span data-stu-id="0c226-148">Get assistance</span></span>

<span data-ttu-id="0c226-149">若要取得有關開啟 Microsoft 365 Defender 的最常見問題的 [解答，請閱讀常見問題](mtp-enable-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="0c226-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="0c226-150">Microsoft 支援人員可協助在租使用者上提供或取消提供服務及相關資源。</span><span class="sxs-lookup"><span data-stu-id="0c226-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="0c226-151">在 Microsoft  365 安全性中心中選取需要協助嗎？以尋求協助。</span><span class="sxs-lookup"><span data-stu-id="0c226-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="0c226-152">聯繫支援人員時，請提及 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="0c226-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c226-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="0c226-153">Related topics</span></span>

- [<span data-ttu-id="0c226-154">常見問題集</span><span class="sxs-lookup"><span data-stu-id="0c226-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="0c226-155">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="0c226-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="0c226-156">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="0c226-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="0c226-157">Microsoft 365 Defender 概觀</span><span class="sxs-lookup"><span data-stu-id="0c226-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="0c226-158">Microsoft Defender 端點概觀</span><span class="sxs-lookup"><span data-stu-id="0c226-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="0c226-159">Office 365 的 Defender 概觀</span><span class="sxs-lookup"><span data-stu-id="0c226-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="0c226-160">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="0c226-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="0c226-161">Microsoft Defender 身分識別概觀</span><span class="sxs-lookup"><span data-stu-id="0c226-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="0c226-162">端點資料儲存的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0c226-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
