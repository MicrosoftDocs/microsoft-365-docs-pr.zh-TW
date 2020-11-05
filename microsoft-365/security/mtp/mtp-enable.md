---
title: 在 Microsoft 365 security center 中開啟 Microsoft 365 Defender
description: 瞭解如何啟用 Microsoft 365 Defender，並開始整合您的安全性事件與回應。
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
ms.openlocfilehash: c5b8cae9e4eabcb2b3c6a7eb76971784193a221d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920499"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="218ca-104">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="218ca-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="218ca-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="218ca-105">**Applies to:**</span></span>
- <span data-ttu-id="218ca-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="218ca-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="218ca-107">[Microsoft 365 Defender](microsoft-threat-protection.md) 整合您的事件回應程式，方法是在 microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security 和 microsoft Defender for Identity 中整合重要功能。</span><span class="sxs-lookup"><span data-stu-id="218ca-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="218ca-108">此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。</span><span class="sxs-lookup"><span data-stu-id="218ca-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="218ca-109">Microsoft 365 Defender 會在具備必要許可權的合格客戶造訪 Microsoft 365 的安全性中心時自動開啟。</span><span class="sxs-lookup"><span data-stu-id="218ca-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="218ca-110">請閱讀本文以瞭解各種必要條件，以及如何布建 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="218ca-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="218ca-111">檢查授權資格和必要許可權</span><span class="sxs-lookup"><span data-stu-id="218ca-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="218ca-112">Microsoft 365 安全性產品的授權一般會使您在 Microsoft 365 的安全性中心使用 Microsoft 365 Defender，而不需要額外授權成本。</span><span class="sxs-lookup"><span data-stu-id="218ca-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="218ca-113">我們建議您取得 Microsoft 365 E5、E5 或 A5 安全授權或有效的授權組合，以提供所有支援服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="218ca-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="218ca-114">如需詳細的授權資訊，請 [閱讀授權要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="218ca-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="218ca-115">檢查您的角色</span><span class="sxs-lookup"><span data-stu-id="218ca-115">Check your role</span></span>
<span data-ttu-id="218ca-116">您必須是 **全域系統管理員** 或 Azure Active Directory 中的 **安全性系統管理員** ，才可開啟 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="218ca-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="218ca-117">在 Azure AD 中查看您的角色</span><span class="sxs-lookup"><span data-stu-id="218ca-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="218ca-118">支援的服務</span><span class="sxs-lookup"><span data-stu-id="218ca-118">Supported services</span></span>
<span data-ttu-id="218ca-119">Microsoft 365 Defender 會匯總您已部署之各種支援服務的資料。</span><span class="sxs-lookup"><span data-stu-id="218ca-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="218ca-120">它會集中處理及儲存資料，以識別新的洞察力，並可讓集中式回應工作流程成為可能。</span><span class="sxs-lookup"><span data-stu-id="218ca-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="218ca-121">這樣做不會影響現有的部署、設定或與整合服務相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="218ca-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="218ca-122">若要取得最佳保護，並優化 Microsoft 365 Defender，我們建議在您的網路上部署所有適用的受支援服務。</span><span class="sxs-lookup"><span data-stu-id="218ca-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="218ca-123">如需詳細資訊，請 [參閱部署支援的服務](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="218ca-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="218ca-124">啟動服務之前</span><span class="sxs-lookup"><span data-stu-id="218ca-124">Before starting the service</span></span>
<span data-ttu-id="218ca-125">在您開啟服務之前，Microsoft 365 security center ( [security.microsoft.com](https://security.microsoft.com)) 會在您從功能窗格中選取 [ **事件** ]、[ **動作中心** ] 或 [ **搜尋** ] 時，顯示 [microsoft 365 Defender 設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="218ca-125">Before you turn on the service, the Microsoft 365 security center ( [security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents** , **Action center** , or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="218ca-126">如果您不具備使用 Microsoft 365 Defender 的資格，就不會顯示這些流覽專案。</span><span class="sxs-lookup"><span data-stu-id="218ca-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="218ca-127">![Microsoft 365 Defender 尚未在 microsoft ](../../media/mtp-enable/mtp-settings.png)
 *365 security center 中開啟 Microsoft 365 defender 設定* 時所顯示之 microsoft 365 defender 設定頁面的圖像</span><span class="sxs-lookup"><span data-stu-id="218ca-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="218ca-128">啟動服務</span><span class="sxs-lookup"><span data-stu-id="218ca-128">Starting the service</span></span>
<span data-ttu-id="218ca-129">若要開啟 Microsoft 365 Defender，只要選取 [ **開啟 microsoft 365 defender** ] 並套用變更。</span><span class="sxs-lookup"><span data-stu-id="218ca-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="218ca-130">您也可以在功能窗格中選取 [ ( [security.microsoft.com/settings](https://security.microsoft.com/settings)) **設定** ]，然後選取 [ **microsoft 365 Defender** ]，即可存取此選項。</span><span class="sxs-lookup"><span data-stu-id="218ca-130">You can also access this option by selecting **Settings** ( [security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

>[!NOTE]
><span data-ttu-id="218ca-131">如果您在功能窗格中看不到 **設定** 或無法存取頁面，請檢查您的許可權和授權。</span><span class="sxs-lookup"><span data-stu-id="218ca-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="218ca-132">資料中心位置</span><span class="sxs-lookup"><span data-stu-id="218ca-132">Data center location</span></span>
<span data-ttu-id="218ca-133">Microsoft 365 Defender 會將資料儲存並處理于 [Microsoft Defender For Endpoint 所使用的相同位置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="218ca-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="218ca-134">如果您沒有 Microsoft Defender for Endpoint，會根據使用中 Microsoft 365 安全性服務的位置，自動選取新的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="218ca-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="218ca-135">選取的資料中心位置會顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="218ca-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="218ca-136">在 Microsoft 365 的安全性中心中，選取 [ **需要協助** ]，以與 microsoft 支援部門聯繫，以在不同的資料中心位置布建 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="218ca-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="218ca-137">Microsoft Defender for Endpoint 會在歐盟 (歐盟透過 Azure Defender 開啟時) 資料中心。</span><span class="sxs-lookup"><span data-stu-id="218ca-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="218ca-138">Microsoft 365 Defender 會在相同的歐盟資料中心，針對以這種方式布建 Defender 的客戶自動布建。</span><span class="sxs-lookup"><span data-stu-id="218ca-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="218ca-139">確認服務已開啟</span><span class="sxs-lookup"><span data-stu-id="218ca-139">Confirm that the service is on</span></span>
<span data-ttu-id="218ca-140">服務一旦佈建，它會新增：</span><span class="sxs-lookup"><span data-stu-id="218ca-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="218ca-141">事件管理</span><span class="sxs-lookup"><span data-stu-id="218ca-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="218ca-142">用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="218ca-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="218ca-143">[高級搜尋](advanced-hunting-overview.md) 功能</span><span class="sxs-lookup"><span data-stu-id="218ca-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="218ca-144">![Microsoft 365 security center 導覽窗格與 Microsoft 365 Defender 的影像功能 ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 security center with 事件管理和其他 Microsoft 365 Defender 功能*</span><span class="sxs-lookup"><span data-stu-id="218ca-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="218ca-145">取得 Microsoft Defender 的身分識別資料</span><span class="sxs-lookup"><span data-stu-id="218ca-145">Getting Microsoft Defender for Identity data</span></span>
<span data-ttu-id="218ca-146">若要使用 Microsoft 365 Defender 共用 Microsoft Defender 的身分識別資料，請確定 Microsoft Cloud App Security 和 Microsoft Defender for Identity integration 已開啟。</span><span class="sxs-lookup"><span data-stu-id="218ca-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> [<span data-ttu-id="218ca-147">深入了解此整合</span><span class="sxs-lookup"><span data-stu-id="218ca-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a><span data-ttu-id="218ca-148">關閉 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="218ca-148">Turn off Microsoft 365 Defender</span></span>
<span data-ttu-id="218ca-149">若要停止使用 microsoft 365 defender，請 **Settings** 移至 microsoft  >  365 security center 中的設定 **Microsoft 365 Defender**  >  **加入宣告/自願退出** 。</span><span class="sxs-lookup"><span data-stu-id="218ca-149">To stop using Microsoft 365 Defender, go to **Settings** > **Microsoft 365 Defender** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="218ca-150">取消選取 [ **開啟 Microsoft 365 Defender** ] 並套用變更。</span><span class="sxs-lookup"><span data-stu-id="218ca-150">Unselect **Turn on Microsoft 365 Defender** and apply the changes.</span></span>

<span data-ttu-id="218ca-151">對應的功能將會從 Microsoft 365 的安全性中心移除。</span><span class="sxs-lookup"><span data-stu-id="218ca-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="218ca-152">取得協助</span><span class="sxs-lookup"><span data-stu-id="218ca-152">Get assistance</span></span>

<span data-ttu-id="218ca-153">若要取得有關開啟 Microsoft 365 Defender 的最常見問題的答案，請 [參閱常見問題](mtp-enable-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="218ca-153">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="218ca-154">Microsoft 支援人員可協助您布建或取消設定租使用者上的服務和相關資源。</span><span class="sxs-lookup"><span data-stu-id="218ca-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="218ca-155">如需協助，請選取 [Microsoft 365 security center] 中的 [ **需要協助？** ]。</span><span class="sxs-lookup"><span data-stu-id="218ca-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="218ca-156">當您聯繫支援時，請提及 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="218ca-156">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="218ca-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="218ca-157">Related topics</span></span>

- [<span data-ttu-id="218ca-158">常見問題集</span><span class="sxs-lookup"><span data-stu-id="218ca-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="218ca-159">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="218ca-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="218ca-160">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="218ca-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="218ca-161">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="218ca-161">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="218ca-162">Microsoft Defender for Endpoint 簡介</span><span class="sxs-lookup"><span data-stu-id="218ca-162">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="218ca-163">適用于 Office 的 Defender 365 簡介</span><span class="sxs-lookup"><span data-stu-id="218ca-163">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="218ca-164">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="218ca-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="218ca-165">Microsoft Defender 身分識別概述</span><span class="sxs-lookup"><span data-stu-id="218ca-165">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="218ca-166">Microsoft Defender for Endpoint data storage</span><span class="sxs-lookup"><span data-stu-id="218ca-166">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
