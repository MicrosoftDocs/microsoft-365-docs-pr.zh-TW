---
title: 報告及疑難排解 Microsoft Defender for Endpoint ASR 規則
description: 本主題說明如何報告及疑難排解 Microsoft Defender for Endpoint ASR 規則
keywords: 攻擊面減少規則，asr，hips，主機入侵防護系統，保護規則，反侵入，antiexploit，exploit，感染防護，microsoft defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 65e3e8d1baef7ca4440824c9a262f0b5f696b657
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194742"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="f85be-104">報告及疑難排解 Microsoft Defender 以取得 ATP ASR 規則</span><span class="sxs-lookup"><span data-stu-id="f85be-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f85be-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f85be-105">**Applies to:**</span></span>

- [<span data-ttu-id="f85be-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f85be-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f85be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f85be-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="f85be-108">Microsoft 365 的安全性中心是一個新的介面，可監控和管理跨您的 Microsoft identity、資料、裝置、應用程式和基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="f85be-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="f85be-109">其可讓您輕鬆檢視組織的安全性狀況、採取行動來設定裝置、使用者和應用程式，並取得可疑活動的警示。</span><span class="sxs-lookup"><span data-stu-id="f85be-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="f85be-110">Microsoft 365 安全性中心主要供安全性管理員和安全性作業小組更妥善地管理及保護其組織。</span><span class="sxs-lookup"><span data-stu-id="f85be-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="f85be-111">流覽 Microsoft 365 的安全性中心，網址為 https://security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="f85be-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="f85be-112">在 Microsoft 365 的安全性中心，我們為您提供了目前的 ASR 規則設定和房地產中的事件的完整外觀。</span><span class="sxs-lookup"><span data-stu-id="f85be-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="f85be-113">請注意，您的裝置必須架至 Microsoft Defender for Endpoint service 中，才可填入這些報告。</span><span class="sxs-lookup"><span data-stu-id="f85be-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="f85be-114">以下是「Microsoft 365 安全性中心」 (「**報告**  >  **裝置**  >  **攻擊面降低**) 」下的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="f85be-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="f85be-115">在裝置層級 **，從 [** **攻擊面減少規則** ] 窗格中選取 [設定]。</span><span class="sxs-lookup"><span data-stu-id="f85be-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="f85be-116">此時會顯示下列畫面，您可以在其中選取特定裝置，並檢查其個別的 ASR 規則設定。</span><span class="sxs-lookup"><span data-stu-id="f85be-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="ASR 規則畫面":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="f85be-118">Microsoft Defender for Endpoint –高級搜尋</span><span class="sxs-lookup"><span data-stu-id="f85be-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="f85be-119">Microsoft Defender 端點最強大的功能之一是「高級搜尋」。</span><span class="sxs-lookup"><span data-stu-id="f85be-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="f85be-120">如果您不熟悉高級搜尋，請參閱 [使用高級搜尋主動搜尋威脅](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f85be-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="f85be-121">「高級搜尋」是以查詢為基礎的 (Kusto 查詢語言) 威脅搜尋工具，可讓您探索最多30天的已捕獲 (raw) 資料，該 Defender 的端點會從您的裝置收集。</span><span class="sxs-lookup"><span data-stu-id="f85be-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that Defender for Endpoint collects from your devices.</span></span> <span data-ttu-id="f85be-122">透過「高級搜尋」，您可以主動檢查事件，以找出感興趣的指示器和實體。</span><span class="sxs-lookup"><span data-stu-id="f85be-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="f85be-123">對資料的靈活存取可協助對已知和潛在威脅進行無限制的搜尋。</span><span class="sxs-lookup"><span data-stu-id="f85be-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="f85be-124">透過「高級搜尋」，可以解壓縮 ASR 規則資訊、建立報告，以及取得指定之 ASR 規則 audit 或封鎖事件內容的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f85be-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="f85be-125">在 Microsoft Defender 資訊安全中心的「高級搜尋」區段中，您可以從 [DeviceEvents] 表格中查詢 ASR 規則事件。</span><span class="sxs-lookup"><span data-stu-id="f85be-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="f85be-126">例如，下列的簡單查詢可以在過去30天內，以資料來源形式報告所有具有 ASR 規則的事件，並以 ActionType 計數來匯總這些事件，在此情況下，它會是 ASR 規則的實際 codename。</span><span class="sxs-lookup"><span data-stu-id="f85be-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="高級搜尋查詢":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="高級搜尋畫面":::

<span data-ttu-id="f85be-129">透過高級搜尋，您可以將查詢整形成您的喜好，這樣您就可以查看所發生的情形，不論您是想要尋找個別機器上的某個專案，還是想要從您的整個環境析取見解。</span><span class="sxs-lookup"><span data-stu-id="f85be-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="f85be-130">Microsoft Defender for Endpoint machine 時序表</span><span class="sxs-lookup"><span data-stu-id="f85be-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="f85be-131">「高級搜尋」（但範圍較窄）是「Microsoft Defender for Endpoint machine」時程表的替代方法。</span><span class="sxs-lookup"><span data-stu-id="f85be-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="f85be-132">您可以在過去六個月內，查看裝置的所有收集的事件，在 Microsoft Defender 資訊安全中心中，移至 [機器] 清單，選取指定的機器，然後按一下 [時程表] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f85be-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="f85be-133">下圖是在指定的端點上，這些事件的時程表視圖的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="f85be-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="f85be-134">在此視圖中，您可以根據右側窗格中的任何事件群組來篩選事件清單。</span><span class="sxs-lookup"><span data-stu-id="f85be-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="f85be-135">您也可以啟用或停用已標記和詳細的事件，同時在歷史時程表中查看提醒及滾動。</span><span class="sxs-lookup"><span data-stu-id="f85be-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="microsoft defender 安全中心時程表":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="f85be-137">如何疑難排解 ASR 規則？</span><span class="sxs-lookup"><span data-stu-id="f85be-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="f85be-138">第一個也是最直接的方式，就是在 Windows 裝置上進行檢查，啟用了哪些 ASR 規則 (及其設定) 使用 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f85be-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="f85be-139">以下是一些 Windows 提供的資訊來源，可疑難排解 ASR 規則的影響與運作。</span><span class="sxs-lookup"><span data-stu-id="f85be-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="f85be-140">查詢作用中的規則</span><span class="sxs-lookup"><span data-stu-id="f85be-140">Querying which rules are active</span></span>
<span data-ttu-id="f85be-141">判斷是否已啟用 ASR 規則的最簡單方法之一，也就是透過 PowerShell Cmdlet MpPreference。</span><span class="sxs-lookup"><span data-stu-id="f85be-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="f85be-142">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="f85be-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="取得 mppreference 腳本":::

<span data-ttu-id="f85be-144">有多個啟用中的 ASR 規則，具有不同的已設定動作。</span><span class="sxs-lookup"><span data-stu-id="f85be-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="f85be-145">若要展開有關 ASR 規則的上述資訊，您可以使用 **AttackSurfaceReductionRules_Ids** 和/或 **AttackSurfaceReductionRules_Actions** 屬性。</span><span class="sxs-lookup"><span data-stu-id="f85be-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="f85be-146">範例：</span><span class="sxs-lookup"><span data-stu-id="f85be-146">Example:</span></span>

<span data-ttu-id="f85be-147">*MPPreference |Select-Object-ExpandProperty \* \* AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="f85be-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="取得 mpreference 範例":::

<span data-ttu-id="f85be-149">以上會顯示所有 IDs，使其設定值不同于 0 (未設定) 的 ASR 規則。</span><span class="sxs-lookup"><span data-stu-id="f85be-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="f85be-150">接下來的步驟是列出每個規則所設定的實際動作 (區塊或審計) 。</span><span class="sxs-lookup"><span data-stu-id="f85be-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="f85be-151">*MPPreference |Select-Object-ExpandProperty \* \* AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="f85be-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="取得 mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="f85be-153">查詢封鎖和審核事件</span><span class="sxs-lookup"><span data-stu-id="f85be-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="f85be-154">可在 Windows Defender 記錄中查看 ASR 規則事件。</span><span class="sxs-lookup"><span data-stu-id="f85be-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="f85be-155">若要存取它，請開啟 Windows 事件檢視器，並流覽至 **應用程式及服務記錄**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **運作**。</span><span class="sxs-lookup"><span data-stu-id="f85be-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="事件檢視器 scr":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="f85be-157">Microsoft Defender 惡意程式碼保護記錄</span><span class="sxs-lookup"><span data-stu-id="f85be-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="f85be-158">您也可以透過可用於管理及設定的 Microsoft Defender 防毒軟體專用命令列工具（稱為）來查看規則事件， `*mpcmdrun.exe*` 並視需要自動化工作。</span><span class="sxs-lookup"><span data-stu-id="f85be-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="f85be-159">您可以在 *%ProgramFiles% \ Windows Defender\MpCmdRun.exe* 中找到此公用程式。</span><span class="sxs-lookup"><span data-stu-id="f85be-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="f85be-160">您必須從提升許可權的命令提示字元執行 (，也就是以系統管理員身分) 執行。</span><span class="sxs-lookup"><span data-stu-id="f85be-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="f85be-161">若要產生支援資訊，請輸入 *MpCmdRun.exe-getfiles*。</span><span class="sxs-lookup"><span data-stu-id="f85be-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="f85be-162">經過一段時間後，會將幾個記錄封裝到封存 (MpSupportFiles.cab) 並在 *C:\ProgramData\Microsoft\ Windows Defender \Support* 中提供。</span><span class="sxs-lookup"><span data-stu-id="f85be-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="惡意程式碼保護記錄":::

<span data-ttu-id="f85be-164">解壓縮該封存，您將有許多檔案可供疑難排解之用。</span><span class="sxs-lookup"><span data-stu-id="f85be-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="f85be-165">最相關的檔如下：</span><span class="sxs-lookup"><span data-stu-id="f85be-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="f85be-166">**MPOperationalEvents.txt** -此檔案包含在事件檢視器中找到 Windows Defender 操作記錄檔的相同層級資訊。</span><span class="sxs-lookup"><span data-stu-id="f85be-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="f85be-167">**MPRegistry.txt** –在此檔案中，您可以從捕獲支援記錄檔的時刻分析所有目前的 Windows Defender 設定。</span><span class="sxs-lookup"><span data-stu-id="f85be-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="f85be-168">**MPLog.txt** –此記錄檔包含 Windows Defender 所有動作/作業的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f85be-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
