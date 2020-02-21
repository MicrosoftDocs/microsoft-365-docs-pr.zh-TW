---
title: 測試人員風險管理通知範本
description: 了解測試人員風險管理 Microsoft 365 中的通知範本
keywords: Microsoft 365, 測試人員風險管理, 風險管理, 合規性
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 92844691cba4adf39c7b4eee30de97ccff9d0890
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179084"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="8de66-104">測試人員風險管理通知範本</span><span class="sxs-lookup"><span data-stu-id="8de66-104">Insider risk management notice templates</span></span>

<span data-ttu-id="8de66-105">測試人員風險管理看到範本，可讓您將電子郵件傳送給員工，當使用者活動所產生的原則相符項目和警示。</span><span class="sxs-lookup"><span data-stu-id="8de66-105">Insider risk management notice templates allow you to send email messages to employees when their activities generate a policy match and alert.</span></span> <span data-ttu-id="8de66-106">在大多數情況下，產生警示的員工動作是錯誤或沒有不良意圖不慎活動的結果。</span><span class="sxs-lookup"><span data-stu-id="8de66-106">In most cases, employee actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="8de66-107">通知做為簡單的提醒給員工更仔細或重新整理程式訓練或公司的政策資源提供的連結或資訊。</span><span class="sxs-lookup"><span data-stu-id="8de66-107">Notices serve as simple reminders to employees to be more careful or to provide links or information for refresher training or corporate policy resources.</span></span> <span data-ttu-id="8de66-108">通知可以是您的內部規範訓練程式很重要的一部分，且可協助您建立含有週期性風險活動的員工所記錄的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="8de66-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for employees with recurring risk activities.</span></span>

<span data-ttu-id="8de66-109">如果您想要傳送給使用者的電子郵件提醒通知的原則相符項目是此問題： 解析程序的一部分，請建立通知範本。</span><span class="sxs-lookup"><span data-stu-id="8de66-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="8de66-110">只能以經過檢閱特定警示相關聯的員工電子郵件地址傳送通知。</span><span class="sxs-lookup"><span data-stu-id="8de66-110">Notices can only be sent to the employee email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="8de66-111">當選取要套用至原則相符項目通知範本，您可以選擇接受範本中定義的欄位值或視需要覆寫欄位。</span><span class="sxs-lookup"><span data-stu-id="8de66-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="8de66-112">請注意範本儀表板</span><span class="sxs-lookup"><span data-stu-id="8de66-112">Notice templates dashboard</span></span>

<span data-ttu-id="8de66-113">**通知範本儀表板**會顯示設定的通知範本的清單，並可讓您建立新的通知範本。</span><span class="sxs-lookup"><span data-stu-id="8de66-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="8de66-114">反向順序列出的通知範本與要先列出最新的通知範本。</span><span class="sxs-lookup"><span data-stu-id="8de66-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![測試人員風險管理通知範本儀表板](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="8de66-116">傳送通知的 HTML</span><span class="sxs-lookup"><span data-stu-id="8de66-116">HTML for notices</span></span>

<span data-ttu-id="8de66-117">如果您想要建立多個簡單文字型電子郵件通知，您可以使用 HTML 在郵件內文] 欄位中的通知範本來建立更詳細的訊息。</span><span class="sxs-lookup"><span data-stu-id="8de66-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="8de66-118">下列範例會將郵件內文格式提供基本的 HTML 電子郵件通知範本：</span><span class="sxs-lookup"><span data-stu-id="8de66-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> <span data-ttu-id="8de66-119">測試人員風險管理中的 HTML href 屬性實作注意到目前支援 URL 參照僅單引號記號而不是雙引號的範本。</span><span class="sxs-lookup"><span data-stu-id="8de66-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="8de66-120">建立新的通知範本</span><span class="sxs-lookup"><span data-stu-id="8de66-120">Create a new notice template</span></span>

