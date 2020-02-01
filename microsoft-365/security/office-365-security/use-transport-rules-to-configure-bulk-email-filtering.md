---
title: 使用郵件流程規則來設定 Exchange Online Protection 中篩選大量電子郵件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 系統管理員可以了解如何使用 Exchange Online Protection 中的郵件流程規則的大量電子郵件篩選。
ms.openlocfilehash: 5188ce077ce15ab7ad5d03e4aa2c172db6a80c37
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598040"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="c1b20-103">使用郵件流程規則來設定 Exchange Online Protection 中篩選大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="c1b20-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="c1b20-104">您可以設定全公司內容篩選的垃圾郵件和大量電子郵件使用的預設垃圾郵件內容篩選器原則。</span><span class="sxs-lookup"><span data-stu-id="c1b20-104">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies.</span></span> <span data-ttu-id="c1b20-105">請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)and [Set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)有關如何設定內容篩選原則。</span><span class="sxs-lookup"><span data-stu-id="c1b20-105">Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) on how to set the content filter policies.</span></span>

<span data-ttu-id="c1b20-106">如果您想要更多選項] 來篩選大量郵件，您可以建立要搜尋的文字模式或經常大量電子郵件中找到的片語的郵件流程規則 （也稱為傳輸規則）。</span><span class="sxs-lookup"><span data-stu-id="c1b20-106">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails.</span></span> <span data-ttu-id="c1b20-107">任何包含這些特性的郵件會被標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="c1b20-107">Any message containing these characteristics will be marked as spam.</span></span> <span data-ttu-id="c1b20-108">使用這些規則有助於減少貴組織接收到的不想要的大量電子郵件數量。</span><span class="sxs-lookup"><span data-stu-id="c1b20-108">Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1b20-109">建立郵件流程規則記載本主題之前，建議您先閱讀[垃圾郵件和大量電子郵件之間的差異為何？](what-s-the-difference-between-junk-email-and-bulk-email.md)和[大量抱怨層級的值](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b20-109">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span><br>
> <span data-ttu-id="c1b20-110">下列程序會針對您整個組織將郵件標記為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="c1b20-110">The following procedures mark a message as spam for your entire organization.</span></span> <span data-ttu-id="c1b20-111">不過，您可以新增另一項條件，只將這些規則套用至貴組織中的特定收件者。</span><span class="sxs-lookup"><span data-stu-id="c1b20-111">However, you can add another condition to apply these rules only to specific recipients in your organization.</span></span> <span data-ttu-id="c1b20-112">如此一來，積極的大量電子郵件篩選設定可以套用至高目標的幾個使用者在您的使用者 （大部分取得他們註冊的帶正負號的大量電子郵件） 的其餘部分時不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="c1b20-112">This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="c1b20-113">建立郵件流程規則，以篩選大量電子郵件根據文字模式</span><span class="sxs-lookup"><span data-stu-id="c1b20-113">Create a mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="c1b20-114">在 Exchange 系統管理中心 (EAC) 中，移至 **[郵件流程]** \> **[規則]**。</span><span class="sxs-lookup"><span data-stu-id="c1b20-114">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="c1b20-115">按一下 [**新增**![加入圖示](../media/ITPro-EAC-AddIcon.gif)]，然後選取 [**建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="c1b20-115">Click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="c1b20-116">指定規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="c1b20-116">Specify a name for the rule.</span></span>

4. <span data-ttu-id="c1b20-117">按一下 [**更多選項**![更多選項圖示](../media/ITPro-EAC-MoreOptionsIcon.png)。</span><span class="sxs-lookup"><span data-stu-id="c1b20-117">Click **More options** ![More options icon](../media/ITPro-EAC-MoreOptionsIcon.png).</span></span> <span data-ttu-id="c1b20-118">在**套用此規則情況**] 下選取 [**主旨或本文** \> **主旨或內文符合這些文字模式**。</span><span class="sxs-lookup"><span data-stu-id="c1b20-118">Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>

5. <span data-ttu-id="c1b20-119">在 [**指定單字或片語**] 對話方塊中，新增下列規則運算式通常位於大量電子郵件，一次，然後完成後，按一下 [**確定]** :</span><span class="sxs-lookup"><span data-stu-id="c1b20-119">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **OK** when you're done:</span></span>

   - `If you are unable to view the content of this email\, please`

   - `\>(safe )?unsubscribe( here)?\</a\>`

   - `If you do not wish to receive further communications like this\, please`

   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

   - `To stop receiving these+emails\:http\://`

   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

   - `no longer (wish )?(to )?(be sent|receive) w+ email`

   - `If you are unable to view the content of this email\, please click here`

   - `To ensure you receive (your daily deals|our e-?mails)\, add`

   - `If you no longer wish to receive these emails`

   - `to change your (subscription preferences|preferences or unsubscribe)`

   - `click (here to|the) unsubscribe`

   <span data-ttu-id="c1b20-120">上面的清單並未常見於大量電子郵件; 中的規則運算式可以新增或移除視需要更多。</span><span class="sxs-lookup"><span data-stu-id="c1b20-120">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="c1b20-121">不過，它是不錯的起點。</span><span class="sxs-lookup"><span data-stu-id="c1b20-121">However, it's a good starting point.</span></span>

   <span data-ttu-id="c1b20-p106">在主旨或郵件的其他標頭欄位中搜尋字詞或文字模式，會發生在郵件已從 MIME 內容傳輸編碼方法進行解碼*之後*，該編碼方法用來在 SMTP 伺服器之間傳送 ASCII 文字二進位訊息。您無法使用條件或例外狀況來搜尋主旨或郵件中其他標頭欄位的原始 (通常是 Base64) 編碼值。</span><span class="sxs-lookup"><span data-stu-id="c1b20-p106">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

6. <span data-ttu-id="c1b20-124">在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。</span><span class="sxs-lookup"><span data-stu-id="c1b20-124">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>

7. <span data-ttu-id="c1b20-125">在 **[指定 SCL]** 對話方塊中，將 SCL 設定為 **5**、**6** 或 **9**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c1b20-125">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>

   <span data-ttu-id="c1b20-126">將 SCL 設為 5 或 6 會採取 **[垃圾郵件]** 動作，將 SCL 設為 9 會採取 **[高信賴度的垃圾郵件]** 動作 (在內容篩選原則中設定)。</span><span class="sxs-lookup"><span data-stu-id="c1b20-126">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy.</span></span> <span data-ttu-id="c1b20-127">服務將執行內容篩選原則中所設定的動作。</span><span class="sxs-lookup"><span data-stu-id="c1b20-127">The service will perform the action set in the content filter policy.</span></span> <span data-ttu-id="c1b20-128">預設動作是要將郵件傳遞至收件者的垃圾郵件] 資料夾，但是可以設定不同的動作，如所述[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b20-128">The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

   <span data-ttu-id="c1b20-129">如果您設定的動作是要隔離郵件，而不是將它傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息至管理員隔離區為郵件流程規則比對，且已將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="c1b20-129">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span>

   <span data-ttu-id="c1b20-130">如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b20-130">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="c1b20-131">儲存規則。</span><span class="sxs-lookup"><span data-stu-id="c1b20-131">Save the rule.</span></span>

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="c1b20-132">建立郵件流程規則，以篩選器片語為基礎的大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="c1b20-132">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="c1b20-133">在 EAC 中，移至 [郵件流程]\*\*\*\* \> [規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c1b20-133">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="c1b20-134">按一下 [**新增**![加入圖示](../media/ITPro-EAC-AddIcon.gif)]，然後選取 [**建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="c1b20-134">Click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="c1b20-135">指定規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="c1b20-135">Specify a name for the rule.</span></span>

4. <span data-ttu-id="c1b20-136">按一下 [更多選項]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c1b20-136">Click **More options**.</span></span> <span data-ttu-id="c1b20-137">在**套用此規則情況**] 下選取 [**主旨或本文** \> **主旨或內文包含任何這些字詞**。</span><span class="sxs-lookup"><span data-stu-id="c1b20-137">Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>

5. <span data-ttu-id="c1b20-138">在 [**指定單字或片語**] 對話方塊中，新增下列常見於大量電子郵件，一次中然後當您完成時按一下 [**確定]** :</span><span class="sxs-lookup"><span data-stu-id="c1b20-138">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span>

   - `to change your preferences or unsubscribe`

   - `Modify email preferences or unsubscribe`

   - `This is a promotional email`

   - `You are receiving this email because you requested a subscription`

   - `click here to unsubscribe`

   - `You have received this email because you are subscribed`

   - `If you no longer wish to receive our email newsletter`

   - `to unsubscribe from this newsletter`

   - `If you have trouble viewing this email`

   - `This is an advertisement`

   - `you would like to unsubscribe or change your`

   - `view this email as a webpage`

   - `You are receiving this email because you are subscribed`

   <span data-ttu-id="c1b20-139">這份清單並非常見於大量電子郵件; 中的片語可以新增或移除視需要更多。</span><span class="sxs-lookup"><span data-stu-id="c1b20-139">This list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="c1b20-140">不過，它是不錯的起點。</span><span class="sxs-lookup"><span data-stu-id="c1b20-140">However, it's a good starting point.</span></span>

6. <span data-ttu-id="c1b20-141">在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。</span><span class="sxs-lookup"><span data-stu-id="c1b20-141">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>

7. <span data-ttu-id="c1b20-142">在 **[指定 SCL]** 對話方塊中，將 SCL 設定為 **5**、**6** 或 **9**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c1b20-142">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>

   <span data-ttu-id="c1b20-143">將 SCL 設為 5 或 6 會採取 **[垃圾郵件]** 動作，將 SCL 設為 9 會採取 **[高信賴度的垃圾郵件]** 動作 (在內容篩選原則中設定)。</span><span class="sxs-lookup"><span data-stu-id="c1b20-143">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy.</span></span> <span data-ttu-id="c1b20-144">服務將執行內容篩選原則中所設定的動作。</span><span class="sxs-lookup"><span data-stu-id="c1b20-144">The service will perform the action set in the content filter policy.</span></span> <span data-ttu-id="c1b20-145">預設動作是要將郵件傳遞至收件者的垃圾郵件] 資料夾，但是可以設定不同的動作，如所述[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b20-145">The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

   <span data-ttu-id="c1b20-146">如果您設定的動作是要隔離郵件，而不是將它傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息至管理員隔離區為郵件流程規則比對，且已將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="c1b20-146">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span>

   <span data-ttu-id="c1b20-147">如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b20-147">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="c1b20-148">儲存規則。</span><span class="sxs-lookup"><span data-stu-id="c1b20-148">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="c1b20-149">相關資訊</span><span class="sxs-lookup"><span data-stu-id="c1b20-149">For more information</span></span>

[<span data-ttu-id="c1b20-150">垃圾郵件和大量電子郵件有什麼不同？</span><span class="sxs-lookup"><span data-stu-id="c1b20-150">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="c1b20-151">大量相容層級值</span><span class="sxs-lookup"><span data-stu-id="c1b20-151">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="c1b20-152">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="c1b20-152">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="c1b20-153">進階垃圾郵件篩選選項</span><span class="sxs-lookup"><span data-stu-id="c1b20-153">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
