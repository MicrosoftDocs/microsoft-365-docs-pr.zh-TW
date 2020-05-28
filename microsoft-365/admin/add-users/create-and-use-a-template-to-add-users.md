---
title: 建立並使用範本來新增使用者
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: 您可以建立並使用範本，以在您新增多個使用者時節省時間和標準化設定。
ms.openlocfilehash: 3173d28f27acdf1a084137d36cd71894e94e9547
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387222"
---
# <a name="create-and-use-a-template-to-add-users"></a><span data-ttu-id="806ab-103">建立並使用範本來新增使用者</span><span class="sxs-lookup"><span data-stu-id="806ab-103">Create and use a template to add users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="806ab-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="806ab-104">The admin center is changing.</span></span> <span data-ttu-id="806ab-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="806ab-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="806ab-106">您可以建立並使用範本，以在您新增多個使用者時節省時間和標準化設定。</span><span class="sxs-lookup"><span data-stu-id="806ab-106">You can create and use a template to save time and standardize settings when you are adding multiple users.</span></span> <span data-ttu-id="806ab-107">如果您有共用許多通用屬性的使用者，例如具有相同角色的使用者，以及需要相同軟體的使用者，則範本特別有用。</span><span class="sxs-lookup"><span data-stu-id="806ab-107">Templates are particularly useful if you have users who share many common properties, like those who have the same role and work at the same location and those who require the same software.</span></span> <span data-ttu-id="806ab-108">例如，您可能有一個支援工程師小組，可在相同的 office 中工作。</span><span class="sxs-lookup"><span data-stu-id="806ab-108">For example, you might have a team of support engineers who work in the same office.</span></span>  

## <a name="create-a-template"></a><span data-ttu-id="806ab-109">建立範本</span><span class="sxs-lookup"><span data-stu-id="806ab-109">Create a template</span></span>

<span data-ttu-id="806ab-110">可輕鬆建立範本 &mdash; 您可以選取 [**使用者**作用中  >  **使用者**]  >  **使用者範本**，然後從下拉式清單中選取 [**新增範本**]，或者您可以新增使用者，並在完成時，您可以選擇將專案儲存為範本。</span><span class="sxs-lookup"><span data-stu-id="806ab-110">Templates are easy to create&mdash;you can select **Users** > **Active users** > **User templates**, and then select **Add a template** from the drop-down list, or you can add a new user and when you are finished, you will have the option of saving the entry as a template.</span></span>

<span data-ttu-id="806ab-111">在新增使用者之後建立範本後，您針對下列設定所選擇的值會儲存在範本中：</span><span class="sxs-lookup"><span data-stu-id="806ab-111">When you create a template after adding a user, the values you choose for the following settings are saved in the template:</span></span>

- <span data-ttu-id="806ab-112">網域名稱</span><span class="sxs-lookup"><span data-stu-id="806ab-112">Domain name</span></span>
- <span data-ttu-id="806ab-113">密碼設定選項：您可以選擇建立密碼或自動產生密碼</span><span class="sxs-lookup"><span data-stu-id="806ab-113">Password settings choice: you can choose to create passwords or have them auto-generated</span></span>
- <span data-ttu-id="806ab-114">一次性密碼選擇：您可以要求使用者在第一次登入後建立新密碼</span><span class="sxs-lookup"><span data-stu-id="806ab-114">One-time password choice: you can require the user to create a new password after first sign in</span></span>
- <span data-ttu-id="806ab-115">授權位置</span><span class="sxs-lookup"><span data-stu-id="806ab-115">License location</span></span>
- <span data-ttu-id="806ab-116">授權選項</span><span class="sxs-lookup"><span data-stu-id="806ab-116">License choices</span></span>
- <span data-ttu-id="806ab-117">應用程式選擇</span><span class="sxs-lookup"><span data-stu-id="806ab-117">Application choices</span></span>
- <span data-ttu-id="806ab-118">角色</span><span class="sxs-lookup"><span data-stu-id="806ab-118">Role</span></span>
- <span data-ttu-id="806ab-119">大部分設定檔資訊，例如**工作設定檔**、**部門**、 **Office**、 **office phone**及**街道位址**</span><span class="sxs-lookup"><span data-stu-id="806ab-119">Most profile information, such as **Job profile**, **Department**, **Office**, **Office phone**, and **Street address**</span></span> 

