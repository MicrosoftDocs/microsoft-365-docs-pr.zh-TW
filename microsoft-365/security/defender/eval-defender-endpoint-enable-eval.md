---
title: 啟用 Microsoft Defender for Endpoint 評估，啟用 MDE 的評估
description: 啟用您的 Microsoft 365 Defender 試用實驗室或試驗環境（包括檢查授權狀態）和上架 enpoints
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457798"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a><span data-ttu-id="01df3-103">啟用 Microsoft Defender for Endpoint 評估環境</span><span class="sxs-lookup"><span data-stu-id="01df3-103">Enable Microsoft Defender for Endpoint evaluation environment</span></span>


<span data-ttu-id="01df3-104">本文將引導您完成使用生產裝置為 Microsoft Defender for Endpoint 設定評估環境的步驟。</span><span class="sxs-lookup"><span data-stu-id="01df3-104">This article will guide you through the steps on setting up the evaluation environment for Microsoft Defender for Endpoint using production devices.</span></span> 


>[!TIP]
><span data-ttu-id="01df3-105">Microsoft Defender for Endpoint 也隨附產品內評估實驗室，您可以在其中新增預先設定的裝置，並執行模擬以評估平臺的功能。</span><span class="sxs-lookup"><span data-stu-id="01df3-105">Microsoft Defender for Endpoint also comes with an in-product evaluation lab where you can add pre-configured devices and run simulations to evaluate the capabilities of the platform.</span></span> <span data-ttu-id="01df3-106">實驗室附帶簡化的設定體驗，可協助快速示範 Microsoft Defender for Enpdoint 的價值，包含許多功能（例如高級搜尋和威脅分析）的指導方針。</span><span class="sxs-lookup"><span data-stu-id="01df3-106">The lab comes with a simplified set-up experience that can help quickly demonstrate the value of Microsoft Defender for Enpdoint including guidance for many features like advanced hunting and threat analytics.</span></span> <span data-ttu-id="01df3-107">如需詳細資訊，請參閱 [評估功能](/defender-endpoint/evaluation-lab.md)。</span><span class="sxs-lookup"><span data-stu-id="01df3-107">For more information, see [Evaluate capabilities](/defender-endpoint/evaluation-lab.md).</span></span> <br> <span data-ttu-id="01df3-108">在本文所提供的指導方針與評估實驗室之間的主要差異在於，評估環境使用生產裝置，而評估實驗室使用非生產裝置。</span><span class="sxs-lookup"><span data-stu-id="01df3-108">The main difference between the guidance provided in this article and the evaluation lab is the evaluation environment uses production devices whereas the evaluation lab uses non-production devices.</span></span> 

<span data-ttu-id="01df3-109">使用下列步驟來啟用 Microsoft Defender for Endpoint 的評估。</span><span class="sxs-lookup"><span data-stu-id="01df3-109">Use the following steps to enable the evaluation for Microsoft Defender for Endpoint.</span></span>

