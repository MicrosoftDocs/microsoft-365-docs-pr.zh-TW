---
title: Microsoft 受管理電腦中的應用程式
description: 說明如何處理應用程式，包括如何封裝、部署及支援應用程式。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 20d68ec007ccda82816ad2288428016019f6d4b2
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840690"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="06ab0-104">Microsoft 受管理電腦中的應用程式</span><span class="sxs-lookup"><span data-stu-id="06ab0-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="06ab0-105">應用程式一般</span><span class="sxs-lookup"><span data-stu-id="06ab0-105">Apps generally</span></span>

<span data-ttu-id="06ab0-106">Microsoft 包含特定的主要應用程式，以及參與 Microsoft Managed Desktop 所需的 Microsoft 365 E3 或 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="06ab0-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="06ab0-107">不過，即使我們提供這些應用程式，仍有一些責任和動作可完成。</span><span class="sxs-lookup"><span data-stu-id="06ab0-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="06ab0-108">您也可以使用 Microsoft Intune 的部署管線，在公司入口網站或必要的後臺安裝中，為您的使用者部署其他非 Microsoft 應用程式，以進行自助服務。</span><span class="sxs-lookup"><span data-stu-id="06ab0-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="06ab0-109">如果您有專業技術，您可以自行遷移所需的應用程式。另外，Microsoft 諮詢服務 (MCS) 或非 Microsoft 廠商很樂意協助您進行打包和遷移專案。</span><span class="sxs-lookup"><span data-stu-id="06ab0-109">If you have the expertise, you can migrate those apps you need yourself; alternatively, Microsoft Consulting Services (MCS) or non-Microsoft vendors will be happy to help you with a packaging and migration project.</span></span> <span data-ttu-id="06ab0-110">如需使用 MCS 的詳細資訊，請參閱使用 [Microsoft 諮詢服務](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="06ab0-110">For more information about working with MCS, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>


## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="06ab0-111">Microsoft 提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="06ab0-111">Apps provided by Microsoft</span></span>

