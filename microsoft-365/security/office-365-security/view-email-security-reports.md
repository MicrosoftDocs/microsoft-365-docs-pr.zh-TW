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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 瞭解如何尋找及使用貴組織的電子郵件安全性報告。 電子郵件安全性報告可在安全性 & 規範中心中取得。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11fe6fd76d21b2dbd7a3e651d40efaa79f675a43
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52531008"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="c09b1-104">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c09b1-105">**適用於**</span><span class="sxs-lookup"><span data-stu-id="c09b1-105">**Applies to**</span></span>
- [<span data-ttu-id="c09b1-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c09b1-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c09b1-107">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="c09b1-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c09b1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c09b1-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c09b1-109">[安全性 & 合規性中心](https://protection.office.com)提供各種報告，可協助您在保護組織時，看到 Microsoft 365 中的電子郵件安全性功能（例如，反垃圾郵件、反惡意程式碼和加密功能）。</span><span class="sxs-lookup"><span data-stu-id="c09b1-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="c09b1-110">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-these-reports)，您可以移至 [ **報表**] \> **儀表板**，在安全性 & 規範中心中查看這些報告。</span><span class="sxs-lookup"><span data-stu-id="c09b1-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="c09b1-111">若要直接移至 [報告] 儀表板，請開啟] <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全性 & 規範中心內的報告儀表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="c09b1-113">已遭破壞的使用者報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="c09b1-114">使用 Exchange Online 信箱的 Microsoft 365 組織可取得此報告。</span><span class="sxs-lookup"><span data-stu-id="c09b1-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="c09b1-115">無法在獨立 Exchange Online Protection (EOP) 組織中使用。</span><span class="sxs-lookup"><span data-stu-id="c09b1-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="c09b1-116">「已 **遭破壞的使用者** 報告」顯示顯示過去7天內已標示為 **可疑** 或 **限制** 的使用者帳戶數目。</span><span class="sxs-lookup"><span data-stu-id="c09b1-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="c09b1-117">在上述任一狀態的帳戶都有問題或甚至遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="c09b1-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="c09b1-118">在經常使用的情況下，您可以使用報表來找出峰值，甚至是趨勢，也就是可疑或受限制的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c09b1-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="c09b1-119">如需遭到破壞之使用者的詳細資訊，請參閱 [回應遭到破壞的電子郵件帳戶](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![報表儀表板中受損的使用者小工具](../../media/compromised-users-report-widget.png)

<span data-ttu-id="c09b1-121">匯總視圖會顯示過去90天的資料，詳細資料檢視會顯示過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="c09b1-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="c09b1-122">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [已 **遭破壞的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="c09b1-123">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="c09b1-124">您可以按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="c09b1-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="c09b1-125">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="c09b1-126">**可疑**：使用者帳戶已傳送可疑的電子郵件，而且受到限制傳送電子郵件的風險。</span><span class="sxs-lookup"><span data-stu-id="c09b1-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="c09b1-127">**限制**：由於高度可疑的模式，使用者帳戶已限制傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c09b1-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![已遭破壞之使用者報告中的報表檢視](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="c09b1-129">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="c09b1-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="c09b1-130">**建立時間**</span><span class="sxs-lookup"><span data-stu-id="c09b1-130">**Creation time**</span></span>
- <span data-ttu-id="c09b1-131">**User ID**</span><span class="sxs-lookup"><span data-stu-id="c09b1-131">**User ID**</span></span>
- <span data-ttu-id="c09b1-132">**Action**</span><span class="sxs-lookup"><span data-stu-id="c09b1-132">**Action**</span></span>

<span data-ttu-id="c09b1-133">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="c09b1-134">加密報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-134">Encryption report</span></span>

<span data-ttu-id="c09b1-135">您可以在 EOP (訂閱中使用 Exchange Online 或獨立 EOP 中的信箱，但沒有 Exchange Online 信箱) 的 **加密報告**。</span><span class="sxs-lookup"><span data-stu-id="c09b1-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="c09b1-136">組織的安全小組可以使用此報告中的資訊來識別模式，並主動套用或調整敏感電子郵件訊息的原則。</span><span class="sxs-lookup"><span data-stu-id="c09b1-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="c09b1-137">例如：</span><span class="sxs-lookup"><span data-stu-id="c09b1-137">For example:</span></span>

- <span data-ttu-id="c09b1-138">如果您看到大量的電子郵件是由使用者加密，您可能會想要新增加密原則，以自動化某些使用案例的加密。</span><span class="sxs-lookup"><span data-stu-id="c09b1-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="c09b1-139">如需詳細資訊，請參閱[定義郵件流程規則，以在 Microsoft 365 中加密電子郵件訊息](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="c09b1-140">如果您有許多可供使用的加密範本，但沒有人正在使用這些範本，您可能會探索使用者是否需要功能訓練。</span><span class="sxs-lookup"><span data-stu-id="c09b1-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="c09b1-141">匯總視圖允許篩選過去90天，而詳細資料檢視允許篩選10天。</span><span class="sxs-lookup"><span data-stu-id="c09b1-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="c09b1-142">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **加密報告**]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="c09b1-143">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="c09b1-144">若要深入瞭解加密，請參閱[Microsoft 365 中的電子郵件加密](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="c09b1-145">加密報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="c09b1-145">Report view for the Encryption report</span></span>

<span data-ttu-id="c09b1-146">您可以在圖表上使用下列篩選：</span><span class="sxs-lookup"><span data-stu-id="c09b1-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="c09b1-147">**查看資料：郵件加密報告** 和 **分解方式：加密方法**：下列為可用的加密方法：</span><span class="sxs-lookup"><span data-stu-id="c09b1-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="c09b1-148">**使用者加密**</span><span class="sxs-lookup"><span data-stu-id="c09b1-148">**Encryption by user**</span></span>
  - <span data-ttu-id="c09b1-149">**依原則加密**</span><span class="sxs-lookup"><span data-stu-id="c09b1-149">**Encryption by policy**</span></span>

  <span data-ttu-id="c09b1-150">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改此圖表：</span><span class="sxs-lookup"><span data-stu-id="c09b1-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="c09b1-151">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c09b1-152">加密方法。</span><span class="sxs-lookup"><span data-stu-id="c09b1-152">Encryption method.</span></span>
  - <span data-ttu-id="c09b1-153">加密範本。</span><span class="sxs-lookup"><span data-stu-id="c09b1-153">Encryption template.</span></span>

- <span data-ttu-id="c09b1-154">**查看資料：郵件加密報告** 和 **分解方式：加密範本**：下列為可供使用的加密方法：</span><span class="sxs-lookup"><span data-stu-id="c09b1-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="c09b1-155">**請勿轉寄**</span><span class="sxs-lookup"><span data-stu-id="c09b1-155">**Do not forward**</span></span>
  - <span data-ttu-id="c09b1-156">**只加密**</span><span class="sxs-lookup"><span data-stu-id="c09b1-156">**Encrypt only**</span></span>
  - <span data-ttu-id="c09b1-157">**OME 先前版本**</span><span class="sxs-lookup"><span data-stu-id="c09b1-157">**OME previous**</span></span>
  - <span data-ttu-id="c09b1-158">**自訂**</span><span class="sxs-lookup"><span data-stu-id="c09b1-158">**Custom**</span></span>

  <span data-ttu-id="c09b1-159">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改此圖表：</span><span class="sxs-lookup"><span data-stu-id="c09b1-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="c09b1-160">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c09b1-161">加密方法</span><span class="sxs-lookup"><span data-stu-id="c09b1-161">Encryption method</span></span>
  - <span data-ttu-id="c09b1-162">加密範本</span><span class="sxs-lookup"><span data-stu-id="c09b1-162">Encryption template</span></span>

- <span data-ttu-id="c09b1-163">**查看資料：前5位收件者網域**：此視圖會顯示圓形圖，其中包含前5位收件者網域的已傳送郵件計數。</span><span class="sxs-lookup"><span data-stu-id="c09b1-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="c09b1-164">如果您按一下 [ **篩選**]，您可以選取 [ **開始日期** ] 和 [ **結束日期**]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="c09b1-165">加密報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="c09b1-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="c09b1-166">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="c09b1-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="c09b1-167">**逐項換行：** 加密 **範本：加密範本**：下列會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c09b1-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="c09b1-168">**Date**</span><span class="sxs-lookup"><span data-stu-id="c09b1-168">**Date**</span></span>
  - <span data-ttu-id="c09b1-169">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="c09b1-169">**Sender address**</span></span>
  - <span data-ttu-id="c09b1-170">**加密範本**</span><span class="sxs-lookup"><span data-stu-id="c09b1-170">**Encryption template**</span></span>
  - <span data-ttu-id="c09b1-171">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="c09b1-171">**Encryption method**</span></span>
  - <span data-ttu-id="c09b1-172">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="c09b1-172">**Recipient address**</span></span>
  - <span data-ttu-id="c09b1-173">**主旨**</span><span class="sxs-lookup"><span data-stu-id="c09b1-173">**Subject**</span></span>

- <span data-ttu-id="c09b1-174">**資料查看依據：前5位收件者網域**：</span><span class="sxs-lookup"><span data-stu-id="c09b1-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="c09b1-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="c09b1-175">**Date**</span></span>
  - <span data-ttu-id="c09b1-176">**收件者網域**</span><span class="sxs-lookup"><span data-stu-id="c09b1-176">**Recipient domain**</span></span>
  - <span data-ttu-id="c09b1-177">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="c09b1-177">**Message count**</span></span>

<span data-ttu-id="c09b1-178">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="c09b1-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="c09b1-179">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="c09b1-180">加密方法</span><span class="sxs-lookup"><span data-stu-id="c09b1-180">Encryption method</span></span>
- <span data-ttu-id="c09b1-181">加密範本</span><span class="sxs-lookup"><span data-stu-id="c09b1-181">Encryption template</span></span>

<span data-ttu-id="c09b1-182">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="c09b1-183">郵件流程狀態報表</span><span class="sxs-lookup"><span data-stu-id="c09b1-183">Mailflow status report</span></span>

<span data-ttu-id="c09b1-184">**郵件流程狀態報表** 包含惡意程式碼、垃圾郵件、網路釣魚和 edge 封鎖郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c09b1-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="c09b1-185">如需詳細資訊，請參閱 [郵件流程 status report](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="c09b1-186">電子郵件報告中的惡意程式碼偵測</span><span class="sxs-lookup"><span data-stu-id="c09b1-186">Malware detections in email report</span></span>

<span data-ttu-id="c09b1-187">[**電子郵件中的惡意** 代碼偵測] 報告會顯示在 Exchange Online Protection 或 EOP) 所偵測到的內送和外寄電子 (郵件中，惡意程式碼偵測的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c09b1-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="c09b1-188">如需 EOP 中惡意程式碼保護的詳細資訊，請參閱 [EOP 中的反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="c09b1-189">匯總 view 篩選允許90天，而 [詳細資料表格篩選] 只允許10天。</span><span class="sxs-lookup"><span data-stu-id="c09b1-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="c09b1-190">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後 **在電子郵件中選取惡意** 代碼偵測。</span><span class="sxs-lookup"><span data-stu-id="c09b1-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="c09b1-191">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![在 [報告] 儀表板的電子郵件小工具中偵測惡意程式碼](../../media/malware-detections-widget.png)

<span data-ttu-id="c09b1-193">您可以按一下 [ **篩選** ] 並選取 [篩選]，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="c09b1-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="c09b1-194">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="c09b1-195">**入境**</span><span class="sxs-lookup"><span data-stu-id="c09b1-195">**Inbound**</span></span>
- <span data-ttu-id="c09b1-196">**出境**</span><span class="sxs-lookup"><span data-stu-id="c09b1-196">**Outbound**</span></span>

![電子郵件中的惡意程式碼偵測報表檢視](../../media/malware-detections-report-view.png)

<span data-ttu-id="c09b1-198">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="c09b1-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="c09b1-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="c09b1-199">**Date**</span></span>
- <span data-ttu-id="c09b1-200">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="c09b1-200">**Sender address**</span></span>
- <span data-ttu-id="c09b1-201">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="c09b1-201">**Recipient address**</span></span>
- <span data-ttu-id="c09b1-202">**郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中可用，且應該是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c09b1-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="c09b1-203">範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="c09b1-204">**主旨**</span><span class="sxs-lookup"><span data-stu-id="c09b1-204">**Subject**</span></span>
- <span data-ttu-id="c09b1-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="c09b1-205">**Filename**</span></span>
- <span data-ttu-id="c09b1-206">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="c09b1-206">**Malware name**</span></span>

<span data-ttu-id="c09b1-207">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="c09b1-208">郵件延遲報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-208">Mail latency report</span></span>

<span data-ttu-id="c09b1-209">**郵件延遲報告** 包含組織內的郵件傳遞和引爆延遲的資訊。</span><span class="sxs-lookup"><span data-stu-id="c09b1-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="c09b1-210">如需詳細資訊，請參閱 [郵件延遲報告](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="c09b1-211">傳送和接收的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-211">Sent and received email report</span></span>

<span data-ttu-id="c09b1-212">**傳送和接收的電子郵件** 報告包含惡意程式碼、垃圾郵件、郵件流程規則 (（也稱為傳輸規則) ）的相關資訊，以及電子郵件進入服務後的高級惡意軟體偵測。</span><span class="sxs-lookup"><span data-stu-id="c09b1-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="c09b1-213">如需詳細資訊，請參閱 [送出和接收的電子郵件報告](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="c09b1-214">垃圾郵件偵測報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-214">Spam detections report</span></span>

<span data-ttu-id="c09b1-215">**垃圾郵件** 偵測報告會顯示由 EOP 封鎖的垃圾電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c09b1-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="c09b1-216">郵件會個別計算，而不是每個收件者。</span><span class="sxs-lookup"><span data-stu-id="c09b1-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="c09b1-217">例如，如果相同的垃圾郵件已傳送給組織中的100收件者，則會算作一封郵件。</span><span class="sxs-lookup"><span data-stu-id="c09b1-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="c09b1-218">匯總視圖允許90天篩選，而詳細資料表格允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="c09b1-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="c09b1-219">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **垃圾郵件** 偵測]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="c09b1-220">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![報告儀表板中的垃圾郵件偵測小工具](../../media/spam-detections-report-widget.png)

<span data-ttu-id="c09b1-222">如需反垃圾郵件保護的詳細資訊，請參閱 [EOP 中的反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="c09b1-223">垃圾郵件偵測報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="c09b1-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="c09b1-224">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="c09b1-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="c09b1-225">**分解方式：動作**：會顯示下列事件種類：</span><span class="sxs-lookup"><span data-stu-id="c09b1-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="c09b1-226">**篩選的垃圾郵件內容**</span><span class="sxs-lookup"><span data-stu-id="c09b1-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="c09b1-227">**垃圾郵件 IP 封鎖**</span><span class="sxs-lookup"><span data-stu-id="c09b1-227">**Spam IP block**</span></span>
  - <span data-ttu-id="c09b1-228">**垃圾郵件信封封鎖**</span><span class="sxs-lookup"><span data-stu-id="c09b1-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="c09b1-229">**垃圾郵件 DBEB 篩選器**：以目錄為基礎的 edge 封鎖 (DBEB) </span><span class="sxs-lookup"><span data-stu-id="c09b1-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="c09b1-230">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您可以看到該天已封鎖的專案數，以及這些專案的分類方式。</span><span class="sxs-lookup"><span data-stu-id="c09b1-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![垃圾郵件偵測報告中的動作視圖](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="c09b1-232">**分解方式：方向**：下列方向如下：</span><span class="sxs-lookup"><span data-stu-id="c09b1-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="c09b1-233">**入境**</span><span class="sxs-lookup"><span data-stu-id="c09b1-233">**Inbound**</span></span>
  - <span data-ttu-id="c09b1-234">**出境**</span><span class="sxs-lookup"><span data-stu-id="c09b1-234">**Outbound**</span></span>

  ![垃圾郵件偵測報告中的方向視圖](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="c09b1-236">如果您按一下報表檢視中的 **篩選器** ，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="c09b1-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="c09b1-237">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="c09b1-238">方向值</span><span class="sxs-lookup"><span data-stu-id="c09b1-238">Direction values</span></span>
- <span data-ttu-id="c09b1-239">事件種類值</span><span class="sxs-lookup"><span data-stu-id="c09b1-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="c09b1-240">垃圾郵件偵測報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="c09b1-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="c09b1-241">如果您按一下任何報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c09b1-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="c09b1-242">**Date**</span><span class="sxs-lookup"><span data-stu-id="c09b1-242">**Date**</span></span>
- <span data-ttu-id="c09b1-243">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="c09b1-243">**Sender address**</span></span>
- <span data-ttu-id="c09b1-244">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="c09b1-244">**Recipient address**</span></span>
- <span data-ttu-id="c09b1-245">**事件類型**</span><span class="sxs-lookup"><span data-stu-id="c09b1-245">**Event type**</span></span>
- <span data-ttu-id="c09b1-246">**Action**</span><span class="sxs-lookup"><span data-stu-id="c09b1-246">**Action**</span></span>
- <span data-ttu-id="c09b1-247">**主旨**</span><span class="sxs-lookup"><span data-stu-id="c09b1-247">**Subject**</span></span>

<span data-ttu-id="c09b1-248">如果您按一下 [詳細資料] 表格中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="c09b1-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="c09b1-249">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="c09b1-250">方向值</span><span class="sxs-lookup"><span data-stu-id="c09b1-250">Direction values</span></span>
- <span data-ttu-id="c09b1-251">事件種類值</span><span class="sxs-lookup"><span data-stu-id="c09b1-251">Event type values</span></span>

<span data-ttu-id="c09b1-252">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="c09b1-253">欺騙偵測報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-253">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="c09b1-254">本文中所述的 [已改進的欺騙偵測報告] 是預覽中所述，視情況而變更，並非所有組織都提供這些報告。</span><span class="sxs-lookup"><span data-stu-id="c09b1-254">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="c09b1-255">舊的報表版本只會顯示出 **良好的郵件** ，並 **視為垃圾** 郵件。</span><span class="sxs-lookup"><span data-stu-id="c09b1-255">The older version of the report showed only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="c09b1-256">**欺騙** 偵測報告會顯示因欺騙性而封鎖或允許的郵件相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c09b1-256">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="c09b1-257">如需有關電子欺騙的詳細資訊，請參閱 [EOP 中的反欺騙防護](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-257">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="c09b1-258">報表的匯總視圖允許45天的篩選 <sup>\*</sup> ，而詳細資料檢視只允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="c09b1-258">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="c09b1-259"><sup>\*</sup> 最後，您將可以使用超過90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="c09b1-259"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="c09b1-260">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **偽造** 偵測]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-260">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="c09b1-261">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-261">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![報告儀表板中的欺騙偵測構件](../../media/spoof-detections-widget.png)

<span data-ttu-id="c09b1-263">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您可以看到偵測到的冒牌郵件數目及原因。</span><span class="sxs-lookup"><span data-stu-id="c09b1-263">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="c09b1-264">您可以按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="c09b1-264">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="c09b1-265">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-265">**Start date** and **End date**</span></span>

- <span data-ttu-id="c09b1-266">**結果**</span><span class="sxs-lookup"><span data-stu-id="c09b1-266">**Result**</span></span>
  - <span data-ttu-id="c09b1-267">**通過**</span><span class="sxs-lookup"><span data-stu-id="c09b1-267">**Pass**</span></span>
  - <span data-ttu-id="c09b1-268">**失敗**</span><span class="sxs-lookup"><span data-stu-id="c09b1-268">**Fail**</span></span>
  - <span data-ttu-id="c09b1-269">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="c09b1-269">**SoftPass**</span></span>
  - <span data-ttu-id="c09b1-270">**無**</span><span class="sxs-lookup"><span data-stu-id="c09b1-270">**None**</span></span>
  - <span data-ttu-id="c09b1-271">**其他**</span><span class="sxs-lookup"><span data-stu-id="c09b1-271">**Other**</span></span>

- <span data-ttu-id="c09b1-272">**哄騙類型**： **Internal** 和 **External**</span><span class="sxs-lookup"><span data-stu-id="c09b1-272">**Spoof type**: **Internal** and **External**</span></span>

![欺騙偵測報告中的報表檢視](../../media/spoof-detections-report-view.png)

<span data-ttu-id="c09b1-274">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="c09b1-274">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="c09b1-275">**Date**</span><span class="sxs-lookup"><span data-stu-id="c09b1-275">**Date**</span></span>
- <span data-ttu-id="c09b1-276">**偽裝的使用者**</span><span class="sxs-lookup"><span data-stu-id="c09b1-276">**Spoofed user**</span></span>
- <span data-ttu-id="c09b1-277">**傳送基礎結構**</span><span class="sxs-lookup"><span data-stu-id="c09b1-277">**Sending infrastructure**</span></span>
- <span data-ttu-id="c09b1-278">**哄騙類型**</span><span class="sxs-lookup"><span data-stu-id="c09b1-278">**Spoof type**</span></span>
- <span data-ttu-id="c09b1-279">**結果**</span><span class="sxs-lookup"><span data-stu-id="c09b1-279">**Result**</span></span>
- <span data-ttu-id="c09b1-280">**結果代碼**</span><span class="sxs-lookup"><span data-stu-id="c09b1-280">**Result code**</span></span>
- <span data-ttu-id="c09b1-281">**SPF**</span><span class="sxs-lookup"><span data-stu-id="c09b1-281">**SPF**</span></span>
- <span data-ttu-id="c09b1-282">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="c09b1-282">**DKIM**</span></span>
- <span data-ttu-id="c09b1-283">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="c09b1-283">**DMARC**</span></span>
- <span data-ttu-id="c09b1-284">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="c09b1-284">**Message count**</span></span>

<span data-ttu-id="c09b1-285">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-285">To go back to the report view, click **View report**.</span></span>

<span data-ttu-id="c09b1-286">如需複合驗證結果代碼的詳細資訊，請參閱[反垃圾郵件郵件頭 in Microsoft 365](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-286">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="c09b1-287">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-287">Threat protection status report</span></span>

<span data-ttu-id="c09b1-288">「**威脅防護狀態**」報告可用於 EOP 和 Microsoft Defender for Office 365。不過，報告包含不同的資料。</span><span class="sxs-lookup"><span data-stu-id="c09b1-288">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="c09b1-289">例如，EOP 客戶可以查看在電子郵件中偵測到惡意程式碼的相關資訊，但不是[SharePoint、OneDrive 及 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)所偵測到之惡意檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c09b1-289">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="c09b1-290">該報告提供包含惡意內容的電子郵件統計，例如檔案或網站位址 (URLs 反惡意程式碼引擎封鎖的) 、[零小時自動清除 (ZAP) ](zero-hour-auto-purge.md)，以及用於 Office 365 功能（如[安全連結](safe-links.md)、[安全附件](safe-attachments.md)和[反網路釣魚](set-up-anti-phishing-policies.md)）的 Defender。</span><span class="sxs-lookup"><span data-stu-id="c09b1-290">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="c09b1-291">您可以使用此資訊來識別趨勢，或判斷組織原則是否需要調整。</span><span class="sxs-lookup"><span data-stu-id="c09b1-291">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="c09b1-292">**附注：請** 務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為五個不同的郵件，而不是一封郵件。</span><span class="sxs-lookup"><span data-stu-id="c09b1-292">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="c09b1-293">若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **威脅防護狀態**]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-293">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="c09b1-294">若要直接前往報告，請開啟下列其中一個 URLs：</span><span class="sxs-lookup"><span data-stu-id="c09b1-294">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="c09b1-295">Microsoft Defender Office 365：<https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="c09b1-295">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="c09b1-296">EOP <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="c09b1-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![報告儀表板中的威脅防護狀態構件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="c09b1-298">根據預設，圖表會顯示過去7天的資料。</span><span class="sxs-lookup"><span data-stu-id="c09b1-298">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="c09b1-299">如果您按一下 [ **篩選**]，可以選取90天的日期範圍 (試用訂閱可能限制為30天) 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-299">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="c09b1-300">[詳細資料] 表格視圖允許篩選30天。</span><span class="sxs-lookup"><span data-stu-id="c09b1-300">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="c09b1-301">威脅防護狀態報表的報表檢視</span><span class="sxs-lookup"><span data-stu-id="c09b1-301">Report view for the Threat protection status report</span></span>

<span data-ttu-id="c09b1-302">您可使用下列檢視：</span><span class="sxs-lookup"><span data-stu-id="c09b1-302">The following views are available:</span></span>

- <span data-ttu-id="c09b1-303">**資料查看方式：概述**：以下是顯示的偵測資訊：</span><span class="sxs-lookup"><span data-stu-id="c09b1-303">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="c09b1-304">**電子郵件惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="c09b1-304">**Email malware**</span></span>
  - <span data-ttu-id="c09b1-305">**電子郵件網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="c09b1-305">**Email phish**</span></span>
  - <span data-ttu-id="c09b1-306">**內容惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="c09b1-306">**Content malware**</span></span>

  ![威脅防護狀態報表中的一覽視圖](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="c09b1-308">**資料查看方式：內容 \>惡意軟體**<sup>1</sup>：對 Office 365 組織的 Microsoft Defender 顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c09b1-308">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="c09b1-309">**反惡意程式碼引擎**： [Microsoft 365 中內建的病毒偵測](virus-detection-in-spo.md)，在 Sharepoint、OneDrive 及 Microsoft Teams 中偵測到惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="c09b1-309">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="c09b1-310">檔案 **引爆**： [SharePoint、OneDrive 及 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)所偵測到的惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="c09b1-310">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![威脅防護狀態報表中的內容惡意程式碼視圖](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="c09b1-312">**查看資料：郵件覆寫**：下列的覆寫原因資訊如下：</span><span class="sxs-lookup"><span data-stu-id="c09b1-312">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="c09b1-313">**內部部署略過**</span><span class="sxs-lookup"><span data-stu-id="c09b1-313">**On-premises skip**</span></span>
  - <span data-ttu-id="c09b1-314">**IP 允許**</span><span class="sxs-lookup"><span data-stu-id="c09b1-314">**IP Allow**</span></span>
  - <span data-ttu-id="c09b1-315">**郵件流程規則**</span><span class="sxs-lookup"><span data-stu-id="c09b1-315">**Mail flow rule**</span></span>
  - <span data-ttu-id="c09b1-316">**寄件者允許**</span><span class="sxs-lookup"><span data-stu-id="c09b1-316">**Sender allow**</span></span>
  - <span data-ttu-id="c09b1-317">**網域允許**</span><span class="sxs-lookup"><span data-stu-id="c09b1-317">**Domain allow**</span></span>
  - <span data-ttu-id="c09b1-318">**未啟用的 ZAP**</span><span class="sxs-lookup"><span data-stu-id="c09b1-318">**ZAP not enabled**</span></span>
  - <span data-ttu-id="c09b1-319">**未啟用垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="c09b1-319">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="c09b1-320">**使用者安全寄件者**</span><span class="sxs-lookup"><span data-stu-id="c09b1-320">**User Safe Sender**</span></span>
  - <span data-ttu-id="c09b1-321">**使用者安全網域**</span><span class="sxs-lookup"><span data-stu-id="c09b1-321">**User Safe Domain**</span></span>

  ![威脅防護狀態報表中的郵件覆寫視圖](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="c09b1-323">**分解方式：偵測技術** 和 **查看資料：電子郵件網路釣魚：電子郵件 \> 網路釣魚**：下列資訊會顯示：</span><span class="sxs-lookup"><span data-stu-id="c09b1-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="c09b1-324">**ATP 產生的 url 信譽**<sup>1</sup>：在其他 Microsoft 365 客戶的 Office 365 detonations 中，從 Defender 產生惡意 URL 信譽。</span><span class="sxs-lookup"><span data-stu-id="c09b1-324">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="c09b1-325">**高級網路釣魚篩選**：以機器學習為基礎的網路釣魚信號。</span><span class="sxs-lookup"><span data-stu-id="c09b1-325">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="c09b1-326">**反欺騙-DMARC 失敗**：郵件上的 DMARC 驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="c09b1-326">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="c09b1-327">**反欺騙-組織內**：寄件者正嘗試哄騙收件者網域。</span><span class="sxs-lookup"><span data-stu-id="c09b1-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="c09b1-328">**反欺騙-外部網域**：寄件者正嘗試哄騙其他一些網域。</span><span class="sxs-lookup"><span data-stu-id="c09b1-328">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="c09b1-329">**品牌** 模擬：模擬以寄件者為基礎的知名品牌。</span><span class="sxs-lookup"><span data-stu-id="c09b1-329">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="c09b1-330">**網域** 模擬 <sup>1</sup>：模仿客戶擁有或定義的網域。</span><span class="sxs-lookup"><span data-stu-id="c09b1-330">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="c09b1-331">**EOP url 信譽**：惡意 url 信譽。</span><span class="sxs-lookup"><span data-stu-id="c09b1-331">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="c09b1-332">**一般網路釣魚篩選器**：根據分析規則的網路釣魚信號。</span><span class="sxs-lookup"><span data-stu-id="c09b1-332">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="c09b1-333">**別人**</span><span class="sxs-lookup"><span data-stu-id="c09b1-333">**Others**</span></span>
  - <span data-ttu-id="c09b1-334">**網路釣魚 ZAP**<sup>2</sup>：零小時自動清除網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="c09b1-334">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="c09b1-335">**URL 引爆**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c09b1-335">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="c09b1-336">**使用者** 模擬 <sup>1</sup>：模擬由系統管理員定義或透過信箱智慧學出的使用者。</span><span class="sxs-lookup"><span data-stu-id="c09b1-336">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![威脅防護狀態報表中網路釣魚電子郵件的偵測技術視圖](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="c09b1-338">**分解方式：偵測技術** 和 **View Data：電子郵件 \> 惡意** 代碼：會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c09b1-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="c09b1-339">**ATP 產生的檔案信譽**<sup>1</sup>： Office 365 detonations 之 Defender 所產生的所有惡意檔信譽。</span><span class="sxs-lookup"><span data-stu-id="c09b1-339">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="c09b1-340">**反惡意程式碼引擎**<sup>1</sup>：偵測到反惡意程式碼引擎。</span><span class="sxs-lookup"><span data-stu-id="c09b1-340">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="c09b1-341">**反惡意程式碼原則檔案類型封鎖**：由於郵件中所識別的惡意檔案類型，郵件會篩選掉這些電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c09b1-341">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="c09b1-342">**檔引爆**<sup>1</sup>：由安全附件偵測。</span><span class="sxs-lookup"><span data-stu-id="c09b1-342">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="c09b1-343">**惡意檔信譽**</span><span class="sxs-lookup"><span data-stu-id="c09b1-343">**Malicious file reputation**</span></span>
  - <span data-ttu-id="c09b1-344">**惡意程式碼 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c09b1-344">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="c09b1-345">**別人**</span><span class="sxs-lookup"><span data-stu-id="c09b1-345">**Others**</span></span>

  ![威脅防護狀態報表中惡意程式碼的偵測技術視圖](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="c09b1-347">**分解方式：原則類型** 和 **view data \>** by：電子郵件惡意程式碼： **電子郵件 \> 惡意** 代碼：下列是顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c09b1-347">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="c09b1-348">**反惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="c09b1-348">**Anti-malware**</span></span>
  - <span data-ttu-id="c09b1-349">**安全附件**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c09b1-349">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="c09b1-350">**反網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="c09b1-350">**Anti-phish**</span></span>
  - <span data-ttu-id="c09b1-351">**反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="c09b1-351">**Anti-spam**</span></span>
  - <span data-ttu-id="c09b1-352">**郵件流程規則** (也稱為傳輸規則) </span><span class="sxs-lookup"><span data-stu-id="c09b1-352">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="c09b1-353">**別人**</span><span class="sxs-lookup"><span data-stu-id="c09b1-353">**Others**</span></span>

  ![威脅防護狀態報表中仿冒電子郵件的原則類型視圖](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="c09b1-355">**分解方式：傳遞狀態** 和查看資料：電子郵件的 **\> 網路釣魚詐騙** 或 **view data：電子郵件 \> 惡意** 代碼：會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c09b1-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="c09b1-356">**傳遞失敗**</span><span class="sxs-lookup"><span data-stu-id="c09b1-356">**Delivery failed**</span></span>
  - <span data-ttu-id="c09b1-357">**下降**</span><span class="sxs-lookup"><span data-stu-id="c09b1-357">**Dropped**</span></span>
  - <span data-ttu-id="c09b1-358">**轉發**</span><span class="sxs-lookup"><span data-stu-id="c09b1-358">**Forwarded**</span></span>
  - <span data-ttu-id="c09b1-359">**主控信箱：自訂資料夾**</span><span class="sxs-lookup"><span data-stu-id="c09b1-359">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="c09b1-360">**主控信箱：刪除的郵件**</span><span class="sxs-lookup"><span data-stu-id="c09b1-360">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="c09b1-361">**主控信箱：收件匣**</span><span class="sxs-lookup"><span data-stu-id="c09b1-361">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="c09b1-362">**主控信箱：垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="c09b1-362">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="c09b1-363">**內部部署伺服器：已傳送**</span><span class="sxs-lookup"><span data-stu-id="c09b1-363">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="c09b1-364">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="c09b1-364">**Quarantine**</span></span>

  ![威脅防護狀態報表中仿冒電子郵件的傳遞狀態視圖](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="c09b1-366"><sup>1</sup>僅限 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="c09b1-366"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="c09b1-367"><sup>兩</sup>個零小時自動清除 (ZAP) 不可用於獨立 EOP 中 (它只適用于 Exchange Online 信箱) 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-367"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="c09b1-368">如果您按一下 [ **篩選**]，可用的篩選取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="c09b1-368">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="c09b1-369">如需 **查看資料：內容 \> 惡意程式碼**，您可以依 **開始日期** 和 **結束日期** 以及 **偵測** 值，修改報告。</span><span class="sxs-lookup"><span data-stu-id="c09b1-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="c09b1-370">如需 **查看資料：郵件覆寫**，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c09b1-370">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c09b1-371">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-371">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c09b1-372">**覆寫原因**</span><span class="sxs-lookup"><span data-stu-id="c09b1-372">**Override Reason**</span></span>
  - <span data-ttu-id="c09b1-373">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-373">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="c09b1-374">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-374">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="c09b1-375">**網域**</span><span class="sxs-lookup"><span data-stu-id="c09b1-375">**Domain**</span></span>

- <span data-ttu-id="c09b1-376">對於所有其他視圖，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c09b1-376">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c09b1-377">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-377">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c09b1-378">**偵測**</span><span class="sxs-lookup"><span data-stu-id="c09b1-378">**Detection**</span></span>
  - <span data-ttu-id="c09b1-379">**保護者**： **ATP** 或 **EOP**</span><span class="sxs-lookup"><span data-stu-id="c09b1-379">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="c09b1-380">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-380">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="c09b1-381">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-381">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="c09b1-382">**網域**</span><span class="sxs-lookup"><span data-stu-id="c09b1-382">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="c09b1-383">威脅防護狀態報表的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="c09b1-383">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="c09b1-384">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="c09b1-384">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="c09b1-385">**資料查看方式：一覽**：沒有可用的 **視圖詳細資料表格** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c09b1-385">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="c09b1-386">**資料查看方式：內容 \> 惡意** 代碼：</span><span class="sxs-lookup"><span data-stu-id="c09b1-386">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="c09b1-387">**Date**</span><span class="sxs-lookup"><span data-stu-id="c09b1-387">**Date**</span></span>
  - <span data-ttu-id="c09b1-388">**位置**</span><span class="sxs-lookup"><span data-stu-id="c09b1-388">**Location**</span></span>
  - <span data-ttu-id="c09b1-389">**導向者**</span><span class="sxs-lookup"><span data-stu-id="c09b1-389">**Directed by**</span></span>
  - <span data-ttu-id="c09b1-390">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="c09b1-390">**Malware name**</span></span>

  <span data-ttu-id="c09b1-391">如果您按一下此視圖中的 [ **篩選器** ]，您可以依 **開始日期** 和 **結束日期** 以及 **偵測** 值，修改報告。</span><span class="sxs-lookup"><span data-stu-id="c09b1-391">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="c09b1-392">**查看資料：郵件覆寫**：</span><span class="sxs-lookup"><span data-stu-id="c09b1-392">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="c09b1-393">**Date**</span><span class="sxs-lookup"><span data-stu-id="c09b1-393">**Date**</span></span>
  - <span data-ttu-id="c09b1-394">**主旨**</span><span class="sxs-lookup"><span data-stu-id="c09b1-394">**Subject**</span></span>
  - <span data-ttu-id="c09b1-395">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c09b1-395">**Sender**</span></span>
  - <span data-ttu-id="c09b1-396">**收件者**</span><span class="sxs-lookup"><span data-stu-id="c09b1-396">**Recipients**</span></span>
  - <span data-ttu-id="c09b1-397">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="c09b1-397">**Detected by**</span></span>
  - <span data-ttu-id="c09b1-398">**覆寫原因**</span><span class="sxs-lookup"><span data-stu-id="c09b1-398">**Override Reason**</span></span>
  - <span data-ttu-id="c09b1-399">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="c09b1-399">**Source of Compromise**</span></span>
  - <span data-ttu-id="c09b1-400">**標記**</span><span class="sxs-lookup"><span data-stu-id="c09b1-400">**Tags**</span></span>

  <span data-ttu-id="c09b1-401">如果您按一下此視圖中的 **篩選器** ，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c09b1-401">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c09b1-402">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-402">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c09b1-403">**覆寫原因**</span><span class="sxs-lookup"><span data-stu-id="c09b1-403">**Override Reason**</span></span>
  - <span data-ttu-id="c09b1-404">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="c09b1-405">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="c09b1-406">**網域**</span><span class="sxs-lookup"><span data-stu-id="c09b1-406">**Domain**</span></span>
  - <span data-ttu-id="c09b1-407">收件 **者 (請** 注意，[詳細資料] 表格視圖中只提供此可篩選的屬性) </span><span class="sxs-lookup"><span data-stu-id="c09b1-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="c09b1-408">所有其他圖表：</span><span class="sxs-lookup"><span data-stu-id="c09b1-408">All other charts:</span></span>

  - <span data-ttu-id="c09b1-409">**Date**</span><span class="sxs-lookup"><span data-stu-id="c09b1-409">**Date**</span></span>
  - <span data-ttu-id="c09b1-410">**主旨**</span><span class="sxs-lookup"><span data-stu-id="c09b1-410">**Subject**</span></span>
  - <span data-ttu-id="c09b1-411">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c09b1-411">**Sender**</span></span>
  - <span data-ttu-id="c09b1-412">**收件者**</span><span class="sxs-lookup"><span data-stu-id="c09b1-412">**Recipients**</span></span>
  - <span data-ttu-id="c09b1-413">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="c09b1-413">**Detected by**</span></span>
  - <span data-ttu-id="c09b1-414">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="c09b1-414">**Delivery Status**</span></span>
  - <span data-ttu-id="c09b1-415">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="c09b1-415">**Source of Compromise**</span></span>
  - <span data-ttu-id="c09b1-416">**標記**</span><span class="sxs-lookup"><span data-stu-id="c09b1-416">**Tags**</span></span>

  <span data-ttu-id="c09b1-417">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="c09b1-417">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="c09b1-418">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="c09b1-418">**Start date** and **End date**</span></span>
  - <span data-ttu-id="c09b1-419">**偵測**</span><span class="sxs-lookup"><span data-stu-id="c09b1-419">**Detection**</span></span>
  - <span data-ttu-id="c09b1-420">**受保護**： Office 365 或 **EOP** **的 Defender**</span><span class="sxs-lookup"><span data-stu-id="c09b1-420">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="c09b1-421">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="c09b1-422">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="c09b1-423">**網域**</span><span class="sxs-lookup"><span data-stu-id="c09b1-423">**Domain**</span></span>
  - <span data-ttu-id="c09b1-424">收件 **者 (請** 注意，[詳細資料] 表格視圖中只提供此可篩選的屬性) </span><span class="sxs-lookup"><span data-stu-id="c09b1-424">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="c09b1-425">主要惡意程式碼報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-425">Top malware report</span></span>

<span data-ttu-id="c09b1-426">**主要惡意** 代碼報告會顯示 [EOP 中的反惡意程式碼防護](anti-malware-protection.md)所偵測到的各種惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="c09b1-426">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="c09b1-427">若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **主要惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="c09b1-427">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="c09b1-428">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="c09b1-428">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![報表儀表板中的主要惡意程式碼小工具](../../media/top-malware-report-widget.png)

<span data-ttu-id="c09b1-430">當您將游標移到圓形圖中的楔形上方時，您可以看到惡意程式碼類型的名稱，以及偵測到該惡意程式碼的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="c09b1-430">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![主要惡意程式碼報表檢視](../../media/top-malware-report-view.png)

<span data-ttu-id="c09b1-432">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="c09b1-432">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="c09b1-433">**主要惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="c09b1-433">**Top malware**</span></span>
- <span data-ttu-id="c09b1-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="c09b1-434">**Count**</span></span>

<span data-ttu-id="c09b1-435">如果您按一下 [報表檢視] 或 [詳細資料表格] 視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="c09b1-435">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="c09b1-436">URL 威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-436">URL threat protection report</span></span>

<span data-ttu-id="c09b1-437">Office 365 的「 **URL 威脅防護」報告** 可用於的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="c09b1-437">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="c09b1-438">如需詳細資訊，請參閱 [URL 威脅防護報告](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-438">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="c09b1-439">使用者報告的訊息報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-439">User-reported messages report</span></span>

<span data-ttu-id="c09b1-440">「 **使用者報告的訊息** 報告」顯示使用者已使用 [報告郵件增益集](enable-the-report-message-add-in.md) 或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md)舉報為垃圾郵件、網路釣魚企圖或良好郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c09b1-440">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="c09b1-441">詳細資料可用於每封郵件，包括傳遞原因、為您的組織設定的垃圾郵件原則例外狀況或郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="c09b1-441">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="c09b1-442">若要查看詳細資料，請選取 [使用者報告] 清單中的專案，然後查看 [ **摘要** ] 和 [ **詳細資料** ] 索引標籤上的資訊。</span><span class="sxs-lookup"><span data-stu-id="c09b1-442">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![User-Reported 郵件報告顯示使用者標示為垃圾郵件，而非垃圾郵件或網路釣魚企圖。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="c09b1-444">若要查看此報告，請在 [ [安全性 & 規範中心](https://protection.office.com)] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="c09b1-444">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="c09b1-445">移至 **威脅管理** \> **儀表板** \> **使用者報告的郵件**。</span><span class="sxs-lookup"><span data-stu-id="c09b1-445">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="c09b1-446">移至 **威脅管理** \> **檢查** \> **使用者報告的郵件**。</span><span class="sxs-lookup"><span data-stu-id="c09b1-446">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![在 [安全性 & 規範中心] 中，選擇 [威脅管理] [ \> \> 使用者報告的郵件]](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="c09b1-448">為了讓使用者報告的郵件報告正確運作，必須為您的 Office 365 環境 **開啟審計記錄**。</span><span class="sxs-lookup"><span data-stu-id="c09b1-448">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="c09b1-449">這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。</span><span class="sxs-lookup"><span data-stu-id="c09b1-449">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="c09b1-450">如需詳細資訊，請參閱[開啟或關閉 Microsoft 365 審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-450">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="c09b1-451">查看這些報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="c09b1-451">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="c09b1-452">為了查看和使用本文所述的報表，您必須是安全性 & 合規性中心之一的下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="c09b1-452">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="c09b1-453">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="c09b1-453">**Organization Management**</span></span>
- <span data-ttu-id="c09b1-454">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="c09b1-454">**Security Administrator**</span></span>
- <span data-ttu-id="c09b1-455">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="c09b1-455">**Security Reader**</span></span>
- <span data-ttu-id="c09b1-456">**全域讀取者**</span><span class="sxs-lookup"><span data-stu-id="c09b1-456">**Global Reader**</span></span>

<span data-ttu-id="c09b1-457">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-457">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="c09b1-458">**附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 的安全性 & 合規性中心 _和_ 許可權中所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="c09b1-458">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c09b1-459">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-459">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="c09b1-460">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="c09b1-460">What if the reports aren't showing data?</span></span>

<span data-ttu-id="c09b1-461">如果您未看到報表中的資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="c09b1-461">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="c09b1-462">若要深入瞭解，請參閱 [防禦威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="c09b1-462">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c09b1-463">相關主題</span><span class="sxs-lookup"><span data-stu-id="c09b1-463">Related topics</span></span>

[<span data-ttu-id="c09b1-464">EOP 中的反垃圾郵件和反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="c09b1-464">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="c09b1-465">安全性與合規性中心內的智慧型報表和深入解析</span><span class="sxs-lookup"><span data-stu-id="c09b1-465">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="c09b1-466">在安全性 & 規範中心內，查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-466">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="c09b1-467">View Office 365 的 Defender 報告</span><span class="sxs-lookup"><span data-stu-id="c09b1-467">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
