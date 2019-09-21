---
title: 如何減少 Office 365 中的垃圾郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/07/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: 了解最常用來協助減少 Office 365 中垃圾郵件的方式。
ms.openlocfilehash: d99b5e1452c60be713f0f4cfbab965d30eeeb8ef
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077995"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a><span data-ttu-id="0b78a-103">如何減少 Office 365 中的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="0b78a-103">How to reduce spam email in Office 365</span></span>

 <span data-ttu-id="0b78a-104">**您在 Office 365 收到太多垃圾郵件嗎？請執行此動作。**</span><span class="sxs-lookup"><span data-stu-id="0b78a-104">**Are you getting too much spam in Office 365? Do this.**</span></span>
  
<span data-ttu-id="0b78a-p101">我們強烈建議您使用[回報郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)來報告誤判郵件，以協助我們改進我們的篩選器。此外，您可以使用[提交總管](admin-submission.md)來提交郵件。</span><span class="sxs-lookup"><span data-stu-id="0b78a-p101">We strongly recommend that you report False Negative messages by [using the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) to help us improve our filters. Additionally, you can forward the message [as an attachment](admin-submission.md) to junk@office365.microsoft.com or phish@office365.microsoft.com (if it was phish).</span></span>

> [!TIP]
> <span data-ttu-id="0b78a-p102">如果您認為郵件是垃圾郵件，而且郵件也位於垃圾郵件資料夾，那就沒有問題。如果您完全不想在信箱中看到垃圾郵件，則應該變更反垃圾郵件原則來隔離郵件。如需隔離郵件的詳細資訊，請參閱[隔離Office 365 中的電子郵件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="0b78a-p102">If you think the message is junk and it is in the Junk Email folder, that should not be a problem. If you don't want to see it at all in the mailbox, you should change the antispam policy to quarantine the message. More information on quarantining a message can be found in [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

## <a name="fixing-allowed-spam"></a><span data-ttu-id="0b78a-110">修正允許的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="0b78a-110">Fixing allowed spam</span></span>

<span data-ttu-id="0b78a-p103">我們經常看到客戶因為設定錯誤而將垃圾郵件收到收件匣中。其中最常見的是在郵件流程規則 (也稱為傳輸規則) 中將網域設定為繞過篩選器，或將您的網域設定在允許/安全寄件者清單中。這樣不好，因為原本會被攔截的這些郵件會跳過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="0b78a-p103">We often see that customers get junk mail into their inbox because of incorrect configurations. The most common of which is configuring your domains in a mail flow rule (also known as a transport rule) to bypass filters or listing your domain(s) in the allowed/safe-senders list. This is not good because these messages skip spam filtering and could have otherwise been caught.</span></span>  

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a><span data-ttu-id="0b78a-114">收到太多垃圾郵件的其他常見原因解決方案</span><span class="sxs-lookup"><span data-stu-id="0b78a-114">Solutions to other common causes of getting too much spam</span></span>

<span data-ttu-id="0b78a-p104">為了保護您免於收到太多垃圾郵件，Exchange Online Protection (EOP) 需要系統管理員完成一些工作。如果您不是 Office 365 租用戶的系統管理員，而且收到太多垃圾郵件，則您可能會想要與您的系統管理員合作處理這些工作。否則，您可以跳至使用者區段。</span><span class="sxs-lookup"><span data-stu-id="0b78a-p104">In order to protect you from getting too much spam, Exchange Online Protection (EOP) requires that administrators complete a few tasks. If you are not the administrator for your Office 365 tenant and you are getting too much spam, then you may want to work with your administrator on these tasks. Otherwise, you can skip to the user section.</span></span>
  
### <a name="for-admins"></a><span data-ttu-id="0b78a-118">若為系統管理員</span><span class="sxs-lookup"><span data-stu-id="0b78a-118">For admins</span></span>

- <span data-ttu-id="0b78a-p105">**將您的 DNS 記錄指向 Office 365** 為了讓 EOP 提供最佳防護，所有網域的郵件交換程式 (MX) DNS 記錄都必須指向 Office 365，而且只能指向 Office 365。請參閱[當您管理 DNS 記錄時建立 Office 365 的 DNS 記錄](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)。</span><span class="sxs-lookup"><span data-stu-id="0b78a-p105">**Point your DNS records to Office 365** In order for EOP to provide the best protection, your mail exchanger (MX) DNS record(s) for all domains must be pointed to Office 365 -- and only to Office 365. See [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span></span>
    
- <span data-ttu-id="0b78a-p106">**啟用所有信箱上的垃圾郵件規則** 根據預設，垃圾郵件篩選動作會設為 [將郵件移至垃圾郵件資料夾]\*\*\*\*。如果這是您目前喜好的垃圾郵件原則動作，則每個信箱[也須啟用垃圾郵件規則](https://support.office.com/zh-TW/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。若要進行此檢查，您可以對一或多個信箱執行 Get-MailboxJunkEmailConfiguration Cmdlet。例如，您可能會對所有信箱進行此檢查，方法為執行 Cmdlet：Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}</span><span class="sxs-lookup"><span data-stu-id="0b78a-p106">**Enable the junk mail rule on all mailboxes** By default, the spam filtering action is set to **Move message to Junk Email folder**. If this is the preferred and current spam policy action, then each mailbox [must also have the junk mail rule enabled](https://support.office.com/zh-TW/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). To check this, you can run the Get-MailboxJunkEmailConfiguration cmdlet against one or more mailboxes. For example, you might check all mailboxes for this by running the following: Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}</span></span>
    
    <span data-ttu-id="0b78a-p107">檢視輸出時，Enable 屬性應設為 True。如果設為 False，您可以執行 Set-MailboxJunkEmailConfiguration 將其變更為 True，如下所示：Set-MailboxJunkEmailConfiguration -Identity $values.UserPrincipalName -Enabled $true。</span><span class="sxs-lookup"><span data-stu-id="0b78a-p107">When viewing the output, the Enable property should be set to True. If it is set to False, you can run Set-MailboxJunkEmailConfiguration to change it to True.</span></span>
    
- <span data-ttu-id="0b78a-p108">**在內部部署 Exchange Server 中建立郵件流程規則** 如果您使用的是 Exchange Online Protection，但您的信箱位於內部部署 Exchange Server，則您需要在內部部署 Exchange Server 中建立幾個郵件流程規則。請參閱 [EOP 專屬的指示](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150))。</span><span class="sxs-lookup"><span data-stu-id="0b78a-p108">**Create mail flow rules in on-premises Exchange Server** If you are using Exchange Online Protection, but your mailboxes are located in on-premises Exchange Server, then you will need to create a couple of mail flow rules in on-premises Exchange Server. See the [instructions for EOP-only](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)).</span></span>
    
- <span data-ttu-id="0b78a-p109">**將大量電子郵件標示為垃圾郵件** 大量電子郵件是使用者可能已註冊，但仍有可能不想要的電子郵件。在郵件標頭中，於 X-Microsoft-Antispam 標頭中尋找 BCL (大量信賴等級) 屬性。如果 BCL 值小於垃圾郵件篩選器中設定的閾值，您可能想要調整閾值，而不是將這些類型的大宗郵件標示為垃圾郵件。不同的使用者對於[大量電子郵件的處理方式](https://docs.microsoft.com/zh-TW/office365/SecurityCompliance/bulk-complaint-level-values) 各有不同的容錯和喜好設定。您可以針對不同的使用者喜好設定建立不同的原則或規則。</span><span class="sxs-lookup"><span data-stu-id="0b78a-p109">**Mark bulk email as spam** Bulk email is email which users may have signed up for, but may still be undesirable. In the message header, find the BCL (Bulk Confidence Level) property in the X-Microsoft-Antispam header. If the BCL value is less than the threshold set in the spam filter, you may want to adjust the threshold to instead mark these types of bulk messages as spam. Different users have different tolerances and preferences for [how bulk email](https://docs.microsoft.com/zh-TW/office365/SecurityCompliance/bulk-complaint-level-values) is handled. You can create different policies or rules for different user preferences.</span></span> 
    
- <span data-ttu-id="0b78a-p110">**立即封鎖寄件者** 在您需要立即封鎖寄件者的情況下，您可以依電子郵件地址、網域或 IP 位址進行封鎖。請參閱[在 Office 365 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。使用者允許清單中的項目可以覆寫系統管理員所設定的封鎖。</span><span class="sxs-lookup"><span data-stu-id="0b78a-p110">**Immediately block a sender** In the case where you need to immediately block a sender, you can block by email address, domain, or IP address. See [Block email spam with the Office 365 spam filter to prevent false negative issues](create-block-sender-lists-in-office-365.md). An entry in an end-user allow list can override a block set by the administrator.</span></span>
    
- <span data-ttu-id="0b78a-137">**開啟使用者的回報郵件增益集**：我們強烈建議您[為使用者啟用回報郵件增益集](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="0b78a-137">**Turn on the report message add-in for users** We strongly recommend that you [enable the report message add-in for you users](enable-the-report-message-add-in.md). As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>

- <span data-ttu-id="0b78a-138">**使用[提交總管](admin-submission.md)** 系統管理員現在可以使用檔案或網路訊息 ID、URL 以及 Microsoft Office 365 掃描的檔案來傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0b78a-138">**Use [Submissions Explorer](admin-submission.md)** Admins can now send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span> <span data-ttu-id="0b78a-139">身為系統管理員，您也能夠檢視使用者傳送的意見反應，並使用任何模式來調整任何可能造成問題的設定。</span><span class="sxs-lookup"><span data-stu-id="0b78a-139">Turn on the report message add-in for users We strongly recommend that you enable the report message add-in for you users. As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>

- <span data-ttu-id="0b78a-140">**啟用 [DKIM](use-dkim-to-validate-outbound-email.md)** 以簽署所有外寄郵件，藉此提高您的網域和租用戶中的安全性。</span><span class="sxs-lookup"><span data-stu-id="0b78a-140">**Enable [DKIM](use-dkim-to-validate-outbound-email.md)** to sign all your outbound messages to increase the security in your domain and tenant.</span></span>
 > [!TIP]
> <span data-ttu-id="0b78a-141">啟用 DKIM 之後，您必須啟用 [DMARC](use-dkim-to-validate-outbound-email.md)，因為此記錄會驗證 DKIM 和 SPF 是否正確運作，而一般來說，因為 O365 會管理您的私人和公用對稱金鑰，偽造的電子郵件不會有簽章。</span><span class="sxs-lookup"><span data-stu-id="0b78a-141">After you enable DKIM you must enable [DMARC](use-dkim-to-validate-outbound-email.md) since this record will validate if DKIM and SPF are working correctly and, generally, spoofing emails don't have the signature, since O365 manages your private and public symmetric key.</span></span>
    
### <a name="for-users"></a><span data-ttu-id="0b78a-142">若為使用者</span><span class="sxs-lookup"><span data-stu-id="0b78a-142">For users</span></span>

- <span data-ttu-id="0b78a-p112">**啟用垃圾郵件規則，並檢查您的允許清單** 檢查垃圾郵件動作規則是否已啟用，以及寄件者或寄件者的網域是否未設為要在您的個人允許清單中略過。存取這些設定的最佳方式來自[封鎖或允許 (垃圾郵件設定)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)。當您在那裡時，也可以選擇封鎖寄件者的電子郵件地址或網域。</span><span class="sxs-lookup"><span data-stu-id="0b78a-p112">**Enable the junk mail rule and check your allow list** Check that the junk mail action rule is enabled and that the sender or sender's domain is not set to bypass in your personal allow list. The best way to access these settings is from [Block or allow (junk email settings)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). While you are there, you may also choose to block the sender's email address or domain.</span></span>
    
- <span data-ttu-id="0b78a-146">**向 Microsoft 回報垃圾郵件**：請使用[使用回報郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) 將垃圾郵件回報給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="0b78a-146">**Report spam to Microsoft** Report spam messages to Microsoft by using the [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Additionally, you can send a message to junk@office365.microsoft.com and attach one or more messages to report.</span></span>
       
- <span data-ttu-id="0b78a-p113">**從大量電子郵件取消訂閱** 如果郵件是您已註冊的項目 (例如電子報、產品公告等)，而且其包含的連結來自聲譽卓著的來源，則您可能只想取消訂閱。Office 365 通常不會將這些郵件視為垃圾郵件。您也可以選擇封鎖寄件者，或要求系統管理員進行將導致所有大宗郵件被視為垃圾郵件的變更。</span><span class="sxs-lookup"><span data-stu-id="0b78a-p113">**Unsubscribe from bulk email** If the message was something that you signed up for (newsletters, product announcements, etc.) and contains an unsubscribe link from a reputable source, you may want to simply unsubscribe. Office 365 does not typically treat these messages as spam. You can also choose to block the sender, or ask your administrator to make a change that will cause all bulk mail to be treated as spam.</span></span>
