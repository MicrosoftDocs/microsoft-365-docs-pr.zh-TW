---
title: '設定 Microsoft Viva 的教學內容來源 Learning Microsoft 365 系統管理中心中 (預覽) '
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 瞭解如何設定 Microsoft Viva 的教學內容來源 Learning Microsoft 365 系統管理中心中 (預覽) 。
ms.openlocfilehash: ac9ec6196f758d3ed02d3a102fef80b8a7adeeaa
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288920"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a>設定 Microsoft Viva 的教學內容來源 Learning Microsoft 365 系統管理中心中 (預覽) 

> [!NOTE]
> 本文中的資訊與在正式發行之前可能會充分修改的預覽產品有關。 

Microsoft 365 系統管理中心的系統管理員（自行或指派知識系統管理員角色給組織中所選的個人）可以管理與 Viva Learning (預覽) 相關的設定，並且可以設定學習內容來源。

管理員會選取哪些其他學習內容來源 (例如，SharePoint 或支援的協力廠商內容提供者來源) 可供 Viva Learning (預覽) 的使用者使用。 然後，系統管理員會設定這些來源，以確定內容可用於搜尋及探索，而且可以透過使用 Viva Learning (Preview) 的員工流覽。

> [!NOTE]
>  使用者在瀏覽器或內嵌檢視器中登入非 Microsoft 和 LinkedIn Learning Pro learnings。 這項設定的學習會受限於組織和協力廠商之間的個別授權、隱私權和服務條款，而不是 Viva Learning (Preview) 條款。 在選取這種教學類型之前，請確認您的組織和使用者已具備適當的合約。

## <a name="assign-the-knowledge-admin-role-optional"></a>指派知識系統管理員角色 (選用) 

您必須是 Microsoft 365 全域系統管理員，才可執行這些工作。

> [!TIP]
> 知識系統管理員應為適度的技術，且具有現有的 SharePoint 系統管理員認證，最好是 versed 在教育、教學、訓練或員工經驗中的部分組織中。

### <a name="add-a-knowledge-admin"></a>新增知識管理

若要新增 Viva Learning (預覽) 的知識系統管理員，請遵循下列步驟：

1. 在 Microsoft 365 系統管理中心的左側導覽中，移至 [**角色**]。

2. 在 [ **角色** ] 頁面上，選取 [ **Azure AD** ] 索引標籤上的 [ **知識管理員**]。
 
3. 在 [ **知識管理員** ] 面板上，選取 [指派的系統 **管理員**]，然後選取 [ **新增**]。

     ![角色] 頁面中顯示 [知識管理員] 面板以加入使用者的 Microsoft 365 系統管理中心。](../media/learning/learning-add-knowledge-admin-1.png)

