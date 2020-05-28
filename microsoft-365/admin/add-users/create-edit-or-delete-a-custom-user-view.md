---
title: 建立、編輯或刪除自訂使用者檢視
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: 瞭解如何使用篩選器，在 Microsoft 365 中建立、編輯或刪除自訂使用者視圖。
ms.openlocfilehash: faea21f0e5142d197cc2b90d6ade99490f9f88e3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387210"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="f9a71-103">在 Office 365 中建立、編輯或刪除自訂使用者視圖</span><span class="sxs-lookup"><span data-stu-id="f9a71-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="f9a71-104">如果您是 Office 365 的全域或使用者管理系統管理員，您可以建立自訂使用者視圖，以查看特定的使用者子集。</span><span class="sxs-lookup"><span data-stu-id="f9a71-104">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="f9a71-105">這些視圖是除了 Office 365 隨附的標準一組視圖之外。</span><span class="sxs-lookup"><span data-stu-id="f9a71-105">These views are in addition to the standard set of views that come with Office 365.</span></span> <span data-ttu-id="f9a71-106">您可以建立、編輯或刪除自訂使用者視圖，而且您建立的自訂視圖可供所有系統管理員使用。</span><span class="sxs-lookup"><span data-stu-id="f9a71-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="f9a71-107">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="f9a71-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="f9a71-108">Admin center 中的自訂使用者視圖</span><span class="sxs-lookup"><span data-stu-id="f9a71-108">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="f9a71-109">當您建立、編輯或刪除自訂使用者視圖時，所做的變更會顯示在您公司的所有系統管理員都看到 [**使用者**] 頁面上的 [**篩選**] 清單中。</span><span class="sxs-lookup"><span data-stu-id="f9a71-109">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="f9a71-110">您最多可以建立50個自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="f9a71-110">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="f9a71-111">當您建立、編輯或刪除自訂使用者視圖時，所做的變更會顯示在您公司的所有系統管理員都看到 [**使用者**] 頁面上的 [**視圖**] 清單中。</span><span class="sxs-lookup"><span data-stu-id="f9a71-111">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="f9a71-112">您最多可以建立50個自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="f9a71-112">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="f9a71-113">當您建立、編輯或刪除自訂使用者視圖時，所做的變更會顯示在您公司的所有系統管理員都看到 [**使用者**] 頁面上的 [**視圖**] 清單中。</span><span class="sxs-lookup"><span data-stu-id="f9a71-113">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="f9a71-114">您最多可以建立50個自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="f9a71-114">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="f9a71-115">標準使用者視圖預設會顯示在 [**篩選**] 下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="f9a71-115">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="f9a71-116">標準篩選包括**所有使用者**、**授權的使用者**、**來賓使用者**、**允許登入**、登**入封鎖**、未授權的**使用者**、**有錯誤的使用者**、**計費管理員**、**全域系統管理員**、**服務台管理員**、**服務管理員**和**使用者管理系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="f9a71-116">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="f9a71-117">您無法編輯或刪除標準視圖。</span><span class="sxs-lookup"><span data-stu-id="f9a71-117">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="f9a71-118">有關標準視圖的注意事項幾點：</span><span class="sxs-lookup"><span data-stu-id="f9a71-118">A few things to note about standard views:</span></span> 

