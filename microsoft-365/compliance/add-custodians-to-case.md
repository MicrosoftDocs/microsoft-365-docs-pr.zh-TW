---
title: 新增 custodians 至進階電子文件探索案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f77a2967c6b789d28a95516594b1bdd5d8b9f3c6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080212"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>新增 custodians 至進階電子文件探索案例

使用進階電子文件中的內建 custodian 管理工具，來調整您繞管理 custodians 和識別相關、 custodial 資料來源與案例相關聯的工作流程。 當您新增 custodian 時，系統會自動識別並保留其 Exchange 信箱和 OneDrive 商務帳戶。 在您調查探索過程中，您可能也會識別其他資料來源 （例如信箱、 網站或小組） custodian 存取或參與。 在此情況下，您可以使用 custodian 管理工具來建立關聯的資料來源將特定 custodian。 Custodians 及新增至案例，並將其他資料來源關聯它們之後，您可以快速地保留資料並搜尋 custodial 資料。

若要新增及管理 custodians 進階的 eDiscovery 案例中使用下列工作流程。 

![Custodian 管理] 索引標籤](../media/CustodianMgtPage.png)

## <a name="before-you-begin"></a>開始之前

若要新增 custodians 案例，您必須是 「 eDiscovery 管理員角色群組的成員。 這將會提供將 custodians 新增至案例及保留 custodial 資料來源上的必要權限。


## <a name="step-1-add-potential-custodians"></a>步驟 1： 新增潛在 custodians

第一個步驟是以找出並將 custodians 新增至案例。

1. 在**進階電子文件探索**首頁上，按一下您想要新增至 custodians 的案例。 
 
