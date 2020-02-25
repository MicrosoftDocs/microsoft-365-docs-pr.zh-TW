---
title: 使用 Google Domains 變更名稱伺服器以設定 Office 365
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: 了解如何設定 Office 365 來管理您在 Google Domains 的自訂網域的 DNS 記錄。
ms.openlocfilehash: 771d38b9a3d08bef75c3ad1958f981539edb6c04
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239845"
---
# <a name="change-nameservers-to-set-up-office-365-with-google-domains"></a>使用 Google Domains 變更名稱伺服器以設定 Office 365

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果要讓 Office 365 為您管理 Office 365 DNS 記錄，請按照下列指示進行 (您可視需要[在 Google Domains 管理所有 Office 365 DNS 記錄](create-dns-records-at-google-domains.md))。
  
    
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證

在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
> [!NOTE]
>  這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 若要開始，透過[這個連結](https://domains.google.com/registrar)移至 Google Domains 上您的網域頁面。 You'll be prompted to sign in. To do so:
    
1. 選取 [**登入**]。
    
2. 輸入您的登入認證，然後再選取 [**登入**]。
    
2. 在 [**網域**] 頁面上，在 [**網域**] 區段中，選取**設定 DNS**針對您想要編輯的網域。 
    
3. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**Type** <br/> |**TTL** <br/> |**資料** <br/> |
|@  <br/> |TXT  <br/> |1H]  <br/> |MS=ms *XXXXXXXX* <br/> **附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. 選取 **[新增]**。
    
5. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

    
2. 在 [**網域**] 頁面上，選取您要驗證的網域。 
    
3. 在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。
    
4. 在 [**驗證網域**] 頁面上，選取 [**驗證**]。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果您遇到與郵件流程或其他問題新增 DNS 記錄之後，請參閱[尋找並修正新增網域或 Office 365 中的 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄

如要完成網域設定以用於 Office 365，請在您的網域註冊機構更改網域的 NS 記錄，使它指向 Office 365 主要和次要名稱伺服器。這樣就會設定並讓 Office 365 為您更新網域的 DNS 記錄。我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。
  
> [!CAUTION]
> 當您變更網域的 NS 記錄以指向 Office 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。 例如，所有的電子郵件傳送至您的網域 (例如 rob @ *your_domain。*  com) 都會開始送往 Office 365 之後進行這項變更。 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. 這四個 > 當您完成在此區段中，應該會列出的唯一名稱伺服器的步驟︰ 
  
1. 首先請用[這個連結](https://domains.google.com/registrar)移至 Google Domains 上您的網域頁面。系統會提示您登入。若要執行此作業，請執行下列動作：
    
1. 選取 [**登入**]。
    
2. 輸入您的登入認證，然後再選取 [**登入**。
    
2. 在 [**網域**] 頁面上，在 [**網域**] 區段中，選取**設定 DNS**針對您想要編輯的網域。 
    
3. 在 [**網域**] 頁面上**Name servers** ] 區段中，選取**使用自訂名稱伺服器**。
    
    ![Google-網域-BP-重新委派-1-1](../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. 請根據現在顯示頁面上是否列出名稱伺服器，來選擇下列兩個程序其中一項繼續︰
    
  - 如果有**無**列 」 名稱伺服器，[如果有列出名稱伺服器](#if-there-are-no-nameservers-already-listed)。
    
  - 如果**是**那里 」 列出名稱伺服器，[如果有列出名稱伺服器](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>如果列表上「沒有」名稱伺服器

1. 新增第一個名稱伺服器。
    
    在 [**名稱伺服器**] 區段的 [**名稱伺服器**] 方塊中，輸入或複製並貼上下表中的第一個值。 
    
|||
|:-----|:-----|
|**第一個名稱伺服器** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**第二個名稱伺服器** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**第三個名稱伺服器** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四個名稱伺服器** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-2](../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. 選取 **+ （新增）** 的控制項來建立空白的列。 
    
    ![Google-網域-BP-重新委派-1-3](../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. 新增其他三個名稱伺服器記錄。
    
    在 [**使用自訂名稱伺服器**] 區段中，在表格中，使用下一列的值來建立記錄，然後選取 **+ （新增）** 的控制項，以新增另一個資料列。 
    
    重複這個程序，直到四筆名稱伺服器記錄全部建立完畢。
    
4. 選取 **[儲存]**。
    
    ![Google-網域-BP-重新委派-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> 您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。 
  
### <a name="if-there-are-nameservers-already-listed"></a>如果列表上「有」名稱伺服器

1. 如果有任何其他列出的名稱伺服器，請選取 [**編輯**]。
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (也就是刪除只是任何目前的名稱*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**。) 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. 刪除每個選取它，，然後按鍵盤上的**Delete**鍵。 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. 同樣在 [**名稱伺服器**] 區段的**名稱伺服器**列中，輸入或複製並貼上下表中的值。 
    
|||
|:-----|:-----|
|**第一個名稱伺服器** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**第二個名稱伺服器** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**第三個名稱伺服器** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四個名稱伺服器** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-7](../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. 選取 **+(add)** 控制項來建立空白的列。 
    
    ![Google-Domains-BP-Redelegate-1-8](../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. 新增其他兩筆名稱伺服器記錄。
    
    在 [**使用自訂名稱伺服器**] 區段中，在表格中，使用下一列的值來建立記錄，然後選取 **+(add)** 控制項以新增另一個資料列。 
    
    重複這個程序，直到四筆名稱伺服器記錄全部建立完畢。
    
6. 選取 **[儲存]**。
    
    ![Google-網域-BP-重新委派-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> 您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。 
  
