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
ms.openlocfilehash: 4bd4ea351612c2ae5175cd27fa7a689d671a8b62
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755569"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>建立、編輯或刪除自訂使用者檢視

如果您是 Microsoft 365 for business 訂閱的全域或使用者管理管理員，您可以建立自訂使用者視圖，以查看特定的使用者子集。 這些視圖是除了標準的一組視圖之外。 您可以建立、編輯或刪除自訂使用者視圖，而且您建立的自訂視圖可供所有系統管理員使用。
  
## <a name="custom-user-views-in-the-admin-center"></a>Admin center 中的自訂使用者視圖

當您建立、編輯或刪除自訂使用者視圖時，所做的變更會顯示在您公司的所有系統管理員都看到 [**使用者**] 頁面上的 [**篩選**] 清單中。 您最多可以建立50個自訂視圖。 

> [!TIP]
>  標準使用者視圖預設會顯示在 [ **篩選** ] 下拉式清單中。 標準篩選包括 **所有使用者**、 **授權的使用者**、 **來賓使用者**、  **允許登入**、登 **入封鎖**、未授權的 **使用者**、 **有錯誤的使用者**、 **計費管理員**、 **全域系統管理員**、 **服務台管理員**、 **服務管理員** 和 **使用者管理系統管理員**。 您無法編輯或刪除標準視圖。 

有關標準視圖的注意事項幾點： 

- 如果清單中的使用者超過2000，部分標準視圖會顯示未排序的清單。 若要在清單中尋找特定的使用者，請使用搜尋方塊。 
- 如果您未從 Microsoft 購買 Microsoft 365， **計費系統管理員** 不會出現在 [標準視圖] 清單中。 For more information, see [Assigning admin roles](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>選擇自訂使用者視圖的篩選

您可以在 **自訂篩選** 窗格中建立及編輯自訂視圖。 如果您選取多個篩選選項，會取得包含符合所有選取準則之使用者的結果。 下列範例會示範如何建立名為 "加拿大 users" 的自訂視圖，以顯示位於加拿大的特定網域上的所有使用者。 

  
 **A 網域** 如果您的組織有多個網域，您可以從可用的網域下拉式清單中選擇。 
  
 **B 登錄狀態** 選擇允許或封鎖的使用者。 
  
 **C-位置** 從國家/地區的下拉式清單中選擇位置。 
  
 **D 指派產品授權** 從您的組織中可用的授權下拉式清單中選擇。 使用此篩選器顯示已指派授權的使用者。 使用者也可以有其他授權。 
  
您也可以在組織中使用的其他使用者設定檔詳細資料進行篩選，例如部門、城市、省或直轄市、國家或地區或職稱。
  
 **其他條件：**
  
- **僅限同步** 處理的使用者選取此方塊以顯示已與本機 Active Directory 同步的所有使用者，不論使用者是否已啟用。 
    
- **發生錯誤的使用者** 選取此方塊以顯示可能有布建錯誤的使用者。 
    
- **未經許可的使用者** 選取此方塊，以尋找未獲指派授權的所有使用者。 此視圖的結果也可以包含具有 Exchange 信箱，但沒有授權的使用者。 若要特別追蹤這些使用者，請使用篩選 **未經授權的使用者與 Exchange 信箱或檔案**。 此視圖的結果也可以包含有 Exchange 封存，但沒有授權的使用者。
    
- **具有 Exchange 信箱或封存的未授權使用者** 選取此方塊以顯示 Exchange Online 中所建立的使用者帳戶，並有 Exchange 信箱，但未獲指派 Microsoft 365 授權。 此篩選的結果包括已被指派 Exchange 封存的使用者。 

> [!NOTE]
> **具有 Exchange 信箱的未經許可使用者** 可在下列情況中運作：
1. 信箱最近從 **共用** 轉換為 **使用者** ，而且沒有授權。
2. 信箱最近已遷移至 Microsoft 365，但是尚未指派授權。
3. 信箱已使用 PowerShell 建立，尚未指派授權。
4. 會為使用者布建已使用 New-RemoteMailbox Cmdlet 建立內部部署的新信箱。
    
> [!TIP]
> 如果您建立的自訂視圖傳回超過2000的使用者，則不會排序所產生的使用者清單。 在此情況下，請使用搜尋方塊尋找使用者或編輯您的自訂視圖，以精煉搜尋。 
  
## <a name="create-a-custom-user-view"></a>建立自訂使用者視圖

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 [ **使用者**] [作用中 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">使用者</a>]。
    
2. 在 [作用中 **使用者** ] 頁面上，選取 [ **篩選** ]，然後選取 [ **新增篩選**]。
  
3. 在 [ **自訂篩選** ] 頁面上，輸入篩選器的名稱，選擇您自訂篩選的條件，然後選取 [ **新增**]。 您的自訂視圖現在會包含在篩選器的下拉式清單中。
    
::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 [ **使用者**] [作用中 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">使用者</a>]。  

2. 在 [作用中 **使用者** ] 頁面上選取 [ **視圖** ]，然後選取 [ **新增自訂視圖**]。
  
3. 在 [ **自訂視圖** ] 頁面上，輸入篩選器的名稱，選擇您自訂篩選的條件，然後選取 [ **新增**]。 您的自訂視圖現在會包含在篩選器的下拉式清單中。

::: moniker-end


::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 [ **使用者**] [作用中 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">使用者</a>]。 

2. 在 [作用中 **使用者** ] 頁面上選取 [ **視圖** ]，然後選取 [ **新增自訂視圖**]。
  
3. 在 [ **自訂視圖** ] 頁面上，輸入篩選器的名稱，選擇您自訂篩選的條件，然後選取 [ **新增**]。 您的自訂視圖現在會包含在篩選器的下拉式清單中。

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>編輯或刪除自訂使用者視圖

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 [ **使用者**] [作用中 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">使用者</a>]。
    
2. 在 [作用中 **使用者** ] 頁面上，選取 [ **篩選**]，選取您要變更的篩選，然後選取 [ **編輯篩選**]。 
    
    > [!TIP]
    > 您只能編輯自訂的視圖。 
  
3. 在 [ **自訂篩選** ] 頁面上，視需要編輯資訊，然後選取 [ **儲存**]。 或者，若要刪除篩選，請在頁面底部選取 [ **刪除**]。 
    
::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 [ **使用者**] [作用中 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">使用者</a>]。  

2. 在 [作用中 **使用者** ] 頁面上，選取 [ **視圖**]，選取您要變更的篩選，然後選取 [ **編輯此視圖**]。 
    
    > [!TIP]
    > 您只能編輯自訂的視圖。 
  
3. 在 [ **自訂視圖** ] 頁面上，視需要編輯資訊，然後選取 [ **儲存**]。 或者，若要刪除篩選，請在頁面底部選取 [ **刪除自訂視圖**]。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 [ **使用者**] [作用中 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">使用者</a>]。 

2. 在 [作用中 **使用者** ] 頁面上，選取 [ **視圖**]，選取您要變更的篩選，然後選取 [ **編輯此視圖**]。 
    
    > [!TIP]
    > 您只能編輯自訂的視圖。 
  
3. 在 [ **自訂視圖** ] 頁面上，視需要編輯資訊，然後選取 [ **儲存**]。 或者，若要刪除篩選，請在頁面底部選取 [ **刪除自訂視圖**]。 

::: moniker-end


     