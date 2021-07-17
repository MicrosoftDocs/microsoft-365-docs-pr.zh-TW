---
title: 端點評估的試驗性 Defender
description: 啟用您的 Microsoft 365 Defender 試用實驗室或試驗環境。
keywords: Microsoft 365 Defender 試用版，請嘗試 Microsoft 365 Defender，評估 Microsoft 365 Defender，Microsoft 365 Defender 評估實驗室，Microsoft 365 Defender 試驗，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457841"
---
# <a name="pilot-mde-evaluation"></a><span data-ttu-id="2ac3b-104">試驗 MDE 評估</span><span class="sxs-lookup"><span data-stu-id="2ac3b-104">Pilot MDE Evaluation</span></span>

>[!NOTE]
><span data-ttu-id="2ac3b-105">為便於您透過一般部署，此案例只會涵蓋 Microsoft Endpoint Configuration Manager 的使用。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-105">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="2ac3b-106">Defender for Endpoint 支援使用其他上架工具，但不涵蓋部署指南中的那些案例。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-106">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="2ac3b-107">如需詳細資訊，請參閱 [在 Microsoft Defender For Endpoint 中的板載裝置](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-107">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="step-1-check-license-state"></a><span data-ttu-id="2ac3b-108">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="2ac3b-108">Step 1.</span></span> <span data-ttu-id="2ac3b-109">檢查授權狀態</span><span class="sxs-lookup"><span data-stu-id="2ac3b-109">Check license state</span></span>

<span data-ttu-id="2ac3b-110">檢查授權狀態以及是否已正確布建，可透過系統管理中心或透過 **Microsoft Azure 入口網站** 進行。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-110">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="2ac3b-111">若要查看您的授權，請移至 **Microsoft Azure 入口網站**，並流覽至「 [Microsoft Azure 入口網站授權」一節](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-111">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Azure 授權頁面影像](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="2ac3b-113">或者，在系統管理中心中，流覽至 [**帳單**] [  >  **訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-113">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="2ac3b-114">在螢幕上，您會看到所有已布建的授權及其目前的 **狀態**。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-114">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![計費授權影像](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="2ac3b-116">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="2ac3b-116">Step 2.</span></span> <span data-ttu-id="2ac3b-117">使用任何支援的管理工具的板載端點</span><span class="sxs-lookup"><span data-stu-id="2ac3b-117">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="2ac3b-118">「 [計畫部署](deployment-strategy.md) 」主題概要說明部署用於端點的 Defender 所需執行的一般步驟。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-118">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="2ac3b-119">觀賞這段影片，快速流覽上架程式，並瞭解可用的工具和方法。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-119">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

<span data-ttu-id="2ac3b-120">在識別您的架構之後，您必須決定要使用的部署方法。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-120">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="2ac3b-121">您選擇的部署工具會影響您板載端點到服務的方式。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-121">The deployment tool you choose influences how you onboard endpoints to the service.</span></span>

### <a name="onboarding-tool-options"></a><span data-ttu-id="2ac3b-122">上架工具選項</span><span class="sxs-lookup"><span data-stu-id="2ac3b-122">Onboarding tool options</span></span>

<span data-ttu-id="2ac3b-123">下表根據您在上架所需的端點，列出可用的工具。</span><span class="sxs-lookup"><span data-stu-id="2ac3b-123">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="2ac3b-124">端點</span><span class="sxs-lookup"><span data-stu-id="2ac3b-124">Endpoint</span></span>     | <span data-ttu-id="2ac3b-125">工具選項</span><span class="sxs-lookup"><span data-stu-id="2ac3b-125">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="2ac3b-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="2ac3b-126">**Windows**</span></span>  |  [<span data-ttu-id="2ac3b-127">本機腳本 (最多10個裝置) </span><span class="sxs-lookup"><span data-stu-id="2ac3b-127">Local script (up to 10 devices)</span></span>](../defender-endpoint/configure-endpoints-script.md) <br> [<span data-ttu-id="2ac3b-128">群組原則</span><span class="sxs-lookup"><span data-stu-id="2ac3b-128">Group Policy</span></span>](../defender-endpoint/configure-endpoints-gp.md) <br> [<span data-ttu-id="2ac3b-129">Microsoft 端點管理員/行動裝置管理員</span><span class="sxs-lookup"><span data-stu-id="2ac3b-129">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](../defender-endpoint/configure-endpoints-mdm.md) <br> [<span data-ttu-id="2ac3b-130">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2ac3b-130">Microsoft Endpoint Configuration Manager</span></span>](../defender-endpoint/configure-endpoints-sccm.md) <br> [<span data-ttu-id="2ac3b-131">VDI 腳本</span><span class="sxs-lookup"><span data-stu-id="2ac3b-131">VDI scripts</span></span>](../defender-endpoint/configure-endpoints-vdi.md) <br> [<span data-ttu-id="2ac3b-132">與 Azure Defender 整合</span><span class="sxs-lookup"><span data-stu-id="2ac3b-132">Integration with Azure Defender</span></span>](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="2ac3b-133">**macOS**</span><span class="sxs-lookup"><span data-stu-id="2ac3b-133">**macOS**</span></span>    | [<span data-ttu-id="2ac3b-134">本機指令碼</span><span class="sxs-lookup"><span data-stu-id="2ac3b-134">Local scripts</span></span>](../defender-endpoint/mac-install-manually.md) <br> [<span data-ttu-id="2ac3b-135">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="2ac3b-135">Microsoft Endpoint Manager</span></span>](../defender-endpoint/mac-install-with-intune.md) <br> [<span data-ttu-id="2ac3b-136">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="2ac3b-136">JAMF Pro</span></span>](../defender-endpoint/mac-install-with-jamf.md) <br> [<span data-ttu-id="2ac3b-137">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="2ac3b-137">Mobile Device Management</span></span>](../defender-endpoint/mac-install-with-other-mdm.md) |
| <span data-ttu-id="2ac3b-138">**Linux 伺服器**</span><span class="sxs-lookup"><span data-stu-id="2ac3b-138">**Linux Server**</span></span> | [<span data-ttu-id="2ac3b-139">本機腳本</span><span class="sxs-lookup"><span data-stu-id="2ac3b-139">Local script</span></span>](../defender-endpoint/linux-install-manually.md) <br> [<span data-ttu-id="2ac3b-140">木偶</span><span class="sxs-lookup"><span data-stu-id="2ac3b-140">Puppet</span></span>](../defender-endpoint/linux-install-with-puppet.md) <br> [<span data-ttu-id="2ac3b-141">Ansible</span><span class="sxs-lookup"><span data-stu-id="2ac3b-141">Ansible</span></span>](../defender-endpoint/linux-install-with-ansible.md)|
| <span data-ttu-id="2ac3b-142">**iOS**</span><span class="sxs-lookup"><span data-stu-id="2ac3b-142">**iOS**</span></span>      | [<span data-ttu-id="2ac3b-143">以應用程式為基礎</span><span class="sxs-lookup"><span data-stu-id="2ac3b-143">App-based</span></span>](../defender-endpoint/ios-install.md)                                |
| <span data-ttu-id="2ac3b-144">**Android**</span><span class="sxs-lookup"><span data-stu-id="2ac3b-144">**Android**</span></span>  | [<span data-ttu-id="2ac3b-145">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="2ac3b-145">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)               |
