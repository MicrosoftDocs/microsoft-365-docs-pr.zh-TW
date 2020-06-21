---
title: Microsoft 365 中的使用者垃圾郵件通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以在 Exchange Online Protection （EOP）中深入瞭解隔離郵件的使用者垃圾郵件通知。
ms.openlocfilehash: 14dcdfa8373e3826b23bc5574d1b5ae8ff76927b
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754781"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="d6285-103">使用使用者垃圾郵件通知來釋放及報告隔離的郵件</span><span class="sxs-lookup"><span data-stu-id="d6285-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="d6285-104">在擁有 Exchange Online 信箱的 Microsoft 365 組織中或是沒有 Exchange Online 信箱的獨立 Exchange Online Protection (EOP) 組織中，隔離區會保存可能有害或垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d6285-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="d6285-105">如需詳細資訊，請參閱[EOP 中的隔離郵件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="d6285-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="d6285-106">根據預設，會停用反垃圾郵件原則中的使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="d6285-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="d6285-107">當系統管理員[啟用使用者垃圾郵件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)時，收件者（包括共用信箱）將會收到有關其郵件（已被隔離為垃圾郵件、大量電子郵件，或（截止2020年4月）網路釣魚的定期通知。</span><span class="sxs-lookup"><span data-stu-id="d6285-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="d6285-108">以高可信度網路釣魚、惡意程式碼或郵件流程規則（也稱為傳輸規則）隔離的郵件只適用于系統管理員。</span><span class="sxs-lookup"><span data-stu-id="d6285-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="d6285-109">如需詳細資訊，請參閱[在 EOP 中管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="d6285-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="d6285-110">使用者垃圾郵件通知包含每個隔離郵件的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d6285-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="d6285-111">**寄件者**：隔離郵件的傳送名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d6285-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="d6285-112">**Subject**：隔離郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="d6285-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="d6285-113">**日期**：郵件被隔離的日期和時間（UTC）。</span><span class="sxs-lookup"><span data-stu-id="d6285-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="d6285-114">**封鎖寄件者**：按一下此連結可將寄件者新增至您的封鎖寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="d6285-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="d6285-115">如需詳細資訊，請參閱[封鎖郵件寄件者](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。</span><span class="sxs-lookup"><span data-stu-id="d6285-115">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="d6285-116">**發行**：針對垃圾郵件（沒有網路釣魚）郵件，您可以在這裡放開郵件，而不需要隔離安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="d6285-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="d6285-117">**檢查**：按一下此連結，以移至 [安全性 & 規範中心] 中的 [隔離]，您可以在此發行、刪除或報告您的隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="d6285-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="d6285-118">如需詳細資訊，請參閱[在 EOP 中尋找及發行隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="d6285-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![最終使用者垃圾郵件通知範例](../../media/end-user-spam-notification.png)
