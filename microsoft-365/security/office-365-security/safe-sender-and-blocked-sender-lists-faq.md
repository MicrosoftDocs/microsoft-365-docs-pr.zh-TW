---
title: Exchange Online 中的安全寄件者和封鎖寄件者清單
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: 以 Exchange Online 或 Exchange Online Protection (EOP) 系統管理員身分，您可以協助確保服務透過電子郵件訊息不會標示為垃圾郵件。 若要這麼做的一種方式是貴組織中的人員來建立安全寄件者和封鎖的寄件者清單。
ms.openlocfilehash: 03d0bb35f174b1dcc76fa93f5a5411e8a437ea25
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031778"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="ef97f-104">Exchange Online 中的安全寄件者和封鎖寄件者清單</span><span class="sxs-lookup"><span data-stu-id="ef97f-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="ef97f-105">以 Exchange Online 或 Exchange Online Protection (EOP) 系統管理員身分，您可以協助確保服務透過電子郵件訊息不會標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="ef97f-105">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam.</span></span> <span data-ttu-id="ef97f-106">若要這麼做的一種方式是貴組織中的人員來建立安全寄件者和封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="ef97f-106">One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span> 
  
 <span data-ttu-id="ef97f-107">*請參閱更新的版的秘訣和程序說明如何使用身為系統管理員在這些清單*[防止誤判電子郵件標示為垃圾郵件安全清單或其他技術](https://go.microsoft.com/fwlink/p/?LinkID=534224)。</span><span class="sxs-lookup"><span data-stu-id="ef97f-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span></span> 
  
<span data-ttu-id="ef97f-108">如果您不是系統管理員，而且您只想要管理自己在 Outlook 中的垃圾郵件所使用的安全寄件者清單，請參閱本概觀[垃圾郵件篩選器](https://go.microsoft.com/fwlink/?LinkId=817222)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="ef97f-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in this overview of [the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=817222).</span></span> 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="ef97f-109">什麼是安全及封鎖寄件者限制在 Exchange Online 嗎？</span><span class="sxs-lookup"><span data-stu-id="ef97f-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="ef97f-110">Exchange Online 中的安全及封鎖的寄件者限制跟在 Active Directory，以及 Outlook 限制。</span><span class="sxs-lookup"><span data-stu-id="ef97f-110">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits.</span></span> <span data-ttu-id="ef97f-111">其中包括：</span><span class="sxs-lookup"><span data-stu-id="ef97f-111">They are:</span></span>
  
- <span data-ttu-id="ef97f-112">安全寄件者限制： 1024</span><span class="sxs-lookup"><span data-stu-id="ef97f-112">Safe sender limit: 1,024</span></span>
    
- <span data-ttu-id="ef97f-113">封鎖的寄件者限制： 500</span><span class="sxs-lookup"><span data-stu-id="ef97f-113">Blocked sender limit: 500</span></span>
    
<span data-ttu-id="ef97f-114">注意：</span><span class="sxs-lookup"><span data-stu-id="ef97f-114">Note:</span></span>
  
<span data-ttu-id="ef97f-115">您可能會遇到錯誤[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)中所述。</span><span class="sxs-lookup"><span data-stu-id="ef97f-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="ef97f-116">若要解決此問題，請清除 「 信任來自我的連絡人的電子郵件 」] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ef97f-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="ef97f-117">或者，降低量是預設連絡人] 資料夾中將它顯示在允許的最大限制遵守 1024年個在 Exchange Online 設定為 「 MaxSafeSenders 」 屬性的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ef97f-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="ef97f-118">如需此屬性與 Set-mailbox 指令程式的詳細資訊，請參閱 < 下列主題：</span><span class="sxs-lookup"><span data-stu-id="ef97f-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>
  
[<span data-ttu-id="ef97f-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="ef97f-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a><span data-ttu-id="ef97f-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ef97f-120">See also</span></span>

[<span data-ttu-id="ef97f-121">寄件者篩選在 Exchange 2016</span><span class="sxs-lookup"><span data-stu-id="ef97f-121">Sender filtering in Exchange 2016</span></span>](https://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

