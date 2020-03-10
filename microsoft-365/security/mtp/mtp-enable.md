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
ms.openlocfilehash: fa970b28939ad43bf6a2717e603013277bc9130f
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569165"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="17f8c-104">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="17f8c-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="17f8c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="17f8c-105">**Applies to:**</span></span>
- <span data-ttu-id="17f8c-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="17f8c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="17f8c-107">Microsoft 威脅防護整合了您的事件回應流程，方法是整合跨 Microsoft Defender 進階威脅防護 (ATP)、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的重要功能。</span><span class="sxs-lookup"><span data-stu-id="17f8c-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="17f8c-108">此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。</span><span class="sxs-lookup"><span data-stu-id="17f8c-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="17f8c-109">若要取得最佳保護，並優化 Microsoft 威脅防護，我們建議您在網路上部署所有適用的受支援服務。</span><span class="sxs-lookup"><span data-stu-id="17f8c-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="17f8c-110">如需詳細資訊，請[參閱部署支援的服務](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="17f8c-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="17f8c-111">檢查授權資格和必要許可權</span><span class="sxs-lookup"><span data-stu-id="17f8c-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="17f8c-112">Microsoft 365 E5，E5 Security，or A5 授權或有效的授權組合，可提供支援服務的存取權，並可讓您在 Microsoft 365 安全性中心使用 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="17f8c-112">A Microsoft 365 E5, E5 Security, or A5 license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