<span data-ttu-id="806ab-120">下列是使用者特有的資訊，而且不會儲存在範本中：</span><span class="sxs-lookup"><span data-stu-id="806ab-120">The following information is user-specific and isn't saved in the template:</span></span>

- <span data-ttu-id="806ab-121">名字和姓氏</span><span class="sxs-lookup"><span data-stu-id="806ab-121">First and last name</span></span>
- <span data-ttu-id="806ab-122">辨別名稱 (DN)</span><span class="sxs-lookup"><span data-stu-id="806ab-122">Display name</span></span>
- <span data-ttu-id="806ab-123">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="806ab-123">User name</span></span>
- <span data-ttu-id="806ab-124">選擇以電子郵件傳送密碼及傳送密碼的電子郵件</span><span class="sxs-lookup"><span data-stu-id="806ab-124">Choice to send the password in email and who the password email is sent to</span></span>
- <span data-ttu-id="806ab-125">行動電話號碼</span><span class="sxs-lookup"><span data-stu-id="806ab-125">Mobile phone number</span></span>

<span data-ttu-id="806ab-126">如果您選擇不輸入區段中設定的資訊，此值將會是空白的，且此設定不會顯示在範本中。</span><span class="sxs-lookup"><span data-stu-id="806ab-126">If you choose not to enter information for a setting within a section, that value will be blank and that setting will not display in the template.</span></span> <span data-ttu-id="806ab-127">例如，如果您將**職稱**保留空白，當您檢查範本和使用範本時，**職務**根本不會出現。</span><span class="sxs-lookup"><span data-stu-id="806ab-127">For example, if you leave **Job title** blank, when you review your template and when you use your template, **Job title** will not appear at all.</span></span> <span data-ttu-id="806ab-128">如果您將所有**設定檔**區段設定保留空白，則**設定檔**區段會顯示您的最終範本中**無提供**的內容。</span><span class="sxs-lookup"><span data-stu-id="806ab-128">If you leave all the **Profile** section settings blank, the **Profile** section will display **None provided** in your final template.</span></span>

<span data-ttu-id="806ab-129">當您選取 [**新增範本**] 選項來建立範本時，您可以選擇要完成的值。</span><span class="sxs-lookup"><span data-stu-id="806ab-129">When you create a template by selecting the **Add a template** option, you can choose which values to complete.</span></span> <span data-ttu-id="806ab-130">保留空白的任何內容，都將顯示為範本中提供的 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="806ab-130">Anything that is left blank will appear as **None provided** in the template.</span></span>

## <a name="use-a-template-to-add-a-user"></a><span data-ttu-id="806ab-131">使用範本新增使用者</span><span class="sxs-lookup"><span data-stu-id="806ab-131">Use a template to add a user</span></span>

<span data-ttu-id="806ab-132">若要使用現有的範本來新增使用者：</span><span class="sxs-lookup"><span data-stu-id="806ab-132">To use an existing template to add a user:</span></span>

