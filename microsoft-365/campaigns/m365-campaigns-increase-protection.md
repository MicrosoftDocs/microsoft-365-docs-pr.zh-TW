---
title: 加強威脅防護
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: 取得在 Microsoft 365 中提高保護層級的協助
ms.openlocfilehash: 61ac32d3debe391794e85df8c129e5df72887e9e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198372"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a><span data-ttu-id="cb584-103">增強 Microsoft 365 訂閱的威脅防護</span><span class="sxs-lookup"><span data-stu-id="cb584-103">Increase threat protection for Microsoft 365 subscription</span></span>

<span data-ttu-id="cb584-104">本文可協助您提高 Microsoft 365 訂閱中的保護，以防範網路釣魚、惡意程式碼和其他威脅。</span><span class="sxs-lookup"><span data-stu-id="cb584-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="cb584-105">這些建議適用于已增加安全性需求的組織，例如政治活動、法律辦事處和衛生保健診所。</span><span class="sxs-lookup"><span data-stu-id="cb584-105">These recommendations are appropriate for organizations with an increased need for security, like political campaigns, law offices, and health care clinics.</span></span>

<span data-ttu-id="cb584-106">開始之前，請先檢查您的 Microsoft 安全分數。</span><span class="sxs-lookup"><span data-stu-id="cb584-106">Before you begin, check your Microsoft Secure Score.</span></span> <span data-ttu-id="cb584-107">Microsoft 安全分數會根據您的定期活動和安全性設定來分析貴組織的安全性，並指定分數。</span><span class="sxs-lookup"><span data-stu-id="cb584-107">Microsoft Secure Score analyzes your organization's security based on your regular activities and security settings and assigns a score.</span></span> <span data-ttu-id="cb584-108">請先記下您目前的分數。</span><span class="sxs-lookup"><span data-stu-id="cb584-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="cb584-109">採取本文中建議的動作可提升您的分數。</span><span class="sxs-lookup"><span data-stu-id="cb584-109">Taking the actions recommended in this article increases your score.</span></span> <span data-ttu-id="cb584-110">目標不會達到最大分數，但請注意保護您的環境不會對使用者生產力造成不良影響的機會。</span><span class="sxs-lookup"><span data-stu-id="cb584-110">The goal isn't to achieve the max score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span>