<span data-ttu-id="17f8c-113">如需詳細的授權資訊，請[閱讀授權要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="17f8c-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="17f8c-114">檢查您的角色</span><span class="sxs-lookup"><span data-stu-id="17f8c-114">Check your role</span></span>
<span data-ttu-id="17f8c-115">您必須是**全域系統管理員**或 Azure Active Directory 中的**安全性系統管理員**，才可開啟 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="17f8c-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="17f8c-116">在 Azure AD 中查看您的角色</span><span class="sxs-lookup"><span data-stu-id="17f8c-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="17f8c-117">開始使用服務</span><span class="sxs-lookup"><span data-stu-id="17f8c-117">Start using the service</span></span>
<span data-ttu-id="17f8c-118">Microsoft 威脅防護會匯總各種整合服務中的資料。</span><span class="sxs-lookup"><span data-stu-id="17f8c-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="17f8c-119">它會集中處理及儲存資料，以識別新的洞察力，並可讓集中式回應工作流程成為可能。</span><span class="sxs-lookup"><span data-stu-id="17f8c-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="17f8c-120">在您開啟服務之前，當您從功能窗格中選取 [**事件**]、[**動作中心**] 或 [**搜尋**] 時，microsoft 365 安全中心（[security.microsoft.com](https://security.microsoft.com)）會顯示 microsoft 威脅防護歡迎頁面。</span><span class="sxs-lookup"><span data-stu-id="17f8c-120">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="17f8c-121">如果您不具備使用 Microsoft 威脅防護的資格，就不會顯示這些流覽選項。</span><span class="sxs-lookup"><span data-stu-id="17f8c-121">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="17f8c-122">![顯示 microsoft](../../media/mtp-welcome.png)
*365 security center 中*microsoft 威脅防護歡迎頁面上的 microsoft 威脅防護功能，顯示 microsoft 威脅防護歡迎頁面的圖像</span><span class="sxs-lookup"><span data-stu-id="17f8c-122">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="17f8c-123">若要開啟 Microsoft 威脅防護，只需從歡迎頁面完成此程式。</span><span class="sxs-lookup"><span data-stu-id="17f8c-123">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="17f8c-124">您也可以在功能窗格中存取**設定**（[security.microsoft.com/settings](https://security.microsoft.com/settings)），並選取 [ **microsoft 威脅防護**]，以開啟 microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="17f8c-124">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="17f8c-125">如果您在功能窗格中看不到**設定**或無法存取頁面，請檢查您的許可權和授權。</span><span class="sxs-lookup"><span data-stu-id="17f8c-125">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="17f8c-126">選取資料中心位置</span><span class="sxs-lookup"><span data-stu-id="17f8c-126">Select data center location</span></span>
<span data-ttu-id="17f8c-127">如果已為您的組織佈建 Microsoft Defender ATP，則資料將會儲存在為[您的 Microsoft Defender ATP 資料](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)選取的相同資料中心位置中。</span><span class="sxs-lookup"><span data-stu-id="17f8c-127">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="17f8c-128">如果您沒有 Microsoft Defender ATP，系統會要求您選擇專用於 Microsoft 威脅防護的新資料中心位置。</span><span class="sxs-lookup"><span data-stu-id="17f8c-128">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="17f8c-129">您必須先提供同意，才可在服務和匯總間共用資料。</span><span class="sxs-lookup"><span data-stu-id="17f8c-129">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="17f8c-130">確認服務已開啟</span><span class="sxs-lookup"><span data-stu-id="17f8c-130">Confirm that the service is on</span></span>
<span data-ttu-id="17f8c-131">服務一旦佈建，它會新增：</span><span class="sxs-lookup"><span data-stu-id="17f8c-131">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="17f8c-132">事件管理</span><span class="sxs-lookup"><span data-stu-id="17f8c-132">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="17f8c-133">用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="17f8c-133">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="17f8c-134">[高級搜尋](advanced-hunting-overview.md)功能</span><span class="sxs-lookup"><span data-stu-id="17f8c-134">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="17f8c-135">![Microsoft 365 security center 導覽窗格與 microsoft 威脅防護的影像功能](../../media/mtp-on.png)
*microsoft 365 security center with 事件管理和其他 Microsoft 威脅防護功能*</span><span class="sxs-lookup"><span data-stu-id="17f8c-135">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="17f8c-136">取得 Azure ATP 資料</span><span class="sxs-lookup"><span data-stu-id="17f8c-136">Getting Azure ATP data</span></span>
<span data-ttu-id="17f8c-137">若要使用 Microsoft 威脅防護共用 Azure ATP 資料，請確認已開啟 Microsoft Cloud App Security 和 Azure ATP 整合。</span><span class="sxs-lookup"><span data-stu-id="17f8c-137">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="17f8c-138">深入了解此整合</span><span class="sxs-lookup"><span data-stu-id="17f8c-138">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="17f8c-139">關閉 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="17f8c-139">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="17f8c-140">若要停止使用 Microsoft 威脅防護，請移至 Microsoft 365 安全性中心的 [設定]\*\*\*\*  >  [Microsoft 威脅防護]\*\*\*\*  >  [選擇加入/選擇退出]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="17f8c-140">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="17f8c-141">取消選取 [開啟 Microsoft 威脅防護]\*\*\*\* 並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="17f8c-141">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="17f8c-142">對應的功能將會從 Microsoft 365 的安全性中心移除。</span><span class="sxs-lookup"><span data-stu-id="17f8c-142">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="17f8c-143">取得協助</span><span class="sxs-lookup"><span data-stu-id="17f8c-143">Get assistance</span></span>

<span data-ttu-id="17f8c-144">Microsoft 支援人員可協助您布建或取消設定租使用者上的服務和相關資源。</span><span class="sxs-lookup"><span data-stu-id="17f8c-144">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="17f8c-145">如需協助，請選取 [Microsoft 365 security center] 中的 [**需要協助？** ]。</span><span class="sxs-lookup"><span data-stu-id="17f8c-145">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="17f8c-146">當您聯繫支援時，請提及 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="17f8c-146">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="17f8c-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="17f8c-147">Related topics</span></span>

- [<span data-ttu-id="17f8c-148">Microsoft 威脅防護更新概觀</span><span class="sxs-lookup"><span data-stu-id="17f8c-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="17f8c-149">授權需求和其他必要條件</span><span class="sxs-lookup"><span data-stu-id="17f8c-149">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="17f8c-150">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="17f8c-150">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="17f8c-151">Microsoft Defender ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="17f8c-151">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="17f8c-152">Office 365 ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="17f8c-152">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="17f8c-153">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="17f8c-153">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="17f8c-154">Azure ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="17f8c-154">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="17f8c-155">Microsoft Defender ATP 資料儲存</span><span class="sxs-lookup"><span data-stu-id="17f8c-155">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
