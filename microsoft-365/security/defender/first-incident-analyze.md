---
title: 步驟 1： 會審及分析您的第一個事件
description: 如何在 Microsoft 365 Defender 中會審及開始分析第一個事件。
keywords: 事件、警示、調查、關聯性、攻擊、電腦、裝置、使用者、identity、身分識別、信箱、電子郵件、365、microsoft、m365、事件回應、網路攻擊
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 82e1d1b117fd8c68077a249a14f66b9915d517e9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287768"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a><span data-ttu-id="936fc-105">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="936fc-105">Step 1.</span></span> <span data-ttu-id="936fc-106">會審及分析您的第一個事件</span><span class="sxs-lookup"><span data-stu-id="936fc-106">Triage and analyze your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="936fc-107">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="936fc-107">**Applies to:**</span></span>
- <span data-ttu-id="936fc-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="936fc-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="936fc-109">當您花些時間根據組織的標準來建立、實施及維護安全性措施時，您可以設定安全性解決方案，協助您快速識別安全性風險和威脅。</span><span class="sxs-lookup"><span data-stu-id="936fc-109">As you spend some time establishing, implementing, and maintaining security measures according to the organization’s standards, you can set up security solutions to help you quickly identify security risks and threats.</span></span> <span data-ttu-id="936fc-110">Microsoft 365 Defender 可讓您透過單一窗格的玻璃體驗偵測、會審和調查事件，您可以在其中找到您及時決定所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="936fc-110">Microsoft 365 Defender allows you to detect, triage, and investigate incidents through its single-pane-of-glass experience where you can find the information you need to make timely decisions.</span></span>

<span data-ttu-id="936fc-111">偵測到安全性事件後，Microsoft 365 Defender 會顯示對其他事件或事件進行會審或優先順序設定時所需的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="936fc-111">Once a security incident is detected, Microsoft 365 Defender presents details you will need to triage or prioritize an incident or incidents over others.</span></span> <span data-ttu-id="936fc-112">決定優先順序之後，分析員可以著重于調查指派案例的精力。</span><span class="sxs-lookup"><span data-stu-id="936fc-112">After determining prioritization, analysts can then focus their energy on investigating cases assigned to them.</span></span>

## <a name="detection-by-microsoft-365-defender"></a><span data-ttu-id="936fc-113">Microsoft 365 Defender 偵測</span><span class="sxs-lookup"><span data-stu-id="936fc-113">Detection by Microsoft 365 Defender</span></span>

<span data-ttu-id="936fc-114">Microsoft 365 Defender 會從多個 Microsoft 安全性平臺接收警示和事件，作為偵測來源，以建立整體的圖片和惡意活動的內容。</span><span class="sxs-lookup"><span data-stu-id="936fc-114">Microsoft 365 Defender receives alerts and events from multiple Microsoft security platforms as detection sources to create a holistic picture and context of malicious activity.</span></span> <span data-ttu-id="936fc-115">可能的偵測來源如下：</span><span class="sxs-lookup"><span data-stu-id="936fc-115">These are the possible detection sources:</span></span>