![在 Microsoft Defender 評估環境中啟用 Microsoft Defender for Endpoint 的步驟](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [<span data-ttu-id="01df3-111">步驟1。檢查授權狀態</span><span class="sxs-lookup"><span data-stu-id="01df3-111">Step 1. Check license state</span></span>](#step-1-check-license-state)
- [<span data-ttu-id="01df3-112">步驟2。板載端點</span><span class="sxs-lookup"><span data-stu-id="01df3-112">Step 2. Onboard endpoints</span></span>](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a><span data-ttu-id="01df3-113">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="01df3-113">Step 1.</span></span> <span data-ttu-id="01df3-114">檢查授權狀態</span><span class="sxs-lookup"><span data-stu-id="01df3-114">Check license state</span></span>

<span data-ttu-id="01df3-115">您必須先檢查授權狀態，以確認已正確布建。</span><span class="sxs-lookup"><span data-stu-id="01df3-115">You'll first need to check the license state to verify that it was properly provisioned.</span></span> <span data-ttu-id="01df3-116">您可以透過系統管理中心或 **Microsoft Azure 入口網站** 進行這項作業。</span><span class="sxs-lookup"><span data-stu-id="01df3-116">You can do this through the admin center or through the **Microsoft Azure portal**.</span></span>


1. <span data-ttu-id="01df3-117">若要查看您的授權，請移至 **Microsoft Azure 入口網站**，並流覽至「 [Microsoft Azure 入口網站授權」一節](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。</span><span class="sxs-lookup"><span data-stu-id="01df3-117">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Azure 授權頁面影像](../../media/defender/atp-licensing-azure-portal.png)

1. <span data-ttu-id="01df3-119">或者，在系統管理中心中，流覽至 [**帳單**] [  >  **訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="01df3-119">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="01df3-120">在螢幕上，您會看到所有已布建的授權及其目前的 **狀態**。</span><span class="sxs-lookup"><span data-stu-id="01df3-120">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![計費授權影像](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="01df3-122">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="01df3-122">Step 2.</span></span> <span data-ttu-id="01df3-123">使用任何支援的管理工具的板載端點</span><span class="sxs-lookup"><span data-stu-id="01df3-123">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="01df3-124">確認已正確布建授權狀態之後，即可啟動上架裝置至服務。</span><span class="sxs-lookup"><span data-stu-id="01df3-124">After verifying that the license state has been provisioned properly, you can start onboarding devices to the service.</span></span> 

<span data-ttu-id="01df3-125">為了評估 Microsoft Defender for Endpoint，我們建議您選擇執行評估的一些 Windows 10 裝置。</span><span class="sxs-lookup"><span data-stu-id="01df3-125">For the purpose of evaluating Microsoft Defender for Endpoint, we recommend choosing a couple of Windows 10 devices to conduct the evaluation on.</span></span> 

<span data-ttu-id="01df3-126">「 [計畫部署](../defender-endpoint/deployment-strategy.md) 」主題概要說明部署用於端點的 Defender 所需執行的一般步驟。</span><span class="sxs-lookup"><span data-stu-id="01df3-126">The [Plan deployment](../defender-endpoint/deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="01df3-127">觀賞這段影片，快速流覽上架程式，並瞭解可用的工具和方法。</span><span class="sxs-lookup"><span data-stu-id="01df3-127">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a><span data-ttu-id="01df3-128">上架工具選項</span><span class="sxs-lookup"><span data-stu-id="01df3-128">Onboarding tool options</span></span>

<span data-ttu-id="01df3-129">下表根據您在上架所需的端點，列出可用的工具。</span><span class="sxs-lookup"><span data-stu-id="01df3-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

<span data-ttu-id="01df3-130">端點</span><span class="sxs-lookup"><span data-stu-id="01df3-130">Endpoint</span></span> | <span data-ttu-id="01df3-131">工具選項</span><span class="sxs-lookup"><span data-stu-id="01df3-131">Tool options</span></span>
:---|:---
<span data-ttu-id="01df3-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="01df3-132">**Windows**</span></span> | <span data-ttu-id="01df3-133">[本機腳本 (最多10個裝置，) ](../defender-endpoint/configure-endpoints-script.md)，[群組原則](../defender-endpoint/configure-endpoints-gp.md)， [Microsoft 端點管理員/行動裝置管理員](../defender-endpoint/configure-endpoints-mdm.md)， [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md)， [VDI 腳本](../defender-endpoint/configure-endpoints-vdi.md)，[與 Azure Defender 整合](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span><span class="sxs-lookup"><span data-stu-id="01df3-133">[Local script (up to 10 devices)](../defender-endpoint/configure-endpoints-script.md),  [Group Policy](../defender-endpoint/configure-endpoints-gp.md),  [Microsoft Endpoint Manager/ Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md),  [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md),  [VDI scripts](../defender-endpoint/configure-endpoints-vdi.md),  [Integration with Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span></span>
<span data-ttu-id="01df3-134">**macOS**</span><span class="sxs-lookup"><span data-stu-id="01df3-134">**macOS**</span></span> | <span data-ttu-id="01df3-135">[本機腳本](../defender-endpoint/mac-install-manually.md)， [Microsoft 端點管理員](../defender-endpoint/mac-install-with-intune.md)， [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md)，行動[裝置管理](../defender-endpoint/mac-install-with-other-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="01df3-135">[Local scripts](../defender-endpoint/mac-install-manually.md),  [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md),  [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md),  [Mobile Device Management](../defender-endpoint/mac-install-with-other-mdm.md)</span></span>
<span data-ttu-id="01df3-136">**Linux 伺服器**</span><span class="sxs-lookup"><span data-stu-id="01df3-136">**Linux Server**</span></span> | <span data-ttu-id="01df3-137">[Local script](../defender-endpoint/linux-install-manually.md)、  [Puppet](../defender-endpoint/linux-install-with-puppet.md)、  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span><span class="sxs-lookup"><span data-stu-id="01df3-137">[Local script](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span></span>
<span data-ttu-id="01df3-138">**iOS**</span><span class="sxs-lookup"><span data-stu-id="01df3-138">**iOS**</span></span> | [<span data-ttu-id="01df3-139">以應用程式為基礎</span><span class="sxs-lookup"><span data-stu-id="01df3-139">App-based</span></span>](../defender-endpoint/ios-install.md)
<span data-ttu-id="01df3-140">**Android**</span><span class="sxs-lookup"><span data-stu-id="01df3-140">**Android**</span></span> | [<span data-ttu-id="01df3-141">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="01df3-141">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)



## <a name="next-step"></a><span data-ttu-id="01df3-142">後續步驟</span><span class="sxs-lookup"><span data-stu-id="01df3-142">Next step</span></span>
[<span data-ttu-id="01df3-143">設定 Microsoft Defender for Endpoint 的試用版</span><span class="sxs-lookup"><span data-stu-id="01df3-143">Setup the pilot for Microsoft Defender for Endpoint</span></span>](eval-defender-endpoint-pilot.md)
 
<span data-ttu-id="01df3-144">回到概述以 [評估 Microsoft Defender For Endpoint](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="01df3-144">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="01df3-145">回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述</span><span class="sxs-lookup"><span data-stu-id="01df3-145">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>