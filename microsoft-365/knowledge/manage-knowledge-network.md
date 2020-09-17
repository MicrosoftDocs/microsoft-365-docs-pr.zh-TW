---
title: '管理您的知識管理網路 (預覽)  '
description: 如何設定知識管理。
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 3ca180dba82e677dbc0d9f112b713df14820ce61
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950769"
---
# <a name="manage-your-knowledge-management-network-preview"></a>管理您的知識管理網路 (預覽) 

> [!Note] 
> 本文內容適用于 Project Cortex 私人預覽。 [進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。


在您 [設定知識管理](set-up-knowledge-network.md)之後，任何時候，系統管理員都可以透過 Microsoft 365 系統管理中心對設定設定進行調整。

例如，您可能需要調整下列專案的設定：
- 將新的 SharePoint 來源新增至本主題。
- 變更哪些使用者將可以存取主題。
- 變更哪些使用者具有在主題中心執行工作的許可權。
- 變更主題中心的名稱


## <a name="requirements"></a>需求 
您必須具有全域管理員或 SharePoint 系統管理員許可權，才能存取 Microsoft 365 系統管理中心和管理組織知識工作。


## <a name="to-access-knowledge-management-settings"></a>若要存取知識管理設定：

1. 在 Microsoft 365 系統管理中心中，選取 [ **安裝**]，然後查看 [ **組織知識** ] 區段。
2. 在 [ **組織知識** ] 區段中，按一下 **[將人員連線到知識]**。<br/>

    ![將人員連線至知識](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. 在 [連線 **人員至知識** ] 頁面上，選取 [ **管理** ] 開啟 [ **知識網路設定** ] 窗格。<br/>

    ![知識網路-設定](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a>變更知識網路可尋找主題的方式

如果您想要為 SharePoint 主題來源更新您的選擇，請選取 [ **主題探索** ] 索引標籤。 此設定可讓您選取您租使用者中的 SharePoint 網站，將會針對主題進行編目及挖掘。

1. 在 [ **主題探索** ] 索引標籤上，選取 [ **SharePoint 主題來源**] 底下的 [ **編輯**]。
2. 在 [ **選取 SharePoint 主題來源** ] 頁面上，選取要在探索過程中將其編目為主題來源的 SharePoint 網站。 這包括：</br>
    a. **所有網站**：您租使用者中的所有 SharePoint 網站。 這會捕獲目前和未來的網站。</br>
    b. **全部，除了選取的網站以外**：請輸入您要排除的網站名稱。  您也可以從探索中上傳想要選擇從探索中移除的網站清單。 未來建立的網站會包含為主題探索的來源。 </br>
    c. **僅限選取的網站**：輸入您要包含的網站名稱。 您也可以上傳網站清單。 未來建立的網站不會包含為主題探索的來源。 </br>

    ![選擇尋找主題的方式](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    如果您有許多您想要排除 (的網站，請選取 [ **全部] （選取的網站除外）**) 或包含 (如果您 **只選取了 [選取的網站** ]) ，您可以選擇上載具有網站名稱和 URLs 的 CSV 檔案。 如果您想要使用 CSV 範本檔案，您可以選取 [ **下載網站範本 .csv** ]。

3. 選取 [儲存]****。

##  <a name="change-who-can-see-topics-in-your-organization"></a>變更可以查看組織中主題的人員

如果您想要更新組織中的哪些人員可以查看搜尋結果中已發現的主題，以及在 SharePoint 頁面等內容中突出顯示主題，請選取 [ **主題探索** ] 索引標籤。

1. 在 [ **主題探索** ] 索引標籤上，于 [ **誰可以在知識網路中查看主題**] 底下，選取 [ **編輯**]。
2. 在 [ **知識網路] 頁面中的 [可查看主題** ] 頁面上，您可以選擇誰將有權存取主題詳細資料，例如高亮主題、主題卡片、搜尋中的主題答案及主題頁面。 您可以選取：</br>
    a. **組織中的所有人**</br>
    b. **僅限選取的人員或安全性群組**</br>
    c. **沒人**</br>

    ![誰可以查看主題](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. 選取 [儲存]****。  
 
> [!Note] 
> 雖然此設定可讓您選取組織中的任何使用者，但只有具有指派的知識管理授權的使用者才能查看主題。

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a>變更誰有權在主題中心執行工作？

如果您想要更新主題中心頁面上具有下列許可權的人員，請選取 [ **主題許可權** ] 索引標籤：

- 哪些使用者可以建立及編輯主題：在探索或編輯現有主題頁面詳細資料時，建立未找到的新主題。
- 哪些使用者可以管理下列主題：確認或拒絕已探索的主題。

若要更新誰有權建立及編輯主題：

1. 在 [ **主題許可權** ] 索引標籤的 [ **誰可以建立及編輯主題**] 中，選取 [ **編輯**]。</br>
2. 您可以在 [ **誰可以建立及編輯主題** ] 頁面上，選取：</br>
    a. **組織中的所有人**</br>
    b. **僅限選取的人員或安全性群組**</br>

    ![建立及編輯主題](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. 選取 [儲存]****。</br>

若要更新誰具有管理主題的許可權：

1. 在 [ **主題許可權** ] 索引標籤的 [ **誰可以管理主題**] 下，選取 [ **編輯**]。</br>
2. 您可以在 [ **誰可以管理主題** ] 頁面上，選取：</br>
    a. **組織中的所有人**</br>
    b. **選取的人員或安全性群組**</br>

    ![管理主題](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. 選取 [儲存]****。</br>


##  <a name="update-your-topic-center-name"></a>更新主題中心名稱

如果您想要更新主題中心的名稱，請選取 [ **主題中心** ] 索引標籤。 

1. 在 [ **主題中心** ] 索引標籤的 [ **主題中心名稱**] 下，選取 [ **編輯**]。
2. 在 [ **編輯主題中心名稱** ] 頁面上，于 [ **主題中心名稱** ] 方塊中，輸入主題中心的新名稱。
3. 選取 **[儲存]**

    ![編輯主題中心名稱](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a>另請參閱



  






