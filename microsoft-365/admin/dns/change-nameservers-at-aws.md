---
title: 使用 Amazon Web 服務（AWS）變更名稱伺服器以設定 Microsoft
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: '瞭解如何設定 Microsoft 以管理 Amazon Web 服務（AWS）上的 DNS 記錄。 '
ms.openlocfilehash: 6393ef3e0d9603f122685dd3e3904b653fda8c34
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629992"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a>使用 Amazon Web 服務（AWS）變更名稱伺服器以設定 Microsoft

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果您想讓 Microsoft 為您管理您的 DNS 記錄，請遵循下列指示。 （如果您願意，您可以[在 AWS 管理所有的 MICROSOFT DNS 記錄](create-dns-records-at-aws.md)。）
  
    
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證

在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。 您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。系統會提示您先登入。
    
2. 在 [**資源**] 頁面上，選取 [**主控區域**]。
    
3. 在 [**主控區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。 
    
4. 選取 [**建立記錄集**]。
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**名稱** <br/> |**Type** <br/> |**Alias** <br/> |**TTL (Seconds)** <br/> |**值** <br/> |**Routing Policy** <br/> |
|（將此欄位保留空白）  <br/> |TXT - Text  <br/> |否  <br/> |300  <br/> |MS=ms *XXXXXXXX* <br/> **附註：** 這是範例。 從表格中，使用您的特定**目的地或指向位址**值。 [How do I find this?](../get-help-with-domains/information-for-dns-records.md)  <br/>  |簡易 <br/> |
   
6. 選取 [建立]****。
    
7. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。
  
當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。
  
1. 在 Microsoft 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
4. 在 [驗證網域]**** 頁面上，選取 [驗證]****。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。 如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱[尋找並修正新增您的網域或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄

若要使用 Microsoft 設定您的網域，請在您的網域註冊機構變更網域的 NS 記錄，以指向 Microsoft 主要和次要名稱伺服器。 這會將 Microsoft 設定為您為您更新網域的 DNS 記錄。 我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。
  
> [!CAUTION]
> 當您將網域的 NS 記錄變更為指向 Microsoft 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。 例如，在您進行此變更之後，所有傳送至您網域的電子郵件（如 rob@ *your_domain* .com）都會開始向 Microsoft。 
  
> [!IMPORTANT]
>  下列程式將告訴您如何刪除清單中的任何其他、不想要的名稱伺服器，以及如何新增正確的名稱伺服器（如果尚未列出）。 > 完成本節中的步驟之後，應該會列出的唯一名稱伺服器為下列四種： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. 首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。 系統會提示您先登入。
    
2. 在 [**資源**] 頁面上，選取 [**主控區域**]。
    
3. 在 [**主控區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。 
    
4. 選取 [**名稱**伺服器] 記錄集。 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. 在 [**值**] 方塊的 [ **NS-名稱伺服器**] 記錄集中，選取所有的名稱伺服器，然後按下鍵盤上的**delete**鍵來刪除所有。 
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. （也就是說，只刪除所有*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的目前名稱伺服器。） 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. 在 [ **TTL （秒）：** ] 區域中，選取 [ **1H** （1小時）]。 
    
    ![選取1H 一小時](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. 仍在**NS 名稱伺服器**記錄集中的 [**值**] 方塊中，輸入或複製並貼上下表中的**第一個行**值，然後按下鍵盤上的**Enter**鍵，然後輸入或複製並貼上下**一行**的值。 
    
    > [!IMPORTANT]
    > 每個名稱伺服器值都*必須*在 [**值**] 方塊中各自的個別行上，如下圖所示。 
  
|||
|:-----|:-----|
|**第一行** <br/> |ns1.bdm.microsoftonline.com。  <br/> **This value MUST end with a period (.)** <br/> |
|**第二行** <br/> |ns2.bdm.microsoftonline.com。  <br/> **This value MUST end with a period (.)** <br/> |
|**第三行** <br/> |ns3.bdm.microsoftonline.com。  <br/> **This value MUST end with a period (.)** <br/> |
|**第四行** <br/> |ns4.bdm.microsoftonline.com。  <br/> **This value MUST end with a period (.)** <br/> |
   
   ![在 [值] 方塊中，輸入或貼上第一個行的值](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. 選取 [**儲存記錄集**]。
    
    ![選取儲存記錄集](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。 
