---
title: '透過模擬攻擊體驗 Microsoft Defender for Endpoint (MDE) '
description: 試驗您的 Microsoft 365 Defender 試用實驗室或試驗環境。
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
ms.openlocfilehash: 131a048e806976afa3bffbd3f3bce2d61a370225
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457824"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a><span data-ttu-id="5e02d-104">透過模擬攻擊體驗 Microsoft Defender for Endpoint (MDE) </span><span class="sxs-lookup"><span data-stu-id="5e02d-104">Experience Microsoft Defender for Endpoint (MDE) through simulated attacks</span></span>

>[!TIP]
>
>- <span data-ttu-id="5e02d-105">深入瞭解 Microsoft Defender for Endpoint 中的最新增強功能： [端點的新](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)功能</span><span class="sxs-lookup"><span data-stu-id="5e02d-105">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="5e02d-106">在最近的 MITRE 評估中，以試用版的端點示範業界一流的光學器件和偵測功能。</span><span class="sxs-lookup"><span data-stu-id="5e02d-106">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="5e02d-107">讀取：[從 MITRE ATT 中 Insights&以 CK 為基礎的評估](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。</span><span class="sxs-lookup"><span data-stu-id="5e02d-107">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="5e02d-108">您可能想要在將許多裝置上架到服務之前，體驗端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="5e02d-108">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="5e02d-109">若要這麼做，您可以在一些測試裝置上執行受控制的攻擊模擬。</span><span class="sxs-lookup"><span data-stu-id="5e02d-109">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="5e02d-110">在執行模擬後的攻擊之後，您可以查看 Endpoint 的 Endpoint 面對惡意活動的反應，以及如何啟用有效的回應。</span><span class="sxs-lookup"><span data-stu-id="5e02d-110">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5e02d-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="5e02d-111">Before you begin</span></span>

<span data-ttu-id="5e02d-112">若要執行提供的任何模擬，您至少需要 [一個架裝置](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="5e02d-112">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span>

<span data-ttu-id="5e02d-113">閱讀每個攻擊案例中提供的逐步檔。</span><span class="sxs-lookup"><span data-stu-id="5e02d-113">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="5e02d-114">每個檔都包括作業系統和應用程式需求，以及針對攻擊案例的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="5e02d-114">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="5e02d-115">執行模擬</span><span class="sxs-lookup"><span data-stu-id="5e02d-115">Run a simulation</span></span>

1. <span data-ttu-id="5e02d-116">在 **[** 說明  >  **模擬 & 教學** 課程] 中，選取您要模擬的哪個可用攻擊案例：</span><span class="sxs-lookup"><span data-stu-id="5e02d-116">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="5e02d-117">**案例1：檔丟掉後門** -模擬 socially 工程的引誘檔的傳遞。</span><span class="sxs-lookup"><span data-stu-id="5e02d-117">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="5e02d-118">檔會啟動巧盡心思的後門，可提供駭客控制權。</span><span class="sxs-lookup"><span data-stu-id="5e02d-118">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="5e02d-119">**案例2： fileless 進攻中的 PowerShell 腳本** -模擬 fileless 攻擊，其受 PowerShell、showcasing 攻擊面不足和裝置教育偵測惡意記憶體活動的偵測。</span><span class="sxs-lookup"><span data-stu-id="5e02d-119">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="5e02d-120">**案例3：自動化事件回應** -觸發自動調查，它會自動 hunts 及 remediates 違犯的專案，以調整您的事件回應容量。</span><span class="sxs-lookup"><span data-stu-id="5e02d-120">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="5e02d-121">下載並閱讀您所選案例中提供的對應逐步檔。</span><span class="sxs-lookup"><span data-stu-id="5e02d-121">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="5e02d-122">流覽以 **協助**  >  **模擬 & 教學** 課程，以下載模擬檔案或複製類比腳本。</span><span class="sxs-lookup"><span data-stu-id="5e02d-122">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="5e02d-123">您可以選擇在測試裝置上下載檔案或腳本，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="5e02d-123">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="5e02d-124">依照練習檔中的指示，在測試裝置上執行類比檔或腳本。</span><span class="sxs-lookup"><span data-stu-id="5e02d-124">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="5e02d-125">類比檔或腳本模仿攻擊活動，但實際上卻是良性的，且不會損害或損害測試裝置。</span><span class="sxs-lookup"><span data-stu-id="5e02d-125">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
>

## <a name="alternate-topic-text"></a><span data-ttu-id="5e02d-126">替代主題文字</span><span class="sxs-lookup"><span data-stu-id="5e02d-126">ALTERNATE TOPIC TEXT</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="5e02d-127">類比攻擊案例</span><span class="sxs-lookup"><span data-stu-id="5e02d-127">Simulate attack scenarios</span></span>

<span data-ttu-id="5e02d-128">透過連線來執行您自己的攻擊模擬，以使用測試裝置。</span><span class="sxs-lookup"><span data-stu-id="5e02d-128">Use the test devices to run your own attack simulations by connecting to them.</span></span>

<span data-ttu-id="5e02d-129">您可以使用下列方式模擬攻擊案例：</span><span class="sxs-lookup"><span data-stu-id="5e02d-129">You can simulate attack scenarios using:</span></span>

- <span data-ttu-id="5e02d-130">「 [自行執行它」攻擊案例](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="5e02d-130">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="5e02d-131">威脅模擬器</span><span class="sxs-lookup"><span data-stu-id="5e02d-131">Threat simulators</span></span>

<span data-ttu-id="5e02d-132">您也可以使用 [高級搜尋](advanced-hunting-overview.md) 查詢資料和 [威脅分析](threat-analytics.md) ，以查看有關新興威脅的報告。</span><span class="sxs-lookup"><span data-stu-id="5e02d-132">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="5e02d-133">自行攻擊案例</span><span class="sxs-lookup"><span data-stu-id="5e02d-133">Do-it-yourself attack scenarios</span></span>

<span data-ttu-id="5e02d-134">如果您正在尋找預先類比，您可以使用我們「 [自己動手」的攻擊案例](https://securitycenter.windows.com/tutorials)。</span><span class="sxs-lookup"><span data-stu-id="5e02d-134">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="5e02d-135">這些腳本是安全、有記錄且便於使用。</span><span class="sxs-lookup"><span data-stu-id="5e02d-135">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="5e02d-136">這些案例會反映 Defender 的端點功能，並引導您完成調查經驗。</span><span class="sxs-lookup"><span data-stu-id="5e02d-136">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

>[!NOTE]
><span data-ttu-id="5e02d-137">使用 RDP 進行與測試裝置的連線。</span><span class="sxs-lookup"><span data-stu-id="5e02d-137">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="5e02d-138">請確定您的防火牆設定允許 RDP 連線。</span><span class="sxs-lookup"><span data-stu-id="5e02d-138">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="5e02d-139">連線裝置，並選取 **連線** 以執行攻擊模擬。</span><span class="sxs-lookup"><span data-stu-id="5e02d-139">Connect to your device and run an attack simulation by selecting **Connect**.</span></span>

    ![測試裝置的 [連接] 按鈕影像](images/test-machine-table.png)

2. <span data-ttu-id="5e02d-141">選取 [**連線**] 以儲存 RDP 檔案並加以啟動。</span><span class="sxs-lookup"><span data-stu-id="5e02d-141">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![遠端桌面連線的影像](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="5e02d-143">如果您沒有在初始設定期間儲存的密碼複本，您可以從功能表中選取 [ **重設密碼** ] 以重設密碼： ![ 重設密碼的影像](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="5e02d-143">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span>
    >
    > <span data-ttu-id="5e02d-144">裝置會將其狀態變更為「執行重新設定密碼」，然後您會在幾分鐘內看到新的密碼。</span><span class="sxs-lookup"><span data-stu-id="5e02d-144">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="5e02d-145">輸入在裝置建立步驟中顯示的密碼。</span><span class="sxs-lookup"><span data-stu-id="5e02d-145">Enter the password that was displayed during the device creation step.</span></span>

   ![輸入認證的視窗影像](images/enter-password.png)

4. <span data-ttu-id="5e02d-147">在裝置上執行自行攻擊模擬。</span><span class="sxs-lookup"><span data-stu-id="5e02d-147">Run Do-it-yourself attack simulations on the device.</span></span>

### <a name="threat-simulator-scenarios"></a><span data-ttu-id="5e02d-148">威脅模擬器案例</span><span class="sxs-lookup"><span data-stu-id="5e02d-148">Threat simulator scenarios</span></span>

<span data-ttu-id="5e02d-149">如果您選擇在實驗室設定期間安裝任何受支援的威脅模擬器，您可以在評估實驗室裝置上執行內建模擬。</span><span class="sxs-lookup"><span data-stu-id="5e02d-149">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span>

<span data-ttu-id="5e02d-150">使用協力廠商平臺執行威脅模擬是一種很好的方法，可以在實驗室環境的範圍內評估 Microsoft Defender for Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="5e02d-150">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
>
><span data-ttu-id="5e02d-151">在您可以執行模擬之前，請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="5e02d-151">Before you can run simulations, ensure the following requirements are met:</span></span>

>- <span data-ttu-id="5e02d-152">裝置必須新增至評估實驗室</span><span class="sxs-lookup"><span data-stu-id="5e02d-152">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="5e02d-153">威脅模擬器必須安裝在評估實驗室中</span><span class="sxs-lookup"><span data-stu-id="5e02d-153">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="5e02d-154">從入口網站選取 [ **建立類比**]。</span><span class="sxs-lookup"><span data-stu-id="5e02d-154">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="5e02d-155">選取威脅模擬器。</span><span class="sxs-lookup"><span data-stu-id="5e02d-155">Select a threat simulator.</span></span>

    ![威脅模擬器選取專案的影像](images/select-simulator.png)

3. <span data-ttu-id="5e02d-157">選擇類比或查看類比圖庫，以流覽可用模擬。</span><span class="sxs-lookup"><span data-stu-id="5e02d-157">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span>

    <span data-ttu-id="5e02d-158">您可以從下列專案進入類比庫：</span><span class="sxs-lookup"><span data-stu-id="5e02d-158">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="5e02d-159">**模擬一覽表** 磚中的主要評估儀表板或</span><span class="sxs-lookup"><span data-stu-id="5e02d-159">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="5e02d-160">透過流覽流覽窗格 **評估與示教**  >  **類比 & 教學** 課程，然後選取 [**模擬目錄**]。</span><span class="sxs-lookup"><span data-stu-id="5e02d-160">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="5e02d-161">選取您要在其中執行模擬的裝置。</span><span class="sxs-lookup"><span data-stu-id="5e02d-161">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="5e02d-162">選取 [ **建立類比**]。</span><span class="sxs-lookup"><span data-stu-id="5e02d-162">Select **Create simulation**.</span></span>

6. <span data-ttu-id="5e02d-163">選取 [ **模擬** ] 索引標籤，以查看模擬的進度。查看類比狀態、作用中警示和其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5e02d-163">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span>

    <span data-ttu-id="5e02d-164">![模擬的影像索引標籤](images/simulations-tab.png)
</span><span class="sxs-lookup"><span data-stu-id="5e02d-164">![Image of simulations tab](images/simulations-tab.png)
</span></span><br>

<span data-ttu-id="5e02d-165">執行模擬後，我們鼓勵您逐步完成實驗室進度列，並探索 **Microsoft Defender For Endpoint 會觸發自動調查和修正**。</span><span class="sxs-lookup"><span data-stu-id="5e02d-165">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="5e02d-166">查看由功能收集及分析的證據。</span><span class="sxs-lookup"><span data-stu-id="5e02d-166">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="5e02d-167">使用豐富的查詢語言和原始遙測，並查看在威脅分析中所記錄的一些世界範圍威脅，以透過「高級搜尋」搜尋攻擊證據。</span><span class="sxs-lookup"><span data-stu-id="5e02d-167">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>
