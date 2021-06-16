---
title: 在 Microsoft 365 Defender 入口網站中查看電子郵件安全性報告
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
description: 瞭解如何尋找及使用貴組織的電子郵件安全性報告。 Microsoft 365 Defender 入口網站中提供電子郵件安全性報告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb7570722fcc957ca86d68f6b42ef254578d7bd7
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930318"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="d9266-104">在 Microsoft 365 Defender 入口網站中查看電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="d9266-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d9266-105">**適用於**</span><span class="sxs-lookup"><span data-stu-id="d9266-105">**Applies to**</span></span>
- [<span data-ttu-id="d9266-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d9266-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d9266-107">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="d9266-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d9266-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9266-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d9266-109">[Microsoft 365 Defender 入口網站](https://security.microsoft.com)中提供各種報告，可協助您在保護組織時，看到 Microsoft 365 中的電子郵件安全性功能，例如反垃圾郵件、反惡意程式碼和加密功能。</span><span class="sxs-lookup"><span data-stu-id="d9266-109">A variety of reports are available in the [Microsoft 365 Defender portal](https://security.microsoft.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="d9266-110">如果您有 [必要的許可權](#what-permissions-are-needed-to-view-these-reports)，您可以在 Microsoft 365 Defender 入口網站中透過 **報告** \> **&** 共同作業 \> **電子郵件 &** 共同作業報告來查看這些報告。</span><span class="sxs-lookup"><span data-stu-id="d9266-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="d9266-111">若要直接移至 [報告] 儀表板，請開啟] <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="d9266-111">To go directly to the Reports dashboard, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender 入口網站中的報表儀表板](../../media/email-collaboration-reports.png)

## <a name="compromised-users-report"></a><span data-ttu-id="d9266-113">已遭破壞的使用者報告</span><span class="sxs-lookup"><span data-stu-id="d9266-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="d9266-114">使用 Exchange Online 信箱的 Microsoft 365 組織可取得此報告。</span><span class="sxs-lookup"><span data-stu-id="d9266-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="d9266-115">無法在獨立 Exchange Online Protection (EOP) 組織中使用。</span><span class="sxs-lookup"><span data-stu-id="d9266-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="d9266-116">「已 **遭破壞的使用者** 報告」顯示顯示過去7天內已標示為 **可疑** 或 **限制** 的使用者帳戶數目。</span><span class="sxs-lookup"><span data-stu-id="d9266-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="d9266-117">在上述任一狀態的帳戶都有問題或甚至遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="d9266-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="d9266-118">在經常使用的情況下，您可以使用報表來找出峰值，甚至是趨勢，也就是可疑或受限制的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d9266-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="d9266-119">如需遭到破壞之使用者的詳細資訊，請參閱 [回應遭到破壞的電子郵件帳戶](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![報表儀表板中受損的使用者小工具](../../media/compromised-users-report-widget.png)

<span data-ttu-id="d9266-121">匯總視圖會顯示過去90天的資料，詳細資料檢視會顯示過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="d9266-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="d9266-122">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 & 共同報告**]，然後按一下 [已 **遭破壞之使用者** 的 **詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d9266-122">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Compromised users**.</span></span> <span data-ttu-id="d9266-123">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="d9266-123">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="d9266-124">您可以按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="d9266-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="d9266-125">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="d9266-126">**可疑**：使用者帳戶已傳送可疑的電子郵件，而且受到限制傳送電子郵件的風險。</span><span class="sxs-lookup"><span data-stu-id="d9266-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="d9266-127">**限制**：由於高度可疑的模式，使用者帳戶已限制傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9266-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![已遭破壞之使用者報告中的報表檢視](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="d9266-129">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="d9266-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="d9266-130">**建立時間**</span><span class="sxs-lookup"><span data-stu-id="d9266-130">**Creation time**</span></span>
- <span data-ttu-id="d9266-131">**User ID**</span><span class="sxs-lookup"><span data-stu-id="d9266-131">**User ID**</span></span>
- <span data-ttu-id="d9266-132">**Action**</span><span class="sxs-lookup"><span data-stu-id="d9266-132">**Action**</span></span>

<span data-ttu-id="d9266-133">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="d9266-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="d9266-134">加密報告</span><span class="sxs-lookup"><span data-stu-id="d9266-134">Encryption report</span></span>

<span data-ttu-id="d9266-135">您可以在 EOP (訂閱中使用 Exchange Online 或獨立 EOP 中的信箱，但沒有 Exchange Online 信箱) 的 **加密報告**。</span><span class="sxs-lookup"><span data-stu-id="d9266-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="d9266-136">組織的安全小組可以使用此報告中的資訊來識別模式，並主動套用或調整敏感電子郵件訊息的原則。</span><span class="sxs-lookup"><span data-stu-id="d9266-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="d9266-137">例如：</span><span class="sxs-lookup"><span data-stu-id="d9266-137">For example:</span></span>

- <span data-ttu-id="d9266-138">如果您看到大量的電子郵件是由使用者加密，您可能會想要新增加密原則，以自動化某些使用案例的加密。</span><span class="sxs-lookup"><span data-stu-id="d9266-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="d9266-139">如需詳細資訊，請參閱[定義郵件流程規則，以在 Microsoft 365 中加密電子郵件訊息](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="d9266-140">如果您有許多可供使用的加密範本，但沒有人正在使用這些範本，您可能會探索使用者是否需要功能訓練。</span><span class="sxs-lookup"><span data-stu-id="d9266-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="d9266-141">匯總視圖允許篩選過去90天，而詳細資料檢視允許篩選10天。</span><span class="sxs-lookup"><span data-stu-id="d9266-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="d9266-142">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 & 共同報告**]，然後按一下 [**加密報告**] 底下的 [**查看詳細資料**]</span><span class="sxs-lookup"><span data-stu-id="d9266-142">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Encryption report**.</span></span> <span data-ttu-id="d9266-143">若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="d9266-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="d9266-144">若要深入瞭解加密，請參閱[Microsoft 365 中的電子郵件加密](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="d9266-145">加密報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="d9266-145">Report view for the Encryption report</span></span>

<span data-ttu-id="d9266-146">您可以在圖表上使用下列篩選：</span><span class="sxs-lookup"><span data-stu-id="d9266-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="d9266-147">**查看資料：郵件加密報告** 和 **分解方式：加密方法**：下列為可用的加密方法：</span><span class="sxs-lookup"><span data-stu-id="d9266-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="d9266-148">**使用者加密**</span><span class="sxs-lookup"><span data-stu-id="d9266-148">**Encryption by user**</span></span>
  - <span data-ttu-id="d9266-149">**依原則加密**</span><span class="sxs-lookup"><span data-stu-id="d9266-149">**Encryption by policy**</span></span>

  <span data-ttu-id="d9266-150">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改此圖表：</span><span class="sxs-lookup"><span data-stu-id="d9266-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="d9266-151">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d9266-152">加密方法。</span><span class="sxs-lookup"><span data-stu-id="d9266-152">Encryption method.</span></span>
  - <span data-ttu-id="d9266-153">加密範本。</span><span class="sxs-lookup"><span data-stu-id="d9266-153">Encryption template.</span></span>

- <span data-ttu-id="d9266-154">**查看資料：郵件加密報告** 和 **分解方式：加密範本**：下列為可供使用的加密方法：</span><span class="sxs-lookup"><span data-stu-id="d9266-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="d9266-155">**請勿轉寄**</span><span class="sxs-lookup"><span data-stu-id="d9266-155">**Do not forward**</span></span>
  - <span data-ttu-id="d9266-156">**只加密**</span><span class="sxs-lookup"><span data-stu-id="d9266-156">**Encrypt only**</span></span>
  - <span data-ttu-id="d9266-157">**OME 先前版本**</span><span class="sxs-lookup"><span data-stu-id="d9266-157">**OME previous**</span></span>
  - <span data-ttu-id="d9266-158">**自訂**</span><span class="sxs-lookup"><span data-stu-id="d9266-158">**Custom**</span></span>

  <span data-ttu-id="d9266-159">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改此圖表：</span><span class="sxs-lookup"><span data-stu-id="d9266-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="d9266-160">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d9266-161">加密方法</span><span class="sxs-lookup"><span data-stu-id="d9266-161">Encryption method</span></span>
  - <span data-ttu-id="d9266-162">加密範本</span><span class="sxs-lookup"><span data-stu-id="d9266-162">Encryption template</span></span>

- <span data-ttu-id="d9266-163">**查看資料：前5位收件者網域**：此視圖會顯示圓形圖，其中包含前5位收件者網域的已傳送郵件計數。</span><span class="sxs-lookup"><span data-stu-id="d9266-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="d9266-164">如果您按一下 [ **篩選**]，您可以選取 [ **開始日期** ] 和 [ **結束日期**]。</span><span class="sxs-lookup"><span data-stu-id="d9266-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="d9266-165">加密報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="d9266-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="d9266-166">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="d9266-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d9266-167">**逐項換行：** 加密 **範本：加密範本**：下列會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d9266-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="d9266-168">**Date**</span><span class="sxs-lookup"><span data-stu-id="d9266-168">**Date**</span></span>
  - <span data-ttu-id="d9266-169">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="d9266-169">**Sender address**</span></span>
  - <span data-ttu-id="d9266-170">**加密範本**</span><span class="sxs-lookup"><span data-stu-id="d9266-170">**Encryption template**</span></span>
  - <span data-ttu-id="d9266-171">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="d9266-171">**Encryption method**</span></span>
  - <span data-ttu-id="d9266-172">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="d9266-172">**Recipient address**</span></span>
  - <span data-ttu-id="d9266-173">**主旨**</span><span class="sxs-lookup"><span data-stu-id="d9266-173">**Subject**</span></span>

- <span data-ttu-id="d9266-174">**資料查看依據：前5位收件者網域**：</span><span class="sxs-lookup"><span data-stu-id="d9266-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="d9266-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="d9266-175">**Date**</span></span>
  - <span data-ttu-id="d9266-176">**收件者網域**</span><span class="sxs-lookup"><span data-stu-id="d9266-176">**Recipient domain**</span></span>
  - <span data-ttu-id="d9266-177">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="d9266-177">**Message count**</span></span>

<span data-ttu-id="d9266-178">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="d9266-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d9266-179">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="d9266-180">加密方法</span><span class="sxs-lookup"><span data-stu-id="d9266-180">Encryption method</span></span>
- <span data-ttu-id="d9266-181">加密範本</span><span class="sxs-lookup"><span data-stu-id="d9266-181">Encryption template</span></span>

<span data-ttu-id="d9266-182">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="d9266-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="d9266-183">郵件流程狀態報表</span><span class="sxs-lookup"><span data-stu-id="d9266-183">Mailflow status report</span></span>

<span data-ttu-id="d9266-184">**郵件流程狀態報表** 包含惡意程式碼、垃圾郵件、網路釣魚和 edge 封鎖郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d9266-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="d9266-185">如需詳細資訊，請參閱 [郵件流程 status report](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="d9266-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="d9266-186">電子郵件報告中的惡意程式碼偵測</span><span class="sxs-lookup"><span data-stu-id="d9266-186">Malware detections in email report</span></span>

<span data-ttu-id="d9266-187">[**電子郵件中的惡意** 代碼偵測] 報告會顯示在 Exchange Online Protection 或 EOP) 所偵測到的內送和外寄電子 (郵件中，惡意程式碼偵測的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d9266-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="d9266-188">如需 EOP 中惡意程式碼保護的詳細資訊，請參閱 [EOP 中的反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="d9266-189">匯總 view 篩選允許90天，而 [詳細資料表格篩選] 只允許10天。</span><span class="sxs-lookup"><span data-stu-id="d9266-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="d9266-190">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 &** 共同作業報告]，然後按一下 [**在電子郵件中偵測到惡意軟體的\*\*\*\*詳細資料**</span><span class="sxs-lookup"><span data-stu-id="d9266-190">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Malware detected in email**.</span></span> <span data-ttu-id="d9266-191">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="d9266-191">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![在 [報告] 儀表板的電子郵件小工具中偵測惡意程式碼](../../media/malware-detections-widget.png)

<span data-ttu-id="d9266-193">您可以按一下 [ **篩選** ] 並選取 [篩選]，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="d9266-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="d9266-194">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="d9266-195">**入境**</span><span class="sxs-lookup"><span data-stu-id="d9266-195">**Inbound**</span></span>
- <span data-ttu-id="d9266-196">**出境**</span><span class="sxs-lookup"><span data-stu-id="d9266-196">**Outbound**</span></span>

![電子郵件中的惡意程式碼偵測報表檢視](../../media/malware-detections-report-view.png)

<span data-ttu-id="d9266-198">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="d9266-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="d9266-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="d9266-199">**Date**</span></span>
- <span data-ttu-id="d9266-200">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="d9266-200">**Sender address**</span></span>
- <span data-ttu-id="d9266-201">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="d9266-201">**Recipient address**</span></span>
- <span data-ttu-id="d9266-202">**郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中可用，且應該是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d9266-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="d9266-203">範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。</span><span class="sxs-lookup"><span data-stu-id="d9266-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="d9266-204">**主旨**</span><span class="sxs-lookup"><span data-stu-id="d9266-204">**Subject**</span></span>
- <span data-ttu-id="d9266-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="d9266-205">**Filename**</span></span>
- <span data-ttu-id="d9266-206">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="d9266-206">**Malware name**</span></span>

<span data-ttu-id="d9266-207">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="d9266-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="d9266-208">郵件延遲報告</span><span class="sxs-lookup"><span data-stu-id="d9266-208">Mail latency report</span></span>

<span data-ttu-id="d9266-209">**郵件延遲報告** 包含組織內的郵件傳遞和引爆延遲的資訊。</span><span class="sxs-lookup"><span data-stu-id="d9266-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="d9266-210">如需詳細資訊，請參閱 [郵件延遲報告](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="d9266-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="d9266-211">傳送和接收的電子郵件報告</span><span class="sxs-lookup"><span data-stu-id="d9266-211">Sent and received email report</span></span>

<span data-ttu-id="d9266-212">**傳送和接收的電子郵件** 報告包含惡意程式碼、垃圾郵件、郵件流程規則 (（也稱為傳輸規則) ）的相關資訊，以及電子郵件進入服務後的高級惡意軟體偵測。</span><span class="sxs-lookup"><span data-stu-id="d9266-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="d9266-213">如需詳細資訊，請參閱 [送出和接收的電子郵件報告](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="d9266-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="d9266-214">垃圾郵件偵測報告</span><span class="sxs-lookup"><span data-stu-id="d9266-214">Spam detections report</span></span>

<span data-ttu-id="d9266-215">**垃圾郵件** 偵測報告會顯示由 EOP 封鎖的垃圾電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9266-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="d9266-216">郵件會個別計算，而不是每個收件者。</span><span class="sxs-lookup"><span data-stu-id="d9266-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="d9266-217">例如，如果相同的垃圾郵件已傳送給組織中的100收件者，則會算作一封郵件。</span><span class="sxs-lookup"><span data-stu-id="d9266-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="d9266-218">匯總視圖允許90天篩選，而詳細資料表格允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="d9266-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="d9266-219">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 & 共同報告**]，然後按一下 [**垃圾郵件** 偵測] 底下的 [**查看詳細資料**]</span><span class="sxs-lookup"><span data-stu-id="d9266-219">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click click **View details** under **Spam detections**.</span></span> <span data-ttu-id="d9266-220">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="d9266-220">To go directly to the report, open <https://security.microsoft.com/reports/SpamDetections>.</span></span>

![報告儀表板中的垃圾郵件偵測小工具](../../media/spam-detections-report-widget.png)

<span data-ttu-id="d9266-222">如需反垃圾郵件保護的詳細資訊，請參閱 [EOP 中的反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="d9266-223">垃圾郵件偵測報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="d9266-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="d9266-224">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="d9266-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="d9266-225">**分解方式：動作**：會顯示下列事件種類：</span><span class="sxs-lookup"><span data-stu-id="d9266-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="d9266-226">**篩選的垃圾郵件內容**</span><span class="sxs-lookup"><span data-stu-id="d9266-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="d9266-227">**垃圾郵件 IP 封鎖**</span><span class="sxs-lookup"><span data-stu-id="d9266-227">**Spam IP block**</span></span>
  - <span data-ttu-id="d9266-228">**垃圾郵件信封封鎖**</span><span class="sxs-lookup"><span data-stu-id="d9266-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="d9266-229">**垃圾郵件 DBEB 篩選器**：以目錄為基礎的 edge 封鎖 (DBEB) </span><span class="sxs-lookup"><span data-stu-id="d9266-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="d9266-230">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您可以看到該天已封鎖的專案數，以及這些專案的分類方式。</span><span class="sxs-lookup"><span data-stu-id="d9266-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![垃圾郵件偵測報告中的動作視圖](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="d9266-232">**分解方式：方向**：下列方向如下：</span><span class="sxs-lookup"><span data-stu-id="d9266-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="d9266-233">**入境**</span><span class="sxs-lookup"><span data-stu-id="d9266-233">**Inbound**</span></span>
  - <span data-ttu-id="d9266-234">**出境**</span><span class="sxs-lookup"><span data-stu-id="d9266-234">**Outbound**</span></span>

  ![垃圾郵件偵測報告中的方向視圖](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="d9266-236">如果您按一下報表檢視中的 **篩選器** ，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="d9266-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d9266-237">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="d9266-238">方向值</span><span class="sxs-lookup"><span data-stu-id="d9266-238">Direction values</span></span>
- <span data-ttu-id="d9266-239">事件種類值</span><span class="sxs-lookup"><span data-stu-id="d9266-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="d9266-240">垃圾郵件偵測報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="d9266-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="d9266-241">如果您按一下任何報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d9266-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="d9266-242">**Date**</span><span class="sxs-lookup"><span data-stu-id="d9266-242">**Date**</span></span>
- <span data-ttu-id="d9266-243">**寄件者位址**</span><span class="sxs-lookup"><span data-stu-id="d9266-243">**Sender address**</span></span>
- <span data-ttu-id="d9266-244">**收件者位址**</span><span class="sxs-lookup"><span data-stu-id="d9266-244">**Recipient address**</span></span>
- <span data-ttu-id="d9266-245">**事件類型**</span><span class="sxs-lookup"><span data-stu-id="d9266-245">**Event type**</span></span>
- <span data-ttu-id="d9266-246">**Action**</span><span class="sxs-lookup"><span data-stu-id="d9266-246">**Action**</span></span>
- <span data-ttu-id="d9266-247">**主旨**</span><span class="sxs-lookup"><span data-stu-id="d9266-247">**Subject**</span></span>

<span data-ttu-id="d9266-248">如果您按一下 [詳細資料] 表格中的 [ **篩選** ]，您可以使用下列篩選器修改結果：</span><span class="sxs-lookup"><span data-stu-id="d9266-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d9266-249">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="d9266-250">方向值</span><span class="sxs-lookup"><span data-stu-id="d9266-250">Direction values</span></span>
- <span data-ttu-id="d9266-251">事件種類值</span><span class="sxs-lookup"><span data-stu-id="d9266-251">Event type values</span></span>

<span data-ttu-id="d9266-252">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="d9266-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="d9266-253">欺騙偵測報告</span><span class="sxs-lookup"><span data-stu-id="d9266-253">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="d9266-254">本文中所述的 [已改進的欺騙偵測報告] 是預覽中所述，視情況而變更，並非所有組織都提供這些報告。</span><span class="sxs-lookup"><span data-stu-id="d9266-254">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="d9266-255">舊的報表版本只會顯示出 **良好的郵件** ，並 **視為垃圾** 郵件。</span><span class="sxs-lookup"><span data-stu-id="d9266-255">The older version of the report showed only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="d9266-256">**欺騙** 偵測報告會顯示因欺騙性而封鎖或允許的郵件相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d9266-256">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="d9266-257">如需有關電子欺騙的詳細資訊，請參閱 [EOP 中的反欺騙防護](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-257">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="d9266-258">報表的匯總視圖允許45天的篩選 <sup>\*</sup> ，而詳細資料檢視只允許10天的篩選。</span><span class="sxs-lookup"><span data-stu-id="d9266-258">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="d9266-259"><sup>\*</sup> 最後，您將可以使用超過90天的篩選。</span><span class="sxs-lookup"><span data-stu-id="d9266-259"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="d9266-260">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 & 共同報告**]，然後按一下 [**欺騙** 偵測] 底下的 [**查看詳細資料**]</span><span class="sxs-lookup"><span data-stu-id="d9266-260">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Spoof detections**.</span></span> <span data-ttu-id="d9266-261">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="d9266-261">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReport>.</span></span>

![報告儀表板中的欺騙偵測構件](../../media/spoof-detections-widget.png)

<span data-ttu-id="d9266-263">當您將滑鼠停留在圖表中的某一天 (資料點) 時，您可以看到偵測到的冒牌郵件數目及原因。</span><span class="sxs-lookup"><span data-stu-id="d9266-263">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="d9266-264">您可以按一下 [ **篩選** ] 並選取下列其中一個或多個值，以篩選圖表和詳細資料表格：</span><span class="sxs-lookup"><span data-stu-id="d9266-264">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="d9266-265">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-265">**Start date** and **End date**</span></span>

- <span data-ttu-id="d9266-266">**結果**</span><span class="sxs-lookup"><span data-stu-id="d9266-266">**Result**</span></span>
  - <span data-ttu-id="d9266-267">**通過**</span><span class="sxs-lookup"><span data-stu-id="d9266-267">**Pass**</span></span>
  - <span data-ttu-id="d9266-268">**失敗**</span><span class="sxs-lookup"><span data-stu-id="d9266-268">**Fail**</span></span>
  - <span data-ttu-id="d9266-269">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="d9266-269">**SoftPass**</span></span>
  - <span data-ttu-id="d9266-270">**無**</span><span class="sxs-lookup"><span data-stu-id="d9266-270">**None**</span></span>
  - <span data-ttu-id="d9266-271">**其他**</span><span class="sxs-lookup"><span data-stu-id="d9266-271">**Other**</span></span>

- <span data-ttu-id="d9266-272">**哄騙類型**： **Internal** 和 **External**</span><span class="sxs-lookup"><span data-stu-id="d9266-272">**Spoof type**: **Internal** and **External**</span></span>

![欺騙偵測報告中的報表檢視](../../media/spoof-detections-report-view.png)

<span data-ttu-id="d9266-274">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="d9266-274">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="d9266-275">**Date**</span><span class="sxs-lookup"><span data-stu-id="d9266-275">**Date**</span></span>
- <span data-ttu-id="d9266-276">**偽裝的使用者**</span><span class="sxs-lookup"><span data-stu-id="d9266-276">**Spoofed user**</span></span>
- <span data-ttu-id="d9266-277">**傳送基礎結構**</span><span class="sxs-lookup"><span data-stu-id="d9266-277">**Sending infrastructure**</span></span>
- <span data-ttu-id="d9266-278">**哄騙類型**</span><span class="sxs-lookup"><span data-stu-id="d9266-278">**Spoof type**</span></span>
- <span data-ttu-id="d9266-279">**結果**</span><span class="sxs-lookup"><span data-stu-id="d9266-279">**Result**</span></span>
- <span data-ttu-id="d9266-280">**結果代碼**</span><span class="sxs-lookup"><span data-stu-id="d9266-280">**Result code**</span></span>
- <span data-ttu-id="d9266-281">**SPF**</span><span class="sxs-lookup"><span data-stu-id="d9266-281">**SPF**</span></span>
- <span data-ttu-id="d9266-282">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="d9266-282">**DKIM**</span></span>
- <span data-ttu-id="d9266-283">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="d9266-283">**DMARC**</span></span>
- <span data-ttu-id="d9266-284">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="d9266-284">**Message count**</span></span>

<span data-ttu-id="d9266-285">若要回到報表檢視，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="d9266-285">To go back to the report view, click **View report**.</span></span>

<span data-ttu-id="d9266-286">如需複合驗證結果代碼的詳細資訊，請參閱[反垃圾郵件郵件頭 in Microsoft 365](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-286">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="d9266-287">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="d9266-287">Threat protection status report</span></span>

<span data-ttu-id="d9266-288">「**威脅防護狀態**」報告可用於 EOP 和 Microsoft Defender for Office 365。不過，報告包含不同的資料。</span><span class="sxs-lookup"><span data-stu-id="d9266-288">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="d9266-289">例如，EOP 客戶可以查看在電子郵件中偵測到惡意程式碼的相關資訊，但不是[SharePoint、OneDrive 及 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)所偵測到之惡意檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d9266-289">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="d9266-290">該報告提供包含惡意內容的電子郵件統計，例如檔案或網站位址 (URLs 反惡意程式碼引擎封鎖的) 、[零小時自動清除 (ZAP) ](zero-hour-auto-purge.md)，以及用於 Office 365 功能（如[安全連結](safe-links.md)、[安全附件](safe-attachments.md)和[反網路釣魚](set-up-anti-phishing-policies.md)）的 Defender。</span><span class="sxs-lookup"><span data-stu-id="d9266-290">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="d9266-291">您可以使用此資訊來識別趨勢，或判斷組織原則是否需要調整。</span><span class="sxs-lookup"><span data-stu-id="d9266-291">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="d9266-292">**附注：請** 務必瞭解，如果郵件傳送給五位收件者，我們會將其統計為五個不同的郵件，而不是一封郵件。</span><span class="sxs-lookup"><span data-stu-id="d9266-292">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="d9266-293">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 & 共同報告**]，然後按一下 [**威脅防護狀態**] 底下的 [**查看詳細資料**]</span><span class="sxs-lookup"><span data-stu-id="d9266-293">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Threat protection status**.</span></span> <span data-ttu-id="d9266-294">若要直接前往報告，請開啟下列其中一個 URLs：</span><span class="sxs-lookup"><span data-stu-id="d9266-294">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="d9266-295">Microsoft Defender Office 365：<https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="d9266-295">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="d9266-296">EOP <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="d9266-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![報告儀表板中的威脅防護狀態構件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="d9266-298">根據預設，圖表會顯示過去7天的資料。</span><span class="sxs-lookup"><span data-stu-id="d9266-298">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="d9266-299">如果您按一下 [ **篩選**]，可以選取90天的日期範圍 (試用訂閱可能限制為30天) 。</span><span class="sxs-lookup"><span data-stu-id="d9266-299">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="d9266-300">[詳細資料] 表格視圖允許篩選30天。</span><span class="sxs-lookup"><span data-stu-id="d9266-300">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="d9266-301">威脅防護狀態報表的報表檢視</span><span class="sxs-lookup"><span data-stu-id="d9266-301">Report view for the Threat protection status report</span></span>

<span data-ttu-id="d9266-302">您可使用下列檢視：</span><span class="sxs-lookup"><span data-stu-id="d9266-302">The following views are available:</span></span>

- <span data-ttu-id="d9266-303">**資料查看方式：概述**：以下是顯示的偵測資訊：</span><span class="sxs-lookup"><span data-stu-id="d9266-303">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="d9266-304">**電子郵件惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="d9266-304">**Email malware**</span></span>
  - <span data-ttu-id="d9266-305">**電子郵件網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="d9266-305">**Email phish**</span></span>
  - <span data-ttu-id="d9266-306">**內容惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="d9266-306">**Content malware**</span></span>

  ![威脅防護狀態報表中的一覽視圖](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="d9266-308">**資料查看方式：內容 \>惡意軟體**<sup>1</sup>：對 Office 365 組織的 Microsoft Defender 顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d9266-308">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="d9266-309">**反惡意程式碼引擎**： [Microsoft 365 中內建的病毒偵測](virus-detection-in-spo.md)，在 Sharepoint、OneDrive 及 Microsoft Teams 中偵測到惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="d9266-309">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="d9266-310">檔案 **引爆**： [SharePoint、OneDrive 及 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)所偵測到的惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="d9266-310">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![威脅防護狀態報表中的內容惡意程式碼視圖](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="d9266-312">**查看資料：郵件覆寫**：下列的覆寫原因資訊如下：</span><span class="sxs-lookup"><span data-stu-id="d9266-312">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="d9266-313">**內部部署略過**</span><span class="sxs-lookup"><span data-stu-id="d9266-313">**On-premises skip**</span></span>
  - <span data-ttu-id="d9266-314">**IP 允許**</span><span class="sxs-lookup"><span data-stu-id="d9266-314">**IP Allow**</span></span>
  - <span data-ttu-id="d9266-315">**郵件流程規則**</span><span class="sxs-lookup"><span data-stu-id="d9266-315">**Mail flow rule**</span></span>
  - <span data-ttu-id="d9266-316">**寄件者允許**</span><span class="sxs-lookup"><span data-stu-id="d9266-316">**Sender allow**</span></span>
  - <span data-ttu-id="d9266-317">**網域允許**</span><span class="sxs-lookup"><span data-stu-id="d9266-317">**Domain allow**</span></span>
  - <span data-ttu-id="d9266-318">**未啟用的 ZAP**</span><span class="sxs-lookup"><span data-stu-id="d9266-318">**ZAP not enabled**</span></span>
  - <span data-ttu-id="d9266-319">**未啟用垃圾郵件資料夾**</span><span class="sxs-lookup"><span data-stu-id="d9266-319">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="d9266-320">**使用者安全寄件者**</span><span class="sxs-lookup"><span data-stu-id="d9266-320">**User Safe Sender**</span></span>
  - <span data-ttu-id="d9266-321">**使用者安全網域**</span><span class="sxs-lookup"><span data-stu-id="d9266-321">**User Safe Domain**</span></span>

  ![威脅防護狀態報表中的郵件覆寫視圖](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="d9266-323">**分解方式：偵測技術** 和 **查看資料：電子郵件網路釣魚：電子郵件 \> 網路釣魚**：下列資訊會顯示：</span><span class="sxs-lookup"><span data-stu-id="d9266-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="d9266-324">**ATP 產生的 url 信譽**<sup>1</sup>：在其他 Microsoft 365 客戶的 Office 365 detonations 中，從 Defender 產生惡意 URL 信譽。</span><span class="sxs-lookup"><span data-stu-id="d9266-324">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="d9266-325">**高級網路釣魚篩選**：以機器學習為基礎的網路釣魚信號。</span><span class="sxs-lookup"><span data-stu-id="d9266-325">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="d9266-326">**反欺騙-DMARC 失敗**：郵件上的 DMARC 驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="d9266-326">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="d9266-327">**反欺騙-組織內**：寄件者正嘗試哄騙收件者網域。</span><span class="sxs-lookup"><span data-stu-id="d9266-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="d9266-328">**反欺騙-外部網域**：寄件者正嘗試哄騙其他一些網域。</span><span class="sxs-lookup"><span data-stu-id="d9266-328">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="d9266-329">**品牌** 模擬：模擬以寄件者為基礎的知名品牌。</span><span class="sxs-lookup"><span data-stu-id="d9266-329">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="d9266-330">**網域** 模擬 <sup>1</sup>：模仿客戶擁有或定義的網域。</span><span class="sxs-lookup"><span data-stu-id="d9266-330">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="d9266-331">**EOP url 信譽**：惡意 url 信譽。</span><span class="sxs-lookup"><span data-stu-id="d9266-331">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="d9266-332">**一般網路釣魚篩選器**：根據分析規則的網路釣魚信號。</span><span class="sxs-lookup"><span data-stu-id="d9266-332">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="d9266-333">**別人**</span><span class="sxs-lookup"><span data-stu-id="d9266-333">**Others**</span></span>
  - <span data-ttu-id="d9266-334">**網路釣魚 ZAP**<sup>2</sup>：零小時自動清除網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="d9266-334">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="d9266-335">**URL 引爆**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d9266-335">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="d9266-336">**使用者** 模擬 <sup>1</sup>：模擬由系統管理員定義或透過信箱智慧學出的使用者。</span><span class="sxs-lookup"><span data-stu-id="d9266-336">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![威脅防護狀態報表中網路釣魚電子郵件的偵測技術視圖](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="d9266-338">**分解方式：偵測技術** 和 **View Data：電子郵件 \> 惡意** 代碼：會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d9266-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="d9266-339">**ATP 產生的檔案信譽**<sup>1</sup>： Office 365 detonations 之 Defender 所產生的所有惡意檔信譽。</span><span class="sxs-lookup"><span data-stu-id="d9266-339">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="d9266-340">**反惡意程式碼引擎**<sup>1</sup>：偵測到反惡意程式碼引擎。</span><span class="sxs-lookup"><span data-stu-id="d9266-340">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="d9266-341">**反惡意程式碼原則檔案類型封鎖**：由於郵件中所識別的惡意檔案類型，郵件會篩選掉這些電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9266-341">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="d9266-342">**檔引爆**<sup>1</sup>：由安全附件偵測。</span><span class="sxs-lookup"><span data-stu-id="d9266-342">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="d9266-343">**惡意檔信譽**</span><span class="sxs-lookup"><span data-stu-id="d9266-343">**Malicious file reputation**</span></span>
  - <span data-ttu-id="d9266-344">**惡意程式碼 ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d9266-344">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="d9266-345">**別人**</span><span class="sxs-lookup"><span data-stu-id="d9266-345">**Others**</span></span>

  ![威脅防護狀態報表中惡意程式碼的偵測技術視圖](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="d9266-347">**分解方式：原則類型** 和 **view data \>** by：電子郵件惡意程式碼： **電子郵件 \> 惡意** 代碼：下列是顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d9266-347">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="d9266-348">**反惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="d9266-348">**Anti-malware**</span></span>
  - <span data-ttu-id="d9266-349">**安全附件**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d9266-349">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="d9266-350">**反網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="d9266-350">**Anti-phish**</span></span>
  - <span data-ttu-id="d9266-351">**反垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="d9266-351">**Anti-spam**</span></span>
  - <span data-ttu-id="d9266-352">**郵件流程規則** (也稱為傳輸規則) </span><span class="sxs-lookup"><span data-stu-id="d9266-352">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="d9266-353">**別人**</span><span class="sxs-lookup"><span data-stu-id="d9266-353">**Others**</span></span>

  ![威脅防護狀態報表中仿冒電子郵件的原則類型視圖](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="d9266-355">**分解方式：傳遞狀態** 和查看資料：電子郵件的 **\> 網路釣魚詐騙** 或 **view data：電子郵件 \> 惡意** 代碼：會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d9266-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="d9266-356">**傳遞失敗**</span><span class="sxs-lookup"><span data-stu-id="d9266-356">**Delivery failed**</span></span>
  - <span data-ttu-id="d9266-357">**下降**</span><span class="sxs-lookup"><span data-stu-id="d9266-357">**Dropped**</span></span>
  - <span data-ttu-id="d9266-358">**轉發**</span><span class="sxs-lookup"><span data-stu-id="d9266-358">**Forwarded**</span></span>
  - <span data-ttu-id="d9266-359">**主控信箱：自訂資料夾**</span><span class="sxs-lookup"><span data-stu-id="d9266-359">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="d9266-360">**主控信箱：刪除的郵件**</span><span class="sxs-lookup"><span data-stu-id="d9266-360">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="d9266-361">**主控信箱：收件匣**</span><span class="sxs-lookup"><span data-stu-id="d9266-361">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="d9266-362">**主控信箱：垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="d9266-362">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="d9266-363">**內部部署伺服器：已傳送**</span><span class="sxs-lookup"><span data-stu-id="d9266-363">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="d9266-364">**隔離區**</span><span class="sxs-lookup"><span data-stu-id="d9266-364">**Quarantine**</span></span>

  ![威脅防護狀態報表中仿冒電子郵件的傳遞狀態視圖](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="d9266-366"><sup>1</sup>僅限 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="d9266-366"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="d9266-367"><sup>兩</sup>個零小時自動清除 (ZAP) 不可用於獨立 EOP 中 (它只適用于 Exchange Online 信箱) 。</span><span class="sxs-lookup"><span data-stu-id="d9266-367"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="d9266-368">如果您按一下 [ **篩選**]，可用的篩選取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="d9266-368">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d9266-369">如需 **查看資料：內容 \> 惡意程式碼**，您可以依 **開始日期** 和 **結束日期** 以及 **偵測** 值，修改報告。</span><span class="sxs-lookup"><span data-stu-id="d9266-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="d9266-370">如需 **查看資料：郵件覆寫**，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="d9266-370">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d9266-371">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-371">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d9266-372">**覆寫原因**</span><span class="sxs-lookup"><span data-stu-id="d9266-372">**Override Reason**</span></span>
  - <span data-ttu-id="d9266-373">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="d9266-373">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d9266-374">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-374">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="d9266-375">**網域**</span><span class="sxs-lookup"><span data-stu-id="d9266-375">**Domain**</span></span>

- <span data-ttu-id="d9266-376">對於所有其他視圖，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="d9266-376">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d9266-377">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-377">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d9266-378">**偵測**</span><span class="sxs-lookup"><span data-stu-id="d9266-378">**Detection**</span></span>
  - <span data-ttu-id="d9266-379">**保護者**： **ATP** 或 **EOP**</span><span class="sxs-lookup"><span data-stu-id="d9266-379">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="d9266-380">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="d9266-380">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d9266-381">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-381">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="d9266-382">**網域**</span><span class="sxs-lookup"><span data-stu-id="d9266-382">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="d9266-383">威脅防護狀態報表的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="d9266-383">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="d9266-384">如果您按一下 [ **查看詳細資料] 表格**，顯示的資訊將取決於您所查看的圖表：</span><span class="sxs-lookup"><span data-stu-id="d9266-384">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d9266-385">**資料查看方式：一覽**：沒有可用的 **視圖詳細資料表格** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d9266-385">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="d9266-386">**資料查看方式：內容 \> 惡意** 代碼：</span><span class="sxs-lookup"><span data-stu-id="d9266-386">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="d9266-387">**Date**</span><span class="sxs-lookup"><span data-stu-id="d9266-387">**Date**</span></span>
  - <span data-ttu-id="d9266-388">**位置**</span><span class="sxs-lookup"><span data-stu-id="d9266-388">**Location**</span></span>
  - <span data-ttu-id="d9266-389">**導向者**</span><span class="sxs-lookup"><span data-stu-id="d9266-389">**Directed by**</span></span>
  - <span data-ttu-id="d9266-390">**惡意軟體名稱**</span><span class="sxs-lookup"><span data-stu-id="d9266-390">**Malware name**</span></span>

  <span data-ttu-id="d9266-391">如果您按一下此視圖中的 [ **篩選器** ]，您可以依 **開始日期** 和 **結束日期** 以及 **偵測** 值，修改報告。</span><span class="sxs-lookup"><span data-stu-id="d9266-391">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="d9266-392">**查看資料：郵件覆寫**：</span><span class="sxs-lookup"><span data-stu-id="d9266-392">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="d9266-393">**Date**</span><span class="sxs-lookup"><span data-stu-id="d9266-393">**Date**</span></span>
  - <span data-ttu-id="d9266-394">**主旨**</span><span class="sxs-lookup"><span data-stu-id="d9266-394">**Subject**</span></span>
  - <span data-ttu-id="d9266-395">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d9266-395">**Sender**</span></span>
  - <span data-ttu-id="d9266-396">**收件者**</span><span class="sxs-lookup"><span data-stu-id="d9266-396">**Recipients**</span></span>
  - <span data-ttu-id="d9266-397">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="d9266-397">**Detected by**</span></span>
  - <span data-ttu-id="d9266-398">**覆寫原因**</span><span class="sxs-lookup"><span data-stu-id="d9266-398">**Override Reason**</span></span>
  - <span data-ttu-id="d9266-399">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="d9266-399">**Source of Compromise**</span></span>
  - <span data-ttu-id="d9266-400">**標記**</span><span class="sxs-lookup"><span data-stu-id="d9266-400">**Tags**</span></span>

  <span data-ttu-id="d9266-401">如果您按一下此視圖中的 **篩選器** ，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="d9266-401">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d9266-402">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-402">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d9266-403">**覆寫原因**</span><span class="sxs-lookup"><span data-stu-id="d9266-403">**Override Reason**</span></span>
  - <span data-ttu-id="d9266-404">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="d9266-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d9266-405">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="d9266-406">**網域**</span><span class="sxs-lookup"><span data-stu-id="d9266-406">**Domain**</span></span>
  - <span data-ttu-id="d9266-407">收件 **者 (請** 注意，[詳細資料] 表格視圖中只提供此可篩選的屬性) </span><span class="sxs-lookup"><span data-stu-id="d9266-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="d9266-408">所有其他圖表：</span><span class="sxs-lookup"><span data-stu-id="d9266-408">All other charts:</span></span>

  - <span data-ttu-id="d9266-409">**Date**</span><span class="sxs-lookup"><span data-stu-id="d9266-409">**Date**</span></span>
  - <span data-ttu-id="d9266-410">**主旨**</span><span class="sxs-lookup"><span data-stu-id="d9266-410">**Subject**</span></span>
  - <span data-ttu-id="d9266-411">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d9266-411">**Sender**</span></span>
  - <span data-ttu-id="d9266-412">**收件者**</span><span class="sxs-lookup"><span data-stu-id="d9266-412">**Recipients**</span></span>
  - <span data-ttu-id="d9266-413">**偵測到**</span><span class="sxs-lookup"><span data-stu-id="d9266-413">**Detected by**</span></span>
  - <span data-ttu-id="d9266-414">**傳遞狀態**</span><span class="sxs-lookup"><span data-stu-id="d9266-414">**Delivery Status**</span></span>
  - <span data-ttu-id="d9266-415">**受損來源**</span><span class="sxs-lookup"><span data-stu-id="d9266-415">**Source of Compromise**</span></span>
  - <span data-ttu-id="d9266-416">**標記**</span><span class="sxs-lookup"><span data-stu-id="d9266-416">**Tags**</span></span>

  <span data-ttu-id="d9266-417">如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：</span><span class="sxs-lookup"><span data-stu-id="d9266-417">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d9266-418">**開始日期** 和 **結束日期**</span><span class="sxs-lookup"><span data-stu-id="d9266-418">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d9266-419">**偵測**</span><span class="sxs-lookup"><span data-stu-id="d9266-419">**Detection**</span></span>
  - <span data-ttu-id="d9266-420">**受保護**： Office 365 或 **EOP** **的 Defender**</span><span class="sxs-lookup"><span data-stu-id="d9266-420">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="d9266-421">**標記**：依已套用指定使用者標記的使用者或群組來篩選結果 (包含優先順序帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="d9266-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="d9266-422">如需使用者標記的相關資訊，請參閱 [user tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="d9266-423">**網域**</span><span class="sxs-lookup"><span data-stu-id="d9266-423">**Domain**</span></span>
  - <span data-ttu-id="d9266-424">收件 **者 (請** 注意，[詳細資料] 表格視圖中只提供此可篩選的屬性) </span><span class="sxs-lookup"><span data-stu-id="d9266-424">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="d9266-425">主要惡意程式碼報告</span><span class="sxs-lookup"><span data-stu-id="d9266-425">Top malware report</span></span>

<span data-ttu-id="d9266-426">**主要惡意** 代碼報告會顯示 [EOP 中的反惡意程式碼防護](anti-malware-protection.md)所偵測到的各種惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="d9266-426">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="d9266-427">若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 & 共同報告**]，然後按一下 [**主要惡意** 代碼] 底下的 [**查看詳細資料**</span><span class="sxs-lookup"><span data-stu-id="d9266-427">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Top malware**.</span></span> <span data-ttu-id="d9266-428">若要直接前往報表，請開啟 <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="d9266-428">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![報表儀表板中的主要惡意程式碼小工具](../../media/top-malware-report-widget.png)

<span data-ttu-id="d9266-430">當您將游標移到圓形圖中的楔形上方時，您可以看到惡意程式碼類型的名稱，以及偵測到該惡意程式碼的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="d9266-430">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![主要惡意程式碼報表檢視](../../media/top-malware-report-view.png)

<span data-ttu-id="d9266-432">如果您按一下 [ **查看詳細資料] 表格**，您可以看到下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="d9266-432">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="d9266-433">**主要惡意程式碼**</span><span class="sxs-lookup"><span data-stu-id="d9266-433">**Top malware**</span></span>
- <span data-ttu-id="d9266-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="d9266-434">**Count**</span></span>

<span data-ttu-id="d9266-435">如果您按一下 [報表檢視] 或 [詳細資料表格] 視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="d9266-435">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="d9266-436">URL 威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="d9266-436">URL threat protection report</span></span>

<span data-ttu-id="d9266-437">Office 365 的「 **URL 威脅防護」報告** 可用於的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="d9266-437">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="d9266-438">如需詳細資訊，請參閱 [URL 威脅防護報告](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="d9266-438">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="d9266-439">使用者報告的訊息報告</span><span class="sxs-lookup"><span data-stu-id="d9266-439">User reported messages report</span></span>

<span data-ttu-id="d9266-440">「 **使用者報告的訊息** 報告」顯示使用者已使用 [報告郵件增益集](enable-the-report-message-add-in.md) 或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md)舉報為垃圾郵件、網路釣魚企圖或良好郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d9266-440">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="d9266-441">詳細資料可用於每封郵件，包括傳遞原因、為您的組織設定的垃圾郵件原則例外狀況或郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="d9266-441">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="d9266-442">若要查看詳細資料，請選取 [使用者報告] 清單中的專案，然後查看 [ **摘要** ] 和 [ **詳細資料** ] 索引標籤上的資訊。</span><span class="sxs-lookup"><span data-stu-id="d9266-442">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![「使用者報告的訊息報告」顯示使用者標示為垃圾郵件，而非垃圾郵件或網路釣魚企圖。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="d9266-444">若要查看此報告，請在 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)中，移至 **Reports** \> **email &** 共同作業 \> **電子郵件 & 共同作業報告** \> **使用者報告的訊息**。</span><span class="sxs-lookup"><span data-stu-id="d9266-444">To view this report, in the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span>

- <span data-ttu-id="d9266-445">移至 **報表** \> **電子郵件 &** 共同作業 \> **電子郵件 & 共同作業報告** \> **使用者報告的訊息**。</span><span class="sxs-lookup"><span data-stu-id="d9266-445">Go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** \> **User reported messages**.</span></span>

![在 Microsoft 365 Defender 入口網站中，選擇報表 \> 電子郵件 & 共同作業 \> 電子郵件 & 共同作業報告 \> 使用者報告的訊息](../../media/user-reported-messages.png)

> [!IMPORTANT]
> <span data-ttu-id="d9266-447">為了讓使用者報告的訊息報告正確運作，必須為您的 Office 365 環境 **開啟審核記錄**。</span><span class="sxs-lookup"><span data-stu-id="d9266-447">In order for the User reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="d9266-448">這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。</span><span class="sxs-lookup"><span data-stu-id="d9266-448">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="d9266-449">如需詳細資訊，請參閱[開啟或關閉 Microsoft 365 審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-449">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="d9266-450">查看這些報表所需的許可權為何？</span><span class="sxs-lookup"><span data-stu-id="d9266-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="d9266-451">為了查看和使用本文所述的報表，您必須是 Microsoft 365 Defender 入口網站中下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="d9266-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="d9266-452">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="d9266-452">**Organization Management**</span></span>
- <span data-ttu-id="d9266-453">**安全性系統管理員**</span><span class="sxs-lookup"><span data-stu-id="d9266-453">**Security Administrator**</span></span>
- <span data-ttu-id="d9266-454">**安全性讀取者**</span><span class="sxs-lookup"><span data-stu-id="d9266-454">**Security Reader**</span></span>
- <span data-ttu-id="d9266-455">**全域讀取器**</span><span class="sxs-lookup"><span data-stu-id="d9266-455">**Global Reader**</span></span>

<span data-ttu-id="d9266-456">如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-456">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="d9266-457">**附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="d9266-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d9266-458">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-458">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="d9266-459">如果報告未顯示資料，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="d9266-459">What if the reports aren't showing data?</span></span>

<span data-ttu-id="d9266-460">如果您未看到報表中的資料，請仔細檢查您的原則設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="d9266-460">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="d9266-461">若要深入瞭解，請參閱 [防禦威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="d9266-461">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9266-462">相關主題</span><span class="sxs-lookup"><span data-stu-id="d9266-462">Related topics</span></span>

[<span data-ttu-id="d9266-463">EOP 中的反垃圾郵件和反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="d9266-463">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="d9266-464">Microsoft 365 Defender 入口網站中的智慧報告和洞察力</span><span class="sxs-lookup"><span data-stu-id="d9266-464">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="d9266-465">在 Microsoft 365 Defender 入口網站中查看郵件流程報告</span><span class="sxs-lookup"><span data-stu-id="d9266-465">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="d9266-466">View Office 365 的 Defender 報告</span><span class="sxs-lookup"><span data-stu-id="d9266-466">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
