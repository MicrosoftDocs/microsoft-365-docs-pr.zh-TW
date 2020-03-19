---
title: 隔離
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
ms.assetid: e9eecdde-dcc2-4283-a820-98d1e740e4f
ms.collection:
- M365-security-compliance
description: 深入瞭解 Exchange Online 和 Exchange Online Protection 的主控隔離。
ms.openlocfilehash: ea803a4681a12647f57cf17839d26fb391222364
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856878"
---
# <a name="quarantine"></a><span data-ttu-id="e9c2b-103">隔離</span><span class="sxs-lookup"><span data-stu-id="e9c2b-103">Quarantine</span></span>

<span data-ttu-id="e9c2b-104">下列主題為 Exchange Online 與 Exchange Online Protection (EOP) 系統管理員和使用者提供託管隔離區的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="e9c2b-104">The following topics provide information about the hosted quarantine for both Exchange Online and Exchange Online Protection (EOP) admins and end users:</span></span>

- <span data-ttu-id="e9c2b-105">[隔離常見問題集](quarantine-faq.md) - 為系統管理員和使用者提供隔離區的一般問題與解答</span><span class="sxs-lookup"><span data-stu-id="e9c2b-105">[Quarantine FAQ](quarantine-faq.md) - Provides general questions and answers about the quarantine for both admins and end users</span></span>

- <span data-ttu-id="e9c2b-106">[在 Office 365 中以系統管理員身分管理隔離的郵件和](manage-quarantined-messages-and-files.md)檔案：說明系統管理員如何在 Exchange 系統管理中心（EAC）中尋找並放開位於隔離區中的任何郵件，並選擇性地將其報告為誤報（非垃圾郵件）郵件給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="e9c2b-106">[Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md): Describes how admins can find and release any message that resides in the quarantine in the Exchange admin center (EAC), and optionally report it as a false positive (not junk) message to Microsoft.</span></span>

- <span data-ttu-id="e9c2b-107">[以 Office 365 中的使用者身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)：說明使用者如何在垃圾郵件隔離使用者介面中尋找和放開自己的垃圾隔離郵件，並向 Microsoft 報告這些郵件不是垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="e9c2b-107">[Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md): Describes how end users can find and release their own spam-quarantined messages in the spam quarantine user interface, and report them as not junk to Microsoft.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="e9c2b-108">若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。</span><span class="sxs-lookup"><span data-stu-id="e9c2b-108">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="e9c2b-109">保護內部部署信箱的 EOP 客戶必須是透過目錄同步處理或 EAC 建立的有效電子郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="e9c2b-109">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="e9c2b-110">如需管理使用者的詳細資訊，EOP 系統管理員可以參閱[在 EOP 中管理郵件使用者](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="e9c2b-110">For more information about managing users, EOP admins can refer to [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="e9c2b-111">對於 EOP 獨立客戶，則建議使用目錄同步處理並啟用目錄架構邊緣封鎖；如需詳細資訊，請參閱[使用目錄架構邊緣封鎖以拒絕傳送至無效收件者的郵件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="e9c2b-111">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>
