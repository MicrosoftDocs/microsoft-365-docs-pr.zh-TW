---
title: 在 Microsoft 威脅防護中處理假像的誤報或漏報
description: 在 Microsoft 威脅防護中，AIR 是否已錯過或錯誤地偵測到什麼？ 瞭解如何將誤報或錯誤否定提交給 Microsoft 進行分析。
keywords: 自動化，調查，警示，觸發器，動作，修正，誤報，誤報，false 負數
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365-initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: f8d741cbc7215c18d096573fe6555dfe7709c58b
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413635"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="b9fed-105">在自動化調查和回應功能中處理誤報/負片</span><span class="sxs-lookup"><span data-stu-id="b9fed-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b9fed-106">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b9fed-106">**Applies to:**</span></span>
- <span data-ttu-id="b9fed-107">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="b9fed-107">Microsoft Threat Protection</span></span>

<span data-ttu-id="b9fed-108">Microsoft 威脅防護中的 [自動化調查和回應功能](mtp-autoir.md) 是否遺漏或錯誤地偵測到某項內容？</span><span class="sxs-lookup"><span data-stu-id="b9fed-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="b9fed-109">您可以採取一些步驟加以修正。</span><span class="sxs-lookup"><span data-stu-id="b9fed-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="b9fed-110">您可以：</span><span class="sxs-lookup"><span data-stu-id="b9fed-110">You can:</span></span>

- <span data-ttu-id="b9fed-111">[向 Microsoft 報告誤報/負數](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="b9fed-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="b9fed-112">視需要[調整提醒](#adjust-an-alert-to-prevent-false-positives-from-recurring) () ;和</span><span class="sxs-lookup"><span data-stu-id="b9fed-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="b9fed-113">[復原對裝置採取的修正動作](#undo-a-remediation-action-that-was-taken-on-a-device)。</span><span class="sxs-lookup"><span data-stu-id="b9fed-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="b9fed-114">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="b9fed-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="b9fed-115">將誤報報告給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="b9fed-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="b9fed-116">偵測到未接或誤接專案</span><span class="sxs-lookup"><span data-stu-id="b9fed-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="b9fed-117">服務</span><span class="sxs-lookup"><span data-stu-id="b9fed-117">Service</span></span>  |<span data-ttu-id="b9fed-118">處理方式</span><span class="sxs-lookup"><span data-stu-id="b9fed-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b9fed-119">-電子郵件</span><span class="sxs-lookup"><span data-stu-id="b9fed-119">- Email message</span></span> <br/><span data-ttu-id="b9fed-120">-電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="b9fed-120">- Email attachment</span></span> <br/><span data-ttu-id="b9fed-121">-電子郵件訊息中的 URL</span><span class="sxs-lookup"><span data-stu-id="b9fed-121">- URL in an email message</span></span><br/><span data-ttu-id="b9fed-122">-Office 檔案中的 URL</span><span class="sxs-lookup"><span data-stu-id="b9fed-122">- URL in an Office file</span></span>      |[<span data-ttu-id="b9fed-123">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="b9fed-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="b9fed-124">將可疑的垃圾郵件、網路釣魚、URLs 及檔案提交給 Microsoft 進行掃描</span><span class="sxs-lookup"><span data-stu-id="b9fed-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="b9fed-125">裝置上的檔或應用程式</span><span class="sxs-lookup"><span data-stu-id="b9fed-125">File or app on a device</span></span>    |[<span data-ttu-id="b9fed-126">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="b9fed-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="b9fed-127">將檔案提交給 Microsoft 以進行惡意程式碼分析</span><span class="sxs-lookup"><span data-stu-id="b9fed-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="b9fed-128">調整提醒以避免定期誤報</span><span class="sxs-lookup"><span data-stu-id="b9fed-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="b9fed-129">案例</span><span class="sxs-lookup"><span data-stu-id="b9fed-129">Scenario</span></span> |<span data-ttu-id="b9fed-130">服務</span><span class="sxs-lookup"><span data-stu-id="b9fed-130">Service</span></span> |<span data-ttu-id="b9fed-131">處理方式</span><span class="sxs-lookup"><span data-stu-id="b9fed-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="b9fed-132">-由合法使用所觸發的警示</span><span class="sxs-lookup"><span data-stu-id="b9fed-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="b9fed-133">-警示不准確</span><span class="sxs-lookup"><span data-stu-id="b9fed-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="b9fed-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b9fed-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="b9fed-135">或</span><span class="sxs-lookup"><span data-stu-id="b9fed-135">or</span></span> <br/>[<span data-ttu-id="b9fed-136">Azure 高級威脅偵測</span><span class="sxs-lookup"><span data-stu-id="b9fed-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="b9fed-137">在雲端應用程式安全性入口網站中管理提醒</span><span class="sxs-lookup"><span data-stu-id="b9fed-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="b9fed-138">檔案、IP 位址、URL 或網域在裝置上視為惡意程式碼，即使它是安全的</span><span class="sxs-lookup"><span data-stu-id="b9fed-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="b9fed-139">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="b9fed-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="b9fed-140">使用 "Allow" 動作建立自訂指示器</span><span class="sxs-lookup"><span data-stu-id="b9fed-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="b9fed-141">復原裝置上所執行的修復動作</span><span class="sxs-lookup"><span data-stu-id="b9fed-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="b9fed-142">如果對裝置執行修正動作 (例如 Windows 10 裝置) ，且該專案實際上不是威脅，您的安全性作業小組可以復原 [動作中心](mtp-action-center.md)的修復動作。</span><span class="sxs-lookup"><span data-stu-id="b9fed-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9fed-143">在嘗試執行下列工作之前，請先確定您具備 [必要的許可權](mtp-action-center.md#required-permissions-for-action-center-tasks) 。</span><span class="sxs-lookup"><span data-stu-id="b9fed-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="b9fed-144">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="b9fed-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="b9fed-145">在功能窗格中，選擇 [控制中心]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9fed-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="b9fed-146">在 [ **記錄** ] 索引標籤上，選取您要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="b9fed-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="b9fed-147">這會開啟快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="b9fed-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="b9fed-148">使用篩選器縮小結果清單。</span><span class="sxs-lookup"><span data-stu-id="b9fed-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="b9fed-149">在選取專案的浮出控制項中，選取 [ **開啟調查] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="b9fed-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="b9fed-150">在 [調查詳細資料] 視圖中，選取 [ **動作** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b9fed-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="b9fed-151">選取狀態為 [**已完成**] 的專案，然後在 [**決策**] 欄中尋找連結（如「**已核准**」）。</span><span class="sxs-lookup"><span data-stu-id="b9fed-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="b9fed-152">這會開啟快顯視窗，包含動作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b9fed-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="b9fed-153">若要復原動作，請選取 [ **刪除修正**]。</span><span class="sxs-lookup"><span data-stu-id="b9fed-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9fed-154">請參閱</span><span class="sxs-lookup"><span data-stu-id="b9fed-154">See also</span></span>

- [<span data-ttu-id="b9fed-155">檢視自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="b9fed-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="b9fed-156">使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅</span><span class="sxs-lookup"><span data-stu-id="b9fed-156">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
