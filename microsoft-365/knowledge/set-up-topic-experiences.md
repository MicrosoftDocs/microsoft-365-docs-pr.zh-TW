---
title: '設定知識管理 (預覽)  '
description: 如何設定知識管理。
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: c7c30c0f8c1ec4cf8836547e2a23e1e2e6f4f783
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988945"
---
# <a name="set-up-knowledge-management-preview"></a>設定知識管理 (預覽) 

> [!Note] 
> 本文內容適用于 Project Cortex 私人預覽。 [如需詳細資訊，請參閱 Project Cortex](https://aka.ms/projectcortex)。

您可以使用 Microsoft 365 系統管理中心來設定及設定 [知識管理](knowledge-management-overview.md)。 

> [!Important]
> 在您的環境中規劃安裝和設定知識管理的最佳方式是很重要的。 例如，您將需要考慮下列事項：
- 您要分析主題的 SharePoint 網站。
- 您要讓主題看得見哪些使用者。
- 您要授與主題中心主題的許可權的使用者。
- 您想要在主題中心提供許可權以建立或編輯主題的使用者。
- 您想要為主題中心提供什麼名稱。

> [!Note]
> 您可能會發現建立安全性群組以將查看主題、管理主題及建立及編輯主題所需的許可權指派給使用者十分有用。

系統管理員也可以在安裝程式之後，透過 Microsoft 365 系統管理中心的知識管理設定 [變更所選取的設定](topic-experiences-discovery.md) 。

## <a name="requirements"></a>需求 
您必須具有全域管理員或 SharePoint 系統管理員許可權，才能存取 Microsoft 365 系統管理中心及設定組織知識工作。

## <a name="set-up-your-knowledge-network"></a>設定您的知識網路

設定您的知識網路可引導您完成下列作業：

- 主題探索：選取要從探索中排除的主題來源和主題。
- 主題可見度：選取可在 [搜尋] 和 [主題] 頁面中查看主題做為醒目提示的人員。
- 主題許可權：選擇誰可以建立、編輯及管理主題。
- 主題中心：建立主題中心。
- 檢查：檢查並套用您的設定。

若要設定您的知識網路：

1. 在 Microsoft 365 系統管理中心 (admin.microsoft.com) 中，選取 [ **設定** ]，然後查看 [ **組織知識** ] 區段。
2. 在 [ **組織知識** ] 區段中，按一下 **[將人員連線到知識]** 。<br/>

    ![將人員連線至知識](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. 在 [連線 **人員至知識]** 頁面上，按一下 [ **開始** ]，逐步引導您完成安裝程式。<br/>

    ![開始使用](../media/content-understanding/k-get-started.png) </br>

4. 在 [ **選擇知識網路可如何尋找主題** ] 頁面上，您會設定主題探索。 在 [ **選取 SharePoint 主題來源** ] 區段中，選取要在探索過程中將其編目為主題來源的 SharePoint 網站。 這包括：</br>
    a. **所有網站** ：您租使用者中的所有 SharePoint 網站。 這會捕獲目前和未來的網站。</br>
    b. **全部，除了選取的網站以外** ：請輸入您要排除的網站名稱。  您也可以上傳想要從探索中選擇的網站清單。 在未來建立的網站將會包含為主題探索的來源。 </br>
    c. **僅限選取的網站** ：輸入您要包含的網站名稱。 您也可以上傳網站清單。 未來建立的網站不會包含為主題探索的來源。 </br>

    ![選擇尋找主題的方式](../media/content-understanding/ksetup1.png) </br>
   
5. 在 [以 **名稱排除主題** ] 區段中，您可以選擇包含您不想在已探索結果中的主題名稱。 使用此設定可防止敏感主題加入為知識網路的一部分。 您的選項包括：</br>
    a. **不排除任何主題** </br>
    b. **依名稱排除主題** ：如果您有不想要在知識網路中顯示的主題。</br>

    ![排除主題](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a>操作方法：依名稱排除主題    

    如果您需要排除相關主題，請在選取 [ **依名稱排除主題** ] 之後，選取 [ **下載 .csv 範本** ]。 使用 Excel。CSV 範本，以包含您要從探索結果中排除的主題清單。

    ![排除 CSV 範本中的主題](../media/content-understanding/csv1.png) </br>

    在 CSV 範本中，輸入您要排除之主題的下列相關資訊：

    - **名稱** ：輸入您要排除的主題名稱。 方法有兩種：</br>
        - 完全相符：您可以包含確切的名稱或縮寫 (例如， *Contoso* 或 *ATL* ) 。</br>
        - 部分相符：您可以排除包含特定單字的所有主題。  例如， *弧線* 會排除具有文字 *弧線* 的所有主題，例如 *弧線圓形* 、 *等離子弧線焊接* 或 *訓練弧* 。請注意，它不會排除包含文字（如 *架構* ）一部分的主題。</br>
    - **擴充 (選用)** ：若要排除縮寫，請輸入縮寫所代表的字。</br>
    - **MatchType-Exact/partial** ：輸入您輸入的名稱是 *完全* 或 *部分* 相符類型。</br>

    完成並儲存 CSV 範本檔之後，請選取 **[流覽]** 以找出並選取。
    
    選取 **[下一步]** 。</br>

6. 在 [ **誰可以看到主題及其可以查看的位置** ] 頁面上，您會設定主題可見度。 在 [在 **知識網路中查看主題** ] 設定中，您可以選擇誰可以存取主題詳細資料，例如高亮主題、主題卡片、搜尋中的主題答案及主題頁面。 您可以選取：</br>
    a. **組織中的所有人**</br>
    b. **僅限選取的人員或安全性群組**</br>
    c. **沒人**</br>

    ![誰可以查看主題](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > 雖然此設定可讓您選取組織中的任何使用者，但只有具有指派的知識管理授權的使用者才能查看主題。 

7. 在 [ **主題管理的許可權** ] 頁面中，您可以選擇誰將可以建立、編輯或管理主題。 在 [ **可以建立及編輯主題的人員** ] 區段中，您可以選取：</br>
    a. **組織中的所有人**</br>
    b. **僅限選取的人員或安全性群組**</br>
8. 您可以在 [ **誰可以管理主題** ] 區段中，選取：</br>
    a. **組織中的所有人**</br>
    b. **選取的人員或安全性群組**</br>

    ![主題管理的許可權](../media/content-understanding/ksetup3.png) </br>

    選取 **[下一步]** 。</br>
9. 在 [ **建立主題中心** ] 頁面上，您可以建立可以查看主題頁面和管理主題的主題中心網站。  在 [ **主題中心名稱** ] 方塊中，輸入主題中心的名稱。 您可以選擇性地在 [ **網站描述** ] 方塊中輸入簡短的描述。 </br>

選取 **[下一步]** 。</br>

   ![建立知識中心](../media/content-understanding/ksetup4.png) </br> 

10. 在 **[檢閱並完成]** 頁面上，您可以查看您選取的設定，並選擇進行變更。 如果您對您的選擇感到滿意，請選取 **[啟用]** 。

    ![完成和審閱](../media/content-understanding/ksetup5.png) </br> 

11. 隨即會顯示 **知識網路啟用** 頁面，確認系統會立即開始分析您所選取的網站，以取得主題及建立「知識中心」網站。 選取 **[完成]** 。</br>

    ![啟動](../media/content-understanding/ksetup6.png) </br> 

12. 您將會傳回 [連線 **人員到知識]** 頁面。 在此頁面上，您可以選取 **[管理]** ，以對設定進行任何變更。 

    ![套用的設定](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> 安裝程式完成後，系統管理員可以隨時 [變更選取的知識管理設定](topic-experiences-discovery.md) ，方法是回到此頁面。


## <a name="see-also"></a>請參閱



  






