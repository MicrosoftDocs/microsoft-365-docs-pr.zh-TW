---
title: Microsoft Defender for Endpoint 入口網站概述
description: Microsoft Defender 資訊安全中心可以監視您的商業網路，並協助回應潛在的高級持續威脅 (APT) 或資料破壞。
keywords: Microsoft Defender 資訊安全中心，入口網站，cybersecurity 威脅情報，儀表板，警示佇列，裝置清單，設定，裝置管理，高級攻擊
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa7f2df1f0164f24c7f4698e8aa0b699f4884c09
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186218"
---
# <a name="microsoft-defender-security-center-portal-overview"></a><span data-ttu-id="fc56f-104">Microsoft Defender 安全中心入口網站概觀</span><span class="sxs-lookup"><span data-stu-id="fc56f-104">Microsoft Defender Security Center portal overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fc56f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="fc56f-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc56f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fc56f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc56f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc56f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="fc56f-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="fc56f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fc56f-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="fc56f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink) 

<span data-ttu-id="fc56f-110">Enterprise 安全小組可使用 Microsoft Defender 資訊安全中心監視及協助回應潛在的持續威脅活動或資料違例的警示。</span><span class="sxs-lookup"><span data-stu-id="fc56f-110">Enterprise security teams can use Microsoft Defender Security Center to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span>

