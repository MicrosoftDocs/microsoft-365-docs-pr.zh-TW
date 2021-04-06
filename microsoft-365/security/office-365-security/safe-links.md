---
title: 安全連結
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 在本文中，系統管理員可以深入瞭解 Office 365 的安全連結保護，以保護其組織免受使用惡意 URLs 的網路釣魚和其他攻擊。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 06ec3ab1a255e9eaa8c190ed5c248c9587273e03
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204688"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="af416-103">Microsoft Defender for Office 365 中的安全連結</span><span class="sxs-lookup"><span data-stu-id="af416-103">Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="af416-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="af416-104">**Applies to**</span></span>
- [<span data-ttu-id="af416-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="af416-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="af416-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af416-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="af416-107">本文適用於擁有[適用於 Office 365 的 Microsoft Defender](defender-for-office-365.md) 的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="af416-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="af416-108">如果您使用的是 Outlook.com、Microsoft 365 系列或 Microsoft 365 個人版，且您在 Outlook 中尋找 Safelinks 的相關資訊，請參閱 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="af416-108">If you're using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="af416-109">安全連結是 [Office 365 的 Defender](defender-for-office-365.md) 中的一項功能，可提供郵件流程中的輸入電子郵件訊息的 URL 掃描和修正，以及電子郵件及其他位置中 URLs 和連結的時間驗證。</span><span class="sxs-lookup"><span data-stu-id="af416-109">Safe Links is a feature in [Defender for Office 365](defender-for-office-365.md) that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.</span></span> <span data-ttu-id="af416-110">在 Exchange Online Protection (EOP) 中，除了內送電子郵件訊息中的一般 [反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md) 之外，也會進行安全連結掃描。</span><span class="sxs-lookup"><span data-stu-id="af416-110">Safe Links scanning occurs in addition to the regular [anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md) in inbound email messages in Exchange Online Protection (EOP).</span></span> <span data-ttu-id="af416-111">安全連結掃描可協助保護您的組織免受網路釣魚和其他攻擊中所用的惡意連結。</span><span class="sxs-lookup"><span data-stu-id="af416-111">Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.</span></span>

<span data-ttu-id="af416-112">在下列位置可取得安全連結保護：</span><span class="sxs-lookup"><span data-stu-id="af416-112">Safe Links protection is available in the following locations:</span></span>

- <span data-ttu-id="af416-113">**電子郵件訊息**：安全連結保護電子郵件訊息中的連結是由安全連結原則所控制。</span><span class="sxs-lookup"><span data-stu-id="af416-113">**Email messages**: Safe Links protection for links in email messages is controlled by Safe Links policies.</span></span> <span data-ttu-id="af416-114">沒有預設的安全連結原則， **因此若要在電子郵件中取得安全連結的保護，您必須建立一或多個安全連結原則**。</span><span class="sxs-lookup"><span data-stu-id="af416-114">There is no default Safe Links policy, **so to get the protection of Safe Links in email messages, you need to create one or more Safe Links policies**.</span></span> <span data-ttu-id="af416-115">如需相關指示，請參閱 [設定 Microsoft Defender For Office 365 中的安全連結原則](set-up-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="af416-115">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

  <span data-ttu-id="af416-116">如需電子郵件安全連結保護的詳細資訊，請參閱本文稍後的 [ [電子郵件的安全連結設定](#safe-links-settings-for-email-messages) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="af416-116">For more information about Safe Links protection for email messages, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>

- <span data-ttu-id="af416-117">**Microsoft 團隊** (目前在點擊預覽) ：對小組交談、群組聊天或管道中的連結的安全連結保護也是由安全連結原則所控制。</span><span class="sxs-lookup"><span data-stu-id="af416-117">**Microsoft Teams** (currently in TAP Preview): Safe Links protection for links in Teams conversations, group chats, or from channels is also controlled by Safe Links policies.</span></span> <span data-ttu-id="af416-118">沒有預設的安全連結原則， **因此若要在小組中取得安全連結的保護，您必須建立一或多個安全連結原則**。</span><span class="sxs-lookup"><span data-stu-id="af416-118">There is no default Safe Links policy, **so to get the protection of Safe Links in Teams, you need to create one or more Safe Links policies**.</span></span>

  <span data-ttu-id="af416-119">如需小組中安全連結保護的詳細資訊，請參閱本文稍後的 [ [Microsoft 小組的安全連結設定](#safe-links-settings-for-microsoft-teams) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="af416-119">For more information about Safe Links protection in Teams, see the [Safe Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) section later in this article.</span></span>

- <span data-ttu-id="af416-120">**Office 365 應用程式**： office 365 應用程式的安全連結保護可在支援的桌面、行動裝置和網路 ap 中取得。</span><span class="sxs-lookup"><span data-stu-id="af416-120">**Office 365 apps**: Safe Links protection for Office 365 apps is available in supported desktop, mobile, and web aps.</span></span> <span data-ttu-id="af416-121">您可以在安全連結原則 **以外** 的全域設定中，**設定** Office 365 應用程式的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="af416-121">You **configure** Safe Links protection for Office 365 apps in the global setting that are **outside** of Safe Links policies.</span></span> <span data-ttu-id="af416-122">如需相關指示，請參閱 [在 Microsoft Defender For Office 365 中設定安全連結設定的全域設定](configure-global-settings-for-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="af416-122">For instructions, see [Configure global settings for Safe Links settings in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

  <span data-ttu-id="af416-123">不過，Office 365 應用程式的安全連結保護只 **適用** 于包含在使用中安全連結原則中的使用者。</span><span class="sxs-lookup"><span data-stu-id="af416-123">But, Safe Links protection for Office 365 apps is only **applied** to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="af416-124">如果使用者未包含在使用中的安全連結原則中，使用者就不會在支援的 Office 365 應用程式中取得安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="af416-124">If a user isn't included in an active Safe Links policy, the user doesn't get Safe Links protection in supported Office 365 apps.</span></span>

  <span data-ttu-id="af416-125">如需 Office 365 應用程式中安全連結保護的詳細資訊，請參閱本文稍後的 [office 365 應用程式的安全連結設定](#safe-links-settings-for-office-365-apps) 一節。</span><span class="sxs-lookup"><span data-stu-id="af416-125">For more information about Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>

<span data-ttu-id="af416-126">本文包含下列安全連結設定類型的詳細描述：</span><span class="sxs-lookup"><span data-stu-id="af416-126">This article includes detailed descriptions of the following types of Safe Links settings:</span></span>

- <span data-ttu-id="af416-127">**安全連結原則中的設定**：這些設定僅適用于包含在特定原則中的使用者，而且各原則的設定可能不同。</span><span class="sxs-lookup"><span data-stu-id="af416-127">**Settings in Safe Links policies**: These settings apply only to the users who are included in the specific policies, and the settings might be different between policies.</span></span> <span data-ttu-id="af416-128">這些設定包括：</span><span class="sxs-lookup"><span data-stu-id="af416-128">These settings include:</span></span>

  - [<span data-ttu-id="af416-129">電子郵件訊息的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="af416-129">Safe Links settings for email messages</span></span>](#safe-links-settings-for-email-messages)
  - [<span data-ttu-id="af416-130">Microsoft 小組的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="af416-130">Safe Links settings for Microsoft Teams</span></span>](#safe-links-settings-for-microsoft-teams)
  - [<span data-ttu-id="af416-131">安全連結原則中的「不要重新寫入下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="af416-131">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- <span data-ttu-id="af416-132">**全域安全連結設定**：這些設定會全域設定，而不是在安全連結原則中。</span><span class="sxs-lookup"><span data-stu-id="af416-132">**Global Safe Links settings**: These settings are configured globally, not in Safe Links policies.</span></span> <span data-ttu-id="af416-133">不過，這些設定僅適用于包含在使用中安全連結原則中的使用者。</span><span class="sxs-lookup"><span data-stu-id="af416-133">But, the settings apply only to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="af416-134">這些設定包括：</span><span class="sxs-lookup"><span data-stu-id="af416-134">These settings include:</span></span>

  - [<span data-ttu-id="af416-135">Office 365 應用程式的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="af416-135">Safe Links settings for Office 365 apps</span></span>](#safe-links-settings-for-office-365-apps)
  - [<span data-ttu-id="af416-136">安全連結的「封鎖下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="af416-136">"Block the following URLs" list for Safe Links</span></span>](#block-the-following-urls-list-for-safe-links)

<span data-ttu-id="af416-137">下表說明 Microsoft 365 和 Office 365 組織中包含 Office 365 的 Defender 的安全連結案例 (換句話說，缺乏授權是) 範例中的問題。</span><span class="sxs-lookup"><span data-stu-id="af416-137">The following table describes scenarios for Safe Links in Microsoft 365 and Office 365 organizations that include Defender for Office 365 (in other words, lack of licensing is never an issue in the examples).</span></span>

****

|<span data-ttu-id="af416-138">案例</span><span class="sxs-lookup"><span data-stu-id="af416-138">Scenario</span></span>|<span data-ttu-id="af416-139">結果</span><span class="sxs-lookup"><span data-stu-id="af416-139">Result</span></span>|
|---|---|
|<span data-ttu-id="af416-140">Jean-francois 是行銷部門的成員。</span><span class="sxs-lookup"><span data-stu-id="af416-140">Jean is a member of the marketing department.</span></span> <span data-ttu-id="af416-141">在安全連結的通用設定中開啟 Office 365 應用程式的安全連結保護，以及適用于行銷部門成員的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="af416-141">Safe Links protection for Office 365 apps is turned on in the global settings for Safe Links, and a Safe Links policy that applies to members of the marketing department exists.</span></span> <span data-ttu-id="af416-142">Jean-francois 會在電子郵件訊息中開啟 PowerPoint 簡報，然後按一下簡報中的 URL。</span><span class="sxs-lookup"><span data-stu-id="af416-142">Jean opens a PowerPoint presentation in an email message, and then clicks a URL in the presentation.</span></span>|<span data-ttu-id="af416-143">Jean-francois 受到安全連結的保護。</span><span class="sxs-lookup"><span data-stu-id="af416-143">Jean is protected by Safe Links.</span></span> <p> <span data-ttu-id="af416-144">Jean-francois 包含在安全連結原則中，且已開啟 Office 365 應用程式的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="af416-144">Jean is included in a Safe Links policy, and Safe Links protection for Office 365 apps is turned on.</span></span> <p> <span data-ttu-id="af416-145">如需 Office 365 應用程式中安全連結保護需求的詳細資訊，請參閱本文稍後的「 [Office 365 應用程式的安全連結設定](#safe-links-settings-for-office-365-apps) 」一節。</span><span class="sxs-lookup"><span data-stu-id="af416-145">For more information about the requirements for Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>|
|<span data-ttu-id="af416-146">Chris 的 Microsoft 365 E5 組織未設定安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="af416-146">Chris's Microsoft 365 E5 organization has no Safe Links policies configured.</span></span> <span data-ttu-id="af416-147">Chris 會接收來自外部寄件者的電子郵件，該寄件者包含的 URL 指向他最後按一下的惡意網站。</span><span class="sxs-lookup"><span data-stu-id="af416-147">Chris receives an email from an external sender that contains a URL to a malicious website that he ultimately clicks.</span></span>|<span data-ttu-id="af416-148">Chris 未受到安全連結的保護。</span><span class="sxs-lookup"><span data-stu-id="af416-148">Chris is not protected by Safe Links.</span></span> <p> <span data-ttu-id="af416-149">管理員至少必須建立一個安全連結原則，以供任何人取得輸入電子郵件訊息中的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="af416-149">An admin must create at least one Safe Links policy for anyone to get Safe Links protection in inbound email messages.</span></span> <span data-ttu-id="af416-150">在原則的條件中必須包含 Chris，才可取得安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="af416-150">Chris must be included in the conditions of policy to get Safe Links protection.</span></span>|
|<span data-ttu-id="af416-151">在 Pat 的組織中，沒有系統管理員已建立任何安全連結原則，但已開啟 Office 365 應用程式的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="af416-151">In Pat's organization, no admins have created any Safe Links policies, but Safe Links protection for Office 365 apps is turned on.</span></span> <span data-ttu-id="af416-152">Pat 開啟 Word 檔，然後按一下檔案中的 URL。</span><span class="sxs-lookup"><span data-stu-id="af416-152">Pat opens a Word document and clicks a URL in the file.</span></span>|<span data-ttu-id="af416-153">Pat 未受到安全連結的保護。</span><span class="sxs-lookup"><span data-stu-id="af416-153">Pat is not protected by Safe Links.</span></span> <p> <span data-ttu-id="af416-154">雖然以全域方式開啟 Office 365 應用程式的安全連結保護，但 Pat 並未包含在任何使用中的安全連結原則中，因此無法套用保護。</span><span class="sxs-lookup"><span data-stu-id="af416-154">Although Safe Links protection for Office 365 apps is turned on globally, Pat is not included in any active Safe Links policies, so the protection can't be applied.</span></span>|
|<span data-ttu-id="af416-155">在「企業版的組織」中，于 [ `https://tailspintoys.com` 安全連結的全域設定] 中的 [ **封鎖下列 URLs** ] 清單中設定。</span><span class="sxs-lookup"><span data-stu-id="af416-155">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span></span> <span data-ttu-id="af416-156">包含「擁有先生」的安全連結原則已存在。</span><span class="sxs-lookup"><span data-stu-id="af416-156">A Safe Links policy that includes Lee already exists.</span></span> <span data-ttu-id="af416-157">「電子郵件」會收到包含 URL 的電子郵件 `https://tailspintoys.com/aboutus/trythispage` 。</span><span class="sxs-lookup"><span data-stu-id="af416-157">Lee receives an email message that contains the URL `https://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="af416-158">Lee 按下該 URL。</span><span class="sxs-lookup"><span data-stu-id="af416-158">Lee clicks the URL.</span></span>|<span data-ttu-id="af416-159">您可以自動封鎖此 URL。這取決於清單中的 URL 專案和使用的電子郵件用戶端。</span><span class="sxs-lookup"><span data-stu-id="af416-159">The URL might be automatically blocked for Lee; it depends on the URL entry in the list and the email client Lee used.</span></span> <span data-ttu-id="af416-160">如需詳細資訊，請參閱本文稍後的「 [阻止下列 URLs 的安全連結」清單](#block-the-following-urls-list-for-safe-links) 一節。</span><span class="sxs-lookup"><span data-stu-id="af416-160">For more information, see the ["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links) section later in this article.</span></span>|
|<span data-ttu-id="af416-161">曉明和 Julia 這兩個 contoso.com 的工作。</span><span class="sxs-lookup"><span data-stu-id="af416-161">Jamie and Julia both work for contoso.com.</span></span> <span data-ttu-id="af416-162">很久之前，系統管理員設定了同時適用于曉明和 Julia 的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="af416-162">A long time ago, admins configured Safe Links policies that apply to both of Jamie and Julia.</span></span> <span data-ttu-id="af416-163">曉明會將電子郵件傳送至 Julia，而不知道電子郵件中包含惡意 URL。</span><span class="sxs-lookup"><span data-stu-id="af416-163">Jamie sends an email to Julia, not knowing that the email contains a malicious URL.</span></span>|<span data-ttu-id="af416-164">**如果** 套用至她的安全連結原則設定為套用至內部收件者之間的郵件，則安全連結會保護 Julia。</span><span class="sxs-lookup"><span data-stu-id="af416-164">Julia is protected by Safe Links **if** the Safe Links policy that applies to her is configured to apply to messages between internal recipients.</span></span> <span data-ttu-id="af416-165">如需詳細資訊，請參閱本文稍後的「 [電子郵件的安全連結設定](#safe-links-settings-for-email-messages) 」一節。</span><span class="sxs-lookup"><span data-stu-id="af416-165">For more information, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>|

## <a name="safe-links-settings-for-email-messages"></a><span data-ttu-id="af416-166">電子郵件訊息的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="af416-166">Safe Links settings for email messages</span></span>

<span data-ttu-id="af416-167">安全連結會掃描內送電子郵件中的已知惡意超連結。</span><span class="sxs-lookup"><span data-stu-id="af416-167">Safe Links scans incoming email for known malicious hyperlinks.</span></span> <span data-ttu-id="af416-168">掃描的 URLs 會使用 Microsoft standard URL 前置詞來重新寫入： `https://nam01.safelinks.protection.outlook.com` 。</span><span class="sxs-lookup"><span data-stu-id="af416-168">Scanned URLs are rewritten using the Microsoft standard URL prefix: `https://nam01.safelinks.protection.outlook.com`.</span></span> <span data-ttu-id="af416-169">在重新寫入連結之後，它會針對潛在的惡意內容進行分析。</span><span class="sxs-lookup"><span data-stu-id="af416-169">After the link is rewritten, it's analyzed for potentially malicious content.</span></span>

<span data-ttu-id="af416-170">安全連結會重新寫入 URL 後，即使郵件是 *手動* 轉寄或回復 (給內部及外部收件者) ，該 url 仍會保持重新寫入狀態。</span><span class="sxs-lookup"><span data-stu-id="af416-170">After Safe Links rewrites a URL, the URL remains rewritten even if the message is *manually* forwarded or replied to (both to internal and external recipients).</span></span> <span data-ttu-id="af416-171">新增至轉寄或回復郵件的其他連結不會被重新寫入。</span><span class="sxs-lookup"><span data-stu-id="af416-171">Additional links that are added to the forwarded or replied to message are not rewritten.</span></span> <span data-ttu-id="af416-172">不過，如果是透過收件匣規則或 SMTP 轉寄進行 *自動* 轉寄，將不會在預期的收件者的郵件中重新寫入此 url， *除非* 該收件者也是由安全連結所保護，或是 URL 已在先前的通訊中重新寫入。</span><span class="sxs-lookup"><span data-stu-id="af416-172">However, in the case of *automatic* forwarding by Inbox rules or SMTP forwarding, the URL will not be rewritten in the message that's intended for the final recipient *unless* that recipient is also protected by Safe Links or the URL had already been rewritten in a previous communication.</span></span> 

<span data-ttu-id="af416-173">下列清單說明適用于電子郵件訊息的安全連結原則中的設定：</span><span class="sxs-lookup"><span data-stu-id="af416-173">The settings in Safe Links policies that apply to email messages are described in the following list:</span></span>

- <span data-ttu-id="af416-174">**選取郵件中不明的潛在惡意 URLs 動作**：啟用或停用電子郵件中的安全連結掃描。</span><span class="sxs-lookup"><span data-stu-id="af416-174">**Select the action for unknown potentially malicious URLs in messages**: Enables or disables Safe Links scanning in email messages.</span></span> <span data-ttu-id="af416-175">建議值為 **On**。</span><span class="sxs-lookup"><span data-stu-id="af416-175">The recommended value is **On**.</span></span> <span data-ttu-id="af416-176">開啟此設定會產生下列動作。</span><span class="sxs-lookup"><span data-stu-id="af416-176">Turning on this setting results in the following actions.</span></span>

  - <span data-ttu-id="af416-177">在 Windows (C2R) 的 Outlook 中啟用安全連結掃描。</span><span class="sxs-lookup"><span data-stu-id="af416-177">Safe Links scanning is enabled in Outlook (C2R) on Windows.</span></span>
  - <span data-ttu-id="af416-178">URLs 會在郵件中按一下 [URLs] 中的 [安全連結保護]，以重新寫入。</span><span class="sxs-lookup"><span data-stu-id="af416-178">URLs are rewritten and users are routed through Safe Links protection when they click URLs in messages.</span></span>
  - <span data-ttu-id="af416-179">按一下時，會針對已知的惡意 URLs 清單及「 [封鎖下列 URLs」清單](#block-the-following-urls-list-for-safe-links)，檢查 URLs。</span><span class="sxs-lookup"><span data-stu-id="af416-179">When clicked, URLs are checked against a list of known malicious URLs and the ["Block the following URLs" list](#block-the-following-urls-list-for-safe-links).</span></span>
  - <span data-ttu-id="af416-180">不具備有效信譽的 URLs 會在背景中以非同步方式引爆。</span><span class="sxs-lookup"><span data-stu-id="af416-180">URLs that don't have a valid reputation are detonated asynchronously in the background.</span></span>

- <span data-ttu-id="af416-181">**對指向檔案的可疑連結和連結套用即時 URL 掃描**：可即時掃描連結，包含指向可下載內容的電子郵件訊息中的連結。</span><span class="sxs-lookup"><span data-stu-id="af416-181">**Apply real-time URL scanning for suspicious links and links that point to files**: Enables real-time scanning of links, including links in email messages that point to downloadable content.</span></span> <span data-ttu-id="af416-182">建議的值為 enabled。</span><span class="sxs-lookup"><span data-stu-id="af416-182">The recommended value is enabled.</span></span>

  - <span data-ttu-id="af416-183">**等候 URL 掃描完成之後，才會傳遞郵件**：</span><span class="sxs-lookup"><span data-stu-id="af416-183">**Wait for URL scanning to complete before delivering the message**:</span></span>

    - <span data-ttu-id="af416-184">已啟用：包含 URLs 的郵件會一直保留，直到完成掃描為止。</span><span class="sxs-lookup"><span data-stu-id="af416-184">Enabled: Messages that contain URLs are held until scanning is finished.</span></span> <span data-ttu-id="af416-185">只有在 URLs 確認為安全後，才會傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="af416-185">Messages are delivered only after the URLs are confirmed to be safe.</span></span> <span data-ttu-id="af416-186">此為建議值。</span><span class="sxs-lookup"><span data-stu-id="af416-186">This is the recommended value.</span></span>
    - <span data-ttu-id="af416-187">Disabled：如果無法完成 URL 掃描，請傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="af416-187">Disabled: If URL scanning can't complete, deliver the message anyway.</span></span>

- <span data-ttu-id="af416-188">對 **組織內傳送的電子郵件套用安全連結**：啟用或停用安全連結掃描在相同 Exchange Online 組織內的內部寄件者和內部收件者之間傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="af416-188">**Apply Safe Links to email messages sent within the organization**: Enables or disables Safe Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span></span> <span data-ttu-id="af416-189">建議的值為 enabled。</span><span class="sxs-lookup"><span data-stu-id="af416-189">The recommended value is enabled.</span></span>

- <span data-ttu-id="af416-190">**請勿追蹤使用者點擊**：啟用或停用儲存安全連結按一下 [電子郵件訊息] 中的 [URLs 的資料]。</span><span class="sxs-lookup"><span data-stu-id="af416-190">**Do not track user clicks**: Enables or disables storing Safe Links click data for URLs clicked in email messages.</span></span> <span data-ttu-id="af416-191">建議值為將此設定保留未選取狀態 (以追蹤使用者點擊) 。</span><span class="sxs-lookup"><span data-stu-id="af416-191">The recommend value is to leave this setting unselected (to track user clicks).</span></span>

  <span data-ttu-id="af416-192">URL 按一下 [追蹤] 以取得內部寄件者和內部收件者之間所傳送的電子郵件中的連結目前不支援。</span><span class="sxs-lookup"><span data-stu-id="af416-192">URL click tracking for links in email messages sent between internal senders and internal recipients is currently not supported.</span></span>

- <span data-ttu-id="af416-193">**不允許使用者依序按一下原始 url**：允許或封鎖使用者按一下 [ [警告] 頁面](#warning-pages-from-safe-links) 至原始 url。</span><span class="sxs-lookup"><span data-stu-id="af416-193">**Do not allow users to click through to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL.</span></span> <span data-ttu-id="af416-194">建議值已啟用。</span><span class="sxs-lookup"><span data-stu-id="af416-194">The recommend value is enabled.</span></span>

- <span data-ttu-id="af416-195">**在通知和警告頁面上顯示組織商標**：此選項會在警告頁面上顯示組織的署名。</span><span class="sxs-lookup"><span data-stu-id="af416-195">**Display the organization branding on notification and warning pages**: This option shows your organization's branding on warning pages.</span></span> <span data-ttu-id="af416-196">署名可協助使用者識別合法的警告，因為攻擊者經常會使用預設的 Microsoft 警告頁面。</span><span class="sxs-lookup"><span data-stu-id="af416-196">Branding helps users identify legitimate warnings, because default Microsoft warning pages are often used by attackers.</span></span> <span data-ttu-id="af416-197">如需自訂商標的詳細資訊，請參閱 [將品牌新增至您組織的 Azure Active Directory 登入頁面](/azure/active-directory/fundamentals/customize-branding)。</span><span class="sxs-lookup"><span data-stu-id="af416-197">For more information about customized branding, see [Add branding to your organization's Azure Active Directory sign-in page](/azure/active-directory/fundamentals/customize-branding).</span></span>

- <span data-ttu-id="af416-198">**請勿重新寫入下列 URLs**：保留 URLs。</span><span class="sxs-lookup"><span data-stu-id="af416-198">**Do not rewrite the following URLs**: Leaves URLs as they are.</span></span> <span data-ttu-id="af416-199">保留不需要掃描之安全 URLs 的自訂清單。</span><span class="sxs-lookup"><span data-stu-id="af416-199">Keeps a custom list of safe URLs that don't need scanning.</span></span> <span data-ttu-id="af416-200">每個安全連結原則的清單都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="af416-200">The list is unique for each Safe Links policy.</span></span> <span data-ttu-id="af416-201">如需 [不要重新 **寫入下列 URLs** ] 清單的詳細資訊，請參閱本文稍後的「 [安全連結原則中的「不要重新寫入下列 URLs」清單](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 」一節。</span><span class="sxs-lookup"><span data-stu-id="af416-201">For more information about the **Do not rewrite the following URLs** list, see the ["Do not rewrite the following URLs" lists in Safe Links policies](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="af416-202">如需安全連結原則之標準和嚴格原則設定的建議值的詳細資訊，請參閱 [安全連結原則設定](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="af416-202">For more information about the recommended values for Standard and Strict policy settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="af416-203">**收件者篩選器**：您必須指定收件者條件和例外狀況，以決定要套用的原則。</span><span class="sxs-lookup"><span data-stu-id="af416-203">**Recipient filters**: You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="af416-204">您可以使用這些屬性做為條件和例外狀況：</span><span class="sxs-lookup"><span data-stu-id="af416-204">You can use these properties for conditions and exceptions:</span></span>

  - <span data-ttu-id="af416-205">**收件者是**</span><span class="sxs-lookup"><span data-stu-id="af416-205">**The recipient is**</span></span>
  - <span data-ttu-id="af416-206">**收件者網域是**</span><span class="sxs-lookup"><span data-stu-id="af416-206">**The recipient domain is**</span></span>
  - <span data-ttu-id="af416-207">**收件者是以下的成員**</span><span class="sxs-lookup"><span data-stu-id="af416-207">**The recipient is a member of**</span></span>

  <span data-ttu-id="af416-208">您只可以使用條件或例外狀況，但條件或例外狀況可以包含多個值。</span><span class="sxs-lookup"><span data-stu-id="af416-208">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="af416-209">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="af416-209">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="af416-210">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="af416-210">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

- <span data-ttu-id="af416-211">**Priority**：如果您建立多個原則，您可以指定要套用的順序。</span><span class="sxs-lookup"><span data-stu-id="af416-211">**Priority**: If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="af416-212">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="af416-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="af416-213">如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="af416-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="how-safe-links-works-in-email-messages"></a><span data-ttu-id="af416-214">安全連結在電子郵件訊息中的運作方式</span><span class="sxs-lookup"><span data-stu-id="af416-214">How Safe Links works in email messages</span></span>

<span data-ttu-id="af416-215">在較高的層次，以下是在電子郵件訊息中 URLs 安全連結保護的運作方式：</span><span class="sxs-lookup"><span data-stu-id="af416-215">At a high level, here's how Safe Links protection works on URLs in email messages:</span></span>

1. <span data-ttu-id="af416-216">所有電子郵件都會透過 EOP，網際網路通訊協定 (IP) 和信封篩選器，簽章型惡意程式碼保護，反垃圾郵件和反惡意程式碼篩選，然後將郵件傳遞至收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="af416-216">All email goes through EOP, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters before the message is delivered to the recipient's mailbox.</span></span>

2. <span data-ttu-id="af416-217">使用者在其信箱中開啟郵件，然後按一下郵件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="af416-217">The user opens the message in their mailbox and clicks on a URL in the message.</span></span>

3. <span data-ttu-id="af416-218">安全連結會在開啟網站之前，立即檢查 URL：</span><span class="sxs-lookup"><span data-stu-id="af416-218">Safe Links immediately checks the URL before opening the website:</span></span>

   - <span data-ttu-id="af416-219">如果此 URL 包含在 [ **封鎖下列 URLs** ] 清單中，則會開啟 [封鎖的 URL 警告](#blocked-url-warning) 。</span><span class="sxs-lookup"><span data-stu-id="af416-219">If the URL is included in the **Block the following URLs** list, a [blocked URL warning](#blocked-url-warning) opens.</span></span>

   - <span data-ttu-id="af416-220">如果 URL 指向已確定為惡意的網站，則會開啟 [惡意的網站警告](#malicious-website-warning) 頁面 (或不同的警告頁面) 。</span><span class="sxs-lookup"><span data-stu-id="af416-220">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="af416-221">如果 URL 指向可供下載的檔案，而且在套用至該使用者的原則中，[套用 **即時 URL 掃描（指向檔** ] 設定已啟用），則會檢查下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="af416-221">If the URL points to a downloadable file, and the **Apply real-time URL scanning for suspicious links and links that point to files** setting is enabled in the policy that applies to the user, the downloadable file is checked.</span></span>

   - <span data-ttu-id="af416-222">如果此 URL 確定為安全，網站會開啟。</span><span class="sxs-lookup"><span data-stu-id="af416-222">If the URL is determined to be safe, the website opens.</span></span>

## <a name="safe-links-settings-for-microsoft-teams"></a><span data-ttu-id="af416-223">Microsoft 小組的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="af416-223">Safe Links settings for Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af416-224">從3月2020，這項功能只是在預覽中，僅供 Microsoft 小組技術採用計畫的成員使用 (點擊) 。</span><span class="sxs-lookup"><span data-stu-id="af416-224">As of March 2020, this feature is in Preview and is available only to members of the Microsoft Teams Technology Adoption Program (TAP).</span></span> <span data-ttu-id="af416-225">如需發行排程的相關資訊，請參閱 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。</span><span class="sxs-lookup"><span data-stu-id="af416-225">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).</span></span>

<span data-ttu-id="af416-226">您可以在安全連結原則中啟用或停用 Microsoft 小組的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="af416-226">You enable or disable Safe Links protection for Microsoft Teams in Safe Links policies.</span></span> <span data-ttu-id="af416-227">具體說來，您可以在 **Microsoft 小組設定中，針對未知或可能惡意的 URLs** ，使用 [選取] 動作。</span><span class="sxs-lookup"><span data-stu-id="af416-227">Specifically, you use the **Select the action for unknown or potentially malicious URLs within Microsoft Teams** setting.</span></span> <span data-ttu-id="af416-228">建議值為 **On**。</span><span class="sxs-lookup"><span data-stu-id="af416-228">The recommended value is **On**.</span></span>

<span data-ttu-id="af416-229">在 [安全連結原則] 中，套用至電子郵件中連結的下列設定也適用于小組中的連結：</span><span class="sxs-lookup"><span data-stu-id="af416-229">The following settings in Safe Links policies that apply to links in email messages also apply to links in Teams:</span></span>

- <span data-ttu-id="af416-230">**針對可疑的連結和指向檔案的連結套用即時 URL 掃描**</span><span class="sxs-lookup"><span data-stu-id="af416-230">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>
- <span data-ttu-id="af416-231">**不要追蹤使用者點選**</span><span class="sxs-lookup"><span data-stu-id="af416-231">**Do not track user clicks**</span></span>
- <span data-ttu-id="af416-232">**不允許使用者點選原始 URL**</span><span class="sxs-lookup"><span data-stu-id="af416-232">**Do not allow users to click through to original URL**</span></span>

<span data-ttu-id="af416-233">這些設定會在 [ [電子郵件的先前安全連結設定](#safe-links-settings-for-email-messages) ] 區段中說明。</span><span class="sxs-lookup"><span data-stu-id="af416-233">These settings are explained in the previous [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section.</span></span>

<span data-ttu-id="af416-234">在您開啟 Microsoft 小組的安全連結保護之後，當受保護的使用者按一下連結時 (的 [保護]) 時，就會檢查小組中 URLs 的已知惡意連結清單。</span><span class="sxs-lookup"><span data-stu-id="af416-234">After you turn on Safe Links protection for Microsoft Teams, URLs in Teams are checked against a list of known malicious links when the protected user clicks the link (time-of-click protection).</span></span> <span data-ttu-id="af416-235">不會重寫 URLs。</span><span class="sxs-lookup"><span data-stu-id="af416-235">URLs are not rewritten.</span></span> <span data-ttu-id="af416-236">若發現有惡意的連結，使用者將有下列經驗：</span><span class="sxs-lookup"><span data-stu-id="af416-236">If a link is found to be malicious, users will have the following experiences:</span></span>

- <span data-ttu-id="af416-237">如果連結已按一下小組交談中的 [群組聊天] 或 [來自通道]，則 [警告] 頁面會顯示在預設網頁瀏覽器中（如下列螢幕擷取畫面所示）。</span><span class="sxs-lookup"><span data-stu-id="af416-237">If the link was clicked in a Teams conversation, group chat, or from channels, the warning page as shown in the screenshot below will appear in the default web browser.</span></span>
- <span data-ttu-id="af416-238">如果從釘選的索引標籤按一下連結，則 [警告] 頁面會出現在該索引標籤的 [小組] 介面中。出於安全性原因，在網頁瀏覽器中開啟連結的選項已停用。</span><span class="sxs-lookup"><span data-stu-id="af416-238">If the link was clicked from a pinned tab, the warning page will appear in the Teams interface within that tab. The option to open the link in a web browser is disabled for security reasons.</span></span>
- <span data-ttu-id="af416-239">根據已設定原則中 [ **不允許使用者點擊至原始 url** ] 設定的方式，使用者將不允許按一下原始 Url (**繼續 (不建議** 在螢幕擷取畫面) 中) 。</span><span class="sxs-lookup"><span data-stu-id="af416-239">Depending on how the **Do not allow users to click through to original URL** setting in the policy is configured, the user will or will not be allowed to click through to the original URL (**Continue anyway (not recommended)** in the screenshot).</span></span> <span data-ttu-id="af416-240">建議您啟用 [ **不允許使用者點擊至原始 url** ] 設定，讓使用者無法按一下原始 url。</span><span class="sxs-lookup"><span data-stu-id="af416-240">We recommend that you enable the **Do not allow users to click through to original URL** setting so users can't click through to the original URL.</span></span>

<span data-ttu-id="af416-241">如果已啟用團隊保護的安全連結原則中未包含傳送連結的使用者，則使用者可以隨意按一下其電腦或裝置上的原始 URL。</span><span class="sxs-lookup"><span data-stu-id="af416-241">If the user who sent the link isn't included in a Safe Links policy where Teams protection is enabled, the user is free to click through to the original URL on their computer or device.</span></span>

![「小組的安全連結」頁面報告惡意連結。](../../media/tp-safe-links-for-teams-malicious.png)

<span data-ttu-id="af416-243">按一下 [警告] 頁面上的 [ **後退** ] 按鈕，會將使用者傳回其原始的內容或 URL 位置。</span><span class="sxs-lookup"><span data-stu-id="af416-243">Clicking the **Go Back** button on the warning page will return the user to their original context or URL location.</span></span> <span data-ttu-id="af416-244">不過，再次按一下原始連結會導致安全的連結重新掃描 URL，因此會重新顯示 [警告] 頁面。</span><span class="sxs-lookup"><span data-stu-id="af416-244">However, clicking on the original link again will cause Safe Links to rescan the URL, so the warning page will reappear.</span></span>

### <a name="how-safe-links-works-in-teams"></a><span data-ttu-id="af416-245">安全連結在小組中的運作方式</span><span class="sxs-lookup"><span data-stu-id="af416-245">How Safe Links works in Teams</span></span>

<span data-ttu-id="af416-246">在較高的層次，以下是 Microsoft 小組中 URLs 的安全連結保護的運作方式：</span><span class="sxs-lookup"><span data-stu-id="af416-246">At a high level, here's how Safe Links protection works for URLs in Microsoft Teams:</span></span>

1. <span data-ttu-id="af416-247">使用者啟動小組應用程式。</span><span class="sxs-lookup"><span data-stu-id="af416-247">A user starts the Teams app.</span></span>

2. <span data-ttu-id="af416-248">Microsoft 365 會驗證使用者的組織是否包含 Microsoft Defender for Office 365，以及是否將使用者加入使用中的安全連結原則，以啟用 Microsoft 小組的保護功能。</span><span class="sxs-lookup"><span data-stu-id="af416-248">Microsoft 365 verifies that the user's organization includes Microsoft Defender for Office 365, and that the user is included in an active Safe Links policy where protection for Microsoft Teams is enabled.</span></span>

3. <span data-ttu-id="af416-249">在聊天、群組聊天、頻道及標籤式中按一下使用者時，會驗證 URLs。</span><span class="sxs-lookup"><span data-stu-id="af416-249">URLs are validated at the time of click for the user in chats, group chats, channels, and tabs.</span></span>

## <a name="safe-links-settings-for-office-365-apps"></a><span data-ttu-id="af416-250">Office 365 應用程式的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="af416-250">Safe Links settings for Office 365 apps</span></span>

<span data-ttu-id="af416-251">適用于 Office 365 應用程式的安全連結保護會檢查 Office 檔中的連結，不會檢查電子郵件中的連結 (但是可以在開啟檔後，檢查電子郵件中附加 Office 檔中的連結) 。</span><span class="sxs-lookup"><span data-stu-id="af416-251">Safe Links protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).</span></span>

<span data-ttu-id="af416-252">適用于 Office 365 應用程式的安全連結保護具有下列用戶端需求：</span><span class="sxs-lookup"><span data-stu-id="af416-252">Safe Links protection for Office 365 apps has the following client requirements:</span></span>

- <span data-ttu-id="af416-253">Microsoft 365 應用程式或 Microsoft 365 商務版 Premium。</span><span class="sxs-lookup"><span data-stu-id="af416-253">Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="af416-254">Windows、Mac 或網頁瀏覽器中目前的 Word、Excel 及 PowerPoint 版本。</span><span class="sxs-lookup"><span data-stu-id="af416-254">Current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a web browser.</span></span>
  - <span data-ttu-id="af416-255">IOS 或 Android 裝置上的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="af416-255">Office apps on iOS or Android devices.</span></span>
  - <span data-ttu-id="af416-256">Windows 上的 Visio。</span><span class="sxs-lookup"><span data-stu-id="af416-256">Visio on Windows.</span></span>
  - <span data-ttu-id="af416-257">在網頁瀏覽器中 OneNote。</span><span class="sxs-lookup"><span data-stu-id="af416-257">OneNote in a web browser.</span></span>

- <span data-ttu-id="af416-258">Office 365 應用程式已設定為使用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="af416-258">Office 365 apps are configured to use modern authentication.</span></span> <span data-ttu-id="af416-259">如需詳細資訊，請參閱 [如何針對 office 2013、office 2016 和 office 2019 用戶端應用程式運作新式驗證](../../enterprise/modern-auth-for-office-2013-and-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="af416-259">For more information, see [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span>

- <span data-ttu-id="af416-260">使用者已使用其工作或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="af416-260">Users are signed in using their work or school accounts.</span></span> <span data-ttu-id="af416-261">如需詳細資訊，請參閱登 [入 Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)。</span><span class="sxs-lookup"><span data-stu-id="af416-261">For more information, see [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).</span></span>

<span data-ttu-id="af416-262">您可以在安全連結的全域設定中，設定 Office 365 應用程式的安全連結保護，而不是在安全連結原則中設定。</span><span class="sxs-lookup"><span data-stu-id="af416-262">You configure Safe Links protection for Office 365 apps in the global settings for Safe Links, not in Safe Links policies.</span></span> <span data-ttu-id="af416-263">不過，為了套用安全連結保護，若要套用 Office 365 應用程式，開啟 Office 檔並按一下連結的使用者必須包含在使用中的安全連結原則中。</span><span class="sxs-lookup"><span data-stu-id="af416-263">But, in order for Safe Links protection for Office 365 apps to be applied, the user who opens the Office document and clicks the link must be included in an active Safe Links policy.</span></span>

<span data-ttu-id="af416-264">下列安全連結設定可用於 Office 365 應用程式：</span><span class="sxs-lookup"><span data-stu-id="af416-264">The following Safe Links settings are available for Office 365 apps:</span></span>

- <span data-ttu-id="af416-265">**Office 365 應用程式**：啟用或停用支援的 office 365 應用程式中的安全連結掃描。</span><span class="sxs-lookup"><span data-stu-id="af416-265">**Office 365 applications**: Enables or disables Safe Links scanning in supported Office 365 apps.</span></span> <span data-ttu-id="af416-266">預設值和建議值為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="af416-266">The default and recommended value is **On**.</span></span>

- <span data-ttu-id="af416-267">**不要追蹤使用者按一下 [安全連結**] 的時間：啟用或停用儲存安全連結按一下桌上出版本 Word、Excel、PowerPoint 和 Visio 中 URLs 所按一下的 [資料]。</span><span class="sxs-lookup"><span data-stu-id="af416-267">**Do not track when users click Safe Links**: Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="af416-268">建議的值為 **Off**，這表示會追蹤使用者按一下。</span><span class="sxs-lookup"><span data-stu-id="af416-268">The recommended value is **Off**, which means user clicks are tracked.</span></span>

- <span data-ttu-id="af416-269">**請勿讓使用者點擊 [安全連結至原始 url**]：允許或封鎖使用者在桌上出版本 Word、Excel、PowerPoint 和 Visio 中，按一下 [ [警告] 頁面](#warning-pages-from-safe-links) 中的原始 url。</span><span class="sxs-lookup"><span data-stu-id="af416-269">**Do not let users click through safe links to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL in in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="af416-270">預設值和建議值為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="af416-270">The default and recommended value is **On**.</span></span>

<span data-ttu-id="af416-271">若要設定 Office 365 應用程式的安全連結設定，請參閱 [設定 office 365 應用程式的安全連結保護](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="af416-271">To configure the Safe Links settings for Office 365 apps, see [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).</span></span>

<span data-ttu-id="af416-272">如需標準和嚴格原則設定之建議值的詳細資訊，請參閱 [通用連結的通用設定](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="af416-272">For more information about the recommended values for Standard and Strict policy settings, see [Global settings for Safe Links](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links).</span></span>

### <a name="how-safe-links-works-in-office-365-apps"></a><span data-ttu-id="af416-273">Office 365 應用程式中的安全連結的運作方式</span><span class="sxs-lookup"><span data-stu-id="af416-273">How Safe Links works in Office 365 apps</span></span>

<span data-ttu-id="af416-274">在較高的層次，以下是 Office 365 應用程式中 URLs 安全連結保護的運作方式。</span><span class="sxs-lookup"><span data-stu-id="af416-274">At a high level, here's how Safe Links protection works for URLs in Office 365 apps.</span></span> <span data-ttu-id="af416-275">上一節將說明支援的 Office 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="af416-275">The supported Office 365 apps are described in the previous section.</span></span>

1. <span data-ttu-id="af416-276">使用者在包含 Microsoft 365 應用程式或 Microsoft 365 商務版的組織中，使用他們的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="af416-276">A user signs in using their work or school account in an organization that includes Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>

2. <span data-ttu-id="af416-277">使用者開啟並按一下連結的 Office 檔位於支援的 Office 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="af416-277">The user opens and clicks on a link an Office document in a supported Office app.</span></span>

3. <span data-ttu-id="af416-278">安全連結會在開啟目標網站之前，立即檢查 URL：</span><span class="sxs-lookup"><span data-stu-id="af416-278">Safe Links immediately checks the URL before opening the target website:</span></span>

   - <span data-ttu-id="af416-279">如果此 URL 包含在跳過安全連結的清單中 (**封鎖下列 URLs** 清單) [封鎖的 URL 警告](#blocked-url-warning) ] 頁面隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="af416-279">If the URL is included in the list that skips Safe Links scanning (the **Block the following URLs** list) a [blocked URL warning](#blocked-url-warning) page opens.</span></span>

   - <span data-ttu-id="af416-280">如果 URL 指向已確定為惡意的網站，則會開啟 [惡意的網站警告](#malicious-website-warning) 頁面 (或不同的警告頁面) 。</span><span class="sxs-lookup"><span data-stu-id="af416-280">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="af416-281">如果 URL 指向可供下載的檔案，而且套用至使用者的安全連結原則已設定為可掃描可下載內容的連結 (會 **將即時 URL 掃描套用至可疑連結的連結，並將指向** [檔案]) 的連結，則會檢查下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="af416-281">If the URL points to a downloadable file, and the Safe Links policy that applies to the user is configured to scan links to downloadable content (**Apply real-time URL scanning for suspicious links and links that point to files**), the downloadable file is checked.</span></span>

   - <span data-ttu-id="af416-282">如果此 URL 被視為安全的，使用者會進入網站。</span><span class="sxs-lookup"><span data-stu-id="af416-282">If the URL is considered safe, the user is taken to the website.</span></span>

   - <span data-ttu-id="af416-283">如果安全連結掃描無法完成，則安全連結保護不會觸發。</span><span class="sxs-lookup"><span data-stu-id="af416-283">If Safe Links scanning is unable to complete, Safe Links protection does not trigger.</span></span> <span data-ttu-id="af416-284">在 Office 桌面用戶端中，使用者會先收到警告，再繼續前往目的地網站。</span><span class="sxs-lookup"><span data-stu-id="af416-284">In Office desktop clients, the user will be warned before they proceed to the destination website.</span></span>

> [!NOTE]
> <span data-ttu-id="af416-285">在每個會話開始時，可能需要幾秒鐘的時間，以確認使用者已啟用 Office 的安全連結。</span><span class="sxs-lookup"><span data-stu-id="af416-285">It may take several seconds at the beginning of each session to verify that the user has Safe Links for Office enabled.</span></span>

## <a name="block-the-following-urls-list-for-safe-links"></a><span data-ttu-id="af416-286">安全連結的「封鎖下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="af416-286">"Block the following URLs" list for Safe Links</span></span>

<span data-ttu-id="af416-287">**Block 下列 URLs** 清單會定義在下列位置中，以安全連結掃描時，永遠封鎖的連結：</span><span class="sxs-lookup"><span data-stu-id="af416-287">The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:</span></span>

- <span data-ttu-id="af416-288">電子郵件。</span><span class="sxs-lookup"><span data-stu-id="af416-288">Email messages.</span></span>
- <span data-ttu-id="af416-289">Windows 和 Mac 中 Office 365 應用程式中的檔。</span><span class="sxs-lookup"><span data-stu-id="af416-289">Documents in Office 365 apps in Windows and Mac.</span></span>
- <span data-ttu-id="af416-290">Office 中用於 iOS 和 Android 的檔。</span><span class="sxs-lookup"><span data-stu-id="af416-290">Documents in Office for iOS and Android.</span></span>

<span data-ttu-id="af416-291">當使用中安全連結原則中的使用者在支援的應用程式中按一下封鎖的連結時，會移至 [ [封鎖的 URL 警告](#blocked-url-warning) ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="af416-291">When a user in an active Safe Links policy clicks a blocked link in a supported app, they're taken to the [Blocked URL warning](#blocked-url-warning) page.</span></span>

<span data-ttu-id="af416-292">您可以在 [安全連結] 的 [通用設定] 中設定 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="af416-292">You configure the list of URLs in the global settings for Safe Links.</span></span> <span data-ttu-id="af416-293">如需相關指示，請參閱 Configure the the 「 [Block the URLs」清單](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="af416-293">For instructions, see [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).</span></span>

<span data-ttu-id="af416-294">**附註**：</span><span class="sxs-lookup"><span data-stu-id="af416-294">**Notes**:</span></span>

- <span data-ttu-id="af416-295">如需在所有位置封鎖的真正通用 URLs 清單，請參閱 [Manage The 承租人 Allow/封鎖清單](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="af416-295">For a truly universal list of URLs that are blocked everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="af416-296">限制：</span><span class="sxs-lookup"><span data-stu-id="af416-296">Limits:</span></span>
  - <span data-ttu-id="af416-297">專案的數目上限為500。</span><span class="sxs-lookup"><span data-stu-id="af416-297">The maximum number of entries is 500.</span></span>
  - <span data-ttu-id="af416-298">專案的長度上限為128個字元。</span><span class="sxs-lookup"><span data-stu-id="af416-298">The maximum length of an entry is 128 characters.</span></span>
  - <span data-ttu-id="af416-299">所有專案都不得超過10000個字元。</span><span class="sxs-lookup"><span data-stu-id="af416-299">All of the entries can't exceed 10,000 characters.</span></span>

- <span data-ttu-id="af416-300">請勿在 URL 的結尾加入正斜線 (`/`) 。</span><span class="sxs-lookup"><span data-stu-id="af416-300">Don't include a forward slash (`/`) at the end of the URL.</span></span> <span data-ttu-id="af416-301">例如，使用 `https://www.contoso.com` ，not `https://www.contoso.com/` 。</span><span class="sxs-lookup"><span data-stu-id="af416-301">For example, use `https://www.contoso.com`, not `https://www.contoso.com/`.</span></span>

- <span data-ttu-id="af416-302">例如，僅限網域的 URL (例如 `contoso.com` 或 `tailspintoys.com`) 會封鎖任何包含網域的 url。</span><span class="sxs-lookup"><span data-stu-id="af416-302">A domain only-URL (for example `contoso.com` or `tailspintoys.com`) will block any URL that contains the domain.</span></span>

- <span data-ttu-id="af416-303">您可以封鎖子域，但不封鎖整個網域。</span><span class="sxs-lookup"><span data-stu-id="af416-303">You can block a subdomain without blocking the full domain.</span></span> <span data-ttu-id="af416-304">例如， `toys.contoso.com*` 封鎖包含子域的任何 URL，但它不會封鎖包含完整網域的 URLs `contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="af416-304">For example, `toys.contoso.com*` blocks any URL that contains the subdomain, but it doesn't block URLs that contain the full domain `contoso.com`.</span></span>

- <span data-ttu-id="af416-305">每個 URL 專案最多可以包含三個萬用字元 (`*`) 。</span><span class="sxs-lookup"><span data-stu-id="af416-305">You can include up to three wildcards (`*`) per URL entry.</span></span>

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a><span data-ttu-id="af416-306">「封鎖下列 URLs 的專案語法」清單</span><span class="sxs-lookup"><span data-stu-id="af416-306">Entry syntax for the "Block the following URLs" list</span></span>

<span data-ttu-id="af416-307">下表說明您可以輸入的值及其結果的範例：</span><span class="sxs-lookup"><span data-stu-id="af416-307">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="af416-308">值</span><span class="sxs-lookup"><span data-stu-id="af416-308">Value</span></span>|<span data-ttu-id="af416-309">結果</span><span class="sxs-lookup"><span data-stu-id="af416-309">Result</span></span>|
|---|---|
|`contoso.com` <p> <span data-ttu-id="af416-310">或</span><span class="sxs-lookup"><span data-stu-id="af416-310">or</span></span> <p> `*contoso.com*`|<span data-ttu-id="af416-311">封鎖網域、子域及路徑。</span><span class="sxs-lookup"><span data-stu-id="af416-311">Blocks the domain, subdomains, and paths.</span></span> <span data-ttu-id="af416-312">例如，， `https://www.contoso.com` `https://sub.contoso.com` 及 `https://contoso.com/abc` 會封鎖。</span><span class="sxs-lookup"><span data-stu-id="af416-312">For example, `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc` are blocked.</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="af416-313">封鎖 `https://contoso.com/a` 但不其他類似的子路徑 `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="af416-313">Blocks `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="af416-314">區塊 `https://contoso.com/a` 及其他類似的子路徑 `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="af416-314">Blocks `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="af416-315">`toys`在此範例中封鎖子域 () 但是允許按一下其他網域 URLs (如 `https://contoso.com` 或 `https://home.contoso.com`) 。</span><span class="sxs-lookup"><span data-stu-id="af416-315">Blocks a subdomain (`toys` in this example) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a><span data-ttu-id="af416-316">安全連結原則中的「不要重新寫入下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="af416-316">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>

> [!NOTE]
> <span data-ttu-id="af416-317">如果您的組織使用安全連結原則， **請勿重新寫入下列 URLs** 清單是協力廠商網路釣魚測試唯一支援的方法。</span><span class="sxs-lookup"><span data-stu-id="af416-317">If your organization use Safe Links policies, the **Do not rewrite the following URLs** lists are the only supported method for third party phishing tests.</span></span>

<span data-ttu-id="af416-318">每個安全連結原則都包含 **[不要重新寫入下列 URLs** 清單，您可以使用此清單來指定不會以安全連結掃描來重新寫入 URLs。</span><span class="sxs-lookup"><span data-stu-id="af416-318">Each Safe Links policy contains a **Do not rewrite the following URLs** list that you can use to specify URLs that are not rewritten by Safe Links scanning.</span></span> <span data-ttu-id="af416-319">換句話說，此清單允許包含在原則中的使用者存取指定的 URLs，否則會受到安全連結的封鎖。</span><span class="sxs-lookup"><span data-stu-id="af416-319">In other words, the list allows users who are included in the policy to access the specified URLs that would otherwise be blocked by Safe Links.</span></span> <span data-ttu-id="af416-320">您可以在不同的安全連結原則中設定不同的清單。</span><span class="sxs-lookup"><span data-stu-id="af416-320">You can configure different lists in different Safe Links policies.</span></span> <span data-ttu-id="af416-321">原則處理會在第一 (後停止，最高優先順序) 原則會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="af416-321">Policy processing stops after the first (likely, the highest priority) policy is applied to the user.</span></span> <span data-ttu-id="af416-322">因此，只有一個不重新 **寫入下列 URLs** 清單會套用至包含在多個作用中安全連結原則中的使用者。</span><span class="sxs-lookup"><span data-stu-id="af416-322">So, only one **Do not rewrite the following URLs** list is applied to a user who is included in multiple active Safe Links policies.</span></span>

<span data-ttu-id="af416-323">若要將專案新增至新的或現有的安全連結原則中的清單，請參閱 [建立安全連結原則](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) 或 [修改安全連結原則](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="af416-323">To add entries to the list in new or existing Safe Links policies, see [Create Safe Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).</span></span>

<span data-ttu-id="af416-324">**附註**：</span><span class="sxs-lookup"><span data-stu-id="af416-324">**Notes**:</span></span>

- <span data-ttu-id="af416-325">下列用戶端無法辨識安全連結原則中的 [ **不要重新寫入下列 URLs** 清單。</span><span class="sxs-lookup"><span data-stu-id="af416-325">The following clients don't recognize the **Do not rewrite the following URLs** lists in Safe Links policies.</span></span> <span data-ttu-id="af416-326">您可以根據這些用戶端中的安全連結掃描的結果，URLs 封鎖原則中所含的使用者：</span><span class="sxs-lookup"><span data-stu-id="af416-326">Users included in the polices can be blocked from accessing the URLs based on the results of Safe Links scanning in these clients:</span></span>

  - <span data-ttu-id="af416-327">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af416-327">Microsoft Teams</span></span>
  - <span data-ttu-id="af416-328">Office web apps</span><span class="sxs-lookup"><span data-stu-id="af416-328">Office web apps</span></span>

  <span data-ttu-id="af416-329">如需真實通用的 URLs 允許任何地方使用的清單，請參閱 [Manage The 承租人 Allow/封鎖清單](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="af416-329">For a truly universal list of URLs that are allowed everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="af416-330">考慮在清單中新增常用的內部 URLs，以提升使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="af416-330">Consider adding commonly used internal URLs to the list to improve the user experience.</span></span> <span data-ttu-id="af416-331">例如，如果您有內部部署服務（例如商務用 Skype 或 SharePoint），您可以將這些服務新增 URLs 以從掃描中排除。</span><span class="sxs-lookup"><span data-stu-id="af416-331">For example, if you have on-premises services, such as Skype for Business or SharePoint, you can add those URLs to exclude them from scanning.</span></span>

- <span data-ttu-id="af416-332">如果您已有 [安全連結原則] 中 **的 [不要重新寫入下列 URLs** 專案]，請務必查看清單，並視需要新增萬用字元。</span><span class="sxs-lookup"><span data-stu-id="af416-332">If you already have **Do not rewrite the following URLs** entries in your Safe Links policies, be sure to review the lists and add wildcards as required.</span></span> <span data-ttu-id="af416-333">例如，您的清單有類似的專案， `https://contoso.com/a` 而您後來決定包含類似的子路徑 `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="af416-333">For example, your list has an entry like `https://contoso.com/a` and you later decide to include subpaths like `https://contoso.com/a/b`.</span></span> <span data-ttu-id="af416-334">除了新增專案之外，將萬用字元新增至現有專案，使其變成 `https://contoso.com/a/*` 。</span><span class="sxs-lookup"><span data-stu-id="af416-334">Instead of adding a new entry, add a wildcard to the existing entry so it becomes `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="af416-335">每個 URL 專案最多可以包含三個萬用字元 (`*`) 。</span><span class="sxs-lookup"><span data-stu-id="af416-335">You can include up to three wildcards (`*`) per URL entry.</span></span> <span data-ttu-id="af416-336">萬用字元會明確包含首碼或子域。</span><span class="sxs-lookup"><span data-stu-id="af416-336">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="af416-337">例如，該專案與 `contoso.com` 不同的專案不同 `*.contoso.com/*` ，因為 `*.contoso.com/*` 允許人員造訪指定網域中的子域和路徑。</span><span class="sxs-lookup"><span data-stu-id="af416-337">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a><span data-ttu-id="af416-338">[不要重新寫入下列 URLs] 清單的專案語法</span><span class="sxs-lookup"><span data-stu-id="af416-338">Entry syntax for the "Do not rewrite the following URLs" list</span></span>

<span data-ttu-id="af416-339">下表說明您可以輸入的值及其結果的範例：</span><span class="sxs-lookup"><span data-stu-id="af416-339">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="af416-340">值</span><span class="sxs-lookup"><span data-stu-id="af416-340">Value</span></span>|<span data-ttu-id="af416-341">結果</span><span class="sxs-lookup"><span data-stu-id="af416-341">Result</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="af416-342">允許存取， `https://contoso.com` 但非子域或路徑。</span><span class="sxs-lookup"><span data-stu-id="af416-342">Allows access to `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="af416-343">允許存取網域、子域及路徑 (例如，、、 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` 或 `https://www.contoso.com/a`) 。</span><span class="sxs-lookup"><span data-stu-id="af416-343">Allows access to a domain, subdomains, and paths (for example, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`).</span></span> <p> <span data-ttu-id="af416-344">此專案原本很好 `*contoso.com*` ，因為它不允許可能的詐騙網站，例如 `https://www.falsecontoso.com` 或 `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="af416-344">This entry is inherently better than `*contoso.com*`, because it doesn't allow potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="af416-345">允許存取 `https://contoso.com/a` ，但不允許像這樣的子路徑 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="af416-345">Allows access to `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="af416-346">允許存取 `https://contoso.com/a` 和子路徑，如 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="af416-346">Allows access to `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|

## <a name="warning-pages-from-safe-links"></a><span data-ttu-id="af416-347">安全連結的警告頁面</span><span class="sxs-lookup"><span data-stu-id="af416-347">Warning pages from Safe Links</span></span>

<span data-ttu-id="af416-348">本節包含當您按一下 URL 時，安全連結保護所觸發之各種警告頁面的範例。</span><span class="sxs-lookup"><span data-stu-id="af416-348">This section contains examples of the various warning pages that are triggered by Safe Links protection when you click a URL.</span></span>

<span data-ttu-id="af416-349">請注意，許多警告頁面已更新。</span><span class="sxs-lookup"><span data-stu-id="af416-349">Note that several warning pages have been updated.</span></span> <span data-ttu-id="af416-350">如果您還沒有看到更新的頁面，您會很快。</span><span class="sxs-lookup"><span data-stu-id="af416-350">If you're not already seeing the updated pages, you will soon.</span></span> <span data-ttu-id="af416-351">更新的頁面包含新的色彩配置、更詳細的資訊，以及在有指定的警告和建議下，可繼續前往網站的功能。</span><span class="sxs-lookup"><span data-stu-id="af416-351">The updated pages include a new color scheme, more detail, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="scan-in-progress-notification"></a><span data-ttu-id="af416-352">掃描進行中的通知</span><span class="sxs-lookup"><span data-stu-id="af416-352">Scan in progress notification</span></span>

<span data-ttu-id="af416-353">安全連結正在掃描按一下的 URL。</span><span class="sxs-lookup"><span data-stu-id="af416-353">The clicked URL is being scanned by Safe Links.</span></span> <span data-ttu-id="af416-354">您可能需要稍等片刻，再重新嘗試連結。</span><span class="sxs-lookup"><span data-stu-id="af416-354">You might need to wait a few moments before trying the link again.</span></span>

![「正在掃描連結」通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="af416-356">原始通知頁面如下所示：</span><span class="sxs-lookup"><span data-stu-id="af416-356">The original notification page looked like this:</span></span>

![原始「正在掃描連結」通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a><span data-ttu-id="af416-358">可疑的郵件警告</span><span class="sxs-lookup"><span data-stu-id="af416-358">Suspicious message warning</span></span>

<span data-ttu-id="af416-359">按一下的 URL 位於類似其他可疑郵件的電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="af416-359">The clicked URL was in an email message that's similar to other suspicious messages.</span></span> <span data-ttu-id="af416-360">建議您先檢查電子郵件訊息，再繼續進行網站。</span><span class="sxs-lookup"><span data-stu-id="af416-360">We recommend that you double-check the email message before proceeding to the site.</span></span>

![「從可疑的郵件按一下連結」警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a><span data-ttu-id="af416-362">網路釣魚嘗試警告</span><span class="sxs-lookup"><span data-stu-id="af416-362">Phishing attempt warning</span></span>

<span data-ttu-id="af416-363">按一下的 URL 位於已識別為網路釣魚攻擊的電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="af416-363">The clicked URL was in an email message that has been identified as a phishing attack.</span></span> <span data-ttu-id="af416-364">因此，電子郵件中的所有 URLs 都會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="af416-364">As a result, all URLs in the email message are blocked.</span></span> <span data-ttu-id="af416-365">建議您不要繼續進行網站。</span><span class="sxs-lookup"><span data-stu-id="af416-365">We recommend that you do not proceed to the site.</span></span>

![「從網路釣魚郵件按一下連結」警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a><span data-ttu-id="af416-367">惡意網站警告</span><span class="sxs-lookup"><span data-stu-id="af416-367">Malicious website warning</span></span>

<span data-ttu-id="af416-368">已按一下的 URL 指向已識別為惡意的網站。</span><span class="sxs-lookup"><span data-stu-id="af416-368">The clicked URL points to a site that has been identified as malicious.</span></span> <span data-ttu-id="af416-369">建議您不要繼續進行網站。</span><span class="sxs-lookup"><span data-stu-id="af416-369">We recommend that you do not proceed to the site.</span></span>

![「此網站歸類為惡意」警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="af416-371">原始的 [警告] 頁面如下所示：</span><span class="sxs-lookup"><span data-stu-id="af416-371">The original warning page looked like this:</span></span>

![原始「此網站已歸類為惡意」警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="af416-373">封鎖的 URL 警告</span><span class="sxs-lookup"><span data-stu-id="af416-373">Blocked URL warning</span></span>

<span data-ttu-id="af416-374">您組織中的系統管理員已手動封鎖已按一下的 URL (在 [安全連結) ] 的 [全域設定] 中 **封鎖下列 URLs** 清單。</span><span class="sxs-lookup"><span data-stu-id="af416-374">The clicked URL has been manually blocked by an admin in your organization (the **Block the following URLs** list in the global settings for Safe Links).</span></span> <span data-ttu-id="af416-375">因為安全連結已手動封鎖，所以無法掃描連結。</span><span class="sxs-lookup"><span data-stu-id="af416-375">The link was not scanned by Safe Links because it was manually blocked.</span></span>

<span data-ttu-id="af416-376">管理員手動封鎖特定 URLs 的原因有幾個。</span><span class="sxs-lookup"><span data-stu-id="af416-376">There are several reasons why an admin would manually block specific URLs.</span></span> <span data-ttu-id="af416-377">如果您認為網站不應該封鎖，請與您的系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="af416-377">If you think the site should not be blocked, contact your admin.</span></span>

![「您的系統管理員已封鎖此網站」警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="af416-379">原始的 [警告] 頁面如下所示：</span><span class="sxs-lookup"><span data-stu-id="af416-379">The original warning page looked like this:</span></span>

![原始「根據您組織的 URL 原則，已封鎖此網站」警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a><span data-ttu-id="af416-381">錯誤警告</span><span class="sxs-lookup"><span data-stu-id="af416-381">Error warning</span></span>

<span data-ttu-id="af416-382">發生某種類型的錯誤，無法開啟此 URL。</span><span class="sxs-lookup"><span data-stu-id="af416-382">Some kind of error has occurred, and the URL can't be opened.</span></span>

![「無法載入您嘗試存取的頁面」警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="af416-384">原始的 [警告] 頁面如下所示：</span><span class="sxs-lookup"><span data-stu-id="af416-384">The original warning page looked like this:</span></span>

![原始「無法載入此網頁」網頁」警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)