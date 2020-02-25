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
search.appverid:
- MET150
- MOE150
description: 您可以建立及使用範本來節省時間和標準化的設定，當您新增多位使用者。
ms.openlocfilehash: a81b9c6673503c0c7aaec9b804f8e1357a7b6c5f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239395"
---
# <a name="create-and-use-a-template-to-add-users"></a><span data-ttu-id="eefa8-103">建立並使用範本來新增使用者</span><span class="sxs-lookup"><span data-stu-id="eefa8-103">Create and use a template to add users</span></span>

<span data-ttu-id="eefa8-104">您可以建立及使用範本來節省時間和標準化的設定，當您要新增多個使用者。</span><span class="sxs-lookup"><span data-stu-id="eefa8-104">You can create and use a template to save time and standardize settings when you are adding multiple users.</span></span> <span data-ttu-id="eefa8-105">範本會特別有用，如果您有共用許多常見屬性，如使用者有相同的角色，且在相同的位置和那些人員需要相同的軟體工作的使用者。</span><span class="sxs-lookup"><span data-stu-id="eefa8-105">Templates are particularly useful if you have users who share many common properties, like those who have the same role and work at the same location and those who require the same software.</span></span> <span data-ttu-id="eefa8-106">例如，您可能必須支援工程師合作相同的 office 中的小組。</span><span class="sxs-lookup"><span data-stu-id="eefa8-106">For example, you might have a team of support engineers who work in the same office.</span></span>  

## <a name="create-a-template"></a><span data-ttu-id="eefa8-107">建立範本</span><span class="sxs-lookup"><span data-stu-id="eefa8-107">Create a template</span></span>

<span data-ttu-id="eefa8-108">範本很容易建立&mdash;您可以選取**使用者** > **作用中使用者** > **使用者範本**，然後選取 [**新增範本**，從下拉式清單] 清單中，或您可以新增新的使用者，當您完成時，您必須將項目儲存為範本的選項。</span><span class="sxs-lookup"><span data-stu-id="eefa8-108">Templates are easy to create&mdash;you can select **Users** > **Active users** > **User templates**, and then select **Add a template** from the drop-down list, or you can add a new user and when you are finished, you will have the option of saving the entry as a template.</span></span>

<span data-ttu-id="eefa8-109">當您建立的範本新增使用者之後時，您選擇下列設定值會儲存在範本中：</span><span class="sxs-lookup"><span data-stu-id="eefa8-109">When you create a template after adding a user, the values you choose for the following settings are saved in the template:</span></span>

- <span data-ttu-id="eefa8-110">網域名稱</span><span class="sxs-lookup"><span data-stu-id="eefa8-110">Domain name</span></span>
- <span data-ttu-id="eefa8-111">密碼設定選擇： 您可以選擇建立密碼或已將其自動產生</span><span class="sxs-lookup"><span data-stu-id="eefa8-111">Password settings choice: you can choose to create passwords or have them auto-generated</span></span>
- <span data-ttu-id="eefa8-112">單次密碼選擇： 您可以要求使用者在第一個登入之後建立新的密碼</span><span class="sxs-lookup"><span data-stu-id="eefa8-112">One-time password choice: you can require the user to create a new password after first sign in</span></span>
- <span data-ttu-id="eefa8-113">授權位置</span><span class="sxs-lookup"><span data-stu-id="eefa8-113">License location</span></span>
- <span data-ttu-id="eefa8-114">授權選項</span><span class="sxs-lookup"><span data-stu-id="eefa8-114">License choices</span></span>
- <span data-ttu-id="eefa8-115">應用程式選項</span><span class="sxs-lookup"><span data-stu-id="eefa8-115">Application choices</span></span>
- <span data-ttu-id="eefa8-116">角色</span><span class="sxs-lookup"><span data-stu-id="eefa8-116">Role</span></span>
- <span data-ttu-id="eefa8-117">大部分設定檔資訊，例如**工作的設定檔**、**部門**、 **Office**、**辦公室電話**，以及 **-路/街地址**</span><span class="sxs-lookup"><span data-stu-id="eefa8-117">Most profile information, such as **Job profile**, **Department**, **Office**, **Office phone**, and **Street address**</span></span> 

