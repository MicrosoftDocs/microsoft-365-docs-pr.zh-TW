---
title: 已報告訊息的系統管理員檢閱
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 瞭解如何查看所報告的訊息，並提供對您的使用者意見反應。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7386f5b283e2bfabb76eee91d33dfda0e42ec7b1
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769122"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="20cbf-103">已報告訊息的系統管理員檢閱</span><span class="sxs-lookup"><span data-stu-id="20cbf-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="20cbf-104">本文中的資訊與在正式發行之前可能會充分修改的預覽產品有關。</span><span class="sxs-lookup"><span data-stu-id="20cbf-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="20cbf-105">本檔僅供評估和探索之用。</span><span class="sxs-lookup"><span data-stu-id="20cbf-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="20cbf-106">**適用於**</span><span class="sxs-lookup"><span data-stu-id="20cbf-106">**Applies to**</span></span>
- [<span data-ttu-id="20cbf-107">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="20cbf-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="20cbf-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20cbf-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="20cbf-109">在 Microsoft 365 具有 Exchange Online 信箱和 Microsoft Defender for Office 365 的組織中，管理員現在可以在查看報告的訊息之後，將範本化郵件傳送回給最終使用者。</span><span class="sxs-lookup"><span data-stu-id="20cbf-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="20cbf-110">您也可以根據系統管理員的判定，針對您的組織自訂此格式。</span><span class="sxs-lookup"><span data-stu-id="20cbf-110">This can be customized for your organization and based on your admin’s verdict as well.</span></span>

<span data-ttu-id="20cbf-111">此功能的設計目的是要提供對使用者的意見反應，但不會變更系統中的郵件 verdicts。</span><span class="sxs-lookup"><span data-stu-id="20cbf-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="20cbf-112">為了協助 Microsoft 更新及改善其篩選，您必須提交郵件以供使用系統 [管理員提交](admin-submission.md)進行分析。</span><span class="sxs-lookup"><span data-stu-id="20cbf-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="20cbf-113">如果郵件被報告為 [誤報或漏報](report-false-positives-and-false-negatives.md)，您將只能標示及通知使用者的審閱結果。</span><span class="sxs-lookup"><span data-stu-id="20cbf-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20cbf-114">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="20cbf-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="20cbf-115">若要修改使用者提交的設定，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="20cbf-115">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="20cbf-116">[Microsoft 365 Security center](permissions-microsoft-365-security-center.md)中的組織管理或安全性管理員。</span><span class="sxs-lookup"><span data-stu-id="20cbf-116">Organization Management or Security Administrator in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="20cbf-117">[Exchange Online](/Exchange/permissions-exo/permissions-exo)中的組織管理。</span><span class="sxs-lookup"><span data-stu-id="20cbf-117">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo).</span></span>

- <span data-ttu-id="20cbf-118">您也需要 Exchange Online PowerShell 的存取權。</span><span class="sxs-lookup"><span data-stu-id="20cbf-118">You'll also need access to the Exchange Online PowerShell.</span></span> <span data-ttu-id="20cbf-119">如果您嘗試使用的帳戶不具備 Exchange Online PowerShell 的存取權，您會收到錯誤，指出 *在您的網域中指定電子郵件地址*。</span><span class="sxs-lookup"><span data-stu-id="20cbf-119">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="20cbf-120">如需啟用或停用 Exchange Online PowerShell 存取權的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="20cbf-120">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="20cbf-121">啟用或停用 Exchange Online PowerShell 的存取權</span><span class="sxs-lookup"><span data-stu-id="20cbf-121">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="20cbf-122">Exchange Online 中的用戶端存取規則</span><span class="sxs-lookup"><span data-stu-id="20cbf-122">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="20cbf-123">設定用來通知使用者的郵件</span><span class="sxs-lookup"><span data-stu-id="20cbf-123">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="20cbf-124">在 [Microsoft 365 的安全性中心](../defender/overview-security-center.md)，移至 [原則] **& 規則** \> **威脅** 原則 \> **使用者報告的郵件設定**。</span><span class="sxs-lookup"><span data-stu-id="20cbf-124">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Policies & rules** \> **Threat policies** \> **User reported message settings**.</span></span>

2. <span data-ttu-id="20cbf-125">如果您想要指定寄件者顯示名稱，請在 [系統管理員檢查結果] 區段的 [**電子郵件通知**] 下，選取要 **用來做為寄件者的 Office 365 電子郵件地址** 的方塊，然後輸入您想要使用的名稱。</span><span class="sxs-lookup"><span data-stu-id="20cbf-125">If you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="20cbf-126">這是 Outlook 會顯示的電子郵件地址，以及回復會移至哪一個位置。</span><span class="sxs-lookup"><span data-stu-id="20cbf-126">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="20cbf-127">如果您想要自訂任何範本，請按一下 [ **自訂電子郵件通知**]。</span><span class="sxs-lookup"><span data-stu-id="20cbf-127">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="20cbf-128">在這個浮出控制項中，您將可以自訂下列專案：</span><span class="sxs-lookup"><span data-stu-id="20cbf-128">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="20cbf-129">網路釣魚</span><span class="sxs-lookup"><span data-stu-id="20cbf-129">Phishing</span></span>
    - <span data-ttu-id="20cbf-130">垃圾</span><span class="sxs-lookup"><span data-stu-id="20cbf-130">Junk</span></span>
    - <span data-ttu-id="20cbf-131">找不到威脅</span><span class="sxs-lookup"><span data-stu-id="20cbf-131">No threats found</span></span>
    - <span data-ttu-id="20cbf-132">認知訓練</span><span class="sxs-lookup"><span data-stu-id="20cbf-132">Awareness training</span></span>
    - <span data-ttu-id="20cbf-133">頁尾</span><span class="sxs-lookup"><span data-stu-id="20cbf-133">Footer</span></span>

4. <span data-ttu-id="20cbf-134">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="20cbf-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="20cbf-135">若要清除這些值，請在 [使用者報送] 頁面上按一下 [ **放棄** ]。</span><span class="sxs-lookup"><span data-stu-id="20cbf-135">To clear these values, click **Discard** on the User submissions page.</span></span>
