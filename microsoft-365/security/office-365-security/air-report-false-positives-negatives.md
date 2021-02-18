---
title: 如何在 Microsoft Defender for Office 365 中報告自動調查的誤報或漏報
description: Microsoft Defender for Office 365 中的 AIR 是否已錯過或錯誤地偵測到什麼？ 瞭解如何將誤報或錯誤否定提交給 Microsoft 進行分析。
keywords: 自動化，調查，警示，觸發器，動作，修正，誤報，誤報，false 負數
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 48d7e1a7497f9bc2a07a84b36fb07939d25609bf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289146"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="63e0e-105">如何在自動化調查和回應功能中報告誤報/負片</span><span class="sxs-lookup"><span data-stu-id="63e0e-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="63e0e-106">**適用於**</span><span class="sxs-lookup"><span data-stu-id="63e0e-106">**Applies to**</span></span>
- [<span data-ttu-id="63e0e-107">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="63e0e-107">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="63e0e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63e0e-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="63e0e-109">如果 [自動調查和回應 (Office 365 未接或誤偵測功能的空氣) 功能](automated-investigation-response-office.md) ，您的安全性運作小組可以採取這些步驟來修正問題。</span><span class="sxs-lookup"><span data-stu-id="63e0e-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="63e0e-110">這類動作包括：</span><span class="sxs-lookup"><span data-stu-id="63e0e-110">Such actions include:</span></span>

- <span data-ttu-id="63e0e-111">[向 Microsoft 報告誤報/負數](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="63e0e-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="63e0e-112">在需要時[調整提醒](#adjust-an-alert-to-prevent-false-positives-from-recurring) () ;和</span><span class="sxs-lookup"><span data-stu-id="63e0e-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="63e0e-113">復原[採取的修復動作](#undo-a-remediation-action)。</span><span class="sxs-lookup"><span data-stu-id="63e0e-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="63e0e-114">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="63e0e-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="63e0e-115">將誤報報告給 Microsoft 進行分析</span><span class="sxs-lookup"><span data-stu-id="63e0e-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="63e0e-116">如果 Microsoft Defender for Office 365 中的 AIR 錯過電子郵件、電子郵件附件、電子郵件中的 URL 或 Office 檔案中的 URL，您可以 [將可疑的垃圾郵件、網路釣魚程式、URLs 和檔案提交給 Microsoft For office 365 掃描](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="63e0e-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="63e0e-117">您也可以 [將檔案提交給 Microsoft 以進行惡意程式碼分析](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="63e0e-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="63e0e-118">調整提醒以避免定期誤報</span><span class="sxs-lookup"><span data-stu-id="63e0e-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="63e0e-119">如果透過合法的使用觸發警示，或警示不准確，您可以 [在雲端 App 安全性入口網站中管理提醒](https://docs.microsoft.com/cloud-app-security/managing-alerts)。</span><span class="sxs-lookup"><span data-stu-id="63e0e-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="63e0e-120">如果您的組織使用的是 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection) ，除了 Office 365 之外，在裝置上會將檔案、IP 位址、URL 或網域視為惡意程式碼，即使它是安全的，您還是可以 [使用裝置的「允許」動作來建立自訂指示器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="63e0e-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="63e0e-121">復原修正動作</span><span class="sxs-lookup"><span data-stu-id="63e0e-121">Undo a remediation action</span></span>

<span data-ttu-id="63e0e-122">在大多數情況下，如果對電子郵件訊息、電子郵件附件或 URL 採取修正動作，而該專案實際上不是威脅，則您的安全作業小組可以復原修正動作，並採取步驟以避免定期誤報。</span><span class="sxs-lookup"><span data-stu-id="63e0e-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="63e0e-123">您可以使用 [威脅瀏覽器](#undo-an-action-using-threat-explorer) 或 [ [動作]](#undo-an-action-in-the-action-center) 索引標籤進行調查，以復原動作。</span><span class="sxs-lookup"><span data-stu-id="63e0e-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63e0e-124">在嘗試執行下列工作之前，請先確定您具備必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="63e0e-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="63e0e-125">使用威脅瀏覽器復原動作</span><span class="sxs-lookup"><span data-stu-id="63e0e-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="63e0e-126">透過威脅瀏覽器，您的安全性運作小組可以找到動作所影響的電子郵件，並可能復原動作。</span><span class="sxs-lookup"><span data-stu-id="63e0e-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="63e0e-127">案例</span><span class="sxs-lookup"><span data-stu-id="63e0e-127">Scenario</span></span>|<span data-ttu-id="63e0e-128">復原選項</span><span class="sxs-lookup"><span data-stu-id="63e0e-128">Undo Options</span></span>|<span data-ttu-id="63e0e-129">深入了解</span><span class="sxs-lookup"><span data-stu-id="63e0e-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="63e0e-130">將電子郵件路由傳送至使用者的 [垃圾郵件] 資料夾</span><span class="sxs-lookup"><span data-stu-id="63e0e-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="63e0e-131">-將郵件移至使用者的 [刪除的郵件] 資料夾</span><span class="sxs-lookup"><span data-stu-id="63e0e-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="63e0e-132">-將郵件移至使用者的收件匣</span><span class="sxs-lookup"><span data-stu-id="63e0e-132">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="63e0e-133">-刪除郵件</span><span class="sxs-lookup"><span data-stu-id="63e0e-133">- Delete the message</span></span>|[<span data-ttu-id="63e0e-134">尋找並調查 Office 365 中傳遞的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="63e0e-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="63e0e-135">已隔離的電子郵件訊息或檔</span><span class="sxs-lookup"><span data-stu-id="63e0e-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="63e0e-136">-發行電子郵件或檔案</span><span class="sxs-lookup"><span data-stu-id="63e0e-136">- Release the email or file</span></span><br/><span data-ttu-id="63e0e-137">-刪除電子郵件或檔</span><span class="sxs-lookup"><span data-stu-id="63e0e-137">- Delete the email or file</span></span>|[<span data-ttu-id="63e0e-138">以系統管理員身分管理被隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="63e0e-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="63e0e-139">復原動作中心的動作</span><span class="sxs-lookup"><span data-stu-id="63e0e-139">Undo an action in the Action center</span></span>

<span data-ttu-id="63e0e-140">在「行動中心」中，您可以看到已採取的修復動作，並可能復原動作。</span><span class="sxs-lookup"><span data-stu-id="63e0e-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="63e0e-141">請移至 Microsoft 365 的安全性中心 ([https://security.microsoft.com](https://security.microsoft.com)) 。</span><span class="sxs-lookup"><span data-stu-id="63e0e-141">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>
2. <span data-ttu-id="63e0e-142">在功能窗格中，選取 [ **動作中心**]。</span><span class="sxs-lookup"><span data-stu-id="63e0e-142">In the navigation pane, select **Action center**.</span></span> 
3. <span data-ttu-id="63e0e-143">選取 [ **記錄** ] 索引標籤，以查看已完成的動作清單。</span><span class="sxs-lookup"><span data-stu-id="63e0e-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="63e0e-144">選取專案。</span><span class="sxs-lookup"><span data-stu-id="63e0e-144">Select an item.</span></span> <span data-ttu-id="63e0e-145">其快顯視窗隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="63e0e-145">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="63e0e-146">在快顯視窗中，選取 [ **復原**]。</span><span class="sxs-lookup"><span data-stu-id="63e0e-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="63e0e-147"> (只有可復原的動作才能具有 [ **復原** ] 按鈕。 ) </span><span class="sxs-lookup"><span data-stu-id="63e0e-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="63e0e-148">請參閱</span><span class="sxs-lookup"><span data-stu-id="63e0e-148">See also</span></span>

- [<span data-ttu-id="63e0e-149">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="63e0e-149">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="63e0e-150">Microsoft Defender for Office 365 中的自動調查</span><span class="sxs-lookup"><span data-stu-id="63e0e-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
