---
title: 儀表板深入資訊-威脅和弱點管理
description: 威脅和弱點管理儀表板可協助 SecOps 及安全性系統管理員解決 cybersecurity 威脅，並建立其組織的安全性恢復能力。
keywords: Microsoft Defender for Endpoint tvm，Microsoft Defender for Endpoint tvm 儀表板，威脅 & 漏洞管理，威脅和弱點管理，風險威脅 & 弱點管理，安全性設定，Microsoft 安全評分的裝置，披露分數
search.appverid: met150
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 82b6123a99eb406918708c6bf23b870ef3bc3d79
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934138"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a><span data-ttu-id="23690-104">儀表板深入資訊-威脅和弱點管理</span><span class="sxs-lookup"><span data-stu-id="23690-104">Dashboard insights - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="23690-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="23690-105">**Applies to:**</span></span>

- [<span data-ttu-id="23690-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="23690-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="23690-107">威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="23690-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="23690-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23690-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="23690-109">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="23690-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="23690-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="23690-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="23690-111">威脅和弱點管理是 Endpoint 的 Defender 元件，並提供安全性管理員和具有唯一值的安全性作業小組，包括：</span><span class="sxs-lookup"><span data-stu-id="23690-111">Threat and vulnerability management is a component of Defender for Endpoint, and provides both security administrators and security operations teams with unique value, including:</span></span>


- <span data-ttu-id="23690-112">即時端點偵測和回應（EDR）深入資訊與端點漏洞相關聯</span><span class="sxs-lookup"><span data-stu-id="23690-112">Real-time endpoint detection and response (EDR) insights correlated with endpoint vulnerabilities</span></span>
- <span data-ttu-id="23690-113">事件調查期間的寶貴裝置弱點內容</span><span class="sxs-lookup"><span data-stu-id="23690-113">Invaluable device vulnerability context during incident investigations</span></span>
- <span data-ttu-id="23690-114">透過 Microsoft Intune 和 Microsoft 端點 Configuration Manager 的內建修復程式</span><span class="sxs-lookup"><span data-stu-id="23690-114">Built-in remediation processes through Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>  
  
<span data-ttu-id="23690-115">您可以使用 [Microsoft Defender Security Center](https://securitycenter.windows.com/) 中的威脅和弱點管理功能，進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="23690-115">You can use the threat and vulnerability management capability in [Microsoft Defender Security Center](https://securitycenter.windows.com/) to:</span></span>

- <span data-ttu-id="23690-116">查看裝置的披露分數和 Microsoft 安全分數，以及最上層的安全性建議、軟體弱點、修復活動及公開的裝置</span><span class="sxs-lookup"><span data-stu-id="23690-116">View you exposure score and Microsoft Secure Score for Devices, along with top security recommendations, software vulnerability, remediation activities, and exposed devices</span></span>
- <span data-ttu-id="23690-117">將 EDR 洞察力與端點漏洞關聯，並加以處理</span><span class="sxs-lookup"><span data-stu-id="23690-117">Correlate EDR insights with endpoint vulnerabilities and process them</span></span>
- <span data-ttu-id="23690-118">選取修正選項，以會審及追蹤修正任務</span><span class="sxs-lookup"><span data-stu-id="23690-118">Select remediation options to triage and track the remediation tasks</span></span>
- <span data-ttu-id="23690-119">選取例外狀況選項及追蹤作用中例外狀況</span><span class="sxs-lookup"><span data-stu-id="23690-119">Select exception options and track active exceptions</span></span>

> [!NOTE]
> <span data-ttu-id="23690-120">在過去30天內非使用中的裝置，不會考慮反映組織威脅的資料，也不會考慮到裝置的漏洞管理洩密分數和 Microsoft 安全分數。</span><span class="sxs-lookup"><span data-stu-id="23690-120">Devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management exposure score and Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="23690-121">觀賞這段影片，可快速流覽「威脅及弱點管理」儀表板中的內容。</span><span class="sxs-lookup"><span data-stu-id="23690-121">Watch this video for a quick overview of what is in the threat and vulnerability management dashboard.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="23690-122">威脅與弱點管理儀表板</span><span class="sxs-lookup"><span data-stu-id="23690-122">Threat and vulnerability management dashboard</span></span>

 ![Microsoft Defender for Endpoint 入口網站](images/tvm-dashboard-devices.png)

<span data-ttu-id="23690-124">範圍</span><span class="sxs-lookup"><span data-stu-id="23690-124">Area</span></span> | <span data-ttu-id="23690-125">描述</span><span class="sxs-lookup"><span data-stu-id="23690-125">Description</span></span>
:---|:---
<span data-ttu-id="23690-126">**選取的裝置群組 ( #/# )**</span><span class="sxs-lookup"><span data-stu-id="23690-126">**Selected device groups (#/#)**</span></span>   | <span data-ttu-id="23690-127">篩選您想要在儀表板和卡片依設備群組查看的威脅和弱點管理資料。</span><span class="sxs-lookup"><span data-stu-id="23690-127">Filter the threat and vulnerability management data you want to see in the dashboard and cards by device groups.</span></span> <span data-ttu-id="23690-128">您在篩選中選取的專案會套用整個威脅和弱點管理頁面。</span><span class="sxs-lookup"><span data-stu-id="23690-128">What you select in the filter applies throughout the threat and vulnerability management pages.</span></span>
[<span data-ttu-id="23690-129">**暴險分數**</span><span class="sxs-lookup"><span data-stu-id="23690-129">**Exposure score**</span></span>](tvm-exposure-score.md)   | <span data-ttu-id="23690-130">請參閱貴組織裝置對威脅及弱點的影響的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="23690-130">See the current state of your organization's device exposure to threats and vulnerabilities.</span></span> <span data-ttu-id="23690-131">有許多因素會影響組織的暴露分數：在裝置中發現的弱點、裝置的可能性遭到破壞、組織中的裝置價值，以及您的裝置發現的相關警示。</span><span class="sxs-lookup"><span data-stu-id="23690-131">Several factors affect your organization's exposure score: weaknesses discovered in your devices, likelihood of your devices to be breached, value of the devices to your organization, and relevant alerts discovered with your devices.</span></span> <span data-ttu-id="23690-132">目標是降低組織的暴露分數，使其更加安全。</span><span class="sxs-lookup"><span data-stu-id="23690-132">The goal is to lower the exposure score of your organization to be more secure.</span></span> <span data-ttu-id="23690-133">若要降低分數，您需要修正安全性建議中所列的相關安全性設定問題。</span><span class="sxs-lookup"><span data-stu-id="23690-133">To reduce the score, you need to remediate the related security configuration issues listed in the security recommendations.</span></span>
[<span data-ttu-id="23690-134">**裝置用 Microsoft 安全分數**</span><span class="sxs-lookup"><span data-stu-id="23690-134">**Microsoft Secure Score for Devices**</span></span>](tvm-microsoft-secure-score-devices.md) | <span data-ttu-id="23690-135">請參閱您組織的作業系統、應用程式、網路、帳戶及安全性控制的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="23690-135">See the security posture of the operating system, applications, network, accounts, and security controls of your organization.</span></span> <span data-ttu-id="23690-136">目標是修正相關的安全性設定問題，以提升裝置的排名。</span><span class="sxs-lookup"><span data-stu-id="23690-136">The goal is to remediate the related security configuration issues to increase your score for devices.</span></span> <span data-ttu-id="23690-137">選取這些條將會帶您前往 [ **安全性建議** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="23690-137">Selecting the bars will take you to the **Security recommendation** page.</span></span>
<span data-ttu-id="23690-138">**裝置洩密分配**</span><span class="sxs-lookup"><span data-stu-id="23690-138">**Device exposure distribution**</span></span> | <span data-ttu-id="23690-139">瞭解有多少裝置會根據其公開層級公開。</span><span class="sxs-lookup"><span data-stu-id="23690-139">See how many devices are exposed based on their exposure level.</span></span> <span data-ttu-id="23690-140">選取 [環圈圖] 中的區段，以移至 [ **裝置] 清單** 頁面，並查看受影響的裝置名稱、暴露層級、風險層級，以及其他詳細資料，例如網域、作業系統平臺、其健康狀態、最後一次看到的時間，以及其標記。</span><span class="sxs-lookup"><span data-stu-id="23690-140">Select a section in the doughnut chart to go to the **Devices list** page and view the affected device names, exposure level, risk level, and other details such as domain, operating system platform, its health state, when it was last seen, and its tags.</span></span>
<span data-ttu-id="23690-141">**主要安全性建議**</span><span class="sxs-lookup"><span data-stu-id="23690-141">**Top security recommendations**</span></span> | <span data-ttu-id="23690-142">請查看排序後的安全性建議，其排序及設定優先順序取決於組織的風險危險性及其所需的緊迫程度。</span><span class="sxs-lookup"><span data-stu-id="23690-142">See the collated security recommendations that are sorted and prioritized based on your organization's risk exposure and the urgency that it requires.</span></span> <span data-ttu-id="23690-143">選取 [ **顯示更多** ]，以查看清單中的其餘安全性建議。</span><span class="sxs-lookup"><span data-stu-id="23690-143">Select **Show more** to see the rest of the security recommendations in the list.</span></span> <span data-ttu-id="23690-144">選取 [ **顯示例外** 狀況，列出例外狀況] 的建議。</span><span class="sxs-lookup"><span data-stu-id="23690-144">Select **Show exceptions** for the list of recommendations that have an exception.</span></span>
<span data-ttu-id="23690-145">**最常見的漏洞軟體**</span><span class="sxs-lookup"><span data-stu-id="23690-145">**Top vulnerable software**</span></span> | <span data-ttu-id="23690-146">透過網路裝置上安裝的易受攻擊的軟體清單清單，即時瞭解貴組織的軟體清查，以及這些電腦對組織公開分數的影響。</span><span class="sxs-lookup"><span data-stu-id="23690-146">Get real-time visibility into your organization's software inventory with a stack-ranked list of vulnerable software installed on your network's devices and how they impact your organizational exposure score.</span></span> <span data-ttu-id="23690-147">選取專案以取得詳細資料，或 **顯示更多內容** ，以查看 [ **軟體清查** ] 頁面中的其他有隱患的軟體清單。</span><span class="sxs-lookup"><span data-stu-id="23690-147">Select an item for details or **Show more** to see the rest of the vulnerable software list in the **Software inventory** page.</span></span>
<span data-ttu-id="23690-148">**主要修復活動**</span><span class="sxs-lookup"><span data-stu-id="23690-148">**Top remediation activities**</span></span> | <span data-ttu-id="23690-149">追蹤安全性建議所產生的修復活動。</span><span class="sxs-lookup"><span data-stu-id="23690-149">Track the remediation activities generated from the security recommendations.</span></span> <span data-ttu-id="23690-150">您可以選取清單中的每個專案，以查看 **修正** 頁面中的詳細資料，或選取 [ **顯示更多** ]，以查看其餘的修復活動和作用中例外狀況。</span><span class="sxs-lookup"><span data-stu-id="23690-150">You can select each item on the list to see the details in the **Remediation** page or select **Show more** to view the rest of the remediation activities, and active exceptions.</span></span>
<span data-ttu-id="23690-151">**主要公開裝置**</span><span class="sxs-lookup"><span data-stu-id="23690-151">**Top exposed devices**</span></span> | <span data-ttu-id="23690-152">查看已公開的裝置名稱和其公開層級。</span><span class="sxs-lookup"><span data-stu-id="23690-152">View exposed device names and their exposure level.</span></span> <span data-ttu-id="23690-153">從清單中選取裝置名稱，以移至 [裝置] 頁面，您可以在此頁面上查看警示、風險、事件、安全性建議、已安裝的軟體，以及已發現的裝置相關聯的漏洞。</span><span class="sxs-lookup"><span data-stu-id="23690-153">Select a device name from the list to go to the device page where you can view the alerts, risks, incidents, security recommendations, installed software, and discovered vulnerabilities associated with the exposed devices.</span></span> <span data-ttu-id="23690-154">選取 [ **顯示更多** ]，以查看其餘的 [已公開的裝置] 清單。</span><span class="sxs-lookup"><span data-stu-id="23690-154">Select **Show more** to see the rest of the exposed devices list.</span></span> <span data-ttu-id="23690-155">在 [裝置] 清單中，您可以管理標記、啟動自動調查、啟動即時回應會話、收集調查套件、執行防病毒掃描、限制應用程式執行，以及隔離裝置。</span><span class="sxs-lookup"><span data-stu-id="23690-155">From the devices list, you can manage tags, initiate automated investigations, initiate a live response session, collect an investigation package, run antivirus scan, restrict app execution, and isolate device.</span></span>

<span data-ttu-id="23690-156">如需整個入口網站上使用之圖示的詳細資訊，請參閱 [Microsoft Defender For Endpoint 圖示](portal-overview.md#microsoft-defender-for-endpoint-icons)。</span><span class="sxs-lookup"><span data-stu-id="23690-156">For more information on the icons used throughout the portal, see [Microsoft Defender for Endpoint icons](portal-overview.md#microsoft-defender-for-endpoint-icons).</span></span>


## <a name="related-topics"></a><span data-ttu-id="23690-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="23690-157">Related topics</span></span>

- [<span data-ttu-id="23690-158">威脅和弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="23690-158">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="23690-159">暴險分數</span><span class="sxs-lookup"><span data-stu-id="23690-159">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="23690-160">裝置用 Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="23690-160">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="23690-161">安全性建議</span><span class="sxs-lookup"><span data-stu-id="23690-161">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="23690-162">軟體庫存</span><span class="sxs-lookup"><span data-stu-id="23690-162">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="23690-163">活動時間表</span><span class="sxs-lookup"><span data-stu-id="23690-163">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)