- <span data-ttu-id="936fc-116">[Microsoft defender for endpoint](../defender-endpoint/microsoft-defender-endpoint.md)是一個端點偵測和回應方案 (EDR) 使用 microsoft Defender 防毒軟體，以及使用 microsoft Security Graph 的啟用雲端功能的高級威脅防護。</span><span class="sxs-lookup"><span data-stu-id="936fc-116">[Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md) is an endpoint detection and response solution (EDR) that uses Microsoft Defender antivirus as well as cloud-enabled advanced threat protection using Microsoft Security Graph.</span></span> <span data-ttu-id="936fc-117">Defender for Endpoint 是一種整合的平臺，可提供預防性保護、破壞性偵測、自動調查和回應。</span><span class="sxs-lookup"><span data-stu-id="936fc-117">Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="936fc-118">它會保護 cyberthreats 中的端點、偵測高級攻擊和資料違例、自動化安全性事件，以及改善安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="936fc-118">It protects endpoints from cyberthreats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span>
- <span data-ttu-id="936fc-119">[Microsoft Defender For Identity](/defender-for-identity/what-is) 是雲端式的安全性解決方案，可使用內部部署的 Active Directory 網域服務 (AD DS) 信號來識別、偵測和調查組織中的高級威脅、已遭破壞的身分識別，以及惡意的內幕程式列動。</span><span class="sxs-lookup"><span data-stu-id="936fc-119">[Microsoft Defender for Identity](/defender-for-identity/what-is) is a cloud-based security solution that uses your on-premises Active Directory Domain Services (AD DS) signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span>
- <span data-ttu-id="936fc-120">[Microsoft Cloud App Security](/cloud-app-security/)充當您的企業使用者和其使用的雲端資源之間即時經紀人存取的閘道，不論使用者位於何處，不論其使用的裝置為何。</span><span class="sxs-lookup"><span data-stu-id="936fc-120">[Microsoft Cloud App Security](/cloud-app-security/) acts as a gatekeeper to broker access in real time between your enterprise users and the cloud resources they use, wherever your users are located and regardless of the device they are using.</span></span>
- <span data-ttu-id="936fc-121">[Microsoft Defender for Office 365](../office-365-security/overview.md)會防範電子郵件訊息、連結 (URLs) 及共同作業工具的惡意威脅，以保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="936fc-121">[Microsoft Defender for Office 365](../office-365-security/overview.md) safeguards your organization against malicious threats in email messages, links (URLs), and collaboration tools.</span></span>
- <span data-ttu-id="936fc-122">[Azure 安全性中心](/azure/security-center/security-center-introduction) 是一種整合的基礎結構安全性管理系統，可增強資料中心的安全性狀況，並在雲端和內部部署中，為您的混合工作負載提供高級威脅防護。</span><span class="sxs-lookup"><span data-stu-id="936fc-122">[Azure Security Center](/azure/security-center/security-center-introduction) is a unified infrastructure security management system that strengthens the security posture of your data centers and provides advanced threat protection across your hybrid workloads in the cloud as well as on premises.</span></span>

