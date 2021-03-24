---
title: 隔離的電子郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 中包含可能危險或有害郵件的隔離。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd748871cc09905f9878d5917351b1c185cc1106
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060063"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="04c07-103">EOP 中隔離的電子郵件</span><span class="sxs-lookup"><span data-stu-id="04c07-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="04c07-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="04c07-104">**Applies to**</span></span>
- [<span data-ttu-id="04c07-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="04c07-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="04c07-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="04c07-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="04c07-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04c07-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="04c07-108">在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱，隔離可用於存放可能危險或不需要的郵件。</span><span class="sxs-lookup"><span data-stu-id="04c07-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="04c07-109">如果找到 *任何* 包含惡意程式碼的附件，反惡意程式碼原則就會自動隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="04c07-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="04c07-110">如需詳細資訊，請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="04c07-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="04c07-111">根據預設，反垃圾郵件原則會隔離網路釣魚郵件，並將垃圾郵件和大量電子郵件傳送至使用者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="04c07-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="04c07-112">不過，您也可以建立及自訂反垃圾郵件原則，以隔離垃圾郵件和大量電子郵件。</span><span class="sxs-lookup"><span data-stu-id="04c07-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="04c07-113">如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="04c07-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="04c07-114">使用者和系統管理員都可以處理隔離的郵件：</span><span class="sxs-lookup"><span data-stu-id="04c07-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="04c07-115">系統管理員可以使用所有類型的隔離郵件來處理所有使用者。</span><span class="sxs-lookup"><span data-stu-id="04c07-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="04c07-116">只有系統管理員可以處理被隔離為惡意程式碼、高可信度網路釣魚的郵件，或郵件流程規則的結果 (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="04c07-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="04c07-117">如需詳細資訊，請參閱[在 EOP 中管理隔離的郵件和檔案](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="04c07-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="04c07-118">如果郵件被隔離為垃圾郵件、大量電子郵件， (或在 2020) 網路釣魚時，使用者可以使用被隔離的郵件，而這些郵件是收件者。</span><span class="sxs-lookup"><span data-stu-id="04c07-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="04c07-119">如需詳細資訊，請參閱 [在 EOP 中尋找及發行隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="04c07-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="04c07-120">若要防止使用者管理其自己的隔離網路釣魚郵件，系統管理員可以針對反垃圾郵件原則中的 **網路釣魚電子郵件** 篩選判定，設定不同的動作。</span><span class="sxs-lookup"><span data-stu-id="04c07-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="04c07-121">如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="04c07-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="04c07-122">系統管理員和使用者可以向隔離中的 Microsoft 報告誤報。</span><span class="sxs-lookup"><span data-stu-id="04c07-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="04c07-123">如需有關隔離的詳細資訊，請參閱 [隔離常見問題](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="04c07-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
