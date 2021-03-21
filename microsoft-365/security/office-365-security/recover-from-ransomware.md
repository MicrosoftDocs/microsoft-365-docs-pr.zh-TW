---
title: 從勒索軟體的攻擊中復原
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 系統管理員可以瞭解如何從勒索軟體的攻擊復原。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 21a6dc4cca2aac189740f2dba4ed10dc865792a6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922893"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="f9a51-103">從 Microsoft 365 復原勒索軟體攻擊</span><span class="sxs-lookup"><span data-stu-id="f9a51-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f9a51-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="f9a51-104">**Applies to**</span></span>
- [<span data-ttu-id="f9a51-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f9a51-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f9a51-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="f9a51-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f9a51-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9a51-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f9a51-108">即使您採取每一種防範措施保護您的組織，您還是可以遭到 [勒索軟體](/windows/security/threat-protection/intelligence/ransomware-malware) 攻擊的受害人。</span><span class="sxs-lookup"><span data-stu-id="f9a51-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="f9a51-109">勒索軟體是大型企業，攻擊非常複雜。</span><span class="sxs-lookup"><span data-stu-id="f9a51-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="f9a51-110">本文中的步驟可讓您最有可能復原資料，並停止感染的內部傳播。</span><span class="sxs-lookup"><span data-stu-id="f9a51-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="f9a51-111">在您開始之前，請考慮下列項目：</span><span class="sxs-lookup"><span data-stu-id="f9a51-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="f9a51-112">不保證支付 ransom 將會傳回檔案的存取權。</span><span class="sxs-lookup"><span data-stu-id="f9a51-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="f9a51-113">實際上，支付 ransom 可讓您成為更多勒索軟體的目標。</span><span class="sxs-lookup"><span data-stu-id="f9a51-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="f9a51-114">如果您已付費，但已復原但未使用攻擊者的解決方案，請與您的銀行聯繫以查看是否可以封鎖交易。</span><span class="sxs-lookup"><span data-stu-id="f9a51-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="f9a51-115">我們也建議您向法律強制執行、詐騙報告網站和 Microsoft 報告勒索軟體攻擊，如本文稍後所述。</span><span class="sxs-lookup"><span data-stu-id="f9a51-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="f9a51-116">您必須快速回應攻擊及其結果，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="f9a51-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="f9a51-117">您等候的時間越長，您可以復原受影響資料的可能性也就越低。</span><span class="sxs-lookup"><span data-stu-id="f9a51-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="f9a51-118">步驟1：驗證備份</span><span class="sxs-lookup"><span data-stu-id="f9a51-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="f9a51-119">如果您有離線備份，您可能會在您從環境中移除勒索軟體的負載 (惡意程式碼) **之後** 還原加密的資料。</span><span class="sxs-lookup"><span data-stu-id="f9a51-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="f9a51-120">如果您沒有備份，或是您的備份也受到勒索軟體的影響，您可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="f9a51-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="f9a51-121">步驟2：停用 Exchange ActiveSync 和 OneDrive 同步處理</span><span class="sxs-lookup"><span data-stu-id="f9a51-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="f9a51-122">這裡的關鍵點是停止勒索軟體加密的資料加密。</span><span class="sxs-lookup"><span data-stu-id="f9a51-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="f9a51-123">如果您懷疑電子郵件為勒索軟體加密的目標，請暫時停用使用者對信箱的存取。</span><span class="sxs-lookup"><span data-stu-id="f9a51-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="f9a51-124">Exchange ActiveSync 會同步處理裝置和 Exchange Online 信箱之間的資料。</span><span class="sxs-lookup"><span data-stu-id="f9a51-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="f9a51-125">若要停用信箱的 Exchange ActiveSync，請參閱 [如何為 Exchange Online 中的使用者停用 exchange ActiveSync](https://support.microsoft.com/help/2795303)。</span><span class="sxs-lookup"><span data-stu-id="f9a51-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="f9a51-126">若要停用信箱的其他類型的存取，請參閱：</span><span class="sxs-lookup"><span data-stu-id="f9a51-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="f9a51-127">[啟用或停用信箱的 MAPI](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。</span><span class="sxs-lookup"><span data-stu-id="f9a51-127">[Enable or disable MAPI for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="f9a51-128">啟用或停用使用者 POP3 或 IMAP4 存取權</span><span class="sxs-lookup"><span data-stu-id="f9a51-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="f9a51-129">暫停 OneDrive 同步處理會協助保護您的雲端資料，使其不會受到可能受感染的裝置更新。</span><span class="sxs-lookup"><span data-stu-id="f9a51-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="f9a51-130">如需詳細資訊，請參閱 how [To Pause And Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。</span><span class="sxs-lookup"><span data-stu-id="f9a51-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="f9a51-131">步驟3：從受影響的裝置移除惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="f9a51-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="f9a51-132">在所有置疑的電腦和裝置上執行完整、目前的防病毒掃描，以偵測和移除與勒索軟體相關聯的負載。</span><span class="sxs-lookup"><span data-stu-id="f9a51-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="f9a51-133">請勿忘記掃描正在同步處理之資料的裝置，或對應網路磁碟機的目標。</span><span class="sxs-lookup"><span data-stu-id="f9a51-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="f9a51-134">您可以將 [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) 或 (用於舊版用戶端) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)。</span><span class="sxs-lookup"><span data-stu-id="f9a51-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="f9a51-135">另一種方式也可協助您移除勒索軟體或惡意軟體是 [惡意軟體移除工具 (MSRT) ](https://www.microsoft.com/download/details.aspx?id=9905)。</span><span class="sxs-lookup"><span data-stu-id="f9a51-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="f9a51-136">如果這些選項不起作用，您可以嘗試使用 [Windows Defender 離線](https://support.microsoft.com/help/17466) 或 [疑難排解偵測和移除惡意程式碼的問題](https://support.microsoft.com/help/4466982)。</span><span class="sxs-lookup"><span data-stu-id="f9a51-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="f9a51-137">步驟4：在已清除的電腦或裝置上復原檔案</span><span class="sxs-lookup"><span data-stu-id="f9a51-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="f9a51-138">在您完成上述步驟以從環境中移除勒索軟體負載 (（該負載會使勒索軟體無法加密或移除) 您的檔案）之後，您可以使用 windows 10 和 Windows 8.1 中的檔案歷程 [記錄](https://support.microsoft.com/help/17128) ，或 windows 7 中的系統保護，以嘗試復原您的本機檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="f9a51-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="f9a51-139">**附註**：</span><span class="sxs-lookup"><span data-stu-id="f9a51-139">**Notes**:</span></span>

- <span data-ttu-id="f9a51-140">有些勒索軟體也會加密或刪除備份版本，因此您無法使用檔案記錄或系統保護來還原檔案。</span><span class="sxs-lookup"><span data-stu-id="f9a51-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="f9a51-141">如果發生這種情況，您需要在外部磁片磁碟機或未受勒索軟體或 OneDrive 的裝置上使用備份，如下一節所述。</span><span class="sxs-lookup"><span data-stu-id="f9a51-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="f9a51-142">如果資料夾與 OneDrive 同步處理，而且您不是使用最新版的 Windows，則可能會有一些限制使用檔案歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="f9a51-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="f9a51-143">步驟5：在您的 OneDrive 商務中復原檔案</span><span class="sxs-lookup"><span data-stu-id="f9a51-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="f9a51-144">在 OneDrive for Business 中還原檔案，可讓您在過去的30天內，將整個 OneDrive 還原至上一個時間點。</span><span class="sxs-lookup"><span data-stu-id="f9a51-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="f9a51-145">如需詳細資訊，請參閱 [還原您的 OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)。</span><span class="sxs-lookup"><span data-stu-id="f9a51-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="f9a51-146">步驟6：復原已刪除的電子郵件</span><span class="sxs-lookup"><span data-stu-id="f9a51-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="f9a51-147">在少數情況下，勒索軟體會刪除所有的電子郵件，您可能會復原已刪除的郵件。</span><span class="sxs-lookup"><span data-stu-id="f9a51-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="f9a51-148">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="f9a51-148">For more information, see:</span></span>

- [<span data-ttu-id="f9a51-149">復原刪除的郵件使用者的信箱</span><span class="sxs-lookup"><span data-stu-id="f9a51-149">Recover deleted messages in a user's mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="f9a51-150">在 Windows 版 Outlook 復原已刪除的項目</span><span class="sxs-lookup"><span data-stu-id="f9a51-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="f9a51-151">步驟7：重新啟用 Exchange ActiveSync 和 OneDrive 同步處理</span><span class="sxs-lookup"><span data-stu-id="f9a51-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="f9a51-152">在您清潔電腦和裝置並復原資料之後，您可以重新啟用 Exchange ActiveSync 和您先前在 [步驟 2](#step-2-disable-exchange-activesync-and-onedrive-sync)中停用 OneDrive 同步處理。</span><span class="sxs-lookup"><span data-stu-id="f9a51-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="f9a51-153">步驟 8 (選用) ：封鎖特定檔案副檔名 OneDrive 同步處理</span><span class="sxs-lookup"><span data-stu-id="f9a51-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="f9a51-154">復原之後，您可以防止商務用戶端的 OneDrive 同步處理此勒索軟體所影響的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="f9a51-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="f9a51-155">如需詳細資訊，請參閱 [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="f9a51-155">For more information, see [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="f9a51-156">報告攻擊</span><span class="sxs-lookup"><span data-stu-id="f9a51-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="f9a51-157">連絡人法律強制執行</span><span class="sxs-lookup"><span data-stu-id="f9a51-157">Contact law enforcement</span></span>

<span data-ttu-id="f9a51-158">您應與當地或聯邦執法機構聯繫。</span><span class="sxs-lookup"><span data-stu-id="f9a51-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="f9a51-159">例如，如果您在美國，您可以聯繫 [FBI 當地欄位 office](https://www.fbi.gov/contact-us/field)、 [IC3](http://www.ic3.gov/complaint/default.aspx) 或 [機密服務](http://www.secretservice.gov/)。</span><span class="sxs-lookup"><span data-stu-id="f9a51-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="f9a51-160">將報告提交至您的國家/地區的騙局報告網站</span><span class="sxs-lookup"><span data-stu-id="f9a51-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="f9a51-161">騙局報告網站提供如何防止和避免詐騙的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f9a51-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="f9a51-162">當您是騙局的受害者時，也會提供要報告的機制。</span><span class="sxs-lookup"><span data-stu-id="f9a51-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="f9a51-163">澳大利亞： [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="f9a51-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="f9a51-164">加拿大： [加拿大反欺詐中心](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="f9a51-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="f9a51-165">法國： [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="f9a51-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="f9a51-166">德國： [Bundesamt Für Sicherheit in Der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="f9a51-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="f9a51-167">愛爾蘭： a [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="f9a51-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="f9a51-168">紐西蘭： [使用者事務詐騙](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="f9a51-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="f9a51-169">英國： [動作欺詐](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="f9a51-169">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="f9a51-170">美國： [線上防護](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="f9a51-170">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="f9a51-171">如果您的國家/地區未列出，請諮詢您的當地或聯邦執法機構。</span><span class="sxs-lookup"><span data-stu-id="f9a51-171">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="f9a51-172">將電子郵件提交至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="f9a51-172">Submit email messages to Microsoft</span></span>

<span data-ttu-id="f9a51-173">您可以使用數種方法中的其中一種，報告包含勒索軟體的網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="f9a51-173">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="f9a51-174">如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="f9a51-174">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9a51-175">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f9a51-175">See also</span></span>

- [<span data-ttu-id="f9a51-176">軟體</span><span class="sxs-lookup"><span data-stu-id="f9a51-176">Ransomware</span></span>](/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="f9a51-177">勒索軟體回應-支付或不支付費用？</span><span class="sxs-lookup"><span data-stu-id="f9a51-177">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="f9a51-178">Norsk Hydro 會以透明度回應勒索軟體攻擊</span><span class="sxs-lookup"><span data-stu-id="f9a51-178">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="f9a51-179">勒索軟體偵測和復原 OneDrive 中的檔案</span><span class="sxs-lookup"><span data-stu-id="f9a51-179">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="f9a51-180">Microsoft Security 情報報告</span><span class="sxs-lookup"><span data-stu-id="f9a51-180">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="f9a51-181">啟用或停用 Office 檔案中的宏</span><span class="sxs-lookup"><span data-stu-id="f9a51-181">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="f9a51-182">EOP 和 Microsoft Defender for Office 365 安全性的建議設定</span><span class="sxs-lookup"><span data-stu-id="f9a51-182">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="f9a51-183">值得升級： Windows 10 上的下一代安全性會為2017中的勒索軟體的爆發，證實其可復原</span><span class="sxs-lookup"><span data-stu-id="f9a51-183">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="f9a51-184">沒有 ma，Samas：在此勒索軟體的 modus operandi 中有哪些？</span><span class="sxs-lookup"><span data-stu-id="f9a51-184">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="f9a51-185">Locky 惡意程式碼（幸運）以避免出現</span><span class="sxs-lookup"><span data-stu-id="f9a51-185">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="f9a51-186">MSRT 2016 年7月： Cerber 勒索軟體</span><span class="sxs-lookup"><span data-stu-id="f9a51-186">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="f9a51-187">Cerberus 的三個機頭（如 Cerber）勒索軟體</span><span class="sxs-lookup"><span data-stu-id="f9a51-187">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="f9a51-188"> () Da Vinci 程式碼影響的 Troldesh 勒索軟體</span><span class="sxs-lookup"><span data-stu-id="f9a51-188">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)