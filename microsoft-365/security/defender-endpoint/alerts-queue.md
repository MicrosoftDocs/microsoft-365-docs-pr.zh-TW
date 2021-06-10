---
title: 查看和組織 Microsoft Defender for Endpoint 警示佇列
description: 瞭解 Microsoft Defender for Endpoint 警示佇列的運作方式，以及如何排序和篩選警示清單。
keywords: 警示，佇列，警示佇列，排序，順序，篩選，管理提醒，新增，進行中，已解決、最近、佇列中的時間、嚴重性、時間週期、microsoft 威脅專家警示
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
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 48a3ff8dba5bccd62d7d43b295c136a814056a15
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934330"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a><span data-ttu-id="d0a4f-104">查看和組織 Microsoft Defender for Endpoint 警示佇列</span><span class="sxs-lookup"><span data-stu-id="d0a4f-104">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d0a4f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d0a4f-105">**Applies to:**</span></span>
- [<span data-ttu-id="d0a4f-106">端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="d0a4f-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="d0a4f-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d0a4f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d0a4f-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-alertsq-abovefoldlink) 

<span data-ttu-id="d0a4f-109">**警示佇列** 顯示從您網路中的裝置標記的警示清單。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-109">The **Alerts queue** shows a list of alerts that were flagged from devices in your network.</span></span> <span data-ttu-id="d0a4f-110">依預設，佇列會顯示過去30天的分組視圖中看到的警示。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-110">By default, the queue displays alerts seen in the last 30 days in a grouped view.</span></span> <span data-ttu-id="d0a4f-111">最新的提醒會顯示在清單的頂端，可協助您先看到最近的警示。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-111">The most recent alerts are showed at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="d0a4f-112">透過自動化調查和修正功能大幅減少警示佇列，讓安全性作業專家能夠將重點放在更複雜的威脅及其他高價值計畫上。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-112">The alerts queue is significantly reduced with automated investigation and remediation, allowing security operations experts to focus on more sophisticated threats and other high value initiatives.</span></span> <span data-ttu-id="d0a4f-113">當警示包含自動調查的支援實體時 (例如，在具有支援之作業系統之裝置中的檔案) ，便可以開始進行自動調查和修正。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-113">When an alert contains a supported entity for automated investigation (for example, a file) in a device that has a supported operating system for it, an automated investigation and remediation can start.</span></span> <span data-ttu-id="d0a4f-114">如需自動調查的詳細資訊，請參閱 [自動化調查的概述](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-114">For more information on automated investigations, see [Overview of Automated investigations](automated-investigations.md).</span></span>

<span data-ttu-id="d0a4f-115">您可以選擇從多個選項自訂 [提醒] 佇列視圖。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-115">There are several options you can choose from to customize the alerts queue view.</span></span> 

<span data-ttu-id="d0a4f-116">您可以在上方導覽上進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="d0a4f-116">On the top navigation you can:</span></span>

- <span data-ttu-id="d0a4f-117">選取分組的 view 或 list view</span><span class="sxs-lookup"><span data-stu-id="d0a4f-117">Select grouped view or list view</span></span>
- <span data-ttu-id="d0a4f-118">自訂欄以新增或移除欄</span><span class="sxs-lookup"><span data-stu-id="d0a4f-118">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="d0a4f-119">選取每頁顯示的專案</span><span class="sxs-lookup"><span data-stu-id="d0a4f-119">Select the items to show per page</span></span>
- <span data-ttu-id="d0a4f-120">在頁面間流覽</span><span class="sxs-lookup"><span data-stu-id="d0a4f-120">Navigate between pages</span></span>
- <span data-ttu-id="d0a4f-121">套用篩選</span><span class="sxs-lookup"><span data-stu-id="d0a4f-121">Apply filters</span></span>