<span data-ttu-id="936fc-123">在 Microsoft 365 Defender 中，會透過關聯來自這些不同偵測來源的警示來識別[事件](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="936fc-123">In Microsoft 365 Defender, [incidents](incidents-overview.md) are identified by correlating alerts from these different detection sources.</span></span> <span data-ttu-id="936fc-124">您可以從 Microsoft 365 Defender 立即開始，從事件佇列開始，而不是將資源放在一起，也不會將多個警示 stringing 在各自的事件中。</span><span class="sxs-lookup"><span data-stu-id="936fc-124">Instead of spending resources stringing together or distinguishing multiple alerts into their respective incidents, you can start with the incident queue in Microsoft 365 Defender right away.</span></span> <span data-ttu-id="936fc-125">這可讓您以有效的方式透過端點、身分識別、電子郵件和應用程式來會審事件，並減少攻擊的損毀。</span><span class="sxs-lookup"><span data-stu-id="936fc-125">This allows you to triage incidents in an efficient manner across endpoints, identities, email, and applications, and reduce the damage from an attack.</span></span>

## <a name="triage-your-incidents"></a><span data-ttu-id="936fc-126">會審您的事件</span><span class="sxs-lookup"><span data-stu-id="936fc-126">Triage your incidents</span></span>

<span data-ttu-id="936fc-127">當您使用組織的優先順序建議方法來會審事件清單之後，Microsoft 365 Defender 中的事件回應便會啟動。</span><span class="sxs-lookup"><span data-stu-id="936fc-127">Incident response in Microsoft 365 Defender starts once you triage the list of incidents using your organization’s recommended method of prioritization.</span></span> <span data-ttu-id="936fc-128">「會審」表示將重要性或緊急程度指派給事件，進而決定調查的順序。</span><span class="sxs-lookup"><span data-stu-id="936fc-128">To triage means to assign a level of importance or urgency to incidents, which then determines the order in which they will be investigated.</span></span>

<span data-ttu-id="936fc-129">在 Microsoft 365 Defender 中決定排定哪個事件優先順序的有用範例，可透過下列公式加以摘要：*嚴重性 + 影響 = 優先順序*。</span><span class="sxs-lookup"><span data-stu-id="936fc-129">A useful sample guide for determining which incident to prioritize in Microsoft 365 Defender can be summarized by the formula: *Severity + Impact = Priority*.</span></span>

- <span data-ttu-id="936fc-130">「**嚴重性**」是由 Microsoft 365 Defender 和其整合安全性元件所指定的層級。</span><span class="sxs-lookup"><span data-stu-id="936fc-130">**Severity** is the level designated by Microsoft 365 Defender and its integrated security components.</span></span>
- <span data-ttu-id="936fc-131">**影響** 是由組織所決定，但不限於受到影響的使用者、裝置、受影響的使用者、裝置、服務 (的閾值數目，甚至是) 的組合，甚至是警示類型。</span><span class="sxs-lookup"><span data-stu-id="936fc-131">**Impact** is determined by the organization and generally includes, but not limited to, a threshold number of impacted users, devices, services affected (or a combination thereof), and even alert type.</span></span>

<span data-ttu-id="936fc-132">分析員接著會根據組織設定的 **優先順序** 準則來發起調查。</span><span class="sxs-lookup"><span data-stu-id="936fc-132">Analysts then initiate investigations based on the **Priority** criteria set by the organization.</span></span>

<span data-ttu-id="936fc-133">事件優先順序可能會因組織而異。</span><span class="sxs-lookup"><span data-stu-id="936fc-133">Incident prioritization might vary depending on the organization.</span></span> <span data-ttu-id="936fc-134">NIST 建議同時考慮事件的功能和資訊影響，以及可復原性。</span><span class="sxs-lookup"><span data-stu-id="936fc-134">NIST recommends also considering the functional and informational impact of the incident, and recoverability.</span></span>

<span data-ttu-id="936fc-135">以下只是一種會審方式：</span><span class="sxs-lookup"><span data-stu-id="936fc-135">The following is just one approach to triage:</span></span>

1. <span data-ttu-id="936fc-136">移至 [ [事件](incidents-overview.md) ] 頁面以啟動會審。</span><span class="sxs-lookup"><span data-stu-id="936fc-136">Go to the [incidents](incidents-overview.md) page to initiate triage.</span></span> <span data-ttu-id="936fc-137">您可以在這裡看到影響組織的事件清單。</span><span class="sxs-lookup"><span data-stu-id="936fc-137">Here you can see a list of incidents affecting your organization.</span></span> <span data-ttu-id="936fc-138">依預設，會從最新的事件排列到最舊的事件。</span><span class="sxs-lookup"><span data-stu-id="936fc-138">By default, they are arranged from the most recent to the oldest incident.</span></span> <span data-ttu-id="936fc-139">您也可以在這裡看到每個事件的不同欄，顯示其嚴重性、類別、作用中的警示數目，以及受影響的實體等其他。</span><span class="sxs-lookup"><span data-stu-id="936fc-139">From here, you can also see different columns for each incident showing their severity, category, number of active alerts, and impacted entities, among others.</span></span> <span data-ttu-id="936fc-140">您可以自訂一組欄，並依據某些欄來排序事件佇列，方法是選取欄名稱。</span><span class="sxs-lookup"><span data-stu-id="936fc-140">You can customize the set of columns and sort the incident queue by some these columns by selecting the column name.</span></span> <span data-ttu-id="936fc-141">您也可以根據需要來篩選事件佇列。</span><span class="sxs-lookup"><span data-stu-id="936fc-141">You can also filter the incident queue according to your needs.</span></span> <span data-ttu-id="936fc-142">如需可用篩選的完整清單，請參閱設定 [事件優先順序](incident-queue.md#available-filters)。</span><span class="sxs-lookup"><span data-stu-id="936fc-142">For a full list of available filters, see [Prioritize incidents](incident-queue.md#available-filters).</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="事件佇列的範例":::

    <span data-ttu-id="936fc-144">如何對此項事件集執行會審的一個範例是針對受影響更多使用者和裝置的事件設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="936fc-144">One example of how you might perform triage for this set of incidents is to prioritize incidents that affected more users and devices.</span></span> <span data-ttu-id="936fc-145">在此範例中，您可能會設定事件識別碼6769的優先順序，因為它會影響最大數目的實體：7裝置、6個使用者和2個信箱。</span><span class="sxs-lookup"><span data-stu-id="936fc-145">In this example, you might prioritize incident ID 6769 because it affected the largest number of entities: 7 devices, 6 users, and 2 mailboxes.</span></span> <span data-ttu-id="936fc-146">此外，此事件似乎包含 Microsoft Defender 的警示，表示身分識別的警示及可能的認證盜竊。</span><span class="sxs-lookup"><span data-stu-id="936fc-146">Furthermore, the incident appears to contain alerts from Microsoft Defender for Identity which indicate an identity-based alert and possible credential theft.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="高影響事件的範例":::

2. <span data-ttu-id="936fc-148">選取 [事件名稱] 旁邊的圓形，以查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="936fc-148">Select the circle next to the incident name to review the details.</span></span> <span data-ttu-id="936fc-149">側邊窗格會出現在右側，其中包含可協助您深入瞭解的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="936fc-149">A side pane will appear on the right side, which contains additional information that can assist your triage further.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="事件側邊窗格的範例":::

   <span data-ttu-id="936fc-151">例如，透過查看哪個 [MITRE ATT&CK](https://attack.mitre.org/) 策略，攻擊者根據事件的類別所使用的策略，您可能會將此事件的優先順序，因為攻擊者使用的是盜竊的認證、已建立的命令和控制、已執行橫向移動，以及挾帶部分資料。</span><span class="sxs-lookup"><span data-stu-id="936fc-151">For example, by looking at which [MITRE ATT&CK](https://attack.mitre.org/) tactics the attacker used based on the incident’s categories, you might prioritize this incident because the attacker used stolen credentials, established command and control, performed lateral movement, and exfiltrated some data.</span></span> <span data-ttu-id="936fc-152">這表示攻擊者已深入瞭解網路，可能會竊取機密資訊。</span><span class="sxs-lookup"><span data-stu-id="936fc-152">This suggests the attacker has already gone deep into the network and possibly stolen confidential information.</span></span>

   <span data-ttu-id="936fc-153">此外，如果您的組織已執行零信任架構，您可以將認證存取視為重要的安全性違規（必要優先）。</span><span class="sxs-lookup"><span data-stu-id="936fc-153">Additionally, if your organization has implemented the Zero Trust framework, you would consider credential access as an important security violation worth prioritizing.</span></span>

   <span data-ttu-id="936fc-154">向下滾動側邊窗格，您會看到特定的受影響實體，例如使用者、裝置和信箱。</span><span class="sxs-lookup"><span data-stu-id="936fc-154">Scrolling down the side pane, you will see the specific impacted entities such as users, devices, and mailboxes.</span></span> <span data-ttu-id="936fc-155">您可以檢查每個裝置的公開層級，以及受影響信箱的擁有者。</span><span class="sxs-lookup"><span data-stu-id="936fc-155">You can check the exposure level of each device and the owners of affected mailboxes.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="事件側窗格詳細資料的範例":::

3. <span data-ttu-id="936fc-157">在側邊窗格的右下方，您可以找到相關聯的警示。</span><span class="sxs-lookup"><span data-stu-id="936fc-157">Further down the side pane, you can find the associated alerts.</span></span> <span data-ttu-id="936fc-158">Microsoft 365 Defender 已將所述警示的關聯性加入單一事件，可節約您的時間和資源，以改善對攻擊的修正。</span><span class="sxs-lookup"><span data-stu-id="936fc-158">Microsoft 365 Defender has already performed the correlation of said alerts into a single incident, saving you time and resources better spent remediating the attack.</span></span> <span data-ttu-id="936fc-159">提醒是可疑的，因此可能會導致惡意的系統事件，以建議網路上的攻擊者是否存在。</span><span class="sxs-lookup"><span data-stu-id="936fc-159">Alerts are suspicious and therefore possibly malicious system events that suggest the presence of an attacker on a network.</span></span>

   <span data-ttu-id="936fc-160">在此範例中，87個別警示已確定為一個安全性事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="936fc-160">In this example, 87 individual alerts were determined to be part of one security incident.</span></span> <span data-ttu-id="936fc-161">您可以查看所有提醒，快速瞭解攻擊的播放方式。</span><span class="sxs-lookup"><span data-stu-id="936fc-161">You can view all the alerts to get a quick view of how the attack played out.</span></span>

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="事件側邊窗格中的警示範例":::

## <a name="analyze-your-first-incident"></a><span data-ttu-id="936fc-163">分析第一個事件</span><span class="sxs-lookup"><span data-stu-id="936fc-163">Analyze your first incident</span></span>

<span data-ttu-id="936fc-164">瞭解警報周圍的內容同樣重要。</span><span class="sxs-lookup"><span data-stu-id="936fc-164">Understanding the context surrounding alerts is equally important.</span></span> <span data-ttu-id="936fc-165">預警通常並非單一獨立事件。</span><span class="sxs-lookup"><span data-stu-id="936fc-165">Often an alert is not a single independent event.</span></span> <span data-ttu-id="936fc-166">已建立的進程鏈、命令和動作可能不會同時發生。</span><span class="sxs-lookup"><span data-stu-id="936fc-166">There is a chain of processes created, commands, and actions that might not have occurred at the same time.</span></span> <span data-ttu-id="936fc-167">因此，分析員必須尋找裝置時程表中的可疑實體的第一及最後一個活動，以瞭解警示的內容。</span><span class="sxs-lookup"><span data-stu-id="936fc-167">Therefore, an analyst must look for the first and last activities of the suspicious entity in device timelines to understand the context of the alerts.</span></span>

<span data-ttu-id="936fc-168">有多種方式可使用 Microsoft 365 Defender 讀取及分析資料，但分析師的最後目標是儘快回應事件。</span><span class="sxs-lookup"><span data-stu-id="936fc-168">There are multiple ways to read and analyze data using Microsoft 365 Defender but the end goal for analysts is to respond to incidents as quickly as possible.</span></span> <span data-ttu-id="936fc-169">雖然 Microsoft 365 Defender 可以大幅減少[平均時間以修正 (MTTR) ](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/)透過業界領先的[自動化調查和回應](m365d-autoir.md)功能，但總會需要手動分析的情況。</span><span class="sxs-lookup"><span data-stu-id="936fc-169">While Microsoft 365 Defender can significantly reduce [Mean Time to Remediate (MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) through the industry-leading [automated investigation and response](m365d-autoir.md) feature, there are always cases that require manual analysis.</span></span>

<span data-ttu-id="936fc-170">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="936fc-170">Here's an example:</span></span>

1. <span data-ttu-id="936fc-171">決定會審優先順序之後，分析員會透過選取事件名稱來開始深入分析。</span><span class="sxs-lookup"><span data-stu-id="936fc-171">Once triage priority has been determined, an analyst begins an in-depth analysis by selecting the incident name.</span></span> <span data-ttu-id="936fc-172">此頁面會顯示 **事件摘要** ，其中的資料會顯示在索引標籤中，以協助進行分析。</span><span class="sxs-lookup"><span data-stu-id="936fc-172">This page brings up the **Incident Summary** where data is displayed in tabs to assist with the analysis.</span></span> <span data-ttu-id="936fc-173">在 [ **警示** ] 索引標籤下會顯示警示類型。</span><span class="sxs-lookup"><span data-stu-id="936fc-173">Under the **Alerts** tab the type of alerts are displayed.</span></span> <span data-ttu-id="936fc-174">分析員可依序按一下每個警示，以深入查看個別的偵測來源。</span><span class="sxs-lookup"><span data-stu-id="936fc-174">Analysts can click on each alert to drill down into the respective detection source.</span></span>

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="事件 [摘要] 索引標籤的範例":::

    <span data-ttu-id="936fc-176">如需每個偵測來源涵蓋哪個網域的快速指南，請參閱本文的 [偵測一節](#detection-by-microsoft-365-defender) 。</span><span class="sxs-lookup"><span data-stu-id="936fc-176">For a quick guide about which domain each detection source covers, review the [Detect](#detection-by-microsoft-365-defender) section of this article.</span></span>

2. <span data-ttu-id="936fc-177">在 [ **警示** ] 索引標籤上，分析員可以從偵測至偵測來源，以進行更深入的調查和分析。</span><span class="sxs-lookup"><span data-stu-id="936fc-177">From the **Alerts** tab, an analyst can pivot to the detection source to conduct a more in-depth investigation and analysis.</span></span> <span data-ttu-id="936fc-178">例如，使用 Microsoft Cloud App Security 作為偵測來源來選取惡意程式碼偵測時，會將分析員視為對應的警示頁面。</span><span class="sxs-lookup"><span data-stu-id="936fc-178">For example, selecting Malware Detection with Microsoft Cloud App Security as the detection source takes the analyst to its corresponding alert page.</span></span>

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="選取事件警示的範例":::

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Microsoft Cloud App Security 中對應頁面的範例":::

3. <span data-ttu-id="936fc-181">若要進一步調查我們的範例，請滾動至頁面底部，以查看 **受影響的使用者**。</span><span class="sxs-lookup"><span data-stu-id="936fc-181">To investigate our example further, scrolling to the bottom of the page to view the **Users affected**.</span></span> <span data-ttu-id="936fc-182">若要查看惡意程式碼偵測的活動和內容，請選取 [Annette 峰的使用者] 頁面。</span><span class="sxs-lookup"><span data-stu-id="936fc-182">To see the activity and context surrounding the malware detection, select Annette Hill’s user page .</span></span>

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="使用者頁面的範例":::

4. <span data-ttu-id="936fc-184">在 [使用者] 頁面上，是以時間為基礎的事件清單，以 *來自 TOR 網路 IP 位址* 警示的危險登入。</span><span class="sxs-lookup"><span data-stu-id="936fc-184">On the user page is a chronological list of events starting with a *Risky Sign-in from a TOR network IP Address* alert.</span></span> <span data-ttu-id="936fc-185">當活動的 suspiciousness 取決於組織執行其業務的方式性質時，在大多數情況下，使用洋蔥路由器 (TOR) ，在企業環境中，允許使用者以匿名方式流覽網頁的網路，可能會被視為一般線上作業的極不可能且不必要的。</span><span class="sxs-lookup"><span data-stu-id="936fc-185">While the suspiciousness of an activity depends on the nature of how an organization conducts its business, in most cases the use of The Onion Router (TOR), a network that allows users to browse the web anonymously, in an enterprise environment might be considered highly unlikely and unnecessary for regular online operations.</span></span>

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="使用者事件清單的時間順序範例":::

5. <span data-ttu-id="936fc-187">您可以選取每個警示，以取得有關活動的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="936fc-187">Each alert can be selected to obtain more information on the activity.</span></span> <span data-ttu-id="936fc-188">例如， **從 TOR IP 位址警示中** 選取 [活動]，會將您帶到該警示本身的頁面。</span><span class="sxs-lookup"><span data-stu-id="936fc-188">For example, selecting **Activity from a Tor IP Address** alert leads you to that alert’s own page.</span></span> <span data-ttu-id="936fc-189">Annette 是 Office 365 的管理員，這表示她具有較高的許可權，來源事件可能會導致存取機密資訊。</span><span class="sxs-lookup"><span data-stu-id="936fc-189">Annette is an Administrator of Office 365, which means she has elevated privileges and the source incident might have led to access to confidential information.</span></span>

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Microsoft Cloud App Security 的警示詳細資料範例":::

6. <span data-ttu-id="936fc-191">透過選取其他警示，分析員便可取得攻擊的完整畫面。</span><span class="sxs-lookup"><span data-stu-id="936fc-191">By selecting other alerts, an analyst can get a complete picture of the attack.</span></span>

## <a name="next-step"></a><span data-ttu-id="936fc-192">下一步</span><span class="sxs-lookup"><span data-stu-id="936fc-192">Next step</span></span>

<span data-ttu-id="936fc-193">[![步驟2：瞭解如何修正事件](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)</span><span class="sxs-lookup"><span data-stu-id="936fc-193">[![Step 2: Learn how to remediate incidents](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)</span></span>

<span data-ttu-id="936fc-194">瞭解如何 [修正事件](first-incident-remediate.md)。</span><span class="sxs-lookup"><span data-stu-id="936fc-194">Learn how to [remediate incidents](first-incident-remediate.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="936fc-195">另請參閱</span><span class="sxs-lookup"><span data-stu-id="936fc-195">See also</span></span>

- [<span data-ttu-id="936fc-196">事件概觀</span><span class="sxs-lookup"><span data-stu-id="936fc-196">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="936fc-197">調查事件</span><span class="sxs-lookup"><span data-stu-id="936fc-197">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="936fc-198">管理事件</span><span class="sxs-lookup"><span data-stu-id="936fc-198">Manage incidents</span></span>](manage-incidents.md)
