---
title: 在 Microsoft 的 eNomCentral 建立 DNS 記錄
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以供 Microsoft eNomCentral。
ms.openlocfilehash: 528659667ee062c8cf767bed0989558020032924
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910363"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a>在 Microsoft 的 eNomCentral 建立 DNS 記錄

 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。

如果 eNomCentral 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。

在 eNomCentral 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。

> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。

> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。

請依照下列步驟操作或[觀看影片 (0:46 從開始)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。

1. 首先請用[這個連結](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)移至 eNom Central 上您的網域頁面。系統會提示您先登入。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 在 [ **我的網域**] 底下，選取您要編輯的網功能變數名稱稱。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. On the **Manage Domain** drop-down list, choose **Host Records**.

   ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. 在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。

   從下拉式清單中選擇 [ **記錄類型** ] 值。

   |主機名稱|Record Type|位址|
   |---|---|---|
   |@|TXT|MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。 [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. 選取 [ **儲存**]。

   ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。

現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 365 並要求 Microsoft 365 尋找該記錄。

在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。

1. 在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

2. 在 **[網域]** 頁面上，選取您要驗證的網域。

3. 在 **[設定]** 頁面上，選取 **[開始設定]**。

4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。

> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft
<a name="BKMK_add_MX"> </a>

請依照下列步驟操作或[觀看影片 (從 3:40 處開始)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。

1. 首先請用[這個連結](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)移至 eNom Central 上您的網域頁面。系統會提示您先登入。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 在 [ **我的網域**] 底下，選取您要編輯的網功能變數名稱稱。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. 在 [ **管理網域** ] 下拉式清單中，選擇 [ **電子郵件設定**]。

   ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. 在 [ **服務選擇** ] 下拉式清單中，選擇 [ **使用者 (MX])**。

   ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. In the boxes for the new record, type or copy and paste the values from the following table.

   |主機名稱|Address (位址)|Pref|
   |---|---|---|
   |@| *\<domain-key\>*  mail.protection.outlook.com。  <br/> **此值必須以英文句點 (.) 結尾。** <br/> **附注：***\<domain-key\>* 從您的 Microsoft 帳戶取得。 [How do I find this?](../get-help-with-domains/information-for-dns-records.md)|10   <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](../setup/domains-faq.yml)|

   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. 選取 [ **儲存**]。

   ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. 如果有任何其他現有的 MX 記錄，請選取其核取方塊來進行選取。

   ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. 選取 [ **刪除] 複選** 框。

   ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

請依照下列步驟操作或[觀看影片 (從 4:24 處開始)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。

1. 首先請用[這個連結](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)移至 eNom Central 上您的網域頁面。系統會提示您先登入。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 在 [ **我的網域**] 底下，選取您要編輯的網功能變數名稱稱。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. On the **Manage Domain** drop-down list, choose **Host Records**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 選取 [ **新增列**]。

   ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. 在六筆新記錄的方塊中，輸入或複製並貼上下列的值。

   從下拉式清單中選擇 [ **記錄類型** ] 值。

   |主機名稱|Record Type|Address (位址)|
   |---|---|---|
   |autodiscover (自動探索)|CNAME (Alias) (CNAME (別名))|autodiscover.outlook.com.  <br/> **此值必須以英文句點 (.) 結尾。**|
   |sip|CNAME (Alias) (CNAME (別名))|sipdir.online.lync.com.  <br/> **此值必須以英文句點 (.) 結尾。**|
   |lyncdiscover|CNAME (Alias) (CNAME (別名))|webdir.online.lync.com.  <br/> **此值必須以英文句點 (.) 結尾。**|
   |enterpriseregistration|CNAME (Alias) (CNAME (別名))|enterpriseregistration.windows.net.  <br/> **此值必須以英文句點 (.) 結尾。**|
   |enterpriseenrollment|CNAME (Alias) (CNAME (別名))|enterpriseenrollment-s.manage.microsoft.com.  <br/> **此值必須以英文句點 (.) 結尾。**|

   ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. 選取 [ **儲存**]。

   ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。 請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。

請依照下列步驟操作或[觀看影片 (從 5:12 處開始)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。

1. 首先請用[這個連結](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)移至 eNom Central 上您的網域頁面。系統會提示您先登入。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 在 [ **我的網域**] 底下，選取您要編輯的網功能變數名稱稱。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. On the **Manage Domain** drop-down list, choose **Host Records**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。

   從下拉式清單中選擇 [ **記錄類型** ] 值。

   |主機名稱|Record Type|位址|
   |---|---|---|
   |@|TXT|v=spf1 include:spf.protection.outlook.com -all  <br/>**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。|

   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. 選取 [ **儲存**]。

   ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>新增兩筆 Microsoft 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

請依照下列步驟操作或[觀看影片 (從 5:50 處開始)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。

1. 首先請用[這個連結](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)移至 eNom Central 上您的網域頁面。系統會提示您先登入。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 在 [ **我的網域**] 底下，選取您要編輯的網功能變數名稱稱。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. On the **Manage Domain** drop-down list, choose **Host Records**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 在 [ **新增列**] 右邊，選取 [新增 **SRV 或 SPF 記錄**]。

   ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. 在這兩筆新記錄的方塊中，輸入或複製並貼上下表中的值。

   |Service (服務)|Protocol (通訊協定)|Priority (優先順序)|Weight (權數)|Port (連接埠)|目標 (主機名稱) |
   |---|---|---|---|---|---|
   |_sip|_tls|100|1|443|sipdir.online.lync.com.  <br/> **此值必須以英文句點 (.) 結尾。**|
   |_sipfederationtls|_tcp|100|1|5061|sipfed.online.lync.com。  <br/> **此值必須以英文句點 (.) 結尾。**|

   ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. 選取 [**儲存**]

   ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。