<span data-ttu-id="fc56f-111">您可以使用[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="fc56f-111">You can use [Microsoft Defender Security Center](https://securitycenter.windows.com/) to:</span></span>

- <span data-ttu-id="fc56f-112">從您的端點查看、排序及會審警示</span><span class="sxs-lookup"><span data-stu-id="fc56f-112">View, sort, and triage alerts from your endpoints</span></span>
- <span data-ttu-id="fc56f-113">搜尋有關觀察到的指標的詳細資訊，例如檔案及 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fc56f-113">Search for more information on observed indicators such as files and IP Addresses</span></span>
- <span data-ttu-id="fc56f-114">變更 Microsoft Defender 的端點設定，包括時區及複查授權資訊</span><span class="sxs-lookup"><span data-stu-id="fc56f-114">Change Microsoft Defender for Endpoint settings, including time zone and review licensing information</span></span>

## <a name="microsoft-defender-security-center"></a><span data-ttu-id="fc56f-115">Microsoft Defender 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="fc56f-115">Microsoft Defender Security Center</span></span>

<span data-ttu-id="fc56f-116">當您開啟入口網站時，您會看到：</span><span class="sxs-lookup"><span data-stu-id="fc56f-116">When you open the portal, you'll see:</span></span>

- <span data-ttu-id="fc56f-117"> (1) 導覽窗格 (選取功能窗格頂端的水平線以顯示或隱藏它) </span><span class="sxs-lookup"><span data-stu-id="fc56f-117">(1) Navigation pane (select the horizontal lines at the top of the navigation pane to show or hide it)</span></span>
- <span data-ttu-id="fc56f-118"> (2) 搜尋、Community 中心、當地語系化、協助和支援、意見反應</span><span class="sxs-lookup"><span data-stu-id="fc56f-118">(2) Search, Community center, Localization, Help and support, Feedback</span></span>

 ![Microsoft Defender for Endpoint 入口網站](images/mdatp-portal-overview.png)

> [!NOTE]
> <span data-ttu-id="fc56f-120">只有在您的裝置使用 Microsoft Defender 防毒軟體成為預設的即時保護反惡意軟體產品時，才會顯示惡意程式碼相關的偵測。</span><span class="sxs-lookup"><span data-stu-id="fc56f-120">Malware related detections will only appear if your devices are using Microsoft Defender Antivirus as the default real-time protection antimalware product.</span></span>

<span data-ttu-id="fc56f-121">您可以使用所有區段中可用的功能表選項來流覽入口網站。</span><span class="sxs-lookup"><span data-stu-id="fc56f-121">You can navigate through the portal using the menu options available in all sections.</span></span> <span data-ttu-id="fc56f-122">請參閱下表，以取得每個區段的描述。</span><span class="sxs-lookup"><span data-stu-id="fc56f-122">Refer to the following table for a description of each section.</span></span>

<span data-ttu-id="fc56f-123">區域</span><span class="sxs-lookup"><span data-stu-id="fc56f-123">Area</span></span> | <span data-ttu-id="fc56f-124">描述</span><span class="sxs-lookup"><span data-stu-id="fc56f-124">Description</span></span>
:---|:---
<span data-ttu-id="fc56f-125">**(1) 導覽窗格**</span><span class="sxs-lookup"><span data-stu-id="fc56f-125">**(1) Navigation pane**</span></span> | <span data-ttu-id="fc56f-126">使用功能窗格在 **儀表板**、**事件**、**裝置清單**、**警示佇列**、**自動調查**、**高級搜尋**、**報告**、**合作夥伴 & APIs**、**威脅 & 弱點管理**、**評估與教程**、**服務健康** 情況、設定 **管理** 及 **設定** 之間移動。</span><span class="sxs-lookup"><span data-stu-id="fc56f-126">Use the navigation pane to move between **Dashboards**, **Incidents**, **Devices list**, **Alerts queue**, **Automated investigations**, **Advanced hunting**, **Reports**, **Partners & APIs**, **Threat & Vulnerability Management**, **Evaluation and tutorials**, **Service health**, **Configuration management**, and **Settings**.</span></span> <span data-ttu-id="fc56f-127">選取導覽窗格頂端的水平線，以顯示或隱藏它。</span><span class="sxs-lookup"><span data-stu-id="fc56f-127">Select the horizontal lines at the top of the navigation pane to show or hide it.</span></span>
<span data-ttu-id="fc56f-128">**儀錶 板**</span><span class="sxs-lookup"><span data-stu-id="fc56f-128">**Dashboards**</span></span> | <span data-ttu-id="fc56f-129">存取使用中的自動調查、作用中警示、自動調查統計資料、有風險的裝置、具有感應器問題的裝置、服務健康情況、偵測來源及每日裝置報告儀表板的狀態。</span><span class="sxs-lookup"><span data-stu-id="fc56f-129">Access the active automated investigations, active alerts, automated investigations statistics, devices at risk, users at risk, devices with sensor issues, service health, detection sources, and daily devices reporting dashboards.</span></span>
<span data-ttu-id="fc56f-130">**事件**</span><span class="sxs-lookup"><span data-stu-id="fc56f-130">**Incidents**</span></span> | <span data-ttu-id="fc56f-131">查看已匯總為事件的警示。</span><span class="sxs-lookup"><span data-stu-id="fc56f-131">View alerts that have been aggregated as incidents.</span></span>
<span data-ttu-id="fc56f-132">**裝置清單**</span><span class="sxs-lookup"><span data-stu-id="fc56f-132">**Devices list**</span></span> | <span data-ttu-id="fc56f-133">顯示架至 Defender for Endpoint 的裝置清單、某些有關這些裝置的相關資訊，以及其曝光和風險層級。</span><span class="sxs-lookup"><span data-stu-id="fc56f-133">Displays the list of devices that are onboarded to Defender for Endpoint, some information about them, and their exposure and risk levels.</span></span>
<span data-ttu-id="fc56f-134">**警示佇列**</span><span class="sxs-lookup"><span data-stu-id="fc56f-134">**Alerts queue**</span></span> | <span data-ttu-id="fc56f-135">從組織中的裝置，查看所產生的警示。</span><span class="sxs-lookup"><span data-stu-id="fc56f-135">View alerts generated from devices in your organizations.</span></span>
<span data-ttu-id="fc56f-136">**自動化調查**</span><span class="sxs-lookup"><span data-stu-id="fc56f-136">**Automated investigations**</span></span> | <span data-ttu-id="fc56f-137">顯示已在網路中執行的自動化調查、觸發警示、每項調查的狀態和其他詳細資料，例如調查開始和調查的期間。</span><span class="sxs-lookup"><span data-stu-id="fc56f-137">Displays automated investigations that have been conducted in the network, triggering alert, the status of each investigation and other details such as when the investigation started and the duration of the investigation.</span></span>
<span data-ttu-id="fc56f-138">**進階搜捕**</span><span class="sxs-lookup"><span data-stu-id="fc56f-138">**Advanced hunting**</span></span> | <span data-ttu-id="fc56f-139">「高級搜尋」可讓您使用強大的搜尋和查詢工具，主動搜尋並調查整個組織。</span><span class="sxs-lookup"><span data-stu-id="fc56f-139">Advanced hunting allows you to proactively hunt and investigate across your organization using a powerful search and query tool.</span></span>
<span data-ttu-id="fc56f-140">**報告**</span><span class="sxs-lookup"><span data-stu-id="fc56f-140">**Reports**</span></span> | <span data-ttu-id="fc56f-141">查看詳細描述威脅防護、裝置健康情況和合規性、web 保護及弱點的圖形。</span><span class="sxs-lookup"><span data-stu-id="fc56f-141">View graphs detailing threat protection, device health and compliance, web protection, and vulnerability.</span></span>
<span data-ttu-id="fc56f-142">**合作夥伴與 API**</span><span class="sxs-lookup"><span data-stu-id="fc56f-142">**Partners & APIs**</span></span> | <span data-ttu-id="fc56f-143">View the 支援的合作夥伴連線，增強平臺的偵測、調查和威脅智慧功能。</span><span class="sxs-lookup"><span data-stu-id="fc56f-143">View supported partner connections, which enhance the detection, investigation, and threat intelligence capabilities of the platform.</span></span> <span data-ttu-id="fc56f-144">您也可以查看已連接的應用程式、API explorer、API 使用方式一覽及資料匯出設定。</span><span class="sxs-lookup"><span data-stu-id="fc56f-144">You can also view connected applications, the API explorer, API usage overview, and data export settings.</span></span>
<span data-ttu-id="fc56f-145">**威脅 & 弱點管理**</span><span class="sxs-lookup"><span data-stu-id="fc56f-145">**Threat & Vulnerability management**</span></span> | <span data-ttu-id="fc56f-146">查看適用于裝置的 Microsoft 安全分數、披露分數、公開的裝置、易受攻擊的軟體，並針對主要安全性建議採取行動。</span><span class="sxs-lookup"><span data-stu-id="fc56f-146">View your Microsoft Secure Score for Devices, exposure score, exposed devices, vulnerable software, and take action on top security recommendations.</span></span>
<span data-ttu-id="fc56f-147">**評估與示教**</span><span class="sxs-lookup"><span data-stu-id="fc56f-147">**Evaluation and tutorials**</span></span> | <span data-ttu-id="fc56f-148">管理測試裝置、攻擊模擬及報告。</span><span class="sxs-lookup"><span data-stu-id="fc56f-148">Manage test devices, attack simulations, and reports.</span></span> <span data-ttu-id="fc56f-149">透過試用環境中的引導式試驗，瞭解並體驗到端點功能。</span><span class="sxs-lookup"><span data-stu-id="fc56f-149">Learn and experience the Defender for Endpoint capabilities through a guided walk-through in a trial environment.</span></span>
<span data-ttu-id="fc56f-150">**服務健康狀況**</span><span class="sxs-lookup"><span data-stu-id="fc56f-150">**Service health**</span></span> | <span data-ttu-id="fc56f-151">提供端點服務之 Defender 的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="fc56f-151">Provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="fc56f-152">您可以驗證服務健康情況是否良好，或是否有目前的問題。</span><span class="sxs-lookup"><span data-stu-id="fc56f-152">You'll be able to verify that the service health is healthy or if there are current issues.</span></span>
<span data-ttu-id="fc56f-153">**設定管理**</span><span class="sxs-lookup"><span data-stu-id="fc56f-153">**Configuration management**</span></span> | <span data-ttu-id="fc56f-154">顯示 boarded 裝置、組織的安全性基準、預測分析、web 保護覆蓋範圍，並可讓您在裝置上執行攻擊面管理。</span><span class="sxs-lookup"><span data-stu-id="fc56f-154">Displays on-boarded devices, your organizations' security baseline, predictive analysis, web protection coverage, and allows you to perform attack surface management on your devices.</span></span>
<span data-ttu-id="fc56f-155">**設定**</span><span class="sxs-lookup"><span data-stu-id="fc56f-155">**Settings**</span></span> | <span data-ttu-id="fc56f-156">顯示您在上架期間選取的設定，並可讓您更新行業偏好設定和保留原則週期。</span><span class="sxs-lookup"><span data-stu-id="fc56f-156">Shows the settings you selected during onboarding and lets you update your industry preferences and retention policy period.</span></span> <span data-ttu-id="fc56f-157">您也可以設定其他設定設定，例如許可權、APIs、規則、裝置管理、IT 服務管理及網路評估。</span><span class="sxs-lookup"><span data-stu-id="fc56f-157">You can also set other configuration settings such as permissions, APIs, rules, device management, IT service management, and network assessments.</span></span>
<span data-ttu-id="fc56f-158">**(2) 搜尋、Community 中心、當地語系化、協助和支援、意見反應**</span><span class="sxs-lookup"><span data-stu-id="fc56f-158">**(2) Search, Community center, Localization,  Help and support, Feedback**</span></span> | <span data-ttu-id="fc56f-159">**搜尋** -搜尋依裝置、檔案、使用者、URL、IP、弱點、軟體及建議。</span><span class="sxs-lookup"><span data-stu-id="fc56f-159">**Search** - search by device, file, user, URL, IP, vulnerability, software, and recommendation.</span></span> </br></br> <span data-ttu-id="fc56f-160">**Community center** -存取 Community 中心，以瞭解、共同作業及分享產品的經驗。</span><span class="sxs-lookup"><span data-stu-id="fc56f-160">**Community center** - Access the Community center to learn, collaborate, and share experiences about the product.</span></span> </br></br>  <span data-ttu-id="fc56f-161">**當地語系化** -設定時區。</span><span class="sxs-lookup"><span data-stu-id="fc56f-161">**Localization** - Set time zones.</span></span> </br></br>  <span data-ttu-id="fc56f-162">說明 **與支援**-存取適用于 Endpoint 的 Defender 指南、Microsoft 和 Microsoft Premier support、授權資訊、模擬 & 教程、Defender for endpoint 評估實驗室，請參閱威脅專家。</span><span class="sxs-lookup"><span data-stu-id="fc56f-162">**Help and support** - Access the Defender for Endpoint guide, Microsoft and Microsoft Premier support, license information, simulations & tutorials, Defender for Endpoint evaluation lab, consult a threat expert.</span></span></br></br> <span data-ttu-id="fc56f-163">**意見** 反應-提供您喜歡的意見或我們可以做什麼。</span><span class="sxs-lookup"><span data-stu-id="fc56f-163">**Feedback** - Provide comments about what you like or what we can do better.</span></span>

> [!NOTE]
> <span data-ttu-id="fc56f-164">針對具有高解析度 DPI 縮放問題的裝置，請參閱[Windows 縮放性問題以取得高 DPI 裝置](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices)，以取得可能的解決方案。</span><span class="sxs-lookup"><span data-stu-id="fc56f-164">For devices with high resolution DPI scaling issues, please see [Windows scaling issues for high-DPI devices](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices) for possible solutions.</span></span>

## <a name="microsoft-defender-for-endpoint-icons"></a><span data-ttu-id="fc56f-165">Microsoft Defender for Endpoint 圖示</span><span class="sxs-lookup"><span data-stu-id="fc56f-165">Microsoft Defender for Endpoint icons</span></span>

<span data-ttu-id="fc56f-166">下表提供整個入口網站上使用之圖示的資訊：</span><span class="sxs-lookup"><span data-stu-id="fc56f-166">The following table provides information on the icons used all throughout the portal:</span></span>

<span data-ttu-id="fc56f-167">圖示</span><span class="sxs-lookup"><span data-stu-id="fc56f-167">Icon</span></span> | <span data-ttu-id="fc56f-168">描述</span><span class="sxs-lookup"><span data-stu-id="fc56f-168">Description</span></span>
:---|:---
![ATP 標誌圖示](images/atp-logo-icon.png)| <span data-ttu-id="fc56f-170">Microsoft Defender for Endpoint 標誌</span><span class="sxs-lookup"><span data-stu-id="fc56f-170">Microsoft Defender for Endpoint logo</span></span>
![警示圖示](images/alert-icon.png)| <span data-ttu-id="fc56f-172">警示–指出與高級攻擊相關的活動。</span><span class="sxs-lookup"><span data-stu-id="fc56f-172">Alert – Indication of an activity correlated with advanced attacks.</span></span>
![偵測圖示](images/detection-icon.png)| <span data-ttu-id="fc56f-174">偵測–指出惡意程式碼威脅偵測。</span><span class="sxs-lookup"><span data-stu-id="fc56f-174">Detection – Indication of a malware threat detection.</span></span>
![作用中威脅圖示](images/active-threat-icon.png)| <span data-ttu-id="fc56f-176">主動威脅–偵測時主動執行的威脅。</span><span class="sxs-lookup"><span data-stu-id="fc56f-176">Active threat – Threats actively executing at the time of detection.</span></span>
![修正 icon1](images/remediated-icon.png)| <span data-ttu-id="fc56f-178">修正–從裝置移除威脅。</span><span class="sxs-lookup"><span data-stu-id="fc56f-178">Remediated – Threat removed from the device.</span></span>
![未修正圖示](images/not-remediated-icon.png)| <span data-ttu-id="fc56f-180">未修正–未從裝置移除威脅。</span><span class="sxs-lookup"><span data-stu-id="fc56f-180">Not remediated – Threat not removed from the device.</span></span>
![Thunderbolt 圖示](images/atp-thunderbolt-icon.png)| <span data-ttu-id="fc56f-182">會指出在 **警示處理樹狀目錄** 中觸發警示的事件。</span><span class="sxs-lookup"><span data-stu-id="fc56f-182">Indicates events that triggered an alert in the **Alert process tree**.</span></span>
![裝置圖示](images/atp-machine-icon.png)| <span data-ttu-id="fc56f-184">裝置圖示</span><span class="sxs-lookup"><span data-stu-id="fc56f-184">Device icon</span></span>
![Microsoft Defender AV 事件圖示](images/atp-windows-defender-av-events-icon.png)| <span data-ttu-id="fc56f-186">Microsoft Defender 防毒軟體事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-186">Microsoft Defender Antivirus events</span></span>
![Application Guard 事件圖示](images/atp-Application-Guard-events-icon.png)| <span data-ttu-id="fc56f-188">Windows Defender 應用程式防護事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-188">Windows Defender Application Guard events</span></span>
![Device Guard 事件圖示](images/atp-Device-Guard-events-icon.png)| <span data-ttu-id="fc56f-190">Windows Defender Device Guard 事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-190">Windows Defender Device Guard events</span></span>
![Exploit Guard 事件圖示](images/atp-Exploit-Guard-events-icon.png)| <span data-ttu-id="fc56f-192">Windows DefenderExploit Guard 事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-192">Windows Defender Exploit Guard events</span></span>
![SmartScreen 事件圖示](images/atp-Smart-Screen-events-icon.png)| <span data-ttu-id="fc56f-194">Windows DefenderSmartScreen 事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-194">Windows Defender SmartScreen events</span></span>
![防火牆事件圖示](images/atp-Firewall-events-icon.png)| <span data-ttu-id="fc56f-196">Windows防火牆事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-196">Windows Firewall events</span></span>
![回應動作圖示](images/atp-respond-action-icon.png)| <span data-ttu-id="fc56f-198">回應動作</span><span class="sxs-lookup"><span data-stu-id="fc56f-198">Response action</span></span>
![處理程式事件圖示](images/atp-process-event-icon.png)| <span data-ttu-id="fc56f-200">處理程式事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-200">Process events</span></span>
![網路通訊事件圖示](images/atp-network-communications-icon.png)| <span data-ttu-id="fc56f-202">網路事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-202">Network events</span></span>
![檔觀測的事件圖示](images/atp-file-observed-icon.png)| <span data-ttu-id="fc56f-204">檔案事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-204">File  events</span></span>
![登錄事件圖示](images/atp-registry-event-icon.png)| <span data-ttu-id="fc56f-206">登錄事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-206">Registry events</span></span>
![模組載入 DLL 事件圖示](images/atp-module-load-icon.png)| <span data-ttu-id="fc56f-208">載入 DLL 事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-208">Load DLL events</span></span>
![其他事件圖示](images/atp-Other-events-icon.png)| <span data-ttu-id="fc56f-210">其他事件</span><span class="sxs-lookup"><span data-stu-id="fc56f-210">Other events</span></span>
![存取權杖修改圖示](images/atp-access-token-modification-icon.png)| <span data-ttu-id="fc56f-212">存取權杖修改</span><span class="sxs-lookup"><span data-stu-id="fc56f-212">Access token modification</span></span>
![檔案建立圖示](images/atp-file-creation-icon.png)| <span data-ttu-id="fc56f-214">檔建立</span><span class="sxs-lookup"><span data-stu-id="fc56f-214">File creation</span></span>
![簽署者圖示](images/atp-signer-icon.png)| <span data-ttu-id="fc56f-216">簽名</span><span class="sxs-lookup"><span data-stu-id="fc56f-216">Signer</span></span>
![檔路徑圖示](images/atp-File-path-icon.png)| <span data-ttu-id="fc56f-218">檔案路徑</span><span class="sxs-lookup"><span data-stu-id="fc56f-218">File path</span></span>
![命令列圖示](images/atp-command-line-icon.png)| <span data-ttu-id="fc56f-220">命令列</span><span class="sxs-lookup"><span data-stu-id="fc56f-220">Command line</span></span>
![未簽署檔圖示](images/atp-unsigned-file-icon.png)| <span data-ttu-id="fc56f-222">未簽署檔</span><span class="sxs-lookup"><span data-stu-id="fc56f-222">Unsigned file</span></span>
![處理樹狀圖示](images/atp-process-tree.png)| <span data-ttu-id="fc56f-224">處理樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="fc56f-224">Process tree</span></span>
![記憶體配置圖示](images/atp-memory-allocation-icon.png)| <span data-ttu-id="fc56f-226">記憶體配置</span><span class="sxs-lookup"><span data-stu-id="fc56f-226">Memory allocation</span></span>
![處理常式注入圖示](images/atp-process-injection.png)| <span data-ttu-id="fc56f-228">處理常式注入</span><span class="sxs-lookup"><span data-stu-id="fc56f-228">Process injection</span></span>
![Powershell 命令執行圖示](images/atp-powershell-command-run-icon.png)| <span data-ttu-id="fc56f-230">Powershell 命令執行</span><span class="sxs-lookup"><span data-stu-id="fc56f-230">Powershell command run</span></span>
![Community 居中圖示](images/atp-community-center.png) | <span data-ttu-id="fc56f-232">Community 中心</span><span class="sxs-lookup"><span data-stu-id="fc56f-232">Community center</span></span>
![通知圖示](images/atp-notifications.png) | <span data-ttu-id="fc56f-234">通知</span><span class="sxs-lookup"><span data-stu-id="fc56f-234">Notifications</span></span>
![找不到威脅](images/no-threats-found.png) | <span data-ttu-id="fc56f-236">自動調查-找不到威脅</span><span class="sxs-lookup"><span data-stu-id="fc56f-236">Automated investigation - no threats found</span></span>
![失敗圖示](images/failed.png) | <span data-ttu-id="fc56f-238">自動調查-失敗</span><span class="sxs-lookup"><span data-stu-id="fc56f-238">Automated investigation - failed</span></span>
![部分修正圖示](images/partially-investigated.png) | <span data-ttu-id="fc56f-240">自動調查-部分調查</span><span class="sxs-lookup"><span data-stu-id="fc56f-240">Automated investigation - partially investigated</span></span>
![由系統終止](images/terminated-by-system.png) | <span data-ttu-id="fc56f-242">自動化調查-由系統終止</span><span class="sxs-lookup"><span data-stu-id="fc56f-242">Automated investigation - terminated by system</span></span>
![擱置圖示](images/pending.png) | <span data-ttu-id="fc56f-244">自動化調查-擱置</span><span class="sxs-lookup"><span data-stu-id="fc56f-244">Automated investigation - pending</span></span>
![正在執行圖示](images/running.png) | <span data-ttu-id="fc56f-246">自動調查-正在執行</span><span class="sxs-lookup"><span data-stu-id="fc56f-246">Automated investigation - running</span></span>
![修正 icon2](images/remediated.png) | <span data-ttu-id="fc56f-248">自動調查-已修正</span><span class="sxs-lookup"><span data-stu-id="fc56f-248">Automated investigation - remediated</span></span>
![部分調查圖示](images/partially_remediated.png) | <span data-ttu-id="fc56f-250">自動調查-部分修正</span><span class="sxs-lookup"><span data-stu-id="fc56f-250">Automated investigation - partially remediated</span></span>
![威脅洞察力圖示](images/tvm_bug_icon.png) | <span data-ttu-id="fc56f-252">威脅 & 弱點管理-威脅洞察力</span><span class="sxs-lookup"><span data-stu-id="fc56f-252">Threat & Vulnerability Management - threat insights</span></span>
![可能的主動警示圖示](images/tvm_alert_icon.png) | <span data-ttu-id="fc56f-254">威脅 & 漏洞管理-可能的主動警示</span><span class="sxs-lookup"><span data-stu-id="fc56f-254">Threat & Vulnerability Management - possible active alert</span></span>
![建議的 insights 圖示](images/tvm_insight_icon.png) | <span data-ttu-id="fc56f-256">威脅 & 弱點管理-建議的洞察力</span><span class="sxs-lookup"><span data-stu-id="fc56f-256">Threat & Vulnerability Management - recommendation insights</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc56f-257">相關主題</span><span class="sxs-lookup"><span data-stu-id="fc56f-257">Related topics</span></span>

- [<span data-ttu-id="fc56f-258">Microsoft Defender 資訊安全中心概觀</span><span class="sxs-lookup"><span data-stu-id="fc56f-258">Overview of Microsoft Defender Security Center</span></span>](use.md)
- [<span data-ttu-id="fc56f-259">View the Security operations 儀表板</span><span class="sxs-lookup"><span data-stu-id="fc56f-259">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="fc56f-260">查看威脅 & 漏洞管理儀表板</span><span class="sxs-lookup"><span data-stu-id="fc56f-260">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="fc56f-261">查看威脅分析儀表板並採取建議的緩解動作</span><span class="sxs-lookup"><span data-stu-id="fc56f-261">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
