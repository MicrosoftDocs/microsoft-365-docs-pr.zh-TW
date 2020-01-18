---
title: 使用取消列出入口網站，將您自己從 Office 365 封鎖寄件者清單中移除
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
description: 當您嘗試將電子郵件傳送給其電子郵件地址是在 Office 365 中的收件者時，是否收到錯誤？如果您認為您不應該收到錯誤訊息，您可以使用取消列出入口網站，將您自己從 Office 365 封鎖寄件者清單中移除。
ms.openlocfilehash: da1c066c79acd6fb8b80796a0fc7f39d52337017
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238460"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a><span data-ttu-id="7e18f-104">使用取消列出入口網站，將您自己從 Office 365 封鎖寄件者清單中移除</span><span class="sxs-lookup"><span data-stu-id="7e18f-104">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>

<span data-ttu-id="7e18f-p102">當您嘗試將電子郵件傳送給其電子郵件地址是在 Office 365 中的收件者時，是否收到錯誤？如果您認為您不應該收到錯誤訊息，您可以使用取消列出入口網站，將您自己從 Office 365 封鎖寄件者清單中移除。</span><span class="sxs-lookup"><span data-stu-id="7e18f-p102">Are you getting an error message when you try to send an email to a recipient whose email address is in Office 365? If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the Office 365 blocked senders list.</span></span>

## <a name="what-is-the-office-365-blocked-senders-list"></a><span data-ttu-id="7e18f-107">什麼是 Office 365 封鎖寄件者清單？</span><span class="sxs-lookup"><span data-stu-id="7e18f-107">What is the Office 365 blocked senders list?</span></span>

<span data-ttu-id="7e18f-p103">Microsoft 會使用封鎖寄件者清單，來保護其客戶避免垃圾郵件、詐騙和網路釣魚攻擊。您的郵件伺服器的 IP 位址，也就是您的郵件伺服器用來在網際網路上識別其本身的位址，因為其中一個原因，已標記為 Office 365 的潛在威脅。當 Office 365 將 IP 位址新增至清單時，它會防止 IP 位址和透過我們的資料中心的任何客戶之間的所有進一步通訊。</span><span class="sxs-lookup"><span data-stu-id="7e18f-p103">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks. Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Office 365 for one of a variety of reasons. When Office 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="7e18f-111">當您收到包含錯誤如下的郵件訊息時，您就會知道您已新增至清單：</span><span class="sxs-lookup"><span data-stu-id="7e18f-111">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="7e18f-112">550 5.7.606-649 存取遭拒，禁止傳送 IP [_IP 位址_];若要要求從此清單移除請造訪https://sender.office.com/，並按照指示。</span><span class="sxs-lookup"><span data-stu-id="7e18f-112">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="7e18f-113">如需詳細資訊，請參閱[電子郵件未傳遞回報在 Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="7e18f-113">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="7e18f-114">其中  _IP address_ 是郵件伺服器執行所在之電腦的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7e18f-114">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="7e18f-115">若要使用 Office 365 取消列出入口網站將您自己從封鎖寄件者清單中移除</span><span class="sxs-lookup"><span data-stu-id="7e18f-115">To use the Office 365 delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="7e18f-116">在 Web 瀏覽器中，移至 [https://sender.office.com](https://sender.office.com)。</span><span class="sxs-lookup"><span data-stu-id="7e18f-116">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>

2. <span data-ttu-id="7e18f-p105">遵循頁面中的指示。請確定您使用被傳送錯誤訊息的電子郵件地址，以及在錯誤訊息中指定的 IP 位址。您每次造訪只能輸入一個電子郵件地址及一個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7e18f-p105">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="7e18f-120">按一下 **[送出]**。</span><span class="sxs-lookup"><span data-stu-id="7e18f-120">Click **Submit**.</span></span>

    <span data-ttu-id="7e18f-121">入口網站會將電子郵件傳送至您提供的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="7e18f-121">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="7e18f-122">電子郵件看起來如下：![接收當您透過 delist 入口網站將要求提交的電子郵件的螢幕擷取畫面](../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="7e18f-122">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="7e18f-123">按一下取消列出入口網站傳送給您的電子郵件中的確認連結。</span><span class="sxs-lookup"><span data-stu-id="7e18f-123">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="7e18f-124">這可以讓您回到取消列出入口網站。</span><span class="sxs-lookup"><span data-stu-id="7e18f-124">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="7e18f-125">在取消列出入口網站中，按一下 **[取消列出 IP]**。</span><span class="sxs-lookup"><span data-stu-id="7e18f-125">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="7e18f-p107">從封鎖寄件者清單移除 IP 位址後，來自該 IP 位址的電子郵件訊息將會傳遞給使用 Office 365 的收件者。因此，請確認您確信從該 IP 位址傳送的電子郵件沒有不當或惡意，否則，可能會再度封鎖 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7e18f-p107">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Office 365. So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7e18f-128">它可能需要長達 24 小時，或結果而異廣泛限制會移除前。</span><span class="sxs-lookup"><span data-stu-id="7e18f-128">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="7e18f-129">了解[如何防止實際電子郵件被標示為在 Office 365 中的垃圾郵件](prevent-email-from-being-marked-as-spam.md )和[控制 Office 365 中的輸出垃圾郵件](outbound-spam-controls.md)，以防止 IP 列入黑名單。</span><span class="sxs-lookup"><span data-stu-id="7e18f-129">Read about [How to prevent real email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md ) and [Controlling outbound spam in Office 365](outbound-spam-controls.md) to prevent IP from being blacklisted.</span></span>