2. 按一下 [ **Custodians** ] 索引標籤，然後按一下 [ **+ 新增 custodians**。

3. 尋找要新增至案例 custodians。 輸入人名顯示從貴組織的 Azure Active Directory 使用者的第一個部分。 當您找到正確的人員時，請按一下 [他們將它們新增至清單的名稱。

   ![識別潛在 Custodians](../media/AddCustodianStep1.png)
 
4. 新增所有相關的 custodians 之後，按一下 [**下一步**選取 custodians 的主要資料來源。
  
## <a name="step-2-select-custodian-data-sources"></a>步驟 2： 選取 [custodian 資料來源

新增 custodians 之後, custodian 工具可協助您識別每個 custodian 所擁有的主要資料來源。 這些資料位置為 custodian 的 Exchange 信箱和 OneDrive 帳戶。 

若要找出 custodian 資料來源： 

1. 若要選取的 Exchange 信箱的所有 custodians，選取頂端的資料行的 [ **Exchange** ] 核取方塊。 您可以再清除任何特定 custodian 若要移除的信箱為 custodial 位置核取方塊。 或者，您可以保留在未選取的資料行的最頂端的 [ **Exchange** ] 核取方塊，然後再選取個別 custodians] 核取方塊。 
 
   ![選取 [Custodial 資料來源](../media/AddCustodianStep2.png)
 
2. 重複相同的 custodians 的 OneDrive 帳戶。 

    選取 custodian 資料來源之後，系統會自動嘗試找出並確認這些資料來源而言，且然後將它們新增至這種情況，作為 custodians 相關聯的資料來源。
 
4. 按 [**下一**開始建立額外的資料來源]，以在這種情況 custodians 的關聯。

## <a name="step-3-associate-additional-data-sources-to-a-custodian"></a>步驟 3： 建立額外的資料來源]，以 custodian 的關聯

根據您正在調查的情況下，您也可以搜尋 （和保留內容中） 時，需要特定 custodian 可能具有存取信箱，Office 365 群組 custodian 目前的成員或 custodian 也已經存取的網站。 讓您在上一個步驟中指定的主要 custodian 資料來源，除了可以也其他 Office 365 的資料來源關聯的情況下 custodian。 

若要將信箱、 網站或小組對應至特定 custodian:

1. 在 [**選取其他資料來源**] 頁面上，按一下 [**新增**資料列中的特定 custodian。 
  
   ![將其他資料來源對應](../media/AddCustodianStep3.PNG)

2. 在彈出式頁面上，您可以指定資料來源是從任何下列的 Office 365 服務：
  
   -  **Exchange 電子郵件**-按一下 [**選擇使用者、 群組或小組**，然後再按一下 [**選擇使用者、 群組或小組**。 使用 [搜尋] 方塊來尋找要與 custodian 產生關聯的信箱。 若要指定要指派給所選 custodian 的信箱，請使用 [搜尋] 方塊來尋找使用者信箱和通訊群組。 您也可以指派 Office 365 群組或 Microsoft 小組相關聯的信箱。 選取使用者、 群組、 小組] 核取方塊，按一下 [**選擇**，然後按一下 [**完成**。

        > [!NOTE]
        > 當您按一下 [選擇使用者、 群組或小組來指定信箱時，會顯示信箱選擇器是空的。 這項設計的目的是提升效能。 若要將信箱新增至這份清單，輸入名稱或別名 （3 個字元的最少） 在 [搜尋] 方塊中。
     
     - **SharePoint 網站**-按一下 [**選擇網站**]，然後按一下 [**選擇網站**]，以顯示您組織中的 SharePoint 網站清單。 若要關聯 custodian 網站，您可以選取清單中的網站，或您可以輸入不同的站台或與 Office 365 群組、 Microsoft Team 或 OneDrive 帳戶相關聯的網站的 URL。
     
     - **Teams** – 按一下 [**選擇小組**，然後按一下 [**選擇小組**]，以顯示 custodian 屬於目前的 Microsoft Teams 的清單。 選取您想要新增至您 custodian Teams。 一旦選取，系統會自動識別相關聯的 SharePoint 網站和群組信箱相關聯的 Microsoft Team & 選取。 按一下 [**選擇**，然後按一下 [**完成**。

       ![對應的資料來源](../media/AddCustodianStep4.PNG)
        
      > [!NOTE]
      > 若要建立與 custodian 關聯的其他小組，您必須分別新增信箱及使用**Exchange 郵件**與**SharePoint 網站**位置相關聯的小組網站。

您已完成 custodians 與建立關聯的其他資料來源之後，您可以檢視信箱、 網站或小組上**選取 [其他資料來源] 頁面上**的每個 custodian 相關聯的總數。 當您已完成的相關資料來源的特定 custodian 時，將會維護此關聯，而且期間收集、 處理及檢閱階段的 eDiscovery 工作流程中使用。

## <a name="step-4-place-custodians-on-hold"></a>步驟 4： 就地 custodians 上保留

您已完成 custodians 及資料來源，以新增至案例之後，您可以選擇性地放置一些或 custodians 上的所有保留。 當您保留上放置 custodian 時，custodian 相關聯的所有內容位置中的所有內容會都保留直到移除保留或釋放保留中的 custodian。 在某些情況下，您可能想要將 custodians 新增至案例中，而不將其置於保留狀態。

要放置 custodians 與資料來源上的保留：

1. 在 [**暫止上選取 custodians** ] 頁面上，選取要就地保留所有 custodians 欄頂端的 [**保留**] 核取方塊。 您可以再清除從保留移除任何特定 custodian 核取方塊。 或者，您可以保留在未選取的資料行的最頂端的 [**保留**] 核取方塊，然後再選取個別 custodians] 核取方塊。 
 
   ![就地保留](../media/AddCustodianStep5.PNG)

2. 驗證 custodian 保留選取項目，然後按一下 [**完成**]。

如果您未保留 custodian、 custodian 和其相關聯的資料來源會加入至的案例，但這些資料來源中的內容將不會置於保留。

Custodian 處於保留狀態之後，就會自動建立包含所有 custodial 來源 custodian 保留原則。 若要檢視此原則：

1. 在**首頁**上的情況下，按一下 [**保留**] 索引標籤，然後按一下 [ **CustodianHold Guid**  

2. 在彈出式頁面上，按一下 [**編輯保留**檢視會處於保留狀態的所有 custodian 資料來源。

