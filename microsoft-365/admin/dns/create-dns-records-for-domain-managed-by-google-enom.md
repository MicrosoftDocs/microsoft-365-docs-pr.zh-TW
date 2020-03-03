---
title: 您的網域由 Google (eNom) 管理時建立 DNS 記錄
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
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: 了解如何存取 eNom，並透過 Google Domains] 頁面上建立 DNS。
ms.openlocfilehash: 566b3990c6cc3080eac9d1367531eea42ab135d1
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362498"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>您的網域由 Google (eNom) 管理時建立 DNS 記錄

 若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。 
  
若要將您的郵件帳戶移轉到 Office 365，您需要在您的網域註冊機構建立 DNS 記錄。
  
如果您購買透過 Google 網域註冊時為您的**Google Apps for Work**帳戶時，您的 DNS 記錄是由 Google 管理，但是註冊 eNom。 
  
您可以存取 eNom，並透過 Google**網域**] 頁面上建立 DNS]。 請按照本文所述的步驟進行。 
  
## <a name="create-the-dns-record"></a>建立 DNS 記錄

1. 在[Google 系統管理主控台](https://www.google.com/work/apps/business)中，選取 [**登入**。
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. 輸入您的網域名稱，然後再選取 [**移**。
    
    ![Google-Apps-Configure-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. 在頁面底部，選取 [**更多控制項**。
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Select **Domains**.
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. 在 [**網域**] 頁面上，選取 [**新增/移除網域**。
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. 在 [**網域**] 頁面上選取 [**進階 DNS 設定**]。
    
    > [!NOTE]
    > 如果您未購買透過 Google 網域名稱註冊您的**Google Apps for Work**帳戶時，您不會有**進階 DNS 設定**上您的**網域**頁面。 相反地，您必須直接前往您網域主機的網站以存取您的 DNS 設定，並執行此操作與下列步驟。 如需詳細資訊，請參閱[存取您的 G Suite 網域設定](https://support.google.com/a/answer/54693?hl=en)。 
  
    ![Google-Apps-eNom-Configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. 在 [**進階 DNS 設定**] 頁面上，選取 [**登入 DNS 主控台**。 請注意的**登入名稱**及**密碼**資訊。 您在下一個步驟需要用到這些資訊。 
    
    ![Google-Apps-eNom-Configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. 登入 Google**網域管理員**從 [**進階 DNS 設定**] 頁面上使用的**登入名稱**與**密碼**。 
    
    ![Google-Apps-eNom-Configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. 在 [ ***domain_name*** ] 頁面的 [在 [**主機記錄**] 區段中，選取 [**編輯**]。
    
    ![Google-Apps-eNom-Configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. 在 [**主機記錄**] 區段中，選取 [**加入新**項目。
    
    ![Google-Apps-eNom-Configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. 在新記錄的方塊中，輸入或複製並貼上下表中的值。
    
    |**主應用程式**|**TXT VALUE**|**記錄類型**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > This is an example. 在這裡請使用您自己的 **[目的地或指向位址]** 值，請參閱 Office 365 表格。 
  
    [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)
  
12. 選取 [儲存]****。
    
    ![Google-Apps-eNom-Configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. 選取 [**儲存變更**。
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
