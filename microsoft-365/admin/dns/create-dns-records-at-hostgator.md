---
title: 在 Hostgator 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Hostgator。
ms.openlocfilehash: d2d8d535d137ca3de2fc6dfc04abe8cf61dda07d
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939188"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a>在 Hostgator 建立 Microsoft 的 DNS 記錄

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 Hostgator 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。
  
> [!IMPORTANT]
> 您必須先執行第一個 procedurebelow，將[您的網域指向您的託管帳戶](#point-your-domain-to-your-hosting-account)，再使用本文中的任何其他程式新增 DNS 記錄。 

在 Hostgator 進行上述所有變更之後，您的網域就會設定為與 Microsoft 服務搭配使用。
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="point-your-domain-to-your-hosting-account"></a>將您的網域指向您的託管帳戶
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> 您必須先執行此程式，再執行本文中的任何其他程式。 
  
請遵循下列步驟，建立您的網域和代管帳戶的關聯。
  
1. 若要開始使用，請移至您的網域管理頁面 Hostgator，方法是使用[此連結](https://portal.hostgator.com/)。 You'll be prompted to log in.
    
2. 選取左側的 [**網域**]。
  
3. 在 [**管理網域**] 頁面上，選取您要更新的網域。 
  
4. 在左側的快顯功能表上，選取 [**名稱伺服器**]。
  
5. 在您網域的 [**名稱伺服器**] 頁面上，在 [**自動將此網域指向我的主機帳戶**] 下拉式清單中，選擇與您的網域相關聯的主控帳戶。 
  
6. 選取 [**儲存名稱伺服器**]。
    
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> 執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。 
  
在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 若要開始使用，請移至您位於 Hostgator 的 cPanel 頁面。系統會提示您先登入。
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. 您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。 您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. 若要開始使用 Microsoft，您可以從 Hostgator 或重新委派名稱伺服器購買主控帳戶，[以指向 Microsoft](change-nameservers-at-hostgator.md)。 
  
2. 在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。
    
3. 在 [**高級區域編輯器**] 頁面的 [新增**記錄**] 區域，于新記錄的方塊中，輸入或複製並貼上下表中的值。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**TTL** <br/> |**類型** <br/> |**TXT Data** <br/> |
    |使用您的*domain_name*。 (for example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |1   <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 在這裡請使用您自己來自表格的 [目的地或指向位址]**** 值。 [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |
   
4. 選取 [**新增記錄**]。
    
5. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。
  
在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  
1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。
    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
4. 在 [驗證網域]**** 頁面上，選取 [驗證]****。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> 執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. 您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。 您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. 若要開始使用 Microsoft，您可以從 Hostgator 或重新委派名稱伺服器購買主控帳戶，[以指向 Microsoft](change-nameservers-at-hostgator.md)。 
  
2. 在 [**控制台**] 頁面的 [**電子郵件**] 區域中，選取 [ **MX 專案**]。
    
 
3. 在 [**電子郵件路由**] 區域中，選取 [**遠端郵件交換器**]。

4. 選取 [**變更**]。
  
5. 在 [新增**記錄**] 區域的新記錄方塊中，輸入或複製並貼上下表中的值。 
    
    |**優先順序**|**Destination**|
    |:-----|:-----|
    |0  <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<網域金鑰\>*  .mail.protection.outlook.com  <br/> **附注：** 從您\<的 Microsoft 帳戶取得您的*網域金鑰*\> 。    [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |
  
6. 選取 [**新增記錄**]。
   
 
7. 如果 [ **Mx 記錄**] 區段中有任何其他 MX 記錄，請移除每個記錄。 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的六筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> 執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. 您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。 您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. 若要開始使用 Microsoft，您可以從 Hostgator 或重新委派名稱伺服器購買主控帳戶，[以指向 Microsoft](change-nameservers-at-hostgator.md)。 
  
2. 在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。
    
3. 新增六筆 CNAME 記錄的第一筆。
    
    在 [**高級區域編輯器**] 頁面的 [新增**記錄**] 區域，于新記錄的方塊中，輸入或複製並貼上下表中第一列的值。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**類型**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*。 （例如，autodiscover.fourthcoffee.com）。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*。 （例如，sip.fourthcoffee.com）。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*。 （例如，lyncdiscover.fourthcoffee.com）。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*。 （例如，enterpriseregistration.fourthcoffee.com）。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*。 （例如，enterpriseregistration.fourthcoffee.com）。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. 選取 [**新增記錄**]。

5. 逐一新增其餘五筆 CNAME 記錄。
    
    在 [ **Add a record] （新增記錄**）區段中，使用表格中下一列的值來建立記錄，然後再選取 [**新增記錄**] 以完成記錄。 
    
    重複這個程序，直到六筆 CNAME 記錄全部建立完畢。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。 而是，請將必要的 Microsoft 值新增到目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。 需要範例？ 請參閱這些 [Microsoft 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。 若要驗證您的 SPF 記錄，您可以使用其中一種 [SPF 驗證工具](../setup/domains-faq.md)。 
  
> [!IMPORTANT]
> 執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. 您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。 您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. 若要開始使用 Microsoft，您可以從 Hostgator 或重新委派名稱伺服器購買主控帳戶，[以指向 Microsoft](change-nameservers-at-hostgator.md)。 
  
2. 在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**類型**|**TXT Data**|
    |:-----|:-----|:-----|:-----|
    |使用您的*domain_name*。 (for example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
  
4. 選取 [**新增記錄**]。
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>新增兩筆 Microsoft 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> 執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. 您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。 您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. 若要開始使用 Microsoft，您可以從 Hostgator 或重新委派名稱伺服器購買主控帳戶，[以指向 Microsoft](change-nameservers-at-hostgator.md)。 
  
2. 在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。

    
3. 新增兩筆 SRV 記錄中的第一筆。
    
    在 [ **ADVANCED DNS 區域編輯器**] 頁面上的 [**新增記錄**] 區域，于新記錄的方塊中，輸入或複製並貼上下表中第一列的值。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**類型**|**Priority** (優先順序)|**Weight** (權數)|**Port** (連接埠)|**Target** (目標)|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip。 _tls。 *domain_name*。 （例如 _sip，_tls fourthcoffee）  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls。 _tcp。 *domain_name*。 （例如 _sipfederationtls，_tcp fourthcoffee）  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. 選取 [**新增記錄**]。

  
5. 新增另一筆 SRV 記錄。
    
    在 [ **Add a record] （新增記錄**）區段中，使用表格中下一列的值來建立記錄，然後再選取 [**新增記錄**] 以完成記錄。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
