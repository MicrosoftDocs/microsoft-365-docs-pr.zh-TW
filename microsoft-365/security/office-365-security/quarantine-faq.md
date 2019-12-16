---
title: 隔離常見問題集
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 本主題提供有關託管隔離區的常見問題與解答。
ms.openlocfilehash: f8d7d0820685671c4cbe9ae7671058cc60d8e637
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971551"
---
# <a name="quarantine-faq"></a><span data-ttu-id="3a3f1-103">隔離區常見問題集</span><span class="sxs-lookup"><span data-stu-id="3a3f1-103">Quarantine FAQ</span></span>

<span data-ttu-id="3a3f1-p101">本主題提供有關託管隔離區的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection 客戶。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-p101">This topic provides frequently asked questions and answers about the hosted quarantine. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection customers.</span></span>

 <span data-ttu-id="3a3f1-106">**問：如何管理隔離區中的惡意程式碼隔離郵件？**</span><span class="sxs-lookup"><span data-stu-id="3a3f1-106">**Q. How do I manage malware-quarantined messages in quarantine?**</span></span>

<span data-ttu-id="3a3f1-107">您需要使用安全性與合規性中心，以便查看並使用傳送到隔離區的郵件，因為他們包含惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-107">You need to use the Security &amp; Compliance Center in order to view and work with messages that were sent to quarantine because they contain malware.</span></span> <span data-ttu-id="3a3f1-108">如需詳細資訊，請參閱[在 Office 365 中隔離電子郵件訊息](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-108">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

 <span data-ttu-id="3a3f1-109">**問：如何設定服務以將因垃圾郵件而遭到隔離的郵件傳送至隔離區？**</span><span class="sxs-lookup"><span data-stu-id="3a3f1-109">**Q. How do I configure the service to send spam-quarantined messages to the quarantine?**</span></span>

<span data-ttu-id="3a3f1-110">答：</span><span class="sxs-lookup"><span data-stu-id="3a3f1-110">A.</span></span> <span data-ttu-id="3a3f1-111">根據預設，經過內容篩選的郵件會傳送到收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-111">By default, content-filtered messages are sent to the recipients Junk Email folder.</span></span> <span data-ttu-id="3a3f1-112">但系統管理員可以設定內容篩選原則，改成將垃圾郵件隔離郵件傳送至隔離區。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-112">However, admins can configure content filter policies to send spam-quarantined messages to the quarantine instead.</span></span> <span data-ttu-id="3a3f1-113">如需在經過內容篩選的郵件上可執行的各種動作的詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-113">For more information about the different actions that can be performed on content-filtered messages, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

 <span data-ttu-id="3a3f1-114">**問：此服務是否可讓系統管理員和使用者管理被當成垃圾郵件隔離的郵件？**</span><span class="sxs-lookup"><span data-stu-id="3a3f1-114">**Q. Does the service have administrator and end user management of spam-quarantined messages?**</span></span>

<span data-ttu-id="3a3f1-p104">答：如果您是系統管理員，您可以在 Exchange 系統管理中心 (EAC) 中搜尋及檢視關於所有隔離電子郵件的詳細資訊。找到郵件後，您可以將該郵件釋出給特定使用者，並可選擇向 Microsoft 垃圾郵件分析小組報告該郵件為誤判 (非垃圾郵件)。如需詳細資訊，請參閱 [以系統管理員身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-an-administrator.md)。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-p104">A. As an administrator, you can search for and view details about all quarantined email messages in the Exchange admin center (EAC). After locating the message, you can release it to specific users and optionally report it as a false positive (not junk) to the Microsoft Spam Analysis Team. For more information, see [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

<span data-ttu-id="3a3f1-119">如果您是使用者，則可以透過下列項目管理自己被當成垃圾郵件隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="3a3f1-119">As an end user, you can manage your own spam-quarantined messages via:</span></span>

- <span data-ttu-id="3a3f1-120">垃圾郵件隔離使用者介面。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-120">The spam quarantine user interface.</span></span> <span data-ttu-id="3a3f1-121">如需詳細資訊，請參閱 [以 Office 365 使用者身分尋找並釋出被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-121">Find and release quarantined messages as a user in Office 365</span></span>

 <span data-ttu-id="3a3f1-122">**問：如何授權使用者存取垃圾郵件隔離區？**</span><span class="sxs-lookup"><span data-stu-id="3a3f1-122">**Q. How do I grant access to the spam quarantine for my end users?**</span></span>

