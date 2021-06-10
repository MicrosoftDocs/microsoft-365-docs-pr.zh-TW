---
title: 解決適用於端點的 Microsoft Defender 中的誤判/漏報
description: 瞭解如何在 Microsoft Defender for Endpoint 中處理誤報或虛假的否定。
keywords: 防病毒，例外，排除，Microsoft Defender for Endpoint，誤報，false 負數，封鎖檔，封鎖的 url
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
- m365solution-scenario
- m365scenario-fpfn
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs, yonghree, jcedola
ms.custom: FPFN
ms.openlocfilehash: 368de770f772dc75a366b2120c8824fda6a7ba11
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933586"
---
# <a name="address-false-positivesnegatives-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="3608c-104">解決適用於端點的 Microsoft Defender 中的誤判/漏報</span><span class="sxs-lookup"><span data-stu-id="3608c-104">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3608c-105">**適用於**</span><span class="sxs-lookup"><span data-stu-id="3608c-105">**Applies to**</span></span>

- [<span data-ttu-id="3608c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3608c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146806)

<span data-ttu-id="3608c-107">在 endpoint protection 解決方案中，誤報是指偵測到並識別為惡意的實體（例如檔案或處理常式），即使實體實際上不是威脅也是一樣。</span><span class="sxs-lookup"><span data-stu-id="3608c-107">In endpoint protection solutions, a false positive is an entity, such as a file or a process, that was detected and identified as malicious, even though the entity isn't actually a threat.</span></span> <span data-ttu-id="3608c-108">誤報是指未被偵測為威脅的實體，但實際上為惡意。</span><span class="sxs-lookup"><span data-stu-id="3608c-108">A false negative is an entity that was not detected as a threat, even though it actually is malicious.</span></span> <span data-ttu-id="3608c-109">任何威脅防護解決方案（包括 [Microsoft Defender For Endpoint](microsoft-defender-endpoint.md)）都可能會發生誤報/負片。</span><span class="sxs-lookup"><span data-stu-id="3608c-109">False positives/negatives can occur with any threat protection solution, including [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).</span></span>

![在端點中定義 false 正值和負值](images/false-positives-overview.png)

<span data-ttu-id="3608c-111">幸運的是，您可以採取步驟解決並減少這類問題。</span><span class="sxs-lookup"><span data-stu-id="3608c-111">Fortunately, steps can be taken to address and reduce these kinds of issues.</span></span> <span data-ttu-id="3608c-112">如果您在[Microsoft Defender 資訊安全中心](../defender/microsoft-365-security-center-mde.md)中看到誤報/負片，您的安全性作業可以採取步驟來處理它們，方法是使用下列程式：</span><span class="sxs-lookup"><span data-stu-id="3608c-112">If you're seeing false positives/negatives in your [Microsoft Defender Security Center](../defender/microsoft-365-security-center-mde.md), your security operations can take steps to address them by using the following process:</span></span>

1.  [<span data-ttu-id="3608c-113">審閱和分類提醒</span><span class="sxs-lookup"><span data-stu-id="3608c-113">Review and classify alerts</span></span>](#part-1-review-and-classify-alerts) 
2.  [<span data-ttu-id="3608c-114">複查所執行的修復動作</span><span class="sxs-lookup"><span data-stu-id="3608c-114">Review remediation actions that were taken</span></span>](#part-2-review-remediation-actions)
3.  [<span data-ttu-id="3608c-115">審閱及定義排除專案</span><span class="sxs-lookup"><span data-stu-id="3608c-115">Review and define exclusions</span></span>](#part-3-review-or-define-exclusions)
4.  [<span data-ttu-id="3608c-116">提交實體進行分析</span><span class="sxs-lookup"><span data-stu-id="3608c-116">Submit an entity for analysis</span></span>](#part-4-submit-a-file-for-analysis)
5.  [<span data-ttu-id="3608c-117">檢查並調整威脅防護設定</span><span class="sxs-lookup"><span data-stu-id="3608c-117">Review and adjust your threat protection settings</span></span>](#part-5-review-and-adjust-your-threat-protection-settings)

<span data-ttu-id="3608c-118">您可以在執行本文所述的工作時，取得錯誤陽性/負片問題，以取得協助。</span><span class="sxs-lookup"><span data-stu-id="3608c-118">You can get help if you still have issues with false positives/negatives after performing the tasks described in this article.</span></span> <span data-ttu-id="3608c-119">[仍需要協助嗎？](#still-need-help)</span><span class="sxs-lookup"><span data-stu-id="3608c-119">See [Still need help?](#still-need-help)</span></span>

![解決誤報和負片的步驟](images/false-positives-step-diagram.png)

> [!NOTE]
> <span data-ttu-id="3608c-121">本文適用于使用 [Microsoft Defender For Endpoint](microsoft-defender-endpoint.md)的安全性操作員及安全性管理員的指導方針。</span><span class="sxs-lookup"><span data-stu-id="3608c-121">This article is intended as guidance for security operators and security administrators who are using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).</span></span>

## <a name="part-1-review-and-classify-alerts"></a><span data-ttu-id="3608c-122">第1部分：檢查和分類警示</span><span class="sxs-lookup"><span data-stu-id="3608c-122">Part 1: Review and classify alerts</span></span>

<span data-ttu-id="3608c-123">如果您看到因偵測到非預期的惡意或可疑而觸發的 [警示](alerts.md) ，您可以抑制該實體的警示。</span><span class="sxs-lookup"><span data-stu-id="3608c-123">If you see an [alert](alerts.md) that was triggered because something was detected as malicious or suspicious that should not have been, you can suppress the alert for that entity.</span></span> <span data-ttu-id="3608c-124">您也可以抑制不一定是誤報的警示，但並不重要。</span><span class="sxs-lookup"><span data-stu-id="3608c-124">You can also suppress alerts that are not necessarily false positives, but are unimportant.</span></span> <span data-ttu-id="3608c-125">我們建議您也對提醒進行分類。</span><span class="sxs-lookup"><span data-stu-id="3608c-125">We recommend that you classify alerts as well.</span></span> 

<span data-ttu-id="3608c-126">管理提醒和分類 true/false 正值有助於訓練威脅防護解決方案，以及減少因時間的誤報或漏報數目。</span><span class="sxs-lookup"><span data-stu-id="3608c-126">Managing your alerts and classifying true/false positives helps to train your threat protection solution and can reduce the number of false positives or false negatives over time.</span></span> <span data-ttu-id="3608c-127">採取這些步驟也有助於減少安全性作業儀表板中的噪音，讓安全性小組能夠專注于優先順序較高的工作專案。</span><span class="sxs-lookup"><span data-stu-id="3608c-127">Taking these steps also helps reduce noise in your security operations dashboard so that your security team can focus on higher priority work items.</span></span>

### <a name="determine-whether-an-alert-is-accurate"></a><span data-ttu-id="3608c-128">判斷警示是否正確</span><span class="sxs-lookup"><span data-stu-id="3608c-128">Determine whether an alert is accurate</span></span>

<span data-ttu-id="3608c-129">在您分類或抑制警示之前，請先判斷警示是否正確、誤報或良性。</span><span class="sxs-lookup"><span data-stu-id="3608c-129">Before you classify or suppress an alert, determine whether the alert is accurate, a false positive, or benign.</span></span>

1. <span data-ttu-id="3608c-130">移至 Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-130">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="3608c-131">在功能窗格中，選擇 [ **警示佇列**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-131">In the navigation pane, choose **Alerts queue**.</span></span>

3. <span data-ttu-id="3608c-132">選取警示的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3608c-132">Select an alert to more details about the alert.</span></span> <span data-ttu-id="3608c-133"> (請參閱 [在 Microsoft Defender For Endpoint 中查看警示](review-alerts.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-133">(See [Review alerts in Microsoft Defender for Endpoint](review-alerts.md).)</span></span>

4. <span data-ttu-id="3608c-134">根據警示狀態，採取下表所述的步驟：</span><span class="sxs-lookup"><span data-stu-id="3608c-134">Depending on the alert status, take the steps described in the following table:</span></span> 

| <span data-ttu-id="3608c-135">警示狀態</span><span class="sxs-lookup"><span data-stu-id="3608c-135">Alert status</span></span> | <span data-ttu-id="3608c-136">處理方式</span><span class="sxs-lookup"><span data-stu-id="3608c-136">What to do</span></span> |
|:---|:---|
| <span data-ttu-id="3608c-137">警示準確無誤</span><span class="sxs-lookup"><span data-stu-id="3608c-137">The alert is accurate</span></span> | <span data-ttu-id="3608c-138">指派提醒，然後進一步 [調查](investigate-alerts.md) 。</span><span class="sxs-lookup"><span data-stu-id="3608c-138">Assign the alert, and then [investigate it](investigate-alerts.md) further.</span></span> |
| <span data-ttu-id="3608c-139">警示是誤報</span><span class="sxs-lookup"><span data-stu-id="3608c-139">The alert is a false positive</span></span> | <span data-ttu-id="3608c-140">1. [將警示分類](#classify-an-alert) 為 false 陽性。</span><span class="sxs-lookup"><span data-stu-id="3608c-140">1. [Classify the alert](#classify-an-alert) as a false positive.</span></span> <br/><span data-ttu-id="3608c-141">2. [抑制警示](#suppress-an-alert)。</span><span class="sxs-lookup"><span data-stu-id="3608c-141">2. [Suppress the alert](#suppress-an-alert).</span></span> <br/> <span data-ttu-id="3608c-142">3. [建立](#indicators-for-microsoft-defender-for-endpoint) Microsoft Defender for Endpoint 的標記。</span><span class="sxs-lookup"><span data-stu-id="3608c-142">3. [Create an indicator](#indicators-for-microsoft-defender-for-endpoint) for Microsoft Defender for Endpoint.</span></span> <br/> <span data-ttu-id="3608c-143">4. [提交檔案給 Microsoft 進行分析](#part-4-submit-a-file-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="3608c-143">4. [Submit a file to Microsoft for analysis](#part-4-submit-a-file-for-analysis).</span></span> |
| <span data-ttu-id="3608c-144">警示正確，但誤報 (不重要) </span><span class="sxs-lookup"><span data-stu-id="3608c-144">The alert is accurate, but benign (unimportant)</span></span> | <span data-ttu-id="3608c-145">將[警示歸類](#classify-an-alert)為 true 正值，然後[抑制警示](#suppress-an-alert)。</span><span class="sxs-lookup"><span data-stu-id="3608c-145">[Classify the alert](#classify-an-alert) as a true positive, and then [suppress the alert](#suppress-an-alert).</span></span> |

### <a name="classify-an-alert"></a><span data-ttu-id="3608c-146">分類警示</span><span class="sxs-lookup"><span data-stu-id="3608c-146">Classify an alert</span></span>

<span data-ttu-id="3608c-147">警示可以分類為 Microsoft Defender 資訊安全中心中的誤報或 true 陽性。</span><span class="sxs-lookup"><span data-stu-id="3608c-147">Alerts can be classified as false positives or true positives in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="3608c-148">分類提醒可協助訓練 Microsoft Defender for Endpoint，這樣一來，您就能看到更真實的通知，以及更少的錯誤警示。</span><span class="sxs-lookup"><span data-stu-id="3608c-148">Classifying alerts helps train Microsoft Defender for Endpoint so that, over time, you'll see more true alerts and fewer false alerts.</span></span>

1. <span data-ttu-id="3608c-149">移至 Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-149">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="3608c-150">選取 [ **提醒佇列**]，然後選取警示。</span><span class="sxs-lookup"><span data-stu-id="3608c-150">Select **Alerts queue**, and then select an alert.</span></span>

3. <span data-ttu-id="3608c-151">針對選取的警示，選取 [**動作**  >  **管理警示**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-151">For the selected alert, select **Actions** > **Manage alert**.</span></span> <span data-ttu-id="3608c-152">隨即開啟彈出窗格。</span><span class="sxs-lookup"><span data-stu-id="3608c-152">A flyout pane opens.</span></span>

4. <span data-ttu-id="3608c-153">在 [ **管理提醒** ] 區段中，選取 [ **True 警示** ] 或 [ **False 警示**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-153">In the **Manage alert** section, select either **True alert** or **False alert**.</span></span> <span data-ttu-id="3608c-154"> (使用 **false 警示** 來分類誤報的誤報。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-154">(Use **False alert** to classify a false positive.)</span></span>

> [!TIP]
> <span data-ttu-id="3608c-155">如需抑制警告的詳細資訊，請參閱 [管理 Microsoft Defender For Endpoint 警示](/microsoft-365/security/defender-endpoint/manage-alerts)。</span><span class="sxs-lookup"><span data-stu-id="3608c-155">For more information about suppressing alerts, see [Manage Microsoft Defender for Endpoint alerts](/microsoft-365/security/defender-endpoint/manage-alerts).</span></span> <span data-ttu-id="3608c-156">而且，如果您的組織使用安全性資訊和事件管理 (SIEM) server，請務必同時定義抑制規則。</span><span class="sxs-lookup"><span data-stu-id="3608c-156">And, if your organization is using a security information and event management (SIEM) server, make sure to define a suppression rule there, too.</span></span> 

### <a name="suppress-an-alert"></a><span data-ttu-id="3608c-157">抑制警示</span><span class="sxs-lookup"><span data-stu-id="3608c-157">Suppress an alert</span></span>

<span data-ttu-id="3608c-158">如果您的提醒是誤報或為 true，但不重要的事件，您可以在 Microsoft Defender 資訊安全中心中抑制這些警示。</span><span class="sxs-lookup"><span data-stu-id="3608c-158">If you have alerts that are either false positives or that are true positives but for unimportant events, you can suppress those alerts in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="3608c-159">抑制提醒有助於減少安全性作業儀表板中的噪音。</span><span class="sxs-lookup"><span data-stu-id="3608c-159">Suppressing alerts helps reduce noise in your security operations dashboard.</span></span> 

1. <span data-ttu-id="3608c-160">移至 Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-160">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="3608c-161">在功能窗格中，選取 [ **警示佇列**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-161">In the navigation pane, select **Alerts queue**.</span></span>

3. <span data-ttu-id="3608c-162">選取您要抑制的警示，以開啟其 **詳細資料** 窗格。</span><span class="sxs-lookup"><span data-stu-id="3608c-162">Select an alert that you want to suppress to open its **Details** pane.</span></span>

4. <span data-ttu-id="3608c-163">在 **詳細資料** 窗格中，選擇 [省略號 (**...** ]) ，然後 **建立隱藏規則**。</span><span class="sxs-lookup"><span data-stu-id="3608c-163">In the **Details** pane, choose the ellipsis (**...**), and then **Create a suppression rule**.</span></span>

5. <span data-ttu-id="3608c-164">指定抑制規則的所有設定，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-164">Specify all the settings for your suppression rule, and then choose **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="3608c-165">需要關於抑制規則的協助嗎？</span><span class="sxs-lookup"><span data-stu-id="3608c-165">Need help with suppression rules?</span></span> <span data-ttu-id="3608c-166">請參閱 [抑制警示並建立新的抑制規則](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule)。</span><span class="sxs-lookup"><span data-stu-id="3608c-166">See [Suppress an alert and create a new suppression rule](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule).</span></span>

## <a name="part-2-review-remediation-actions"></a><span data-ttu-id="3608c-167">第2部分：複查修復動作</span><span class="sxs-lookup"><span data-stu-id="3608c-167">Part 2: Review remediation actions</span></span>

<span data-ttu-id="3608c-168">[修正動作](manage-auto-investigation.md#remediation-actions)（例如傳送檔案至隔離或停止程式）的工作是針對實體 (，例如偵測為威脅) 的檔案。</span><span class="sxs-lookup"><span data-stu-id="3608c-168">[Remediation actions](manage-auto-investigation.md#remediation-actions), such as sending a file to quarantine or stopping a process, are taken on entities (such as files) that are detected as threats.</span></span> <span data-ttu-id="3608c-169">透過自動調查和 Microsoft Defender 防毒軟體，會自動進行多種類型的修復動作：</span><span class="sxs-lookup"><span data-stu-id="3608c-169">Several types of remediation actions occur automatically through automated investigation and Microsoft Defender Antivirus:</span></span>   
- <span data-ttu-id="3608c-170">隔離檔</span><span class="sxs-lookup"><span data-stu-id="3608c-170">Quarantine a file</span></span>
- <span data-ttu-id="3608c-171">移除登錄機碼</span><span class="sxs-lookup"><span data-stu-id="3608c-171">Remove a registry key</span></span>
- <span data-ttu-id="3608c-172">終止進程</span><span class="sxs-lookup"><span data-stu-id="3608c-172">Kill a process</span></span>
- <span data-ttu-id="3608c-173">停止服務</span><span class="sxs-lookup"><span data-stu-id="3608c-173">Stop a service</span></span>
- <span data-ttu-id="3608c-174">停用驅動程式</span><span class="sxs-lookup"><span data-stu-id="3608c-174">Disable a driver</span></span>
- <span data-ttu-id="3608c-175">移除排程任務</span><span class="sxs-lookup"><span data-stu-id="3608c-175">Remove a scheduled task</span></span>

<span data-ttu-id="3608c-176">其他動作（例如啟動防病毒掃描或收集調查套件）會手動或透過 [即時回應](live-response.md)進行。</span><span class="sxs-lookup"><span data-stu-id="3608c-176">Other actions, such as starting an antivirus scan or collecting an investigation package, occur manually or through [Live Response](live-response.md).</span></span> <span data-ttu-id="3608c-177">透過 Live Response 採取的動作無法復原。</span><span class="sxs-lookup"><span data-stu-id="3608c-177">Actions taken through Live Response cannot be undone.</span></span>

<span data-ttu-id="3608c-178">在您檢查提醒後，下一步是 [複查修復動作](manage-auto-investigation.md)。</span><span class="sxs-lookup"><span data-stu-id="3608c-178">After you have reviewed your alerts, your next step is to [review remediation actions](manage-auto-investigation.md).</span></span> <span data-ttu-id="3608c-179">如果因誤報而採取任何動作，您可以復原大多數類型的修復動作。</span><span class="sxs-lookup"><span data-stu-id="3608c-179">If any actions were taken as a result of false positives, you can undo most kinds of remediation actions.</span></span> <span data-ttu-id="3608c-180">具體說來，您可以：</span><span class="sxs-lookup"><span data-stu-id="3608c-180">Specifically, you can:</span></span>

- [<span data-ttu-id="3608c-181">從行動中心還原隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="3608c-181">Restore a quarantined file from the Action Center</span></span>](#restore-a-quarantined-file-from-the-action-center)
- [<span data-ttu-id="3608c-182">一次撤銷多個動作</span><span class="sxs-lookup"><span data-stu-id="3608c-182">Undo multiple actions at one time</span></span>](#undo-multiple-actions-at-one-time)
- <span data-ttu-id="3608c-183">[在多個裝置間移除隔離區中的](#remove-a-file-from-quarantine-across-multiple-devices)檔案。</span><span class="sxs-lookup"><span data-stu-id="3608c-183">[Remove a file from quarantine across multiple devices](#remove-a-file-from-quarantine-across-multiple-devices).</span></span>  <span data-ttu-id="3608c-184">及</span><span class="sxs-lookup"><span data-stu-id="3608c-184">and</span></span> 
- [<span data-ttu-id="3608c-185">從隔離區還原檔案</span><span class="sxs-lookup"><span data-stu-id="3608c-185">Restore file from quarantine</span></span>](#restore-file-from-quarantine)

<span data-ttu-id="3608c-186">當您完成檢查並撤銷因誤報而採取的動作時，請繼續 [審閱或定義排除](#part-3-review-or-define-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="3608c-186">When you're done reviewing and undoing actions that were taken as a result of false positives, proceed to [review or define exclusions](#part-3-review-or-define-exclusions).</span></span>

### <a name="review-completed-actions"></a><span data-ttu-id="3608c-187">查看已完成的動作</span><span class="sxs-lookup"><span data-stu-id="3608c-187">Review completed actions</span></span>

1. <span data-ttu-id="3608c-188">請移至「行動中心」 ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-188">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span> 

2. <span data-ttu-id="3608c-189">選取 [ **記錄** ] 索引標籤，以查看採取的動作清單。</span><span class="sxs-lookup"><span data-stu-id="3608c-189">Select the **History** tab to view a list of actions that were taken.</span></span>  

3. <span data-ttu-id="3608c-190">選取專案，以查看有關所採取之修正動作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3608c-190">Select an item to view more details about the remediation action that was taken.</span></span>

### <a name="restore-a-quarantined-file-from-the-action-center"></a><span data-ttu-id="3608c-191">從行動中心還原隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="3608c-191">Restore a quarantined file from the Action Center</span></span>

1. <span data-ttu-id="3608c-192">請移至「行動中心」 ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-192">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="3608c-193">在 [ **記錄** ] 索引標籤上，選取您要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="3608c-193">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="3608c-194">在快顯視窗中，選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-194">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="3608c-195">如果無法使用此方法復原動作，您就不會看到 [ **復原** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3608c-195">If the action cannot be undone with this method, you will not see an **Undo** button.</span></span> <span data-ttu-id="3608c-196"> (若要深入瞭解，請參閱 [復原已完成的動作](manage-auto-investigation.md#undo-completed-actions)。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-196">(To learn more, see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions).)</span></span>

### <a name="undo-multiple-actions-at-one-time"></a><span data-ttu-id="3608c-197">一次撤銷多個動作</span><span class="sxs-lookup"><span data-stu-id="3608c-197">Undo multiple actions at one time</span></span>

1. <span data-ttu-id="3608c-198">請移至「行動中心」 ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-198">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="3608c-199">在 [ **記錄** ] 索引標籤上，選取您要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="3608c-199">On the **History** tab, select the actions that you want to undo.</span></span>

3. <span data-ttu-id="3608c-200">在螢幕右側的窗格中，選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-200">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="3608c-201">在多個裝置之間移除隔離區中的檔案</span><span class="sxs-lookup"><span data-stu-id="3608c-201">Remove a file from quarantine across multiple devices</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3608c-202">![隔離的檔案](images/autoir-quarantine-file-1.png)</span><span class="sxs-lookup"><span data-stu-id="3608c-202">![Quarantine file](images/autoir-quarantine-file-1.png)</span></span>

1. <span data-ttu-id="3608c-203">請移至「行動中心」 ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-203">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="3608c-204">在 [ **記錄** ] 索引標籤上，選取具有 [ **隔離** 檔] 動作類型的檔案。</span><span class="sxs-lookup"><span data-stu-id="3608c-204">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="3608c-205">在螢幕右側的窗格中，選取 [套用至此檔案 **的 X 個實例**]，然後選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-205">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

### <a name="restore-file-from-quarantine"></a><span data-ttu-id="3608c-206">從隔離區還原檔案</span><span class="sxs-lookup"><span data-stu-id="3608c-206">Restore file from quarantine</span></span>

<span data-ttu-id="3608c-207">如果您已決定在調查之後清除檔案，您可以從隔離區復原檔案並將其移除。</span><span class="sxs-lookup"><span data-stu-id="3608c-207">You can roll back and remove a file from quarantine if you’ve determined that it’s clean after an investigation.</span></span> <span data-ttu-id="3608c-208">在隔離檔案的每個裝置上執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="3608c-208">Run the following command on each device where the file was quarantined.</span></span>

1. <span data-ttu-id="3608c-209">在裝置上開啟已提升許可權的命令列提示：</span><span class="sxs-lookup"><span data-stu-id="3608c-209">Open an elevated command–line prompt on the device:</span></span>

   1. <span data-ttu-id="3608c-210">轉至 **[開始]** 並鍵入 _「cmd」_。</span><span class="sxs-lookup"><span data-stu-id="3608c-210">Go to **Start** and type _cmd_.</span></span>

   1. <span data-ttu-id="3608c-211">以滑鼠右鍵按一下 [ **命令提示** 字元]，然後選取 [ **以管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-211">Right–click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="3608c-212">輸入下列命令，然後按 **enter**：</span><span class="sxs-lookup"><span data-stu-id="3608c-212">Enter the following command, and press **Enter**:</span></span>

    ```console
    "ProgramFiles%\Windows Defender\MpCmdRun.exe" –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
    ```

    > [!NOTE]
    > <span data-ttu-id="3608c-213">在某些情況下， **ThreatName** 可能會顯示為： `EUS:Win32/
CustomEnterpriseBlock!cl` 。</span><span class="sxs-lookup"><span data-stu-id="3608c-213">In some scenarios, the **ThreatName** may appear as: `EUS:Win32/
CustomEnterpriseBlock!cl`.</span></span> <span data-ttu-id="3608c-214">在過去30天內，在此裝置上已隔離的所有自訂封鎖檔案都會還原為端點。</span><span class="sxs-lookup"><span data-stu-id="3608c-214">Defender for Endpoint will restore all custom blocked files that were quarantined on this device in the last 30 days.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3608c-215">被隔離成可能網路威脅的檔案可能無法復原。</span><span class="sxs-lookup"><span data-stu-id="3608c-215">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="3608c-216">如果使用者嘗試在隔離後還原檔案，該檔案可能無法存取。</span><span class="sxs-lookup"><span data-stu-id="3608c-216">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="3608c-217">這可能是因為系統已無法再有存取該檔案的網路認證。</span><span class="sxs-lookup"><span data-stu-id="3608c-217">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="3608c-218">一般來說，這是暫時登入系統或共用資料夾，且存取權杖已到期的結果。</span><span class="sxs-lookup"><span data-stu-id="3608c-218">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

3. <span data-ttu-id="3608c-219">在螢幕右側的窗格中，選取 [套用至此檔案 **的 X 個實例**]，然後選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-219">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span> 


## <a name="part-3-review-or-define-exclusions"></a><span data-ttu-id="3608c-220">第3部分：審閱或定義排除專案</span><span class="sxs-lookup"><span data-stu-id="3608c-220">Part 3: Review or define exclusions</span></span>

<span data-ttu-id="3608c-221">排除是您指定作為修正動作例外狀況的實體（例如檔案或 URL）。</span><span class="sxs-lookup"><span data-stu-id="3608c-221">An exclusion is an entity, such as a file or URL, that you specify as an exception to remediation actions.</span></span> <span data-ttu-id="3608c-222">仍然可以偵測到已排除的實體，但不會對該實體採取任何修正動作。</span><span class="sxs-lookup"><span data-stu-id="3608c-222">The excluded entity can still get detected, but no remediation actions are taken on that entity.</span></span> <span data-ttu-id="3608c-223">也就是說，已偵測到的檔案或處理常式不會停止、傳送至隔離、移除，或由 Microsoft Defender for Endpoint 變更為已變更。</span><span class="sxs-lookup"><span data-stu-id="3608c-223">That is, the detected file or process won’t be stopped, sent to quarantine, removed, or otherwise changed by Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="3608c-224">若要在 Microsoft Defender for Endpoint 中定義排除專案，請執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="3608c-224">To define exclusions across Microsoft Defender for Endpoint, perform the following tasks:</span></span>
- [<span data-ttu-id="3608c-225">為 Microsoft Defender 防毒軟體定義排除專案</span><span class="sxs-lookup"><span data-stu-id="3608c-225">Define exclusions for Microsoft Defender Antivirus</span></span>](#exclusions-for-microsoft-defender-antivirus)
- [<span data-ttu-id="3608c-226">為 Microsoft Defender for Endpoint 建立 "allow" 標記</span><span class="sxs-lookup"><span data-stu-id="3608c-226">Create “allow” indicators for Microsoft Defender for Endpoint</span></span>](#indicators-for-microsoft-defender-for-endpoint)

> [!NOTE]
> <span data-ttu-id="3608c-227">Microsoft Defender 防毒軟體排除只會套用至防防毒保護，而不是跨其他 Microsoft Defender for Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="3608c-227">Microsoft Defender Antivirus exclusions apply only to antivirus protection, not across other Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="3608c-228">若要排除廣泛的檔案，請針對 Microsoft Defender for Endpoint 的 Microsoft Defender 防毒軟體和[自訂指示器](/microsoft-365/security/defender-endpoint/manage-indicators)使用排除。</span><span class="sxs-lookup"><span data-stu-id="3608c-228">To exclude files broadly, use exclusions for Microsoft Defender Antivirus and [custom indicators](/microsoft-365/security/defender-endpoint/manage-indicators) for Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="3608c-229">本節中的程式說明如何定義排除和指示器。</span><span class="sxs-lookup"><span data-stu-id="3608c-229">The procedures in this section describe how to define exclusions and indicators.</span></span>

### <a name="exclusions-for-microsoft-defender-antivirus"></a><span data-ttu-id="3608c-230">Microsoft Defender 防毒軟體的排除專案</span><span class="sxs-lookup"><span data-stu-id="3608c-230">Exclusions for Microsoft Defender Antivirus</span></span>

<span data-ttu-id="3608c-231">一般說來，您不需要為 Microsoft Defender 防毒軟體定義排除專案。</span><span class="sxs-lookup"><span data-stu-id="3608c-231">In general, you should not need to define exclusions for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="3608c-232">請確定您少定義排除專案，而且您只會包含會產生誤報的檔案、資料夾、處理常式及處理常式開啟的檔。</span><span class="sxs-lookup"><span data-stu-id="3608c-232">Make sure that you define exclusions sparingly, and that you only include the files, folders, processes, and process-opened files that are resulting in false positives.</span></span> <span data-ttu-id="3608c-233">此外，請務必定期查看您定義的排除專案。</span><span class="sxs-lookup"><span data-stu-id="3608c-233">In addition, make sure to review your defined exclusions regularly.</span></span> <span data-ttu-id="3608c-234">建議使用[Microsoft 端點管理員](/mem/endpoint-manager-overview)來定義或編輯您的防病毒排除專案。不過，您可以使用其他方法，例如[群組原則](/azure/active-directory-domain-services/manage-group-policy) (請參閱[管理 Microsoft Defender for Endpoint](manage-atp-post-migration.md)) 。</span><span class="sxs-lookup"><span data-stu-id="3608c-234">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to define or edit your antivirus exclusions; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

> [!TIP]
> <span data-ttu-id="3608c-235">需要防病毒排除的協助嗎？</span><span class="sxs-lookup"><span data-stu-id="3608c-235">Need help with antivirus exclusions?</span></span> <span data-ttu-id="3608c-236">請參閱[設定及驗證 Microsoft Defender 防毒軟體掃描的排除](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)專案。</span><span class="sxs-lookup"><span data-stu-id="3608c-236">See [Configure and validate exclusions for Microsoft Defender Antivirus scans](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-manage-antivirus-exclusions-for-existing-policies"></a><span data-ttu-id="3608c-237">使用 Microsoft 端點管理員管理現有原則的防病毒排除 () </span><span class="sxs-lookup"><span data-stu-id="3608c-237">Use Microsoft Endpoint Manager to manage antivirus exclusions (for existing policies)</span></span>

1. <span data-ttu-id="3608c-238">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-238">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="3608c-239">選擇 [ **Endpoint security**  >  **防病毒**]，然後選取現有的原則。</span><span class="sxs-lookup"><span data-stu-id="3608c-239">Choose **Endpoint security** > **Antivirus**, and then select an existing policy.</span></span> <span data-ttu-id="3608c-240"> (如果您沒有現有的原則，或是您想要建立新的原則，請跳至 [下一個](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions) 程式) 。</span><span class="sxs-lookup"><span data-stu-id="3608c-240">(If you don’t have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)).</span></span>

3. <span data-ttu-id="3608c-241">選擇 [ **屬性**]，然後選擇 [ **設定設定**] 旁的 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-241">Choose **Properties**, and next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="3608c-242">展開 **Microsoft Defender 防毒軟體排除** 專案，然後指定排除專案。</span><span class="sxs-lookup"><span data-stu-id="3608c-242">Expand **Microsoft Defender Antivirus Exclusions** and then specify your exclusions.</span></span>

5. <span data-ttu-id="3608c-243">選擇 [ **審閱 + 儲存**]，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-243">Choose **Review + save**, and then choose **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions"></a><span data-ttu-id="3608c-244">使用 Microsoft 端點管理員建立包含排除的新防病毒原則</span><span class="sxs-lookup"><span data-stu-id="3608c-244">Use Microsoft Endpoint Manager to create a new antivirus policy with exclusions</span></span>

1. <span data-ttu-id="3608c-245">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-245">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="3608c-246">選擇 [**安全性**  >  **防病毒**  >  **+ 建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-246">Choose **Endpoint security** > **Antivirus** > **+ Create Policy**.</span></span> 

3. <span data-ttu-id="3608c-247">選取平臺 (，例如 **Windows 10 和更新版本**、 **macOS**] 或 [ **Windows 10 及 Windows Server**) 。</span><span class="sxs-lookup"><span data-stu-id="3608c-247">Select a platform (such as **Windows 10 and later**, **macOS**, or **Windows 10 and Windows Server**).</span></span>

4. <span data-ttu-id="3608c-248">在 [**設定檔**] 中，選取 [ **Microsoft Defender 防毒軟體排除**]，然後選擇 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-248">For **Profile**, select **Microsoft Defender Antivirus exclusions**, and then choose **Create**.</span></span>

5. <span data-ttu-id="3608c-249">指定設定檔的名稱和描述，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3608c-249">Specify a name and description for the profile, and then choose **Next**.</span></span>

6. <span data-ttu-id="3608c-250">在 [ **設定設定** ] 索引標籤上，指定防病毒排除，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3608c-250">On the **Configuration settings** tab, specify your antivirus exclusions, and then choose **Next**.</span></span>

7. <span data-ttu-id="3608c-251">在 [ **範圍** 標籤] 索引標籤上，如果您在組織中使用範圍標記，請指定您要建立之原則的範圍標記。</span><span class="sxs-lookup"><span data-stu-id="3608c-251">On the **Scope tags** tab, if you are using scope tags in your organization, specify scope tags for the policy you are creating.</span></span> <span data-ttu-id="3608c-252"> (請參閱 [Scope tags](/mem/intune/fundamentals/scope-tags)。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-252">(See [Scope tags](/mem/intune/fundamentals/scope-tags).)</span></span>

8. <span data-ttu-id="3608c-253">在 [ **工作分派** ] 索引標籤上，指定應套用原則的使用者和群組，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3608c-253">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="3608c-254"> (如果您需要協助工作指派，請參閱[在 Microsoft Intune 中指派使用者和裝置設定檔](/mem/intune/configuration/device-profile-assign)。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-254">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

9. <span data-ttu-id="3608c-255">在 [ **複查 + 建立** ] 索引標籤上，複查設定，然後選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-255">On the **Review + create** tab, review the settings, and then choose **Create**.</span></span>

### <a name="indicators-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="3608c-256">Microsoft Defender for Endpoint 的標記</span><span class="sxs-lookup"><span data-stu-id="3608c-256">Indicators for Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="3608c-257">指標[ (特別](/microsoft-365/security/defender-endpoint/manage-indicators)、有損損或 IoCs) 可讓您的安全性作業小組定義實體的偵測、預防和排除。</span><span class="sxs-lookup"><span data-stu-id="3608c-257">[Indicators](/microsoft-365/security/defender-endpoint/manage-indicators) (specifically, indicators of compromise, or IoCs) enable your security operations team to define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="3608c-258">例如，您可以在 Microsoft Defender for Endpoint 中指定要省略的掃描和修正動作中的某些檔案。</span><span class="sxs-lookup"><span data-stu-id="3608c-258">For example, you can specify certain files to be omitted from scans and remediation actions in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3608c-259">您也可以使用指示器，針對特定的檔案、IP 位址或 URLs 產生警示。</span><span class="sxs-lookup"><span data-stu-id="3608c-259">Or, indicators can be used to generate alerts for certain files, IP addresses, or URLs.</span></span>

<span data-ttu-id="3608c-260">若要將實體指定為 Microsoft Defender for Endpoint 的排除專案，請為這些實體建立 "allow" 標記。</span><span class="sxs-lookup"><span data-stu-id="3608c-260">To specify entities as exclusions for Microsoft Defender for Endpoint, create "allow" indicators for those entities.</span></span> <span data-ttu-id="3608c-261">Microsoft Defender for Endpoint 中的這類「允許」指示器適用于 [下一代保護](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)、 [端點偵測和回應](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)，以及 [自動調查 & 修復](/microsoft-365/security/defender-endpoint/automated-investigations)。</span><span class="sxs-lookup"><span data-stu-id="3608c-261">Such "allow" indicators in Microsoft Defender for Endpoint apply to [next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), [endpoint detection and response](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response), and [automated investigation & remediation](/microsoft-365/security/defender-endpoint/automated-investigations).</span></span>

<span data-ttu-id="3608c-262">可為下列專案建立 "Allow" 指示器：</span><span class="sxs-lookup"><span data-stu-id="3608c-262">"Allow" indicators can be created for:</span></span>

- [<span data-ttu-id="3608c-263">Files</span><span class="sxs-lookup"><span data-stu-id="3608c-263">Files</span></span>](#indicators-for-files)
- [<span data-ttu-id="3608c-264">IP 位址、URLs 及網域</span><span class="sxs-lookup"><span data-stu-id="3608c-264">IP addresses, URLs, and domains</span></span>](#indicators-for-ip-addresses-urls-or-domains)
- [<span data-ttu-id="3608c-265">應用程式憑證</span><span class="sxs-lookup"><span data-stu-id="3608c-265">Application certificates</span></span>](#indicators-for-application-certificates)

![指示器類型圖表](images/false-positives-indicators.png)

#### <a name="indicators-for-files"></a><span data-ttu-id="3608c-267">檔標記</span><span class="sxs-lookup"><span data-stu-id="3608c-267">Indicators for files</span></span>

<span data-ttu-id="3608c-268">當您為檔案 [（例如可執行檔）建立「允許」指示器](/microsoft-365/security/defender-endpoint/indicator-file)時，它會協助防止您的組織所使用的檔案遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="3608c-268">When you [create an "allow" indicator for a file, such as an executable](/microsoft-365/security/defender-endpoint/indicator-file), it helps prevent files that your organization is using from being blocked.</span></span> <span data-ttu-id="3608c-269">檔案可以包含可遷移的可執行檔 (PE) 檔案，例如 `.exe` 和 `.dll` files。</span><span class="sxs-lookup"><span data-stu-id="3608c-269">Files can include portable executable (PE) files, such as `.exe` and `.dll` files.</span></span> 

<span data-ttu-id="3608c-270">在您為檔案建立指示器之前，請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="3608c-270">Before you create indicators for files, make sure the following requirements are met:</span></span>
- <span data-ttu-id="3608c-271">已啟用以雲端式保護方式設定 Microsoft Defender 防毒軟體 (請參閱[管理雲端型保護](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)) </span><span class="sxs-lookup"><span data-stu-id="3608c-271">Microsoft Defender Antivirus is configured with cloud-based protection enabled (see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus))</span></span>
- <span data-ttu-id="3608c-272">反惡意軟體用戶端版本為4.18.1901 或更新版本</span><span class="sxs-lookup"><span data-stu-id="3608c-272">Antimalware client version is 4.18.1901.x or later</span></span> 
- <span data-ttu-id="3608c-273">裝置執行 Windows 10，版本1703或更新版本;Windows Server 2016;或 Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3608c-273">Devices are running Windows 10, version 1703 or later; Windows Server 2016; or Windows Server 2019</span></span> 
- <span data-ttu-id="3608c-274">[已開啟組塊或 allow 功能](/microsoft-365/security/defender-endpoint/advanced-features)</span><span class="sxs-lookup"><span data-stu-id="3608c-274">The [Block or allow feature is turned on](/microsoft-365/security/defender-endpoint/advanced-features)</span></span> 

#### <a name="indicators-for-ip-addresses-urls-or-domains"></a><span data-ttu-id="3608c-275">IP 位址、URLs 或網域的標記</span><span class="sxs-lookup"><span data-stu-id="3608c-275">Indicators for IP addresses, URLs, or domains</span></span>

<span data-ttu-id="3608c-276">當您 [為 IP 位址、URL 或網域建立「允許」指示器](/microsoft-365/security/defender-endpoint/indicator-ip-domain)時，它有助於防止組織使用的網站或 IP 位址遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="3608c-276">When you [create an "allow" indicator for an IP address, URL, or domain](/microsoft-365/security/defender-endpoint/indicator-ip-domain), it helps prevent the sites or IP addresses your organization uses from being blocked.</span></span>

<span data-ttu-id="3608c-277">在您為 IP 位址、URLs 或網域建立指示器之前，請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="3608c-277">Before you create indicators for IP addresses, URLs, or domains, make sure the following requirements are met:</span></span>
- <span data-ttu-id="3608c-278">已在封鎖模式中啟用在 Defender for Endpoint 中的網路保護 (請參閱 [Enable network protection](/microsoft-365/security/defender-endpoint/enable-network-protection)) </span><span class="sxs-lookup"><span data-stu-id="3608c-278">Network protection in Defender for Endpoint is enabled in block mode (see [Enable network protection](/microsoft-365/security/defender-endpoint/enable-network-protection))</span></span>
- <span data-ttu-id="3608c-279">反惡意軟體用戶端版本為4.18.1906 或更新版本</span><span class="sxs-lookup"><span data-stu-id="3608c-279">Antimalware client version is 4.18.1906.x or later</span></span> 
- <span data-ttu-id="3608c-280">裝置執行 Windows 10、版本1709或更新版本）</span><span class="sxs-lookup"><span data-stu-id="3608c-280">Devices are running Windows 10, version 1709, or later</span></span> 

<span data-ttu-id="3608c-281">在 Microsoft Defender 資訊安全中心中開啟自訂網路指示器 (請參閱[高級功能](/microsoft-365/security/defender-endpoint/advanced-features)) </span><span class="sxs-lookup"><span data-stu-id="3608c-281">Custom network indicators are turned on in the Microsoft Defender Security Center (see [Advanced features](/microsoft-365/security/defender-endpoint/advanced-features))</span></span>   

#### <a name="indicators-for-application-certificates"></a><span data-ttu-id="3608c-282">應用程式憑證的標記</span><span class="sxs-lookup"><span data-stu-id="3608c-282">Indicators for application certificates</span></span> 

<span data-ttu-id="3608c-283">當您 [為應用程式憑證建立「允許」指示器](/microsoft-365/security/defender-endpoint/indicator-certificates)時，它可協助防止組織使用的應用程式（例如內部開發的應用程式）遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="3608c-283">When you [create an "allow" indicator for an application certificate](/microsoft-365/security/defender-endpoint/indicator-certificates), it helps prevent applications, such as internally developed applications, that your organization uses from being blocked.</span></span> <span data-ttu-id="3608c-284">`.CER``.PEM`支援副檔名或副檔名。</span><span class="sxs-lookup"><span data-stu-id="3608c-284">`.CER` or `.PEM` file extensions are supported.</span></span>   

<span data-ttu-id="3608c-285">在您建立應用程式憑證的指示器之前，請確定符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="3608c-285">Before you create indicators for application certificates, make sure the following requirements are met:</span></span>
- <span data-ttu-id="3608c-286">已啟用以雲端式保護方式設定 Microsoft Defender 防毒軟體 (請參閱[管理雲端型保護](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)) </span><span class="sxs-lookup"><span data-stu-id="3608c-286">Microsoft Defender Antivirus is configured with cloud-based protection enabled (see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus))</span></span>
- <span data-ttu-id="3608c-287">反惡意軟體用戶端版本為4.18.1901 或更新版本</span><span class="sxs-lookup"><span data-stu-id="3608c-287">Antimalware client version is 4.18.1901.x or later</span></span> 
- <span data-ttu-id="3608c-288">裝置執行 Windows 10，版本1703或更新版本;Windows Server 2016;或 Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3608c-288">Devices are running Windows 10, version 1703 or later; Windows Server 2016; or Windows Server 2019</span></span> 
- <span data-ttu-id="3608c-289">病毒和威脅防護定義是最新的</span><span class="sxs-lookup"><span data-stu-id="3608c-289">Virus and threat protection definitions are up to date</span></span>  

> [!TIP]
> <span data-ttu-id="3608c-290">當您建立指示器時，您可以逐個定義它們，也可以一次匯入多個專案。</span><span class="sxs-lookup"><span data-stu-id="3608c-290">When you create indicators, you can define them one by one, or import multiple items at once.</span></span> <span data-ttu-id="3608c-291">請記住，單一承租人的限制為15000標記。</span><span class="sxs-lookup"><span data-stu-id="3608c-291">Keep in mind there's a limit of 15,000 indicators for a single tenant.</span></span> <span data-ttu-id="3608c-292">而且，您可能需要先收集特定詳細資料，例如檔案雜湊資訊。</span><span class="sxs-lookup"><span data-stu-id="3608c-292">And, you might need to gather certain details first, such as file hash information.</span></span> <span data-ttu-id="3608c-293">請務必先檢查必要條件，再 [建立指示器](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="3608c-293">Make sure to review the prerequisites before you [create indicators](manage-indicators.md).</span></span> 

## <a name="part-4-submit-a-file-for-analysis"></a><span data-ttu-id="3608c-294">第4部分：提交檔案以進行分析</span><span class="sxs-lookup"><span data-stu-id="3608c-294">Part 4: Submit a file for analysis</span></span>

<span data-ttu-id="3608c-295">您可以將實體（例如檔案和 fileless 偵測）提交給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="3608c-295">You can submit entities, such as files and fileless detections, to Microsoft for analysis.</span></span> <span data-ttu-id="3608c-296">Microsoft security 研究員會分析所有提交，其結果會協助通知 Microsoft Defender 進行端點威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="3608c-296">Microsoft security researchers analyze all submissions, and their results help inform Microsoft Defender for Endpoint threat protection capabilities.</span></span> <span data-ttu-id="3608c-297">當您在提交網站登入時，您可以追蹤您的提交。</span><span class="sxs-lookup"><span data-stu-id="3608c-297">When you sign in at the submission site, you can track your submissions.</span></span>

### <a name="submit-a-file-for-analysis"></a><span data-ttu-id="3608c-298">提交檔案以進行分析</span><span class="sxs-lookup"><span data-stu-id="3608c-298">Submit a file for analysis</span></span>

<span data-ttu-id="3608c-299">如果您有錯誤偵測為惡意或已錯過的檔案，請遵循下列步驟提交檔案進行分析。</span><span class="sxs-lookup"><span data-stu-id="3608c-299">If you have a file that was either wrongly detected as malicious or was missed, follow these steps to submit the file for analysis.</span></span>

1. <span data-ttu-id="3608c-300">請參閱此處的指導方針： [提交檔案以進行分析](/windows/security/threat-protection/intelligence/submission-guide)。</span><span class="sxs-lookup"><span data-stu-id="3608c-300">Review the guidelines here: [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="3608c-301">流覽 Microsoft 安全情報提交網站 ([https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission)) ，並提交您的檔案 (s) 。</span><span class="sxs-lookup"><span data-stu-id="3608c-301">Visit the Microsoft Security Intelligence submission site ([https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission)), and submit your file(s).</span></span>

### <a name="submit-a-fileless-detection-for-analysis"></a><span data-ttu-id="3608c-302">提交 fileless 偵測以供分析</span><span class="sxs-lookup"><span data-stu-id="3608c-302">Submit a fileless detection for analysis</span></span>

<span data-ttu-id="3608c-303">如果偵測到某項專案是以惡意程式碼為基礎，而且您沒有檔案，您可以提交檔案 `Mpsupport.cab` 進行分析。</span><span class="sxs-lookup"><span data-stu-id="3608c-303">If something was detected as malware based on behavior, and you don’t have a file, you can submit your `Mpsupport.cab` file for analysis.</span></span> <span data-ttu-id="3608c-304">您可以在 Windows 10 上使用 Microsoft 惡意程式碼保護 Command-Line 公用程式 (MPCmdRun.exe) 工具，取得 *.cab* 檔案。</span><span class="sxs-lookup"><span data-stu-id="3608c-304">You can get the *.cab* file by using the Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) tool on Windows 10.</span></span>

1.  <span data-ttu-id="3608c-305">移至 ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` ，然後 `MpCmdRun.exe` 以系統管理員身分執行。</span><span class="sxs-lookup"><span data-stu-id="3608c-305">Go to ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`, and then run `MpCmdRun.exe` as an administrator.</span></span>

2.  <span data-ttu-id="3608c-306">類型 `mpcmdrun.exe -GetFiles` ，然後按 **enter**。</span><span class="sxs-lookup"><span data-stu-id="3608c-306">Type `mpcmdrun.exe -GetFiles`, and then press **Enter**.</span></span>
   <span data-ttu-id="3608c-307">會產生包含各種診斷記錄檔的 .cab 檔。</span><span class="sxs-lookup"><span data-stu-id="3608c-307">A .cab file is generated that contains various diagnostic logs.</span></span> <span data-ttu-id="3608c-308">檔案的位置會在命令提示字元的輸出中指定。</span><span class="sxs-lookup"><span data-stu-id="3608c-308">The location of the file is specified in the output of the command prompt.</span></span> <span data-ttu-id="3608c-309">根據預設，位置是 `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` 。</span><span class="sxs-lookup"><span data-stu-id="3608c-309">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

3.  <span data-ttu-id="3608c-310">請參閱此處的指導方針： [提交檔案以進行分析](/windows/security/threat-protection/intelligence/submission-guide)。</span><span class="sxs-lookup"><span data-stu-id="3608c-310">Review the guidelines here: [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

4.  <span data-ttu-id="3608c-311">流覽 Microsoft 安全情報提交網站 ([https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission)) ，然後提交您的 .cab 檔案。</span><span class="sxs-lookup"><span data-stu-id="3608c-311">Visit the Microsoft Security Intelligence submission site ([https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission)), and submit your .cab files.</span></span>

### <a name="what-happens-after-a-file-is-submitted"></a><span data-ttu-id="3608c-312">提交檔後會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="3608c-312">What happens after a file is submitted?</span></span>

<span data-ttu-id="3608c-313">您的提交會立即由我們的系統進行掃描，以在分析員開始處理您的案例之前，為您提供最新的決定。</span><span class="sxs-lookup"><span data-stu-id="3608c-313">Your submission is immediately scanned by our systems to give you the latest determination even before an analyst starts handling your case.</span></span> <span data-ttu-id="3608c-314">檔可能已由分析員提交並處理。</span><span class="sxs-lookup"><span data-stu-id="3608c-314">It’s possible that a file might have already been submitted and processed by an analyst.</span></span> <span data-ttu-id="3608c-315">在這種情況下，會很快進行判斷。</span><span class="sxs-lookup"><span data-stu-id="3608c-315">In those cases, a determination is made quickly.</span></span>

<span data-ttu-id="3608c-316">對於尚未處理的報送，會依照下列方式進行分析的優先順序：</span><span class="sxs-lookup"><span data-stu-id="3608c-316">For submissions that were not already processed, they are prioritized for analysis as follows:</span></span>

- <span data-ttu-id="3608c-317">可能影響大量電腦的流行檔案會獲得較高的優先順序。</span><span class="sxs-lookup"><span data-stu-id="3608c-317">Prevalent files with the potential to impact large numbers of computers are given a higher priority.</span></span>
- <span data-ttu-id="3608c-318">已驗證的客戶，尤其是具有有效 [軟體保證 IDs (SAIDs) ](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx)中的企業客戶，都具有較高的優先順序。</span><span class="sxs-lookup"><span data-stu-id="3608c-318">Authenticated customers, especially enterprise customers with valid [Software Assurance IDs (SAIDs)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx), are given a higher priority.</span></span>
- <span data-ttu-id="3608c-319">被稱為「持有者」標為高優先順序的報送會立即注意。</span><span class="sxs-lookup"><span data-stu-id="3608c-319">Submissions flagged as high priority by SAID holders are given immediate attention.</span></span>

<span data-ttu-id="3608c-320">若要檢查有關您提交的更新，請在[Microsoft 安全情報提交網站](https://www.microsoft.com/wdsi/filesubmission)上登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-320">To check for updates regarding your submission, sign in at the [Microsoft Security Intelligence submission site](https://www.microsoft.com/wdsi/filesubmission).</span></span> 

> [!TIP]
> <span data-ttu-id="3608c-321">若要深入瞭解，請參閱 [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions)。</span><span class="sxs-lookup"><span data-stu-id="3608c-321">To learn more, see [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions).</span></span>

## <a name="part-5-review-and-adjust-your-threat-protection-settings"></a><span data-ttu-id="3608c-322">第5部分：檢查並調整威脅防護設定</span><span class="sxs-lookup"><span data-stu-id="3608c-322">Part 5: Review and adjust your threat protection settings</span></span>

<span data-ttu-id="3608c-323">Microsoft Defender for Endpoint 提供各種各樣的選項，包括微調各種功能及功能的設定的功能。</span><span class="sxs-lookup"><span data-stu-id="3608c-323">Microsoft Defender for Endpoint offers a wide variety of options, including the ability to fine-tune settings for various features and capabilities.</span></span> <span data-ttu-id="3608c-324">如果您收到大量的誤報，請務必檢查您組織的威脅防護設定。</span><span class="sxs-lookup"><span data-stu-id="3608c-324">If you’re getting numerous false positives, make sure to review your organization’s threat protection settings.</span></span> <span data-ttu-id="3608c-325">您可能需要進行一些調整：</span><span class="sxs-lookup"><span data-stu-id="3608c-325">You might need to make some adjustments to:</span></span>

- [<span data-ttu-id="3608c-326">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="3608c-326">Cloud-delivered protection</span></span>](#cloud-delivered-protection)
- [<span data-ttu-id="3608c-327">可能有害之應用程式的修復</span><span class="sxs-lookup"><span data-stu-id="3608c-327">Remediation for potentially unwanted applications</span></span>](#remediation-for-potentially-unwanted-applications)
- [<span data-ttu-id="3608c-328">自動化調查和修正</span><span class="sxs-lookup"><span data-stu-id="3608c-328">Automated investigation and remediation</span></span>](#automated-investigation-and-remediation)

### <a name="cloud-delivered-protection"></a><span data-ttu-id="3608c-329">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="3608c-329">Cloud-delivered protection</span></span>

<span data-ttu-id="3608c-330">檢查您的雲端提供的保護層級 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="3608c-330">Check your cloud-delivered protection level for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="3608c-331">根據預設，已將雲端傳送保護設定為 [ **未** 設定]，這會對應至大多陣列織的一般保護層級。</span><span class="sxs-lookup"><span data-stu-id="3608c-331">By default, cloud-delivered protection is set to **Not configured**, which corresponds to a normal level of protection for most organizations.</span></span> <span data-ttu-id="3608c-332">如果您的雲端傳送保護設定為 **高**、 **高 +** 或零的 **容錯**，您可能會遇到較高的誤報數目。</span><span class="sxs-lookup"><span data-stu-id="3608c-332">If your cloud-delivered protection is set to **High**, **High +**, or **Zero tolerance**, you might experience a higher number of false positives.</span></span>

> [!TIP]
> <span data-ttu-id="3608c-333">若要深入瞭解設定雲端提供的保護，請參閱 [指定雲端提供的保護層級](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="3608c-333">To learn more about configuring your cloud-delivered protection, see [Specify the cloud-delivered protection level](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="3608c-334">建議使用[Microsoft 端點管理員](/mem/endpoint-manager-overview)來編輯或設定您的雲端提供的保護設定。不過，您可以使用其他方法，例如[群組原則](/azure/active-directory-domain-services/manage-group-policy) (請參閱[管理 Microsoft Defender for Endpoint](manage-atp-post-migration.md)) 。</span><span class="sxs-lookup"><span data-stu-id="3608c-334">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to edit or set your cloud-delivered protection settings; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-review-and-edit-cloud-delivered-protection-settings-for-existing-policies"></a><span data-ttu-id="3608c-335">使用 Microsoft 端點管理員複查及編輯現有原則的雲端傳送保護設定 () </span><span class="sxs-lookup"><span data-stu-id="3608c-335">Use Microsoft Endpoint Manager to review and edit cloud-delivered protection settings (for existing policies)</span></span>

1. <span data-ttu-id="3608c-336">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-336">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="3608c-337">選擇 [ **Endpoint security**  >  **防病毒**]，然後選取現有的原則。</span><span class="sxs-lookup"><span data-stu-id="3608c-337">Choose **Endpoint security** > **Antivirus** and then select an existing policy.</span></span> <span data-ttu-id="3608c-338"> (如果您沒有現有的原則，或是您想要建立新的原則，請跳至 [下一個](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy) 程式) 。</span><span class="sxs-lookup"><span data-stu-id="3608c-338">(If you don’t have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)).</span></span>

3. <span data-ttu-id="3608c-339">在 [ **管理**] 下，選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-339">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="3608c-340">然後，選擇 [ **設定設定**] 旁的 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-340">Then, next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="3608c-341">展開 [ **cloud protection**]，並在 [ **雲端提供的保護層級** ] 列中查看您目前的設定。</span><span class="sxs-lookup"><span data-stu-id="3608c-341">Expand **Cloud protection**, and review your current setting in the **Cloud-delivered protection level** row.</span></span> <span data-ttu-id="3608c-342">建議您將雲端提供的保護設定為 [ **未設定**]，這樣可提供強大的保護，同時減少接收誤報的機率。</span><span class="sxs-lookup"><span data-stu-id="3608c-342">We recommend setting cloud-delivered protection to **Not configured**, which provides strong protection while reducing the chances of getting false positives.</span></span>

5. <span data-ttu-id="3608c-343">選擇 [複查] 和 [ **儲存**]，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-343">Choose **Review + save**, and then **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy"></a><span data-ttu-id="3608c-344">使用 Microsoft 端點管理員設定新原則的雲端傳送保護設定 () </span><span class="sxs-lookup"><span data-stu-id="3608c-344">Use Microsoft Endpoint Manager to set cloud-delivered protection settings (for a new policy)</span></span>

1. <span data-ttu-id="3608c-345">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-345">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="3608c-346">選擇 [**安全性**  >  **防病毒**  >  **+ 建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-346">Choose **Endpoint security** > **Antivirus** > **+ Create policy**.</span></span>

3. <span data-ttu-id="3608c-347">在 [**平臺**] 中，選取選項，然後針對 [**設定檔**]，選取 [**防病毒** 或 **Microsoft Defender 防毒軟體** (特定選項取決於您為 **Platform** 選取的專案。 ) 然後選擇 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-347">For **Platform**, select an option, and then for **Profile**, select **Antivirus** or **Microsoft Defender Antivirus** (the specific option depends on what you selected for **Platform**.) Then choose **Create**.</span></span>

4. <span data-ttu-id="3608c-348">在 [ **基礎** ] 索引標籤上，指定原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="3608c-348">On the **Basics** tab, specify a name and description for the policy.</span></span> <span data-ttu-id="3608c-349">接著選擇 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="3608c-349">Then choose **Next**.</span></span>

5. <span data-ttu-id="3608c-350">在 [ **設定設定** ] 索引標籤上，展開 [ **Cloud protection**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="3608c-350">On the **Configuration settings** tab, expand **Cloud protection**, and specify the following settings:</span></span>
   - <span data-ttu-id="3608c-351">將 **雲端傳送保護開啟** 為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="3608c-351">Set **Turn on cloud-delivered protection** to **Yes**.</span></span>
   - <span data-ttu-id="3608c-352">將 **[雲端式保護層級]** 設定為 **[未設定]**。</span><span class="sxs-lookup"><span data-stu-id="3608c-352">Set **Cloud-delivered protection level** to **Not configured**.</span></span> <span data-ttu-id="3608c-353"> (此層級預設會提供強層級的保護，同時降低取得誤報的機率。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-353">(This level provides a strong level of protection by default while reducing the chances of getting false positives.)</span></span>

6. <span data-ttu-id="3608c-354">在 [ **範圍** 標籤] 索引標籤上，如果您在組織中使用範圍標記，請指定原則的範圍標記。</span><span class="sxs-lookup"><span data-stu-id="3608c-354">On the **Scope tags** tab, if you are using scope tags in your organization, specify scope tags for the policy.</span></span> <span data-ttu-id="3608c-355"> (請參閱 [Scope tags](/mem/intune/fundamentals/scope-tags)。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-355">(See [Scope tags](/mem/intune/fundamentals/scope-tags).)</span></span>

7. <span data-ttu-id="3608c-356">在 [ **工作分派** ] 索引標籤上，指定應套用原則的使用者和群組，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3608c-356">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="3608c-357"> (如果您需要協助工作指派，請參閱[在 Microsoft Intune 中指派使用者和裝置設定檔](/mem/intune/configuration/device-profile-assign)。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-357">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

8. <span data-ttu-id="3608c-358">在 [ **複查 + 建立** ] 索引標籤上，複查設定，然後選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-358">On the **Review + create** tab, review the settings, and then choose **Create**.</span></span>  

### <a name="remediation-for-potentially-unwanted-applications"></a><span data-ttu-id="3608c-359">可能有害之應用程式的修復</span><span class="sxs-lookup"><span data-stu-id="3608c-359">Remediation for potentially unwanted applications</span></span>

<span data-ttu-id="3608c-360">可能有害的應用程式 (PUA) 是一種軟體類別，可導致裝置執行緩慢、顯示未預期的廣告，或是安裝可能是意外或不需要的其他軟體。</span><span class="sxs-lookup"><span data-stu-id="3608c-360">Potentially unwanted applications (PUA) are a category of software that can cause devices to run slowly, display unexpected ads, or install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="3608c-361">PUA 的範例包括廣告軟體、搭售軟體，以及與安全性產品行為不同的規避軟體。</span><span class="sxs-lookup"><span data-stu-id="3608c-361">Examples of PUA include advertising software, bundling software, and evasion software that behaves differently with security products.</span></span> <span data-ttu-id="3608c-362">雖然 PUA 不會被視為惡意程式碼，但某些類型的軟體會根據其行為和信譽而 PUA。</span><span class="sxs-lookup"><span data-stu-id="3608c-362">Although PUA is not considered malware, some kinds of software are PUA based on their behavior and reputation.</span></span>

> [!TIP]
> <span data-ttu-id="3608c-363">若要深入瞭解 PUA，請參閱偵測 [和封鎖可能不需要的應用程式](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="3608c-363">To learn more about PUA, see [Detect and block potentially unwanted applications](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus).</span></span>
 
<span data-ttu-id="3608c-364">視您的組織使用的應用程式而定，您可能會因為 PUA 保護設定而取得誤報。</span><span class="sxs-lookup"><span data-stu-id="3608c-364">Depending on the apps your organization is using, you might be getting false positives as a result of your PUA protection settings.</span></span> <span data-ttu-id="3608c-365">如有必要，請考慮在稽核模式中執行 PUA 保護一段時間，或將 PUA protection 套用至組織中裝置的子集。</span><span class="sxs-lookup"><span data-stu-id="3608c-365">If necessary, consider running PUA protection in audit mode for a while, or apply PUA protection to a subset of devices in your organization.</span></span> <span data-ttu-id="3608c-366">您可以為 Microsoft Edge 瀏覽器及 Microsoft Defender 防毒軟體設定 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="3608c-366">PUA protection can be configured for the Microsoft Edge browser and for Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="3608c-367">建議使用[Microsoft 端點管理員](/mem/endpoint-manager-overview)來編輯或設定 PUA 保護設定;不過，您可以使用其他方法，例如[群組原則](/azure/active-directory-domain-services/manage-group-policy) (請參閱[管理 Microsoft Defender for Endpoint](manage-atp-post-migration.md)) 。</span><span class="sxs-lookup"><span data-stu-id="3608c-367">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to edit or set PUA protection settings; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-edit-pua-protection-for-existing-configuration-profiles"></a><span data-ttu-id="3608c-368">使用 Microsoft 端點管理員編輯現有設定設定檔的 PUA 保護 () </span><span class="sxs-lookup"><span data-stu-id="3608c-368">Use Microsoft Endpoint Manager to edit PUA protection (for existing configuration profiles)</span></span>

1. <span data-ttu-id="3608c-369">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-369">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="3608c-370">選擇 [**裝置** 設定  >  **設定檔**]，然後選取現有的原則。</span><span class="sxs-lookup"><span data-stu-id="3608c-370">Choose **Devices** > **Configuration profiles**, and then select an existing policy.</span></span> <span data-ttu-id="3608c-371"> (如果您沒有現有的原則，或是您想要建立新的原則，請跳至 [下一個](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile)程式。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-371">(If you don’t have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile).)</span></span>

3. <span data-ttu-id="3608c-372">在 [ **管理**] 下 **，選擇 [** 內容]，然後按一下 [ **設定設定**] 旁的 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-372">Under **Manage**, choose **Properties**, and then, next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="3608c-373">在 [**設定設定**] 索引標籤上，向下滾動並展開 **Microsoft Defender 防毒軟體**。</span><span class="sxs-lookup"><span data-stu-id="3608c-373">On the **Configuration settings** tab, scroll down and expand **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="3608c-374">將 [偵測 **可能有害的應用程式** ] 設定為 [ **審計**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-374">Set **Detect potentially unwanted applications** to **Audit**.</span></span> <span data-ttu-id="3608c-375"> (您可以將它關閉，但透過使用「稽核模式」，您就能看到偵測。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-375">(You can turn it off, but by using audit mode, you will be able to see detections.)</span></span>

6. <span data-ttu-id="3608c-376">選擇 [ **審閱 + 儲存**]，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-376">Choose **Review + save**, and then choose **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile"></a><span data-ttu-id="3608c-377">使用 Microsoft 端點管理員設定新設定設定檔的 PUA 保護 () </span><span class="sxs-lookup"><span data-stu-id="3608c-377">Use Microsoft Endpoint Manager to set PUA protection (for a new configuration profile)</span></span>

1. <span data-ttu-id="3608c-378">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-378">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="3608c-379">選擇 [**裝置**  >  **設定檔**]  >  **+ [建立設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-379">Choose **Devices** > **Configuration profiles** > **+ Create profile**.</span></span>

3. <span data-ttu-id="3608c-380">針對 [**平臺**]，選擇 [ **Windows 10 和更新版本**]，然後針對 [**設定檔**] 選取 [**裝置限制**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-380">For the **Platform**, choose **Windows 10 and later**, and for **Profile**, select **Device restrictions**.</span></span>

4. <span data-ttu-id="3608c-381">在 [ **基礎** ] 索引標籤上，指定原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="3608c-381">On the **Basics** tab, specify a name and description for your policy.</span></span> <span data-ttu-id="3608c-382">接著選擇 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="3608c-382">Then choose **Next**.</span></span>

5. <span data-ttu-id="3608c-383">在 [**設定設定**] 索引標籤上，向下滾動並展開 **Microsoft Defender 防毒軟體**。</span><span class="sxs-lookup"><span data-stu-id="3608c-383">On the **Configuration settings** tab, scroll down and expand **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="3608c-384">設定 [偵測 **可能有害的應用程式** 進行 **審計**]，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3608c-384">Set **Detect potentially unwanted applications** to **Audit**, and then choose **Next**.</span></span> <span data-ttu-id="3608c-385"> (您可以關閉 PUA 保護，但透過使用稽核模式，您就可以看到偵測。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-385">(You can turn off PUA protection, but by using audit mode, you will be able to see detections.)</span></span>

7. <span data-ttu-id="3608c-386">在 [ **工作分派** ] 索引標籤上，指定應套用原則的使用者和群組，然後選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3608c-386">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="3608c-387"> (如果您需要協助工作指派，請參閱[在 Microsoft Intune 中指派使用者和裝置設定檔](/mem/intune/configuration/device-profile-assign)。 ) </span><span class="sxs-lookup"><span data-stu-id="3608c-387">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

8. <span data-ttu-id="3608c-388">在 [ **適用性規則** ] 索引標籤上，指定要包含或排除的原則中的 OS 版本。</span><span class="sxs-lookup"><span data-stu-id="3608c-388">On the **Applicability Rules** tab, specify the OS editions or versions to include or exclude from the policy.</span></span> <span data-ttu-id="3608c-389">例如，您可以設定原則套用至所有的裝置 Windows 10 的某些版本。</span><span class="sxs-lookup"><span data-stu-id="3608c-389">For example, you can set the policy to be applied to all devices certain editions of Windows 10.</span></span> <span data-ttu-id="3608c-390">接著選擇 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="3608c-390">Then choose **Next**.</span></span>

9. <span data-ttu-id="3608c-391">在 [ **複查 + 建立** ] 索引標籤上，複查您的設定，然後選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-391">On the **Review + create** tab, review your settings, and, and then choose **Create**.</span></span>

### <a name="automated-investigation-and-remediation"></a><span data-ttu-id="3608c-392">自動化調查與補救措施</span><span class="sxs-lookup"><span data-stu-id="3608c-392">Automated investigation and remediation</span></span>

<span data-ttu-id="3608c-393">[自動調查和修正](automated-investigations.md) (AIR) 功能是專門用來檢查警示，並立即採取行動以解決違規行為。</span><span class="sxs-lookup"><span data-stu-id="3608c-393">[Automated investigation and remediation](automated-investigations.md) (AIR) capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="3608c-394">在觸發警示時，自動調查執行時，會針對每個證據調查產生一個判定。</span><span class="sxs-lookup"><span data-stu-id="3608c-394">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="3608c-395">Verdicts 可能是 *惡意*、 *可疑* 或 *沒有發現威脅*。</span><span class="sxs-lookup"><span data-stu-id="3608c-395">Verdicts can be *Malicious*, *Suspicious*, or *No threats found*.</span></span> 

<span data-ttu-id="3608c-396">根據您組織的 [自動化設定層級](/microsoft-365/security/defender-endpoint/automation-levels) 及其他安全性設定，對被視為 *惡意* 或 *可疑* 的偽像採取修正動作。</span><span class="sxs-lookup"><span data-stu-id="3608c-396">Depending on the [level of automation](/microsoft-365/security/defender-endpoint/automation-levels) set for your organization and other security settings, remediation actions are taken on artifacts that are considered to be *Malicious* or *Suspicious*.</span></span> <span data-ttu-id="3608c-397">在某些情況下，會自動進行修正動作;在其他情況下，修復動作會以手動方式取得，或是只在您的安全操作小組核准時進行。</span><span class="sxs-lookup"><span data-stu-id="3608c-397">In some cases, remediation actions occur automatically; in other cases, remediation actions are taken manually or only upon approval by your security operations team.</span></span> 

- <span data-ttu-id="3608c-398">[深入瞭解自動化層級](/microsoft-365/security/defender-endpoint/automation-levels);然後</span><span class="sxs-lookup"><span data-stu-id="3608c-398">[Learn more about automation levels](/microsoft-365/security/defender-endpoint/automation-levels); and then</span></span> 
- <span data-ttu-id="3608c-399">[在 Defender For Endpoint 中設定 AIR 功能](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation)。</span><span class="sxs-lookup"><span data-stu-id="3608c-399">[Configure AIR capabilities in Defender for Endpoint](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3608c-400">建議使用 *完整的自動化* ，以進行自動調查和修復。</span><span class="sxs-lookup"><span data-stu-id="3608c-400">We recommend using *Full automation* for automated investigation and remediation.</span></span> <span data-ttu-id="3608c-401">請勿關閉這些功能，因為是誤報。</span><span class="sxs-lookup"><span data-stu-id="3608c-401">Don't turn these capabilities off because of a false positive.</span></span> <span data-ttu-id="3608c-402">相反地，使用 ["allow" 標記來定義例外](#indicators-for-microsoft-defender-for-endpoint)狀況，並將自動調查和修正設定為自動採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="3608c-402">Instead, use ["allow" indicators to define exceptions](#indicators-for-microsoft-defender-for-endpoint), and keep automated investigation and remediation set to take appropriate actions automatically.</span></span> <span data-ttu-id="3608c-403">遵循 [此指南](automation-levels.md#levels-of-automation) 可協助減少您的安全作業小組必須處理的提醒數目。</span><span class="sxs-lookup"><span data-stu-id="3608c-403">Following [this guidance](automation-levels.md#levels-of-automation) helps reduce the number of alerts your security operations team must handle.</span></span> 

## <a name="still-need-help"></a><span data-ttu-id="3608c-404">仍需要協助嗎？</span><span class="sxs-lookup"><span data-stu-id="3608c-404">Still need help?</span></span>

<span data-ttu-id="3608c-405">如果您已完成本文中的所有步驟，但仍需要協助，請與技術支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="3608c-405">If you have worked through all the steps in this article and still need help, contact technical support.</span></span>

1. <span data-ttu-id="3608c-406">移至 Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3608c-406">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="3608c-407">在右上角，選取 [問號] (**？**) ]，然後選取 [ **Microsoft 支援**]。</span><span class="sxs-lookup"><span data-stu-id="3608c-407">In the upper right corner, select the question mark (**?**), and then select **Microsoft support**.</span></span>

3. <span data-ttu-id="3608c-408">在 [ **支援助理** ] 視窗中，描述您的問題，然後傳送您的郵件。</span><span class="sxs-lookup"><span data-stu-id="3608c-408">In the **Support Assistant** window, describe your issue, and then send your message.</span></span> <span data-ttu-id="3608c-409">您可以從那裡開啟服務要求。</span><span class="sxs-lookup"><span data-stu-id="3608c-409">From there, you can open a service request.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3608c-410">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3608c-410">See also</span></span>

[<span data-ttu-id="3608c-411">管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3608c-411">Manage Microsoft Defender for Endpoint</span></span>](manage-atp-post-migration.md)

[<span data-ttu-id="3608c-412">Microsoft Defender 資訊安全中心概觀</span><span class="sxs-lookup"><span data-stu-id="3608c-412">Overview of Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use) 
