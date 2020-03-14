---
title: 在 Office 365 中建立、編輯或刪除自訂使用者視圖
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: 瞭解如何在 Office 365 中使用篩選來建立、編輯或刪除自訂使用者視圖。
ms.openlocfilehash: ba03d3da3e8bfdc4f2a661d1dc59845a8a22609f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42632951"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="17da4-103">在 Office 365 中建立、編輯或刪除自訂使用者視圖</span><span class="sxs-lookup"><span data-stu-id="17da4-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="17da4-104">如果您是 Office 365 的全域或使用者管理系統管理員，您可以建立自訂使用者視圖，以查看特定的使用者子集。</span><span class="sxs-lookup"><span data-stu-id="17da4-104">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="17da4-105">這些視圖是除了 Office 365 隨附的標準一組視圖之外。</span><span class="sxs-lookup"><span data-stu-id="17da4-105">These views are in addition to the standard set of views that come with Office 365.</span></span> <span data-ttu-id="17da4-106">您可以建立、編輯或刪除自訂使用者視圖，而且您建立的自訂視圖可供所有系統管理員使用。</span><span class="sxs-lookup"><span data-stu-id="17da4-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="17da4-107">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="17da4-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="17da4-108">Admin center 中的自訂使用者視圖</span><span class="sxs-lookup"><span data-stu-id="17da4-108">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="17da4-109">當您建立、編輯或刪除自訂使用者視圖時，所做的變更會顯示在您公司的所有系統管理員都看到 [**使用者**] 頁面上的 [**篩選**] 清單中。</span><span class="sxs-lookup"><span data-stu-id="17da4-109">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="17da4-110">您最多可以建立50個自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="17da4-110">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="17da4-111">當您建立、編輯或刪除自訂使用者視圖時，所做的變更會顯示在您公司的所有系統管理員都看到 [**使用者**] 頁面上的 [**視圖**] 清單中。</span><span class="sxs-lookup"><span data-stu-id="17da4-111">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="17da4-112">您最多可以建立50個自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="17da4-112">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="17da4-113">當您建立、編輯或刪除自訂使用者視圖時，所做的變更會顯示在您公司的所有系統管理員都看到 [**使用者**] 頁面上的 [**視圖**] 清單中。</span><span class="sxs-lookup"><span data-stu-id="17da4-113">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="17da4-114">您最多可以建立50個自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="17da4-114">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="17da4-115">標準使用者視圖預設會顯示在 [**篩選**] 下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="17da4-115">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="17da4-116">標準篩選包括**所有使用者**、**授權的使用者**、**來賓使用者**、**允許登入**、登**入封鎖**、未授權的**使用者**、**有錯誤的使用者**、**計費管理員**、**全域系統管理員**、**服務台管理員**、**服務管理員**和**使用者管理系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="17da4-116">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="17da4-117">您無法編輯或刪除標準視圖。</span><span class="sxs-lookup"><span data-stu-id="17da4-117">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="17da4-118">有關標準視圖的注意事項幾點：</span><span class="sxs-lookup"><span data-stu-id="17da4-118">A few things to note about standard views:</span></span> 

- <span data-ttu-id="17da4-119">如果清單中的使用者超過2000，部分標準視圖會顯示未排序的清單。</span><span class="sxs-lookup"><span data-stu-id="17da4-119">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="17da4-120">若要在清單中尋找特定的使用者，請使用搜尋方塊。</span><span class="sxs-lookup"><span data-stu-id="17da4-120">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="17da4-121">如果您未從 Microsoft 購買 Office 365，**計費系統管理員**不會出現在 [標準視圖] 清單中。</span><span class="sxs-lookup"><span data-stu-id="17da4-121">If you didn't purchase Office 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="17da4-122">For more information, see [Assigning admin roles](assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="17da4-122">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="17da4-123">選擇自訂使用者視圖的篩選</span><span class="sxs-lookup"><span data-stu-id="17da4-123">Choose the filters for your custom user view</span></span>

<span data-ttu-id="17da4-124">您可以在**自訂篩選**窗格中建立及編輯自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="17da4-124">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="17da4-125">如果您選取多個篩選選項，會取得包含符合所有選取準則之使用者的結果。</span><span class="sxs-lookup"><span data-stu-id="17da4-125">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="17da4-126">下列範例會示範如何建立名為 "加拿大 users" 的自訂視圖，以顯示位於加拿大的特定網域上的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="17da4-126">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="17da4-127">**A 網域**如果您的組織有多個網域，您可以從可用的網域下拉式清單中選擇。</span><span class="sxs-lookup"><span data-stu-id="17da4-127">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="17da4-128">**B 登錄狀態**選擇允許或封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="17da4-128">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="17da4-129">**C-位置**從國家/地區的下拉式清單中選擇位置。</span><span class="sxs-lookup"><span data-stu-id="17da4-129">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="17da4-130">**D 指派產品授權**從您的組織中可用的授權下拉式清單中選擇。</span><span class="sxs-lookup"><span data-stu-id="17da4-130">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="17da4-131">使用此篩選器顯示已指派授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="17da4-131">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="17da4-132">使用者也可以有其他授權。</span><span class="sxs-lookup"><span data-stu-id="17da4-132">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="17da4-133">您也可以在組織中使用的其他使用者設定檔詳細資料進行篩選，例如部門、城市、省或直轄市、國家或地區或職稱。</span><span class="sxs-lookup"><span data-stu-id="17da4-133">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="17da4-134">**其他條件：**</span><span class="sxs-lookup"><span data-stu-id="17da4-134">**Other conditions:**</span></span>
  
