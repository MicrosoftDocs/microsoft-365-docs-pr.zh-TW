---
title: 變更名稱伺服器以設定 Microsoft 搭配 Google 網域
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: 瞭解如何設定 Microsoft 以管理 Google 網域的自訂網域的 DNS 記錄。
ms.openlocfilehash: 65649632b5e28e97909d91ca3e04355375afe3ac
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400650"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a>變更名稱伺服器以設定 Microsoft 搭配 Google 網域

 若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。 
  
如果您想讓 Microsoft 為您管理您的 DNS 記錄，請遵循下列指示。 （如果您願意，您可以[管理 Google 網域中的所有 DNS 記錄](create-dns-records-at-google-domains.md)。）
  
    
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證

在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。
  
> [!NOTE]
>  這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 若要開始，請透過[此連結](https://domains.google.com/registrar)移至 Google 網域上的 [網域] 頁面。 You'll be prompted to sign in. To do so:
    
1. 選取 [登**入**]。
    
2. 輸入您的登入認證，然後再次選取 [登**入**]。
    
2. 在 [**網域**] 頁面上的 [**網域**] 區段中，針對您要編輯的網域選取 [**設定 DNS** ]。 
    
3. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**Type** <br/> |**TTL** <br/> |**資料** <br/> |
|@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX* <br/> **附註：** 這是範例。 在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。 [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. 選取 **[新增]**。
    
5. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。
  
在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  
1. 在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄

若要使用 Microsoft 設定您的網域，請在您的網域註冊機構變更網域的 NS 記錄，以指向 Microsoft 主要和次要名稱伺服器。 這會將 Microsoft 設定為您為您更新網域的 DNS 記錄。 我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。
  
> [!CAUTION]
> 當您將網域的 NS 記錄變更為指向 Microsoft 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。 例如，所有傳送至您網域的電子郵件（如 rob@ *your_domain。*  com）在您進行此變更之後，將會開始進行 Microsoft。 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > 完成本節中的步驟之後，唯一應該會列出的名稱伺服器為下列四種： 
  
1. 首先請用[這個連結](https://domains.google.com/registrar)移至 Google Domains 上您的網域頁面。系統會提示您登入。若要執行此作業，請執行下列動作：
    
1. 選取 [登**入**]。
    
2. 輸入您的登入認證，然後再選取 [登**入**]。
    
2. 在 [**網域**] 頁面上的 [**網域**] 區段中，針對您要編輯的網域選取 [**設定 DNS** ]。 
    
3. 在 [**網域**] 頁面上，選取 [**名稱伺服器**] 區段中的 [**使用自訂名稱伺服器**]。
    
    ![Google-網域-BP-重新委派-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. 請根據現在顯示頁面上是否列出名稱伺服器，來選擇下列兩個程序其中一項繼續︰
    
  - 如果沒有列出**任何**名稱伺服器，[則未列出任何名稱伺服器](#if-there-are-no-nameservers-already-listed)。
    
  - 如果已**列出名稱伺服器，** 如果已[列出名稱伺服器](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>如果列表上「沒有」名稱伺服器

1. 新增第一個名稱伺服器。
    
    在 [**名稱**伺服器] 區段的 [**名稱伺服器**] 方塊中，輸入或複製並貼上下清單格中的第一個值。 
    
|||
|:-----|:-----|
|**第一個名稱伺服器** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**第二個名稱伺服器** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**第三名稱伺服器** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四名稱伺服器** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-網域-BP-重新委派-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. 選取 [ **+] （新增）** 控制項來建立空白列。 
    
    ![Google-網域-BP-重新委派-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. 新增其他三個名稱伺服器記錄。
    
    在 [**使用自訂名稱伺服器**] 區段中，使用表格中下一列的值來建立記錄，然後選取 [ **+] （新增）** 控制項以新增另一列。 
    
    重複這個程序，直到四筆名稱伺服器記錄全部建立完畢。
    
4. 選取 [儲存]****。
    
    ![Google-網域-BP-重新委派-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> 您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。 然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。 
  
### <a name="if-there-are-nameservers-already-listed"></a>如果列表上「有」名稱伺服器

1. 如果有列出任何其他名稱伺服器，請選取 [**編輯**]。
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. （也就是說，只刪除所有*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的目前名稱伺服器。） 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. 選取它，然後按鍵盤上的**Delete**鍵，逐一刪除。 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. 在 [**名稱**伺服器] 區段的 [名稱**伺服器**] 列中，輸入或複製並貼上下清單格中的值。 
    
|||
|:-----|:-----|
|**第一個名稱伺服器** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**第二個名稱伺服器** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**第三名稱伺服器** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四名稱伺服器** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-網域-BP-重新委派-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. 選取 [ **+] （新增）** 控制項來建立空白列。 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. 新增其他兩筆名稱伺服器記錄。
    
    在 [**使用自訂名稱伺服器**] 區段中，使用表格中下一列的值來建立記錄，然後選取 [ **+] （新增）** 控制項以新增另一列。 
    
    重複這個程序，直到四筆名稱伺服器記錄全部建立完畢。
    
6. 選取 [儲存]****。
    
    ![Google-網域-BP-重新委派-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> 您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。 然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。 
  
