---
title: 何謂 EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom:
- TN2DMC
- seo-marvel-apr2020
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: 在本文中，您將瞭解 Exchange Online Protection （EOP）（即雲端式電子郵件篩選服務）。
ms.openlocfilehash: 7a9c122edf229d70f0ea5a1dbea8be56b5a2a3a9
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034935"
---
# <a name="what-is-exchange-online-protection-eop"></a><span data-ttu-id="d9752-103">何謂 Exchange Online Protection （EOP）</span><span class="sxs-lookup"><span data-stu-id="d9752-103">What is Exchange Online Protection (EOP)</span></span>

<span data-ttu-id="d9752-104">Exchange Online Protection （EOP）是雲端式的電子郵件篩選服務，可協助您的組織抵禦垃圾郵件和惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="d9752-104">Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="d9752-105">如果您在 Microsoft 365 中有信箱，這些信箱會自動受到 EOP 保護，因為它是服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="d9752-105">If you have mailboxes in Microsoft 365, they are automatically protected by EOP since it is part of the service.</span></span> <span data-ttu-id="d9752-106">這包括在 Microsoft 365 和內部部署中具有信箱的組織，這通常稱為混合式案例。</span><span class="sxs-lookup"><span data-stu-id="d9752-106">This includes organizations that have mailboxes in both Microsoft 365 and on-premise, which is commonly known as a hybrid scenario.</span></span> <span data-ttu-id="d9752-107">EOP 獨立版也可用於沒有雲端信箱的客戶，但想要保護其內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="d9752-107">EOP standalone is also available for customers who do not have mailboxes in the cloud but want to protect their on-premises mailboxes.</span></span>

<span data-ttu-id="d9752-108">EOP 會嘗試篩選出垃圾郵件，使您的收件匣不清楚使用者不想要看到的內容。</span><span class="sxs-lookup"><span data-stu-id="d9752-108">EOP attempts to filter out junk, keeping your Inbox clear of content that users don't want to see.</span></span> <span data-ttu-id="d9752-109">通常，垃圾郵件會傳遞至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d9752-109">Normally, junk mail is delivered to the Junk Email folder.</span></span> <span data-ttu-id="d9752-110">有些使用者想要檢查，確定篩選執行的是其所需要的功能，因此 [垃圾郵件] 資料夾是一種簡單的方法供使用者自行檢查。</span><span class="sxs-lookup"><span data-stu-id="d9752-110">Some users like to check to make sure the filtering is doing what they want so the Junk Email folder is an easy way for users to check on their own.</span></span>  

> [!TIP]
> <span data-ttu-id="d9752-111">當垃圾郵件自動進入 [垃圾郵件] 資料夾時，這是一項很好的做法。</span><span class="sxs-lookup"><span data-stu-id="d9752-111">It is a good thing when junk or otherwise bad email goes into the Junk Email folder automatically.</span></span> <span data-ttu-id="d9752-112">服務會根據預設或自訂的系統管理員設定狀態，進行必要的工作。</span><span class="sxs-lookup"><span data-stu-id="d9752-112">The service will do what is necessary based on what the default or the custom admin settings state.</span></span> <span data-ttu-id="d9752-113">換句話說，使用者不應該擔心會在 [垃圾郵件] 資料夾中看到大量的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d9752-113">In other words, users should not worry about seeing a lot of spam mail in the Junk Email folder.</span></span> <span data-ttu-id="d9752-114">如果系統管理員喜歡移動所有垃圾郵件，則應該設定隔離。</span><span class="sxs-lookup"><span data-stu-id="d9752-114">If admins prefer to move all junk out of sight, then the Quarantine should be configured.</span></span> <span data-ttu-id="d9752-115">如需詳細資訊，請參閱[隔離電子郵件訊息](quarantine-email-messages.md)文章。</span><span class="sxs-lookup"><span data-stu-id="d9752-115">For more details, see the [Quarantine email messages](quarantine-email-messages.md) article.</span></span>

## <a name="important-terms"></a><span data-ttu-id="d9752-116">重要字詞</span><span class="sxs-lookup"><span data-stu-id="d9752-116">Important terms</span></span>

<span data-ttu-id="d9752-117">**輸入**：即將加入 Microsoft 365 的郵件。</span><span class="sxs-lookup"><span data-stu-id="d9752-117">**Inbound**: Messages that are coming into Microsoft 365.</span></span>

<span data-ttu-id="d9752-118">**輸出**：即將離開 Microsoft 365 的郵件。</span><span class="sxs-lookup"><span data-stu-id="d9752-118">**Outbound**: Messages that are going out of Microsoft 365.</span></span>

