---
title: 處理誤判或漏報中產生 Microsoft 威脅防護中
description: 某個項目已未接或錯誤偵測到的空調中 Microsoft 威脅防護？ 了解如何提交誤判或 false 的負號給 Microsoft 進行分析。
keywords: 自動化，調查、 提醒、 觸發程序、 動作、 修復、 正數，則為 false 誤判
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2f3808f599caa4ed347fc182005397c14b9f51b2
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42262000"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="adcbf-105">處理中自動進行調查並回應功能，則為 false positive/負號</span><span class="sxs-lookup"><span data-stu-id="adcbf-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="adcbf-106">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="adcbf-106">**Applies to:**</span></span>
- <span data-ttu-id="adcbf-107">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="adcbf-107">Microsoft Threat Protection</span></span>

<span data-ttu-id="adcbf-108">未[自動的調查及回應功能](mtp-autoir.md)Microsoft 威脅防護中遺漏或錯誤偵測到某個嗎？</span><span class="sxs-lookup"><span data-stu-id="adcbf-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="adcbf-109">有修正此問題時可採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="adcbf-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="adcbf-110">您可以：</span><span class="sxs-lookup"><span data-stu-id="adcbf-110">You can:</span></span>

- <span data-ttu-id="adcbf-111">[報告可為正數/誤判給 Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="adcbf-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="adcbf-112">[調整您的通知](#adjust-an-alert-to-prevent-false-positives-from-recurring)（如果需要）;和</span><span class="sxs-lookup"><span data-stu-id="adcbf-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="adcbf-113">[復原，拍攝裝置的修復動作](#undo-a-remediation-action-that-was-taken-on-a-device)。</span><span class="sxs-lookup"><span data-stu-id="adcbf-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="adcbf-114">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="adcbf-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="adcbf-115">向 Microsoft 報告可為正數/誤判進行分析</span><span class="sxs-lookup"><span data-stu-id="adcbf-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="adcbf-116">未接或錯誤偵測到的項目</span><span class="sxs-lookup"><span data-stu-id="adcbf-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="adcbf-117">服務</span><span class="sxs-lookup"><span data-stu-id="adcbf-117">Service</span></span>  |<span data-ttu-id="adcbf-118">處理方式</span><span class="sxs-lookup"><span data-stu-id="adcbf-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="adcbf-119">電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="adcbf-119">- Email message</span></span> <br/><span data-ttu-id="adcbf-120">電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="adcbf-120">- Email attachment</span></span> <br/><span data-ttu-id="adcbf-121">-在 [電子郵件 URL</span><span class="sxs-lookup"><span data-stu-id="adcbf-121">- URL in an email message</span></span><br/><span data-ttu-id="adcbf-122">-在 Office 檔案 URL</span><span class="sxs-lookup"><span data-stu-id="adcbf-122">- URL in an Office file</span></span>      |[<span data-ttu-id="adcbf-123">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="adcbf-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="adcbf-124">送出可疑的垃圾郵件、 釣魚程式、 Url 和 microsoft Office 365 掃描的檔案</span><span class="sxs-lookup"><span data-stu-id="adcbf-124">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="adcbf-125">檔案或裝置上的應用程式</span><span class="sxs-lookup"><span data-stu-id="adcbf-125">File or app on a device</span></span>    |[<span data-ttu-id="adcbf-126">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="adcbf-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="adcbf-127">提交給 Microsoft 進行惡意程式碼分析的檔案</span><span class="sxs-lookup"><span data-stu-id="adcbf-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="adcbf-128">調整以避免誤判週期性警示</span><span class="sxs-lookup"><span data-stu-id="adcbf-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="adcbf-129">案例</span><span class="sxs-lookup"><span data-stu-id="adcbf-129">Scenario</span></span> |<span data-ttu-id="adcbf-130">服務</span><span class="sxs-lookup"><span data-stu-id="adcbf-130">Service</span></span> |<span data-ttu-id="adcbf-131">處理方式</span><span class="sxs-lookup"><span data-stu-id="adcbf-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="adcbf-132">-合法的使用時觸發警示</span><span class="sxs-lookup"><span data-stu-id="adcbf-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="adcbf-133">-警示是不正確</span><span class="sxs-lookup"><span data-stu-id="adcbf-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="adcbf-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="adcbf-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="adcbf-135">或</span><span class="sxs-lookup"><span data-stu-id="adcbf-135">or</span></span> <br/>[<span data-ttu-id="adcbf-136">Azure 的進階的威脅偵測</span><span class="sxs-lookup"><span data-stu-id="adcbf-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="adcbf-137">管理提醒在 Cloud App Security 入口網站</span><span class="sxs-lookup"><span data-stu-id="adcbf-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="adcbf-138">檔案、 IP 地址、 URL 或網域會被視為惡意程式碼在裝置上，即使其為安全</span><span class="sxs-lookup"><span data-stu-id="adcbf-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="adcbf-139">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="adcbf-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="adcbf-140">使用 「 允許 「 巨集指令建立的自訂標記</span><span class="sxs-lookup"><span data-stu-id="adcbf-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="adcbf-141">復原裝置上的修復動作</span><span class="sxs-lookup"><span data-stu-id="adcbf-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="adcbf-142">如果補救動作 （例如 Windows 10 裝置） 裝置上，且實際上全新的項目，您的安全性作業小組可以復原[重要訊息中心](mtp-action-center.md)中的補救動作。</span><span class="sxs-lookup"><span data-stu-id="adcbf-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually clean, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adcbf-143">確定您嘗試執行下列工作之前，先具有[必要權限](mtp-action-center.md#required-permissions-for-action-center-tasks)。</span><span class="sxs-lookup"><span data-stu-id="adcbf-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="adcbf-144">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="adcbf-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="adcbf-145">在功能窗格中，選擇 [控制中心]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="adcbf-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="adcbf-146">在 [**歷程記錄**] 索引標籤中，選取您想要復原的動作。</span><span class="sxs-lookup"><span data-stu-id="adcbf-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="adcbf-147">如此會開啟彈出式視窗。</span><span class="sxs-lookup"><span data-stu-id="adcbf-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="adcbf-148">使用篩選來縮小結果清單中。</span><span class="sxs-lookup"><span data-stu-id="adcbf-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="adcbf-149">在彈出式視窗中選取的項目，選取 [**開啟調查] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="adcbf-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="adcbf-150">在調查詳細資料] 檢視中，選取 [**動作**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="adcbf-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="adcbf-151">選取項目具有狀態為 **[已完成**，並尋找中的連結，例如**已核准**，**決定**資料行。</span><span class="sxs-lookup"><span data-stu-id="adcbf-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="adcbf-152">這會開啟巨集指令的更多詳細彈出式視窗。</span><span class="sxs-lookup"><span data-stu-id="adcbf-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="adcbf-153">若要復原的動作，請選取 [**刪除修復**]。</span><span class="sxs-lookup"><span data-stu-id="adcbf-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="adcbf-154">相關文章</span><span class="sxs-lookup"><span data-stu-id="adcbf-154">Related articles</span></span>

- [<span data-ttu-id="adcbf-155">與自動化調查及回應相關的核准或拒絕動作</span><span class="sxs-lookup"><span data-stu-id="adcbf-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

- [<span data-ttu-id="adcbf-156">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="adcbf-156">Learn more about the Action center</span></span>](mtp-action-center.md)

- [<span data-ttu-id="adcbf-157">使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅</span><span class="sxs-lookup"><span data-stu-id="adcbf-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
