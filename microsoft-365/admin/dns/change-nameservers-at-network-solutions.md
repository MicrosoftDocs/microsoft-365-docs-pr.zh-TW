---
title: 使用網路解決方案變更名稱伺服器以設定 Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: '若要讓 Microsoft 管理您的 DNS 記錄，請瞭解如何設定含網路方案的 Microsoft 自訂網域。 '
ms.openlocfilehash: 2b3b575943ebd95ffcbd34dd4578133fa7dd4f79
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629752"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a>使用網路解決方案變更名稱伺服器以設定 Microsoft

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。
  
如果您想讓 Microsoft 為您管理您的 DNS 記錄，請遵循下列指示。 （如果您願意，您可以[在 [網路方案] 中管理所有的 MICROSOFT DNS 記錄](create-dns-records-at-network-solutions.md)。）
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a>在 Network Solutions 新增 TXT 記錄以驗證您擁有該網域

在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。 您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
請依照下列步驟操作或[觀看影片 (從 0:47 處開始)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。系統會提示您先登入。
    
    > [!IMPORTANT]
    > 在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 選取您要修改之網域名稱旁的核取方塊。
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. 選取 [**編輯 DNS**]。
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. 選取 [**管理 ADVANCED DNS 記錄**]。
    
    (You may have to scroll down.)
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. 向下滾動至 [**文字（TXT 記錄）** ] 區段，然後選取 [**編輯 TXT 記錄**]。
    
    ![選取 [編輯 TXT 記錄]](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. In the boxes for the new record, type or copy and paste the values in the following table.
    
|**Host**|**TTL**|**Text**|
|:-----|:-----|:-----|
|@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **請注意**：這是一個範例。 從 Microsoft 365 的表格中，使用您的特定**目的地或指向位址**值。           [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![在新記錄的方塊中輸入或貼上值](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. 選取 [**繼續**]。
    
    ![選取 [繼續]](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. 選取 [**儲存變更**]。
    
    ![選取 [儲存變更]](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 365，並要求 Microsoft 365 尋找該記錄。
  
當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。
  
1. 在 Microsoft 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
    
  
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
    
  
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
    
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄

若要使用 Microsoft 設定您的網域，請在您的網域註冊機構變更網域的 NS 記錄，以指向 Microsoft 主要和次要名稱伺服器。 這會將 Microsoft 設定為您為您更新網域的 DNS 記錄。 我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。
  
> [!CAUTION]
> 當您將網域的 NS 記錄變更為指向 Microsoft 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。 例如，在您進行此變更之後，所有傳送至您網域的電子郵件（如 rob@ *your_domain* .com）都會開始向 Microsoft。
  
準備好變更您的 NS 記錄，讓 Microsoft 能夠設定您的網域？ 請依照下列步驟操作或[觀看影片 (從 2:23 處開始)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
> [!IMPORTANT]
>  當您完成本節中的步驟之後，應該會列出的*唯一*名稱伺服器為下列四種： **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**和**ns4.bdm.microsoftonline.com**。 The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. 首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。 系統會提示您先登入。
    
    > [!IMPORTANT]
    > 在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 選取您要修改之網域名稱旁的核取方塊。
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. 選取 [**編輯 DNS**]。
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. 選取 [**移動 DNS**]。
    
    ![NetworkSolutionsBP-重新委派-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. 請根據現在顯示頁面上是否列出名稱伺服器，來選擇下列兩個程序其中一項繼續︰
    
  - 如果沒有列出**任何**名稱伺服器，[則未列出任何名稱伺服器](#if-there-are-no-nameservers-already-listed)。
    
  - 如果已**列出名稱伺服器，** 如果已[列出名稱伺服器](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>如果列表上「沒有」名稱伺服器

1. 在 [**網域**] 頁面上，選取 [**指定功能變數名稱伺服器**] 區段中的 [**新增更多名稱伺服器**]。
    
    ![NetworkSolutionsBP-重新委派-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. 在 [**功能變數名稱**] 頁面上，輸入或複製並貼上下表中名稱伺服器的值。 
    
|||
|:-----|:-----|
|**Name server 1 (名稱伺服器 1)** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**名稱伺服器2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 2 (名稱伺服器 2)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 2 (名稱伺服器 2)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NetworkSolutionsBP-重新委派-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. 選取 [**移動 DNS**]。
    
    ![NetworkSolutionsBP-重新委派-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. 選取 [**儲存變更**]。
    
    ![NetworkSolutionsBP-重新委派-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> 您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。 然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。 
  
### <a name="if-there-are-nameservers-already-listed"></a>如果列表上「有」名稱伺服器

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. （也就是說，*只*刪除所有*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的目前名稱伺服器。）
  
1. 如果有列出任何其他名稱伺服器，請選取它，然後按鍵盤上的**delete**鍵，逐一刪除。
    
    ![NetworkSolutions-BP-重新委派-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. 選取 [**新增更多名稱伺服器**]。
    
    ![NetworkSolutionsBP-重新委派-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. 在 [**功能變數名稱**] 頁面上，輸入或複製並貼上下表中名稱伺服器的值。
 
    
|||
|:-----|:-----|
|**Name server 1 (名稱伺服器 1)** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**名稱伺服器2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3 (名稱伺服器 3)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4 (名稱伺服器 4)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NetworkSolutionsBP-重新委派-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. 選取 [**移動 DNS**]。
    
    ![NetworkSolutionsBP-重新委派-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. 選取 [**儲存變更]。**
    
    ![NetworkSolutionsBP-重新委派-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> 您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。 然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。
