---
title: 變更名稱伺服器以設定 Office 365 使用 Namecheap
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: '了解如何設定 Office 365 自訂網域與 Namecheap，如果您希望 Office 365 來管理您的 DNS 記錄。 '
ms.openlocfilehash: caf0a484b82ecf10f2835ae8fd5dea98c16e61c3
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239819"
---
# <a name="change-nameservers-to-set-up-office-365-with-namecheap"></a>變更名稱伺服器以設定 Office 365 使用 Namecheap

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。
  
如果您希望讓 Office 365 來管理您的 Office 365 DNS 記錄，請遵循下列指示。 （如果您想要的話，您可以[管理在 Namecheap 所有 Office 365 DNS 記錄](create-dns-records-at-namecheap.md)。）
  
    
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證

1. 若要開始，使用[這個連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)移至您在 Namecheap 的網域頁面。 系統會提示您登入，並繼續。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. 在**登陸**頁面上，在 [**帳戶**] 下，從下拉式清單中選擇**網域清單**。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 [**網域清單**] 頁面上，尋找您想要編輯的網域名稱，然後選取**管理**。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 選取 [**進階 DNS**]。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. 在 [**主機記錄**] 區段中，選取 [**新增新的記錄**。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. 在 [**類型**下拉式清單，選取 [ **TXT 記錄**]。
    
    > [!NOTE]
    > 當您選取 [**新增新的記錄**會自動出現**類型**下拉式清單。
  
    ![Namecheap-DYN-BP-CONFIGURE-1-確認-1-1](../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
    （從下拉式清單選擇 [ **TTL** ] 值）。 
    
|**類型**|**主機**|**Value** (值)|**TTL**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **附註**： 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |30 分鐘  <br/> |
   
   ![Namecheap-DYN-BP-CONFIGURE-1-確認-1-2](../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. 選取**儲存的變更**（核取記號） 的控制項。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-確認-1-3](../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

    
2. 在 [**網域**] 頁面上，選取您要驗證的網域。 
    
    
  
3. 在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。
    
    
  
4. 在 [**驗證網域**] 頁面上，選取 [**驗證**]。
    
    
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄

如要完成網域設定以用於 Office 365，請在您的網域註冊機構更改網域的 NS 記錄，使它指向 Office 365 主要和次要名稱伺服器。這樣就會設定並讓 Office 365 為您更新網域的 DNS 記錄。我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。
  
> [!CAUTION]
> 當您變更網域的 NS 記錄以指向 Office 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。例如，在您完成這項變更之後，凡是傳送到您的網域 (例如 rob@ *your_domain*  .com) 的電子郵件都將開始傳送到 Office 365。 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. 若要開始，使用[這個連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)移至您在 Namecheap 的網域頁面。 系統會提示您登入，並繼續。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. 在**登陸**頁面上，在 [**帳戶**] 下，從下拉式清單中選擇**網域清單**。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 [**網域清單**] 頁面上，尋找您想要編輯的網域名稱，然後選取**管理**。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 選取 [**網域**]。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-重新委派-1-1](../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. 尋找 [**名稱**] 區段中，並再從**Namecheap 預設**下拉式清單中選取 [**自訂**。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-重新委派-1-2](../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. 請根據是否已經現在顯示頁面上列出名稱伺服器，繼續進行下列其中一個兩個程序。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>如果列表上「沒有」名稱伺服器
<a name="BKMK_ProcedureWithOUT"> </a>

1. 選取 [**新增名稱伺服器**兩次，以新增兩個新列。
    
    ![Namecheap-BP-Redelegate-1-3-1](../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. 在 [**名稱**] 方塊中，輸入或複製並貼上下表中的值。
    
|||
|:-----|:-----|
|**Nameserver 1 (名稱伺服器 1)** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2 (名稱伺服器 2)** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3 (名稱伺服器 3)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4 (名稱伺服器 4)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. 選取**儲存**（核取記號） 的控制項。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-重新委派-1-5](../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> 您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。 
  
### <a name="if-there-are-nameservers-already-listed"></a>如果列表上「有」名稱伺服器

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (也就是*只*刪除任何目前的名稱伺服器，*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**。) 
  
1. 如果有任何其他名稱伺服器列在 [**名稱**] 方塊中，刪除每個選取它，然後按鍵盤上的**Delete**鍵。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-重新委派-1-4](../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. 選取 [**新增名稱伺服器**兩次，以新增兩個新列。 
    
    ![Namecheap-BP-Redelegate-1-3-1](../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. 在 [**名稱**] 方塊中，輸入或複製並貼上下表中的值。
 
    
|||
|:-----|:-----|
|**Name server 1 (名稱伺服器 1)** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2 (名稱伺服器 2)** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3 (名稱伺服器 3)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4 (名稱伺服器 4)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. 選取**儲存**（核取記號） 的控制項。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-重新委派-1-5](../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> 您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。