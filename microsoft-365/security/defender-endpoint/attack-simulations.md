---
title: 透過模擬攻擊體驗 Microsoft Defender for Endpoint
description: 執行提供的攻擊案例模擬，以體驗 Microsoft Defender for Endpoint 如何偵測、調查和回應違規行為。
keywords: test，案例，攻擊，模擬，模擬，diy，Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 9a56167f0025ec42f4fd441886f83026c1bf23d6
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339531"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="e5b30-104">透過模擬攻擊體驗 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e5b30-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e5b30-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e5b30-105">**Applies to:**</span></span>
- [<span data-ttu-id="e5b30-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e5b30-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e5b30-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5b30-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="e5b30-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e5b30-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e5b30-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e5b30-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="e5b30-110">深入瞭解 Microsoft Defender for Endpoint 中的最新增強功能： [端點的新](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)功能</span><span class="sxs-lookup"><span data-stu-id="e5b30-110">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="e5b30-111">在最近的 MITRE 評估中，以試用版的端點示範業界一流的光學器件和偵測功能。</span><span class="sxs-lookup"><span data-stu-id="e5b30-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="e5b30-112">讀取：[從 MITRE ATT 中 Insights&以 CK 為基礎的評估](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。</span><span class="sxs-lookup"><span data-stu-id="e5b30-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="e5b30-113">您可能想要在將許多裝置上架到服務之前，體驗端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="e5b30-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="e5b30-114">若要這麼做，您可以在一些測試裝置上執行受控制的攻擊模擬。</span><span class="sxs-lookup"><span data-stu-id="e5b30-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="e5b30-115">在執行模擬後的攻擊之後，您可以查看 Endpoint 的 Endpoint 面對惡意活動的反應，以及如何啟用有效的回應。</span><span class="sxs-lookup"><span data-stu-id="e5b30-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e5b30-116">事前準備</span><span class="sxs-lookup"><span data-stu-id="e5b30-116">Before you begin</span></span>

<span data-ttu-id="e5b30-117">若要執行提供的任何模擬，您至少需要 [一個架裝置](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="e5b30-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="e5b30-118">閱讀每個攻擊案例中提供的逐步檔。</span><span class="sxs-lookup"><span data-stu-id="e5b30-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="e5b30-119">每個檔都包括作業系統和應用程式需求，以及針對攻擊案例的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="e5b30-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="e5b30-120">執行模擬</span><span class="sxs-lookup"><span data-stu-id="e5b30-120">Run a simulation</span></span>

1. <span data-ttu-id="e5b30-121">在 **端點**  >  **評估中 & 教程**  >  **教程 & 模擬**，請選取您要模擬的哪個可用攻擊案例：</span><span class="sxs-lookup"><span data-stu-id="e5b30-121">In **Endpoints** > **Evaluation & tutorials** > **Tutorials & simulations**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="e5b30-122">**案例1：檔丟掉後門** -模擬 socially 工程的引誘檔的傳遞。</span><span class="sxs-lookup"><span data-stu-id="e5b30-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="e5b30-123">檔會啟動巧盡心思的後門，可提供駭客控制權。</span><span class="sxs-lookup"><span data-stu-id="e5b30-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="e5b30-124">**案例2： fileless 進攻中的 PowerShell 腳本** -模擬 fileless 攻擊，其受 PowerShell、showcasing 攻擊面不足和裝置教育偵測惡意記憶體活動的偵測。</span><span class="sxs-lookup"><span data-stu-id="e5b30-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="e5b30-125">**案例3：自動化事件回應** -觸發自動調查，它會自動 hunts 及 remediates 違犯的專案，以調整您的事件回應容量。</span><span class="sxs-lookup"><span data-stu-id="e5b30-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="e5b30-126">下載並閱讀您所選案例中提供的對應逐步檔。</span><span class="sxs-lookup"><span data-stu-id="e5b30-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="e5b30-127">流覽以 **協助**  >  **模擬 & 教學** 課程，以下載模擬檔案或複製類比腳本。</span><span class="sxs-lookup"><span data-stu-id="e5b30-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="e5b30-128">您可以選擇在測試裝置上下載檔案或腳本，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="e5b30-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="e5b30-129">依照練習檔中的指示，在測試裝置上執行類比檔或腳本。</span><span class="sxs-lookup"><span data-stu-id="e5b30-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="e5b30-130">類比檔或腳本模仿攻擊活動，但實際上卻是良性的，且不會損害或損害測試裝置。</span><span class="sxs-lookup"><span data-stu-id="e5b30-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="e5b30-131">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e5b30-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e5b30-132">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e5b30-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="e5b30-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="e5b30-133">Related topics</span></span>

- [<span data-ttu-id="e5b30-134">將裝置上線</span><span class="sxs-lookup"><span data-stu-id="e5b30-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="e5b30-135">將 Windows 10 裝置上線</span><span class="sxs-lookup"><span data-stu-id="e5b30-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
