---
title: 安全連結
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.article: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365-initiative-defender-office365
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
description: 在本文中，系統管理員可以深入瞭解 Office 365 的安全連結保護 (ATP) ，以保護其組織免受使用惡意 URLs 之網路釣魚和其他攻擊的威脅。
ms.openlocfilehash: 7b10a941d63fd654a61c6d6ec78869f4bafb3edd
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417270"
---
# <a name="safe-links-in-office-365-atp"></a><span data-ttu-id="04875-103">Office 365 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="04875-103">Safe Links in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="04875-104">本文適用于具有 [Office 365 高級威脅防護 (ATP) ](office-365-atp.md)的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="04875-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="04875-105">如果您使用的是 Outlook.com、Microsoft 365 系列或 Microsoft 365 個人版，且您在 Outlook 中尋找 Safelinks 的相關資訊，請參閱 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="04875-105">If you're using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="04875-106">安全連結是 [Office 365 高級威脅防護](office-365-atp.md) 中的一項功能，可提供郵件流程中的輸入電子郵件訊息的 URL 掃描和修正，以及電子郵件和其他位置中 URLs 和連結的時間驗證。</span><span class="sxs-lookup"><span data-stu-id="04875-106">Safe Links is a feature in [Office 365 Advanced Threat Protection](office-365-atp.md) that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.</span></span> <span data-ttu-id="04875-107">在 Exchange Online Protection (EOP) 中，除了內送電子郵件訊息中的一般 [反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md) 之外，也會進行安全連結掃描。</span><span class="sxs-lookup"><span data-stu-id="04875-107">Safe Links scanning occurs in addition to the regular [anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md) in inbound email messages in Exchange Online Protection (EOP).</span></span> <span data-ttu-id="04875-108">安全連結掃描可協助保護您的組織免受網路釣魚和其他攻擊中所用的惡意連結。</span><span class="sxs-lookup"><span data-stu-id="04875-108">Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.</span></span>

<span data-ttu-id="04875-109">在下列位置可取得安全連結保護：</span><span class="sxs-lookup"><span data-stu-id="04875-109">Safe Links protection is available in the following locations:</span></span>

