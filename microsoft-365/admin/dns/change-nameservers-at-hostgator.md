---
title: 使用 Hostgator 變更名稱伺服器以設定 Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: 瞭解如何在 Hostgator 中設定 Microsoft 管理自訂網域的 DNS 記錄。
ms.openlocfilehash: 02052e98ba92c970a1e8bcc89c73df6946a6c472
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646436"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a>使用 Hostgator 變更名稱伺服器以設定 Microsoft 365

 若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。
  
如果您想讓 Microsoft 為您管理您的 DNS 記錄，請遵循下列指示。  (如果您願意，您可以 [在 Hostgator 管理所有的 MICROSOFT DNS 記錄](create-dns-records-at-hostgator.md)。 ) 
  
    
## <a name="point-your-domain-to-your-hosting-account"></a>將您的網域指向您的代管帳戶。

> [!IMPORTANT]
> 您必須先執行此程式，再執行下一節中的 **程式，新增 TXT 記錄以進行驗證**。
  
請遵循下列步驟，建立您的網域和代管帳戶的關聯。
  
1. 首先請用[這個連結](https://portal.hostgator.com/domain/manage)移至 Hostgator 上您的客戶入口網站頁面。系統會提示您先登入。
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. 選取 [ **網域** ] 索引標籤。
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. 在 [ **管理網域** ] 頁面上的 [ **我的網域** ] 區域中，選取您要更新的網域。
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. 在 [ **網域概述** ] 頁面的 [ **名稱伺服器** ] 區域中，選取 [ **變更**]。
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. 在您網域的 [ **名稱伺服器** ] 頁面上，于 [ **選取主控帳戶** ] 下拉式清單中，選擇與您的網域相關聯的 **主控帳戶** 。
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. 選取 [ **儲存名稱伺服器**]。
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證

> [!IMPORTANT]
> 在執行此程式之前，您必須先執行本文第一節中的 [程式，將您的網域指向您的託管帳戶。](#point-your-domain-to-your-hosting-account)。
  
在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。
  
1. 若要開始使用，請移至您位於 Hostgator 的 cPanel 頁面。系統會提示您先登入。
    
    (每個 Hostgator 代管的帳戶都有一個唯一的 cPanel 位址。您的 cPanel 位址看起來應該像這樣：https://YourSiteAddress:secure-port-number。您從 Hostgator 收到的註冊電子郵件會指出該位址。)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. 若要開始使用，您可以從 Hostgator 購買主控帳戶，也可以 [變更您網域的名稱伺服器 (NS) 記錄](#change-your-domains-nameserver-ns-records) ，以指向 Microsoft。 
  
2. 在 [ **控制台** ] 頁面的 [ **網域** ] 區域中，選取 [ **高級 DNS 區域編輯器**]。
    
    (您可能需要向下捲動。) 
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (從下拉式清單中選擇 [Type] (類型) 值。) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**TTL** <br/> |**類型** <br/> |**TXT Data** <br/> |
|使用您的  *domain_name*  。 (for example, fourthcoffee.com.)  <br/> **此值必須以英文句點 (.) 結尾。** <br/> |1   <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。 [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. 選取 [ **新增記錄**]。
    
5. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。
  
在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  
1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄

若要使用 Microsoft 設定您的網域，請在您的網域註冊機構變更網域的 NS 記錄，以指向 Microsoft 主要和次要名稱伺服器。 這會將 Microsoft 設定為您為您更新網域的 DNS 記錄。 我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。
  
> [!CAUTION]
> 當您將網域的 NS 記錄變更為指向 Microsoft 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。 例如，所有傳送至您網域的電子郵件 (例如 rob@ *your_domain*  .com) 會在您進行此變更之後，從 Microsoft 開始。
  
> [!IMPORTANT]
> 下列程式將告訴您如何刪除清單中的任何其他、不想要的名稱伺服器，以及如何新增正確的名稱伺服器（如果尚未列出）。 當您完成本節中的步驟之後，應該會列出的唯一名稱伺服器為下列四種：  **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**和 **ns4.bdm.microsoftonline.com**。
  
1. 首先請用[這個連結](https://portal.hostgator.com/domain/manage)移至 Hostgator 上您的客戶入口網站頁面。系統會提示您先登入。
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. 選取 [ **網域** ] 索引標籤。 
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. 在 [ **管理網域** ] 頁面上的 [ **我的網域** ] 區域中，選取您要更新的網域。 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. 在 [ **網域一覽** ] 頁面的 [ **名稱伺服器** ] 區域中，選取 [ **變更**]。
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. 在您網域的 [ **名稱伺服器** ] 頁面上，于 [ **選取主控帳戶** ] 下拉式清單中，選擇與您的網域相關聯的 **主控帳戶** 。 
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. 選取 [ **手動設定我的名稱伺服器**]。
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   **警告**：只有當現有的名稱伺服器不是四個正確的名稱伺服器時，才遵循這些步驟。  (也就是說，只刪除所有  *未*  命名為 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或 **ns4.bdm.microsoftonline.com**的目前名稱伺服器。 ) 
  
        在您網域的 [名稱伺服器] 頁面上，在名稱伺服器清單中，選取清單中的每個名稱伺服器，然後按鍵盤上的**delete**鍵，以刪除清單中的每個**名稱伺服器**。 
    
   ![Hostgator-BP-Redelegate-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. 同樣在名稱伺服器清單中，輸入或複製並貼上下表中的前兩個值。
    
|||
|:-----|:-----|
|**Name Server 1: (名稱伺服器 1:)** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**名稱伺服器2：** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**名稱伺服器3：** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**名稱伺服器4：** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Hostgator-BP-重新委派-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. 新增其他名稱伺服器的值。
    
    選取 [ ** (+) ** 新增]，然後在記錄的方塊中輸入或複製並貼上表格中下一列的值。 
    
    重複這個程序，直到四筆名稱伺服器記錄全部建立完畢。
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. 選取 [ **儲存名稱伺服器**]。
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> 您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。 然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。