1. <span data-ttu-id="806ab-133">在系統管理中心中，選取 [**使用者**作用中  >  **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="806ab-133">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="806ab-134">選取 [**使用者範本**]，然後從下拉式清單中選取範本。</span><span class="sxs-lookup"><span data-stu-id="806ab-134">Select **User templates**, and then select a template from the drop-down list.</span></span> <span data-ttu-id="806ab-135">（清單只會包含您建立的範本，而不會包含其他系統管理員所建立的範本）。</span><span class="sxs-lookup"><span data-stu-id="806ab-135">(The list will contain only the templates that you created, not those created by other admins.)</span></span>

 > [!NOTE]
 > <span data-ttu-id="806ab-136">您也可以使用範本，選取 [**使用者範本**] [  >  **管理範本**]，選取範本，然後選取 [**使用範本**]，以新增使用者。</span><span class="sxs-lookup"><span data-stu-id="806ab-136">You can also use a template to add a user by selecting **User templates** > **Manage templates**, selecting a template, and then selecting **Use template**.</span></span>

3. <span data-ttu-id="806ab-137">依照步驟從您選取的範本建立使用者。</span><span class="sxs-lookup"><span data-stu-id="806ab-137">Follow the steps to create a user from the template you selected.</span></span>

> [!NOTE]
> <span data-ttu-id="806ab-138">如果您要新增的使用者不足以供您新增，且您的付款資訊可供使用，我們會嘗試使用您現有的付款資訊購買其他授權。</span><span class="sxs-lookup"><span data-stu-id="806ab-138">If you have insufficient licenses available for a user that you add, and your payment information is available, we will attempt to purchase another license using your existing payment information.</span></span> <span data-ttu-id="806ab-139">如果您的付款資訊無法使用，則會將使用者建立為未經許可的使用者。</span><span class="sxs-lookup"><span data-stu-id="806ab-139">If your payment information is unavailable, the user will be created as an unlicensed user.</span></span>

## <a name="manage-templates"></a><span data-ttu-id="806ab-140">管理範本</span><span class="sxs-lookup"><span data-stu-id="806ab-140">Manage templates</span></span>

<span data-ttu-id="806ab-141">您可以輕鬆刪除不再需要的範本，並新增新範本。</span><span class="sxs-lookup"><span data-stu-id="806ab-141">You can easily delete templates you no longer need and add new ones.</span></span> <span data-ttu-id="806ab-142">若要刪除範本：</span><span class="sxs-lookup"><span data-stu-id="806ab-142">To delete a template:</span></span>

1. <span data-ttu-id="806ab-143">在系統管理中心中，選取 [**使用者**作用中  >  **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="806ab-143">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="806ab-144">選取 [**範本**]，然後從下拉式清單中選取 [**管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="806ab-144">Select **Templates**, and then select **Manage templates** from the drop-down list.</span></span>

3. <span data-ttu-id="806ab-145">隨即會顯示範本清單。</span><span class="sxs-lookup"><span data-stu-id="806ab-145">A list of templates will appear.</span></span> <span data-ttu-id="806ab-146">您可以執行下列任一動作來刪除範本：</span><span class="sxs-lookup"><span data-stu-id="806ab-146">You can delete a template by doing any of the following:</span></span>
    - <span data-ttu-id="806ab-147">選取一個或多個範本，然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="806ab-147">Select one or more templates, and then select **Delete**.</span></span> 
    - <span data-ttu-id="806ab-148">選取範本名稱右側的三個點，然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="806ab-148">Select the three dots to the right of the template name, and then select **Delete**.</span></span>
    - <span data-ttu-id="806ab-149">選取範本名稱。</span><span class="sxs-lookup"><span data-stu-id="806ab-149">Select the template name.</span></span> <span data-ttu-id="806ab-150">在螢幕右側顯示範本詳細資料時，請選取 [**刪除範本**]。</span><span class="sxs-lookup"><span data-stu-id="806ab-150">When the template details appear on the right side of your screen, select **Delete template**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="806ab-151">相關文章</span><span class="sxs-lookup"><span data-stu-id="806ab-151">Related articles</span></span>

[<span data-ttu-id="806ab-152">個別或大量將使用者新增至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="806ab-152">Add users individually or in bulk to Microsoft 365</span></span>](add-users.md)

[<span data-ttu-id="806ab-153">從 Microsoft 365 移除離職員工</span><span class="sxs-lookup"><span data-stu-id="806ab-153">Remove a former employee from Microsoft 365</span></span>](remove-former-employee.md)
  