- <span data-ttu-id="f9a71-119">如果清單中的使用者超過2000，部分標準視圖會顯示未排序的清單。</span><span class="sxs-lookup"><span data-stu-id="f9a71-119">Some standard views display an unsorted list if there are more than 2,000 users in the list.</span></span> <span data-ttu-id="f9a71-120">若要在清單中尋找特定的使用者，請使用搜尋方塊。</span><span class="sxs-lookup"><span data-stu-id="f9a71-120">To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="f9a71-121">如果您未從 Microsoft 購買 Microsoft 365，**計費系統管理員**不會出現在 [標準視圖] 清單中。</span><span class="sxs-lookup"><span data-stu-id="f9a71-121">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="f9a71-122">For more information, see [Assigning admin roles](assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f9a71-122">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="f9a71-123">選擇自訂使用者視圖的篩選</span><span class="sxs-lookup"><span data-stu-id="f9a71-123">Choose the filters for your custom user view</span></span>

<span data-ttu-id="f9a71-124">您可以在**自訂篩選**窗格中建立及編輯自訂視圖。</span><span class="sxs-lookup"><span data-stu-id="f9a71-124">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="f9a71-125">如果您選取多個篩選選項，會取得包含符合所有選取準則之使用者的結果。</span><span class="sxs-lookup"><span data-stu-id="f9a71-125">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="f9a71-126">下列範例會示範如何建立名為 "加拿大 users" 的自訂視圖，以顯示位於加拿大的特定網域上的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="f9a71-126">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="f9a71-127">**A 網域**如果您的組織有多個網域，您可以從可用的網域下拉式清單中選擇。</span><span class="sxs-lookup"><span data-stu-id="f9a71-127">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="f9a71-128">**B 登錄狀態**選擇允許或封鎖的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9a71-128">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="f9a71-129">**C-位置**從國家/地區的下拉式清單中選擇位置。</span><span class="sxs-lookup"><span data-stu-id="f9a71-129">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="f9a71-130">**D 指派產品授權**從您的組織中可用的授權下拉式清單中選擇。</span><span class="sxs-lookup"><span data-stu-id="f9a71-130">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="f9a71-131">使用此篩選器顯示已指派授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9a71-131">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="f9a71-132">使用者也可以有其他授權。</span><span class="sxs-lookup"><span data-stu-id="f9a71-132">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="f9a71-133">您也可以在組織中使用的其他使用者設定檔詳細資料進行篩選，例如部門、城市、省或直轄市、國家或地區或職稱。</span><span class="sxs-lookup"><span data-stu-id="f9a71-133">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="f9a71-134">**其他條件：**</span><span class="sxs-lookup"><span data-stu-id="f9a71-134">**Other conditions:**</span></span>
  
- <span data-ttu-id="f9a71-135">**僅限同步**處理的使用者選取此方塊以顯示已與本機 Active Directory 同步的所有使用者，不論使用者是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="f9a71-135">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="f9a71-136">**發生錯誤的使用者**選取此方塊以顯示可能有布建錯誤的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9a71-136">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="f9a71-137">**未經許可的使用者**選取此方塊，以尋找未獲指派授權的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="f9a71-137">**Unlicensed users** Select this box to find all the users who haven't been assigned a license.</span></span> <span data-ttu-id="f9a71-138">此視圖的結果也可以包含具有 Exchange 信箱，但沒有授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9a71-138">The results for this view can also include users who have an Exchange mailbox but don't have a license.</span></span> <span data-ttu-id="f9a71-139">若要特別追蹤這些使用者，請使用篩選**未經授權的使用者與 Exchange 信箱或檔案**。</span><span class="sxs-lookup"><span data-stu-id="f9a71-139">To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**.</span></span> <span data-ttu-id="f9a71-140">此視圖的結果也可以包含有 Exchange 封存，但沒有授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9a71-140">The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="f9a71-141">**具有 Exchange 信箱或封存的未授權使用者**選取此方塊以顯示 Exchange Online 中所建立的使用者帳戶，並有 Exchange 信箱，但未獲指派 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="f9a71-141">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="f9a71-142">此篩選的結果包括已被指派 Exchange 封存的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9a71-142">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="f9a71-143">**具有 Exchange 信箱的未經許可使用者**可在下列情況中運作：</span><span class="sxs-lookup"><span data-stu-id="f9a71-143">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="f9a71-144">信箱最近從**共用**轉換為**使用者**，而且沒有授權。</span><span class="sxs-lookup"><span data-stu-id="f9a71-144">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="f9a71-145">信箱最近已遷移至 Microsoft 365，但是尚未指派授權。</span><span class="sxs-lookup"><span data-stu-id="f9a71-145">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="f9a71-146">信箱已使用 PowerShell 建立，尚未指派授權。</span><span class="sxs-lookup"><span data-stu-id="f9a71-146">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="f9a71-147">會為使用者布建已使用 New-RemoteMailbox Cmdlet 建立內部部署的新信箱。</span><span class="sxs-lookup"><span data-stu-id="f9a71-147">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="f9a71-148">如果您建立的自訂視圖傳回超過2000的使用者，則不會排序所產生的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="f9a71-148">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="f9a71-149">在此情況下，請使用搜尋方塊尋找使用者或編輯您的自訂視圖，以精煉搜尋。</span><span class="sxs-lookup"><span data-stu-id="f9a71-149">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="f9a71-150">建立自訂使用者視圖</span><span class="sxs-lookup"><span data-stu-id="f9a71-150">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f9a71-151">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f9a71-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="f9a71-152">在 [作用中**使用者**] 頁面上，選取 [**篩選**]，然後選取 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-152">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="f9a71-153">在 [**自訂篩選**] 頁面上，輸入篩選器的名稱，選擇您自訂篩選的條件，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-153">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="f9a71-154">您的自訂視圖現在會包含在篩選器的下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="f9a71-154">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f9a71-155">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f9a71-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="f9a71-156">在 [作用中**使用者**] 頁面上選取 [**視圖**]，然後選取 [**新增自訂視圖**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-156">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="f9a71-157">在 [**自訂視圖**] 頁面上，輸入篩選器的名稱，選擇您自訂篩選的條件，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-157">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="f9a71-158">您的自訂視圖現在會包含在篩選器的下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="f9a71-158">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="f9a71-159">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f9a71-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="f9a71-160">在 [作用中**使用者**] 頁面上選取 [**視圖**]，然後選取 [**新增自訂視圖**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-160">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="f9a71-161">在 [**自訂視圖**] 頁面上，輸入篩選器的名稱，選擇您自訂篩選的條件，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-161">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="f9a71-162">您的自訂視圖現在會包含在篩選器的下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="f9a71-162">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="f9a71-163">編輯或刪除自訂使用者視圖</span><span class="sxs-lookup"><span data-stu-id="f9a71-163">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f9a71-164">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f9a71-164">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="f9a71-165">在 [作用中**使用者**] 頁面上，選取 [**篩選**]，選取您要變更的篩選，然後選取 [**編輯篩選**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-165">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="f9a71-166">您只能編輯自訂的視圖。</span><span class="sxs-lookup"><span data-stu-id="f9a71-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="f9a71-167">在 [**自訂篩選**] 頁面上，視需要編輯資訊，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-167">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="f9a71-168">或者，若要刪除篩選，請在頁面底部選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-168">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f9a71-169">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f9a71-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="f9a71-170">在 [作用中**使用者**] 頁面上，選取 [**視圖**]，選取您要變更的篩選，然後選取 [**編輯此視圖**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="f9a71-171">您只能編輯自訂的視圖。</span><span class="sxs-lookup"><span data-stu-id="f9a71-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="f9a71-172">在 [**自訂視圖**] 頁面上，視需要編輯資訊，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="f9a71-173">或者，若要刪除篩選，請在頁面底部選取 [**刪除自訂視圖**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f9a71-174">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f9a71-174">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="f9a71-175">在 [作用中**使用者**] 頁面上，選取 [**視圖**]，選取您要變更的篩選，然後選取 [**編輯此視圖**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-175">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="f9a71-176">您只能編輯自訂的視圖。</span><span class="sxs-lookup"><span data-stu-id="f9a71-176">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="f9a71-177">在 [**自訂視圖**] 頁面上，視需要編輯資訊，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-177">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="f9a71-178">或者，若要刪除篩選，請在頁面底部選取 [**刪除自訂視圖**]。</span><span class="sxs-lookup"><span data-stu-id="f9a71-178">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     