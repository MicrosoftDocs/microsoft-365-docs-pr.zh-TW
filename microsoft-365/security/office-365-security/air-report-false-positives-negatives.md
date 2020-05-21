---
title: 如何在 Office 365 自動化調查和回應中報告誤報或漏報
description: Office 365 的高級威脅防護是否已錯過或錯誤地偵測到什麼？ 瞭解如何將誤報或錯誤否定提交給 Microsoft 進行分析。
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2dd67af62a400f3e217f146e6d0ee213d74ad99a
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262405"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="efa58-105">如何在自動化調查和回應功能中報告誤報/負片</span><span class="sxs-lookup"><span data-stu-id="efa58-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="efa58-106">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="efa58-106">**Applies to:**</span></span>
- <span data-ttu-id="efa58-107">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="efa58-107">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="efa58-108">[Office 365 中的自動化調查和回應（AIR）功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)是否未命中或錯誤地偵測到某項功能？</span><span class="sxs-lookup"><span data-stu-id="efa58-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="efa58-109">您可以採取一些步驟加以修正。</span><span class="sxs-lookup"><span data-stu-id="efa58-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="efa58-110">您可以：</span><span class="sxs-lookup"><span data-stu-id="efa58-110">You can:</span></span>
- <span data-ttu-id="efa58-111">[向 Microsoft 報告誤報/負數](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="efa58-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="efa58-112">[調整提醒](#adjust-an-alert-to-prevent-false-positives-from-recurring)（如有需要）;和</span><span class="sxs-lookup"><span data-stu-id="efa58-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="efa58-113">[復原對裝置採取的修正動作](#undo-a-remediation-action)。</span><span class="sxs-lookup"><span data-stu-id="efa58-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="efa58-114">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="efa58-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="efa58-115">將誤報報告給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="efa58-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="efa58-116">如果 Office 365 AIR 錯過電子郵件、電子郵件附件、電子郵件訊息中的 URL 或 Office 檔案中的 URL，您可以[將可疑的垃圾郵件、網路釣魚程式、URLs 和檔案提交給 Microsoft For office 365 掃描](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)。</span><span class="sxs-lookup"><span data-stu-id="efa58-116">If Office 365 AIR missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="efa58-117">您也可以[將檔案提交給 Microsoft 以進行惡意程式碼分析](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="efa58-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="efa58-118">調整提醒以避免定期誤報</span><span class="sxs-lookup"><span data-stu-id="efa58-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="efa58-119">如果透過合法的使用觸發警示，或警示不准確，您可以[在雲端 App 安全性入口網站中管理提醒](https://docs.microsoft.com/cloud-app-security/managing-alerts)。</span><span class="sxs-lookup"><span data-stu-id="efa58-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="efa58-120">如果您的組織使用的是[Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection)，除了 Office 365 之外，在裝置上也會將檔案、IP 位址、URL 或網域視為惡意程式碼，即使它是安全的，您還是可以[使用裝置的「允許」動作來建立自訂指示器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="efa58-120">If your organization is using [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="efa58-121">復原修正動作</span><span class="sxs-lookup"><span data-stu-id="efa58-121">Undo a remediation action</span></span>

<span data-ttu-id="efa58-122">在大多數情況下，如果對電子郵件訊息、電子郵件附件或 URL 採取修正動作，而該專案實際上不是威脅，則您的安全作業小組可以復原修正動作，並採取步驟以避免定期誤報。</span><span class="sxs-lookup"><span data-stu-id="efa58-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="efa58-123">您可以使用[威脅瀏覽器](#undo-an-action-using-threat-explorer)或 [[動作]](#undo-an-action-using-the-actions-tab-for-an-investigation)索引標籤進行調查，以復原動作。</span><span class="sxs-lookup"><span data-stu-id="efa58-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="efa58-124">在嘗試執行下列工作之前，請先確定您具備必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="efa58-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="efa58-125">使用威脅瀏覽器復原動作</span><span class="sxs-lookup"><span data-stu-id="efa58-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="efa58-126">透過威脅瀏覽器，您的安全性運作小組可以找到動作所影響的電子郵件，並可能復原動作。</span><span class="sxs-lookup"><span data-stu-id="efa58-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="efa58-127">案例</span><span class="sxs-lookup"><span data-stu-id="efa58-127">Scenario</span></span>  |<span data-ttu-id="efa58-128">復原選項</span><span class="sxs-lookup"><span data-stu-id="efa58-128">Undo Options</span></span>  |<span data-ttu-id="efa58-129">深入了解</span><span class="sxs-lookup"><span data-stu-id="efa58-129">Learn more</span></span> |
|---------|---------|---------|
|<span data-ttu-id="efa58-130">將電子郵件路由傳送至使用者的 [垃圾郵件] 資料夾</span><span class="sxs-lookup"><span data-stu-id="efa58-130">An email message was routed to a user's Junk Email folder</span></span>     |<span data-ttu-id="efa58-131">-將郵件移至使用者的 [刪除的郵件] 資料夾</span><span class="sxs-lookup"><span data-stu-id="efa58-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="efa58-132">-將郵件移至使用者的收件匣</span><span class="sxs-lookup"><span data-stu-id="efa58-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="efa58-133">-刪除郵件</span><span class="sxs-lookup"><span data-stu-id="efa58-133">- Delete the message</span></span>          |[<span data-ttu-id="efa58-134">尋找並調查 Office 365 中傳遞的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="efa58-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|<span data-ttu-id="efa58-135">已隔離的電子郵件訊息或檔</span><span class="sxs-lookup"><span data-stu-id="efa58-135">An email message or a file was quarantined</span></span>     |<span data-ttu-id="efa58-136">-發行電子郵件或檔案</span><span class="sxs-lookup"><span data-stu-id="efa58-136">- Release the email or file</span></span> <br/><span data-ttu-id="efa58-137">-刪除電子郵件或檔</span><span class="sxs-lookup"><span data-stu-id="efa58-137">- Delete the email or file</span></span>         |[<span data-ttu-id="efa58-138">以 Office 365 系統管理員身分管理隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="efa58-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="efa58-139">使用調查的 [動作] 索引標籤復原動作</span><span class="sxs-lookup"><span data-stu-id="efa58-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="efa58-140">在「行動中心」中，您可以看到已採取的修復動作，並可能復原動作。</span><span class="sxs-lookup"><span data-stu-id="efa58-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="efa58-141">移至 [https://protection.office.com](https://protection.office.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="efa58-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="efa58-142">這樣會帶您前往安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="efa58-142">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="efa58-143">移至 [威脅管理]\*\*\*\*  >  [調查]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="efa58-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="efa58-144">在調查清單中，選取專案識別碼旁邊的 [**在新視窗中開啟]** 圖示。</span><span class="sxs-lookup"><span data-stu-id="efa58-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="efa58-145">選取 [**動作**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="efa58-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="efa58-146">選取狀態為 [**已完成**] 的專案，然後在 [**決策**] 欄中尋找連結（如「**已核准**」）。</span><span class="sxs-lookup"><span data-stu-id="efa58-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="efa58-147">這會開啟快顯視窗，包含動作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="efa58-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="efa58-148">若要復原動作，請選取 [**刪除修正**]。</span><span class="sxs-lookup"><span data-stu-id="efa58-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="efa58-149">相關文章</span><span class="sxs-lookup"><span data-stu-id="efa58-149">Related articles</span></span>

[<span data-ttu-id="efa58-150">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="efa58-150">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="efa58-151">開始使用 Office 365 中的自動調查和回應（AIR）</span><span class="sxs-lookup"><span data-stu-id="efa58-151">Get started using Automated investigation and response (AIR) in Office 365</span></span>](office-365-air.md)