<span data-ttu-id="eefa8-118">下列資訊是特定使用者，並不會儲存在範本中：</span><span class="sxs-lookup"><span data-stu-id="eefa8-118">The following information is user-specific and isn’t saved in the template:</span></span>

- <span data-ttu-id="eefa8-119">名字和姓氏</span><span class="sxs-lookup"><span data-stu-id="eefa8-119">First and last name</span></span>
- <span data-ttu-id="eefa8-120">辨別名稱 (DN)</span><span class="sxs-lookup"><span data-stu-id="eefa8-120">Display name</span></span>
- <span data-ttu-id="eefa8-121">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="eefa8-121">User name</span></span>
- <span data-ttu-id="eefa8-122">選擇要將密碼傳送電子郵件及由誰在密碼電子郵件傳送至</span><span class="sxs-lookup"><span data-stu-id="eefa8-122">Choice to send the password in email and who the password email is sent to</span></span>
- <span data-ttu-id="eefa8-123">行動電話號碼</span><span class="sxs-lookup"><span data-stu-id="eefa8-123">Mobile phone number</span></span>

<span data-ttu-id="eefa8-124">如果您選擇不要輸入資訊] 區段中的設定，這個值會是空白，該設定將不會顯示在範本中。</span><span class="sxs-lookup"><span data-stu-id="eefa8-124">If you choose not to enter information for a setting within a section, that value will be blank and that setting will not display in the template.</span></span> <span data-ttu-id="eefa8-125">例如，如果空白**職稱**，檢閱您的範本時，並使用您的範本時，**工作標題**不會出現所有。</span><span class="sxs-lookup"><span data-stu-id="eefa8-125">For example, if you leave **Job title** blank, when you review your template and when you use your template, **Job title** will not appear at all.</span></span> <span data-ttu-id="eefa8-126">如果所有的**設定檔**] 區段中設定保留空白，[**設定檔**] 區段中會顯示**無提供**在最後一個範本中。</span><span class="sxs-lookup"><span data-stu-id="eefa8-126">If you leave all the **Profile** section settings blank, the **Profile** section will display **None provided** in your final template.</span></span>

<span data-ttu-id="eefa8-127">當您選取 [**新增範本**] 選項來建立範本時，您可以選擇要完成之值。</span><span class="sxs-lookup"><span data-stu-id="eefa8-127">When you create a template by selecting the **Add a template** option, you can choose which values to complete.</span></span> <span data-ttu-id="eefa8-128">任何空白的項目會顯示為**沒有提供**範本中。</span><span class="sxs-lookup"><span data-stu-id="eefa8-128">Anything that is left blank will appear as **None provided** in the template.</span></span>

## <a name="use-a-template-to-add-a-user"></a><span data-ttu-id="eefa8-129">使用範本來新增使用者</span><span class="sxs-lookup"><span data-stu-id="eefa8-129">Use a template to add a user</span></span>

<span data-ttu-id="eefa8-130">若要使用現有的範本，將使用者新增：</span><span class="sxs-lookup"><span data-stu-id="eefa8-130">To use an existing template to add a user:</span></span>

