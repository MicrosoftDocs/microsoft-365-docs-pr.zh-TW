---
title: 垃圾郵件和大量電子郵件有什麼不同?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解垃圾郵件 & 大量電子郵件之間的差異。 同時深入瞭解 Exchange Online & Exchange Online Protection （EOP）中可用的不同選項。
ms.openlocfilehash: 5d9d3b513de64d2a150d9e0a1c94bc5ca746b617
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036593"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="fd85e-104">垃圾郵件和大量電子郵件有什麼不同?</span><span class="sxs-lookup"><span data-stu-id="fd85e-104">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="fd85e-105">在 Exchange Online 或獨立 Exchange Online Protection （EOP）中擁有信箱的 Microsoft 365 客戶有時會問：「垃圾郵件和大量電子郵件有什麼不同？」。</span><span class="sxs-lookup"><span data-stu-id="fd85e-105">Microsoft 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="fd85e-106">本主題說明 EOP 中可用的控制項的差異和描述。</span><span class="sxs-lookup"><span data-stu-id="fd85e-106">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="fd85e-107">**垃圾郵件**為垃圾郵件，也就是垃圾郵件，也就是已正確識別的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="fd85e-107">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="fd85e-108">根據預設，EOP 會根據來源電子郵件伺服器的信譽拒絕垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="fd85e-108">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="fd85e-109">如果郵件通過來源 IP 檢查，它會傳送至垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="fd85e-109">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="fd85e-110">如果郵件是由垃圾郵件篩選歸類為垃圾郵件，則郵件預設會傳送給預定收件者，並移至其 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="fd85e-110">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="fd85e-111">您可以設定要對垃圾郵件篩選 verdicts 採取的動作。</span><span class="sxs-lookup"><span data-stu-id="fd85e-111">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="fd85e-112">如需相關指示，請參閱[Configure 反垃圾郵件原則 In Office 365](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fd85e-112">For instructions, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="fd85e-113">如果您不同意垃圾郵件篩選判定，您可以使用數種方式將您認為視為垃圾郵件或非垃圾郵件的郵件，報告為 Microsoft 的[報表訊息和](report-junk-email-messages-to-microsoft.md)檔案中所述。</span><span class="sxs-lookup"><span data-stu-id="fd85e-113">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="fd85e-114">**大量電子郵件**（也稱為_灰色郵件_）很難進行分類。</span><span class="sxs-lookup"><span data-stu-id="fd85e-114">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="fd85e-115">垃圾郵件是常數威脅，大量電子郵件常常是一次的廣告或行銷訊息。</span><span class="sxs-lookup"><span data-stu-id="fd85e-115">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="fd85e-116">有些使用者想要大量的電子郵件訊息（事實上，他們會特意簽署以接收郵件），而其他使用者則會將大量電子郵件視為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="fd85e-116">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="fd85e-117">例如，有些使用者想要接收來自 Contoso 公司的廣告訊息，或在網路安全性上的即將舉行的會議邀請，其他使用者請將這些相同的郵件視為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="fd85e-117">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="fd85e-118">如需有關如何識別大量電子郵件的詳細資訊，請參閱[Office 365 中的大量投訴等級（BCL）](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="fd85e-118">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="fd85e-119">如何管理大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="fd85e-119">How to manage bulk email</span></span>

<span data-ttu-id="fd85e-120">由於大量電子郵件的混合反應，因此不會有適用于每個組織的通用指導方針。</span><span class="sxs-lookup"><span data-stu-id="fd85e-120">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="fd85e-121">反垃圾郵件原則具有預設的 BCL 閾值，用來識別大量電子郵件為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="fd85e-121">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="fd85e-122">系統管理員可增加或減少閾值。</span><span class="sxs-lookup"><span data-stu-id="fd85e-122">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="fd85e-123">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="fd85e-123">For more information, see the following topics:</span></span>

- <span data-ttu-id="fd85e-124">[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fd85e-124">[Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="fd85e-125">EOP 反垃圾郵件原則設定</span><span class="sxs-lookup"><span data-stu-id="fd85e-125">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="fd85e-126">另一種易於忽視的選項：如果接收大量電子郵件的使用者 complains，但郵件是來自可透過 EOP 中垃圾郵件篩選的著名寄件者，請使用者在大量電子郵件訊息中檢查是否有 [取消訂閱] 選項。</span><span class="sxs-lookup"><span data-stu-id="fd85e-126">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