<span data-ttu-id="06ab0-112">隨附于 Microsoft 受管理的桌面授權64是 Microsoft 365 Apps for enterprise Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype 和 OneNote 中的應用程式 ) 。預設 *不* 會包含 Click-to-Run 版本的 microsoft Project 和 Visio，但您可以要求新增這些版本。</span><span class="sxs-lookup"><span data-stu-id="06ab0-112">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="06ab0-113">如需這些應用程式的詳細資訊，請參閱 [Install Microsoft Project or Microsoft Visio On Microsoft Managed Desktop 裝置](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="06ab0-113">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="06ab0-114">Microsoft 對於我們提供的應用程式的支援。</span><span class="sxs-lookup"><span data-stu-id="06ab0-114">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="06ab0-115">Microsoft 將為適用于企業應用程式的包含 Microsoft 365 應用程式，提供完整服務，以進行部署、更新和支援。</span><span class="sxs-lookup"><span data-stu-id="06ab0-115">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="06ab0-116">預設 *不* 會包含 microsoft Project 和 Visio 的 Click-to-Run 版本，但 Microsoft 受管理的桌面會提供部署群組，讓您的 IT 系統管理員可以管理授權，並適當地為您的組織部署這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="06ab0-116">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="06ab0-117">Microsoft 會透過 Microsoft 受管理的桌面支援通道來支援這些應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="06ab0-117">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="06ab0-118">您必須執行哪些動作才能支援我們提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="06ab0-118">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="06ab0-119">您仍需要使用這些應用程式進行的某些工作：</span><span class="sxs-lookup"><span data-stu-id="06ab0-119">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="06ab0-120">**指派授權** -您負責針對適用于企業的 Microsoft 365 應用程式，取得並指派適當的授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="06ab0-120">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="06ab0-121">**將使用者新增至安全性群組** -如果您使用的是 Microsoft Project 或 Visio，您的 IT 系統管理員必須將這些使用者新增至適當的部署群組。</span><span class="sxs-lookup"><span data-stu-id="06ab0-121">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="06ab0-122">IT 系統管理員也負責在使用者離開公司時，從這些使用者回收授權。</span><span class="sxs-lookup"><span data-stu-id="06ab0-122">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="06ab0-123">**部署 microsoft 365 附加** 元件-如果您需要任何適用于企業應用程式的 Microsoft 365 應用程式的任何附加元件，請將它們集中部署，如其他任何 Windows 32 應用程式。</span><span class="sxs-lookup"><span data-stu-id="06ab0-123">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="06ab0-124">您提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="06ab0-124">Apps you provide</span></span>

<span data-ttu-id="06ab0-125">您可能需要其他應用程式，才能進行商務作業。</span><span class="sxs-lookup"><span data-stu-id="06ab0-125">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="06ab0-126">這些應用程式僅能使用 Microsoft Intune 的部署管線部署至 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="06ab0-126">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="06ab0-127">若應用程式需要，您可以將其封裝在廠商 (，而這可能是非 Microsoft 轉銷商或 Microsoft 諮詢服務 (MCS) # A3，或者如果您有這種方式，您可以自行打包。</span><span class="sxs-lookup"><span data-stu-id="06ab0-127">If the app needs it you can have them packaged by a vendor (which could be a non-Microsoft vendor or Microsoft Consulting Services (MCS)) or if you have the means, you can package them yourself.</span></span> <span data-ttu-id="06ab0-128">然後，您可以將這些套件新增至 Microsoft 受管理的桌面入口網站，並將它們指派給 Azure Active Directory 群組，以觸發部署。</span><span class="sxs-lookup"><span data-stu-id="06ab0-128">You then add these packages to the Microsoft Managed Desktop portal and assign them to Azure Active Directory groups to trigger the deployment.</span></span> 

<span data-ttu-id="06ab0-129">如果您目前使用 Microsoft 端點設定管理員部署應用程式，則 Microsoft 受管理的桌面可以提供查詢來評估您的應用程式，並探索哪些專案準備好可遷移至 Microsoft Intune，以及哪些可能需要進行調整。</span><span class="sxs-lookup"><span data-stu-id="06ab0-129">If you currently deploy your apps by using Microsoft Endpoint Configuration Manager, Microsoft Managed Desktop can provide you with a query to assess your apps and discover which ones are ready for to migrate to Microsoft Intune and which ones might require some adjustment.</span></span>


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="06ab0-130">準備您自己的應用程式以包含在 Microsoft 受管理的桌面</span><span class="sxs-lookup"><span data-stu-id="06ab0-130">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="06ab0-131">查看您的應用程式，檢查：</span><span class="sxs-lookup"><span data-stu-id="06ab0-131">Review your apps, checking:</span></span>

- <span data-ttu-id="06ab0-132">沒有任何應用程式被禁止或具有限制的行為，如 [Microsoft Managed Desktop app 需求](https://aka.ms/app-req)所述。</span><span class="sxs-lookup"><span data-stu-id="06ab0-132">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](https://aka.ms/app-req).</span></span>
- <span data-ttu-id="06ab0-133">應用程式必須準備好由 Microsoft Intune 進行管理。</span><span class="sxs-lookup"><span data-stu-id="06ab0-133">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="06ab0-134">如需本主題的詳細資訊，請參閱 [使用 Microsoft intune 的 Windows 10 應用程式部署](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) 及 [新增應用程式至 Microsoft intune](https://docs.microsoft.com/intune/apps-add)。</span><span class="sxs-lookup"><span data-stu-id="06ab0-134">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](https://docs.microsoft.com/intune/apps-add).</span></span>
- <span data-ttu-id="06ab0-135">其他預先打包需求，例如提供授權金鑰、授權條款的合約，以及預先設定的伺服器連線。</span><span class="sxs-lookup"><span data-stu-id="06ab0-135">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

### <a name="decide-how-to-package-apps"></a><span data-ttu-id="06ab0-136">決定如何封裝應用程式</span><span class="sxs-lookup"><span data-stu-id="06ab0-136">Decide how to package apps</span></span>

<span data-ttu-id="06ab0-137">有些獨立的軟體發行者可能需要先打包應用程式，才能進行集中部署。</span><span class="sxs-lookup"><span data-stu-id="06ab0-137">Some independent software publishers might require that your apps are packaged before they are centrally deployed.</span></span> <span data-ttu-id="06ab0-138">「打包」表示應用程式的安裝程式是以授權金鑰、遠端伺服器位置或桌面快捷方式等設定來設定，以便在後臺安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="06ab0-138">“Packaging” means that the app’s installer is configured with settings like license keys, remote server locations, or desktop shortcuts so that the app can be installed in the background.</span></span>

<span data-ttu-id="06ab0-139">有三個可讓您的應用程式封裝的選項：</span><span class="sxs-lookup"><span data-stu-id="06ab0-139">There are three options to get your apps packaged:</span></span> 


- <span data-ttu-id="06ab0-140">您可以自行封裝應用程式</span><span class="sxs-lookup"><span data-stu-id="06ab0-140">You can package apps yourself</span></span>
- <span data-ttu-id="06ab0-141">您可以與非 Microsoft 廠商搭配使用</span><span class="sxs-lookup"><span data-stu-id="06ab0-141">You can work with a non-Microsoft vendor</span></span>
- <span data-ttu-id="06ab0-142">您可以接洽 MCS 以封裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="06ab0-142">You can engage with MCS to package your apps.</span></span> <span data-ttu-id="06ab0-143">請與您的 Microsoft 客戶代表合作。</span><span class="sxs-lookup"><span data-stu-id="06ab0-143">Work with your Microsoft account representative.</span></span> <span data-ttu-id="06ab0-144">如需詳細資訊，請參閱使用 [Microsoft 諮詢服務](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="06ab0-144">For more information, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>



## <a name="deploying-apps"></a><span data-ttu-id="06ab0-145">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="06ab0-145">Deploying apps</span></span>

<span data-ttu-id="06ab0-146">任何您用來取得應用程式打包方式的方法完成之後，您就可以遵循將 [應用程式部署至 Microsoft 受管理的桌面裝置](../get-started/deploy-apps.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="06ab0-146">Whatever method you use to get apps packaged, once that is complete, you're ready to follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>


