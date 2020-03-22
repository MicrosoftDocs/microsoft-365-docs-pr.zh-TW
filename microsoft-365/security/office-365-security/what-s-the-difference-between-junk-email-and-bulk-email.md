---
title: 垃圾郵件和大量電子郵件有什麼不同?
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/7/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: 客戶有時候會 askwhat 垃圾郵件和大量電子郵件之間的差異？本主題的目的在於說明差異，並提供 Exchange Online 和 Exchange Online Protection （EOP）中提供的不同選項的相關資訊。
ms.openlocfilehash: 55924ac5e83ca109fd66d1723cdb7c5f43f20df6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895032"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="d952a-103">垃圾郵件和大量電子郵件有什麼不同?</span><span class="sxs-lookup"><span data-stu-id="d952a-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="d952a-p101">客戶有時會問「垃圾郵件和大量電子郵件有什麼不同?」。本主題旨在說明其中差異，並提供關於 Exchange Online 和 Exchange Online Protection (EOP) 中針對這兩種郵件而提供之不同選項的資訊。</span><span class="sxs-lookup"><span data-stu-id="d952a-p101">Customers sometimes ask "what's the difference between junk email and bulk email messages?" The purpose of this topic is to explain the difference and to provide information about the different options that are available for both in Exchange Online and Exchange Online Protection (EOP).</span></span>
  
 <span data-ttu-id="d952a-106">**什麼是垃圾郵件？**</span><span class="sxs-lookup"><span data-stu-id="d952a-106">**What's junk email?**</span></span>
  
<span data-ttu-id="d952a-p102">垃圾郵件是一種「垃圾」郵件，即服務所篩選的來路不明 (通常是不想要的) 電子郵件。服務預設會根據傳送端 IP 位址的信譽來拒絕垃圾郵件。不過，郵件如果通過 IP 檢查、但被內容篩選分類為垃圾郵件，則會傳送至預定收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d952a-p102">Junk email messages are "spam" messages, which are unsolicited (and typically unwanted) email messages that are filtered by the service. By default, the service rejects the spam message based on the reputation of the sending IP address. However, if it passes IP inspection but is classified as spam by the content filters, the message is sent to the Junk Email folder of the intended recipients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d952a-110">對內容篩選郵件執行的動作可透過 Exchange 系統管理中心（EAC）中的內容篩選原則加以設定，如[Office 365 中的設定反垃圾郵件原則](configure-your-spam-filter-policies.md)所述。</span><span class="sxs-lookup"><span data-stu-id="d952a-110">The action performed on content-filtered messages is configurable via content filter policies in the Exchange admin center (EAC), as described in [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="d952a-111">此外，如果您不同意垃圾郵件分類，您可以透過幾種方式來報告您認為是垃圾郵件或非垃圾郵件的郵件，如[將垃圾郵件、非垃圾郵件和網路釣魚詐騙郵件提交給 microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)所述。</span><span class="sxs-lookup"><span data-stu-id="d952a-111">Also, if you disagree with the spam classification, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> 
  
 <span data-ttu-id="d952a-112">**什麼是大量電子郵件？**</span><span class="sxs-lookup"><span data-stu-id="d952a-112">**What's bulk email?**</span></span>
  
<span data-ttu-id="d952a-p104">大量電子郵件 (也稱為灰色郵件) 是一種較難分類出來的電子郵件類型。不像垃圾郵件是一種持續性威脅，大量電子郵件通常不太包含會重傳的廣告或行銷訊息。有些使用者想要大量電子郵件 (事實上，他們可能刻意登記要收到這些郵件)，有些使用者則認為這類郵件是垃圾郵件。例如，有些使用者想要收到 Contoso Corporation 寄來的廣告電子郵件或未來某個網路安全大會的邀請，有些使用者則認為這類電子郵件是垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d952a-p104">Bulk email, also referred to as gray mail, is a type of email message that's more difficult to classify. Whereas junk email is a constant threat, bulk email is typically comprised of an advertisement or marketing message that's not likely to get sent repeatedly. Bulk email is wanted by some users, and in fact they may have deliberately signed up to receive these messages, while other users may consider these types of messages to be spam. For example, some users want to receive advertising emails from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider such emails to be spam.</span></span>
  
## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="d952a-117">如何管理大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="d952a-117">How to manage bulk email</span></span>

<span data-ttu-id="d952a-p105">要如何管理大量電子郵件，這並不是個非黑即白的決策，因為如果將所有大量電子郵件都分類為垃圾郵件，則想要它的使用者可能會抱怨並將它提交成誤標記為垃圾郵件的誤判 (非垃圾郵件) 郵件。另一方面，如果讓所有大量電子郵件都通過，則不想要它的使用者可能會抱怨並將它提交成誤進收件匣的漏擋垃圾郵件 (誤判正常)。</span><span class="sxs-lookup"><span data-stu-id="d952a-p105">How to manage bulk email isn't a clear cut decision, because if all bulk email is classified as spam, the users that want it may complain and submit it as a false positive (non-spam) message that was wrongly marked as spam. On the other hand, if all bulk email is let through, the users that don't want it may complain and submit it as a missed spam message (false negative) that wrongly arrived in their inbox.</span></span>
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a><span data-ttu-id="d952a-120">在內容篩選原則中啟用大宗郵件敏感度控制</span><span class="sxs-lookup"><span data-stu-id="d952a-120">Enable bulk mail sensitivity control in the content filter policy</span></span>

<span data-ttu-id="d952a-121">根據您公司在大量電子郵件上的原則，系統管理員可以選擇指派大量電子郵件的臨界值。</span><span class="sxs-lookup"><span data-stu-id="d952a-121">Depending on your company's policy on bulk email messages, admins can select a threshold to assign the bulk email.</span></span> <span data-ttu-id="d952a-122">設定可透過 EAC 中的內容篩選原則加以設定。</span><span class="sxs-lookup"><span data-stu-id="d952a-122">The setting is configurable via content filter policies in the EAC.</span></span> <span data-ttu-id="d952a-123">如需步驟，請參閱[Office 365 中的設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d952a-123">Check out [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md) for the steps.</span></span> <span data-ttu-id="d952a-124">您可以選擇1-9 中的臨界值設定，其中1將最大的大量電子郵件標記為垃圾郵件，而9則可以傳遞大多數大量電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d952a-124">You can choose a threshold setting from 1-9, where 1 marks most bulk email as spam, and 9 allows most bulk email to be delivered.</span></span> <span data-ttu-id="d952a-125">服務則會執行已設定的動作 (例如將郵件傳送至收件者的 [垃圾郵件] 資料夾)。</span><span class="sxs-lookup"><span data-stu-id="d952a-125">The service then performs the configured action, such as sending the message to the recipient's Junk Email folder.</span></span> 
  