<span data-ttu-id="8de66-121">若要建立新的測試人員風險管理會注意到範本，您將在 Microsoft 365 合規性中心**測試人員風險管理**解決方案中使用 [通知] 精靈。</span><span class="sxs-lookup"><span data-stu-id="8de66-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="8de66-122">完成下列步驟來建立新的測試人員風險管理通知範本：</span><span class="sxs-lookup"><span data-stu-id="8de66-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="8de66-123">在[Microsoft 365 合規性中心](https://compliance.microsoft.com)，移至**測試人員風險管理**並選取 [**通知範本**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8de66-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="8de66-124">選取 [**建立通知範本**，以開啟 [通知] 精靈。</span><span class="sxs-lookup"><span data-stu-id="8de66-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="8de66-125">在 [**建立新的通知範本**] 頁面上，完成下列欄位：</span><span class="sxs-lookup"><span data-stu-id="8de66-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="8de66-126">**範本名稱**： 輸入通知的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="8de66-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="8de66-127">從案例傳送通知時，這個名稱會出現在通知通知儀表板上和在通知的選取範圍] 清單中的清單。</span><span class="sxs-lookup"><span data-stu-id="8de66-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="8de66-128">**從傳送**： 輸入通知寄件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8de66-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="8de66-129">這個地址將會出現在**從：** 欄位中所有通知傳送給員工，除非變更時將通知傳送從案例。</span><span class="sxs-lookup"><span data-stu-id="8de66-129">This address will appear in the **From:** field in all notices sent to employees unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="8de66-130">**[副本] 及 [密件副本**欄位： 選用的使用者或群組原則相符項目，從您訂閱的 Active Directory 中所選取的通知。</span><span class="sxs-lookup"><span data-stu-id="8de66-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="8de66-131">**主旨**： 郵件的主旨行中顯示的資訊支援文字字元。</span><span class="sxs-lookup"><span data-stu-id="8de66-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="8de66-132">**郵件內文**： 會出現在郵件本文的資訊支援文字或 HTML 值。</span><span class="sxs-lookup"><span data-stu-id="8de66-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="8de66-133">選取 [**建立**]，以建立和儲存的通知範本或選取 [**取消**] 以關閉而不儲存的通知範本。</span><span class="sxs-lookup"><span data-stu-id="8de66-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="8de66-134">更新通知範本</span><span class="sxs-lookup"><span data-stu-id="8de66-134">Update a notice template</span></span>

<span data-ttu-id="8de66-135">若要更新現有的測試人員風險管理注意到範本中，完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8de66-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="8de66-136">在[Microsoft 365 合規性中心](https://compliance.microsoft.com)，移至**測試人員風險管理**並選取 [**通知範本**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8de66-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="8de66-137">在通知儀表板中，選取您想要管理的通知範本。</span><span class="sxs-lookup"><span data-stu-id="8de66-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="8de66-138">在通知詳細資料] 頁面上，選取 [**編輯**]</span><span class="sxs-lookup"><span data-stu-id="8de66-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="8de66-139">在 [**編輯**] 頁面上，您可以編輯下列欄位：</span><span class="sxs-lookup"><span data-stu-id="8de66-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="8de66-140">**範本名稱**： 輸入新的易記名稱的注意事項。</span><span class="sxs-lookup"><span data-stu-id="8de66-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="8de66-141">從案例傳送通知時，這個名稱會出現在通知通知儀表板上和在通知的選取範圍] 清單中的清單。</span><span class="sxs-lookup"><span data-stu-id="8de66-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="8de66-142">**從傳送**： 更新通知的寄件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8de66-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="8de66-143">這個地址將會出現在**從：** 欄位中所有通知傳送給員工，除非變更時將通知傳送從案例。</span><span class="sxs-lookup"><span data-stu-id="8de66-143">This address will appear in the **From:** field in all notices sent to employees unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="8de66-144">**[副本] 及 [密件副本**欄位： 更新選用的使用者或群組原則相符項目，從您訂閱的 Active Directory 中所選取的通知。</span><span class="sxs-lookup"><span data-stu-id="8de66-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="8de66-145">**主旨**： 郵件的主旨行中顯示的最新更新資訊支援文字字元。</span><span class="sxs-lookup"><span data-stu-id="8de66-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="8de66-146">**郵件內文**： 更新資訊，會出現在郵件本文中，支援文字或 HTML 值。</span><span class="sxs-lookup"><span data-stu-id="8de66-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="8de66-147">選取 [**儲存**] 以更新，並儲存通知或選取 [**取消**] 以關閉而不儲存的通知範本。</span><span class="sxs-lookup"><span data-stu-id="8de66-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="8de66-148">刪除通知範本</span><span class="sxs-lookup"><span data-stu-id="8de66-148">Delete a notice template</span></span>

<span data-ttu-id="8de66-149">若要刪除現有的測試人員風險管理注意到範本中，完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8de66-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="8de66-150">在[Microsoft 365 合規性中心](https://compliance.microsoft.com)，移至**測試人員風險管理**並選取 [**通知範本**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8de66-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="8de66-151">在通知儀表板中，選取您想要刪除的通知範本。</span><span class="sxs-lookup"><span data-stu-id="8de66-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="8de66-152">選取 [在工具列上的 [**刪除**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="8de66-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="8de66-153">若要刪除的通知範本，請選取 [刪除] 對話方塊中的 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="8de66-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="8de66-154">若要取消刪除，請選取 [**取消**。</span><span class="sxs-lookup"><span data-stu-id="8de66-154">To cancel the deletion, select **Cancel**.</span></span>
