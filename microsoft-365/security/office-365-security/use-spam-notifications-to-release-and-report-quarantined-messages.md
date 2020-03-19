---
title: Office 36 中的使用者垃圾郵件通知
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
description: 當系統管理員在反垃圾郵件原則中啟用使用者垃圾郵件通知時，郵件收件者會收到有關隔離郵件的定期通知。
ms.openlocfilehash: 67dbf311c37ae61c007b78110522033d79c0b161
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857142"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="aabfb-103">Office 365 中的使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="aabfb-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="aabfb-104">在沒有 Exchange Online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中，隔離區會在 Office 365 組織中包含可能有害或有害的郵件。</span><span class="sxs-lookup"><span data-stu-id="aabfb-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="aabfb-105">如需詳細資訊，請參閱[Office 365 中的隔離](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="aabfb-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="aabfb-106">根據預設，會停用反垃圾郵件原則中的使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="aabfb-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="aabfb-107">當系統管理員[啟用使用者垃圾郵件通知](configure-your-spam-filter-policies.md)時，郵件收件者會收到有關其郵件的定期通知，其郵件是以垃圾郵件、大量電子郵件，或（截止至四月，2020）網路釣魚進行隔離。</span><span class="sxs-lookup"><span data-stu-id="aabfb-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="aabfb-108">在10月2019，我們移除直接從使用者垃圾郵件通知來釋放隔離郵件的功能。</span><span class="sxs-lookup"><span data-stu-id="aabfb-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="aabfb-109">相反地，使用者現在可以移至 Office 365 的安全性 & 合規性中心，以釋放隔離的郵件（直接或透過按一下通知中的 [**複查**]）。</span><span class="sxs-lookup"><span data-stu-id="aabfb-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="aabfb-110">如需詳細資訊，請參閱 [以 Office 365 使用者身分尋找並釋出被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="aabfb-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="aabfb-111">以高可信度網路釣魚、惡意程式碼或郵件流程規則（也稱為傳輸規則）隔離的郵件只適用于系統管理員。</span><span class="sxs-lookup"><span data-stu-id="aabfb-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="aabfb-112">如需詳細資訊，請參閱[在 Office 365 中尋找及發行隔離的郵件為系統管理員](find-and-release-quarantined-messages-as-an-administrator.md)。</span><span class="sxs-lookup"><span data-stu-id="aabfb-112">For more information, see [Find and release quarantined messages as an admin in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

<span data-ttu-id="aabfb-113">使用者垃圾郵件通知包含每個隔離郵件的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="aabfb-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="aabfb-114">**寄件者**：隔離郵件的傳送名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="aabfb-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="aabfb-115">**Subject**：隔離郵件的主旨行文字。</span><span class="sxs-lookup"><span data-stu-id="aabfb-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="aabfb-116">**日期**：郵件被隔離的日期和時間（UTC）。</span><span class="sxs-lookup"><span data-stu-id="aabfb-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="aabfb-117">**封鎖寄件者**：按一下此連結可將寄件者新增至您的封鎖寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="aabfb-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="aabfb-118">**檢查**：按一下此連結以移至安全性 & 規範中心的隔離區，您可以在此發行、刪除或報告隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="aabfb-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![最終使用者垃圾郵件通知範例](../../media/end-user-spam-notification.png)
