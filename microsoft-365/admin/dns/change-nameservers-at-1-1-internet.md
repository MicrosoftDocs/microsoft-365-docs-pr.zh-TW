---
title: 使用 1&1 IONOS 變更名稱伺服器以設定 Microsoft。
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: 瞭解如何設定由世紀運作的 Office 365，以管理您的 DNS 記錄（1&1 網際網路是 DNS 主機服務提供者時）。
ms.openlocfilehash: b363718c7d1d1845117f44317ae9e6b24e9a2e28
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658029"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a>變更名稱伺服器以設定具有 1&1 IONOS 的 Microsoft 365

 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。 
  
如果您想讓 Microsoft 365 為您管理 Microsoft 365 DNS 記錄，請遵循下列指示。  (如果您願意，您可以 [在 1&1 IONOS，管理所有 Microsoft 365 DNS 記錄](create-dns-records-at-1-1-internet.md)。 )  
  

    
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證


在您將自己的網域用於 Microsoft 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
請依照下列步驟操作或[觀看影片 (從 0:42 處開始)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3)。
  
1. 若要開始，請移至您的網域頁面 1&1 IONOS 透過 [此連結](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)。 You'll be prompted to log in. 
    
2. 在 [ **我的網域**] 底下，選取 [ **管理網域**]。
    
3. 在 [ **網域中心** ] 頁面上，尋找您要更新的網域;然後，為該網域選取 **面板** ( **v**) 控制項。
    
4. 在 [ **網域設定** ] 區域中，選取 [ **編輯 DNS 設定**]。
    
5. 在 [ **TXT 和 SRV 記錄** ] 區段中，選取 [ **新增記錄**]。
    
    (您可能需要向下捲動。) 
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Type** <br/> |**Prefix** <br/> |**Name Value** <br/> |
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX* <br/> **請注意**：這是一個範例。 在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Microsoft 365 表格。 [如何找到呢？](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. 請選取 [ **儲存**]，然後再 **儲存** 一次。 
    
8. 在 [ **編輯 DNS 設定** ] 對話方塊中，選取 **[是]**。
    
9. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 365 並要求 Microsoft 365 尋找該記錄。
  
在 Microsoft 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  
1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。
    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱 [尋找並修正在 Microsoft 365 中新增您的網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄

若要使用 Microsoft 365 完成設定您的網域，您可以在網域註冊機構變更網域的 NS 記錄，以指向 Microsoft 365 主要和次要名稱伺服器。 這會將 Microsoft 365 設定為為您更新網域的 DNS 記錄。 我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。
  
> [!CAUTION]
> 當您將網域的 NS 記錄變更為指向 Microsoft 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。 例如，傳送至您網域的所有電子郵件 (例如 rob@ *your_domain*  .com) 會在您進行此變更後開始從 Microsoft 365。 
  
準備好變更您的 NS 記錄，讓 Microsoft 365 可以設定您的網域？ 請依照下列步驟操作或[觀看影片 (從 2:47 處開始)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3)。
  
> [!IMPORTANT]
>  下列程式將告訴您如何刪除清單中的任何其他、不想要的名稱伺服器，以及如何新增正確的名稱伺服器（如果尚未列出）。 > 完成本節中的步驟之後，應該會列出的唯一名稱伺服器為下列四種： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. 若要開始使用，請移至您的網域頁面，1&1 IONOS，方法是使用 [此連結](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)。 You'll be prompted to log in. 
    
2. 在 [ **我的網域**] 底下，選取 [ **管理網域**]。
    
3. 在 [ **網域中心** ] 頁面上，找到您要更新的網域，然後選取該網域的 [ **面板** ] ( **v**) 控制項。
    
4. 在 [ **網域設定** ] 區域中，選取 [ **編輯 DNS 設定**]。
    
5. 在 [ **名稱伺服器設定** ] 區段中，選取 [ **其他名稱伺服器**]。
    
    (您可能需要向下捲動。)
    
6. 請根據現在顯示頁面上是否列出名稱伺服器，來選擇下列兩個程序其中一項繼續︰
    
  - 如果沒有列出 **任何** 名稱伺服器， [則未列出任何名稱伺服器](#if-there-are-no-nameservers-already-listed)。
    
  - 如果已 **列出名稱伺服器，** 如果已 [列出名稱伺服器](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>如果列表上「沒有」名稱伺服器

1. 在 [ **名稱伺服器 1** ] 方塊中，輸入或複製並貼上下清單格中的值。 
    
|||
|:-----|:-----|
|**名稱伺服器1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
   
   ![在 [名稱伺服器 1] 方塊中輸入值](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. 在 [ **其他名稱伺服器** ] 下拉式清單中，選擇 [ **我的次要名稱伺服器**]。
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. 在 [ **名稱伺服器2、3] 及 [4** ] 方塊中，輸入或複製並貼上下表中的值。 
    
|||
|:-----|:-----|
|**名稱伺服器2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**名稱伺服器3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**名稱伺服器4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
![輸入名稱伺服器值](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. 選取 **[儲存]**。
    
    ![在 [名稱伺服器設定] 頁面上選取 [儲存]](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. 在 [ **編輯 DNS 設定** ] 對話方塊中，選取 **[是]**。
    
    ![在 [編輯 DNS 設定] 對話方塊中選取 [儲存]](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。 
  
### <a name="if-there-are-nameservers-already-listed"></a>如果列表上「有」名稱伺服器

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.  (也就是說，  *只*  刪除所有  *未*  命名為 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com** 的目前名稱伺服器。 )  
  
1. 如果 [名稱伺服器] 方塊中已列出名稱伺服器，請選取每個 **名稱伺服器** ，然後按鍵盤上的 **delete** 鍵，逐一刪除。 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. 在 [ **名稱伺服器1、2、3] 及 [4** ] 方塊中，輸入或複製並貼上下表中的值。 
    
|||
|:-----|:-----|
|**名稱伺服器1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**名稱伺服器2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**名稱伺服器3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**名稱伺服器4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![輸入名稱伺服器值](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. 選取 **[儲存]**。
    
    ![在 [名稱伺服器設定] 頁面上選取 [儲存]](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. 在 [ **編輯 DNS 設定** ] 對話方塊中，選取 **[是]**。
    
    ![在 [編輯 DNS 設定] 對話方塊中選取 [儲存]](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。 
  