- <span data-ttu-id="17da4-135">**僅限同步**處理的使用者選取此方塊以顯示已與本機 Active Directory 同步的所有使用者，不論使用者是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="17da4-135">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="17da4-136">**發生錯誤的使用者**選取此方塊以顯示可能有布建錯誤的使用者。</span><span class="sxs-lookup"><span data-stu-id="17da4-136">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="17da4-137">**未經許可的使用者**選取此方塊，以尋找未獲指派授權的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="17da4-137">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="17da4-138">此視圖的結果也可以包含具有 Exchange 信箱，但沒有授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="17da4-138">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="17da4-139">若要特別追蹤這些使用者，請使用篩選**未經授權的使用者與 Exchange 信箱或檔案**。</span><span class="sxs-lookup"><span data-stu-id="17da4-139">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="17da4-140">此視圖的結果也可以包含有 Exchange 封存，但沒有授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="17da4-140">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="17da4-141">**具有 Exchange 信箱或封存的未授權使用者**選取此方塊以顯示在 Exchange Online 中建立且具有 Exchange 信箱，但未獲指派 Office 365 授權的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="17da4-141">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Office 365 license.</span></span> <span data-ttu-id="17da4-142">此篩選的結果包括已被指派 Exchange 封存的使用者。</span><span class="sxs-lookup"><span data-stu-id="17da4-142">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 
    
> [!TIP]
> <span data-ttu-id="17da4-143">如果您建立的自訂視圖傳回超過2000的使用者，則不會排序所產生的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="17da4-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="17da4-144">在此情況下，請使用搜尋方塊尋找使用者或編輯您的自訂視圖，以精煉搜尋。</span><span class="sxs-lookup"><span data-stu-id="17da4-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="17da4-145">建立自訂使用者視圖</span><span class="sxs-lookup"><span data-stu-id="17da4-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="17da4-146">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="17da4-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="17da4-147">在 [作用中**使用者**] 頁面上，選取 [**篩選**]，然後選取 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-147">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="17da4-148">在 [**自訂篩選**] 頁面上，輸入篩選器的名稱，選擇您自訂篩選的條件，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-148">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="17da4-149">您的自訂視圖現在會包含在篩選器的下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="17da4-149">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="17da4-150">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="17da4-150">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="17da4-151">在 [作用中**使用者**] 頁面上選取 [**視圖**]，然後選取 [**新增自訂視圖**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-151">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="17da4-152">在 [**自訂視圖**] 頁面上，輸入篩選器的名稱，選擇您自訂篩選的條件，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-152">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="17da4-153">您的自訂視圖現在會包含在篩選器的下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="17da4-153">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="17da4-154">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="17da4-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="17da4-155">在 [作用中**使用者**] 頁面上選取 [**視圖**]，然後選取 [**新增自訂視圖**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="17da4-156">在 [**自訂視圖**] 頁面上，輸入篩選器的名稱，選擇您自訂篩選的條件，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="17da4-157">您的自訂視圖現在會包含在篩選器的下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="17da4-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="17da4-158">編輯或刪除自訂使用者視圖</span><span class="sxs-lookup"><span data-stu-id="17da4-158">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="17da4-159">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="17da4-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="17da4-160">在 [作用中**使用者**] 頁面上，選取 [**篩選**]，選取您要變更的篩選，然後選取 [**編輯篩選**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-160">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="17da4-161">您只能編輯自訂的視圖。</span><span class="sxs-lookup"><span data-stu-id="17da4-161">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="17da4-162">在 [**自訂篩選**] 頁面上，視需要編輯資訊，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-162">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="17da4-163">或者，若要刪除篩選，請在頁面底部選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-163">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="17da4-164">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="17da4-164">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="17da4-165">在 [作用中**使用者**] 頁面上，選取 [**視圖**]，選取您要變更的篩選，然後選取 [**編輯此視圖**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-165">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="17da4-166">您只能編輯自訂的視圖。</span><span class="sxs-lookup"><span data-stu-id="17da4-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="17da4-167">在 [**自訂視圖**] 頁面上，視需要編輯資訊，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-167">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="17da4-168">或者，若要刪除篩選，請在頁面底部選取 [**刪除自訂視圖**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-168">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="17da4-169">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="17da4-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="17da4-170">在 [作用中**使用者**] 頁面上，選取 [**視圖**]，選取您要變更的篩選，然後選取 [**編輯此視圖**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="17da4-171">您只能編輯自訂的視圖。</span><span class="sxs-lookup"><span data-stu-id="17da4-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="17da4-172">在 [**自訂視圖**] 頁面上，視需要編輯資訊，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="17da4-173">或者，若要刪除篩選，請在頁面底部選取 [**刪除自訂視圖**]。</span><span class="sxs-lookup"><span data-stu-id="17da4-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     

