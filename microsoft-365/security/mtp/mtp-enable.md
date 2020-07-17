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
ms.openlocfilehash: b6ac30f7e32bbec80952ad4f2104032886b11503
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016340"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="3db3b-104">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="3db3b-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="3db3b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3db3b-105">**Applies to:**</span></span>
- <span data-ttu-id="3db3b-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="3db3b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3db3b-107">[Microsoft 威脅防護](microsoft-threat-protection.md)會整合您的事件回應程式，方法是將主要功能與 Microsoft Defender 高級威脅防護（ATP）、OFFICE 365 ATP、Microsoft Cloud App Security 和 Azure atp 整合在一起。</span><span class="sxs-lookup"><span data-stu-id="3db3b-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="3db3b-108">此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。</span><span class="sxs-lookup"><span data-stu-id="3db3b-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="3db3b-109">當具有必要許可權的合格客戶具備必要365許可權時，microsoft 威脅防護即會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="3db3b-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="3db3b-110">請閱讀本文以瞭解各種必要條件，以及如何布建 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="3db3b-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="3db3b-111">檢查授權資格和必要許可權</span><span class="sxs-lookup"><span data-stu-id="3db3b-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="3db3b-112">Microsoft 365 安全性產品的授權一般會使您在 Microsoft 365 的安全性中心使用 Microsoft 威脅防護，而不需要額外授權成本。</span><span class="sxs-lookup"><span data-stu-id="3db3b-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="3db3b-113">我們建議您取得 Microsoft 365 E5、E5 或 A5 安全授權或有效的授權組合，以提供所有支援服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="3db3b-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="3db3b-114">如需詳細的授權資訊，請[閱讀授權要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="3db3b-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="3db3b-115">檢查您的角色</span><span class="sxs-lookup"><span data-stu-id="3db3b-115">Check your role</span></span>
<span data-ttu-id="3db3b-116">您必須是**全域系統管理員**或 Azure Active Directory 中的**安全性系統管理員**，才可開啟 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="3db3b-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="3db3b-117">在 Azure AD 中查看您的角色</span><span class="sxs-lookup"><span data-stu-id="3db3b-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="3db3b-118">支援的服務</span><span class="sxs-lookup"><span data-stu-id="3db3b-118">Supported services</span></span>
<span data-ttu-id="3db3b-119">Microsoft 威脅防護會匯總您已部署之各種支援服務的資料。</span><span class="sxs-lookup"><span data-stu-id="3db3b-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="3db3b-120">它會集中處理及儲存資料，以識別新的洞察力，並可讓集中式回應工作流程成為可能。</span><span class="sxs-lookup"><span data-stu-id="3db3b-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="3db3b-121">這樣做不會影響現有的部署、設定或與整合服務相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="3db3b-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="3db3b-122">若要取得最佳保護，並優化 Microsoft 威脅防護，我們建議您在網路上部署所有適用的受支援服務。</span><span class="sxs-lookup"><span data-stu-id="3db3b-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="3db3b-123">如需詳細資訊，請[參閱部署支援的服務](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="3db3b-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="3db3b-124">啟動服務之前</span><span class="sxs-lookup"><span data-stu-id="3db3b-124">Before starting the service</span></span>
<span data-ttu-id="3db3b-125">在您開啟服務之前，Microsoft 365 的安全性中心（[security.microsoft.com](https://security.microsoft.com)）會在您從功能窗格中選取 [**事件**]、[**動作中心**] 或 [**搜尋**] 時，顯示「microsoft 威脅防護設定」頁面。</span><span class="sxs-lookup"><span data-stu-id="3db3b-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="3db3b-126">如果您不具備使用 Microsoft 威脅防護的資格，就不會顯示這些流覽專案。</span><span class="sxs-lookup"><span data-stu-id="3db3b-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="3db3b-127">![Microsoft ](../../media/mtp-enable/mtp-settings.png)
 *365 security center 中*未開啟 microsoft 威脅防護設定時所顯示之 microsoft 威脅防護設定頁面的圖像</span><span class="sxs-lookup"><span data-stu-id="3db3b-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="3db3b-128">啟動服務</span><span class="sxs-lookup"><span data-stu-id="3db3b-128">Starting the service</span></span>
<span data-ttu-id="3db3b-129">若要開啟 Microsoft 威脅防護，只要選取 [**開啟 Microsoft 威脅防護**] 並套用變更。</span><span class="sxs-lookup"><span data-stu-id="3db3b-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="3db3b-130">您也可以在功能窗格中選取 [**設定**] （[security.microsoft.com/settings](https://security.microsoft.com/settings)），然後選取 [ **microsoft 威脅防護**]，即可存取此選項。</span><span class="sxs-lookup"><span data-stu-id="3db3b-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="3db3b-131">如果您在功能窗格中看不到**設定**或無法存取頁面，請檢查您的許可權和授權。</span><span class="sxs-lookup"><span data-stu-id="3db3b-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="3db3b-132">資料中心位置</span><span class="sxs-lookup"><span data-stu-id="3db3b-132">Data center location</span></span>
<span data-ttu-id="3db3b-133">Microsoft 威脅防護會儲存和處理[Microsoft DEFENDER ATP 使用的相同位置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)的資料。</span><span class="sxs-lookup"><span data-stu-id="3db3b-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="3db3b-134">如果您沒有 Microsoft Defender ATP，會根據使用中 Microsoft 365 安全性服務的位置，自動選取新的資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="3db3b-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="3db3b-135">選取的資料中心位置會顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="3db3b-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="3db3b-136">在 Microsoft 365 的安全性中心中，選取 [**需要協助**]，以與 microsoft 支援人員聯繫，以在不同的資料中心位置提供 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="3db3b-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft Threat Protection in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="3db3b-137">當透過 Azure Security Center 開啟時，Microsoft Defender ATP 會自動布建在歐盟（EU）資料中心。</span><span class="sxs-lookup"><span data-stu-id="3db3b-137">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="3db3b-138">在相同的歐盟資料中心，針對以這種方式布建 Microsoft Defender ATP 的客戶，會自動為其提供 microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="3db3b-138">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="3db3b-139">確認服務已開啟</span><span class="sxs-lookup"><span data-stu-id="3db3b-139">Confirm that the service is on</span></span>
<span data-ttu-id="3db3b-140">服務一旦佈建，它會新增：</span><span class="sxs-lookup"><span data-stu-id="3db3b-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="3db3b-141">事件管理</span><span class="sxs-lookup"><span data-stu-id="3db3b-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="3db3b-142">用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="3db3b-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="3db3b-143">[高級搜尋](advanced-hunting-overview.md)功能</span><span class="sxs-lookup"><span data-stu-id="3db3b-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="3db3b-144">![Microsoft 365 security center 導覽窗格與 Microsoft 威脅防護的影像功能 ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 security center with 事件管理和其他 Microsoft 威脅防護功能*</span><span class="sxs-lookup"><span data-stu-id="3db3b-144">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="3db3b-145">取得 Azure ATP 資料</span><span class="sxs-lookup"><span data-stu-id="3db3b-145">Getting Azure ATP data</span></span>
<span data-ttu-id="3db3b-146">若要使用 Microsoft 威脅防護共用 Azure ATP 資料，請確認已開啟 Microsoft Cloud App Security 和 Azure ATP 整合。</span><span class="sxs-lookup"><span data-stu-id="3db3b-146">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="3db3b-147">深入了解此整合</span><span class="sxs-lookup"><span data-stu-id="3db3b-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="3db3b-148">關閉 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="3db3b-148">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="3db3b-149">若要停止使用 Microsoft 威脅防護，請移至 Microsoft 365 安全性中心的 [設定]\*\*\*\*  >  [Microsoft 威脅防護]\*\*\*\*  >  [選擇加入/選擇退出]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3db3b-149">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="3db3b-150">取消選取 [**開啟 Microsoft 威脅防護**]，然後套用變更。</span><span class="sxs-lookup"><span data-stu-id="3db3b-150">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="3db3b-151">對應的功能將會從 Microsoft 365 的安全性中心移除。</span><span class="sxs-lookup"><span data-stu-id="3db3b-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="3db3b-152">取得協助</span><span class="sxs-lookup"><span data-stu-id="3db3b-152">Get assistance</span></span>

<span data-ttu-id="3db3b-153">若要取得有關開啟 Microsoft 威脅防護最常見的常見問題的答案，請[參閱常見問題](mtp-enable-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="3db3b-153">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="3db3b-154">Microsoft 支援人員可協助您布建或取消設定租使用者上的服務和相關資源。</span><span class="sxs-lookup"><span data-stu-id="3db3b-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="3db3b-155">如需協助，請選取 [Microsoft 365 security center] 中的 [**需要協助？** ]。</span><span class="sxs-lookup"><span data-stu-id="3db3b-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="3db3b-156">當您聯繫支援時，請提及 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="3db3b-156">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3db3b-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="3db3b-157">Related topics</span></span>

- [<span data-ttu-id="3db3b-158">常見問題集</span><span class="sxs-lookup"><span data-stu-id="3db3b-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="3db3b-159">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="3db3b-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="3db3b-160">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="3db3b-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="3db3b-161">Microsoft 威脅防護更新概觀</span><span class="sxs-lookup"><span data-stu-id="3db3b-161">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="3db3b-162">Microsoft Defender ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="3db3b-162">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="3db3b-163">Office 365 ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="3db3b-163">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="3db3b-164">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="3db3b-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="3db3b-165">Azure ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="3db3b-165">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="3db3b-166">Microsoft Defender ATP 資料儲存</span><span class="sxs-lookup"><span data-stu-id="3db3b-166">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)