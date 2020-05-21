---
title: 建立 DLP 原則來保護具有 FCI 或其他屬性的文件
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 許多組織已使用 Windows Server 檔分類基礎結構（FCI）中的分類屬性、SharePoint 中的檔案屬性或協力廠商系統所套用的檔案屬性，來識別及分類敏感資訊的程式。 如果這會描述您的組織，您可以建立 DLP 原則，以辨識 Windows Server FCI 或其他系統已套用至檔的屬性，如此便能在具有特定 FCI 或其他屬性值的 Office 檔上強制執行 DLP 原則。
ms.openlocfilehash: 3fa28492ef4d19903797741795091561de3fa257
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327099"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>建立 DLP 原則來保護具有 FCI 或其他屬性的文件

在 Microsoft 365 中，您可以使用資料遺失防護（DLP）原則來識別、監視和保護機密資訊。 許多組織已使用 Windows Server 檔分類基礎結構（FCI）中的分類屬性、SharePoint 中的檔案屬性或協力廠商系統所套用的檔案屬性，來識別及分類敏感資訊的程式。 如果這會描述您的組織，您可以建立 DLP 原則，以辨識 Windows Server FCI 或其他系統已套用至檔的屬性，如此便能在具有特定 FCI 或其他屬性值的 Office 檔上強制執行 DLP 原則。
  
