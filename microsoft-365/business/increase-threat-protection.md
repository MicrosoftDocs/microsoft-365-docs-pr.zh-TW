---
title: 為商務用 Microsoft 365 增加威脅防護
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 設定 Office 365 的高級威脅防護，並保護機密資料，避免網路釣魚、惡意程式碼和其他威脅。
ms.openlocfilehash: d5510cdc082781fd9a1776e86b1bab1d8a2723d6
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786199"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="08764-103">加強威脅防護</span><span class="sxs-lookup"><span data-stu-id="08764-103">Increase threat protection</span></span>

<span data-ttu-id="08764-104">本文可協助您提高 Microsoft 365 訂閱中的保護，以防範網路釣魚、惡意程式碼和其他威脅。</span><span class="sxs-lookup"><span data-stu-id="08764-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="08764-105">這些建議適用于安全性增加的組織，例如法律辦事處和衛生保健診所的需求。</span><span class="sxs-lookup"><span data-stu-id="08764-105">These recommendations are appropriate for organizations with an increased need for security, like law offices and health care clinics.</span></span>

<span data-ttu-id="08764-106">開始之前，請先檢查您的 Office 365 安全分數。</span><span class="sxs-lookup"><span data-stu-id="08764-106">Before you begin, check your Office 365 Secure Score.</span></span> <span data-ttu-id="08764-107">Office 365 安全分數會根據您的定期活動和安全性設定來分析貴組織的安全性，並指定分數。</span><span class="sxs-lookup"><span data-stu-id="08764-107">Office 365 Secure Score analyzes your organization's security based on your regular activities and security settings, and assigns a score.</span></span> <span data-ttu-id="08764-108">請先記下您目前的分數。</span><span class="sxs-lookup"><span data-stu-id="08764-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="08764-109">若要增加您的分數，請完成本文中建議的動作。</span><span class="sxs-lookup"><span data-stu-id="08764-109">To increase your score, complete the actions recommended in this article.</span></span> <span data-ttu-id="08764-110">目標不會達到最大分數，但請注意保護您的環境不會對使用者生產力造成不良影響的機會。</span><span class="sxs-lookup"><span data-stu-id="08764-110">The goal isn't to achieve the maximum score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span> 

