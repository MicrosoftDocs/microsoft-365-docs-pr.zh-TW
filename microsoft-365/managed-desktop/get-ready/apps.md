---
title: Microsoft 受管理電腦中的應用程式
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bc7192cf82c825a13780567663695d96a760b3ef
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530100"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="ee898-103">Microsoft 受管理電腦中的應用程式</span><span class="sxs-lookup"><span data-stu-id="ee898-103">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="ee898-104">應用程式一般</span><span class="sxs-lookup"><span data-stu-id="ee898-104">Apps generally</span></span>

<span data-ttu-id="ee898-105">Microsoft 包含特定的主要應用程式，以及參與 Microsoft Managed Desktop 所需的 Microsoft 365 E3 或 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="ee898-105">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="ee898-106">不過，即使我們提供這些應用程式，仍有一些責任和動作可完成。</span><span class="sxs-lookup"><span data-stu-id="ee898-106">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="ee898-107">您也可以使用 Microsoft Intune 的部署管線，透過公司入口網站或必要的背景安裝，將其他非 Microsoft 應用程式部署至使用者，以進行自助服務。</span><span class="sxs-lookup"><span data-stu-id="ee898-107">You can also deploy additional non-Microsoft apps to your end users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="ee898-108">如果您有專業技術，您可以自行遷移所需的應用程式。或者，Microsoft 諮詢服務（MCS）或非 Microsoft 廠商很樂意協助您進行打包和遷移專案。</span><span class="sxs-lookup"><span data-stu-id="ee898-108">If you have the expertise, you can migrate those apps you need yourself; alternatively, Microsoft Consulting Services (MCS) or non-Microsoft vendors will be happy to help you with a packaging and migration project.</span></span> <span data-ttu-id="ee898-109">如需使用 MCS 的詳細資訊，請參閱使用[Microsoft 諮詢服務](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="ee898-109">For more information about working with MCS, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>


## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="ee898-110">Microsoft 提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="ee898-110">Apps provided by Microsoft</span></span>

<span data-ttu-id="ee898-111">隨附于 Microsoft 受管理的桌面授權中的 Microsoft 365 應用程式中的64位版本的應用程式，適用于企業標準套件（Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype 和 OneNote）。預設*不*會包含 Microsoft Project 和 Visio 的 Click-to-Run 版本，但您可以要求新增這些版本。</span><span class="sxs-lookup"><span data-stu-id="ee898-111">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="ee898-112">如需這些應用程式的詳細資訊，請參閱[Install Microsoft Project or Microsoft Visio On Microsoft Managed Desktop 裝置](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="ee898-112">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="ee898-113">Microsoft 對於我們提供的應用程式的支援。</span><span class="sxs-lookup"><span data-stu-id="ee898-113">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="ee898-114">Microsoft 將為適用于企業應用程式的包含 Microsoft 365 應用程式，提供完整服務，以進行部署、更新和支援。</span><span class="sxs-lookup"><span data-stu-id="ee898-114">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="ee898-115">預設*不*會包含 microsoft Project 和 Visio 的 Click-to-Run 版本，但 Microsoft 受管理的桌面會提供部署群組，讓您的 IT 系統管理員可以管理授權，並適當地為您的組織部署這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="ee898-115">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="ee898-116">Microsoft 將透過 Microsoft 受管理的桌面支援通道來支援這些應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="ee898-116">Microsoft will support end users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="ee898-117">您必須執行哪些動作才能支援我們提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="ee898-117">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="ee898-118">您仍需要使用這些應用程式進行的某些工作：</span><span class="sxs-lookup"><span data-stu-id="ee898-118">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="ee898-119">**指派授權**-您負責針對適用于 Enterprise 的 Microsoft 365 應用程式取得或指派適當的授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="ee898-119">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to end users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="ee898-120">**將使用者新增至安全性群組**-如果您使用的是 Microsoft Project 或 Visio，您的 IT 系統管理員必須將這些使用者新增至適當的部署群組。</span><span class="sxs-lookup"><span data-stu-id="ee898-120">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="ee898-121">IT 系統管理員也負責在使用者離開公司時，從這些使用者回收授權。</span><span class="sxs-lookup"><span data-stu-id="ee898-121">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="ee898-122">**部署 microsoft 365 附加**元件-如果您需要任何適用于企業應用程式的 Microsoft 365 應用程式的任何附加元件，請將它們集中部署，如其他任何 Windows 32 應用程式。</span><span class="sxs-lookup"><span data-stu-id="ee898-122">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="ee898-123">您提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="ee898-123">Apps you provide</span></span>

<span data-ttu-id="ee898-124">當然，您可能需要許多其他應用程式供商務運作使用。</span><span class="sxs-lookup"><span data-stu-id="ee898-124">Of course, you probably have a number of other apps you need for your business operations.</span></span> <span data-ttu-id="ee898-125">使用 Microsoft Intune 的部署管線，只可將這些裝置部署至 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="ee898-125">These can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="ee898-126">若應用程式需要，您可以將其封裝（可能是非 Microsoft 轉銷商或 Microsoft 諮詢服務（MCS）），或如果您有這種方式，您可以自行打包。</span><span class="sxs-lookup"><span data-stu-id="ee898-126">If the app needs it you can have them packaged by a vendor (which could be a non-Microsoft vendor or Microsoft Consulting Services (MCS)) or if you have the means, you can package them yourself.</span></span> <span data-ttu-id="ee898-127">然後，您可以將這些套件新增至 Microsoft 受管理的桌面入口網站，並將它們指派給 Azure Active Directory 群組，以觸發部署。</span><span class="sxs-lookup"><span data-stu-id="ee898-127">You then add these packages to the Microsoft Managed Desktop portal and assign them to Azure Active Directory groups to trigger the deployment.</span></span> 

<span data-ttu-id="ee898-128">如果您目前使用 Microsoft 端點設定管理員部署應用程式，則 Microsoft 受管理的桌面可以提供查詢來評估您的應用程式，並探索哪些專案準備好可遷移至 Microsoft Intune，以及哪些可能需要進行調整。</span><span class="sxs-lookup"><span data-stu-id="ee898-128">If you currently deploy your apps by using Microsoft Endpoint Configuration Manager, Microsoft Managed Desktop can provide you with a query to assess your apps and discover which ones are ready for to migrate to Microsoft Intune and which ones might require some adjustment.</span></span>


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="ee898-129">準備您自己的應用程式以包含在 Microsoft 受管理的桌面</span><span class="sxs-lookup"><span data-stu-id="ee898-129">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="ee898-130">查看您的應用程式，檢查：</span><span class="sxs-lookup"><span data-stu-id="ee898-130">Review your apps, checking:</span></span>

- <span data-ttu-id="ee898-131">沒有任何應用程式被禁止或具有限制的行為，如[Microsoft Managed Desktop app 需求](https://aka.ms/app-req)所述。</span><span class="sxs-lookup"><span data-stu-id="ee898-131">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](https://aka.ms/app-req).</span></span>
- <span data-ttu-id="ee898-132">應用程式必須準備好由 Microsoft Intune 進行管理。</span><span class="sxs-lookup"><span data-stu-id="ee898-132">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="ee898-133">如需相關資訊，請參閱[Windows 10 app deployment Using Microsoft intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)及[新增應用程式至 Microsoft intune](https://docs.microsoft.com/intune/apps-add)。</span><span class="sxs-lookup"><span data-stu-id="ee898-133">For more about this, see [Windows 10 app deployment using Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](https://docs.microsoft.com/intune/apps-add).</span></span>
- <span data-ttu-id="ee898-134">其他預先打包需求，例如提供授權金鑰、授權條款的合約，以及預先設定的伺服器連線。</span><span class="sxs-lookup"><span data-stu-id="ee898-134">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

### <a name="decide-how-to-package-apps"></a><span data-ttu-id="ee898-135">決定如何封裝應用程式</span><span class="sxs-lookup"><span data-stu-id="ee898-135">Decide how to package apps</span></span>

<span data-ttu-id="ee898-136">有些獨立的軟體廠商可能需要先封裝應用程式，才能進行集中部署。</span><span class="sxs-lookup"><span data-stu-id="ee898-136">Some independent software vendors might require that your apps are packaged before they are centrally deployed.</span></span> <span data-ttu-id="ee898-137">「打包」表示應用程式的安裝程式是以授權金鑰、遠端伺服器位置或桌面快捷方式等設定來設定，以便在後臺安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="ee898-137">“Packaging” means that the app’s installer is configured with settings like license keys, remote server locations, or desktop shortcuts so that the app can be installed in the background.</span></span>

<span data-ttu-id="ee898-138">有三個可讓您的應用程式封裝的選項：</span><span class="sxs-lookup"><span data-stu-id="ee898-138">There are three options to get your apps packaged:</span></span> 


- <span data-ttu-id="ee898-139">您可以自行封裝應用程式</span><span class="sxs-lookup"><span data-stu-id="ee898-139">You can package apps yourself</span></span>
- <span data-ttu-id="ee898-140">您可以與非 Microsoft 廠商搭配使用</span><span class="sxs-lookup"><span data-stu-id="ee898-140">You can work with a non-Microsoft vendor</span></span>
- <span data-ttu-id="ee898-141">您可以接洽 MCS 以封裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="ee898-141">You can engage with MCS to package your apps.</span></span> <span data-ttu-id="ee898-142">請與您的 Microsoft 客戶代表合作。</span><span class="sxs-lookup"><span data-stu-id="ee898-142">Work with your Microsoft account representative.</span></span> <span data-ttu-id="ee898-143">如需詳細資訊，請參閱使用[Microsoft 諮詢服務](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="ee898-143">For more details, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>







## <a name="deploying-apps"></a><span data-ttu-id="ee898-144">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="ee898-144">Deploying apps</span></span>

<span data-ttu-id="ee898-145">任何您用來取得應用程式打包方式的方法完成之後，您就可以遵循將[應用程式部署至 Microsoft 受管理的桌面裝置](../get-started/deploy-apps.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="ee898-145">Whatever method you use to get apps packaged, once that is complete, you're ready to follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>