1. <span data-ttu-id="eefa8-131">在系統管理中心中，選取 [**使用者** > **作用中的使用者**。</span><span class="sxs-lookup"><span data-stu-id="eefa8-131">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="eefa8-132">選取 [**使用者範本**，然後從下拉式清單中選取範本。</span><span class="sxs-lookup"><span data-stu-id="eefa8-132">Select **User templates**, and then select a template from the drop-down list.</span></span> <span data-ttu-id="eefa8-133">（清單會包含只有範本所建立，不那些其他系統管理員所建立）。</span><span class="sxs-lookup"><span data-stu-id="eefa8-133">(The list will contain only the templates that you created, not those created by other admins.)</span></span>

 > [!NOTE]
 > <span data-ttu-id="eefa8-134">您也可以使用範本來新增使用者藉由選取**使用者範本** > **管理範本**] 下，選取範本，然後選取 [**使用範本**。</span><span class="sxs-lookup"><span data-stu-id="eefa8-134">You can also use a template to add a user by selecting **User templates** > **Manage templates**, selecting a template, and then selecting **Use template**.</span></span>

3. <span data-ttu-id="eefa8-135">請依照下列步驟來建立使用者從您所選的範本。</span><span class="sxs-lookup"><span data-stu-id="eefa8-135">Follow the steps to create a user from the template you selected.</span></span>

> [!NOTE]
> <span data-ttu-id="eefa8-136">如果您有不足，無法供您新增使用者的授權，而您的付款資訊，我們會嘗試購買其他授權，使用您現有的付款資訊。</span><span class="sxs-lookup"><span data-stu-id="eefa8-136">If you have insufficient licenses available for a user that you add, and your payment information is available, we will attempt to purchase another license using your existing payment information.</span></span> <span data-ttu-id="eefa8-137">如果您的付款資訊無法使用，使用者會被建立為未授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="eefa8-137">If your payment information is unavailable, the user will be created as an unlicensed user.</span></span>

## <a name="manage-templates"></a><span data-ttu-id="eefa8-138">管理範本</span><span class="sxs-lookup"><span data-stu-id="eefa8-138">Manage templates</span></span>

<span data-ttu-id="eefa8-139">您可以輕鬆地刪除您不再需要並加入新的範本。</span><span class="sxs-lookup"><span data-stu-id="eefa8-139">You can easily delete templates you no longer need and add new ones.</span></span> <span data-ttu-id="eefa8-140">若要刪除範本：</span><span class="sxs-lookup"><span data-stu-id="eefa8-140">To delete a template:</span></span>

1. <span data-ttu-id="eefa8-141">在系統管理中心中，選取 [**使用者** > **作用中的使用者**。</span><span class="sxs-lookup"><span data-stu-id="eefa8-141">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="eefa8-142">選取**範本**]，然後從下拉式清單中選取 [**管理範本**。</span><span class="sxs-lookup"><span data-stu-id="eefa8-142">Select **Templates**, and then select **Manage templates** from the drop-down list.</span></span>

3. <span data-ttu-id="eefa8-143">會顯示範本的清單。</span><span class="sxs-lookup"><span data-stu-id="eefa8-143">A list of templates will appear.</span></span> <span data-ttu-id="eefa8-144">您可以刪除範本執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="eefa8-144">You can delete a template by doing any of the following:</span></span>
    - <span data-ttu-id="eefa8-145">選取一或多個範本，然後選取 [**刪除**。</span><span class="sxs-lookup"><span data-stu-id="eefa8-145">Select one or more templates, and then select **Delete**.</span></span> 
    - <span data-ttu-id="eefa8-146">選取三個點右邊的範本名稱，然後再選取 [**刪除**。</span><span class="sxs-lookup"><span data-stu-id="eefa8-146">Select the three dots to the right of the template name, and then select **Delete**.</span></span>
    - <span data-ttu-id="eefa8-147">選取 [範本名稱。</span><span class="sxs-lookup"><span data-stu-id="eefa8-147">Select the template name.</span></span> <span data-ttu-id="eefa8-148">當畫面的右側顯示範本的詳細資訊時，請選取 [**刪除範本**]。</span><span class="sxs-lookup"><span data-stu-id="eefa8-148">When the template details appear on the right side of your screen, select **Delete template**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="eefa8-149">相關文章</span><span class="sxs-lookup"><span data-stu-id="eefa8-149">Related articles</span></span>

[<span data-ttu-id="eefa8-150">個別或大量新增使用者至 Office 365</span><span class="sxs-lookup"><span data-stu-id="eefa8-150">Add users individually or in bulk to Office 365</span></span>](add-users.md)

[<span data-ttu-id="eefa8-151">從 Office 365 中移除前任員工</span><span class="sxs-lookup"><span data-stu-id="eefa8-151">Remove a former employee from Office 365</span></span>](remove-former-employee.md)
  