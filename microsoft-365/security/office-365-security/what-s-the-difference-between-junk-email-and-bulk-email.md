---
title: '&apos;垃圾郵件和大量電子郵件有什麼不同？'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Exchange Online Protection 中的垃圾郵件 (垃圾郵件) 和大量電子郵件)  (灰色郵件 (EOP) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290642"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="8d7bc-103">EOP 中垃圾郵件和大量電子郵件有什麼不同？</span><span class="sxs-lookup"><span data-stu-id="8d7bc-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8d7bc-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="8d7bc-104">**Applies to**</span></span>
- [<span data-ttu-id="8d7bc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8d7bc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8d7bc-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="8d7bc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="8d7bc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d7bc-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="8d7bc-108">在使用 Exchange Online 中的信箱或獨立 Exchange Online (Protection 的 Microsoft 365 組織中，EOP) 不含 Exchange Online 信箱的組織，客戶有時會問：「垃圾郵件和大量電子郵件有什麼不同？」。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="8d7bc-109">本主題說明 EOP 中可用的控制項的差異和描述。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="8d7bc-110">**垃圾郵件** 為垃圾郵件，也就是) 正確辨識時， (未受歡迎和普遍有害的郵件。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="8d7bc-111">根據預設，EOP 會根據來源電子郵件伺服器的信譽拒絕垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="8d7bc-112">如果郵件通過來源 IP 檢查，它會傳送至垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="8d7bc-113">如果郵件是由垃圾郵件篩選歸類為垃圾郵件，則郵件預設會 () 傳送給預定的收件者，並移至其 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="8d7bc-114">您可以設定要對垃圾郵件篩選 verdicts 採取的動作。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="8d7bc-115">如需相關指示，請參閱 [CONFIGURE EOP 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="8d7bc-116">如果您不同意垃圾郵件篩選判定，您可以使用數種方式將您認為視為垃圾郵件或非垃圾郵件的郵件，報告為 Microsoft 的 [報表訊息和](report-junk-email-messages-to-microsoft.md)檔案中所述。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="8d7bc-117">**大量電子郵件** (也稱為 _灰色郵件_) ，很難進行分類。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="8d7bc-118">垃圾郵件是常數威脅，大量電子郵件常常是一次的廣告或行銷訊息。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="8d7bc-119">有些使用者需要大量電子郵件訊息 (，實際上，他們已特意註冊以接收) ，其他使用者則將大量電子郵件視為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="8d7bc-120">例如，有些使用者想要接收來自 Contoso 公司的廣告訊息，或在網路安全性上的即將舉行的會議邀請，其他使用者請將這些相同的郵件視為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="8d7bc-121">如需有關如何識別大量電子郵件的詳細資訊，請參閱 [EOP 中的大量投訴層級 (BCL) ](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="8d7bc-122">如何管理大量電子郵件</span><span class="sxs-lookup"><span data-stu-id="8d7bc-122">How to manage bulk email</span></span>

<span data-ttu-id="8d7bc-123">由於大量電子郵件的混合反應，因此不會有適用于每個組織的通用指導方針。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="8d7bc-124">反垃圾郵件原則具有預設的 BCL 閾值，用來識別大量電子郵件為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="8d7bc-125">系統管理員可增加或減少閾值。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="8d7bc-126">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="8d7bc-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="8d7bc-127">[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="8d7bc-128">EOP 反垃圾郵件原則設定</span><span class="sxs-lookup"><span data-stu-id="8d7bc-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="8d7bc-129">另一種易於忽視的選項：如果接收大量電子郵件的使用者 complains，但郵件是來自可透過 EOP 中垃圾郵件篩選的著名寄件者，請使用者在大量電子郵件訊息中檢查是否有 [取消訂閱] 選項。</span><span class="sxs-lookup"><span data-stu-id="8d7bc-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
