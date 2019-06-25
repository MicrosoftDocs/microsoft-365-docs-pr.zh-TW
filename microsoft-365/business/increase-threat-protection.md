---
title: 加強 Microsoft 365 商務的威脅防護
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 設定 Office 365 高級威脅防護, 並保護機密資料。
ms.openlocfilehash: b6e9941eee9de4f295b0f8056c1c91b7076e530c
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668380"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="4538c-103">增加威脅防護</span><span class="sxs-lookup"><span data-stu-id="4538c-103">Increase threat protection</span></span>

<span data-ttu-id="4538c-104">本文可協助您加強 Microsoft 365 訂閱中的保護, 以防範網路釣魚、惡意程式碼和其他威脅。</span><span class="sxs-lookup"><span data-stu-id="4538c-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="4538c-105">這些建議適用于對安全性有較高需求的組織, 例如法律辦公室和健康護理診所。</span><span class="sxs-lookup"><span data-stu-id="4538c-105">These recommendations are appropriate for organizations with an increased need for security, like law offices, and health care clinics.</span></span>

<span data-ttu-id="4538c-106">在您開始之前, 請先檢查您的 Office 365 安全分數。</span><span class="sxs-lookup"><span data-stu-id="4538c-106">Before you begin, check your Office 365 Secure Score.</span></span> <span data-ttu-id="4538c-107">Office 365 安全分數會根據您的一般活動和安全性設定來分析您的 Office 365 組織安全性, 並會指定分數。</span><span class="sxs-lookup"><span data-stu-id="4538c-107">Office 365 Secure Score analyzes your Office 365 organization's security based on your regular activities and security settings and assigns a score.</span></span> <span data-ttu-id="4538c-108">請記下您目前的分數。</span><span class="sxs-lookup"><span data-stu-id="4538c-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="4538c-109">採取本文中建議的動作可提高您的分數。</span><span class="sxs-lookup"><span data-stu-id="4538c-109">Taking the actions recommended in this article increases your score.</span></span> <span data-ttu-id="4538c-110">目標不會達到最大分數, 但請注意, 保護您的環境不會對使用者的生產力造成不良影響的機會。</span><span class="sxs-lookup"><span data-stu-id="4538c-110">The goal is not to achieve the max score, but to be aware of opportunities to protect your environment that do not negatively affect productivity for your users.</span></span> 

<span data-ttu-id="4538c-111">如需詳細資訊, 請參閱[Microsoft 安全分數](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score)。</span><span class="sxs-lookup"><span data-stu-id="4538c-111">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="4538c-112">提升郵件中惡意程式碼的保護層級</span><span class="sxs-lookup"><span data-stu-id="4538c-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="4538c-113">您的 Office 365 或 Microsoft 365 環境包含對惡意程式碼的防護, 但是您可以使用常用於惡意程式碼的檔案類型來封鎖附件, 以增加這種保護。</span><span class="sxs-lookup"><span data-stu-id="4538c-113">Your Office 365 or Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="4538c-114">若要以電子郵件加強惡意程式碼保護:</span><span class="sxs-lookup"><span data-stu-id="4538c-114">To increase malware protection in email:</span></span>
  
