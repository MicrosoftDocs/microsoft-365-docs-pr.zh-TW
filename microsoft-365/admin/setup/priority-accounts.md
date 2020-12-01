---
title: 管理及監視優先順序帳戶
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
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477610"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="9bd4f-103">管理及監視優先順序帳戶</span><span class="sxs-lookup"><span data-stu-id="9bd4f-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="9bd4f-104">在每個 Microsoft 365 組織中，有重要的人員，也就是主管、領導者、主管或其他具有敏感、專有或高優先順序資訊存取權的使用者。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="9bd4f-105">為了協助您的組織保護這些帳戶，您現在可以將特定使用者指定為優先順序帳戶，並利用可提供額外保護的應用程式特定功能。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="9bd4f-106">在未來，其他應用程式和功能將支援優先順序帳戶，若要開始，我們已宣告兩項功能： **優先順序帳戶保護** 和 **優質郵件流程監控**。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="9bd4f-107">**優先順序帳戶保護** -Microsoft Defender for office 365 (過去是 office 365 的「高級威脅防護」) 支援優先順序帳戶，作為可在警示、報告和調查篩選中使用的標記。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="9bd4f-108">如需詳細資訊，請參閱 [Microsoft Defender For Office 365 中的使用者標記](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="9bd4f-109">**優質郵件流程監控** -狀況良好的郵件流程對商務成功來說可能很重要，且傳遞延遲或失敗可能對業務造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="9bd4f-110">您可以針對失敗或延遲的電子郵件選擇臨界值，當超過該臨界值時接收通知，然後查看優先順序帳戶的電子郵件問題報告。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="9bd4f-111">如需詳細資訊，請參閱 [新式 EAC 中「優先順序帳戶」報告的電子郵件問題](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9bd4f-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="9bd4f-112">Before you begin</span></span>

<span data-ttu-id="9bd4f-113">本主題中所述的「 **優先順序帳戶保護** 」功能僅適用于符合下列需求的組織：</span><span class="sxs-lookup"><span data-stu-id="9bd4f-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="9bd4f-114">Microsoft Defender for Office 365 方案2，包括具備 Office 365 E3 的 office 365 E5、Microsoft 365 E5 或 Microsoft 365 E5 Security。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="9bd4f-115">本主題中所述的 **高級郵件流程監控** 功能僅適用于符合下列需求的組織：</span><span class="sxs-lookup"><span data-stu-id="9bd4f-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="9bd4f-116">您的組織必須具有至少10000的授權計數，也就是下列產品的其中一個或下列產品的組合： Office 365 E3，Microsoft 365 E3，Office 365 E5，Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="9bd4f-117">例如，您的組織可以有 3000 Office 365 E3 授權和 8500 Microsoft 365 E5，以提供來自合格產品的全部11500授權。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="9bd4f-118">您的組織必須至少要有50個月的活動 Exchange Online 使用者。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="9bd4f-119">您可以監控最多250個優先順序的帳戶。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="9bd4f-120">從設定頁面新增優先順序帳戶</span><span class="sxs-lookup"><span data-stu-id="9bd4f-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="9bd4f-121">在 [ **設定] 頁面** 中新增優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="9bd4f-122">移至 Microsoft 365 系統管理中心，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="9bd4f-123">移至 [**設定**  >  **組織知識**]，然後選擇 [**監視最重要的帳戶**] 底下的 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="9bd4f-124">選擇 [ **開始** ] 或 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="9bd4f-125">在 [ **新增優先順序帳戶** ] 頁面上的搜尋欄位中，輸入您要新增至 [優先順序帳戶] 清單之人員的名稱或電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="9bd4f-126">您也可以針對失敗或延遲的電子郵件設定電子郵件閾值，並取得優先順序帳戶問題的每週報告。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="9bd4f-127">選取使用者，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="9bd4f-128">您也可以從 [作用中的使用者] 頁面新增優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="9bd4f-129">從 [作用中使用者新增優先順序帳戶] 頁面</span><span class="sxs-lookup"><span data-stu-id="9bd4f-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="9bd4f-130">從 [作用中的使用者] 頁面新增優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="9bd4f-131">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="9bd4f-132">移至 [**使用者** 作用中  >  **使用者**]，然後選擇頁面頂端 **的 [...** ]。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="9bd4f-133">選取 [ **管理優先順序帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="9bd4f-134">選取 [ **新增帳戶**]，然後在 [ **新增優先順序帳戶** ] 頁面的 [搜尋] 欄位中，輸入您要新增至 [優先順序帳戶] 清單的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="9bd4f-135">選取使用者，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="9bd4f-136">從 [優先順序帳戶] 清單中移除使用者</span><span class="sxs-lookup"><span data-stu-id="9bd4f-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="9bd4f-137">移至 Microsoft 365 系統管理中心，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="9bd4f-138">移至 [**設定**  >  **組織知識**]，然後選擇 [**監視最重要的帳戶**] 底下的 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="9bd4f-139">在 [**監視您的大部分帳戶**] 頁面上，選擇 [**管理此功能**] 底下的 [**優先順序帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="9bd4f-140">在 [ **優先順序帳戶** ] 頁面上，選取您要從清單中移除的使用者，然後選擇 [ **移除帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9bd4f-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="9bd4f-141">Related topics</span></span>

[<span data-ttu-id="9bd4f-142">在 Microsoft 365 中使用優先順序帳戶</span><span class="sxs-lookup"><span data-stu-id="9bd4f-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)