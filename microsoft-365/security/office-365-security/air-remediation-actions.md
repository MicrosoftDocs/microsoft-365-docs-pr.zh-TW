---
title: Office 365 中的修復動作自動化調查和回應
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 深入瞭解 Office 365 Advanced 威脅防護方案2中自動化調查和回應功能的修復動作。
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955530"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="6a6ca-104">Office 365 中的自動調查遵循的修正動作</span><span class="sxs-lookup"><span data-stu-id="6a6ca-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="6a6ca-105">補救動作</span><span class="sxs-lookup"><span data-stu-id="6a6ca-105">Remediation actions</span></span>

<span data-ttu-id="6a6ca-106">Office 365 中的[自動化調查和回應功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)（AIR）[高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)（Office 365 ATP）方案2包含某些修正動作。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 include certain remediation actions.</span></span> <span data-ttu-id="6a6ca-107">當自動調查執行或完成時，您通常會看到一或多項修正動作需要由安全性作業小組進行核准，才能繼續進行。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="6a6ca-108">下表摘要列出 Office 365 ATP 中目前可用的修復動作。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-108">The following table summarizes the remediation actions that are currently available in Office 365 ATP.</span></span> 

|<span data-ttu-id="6a6ca-109">動作</span><span class="sxs-lookup"><span data-stu-id="6a6ca-109">Action</span></span> | <span data-ttu-id="6a6ca-110">說明</span><span class="sxs-lookup"><span data-stu-id="6a6ca-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="6a6ca-111">封鎖 URL (點擊時)</span><span class="sxs-lookup"><span data-stu-id="6a6ca-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="6a6ca-112">針對包含惡意 URLs 的電子郵件訊息和檔加以防護。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-112">Protects against email messages and documents that contain malicious URLs.</span></span> <span data-ttu-id="6a6ca-113">這可讓您在使用者按一下現有 Office 檔案或舊的電子郵件中的連結時，透過[安全連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)封鎖惡意連結和任何相關的網頁。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="6a6ca-114">虛刪除電子郵件</span><span class="sxs-lookup"><span data-stu-id="6a6ca-114">Soft delete email</span></span>  |<span data-ttu-id="6a6ca-115">從使用者的信箱中，Soft 刪除特定的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-115">Soft delete specific email messages from a user's mailbox.</span></span> <br/><span data-ttu-id="6a6ca-116">虛刪除的郵件會移至使用者的 [可復原的專案] 資料夾，並且會保留直到刪除的專案保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-116">A soft-deleted message is moved to a user's Recoverable Items folder and is retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="6a6ca-117">虛刪除電子郵件聚簇</span><span class="sxs-lookup"><span data-stu-id="6a6ca-117">Soft delete email clusters</span></span>  |<span data-ttu-id="6a6ca-118">Soft delete 惡意電子郵件訊息符合來自所有使用者信箱的查詢。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-118">Soft delete malicious email messages matching a query from all users' mailboxes.</span></span> <br/><span data-ttu-id="6a6ca-119">虛刪除的郵件會移至使用者的 [可復原的專案] 資料夾，並且會保留，直到刪除的專案保留期間到期為止。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-119">Soft-deleted messages are moved to users' Recoverable Items folder and are retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="6a6ca-120">關閉外部郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="6a6ca-120">Turn off external mail forwarding</span></span> |<span data-ttu-id="6a6ca-121">移除特定使用者信箱的轉寄規則。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-121">Removes a forwarding rule from a specific end user's mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="6a6ca-122">在 Office 365 ATP 中，不會自動採取任何修正動作。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-122">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="6a6ca-123">只有組織的安全小組核准時，才會採取補救措施。</span><span class="sxs-lookup"><span data-stu-id="6a6ca-123">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="6a6ca-124">後續步驟</span><span class="sxs-lookup"><span data-stu-id="6a6ca-124">Next steps</span></span>

- [<span data-ttu-id="6a6ca-125">在 Office 365 中進行自動調查後，查看擱置或已完成的修復動作</span><span class="sxs-lookup"><span data-stu-id="6a6ca-125">View pending or completed remediation actions following an automated investigation in Office 365</span></span>](air-review-approve-pending-completed-actions.md)

- [<span data-ttu-id="6a6ca-126">Office 365 中自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="6a6ca-126">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

## <a name="related-articles"></a><span data-ttu-id="6a6ca-127">相關文章</span><span class="sxs-lookup"><span data-stu-id="6a6ca-127">Related articles</span></span>

- [<span data-ttu-id="6a6ca-128">Microsoft Defender 高級威脅防護中的自動調查</span><span class="sxs-lookup"><span data-stu-id="6a6ca-128">Automated investigation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="6a6ca-129">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="6a6ca-129">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)