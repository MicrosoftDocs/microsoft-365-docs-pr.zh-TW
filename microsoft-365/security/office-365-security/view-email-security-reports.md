---
title: 檢視安全性與合規性中心內的電子郵件安全性報告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 瞭解如何尋找及使用貴組織的電子郵件安全性報告。 電子郵件安全性報告可在安全性 & 規範中心中取得。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 588c30ca07684636661c7946b2418b75574c8cbd
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199214"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="c3808-104">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="c3808-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c3808-105">[安全性 & 合規性中心](https://protection.office.com)提供各種報告，可協助您觀察電子郵件安全性功能（例如，反垃圾郵件、反惡意程式碼，以及 Microsoft 365 中的加密功能）如何保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="c3808-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="c3808-106">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-these-reports)，您可以移至 [ **報表**] \> **儀表板**，在安全性 & 規範中心中查看這些報告。</span><span class="sxs-lookup"><span data-stu-id="c3808-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="c3808-107">若要直接移至 [報告] 儀表板，請開啟] <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="c3808-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全性 & 規範中心內的報告儀表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="c3808-109">已遭破壞的使用者報告</span><span class="sxs-lookup"><span data-stu-id="c3808-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="c3808-110">這份報告可在 Microsoft 365 組織中使用 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="c3808-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="c3808-111">在獨立 Exchange Online Protection (EOP) 組織中無法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="c3808-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="c3808-112">「已 **遭破壞的使用者** 報告」顯示顯示過去7天內已標示為 **可疑** 或 **限制** 的使用者帳戶數目。</span><span class="sxs-lookup"><span data-stu-id="c3808-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="c3808-113">在上述任一狀態的帳戶都有問題或甚至遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="c3808-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="c3808-114">在經常使用的情況下，您可以使用報表來找出峰值，甚至是趨勢，也就是可疑或受限制的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c3808-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="c3808-115">如需遭到破壞之使用者的詳細資訊，請參閱 [回應遭到破壞的電子郵件帳戶](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="c3808-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![報表儀表板中受損的使用者小工具](../../media/compromised-users-report-widget.png)

<span data-ttu-id="c3808-117">匯總視圖會顯示過去90天的資料，詳細資料檢視會顯示過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="c3808-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="c3808-118">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [已 **遭破壞的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="c3808-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="c3808-119">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="c3808-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="c3808-120">您可以按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="c3808-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="c3808-121">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c3808-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="c3808-122">**可疑**：使用者帳戶已傳送可疑的電子郵件，而且受到限制傳送電子郵件的風險。</span><span class="sxs-lookup"><span data-stu-id="c3808-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="c3808-123">**限制**：由於高度可疑的模式，使用者帳戶已限制傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c3808-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![已遭破壞之使用者報告中的報表檢視](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="c3808-125">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="c3808-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="c3808-126">**建立時間**</span><span class="sxs-lookup"><span data-stu-id="c3808-126">**Creation time**</span></span>
- <span data-ttu-id="c3808-127">**User ID**</span><span class="sxs-lookup"><span data-stu-id="c3808-127">**User ID**</span></span>
- <span data-ttu-id="c3808-128">**Action**</span><span class="sxs-lookup"><span data-stu-id="c3808-128">**Action**</span></span>

<span data-ttu-id="c3808-129">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="c3808-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="c3808-130">加密報告</span><span class="sxs-lookup"><span data-stu-id="c3808-130">Encryption report</span></span>

<span data-ttu-id="c3808-131">您可以在 Exchange Online 或獨立 EOP 中信箱的 EOP (訂閱中取得 **加密報告** ，而不需要 exchange online 信箱) 。</span><span class="sxs-lookup"><span data-stu-id="c3808-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="c3808-132">組織的安全小組可以使用此報告中的資訊來識別模式，並主動套用或調整敏感電子郵件訊息的原則。</span><span class="sxs-lookup"><span data-stu-id="c3808-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="c3808-133">例如：</span><span class="sxs-lookup"><span data-stu-id="c3808-133">For example:</span></span>