<span data-ttu-id="cb584-111">如需詳細資訊，請參閱 [Microsoft 安全分數](../security/defender/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="cb584-111">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="cb584-112">提升郵件中惡意程式碼的保護層級</span><span class="sxs-lookup"><span data-stu-id="cb584-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="cb584-113">您的 Office 365 或 Microsoft 365 環境包括防範惡意程式碼，但是您可以使用常見於惡意程式碼的檔案類型來封鎖附件，以提升這種保護。</span><span class="sxs-lookup"><span data-stu-id="cb584-113">Your Office 365 or Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="cb584-114">若要將惡意程式碼保護放大電子郵件：</span><span class="sxs-lookup"><span data-stu-id="cb584-114">To bump up malware protection in email:</span></span>

1. <span data-ttu-id="cb584-115">移至 <https://protection.office.com> 並以您的系統管理員帳號憑證登入。</span><span class="sxs-lookup"><span data-stu-id="cb584-115">Go to <https://protection.office.com> and sign in with your admin account credentials.</span></span>

2. <span data-ttu-id="cb584-116">在 [安全性 & 規範中心] 的左功能窗格中，選擇 [ **威脅管理**] 底下的 [ **原則**] \> **Anti-Malware**。</span><span class="sxs-lookup"><span data-stu-id="cb584-116">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>

3. <span data-ttu-id="cb584-117">按兩下預設原則，以編輯此全公司原則。</span><span class="sxs-lookup"><span data-stu-id="cb584-117">Double-click the default policy to edit this company-wide policy.</span></span>

4. <span data-ttu-id="cb584-118">按一下 **[設定]**。</span><span class="sxs-lookup"><span data-stu-id="cb584-118">Click **Settings**.</span></span>

5. <span data-ttu-id="cb584-119">在 [ **一般附件類型篩選**] 底下，選取 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-119">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="cb584-120">封鎖的檔案類型會列在此控制項底下的視窗中。</span><span class="sxs-lookup"><span data-stu-id="cb584-120">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="cb584-121">請務必新增下列 filetypes：</span><span class="sxs-lookup"><span data-stu-id="cb584-121">Make sure you add these filetypes:</span></span>

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   <span data-ttu-id="cb584-122">您可以稍後新增或刪除檔案類型（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="cb584-122">You can add or delete file types later, if needed.</span></span>

6. <span data-ttu-id="cb584-123">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="cb584-123">Click **Save.**</span></span>

<span data-ttu-id="cb584-124">如需詳細資訊，請參閱 [EOP 中的反惡意程式碼保護](../security/office-365-security/anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="cb584-124">For more information, see [Anti-malware protection in EOP](../security/office-365-security/anti-malware-protection.md).</span></span>

## <a name="protect-against-ransomware"></a><span data-ttu-id="cb584-125">防範勒索軟體</span><span class="sxs-lookup"><span data-stu-id="cb584-125">Protect against ransomware</span></span>

<span data-ttu-id="cb584-126">勒索軟體會以加密檔案或鎖定電腦畫面限制存取資料。</span><span class="sxs-lookup"><span data-stu-id="cb584-126">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="cb584-127">然後，它會要求「ransom」（通常是以 cryptocurrencies 如 Bitcoin 的形式） extort money，以供 exchange 存取資料。</span><span class="sxs-lookup"><span data-stu-id="cb584-127">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span>

<span data-ttu-id="cb584-128">您可以建立一或多個郵件流程規則來封鎖勒索軟體，以封鎖用於 (勒索軟體的副檔名，以封鎖在郵件步驟) 中所加入的 [惡意程式碼保護層級](#raise-the-level-of-protection-against-malware-in-mail) ，或警告使用者在電子郵件中接收這些附件。</span><span class="sxs-lookup"><span data-stu-id="cb584-128">You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware (these were added in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step), or to warn users who receive these attachments in email.</span></span>

<span data-ttu-id="cb584-129">除了上一個步驟中所封鎖的檔案之外，在開啟包含宏的 Office 檔案附件之前，請先建立規則，以警告使用者。</span><span class="sxs-lookup"><span data-stu-id="cb584-129">In addition to the files that you blocked in the previous step, it's also good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="cb584-130">勒索軟體可以隱藏在宏內，所以警告使用者不要從他們不知道的人開啟這些檔案。</span><span class="sxs-lookup"><span data-stu-id="cb584-130">Ransomware can be hidden inside macros, so warn users to not open these files from people they don't know.</span></span>

<span data-ttu-id="cb584-131">若要建立郵件傳輸規則：</span><span class="sxs-lookup"><span data-stu-id="cb584-131">To create a mail transport rule:</span></span>

1. <span data-ttu-id="cb584-132">移至 [系統管理中心] <https://admin.microsoft.com> ，然後選擇 [系統 **管理中心**] [ \> **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-132">Go to the admin center at <https://admin.microsoft.com> and choose **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="cb584-133">在 [ **郵件流程** ] 類別中，按一下 [ **規則**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-133">In the **mail flow** category, click **rules**.</span></span>

3. <span data-ttu-id="cb584-134">按一下 [] **+** ，然後按一下 [ **建立新規則**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-134">Click **+**, and then click **Create a new rule**.</span></span>

4. <span data-ttu-id="cb584-135">按一下對話方塊底部的 [ **更多選項** ]，以查看完整的選項組。</span><span class="sxs-lookup"><span data-stu-id="cb584-135">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="cb584-136">針對規則套用下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="cb584-136">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="cb584-137">除非您想要變更設定的預設值，否則請保留預設值。</span><span class="sxs-lookup"><span data-stu-id="cb584-137">Leave the rest of the settings at the default, unless you want to change them.</span></span>

6. <span data-ttu-id="cb584-138">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cb584-138">Click **Save**.</span></span>

|<span data-ttu-id="cb584-139">設定</span><span class="sxs-lookup"><span data-stu-id="cb584-139">Setting</span></span>|<span data-ttu-id="cb584-140">開啟 Office 檔案的附件之前警告使用者</span><span class="sxs-lookup"><span data-stu-id="cb584-140">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="cb584-141">名稱</span><span class="sxs-lookup"><span data-stu-id="cb584-141">Name</span></span>|<span data-ttu-id="cb584-142">反內部的勒索軟體規則：警告使用者</span><span class="sxs-lookup"><span data-stu-id="cb584-142">Anti-ransomware rule: warn users</span></span>|
|<span data-ttu-id="cb584-143">將此規則套用至 if。</span><span class="sxs-lookup"><span data-stu-id="cb584-143">Apply this rule if .</span></span> <span data-ttu-id="cb584-144">.</span><span class="sxs-lookup"><span data-stu-id="cb584-144">.</span></span> <span data-ttu-id="cb584-145">.</span><span class="sxs-lookup"><span data-stu-id="cb584-145">.</span></span>|<span data-ttu-id="cb584-146">任何附件。</span><span class="sxs-lookup"><span data-stu-id="cb584-146">Any attachment .</span></span> <span data-ttu-id="cb584-147">.</span><span class="sxs-lookup"><span data-stu-id="cb584-147">.</span></span> <span data-ttu-id="cb584-148">.</span><span class="sxs-lookup"><span data-stu-id="cb584-148">.</span></span> <span data-ttu-id="cb584-149">副檔名符合。</span><span class="sxs-lookup"><span data-stu-id="cb584-149">file extension matches .</span></span> <span data-ttu-id="cb584-150">.</span><span class="sxs-lookup"><span data-stu-id="cb584-150">.</span></span> <span data-ttu-id="cb584-151">.</span><span class="sxs-lookup"><span data-stu-id="cb584-151">.</span></span>|
|<span data-ttu-id="cb584-152">指定字詞或片語</span><span class="sxs-lookup"><span data-stu-id="cb584-152">Specify words or phrases</span></span>|<span data-ttu-id="cb584-153">新增下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="cb584-153">Add these file types:</span></span> <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|<span data-ttu-id="cb584-154">請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="cb584-154">Do the following .</span></span> <span data-ttu-id="cb584-155">.</span><span class="sxs-lookup"><span data-stu-id="cb584-155">.</span></span> <span data-ttu-id="cb584-156">.</span><span class="sxs-lookup"><span data-stu-id="cb584-156">.</span></span>|<span data-ttu-id="cb584-157">以郵件通知收件者</span><span class="sxs-lookup"><span data-stu-id="cb584-157">Notify the recipient with a message</span></span>|
|<span data-ttu-id="cb584-158">提供郵件文字</span><span class="sxs-lookup"><span data-stu-id="cb584-158">Provide message text</span></span>|<span data-ttu-id="cb584-159">請勿從不知道的人開啟這些類型的檔案，因為這些人可能會包含惡意程式碼的宏。</span><span class="sxs-lookup"><span data-stu-id="cb584-159">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>|

<span data-ttu-id="cb584-160">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="cb584-160">For more information, see:</span></span>

- [<span data-ttu-id="cb584-161">勒索軟體：如何降低風險</span><span class="sxs-lookup"><span data-stu-id="cb584-161">Ransomware: how to reduce risk</span></span>](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [<span data-ttu-id="cb584-162">還原您的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="cb584-162">Restore your OneDrive</span></span>](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="cb584-163">停止電子郵件的自動轉寄功能</span><span class="sxs-lookup"><span data-stu-id="cb584-163">Stop auto-forwarding for email</span></span>

<span data-ttu-id="cb584-164">取得使用者信箱存取權的駭客可將信箱設定為自動轉寄電子郵件，以竊取您的郵件。</span><span class="sxs-lookup"><span data-stu-id="cb584-164">Hackers who gain access to a user's mailbox can steal your mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="cb584-165">即使沒有使用者的認知，也可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="cb584-165">This can happen even without the user's awareness.</span></span> <span data-ttu-id="cb584-166">您可以設定郵件流程規則，避免發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="cb584-166">You can prevent this from happening by configuring a mail flow rule.</span></span>

<span data-ttu-id="cb584-167">若要建立郵件傳輸規則，請觀看 [這段簡短的影片](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) ，或遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cb584-167">To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>

1. <span data-ttu-id="cb584-168">在 Microsoft 365 系統管理中心中，按一下 [系統 **管理中心**] [ \> **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-168">In the Microsoft 365 admin center, click **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="cb584-169">在 [ **郵件流程** ] 類別中，按一下 [ **規則**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-169">In the **mail flow** category, click **rules**.</span></span>

3. <span data-ttu-id="cb584-170">按一下 [] **+** ，然後按一下 [ **建立新規則**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-170">Click **+**, and then click **Create a new rule**.</span></span>

4. <span data-ttu-id="cb584-171">按一下對話方塊底部的 [ **更多選項** ]，以查看完整的選項組。</span><span class="sxs-lookup"><span data-stu-id="cb584-171">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="cb584-172">套用下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="cb584-172">Apply the settings in the following table.</span></span> <span data-ttu-id="cb584-173">除非您想要變更設定的預設值，否則請保留預設值。</span><span class="sxs-lookup"><span data-stu-id="cb584-173">Leave the rest of the settings at the default, unless you want to change them.</span></span>

6. <span data-ttu-id="cb584-174">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cb584-174">Click **Save**.</span></span>

|<span data-ttu-id="cb584-175">設定</span><span class="sxs-lookup"><span data-stu-id="cb584-175">Setting</span></span>|<span data-ttu-id="cb584-176">開啟 Office 檔案的附件之前警告使用者</span><span class="sxs-lookup"><span data-stu-id="cb584-176">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="cb584-177">名稱</span><span class="sxs-lookup"><span data-stu-id="cb584-177">Name</span></span>|<span data-ttu-id="cb584-178">禁止將電子郵件自動轉寄轉送至外部網域</span><span class="sxs-lookup"><span data-stu-id="cb584-178">Prevent auto forwarding of email to external domains</span></span>|
|<span data-ttu-id="cb584-179">將此規則套用至 if .。。</span><span class="sxs-lookup"><span data-stu-id="cb584-179">Apply this rule if ...</span></span>|<span data-ttu-id="cb584-180">寄件者。</span><span class="sxs-lookup"><span data-stu-id="cb584-180">The sender .</span></span> <span data-ttu-id="cb584-181">.</span><span class="sxs-lookup"><span data-stu-id="cb584-181">.</span></span> <span data-ttu-id="cb584-182">.</span><span class="sxs-lookup"><span data-stu-id="cb584-182">.</span></span> <span data-ttu-id="cb584-183">為外部/內部。</span><span class="sxs-lookup"><span data-stu-id="cb584-183">is external/internal .</span></span> <span data-ttu-id="cb584-184">.</span><span class="sxs-lookup"><span data-stu-id="cb584-184">.</span></span> <span data-ttu-id="cb584-185">.</span><span class="sxs-lookup"><span data-stu-id="cb584-185">.</span></span> <span data-ttu-id="cb584-186">組織內部</span><span class="sxs-lookup"><span data-stu-id="cb584-186">Inside the organization</span></span>|
|<span data-ttu-id="cb584-187">新增條件</span><span class="sxs-lookup"><span data-stu-id="cb584-187">Add condition</span></span>|<span data-ttu-id="cb584-188">郵件屬性。</span><span class="sxs-lookup"><span data-stu-id="cb584-188">The message properties .</span></span> <span data-ttu-id="cb584-189">.</span><span class="sxs-lookup"><span data-stu-id="cb584-189">.</span></span> <span data-ttu-id="cb584-190">.</span><span class="sxs-lookup"><span data-stu-id="cb584-190">.</span></span> <span data-ttu-id="cb584-191">包含郵件類型。</span><span class="sxs-lookup"><span data-stu-id="cb584-191">include the message type .</span></span> <span data-ttu-id="cb584-192">.</span><span class="sxs-lookup"><span data-stu-id="cb584-192">.</span></span> <span data-ttu-id="cb584-193">.</span><span class="sxs-lookup"><span data-stu-id="cb584-193">.</span></span> <span data-ttu-id="cb584-194">自動轉寄</span><span class="sxs-lookup"><span data-stu-id="cb584-194">Auto-forward</span></span>|
|<span data-ttu-id="cb584-195">請執行下列動作 .。。</span><span class="sxs-lookup"><span data-stu-id="cb584-195">Do the following ...</span></span>|<span data-ttu-id="cb584-196">封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="cb584-196">Block the message .</span></span> <span data-ttu-id="cb584-197">.</span><span class="sxs-lookup"><span data-stu-id="cb584-197">.</span></span> <span data-ttu-id="cb584-198">.</span><span class="sxs-lookup"><span data-stu-id="cb584-198">.</span></span> <span data-ttu-id="cb584-199">拒絕郵件並包含說明。</span><span class="sxs-lookup"><span data-stu-id="cb584-199">reject the message and include an explanation.</span></span>|
|<span data-ttu-id="cb584-200">提供郵件文字</span><span class="sxs-lookup"><span data-stu-id="cb584-200">Provide message text</span></span>|<span data-ttu-id="cb584-201">由於安全性原因，禁止此組織外部的電子郵件的自動轉寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cb584-201">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>|

## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="cb584-202">保護您的電子郵件免受網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="cb584-202">Protect your email from phishing attacks</span></span>

<span data-ttu-id="cb584-203">如果您已為 Office 365 或 Microsoft 365 環境設定一或多個自訂網域，您可以設定目標的反網路釣魚防護。</span><span class="sxs-lookup"><span data-stu-id="cb584-203">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="cb584-204">反網路釣魚防護是 Microsoft Defender for Office 365 的一部分，可協助保護您的組織免受惡意模擬型網路釣魚攻擊和其他網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="cb584-204">Anti-phishing protection, part of Microsoft Defender for Office 365, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="cb584-205">若尚未設定自訂網域，您不需要執行此動作。</span><span class="sxs-lookup"><span data-stu-id="cb584-205">If you haven't configured a custom domain, you don't need to do this.</span></span>

<span data-ttu-id="cb584-206">建議您建立原則來保護您最重要的使用者和自訂網域，以開始使用這項保護。</span><span class="sxs-lookup"><span data-stu-id="cb584-206">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span>

<span data-ttu-id="cb584-207">若要在 Office 365 的 Defender 中建立反網路釣魚原則，請觀看 [這段簡短的訓練影片](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)，或完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cb584-207">To create an anti-phishing policy in Defender for Office 365, watch [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>

1. <span data-ttu-id="cb584-208">移至<https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="cb584-208">Go to <https://protection.office.com>.</span></span>

2. <span data-ttu-id="cb584-209">在 [安全性 & 規範中心] 的左功能窗格中，選擇 [ **威脅管理**] 底下的 [ **原則**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-209">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="cb584-210">在 [ **原則** ] 頁面上，選擇 [ **反網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-210">On the **Policy** page, choose **Anti-phishing**.</span></span>

4. <span data-ttu-id="cb584-211">在 [ **反網路釣魚** ] 頁面上，選取 [ **+ 建立**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-211">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="cb584-212">嚮導會啟動以逐步逐步定義您的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="cb584-212">A wizard launches that steps you through defining your anti-phishing policy.</span></span>

5. <span data-ttu-id="cb584-213">請依照下表中的建議，指定原則的名稱、描述及設定。</span><span class="sxs-lookup"><span data-stu-id="cb584-213">Specify the name, description, and settings for your policy as recommended in the chart below.</span></span> <span data-ttu-id="cb584-214">如需詳細資訊，請參閱 [瞭解 Microsoft Defender For Office 365 選項中的反網路釣魚原則](../security/office-365-security/set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cb584-214">For more information, see [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

6. <span data-ttu-id="cb584-215">檢查您的設定之後，請選擇 [ **建立這個原則** ] 或 [ **儲存**] （如適用）。</span><span class="sxs-lookup"><span data-stu-id="cb584-215">After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="cb584-216">設定或選項</span><span class="sxs-lookup"><span data-stu-id="cb584-216">Setting or option</span></span>|<span data-ttu-id="cb584-217">建議的設定</span><span class="sxs-lookup"><span data-stu-id="cb584-217">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="cb584-218">名稱</span><span class="sxs-lookup"><span data-stu-id="cb584-218">Name</span></span>|<span data-ttu-id="cb584-219">網域和最有價值的人員</span><span class="sxs-lookup"><span data-stu-id="cb584-219">Domain and most valuable staff</span></span>|
|<span data-ttu-id="cb584-220">描述</span><span class="sxs-lookup"><span data-stu-id="cb584-220">Description</span></span>|<span data-ttu-id="cb584-221">確定最重要的人員和我們的網域未進行類比。</span><span class="sxs-lookup"><span data-stu-id="cb584-221">Ensure most important staff and our domain are not being impersonated.</span></span>|
|<span data-ttu-id="cb584-222">新增要保護的使用者</span><span class="sxs-lookup"><span data-stu-id="cb584-222">Add users to protect</span></span>|<span data-ttu-id="cb584-223">選取 **[+ 新增條件]，收件者是**。</span><span class="sxs-lookup"><span data-stu-id="cb584-223">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="cb584-224">輸入使用者名稱，或輸入商務擁有者、合作夥伴或候選人、經理及其他重要員工成員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cb584-224">Type user names or enter the email address of the business owners, partners, or candidate, managers, and other important staff members.</span></span> <span data-ttu-id="cb584-225">您最多可以新增20個要從類比中保護的內部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="cb584-225">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>|
|<span data-ttu-id="cb584-226">新增要保護的網域</span><span class="sxs-lookup"><span data-stu-id="cb584-226">Add domains to protect</span></span>|<span data-ttu-id="cb584-227">選取 **[+ 新增條件]，收件者網域是**。</span><span class="sxs-lookup"><span data-stu-id="cb584-227">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="cb584-228">輸入您的 Microsoft 365 訂閱相關聯的自訂網域（如果您已定義的話）。</span><span class="sxs-lookup"><span data-stu-id="cb584-228">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="cb584-229">您可以輸入一個以上的網域。</span><span class="sxs-lookup"><span data-stu-id="cb584-229">You can enter more than one domain.</span></span>|
|<span data-ttu-id="cb584-230">選擇動作</span><span class="sxs-lookup"><span data-stu-id="cb584-230">Choose actions</span></span>|<span data-ttu-id="cb584-231">如果模仿的使用者傳送電子郵件：選擇 [重新 **導向郵件至其他電子郵件地址**]，然後輸入安全性管理員的電子郵件地址。例如，*劉愛琳 <span> <span> @contoso .com*。</span><span class="sxs-lookup"><span data-stu-id="cb584-231">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <br/> <span data-ttu-id="cb584-232">如果電子郵件來自冒充的網域：請選擇 **[隔離郵件]**。</span><span class="sxs-lookup"><span data-stu-id="cb584-232">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>|
|<span data-ttu-id="cb584-233">信箱情報</span><span class="sxs-lookup"><span data-stu-id="cb584-233">Mailbox intelligence</span></span>|<span data-ttu-id="cb584-234">當您建立新的反網路釣魚原則時，系統會預設選取信箱情報。</span><span class="sxs-lookup"><span data-stu-id="cb584-234">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="cb584-235">請將此設定保留為 **[開啟]**，以獲得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="cb584-235">Leave this setting **On** for best results.</span></span>|
|<span data-ttu-id="cb584-236">新增受信任的寄件者與網域</span><span class="sxs-lookup"><span data-stu-id="cb584-236">Add trusted senders and domains</span></span>|<span data-ttu-id="cb584-237">您可以在這裡新增您自己的網域或任何其他受信任的網域。</span><span class="sxs-lookup"><span data-stu-id="cb584-237">Here you can add your own domain, or any other trusted domains.</span></span>|
|<span data-ttu-id="cb584-238">套用對象</span><span class="sxs-lookup"><span data-stu-id="cb584-238">Applied to</span></span>|<span data-ttu-id="cb584-239">請選取 **[收件者的網域是]**。</span><span class="sxs-lookup"><span data-stu-id="cb584-239">Select **The recipient domain is**.</span></span> <span data-ttu-id="cb584-240">在 **[任一項]** 底下選取 **[選擇]**。</span><span class="sxs-lookup"><span data-stu-id="cb584-240">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="cb584-241">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="cb584-241">Select **+ Add**.</span></span> <span data-ttu-id="cb584-242">選取功能變數名稱（例如 contoso）旁的核取方塊 *。 <span> <span>com*，在清單中，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-242">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="cb584-243">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cb584-243">Select **Done**.</span></span>|

<span data-ttu-id="cb584-244">如需詳細資訊，請參閱 [在 Office 365 的 Defender 中設定反網路釣魚原則](../security/office-365-security/set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cb584-244">For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a><span data-ttu-id="cb584-245">使用適用于 Office 的 Defender，防止惡意附件、檔案及連結的 Office 365</span><span class="sxs-lookup"><span data-stu-id="cb584-245">Protect against malicious attachments, files, and links with Defender for Office 365</span></span>

![指向的橫幅 https://aka.ms/aboutM365preview 。](../media/m365admincenterchanging.png)

<span data-ttu-id="cb584-247">首先，請確定 <https://admin.microsoft.com> 您已開啟新的系統管理中心預覽，請參閱系統管理員中心。</span><span class="sxs-lookup"><span data-stu-id="cb584-247">First, make sure, in the admin center at <https://admin.microsoft.com> that you have the new admin center preview turned on.</span></span> <span data-ttu-id="cb584-248">開啟 **新系統管理中心** 的文字旁的切換功能。</span><span class="sxs-lookup"><span data-stu-id="cb584-248">Turn on the toggle next to the text **The new admin center**.</span></span>

   ![新的系統管理中心預覽。](../media/previewon.png)

<span data-ttu-id="cb584-250">如果您還沒有在租使用者中看到含卡的「 **安裝** 」頁面，請參閱 how To complete Security & 合規性中心的如何完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="cb584-250">If you don't see the **Setup** page with cards in your tenant yet, see how to complete these steps in Security & Compliance Center.</span></span> <span data-ttu-id="cb584-251">請參閱 [在安全性 & 規範中心設定安全附件](#set-up-safe-attachments-in-the-security--compliance-center) ，並在 [安全性 & 規範中心設定安全連結](#set-up-safe-links-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="cb584-251">See [Set up Safe Attachments in the Security & Compliance Center](#set-up-safe-attachments-in-the-security--compliance-center) and [Set up Safe Links in the Security & Compliance Center](#set-up-safe-links-in-the-security--compliance-center).</span></span>

1. <span data-ttu-id="cb584-252">在左側導覽中，選擇 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-252">In the left nav, choose **Setup**.</span></span>
2. <span data-ttu-id="cb584-253">在 [**安裝**] 頁面上，選擇 [**增加來自高級威脅的保護**] 的 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-253">On the **Setup** page, choose **View** on the **Increase protection from advanced threats** card.</span></span>

   ![在 [增加來自高級威脅的保護] 中，選擇 [View on]。](../media/startatp.png)

3. <span data-ttu-id="cb584-255">在 [ **增加來自高級威脅的保護** ] 頁面上，選擇 [ **開始**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-255">On the **Increase protection from advanced threats** page, choose **Get started**.</span></span>
4. <span data-ttu-id="cb584-256">在開啟的窗格上，選取 [電子郵件中的 **連結和附件**] 旁邊的核取方塊、[ **掃描 SharePoint、OneDrive 和團隊** 中的檔案]，然後在 [掃描專案] 下 **掃描 office desktop 和 office Online 應用程式中的連結** ， **以取得惡意內容**。</span><span class="sxs-lookup"><span data-stu-id="cb584-256">On the pane that opens, select the check boxes next to **Links and attachments in email**, **Scan files in SharePoint, OneDrive, and Teams**, and **Scan links in Office desktop and Office Online apps** under **Scan items for malicious content**.</span></span>

   <span data-ttu-id="cb584-257">在 [ **電子郵件中的連結和附件**] 底下，輸入所有使用者或您要掃描其電子郵件的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="cb584-257">Under **Links and attachments in email**, Type in All Users, or the specific users whose email you want scanned.</span></span>

   ![選取 [增加保護以免受高級威脅] 中的所有核取方塊。](../media/setatp.png)

5. <span data-ttu-id="cb584-259">選擇 [ **建立原則** ] 以開啟安全附件和安全連結。</span><span class="sxs-lookup"><span data-stu-id="cb584-259">Choose **Create policies** to turn on Safe Attachments and Safe Links.</span></span>

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a><span data-ttu-id="cb584-260">在安全性 & 規範中心內設定安全附件</span><span class="sxs-lookup"><span data-stu-id="cb584-260">Set up Safe Attachments in the Security & Compliance Center</span></span>

<span data-ttu-id="cb584-261">人們經常傳送、接收及共用附件，例如文件、簡報和試算表等等。</span><span class="sxs-lookup"><span data-stu-id="cb584-261">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="cb584-262">只查看電子郵件訊息，不一定可輕易知道附件是否安全或有危害。</span><span class="sxs-lookup"><span data-stu-id="cb584-262">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="cb584-263">Microsoft Defender for Office 365 包含安全附件保護，但預設不會開啟此保護。</span><span class="sxs-lookup"><span data-stu-id="cb584-263">Microsoft Defender for Office 365 includes Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="cb584-264">建議您建立新的規則，以開始使用這種保護。</span><span class="sxs-lookup"><span data-stu-id="cb584-264">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="cb584-265">這項保護會延伸至 SharePoint、OneDrive 和 Microsoft 小組中的檔案。</span><span class="sxs-lookup"><span data-stu-id="cb584-265">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>

<span data-ttu-id="cb584-266">若要建立安全附件原則，請觀看 [這段簡短的影片](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cb584-266">To create an Safe Attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>

1. <span data-ttu-id="cb584-267">移至 <https://protection.office.com> 並以您的系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="cb584-267">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="cb584-268">在 [安全性 & 規範中心] 的左功能窗格中，選擇 [ **威脅管理**] 底下的 [ **原則**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-268">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="cb584-269">在 [原則] 頁面上，選擇 [ **安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-269">On the Policy page, choose **Safe Attachments**.</span></span>

4. <span data-ttu-id="cb584-270">在 [安全附件] 頁面上，選取 [ **開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP** ] 核取方塊，廣泛套用此保護。</span><span class="sxs-lookup"><span data-stu-id="cb584-270">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span>

5. <span data-ttu-id="cb584-271">選取 **+** 以建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="cb584-271">Select **+** to create a new policy.</span></span>

6. <span data-ttu-id="cb584-272">套用下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="cb584-272">Apply the settings in the following table.</span></span>

7. <span data-ttu-id="cb584-273">檢查您的設定之後，請選擇 [ **建立這個原則** ] 或 [ **儲存**] （如適用）。</span><span class="sxs-lookup"><span data-stu-id="cb584-273">After you review your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="cb584-274">設定或選項</span><span class="sxs-lookup"><span data-stu-id="cb584-274">Setting or option</span></span>|<span data-ttu-id="cb584-275">建議的設定</span><span class="sxs-lookup"><span data-stu-id="cb584-275">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="cb584-276">名稱</span><span class="sxs-lookup"><span data-stu-id="cb584-276">Name</span></span>|<span data-ttu-id="cb584-277">使用偵測到的惡意程式碼封鎖目前和未來的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cb584-277">Block current and future emails with detected malware.</span></span>|
|<span data-ttu-id="cb584-278">描述</span><span class="sxs-lookup"><span data-stu-id="cb584-278">Description</span></span>|<span data-ttu-id="cb584-279">使用偵測到的惡意程式碼封鎖目前和未來的電子郵件和附件。</span><span class="sxs-lookup"><span data-stu-id="cb584-279">Block current and future emails and attachments with detected malware.</span></span>|
|<span data-ttu-id="cb584-280">儲存附件未知的惡意程式碼回應</span><span class="sxs-lookup"><span data-stu-id="cb584-280">Save attachments unknown malware response</span></span>|<span data-ttu-id="cb584-281">Select **Block-封鎖目前和未來的電子郵件和附件偵測到的惡意** 代碼。</span><span class="sxs-lookup"><span data-stu-id="cb584-281">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>|
|<span data-ttu-id="cb584-282">在偵測時重新導向附件</span><span class="sxs-lookup"><span data-stu-id="cb584-282">Redirect attachment on detection</span></span>|<span data-ttu-id="cb584-283">啟用重新導向 (選取此方塊) </span><span class="sxs-lookup"><span data-stu-id="cb584-283">Enable redirection (select this box)</span></span> <br/> <span data-ttu-id="cb584-284">輸入用於隔離的系統管理員帳戶或信箱設定。</span><span class="sxs-lookup"><span data-stu-id="cb584-284">Enter the admin account or a mailbox setup for quarantine.</span></span> <br/> <span data-ttu-id="cb584-285">若惡意程式碼掃描附件超時或發生錯誤，請套用上述選取範圍。 (選取此方塊) 。</span><span class="sxs-lookup"><span data-stu-id="cb584-285">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>|
|<span data-ttu-id="cb584-286">套用對象</span><span class="sxs-lookup"><span data-stu-id="cb584-286">Applied to</span></span>|<span data-ttu-id="cb584-287">收件者網域是。</span><span class="sxs-lookup"><span data-stu-id="cb584-287">The recipient domain is .</span></span> <span data-ttu-id="cb584-288">.</span><span class="sxs-lookup"><span data-stu-id="cb584-288">.</span></span> <span data-ttu-id="cb584-289">.</span><span class="sxs-lookup"><span data-stu-id="cb584-289">.</span></span> <span data-ttu-id="cb584-290">選取您的網域。</span><span class="sxs-lookup"><span data-stu-id="cb584-290">select your domain.</span></span>|

<span data-ttu-id="cb584-291">如需詳細資訊，請參閱 [在 Office 365 的 Defender 中設定反網路釣魚原則](../security/office-365-security/set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cb584-291">For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

### <a name="set-up-safe-links-in-the-security--compliance-center"></a><span data-ttu-id="cb584-292">在安全性 & 規範中心設定安全連結</span><span class="sxs-lookup"><span data-stu-id="cb584-292">Set up Safe Links in the Security & Compliance Center</span></span>

<span data-ttu-id="cb584-293">駭客有時候會在電子郵件或其他檔案的連結中隱藏惡意網站。</span><span class="sxs-lookup"><span data-stu-id="cb584-293">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="cb584-294">「Microsoft Defender for Office 365」中的安全連結可協助您保護組織，其方式是在電子郵件和 Office 檔中的網頁位址 (URLs) 提供點擊驗證。</span><span class="sxs-lookup"><span data-stu-id="cb584-294">Safe Links, part of Microsoft Defender for Office 365, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="cb584-295">保護是透過安全連結原則定義。</span><span class="sxs-lookup"><span data-stu-id="cb584-295">Protection is defined through Safe Links policies.</span></span>

<span data-ttu-id="cb584-296">我們建議您執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="cb584-296">We recommend that you do the following:</span></span>

- <span data-ttu-id="cb584-297">修改預設原則以提升保護。</span><span class="sxs-lookup"><span data-stu-id="cb584-297">Modify the default policy to increase protection.</span></span>

- <span data-ttu-id="cb584-298">新增針對您網域中所有收件者的新原則。</span><span class="sxs-lookup"><span data-stu-id="cb584-298">Add a new policy targeted to all recipients in your domain.</span></span>

<span data-ttu-id="cb584-299">若要設定安全連結，請觀看 [這段簡短的訓練影片](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cb584-299">To set up Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>

1. <span data-ttu-id="cb584-300">移至 <https://protection.office.com> 並以您的系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="cb584-300">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="cb584-301">在 [安全性 & 規範中心] 的左功能窗格中，選擇 [ **威脅管理**] 底下的 [ **原則**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-301">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="cb584-302">在 [原則] 頁面上，選擇 [ **安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-302">On the Policy page, choose **Safe Links**.</span></span>

<span data-ttu-id="cb584-303">若要修改預設原則：</span><span class="sxs-lookup"><span data-stu-id="cb584-303">To modify the default policy:</span></span>

1. <span data-ttu-id="cb584-304">在 [安全連結] 頁面上，于 [套用 **至整個組織的原則**] 底下，選取 **預設** 原則。</span><span class="sxs-lookup"><span data-stu-id="cb584-304">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span>

2. <span data-ttu-id="cb584-305">在 [ **電子郵件除外，套用至內容**] 底下，選取 [適用于 **企業的 Microsoft 365 應用程式、Office iOS 和 Android**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-305">Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.</span></span>

3. <span data-ttu-id="cb584-306">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cb584-306">Click **Save**.</span></span>

<span data-ttu-id="cb584-307">若要建立新的原則針對您網域中的所有收件者：</span><span class="sxs-lookup"><span data-stu-id="cb584-307">To create a new policy targeted to all recipients in your domain:</span></span>

1. <span data-ttu-id="cb584-308">在 [安全連結] 頁面的 [ **適用于整個組織的原則**] 底下，按一下 **+** 以建立新原則。</span><span class="sxs-lookup"><span data-stu-id="cb584-308">On the Safe links page, under **Policies that apply to the entire organization**, click **+** to create a new policy.</span></span>

2. <span data-ttu-id="cb584-309">套用下表所列的設定。</span><span class="sxs-lookup"><span data-stu-id="cb584-309">Apply the settings listed in the following table.</span></span>

3. <span data-ttu-id="cb584-310">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cb584-310">Click **Save**.</span></span>

|<span data-ttu-id="cb584-311">設定或選項</span><span class="sxs-lookup"><span data-stu-id="cb584-311">Setting or option</span></span>|<span data-ttu-id="cb584-312">建議的設定</span><span class="sxs-lookup"><span data-stu-id="cb584-312">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="cb584-313">名稱</span><span class="sxs-lookup"><span data-stu-id="cb584-313">Name</span></span>|<span data-ttu-id="cb584-314">網域中所有收件者的安全連結原則</span><span class="sxs-lookup"><span data-stu-id="cb584-314">Safe links policy for all recipients in the domain</span></span>|
|<span data-ttu-id="cb584-315">選取郵件中未知可能惡意 URLs 的動作</span><span class="sxs-lookup"><span data-stu-id="cb584-315">Select the action for unknown potentially malicious URLs in messages</span></span>|<span data-ttu-id="cb584-316">選取 **[URLs 會在使用者按一下連結時，重新寫入並檢查已知惡意連結的清單**。</span><span class="sxs-lookup"><span data-stu-id="cb584-316">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>|
|<span data-ttu-id="cb584-317">使用安全附件掃描可下載的內容</span><span class="sxs-lookup"><span data-stu-id="cb584-317">Use Safe Attachments to scan downloadable content</span></span>|<span data-ttu-id="cb584-318">選取此方塊。</span><span class="sxs-lookup"><span data-stu-id="cb584-318">Select this box.</span></span>|
|<span data-ttu-id="cb584-319">套用對象</span><span class="sxs-lookup"><span data-stu-id="cb584-319">Applied to</span></span>|<span data-ttu-id="cb584-320">收件者網域是。</span><span class="sxs-lookup"><span data-stu-id="cb584-320">The recipient domain is .</span></span> <span data-ttu-id="cb584-321">.</span><span class="sxs-lookup"><span data-stu-id="cb584-321">.</span></span> <span data-ttu-id="cb584-322">.</span><span class="sxs-lookup"><span data-stu-id="cb584-322">.</span></span> <span data-ttu-id="cb584-323">選取您的網域。</span><span class="sxs-lookup"><span data-stu-id="cb584-323">select your domain.</span></span>|

<span data-ttu-id="cb584-324">如需詳細資訊，請參閱 [Office 365 的 Defender 中的安全連結](../security/office-365-security/safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="cb584-324">For more information, see [Safe Links in Defender for Office 365](../security/office-365-security/safe-links.md).</span></span>

## <a name="turn-on-the-unified-audit-log"></a><span data-ttu-id="cb584-325">開啟整合的審計記錄檔</span><span class="sxs-lookup"><span data-stu-id="cb584-325">Turn on the Unified Audit Log</span></span>

<span data-ttu-id="cb584-326">在安全性 & 規範中心開啟「審核記錄搜尋」之後，您可以保留記錄中的系統管理員和其他使用者活動，並加以搜尋。</span><span class="sxs-lookup"><span data-stu-id="cb584-326">After you turn on the audit log search in the Security & Compliance Center, you can retain the admin and other user activity in the log and search it.</span></span>

<span data-ttu-id="cb584-327">您必須獲指派 Exchange Online 中的「審計記錄」角色，才可在 Microsoft 365 訂閱中開啟或關閉審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="cb584-327">You must be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 subscription.</span></span> <span data-ttu-id="cb584-328">根據預設，此角色會指派給 Exchange 系統管理中心的 [許可權] 頁面上的 [規範管理] 和 [組織管理] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="cb584-328">By default, this role is assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="cb584-329">Microsoft 365 中的全域系統管理員預設為此群組的成員。</span><span class="sxs-lookup"><span data-stu-id="cb584-329">Global admins in Microsoft 365 are members of this group by default.</span></span>

1. <span data-ttu-id="cb584-330">若要開啟 [審核記錄] 搜尋，請移至 [系統管理中心]，然後選擇左側導覽中 [系統管理中心] 底下的 <https://admin.microsoft.com> [**安全性**]。 </span><span class="sxs-lookup"><span data-stu-id="cb584-330">To turn on the audit log search, go to the admin center at <https://admin.microsoft.com> and then choose **Security** under **Admin centers** in the left nav.</span></span>
2. <span data-ttu-id="cb584-331">在 [ **Microsoft 365 安全性**] 頁面上，選擇 [**更多資源**]，然後在 **Office 365 安全性 & 規範中心** 卡上 **開啟**。</span><span class="sxs-lookup"><span data-stu-id="cb584-331">On the **Microsoft 365 Security** page, choose **More resources**, and then **Open** on the **Office 365 Security & Compliance Center** card.</span></span>

    ![在安全性 & 合規性轎車上選擇 [開啟]。](../media/gotosecandcomp.png)
3. <span data-ttu-id="cb584-333">在 [安全性與合規性] 頁面上，選擇 [ **搜尋** ]，然後再 **審核記錄搜尋**。</span><span class="sxs-lookup"><span data-stu-id="cb584-333">On the security and compliance page, choose **Search** and then **Audit log search**.</span></span>
4. <span data-ttu-id="cb584-334">在 [ **審計記錄搜尋** ] 頁面的頂端，選擇 [ **開啟審計**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-334">On the top of the **Audit log search** page, choose **Turn on auditing**.</span></span>

<span data-ttu-id="cb584-335">開啟功能後，您可以搜尋檔案、資料夾及許多活動。</span><span class="sxs-lookup"><span data-stu-id="cb584-335">After the feature is turned on, you can search for files, folders, and many activities.</span></span> <span data-ttu-id="cb584-336">如需詳細資訊，請參閱 [搜尋審核記錄](../compliance/search-the-audit-log-in-security-and-compliance.md)檔。</span><span class="sxs-lookup"><span data-stu-id="cb584-336">For more information, see [search the audit log](../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a><span data-ttu-id="cb584-337">調整 SharePoint 和 OneDrive 檔案及資料夾的匿名共用設定</span><span class="sxs-lookup"><span data-stu-id="cb584-337">Tune-up anonymous sharing settings for SharePoint and OneDrive files and folders</span></span>

<span data-ttu-id="cb584-338"> (將預設匿名連結到期變更為14天，請將預設共用類型變更為「特定人員」 ) 以變更 OneDrive 和 SharePoint 的共用設定：</span><span class="sxs-lookup"><span data-stu-id="cb584-338">(change default anonymous link expiration to 14 days, change default sharing type to "Specific People") To change the sharing settings for OneDrive and SharePoint:</span></span>

1. <span data-ttu-id="cb584-339">移至 [系統管理中心] <https://admin.microsoft.com> ，然後選擇左側導覽中的 [系統 **管理中心**] 底下的 [ **SharePoint** ]。</span><span class="sxs-lookup"><span data-stu-id="cb584-339">Go to the admin center at <https://admin.microsoft.com> and then choose **SharePoint** under **Admin centers** in the left nav.</span></span>
2. <span data-ttu-id="cb584-340">在 SharePoint 系統管理中心，移至 [ **原則**] [ \> **共用**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-340">In the SharePoint admin center, go to **Policies** \> **Sharing**.</span></span>
3. <span data-ttu-id="cb584-341">在 [ **共用** ] 頁面的 [檔案 **和資料夾連結**] 底下，選取 [ **特定人員**]，然後在 **[任何人] 連結的 [高級設定**] 底下，選取 [ **這些連結必須在這段天數內到期**]，然後輸入 14 (或您想要將連結存留時間限制為) 的其他天數。</span><span class="sxs-lookup"><span data-stu-id="cb584-341">On the **Sharing** page, under **File and folder links**, select **Specific people**, and under **Advanced settings for "Anyone" links**, select **These links must expire within this many days**, and type in 14 (or another number of days you want to restrict the link lifetime to).</span></span>

   ![選擇 [特定人員]，並將連結到期設定為14天。](../media/anyonelinks.png)

## <a name="activity-alerts"></a><span data-ttu-id="cb584-343">活動警示</span><span class="sxs-lookup"><span data-stu-id="cb584-343">Activity alerts</span></span>

<span data-ttu-id="cb584-344">您可以使用活動警示來追蹤系統管理員和使用者活動，並偵測組織中的惡意程式碼和資料遺失防護事件。</span><span class="sxs-lookup"><span data-stu-id="cb584-344">You can use activity alerts to track admin and user activities and detect malware and data loss prevention incidents in your organization.</span></span> <span data-ttu-id="cb584-345">您的訂閱包含一組預設原則，但您也可以建立自訂的原則。</span><span class="sxs-lookup"><span data-stu-id="cb584-345">Your subscription includes a set of default policies, but you can also create custom ones.</span></span> <span data-ttu-id="cb584-346">如需詳細資訊，請參閱 [警示原則](../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cb584-346">For more information, see [alert policies](../compliance/alert-policies.md).</span></span> <span data-ttu-id="cb584-347">例如，如果您在 SharePoint 中儲存重要檔案，而您不想讓任何人在外部共用，您可以建立通知，以在使用者共用郵件時提醒您。</span><span class="sxs-lookup"><span data-stu-id="cb584-347">For example, if you store an important file in SharePoint that you don't want anyone to share externally, you can create a notification that alerts you if someone does share it.</span></span>

<span data-ttu-id="cb584-348">下圖顯示 Microsoft 365 隨附的預設原則。</span><span class="sxs-lookup"><span data-stu-id="cb584-348">The following figure shows the default policies that are included with Microsoft 365.</span></span>

![Microsoft 365 隨附的預設警示原則](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a><span data-ttu-id="cb584-350">停用或管理行事曆共用</span><span class="sxs-lookup"><span data-stu-id="cb584-350">Disable or manage calendar sharing</span></span>

<span data-ttu-id="cb584-351">您可以防止組織中的人員共用他們的行事曆，也可以管理他們可以共用的內容。</span><span class="sxs-lookup"><span data-stu-id="cb584-351">You can prevent people in your organization from sharing their calendars, or you can also manage what they can share.</span></span> <span data-ttu-id="cb584-352">例如，您可以將共用限制為僅限共用空閒/忙碌的時間。</span><span class="sxs-lookup"><span data-stu-id="cb584-352">For example, you can restrict the sharing to free/busy times only.</span></span>

1. <span data-ttu-id="cb584-353">移至 [系統管理中心] <https://admin.microsoft.com> ，然後選擇 [ **設定** \> **組織設定**]。</span><span class="sxs-lookup"><span data-stu-id="cb584-353">Go to the admin center at <https://admin.microsoft.com> and choose **Settings** \> **Org Settings**.</span></span>
2. <span data-ttu-id="cb584-354">在 [ **服務** ] 頁面上，選擇 [行事 **曆**]，然後選擇您組織中的人員是否可以與擁有 Office 365 或 Exchange 的外部人員或任何人共用其行事曆。</span><span class="sxs-lookup"><span data-stu-id="cb584-354">On the **Services** page, choose **Calendar**, and choose whether people in your organization can share their calendars with people outside who have Office 365 or Exchange, or with anyone.</span></span>

   <span data-ttu-id="cb584-355">如果您選擇 [與任何人共用] 選項，您可以決定只共用空閒/忙碌資訊。</span><span class="sxs-lookup"><span data-stu-id="cb584-355">If you choose the share with anyone option, you can decide to also only share free/busy information.</span></span>

3. <span data-ttu-id="cb584-356">選擇頁面底部的 [ **儲存變更** ]。</span><span class="sxs-lookup"><span data-stu-id="cb584-356">Choose **Save changes** on the bottom of the page.</span></span>

   <span data-ttu-id="cb584-357">下圖顯示不允許使用行事曆共用。</span><span class="sxs-lookup"><span data-stu-id="cb584-357">The following figure shows calendar sharing not allowed.</span></span>

   ![如不允許，顯示外部行事曆共用的螢幕擷取畫面。](../media/nocalendarsharing.png)

   <span data-ttu-id="cb584-359">下圖顯示只允許具有空閒/忙碌資訊之電子郵件連結的行事曆共用的設定。</span><span class="sxs-lookup"><span data-stu-id="cb584-359">The following figure shows the settings when calendar sharing is allowed with an email link with only free/busy information.</span></span>

   ![與任何人共用行事曆空閒/忙碌的螢幕擷取畫面。](../media/sharefreebusy.png)

<span data-ttu-id="cb584-361">如果允許使用者共用其行事曆，請參閱如何從網頁上的 Outlook 共用的 [相關指示](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) 。</span><span class="sxs-lookup"><span data-stu-id="cb584-361">If your users are allowed to share their calendars, see [these instructions](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for how to share from Outlook on the web.</span></span>
