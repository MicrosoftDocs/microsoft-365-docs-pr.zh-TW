---
title: 隔離
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9eecdde-dcc2-4283-a820-98d1e740e4f
ms.collection:
- M365-security-compliance
description: 了解託管隔離區的 Exchange Online 和 Exchange Online Protection。
ms.openlocfilehash: 266ae080cbd87780fc8767293d8642d443157214
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077994"
---
# <a name="quarantine"></a><span data-ttu-id="ecc6c-103">隔離</span><span class="sxs-lookup"><span data-stu-id="ecc6c-103">Quarantine</span></span>

<span data-ttu-id="ecc6c-104">下列主題為 Exchange Online 與 Exchange Online Protection (EOP) 系統管理員和使用者提供託管隔離區的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="ecc6c-104">The following topics provide information about the hosted quarantine for both Exchange Online and Exchange Online Protection (EOP) admins and end users:</span></span>
  
- <span data-ttu-id="ecc6c-105">[隔離常見問題集](quarantine-faq.md) - 為系統管理員和使用者提供隔離區的一般問題與解答</span><span class="sxs-lookup"><span data-stu-id="ecc6c-105">[Quarantine FAQ](quarantine-faq.md) - Provides general questions and answers about the quarantine for both admins and end users</span></span> 
    
- <span data-ttu-id="ecc6c-106">[以系統管理員身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-an-administrator.md) - 說明系統管理員如何在 Exchange 系統管理中心 (EAC) 尋找和釋出位於隔離區中的任何郵件，並選擇性地向 Microsoft 將該郵件報告為誤判的郵件 (非垃圾郵件)。</span><span class="sxs-lookup"><span data-stu-id="ecc6c-106">[Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md) - Describes how admins can find and release any message that resides in the quarantine in the Exchange admin center (EAC), and optionally report it as a false positive (not junk) message to Microsoft.</span></span> 
    
- <span data-ttu-id="ecc6c-107">[Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx) -將告訴您如何使用者可以尋找和釋出自己被當成垃圾郵件隔離的郵件在垃圾郵件隔離使用者介面中，並向 Microsoft 報告這些郵件不是垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="ecc6c-107">[Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx) - Describes how end users can find and release their own spam-quarantined messages in the spam quarantine user interface, and report them as not junk to Microsoft.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ecc6c-108">若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。</span><span class="sxs-lookup"><span data-stu-id="ecc6c-108">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="ecc6c-109">保護內部部署信箱的 EOP 客戶必須是透過目錄同步處理或 EAC 建立的有效電子郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="ecc6c-109">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="ecc6c-110">如需管理使用者的詳細資訊，EOP 系統管理員可以參閱[管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="ecc6c-110">For more information about managing users, EOP admins can refer to [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="ecc6c-111">對於 EOP 獨立客戶，則建議使用目錄同步處理並啟用目錄架構邊緣封鎖；如需詳細資訊，請參閱[使用目錄架構邊緣封鎖以拒絕傳送至無效收件者的郵件](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ecc6c-111">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span> 
  
    