<span data-ttu-id="3a3f1-123">答：</span><span class="sxs-lookup"><span data-stu-id="3a3f1-123">A.</span></span> <span data-ttu-id="3a3f1-124">若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-124">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="3a3f1-125">保護內部部署信箱的 EOP 客戶必須是透過目錄同步處理或 EAC 建立的有效電子郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-125">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="3a3f1-126">如需管理使用者的詳細資訊，EOP 系統管理員可以參閱[在 EOP 中管理郵件使用者](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-126">For more information about managing users, EOP admins can refer to [Manage Mail Users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="3a3f1-127">對於 EOP 獨立客戶，則建議使用目錄同步處理並啟用目錄架構邊緣封鎖；如需詳細資訊，請參閱[使用目錄架構邊緣封鎖以拒絕傳送至無效收件者的郵件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-127">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

 <span data-ttu-id="3a3f1-128">**問：不是垃圾郵件的項目是否會傳送到隔離區？**</span><span class="sxs-lookup"><span data-stu-id="3a3f1-128">**Q. Can anything other than spam be sent to the quarantine?**</span></span>

<span data-ttu-id="3a3f1-129">答：</span><span class="sxs-lookup"><span data-stu-id="3a3f1-129">A.</span></span> <span data-ttu-id="3a3f1-130">是的。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-130">Yes.</span></span> <span data-ttu-id="3a3f1-131">如果這是已設定的動作，則符合郵件流程 (也稱為傳輸規則) 的郵件以及被確認為網路釣魚的郵件也會被傳送到系統管理員隔離區。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-131">Messages that match a mail flow rule (also known as a transport rule) along with messages identified as phish can also be sent to the administrator quarantine, if that's the configured action.</span></span> <span data-ttu-id="3a3f1-132">使用者隔離區僅供隔離垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-132">The end user quarantine is for spam only.</span></span>

 <span data-ttu-id="3a3f1-133">**問：郵件會保留在隔離區中多久？**</span><span class="sxs-lookup"><span data-stu-id="3a3f1-133">**Q. For how long are messages kept in the quarantine?**</span></span>

<span data-ttu-id="3a3f1-134">答：</span><span class="sxs-lookup"><span data-stu-id="3a3f1-134">A.</span></span> <span data-ttu-id="3a3f1-135">根據預設，垃圾郵件隔離的郵件會保留在隔離區 30 天，而符合郵件流程規則的隔離郵件會根據您在預設內容篩選原則中設定的保留期，最多保留在隔離區 30 天。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-135">By default, spam-quarantined messages are kept in the quarantine for 30 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for up to 30 days based on the retention period set in your default content filter policy.</span></span> <span data-ttu-id="3a3f1-136">超過這段時間後，郵件就會遭到刪除，而無法擷取。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-136">After this period of time the messages are deleted and are not retrievable.</span></span> <span data-ttu-id="3a3f1-137">符合郵件流程規則的隔離郵件無法設定保留期限。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-137">The retention period for quarantined messages that matched a transport rule is not configurable.</span></span> <span data-ttu-id="3a3f1-138">不過，您可以透過內容篩選原則的 [保留垃圾郵件的天數]\*\*\*\* 設定，縮短垃圾郵件隔離郵件的保留期限。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-138">However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies.</span></span> <span data-ttu-id="3a3f1-139">如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-139">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

 <span data-ttu-id="3a3f1-140">**問：我可以一次釋出或報告多個隔離的郵件嗎？**</span><span class="sxs-lookup"><span data-stu-id="3a3f1-140">**Q. Can I release or report more than one quarantined message at a time?**</span></span>

<span data-ttu-id="3a3f1-141">答：</span><span class="sxs-lookup"><span data-stu-id="3a3f1-141">A.</span></span> <span data-ttu-id="3a3f1-142">是，在隔離區入口網站中最多可同時釋出 100 封郵件。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-142">Yes, up to 100 messages can be released at one time in the Quarantine portal.</span></span> <span data-ttu-id="3a3f1-143">此外，系統管理員還可以建立遠端 Windows PowerShell 指令碼來完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-143">In addition, admins can create a remote Windows PowerShell script to accomplish this task.</span></span> <span data-ttu-id="3a3f1-144">使用 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) 指令程式來搜尋郵件，使用 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) 指令程式來釋出郵件。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-144">Use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for messages, and the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet to release them.</span></span>

 <span data-ttu-id="3a3f1-145">**問：搜尋隔離的郵件時是否支援萬用字元？我可以搜尋特定網域的隔離郵件嗎？**</span><span class="sxs-lookup"><span data-stu-id="3a3f1-145">**Q. Are wildcards supported when searching for quarantined messages? Can I search for quarantined messages for a specific domain?**</span></span>

<span data-ttu-id="3a3f1-p110">答：在 Exchange 系統管理中心指定搜尋準則時不支援萬用字元。例如，在搜尋寄件者時，您必須指定完整的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-p110">A. Wildcards are not supported when specifying search criteria in the Exchange admin center. For example, when searching for a sender, you must specify the full email address.</span></span>

<span data-ttu-id="3a3f1-149">系統管理員可以使用遠端 Windows PowerShell，指定 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) 指令程式在特定網域 (例如 contoso.com) 中搜尋隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="3a3f1-149">Using remote Windows PowerShell, admins can specify the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for quarantined messages for a specific domain (for example, contoso.com):</span></span>

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

<span data-ttu-id="3a3f1-p111">結果可以傳遞至 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) 指令程式。請加上 -ReleaseToAll 參數，以將郵件釋出給所有收件者。郵件一經釋出，就無法再釋出一次。</span><span class="sxs-lookup"><span data-stu-id="3a3f1-p111">The results can be passed to the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet. Include the -ReleaseToAll parameter to release the message to all recipients. Once a message is released, it can't be released again.</span></span>

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```
