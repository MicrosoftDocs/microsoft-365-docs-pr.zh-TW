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
description: 如果您是 Exchange Online 或 Exchange Online Protection (EOP) 系統管理員，您可以協助確保透過服務傳送的電子郵件訊息不會被標示為垃圾郵件。 若要這麼做的一種方式是貴組織中的人員來建立安全寄件者和封鎖的寄件者清單。
ms.openlocfilehash: 9c281460aeff64226343af5e5608ccf42fc83799
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238390"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="7996b-104">Exchange Online 中的安全寄件者和封鎖寄件者清單</span><span class="sxs-lookup"><span data-stu-id="7996b-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="7996b-105">如果您是 Exchange Online 或 Exchange Online Protection (EOP) 系統管理員，您可以協助確保透過服務傳送的電子郵件訊息不會被標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="7996b-105">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam.</span></span> <span data-ttu-id="7996b-106">若要這麼做的一種方式是貴組織中的人員來建立安全寄件者和封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="7996b-106">One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span>

<span data-ttu-id="7996b-107">*請參閱更新的版的秘訣和程序說明如何使用這些清單中的系統管理員*[如何防止良好的電子郵件被標示為在 Office 365 中的垃圾郵件](prevent-email-from-being-marked-as-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="7996b-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [How to prevent good email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md).</span></span>

<span data-ttu-id="7996b-108">如果您不是系統管理員，而且您只想要管理自己在 Outlook 中的垃圾郵件所使用的安全寄件者清單，請參閱[垃圾郵件篩選器概觀](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="7996b-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in the[Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="7996b-109">什麼是安全及封鎖寄件者限制在 Exchange Online 嗎？</span><span class="sxs-lookup"><span data-stu-id="7996b-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="7996b-110">Exchange Online 中的安全及封鎖的寄件者限制跟在 Active Directory，以及 Outlook 限制。</span><span class="sxs-lookup"><span data-stu-id="7996b-110">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits.</span></span> <span data-ttu-id="7996b-111">其中包括：</span><span class="sxs-lookup"><span data-stu-id="7996b-111">They are:</span></span>

- <span data-ttu-id="7996b-112">安全寄件者限制： 1024</span><span class="sxs-lookup"><span data-stu-id="7996b-112">Safe sender limit: 1,024</span></span>

- <span data-ttu-id="7996b-113">封鎖的寄件者限制： 500</span><span class="sxs-lookup"><span data-stu-id="7996b-113">Blocked sender limit: 500</span></span>

<span data-ttu-id="7996b-114">注意：</span><span class="sxs-lookup"><span data-stu-id="7996b-114">Note:</span></span>

<span data-ttu-id="7996b-115">您可能會遇到錯誤[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)中所述。</span><span class="sxs-lookup"><span data-stu-id="7996b-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="7996b-116">若要解決此問題，請清除 「 信任來自我的連絡人的電子郵件 」] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7996b-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="7996b-117">或者，降低量是預設連絡人] 資料夾中將它顯示在允許的最大限制遵守 1024年個在 Exchange Online 設定為 「 MaxSafeSenders 」 屬性的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="7996b-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="7996b-118">如需此屬性與 Set-mailbox 指令程式的詳細資訊，請參閱 < 下列主題：</span><span class="sxs-lookup"><span data-stu-id="7996b-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>

[<span data-ttu-id="7996b-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="7996b-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a><span data-ttu-id="7996b-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7996b-120">See also</span></span>

[<span data-ttu-id="7996b-121">寄件者篩選在 Exchange 伺服器</span><span class="sxs-lookup"><span data-stu-id="7996b-121">Sender filtering in Exchange Server</span></span>](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
