---
title: 試驗 Microsoft Defender for Endpoint，設定試用版、評估中的測試功能
description: 瞭解如何對 Microsoft Defender for Endpoint (MDE) 執行試驗，包括驗證試驗群組和嘗試功能。
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
ms.openlocfilehash: d1efc37bd6412e441593dc9cf81296162f7fa754
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457606"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a><span data-ttu-id="3ca5a-103">試驗 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3ca5a-103">Pilot Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="3ca5a-104">本文將引導您在執行 Microsoft Defender for Endpoint 的試驗過程中執行。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-104">This article will guide you in the process of running a pilot for Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="3ca5a-105">使用下列步驟來設定和設定 Microsoft Defender for Endpoint 的試驗。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-105">Use the following steps to setup and configure the pilot for Microsoft Defender for Endpoint.</span></span> 

![將 Microsoft Defender 身分識別新增至 Defender 評估環境的步驟](../../media/defender/m365-defender-endpoint-pilot-steps.png)

- <span data-ttu-id="3ca5a-107">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="3ca5a-107">Step 1.</span></span> <span data-ttu-id="3ca5a-108">驗證試驗群組</span><span class="sxs-lookup"><span data-stu-id="3ca5a-108">Verify pilot group</span></span>
- <span data-ttu-id="3ca5a-109">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="3ca5a-109">Step 2.</span></span> <span data-ttu-id="3ca5a-110">嘗試功能</span><span class="sxs-lookup"><span data-stu-id="3ca5a-110">Try out capabilities</span></span>

<span data-ttu-id="3ca5a-111">當您試驗 Microsoft Defender for Endpoint 時，您可以選擇先將一些裝置板載至服務，再上架出整個組織。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-111">When you pilot Microsoft Defender for Endpoint, you may choose to onboard a few devices to the service before onboarding your entire organization.</span></span>  

<span data-ttu-id="3ca5a-112">然後您可以嘗試可用的功能，例如執行攻擊模擬，並查看端點的 Defender 如何進行惡意活動，以及如何讓您進行有效的回應。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-112">You can then try out capabilities that are available such as running attack simulations and seeing how Defender for Endpoint surfaces malicious activities and enables you to conduct an efficient response.</span></span> 

## <a name="step-1-verify-pilot-group"></a><span data-ttu-id="3ca5a-113">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="3ca5a-113">Step 1.</span></span> <span data-ttu-id="3ca5a-114">驗證試驗群組</span><span class="sxs-lookup"><span data-stu-id="3ca5a-114">Verify pilot group</span></span>
<span data-ttu-id="3ca5a-115">完成 [ [啟用評估](eval-defender-endpoint-enable-eval.md) ] 區段中所述的上架步驟之後，您應該會在大約一小時之後看到裝置庫存清單中的裝置。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-115">After completing the onboarding steps outlined in the [Enable evaluation](eval-defender-endpoint-enable-eval.md) section, you should see the devices in the Device inventory list approximately after an hour.</span></span> 

<span data-ttu-id="3ca5a-116">當您看到架裝置時，您就可以繼續嘗試試用功能。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-116">When you see your onboarded devices you can then proceed with trying out capabilities.</span></span> 

## <a name="step-2-try-out-capabilities"></a><span data-ttu-id="3ca5a-117">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="3ca5a-117">Step 2.</span></span> <span data-ttu-id="3ca5a-118">嘗試功能</span><span class="sxs-lookup"><span data-stu-id="3ca5a-118">Try out capabilities</span></span>
<span data-ttu-id="3ca5a-119">現在，您已完成加入部分裝置，並確認他們已向服務報告，請試用現成可用的強大功能，以熟悉產品。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-119">Now that you've completed onboarding some devices and verified that they are reporting to the service, familiarize yourself with the product by trying out the powerful capabilities that are available right out of the box.</span></span>

<span data-ttu-id="3ca5a-120">在試驗過程中，您可以輕鬆開始試用某些功能，以查看產品的動作，而不需要經歷複雜的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-120">During the pilot, you can easily get started with trying out some of the features to see the product in action without going through complex configuration steps.</span></span>

<span data-ttu-id="3ca5a-121">讓我們從檢出儀表板開始。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-121">Let's start by checking out the dashboards.</span></span>

