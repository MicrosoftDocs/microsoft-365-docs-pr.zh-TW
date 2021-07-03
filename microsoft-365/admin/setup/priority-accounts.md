---
title: 管理和監視優先帳戶
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: 監視寄件者或寄件者對具有高業務影響之帳戶的失敗及延遲的電子郵件。
ms.openlocfilehash: 86e01e591823c94d8279f975ed7de24cc65776dc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286138"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="a3f5c-103">管理和監視優先帳戶</span><span class="sxs-lookup"><span data-stu-id="a3f5c-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="a3f5c-104">在每個 Microsoft 365 組織中，都有重要的人員，例如主管、負責人、主管或其他具有敏感、專有或高優先順序資訊存取權的使用者。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="a3f5c-105">為了協助您的組織保護這些帳戶，您現在可以將特定使用者指定為優先順序帳戶，並利用可提供額外保護的應用程式特定功能。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="a3f5c-106">在未來，其他應用程式和功能將支援優先順序帳戶，若要開始，我們已宣告兩項功能： **優先順序帳戶保護** 和 **優質郵件流程監控**。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-106">In the future, more apps and features will support priority accounts, and to start with, we've announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="a3f5c-107">**Priority account protection** -Microsoft Defender for Office 365 (過去 Office 365 的「高級威脅防護」) 支援優先順序帳戶，作為可在警示、報告和調查篩選中使用的標記。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="a3f5c-108">如需詳細資訊，請參閱[Microsoft Defender 中的使用者標記以取得 Office 365](../../security/office-365-security/user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>

  <span data-ttu-id="a3f5c-109">「自然問題」是「所有使用者都不是優先順序？</span><span class="sxs-lookup"><span data-stu-id="a3f5c-109">A natural question is, "Aren't all users a priority?</span></span> <span data-ttu-id="a3f5c-110">為何不將所有使用者指定為優先順序帳戶？</span><span class="sxs-lookup"><span data-stu-id="a3f5c-110">Why not designate all users as priority accounts?"</span></span> <span data-ttu-id="a3f5c-111">是的，所有使用者都是優先順序，但優先順序帳戶保護提供下列額外優點：</span><span class="sxs-lookup"><span data-stu-id="a3f5c-111">Yes, all users are a priority, but priority account protection offers the following additional benefits:</span></span>

  - <span data-ttu-id="a3f5c-112">**其他試探法**：我們在 Microsoft 資料中心內分析郵件流程，表示公司主管的郵件流程模式與平均員工不同。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-112">**Additional heuristics**: Our analysis of mail flow in the Microsoft datacenters indicates that mail flow patterns for company executives are different than the average employee.</span></span> <span data-ttu-id="a3f5c-113">「優先順序帳戶保護」提供額外的試探法，特別針對公司主管所定制，對一般員工沒有益處。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-113">Priority account protection offers additional heuristics that are specifically tailored to company executives that wouldn't benefit a regular employee.</span></span>
  - <span data-ttu-id="a3f5c-114">**報表的其他可見度**：實際上，所有使用者的資訊 (或所有受影響的使用者) ，都已存在於警示、報告和調查中。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-114">**Additional visibility in reporting**: In effect, information for all users (or all affected users) is already available in alerts, reports, and investigations.</span></span> <span data-ttu-id="a3f5c-115">[優先順序帳戶] 標記為篩選，可讓您特別瞄準調查。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-115">The priority accounts tag as a filter allows you to specifically target your investigations.</span></span>

