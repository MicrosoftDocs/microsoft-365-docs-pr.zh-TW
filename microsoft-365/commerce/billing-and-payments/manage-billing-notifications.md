---
title: 管理帳單通知和發票附件
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: prkalid, guyb
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
search.appverid:
- MET150
description: 瞭解如何管理接收帳單通知電子郵件和發票附件的人員。
ms.date: 03/17/2021
ms.openlocfilehash: a49598cd1b361a85af8455b0aff19e11fcf96526
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203241"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="7ebd1-103">管理帳單通知和發票附件</span><span class="sxs-lookup"><span data-stu-id="7ebd1-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="7ebd1-104">[ **帳單通知** ] 頁面可讓您管理誰接收您組織的帳單通知電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="7ebd1-105">此頁面也提供將 [組織的發票當做電子郵件附件接收](#receive-your-organizations-invoices-as-email-attachments)的選項。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7ebd1-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="7ebd1-106">Before you begin</span></span>

<span data-ttu-id="7ebd1-107">您必須是全域系統管理員，才能執行本文所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="7ebd1-108">計費系統管理員可以進行一些變更，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="7ebd1-109">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="7ebd1-110">變更您接收電子郵件的語言</span><span class="sxs-lookup"><span data-stu-id="7ebd1-110">Change the language you receive email in</span></span>

<span data-ttu-id="7ebd1-111">計費通知電子郵件會以組織的慣用語言傳送。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-111">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="7ebd1-112">若要變更慣用語言，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-112">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="7ebd1-113">在 Microsoft 365 系統管理中心中，移至 [**帳單**] [帳單  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">通知</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-113">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7ebd1-114">在 [ **帳單通知設定** ] 區段中，選取 [ **編輯通知設定**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-114">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="7ebd1-115">在 [ **帳單通知設定** ] 窗格中的 [ **喜好語言** ] 下，選取您要使用的語言，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-115">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="7ebd1-116">變更接收帳單通知的寄件者</span><span class="sxs-lookup"><span data-stu-id="7ebd1-116">Change who receives billing notifications</span></span>

<span data-ttu-id="7ebd1-117">您組織的帳單通知會傳送至每個全域和計費系統管理員的主要和備用電子郵件地址。若要變更具有全域或計費系統管理員角色的使用者，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-117">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="7ebd1-118">使用 [帳單通知] 頁面指派系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="7ebd1-118">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="7ebd1-119">在系統管理中心中，移至 **帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">帳單通知</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7ebd1-120">在 [ **管理員接收帳單通知** ] 區段中，選取 [描述文字] 中的 [ **帳單管理員** ] 或 [ **全域管理員** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-120">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="7ebd1-121">在右窗格的 [指派的系統 **管理員** ] 索引標籤上，選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-121">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="7ebd1-122">在 [ **新增系統管理員** ] 窗格中，輸入使用者的顯示名稱或使用者名稱，然後從建議清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-122">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="7ebd1-123">在您完成之前，新增多個使用者。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-123">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="7ebd1-124">選取 \*\*\*\*[儲存]。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-124">Select **Save**.</span></span> <span data-ttu-id="7ebd1-125">使用者已新增至指派的系統管理員清單。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-125">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="7ebd1-126">使用 [帳單通知] 頁面移除系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="7ebd1-126">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="7ebd1-127">在系統管理中心中，移至 **帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">帳單通知</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7ebd1-128">在 [ **管理員接收帳單通知** ] 區段中，選取 [描述文字] 中的 [ **帳單管理員** ] 或 [ **全域管理員** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-128">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="7ebd1-129">在右窗格的 [指派的系統 **管理員** ] 索引標籤上，選取要從角色中移除的使用者，然後選取 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-129">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="7ebd1-130">在 [確認] 方塊中，選取 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-130">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="7ebd1-131">使用者會從指派的系統管理員清單中移除。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-131">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="7ebd1-132">變更系統管理員的電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="7ebd1-132">Change the email addresses for admins</span></span>

<span data-ttu-id="7ebd1-133">若要變更組織中其他系統管理員的主要和備用電子郵件地址，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-133">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="7ebd1-134">計費系統管理員可以變更自己的主要和備用電子郵件地址，但不能變更其他管理員。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-134">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="7ebd1-135">在系統管理中心中，移至 **帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">帳單通知</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7ebd1-136">在 [ **管理員接收帳單通知** ] 區段中，選取名稱。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-136">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="7ebd1-137">在右窗格中，視需要新增或更新主要和備用的電子郵件地址，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-137">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="7ebd1-138">變更組織的連絡人電子郵件</span><span class="sxs-lookup"><span data-stu-id="7ebd1-138">Change your organization's contact email</span></span>

<span data-ttu-id="7ebd1-139">除了通用和計費系統管理員之外，我們還會將帳單通知傳送給您組織的連絡人電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-139">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="7ebd1-140">若要變更電子郵件地址，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-140">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="7ebd1-141">在系統管理中心中，移至 **帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">帳單通知</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-141">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7ebd1-142">在 [ **組織連絡人接收帳單通知**] 底下，選取組織連絡人。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-142">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="7ebd1-143">在右窗格中，輸入您要使用的電子郵件地址，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-143">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="7ebd1-144">以電子郵件附件形式接收組織的發票</span><span class="sxs-lookup"><span data-stu-id="7ebd1-144">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="7ebd1-145">計費系統管理員也可以執行本節中的步驟。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-145">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="7ebd1-146">您可以將組織發票的複本附加為 PDF 檔案，以在新發票準備好時開具發票通知電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-146">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="7ebd1-147">使用下列步驟，以附件形式接收發票。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-147">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="7ebd1-148">在系統管理中心中，移至 **帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">帳單通知</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-148">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="7ebd1-149">在 [ **帳單通知設定**] 底下，選取 [ **編輯通知設定**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-149">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="7ebd1-150">在 [ **帳單通知設定** ] 窗格中的 [ **將 PDF 附加至發票電子郵件**] 底下，選取核取方塊，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-150">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="7ebd1-151">若要停用任何時間接收發票附件，請遵循上述步驟，並清除步驟3中的 [ **將 PDF 附加到發票電子郵件** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-151">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="7ebd1-152">如果我有帳單設定檔，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="7ebd1-152">What if I have a billing profile?</span></span>

<span data-ttu-id="7ebd1-153">如果您有帳單設定檔，本文中所述的部分步驟對您的某些訂閱可能稍有不同。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-153">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="7ebd1-154">本節說明這些差異。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-154">This section describes those differences.</span></span> [<span data-ttu-id="7ebd1-155">如何知道我是否有帳單設定檔？</span><span class="sxs-lookup"><span data-stu-id="7ebd1-155">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="7ebd1-156">神秘接收帳單通知？</span><span class="sxs-lookup"><span data-stu-id="7ebd1-156">Who receives Billing notifications?</span></span>

<span data-ttu-id="7ebd1-157">對於指派有下列其中一個角色的使用者，計費通知電子郵件會傳送至主要和備用電子郵件地址：</span><span class="sxs-lookup"><span data-stu-id="7ebd1-157">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="7ebd1-158">計費設定檔擁有者</span><span class="sxs-lookup"><span data-stu-id="7ebd1-158">Billing profile owner</span></span>
- <span data-ttu-id="7ebd1-159">帳單設定檔參與者</span><span class="sxs-lookup"><span data-stu-id="7ebd1-159">Billing profile contributor</span></span>
- <span data-ttu-id="7ebd1-160">發票管理員</span><span class="sxs-lookup"><span data-stu-id="7ebd1-160">Invoice manager</span></span>

<span data-ttu-id="7ebd1-161">若要深入瞭解計費設定檔角色及其管理方式，請參閱 [瞭解 Microsoft 客戶合約在 Azure 中的管理角色](/azure/cost-management-billing/manage/understand-mca-roles)。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-161">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="7ebd1-162">若要變更接收組織的帳單通知的人員，請使用下列步驟來變更指派給使用者的角色。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-162">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="7ebd1-163">在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">票據 & 付款</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-163">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="7ebd1-164">在 [ **記帳設定檔** ] 索引標籤上，選取帳單設定檔。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-164">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="7ebd1-165">在 [ **帳單設定檔角色** ] 區段中，指派或移除 **計費設定檔擁有** 人、 **帳單設定檔參與者** 或 **發票管理員** 的角色。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-165">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="7ebd1-166">以電子郵件附件形式接收發票</span><span class="sxs-lookup"><span data-stu-id="7ebd1-166">Receive invoices as email attachments</span></span>

<span data-ttu-id="7ebd1-167">若要將發票當做附件接收到發票通知，請使用下列步驟來開啟特定計費設定檔的此設定。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-167">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="7ebd1-168">在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">票據 & 付款</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-168">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="7ebd1-169">選取 [ **帳單設定檔** ] 索引標籤，然後從清單中選取帳單設定檔。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-169">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="7ebd1-170">在 [帳單設定檔詳細資料] 頁面的 [在 **電子郵件附件中取得發票**] 底下，將開關切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7ebd1-170">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="7ebd1-171">相關內容</span><span class="sxs-lookup"><span data-stu-id="7ebd1-171">Related content</span></span>

<span data-ttu-id="7ebd1-172">[檢視帳單](view-your-bill-or-invoice.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="7ebd1-172">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="7ebd1-173">[墨西哥企業的 Microsoft 365 帳單資訊](mexico-billing-info.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="7ebd1-173">[Billing information for Microsoft 365 for business in Mexico](mexico-billing-info.md) (article) \</span></span>
<span data-ttu-id="7ebd1-174">[瞭解商務用 Microsoft 365 帳單或發票](understand-your-invoice2.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="7ebd1-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="7ebd1-175">[同時新增使用者並指派授權](../../admin/add-users/add-users.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="7ebd1-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>
