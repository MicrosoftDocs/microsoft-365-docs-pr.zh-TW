---
title: 在 Microsoft 365 Defender 中處理空氣中的誤報或漏報
description: Microsoft 365 Defender 中的 AIR 是否已錯過或錯誤地偵測到什麼？ 瞭解如何將誤報或錯誤否定提交給 Microsoft 進行分析。
keywords: 自動化，調查，警示，修正，誤報，false 負數
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 851fd05f0fec4b8d113e515783092eed0114db0f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199110"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="00d6a-105">在自動化調查和回應功能中處理誤報/負片</span><span class="sxs-lookup"><span data-stu-id="00d6a-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="00d6a-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="00d6a-106">**Applies to:**</span></span>
- <span data-ttu-id="00d6a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00d6a-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="00d6a-108">任何威脅防護解決方案都會偶爾發生誤報/負片錯誤。</span><span class="sxs-lookup"><span data-stu-id="00d6a-108">False positives/negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="00d6a-109">如果 Microsoft 365 Defender 中的 [自動調查和回應功能](m365d-autoir.md) 未接或錯誤地偵測到某項，則您的安全作業小組可以採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="00d6a-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- <span data-ttu-id="00d6a-110">[向 Microsoft 報告誤報/負數](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="00d6a-110">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="00d6a-111">視需要[調整提醒](#adjust-an-alert-to-prevent-false-positives-from-recurring) () ;和</span><span class="sxs-lookup"><span data-stu-id="00d6a-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="00d6a-112">[復原對裝置採取的修正動作](#undo-a-remediation-action-that-was-taken-on-a-device)。</span><span class="sxs-lookup"><span data-stu-id="00d6a-112">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="00d6a-113">下列各節說明如何執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="00d6a-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="00d6a-114">將誤報報告給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="00d6a-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="00d6a-115">偵測到未接或誤接專案</span><span class="sxs-lookup"><span data-stu-id="00d6a-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="00d6a-116">服務</span><span class="sxs-lookup"><span data-stu-id="00d6a-116">Service</span></span>  |<span data-ttu-id="00d6a-117">處理方式</span><span class="sxs-lookup"><span data-stu-id="00d6a-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="00d6a-118">-電子郵件</span><span class="sxs-lookup"><span data-stu-id="00d6a-118">- Email message</span></span> <br/><span data-ttu-id="00d6a-119">-電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="00d6a-119">- Email attachment</span></span> <br/><span data-ttu-id="00d6a-120">-電子郵件訊息中的 URL</span><span class="sxs-lookup"><span data-stu-id="00d6a-120">- URL in an email message</span></span><br/><span data-ttu-id="00d6a-121">-Office 檔案中的 URL</span><span class="sxs-lookup"><span data-stu-id="00d6a-121">- URL in an Office file</span></span>      |[<span data-ttu-id="00d6a-122">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="00d6a-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="00d6a-123">將可疑的垃圾郵件、網路釣魚、URLs 及檔案提交給 Microsoft 進行掃描</span><span class="sxs-lookup"><span data-stu-id="00d6a-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="00d6a-124">裝置上的檔或應用程式</span><span class="sxs-lookup"><span data-stu-id="00d6a-124">File or app on a device</span></span>    |[<span data-ttu-id="00d6a-125">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="00d6a-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="00d6a-126">將檔案提交給 Microsoft 以進行惡意程式碼分析</span><span class="sxs-lookup"><span data-stu-id="00d6a-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="00d6a-127">調整提醒以避免定期誤報</span><span class="sxs-lookup"><span data-stu-id="00d6a-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="00d6a-128">案例</span><span class="sxs-lookup"><span data-stu-id="00d6a-128">Scenario</span></span> |<span data-ttu-id="00d6a-129">服務</span><span class="sxs-lookup"><span data-stu-id="00d6a-129">Service</span></span> |<span data-ttu-id="00d6a-130">處理方式</span><span class="sxs-lookup"><span data-stu-id="00d6a-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="00d6a-131">-由合法使用所觸發的警示</span><span class="sxs-lookup"><span data-stu-id="00d6a-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="00d6a-132">-警示不准確</span><span class="sxs-lookup"><span data-stu-id="00d6a-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="00d6a-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="00d6a-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="00d6a-134">或</span><span class="sxs-lookup"><span data-stu-id="00d6a-134">or</span></span> <br/>[<span data-ttu-id="00d6a-135">Azure 高級威脅偵測</span><span class="sxs-lookup"><span data-stu-id="00d6a-135">Azure Advanced Threat Detection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="00d6a-136">在雲端應用程式安全性入口網站中管理提醒</span><span class="sxs-lookup"><span data-stu-id="00d6a-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="00d6a-137">檔案、IP 位址、URL 或網域在裝置上視為惡意程式碼，即使它是安全的</span><span class="sxs-lookup"><span data-stu-id="00d6a-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="00d6a-138">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="00d6a-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="00d6a-139">使用 "Allow" 動作建立自訂指示器</span><span class="sxs-lookup"><span data-stu-id="00d6a-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="00d6a-140">復原裝置上所執行的修復動作</span><span class="sxs-lookup"><span data-stu-id="00d6a-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="00d6a-141">如果對實體 (採取修正動作，例如裝置或電子郵件訊息) ，且受影響的實體實際上不是威脅，您的安全性作業小組可以復原「 [行動中心](m365d-action-center.md)」中的修復動作。</span><span class="sxs-lookup"><span data-stu-id="00d6a-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="00d6a-142">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="00d6a-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="00d6a-143">在功能窗格中，選擇 [控制中心]。</span><span class="sxs-lookup"><span data-stu-id="00d6a-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="00d6a-144">在 [ **記錄** ] 索引標籤上，選取您要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="00d6a-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="00d6a-145">其快顯視窗隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="00d6a-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="00d6a-146">在快顯視窗中，選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="00d6a-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="00d6a-147">請參閱 [復原已完成動作](m365d-autoir-actions.md#undo-completed-actions)。</span><span class="sxs-lookup"><span data-stu-id="00d6a-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="00d6a-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="00d6a-148">See also</span></span>

- [<span data-ttu-id="00d6a-149">檢視自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="00d6a-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="00d6a-150">使用 Microsoft 365 Defender 中的高級搜尋主動搜尋威脅</span><span class="sxs-lookup"><span data-stu-id="00d6a-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="00d6a-151">在 Microsoft Defender for Endpoint 中處理誤報/負片</span><span class="sxs-lookup"><span data-stu-id="00d6a-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)