3. 在 [ **新增管理員** ] 面板上，選取您為該角色選擇的人員，然後選取 [ **新增**]。

     ![角色] 頁面中顯示 [新增管理員] 面板以新增使用者的 Microsoft 365 系統管理中心。](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a>移除知識管理

若要移除 Viva Learning (Preview) 的知識系統管理員，請遵循下列步驟：

1. 在 Microsoft 365 系統管理中心的左側導覽中，移至 [**角色**]。

2. 在 [ **角色** ] 頁面上的 [ **Azure AD** ] 索引標籤上，然後選取 [ **知識管理員**]。
 
3. 在 [ **知識管理員** ] 面板的 [ **指派** 的系統管理員] 索引標籤上，選取 [ **移除**]，然後選取您要從角色中移除的人員。 若要確認，請選取 [ **移除**]。

     ![角色] 頁面上的 Microsoft 365 系統管理中心顯示指派的系統管理員面板，以移除使用者。](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a>設定學習內容來源的設定

您必須是 Microsoft 365 全域管理員或知識系統管理員，才可執行這些工作。

若要在 Viva Learning 中設定教學內容來源的設定，請遵循下列步驟：

1. 在 Microsoft 365 系統管理中心的左側導覽中，移至 **設定**  >  **組織設定**」。

2. 在 [**組織設定**] 頁面上的 [**服務**] 索引標籤上，選取 [ **Viva Learning (預覽)**]。

     ![Microsoft 365 系統管理中心中的設定頁面，顯示所列 Learning 應用程式。](../media/learning/learning-sharepoint-configure1.png)

3. 在 [ **Viva Learning (預覽)** ] 面板上，選取您要為組織設定的學習內容來源，然後選取 [**儲存**]。

     ![Microsoft 365 系統管理中心顯示內容來源選項的 Learning 面板。](../media/learning/learning-sharepoint-configure2.png)

所有已存在的學習來源中，有些會預設為啟用。 這些學習來源包括：

- LinkedIn Learning (可用內容) 
- Microsoft 學習
- Microsoft 365培訓

> [!NOTE]
> LinkedIn LinkedIn 隱私權原則和使用者合約中提供給使用者的免費內容。 LinkedIn 會接收使用者的 IP 位址，任何先前由 LinkedIn 設定的 cookie，並會設定新的 cookie，以追蹤可用內容的使用。 使用者不需要使用 LinkedIn 來登入以取得免費內容。<br><br>
針對 LinkedIn 的精品內容，您的組織必須訂閱小組才能存取該內容。 使用者必須登入 LinkedIn 以存取該教學，這會在組織的條款和使用者條款中以 LinkedIn 提供。<br><br> 若為非 Microsoft 內容 (除了免費 LinkedIn 內容) 以外，請確定您的組織有訂閱，可讓您的使用者在將該內容連接至 Viva 之前，先使用工作帳戶來存取該內容 Learning (預覽) 。 使用者的非 Microsoft 教學提供者個人訂閱將不會與 Viva Learning (Preview) 整合。 使用者在瀏覽器或內嵌檢視器中登入非 Microsoft 和 LinkedIn Learning Pro learnings。 如果使用者流覽到其不具備組織訂閱的內容，他們可能會看到可用於註冊個別訂閱的提供者頁面。 所有非 Microsoft 的學習都是以非 Microsoft 提供者的條款為 Viva，而不是在 Learning 的一部分中提供。 

若要啟用或停用教學內容來源，請選取來源旁邊的核取方塊。 如果已啟用來源，就會顯示核取記號。

## <a name="third-party-content-providers"></a>協力廠商內容提供者 

一組可用的已連線的教學提供者可能會隨時變更。 當程式成長時，其他提供者會加入。 可用的提供者也可以選擇停止與 Viva Learning (Preview) 的連線。

### <a name="skillsoft-as-a-content-source"></a>Skillsoft 做為內容來源  

若為 Viva Learning (Preview) ，啟用 Skillsoft 的使用者，並選擇查看 Skillsoft 內容將會在 Percipio 頁面上，讓他們輸入您組織的 Percipio 網站名稱。 使用者輸入您組織的網站名稱後，系統會將其導向至頁面登入您組織的 Percipio 網站。 使用者將使用其現有的認證登入，並查看其最初選取的內容。 使用者只會要求使用者輸入 Percipio 網站名稱一次，直到清除其瀏覽器快取。 若要為您的使用者簡化這項體驗，建議您在 Percipio 的內部通訊中包含您的網站名稱，以供您傳送 (預覽) Learning。

這是一種暫時的預覽體驗，而且我們正在與 Skillsoft 搭配使用，以針對一般可用性啟用租使用者特有的整合，這會略過需要使用者提供組織之 Percipio 網站名稱的步驟。 

### <a name="details-on-microsoft-substrate"></a>Microsoft 基底的詳細資料  

若要複製到 Viva 的資料 Learning (Preview) 從非 Microsoft service (學習提供者或學習管理系統) ，您無法直接解壓縮、更正或刪除 Viva 中的資料 Learning (預覽) 。 我們會立即重新整理從非 Microsoft 提供者匯入的資料，以反映非 Microsoft 來源資料中的變更和刪除。

您需要與非 Microsoft 服務的供應商合作，以存取、更正、刪除或解壓縮非 Microsoft 服務之授權、服務或隱私權方面的資料。 所做的變更會反映在 Viva Learning 中所處理的資料，以供您在非 Microsoft service 和 Viva Learning 的資料更新週期完成時 (預覽)  (預覽) 。 如果您關閉 Viva Learning (預覽) 和非 Microsoft 服務之間的連線，則先前從該服務匯入的所有資料都會被刪除。 

## <a name="next-step"></a>下一步

[將 SharePoint 設定為 Microsoft Viva 的教學內容來源 Learning (預覽) ](configure-sharepoint-content-source.md)