<span data-ttu-id="08764-111">如需詳細資訊，請參閱[Microsoft 安全分數](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。</span><span class="sxs-lookup"><span data-stu-id="08764-111">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="08764-112">提升郵件中惡意程式碼的保護層級</span><span class="sxs-lookup"><span data-stu-id="08764-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="08764-113">您的 Office 365 或 Microsoft 365 環境包括防範惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="08764-113">Your Office 365 or Microsoft 365 environment includes protection against malware.</span></span> <span data-ttu-id="08764-114">您可以使用常用於惡意程式碼的檔案類型來封鎖附件，以提升這種保護。</span><span class="sxs-lookup"><span data-stu-id="08764-114">You can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="08764-115">若要提高電子郵件的惡意程式碼保護：</span><span class="sxs-lookup"><span data-stu-id="08764-115">To increase malware protection in email:</span></span>
  
1. <span data-ttu-id="08764-116">移至 [https://protection.office.com](https://protection.office.com) 並以您的系統管理員帳號憑證登入。</span><span class="sxs-lookup"><span data-stu-id="08764-116">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.</span></span> 
    
2. <span data-ttu-id="08764-117">在安全性與 &amp; 合規性中心的左功能窗格中，在 [**威脅管理**] 底下，選擇 [**原則** \> **Anti-Malware**]。</span><span class="sxs-lookup"><span data-stu-id="08764-117">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>
    
3. <span data-ttu-id="08764-118">按兩下預設原則，以編輯此全公司原則。</span><span class="sxs-lookup"><span data-stu-id="08764-118">Double-click the default policy to edit this company-wide policy.</span></span>
    
4. <span data-ttu-id="08764-119">選取 [設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="08764-119">Select **Settings**.</span></span>
    
5. <span data-ttu-id="08764-120">在 [**一般附件類型篩選**] 底下，選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="08764-120">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="08764-121">封鎖的檔案類型會列在此控制項底下的視窗中。</span><span class="sxs-lookup"><span data-stu-id="08764-121">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="08764-122">請務必新增下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="08764-122">Make sure that you add these file types:</span></span>
   - <span data-ttu-id="08764-123">ade、adp、ani、bas，bat，chm，cmd，com，cpl，crt，.hlp，ht，的 hta，inf，ins，jse，mdb，mdb，mde，mdz，msc，msi，msp，.msp，.pcd，reg，.scr，sct，wsc，wsf，wsh，vbe，pif</span><span class="sxs-lookup"><span data-stu-id="08764-123">ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif</span></span>  <br/> 
   
   <span data-ttu-id="08764-124">如有必要，您可以稍後新增或刪除檔案類型。</span><span class="sxs-lookup"><span data-stu-id="08764-124">If necessary, you can add or delete file types later.</span></span>
    
6. <span data-ttu-id="08764-125">選取 [**儲存]。**</span><span class="sxs-lookup"><span data-stu-id="08764-125">Select **Save.**</span></span>
    
<span data-ttu-id="08764-126">如需詳細資訊，請參閱[反惡意程式碼保護](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="08764-126">For more information, see [Anti-malware protection](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).</span></span>
  
## <a name="protect-against-ransomware"></a><span data-ttu-id="08764-127">防護勒索軟體</span><span class="sxs-lookup"><span data-stu-id="08764-127">Protect against ransomware</span></span>

<span data-ttu-id="08764-128">勒索軟體會以加密檔案或鎖定電腦畫面限制存取資料。</span><span class="sxs-lookup"><span data-stu-id="08764-128">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="08764-129">然後，它會要求「ransom」（通常是以 cryptocurrencies 如 Bitcoin 的形式） extort money，以供 exchange 存取資料。</span><span class="sxs-lookup"><span data-stu-id="08764-129">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span> 
  
<span data-ttu-id="08764-130">若要防止勒索軟體，請建立一個或多個郵件流程規則，以封鎖勒索軟體常用的副檔名。</span><span class="sxs-lookup"><span data-stu-id="08764-130">To protect against ransomware, create one or more mail flow rules to block file extensions that are commonly used for ransomware.</span></span> <span data-ttu-id="08764-131">（您已在 [郵件步驟] 中的 [[提升惡意程式碼保護層級](#raise-the-level-of-protection-against-malware-in-mail)] 中新增這些規則。）您也可以在電子郵件中警告接收這些附件的使用者。</span><span class="sxs-lookup"><span data-stu-id="08764-131">(You added these rules in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step.) You can also warn users who receive these attachments in email.</span></span>

<span data-ttu-id="08764-132">除了您在上一個步驟中封鎖的檔案，在開啟包含宏的 Office 檔案附件之前，先建立規則來警告使用者，是一種很好的作法。</span><span class="sxs-lookup"><span data-stu-id="08764-132">In addition to the files that you blocked in the previous step, it's a good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="08764-133">勒索軟體可以隱藏在宏內，所以警告使用者不要從他們不知道的人開啟這些檔案。</span><span class="sxs-lookup"><span data-stu-id="08764-133">Ransomware can be hidden inside macros, so warn users not to open these files from people they don't know.</span></span>

<span data-ttu-id="08764-134">若要建立郵件傳輸規則：</span><span class="sxs-lookup"><span data-stu-id="08764-134">To create a mail transport rule:</span></span>
  
1. <span data-ttu-id="08764-135">移至 [系統管理中心] <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> ，然後選擇 [系統**管理中心**] [ \> **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="08764-135">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>, and choose **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="08764-136">在 [**郵件流程**] 類別中，選取 [**規則**]。</span><span class="sxs-lookup"><span data-stu-id="08764-136">In the **mail flow** category, select **rules**.</span></span>
    
3. <span data-ttu-id="08764-137">選取 [] **+** ，然後選取 [**建立新規則**]。</span><span class="sxs-lookup"><span data-stu-id="08764-137">Select **+**, and then select **Create a new rule**.</span></span>
    
4. <span data-ttu-id="08764-138">在對話方塊底部選取 [**更多選項**]，以查看完整的選項組。</span><span class="sxs-lookup"><span data-stu-id="08764-138">Select **More options** at the bottom of the dialog box to see the full set of options.</span></span> 
    
5. <span data-ttu-id="08764-139">針對規則套用下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="08764-139">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="08764-140">除非您想要變更預設值，否則請對其他設定使用預設值。</span><span class="sxs-lookup"><span data-stu-id="08764-140">Use the default values for the rest of the settings, unless you want to change them.</span></span>
    
6. <span data-ttu-id="08764-141">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="08764-141">Select **Save**.</span></span>
    
|<span data-ttu-id="08764-142">**設定**</span><span class="sxs-lookup"><span data-stu-id="08764-142">**Setting**</span></span>|<span data-ttu-id="08764-143">**開啟 Office 檔案的附件之前警告使用者**</span><span class="sxs-lookup"><span data-stu-id="08764-143">**Warn users before opening attachments of Office files**</span></span>||
|:-----|:-----|:-----|
|<span data-ttu-id="08764-144">名稱</span><span class="sxs-lookup"><span data-stu-id="08764-144">Name</span></span>  <br/> |<span data-ttu-id="08764-145">反內部的勒索軟體規則：警告使用者</span><span class="sxs-lookup"><span data-stu-id="08764-145">Anti-ransomware rule: warn users</span></span>  <br/>  |
|<span data-ttu-id="08764-146">將此規則套用至 if。</span><span class="sxs-lookup"><span data-stu-id="08764-146">Apply this rule if .</span></span> <span data-ttu-id="08764-147">.</span><span class="sxs-lookup"><span data-stu-id="08764-147">.</span></span> <span data-ttu-id="08764-148">.</span><span class="sxs-lookup"><span data-stu-id="08764-148">.</span></span>  <br/> |<span data-ttu-id="08764-149">任何附件。</span><span class="sxs-lookup"><span data-stu-id="08764-149">Any attachment .</span></span> <span data-ttu-id="08764-150">.</span><span class="sxs-lookup"><span data-stu-id="08764-150">.</span></span> <span data-ttu-id="08764-151">.</span><span class="sxs-lookup"><span data-stu-id="08764-151">.</span></span> <span data-ttu-id="08764-152">副檔名符合。</span><span class="sxs-lookup"><span data-stu-id="08764-152">file extension matches .</span></span> <span data-ttu-id="08764-153">.</span><span class="sxs-lookup"><span data-stu-id="08764-153">.</span></span> <span data-ttu-id="08764-154">.</span><span class="sxs-lookup"><span data-stu-id="08764-154">.</span></span>  <br/> |
|<span data-ttu-id="08764-155">指定字詞或片語</span><span class="sxs-lookup"><span data-stu-id="08764-155">Specify words or phrases</span></span>  <br/> |<span data-ttu-id="08764-156">新增下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="08764-156">Add these file types:</span></span>  <br/> <span data-ttu-id="08764-157">.docm、xlsm、sltm、xla、xlam、xll、pptm、potm、ppam、ppsm、sldm</span><span class="sxs-lookup"><span data-stu-id="08764-157">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>  <br/>|
|<span data-ttu-id="08764-158">請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="08764-158">Do the following .</span></span> <span data-ttu-id="08764-159">.</span><span class="sxs-lookup"><span data-stu-id="08764-159">.</span></span> <span data-ttu-id="08764-160">.</span><span class="sxs-lookup"><span data-stu-id="08764-160">.</span></span>  <br/> |<span data-ttu-id="08764-161">以郵件通知收件者</span><span class="sxs-lookup"><span data-stu-id="08764-161">Notify the recipient with a message</span></span>  <br/> |
|<span data-ttu-id="08764-162">提供郵件文字</span><span class="sxs-lookup"><span data-stu-id="08764-162">Provide message text</span></span>  <br/> |<span data-ttu-id="08764-163">請勿從不知道的人開啟這些類型的檔案，因為這些人可能會包含惡意程式碼的宏。</span><span class="sxs-lookup"><span data-stu-id="08764-163">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>  <br/> |
   
<span data-ttu-id="08764-164">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="08764-164">For more information, see:</span></span>
  
- [<span data-ttu-id="08764-165">如何處理勒索軟體</span><span class="sxs-lookup"><span data-stu-id="08764-165">How to deal with ransomware</span></span>](https://go.microsoft.com/fwlink/?linkid=2016501)
    
- [<span data-ttu-id="08764-166">還原您的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="08764-166">Restore your OneDrive</span></span>](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="08764-167">停止電子郵件的自動轉寄功能</span><span class="sxs-lookup"><span data-stu-id="08764-167">Stop auto-forwarding for email</span></span>

<span data-ttu-id="08764-168">取得使用者信箱存取權的駭客可以透過將信箱設定為自動轉寄電子郵件，來竊取郵件。</span><span class="sxs-lookup"><span data-stu-id="08764-168">Hackers who gain access to a user's mailbox can steal mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="08764-169">即使沒有使用者的認知，也可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="08764-169">This can happen even without the user's awareness.</span></span> <span data-ttu-id="08764-170">若要避免發生這種情況，請設定郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="08764-170">To prevent this from happening, configure a mail flow rule.</span></span> 
  
<span data-ttu-id="08764-171">若要建立郵件傳輸規則，請觀看[這段簡短的影片](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7)，或遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="08764-171">To create a mail transport rule, either watch [this short video](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>
  
1. <span data-ttu-id="08764-172">在 Microsoft 365 系統管理中心中，選取 [系統**管理中心**] [ \> **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="08764-172">In the Microsoft 365 admin center, select **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="08764-173">在 [**郵件流程**] 類別中，選取 [**規則**]。</span><span class="sxs-lookup"><span data-stu-id="08764-173">In the **mail flow** category, select **rules**.</span></span>
    
3. <span data-ttu-id="08764-174">選取 [] **+** ，然後選取 [**建立新規則**]。</span><span class="sxs-lookup"><span data-stu-id="08764-174">Select **+**, and then select **Create a new rule**.</span></span>
    
4. <span data-ttu-id="08764-175">若要查看所有選項，請選取對話方塊底部的 [**更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="08764-175">To see all the options, select **More options** at the bottom of the dialog box.</span></span> 
    
5. <span data-ttu-id="08764-176">套用下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="08764-176">Apply the settings in the following table.</span></span> <span data-ttu-id="08764-177">除非您想要變更預設值，否則請對其他設定使用預設值。</span><span class="sxs-lookup"><span data-stu-id="08764-177">Use the default values for the rest of the settings, unless you want to change them.</span></span>
    
6. <span data-ttu-id="08764-178">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="08764-178">Select **Save**.</span></span>
    
|<span data-ttu-id="08764-179">**設定**</span><span class="sxs-lookup"><span data-stu-id="08764-179">**Setting**</span></span>|<span data-ttu-id="08764-180">**開啟 Office 檔案的附件之前警告使用者**</span><span class="sxs-lookup"><span data-stu-id="08764-180">**Warn users before opening attachments of Office files**</span></span>|
|:-----|:-----|
|<span data-ttu-id="08764-181">名稱</span><span class="sxs-lookup"><span data-stu-id="08764-181">Name</span></span>  <br/> |<span data-ttu-id="08764-182">禁止將電子郵件自動轉寄轉送至外部網域</span><span class="sxs-lookup"><span data-stu-id="08764-182">Prevent auto forwarding of email to external domains</span></span>  <br/> |
|<span data-ttu-id="08764-183">將此規則套用至 if .。。</span><span class="sxs-lookup"><span data-stu-id="08764-183">Apply this rule if ...</span></span>  <br/> |<span data-ttu-id="08764-184">寄件者。</span><span class="sxs-lookup"><span data-stu-id="08764-184">The sender .</span></span> <span data-ttu-id="08764-185">.</span><span class="sxs-lookup"><span data-stu-id="08764-185">.</span></span> <span data-ttu-id="08764-186">.</span><span class="sxs-lookup"><span data-stu-id="08764-186">.</span></span> <span data-ttu-id="08764-187">為外部/內部。</span><span class="sxs-lookup"><span data-stu-id="08764-187">is external/internal .</span></span> <span data-ttu-id="08764-188">.</span><span class="sxs-lookup"><span data-stu-id="08764-188">.</span></span> <span data-ttu-id="08764-189">.</span><span class="sxs-lookup"><span data-stu-id="08764-189">.</span></span> <span data-ttu-id="08764-190">組織內部</span><span class="sxs-lookup"><span data-stu-id="08764-190">Inside the organization</span></span>  <br/> |
|<span data-ttu-id="08764-191">新增條件</span><span class="sxs-lookup"><span data-stu-id="08764-191">Add condition</span></span>  <br/> |<span data-ttu-id="08764-192">郵件屬性。</span><span class="sxs-lookup"><span data-stu-id="08764-192">The message properties .</span></span> <span data-ttu-id="08764-193">.</span><span class="sxs-lookup"><span data-stu-id="08764-193">.</span></span> <span data-ttu-id="08764-194">.</span><span class="sxs-lookup"><span data-stu-id="08764-194">.</span></span> <span data-ttu-id="08764-195">包含郵件類型。</span><span class="sxs-lookup"><span data-stu-id="08764-195">include the message type .</span></span> <span data-ttu-id="08764-196">.</span><span class="sxs-lookup"><span data-stu-id="08764-196">.</span></span> <span data-ttu-id="08764-197">.</span><span class="sxs-lookup"><span data-stu-id="08764-197">.</span></span> <span data-ttu-id="08764-198">自動轉寄</span><span class="sxs-lookup"><span data-stu-id="08764-198">Auto-forward</span></span>  <br/> |
|<span data-ttu-id="08764-199">請執行下列動作 .。。</span><span class="sxs-lookup"><span data-stu-id="08764-199">Do the following ...</span></span>  <br/> |<span data-ttu-id="08764-200">封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="08764-200">Block the message .</span></span> <span data-ttu-id="08764-201">.</span><span class="sxs-lookup"><span data-stu-id="08764-201">.</span></span> <span data-ttu-id="08764-202">.</span><span class="sxs-lookup"><span data-stu-id="08764-202">.</span></span> <span data-ttu-id="08764-203">拒絕郵件並包含說明。</span><span class="sxs-lookup"><span data-stu-id="08764-203">reject the message and include an explanation.</span></span>  <br/> |
|<span data-ttu-id="08764-204">提供郵件文字</span><span class="sxs-lookup"><span data-stu-id="08764-204">Provide message text</span></span>  <br/> |<span data-ttu-id="08764-205">由於安全性原因，禁止此組織外部的電子郵件的自動轉寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="08764-205">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="08764-206">保護您的電子郵件免受網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="08764-206">Protect your email from phishing attacks</span></span>

<span data-ttu-id="08764-207">如果您已為 Office 365 或 Microsoft 365 環境設定一或多個自訂網域，您可以設定目標的反網路釣魚防護。</span><span class="sxs-lookup"><span data-stu-id="08764-207">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="08764-208">ATP 反網路釣魚保護，部分的 Office 365 高級威脅防護，可協助保護您的組織免受惡意模擬型網路釣魚攻擊和其他網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="08764-208">ATP anti-phishing protection, part of Office 365 Advanced Threat Protection, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="08764-209">若尚未設定自訂網域，您不需要執行此動作。</span><span class="sxs-lookup"><span data-stu-id="08764-209">If you haven't configured a custom domain, you don't need to do this.</span></span>
  
<span data-ttu-id="08764-210">建議您建立原則來保護您最重要的使用者和自訂網域，以開始使用這項保護。</span><span class="sxs-lookup"><span data-stu-id="08764-210">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span> 

<span data-ttu-id="08764-211">若要建立 ATP 反網路釣魚原則，請觀看[這段簡短的訓練影片](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)，或完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="08764-211">To create an ATP anti-phishing policy, watch  [this short training video](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>
  
1. <span data-ttu-id="08764-212">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="08764-212">Go to [https://protection.office.com](https://protection.office.com).</span></span> 
    
2. <span data-ttu-id="08764-213">在安全性與 &amp; 合規性中心的左功能窗格中，選擇 [**威脅管理**] 底下的 [**原則**]。</span><span class="sxs-lookup"><span data-stu-id="08764-213">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="08764-214">在 [**原則**] 頁面上，選擇 [ **ATP 反網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="08764-214">On the **Policy** page, choose **ATP anti-phishing**.</span></span>
    
4. <span data-ttu-id="08764-215">在 [**反網路釣魚**] 頁面上，選取 [ **+ 建立**]。</span><span class="sxs-lookup"><span data-stu-id="08764-215">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="08764-216">嚮導會啟動以逐步逐步定義您的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="08764-216">A wizard launches that steps you through defining your anti-phishing policy.</span></span>
    
5. <span data-ttu-id="08764-217">依照下表的建議，指定原則的名稱、描述及設定。</span><span class="sxs-lookup"><span data-stu-id="08764-217">Specify the name, description, and settings for your policy as recommended in the following table.</span></span> <span data-ttu-id="08764-218">如需詳細資訊，請參閱[瞭解 ATP 反網路釣魚原則選項](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options)。</span><span class="sxs-lookup"><span data-stu-id="08764-218">For more details, see [Learn about ATP anti-phishing policy options](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options).</span></span> 
    
6. <span data-ttu-id="08764-219">檢查您的設定之後，請選擇 [**建立這個原則**] 或 [**儲存**] （如適用）。</span><span class="sxs-lookup"><span data-stu-id="08764-219">After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="08764-220">**設定或選項**</span><span class="sxs-lookup"><span data-stu-id="08764-220">**Setting or option**</span></span><br/>|<span data-ttu-id="08764-221">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="08764-221">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="08764-222">名稱</span><span class="sxs-lookup"><span data-stu-id="08764-222">Name</span></span>  <br/> |<span data-ttu-id="08764-223">網域和最有價值的活動人員</span><span class="sxs-lookup"><span data-stu-id="08764-223">Domain and most valuable campaign staff</span></span>  <br/> |
|<span data-ttu-id="08764-224">描述</span><span class="sxs-lookup"><span data-stu-id="08764-224">Description</span></span>  <br/> |<span data-ttu-id="08764-225">確定最重要的人員和我們的網域未進行類比。</span><span class="sxs-lookup"><span data-stu-id="08764-225">Ensure most important staff and our domain are not being impersonated.</span></span>  <br/> |
|<span data-ttu-id="08764-226">新增要保護的使用者</span><span class="sxs-lookup"><span data-stu-id="08764-226">Add users to protect</span></span>  <br/> |<span data-ttu-id="08764-227">選取 **[+ 新增條件]，收件者是**。</span><span class="sxs-lookup"><span data-stu-id="08764-227">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="08764-228">輸入使用者名稱，或輸入候選人、活動管理員及其他重要員工成員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="08764-228">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="08764-229">您最多可以新增20個要從類比中保護的內部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="08764-229">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>  <br/> |
|<span data-ttu-id="08764-230">新增要保護的網域</span><span class="sxs-lookup"><span data-stu-id="08764-230">Add domains to protect</span></span>  <br/> |<span data-ttu-id="08764-231">選取 **[+ 新增條件]，收件者網域是**。</span><span class="sxs-lookup"><span data-stu-id="08764-231">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="08764-232">輸入您的 Microsoft 365 訂閱相關聯的自訂網域（如果您已定義的話）。</span><span class="sxs-lookup"><span data-stu-id="08764-232">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="08764-233">您可以輸入一個以上的網域。</span><span class="sxs-lookup"><span data-stu-id="08764-233">You can enter more than one domain.</span></span>  <br/> |
|<span data-ttu-id="08764-234">選擇動作</span><span class="sxs-lookup"><span data-stu-id="08764-234">Choose actions</span></span>  <br/> |<span data-ttu-id="08764-235">如果模仿的使用者傳送電子郵件：選擇 [重新**導向郵件至其他電子郵件地址**]，然後輸入安全性管理員的電子郵件地址。例如，*劉愛琳 <span> <span> @contoso .com*。</span><span class="sxs-lookup"><span data-stu-id="08764-235">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <span data-ttu-id="08764-236">如果電子郵件來自冒充的網域：請選擇 **[隔離郵件]**。</span><span class="sxs-lookup"><span data-stu-id="08764-236">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>  <br/> |
|<span data-ttu-id="08764-237">信箱情報</span><span class="sxs-lookup"><span data-stu-id="08764-237">Mailbox intelligence</span></span>  <br/> |<span data-ttu-id="08764-238">當您建立新的反網路釣魚原則時，系統會預設選取信箱情報。</span><span class="sxs-lookup"><span data-stu-id="08764-238">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="08764-239">請將此設定保留為 **[開啟]**，以獲得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="08764-239">Leave this setting **On** for best results.</span></span>  <br/> |
|<span data-ttu-id="08764-240">新增受信任的寄件者與網域</span><span class="sxs-lookup"><span data-stu-id="08764-240">Add trusted senders and domains</span></span>  <br/> |<span data-ttu-id="08764-241">您可以在這裡新增您自己的網域或任何其他受信任的網域。</span><span class="sxs-lookup"><span data-stu-id="08764-241">Here you can add your own domain, or any other trusted domains.</span></span>  <br/> |
|<span data-ttu-id="08764-242">套用對象</span><span class="sxs-lookup"><span data-stu-id="08764-242">Applied to</span></span>  <br/> |<span data-ttu-id="08764-243">請選取 **[收件者的網域是]**。</span><span class="sxs-lookup"><span data-stu-id="08764-243">Select **The recipient domain is**.</span></span> <span data-ttu-id="08764-244">在 **[任一項]** 底下選取 **[選擇]**。</span><span class="sxs-lookup"><span data-stu-id="08764-244">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="08764-245">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="08764-245">Select **+ Add**.</span></span> <span data-ttu-id="08764-246">選取功能變數名稱（例如 contoso）旁的核取方塊 *。 <span> <span>com*，在清單中，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="08764-246">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="08764-247">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="08764-247">Select **Done**.</span></span>  <br/> |
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a><span data-ttu-id="08764-248">使用 ATP 安全附件防護惡意附件和檔案</span><span class="sxs-lookup"><span data-stu-id="08764-248">Protect against malicious attachments and files with ATP Safe Attachments</span></span>

<span data-ttu-id="08764-249">人們經常傳送、接收及共用附件，例如文件、簡報和試算表等等。</span><span class="sxs-lookup"><span data-stu-id="08764-249">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="08764-250">只查看電子郵件訊息，不一定可輕易知道附件是否安全或有危害。</span><span class="sxs-lookup"><span data-stu-id="08764-250">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="08764-251">Office 365 的高級威脅防護包括 ATP 安全附件保護，但預設不會開啟此保護。</span><span class="sxs-lookup"><span data-stu-id="08764-251">Office 365 Advanced Threat Protection includes ATP Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="08764-252">建議您建立新的規則，以開始使用這種保護。</span><span class="sxs-lookup"><span data-stu-id="08764-252">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="08764-253">這項保護會延伸至 SharePoint、OneDrive 和 Microsoft 小組中的檔案。</span><span class="sxs-lookup"><span data-stu-id="08764-253">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>
  
<span data-ttu-id="08764-254">若要建立 ATP 安全附件原則，請觀看[這段簡短的影片](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="08764-254">To create an ATP safe attachment policy, either watch [this short video](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>
  
1. <span data-ttu-id="08764-255">移至 [https://protection.office.com](https://protection.office.com) ，然後使用您的系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="08764-255">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="08764-256">在安全性與 &amp; 合規性中心的左功能窗格中，選擇 [**威脅管理**] 底下的 [**原則**]。</span><span class="sxs-lookup"><span data-stu-id="08764-256">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="08764-257">在 [原則] 頁面上，選擇 [ **ATP 安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="08764-257">On the Policy page, choose **ATP safe attachments**.</span></span>
    
4. <span data-ttu-id="08764-258">在 [安全附件] 頁面上，選取 [**開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP** ] 核取方塊，廣泛套用此保護。</span><span class="sxs-lookup"><span data-stu-id="08764-258">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span> 
    
5. <span data-ttu-id="08764-259">選取 **+** 以建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="08764-259">Select **+** to create a new policy.</span></span> 
    
6. <span data-ttu-id="08764-260">套用下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="08764-260">Apply the settings in the following table.</span></span> 
    
7. <span data-ttu-id="08764-261">檢查您的設定之後，請選擇 [**建立這個原則**] 或 [**儲存**] （如適用）。</span><span class="sxs-lookup"><span data-stu-id="08764-261">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="08764-262">**設定或選項**</span><span class="sxs-lookup"><span data-stu-id="08764-262">**Setting or option**</span></span>|<span data-ttu-id="08764-263">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="08764-263">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="08764-264">名稱</span><span class="sxs-lookup"><span data-stu-id="08764-264">Name</span></span>  <br/> |<span data-ttu-id="08764-265">使用偵測到的惡意程式碼封鎖目前和未來的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="08764-265">Block current and future emails with detected malware.</span></span>  <br/> |
|<span data-ttu-id="08764-266">描述</span><span class="sxs-lookup"><span data-stu-id="08764-266">Description</span></span>  <br/> |<span data-ttu-id="08764-267">使用偵測到的惡意程式碼封鎖目前和未來的電子郵件和附件。</span><span class="sxs-lookup"><span data-stu-id="08764-267">Block current and future emails and attachments with detected malware.</span></span>  <br/> |
|<span data-ttu-id="08764-268">儲存附件未知的惡意程式碼回應</span><span class="sxs-lookup"><span data-stu-id="08764-268">Save attachments unknown malware response</span></span>  <br/> |<span data-ttu-id="08764-269">Select **Block-封鎖目前和未來的電子郵件和附件偵測到的惡意**代碼。</span><span class="sxs-lookup"><span data-stu-id="08764-269">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>  <br/> |
|<span data-ttu-id="08764-270">在偵測時重新導向附件</span><span class="sxs-lookup"><span data-stu-id="08764-270">Redirect attachment on detection</span></span>  <br/> |<span data-ttu-id="08764-271">啟用重新導向（選取此方塊）輸入系統管理員帳戶或隔離的信箱設定。</span><span class="sxs-lookup"><span data-stu-id="08764-271">Enable redirection (select this box)          Enter the admin account or a mailbox setup for quarantine.</span></span>          <span data-ttu-id="08764-272">若惡意程式碼掃描附件超時或發生錯誤，請套用上述選取範圍（選取此方塊）。</span><span class="sxs-lookup"><span data-stu-id="08764-272">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>  <br/> |
|<span data-ttu-id="08764-273">套用對象</span><span class="sxs-lookup"><span data-stu-id="08764-273">Applied to</span></span>  <br/> |<span data-ttu-id="08764-274">收件者網域是。</span><span class="sxs-lookup"><span data-stu-id="08764-274">The recipient domain is .</span></span> <span data-ttu-id="08764-275">.</span><span class="sxs-lookup"><span data-stu-id="08764-275">.</span></span> <span data-ttu-id="08764-276">.</span><span class="sxs-lookup"><span data-stu-id="08764-276">.</span></span> <span data-ttu-id="08764-277">選取您的網域。</span><span class="sxs-lookup"><span data-stu-id="08764-277">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="08764-278">如需詳細資訊，請參閱[設定 Office 365 ATP 反網路釣魚原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="08764-278">For more information, see [Set up Office 365 ATP anti-phishing policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).</span></span>
  
## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a><span data-ttu-id="08764-279">使用 ATP 安全連結防禦網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="08764-279">Protect against phishing attacks with ATP Safe Links</span></span>

<span data-ttu-id="08764-280">駭客有時候會在電子郵件或其他檔案的連結中隱藏惡意網站。</span><span class="sxs-lookup"><span data-stu-id="08764-280">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="08764-281">Office 365 ATP 安全連結（ATP 安全連結）是 Office 365 高級威脅防護的一部分，可在電子郵件訊息和 Office 檔中提供網頁位址（URLs）的時間驗證，以協助保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="08764-281">Office 365 ATP Safe Links (ATP Safe Links), part of Office 365 Advanced Threat Protection, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="08764-282">保護是透過 ATP 安全連結原則定義。</span><span class="sxs-lookup"><span data-stu-id="08764-282">Protection is defined through ATP Safe Links policies.</span></span>
  
<span data-ttu-id="08764-283">我們建議您執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="08764-283">We recommend that you do the following:</span></span>
  
- <span data-ttu-id="08764-284">修改預設原則以提升保護。</span><span class="sxs-lookup"><span data-stu-id="08764-284">Modify the default policy to increase protection.</span></span>
    
- <span data-ttu-id="08764-285">新增針對您網域中所有收件者的新原則。</span><span class="sxs-lookup"><span data-stu-id="08764-285">Add a new policy targeted to all recipients in your domain.</span></span>
    
<span data-ttu-id="08764-286">若要設定 ATP 安全連結，請觀看[這段簡短的訓練影片](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="08764-286">To set up ATP Safe Links, watch [this short training video](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>
  
1. <span data-ttu-id="08764-287">移至 [https://protection.office.com](https://protection.office.com) ，然後使用您的系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="08764-287">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="08764-288">在安全性與 &amp; 合規性中心的左功能窗格中，選擇 [**威脅管理**] 底下的 [**原則**]。</span><span class="sxs-lookup"><span data-stu-id="08764-288">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="08764-289">在 [原則] 頁面上，選擇 [ **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="08764-289">On the Policy page, choose **ATP Safe Links**.</span></span>
    
<span data-ttu-id="08764-290">若要修改預設原則：</span><span class="sxs-lookup"><span data-stu-id="08764-290">To modify the default policy:</span></span>
  
1. <span data-ttu-id="08764-291">在 [安全連結] 頁面上，于 [套用**至整個組織的原則**] 底下，選取**預設**原則。</span><span class="sxs-lookup"><span data-stu-id="08764-291">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span> 
    
2. <span data-ttu-id="08764-292">在 [**電子郵件除外，套用至內容**] 底下，選取 [適用于**企業的 Microsoft 365 應用程式、Office iOS 和 Android**]。</span><span class="sxs-lookup"><span data-stu-id="08764-292">Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.</span></span>
    
3. <span data-ttu-id="08764-293">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="08764-293">Select **Save**.</span></span> 
    
<span data-ttu-id="08764-294">若要建立新的原則針對您網域中的所有收件者：</span><span class="sxs-lookup"><span data-stu-id="08764-294">To create a new policy targeted to all recipients in your domain:</span></span>
  
1. <span data-ttu-id="08764-295">在 [安全連結] 頁面上，于 [套用**至整個組織的原則**] 底下，選取 [ **+** 建立新原則]。</span><span class="sxs-lookup"><span data-stu-id="08764-295">On the Safe links page, under **Policies that apply to the entire organization**, select **+** to create a new policy.</span></span> 
    
2. <span data-ttu-id="08764-296">套用下表所列的設定。</span><span class="sxs-lookup"><span data-stu-id="08764-296">Apply the settings listed in the following table.</span></span>
    
3. <span data-ttu-id="08764-297">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="08764-297">Select **Save**.</span></span> 

|<span data-ttu-id="08764-298">**設定或選項**</span><span class="sxs-lookup"><span data-stu-id="08764-298">**Setting or option**</span></span>|<span data-ttu-id="08764-299">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="08764-299">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="08764-300">名稱</span><span class="sxs-lookup"><span data-stu-id="08764-300">Name</span></span>  <br/> |<span data-ttu-id="08764-301">網域中所有收件者的安全連結原則</span><span class="sxs-lookup"><span data-stu-id="08764-301">Safe links policy for all recipients in the domain</span></span>  <br/> |
|<span data-ttu-id="08764-302">選取郵件中未知可能惡意 URLs 的動作</span><span class="sxs-lookup"><span data-stu-id="08764-302">Select the action for unknown potentially malicious URLs in messages</span></span>  <br/> |<span data-ttu-id="08764-303">選取 **[URLs 會在使用者按一下連結時，重新寫入並檢查已知惡意連結的清單**。</span><span class="sxs-lookup"><span data-stu-id="08764-303">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>  <br/> |
|<span data-ttu-id="08764-304">使用安全附件掃描可下載的內容</span><span class="sxs-lookup"><span data-stu-id="08764-304">Use Safe Attachments to scan downloadable content</span></span>  <br/> |<span data-ttu-id="08764-305">選取此方塊。</span><span class="sxs-lookup"><span data-stu-id="08764-305">Select this box.</span></span>  <br/> |
|<span data-ttu-id="08764-306">套用對象</span><span class="sxs-lookup"><span data-stu-id="08764-306">Applied to</span></span>  <br/> |<span data-ttu-id="08764-307">收件者網域是。</span><span class="sxs-lookup"><span data-stu-id="08764-307">The recipient domain is .</span></span> <span data-ttu-id="08764-308">.</span><span class="sxs-lookup"><span data-stu-id="08764-308">.</span></span> <span data-ttu-id="08764-309">.</span><span class="sxs-lookup"><span data-stu-id="08764-309">.</span></span> <span data-ttu-id="08764-310">選取您的網域。</span><span class="sxs-lookup"><span data-stu-id="08764-310">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="08764-311">如需詳細資訊，請參閱[Office 365 ATP 安全連結](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="08764-311">For more information, see [Office 365 ATP safe links](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="08764-312">移至 Intune 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="08764-312">Go to Intune admin center</span></span>

1. <span data-ttu-id="08764-313">登入[Azure 入口網站](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="08764-313">Sign in to [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="08764-314">在 [**搜尋**] 方塊中選取 [**所有服務**]，然後輸入*Intune* 。</span><span class="sxs-lookup"><span data-stu-id="08764-314">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="08764-315">結果出現之後，請選取 [ **Microsoft Intune** ] 旁邊的 [開始]，讓它成為最愛，稍後便可輕鬆尋找。</span><span class="sxs-lookup"><span data-stu-id="08764-315">Once the results appear, select the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="08764-316">除了系統管理中心之外，您還可以使用 Intune 來註冊和管理您組織的裝置。</span><span class="sxs-lookup"><span data-stu-id="08764-316">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="08764-317">如需詳細資訊，請參閱[Windows 裝置的註冊方法](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab)及[Intune 所管理裝置的註冊選項](https://docs.microsoft.com/intune/enrollment-options)的功能。</span><span class="sxs-lookup"><span data-stu-id="08764-317">For more information, see [Capabilities by enrollment method for Windows devices](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) and [Enrollment options for devices managed by Intune](https://docs.microsoft.com/intune/enrollment-options).</span></span>
