---
title: 在 Microsoft 365 中設定主題體驗
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何在 Microsoft 365 中設定主題體驗
ms.openlocfilehash: d221f2932dc2ca9f562800b7b274e35e7f3d1db3
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749608"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a>在 Microsoft 365 中設定主題體驗

您可以使用 Microsoft 365 系統管理中心來設定及設定 [主題經驗](topic-experiences-overview.md)。 

在您的環境中規劃設定和設定主題的最佳方式是很重要的。 在您開始本文中的程式之前，請務必閱讀 [Plan 主題經驗](plan-topic-experiences.md) 。

您必須是全域管理員或 SharePoint 管理員，才能存取 Microsoft 365 系統管理中心及設定主題經驗。

## <a name="video-demonstration"></a>影片示範

這段影片顯示在 Microsoft 365 中設定主題體驗的程式。

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topic-experiences"></a>設定主題體驗

設定 Microsoft 365 中的主題體驗

1. 在 [Microsoft 365 系統管理中心](https://admin.microsoft.com)中，選取 [ **安裝**]，然後查看 [檔案 **與內容** ] 區段。
2. 在 [檔案 **與內容** ] 區段中，按一下 **[將人員連線到知識]**。

    ![將人員連線至知識](../media/admin-org-knowledge-options.png) 

3. 在 [連線 **人員至知識]** 頁面上，按一下 [ **開始** ]，逐步引導您完成安裝程式。

    ![入門](../media/k-get-started.png) 

4. 在 [ **選擇知識網路可如何尋找主題** ] 頁面上，您會設定主題探索。 在 [ **選取 SharePoint 主題來源** ] 區段中，選取要在探索過程中將其編目為主題來源的 SharePoint 網站。 請選擇：
    - **所有網站**：您組織中的所有 SharePoint 網站。 這包括目前和未來的網站。
    - **全部，除了選取的網站以外**：請輸入您要排除的網站名稱。  您也可以上傳想要從探索中選擇的網站清單。 在未來建立的網站將會包含為主題探索的來源。 
    - **僅限選取的網站**：輸入您要包含的網站名稱。 您也可以上傳網站清單。 未來建立的網站不會包含為主題探索的來源。
    - **無網站**：不包含任何 SharePoint 網站。

    ![選擇尋找主題的方式](../media/ksetup1.png) 
   
5. 在 [以 **名稱排除主題** ] 區段中，您可以新增要從主題探索中排除的主題名稱。 使用此設定可防止敏感資訊包含為主題。 選項包括：
    - **不排除任何主題** 
    - **依名稱排除主題**

    ![排除主題](../media/topics-excluded-by-name.png) 

     (知識管理員也可以排除探索之後主題中心的主題。 ) 

    #### <a name="how-to-exclude-topics-by-name"></a>操作方法：依名稱排除主題    

    如果您需要排除相關主題，請在選取 [ **依名稱排除主題**] 之後，選取 [下載 .csv 範本並以您想要從探索結果中排除的主題清單加以更新]。

    ![排除 CSV 範本中的主題](../media/exclude-topics-csv.png) 

    在 CSV 範本中，輸入您要排除之主題的下列相關資訊：

    - **名稱**：輸入您要排除的主題名稱。 方法有兩種：
        - 完全相符：您可以包含確切的名稱或縮寫 (例如， *Contoso* 或 *ATL*) 。
        - 部分相符：您可以排除包含特定單字的所有主題。  例如， *弧線* 會排除具有文字 *弧線* 的所有主題，例如 *弧線圓形*、 *等離子弧線焊接* 或 *訓練弧*。請注意，它不會排除包含文字（如 *架構*）一部分的主題。
    - **代表 (選用)**：若要排除縮寫，請輸入縮寫所代表的字。
    - **MatchType-Exact/partial**：輸入您輸入的名稱是 *完全* 或 *部分* 相符類型。

    完成並儲存 .csv 檔案之後，請選取 **[流覽]** 以找出並選取。
    
    選取 **[下一步]**。

6. 在 [ **誰可以看到主題及其可以查看的位置** ] 頁面上，您會設定主題可見度。 在 [在 **知識網路中查看主題** ] 設定中，您可以選擇誰可以存取主題詳細資料，例如高亮主題、主題卡片、搜尋中的主題答案及主題頁面。 您可以選取：
    - **組織中的所有人**
    - **僅限選取的人員或安全性群組**
    - **沒人**

    ![誰可以查看主題](../media/ksetup2.png)  

 > [!Note] 
 > 雖然此設定可讓您選取組織中的任何使用者，但只有具有指派授權之使用者的使用者可以查看主題。

7. 在 [ **主題管理的許可權** ] 頁面中，您可以選擇誰將可以建立、編輯或管理主題。 在 [ **可以建立及編輯主題的人員** ] 區段中，您可以選取：
    - **組織中的所有人**
    - **僅限選取的人員或安全性群組**
    - **沒人**

    ![主題管理的許可權，誰可以建立及編輯主題。](../media/ksetup3.png) 

8. 您可以在 [ **誰可以管理主題** ] 區段中，選取：
    - **組織中的所有人**
    - **僅限選取的人員或安全性群組**

    ![主題管理的許可權](../media/km-setup-create-edit-topics.png) 

    選取 **[下一步]**。

9. 在 [ **建立主題中心** ] 頁面上，您可以建立可以查看主題頁面和管理主題的主題中心網站。 在 [ **網站名稱** ] 方塊中，輸入主題中心的名稱。 您可以選擇性地在 [ **描述** ] 方塊中輸入簡短的描述。 

選取 **[下一步]**。

   ![建立知識中心](../media/ksetup4.png)  

10. 在 **[檢閱並完成]** 頁面上，您可以查看您選取的設定，並選擇進行變更。 如果您對您的選擇感到滿意，請選取 **[啟用]**。

11. 隨即會顯示 **知識網路啟用** 頁面，確認系統會立即開始分析您所選取的網站，以取得主題及建立「知識中心」網站。 選取 **[完成]**。

12. 您將會傳回 [連線 **人員到知識]** 頁面。 在此頁面上，您可以選取 **[管理]**，以對設定進行任何變更。 

    ![套用的設定](../media/ksetup7.png)    

## <a name="assign-licenses"></a>指派授權

當您設定好主題經驗後，您必須指派授權給將使用主題經驗的使用者。 只有具有授權的使用者可以查看主題的相關資訊，包括要聞、主題卡片、主題頁面和主題中心。 

若要指派授權：

1. 在 Microsoft 365 系統管理中心中，在 **[使用者]** 底下，按一下 **[作用中使用者]**。

2. 選取您要授權的使用者，然後按一下 **[管理產品授權]**。

3. 選取 **[指派更多]**。

4. 在 [ **授權**] 底下，選取 **主題經驗**。

5. 在 [**應用程式**] 底下，請確定已同時選取 [使用索引及 **主題體驗** 的 **圖形連接器搜尋]** 。

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 系統管理中心中的 SharePoint Syntex 授權](../media/topic-experiences-licenses.png)

6. 按一下 **[儲存變更]**。

## <a name="manage-topic-experiences"></a>管理主題經驗

在您設定好主題經驗後，您可以在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)變更您在安裝期間所選擇的設定。 請參閱下列參考：

- [在 Microsoft 365 中管理主題探索](topic-experiences-discovery.md)
- [在 Microsoft 365 中管理主題可見度](topic-experiences-knowledge-rules.md)
- [在 Microsoft 365 中管理主題許可權](topic-experiences-user-permissions.md)
- [變更 Microsoft 365 主題中心的名稱](topic-experiences-administration.md)

## <a name="see-also"></a>另請參閱

[主題經驗概述](topic-experiences-overview.md)