### <a name="view-the-device-inventory"></a><span data-ttu-id="3ca5a-122">查看裝置庫存</span><span class="sxs-lookup"><span data-stu-id="3ca5a-122">View the device inventory</span></span>
<span data-ttu-id="3ca5a-123">在您的網路中，您可以在設備清查中看到端點、網路裝置和 IoT 裝置清單。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-123">The device inventory is where you'll see the list of endpoints, network devices, and IoT devices in your network.</span></span> <span data-ttu-id="3ca5a-124">它不僅能為您提供網路中裝置的視圖，也提供有關這些裝置的深入資訊，例如網域、風險層級、作業系統平臺及其他詳細資訊，可讓您更輕鬆地識別最具風險的裝置。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-124">Not only does it provide you with a view of the devices in your network, but it also gives your in-depth information about them such as  domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="3ca5a-125">查看威脅與弱點管理儀表板</span><span class="sxs-lookup"><span data-stu-id="3ca5a-125">View the Threat and vulnerability management dashboard</span></span> 
<span data-ttu-id="3ca5a-126">威脅和弱點管理可協助您將重點放在組織最緊迫和最高風險的弱點上。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-126">Threat and vulnerability management helps you focus on the weaknesses that pose the most urgent and the highest risk to the organization.</span></span> <span data-ttu-id="3ca5a-127">在儀表板中，取得組織公開分數、Microsoft 安全分數的裝置、裝置洩密發佈、主要安全性建議、熱門的安全性建議、熱門的軟體、熱門的修復活動，以及主要公開的裝置資料的高層級視圖。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-127">From the dashboard, get a high-level view of the organization exposure score, Microsoft Secure Score for Devices, device exposure distribution, top security recommendations, top vulnerable software, top remediation activities, and top exposed device data.</span></span> 

### <a name="run-a-simulation"></a><span data-ttu-id="3ca5a-128">執行模擬</span><span class="sxs-lookup"><span data-stu-id="3ca5a-128">Run a simulation</span></span>
<span data-ttu-id="3ca5a-129">Microsoft Defender for Endpoint 隨附「 [自行「執行」」攻擊案例](https://securitycenter.windows.com/tutorials) ，您可以在試驗裝置上執行。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-129">Microsoft Defender for Endpoint comes with ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials) that you can run on your pilot devices.</span></span>  <span data-ttu-id="3ca5a-130">每個檔都包括作業系統和應用程式需求，以及針對攻擊案例的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-130">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span> <span data-ttu-id="3ca5a-131">這些腳本是安全、有記錄且便於使用。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-131">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="3ca5a-132">這些案例會反映 Defender 的端點功能，並引導您完成調查經驗。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-132">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

<span data-ttu-id="3ca5a-133">若要執行提供的任何模擬，您至少需要 [一個架裝置](../defender-endpoint/onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-133">To run any of the provided simulations, you need at least [one onboarded device](../defender-endpoint/onboard-configure.md).</span></span>

1. <span data-ttu-id="3ca5a-134">在 **[** 說明  >  **模擬 & 教學** 課程] 中，選取您要模擬的哪個可用攻擊案例：</span><span class="sxs-lookup"><span data-stu-id="3ca5a-134">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="3ca5a-135">**案例1：檔丟掉後門** -模擬 socially 工程的引誘檔的傳遞。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-135">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="3ca5a-136">檔會啟動巧盡心思的後門，可提供駭客控制權。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-136">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="3ca5a-137">**案例2： fileless 進攻中的 PowerShell 腳本** -模擬 fileless 攻擊，其受 PowerShell、showcasing 攻擊面不足和裝置教育偵測惡意記憶體活動的偵測。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-137">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="3ca5a-138">**案例3：自動化事件回應** -觸發自動調查，它會自動 hunts 及 remediates 違犯的專案，以調整您的事件回應容量。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-138">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="3ca5a-139">下載並閱讀您所選案例中提供的對應逐步檔。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-139">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="3ca5a-140">流覽以 **協助**  >  **模擬 & 教學** 課程，以下載模擬檔案或複製類比腳本。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-140">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="3ca5a-141">您可以選擇在測試裝置上下載檔案或腳本，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-141">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="3ca5a-142">依照練習檔中的指示，在測試裝置上執行類比檔或腳本。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-142">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="3ca5a-143">類比檔或腳本模仿攻擊活動，但實際上卻是良性的，且不會損害或損害測試裝置。</span><span class="sxs-lookup"><span data-stu-id="3ca5a-143">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ca5a-144">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3ca5a-144">Next steps</span></span>
[<span data-ttu-id="3ca5a-145">評估 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3ca5a-145">Evaluate Microsoft Cloud App Security</span></span>](eval-defender-mcas-overview.md)

<span data-ttu-id="3ca5a-146">回到概述以 [評估 Microsoft Defender For Endpoint](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3ca5a-146">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="3ca5a-147">回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述</span><span class="sxs-lookup"><span data-stu-id="3ca5a-147">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>