---
title: Microsoft 受管理的電腦中的應用程式
description: 說明如何處理應用程式，包括如何封裝、部署及支援應用程式。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028941"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="a1e92-104">Microsoft 受管理的電腦中的應用程式</span><span class="sxs-lookup"><span data-stu-id="a1e92-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="a1e92-105">應用程式一般</span><span class="sxs-lookup"><span data-stu-id="a1e92-105">Apps generally</span></span>

<span data-ttu-id="a1e92-106">Microsoft 包含特定的主要應用程式，以及參與 Microsoft Managed Desktop 所需的 Microsoft 365 E3 或 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="a1e92-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="a1e92-107">不過，即使我們提供這些應用程式，仍有一些責任和動作可完成。</span><span class="sxs-lookup"><span data-stu-id="a1e92-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="a1e92-108">您也可以使用 Microsoft Intune 的部署管線，在公司入口網站或必要的後臺安裝中，為您的使用者部署其他非 Microsoft 應用程式，以進行自助服務。</span><span class="sxs-lookup"><span data-stu-id="a1e92-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> 

## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="a1e92-109">Microsoft 提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="a1e92-109">Apps provided by Microsoft</span></span>

<span data-ttu-id="a1e92-110">隨附于 Microsoft 受管理的桌面授權64是 Microsoft 365 Apps for enterprise Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、商務用 Skype 和 OneNote 中的應用程式 ) 。預設 *不* 會包含 Click-to-Run 版本的 microsoft Project 和 Visio，但您可以要求新增這些版本。</span><span class="sxs-lookup"><span data-stu-id="a1e92-110">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="a1e92-111">如需這些應用程式的詳細資訊，請參閱 [Install Microsoft Project or Microsoft Visio On Microsoft Managed Desktop 裝置](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e92-111">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="a1e92-112">Microsoft 對於我們提供的應用程式的支援。</span><span class="sxs-lookup"><span data-stu-id="a1e92-112">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="a1e92-113">Microsoft 將為適用于企業應用程式的包含 Microsoft 365 應用程式，提供完整服務，以進行部署、更新和支援。</span><span class="sxs-lookup"><span data-stu-id="a1e92-113">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="a1e92-114">預設 *不* 會包含 microsoft Project 和 Visio 的 Click-to-Run 版本，但 Microsoft 受管理的桌面會提供部署群組，讓您的 IT 系統管理員可以管理授權，並適當地為您的組織部署這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="a1e92-114">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="a1e92-115">Microsoft 會透過 Microsoft 受管理的桌面支援通道來支援這些應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="a1e92-115">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="a1e92-116">您必須執行哪些動作才能支援我們提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="a1e92-116">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="a1e92-117">您仍需要使用這些應用程式進行的某些工作：</span><span class="sxs-lookup"><span data-stu-id="a1e92-117">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="a1e92-118">**指派授權** -您負責針對適用于企業的 Microsoft 365 應用程式，取得並指派適當的授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="a1e92-118">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="a1e92-119">**將使用者新增至安全性群組** -如果您使用的是 Microsoft Project 或 Visio，您的 IT 系統管理員必須將這些使用者新增至適當的部署群組。</span><span class="sxs-lookup"><span data-stu-id="a1e92-119">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="a1e92-120">IT 系統管理員也負責在使用者離開公司時，從這些使用者回收授權。</span><span class="sxs-lookup"><span data-stu-id="a1e92-120">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="a1e92-121">**部署 microsoft 365 附加** 元件-如果您需要任何適用于企業應用程式的 Microsoft 365 應用程式的任何附加元件，請將它們集中部署，如其他任何 Windows 32 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a1e92-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="a1e92-122">您提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="a1e92-122">Apps you provide</span></span>

<span data-ttu-id="a1e92-123">您可能需要其他應用程式，才能進行商務作業。</span><span class="sxs-lookup"><span data-stu-id="a1e92-123">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="a1e92-124">這些應用程式僅能使用 Microsoft Intune 的部署管線部署至 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="a1e92-124">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="a1e92-125">如需應用程式部署的詳細資訊，請依照將 [應用程式部署至 Microsoft 受管理的桌面裝置](../get-started/deploy-apps.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="a1e92-125">For more information about application deployment follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="a1e92-126">準備您自己的應用程式以包含在 Microsoft 受管理的桌面</span><span class="sxs-lookup"><span data-stu-id="a1e92-126">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="a1e92-127">查看您的應用程式，檢查：</span><span class="sxs-lookup"><span data-stu-id="a1e92-127">Review your apps, checking:</span></span>

- <span data-ttu-id="a1e92-128">沒有任何應用程式被禁止或具有限制的行為，如 [Microsoft Managed Desktop app 需求](../service-description/mmd-app-requirements.md)所述。</span><span class="sxs-lookup"><span data-stu-id="a1e92-128">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="a1e92-129">應用程式必須準備好由 Microsoft Intune 進行管理。</span><span class="sxs-lookup"><span data-stu-id="a1e92-129">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="a1e92-130">如需本主題的詳細資訊，請參閱 [使用 Microsoft intune 的 Windows 10 應用程式部署](/intune/apps-windows-10-app-deploy) 及 [新增應用程式至 Microsoft intune](/intune/apps-add)。</span><span class="sxs-lookup"><span data-stu-id="a1e92-130">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="a1e92-131">其他預先打包需求，例如提供授權金鑰、授權條款的合約，以及預先設定的伺服器連線。</span><span class="sxs-lookup"><span data-stu-id="a1e92-131">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="a1e92-132">準備就緒的步驟</span><span class="sxs-lookup"><span data-stu-id="a1e92-132">Steps to get ready</span></span>

1. <span data-ttu-id="a1e92-133">檢查 [Microsoft 受管理的桌面的必要條件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e92-133">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="a1e92-134">使用 [準備工作評估工具](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="a1e92-134">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="a1e92-135">來賓帳戶的先決條件</span><span class="sxs-lookup"><span data-stu-id="a1e92-135">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="a1e92-136">Microsoft 受管理的電腦的網路設定</span><span class="sxs-lookup"><span data-stu-id="a1e92-136">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="a1e92-137">為 Microsoft 受管理的電腦準備認證和網路設定檔</span><span class="sxs-lookup"><span data-stu-id="a1e92-137">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="a1e92-138">為 Microsoft 受管理的電腦準備內部部署資源存取</span><span class="sxs-lookup"><span data-stu-id="a1e92-138">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="a1e92-139">[Microsoft Managed Desktop 中的應用程式](apps.md) (本文) </span><span class="sxs-lookup"><span data-stu-id="a1e92-139">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="a1e92-140">為 Microsoft 受管理的電腦準備對應磁碟機</span><span class="sxs-lookup"><span data-stu-id="a1e92-140">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="a1e92-141">為 Microsoft 受管理的電腦準備列印資源</span><span class="sxs-lookup"><span data-stu-id="a1e92-141">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