- <span data-ttu-id="a3f5c-116">**進階版郵件 Flow 監控**-狀況良好的郵件流程對商務成功來說可能很重要，且傳遞延遲或失敗可能會對業務造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-116">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="a3f5c-117">您可以針對失敗或延遲的電子郵件選擇臨界值，當超過該臨界值時接收通知，然後查看優先順序帳戶的電子郵件問題報告。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-117">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="a3f5c-118">如需詳細資訊，請參閱 [新式 EAC 中優先順序帳戶報告的電子郵件問題](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="a3f5c-118">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="a3f5c-119">如需優先順序帳戶的安全性最佳作法，請參閱 [優先順序帳戶的安全性建議](../../security/office-365-security/security-recommendations-for-priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-119">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a3f5c-120">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="a3f5c-120">Before you begin</span></span>

<span data-ttu-id="a3f5c-121">本主題中所述的「 **優先順序帳戶保護** 」功能僅適用于符合下列需求的組織：</span><span class="sxs-lookup"><span data-stu-id="a3f5c-121">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="a3f5c-122">適用于 Office 365 方案2（包括具有 Office 365 E3、Office 365 E5、Microsoft 365 E5 或 Microsoft 365 E5 安全性的 Microsoft Defender）。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-122">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="a3f5c-123">本主題中所述 **進階版郵件 Flow 監控** 功能僅適用于符合下列需求的組織：</span><span class="sxs-lookup"><span data-stu-id="a3f5c-123">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="a3f5c-124">您的組織必須具有至少5000的授權計數，或是下列產品的組合中的其中一個，或是下列產品的組合： Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-124">Your organization needs to have a license count of at least 5,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="a3f5c-125">例如，您的組織可以擁有 3,000 個 Office 365 E3 授權，以及 2,500 個 Microsoft 365 E5，總計為 5,500 個合格產品的授權。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-125">For example, your organization can have 3,000 Office 365 E3 licenses and 2,500 Microsoft 365 E5, for a total of 5,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="a3f5c-126">您的組織每月至少需要有 50 位作用中 Exchange Online 使用者</span><span class="sxs-lookup"><span data-stu-id="a3f5c-126">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="a3f5c-127">您可以監控最多250個優先順序的帳戶。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-127">You can monitor up to 250 priority accounts.</span></span>

<span data-ttu-id="a3f5c-128">當您對信箱套用優先順序帳戶保護時，您也應該對擁有信箱存取權的使用者套用優先順序帳戶保護 (例如，CEO 及 CEO 的執行助理負責管理 CEO 的行事曆) 。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-128">When you apply priority account protection to a mailbox, you should also apply priority account protection to users who have access to the mailbox (for example, the CEO and the CEO's executive assistant who manages the CEO's calendar).</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="a3f5c-129">從設定頁面新增優先順序帳戶</span><span class="sxs-lookup"><span data-stu-id="a3f5c-129">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="a3f5c-130">在 [ **設定] 頁面** 中新增優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-130">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="a3f5c-131">移至 Microsoft 365 系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-131">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a3f5c-132">移至 [**設定**  >  **組織知識**]，然後選擇 [**監視最重要的帳戶**] 底下的 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-132">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="a3f5c-133">選取 [**入門**] 或 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-133">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="a3f5c-134">在 [ **新增優先順序帳戶** ] 頁面上的搜尋欄位中，輸入您要新增至 [優先順序帳戶] 清單之人員的名稱或電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-134">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="a3f5c-135">您也可以針對失敗或延遲的電子郵件設定電子郵件閾值，並取得優先順序帳戶問題的每週報告。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-135">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="a3f5c-136">選取使用者，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-136">Select the user and choose **Save**.</span></span>

<span data-ttu-id="a3f5c-137">您也可以從 [作用中的使用者] 頁面新增優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-137">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="a3f5c-138">從 [作用中使用者新增優先順序帳戶] 頁面</span><span class="sxs-lookup"><span data-stu-id="a3f5c-138">Add priority accounts from Active users page</span></span>

<span data-ttu-id="a3f5c-139">從 [作用中的使用者] 頁面新增優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-139">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="a3f5c-140">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-140">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a3f5c-141">移至 [**使用者**] [作用中的  >  **使用者**]，然後在頁面頂端 ([其他動作]) 的三個點。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-141">Go to **Users** > **Active users** and select the three dots (more actions) at the top of the page.</span></span> <span data-ttu-id="a3f5c-142">選取 [ **管理優先順序帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-142">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="a3f5c-143">選取 [ **新增帳戶**]，然後在 [ **新增優先順序帳戶** ] 頁面的 [搜尋] 欄位中，輸入您要新增至 [優先順序帳戶] 清單的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-143">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="a3f5c-144">選取使用者，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-144">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="a3f5c-145">從 [優先順序帳戶] 清單中移除使用者</span><span class="sxs-lookup"><span data-stu-id="a3f5c-145">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="a3f5c-146">移至 Microsoft 365 系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-146">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a3f5c-147">移至 [**設定**  >  **組織知識**]，然後選擇 [**監視最重要的帳戶**] 底下的 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-147">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="a3f5c-148">在 [**監視您的大部分帳戶**] 頁面上，選擇 [**管理此功能**] 底下的 [**優先順序帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-148">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="a3f5c-149">在 [ **優先順序帳戶** ] 頁面上，選取您要從清單中移除的使用者，然後選擇 [ **移除帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="a3f5c-149">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a3f5c-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="a3f5c-150">Related topics</span></span>

[<span data-ttu-id="a3f5c-151">在 Microsoft 365 中使用優先順序帳戶</span><span class="sxs-lookup"><span data-stu-id="a3f5c-151">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