![警示佇列的影像](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a><span data-ttu-id="d0a4f-123">排序、篩選和群組警示佇列</span><span class="sxs-lookup"><span data-stu-id="d0a4f-123">Sort, filter, and group the alerts queue</span></span>

<span data-ttu-id="d0a4f-124">您可以套用下列篩選器來限制警示清單，並取得更具焦點的查看警示。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-124">You can apply the following filters to limit the list of alerts and get a more focused view the alerts.</span></span>

### <a name="severity"></a><span data-ttu-id="d0a4f-125">嚴重性</span><span class="sxs-lookup"><span data-stu-id="d0a4f-125">Severity</span></span>

<span data-ttu-id="d0a4f-126">警示嚴重性</span><span class="sxs-lookup"><span data-stu-id="d0a4f-126">Alert severity</span></span> | <span data-ttu-id="d0a4f-127">描述</span><span class="sxs-lookup"><span data-stu-id="d0a4f-127">Description</span></span>
:---|:---
<span data-ttu-id="d0a4f-128">高</span><span class="sxs-lookup"><span data-stu-id="d0a4f-128">High</span></span> </br><span data-ttu-id="d0a4f-129"> (Red) </span><span class="sxs-lookup"><span data-stu-id="d0a4f-129">(Red)</span></span> | <span data-ttu-id="d0a4f-130">與高級持續性威脅 (APT) 相關聯的警示。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-130">Alerts commonly seen associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="d0a4f-131">這些警示指出高風險，因為它們可能會對裝置造成損毀。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-131">These alerts indicate a high risk because of  the severity of damage they can inflict on devices.</span></span> <span data-ttu-id="d0a4f-132">一些範例包括：認證盜竊工具活動、未與任何群組相關聯的勒索軟體活動、篡改安全性感應器，或任何惡意活動表示的人體敵人。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-132">Some examples are: credential theft tools activities, ransomware activities not associated with any group, tampering with security sensors, or any malicious activities indicative of a human adversary.</span></span>
<span data-ttu-id="d0a4f-133">中</span><span class="sxs-lookup"><span data-stu-id="d0a4f-133">Medium</span></span> </br><span data-ttu-id="d0a4f-134"> (橙色) </span><span class="sxs-lookup"><span data-stu-id="d0a4f-134">(Orange)</span></span> | <span data-ttu-id="d0a4f-135">Endpoint 偵測的警示，以及可能是「高級持續性」威脅 (APT) 部分的入侵後行為。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-135">Alerts from endpoint detection and response post-breach behaviors that might be a part of an advanced persistent threat (APT).</span></span> <span data-ttu-id="d0a4f-136">這包括常見的攻擊階段、反常登錄變更、可疑檔案執行等的觀察行為。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-136">This includes observed behaviors typical of attack stages, anomalous registry change, execution of suspicious files, and so forth.</span></span> <span data-ttu-id="d0a4f-137">雖然有些可能是內部安全性測試的一部分，但它需要進行調查，因為它也可能是高級攻擊的一部分。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-137">Although some might be part of internal security testing, it requires investigation as it might also be a part of an advanced attack.</span></span>
<span data-ttu-id="d0a4f-138">低</span><span class="sxs-lookup"><span data-stu-id="d0a4f-138">Low</span></span> </br><span data-ttu-id="d0a4f-139"> (黃色) </span><span class="sxs-lookup"><span data-stu-id="d0a4f-139">(Yellow)</span></span> | <span data-ttu-id="d0a4f-140">與流行惡意程式碼相關聯的威脅警示。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-140">Alerts on threats associated with prevalent malware.</span></span> <span data-ttu-id="d0a4f-141">例如，駭客的非惡意程式碼駭客工具（例如執行探索命令、清除記錄等）通常不表示組織的高級威脅。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-141">For example, hack-tools, non-malware hack tools, such as running exploration commands, clearing logs, etc., that often do not indicate an advanced threat targeting the organization.</span></span> <span data-ttu-id="d0a4f-142">它也可以來自組織中的使用者所進行的隔離安全性工具測試。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-142">It could also come from an isolated security tool testing by a user in your organization.</span></span>
<span data-ttu-id="d0a4f-143">參考</span><span class="sxs-lookup"><span data-stu-id="d0a4f-143">Informational</span></span> </br><span data-ttu-id="d0a4f-144"> (灰色) </span><span class="sxs-lookup"><span data-stu-id="d0a4f-144">(Grey)</span></span> | <span data-ttu-id="d0a4f-145">可能不會被視為對網路有害，但可促進組織對潛在安全性問題的安全性意識的警示。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-145">Alerts that might not be considered harmful to the network but can drive organizational security awareness on potential security issues.</span></span>

#### <a name="understanding-alert-severity"></a><span data-ttu-id="d0a4f-146">瞭解警示嚴重性</span><span class="sxs-lookup"><span data-stu-id="d0a4f-146">Understanding alert severity</span></span>

<span data-ttu-id="d0a4f-147">Microsoft Defender 防毒軟體 (Microsoft Defender AV) 和 Defender for Endpoint alert 嚴重性不同，因為它們代表不同的範圍。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-147">Microsoft Defender Antivirus (Microsoft Defender AV) and Defender for Endpoint alert severities are different because they represent different scopes.</span></span>

<span data-ttu-id="d0a4f-148">Microsoft Defender AV 威脅嚴重性代表偵測到之威脅 (惡意程式碼) 中的絕對嚴重性，並根據個別裝置可能的潛在風險（如果受到感染）進行指派。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-148">The Microsoft Defender AV threat severity represents the absolute severity of the detected threat (malware), and is assigned based on the potential risk to the individual device, if infected.</span></span>

<span data-ttu-id="d0a4f-149">Defender for Endpoint alert 嚴重性代表偵測到的行為嚴重性、實際的裝置風險，但很重要的是組織的潛在風險。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-149">The Defender for Endpoint alert severity represents the severity of the detected behavior, the actual risk to the device but more importantly the potential risk to the organization.</span></span>

<span data-ttu-id="d0a4f-150">因此，例如：</span><span class="sxs-lookup"><span data-stu-id="d0a4f-150">So, for example:</span></span>

- <span data-ttu-id="d0a4f-151">有關 Microsoft Defender AV 的 Defender for Endpoint 警示的嚴重性偵測到已完全避免但未感染裝置的威脅已分類為「資訊」，因為沒有實際的損毀。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-151">The severity of a Defender for Endpoint alert about a Microsoft Defender AV detected threat that was completely prevented and did not infect the device is categorized as "Informational" because there was no actual damage.</span></span>
- <span data-ttu-id="d0a4f-152">執行時偵測到商業惡意程式碼的警示，但由於 Microsoft Defender AV 封鎖並修正，所以歸類為「低」，因為這可能會造成個別裝置的某些損毀，但不會造成任何組織威脅。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-152">An alert about a commercial malware was detected while executing, but blocked and remediated by Microsoft Defender AV, is categorized as  "Low" because it may have caused some damage to the individual device but poses no organizational threat.</span></span>
- <span data-ttu-id="d0a4f-153">執行時偵測到惡意程式碼的警示，其可能不僅會對個別裝置造成威脅，也不論是否最後封鎖，都可能會排名為「中」或「高」。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-153">An alert about malware detected while executing which can pose a threat not only to the individual device but to the organization, regardless if it was eventually blocked, may be ranked as "Medium" or "High".</span></span>
- <span data-ttu-id="d0a4f-154">未封鎖或修正的可疑行為警示，將會排名「低」、「中」或「高」，遵循相同的組織威脅考慮。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-154">Suspicious behavioral alerts, which weren't blocked or remediated will be ranked "Low", "Medium" or "High" following the same organizational threat considerations.</span></span>

#### <a name="understanding-alert-categories"></a><span data-ttu-id="d0a4f-155">瞭解警示類別</span><span class="sxs-lookup"><span data-stu-id="d0a4f-155">Understanding alert categories</span></span>

<span data-ttu-id="d0a4f-156">我們已重新定義警示類別，使其符合[MITRE ATT&CK matrix](https://attack.mitre.org/)中的[企業攻擊戰術](https://attack.mitre.org/tactics/enterprise/)。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-156">We've redefined the alert categories to align to the [enterprise attack tactics](https://attack.mitre.org/tactics/enterprise/) in the [MITRE ATT&CK matrix](https://attack.mitre.org/).</span></span> <span data-ttu-id="d0a4f-157">新的類別名稱會套用至所有新的警示。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-157">New category names apply to all new alerts.</span></span> <span data-ttu-id="d0a4f-158">現有的提醒會保留先前的類別名稱。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-158">Existing alerts will keep the previous category names.</span></span>

<span data-ttu-id="d0a4f-159">下表列出目前的類別，以及它們通常對應至先前類別的方式。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-159">The table below lists the current categories and how they generally map to previous categories.</span></span> 

| <span data-ttu-id="d0a4f-160">新增類別</span><span class="sxs-lookup"><span data-stu-id="d0a4f-160">New   category</span></span>       | <span data-ttu-id="d0a4f-161">API 類別名稱</span><span class="sxs-lookup"><span data-stu-id="d0a4f-161">API category name</span></span>   | <span data-ttu-id="d0a4f-162">偵測到的威脅活動或元件</span><span class="sxs-lookup"><span data-stu-id="d0a4f-162">Detected threat activity or   component</span></span>                                                                                                 |
|----------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d0a4f-163">集合</span><span class="sxs-lookup"><span data-stu-id="d0a4f-163">Collection</span></span>           | <span data-ttu-id="d0a4f-164">集合</span><span class="sxs-lookup"><span data-stu-id="d0a4f-164">Collection</span></span>          | <span data-ttu-id="d0a4f-165">尋找及收集 exfiltration 的資料</span><span class="sxs-lookup"><span data-stu-id="d0a4f-165">Locating   and collecting data for exfiltration</span></span>                                                                                         |
| <span data-ttu-id="d0a4f-166">命令和控制項</span><span class="sxs-lookup"><span data-stu-id="d0a4f-166">Command and control</span></span>  | <span data-ttu-id="d0a4f-167">CommandAndControl</span><span class="sxs-lookup"><span data-stu-id="d0a4f-167">CommandAndControl</span></span>   | <span data-ttu-id="d0a4f-168">連接攻擊者控制的網路基礎結構以轉送資料或接收命令</span><span class="sxs-lookup"><span data-stu-id="d0a4f-168">Connecting   to attacker-controlled network infrastructure to relay data or receive   commands</span></span>                                          |
| <span data-ttu-id="d0a4f-169">認證存取</span><span class="sxs-lookup"><span data-stu-id="d0a4f-169">Credential access</span></span>    | <span data-ttu-id="d0a4f-170">CredentialAccess</span><span class="sxs-lookup"><span data-stu-id="d0a4f-170">CredentialAccess</span></span>    | <span data-ttu-id="d0a4f-171">取得有效的認證，以在網路中擴充裝置和其他資源的控制權</span><span class="sxs-lookup"><span data-stu-id="d0a4f-171">Obtaining   valid credentials to extend control over devices and other resources in the   network</span></span>                                       |
| <span data-ttu-id="d0a4f-172">國防規避</span><span class="sxs-lookup"><span data-stu-id="d0a4f-172">Defense evasion</span></span>      | <span data-ttu-id="d0a4f-173">DefenseEvasion</span><span class="sxs-lookup"><span data-stu-id="d0a4f-173">DefenseEvasion</span></span>      | <span data-ttu-id="d0a4f-174">避免安全性控制，例如，關閉安全性應用程式、刪除 implants，以及執行 rootkit</span><span class="sxs-lookup"><span data-stu-id="d0a4f-174">Avoiding security controls by, for example, turning off   security apps, deleting implants, and running rootkits</span></span>                        |
| <span data-ttu-id="d0a4f-175">發現</span><span class="sxs-lookup"><span data-stu-id="d0a4f-175">Discovery</span></span>            | <span data-ttu-id="d0a4f-176">發現</span><span class="sxs-lookup"><span data-stu-id="d0a4f-176">Discovery</span></span>           | <span data-ttu-id="d0a4f-177">收集重要裝置和資源的相關資訊，例如系統管理員電腦、網域控制站及檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="d0a4f-177">Gathering   information about important devices and resources, such as administrator   computers, domain controllers, and file servers</span></span>  |
| <span data-ttu-id="d0a4f-178">執行</span><span class="sxs-lookup"><span data-stu-id="d0a4f-178">Execution</span></span>            | <span data-ttu-id="d0a4f-179">執行</span><span class="sxs-lookup"><span data-stu-id="d0a4f-179">Execution</span></span>           | <span data-ttu-id="d0a4f-180">啟動攻擊者工具和惡意程式碼（包括 Rat 和後門程式）</span><span class="sxs-lookup"><span data-stu-id="d0a4f-180">Launching   attacker tools and malicious code, including RATs and backdoors</span></span>                                                             |
| <span data-ttu-id="d0a4f-181">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="d0a4f-181">Exfiltration</span></span>         | <span data-ttu-id="d0a4f-182">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="d0a4f-182">Exfiltration</span></span>        | <span data-ttu-id="d0a4f-183">將網路中的資料解壓縮至外部的受攻擊者控制的位置</span><span class="sxs-lookup"><span data-stu-id="d0a4f-183">Extracting   data from the network to an external, attacker-controlled location</span></span>                                                         |
| <span data-ttu-id="d0a4f-184">利用</span><span class="sxs-lookup"><span data-stu-id="d0a4f-184">Exploit</span></span>              | <span data-ttu-id="d0a4f-185">利用</span><span class="sxs-lookup"><span data-stu-id="d0a4f-185">Exploit</span></span>             | <span data-ttu-id="d0a4f-186">攻擊程式碼和可能的攻擊活動</span><span class="sxs-lookup"><span data-stu-id="d0a4f-186">Exploit   code and possible exploitation activity</span></span>                                                                                       |
| <span data-ttu-id="d0a4f-187">初始存取</span><span class="sxs-lookup"><span data-stu-id="d0a4f-187">Initial access</span></span>       | <span data-ttu-id="d0a4f-188">InitialAccess</span><span class="sxs-lookup"><span data-stu-id="d0a4f-188">InitialAccess</span></span>       | <span data-ttu-id="d0a4f-189">取得目標網路的初始專案，通常涉及密碼猜測、入侵或網路釣魚電子郵件</span><span class="sxs-lookup"><span data-stu-id="d0a4f-189">Gaining   initial entry to the target network, usually involving password-guessing,   exploits, or phishing emails</span></span>                      |
| <span data-ttu-id="d0a4f-190">橫向移動</span><span class="sxs-lookup"><span data-stu-id="d0a4f-190">Lateral movement</span></span>     | <span data-ttu-id="d0a4f-191">LateralMovement</span><span class="sxs-lookup"><span data-stu-id="d0a4f-191">LateralMovement</span></span>     | <span data-ttu-id="d0a4f-192">在目標網路中的裝置間移動，以達到重要資源或取得網路暫留</span><span class="sxs-lookup"><span data-stu-id="d0a4f-192">Moving   between devices in the target network to reach critical resources or gain   network persistence</span></span>                                |
| <span data-ttu-id="d0a4f-193">惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="d0a4f-193">Malware</span></span>              | <span data-ttu-id="d0a4f-194">惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="d0a4f-194">Malware</span></span>             | <span data-ttu-id="d0a4f-195">後門程式、特洛伊木馬程式和其他類型的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="d0a4f-195">Backdoors,   trojans, and other types of malicious code</span></span>                                                                                 |
| <span data-ttu-id="d0a4f-196">堅持</span><span class="sxs-lookup"><span data-stu-id="d0a4f-196">Persistence</span></span>          | <span data-ttu-id="d0a4f-197">堅持</span><span class="sxs-lookup"><span data-stu-id="d0a4f-197">Persistence</span></span>         | <span data-ttu-id="d0a4f-198">建立 autostart 擴充點 (ASEPs) 保持使用中且可經受系統重新開機</span><span class="sxs-lookup"><span data-stu-id="d0a4f-198">Creating   autostart extensibility points (ASEPs) to remain active and survive system   restarts</span></span>                                        |
| <span data-ttu-id="d0a4f-199">許可權提升</span><span class="sxs-lookup"><span data-stu-id="d0a4f-199">Privilege escalation</span></span> | <span data-ttu-id="d0a4f-200">PrivilegeEscalation</span><span class="sxs-lookup"><span data-stu-id="d0a4f-200">PrivilegeEscalation</span></span> | <span data-ttu-id="d0a4f-201">在特權程式或帳戶的上下文中執行程式碼，以取得更高的許可權層級</span><span class="sxs-lookup"><span data-stu-id="d0a4f-201">Obtaining   higher permission levels for code by running it in the context of a   privileged process or account</span></span>                         |
| <span data-ttu-id="d0a4f-202">軟體</span><span class="sxs-lookup"><span data-stu-id="d0a4f-202">Ransomware</span></span>           | <span data-ttu-id="d0a4f-203">軟體</span><span class="sxs-lookup"><span data-stu-id="d0a4f-203">Ransomware</span></span>          | <span data-ttu-id="d0a4f-204">惡意程式碼會加密檔案和 extorts 付款以還原存取</span><span class="sxs-lookup"><span data-stu-id="d0a4f-204">Malware   that encrypts files and extorts payment to restore access</span></span>                                                                     |
| <span data-ttu-id="d0a4f-205">可疑的活動</span><span class="sxs-lookup"><span data-stu-id="d0a4f-205">Suspicious activity</span></span>  | <span data-ttu-id="d0a4f-206">SuspiciousActivity</span><span class="sxs-lookup"><span data-stu-id="d0a4f-206">SuspiciousActivity</span></span>  | <span data-ttu-id="d0a4f-207">可能成為惡意程式碼或部分攻擊的非典型活動</span><span class="sxs-lookup"><span data-stu-id="d0a4f-207">Atypical   activity that could be malware activity or part of an attack</span></span>                                                                 |
| <span data-ttu-id="d0a4f-208">不需要的軟體</span><span class="sxs-lookup"><span data-stu-id="d0a4f-208">Unwanted software</span></span>    | <span data-ttu-id="d0a4f-209">UnwantedSoftware</span><span class="sxs-lookup"><span data-stu-id="d0a4f-209">UnwantedSoftware</span></span>    | <span data-ttu-id="d0a4f-210">影響生產力和使用者經驗的低信譽應用程式和應用程式偵測到可能有害的應用程式 (PUAs) </span><span class="sxs-lookup"><span data-stu-id="d0a4f-210">Low-reputation   apps and apps that impact productivity and the user experience; detected as   potentially unwanted applications (PUAs)</span></span> |

### <a name="status"></a><span data-ttu-id="d0a4f-211">狀態</span><span class="sxs-lookup"><span data-stu-id="d0a4f-211">Status</span></span>

<span data-ttu-id="d0a4f-212">您可以選擇根據其狀態來限制警示清單。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-212">You can choose to limit the list of alerts based on their status.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="d0a4f-213">調查狀態</span><span class="sxs-lookup"><span data-stu-id="d0a4f-213">Investigation state</span></span>

<span data-ttu-id="d0a4f-214">會對應至自動調查狀態。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-214">Corresponds to the automated investigation state.</span></span>

### <a name="category"></a><span data-ttu-id="d0a4f-215">Category</span><span class="sxs-lookup"><span data-stu-id="d0a4f-215">Category</span></span>

<span data-ttu-id="d0a4f-216">您可以選擇篩選佇列以顯示特定類型的惡意活動。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-216">You can choose to filter the queue to display specific types of malicious activity.</span></span>

### <a name="assigned-to"></a><span data-ttu-id="d0a4f-217">指派給</span><span class="sxs-lookup"><span data-stu-id="d0a4f-217">Assigned to</span></span>

<span data-ttu-id="d0a4f-218">您可以選擇顯示指派給您或自動化的警示。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-218">You can choose between showing alerts that are assigned to you or automation.</span></span>

### <a name="detection-source"></a><span data-ttu-id="d0a4f-219">偵測來源</span><span class="sxs-lookup"><span data-stu-id="d0a4f-219">Detection source</span></span>

<span data-ttu-id="d0a4f-220">選取觸發警示偵測的來源。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-220">Select the source that triggered the alert detection.</span></span> <span data-ttu-id="d0a4f-221">Microsoft 威脅專家預覽參與者現在可以篩選並查看新威脅專家管理之搜尋服務中的偵測結果。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-221">Microsoft Threat Experts preview participants can now filter and see detections from the new threat experts-managed hunting service.</span></span>

>[!NOTE]
><span data-ttu-id="d0a4f-222">只有在裝置使用 Microsoft Defender 防毒軟體作為預設即時保護反惡意軟體產品時，才會顯示防病毒篩選器。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-222">The Antivirus filter will only appear if devices are using Microsoft Defender Antivirus as the default real-time protection antimalware product.</span></span>

| <span data-ttu-id="d0a4f-223">偵測來源</span><span class="sxs-lookup"><span data-stu-id="d0a4f-223">Detection source</span></span>                  | <span data-ttu-id="d0a4f-224">API 值</span><span class="sxs-lookup"><span data-stu-id="d0a4f-224">API value</span></span>                  |
|-----------------------------------|----------------------------|
| <span data-ttu-id="d0a4f-225">協力廠商感應器</span><span class="sxs-lookup"><span data-stu-id="d0a4f-225">3rd party sensors</span></span>                 | <span data-ttu-id="d0a4f-226">ThirdPartySensors</span><span class="sxs-lookup"><span data-stu-id="d0a4f-226">ThirdPartySensors</span></span>          |
| <span data-ttu-id="d0a4f-227">防毒</span><span class="sxs-lookup"><span data-stu-id="d0a4f-227">Antivirus</span></span>                         | <span data-ttu-id="d0a4f-228">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="d0a4f-228">WindowsDefenderAv</span></span>          |
| <span data-ttu-id="d0a4f-229">自動調查</span><span class="sxs-lookup"><span data-stu-id="d0a4f-229">Automated investigation</span></span>           | <span data-ttu-id="d0a4f-230">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="d0a4f-230">AutomatedInvestigation</span></span>     |
| <span data-ttu-id="d0a4f-231">自訂偵測</span><span class="sxs-lookup"><span data-stu-id="d0a4f-231">Custom detection</span></span>                  | <span data-ttu-id="d0a4f-232">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="d0a4f-232">CustomDetection</span></span>            |
| <span data-ttu-id="d0a4f-233">自訂 TI</span><span class="sxs-lookup"><span data-stu-id="d0a4f-233">Custom TI</span></span>                         | <span data-ttu-id="d0a4f-234">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="d0a4f-234">CustomerTI</span></span>                 |
| <span data-ttu-id="d0a4f-235">EDR</span><span class="sxs-lookup"><span data-stu-id="d0a4f-235">EDR</span></span>                               | <span data-ttu-id="d0a4f-236">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="d0a4f-236">WindowsDefenderAtp</span></span>         |
| <span data-ttu-id="d0a4f-237">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0a4f-237">Microsoft 365 Defender</span></span>            | <span data-ttu-id="d0a4f-238">具有 MTP 之</span><span class="sxs-lookup"><span data-stu-id="d0a4f-238">MTP</span></span>                        |
| <span data-ttu-id="d0a4f-239">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d0a4f-239">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="d0a4f-240">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="d0a4f-240">OfficeATP</span></span>                  |
| <span data-ttu-id="d0a4f-241">Microsoft 威脅專家</span><span class="sxs-lookup"><span data-stu-id="d0a4f-241">Microsoft Threat Experts</span></span>          | <span data-ttu-id="d0a4f-242">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="d0a4f-242">ThreatExperts</span></span>              |
| <span data-ttu-id="d0a4f-243">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="d0a4f-243">SmartScreen</span></span>                       | <span data-ttu-id="d0a4f-244">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="d0a4f-244">WindowsDefenderSmartScreen</span></span> |

### <a name="os-platform"></a><span data-ttu-id="d0a4f-245">作業系統平臺</span><span class="sxs-lookup"><span data-stu-id="d0a4f-245">OS platform</span></span>

<span data-ttu-id="d0a4f-246">選取您要調查的作業系統平臺，以限制提醒佇列查看。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-246">Limit the alerts queue view by selecting the OS platform that you're interested in investigating.</span></span>

### <a name="device-group"></a><span data-ttu-id="d0a4f-247">裝置群組</span><span class="sxs-lookup"><span data-stu-id="d0a4f-247">Device group</span></span>

<span data-ttu-id="d0a4f-248">如果您有想要檢查的特定裝置群組，您可以選取群組來限制警示佇列的顯示。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-248">If you have specific device groups that you're interested in checking, you can select the groups to limit the alerts queue view.</span></span> 

### <a name="associated-threat"></a><span data-ttu-id="d0a4f-249">相關威脅</span><span class="sxs-lookup"><span data-stu-id="d0a4f-249">Associated threat</span></span>

<span data-ttu-id="d0a4f-250">使用此篩選器，將重點放在與高設定檔威脅相關的警示上。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-250">Use this filter to focus on alerts that are related to high profile threats.</span></span> <span data-ttu-id="d0a4f-251">您可以在 [威脅分析](threat-analytics.md)中看到高設定檔威脅的完整清單。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-251">You can see the full list of high-profile threats in [Threat analytics](threat-analytics.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0a4f-252">相關主題</span><span class="sxs-lookup"><span data-stu-id="d0a4f-252">Related topics</span></span>

- [<span data-ttu-id="d0a4f-253">管理 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="d0a4f-253">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="d0a4f-254">調查 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="d0a4f-254">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="d0a4f-255">調查與 Microsoft Defender for Endpoint alert 相關聯的檔案</span><span class="sxs-lookup"><span data-stu-id="d0a4f-255">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="d0a4f-256">調查 Microsoft Defender for Endpoint Devices 清單中的裝置</span><span class="sxs-lookup"><span data-stu-id="d0a4f-256">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="d0a4f-257">調查與 Microsoft Defender for Endpoint 警示相關聯的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="d0a4f-257">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="d0a4f-258">調查與 Microsoft Defender for Endpoint alert 相關聯的網域</span><span class="sxs-lookup"><span data-stu-id="d0a4f-258">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="d0a4f-259">調查 Microsoft Defender for Endpoint 中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="d0a4f-259">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