![圖表顯示 Office 365 及外部的分類系統](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
例如，您的組織可能會使用 Windows Server FCI，透過個人身分識別資訊（PII）來識別檔，例如社會保險號碼，然後根據檔中找到之 PII 的類型和數量，將 [**個人身分識別資訊**] 屬性設定為 [**高**]、[**適中**]、[**低**]、[**公用**] 或 [**不是 PII** ]。 在 Microsoft 365 中，您可以建立一個 DLP 原則，識別具有該屬性設定為特定值的檔，例如 [**高**] 和 [**中**]，然後採取諸如封鎖對這些檔案的存取等動作。 如果屬性設定為 [**低**] （例如傳送電子郵件通知），相同的原則可以有另一個規則採用其他的動作。 如此一來，DLP 便會與 Windows Server FCI 整合，並協助保護從 Windows Server 檔案伺服器上傳或共用至 Microsoft 365 的 Office 檔。
  
DLP 原則只會尋找特定的屬性名稱/值對。 只要屬性具有對應的 managed 屬性 SharePoint 搜尋，就可以使用任何檔案屬性。 例如，SharePoint 網站集合可能會使用名為「**客戶**」之必要欄位的「**行程報告**」內容類型。 每當人員建立行程報告時，他們必須輸入客戶名稱。 您也可以在 DLP 原則中使用此屬性名稱/值組（例如，如果您想要在**客戶**欄位包含**Contoso**時，封鎖外部使用者存取檔的規則）。
  
請注意，如果您想要將 DLP 原則套用至特定 Microsoft 365 標籤的內容，您不應該遵循這裡的步驟。 請改為了解如何[使用保留標籤做為 DLP 原則中的條件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。
  
## <a name="before-you-create-the-dlp-policy"></a>建立 DLP 原則之前

您必須先在 SharePoint 系統管理中心建立 managed 屬性，才能使用 DLP 原則中的 Windows Server FCI 屬性或其他屬性。 原因如下。
  
在 SharePoint Online 和商務 OneDrive 中，搜尋索引會透過編目您網站上的內容來建立。 編目程式會以編目屬性的形式挑選檔中的內容和中繼資料。 搜尋架構可協助編目程式決定要挑選的內容和中繼資料。 中繼資料的範例包括作者及檔的標題。 不過，若要將檔中的內容和中繼資料取得搜尋索引，編目屬性必須對應至 managed 屬性。 只有 managed 屬性會保留在索引中。 例如，與 author 相關的編目屬性會對應至與 author 相關的 managed 屬性。
  
這一點很重要，因為 DLP 會使用搜尋編目程式來識別和分類您網站上的機密資訊，然後將該機密資訊儲存在搜尋索引的安全部分。 當您將檔上傳至 Office 365 時，SharePoint 會根據檔案屬性，自動建立編目屬性。 不過，若要使用 DLP 原則中的 FCI 或其他屬性，該編目屬性必須對應至 managed 屬性，這樣該屬性的內容就會保留在索引中。
  
如需搜尋及 managed 屬性的詳細資訊，請參閱[Manage the search schema in SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=627454)。
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>步驟1：將具有必要屬性的檔上傳至 Office 365

您必須先將檔上傳至您要在 DLP 原則中參考的屬性。 Microsoft 365 會偵測屬性，並自動從該屬性建立編目屬性。 在下一個步驟中，您將建立 managed 屬性，然後將 managed 屬性對應至此編目屬性。
  
### <a name="step-2-create-a-managed-property"></a>步驟2：建立 managed 屬性

1. 登入 Microsoft 365 系統管理中心。
    
2. 在左側導覽中，選擇 [系統**管理中心**] \> **SharePoint**。 You're now in the SharePoint admin center.
    
3. 在左側導覽中，選擇**search** \> [搜尋**管理**] 頁面上的 [搜尋] [ \> **管理搜尋架構**]。
    
    ![SharePoint 系統管理中心的搜尋管理頁面](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. 在 [ **Managed 屬性**] 頁面的 [ \> **新增 managed 屬性**]。
    
    ![受管理屬性頁面上有以反白顯示的新增受管理的屬性按鈕](../media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. 輸入屬性的名稱和描述。 此名稱會顯示在您的 DLP 原則中。
    
6. 針對 [**類型**]，選擇 [**文字**]。 
    
7. 在 [**主要特性**] 底下，選取 [可**查詢**及可**檢索**]。
    
8. 在 [對應至編目屬性] 底下 **，** \> **新增對應**。
    
9. 在 [編目**屬性選項**] 對話方塊中 \> ，尋找並選取對應至您將在 DLP 原則 OK 中使用的 Windows Server FCI 屬性或其他屬性的編目屬性 \> ** **。
    
    ![選取編目屬性對話方塊](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. 在頁面底部的 \> **[確定]**。
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>建立使用 FCI 屬性或其他屬性的 DLP 原則

在此範例中，組織在其 Windows 伺服器型檔案伺服器上使用 FCI;具體而言，他們使用的是名為**個人身分識別資訊**的 FCI 分類屬性，其可能的值為**High**、**適中**、**低**、**公有**和**非 PII**。 現在，他們想要在 Office 365 的 DLP 原則中利用其現有的 FCI 分類。
  
首先，他們會依照上述步驟，在 SharePoint Online 中建立 managed 屬性，該屬性會對應至自動從 FCI 屬性建立的編目屬性。
  
接下來，他們會建立一個 DLP 原則，其中兩個規則都使用條件**檔案屬性包含下列任一值**：
  
- **FCI PII 內容-高、適中**第一個規則會限制存取檔如果 FCI 分類屬性**個人識別資訊**等於**高**或**適中**，而且檔與組織外部人員共用。 
    
- **FCI PII 內容-低**第二個規則會在 FCI 分類屬性**個人識別資訊**等於**低**，且與組織外部人員共用檔時，將通知傳送給檔擁有者。 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>使用 PowerShell 建立 DLP 原則

請注意，[安全性與合規性中心] 的 UI 中暫時無法使用 [條件**檔案屬性] 這兩個值** &amp; ，但您仍然可以使用 PowerShell 來使用此條件。 您可以使用 `New\Set\Get-DlpCompliancePolicy` Cmdlet 來使用 DLP 原則，並搭配參數使用 Cmdlet， `New\Set\Get-DlpComplianceRule` `ContentPropertyContainsWords` 以新增條件**檔案屬性包含這些值中的任何一個**。
  
如需這些 Cmdlet 的詳細資訊，請參閱[安全性 &amp; 規範中心 Cmdlet](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。
  
1. [&amp;使用遠端 PowerShell 連接至安全規範中心](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. 使用建立原則 `New-DlpCompliancePolicy` 。

以下是建立套用至所有位置之 DLP 原則的 PowerShell 範例。

```powershell
New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
```

3. 使用 `New-DlpComplianceRule` 其中一個規則是**低**值的規則，而另一個規則是用於**高低**值，以建立上述的兩個規則**Moderate** 。 
    
    以下是建立這兩個規則的 PowerShell 範例。 請注意，屬性名稱/值對會以引號括住，屬性名稱可以指定多個以逗號分隔的多個值，不含空格，例如`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

```powershell
New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
```

    Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example. The possible values for each property can be different for every organization. The **High**, **Moderate**, and **Low** values used here are only an example. For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server. For more information, see [Create a classification property](https://go.microsoft.com/fwlink/p/?LinkID=627456).
    
當您完成時，您的原則應該會有兩個新規則，都使用**檔案屬性包含這些值的任何**條件。 請注意，此條件不會出現在 UI 中，但會顯示其他條件、動作和設定。
  
一個規則會封鎖**個人身分識別資訊**屬性等於**High**或**適中**的內容存取權。 第二個規則會傳送有關**個人身分識別資訊**屬性等於**Low**的內容通知。
  
![新的 DLP 原則對話方塊顯示剛才建立的兩個規則](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>建立 DLP 原則之後

執行上述各節中的步驟，會建立一個 DLP 原則，它會使用該屬性快速偵測內容，但只有在新上傳該內容時（即內容的索引），或是該內容已經過編輯（這樣就會重新編制內容）。
  
若要在任何地方使用該屬性偵測內容，您可能想要手動要求您的文件庫、網站或網站集合重新編制索引，以便 DLP 原則知道具有該屬性的所有內容。 在 [SharePoint 線上] 中，會根據定義的編目排程自動編目內容。 編目程式會挑選自上次編目後已變更的內容，並更新索引。 如果您需要 DLP 原則在下一個排程編目之前保護內容，您可以採取下列步驟。
  
> [!CAUTION]
> 重新編制網站索引可能會導致搜尋系統負載大幅。 除非您的案例絕對需要，否則不要重新建立網站索引。 
  
如需詳細資訊，請參閱[手動要求網站、文件庫或清單進行編目和重新建立索引](https://go.microsoft.com/fwlink/p/?LinkID=627457)。
  
### <a name="re-index-a-site-optional"></a>重新建立網站索引（選用）

1. 在網站上，選擇 [**設定**] （右上角的齒輪圖示） \> **網站設定**。
    
2. 在 [**搜尋**] 底下，選擇 [**搜尋及離線可用性**重新 \> **索引網站**]。
    
## <a name="more-information"></a>詳細資訊

- [資料外洩防護原則概觀](data-loss-prevention-policies.md)
    
- [從範本建立 DLP 原則](create-a-dlp-policy-from-a-template.md)
    
- [傳送通知並顯示 DLP 原則的原則秘訣](use-notifications-and-policy-tips.md)
    
- [DLP 原則範本包含哪些內容](what-the-dlp-policy-templates-include.md)
    
- [敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)
