---
title: 將您自己從封鎖的寄件者清單中移除
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何使用取消列出入口網站，將您自己從 Microsoft 365 封鎖的寄件者清單中移除。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4488f5e5607d71da35b2921e863fb02195467e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057188"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="8a22a-103">使用取消列出入口網站，將您自己從封鎖寄件者清單中移除</span><span class="sxs-lookup"><span data-stu-id="8a22a-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8a22a-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="8a22a-104">**Applies to**</span></span>
- [<span data-ttu-id="8a22a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8a22a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8a22a-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="8a22a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8a22a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a22a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8a22a-108">當您嘗試將電子郵件傳送給其電子郵件地址是 Microsoft 365 的收件者時，收到錯誤訊息嗎？</span><span class="sxs-lookup"><span data-stu-id="8a22a-108">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="8a22a-109">如果您認為您不應該收到錯誤訊息，您可以使用取消列出入口網站，將您自己從 [封鎖的寄件者] 清單中移除。</span><span class="sxs-lookup"><span data-stu-id="8a22a-109">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="8a22a-110">什麼是封鎖的寄件者清單？</span><span class="sxs-lookup"><span data-stu-id="8a22a-110">What is the blocked senders list?</span></span>

<span data-ttu-id="8a22a-111">Microsoft 會使用封鎖寄件者清單，來保護其客戶避免垃圾郵件、詐騙和網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="8a22a-111">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="8a22a-112">您的郵件伺服器的 IP 位址（亦即，郵件伺服器用來在網際網路上識別自己的位址）已標記為可能的 Microsoft 365 威脅，原因很多。</span><span class="sxs-lookup"><span data-stu-id="8a22a-112">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="8a22a-113">當 Microsoft 365 將 IP 位址新增至清單時，它會防止 IP 位址與任何以我們的資料中心進行的任何客戶之間的進一步通訊。</span><span class="sxs-lookup"><span data-stu-id="8a22a-113">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="8a22a-114">當您收到包含錯誤如下的郵件訊息時，您就會知道您已新增至清單：</span><span class="sxs-lookup"><span data-stu-id="8a22a-114">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="8a22a-115">550 5.7.606-649 拒絕存取，禁止傳送 IP _位址 [ip 位址_];若要向此清單要求移除，請流覽 <https://sender.office.com/> 並依照指示執行。</span><span class="sxs-lookup"><span data-stu-id="8a22a-115">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="8a22a-116">如需詳細資訊，請參閱 [Exchange Online 中的電子郵件未傳遞](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)回報。</span><span class="sxs-lookup"><span data-stu-id="8a22a-116">For more information see [Email non-delivery reports in Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="8a22a-117">其中  _IP address_ 是郵件伺服器執行所在之電腦的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8a22a-117">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="8a22a-118">若要使用取消列出入口網站，將您自己從封鎖的寄件者清單中移除</span><span class="sxs-lookup"><span data-stu-id="8a22a-118">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="8a22a-119">在 Web 瀏覽器中，移至 <https://sender.office.com>。</span><span class="sxs-lookup"><span data-stu-id="8a22a-119">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="8a22a-p104">遵循頁面中的指示。請確定您使用被傳送錯誤訊息的電子郵件地址，以及在錯誤訊息中指定的 IP 位址。您每次造訪只能輸入一個電子郵件地址及一個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8a22a-p104">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="8a22a-123">按一下 **[送出]**。</span><span class="sxs-lookup"><span data-stu-id="8a22a-123">Click **Submit**.</span></span>

    <span data-ttu-id="8a22a-124">入口網站會將電子郵件傳送至您提供的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8a22a-124">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="8a22a-125">電子郵件看起來如下所示： ![ 透過取消列出入口網站提交要求時，收到的電子郵件螢幕擷取畫面](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="8a22a-125">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="8a22a-126">按一下取消列出入口網站傳送給您的電子郵件中的確認連結。</span><span class="sxs-lookup"><span data-stu-id="8a22a-126">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="8a22a-127">這可以讓您回到取消列出入口網站。</span><span class="sxs-lookup"><span data-stu-id="8a22a-127">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="8a22a-128">在取消列出入口網站中，按一下 **[取消列出 IP]**。</span><span class="sxs-lookup"><span data-stu-id="8a22a-128">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="8a22a-129">從封鎖的寄件者清單中移除 IP 位址之後，來自該 IP 位址的電子郵件將會傳遞給使用 Microsoft 365 的收件者。</span><span class="sxs-lookup"><span data-stu-id="8a22a-129">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="8a22a-130">因此，請確認您確信從該 IP 位址傳送的電子郵件沒有不當或惡意，否則，可能會再度封鎖 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8a22a-130">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a22a-131">最多可能需要24小時的時間，否則結果會在移除限制之前有很大的差異。</span><span class="sxs-lookup"><span data-stu-id="8a22a-131">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="8a22a-132">請參閱 [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md) 和 [EOP 的輸出垃圾郵件保護](outbound-spam-controls.md) ，以防止 IP 遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="8a22a-132">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>