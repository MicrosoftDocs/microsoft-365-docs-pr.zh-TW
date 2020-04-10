---
title: 當您的網域由 Google 管理時建立 DNS 記錄（eNom）
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
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: 瞭解如何透過 Google 網域頁面存取 eNom 及建立 DNS。
ms.openlocfilehash: 8fc13ea2ccc7dfee510ef7abb72f88030d048943
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210655"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>當您的網域由 Google 管理時建立 DNS 記錄（eNom）

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
若要將您的郵件帳戶移轉到 Office 365，您需要在您的網域註冊機構建立 DNS 記錄。
  
如果您在註冊**Google Apps For Work** account 時透過 google 購買網域，您的 DNS 記錄會由 google 管理，但會向 eNom 註冊。 
  
您可以透過 Google**網域**頁面存取 eNom 及建立 DNS。 請按照本文所述的步驟進行。 
  
## <a name="create-the-dns-record"></a>建立 DNS 記錄

1. 在[Google 管理主控台](https://www.google.com/work/apps/business)上，選取 [登**入**]。
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. 輸入您的功能變數名稱，然後選取 [**繼續**]。
    
    ![Google-Apps-Configure-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. 在頁面底部，選取 [**其他控制項**]。
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Select **Domains**.
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. 在 [**網域**] 頁面上，選取 [**新增/移除網域**]。
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. 在 [**網域**] 頁面上，選取 [**高級 DNS 設定**]。
    
    > [!NOTE]
    > 如果您在註冊**Google Apps For Work** account 時未透過 Google 購買功能變數名稱，您的**網域**頁面上將不會有**高級 DNS 設定**。 相反地，您必須直接前往您網域主機的網站以存取您的 DNS 設定，並執行此操作與下列步驟。 如需詳細資訊，請參閱[Access G Suite 網域設定](https://support.google.com/a/answer/54693?hl=en)。 
  
    ![Google-Apps-eNom-Configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. 在 [**高級 DNS 設定**] 頁面上，選取 [登**入 dns 主控台**]。 記下登**入名稱**和**密碼**資訊。 您在下一個步驟需要用到這些資訊。 
    
    ![Google-Apps-eNom-Configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. 使用 [**高級 DNS 設定**] 頁面中的登**入名稱**和**密碼**登入 Google**網域管理員**。 
    
    ![Google-Apps-eNom-Configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. 在 [ ***domain_name*** ] 頁面上的 [**主機記錄**] 區段中，選取 [**編輯**]。
    
    ![Google-Apps-eNom-Configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. 在 [**主機記錄**] 區段中，選取 [**新增**]。
    
    ![Google-Apps-eNom-Configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. 在新記錄的方塊中，輸入或複製並貼上下表中的值。
    
    |**主機**|**TXT VALUE**|**記錄類型**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > This is an example. 在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。 
  
    [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)
  
12. 選取 **[儲存]**。
    
    ![Google-Apps-eNom-Configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. 選取 [**儲存變更**]。
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
