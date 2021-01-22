---
title: 在 Microsoft 365 Defender 中處理 AIR 中的誤誤或漏報
description: MICROSOFT 365 Defender 中的 AIR 偵測到未接或錯誤？ 瞭解如何將誤誤或漏報提交至 Microsoft 進行分析。
keywords: 自動化、調查、警示、觸發、動作、補救、誤正、漏報
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930351"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="61e38-105">在自動化調查與回應功能中處理誤對/負數</span><span class="sxs-lookup"><span data-stu-id="61e38-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="61e38-106">適用於：</span><span class="sxs-lookup"><span data-stu-id="61e38-106">**Applies to:**</span></span>
- <span data-ttu-id="61e38-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61e38-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="61e38-108">Microsoft [](mtp-autoir.md) 365 Defender 中的自動化調查與回應功能是否遺漏或誤偵測到某些專案？</span><span class="sxs-lookup"><span data-stu-id="61e38-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="61e38-109">您可以採取一些步驟來修正此問題。</span><span class="sxs-lookup"><span data-stu-id="61e38-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="61e38-110">您可以：</span><span class="sxs-lookup"><span data-stu-id="61e38-110">You can:</span></span>

- <span data-ttu-id="61e38-111">[向 Microsoft 報告誤正/負數](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="61e38-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="61e38-112">[如有必要，請 (](#adjust-an-alert-to-prevent-false-positives-from-recurring) 您的) ;和</span><span class="sxs-lookup"><span data-stu-id="61e38-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="61e38-113">[復原在裝置上採取的補救動作](#undo-a-remediation-action-that-was-taken-on-a-device)。</span><span class="sxs-lookup"><span data-stu-id="61e38-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="61e38-114">使用這篇文章做為指南。</span><span class="sxs-lookup"><span data-stu-id="61e38-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="61e38-115">向 Microsoft 報告誤正/負數以進行分析</span><span class="sxs-lookup"><span data-stu-id="61e38-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="61e38-116">未接或偵測到錯誤的專案</span><span class="sxs-lookup"><span data-stu-id="61e38-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="61e38-117">服務</span><span class="sxs-lookup"><span data-stu-id="61e38-117">Service</span></span>  |<span data-ttu-id="61e38-118">處理方式</span><span class="sxs-lookup"><span data-stu-id="61e38-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="61e38-119">- 電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="61e38-119">- Email message</span></span> <br/><span data-ttu-id="61e38-120">- 電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="61e38-120">- Email attachment</span></span> <br/><span data-ttu-id="61e38-121">- 電子郵件訊息中的 URL</span><span class="sxs-lookup"><span data-stu-id="61e38-121">- URL in an email message</span></span><br/><span data-ttu-id="61e38-122">- Office 檔案中的 URL</span><span class="sxs-lookup"><span data-stu-id="61e38-122">- URL in an Office file</span></span>      |[<span data-ttu-id="61e38-123">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="61e38-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="61e38-124">將可疑的垃圾郵件、網路釣魚、URL 和檔案提交到 Microsoft 掃描</span><span class="sxs-lookup"><span data-stu-id="61e38-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="61e38-125">裝置上的檔案或應用程式</span><span class="sxs-lookup"><span data-stu-id="61e38-125">File or app on a device</span></span>    |[<span data-ttu-id="61e38-126">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="61e38-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="61e38-127">提交檔案至 Microsoft 進行惡意攻擊分析</span><span class="sxs-lookup"><span data-stu-id="61e38-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="61e38-128">調整警示以防止誤將重複出現</span><span class="sxs-lookup"><span data-stu-id="61e38-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="61e38-129">案例</span><span class="sxs-lookup"><span data-stu-id="61e38-129">Scenario</span></span> |<span data-ttu-id="61e38-130">服務</span><span class="sxs-lookup"><span data-stu-id="61e38-130">Service</span></span> |<span data-ttu-id="61e38-131">處理方式</span><span class="sxs-lookup"><span data-stu-id="61e38-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="61e38-132">- 合法使用會觸發警示</span><span class="sxs-lookup"><span data-stu-id="61e38-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="61e38-133">- 通知不正確</span><span class="sxs-lookup"><span data-stu-id="61e38-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="61e38-134">Microsoft 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="61e38-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="61e38-135">或</span><span class="sxs-lookup"><span data-stu-id="61e38-135">or</span></span> <br/>[<span data-ttu-id="61e38-136">Azure 進位威脅偵測</span><span class="sxs-lookup"><span data-stu-id="61e38-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="61e38-137">在雲端 App 安全性入口網站中管理警示</span><span class="sxs-lookup"><span data-stu-id="61e38-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="61e38-138">即使裝置是安全的，檔案、IP 位址、URL 或網域還是會被視為惡意攻擊</span><span class="sxs-lookup"><span data-stu-id="61e38-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="61e38-139">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="61e38-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="61e38-140">建立具有「允許」動作的自訂標記</span><span class="sxs-lookup"><span data-stu-id="61e38-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="61e38-141">復原在裝置上採取的補救動作</span><span class="sxs-lookup"><span data-stu-id="61e38-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="61e38-142">如果在 Windows 10 裝置 (等裝置上採取補救動作) 且該專案實際上並非威脅，您的安全性作業小組可以在控制中心復原補救 [動作](mtp-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="61e38-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61e38-143">嘗試執行 [下列工作之前](mtp-action-center.md#required-permissions-for-action-center-tasks) ，請確認您擁有必要許可權。</span><span class="sxs-lookup"><span data-stu-id="61e38-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="61e38-144">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="61e38-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="61e38-145">在功能窗格中，選擇 [控制中心]。</span><span class="sxs-lookup"><span data-stu-id="61e38-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="61e38-146">在歷程 **記錄上** ，選取要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="61e38-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="61e38-147">這會開啟飛出視窗。</span><span class="sxs-lookup"><span data-stu-id="61e38-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="61e38-148">使用篩選來縮小結果清單。</span><span class="sxs-lookup"><span data-stu-id="61e38-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="61e38-149">在選定專案的飛出飛出中，選取開啟 **調查頁面**。</span><span class="sxs-lookup"><span data-stu-id="61e38-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="61e38-150">在調查詳細資料檢視中，選取動作 **按鈕** 。</span><span class="sxs-lookup"><span data-stu-id="61e38-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="61e38-151">選取狀態為已完成 **的專案**，在決策欄中尋找連結 **，例如\*\*\*\*已核准。**</span><span class="sxs-lookup"><span data-stu-id="61e38-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="61e38-152">這會開啟一個飛出視窗，包含有關動作的更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="61e38-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="61e38-153">若要復原動作，請選取 Delete **修復**。</span><span class="sxs-lookup"><span data-stu-id="61e38-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="61e38-154">另請參閱</span><span class="sxs-lookup"><span data-stu-id="61e38-154">See also</span></span>

- [<span data-ttu-id="61e38-155">檢視自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="61e38-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="61e38-156">使用 Microsoft 365 Defender 中的進位搜尋主動搜尋威脅</span><span class="sxs-lookup"><span data-stu-id="61e38-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
