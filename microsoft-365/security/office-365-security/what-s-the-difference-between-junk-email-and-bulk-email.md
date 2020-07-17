---
title: '&apos;垃圾郵件和大量電子郵件有什麼不同？'
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
description: 系統管理員可以深入瞭解 Exchange Online Protection （EOP）中的垃圾郵件（垃圾郵件）和大量電子郵件（灰色郵件）之間的差異。
ms.openlocfilehash: c1f5ca724f7a41d9fc11ed0c93f52a79a6ecc8e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819433"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="18886-103">EOP 中垃圾郵件和大量電子郵件有什麼不同？</span><span class="sxs-lookup"><span data-stu-id="18886-103">What's the difference between junk email and bulk email in EOP?</span></span>

<span data-ttu-id="18886-104">在未使用 Exchange online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中使用信箱的 Microsoft 365 組織，客戶有時會問：「垃圾郵件和大量電子郵件有什麼不同？」</span><span class="sxs-lookup"><span data-stu-id="18886-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="18886-105">本主題說明 EOP 中可用的控制項的差異和描述。</span><span class="sxs-lookup"><span data-stu-id="18886-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="18886-106">**垃圾郵件**為垃圾郵件，也就是垃圾郵件，也就是已正確識別的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="18886-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="18886-107">根據預設，EOP 會根據來源電子郵件伺服器的信譽拒絕垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="18886-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="18886-108">如果郵件通過來源 IP 檢查，它會傳送至垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="18886-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="18886-109">如果郵件是由垃圾郵件篩選歸類為垃圾郵件，則郵件預設會傳送給預定收件者，並移至其 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="18886-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="18886-110">您可以設定要對垃圾郵件篩選 verdicts 採取的動作。</span><span class="sxs-lookup"><span data-stu-id="18886-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="18886-111">如需相關指示，請參閱[CONFIGURE EOP 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="18886-111">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="18886-112">如果您不同意垃圾郵件篩選判定，您可以使用數種方式將您認為視為垃圾郵件或非垃圾郵件的郵件，報告為 Microsoft 的[報表訊息和](report-junk-email-messages-to-microsoft.md)檔案中所述。</span><span class="sxs-lookup"><span data-stu-id="18886-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="18886-113">**大量電子郵件**（也稱為_灰色郵件_）很難進行分類。</span><span class="sxs-lookup"><span data-stu-id="18886-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="18886-114">垃圾郵件是常數威脅，大量電子郵件常常是一次的廣告或行銷訊息。</span><span class="sxs-lookup"><span data-stu-id="18886-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="18886-115">有些使用者想要大量的電子郵件訊息（事實上，他們會特意簽署以接收郵件），而其他使用者則會將大量電子郵件視為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="18886-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="18886-116">例如，有些使用者想要接收來自 Contoso 公司的廣告訊息，或在網路安全性上的即將舉行的會議邀請，其他使用者請將這些相同的郵件視為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="18886-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="18886-117">如需有關如何識別大量電子郵件的詳細資訊，請參閱[EOP 中的大量投訴層級（BCL）](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="18886-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="18886-118">如何管理大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="18886-118">How to manage bulk email</span></span>

<span data-ttu-id="18886-119">由於大量電子郵件的混合反應，因此不會有適用于每個組織的通用指導方針。</span><span class="sxs-lookup"><span data-stu-id="18886-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="18886-120">反垃圾郵件原則具有預設的 BCL 閾值，用來識別大量電子郵件為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="18886-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="18886-121">系統管理員可增加或減少閾值。</span><span class="sxs-lookup"><span data-stu-id="18886-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="18886-122">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="18886-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="18886-123">[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="18886-123">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="18886-124">EOP 反垃圾郵件原則設定</span><span class="sxs-lookup"><span data-stu-id="18886-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="18886-125">另一種易於忽視的選項：如果接收大量電子郵件的使用者 complains，但郵件是來自可透過 EOP 中垃圾郵件篩選的著名寄件者，請使用者在大量電子郵件訊息中檢查是否有 [取消訂閱] 選項。</span><span class="sxs-lookup"><span data-stu-id="18886-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