- <span data-ttu-id="04875-110">**電子郵件訊息**：安全連結保護電子郵件訊息中的連結是由安全連結原則所控制。</span><span class="sxs-lookup"><span data-stu-id="04875-110">**Email messages**: Safe Links protection for links in email messages is controlled by Safe Links policies.</span></span> <span data-ttu-id="04875-111">沒有預設的安全連結原則， **因此若要在電子郵件中取得安全連結的保護，您必須建立一或多個安全連結原則**。</span><span class="sxs-lookup"><span data-stu-id="04875-111">There is no default Safe Links policy, **so to get the protection of Safe Links in email messages, you need to create one or more Safe Links policies**.</span></span> <span data-ttu-id="04875-112">如需相關指示，請參閱 [設定 ATP 中的安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="04875-112">For instructions, see [Set up Safe Links policies in ATP](set-up-atp-safe-links-policies.md).</span></span>

  <span data-ttu-id="04875-113">如需電子郵件安全連結保護的詳細資訊，請參閱本文稍後的 [ [電子郵件的安全連結設定](#safe-links-settings-for-email-messages) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="04875-113">For more information about Safe Links protection for email messages, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>

- <span data-ttu-id="04875-114">**Microsoft 團隊** (目前在點擊預覽) ：對小組交談、群組聊天或管道中的連結的安全連結保護也是由安全連結原則所控制。</span><span class="sxs-lookup"><span data-stu-id="04875-114">**Microsoft Teams** (currently in TAP Preview): Safe Links protection for links in Teams conversations, group chats, or from channels is also controlled by Safe Links policies.</span></span> <span data-ttu-id="04875-115">沒有預設的安全連結原則， **因此若要在小組中取得安全連結的保護，您必須建立一或多個安全連結原則**。</span><span class="sxs-lookup"><span data-stu-id="04875-115">There is no default Safe Links policy, **so to get the protection of Safe Links in Teams, you need to create one or more Safe Links policies**.</span></span>

  <span data-ttu-id="04875-116">如需小組中安全連結保護的詳細資訊，請參閱本主題稍後的「 [Microsoft 團隊的安全連結設定](#safe-links-settings-for-microsoft-teams) 」一節。</span><span class="sxs-lookup"><span data-stu-id="04875-116">For more information about Safe Links protection in Teams, see the [Safe Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) section later in this topic.</span></span>

- <span data-ttu-id="04875-117">**Office 365 應用程式**： office 365 應用程式的安全連結保護可在支援的桌面、行動裝置和網路 ap 中取得。</span><span class="sxs-lookup"><span data-stu-id="04875-117">**Office 365 apps**: Safe Links protection for Office 365 apps is available in supported desktop, mobile, and web aps.</span></span> <span data-ttu-id="04875-118">您可以在安全連結原則**以外**的全域設定中，**設定**Office 365 應用程式的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="04875-118">You **configure** Safe Links protection for Office 365 apps in the global setting that are **outside** of Safe Links policies.</span></span> <span data-ttu-id="04875-119">如需相關指示，請參閱 [在 Office 365 ATP 中設定安全連結設定的通用設定](configure-global-settings-for-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="04875-119">For instructions, see [Configure global settings for Safe Links settings in Office 365 ATP](configure-global-settings-for-safe-links.md).</span></span>

  <span data-ttu-id="04875-120">不過，Office 365 應用程式的安全連結保護只 **適用** 于包含在使用中安全連結原則中的使用者。</span><span class="sxs-lookup"><span data-stu-id="04875-120">But, Safe Links protection for Office 365 apps is only **applied** to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="04875-121">如果使用者未包含在使用中的安全連結原則中，使用者就不會在支援的 Office 365 應用程式中取得安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="04875-121">If a user isn't included in an active Safe Links policy, the user doesn't get Safe Links protection in supported Office 365 apps.</span></span>

  <span data-ttu-id="04875-122">如需 Office 365 應用程式中安全連結保護的詳細資訊，請參閱本文稍後的 [office 365 應用程式的安全連結設定](#safe-links-settings-for-office-365-apps) 一節。</span><span class="sxs-lookup"><span data-stu-id="04875-122">For more information about Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>

<span data-ttu-id="04875-123">本文包含下列安全連結設定類型的詳細描述：</span><span class="sxs-lookup"><span data-stu-id="04875-123">This article includes detailed descriptions of the following types of Safe Links settings:</span></span>

- <span data-ttu-id="04875-124">**安全連結原則中的設定**：這些設定僅適用于包含在特定原則中的使用者，而且各原則的設定可能不同。</span><span class="sxs-lookup"><span data-stu-id="04875-124">**Settings in Safe Links policies**: These settings apply only to the users who are included in the specific policies, and the settings might be different between policies.</span></span> <span data-ttu-id="04875-125">這些設定包括：</span><span class="sxs-lookup"><span data-stu-id="04875-125">These settings include:</span></span>

  - [<span data-ttu-id="04875-126">電子郵件訊息的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="04875-126">Safe Links settings for email messages</span></span>](#safe-links-settings-for-email-messages)
  - [<span data-ttu-id="04875-127">Microsoft 小組的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="04875-127">Safe Links settings for Microsoft Teams</span></span>](#safe-links-settings-for-microsoft-teams)
  - [<span data-ttu-id="04875-128">安全連結原則中的「不要重新寫入下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="04875-128">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- <span data-ttu-id="04875-129">**全域安全連結設定**：這些設定會全域設定，而不是在安全連結原則中。</span><span class="sxs-lookup"><span data-stu-id="04875-129">**Global Safe Links settings**: These settings are configured globally, not in Safe Links policies.</span></span> <span data-ttu-id="04875-130">不過，這些設定僅適用于包含在使用中安全連結原則中的使用者。</span><span class="sxs-lookup"><span data-stu-id="04875-130">But, the settings apply only to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="04875-131">這些設定包括：</span><span class="sxs-lookup"><span data-stu-id="04875-131">These settings include:</span></span>

  - [<span data-ttu-id="04875-132">Office 365 應用程式的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="04875-132">Safe Links settings for Office 365 apps</span></span>](#safe-links-settings-for-office-365-apps)
  - [<span data-ttu-id="04875-133">安全連結的「封鎖下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="04875-133">"Block the following URLs" list for Safe Links</span></span>](#block-the-following-urls-list-for-safe-links)

<span data-ttu-id="04875-134">下表說明 Microsoft 365 和 Office 365 組織中包含 ATP (的安全連結案例，也就是說，缺乏授權不是範例) 中的問題。</span><span class="sxs-lookup"><span data-stu-id="04875-134">The following table describes scenarios for Safe Links in Microsoft 365 and Office 365 organizations that include ATP (in other words, lack of licensing is never an issue in the examples).</span></span>

****

|<span data-ttu-id="04875-135">案例</span><span class="sxs-lookup"><span data-stu-id="04875-135">Scenario</span></span>|<span data-ttu-id="04875-136">結果</span><span class="sxs-lookup"><span data-stu-id="04875-136">Result</span></span>|
|---|---|
|<span data-ttu-id="04875-137">Jean-francois 是行銷部門的成員。</span><span class="sxs-lookup"><span data-stu-id="04875-137">Jean is a member of the marketing department.</span></span> <span data-ttu-id="04875-138">在安全連結的通用設定中開啟 Office 365 應用程式的安全連結保護，以及適用于行銷部門成員的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="04875-138">Safe Links protection for Office 365 apps is turned on in the global settings for Safe Links, and a Safe Links policy that applies to members of the marketing department exists.</span></span> <span data-ttu-id="04875-139">Jean-francois 會在電子郵件訊息中開啟 PowerPoint 簡報，然後按一下簡報中的 URL。</span><span class="sxs-lookup"><span data-stu-id="04875-139">Jean opens a PowerPoint presentation in an email message, and then clicks a URL in the presentation.</span></span>|<span data-ttu-id="04875-140">Jean-francois 受到安全連結的保護。</span><span class="sxs-lookup"><span data-stu-id="04875-140">Jean is protected by Safe Links.</span></span> <br/><br/> <span data-ttu-id="04875-141">Jean-francois 包含在安全連結原則中，且已開啟 Office 365 應用程式的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="04875-141">Jean is included in a Safe Links policy, and Safe Links protection for Office 365 apps is turned on.</span></span> <br/><br/> <span data-ttu-id="04875-142">如需 Office 365 應用程式中安全連結保護需求的詳細資訊，請參閱本文稍後的「 [Office 365 應用程式的安全連結設定](#safe-links-settings-for-office-365-apps) 」一節。</span><span class="sxs-lookup"><span data-stu-id="04875-142">For more information about the requirements for Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>|
|<span data-ttu-id="04875-143">Chris 的 Microsoft 365 E5 組織未設定安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="04875-143">Chris's Microsoft 365 E5 organization has no Safe Links policies configured.</span></span> <span data-ttu-id="04875-144">Chris 會接收來自外部寄件者的電子郵件，該寄件者包含的 URL 指向他最後按一下的惡意網站。</span><span class="sxs-lookup"><span data-stu-id="04875-144">Chris receives an email from an external sender that contains a URL to a malicious website that he ultimately clicks.</span></span>|<span data-ttu-id="04875-145">Chris 未受到安全連結的保護。</span><span class="sxs-lookup"><span data-stu-id="04875-145">Chris is not protected by Safe Links.</span></span> <br/><br/> <span data-ttu-id="04875-146">管理員至少必須建立一個安全連結原則，以供任何人取得輸入電子郵件訊息中的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="04875-146">An admin must create at least one Safe Links policy for anyone to get Safe Links protection in inbound email messages.</span></span> <span data-ttu-id="04875-147">在原則的條件中必須包含 Chris，才可取得安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="04875-147">Chris must be included in the conditions of policy to get Safe Links protection.</span></span>|
|<span data-ttu-id="04875-148">在 Pat 的組織中，沒有系統管理員已建立任何安全連結原則，但已開啟 Office 365 應用程式的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="04875-148">In Pat's organization, no admins have created any Safe Links policies, but Safe Links protection for Office 365 apps is turned on.</span></span> <span data-ttu-id="04875-149">Pat 開啟 Word 檔，然後按一下檔案中的 URL。</span><span class="sxs-lookup"><span data-stu-id="04875-149">Pat opens a Word document and clicks a URL in the file.</span></span>|<span data-ttu-id="04875-150">Pat 未受到安全連結的保護。</span><span class="sxs-lookup"><span data-stu-id="04875-150">Pat is not protected by Safe Links.</span></span> <br/><br/> <span data-ttu-id="04875-151">雖然以全域方式開啟 Office 365 應用程式的安全連結保護，但 Pat 並未包含在任何使用中的安全連結原則中，因此無法套用保護。</span><span class="sxs-lookup"><span data-stu-id="04875-151">Although Safe Links protection for Office 365 apps is turned on globally, Pat is not included in any active Safe Links policies, so the protection can't be applied.</span></span>|
|<span data-ttu-id="04875-152">在「企業版的組織」中，于 [ `https://tailspintoys.com` 安全連結的全域設定] 中的 [ **封鎖下列 URLs** ] 清單中設定。</span><span class="sxs-lookup"><span data-stu-id="04875-152">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span></span> <span data-ttu-id="04875-153">包含「擁有先生」的安全連結原則已存在。</span><span class="sxs-lookup"><span data-stu-id="04875-153">A Safe Links policy that includes Lee already exists.</span></span> <span data-ttu-id="04875-154">「電子郵件」會收到包含 URL 的電子郵件 `https://tailspintoys.com/aboutus/trythispage` 。</span><span class="sxs-lookup"><span data-stu-id="04875-154">Lee receives an email message that contains the URL `https://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="04875-155">Lee 按下該 URL。</span><span class="sxs-lookup"><span data-stu-id="04875-155">Lee clicks the URL.</span></span>|<span data-ttu-id="04875-156">您可以自動封鎖此 URL。這取決於清單中的 URL 專案和使用的電子郵件用戶端。</span><span class="sxs-lookup"><span data-stu-id="04875-156">The URL might be automatically blocked for Lee; it depends on the URL entry in the list and the email client Lee used.</span></span> <span data-ttu-id="04875-157">如需詳細資訊，請參閱本主題稍後的「 [阻止下列 URLs 的安全連結的清單](#block-the-following-urls-list-for-safe-links) 」一節。</span><span class="sxs-lookup"><span data-stu-id="04875-157">For more information, see the ["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links) section later in this topic.</span></span>|
|<span data-ttu-id="04875-158">曉明和 Julia 這兩個 contoso.com 的工作。</span><span class="sxs-lookup"><span data-stu-id="04875-158">Jamie and Julia both work for contoso.com.</span></span> <span data-ttu-id="04875-159">很久之前，系統管理員設定了同時適用于曉明和 Julia 的安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="04875-159">A long time ago, admins configured Safe Links policies that apply to both of Jamie and Julia.</span></span> <span data-ttu-id="04875-160">曉明會將電子郵件傳送至 Julia，而不知道電子郵件中包含惡意 URL。</span><span class="sxs-lookup"><span data-stu-id="04875-160">Jamie sends an email to Julia, not knowing that the email contains a malicious URL.</span></span>|<span data-ttu-id="04875-161">**如果**套用至她的安全連結原則設定為套用至內部收件者之間的郵件，則安全連結會保護 Julia。</span><span class="sxs-lookup"><span data-stu-id="04875-161">Julia is protected by Safe Links **if** the Safe Links policy that applies to her is configured to apply to messages between internal recipients.</span></span> <span data-ttu-id="04875-162">如需詳細資訊，請參閱本主題稍後的「 [電子郵件的安全連結設定](#safe-links-settings-for-email-messages) 」一節。</span><span class="sxs-lookup"><span data-stu-id="04875-162">For more information, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this topic.</span></span>|

## <a name="safe-links-settings-for-email-messages"></a><span data-ttu-id="04875-163">電子郵件訊息的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="04875-163">Safe Links settings for email messages</span></span>

<span data-ttu-id="04875-164">安全連結會掃描內送電子郵件中的已知惡意超連結。</span><span class="sxs-lookup"><span data-stu-id="04875-164">Safe Links scans incoming email for known malicious hyperlinks.</span></span> <span data-ttu-id="04875-165">掃描的 URLs 會使用 Microsoft standard URL 前置詞來重新寫入： `https://nam01.safelinks.protection.outlook.com` 。</span><span class="sxs-lookup"><span data-stu-id="04875-165">Scanned URLs are rewritten using the Microsoft standard URL prefix: `https://nam01.safelinks.protection.outlook.com`.</span></span> <span data-ttu-id="04875-166">在重新寫入連結之後，它會針對潛在的惡意內容進行分析。</span><span class="sxs-lookup"><span data-stu-id="04875-166">After the link is rewritten, it's analyzed for potentially malicious content.</span></span>

<span data-ttu-id="04875-167">安全連結重新寫入 URL 後，即使郵件是轉寄或回復的，該 URL 仍會保持重新寫入。</span><span class="sxs-lookup"><span data-stu-id="04875-167">After Safe Links rewrites a URL, the URL remains rewritten, even if the message is forwarded or replied to.</span></span> <span data-ttu-id="04875-168">新增至轉寄或回復郵件的其他連結不會被重新寫入。</span><span class="sxs-lookup"><span data-stu-id="04875-168">Additional links that are added to the forwarded or replied to message are not rewritten.</span></span>

<span data-ttu-id="04875-169">下列清單說明適用于電子郵件訊息的安全連結原則中的設定：</span><span class="sxs-lookup"><span data-stu-id="04875-169">The settings in Safe Links policies that apply to email messages are described in the following list:</span></span>

- <span data-ttu-id="04875-170">**選取郵件中不明的潛在惡意 URLs 動作**：啟用或停用電子郵件中的安全連結掃描。</span><span class="sxs-lookup"><span data-stu-id="04875-170">**Select the action for unknown potentially malicious URLs in messages**: Enables or disables Safe Links scanning in email messages.</span></span> <span data-ttu-id="04875-171">建議值為 **On**。</span><span class="sxs-lookup"><span data-stu-id="04875-171">The recommended value is **On**.</span></span> <span data-ttu-id="04875-172">開啟此設定會產生下列動作。</span><span class="sxs-lookup"><span data-stu-id="04875-172">Turning on this setting results in the following actions.</span></span>

  - <span data-ttu-id="04875-173">在 Windows (C2R) 的 Outlook 中啟用安全連結掃描。</span><span class="sxs-lookup"><span data-stu-id="04875-173">Safe Links scanning is enabled in Outlook (C2R) on Windows.</span></span>
  - <span data-ttu-id="04875-174">URLs 會在郵件中按一下 [URLs] 中的 [安全連結保護]，以重新寫入。</span><span class="sxs-lookup"><span data-stu-id="04875-174">URLs are rewritten and users are routed through Safe Links protection when they click URLs in messages.</span></span>
  - <span data-ttu-id="04875-175">按一下時，會針對已知的惡意 URLs 清單及「 [封鎖下列 URLs」清單](#block-the-following-urls-list-for-safe-links)，檢查 URLs。</span><span class="sxs-lookup"><span data-stu-id="04875-175">When clicked, URLs are checked against a list of known malicious URLs and the ["Block the following URLs" list](#block-the-following-urls-list-for-safe-links).</span></span>
  - <span data-ttu-id="04875-176">不具備有效信譽的 URLs 會在背景中以非同步方式引爆。</span><span class="sxs-lookup"><span data-stu-id="04875-176">URLs that don't have a valid reputation are detonated asynchronously in the background.</span></span>

- <span data-ttu-id="04875-177">**對指向檔案的可疑連結和連結套用即時 URL 掃描**：可即時掃描連結，包含指向可下載內容的電子郵件訊息中的連結。</span><span class="sxs-lookup"><span data-stu-id="04875-177">**Apply real-time URL scanning for suspicious links and links that point to files**: Enables real-time scanning of links, including links in email messages that point to downloadable content.</span></span> <span data-ttu-id="04875-178">建議的值為 enabled。</span><span class="sxs-lookup"><span data-stu-id="04875-178">The recommended value is enabled.</span></span>

  - <span data-ttu-id="04875-179">**等候 URL 掃描完成之後，才會傳遞郵件**：</span><span class="sxs-lookup"><span data-stu-id="04875-179">**Wait for URL scanning to complete before delivering the message**:</span></span>

    - <span data-ttu-id="04875-180">已啟用：包含 URLs 的郵件會一直保留，直到完成掃描為止。</span><span class="sxs-lookup"><span data-stu-id="04875-180">Enabled: Messages that contain URLs are held until scanning is finished.</span></span> <span data-ttu-id="04875-181">只有在 URLs 確認為安全後，才會傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="04875-181">Messages are delivered only after the URLs are confirmed to be safe.</span></span> <span data-ttu-id="04875-182">此為建議值。</span><span class="sxs-lookup"><span data-stu-id="04875-182">This is the recommended value.</span></span>
    - <span data-ttu-id="04875-183">Disabled：如果無法完成 URL 掃描，請傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="04875-183">Disabled: If URL scanning can't complete, deliver the message anyway.</span></span>

- <span data-ttu-id="04875-184">對**組織內傳送的電子郵件套用安全連結**：啟用或停用安全連結掃描在相同 Exchange Online 組織內的內部寄件者和內部收件者之間傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="04875-184">**Apply Safe Links to email messages sent within the organization**: Enables or disables Safe Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span></span> <span data-ttu-id="04875-185">建議的值為 enabled。</span><span class="sxs-lookup"><span data-stu-id="04875-185">The recommended value is enabled.</span></span>

- <span data-ttu-id="04875-186">**請勿追蹤使用者點擊**：啟用或停用儲存安全連結按一下 [電子郵件訊息] 中的 [URLs 的資料]。</span><span class="sxs-lookup"><span data-stu-id="04875-186">**Do not track user clicks**: Enables or disables storing Safe Links click data for URLs clicked in email messages.</span></span> <span data-ttu-id="04875-187">建議值為將此設定保留未選取狀態 (以追蹤使用者點擊) 。</span><span class="sxs-lookup"><span data-stu-id="04875-187">The recommend value is to leave this setting unselected (to track user clicks).</span></span>

  <span data-ttu-id="04875-188">URL 按一下 [追蹤] 以取得內部寄件者和內部收件者之間所傳送的電子郵件中的連結目前不支援。</span><span class="sxs-lookup"><span data-stu-id="04875-188">URL click tracking for links in email messages sent between internal senders and internal recipients is currently not supported.</span></span>

- <span data-ttu-id="04875-189">**不允許使用者依序按一下原始 url**：允許或封鎖使用者按一下 [ [警告] 頁面](#warning-pages-from-safe-links) 至原始 url。</span><span class="sxs-lookup"><span data-stu-id="04875-189">**Do not allow users to click through to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL.</span></span> <span data-ttu-id="04875-190">建議值已啟用。</span><span class="sxs-lookup"><span data-stu-id="04875-190">The recommend value is enabled.</span></span>

- <span data-ttu-id="04875-191">**請勿重新寫入下列 URLs**：保留 URLs。</span><span class="sxs-lookup"><span data-stu-id="04875-191">**Do not rewrite the following URLs**: Leaves URLs as they are.</span></span> <span data-ttu-id="04875-192">保留不需要掃描之安全 URLs 的自訂清單。</span><span class="sxs-lookup"><span data-stu-id="04875-192">Keeps a custom list of safe URLs that don't need scanning.</span></span> <span data-ttu-id="04875-193">每個安全連結原則的清單都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="04875-193">The list is unique for each Safe Links policy.</span></span> <span data-ttu-id="04875-194">如需 [不要重新 **寫入下列 URLs** ] 清單的詳細資訊，請參閱本文稍後的「 [安全連結原則中的「不要重新寫入下列 URLs」清單](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 」一節。</span><span class="sxs-lookup"><span data-stu-id="04875-194">For more information about the **Do not rewrite the following URLs** list, see the ["Do not rewrite the following URLs" lists in Safe Links policies](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="04875-195">如需安全連結原則之標準和嚴格原則設定的建議值的詳細資訊，請參閱 [安全連結原則設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="04875-195">For more information about the recommended values for Standard and Strict policy settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="04875-196">**收件者篩選器**：您必須指定收件者條件和例外狀況，以決定要套用的原則。</span><span class="sxs-lookup"><span data-stu-id="04875-196">**Recipient filters**: You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="04875-197">您可以使用這些屬性做為條件和例外狀況：</span><span class="sxs-lookup"><span data-stu-id="04875-197">You can use these properties for conditions and exceptions:</span></span>

  - <span data-ttu-id="04875-198">**收件者是**</span><span class="sxs-lookup"><span data-stu-id="04875-198">**The recipient is**</span></span>
  - <span data-ttu-id="04875-199">**收件者網域是**</span><span class="sxs-lookup"><span data-stu-id="04875-199">**The recipient domain is**</span></span>
  - <span data-ttu-id="04875-200">**收件者是以下的成員**</span><span class="sxs-lookup"><span data-stu-id="04875-200">**The recipient is a member of**</span></span>

  <span data-ttu-id="04875-201">您只可以使用條件或例外狀況，但條件或例外狀況可以包含多個值。</span><span class="sxs-lookup"><span data-stu-id="04875-201">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="04875-202">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="04875-202">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="04875-203">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="04875-203">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

- <span data-ttu-id="04875-204">**Priority**：如果您建立多個原則，您可以指定要套用的順序。</span><span class="sxs-lookup"><span data-stu-id="04875-204">**Priority**: If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="04875-205">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="04875-205">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="04875-206">如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="04875-206">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="how-safe-links-works-in-email-messages"></a><span data-ttu-id="04875-207">安全連結在電子郵件訊息中的運作方式</span><span class="sxs-lookup"><span data-stu-id="04875-207">How Safe Links works in email messages</span></span>

<span data-ttu-id="04875-208">在較高的層次，以下是在電子郵件訊息中 URLs 安全連結保護的運作方式：</span><span class="sxs-lookup"><span data-stu-id="04875-208">At a high level, here's how Safe Links protection works on URLs in email messages:</span></span>

1. <span data-ttu-id="04875-209">所有電子郵件都會透過 EOP，網際網路通訊協定 (IP) 和信封篩選器，簽章型惡意程式碼保護，反垃圾郵件和反惡意程式碼篩選，然後將郵件傳遞至收件者的信箱。</span><span class="sxs-lookup"><span data-stu-id="04875-209">All email goes through EOP, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters before the message is delivered to the recipient's mailbox.</span></span>

2. <span data-ttu-id="04875-210">使用者在其信箱中開啟郵件，然後按一下郵件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="04875-210">The user opens the message in their mailbox and clicks on a URL in the message.</span></span>

3. <span data-ttu-id="04875-211">安全連結會在開啟網站之前，立即檢查 URL：</span><span class="sxs-lookup"><span data-stu-id="04875-211">Safe Links immediately checks the URL before opening the website:</span></span>

   - <span data-ttu-id="04875-212">如果此 URL 包含在 [ **封鎖下列 URLs** ] 清單中，則會開啟 [封鎖的 URL 警告](#blocked-url-warning) 。</span><span class="sxs-lookup"><span data-stu-id="04875-212">If the URL is included in the **Block the following URLs** list, a [blocked URL warning](#blocked-url-warning) opens.</span></span>

   - <span data-ttu-id="04875-213">如果 URL 指向已確定為惡意的網站，則會開啟 [惡意的網站警告](#malicious-website-warning) 頁面 (或不同的警告頁面) 。</span><span class="sxs-lookup"><span data-stu-id="04875-213">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="04875-214">如果 URL 指向可供下載的檔案，而且在套用至該使用者的原則中，[套用 **即時 URL 掃描（指向檔** ] 設定已啟用），則會檢查下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="04875-214">If the URL points to a downloadable file, and the **Apply real-time URL scanning for suspicious links and links that point to files** setting is enabled in the policy that applies to the user, the downloadable file is checked.</span></span>

   - <span data-ttu-id="04875-215">如果此 URL 確定為安全，網站會開啟。</span><span class="sxs-lookup"><span data-stu-id="04875-215">If the URL is determined to be safe, the website opens.</span></span>

## <a name="safe-links-settings-for-microsoft-teams"></a><span data-ttu-id="04875-216">Microsoft 小組的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="04875-216">Safe Links settings for Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04875-217">從3月2020，這項功能只是在預覽中，僅供 Microsoft 小組技術採用計畫的成員使用 (點擊) 。</span><span class="sxs-lookup"><span data-stu-id="04875-217">As of March 2020, this feature is in Preview and is available only to members of the Microsoft Teams Technology Adoption Program (TAP).</span></span> <span data-ttu-id="04875-218">如需發行排程的相關資訊，請參閱 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。</span><span class="sxs-lookup"><span data-stu-id="04875-218">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).</span></span>

<span data-ttu-id="04875-219">您可以在安全連結原則中啟用或停用 Microsoft 小組的安全連結保護。</span><span class="sxs-lookup"><span data-stu-id="04875-219">You enable or disable Safe Links protection for Microsoft Teams in Safe Links policies.</span></span> <span data-ttu-id="04875-220">具體說來，您可以在 **Microsoft 小組設定中，針對未知或可能惡意的 URLs** ，使用 [選取] 動作。</span><span class="sxs-lookup"><span data-stu-id="04875-220">Specifically, you use the **Select the action for unknown or potentially malicious URLs within Microsoft Teams** setting.</span></span> <span data-ttu-id="04875-221">建議值為 **On**。</span><span class="sxs-lookup"><span data-stu-id="04875-221">The recommended value is **On**.</span></span>

<span data-ttu-id="04875-222">在 [安全連結原則] 中，套用至電子郵件中連結的下列設定也適用于小組中的連結：</span><span class="sxs-lookup"><span data-stu-id="04875-222">The following settings in Safe Links policies that apply to links in email messages also apply to links in Teams:</span></span>

- <span data-ttu-id="04875-223">**針對可疑的連結和指向檔案的連結套用即時 URL 掃描**</span><span class="sxs-lookup"><span data-stu-id="04875-223">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>
- <span data-ttu-id="04875-224">**不要追蹤使用者點選**</span><span class="sxs-lookup"><span data-stu-id="04875-224">**Do not track user clicks**</span></span>
- <span data-ttu-id="04875-225">**不允許使用者點選原始 URL**</span><span class="sxs-lookup"><span data-stu-id="04875-225">**Do not allow users to click through to original URL**</span></span>

<span data-ttu-id="04875-226">這些設定會在 [ [電子郵件的先前安全連結設定](#safe-links-settings-for-email-messages) ] 區段中說明。</span><span class="sxs-lookup"><span data-stu-id="04875-226">These settings are explained in the previous [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section.</span></span>

<span data-ttu-id="04875-227">在您開啟 Microsoft 小組的安全連結保護之後，當受保護的使用者按一下連結時 (的 [保護]) 時，就會檢查小組中 URLs 的已知惡意連結清單。</span><span class="sxs-lookup"><span data-stu-id="04875-227">After you turn on Safe Links protection for Microsoft Teams, URLs in Teams are checked against a list of known malicious links when the protected user clicks the link (time-of-click protection).</span></span> <span data-ttu-id="04875-228">不會重寫 URLs。</span><span class="sxs-lookup"><span data-stu-id="04875-228">URLs are not rewritten.</span></span> <span data-ttu-id="04875-229">若發現有惡意的連結，使用者將有下列經驗：</span><span class="sxs-lookup"><span data-stu-id="04875-229">If a link is found to be malicious, users will have the following experiences:</span></span>

- <span data-ttu-id="04875-230">如果連結已按一下小組交談中的 [群組聊天] 或 [來自通道]，則 [警告] 頁面會顯示在預設網頁瀏覽器中（如下列螢幕擷取畫面所示）。</span><span class="sxs-lookup"><span data-stu-id="04875-230">If the link was clicked in a Teams conversation, group chat, or from channels, the warning page as shown in the screenshot below will appear in the default web browser.</span></span>
- <span data-ttu-id="04875-231">如果從釘選的索引標籤按一下連結，則 [警告] 頁面會出現在該索引標籤的 [小組] 介面中。出於安全性原因，在網頁瀏覽器中開啟連結的選項已停用。</span><span class="sxs-lookup"><span data-stu-id="04875-231">If the link was clicked from a pinned tab, the warning page will appear in the Teams interface within that tab. The option to open the link in a web browser is disabled for security reasons.</span></span>
- <span data-ttu-id="04875-232">根據已設定原則中 [ **不允許使用者點擊至原始 url** ] 設定的方式，使用者將不允許按一下原始 Url (\*\*繼續 (不建議 \*\* 在螢幕擷取畫面) 中) 。</span><span class="sxs-lookup"><span data-stu-id="04875-232">Depending on how the **Do not allow users to click through to original URL** setting in the policy is configured, the user will or will not be allowed to click through to the original URL (**Continue anyway (not recommended)** in the screenshot).</span></span> <span data-ttu-id="04875-233">建議您啟用 [ **不允許使用者點擊至原始 url** ] 設定，讓使用者無法按一下原始 url。</span><span class="sxs-lookup"><span data-stu-id="04875-233">We recommend that you enable the **Do not allow users to click through to original URL** setting so users can't click through to the original URL.</span></span>

<span data-ttu-id="04875-234">如果已啟用團隊保護的安全連結原則中未包含傳送連結的使用者，則使用者可以隨意按一下其電腦或裝置上的原始 URL。</span><span class="sxs-lookup"><span data-stu-id="04875-234">If the user who sent the link isn't included in a Safe Links policy where Teams protection is enabled, the user is free to click through to the original URL on their computer or device.</span></span>

![「小組的安全連結」頁面報告惡意連結。](../../media/tp-safe-links-for-teams-malicious.png)

<span data-ttu-id="04875-236">在 [警告] 頁面上按一下 [ **上一步** ] 按鈕將會關閉頁面 (，也可能會產生空白頁面，使用者可以關閉) 。</span><span class="sxs-lookup"><span data-stu-id="04875-236">Clicking the **Go Back** button on the warning page will close the page (or might result in a blank page that users can close).</span></span> <span data-ttu-id="04875-237">不過，再次按一下原始連結會導致安全的連結重新掃描 URL，因此會重新顯示 [警告] 頁面。</span><span class="sxs-lookup"><span data-stu-id="04875-237">However, clicking on the original link again will cause Safe Links to rescan the URL, so the warning page will reappear.</span></span>

### <a name="how-safe-links-works-in-teams"></a><span data-ttu-id="04875-238">安全連結在小組中的運作方式</span><span class="sxs-lookup"><span data-stu-id="04875-238">How Safe Links works in Teams</span></span>

<span data-ttu-id="04875-239">在較高的層次，以下是 Microsoft 小組中 URLs 的安全連結保護的運作方式：</span><span class="sxs-lookup"><span data-stu-id="04875-239">At a high level, here's how Safe Links protection works for URLs in Microsoft Teams:</span></span>

1. <span data-ttu-id="04875-240">使用者啟動小組應用程式。</span><span class="sxs-lookup"><span data-stu-id="04875-240">A user starts the Teams app.</span></span>

2. <span data-ttu-id="04875-241">Microsoft 365 會驗證使用者的組織是否包含 Office 365 ATP，以及是否將使用者加入使用中的安全連結原則，以啟用 Microsoft 小組的保護功能。</span><span class="sxs-lookup"><span data-stu-id="04875-241">Microsoft 365 verifies that the user's organization includes Office 365 ATP, and that the user is included in an active Safe Links policy where protection for Microsoft Teams is enabled.</span></span>

3. <span data-ttu-id="04875-242">在聊天、群組聊天、頻道及標籤式中按一下使用者時，會驗證 URLs。</span><span class="sxs-lookup"><span data-stu-id="04875-242">URLs are validated at the time of click for the user in chats, group chats, channels, and tabs.</span></span>

## <a name="safe-links-settings-for-office-365-apps"></a><span data-ttu-id="04875-243">Office 365 應用程式的安全連結設定</span><span class="sxs-lookup"><span data-stu-id="04875-243">Safe Links settings for Office 365 apps</span></span>

<span data-ttu-id="04875-244">適用于 Office 365 應用程式的安全連結保護會檢查 Office 檔中的連結，不會檢查電子郵件中的連結 (但是可以在開啟檔後，檢查電子郵件中附加 Office 檔中的連結) 。</span><span class="sxs-lookup"><span data-stu-id="04875-244">Safe Links protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).</span></span>

<span data-ttu-id="04875-245">適用于 Office 365 應用程式的安全連結保護具有下列用戶端需求：</span><span class="sxs-lookup"><span data-stu-id="04875-245">Safe Links protection for Office 365 apps has the following client requirements:</span></span>

- <span data-ttu-id="04875-246">Microsoft 365 應用程式或 Microsoft 365 商務版 Premium。</span><span class="sxs-lookup"><span data-stu-id="04875-246">Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="04875-247">Windows、Mac 或網頁瀏覽器中目前的 Word、Excel 及 PowerPoint 版本。</span><span class="sxs-lookup"><span data-stu-id="04875-247">Current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a web browser.</span></span>
  - <span data-ttu-id="04875-248">IOS 或 Android 裝置上的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="04875-248">Office apps on iOS or Android devices.</span></span>
  - <span data-ttu-id="04875-249">Windows 上的 Visio。</span><span class="sxs-lookup"><span data-stu-id="04875-249">Visio on Windows.</span></span>
  - <span data-ttu-id="04875-250">在網頁瀏覽器中 OneNote。</span><span class="sxs-lookup"><span data-stu-id="04875-250">OneNote in a web browser.</span></span>

- <span data-ttu-id="04875-251">Office 365 應用程式已設定為使用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="04875-251">Office 365 apps are configured to use modern authentication.</span></span> <span data-ttu-id="04875-252">如需詳細資訊，請參閱 [如何針對 office 2013、office 2016 和 office 2019 用戶端應用程式運作新式驗證](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)。</span><span class="sxs-lookup"><span data-stu-id="04875-252">For more information, see [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span>

- <span data-ttu-id="04875-253">使用者已使用其工作或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="04875-253">Users are signed in using their work or school accounts.</span></span> <span data-ttu-id="04875-254">如需詳細資訊，請參閱登 [入 Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)。</span><span class="sxs-lookup"><span data-stu-id="04875-254">For more information, see [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).</span></span>

<span data-ttu-id="04875-255">您可以在安全連結的全域設定中，設定 Office 365 應用程式的安全連結保護，而不是在安全連結原則中設定。</span><span class="sxs-lookup"><span data-stu-id="04875-255">You configure Safe Links protection for Office 365 apps in the global settings for Safe Links, not in Safe Links policies.</span></span> <span data-ttu-id="04875-256">不過，為了套用安全連結保護，若要套用 Office 365 應用程式，開啟 Office 檔並按一下連結的使用者必須包含在使用中的安全連結原則中。</span><span class="sxs-lookup"><span data-stu-id="04875-256">But, in order for Safe Links protection for Office 365 apps to be applied, the user who opens the Office document and clicks the link must be included in an active Safe Links policy.</span></span>

<span data-ttu-id="04875-257">下列安全連結設定可用於 Office 365 應用程式：</span><span class="sxs-lookup"><span data-stu-id="04875-257">The following Safe Links settings are available for Office 365 apps:</span></span>

- <span data-ttu-id="04875-258">**Office 365 應用程式**：啟用或停用支援的 office 365 應用程式中的安全連結掃描。</span><span class="sxs-lookup"><span data-stu-id="04875-258">**Office 365 applications**: Enables or disables Safe Links scanning in supported Office 365 apps.</span></span> <span data-ttu-id="04875-259">預設值和建議值為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="04875-259">The default and recommended value is **On**.</span></span>

- <span data-ttu-id="04875-260">**不要追蹤使用者按一下 [安全連結**] 的時間：啟用或停用儲存安全連結按一下桌上出版本 Word、Excel、PowerPoint 和 Visio 中 URLs 所按一下的 [資料]。</span><span class="sxs-lookup"><span data-stu-id="04875-260">**Do not track when users click Safe Links**: Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="04875-261">建議的值為 **Off**，這表示會追蹤使用者按一下。</span><span class="sxs-lookup"><span data-stu-id="04875-261">The recommended value is **Off**, which means user clicks are tracked.</span></span>

- <span data-ttu-id="04875-262">**請勿讓使用者點擊 [安全連結至原始 url**]：允許或封鎖使用者在桌上出版本 Word、Excel、PowerPoint 和 Visio 中，按一下 [ [警告] 頁面](#warning-pages-from-safe-links) 中的原始 url。</span><span class="sxs-lookup"><span data-stu-id="04875-262">**Do not let users click through safe links to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL in in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="04875-263">預設值和建議值為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="04875-263">The default and recommended value is **On**.</span></span>

<span data-ttu-id="04875-264">若要設定 Office 365 應用程式的安全連結設定，請參閱 [設定 office 365 應用程式的安全連結保護](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="04875-264">To configure the Safe Links settings for Office 365 apps, see [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).</span></span>

<span data-ttu-id="04875-265">如需標準和嚴格原則設定之建議值的詳細資訊，請參閱 [通用連結的通用設定](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="04875-265">For more information about the recommended values for Standard and Strict policy settings, see [Global settings for Safe Links](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links).</span></span>

### <a name="how-safe-links-works-in-office-365-apps"></a><span data-ttu-id="04875-266">Office 365 應用程式中的安全連結的運作方式</span><span class="sxs-lookup"><span data-stu-id="04875-266">How Safe Links works in Office 365 apps</span></span>

<span data-ttu-id="04875-267">在較高的層次，以下是 Office 365 應用程式中 URLs 安全連結保護的運作方式。</span><span class="sxs-lookup"><span data-stu-id="04875-267">At a high level, here's how Safe Links protection works for URLs in Office 365 apps.</span></span> <span data-ttu-id="04875-268">上一節將說明支援的 Office 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="04875-268">The supported Office 365 apps are described in the previous section.</span></span>

1. <span data-ttu-id="04875-269">使用者在包含 Microsoft 365 應用程式或 Microsoft 365 商務版的組織中，使用他們的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="04875-269">A user signs in using their work or school account in an organization that includes Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>

2. <span data-ttu-id="04875-270">使用者開啟並按一下連結的 Office 檔位於支援的 Office 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="04875-270">The user opens and clicks on a link an Office document in a supported Office app.</span></span>

3. <span data-ttu-id="04875-271">安全連結會在開啟目標網站之前，立即檢查 URL：</span><span class="sxs-lookup"><span data-stu-id="04875-271">Safe Links immediately checks the URL before opening the target website:</span></span>

   - <span data-ttu-id="04875-272">如果此 URL 包含在跳過安全連結的清單中 (**封鎖下列 URLs** 清單) [封鎖的 URL 警告](#blocked-url-warning) ] 頁面隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="04875-272">If the URL is included in the list that skips Safe Links scanning (the **Block the following URLs** list) a [blocked URL warning](#blocked-url-warning) page opens.</span></span>

   - <span data-ttu-id="04875-273">如果 URL 指向已確定為惡意的網站，則會開啟 [惡意的網站警告](#malicious-website-warning) 頁面 (或不同的警告頁面) 。</span><span class="sxs-lookup"><span data-stu-id="04875-273">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="04875-274">如果 URL 指向可供下載的檔案，而且套用至使用者的安全連結原則已設定為可掃描可下載內容的連結 (會 **將即時 URL 掃描套用至可疑連結的連結，並將指向** [檔案]) 的連結，則會檢查下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="04875-274">If the URL points to a downloadable file, and the Safe Links policy that applies to the user is configured to scan links to downloadable content (**Apply real-time URL scanning for suspicious links and links that point to files**), the downloadable file is checked.</span></span>

   - <span data-ttu-id="04875-275">如果此 URL 被視為安全的，使用者會進入網站。</span><span class="sxs-lookup"><span data-stu-id="04875-275">If the URL is considered safe, the user is taken to the website.</span></span>

   - <span data-ttu-id="04875-276">如果安全連結掃描無法完成，則安全連結保護不會觸發。</span><span class="sxs-lookup"><span data-stu-id="04875-276">If Safe Links scanning is unable to complete, Safe Links protection does not trigger.</span></span> <span data-ttu-id="04875-277">在 Office 桌面用戶端中，使用者會先收到警告，再繼續前往目的地網站。</span><span class="sxs-lookup"><span data-stu-id="04875-277">In Office desktop clients, the user will be warned before they proceed to the destination website.</span></span>

> [!NOTE]
> <span data-ttu-id="04875-278">在每個會話開始時，可能需要幾秒鐘的時間，以確認使用者已啟用 Office 的安全連結。</span><span class="sxs-lookup"><span data-stu-id="04875-278">It may take several seconds at the beginning of each session to verify that the user has Safe Links for Office enabled.</span></span>

## <a name="block-the-following-urls-list-for-safe-links"></a><span data-ttu-id="04875-279">安全連結的「封鎖下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="04875-279">"Block the following URLs" list for Safe Links</span></span>

<span data-ttu-id="04875-280">**Block 下列 URLs**清單會定義在下列位置中，以安全連結掃描時，永遠封鎖的連結：</span><span class="sxs-lookup"><span data-stu-id="04875-280">The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:</span></span>

- <span data-ttu-id="04875-281">電子郵件。</span><span class="sxs-lookup"><span data-stu-id="04875-281">Email messages.</span></span>
- <span data-ttu-id="04875-282">Windows 和 Mac 中 Office 365 應用程式中的檔。</span><span class="sxs-lookup"><span data-stu-id="04875-282">Documents in Office 365 apps in Windows and Mac.</span></span>
- <span data-ttu-id="04875-283">Office 中用於 iOS 和 Android 的檔。</span><span class="sxs-lookup"><span data-stu-id="04875-283">Documents in Office for iOS and Android.</span></span>

<span data-ttu-id="04875-284">當使用中安全連結原則中的使用者在支援的應用程式中按一下封鎖的連結時，會移至 [ [封鎖的 URL 警告](#blocked-url-warning) ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="04875-284">When a user in an active Safe Links policy clicks a blocked link in a supported app, they're taken to the [Blocked URL warning](#blocked-url-warning) page.</span></span>

<span data-ttu-id="04875-285">您可以在 [安全連結] 的 [通用設定] 中設定 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="04875-285">You configure the list of URLs in the global settings for Safe Links.</span></span> <span data-ttu-id="04875-286">如需相關指示，請參閱 Configure the the 「 [Block the URLs」清單](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="04875-286">For instructions, see [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).</span></span>

<span data-ttu-id="04875-287">**附註**：</span><span class="sxs-lookup"><span data-stu-id="04875-287">**Notes**:</span></span>

- <span data-ttu-id="04875-288">如需在到處都封鎖 URLs 的真正通用清單，請參閱 [Manage URLs In 承租人 Allow Allow/封鎖清單](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="04875-288">For a truly universal list of URLs that are blocked everywhere, see [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="04875-289">限制：</span><span class="sxs-lookup"><span data-stu-id="04875-289">Limits:</span></span>
  - <span data-ttu-id="04875-290">專案的數目上限為500。</span><span class="sxs-lookup"><span data-stu-id="04875-290">The maximum number of entries is 500.</span></span>
  - <span data-ttu-id="04875-291">專案的長度上限為128個字元。</span><span class="sxs-lookup"><span data-stu-id="04875-291">The maximum length of an entry is 128 characters.</span></span>
  - <span data-ttu-id="04875-292">所有專案都不得超過10000個字元。</span><span class="sxs-lookup"><span data-stu-id="04875-292">All of the entries can't exceed 10,000 characters.</span></span>

- <span data-ttu-id="04875-293">請勿在 URL 的結尾加入正斜線 (`/`) 。</span><span class="sxs-lookup"><span data-stu-id="04875-293">Don't include a forward slash (`/`) at the end of the URL.</span></span> <span data-ttu-id="04875-294">例如，使用 `https://www.contoso.com` ，not `https://www.contoso.com/` 。</span><span class="sxs-lookup"><span data-stu-id="04875-294">For example, use `https://www.contoso.com`, not `https://www.contoso.com/`.</span></span>

- <span data-ttu-id="04875-295">例如，僅限網域的 URL (例如 `contoso.com` 或 `tailspintoys.com`) 會封鎖任何包含網域的 url。</span><span class="sxs-lookup"><span data-stu-id="04875-295">A domain only-URL (for example `contoso.com` or `tailspintoys.com`) will block any URL that contains the domain.</span></span>

- <span data-ttu-id="04875-296">您可以封鎖子域，但不封鎖整個網域。</span><span class="sxs-lookup"><span data-stu-id="04875-296">You can block a subdomain without blocking the full domain.</span></span> <span data-ttu-id="04875-297">例如， `toys.contoso.com*` 封鎖包含子域的任何 URL，但它不會封鎖包含完整網域的 URLs `contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="04875-297">For example, `toys.contoso.com*` blocks any URL that contains the subdomain, but it doesn't block URLs that contain the full domain `contoso.com`.</span></span>

- <span data-ttu-id="04875-298">每個 URL 專案最多可以包含三個萬用字元 (`*`) 。</span><span class="sxs-lookup"><span data-stu-id="04875-298">You can include up to three wildcards (`*`) per URL entry.</span></span>

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a><span data-ttu-id="04875-299">「封鎖下列 URLs 的專案語法」清單</span><span class="sxs-lookup"><span data-stu-id="04875-299">Entry syntax for the "Block the following URLs" list</span></span>

<span data-ttu-id="04875-300">下表說明您可以輸入的值及其結果的範例：</span><span class="sxs-lookup"><span data-stu-id="04875-300">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="04875-301">值</span><span class="sxs-lookup"><span data-stu-id="04875-301">Value</span></span>|<span data-ttu-id="04875-302">結果</span><span class="sxs-lookup"><span data-stu-id="04875-302">Result</span></span>|
|---|---|
|`contoso.com` <br/> <span data-ttu-id="04875-303">或</span><span class="sxs-lookup"><span data-stu-id="04875-303">or</span></span> <br/> `*contoso.com*`|<span data-ttu-id="04875-304">封鎖網域、子域及路徑。</span><span class="sxs-lookup"><span data-stu-id="04875-304">Blocks the domain, subdomains, and paths.</span></span> <span data-ttu-id="04875-305">例如，， `https://www.contoso.com` `https://sub.contoso.com` 及 `https://contoso.com/abc` 會封鎖。</span><span class="sxs-lookup"><span data-stu-id="04875-305">For example, `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc` are blocked.</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="04875-306">封鎖 `https://contoso.com/a` 但不其他類似的子路徑 `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="04875-306">Blocks `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="04875-307">區塊 `https://contoso.com/a` 及其他類似的子路徑 `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="04875-307">Blocks `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="04875-308">`toys`在此範例中封鎖子域 () 但是允許按一下其他網域 URLs (如 `https://contoso.com` 或 `https://home.contoso.com`) 。</span><span class="sxs-lookup"><span data-stu-id="04875-308">Blocks a subdomain (`toys` in this example) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a><span data-ttu-id="04875-309">安全連結原則中的「不要重新寫入下列 URLs」清單</span><span class="sxs-lookup"><span data-stu-id="04875-309">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>

> [!NOTE]
> <span data-ttu-id="04875-310">如果您的組織使用安全連結原則， **請勿重新寫入下列 URLs** 清單是協力廠商網路釣魚測試唯一支援的方法。</span><span class="sxs-lookup"><span data-stu-id="04875-310">If your organization use Safe Links policies, the **Do not rewrite the following URLs** lists are the only supported method for third party phishing tests.</span></span>

<span data-ttu-id="04875-311">每個安全連結原則都包含 **[不要重新寫入下列 URLs** 清單，您可以使用此清單來指定不會以安全連結掃描來重新寫入 URLs。</span><span class="sxs-lookup"><span data-stu-id="04875-311">Each Safe Links policy contains a **Do not rewrite the following URLs** list that you can use to specify URLs that are not rewritten by Safe Links scanning.</span></span> <span data-ttu-id="04875-312">換句話說，此清單允許包含在原則中的使用者存取指定的 URLs，否則會受到安全連結的封鎖。</span><span class="sxs-lookup"><span data-stu-id="04875-312">In other words, the list allows users who are included in the policy to access the specified URLs that would otherwise be blocked by Safe Links.</span></span> <span data-ttu-id="04875-313">您可以在不同的安全連結原則中設定不同的清單。</span><span class="sxs-lookup"><span data-stu-id="04875-313">You can configure different lists in different Safe Links policies.</span></span> <span data-ttu-id="04875-314">原則處理會在第一 (後停止，最高優先順序) 原則會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="04875-314">Policy processing stops after the first (likely, the highest priority) policy is applied to the user.</span></span> <span data-ttu-id="04875-315">因此，只有一個不重新 **寫入下列 URLs** 清單會套用至包含在多個作用中安全連結原則中的使用者。</span><span class="sxs-lookup"><span data-stu-id="04875-315">So, only one **Do not rewrite the following URLs** list is applied to a user who is included in multiple active Safe Links policies.</span></span>

<span data-ttu-id="04875-316">若要將專案新增至新的或現有的安全連結原則中的清單，請參閱 [建立安全連結原則](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) 或 [修改安全連結原則](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="04875-316">To add entries to the list in new or existing Safe Links policies, see [Create Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).</span></span>

<span data-ttu-id="04875-317">**附註**：</span><span class="sxs-lookup"><span data-stu-id="04875-317">**Notes**:</span></span>

- <span data-ttu-id="04875-318">下列用戶端無法辨識安全連結原則中的 [ **不要重新寫入下列 URLs** 清單。</span><span class="sxs-lookup"><span data-stu-id="04875-318">The following clients don't recognize the **Do not rewrite the following URLs** lists in Safe Links policies.</span></span> <span data-ttu-id="04875-319">您可以根據這些用戶端中的安全連結掃描的結果，URLs 封鎖原則中所含的使用者：</span><span class="sxs-lookup"><span data-stu-id="04875-319">Users included in the polices can be blocked from accessing the URLs based on the results of Safe Links scanning in these clients:</span></span>

  - <span data-ttu-id="04875-320">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="04875-320">Microsoft Teams</span></span>
  - <span data-ttu-id="04875-321">Office web apps</span><span class="sxs-lookup"><span data-stu-id="04875-321">Office web apps</span></span>

  <span data-ttu-id="04875-322">如需真實通用的 URLs 允許隨處使用的清單，請參閱 [Manage URLs In 承租人 Allow Allow/封鎖清單](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="04875-322">For a truly universal list of URLs that are allowed everywhere, see [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="04875-323">考慮在清單中新增常用的內部 URLs，以提升使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="04875-323">Consider adding commonly used internal URLs to the list to improve the user experience.</span></span> <span data-ttu-id="04875-324">例如，如果您有內部部署服務（例如商務用 Skype 或 SharePoint），您可以將這些服務新增 URLs 以從掃描中排除。</span><span class="sxs-lookup"><span data-stu-id="04875-324">For example, if you have on-premises services, such as Skype for Business or SharePoint, you can add those URLs to exclude them from scanning.</span></span>

- <span data-ttu-id="04875-325">如果您已有 [安全連結原則] 中 **的 [不要重新寫入下列 URLs** 專案]，請務必查看清單，並視需要新增萬用字元。</span><span class="sxs-lookup"><span data-stu-id="04875-325">If you already have **Do not rewrite the following URLs** entries in your Safe Links policies, be sure to review the lists and add wildcards as required.</span></span> <span data-ttu-id="04875-326">例如，您的清單有類似的專案， `https://contoso.com/a` 而您後來決定包含類似的子路徑 `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="04875-326">For example, your list has an entry like `https://contoso.com/a` and you later decide to include subpaths like `https://contoso.com/a/b`.</span></span> <span data-ttu-id="04875-327">除了新增專案之外，將萬用字元新增至現有專案，使其變成 `https://contoso.com/a/*` 。</span><span class="sxs-lookup"><span data-stu-id="04875-327">Instead of adding a new entry, add a wildcard to the existing entry so it becomes `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="04875-328">每個 URL 專案最多可以包含三個萬用字元 (`*`) 。</span><span class="sxs-lookup"><span data-stu-id="04875-328">You can include up to three wildcards (`*`) per URL entry.</span></span> <span data-ttu-id="04875-329">萬用字元會明確包含首碼或子域。</span><span class="sxs-lookup"><span data-stu-id="04875-329">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="04875-330">例如，該專案與 `contoso.com` 不同的專案不同 `*.contoso.com/*` ，因為 `*.contoso.com/*` 允許人員造訪指定網域中的子域和路徑。</span><span class="sxs-lookup"><span data-stu-id="04875-330">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a><span data-ttu-id="04875-331">[不要重新寫入下列 URLs] 清單的專案語法</span><span class="sxs-lookup"><span data-stu-id="04875-331">Entry syntax for the "Do not rewrite the following URLs" list</span></span>

<span data-ttu-id="04875-332">下表說明您可以輸入的值及其結果的範例：</span><span class="sxs-lookup"><span data-stu-id="04875-332">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="04875-333">值</span><span class="sxs-lookup"><span data-stu-id="04875-333">Value</span></span>|<span data-ttu-id="04875-334">結果</span><span class="sxs-lookup"><span data-stu-id="04875-334">Result</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="04875-335">允許存取， `https://contoso.com` 但非子域或路徑。</span><span class="sxs-lookup"><span data-stu-id="04875-335">Allows access to `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="04875-336">允許存取網域、子域及路徑 (例如，、、 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` 或 `https://www.contoso.com/a`) 。</span><span class="sxs-lookup"><span data-stu-id="04875-336">Allows access to a domain, subdomains, and paths (for example, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`).</span></span> <br/><br/> <span data-ttu-id="04875-337">此專案原本很好 `*contoso.com*` ，因為它不允許可能的詐騙網站，例如 `https://www.falsecontoso.com` 或 `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="04875-337">This entry is inherently better than `*contoso.com*`, because it doesn't allow potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="04875-338">允許存取 `https://contoso.com/a` ，但不允許像這樣的子路徑 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="04875-338">Allows access to `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="04875-339">允許存取 `https://contoso.com/a` 和子路徑，如 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="04875-339">Allows access to `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|

## <a name="warning-pages-from-safe-links"></a><span data-ttu-id="04875-340">安全連結的警告頁面</span><span class="sxs-lookup"><span data-stu-id="04875-340">Warning pages from Safe Links</span></span>

<span data-ttu-id="04875-341">本節包含當您按一下 URL 時，安全連結保護所觸發之各種警告頁面的範例。</span><span class="sxs-lookup"><span data-stu-id="04875-341">This section contains examples of the various warning pages that are triggered by Safe Links protection when you click a URL.</span></span>

<span data-ttu-id="04875-342">請注意，許多警告頁面已更新。</span><span class="sxs-lookup"><span data-stu-id="04875-342">Note that several warning pages have been updated.</span></span> <span data-ttu-id="04875-343">如果您還沒有看到更新的頁面，您會很快。</span><span class="sxs-lookup"><span data-stu-id="04875-343">If you're not already seeing the updated pages, you will soon.</span></span> <span data-ttu-id="04875-344">更新的頁面包含新的色彩配置、更詳細的資訊，以及在有指定的警告和建議下，可繼續前往網站的功能。</span><span class="sxs-lookup"><span data-stu-id="04875-344">The updated pages include a new color scheme, more detail, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="scan-in-progress-notification"></a><span data-ttu-id="04875-345">掃描進行中的通知</span><span class="sxs-lookup"><span data-stu-id="04875-345">Scan in progress notification</span></span>

<span data-ttu-id="04875-346">安全連結正在掃描按一下的 URL。</span><span class="sxs-lookup"><span data-stu-id="04875-346">The clicked URL is being scanned by Safe Links.</span></span> <span data-ttu-id="04875-347">您可能需要稍等片刻，再重新嘗試連結。</span><span class="sxs-lookup"><span data-stu-id="04875-347">You might need to wait a few moments before trying the link again.</span></span>

![「正在掃描連結」通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="04875-349">原始通知頁面如下所示：</span><span class="sxs-lookup"><span data-stu-id="04875-349">The original notification page looked like this:</span></span>

![原始「正在掃描連結」通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a><span data-ttu-id="04875-351">可疑的郵件警告</span><span class="sxs-lookup"><span data-stu-id="04875-351">Suspicious message warning</span></span>

<span data-ttu-id="04875-352">按一下的 URL 位於類似其他可疑郵件的電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="04875-352">The clicked URL was in an email message that's similar to other suspicious messages.</span></span> <span data-ttu-id="04875-353">建議您先檢查電子郵件訊息，再繼續進行網站。</span><span class="sxs-lookup"><span data-stu-id="04875-353">We recommend that you double-check the email message before proceeding to the site.</span></span>

![「從可疑的郵件按一下連結」警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a><span data-ttu-id="04875-355">網路釣魚嘗試警告</span><span class="sxs-lookup"><span data-stu-id="04875-355">Phishing attempt warning</span></span>

<span data-ttu-id="04875-356">按一下的 URL 位於已識別為網路釣魚攻擊的電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="04875-356">The clicked URL was in an email message that has been identified as a phishing attack.</span></span> <span data-ttu-id="04875-357">因此，電子郵件中的所有 URLs 都會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="04875-357">As a result, all URLs in the email message are blocked.</span></span> <span data-ttu-id="04875-358">建議您不要繼續進行網站。</span><span class="sxs-lookup"><span data-stu-id="04875-358">We recommend that you do not proceed to the site.</span></span>

![「從網路釣魚郵件按一下連結」警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a><span data-ttu-id="04875-360">惡意網站警告</span><span class="sxs-lookup"><span data-stu-id="04875-360">Malicious website warning</span></span>

<span data-ttu-id="04875-361">已按一下的 URL 指向已識別為惡意的網站。</span><span class="sxs-lookup"><span data-stu-id="04875-361">The clicked URL points to a site that has been identified as malicious.</span></span> <span data-ttu-id="04875-362">建議您不要繼續進行網站。</span><span class="sxs-lookup"><span data-stu-id="04875-362">We recommend that you do not proceed to the site.</span></span>

![「此網站歸類為惡意」警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="04875-364">原始的 [警告] 頁面如下所示：</span><span class="sxs-lookup"><span data-stu-id="04875-364">The original warning page looked like this:</span></span>

![原始「此網站已歸類為惡意」警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="04875-366">封鎖的 URL 警告</span><span class="sxs-lookup"><span data-stu-id="04875-366">Blocked URL warning</span></span>

<span data-ttu-id="04875-367">您組織中的系統管理員已手動封鎖已按一下的 URL (在 [安全連結) ] 的 [全域設定] 中 **封鎖下列 URLs** 清單。</span><span class="sxs-lookup"><span data-stu-id="04875-367">The clicked URL has been manually blocked by an admin in your organization (the **Block the following URLs** list in the global settings for Safe Links).</span></span> <span data-ttu-id="04875-368">因為安全連結已手動封鎖，所以無法掃描連結。</span><span class="sxs-lookup"><span data-stu-id="04875-368">The link was not scanned by Safe Links because it was manually blocked.</span></span>

<span data-ttu-id="04875-369">管理員手動封鎖特定 URLs 的原因有幾個。</span><span class="sxs-lookup"><span data-stu-id="04875-369">There are several reasons why an admin would manually block specific URLs.</span></span> <span data-ttu-id="04875-370">如果您認為網站不應該封鎖，請與您的系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="04875-370">If you think the site should not be blocked, contact your admin.</span></span>

![「您的系統管理員已封鎖此網站」警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="04875-372">原始的 [警告] 頁面如下所示：</span><span class="sxs-lookup"><span data-stu-id="04875-372">The original warning page looked like this:</span></span>

![原始「根據您組織的 URL 原則，已封鎖此網站」警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a><span data-ttu-id="04875-374">錯誤警告</span><span class="sxs-lookup"><span data-stu-id="04875-374">Error warning</span></span>

<span data-ttu-id="04875-375">發生某種類型的錯誤，無法開啟此 URL。</span><span class="sxs-lookup"><span data-stu-id="04875-375">Some kind of error has occurred, and the URL can't be opened.</span></span>

![「無法載入您嘗試存取的頁面」警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="04875-377">原始的 [警告] 頁面如下所示：</span><span class="sxs-lookup"><span data-stu-id="04875-377">The original warning page looked like this:</span></span>

![原始「無法載入此網頁」網頁」警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