1. <span data-ttu-id="4538c-115">移至[https://protection.office.com](https://protection.office.com)並以您的系統管理員帳號憑證登入。</span><span class="sxs-lookup"><span data-stu-id="4538c-115">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.</span></span> 
    
2. <span data-ttu-id="4538c-116">在 [Office 365 安全性&amp;規範中心] 的左功能窗格中, 選擇 [**威脅管理**] 下的 [**原則** \> **反惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="4538c-116">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>
    
3. <span data-ttu-id="4538c-117">按兩下預設原則, 以編輯此全公司原則。</span><span class="sxs-lookup"><span data-stu-id="4538c-117">Double-click the default policy to edit this company-wide policy.</span></span>
    
4. <span data-ttu-id="4538c-118">按一下 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-118">Click **Settings**.</span></span>
    
5. <span data-ttu-id="4538c-119">在 [**常用附件類型篩選**] 底下, 選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-119">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="4538c-120">封鎖的檔案類型會列在此控制項下方的視窗中。</span><span class="sxs-lookup"><span data-stu-id="4538c-120">The file types that are blocked are listed in the window directly below this control.</span></span>  <span data-ttu-id="4538c-121">請確定您新增這些 filetypes:</span><span class="sxs-lookup"><span data-stu-id="4538c-121">Make sure you add these filetypes:</span></span>
   - <span data-ttu-id="4538c-122">ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、.hlp、ht、hta、inf、jse、mdz、.pcd、、cmd、、、、、、、、、、、</span><span class="sxs-lookup"><span data-stu-id="4538c-122">ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif</span></span>  <br/> <span data-ttu-id="4538c-123">如有需要, 您可以稍後新增或刪除檔案類型。</span><span class="sxs-lookup"><span data-stu-id="4538c-123">You can add or delete file types later, if needed.</span></span>
    
6. <span data-ttu-id="4538c-124">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4538c-124">Click **Save.**</span></span>
    
<span data-ttu-id="4538c-125">如需詳細資訊, 請參閱[反惡意程式碼保護](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="4538c-125">For more information, see [Anti-malware protection](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).</span></span>
  
## <a name="protect-against-ransomware"></a><span data-ttu-id="4538c-126">防止勒索軟體</span><span class="sxs-lookup"><span data-stu-id="4538c-126">Protect against ransomware</span></span>

<span data-ttu-id="4538c-127">勒索軟體會透過加密檔案或鎖定電腦螢幕, 來限制資料存取權。</span><span class="sxs-lookup"><span data-stu-id="4538c-127">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="4538c-128">然後, 它會要求「ransom」 (通常是 Bitcoin 的 cryptocurrencies 形式) 來 extort 金錢, 並在 exchange 中存取資料。</span><span class="sxs-lookup"><span data-stu-id="4538c-128">It then attempts to extort money from victims by asking for "ransom," usually in form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span> 
  
<span data-ttu-id="4538c-129">您可以透過建立一或多個郵件流程規則來封鎖勒索軟體 (這些副檔名會在 [在[郵件中提高惡意程式碼的防護等級](#raise-the-level-of-protection-against-malware-in-mail)] 步驟中新增), 或警告使用者收到這些郵件, 以防止勒索代碼電子郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="4538c-129">You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware (these were added in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step), or to warn users who receive these attachments in email.</span></span>

<span data-ttu-id="4538c-130">除了您在上一個步驟中封鎖的檔案之外, 也建議您先建立規則, 以在開啟包含宏的 Office 檔案附件之前警告使用者。</span><span class="sxs-lookup"><span data-stu-id="4538c-130">In addition to the files that you blocked in the previous step, it is also good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="4538c-131">您可以在宏內隱藏勒索軟體, 因此我們會警告使用者不要從他們不知道的人開啟這些檔案。</span><span class="sxs-lookup"><span data-stu-id="4538c-131">Ransomware can be hidden inside macros, so we'll warn users to not open these files from people they do not know.</span></span>

<span data-ttu-id="4538c-132">若要建立郵件傳輸規則:</span><span class="sxs-lookup"><span data-stu-id="4538c-132">To create a mail transport rule:</span></span>
  
1. <span data-ttu-id="4538c-133">移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>管理中心, 然後選擇 [系統**管理中心** \> ] [ **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-133">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="4538c-134">在 [**郵件流程**] 類別中, 按一下 [**規則**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-134">In the **mail flow** category, click **rules**.</span></span>
    
3. <span data-ttu-id="4538c-135">按一下**+**[], 然後按一下 [**建立新規則**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-135">Click **+**, and then click **Create a new rule**.</span></span>
    
4. <span data-ttu-id="4538c-136">按一下對話方塊底部的 [**更多選項**], 以查看完整的選項群組。</span><span class="sxs-lookup"><span data-stu-id="4538c-136">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span> 
    
5. <span data-ttu-id="4538c-137">在下表中套用規則的設定。</span><span class="sxs-lookup"><span data-stu-id="4538c-137">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="4538c-138">除非您想要變更這些設定, 否則預設保留其預設值。</span><span class="sxs-lookup"><span data-stu-id="4538c-138">Leave the rest of the settings at the default, unless you want to change these.</span></span>
    
6. <span data-ttu-id="4538c-139">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4538c-139">Click **Save**.</span></span>
    
|<span data-ttu-id="4538c-140">**設定**</span><span class="sxs-lookup"><span data-stu-id="4538c-140">**Setting**</span></span>|<span data-ttu-id="4538c-141">**開啟 Office 檔案的附件之前警告使用者**</span><span class="sxs-lookup"><span data-stu-id="4538c-141">**Warn users before opening attachments of Office files**</span></span>||
|:-----|:-----|:-----|
|<span data-ttu-id="4538c-142">名稱</span><span class="sxs-lookup"><span data-stu-id="4538c-142">Name</span></span>  <br/> |<span data-ttu-id="4538c-143">反惡意軟體規則: 警告使用者</span><span class="sxs-lookup"><span data-stu-id="4538c-143">Anti-ransomware rule: warn users</span></span>  <br/>  |
|<span data-ttu-id="4538c-144">若要套用此規則。</span><span class="sxs-lookup"><span data-stu-id="4538c-144">Apply this rule if .</span></span> <span data-ttu-id="4538c-145">.</span><span class="sxs-lookup"><span data-stu-id="4538c-145"></span></span> <span data-ttu-id="4538c-146">.</span><span class="sxs-lookup"><span data-stu-id="4538c-146"></span></span>  <br/> |<span data-ttu-id="4538c-147">任何附件。</span><span class="sxs-lookup"><span data-stu-id="4538c-147">Any attachment .</span></span> <span data-ttu-id="4538c-148">.</span><span class="sxs-lookup"><span data-stu-id="4538c-148"></span></span> <span data-ttu-id="4538c-149">.</span><span class="sxs-lookup"><span data-stu-id="4538c-149"></span></span> <span data-ttu-id="4538c-150">副檔名相符。</span><span class="sxs-lookup"><span data-stu-id="4538c-150">file extension matches .</span></span> <span data-ttu-id="4538c-151">.</span><span class="sxs-lookup"><span data-stu-id="4538c-151"></span></span> <span data-ttu-id="4538c-152">.</span><span class="sxs-lookup"><span data-stu-id="4538c-152"></span></span>  <br/> |
|<span data-ttu-id="4538c-153">指定字詞或片語</span><span class="sxs-lookup"><span data-stu-id="4538c-153">Specify words or phrases</span></span>  <br/> |<span data-ttu-id="4538c-154">新增下列檔案類型:</span><span class="sxs-lookup"><span data-stu-id="4538c-154">Add these file types:</span></span>  <br/> <span data-ttu-id="4538c-155">normal.dotm、.docm、xlsm、sltm、xla、xlam、xll、pptm、potm、ppam、ppsm、sldm</span><span class="sxs-lookup"><span data-stu-id="4538c-155">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>  <br/>|
|<span data-ttu-id="4538c-156">請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="4538c-156">Do the following .</span></span> <span data-ttu-id="4538c-157">.</span><span class="sxs-lookup"><span data-stu-id="4538c-157"></span></span> <span data-ttu-id="4538c-158">.</span><span class="sxs-lookup"><span data-stu-id="4538c-158"></span></span>  <br/> |<span data-ttu-id="4538c-159">以郵件通知收件者</span><span class="sxs-lookup"><span data-stu-id="4538c-159">Notify the recipient with a message</span></span>  <br/> |
|<span data-ttu-id="4538c-160">提供訊息文字</span><span class="sxs-lookup"><span data-stu-id="4538c-160">Provide message text</span></span>  <br/> |<span data-ttu-id="4538c-161">請勿從您不知道的人員那裡開啟這類檔案, 因為它們可能含有惡意程式碼的宏。</span><span class="sxs-lookup"><span data-stu-id="4538c-161">Do not open these type of files from people you do not know because they might contain macros with malicious code.</span></span>  <br/> |
   
<span data-ttu-id="4538c-162">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="4538c-162">For more information, see:</span></span>
  
- [<span data-ttu-id="4538c-163">如何處理勒索軟體</span><span class="sxs-lookup"><span data-stu-id="4538c-163">How to deal with ransomware</span></span>](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [<span data-ttu-id="4538c-164">還原您的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="4538c-164">Restore your OneDrive</span></span>](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="4538c-165">停止電子郵件的自動轉寄功能</span><span class="sxs-lookup"><span data-stu-id="4538c-165">Stop auto-forwarding for email</span></span>

<span data-ttu-id="4538c-166">取得使用者信箱存取權的駭客可以透過將信箱設為自動轉寄電子郵件, 來竊取您的郵件。</span><span class="sxs-lookup"><span data-stu-id="4538c-166">Hackers who gain access to a user's mailbox can steal your mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="4538c-167">即使沒有使用者的認知, 也可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="4538c-167">This can happen even without the user's awareness.</span></span> <span data-ttu-id="4538c-168">您可以設定郵件流程規則, 避免發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="4538c-168">You can prevent this from happening by configuring a mail flow rule.</span></span> 
  
<span data-ttu-id="4538c-169">若要建立郵件傳輸規則, 請觀看[這段簡短的影片](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7), 或遵循下列步驟:</span><span class="sxs-lookup"><span data-stu-id="4538c-169">To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>
  
1. <span data-ttu-id="4538c-170">在 Microsoft 365 系統管理中心, 按一下 [系統**管理中心** \> ] [ **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-170">In the Microsoft 365 admin center, click **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="4538c-171">在 [**郵件流程**] 類別中, 按一下 [**規則**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-171">In the **mail flow** category, click **rules**.</span></span>
    
3. <span data-ttu-id="4538c-172">按一下**+**[], 然後按一下 [**建立新規則**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-172">Click **+**, and then click **Create a new rule**.</span></span>
    
4. <span data-ttu-id="4538c-173">按一下對話方塊底部的 [**更多選項**], 以查看完整的選項群組。</span><span class="sxs-lookup"><span data-stu-id="4538c-173">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span> 
    
5. <span data-ttu-id="4538c-174">套用下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="4538c-174">Apply the settings in the following table.</span></span> <span data-ttu-id="4538c-175">除非您想要變更這些設定, 否則預設保留其預設值。</span><span class="sxs-lookup"><span data-stu-id="4538c-175">Leave the rest of the settings at the default, unless you want to change these.</span></span>
    
6. <span data-ttu-id="4538c-176">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4538c-176">Click **Save**.</span></span>
    
|<span data-ttu-id="4538c-177">**設定**</span><span class="sxs-lookup"><span data-stu-id="4538c-177">**Setting**</span></span>|<span data-ttu-id="4538c-178">**開啟 Office 檔案的附件之前警告使用者**</span><span class="sxs-lookup"><span data-stu-id="4538c-178">**Warn users before opening attachments of Office files**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4538c-179">名稱</span><span class="sxs-lookup"><span data-stu-id="4538c-179">Name</span></span>  <br/> |<span data-ttu-id="4538c-180">防止自動將電子郵件轉寄至外部網域</span><span class="sxs-lookup"><span data-stu-id="4538c-180">Prevent auto forwarding of email to external domains</span></span>  <br/> |
|<span data-ttu-id="4538c-181">將此規則套用至 .。。</span><span class="sxs-lookup"><span data-stu-id="4538c-181">Apply this rule if ...</span></span>  <br/> |<span data-ttu-id="4538c-182">寄件者。</span><span class="sxs-lookup"><span data-stu-id="4538c-182">The sender .</span></span> <span data-ttu-id="4538c-183">.</span><span class="sxs-lookup"><span data-stu-id="4538c-183"></span></span> <span data-ttu-id="4538c-184">.</span><span class="sxs-lookup"><span data-stu-id="4538c-184"></span></span> <span data-ttu-id="4538c-185">為 external/internal。</span><span class="sxs-lookup"><span data-stu-id="4538c-185">is external/internal .</span></span> <span data-ttu-id="4538c-186">.</span><span class="sxs-lookup"><span data-stu-id="4538c-186"></span></span> <span data-ttu-id="4538c-187">.</span><span class="sxs-lookup"><span data-stu-id="4538c-187"></span></span> <span data-ttu-id="4538c-188">組織內部</span><span class="sxs-lookup"><span data-stu-id="4538c-188">Inside the organization</span></span>  <br/> |
|<span data-ttu-id="4538c-189">新增條件</span><span class="sxs-lookup"><span data-stu-id="4538c-189">Add condition</span></span>  <br/> |<span data-ttu-id="4538c-190">郵件屬性。</span><span class="sxs-lookup"><span data-stu-id="4538c-190">The message properties .</span></span> <span data-ttu-id="4538c-191">.</span><span class="sxs-lookup"><span data-stu-id="4538c-191"></span></span> <span data-ttu-id="4538c-192">.</span><span class="sxs-lookup"><span data-stu-id="4538c-192"></span></span> <span data-ttu-id="4538c-193">包含郵件類型。</span><span class="sxs-lookup"><span data-stu-id="4538c-193">include the message type .</span></span> <span data-ttu-id="4538c-194">.</span><span class="sxs-lookup"><span data-stu-id="4538c-194"></span></span> <span data-ttu-id="4538c-195">.</span><span class="sxs-lookup"><span data-stu-id="4538c-195"></span></span> <span data-ttu-id="4538c-196">自動轉寄</span><span class="sxs-lookup"><span data-stu-id="4538c-196">Auto-forward</span></span>  <br/> |
|<span data-ttu-id="4538c-197">請執行下列動作 .。。</span><span class="sxs-lookup"><span data-stu-id="4538c-197">Do the following ...</span></span>  <br/> |<span data-ttu-id="4538c-198">封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="4538c-198">Block the message .</span></span> <span data-ttu-id="4538c-199">.</span><span class="sxs-lookup"><span data-stu-id="4538c-199"></span></span> <span data-ttu-id="4538c-200">.</span><span class="sxs-lookup"><span data-stu-id="4538c-200"></span></span> <span data-ttu-id="4538c-201">拒絕郵件並包含說明。</span><span class="sxs-lookup"><span data-stu-id="4538c-201">reject the message and include an explanation.</span></span>  <br/> |
|<span data-ttu-id="4538c-202">提供訊息文字</span><span class="sxs-lookup"><span data-stu-id="4538c-202">Provide message text</span></span>  <br/> |<span data-ttu-id="4538c-203">因為安全性的原因, 無法自動將電子郵件轉寄到此組織外部。</span><span class="sxs-lookup"><span data-stu-id="4538c-203">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="4538c-204">保護您的電子郵件免受網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="4538c-204">Protect your email from phishing attacks</span></span>

<span data-ttu-id="4538c-205">如果您已為 Office 365 或 Microsoft 365 環境設定一或多個自訂網域, 您可以設定目標的反網路釣魚保護。</span><span class="sxs-lookup"><span data-stu-id="4538c-205">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="4538c-206">ATP 反網路釣魚防護, 部分的 Office 365 高級威脅防護, 可協助保護您的組織免受惡意模擬型網路釣魚攻擊和其他網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="4538c-206">ATP anti-phishing protection, part of Office 365 Advanced Threat Protection, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="4538c-207">如果您尚未設定自訂網域, 則不需要執行此動作。</span><span class="sxs-lookup"><span data-stu-id="4538c-207">If you haven't configured a custom domain, you do not need to do this.</span></span>
  
<span data-ttu-id="4538c-208">我們建議您先建立一個原則, 以保護最重要的使用者和您的自訂網域, 以開始使用這項保護。</span><span class="sxs-lookup"><span data-stu-id="4538c-208">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span> 

  
<span data-ttu-id="4538c-209">若要建立 ATP 反網路釣魚原則, 請觀看[這個簡短的訓練影片](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), 或完成下列步驟:</span><span class="sxs-lookup"><span data-stu-id="4538c-209">To create an ATP anti-phishing policy, watch  [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>
  
1. <span data-ttu-id="4538c-210">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="4538c-210">Go to [https://protection.office.com](https://protection.office.com).</span></span> 
    
2. <span data-ttu-id="4538c-211">在 Office 365 安全性&amp;合規性中心的左功能窗格中, 選擇 [**威脅管理**] 底下的 [**原則**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-211">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="4538c-212">在 [**原則**] 頁面上, 選擇 [ **ATP 反網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-212">On the **Policy** page, choose **ATP anti-phishing**.</span></span>
    
4. <span data-ttu-id="4538c-213">在 [**反網路釣魚**] 頁面上, 選取 [ **+ 建立**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-213">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="4538c-214">[! 注意] 會啟動嚮導, 以逐步定義您的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="4538c-214">A wizard launches that steps you through defining your anti-phishing policy.</span></span>
    
5. <span data-ttu-id="4538c-215">請按照下表中的建議, 指定原則的名稱、描述和設定。</span><span class="sxs-lookup"><span data-stu-id="4538c-215">Specify the name, description, and settings for your policy as recommended in the chart below.</span></span> <span data-ttu-id="4538c-216">如需詳細資訊, 請參閱[瞭解 ATP 反網路釣魚原則選項](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="4538c-216">See [Learn about ATP anti-phishing policy options](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409) for more details.</span></span> 
    
6. <span data-ttu-id="4538c-217">檢查您的設定之後, 請視需要選擇 [**建立這個原則**] 或 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-217">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="4538c-218">**設定或選項**</span><span class="sxs-lookup"><span data-stu-id="4538c-218">**Setting or option**</span></span><br/>|<span data-ttu-id="4538c-219">**建議設定**</span><span class="sxs-lookup"><span data-stu-id="4538c-219">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="4538c-220">名稱</span><span class="sxs-lookup"><span data-stu-id="4538c-220">Name</span></span>  <br/> |<span data-ttu-id="4538c-221">網域和最有價值的活動人員</span><span class="sxs-lookup"><span data-stu-id="4538c-221">Domain and most valuable campaign staff</span></span>  <br/> |
|<span data-ttu-id="4538c-222">描述</span><span class="sxs-lookup"><span data-stu-id="4538c-222">Description</span></span>  <br/> |<span data-ttu-id="4538c-223">確保最重要的人員和我們的網域不會受到類比。</span><span class="sxs-lookup"><span data-stu-id="4538c-223">Ensure most important staff and our domain are not being impersonated.</span></span>  <br/> |
|<span data-ttu-id="4538c-224">新增要保護的使用者</span><span class="sxs-lookup"><span data-stu-id="4538c-224">Add users to protect</span></span>  <br/> |<span data-ttu-id="4538c-225">選取 **+ [新增條件], 收件者是**。</span><span class="sxs-lookup"><span data-stu-id="4538c-225">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="4538c-226">輸入使用者名稱, 或輸入候選人、活動管理員及其他重要職員成員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4538c-226">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="4538c-227">您最多可以新增20個要防止模擬的內部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="4538c-227">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>  <br/> |
|<span data-ttu-id="4538c-228">新增要保護的網域</span><span class="sxs-lookup"><span data-stu-id="4538c-228">Add domains to protect</span></span>  <br/> |<span data-ttu-id="4538c-229">選取 **+ 新增條件, 收件者網域是**。</span><span class="sxs-lookup"><span data-stu-id="4538c-229">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="4538c-230">輸入與您的 Microsoft 365 訂閱相關聯的自訂網域 (如果您定義了的話)。</span><span class="sxs-lookup"><span data-stu-id="4538c-230">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="4538c-231">您可以輸入一個以上的網域。</span><span class="sxs-lookup"><span data-stu-id="4538c-231">You can enter more than one domain.</span></span>  <br/> |
|<span data-ttu-id="4538c-232">選擇動作</span><span class="sxs-lookup"><span data-stu-id="4538c-232">Choose actions</span></span>  <br/> |<span data-ttu-id="4538c-233">如果由模擬的使用者傳送電子郵件: 選擇 [**將郵件重新導向至另一個電子郵件地址**], 然後輸入安全性系統管理員的電子郵件地址。例如,*劉愛琳<span><span>@contoso .com*。</span><span class="sxs-lookup"><span data-stu-id="4538c-233">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span>          <span data-ttu-id="4538c-234">如果由模擬的網域傳送電子郵件: 選擇 [**隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-234">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>  <br/> |
|<span data-ttu-id="4538c-235">信箱智慧</span><span class="sxs-lookup"><span data-stu-id="4538c-235">Mailbox intelligence</span></span>  <br/> |<span data-ttu-id="4538c-236">根據預設, 當您建立新的反網路釣魚原則時, 會選取信箱智慧。</span><span class="sxs-lookup"><span data-stu-id="4538c-236">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="4538c-237">將此設定保留為 [**開啟**] 以取得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="4538c-237">Leave this setting **On** for best results.</span></span>  <br/> |
|<span data-ttu-id="4538c-238">新增信任的寄件者和網域</span><span class="sxs-lookup"><span data-stu-id="4538c-238">Add trusted senders and domains</span></span>  <br/> |<span data-ttu-id="4538c-239">您可以在這裡新增您自己的網域或任何其他信任的網域。</span><span class="sxs-lookup"><span data-stu-id="4538c-239">Here you can add your own domain, or any other trusted domains.</span></span>  <br/> |
|<span data-ttu-id="4538c-240">套用至</span><span class="sxs-lookup"><span data-stu-id="4538c-240">Applied to</span></span>  <br/> |<span data-ttu-id="4538c-241">選取 **[收件**者] 網域。</span><span class="sxs-lookup"><span data-stu-id="4538c-241">Select **The recipient domain is**.</span></span> <span data-ttu-id="4538c-242">在**其中任何一項**下, 選取 **[選擇**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-242">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="4538c-243">選取 [ **+ 新增**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-243">Select **+ Add**.</span></span> <span data-ttu-id="4538c-244">選取功能變數名稱旁的核取方塊, 例如\*contoso。<span>com <span> \*, 然後選取清單中的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-244">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="4538c-245">選取 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-245">Select **Done**.</span></span>  <br/> |
   
<span data-ttu-id="4538c-246">如需詳細資訊, 請參閱[設定 Office 365 ATP 反網路釣魚原則](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="4538c-246">For more information, see [Set up Office 365 ATP anti-phishing policies](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).</span></span>
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a><span data-ttu-id="4538c-247">使用 ATP 安全附件來防止惡意附件和檔案</span><span class="sxs-lookup"><span data-stu-id="4538c-247">Protect against malicious attachments and files with ATP Safe Attachments</span></span>

<span data-ttu-id="4538c-248">人們會定期傳送、接收和共用附件, 例如檔、簡報、試算表等等。</span><span class="sxs-lookup"><span data-stu-id="4538c-248">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="4538c-249">只要查看電子郵件訊息, 就不一定容易知道附件是否安全或惡意。</span><span class="sxs-lookup"><span data-stu-id="4538c-249">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="4538c-250">Office 365 高級威脅防護包括 ATP 安全附件保護, 但是預設不會開啟此保護。</span><span class="sxs-lookup"><span data-stu-id="4538c-250">Office 365 Advanced Threat Protection includes ATP Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="4538c-251">建議您建立新的規則, 以開始使用此保護。</span><span class="sxs-lookup"><span data-stu-id="4538c-251">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="4538c-252">這項保護延伸至 SharePoint、OneDrive 及 Microsoft 團隊中的檔案。</span><span class="sxs-lookup"><span data-stu-id="4538c-252">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>
  
<span data-ttu-id="4538c-253">若要建立 ATP 安全附件原則, 請觀看[這段簡短的影片](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), 或完成下列步驟:</span><span class="sxs-lookup"><span data-stu-id="4538c-253">To create an ATP safe attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>
  
1. <span data-ttu-id="4538c-254">移至[https://protection.office.com](https://protection.office.com)並以您的系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="4538c-254">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="4538c-255">在 Office 365 安全性&amp;合規性中心的左功能窗格中, 選擇 [**威脅管理**] 底下的 [**原則**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-255">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="4538c-256">在 [原則] 頁面上, 選擇 [ **ATP 安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-256">On the Policy page, choose **ATP safe attachments**.</span></span>
    
4. <span data-ttu-id="4538c-257">在 [安全附件] 頁面上, 選取 [**開啟 SharePoint、OneDrive 及 Microsoft 團隊**版的 ATP] 核取方塊, 以廣泛套用這種保護。</span><span class="sxs-lookup"><span data-stu-id="4538c-257">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span> 
    
5. <span data-ttu-id="4538c-258">選取**+** 以建立新原則。</span><span class="sxs-lookup"><span data-stu-id="4538c-258">Select **+** to create a new policy.</span></span> 
    
6. <span data-ttu-id="4538c-259">套用下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="4538c-259">Apply the settings in the following table.</span></span> 
    
7. <span data-ttu-id="4538c-260">檢查您的設定之後, 請視需要選擇 [**建立這個原則**] 或 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-260">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="4538c-261">**設定或選項**</span><span class="sxs-lookup"><span data-stu-id="4538c-261">**Setting or option**</span></span>|<span data-ttu-id="4538c-262">**建議設定**</span><span class="sxs-lookup"><span data-stu-id="4538c-262">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="4538c-263">名稱</span><span class="sxs-lookup"><span data-stu-id="4538c-263">Name</span></span>  <br/> |<span data-ttu-id="4538c-264">封鎖目前和未來已偵測到惡意程式碼的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="4538c-264">Block current and future emails with detected malware.</span></span>  <br/> |
|<span data-ttu-id="4538c-265">描述</span><span class="sxs-lookup"><span data-stu-id="4538c-265">Description</span></span>  <br/> |<span data-ttu-id="4538c-266">封鎖目前和未來的電子郵件和附件偵測到的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="4538c-266">Block current and future emails and attachments with detected malware.</span></span>  <br/> |
|<span data-ttu-id="4538c-267">儲存附件未知的惡意軟體回應</span><span class="sxs-lookup"><span data-stu-id="4538c-267">Save attachments unknown malware response</span></span>  <br/> |<span data-ttu-id="4538c-268">Select **block-封鎖目前和未來的電子郵件和附件偵測到的惡意**代碼。</span><span class="sxs-lookup"><span data-stu-id="4538c-268">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>  <br/> |
|<span data-ttu-id="4538c-269">在偵測上重新導向附件</span><span class="sxs-lookup"><span data-stu-id="4538c-269">Redirect attachment on detection</span></span>  <br/> |<span data-ttu-id="4538c-270">啟用重新導向 (選取此方塊) 輸入系統管理員帳戶或隔離的信箱設定。</span><span class="sxs-lookup"><span data-stu-id="4538c-270">Enable redirection (select this box)          Enter the admin account or a mailbox setup for quarantine.</span></span>          <span data-ttu-id="4538c-271">如果惡意程式碼掃描附件時超時或發生錯誤, 請套用上述選取範圍 (選取此方塊)。</span><span class="sxs-lookup"><span data-stu-id="4538c-271">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>  <br/> |
|<span data-ttu-id="4538c-272">套用至</span><span class="sxs-lookup"><span data-stu-id="4538c-272">Applied to</span></span>  <br/> |<span data-ttu-id="4538c-273">收件者網域是。</span><span class="sxs-lookup"><span data-stu-id="4538c-273">The recipient domain is .</span></span> <span data-ttu-id="4538c-274">.</span><span class="sxs-lookup"><span data-stu-id="4538c-274"></span></span> <span data-ttu-id="4538c-275">.</span><span class="sxs-lookup"><span data-stu-id="4538c-275"></span></span> <span data-ttu-id="4538c-276">選取您的網域。</span><span class="sxs-lookup"><span data-stu-id="4538c-276">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="4538c-277">如需詳細資訊, 請參閱[設定 Office 365 ATP 反網路釣魚原則](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="4538c-277">For more information, see [Set up Office 365 ATP anti-phishing policies](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).</span></span>
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a><span data-ttu-id="4538c-278">使用 ATP 安全連結來防禦網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="4538c-278">Protect against phishing attacks with ATP Safe Links</span></span>

<span data-ttu-id="4538c-279">駭客有時會在電子郵件或其他檔案的連結中隱藏惡意的網站。</span><span class="sxs-lookup"><span data-stu-id="4538c-279">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="4538c-280">Office 365 ATP 安全連結 (ATP 安全連結) 是 Office 365 高級威脅防護的一部分, 可提供電子郵件訊息和 Office 檔中的網頁位址 (Url) 驗證, 以協助保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="4538c-280">Office 365 ATP Safe Links (ATP Safe Links), part of Office 365 Advanced Threat Protection, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="4538c-281">保護是透過 ATP 安全連結原則所定義。</span><span class="sxs-lookup"><span data-stu-id="4538c-281">Protection is defined through ATP Safe Links policies.</span></span>
  
<span data-ttu-id="4538c-282">我們建議您執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="4538c-282">We recommend that you do the following:</span></span>
  
- <span data-ttu-id="4538c-283">修改預設原則以提升保護。</span><span class="sxs-lookup"><span data-stu-id="4538c-283">Modify the default policy to increase protection.</span></span>
    
- <span data-ttu-id="4538c-284">新增針對您網域中的所有收件者的新原則。</span><span class="sxs-lookup"><span data-stu-id="4538c-284">Add a new policy targeted to all recipients in your domain.</span></span>
    
<span data-ttu-id="4538c-285">若要設定 ATP 安全連結, 請觀看[這個簡短的訓練影片](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), 或完成下列步驟:</span><span class="sxs-lookup"><span data-stu-id="4538c-285">To set up ATP Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>
  
1. <span data-ttu-id="4538c-286">移至[https://protection.office.com](https://protection.office.com)並以您的系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="4538c-286">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="4538c-287">在 Office 365 安全性&amp;合規性中心的左功能窗格中, 選擇 [**威脅管理**] 底下的 [**原則**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-287">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="4538c-288">在 [原則] 頁面上, 選擇 [ **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-288">On the Policy page, choose **ATP Safe Links**.</span></span>
    
<span data-ttu-id="4538c-289">若要修改預設原則:</span><span class="sxs-lookup"><span data-stu-id="4538c-289">To modify the default policy:</span></span>
  
1. <span data-ttu-id="4538c-290">在 [安全連結] 頁面的 [**適用于整個組織的原則**] 下, 選取**預設**原則。</span><span class="sxs-lookup"><span data-stu-id="4538c-290">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span> 
    
2. <span data-ttu-id="4538c-291">在 [**電子郵件除外的設定**] 下, 選取 [ **office 365 專業增強版]、[office For iOS 和 Android**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-291">Under **Settings that apply to content except email**, select **Office 365 ProPlus, Office for iOS and Android**.</span></span>
    
3. <span data-ttu-id="4538c-292">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4538c-292">Click **Save**.</span></span> 
    
<span data-ttu-id="4538c-293">若要建立以您網域中的所有收件者為目標的新原則:</span><span class="sxs-lookup"><span data-stu-id="4538c-293">To create a new policy targeted to all recipients in your domain:</span></span>
  
1. <span data-ttu-id="4538c-294">在 [安全連結] 頁面上, 按一下**+** [套用**至整個組織的原則**] 下的 [建立新原則]。</span><span class="sxs-lookup"><span data-stu-id="4538c-294">On the Safe links page, under **Policies that apply to the entire organization**, click **+** to create a new policy.</span></span> 
    
2. <span data-ttu-id="4538c-295">套用下表所列的設定。</span><span class="sxs-lookup"><span data-stu-id="4538c-295">Apply the settings listed in the following table.</span></span>
    
3. <span data-ttu-id="4538c-296">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4538c-296">Click **Save**.</span></span> 

|<span data-ttu-id="4538c-297">**設定或選項**</span><span class="sxs-lookup"><span data-stu-id="4538c-297">**Setting or option**</span></span>|<span data-ttu-id="4538c-298">**建議設定**</span><span class="sxs-lookup"><span data-stu-id="4538c-298">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="4538c-299">名稱</span><span class="sxs-lookup"><span data-stu-id="4538c-299">Name</span></span>  <br/> |<span data-ttu-id="4538c-300">網域中所有收件者的安全連結原則</span><span class="sxs-lookup"><span data-stu-id="4538c-300">Safe links policy for all recipients in the domain</span></span>  <br/> |
|<span data-ttu-id="4538c-301">選取郵件中未知潛在惡意 Url 的動作</span><span class="sxs-lookup"><span data-stu-id="4538c-301">Select the action for unknown potentially malicious URLs in messages</span></span>  <br/> |<span data-ttu-id="4538c-302">**當使用者按一下連結時, 會重新寫入並檢查已知惡意連結清單中的 [On url**]。</span><span class="sxs-lookup"><span data-stu-id="4538c-302">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>  <br/> |
|<span data-ttu-id="4538c-303">使用安全附件掃描可下載的內容</span><span class="sxs-lookup"><span data-stu-id="4538c-303">Use Safe Attachments to scan downloadable content</span></span>  <br/> |<span data-ttu-id="4538c-304">選取此方塊。</span><span class="sxs-lookup"><span data-stu-id="4538c-304">Select this box.</span></span>  <br/> |
|<span data-ttu-id="4538c-305">套用至</span><span class="sxs-lookup"><span data-stu-id="4538c-305">Applied to</span></span>  <br/> |<span data-ttu-id="4538c-306">收件者網域是。</span><span class="sxs-lookup"><span data-stu-id="4538c-306">The recipient domain is .</span></span> <span data-ttu-id="4538c-307">.</span><span class="sxs-lookup"><span data-stu-id="4538c-307"></span></span> <span data-ttu-id="4538c-308">.</span><span class="sxs-lookup"><span data-stu-id="4538c-308"></span></span> <span data-ttu-id="4538c-309">選取您的網域。</span><span class="sxs-lookup"><span data-stu-id="4538c-309">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="4538c-310">如需詳細資訊, 請參閱[Office 365 ATP 安全連結](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="4538c-310">For more information, see [Office 365 ATP safe links](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="4538c-311">移至 Intune 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="4538c-311">Go to Intune admin center</span></span>

1. <span data-ttu-id="4538c-312">登入[Azure 入口網站](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="4538c-312">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="4538c-313">選取 [**所有服務**], 然後在 [**搜尋**] 方塊中輸入*Intune* 。</span><span class="sxs-lookup"><span data-stu-id="4538c-313">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="4538c-314">顯示結果後, 按一下 [ **Microsoft Intune** ] 旁的 [開始], 讓其成為最愛且易於尋找。</span><span class="sxs-lookup"><span data-stu-id="4538c-314">Once the results display, click the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="4538c-315">除了系統管理中心之外, 您還可以使用 Intune 來註冊及管理組織的裝置。</span><span class="sxs-lookup"><span data-stu-id="4538c-315">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="4538c-316">如需詳細資訊, 請參閱[Windows 裝置的註冊方法](https://docs.microsoft.com/intune/enrollment-method-capabs)和[Intune 所管理之裝置的註冊選項](https://docs.microsoft.com/intune/enrollment-options)的功能。</span><span class="sxs-lookup"><span data-stu-id="4538c-316">For more information, see [Capabilities by enrollment method for Windows devices](https://docs.microsoft.com/intune/enrollment-method-capabs) and [Enrollment options for devices managed by Intune](https://docs.microsoft.com/intune/enrollment-options).</span></span>