<span data-ttu-id="d9752-119">**Internal**：來自組織內部某人的郵件，到組織內部的某人。</span><span class="sxs-lookup"><span data-stu-id="d9752-119">**Internal**: Messages that are from someone inside the organization to someone inside the organization.</span></span> <span data-ttu-id="d9752-120">這包括混合式案例中的客戶，以及一個信箱可以在內部部署，另一個信箱則位於雲端中。</span><span class="sxs-lookup"><span data-stu-id="d9752-120">This includes customers who are in hybrid scenarios and one mailbox could be on-premises and the other mailbox is in the cloud.</span></span>

<span data-ttu-id="d9752-121">**False 負數（FN）**：垃圾郵件和其他不正確傳送至收件匣的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d9752-121">**False Negative (FN)**: Spam and other junk that incorrectly gets sent into the inbox.</span></span>

<span data-ttu-id="d9752-122">**誤報（FP）**：合法郵件會錯誤地標示為垃圾郵件，並放入垃圾郵件資料夾或隔離區。</span><span class="sxs-lookup"><span data-stu-id="d9752-122">**False Positive (FP)**: Legitimate messages that incorrectly get marked as spam and put into the Junk Email folder or Quarantine.</span></span>

<span data-ttu-id="d9752-123">**垃圾郵件，也稱為未經許可的電子郵件**：這種形式的商業廣告、連鎖信、政治郵件等等。這是使用者未針對嘗試徵求產品或嘗試認可欺詐的垃圾郵件人員進行註冊的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d9752-123">**Spam, also known as unsolicited e-mail**: This comes in the form of commercial advertising, chain letters, political mailings, etc. This is email that users do not sign up for and from spammers who are trying to solicit products or attempting to commit fraud.</span></span>

<span data-ttu-id="d9752-124">**網路釣魚**：網路釣魚是一種特殊類型的垃圾郵件，其目的是為了哄騙您為認可身分識別或欺詐的目的提供個人資訊。</span><span class="sxs-lookup"><span data-stu-id="d9752-124">**Phish**: Phishing is a special type of spam that is intended to trick you into giving up personal information for the purpose of committing identity theft or fraud.</span></span> <span data-ttu-id="d9752-125">這類郵件通常包含惡意連結或附件，但不一定是。</span><span class="sxs-lookup"><span data-stu-id="d9752-125">This type of message usually contains a malicious link or attachment, but not always.</span></span>

<span data-ttu-id="d9752-126">**哄騙**：哄騙是指寄件者從標頭中偽造時，郵件似乎來自于實際來源以外的某人或其他地方。</span><span class="sxs-lookup"><span data-stu-id="d9752-126">**Spoof**: Spoofing is when spammers forge the FROM header so that messages appear to have originated from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="d9752-127">這可以是垃圾郵件，但最常見的是用於網路釣魚使用者。</span><span class="sxs-lookup"><span data-stu-id="d9752-127">This can be spam but most commonly used to phish users.</span></span>

<span data-ttu-id="d9752-128">模擬 **：這**種類型的垃圾郵件也是偽造寄件者位址的方式，但是它是透過修改名稱或網域的一部分，使它看起來像是實際來源。</span><span class="sxs-lookup"><span data-stu-id="d9752-128">**Impersonation**: This type of spam is also a way to forge the sender address, but it is done by modifying part of the name or domain so that it looks like the real source.</span></span> <span data-ttu-id="d9752-129">例如，Bi11@micr0s0ft.com，在帳單中，"l" 實際上是數位十一，而 Microsoft 中的 "o" 是由數位零所取代。</span><span class="sxs-lookup"><span data-stu-id="d9752-129">For example, Bi11@micr0s0ft.com, where the "l" in Bill was actually the number eleven and the "o" in Microsoft was replaced with the number zero.</span></span>

<span data-ttu-id="d9752-130">**大量**：大宗郵件通常是由使用者要求，但有時會在公司向其他公司銷售資訊時間接使用。</span><span class="sxs-lookup"><span data-stu-id="d9752-130">**Bulk**: Bulk mail is usually solicited by users, although sometimes indirectly when companies sell information to other companies.</span></span> <span data-ttu-id="d9752-131">使用者通常會自行註冊大宗郵件（亦即 newletters），但稍後又忘了，並認為是垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d9752-131">It is common that users intentionally sign up for bulk mail (i.e. newletters) but forget later on and think it is spam.</span></span> <span data-ttu-id="d9752-132">大宗郵件傳送超過使用者的註冊和投訴層級時，大宗郵件會變成垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d9752-132">Bulk mail becomes spam when bulk mailers send more than users sign up and complaint levels get too high.</span></span>