- <span data-ttu-id="c3808-134">如果您看到大量的電子郵件是由使用者加密，您可能會想要新增加密原則，以自動化某些使用案例的加密。</span><span class="sxs-lookup"><span data-stu-id="c3808-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="c3808-135">如需詳細資訊，請參閱 [定義郵件流程規則，以加密 Microsoft 365 中的電子郵件訊息](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="c3808-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="c3808-136">如果您有許多可供使用的加密範本，但沒有人正在使用這些範本，您可能會探索使用者是否需要功能訓練。</span><span class="sxs-lookup"><span data-stu-id="c3808-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="c3808-137">匯總視圖允許篩選過去90天，而詳細資料檢視允許篩選10天。</span><span class="sxs-lookup"><span data-stu-id="c3808-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="c3808-138">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **加密報告**]。</span><span class="sxs-lookup"><span data-stu-id="c3808-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="c3808-139">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="c3808-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="c3808-140">若要深入瞭解加密，請參閱 [Microsoft 365 中的電子郵件加密](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="c3808-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="c3808-141">加密報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="c3808-141">Report view for the Encryption report</span></span>

<span data-ttu-id="c3808-142">您可以在圖表上使用下列篩選：</span><span class="sxs-lookup"><span data-stu-id="c3808-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="c3808-143">**查看資料：郵件加密報告** 和 **分解方式：加密方法**：下列為可用的加密方法：</span><span class="sxs-lookup"><span data-stu-id="c3808-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="c3808-144">**使用者加密**</span><span class="sxs-lookup"><span data-stu-id="c3808-144">**Encryption by user**</span></span>
  - <span data-ttu-id="c3808-145">**依原則加密**</span><span class="sxs-lookup"><span data-stu-id="c3808-145">**Encryption by policy**</span></span>

  <span data-ttu-id="c3808-146">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改此圖表：</span><span class="sxs-lookup"><span data-stu-id="c3808-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="c3808-147">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c3808-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c3808-148">加密方法。</span><span class="sxs-lookup"><span data-stu-id="c3808-148">Encryption method.</span></span>
  - <span data-ttu-id="c3808-149">加密範本。</span><span class="sxs-lookup"><span data-stu-id="c3808-149">Encryption template.</span></span>

- <span data-ttu-id="c3808-150">**查看資料：郵件加密報告** 和 **分解方式：加密範本**：下列為可供使用的加密方法：</span><span class="sxs-lookup"><span data-stu-id="c3808-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="c3808-151">**請勿轉寄**</span><span class="sxs-lookup"><span data-stu-id="c3808-151">**Do not forward**</span></span>
  - <span data-ttu-id="c3808-152">**只加密**</span><span class="sxs-lookup"><span data-stu-id="c3808-152">**Encrypt only**</span></span>
  - <span data-ttu-id="c3808-153">**OME 先前版本**</span><span class="sxs-lookup"><span data-stu-id="c3808-153">**OME previous**</span></span>
  - <span data-ttu-id="c3808-154">**自訂**</span><span class="sxs-lookup"><span data-stu-id="c3808-154">**Custom**</span></span>

  <span data-ttu-id="c3808-155">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改此圖表：</span><span class="sxs-lookup"><span data-stu-id="c3808-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="c3808-156">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c3808-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c3808-157">加密方法</span><span class="sxs-lookup"><span data-stu-id="c3808-157">Encryption method</span></span>
  - <span data-ttu-id="c3808-158">加密範本</span><span class="sxs-lookup"><span data-stu-id="c3808-158">Encryption template</span></span>

- <span data-ttu-id="c3808-159">**查看資料：前5位收件者網域**：此視圖會顯示圓形圖，其中包含前5位收件者網域的已傳送郵件計數。</span><span class="sxs-lookup"><span data-stu-id="c3808-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="c3808-160">如果您按一下 [ **篩選**]，您可以選取 [ **開始日期** ] 和 [ **結束日期**]。</span><span class="sxs-lookup"><span data-stu-id="c3808-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="c3808-161">加密報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="c3808-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="c3808-162">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="c3808-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="c3808-163">**逐項換行：** 加密 **範本：加密範本**：下列會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c3808-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="c3808-164">**Date**</span><span class="sxs-lookup"><span data-stu-id="c3808-164">**Date**</span></span>
  - <span data-ttu-id="c3808-165">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="c3808-165">**Sender address**</span></span>
  - <span data-ttu-id="c3808-166">**加密範本**</span><span class="sxs-lookup"><span data-stu-id="c3808-166">**Encryption template**</span></span>
  - <span data-ttu-id="c3808-167">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="c3808-167">**Encryption method**</span></span>
  - <span data-ttu-id="c3808-168">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="c3808-168">**Recipient address**</span></span>
  - <span data-ttu-id="c3808-169">**Subject**</span><span class="sxs-lookup"><span data-stu-id="c3808-169">**Subject**</span></span>

- <span data-ttu-id="c3808-170">**資料查看依據：前5位收件者網域**：</span><span class="sxs-lookup"><span data-stu-id="c3808-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="c3808-171">**Date**</span><span class="sxs-lookup"><span data-stu-id="c3808-171">**Date**</span></span>
  - <span data-ttu-id="c3808-172">**收件者網域**</span><span class="sxs-lookup"><span data-stu-id="c3808-172">**Recipient domain**</span></span>
  - <span data-ttu-id="c3808-173">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="c3808-173">**Message count**</span></span>
  
<span data-ttu-id="c3808-174">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="c3808-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="c3808-175">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c3808-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="c3808-176">加密方法</span><span class="sxs-lookup"><span data-stu-id="c3808-176">Encryption method</span></span>
- <span data-ttu-id="c3808-177">加密範本</span><span class="sxs-lookup"><span data-stu-id="c3808-177">Encryption template</span></span>

<span data-ttu-id="c3808-178">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="c3808-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="c3808-179">郵件流程狀態報表</span><span class="sxs-lookup"><span data-stu-id="c3808-179">Mailflow status report</span></span>

<span data-ttu-id="c3808-180">**郵件流程狀態報表**包含惡意程式碼、垃圾郵件、網路釣魚和 edge 封鎖郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c3808-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="c3808-181">如需詳細資訊，請參閱 [郵件流程 status report](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="c3808-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="c3808-182">電子郵件報告中的惡意程式碼偵測</span><span class="sxs-lookup"><span data-stu-id="c3808-182">Malware detections in email report</span></span>

<span data-ttu-id="c3808-183">[ **電子郵件中的惡意** 代碼偵測] 報告會顯示傳入和傳出電子郵件中的惡意程式碼偵測的相關資訊， (Exchange Online PROTECTION 或 EOP) 偵測到的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="c3808-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="c3808-184">如需 EOP 中惡意程式碼保護的詳細資訊，請參閱 [EOP 中的反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c3808-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="c3808-185">匯總 view 篩選允許90天，而 [詳細資料表格篩選] 只允許10天。</span><span class="sxs-lookup"><span data-stu-id="c3808-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="c3808-186">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後 **在電子郵件中選取惡意**代碼偵測。</span><span class="sxs-lookup"><span data-stu-id="c3808-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="c3808-187">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="c3808-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![在 [報告] 儀表板的電子郵件小工具中偵測惡意程式碼](../../media/malware-detections-widget.png)

<span data-ttu-id="c3808-189">您可以按一下 [ **篩選** ] 並選取 [篩選]，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="c3808-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="c3808-190">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c3808-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="c3808-191">**入境**</span><span class="sxs-lookup"><span data-stu-id="c3808-191">**Inbound**</span></span>
- <span data-ttu-id="c3808-192">**出境**</span><span class="sxs-lookup"><span data-stu-id="c3808-192">**Outbound**</span></span>

![電子郵件中的惡意程式碼偵測報表檢視](../../media/malware-detections-report-view.png)

<span data-ttu-id="c3808-194">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="c3808-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="c3808-195">**Date**</span><span class="sxs-lookup"><span data-stu-id="c3808-195">**Date**</span></span>
- <span data-ttu-id="c3808-196">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="c3808-196">**Sender address**</span></span>
- <span data-ttu-id="c3808-197">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="c3808-197">**Recipient address**</span></span>
- <span data-ttu-id="c3808-198">**郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中可用，且應該是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c3808-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="c3808-199">範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。</span><span class="sxs-lookup"><span data-stu-id="c3808-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="c3808-200">**Subject**</span><span class="sxs-lookup"><span data-stu-id="c3808-200">**Subject**</span></span>
- <span data-ttu-id="c3808-201">**Filename**</span><span class="sxs-lookup"><span data-stu-id="c3808-201">**Filename**</span></span>
- <span data-ttu-id="c3808-202">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="c3808-202">**Malware name**</span></span>

<span data-ttu-id="c3808-203">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="c3808-203">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="c3808-204">傳送和接收的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="c3808-204">Sent and received email report</span></span>

<span data-ttu-id="c3808-205">**傳送和接收的電子郵件**報告包含惡意程式碼、垃圾郵件、郵件流程規則 (（也稱為傳輸規則) ）的相關資訊，以及電子郵件進入服務後的高級惡意軟體偵測。</span><span class="sxs-lookup"><span data-stu-id="c3808-205">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="c3808-206">如需詳細資訊，請參閱 [送出和接收的電子郵件報告](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="c3808-206">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="c3808-207">垃圾郵件偵測報告</span><span class="sxs-lookup"><span data-stu-id="c3808-207">Spam detections report</span></span>

<span data-ttu-id="c3808-208">**垃圾郵件**偵測報告會顯示由 EOP 封鎖的垃圾電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c3808-208">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="c3808-209">郵件會個別計算，而不是每個收件者。</span><span class="sxs-lookup"><span data-stu-id="c3808-209">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="c3808-210">例如，如果相同的垃圾郵件已傳送給組織中的100收件者，則會算作一封郵件。</span><span class="sxs-lookup"><span data-stu-id="c3808-210">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="c3808-211">匯總視圖允許90天篩選，而詳細資料表格允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="c3808-211">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="c3808-212">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **垃圾郵件**偵測]。</span><span class="sxs-lookup"><span data-stu-id="c3808-212">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="c3808-213">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="c3808-213">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![報告儀表板中的垃圾郵件偵測小工具](../../media/spam-detections-report-widget.png)

<span data-ttu-id="c3808-215">如需反垃圾郵件保護的詳細資訊，請參閱 [EOP 中的反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c3808-215">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="c3808-216">垃圾郵件偵測報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="c3808-216">Report view for the Spam detections report</span></span>

<span data-ttu-id="c3808-217">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="c3808-217">The following charts are available in the report view:</span></span>

- <span data-ttu-id="c3808-218">**分解方式：動作**：會顯示下列事件種類：</span><span class="sxs-lookup"><span data-stu-id="c3808-218">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="c3808-219">**篩選的垃圾郵件內容**</span><span class="sxs-lookup"><span data-stu-id="c3808-219">**Spam content filtered**</span></span>
  - <span data-ttu-id="c3808-220">**垃圾郵件 IP 封鎖**</span><span class="sxs-lookup"><span data-stu-id="c3808-220">**Spam IP block**</span></span>
  - <span data-ttu-id="c3808-221">**垃圾郵件信封封鎖**</span><span class="sxs-lookup"><span data-stu-id="c3808-221">**Spam envelope block**</span></span>
  - <span data-ttu-id="c3808-222">**垃圾郵件 DBEB 篩選器**：以目錄為基礎的 edge 封鎖 (DBEB) </span><span class="sxs-lookup"><span data-stu-id="c3808-222">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="c3808-223">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您可以看到該天已封鎖的專案數，以及這些專案的分類方式。</span><span class="sxs-lookup"><span data-stu-id="c3808-223">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![垃圾郵件偵測報告中的動作視圖](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="c3808-225">**分解方式：方向**：下列方向如下：</span><span class="sxs-lookup"><span data-stu-id="c3808-225">**Break down by:Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="c3808-226">**入境**</span><span class="sxs-lookup"><span data-stu-id="c3808-226">**Inbound**</span></span>
  - <span data-ttu-id="c3808-227">**出境**</span><span class="sxs-lookup"><span data-stu-id="c3808-227">**Outbound**</span></span>

  ![垃圾郵件偵測報告中的方向視圖](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="c3808-229">如果您按一下報表檢視中的 **篩選器** ，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="c3808-229">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="c3808-230">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c3808-230">**Start date** and **End date**</span></span>
- <span data-ttu-id="c3808-231">方向值</span><span class="sxs-lookup"><span data-stu-id="c3808-231">Direction values</span></span>
- <span data-ttu-id="c3808-232">事件種類值</span><span class="sxs-lookup"><span data-stu-id="c3808-232">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="c3808-233">垃圾郵件偵測報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="c3808-233">Details table view for the Spam detections report</span></span>

<span data-ttu-id="c3808-234">如果您按一下任何報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c3808-234">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="c3808-235">**Date**</span><span class="sxs-lookup"><span data-stu-id="c3808-235">**Date**</span></span>
- <span data-ttu-id="c3808-236">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="c3808-236">**Sender address**</span></span>
- <span data-ttu-id="c3808-237">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="c3808-237">**Recipient address**</span></span>
- <span data-ttu-id="c3808-238">**事件類型**</span><span class="sxs-lookup"><span data-stu-id="c3808-238">**Event type**</span></span>
- <span data-ttu-id="c3808-239">**Action**</span><span class="sxs-lookup"><span data-stu-id="c3808-239">**Action**</span></span>
- <span data-ttu-id="c3808-240">**Subject**</span><span class="sxs-lookup"><span data-stu-id="c3808-240">**Subject**</span></span>

<span data-ttu-id="c3808-241">如果您按一下 [詳細資料] 表格中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="c3808-241">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="c3808-242">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c3808-242">**Start date** and **End date**</span></span>
- <span data-ttu-id="c3808-243">方向值</span><span class="sxs-lookup"><span data-stu-id="c3808-243">Direction values</span></span>
- <span data-ttu-id="c3808-244">事件種類值</span><span class="sxs-lookup"><span data-stu-id="c3808-244">Event type values</span></span>

<span data-ttu-id="c3808-245">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="c3808-245">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="c3808-246">欺騙偵測報告</span><span class="sxs-lookup"><span data-stu-id="c3808-246">Spoof detections report</span></span>

<span data-ttu-id="c3808-247">「 **欺騙** 偵測報告」會顯示偵測到的電子郵件訊息數量，以及那些已被視為「良好」的電子郵件訊息。 (假冒郵件出於正當商務理由) 而完成。</span><span class="sxs-lookup"><span data-stu-id="c3808-247">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="c3808-248">如需有關電子欺騙的詳細資訊，請參閱 [EOP 中的反欺騙防護](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c3808-248">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="c3808-249">報表的匯總視圖允許90天的篩選，而詳細資料檢視只允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="c3808-249">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="c3808-250">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **偽造**偵測]。</span><span class="sxs-lookup"><span data-stu-id="c3808-250">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="c3808-251">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="c3808-251">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![報告儀表板中的欺騙偵測構件](../../media/spoof-detections-widget.png)

<span data-ttu-id="c3808-253">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您可以看到有多少偽造的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="c3808-253">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="c3808-254">您可以按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="c3808-254">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="c3808-255">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c3808-255">**Start date** and **End date**</span></span>

- <span data-ttu-id="c3808-256">**良好的郵件**</span><span class="sxs-lookup"><span data-stu-id="c3808-256">**Good mail**</span></span>

- <span data-ttu-id="c3808-257">**視為垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="c3808-257">**Caught as spam**</span></span>

![欺騙偵測報告中的報表檢視](../../media/spoof-detections-report-view.png)

<span data-ttu-id="c3808-259">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="c3808-259">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="c3808-260">**Date**</span><span class="sxs-lookup"><span data-stu-id="c3808-260">**Date**</span></span>
- <span data-ttu-id="c3808-261">**欺騙寄件者**</span><span class="sxs-lookup"><span data-stu-id="c3808-261">**Spoofed sender**</span></span>
- <span data-ttu-id="c3808-262">**True 寄件者**</span><span class="sxs-lookup"><span data-stu-id="c3808-262">**True sender**</span></span>
- <span data-ttu-id="c3808-263">**寄件者 IP**</span><span class="sxs-lookup"><span data-stu-id="c3808-263">**Sender IP**</span></span>
- <span data-ttu-id="c3808-264">**Action**</span><span class="sxs-lookup"><span data-stu-id="c3808-264">**Action**</span></span>
- <span data-ttu-id="c3808-265">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="c3808-265">**Message count**</span></span>

<span data-ttu-id="c3808-266">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="c3808-266">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="c3808-267">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="c3808-267">Threat protection status report</span></span>

<span data-ttu-id="c3808-268">「 **威脅防護狀態** 」報告可用於 EOP 和 OFFICE 365 ATP;不過，報告包含不同的資料。</span><span class="sxs-lookup"><span data-stu-id="c3808-268">The **Threat protection status** report is available in both EOP and Office 365 ATP; however, the reports contain different data.</span></span> <span data-ttu-id="c3808-269">例如，EOP 客戶可以查看在電子郵件中偵測到惡意程式碼的相關資訊，但不會 [發現 SharePoint 線上、OneDrive 或 Microsoft 小組中偵測到之惡意](atp-for-spo-odb-and-teams.md)檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c3808-269">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="c3808-270">該報告提供包含惡意內容的電子郵件統計，例如檔案或網站位址 (URLs 反惡意程式碼引擎封鎖的) 、 [零小時自動清除 (ZAP) ](zero-hour-auto-purge.md)，以及 atp 功能（如 [atp 安全連結](atp-safe-links.md)、 [atp 安全附件](atp-safe-attachments.md)及 [atp 反網路釣魚](set-up-anti-phishing-policies.md)）。</span><span class="sxs-lookup"><span data-stu-id="c3808-270">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="c3808-271">您可以使用此資訊來識別趨勢，或判斷組織原則是否需要調整。</span><span class="sxs-lookup"><span data-stu-id="c3808-271">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span> <span data-ttu-id="c3808-272">請務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為五個不同的郵件，而不是一封郵件。</span><span class="sxs-lookup"><span data-stu-id="c3808-272">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="c3808-273">若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **威脅防護狀態**]。</span><span class="sxs-lookup"><span data-stu-id="c3808-273">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="c3808-274">若要直接前往報告，請開啟下列其中一個 URLs：</span><span class="sxs-lookup"><span data-stu-id="c3808-274">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="c3808-275">Office 365 ATP： <https://protection.office.com/reportv2?id=ATPV2AggregateReport> 。</span><span class="sxs-lookup"><span data-stu-id="c3808-275">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport>.</span></span>
- <span data-ttu-id="c3808-276">EOP <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span><span class="sxs-lookup"><span data-stu-id="c3808-276">EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span></span>

![報告儀表板中的威脅防護狀態構件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="c3808-278">根據預設，圖表會顯示過去7天的資料。</span><span class="sxs-lookup"><span data-stu-id="c3808-278">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="c3808-279">如果您按一下 [ **篩選**]，可以選取90天的日期範圍 (試用訂閱可能限制為30天) 。</span><span class="sxs-lookup"><span data-stu-id="c3808-279">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="c3808-280">[詳細資料] 表格視圖允許篩選30天。</span><span class="sxs-lookup"><span data-stu-id="c3808-280">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="c3808-281">威脅防護狀態報表的報表檢視</span><span class="sxs-lookup"><span data-stu-id="c3808-281">Report view for the Threat protection status report</span></span>

<span data-ttu-id="c3808-282">可供使用的視圖如下：</span><span class="sxs-lookup"><span data-stu-id="c3808-282">The following views are available:</span></span>

- <span data-ttu-id="c3808-283">**資料查看方式：概述**：以下是顯示的偵測資訊：</span><span class="sxs-lookup"><span data-stu-id="c3808-283">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="c3808-284">**電子郵件惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="c3808-284">**Email malware**</span></span>
  - <span data-ttu-id="c3808-285">**電子郵件網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="c3808-285">**Email phish**</span></span>
  - <span data-ttu-id="c3808-286">**內容惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="c3808-286">**Content malware**</span></span>

  ![威脅防護狀態報表中的一覽視圖](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="c3808-288">**資料查看方式：內容 \> 惡意軟體**<sup>1</sup>：針對 Office 365 ATP 組織顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c3808-288">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Office 365 ATP organizations:</span></span>

  - <span data-ttu-id="c3808-289">**反惡意程式碼引擎**</span><span class="sxs-lookup"><span data-stu-id="c3808-289">**Anti-malware engine**</span></span>
  - <span data-ttu-id="c3808-290">**檔引爆**</span><span class="sxs-lookup"><span data-stu-id="c3808-290">**File detonation**</span></span>

  ![威脅防護狀態報表中的內容惡意程式碼視圖](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="c3808-292">**分解方式：偵測技術** 和 **查看資料：電子郵件網路釣魚：電子郵件 \> 網路釣魚**：下列資訊會顯示：</span><span class="sxs-lookup"><span data-stu-id="c3808-292">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="c3808-293">**ATP-產生的 URL 信譽**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c3808-293">**ATP-generated URL reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="c3808-294">**高級網路釣魚篩選器**</span><span class="sxs-lookup"><span data-stu-id="c3808-294">**Advanced phish filter**</span></span>
  - <span data-ttu-id="c3808-295">**反欺騙： DMARC 失敗**</span><span class="sxs-lookup"><span data-stu-id="c3808-295">**Anti-spoof: DMARC failure**</span></span>
  - <span data-ttu-id="c3808-296">**反欺騙：組織內**</span><span class="sxs-lookup"><span data-stu-id="c3808-296">**Anti-spoof: Intra-org**</span></span>
  - <span data-ttu-id="c3808-297">**反欺騙：外部網域**</span><span class="sxs-lookup"><span data-stu-id="c3808-297">**Anti-spoof: external domain**</span></span>
  - <span data-ttu-id="c3808-298">**品牌模仿**</span><span class="sxs-lookup"><span data-stu-id="c3808-298">**Brand impersonation**</span></span>
  - <span data-ttu-id="c3808-299">**網域**模擬<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c3808-299">**Domain impersonation**<sup>1</sup></span></span>
  - <span data-ttu-id="c3808-300">**EOP URL 信譽**</span><span class="sxs-lookup"><span data-stu-id="c3808-300">**EOP URL reputation**</span></span>
  - <span data-ttu-id="c3808-301">**一般網路釣魚篩選器**</span><span class="sxs-lookup"><span data-stu-id="c3808-301">**General phish filter**</span></span>
  - <span data-ttu-id="c3808-302">**別人**</span><span class="sxs-lookup"><span data-stu-id="c3808-302">**Others**</span></span>
  - <span data-ttu-id="c3808-303">**網路釣魚 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c3808-303">**Phish ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="c3808-304">**URL 引爆**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c3808-304">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="c3808-305">**使用者**模擬<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c3808-305">**User impersonation**<sup>1</sup></span></span>

  ![威脅防護狀態報表中網路釣魚電子郵件的偵測技術視圖](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="c3808-307">**分解方式：偵測技術** 和 **View Data：電子郵件 \> 惡意**代碼：會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c3808-307">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="c3808-308">**ATP-產生的檔信譽**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c3808-308">**ATP-generated file reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="c3808-309">**反惡意程式碼引擎**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c3808-309">**Anti-malware engine**<sup>1</sup></span></span>
  - <span data-ttu-id="c3808-310">**反惡意程式碼原則檔案類型區塊**</span><span class="sxs-lookup"><span data-stu-id="c3808-310">**Anti-malware policy file type block**</span></span>
  - <span data-ttu-id="c3808-311">**File 引爆**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c3808-311">**File detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="c3808-312">**惡意檔信譽**</span><span class="sxs-lookup"><span data-stu-id="c3808-312">**Malicious file reputation**</span></span>
  - <span data-ttu-id="c3808-313">**惡意程式碼 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c3808-313">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="c3808-314">**別人**</span><span class="sxs-lookup"><span data-stu-id="c3808-314">**Others**</span></span>

  ![威脅防護狀態報表中惡意程式碼的偵測技術視圖](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="c3808-316">**分解方式：原則類型** 和 \*\*view data \> \*\* by：電子郵件惡意程式碼： **電子郵件 \> 惡意**代碼：下列是顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c3808-316">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="c3808-317">**反惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="c3808-317">**Anti-malware**</span></span>
  - <span data-ttu-id="c3808-318">**安全附件**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c3808-318">**Safe Attachment**<sup>1</sup></span></span>
  - <span data-ttu-id="c3808-319">**反網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="c3808-319">**Anti-phish**</span></span>
  - <span data-ttu-id="c3808-320">**反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="c3808-320">**Anti-spam**</span></span>
  - <span data-ttu-id="c3808-321">**郵件流程規則** (也稱為傳輸規則) </span><span class="sxs-lookup"><span data-stu-id="c3808-321">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="c3808-322">**別人**</span><span class="sxs-lookup"><span data-stu-id="c3808-322">**Others**</span></span>

  ![威脅防護狀態報表中仿冒電子郵件的原則類型視圖](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="c3808-324">**分解方式：傳遞狀態** 和查看資料：電子郵件的 \*\* \> 網路釣魚詐騙\*\* 或 **view data：電子郵件 \> 惡意**代碼：會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c3808-324">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="c3808-325">**傳遞失敗**</span><span class="sxs-lookup"><span data-stu-id="c3808-325">**Delivery failed**</span></span>
  - <span data-ttu-id="c3808-326">**下降**</span><span class="sxs-lookup"><span data-stu-id="c3808-326">**Dropped**</span></span>
  - <span data-ttu-id="c3808-327">**轉發**</span><span class="sxs-lookup"><span data-stu-id="c3808-327">**Forwarded**</span></span>
  - <span data-ttu-id="c3808-328">**主控信箱：自訂資料夾**</span><span class="sxs-lookup"><span data-stu-id="c3808-328">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="c3808-329">**主控信箱：刪除的郵件**</span><span class="sxs-lookup"><span data-stu-id="c3808-329">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="c3808-330">**主控信箱：收件匣**</span><span class="sxs-lookup"><span data-stu-id="c3808-330">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="c3808-331">**主控信箱：垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="c3808-331">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="c3808-332">**內部部署伺服器：已傳送**</span><span class="sxs-lookup"><span data-stu-id="c3808-332">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="c3808-333">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="c3808-333">**Quarantine**</span></span>

  ![威脅防護狀態報表中仿冒電子郵件的傳遞狀態視圖](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="c3808-335">僅限<sup>1</sup>個 OFFICE 365 ATP</span><span class="sxs-lookup"><span data-stu-id="c3808-335"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="c3808-336"><sup>兩</sup> 個零小時自動清除 (ZAP) 無法在獨立 EOP 中使用 (它只適用于 Exchange Online 信箱) 。</span><span class="sxs-lookup"><span data-stu-id="c3808-336"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="c3808-337">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c3808-337">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="c3808-338">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c3808-338">**Start date** and **End date**</span></span>
- <span data-ttu-id="c3808-339">偵測值</span><span class="sxs-lookup"><span data-stu-id="c3808-339">Detection value</span></span>
- <span data-ttu-id="c3808-340"> (Office 365 ATP**保護**) ： **atp**或**EOP**。</span><span class="sxs-lookup"><span data-stu-id="c3808-340">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="c3808-341">請注意，View 資料中無法使用這種可篩選的屬性 **：內容 \> 惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="c3808-341">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="c3808-342">威脅防護狀態報表的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="c3808-342">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="c3808-343">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="c3808-343">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="c3808-344">**資料查看方式：內容 \> 惡意**代碼：</span><span class="sxs-lookup"><span data-stu-id="c3808-344">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="c3808-345">**Date**</span><span class="sxs-lookup"><span data-stu-id="c3808-345">**Date**</span></span>
  - <span data-ttu-id="c3808-346">**位置**</span><span class="sxs-lookup"><span data-stu-id="c3808-346">**Location**</span></span>
  - <span data-ttu-id="c3808-347">**導向者**</span><span class="sxs-lookup"><span data-stu-id="c3808-347">**Directed by**</span></span>
  - <span data-ttu-id="c3808-348">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="c3808-348">**Malware name**</span></span>

- <span data-ttu-id="c3808-349">**資料查看方式：一覽**：沒有可用的 **視圖詳細資料表格** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c3808-349">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="c3808-350">所有其他圖表：</span><span class="sxs-lookup"><span data-stu-id="c3808-350">All other charts:</span></span>

  - <span data-ttu-id="c3808-351">**Date**</span><span class="sxs-lookup"><span data-stu-id="c3808-351">**Date**</span></span>
  - <span data-ttu-id="c3808-352">**Subject**</span><span class="sxs-lookup"><span data-stu-id="c3808-352">**Subject**</span></span>
  - <span data-ttu-id="c3808-353">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c3808-353">**Sender**</span></span>
  - <span data-ttu-id="c3808-354">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="c3808-354">**Recipients**</span></span>
  - <span data-ttu-id="c3808-355">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="c3808-355">**Detected by**</span></span>
  - <span data-ttu-id="c3808-356">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="c3808-356">**Delivery status**</span></span>
  - <span data-ttu-id="c3808-357">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="c3808-357">**Source of compromise**</span></span>

<span data-ttu-id="c3808-358">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c3808-358">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="c3808-359">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c3808-359">**Start date** and **End date**</span></span>
- <span data-ttu-id="c3808-360">偵測值</span><span class="sxs-lookup"><span data-stu-id="c3808-360">Detection value</span></span>
- <span data-ttu-id="c3808-361"> (Office 365 ATP**保護**) ： **atp**或**EOP**。</span><span class="sxs-lookup"><span data-stu-id="c3808-361">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="c3808-362">請注意，View 資料中無法使用這種可篩選的屬性 **：內容 \> 惡意程式碼**。</span><span class="sxs-lookup"><span data-stu-id="c3808-362">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="c3808-363">主要惡意程式碼報告</span><span class="sxs-lookup"><span data-stu-id="c3808-363">Top malware report</span></span>

<span data-ttu-id="c3808-364">**主要惡意**代碼報告會顯示[EOP 中的反惡意程式碼防護](anti-malware-protection.md)所偵測到的各種惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="c3808-364">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="c3808-365">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **主要惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="c3808-365">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="c3808-366">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="c3808-366">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![報表儀表板中的主要惡意程式碼小工具](../../media/top-malware-report-widget.png)

<span data-ttu-id="c3808-368">當您將游標移到圓形圖中的楔形上方時，您可以看到惡意程式碼類型的名稱，以及偵測到該惡意程式碼的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="c3808-368">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![主要惡意程式碼報表檢視](../../media/top-malware-report-view.png)

<span data-ttu-id="c3808-370">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="c3808-370">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="c3808-371">**主要惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="c3808-371">**Top malware**</span></span>
- <span data-ttu-id="c3808-372">**Count**</span><span class="sxs-lookup"><span data-stu-id="c3808-372">**Count**</span></span>

<span data-ttu-id="c3808-373">如果您按一下 [報表檢視] 或 [詳細資料表格] 視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="c3808-373">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="c3808-374">URL 威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="c3808-374">URL threat protection report</span></span>

<span data-ttu-id="c3808-375">您可以在 Office 365 Advanced 威脅防護 (ATP) 中取得 **URL 威脅防護報告** 。</span><span class="sxs-lookup"><span data-stu-id="c3808-375">The **URL threat protection report** is available in Office 365 Advanced Threat Protection (ATP).</span></span> <span data-ttu-id="c3808-376">如需詳細資訊，請參閱 [URL 威脅防護報告](view-reports-for-atp.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="c3808-376">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="c3808-377">使用者報告的訊息報告</span><span class="sxs-lookup"><span data-stu-id="c3808-377">User-reported messages report</span></span>

<span data-ttu-id="c3808-378">「 **使用者報告的訊息** 報告」顯示使用者已使用 [報告郵件增益集](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)舉報為垃圾郵件、網路釣魚企圖或良好郵件的電子郵件資訊。</span><span class="sxs-lookup"><span data-stu-id="c3808-378">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="c3808-379">詳細資料可用於每封郵件，包括傳遞原因、為您的組織設定的垃圾郵件原則例外狀況或郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="c3808-379">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="c3808-380">若要查看詳細資料，請選取 [使用者報告] 清單中的專案，然後查看 [ **摘要** ] 和 [ **詳細資料** ] 索引標籤上的資訊。</span><span class="sxs-lookup"><span data-stu-id="c3808-380">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![使用者報告的郵件報告會顯示使用者標示為垃圾郵件，而非垃圾郵件或網路釣魚企圖。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="c3808-382">若要查看此報告，請在 [ [安全性 & 規範中心](https://protection.office.com)] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="c3808-382">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="c3808-383">移至 **威脅管理** \> **儀表板** \> **使用者報告的郵件**。</span><span class="sxs-lookup"><span data-stu-id="c3808-383">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="c3808-384">移至 **威脅管理** \> **檢查** \> **使用者報告的郵件**。</span><span class="sxs-lookup"><span data-stu-id="c3808-384">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![在 [安全性 & 規範中心] 中，選擇 [威脅管理] [ \> \> 使用者報告的郵件]](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="c3808-386">為了讓使用者報告的郵件報告正確運作，您必須為您的 Office 365 環境 **開啟審核記錄** 。</span><span class="sxs-lookup"><span data-stu-id="c3808-386">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="c3808-387">這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。</span><span class="sxs-lookup"><span data-stu-id="c3808-387">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="c3808-388">如需詳細資訊，請參閱 [開啟或關閉 Microsoft 365 審核記錄搜尋](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="c3808-388">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="c3808-389">查看這些報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="c3808-389">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="c3808-390">若要查看和使用報表，您必須是在安全性 & 規範中心 **和** Exchange Online 中所指定角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c3808-390">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="c3808-391">在安全性 & 規範中心，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="c3808-391">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="c3808-392">-組織管理-安全性管理員 (您也可以在 [Azure Active Directory 系統管理中心](https://aad.portal.azure.com) 進行此作業-安全性讀取器</span><span class="sxs-lookup"><span data-stu-id="c3808-392">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="c3808-393">如需詳細資訊，請參閱[安全性與合規性中心中的權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="c3808-393">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="c3808-394">在 Exchange Online 中，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="c3808-394">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="c3808-395">-組織管理-僅限查看組織管理-View-Only 收件者-合規性管理</span><span class="sxs-lookup"><span data-stu-id="c3808-395">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="c3808-396">如需詳細資訊，請參閱 exchange online 中的 [許可權](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 和 [exchange Online 中的管理角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="c3808-396">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="c3808-397">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="c3808-397">What if the reports aren't showing data?</span></span>

<span data-ttu-id="c3808-398">如果您未看到報表中的資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="c3808-398">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="c3808-399">若要深入瞭解，請參閱 [防禦威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="c3808-399">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3808-400">相關主題</span><span class="sxs-lookup"><span data-stu-id="c3808-400">Related topics</span></span>

[<span data-ttu-id="c3808-401">EOP 中的反垃圾郵件和反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="c3808-401">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="c3808-402">安全性與合規性中心內的智慧型報表和深入解析</span><span class="sxs-lookup"><span data-stu-id="c3808-402">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="c3808-403">在安全性 & 規範中心內，查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="c3808-403">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="c3808-404">檢視 Office 365 進階威脅防護的報告</span><span class="sxs-lookup"><span data-stu-id="c3808-404">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
