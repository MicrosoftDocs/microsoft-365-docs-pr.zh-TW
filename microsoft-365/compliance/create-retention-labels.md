---
title: 建立、發佈和自動套用保留標籤
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 建立、發佈及自動套用保留標籤，以在您的 Office 365 環境中保留您需要的內容、刪除您不想要的項目，以及將項目宣告為記錄的相關指示。
ms.openlocfilehash: 1b34833c8320e5d27029474a4da9f0534a63dc51
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262384"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a>建立、發佈和自動套用保留標籤

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

使用下列資訊來協助您建立[保留標籤](labels.md)，然後將標籤自動套用至文件和電子郵件，或發佈標籤，使得使用者可以手動套用標籤。

保留標籤可協助您保留所需的內容，並刪除您不需要的內容。 它們也可以用來將項目宣告為記錄，做為 Microsoft 365 資料的[記錄管理](records-management.md)解決方案的一部分。

您建立及設定保留標籤的位置，取決於您是否使用記錄管理。 以下提供這兩個案例的指示。

## <a name="before-you-begin"></a>開始之前

您的合規性小組中負責建立保留標籤的成員必須具備安全性 &amp; 合規性中心的權限。 根據預設，租用戶系統管理員將可存取此位置，並且可直接讓法務人員與其他人存取安全性 &amp; 合規性中心，而不需要為其提供租用戶系統管理員的所有權限。若要這麼做，我們建議您：移至安全性 &amp; 合規性中心的 [權限]**** 頁面，編輯 [合規性系統管理員]**** 角色群組，將該成員新增到此角色群組。 
  
如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性與合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。
  
需要這些權限才能建立及套用保留標籤和標籤原則。原則強制執行不需要內容的存取權。

## <a name="create-and-configure-retention-labels"></a>建立及設定保留標籤

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：
    
    - 如果您使用記錄管理：
        - [解決方案]****  >  [記錄管理]****  >  [檔案計劃]**** 索引標籤 > [+ 建立標籤]****  >  [保留標籤]****
        
    - 如果您未使用記錄管理：
       - [解決方案]****  >  [資訊控管]****  >  [標籤]**** 索引標籤 > [+ 建立標籤]****
    
    沒有立即看到您的選項？ 先選取 [顯示全部]****。 

2. 遵循精靈中的提示進行。 如果您使用記錄管理：
    
    - 如需有關檔案計劃描述元的資訊，請參閱[檔案計劃管理員的概觀](file-plan-manager.md)
    
    - 若要使用保留標籤將內容宣告為記錄，請啟用 [使用標籤以將內容分類為「記錄」]**** 核取方塊。

3. 重複這些步驟以建立更多標籤。

若要編輯現有的標籤，請將其選取，然後選取 [編輯標籤]****。 這會啟動相同的精靈，讓您變更步驟 2 中的標籤描述和設定。

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a>建立保留標籤原則來發佈保留標籤

發佈保留標籤，讓使用者可以手動套用這些標籤。

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：
    
    - 如果您使用記錄管理：
        - [解決方案]****  >  [記錄管理]**** > [標籤原則]**** 索引標籤 > [發佈標籤]****
    
    - 如果您未使用記錄管理：
        - [解決方案]****  >  [資訊控管]****  >  [標籤原則]**** 索引標籤 > [發佈標籤]****
    
    沒有立即看到您的選項？ 先選取 [顯示全部]****。 

2. 遵循精靈中的提示進行。
    
    如需設定位置的相關資訊，請參閱此頁面上的[保留標籤和位置](#retention-labels-and-locations)一節。 

## <a name="auto-apply-a-retention-label"></a>自動套用保留標籤

根據您指定的條件自動套用保留標籤。

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：
    
    - 如果您使用記錄管理：**資訊控管**：
        - [解決方案]****  >  [記錄管理]****  >  [標籤原則]**** 索引標籤 > [自動套用標籤]****
    
    - 如果您未使用記錄管理：
        - [解決方案]****  >  [資訊控管]****  >  [標籤原則]**** 索引標籤 > [自動套用標籤]****
    
    沒有立即看到您的選項？ 先選取 [顯示全部]****。 

2. 遵循精靈中的提示進行。
    
    如需有關設定會自動套用保留標籤之條件的詳細資訊，請參閱此頁面上的[設定自動套用保留標籤的條件](#configuring-conditions-for-auto-apply-retention-labels)一節。
    
    如需設定位置的相關資訊，請參閱此頁面上的下一節，[保留標籤和位置](#retention-labels-and-locations)。

## <a name="retention-labels-and-locations"></a>保留標籤和位置

可以將不同類型的保留標籤發佈到不同的位置，視保留標籤的功能而定。
  
|**如果保留標籤是...**|**則標籤原則可套用至...**|
|:-----|:-----|
|發佈給使用者  <br/> |Exchange、SharePoint、OneDrive、Office 365 群組  <br/> |
|根據敏感資訊類型而自動套用  <br/> |Exchange (僅限所有信箱)、SharePoint、OneDrive  <br/> |
|根據查詢而自動套用  <br/> |Exchange、SharePoint、OneDrive、Office 365 群組  <br/> |
   
在 Exchange 中，您只能在新傳送的郵件 (傳輸中的資料) 上自動套用保留標籤功能 (適用於查詢和敏感性資訊類型)，而非目前在信箱中的所有郵件 (待用資料)。 此外，您只能在所有信箱中為敏感性資訊類型自動套用保留標籤功能，但無法選取特定信箱。
  
Exchange 公用資料夾和 Skype 不支援保留標籤。


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a>設定自動套用保留標籤的條件

您可以在內容包含以下資訊時，自動將保留標籤套用到內容：
  
- [特定敏感資訊類型](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [符合您所建立查詢的特定關鍵字](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [可訓練分類器的符合項目](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![自動套用標籤的選擇條件頁面](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

將自動套用保留標籤套用到符合您設定之條件的所有內容，最多可能需要 7 天的時間。

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>自動將標籤套用至包含特定類型敏感資訊的內容

當您為敏感性資訊建立自動套用保留標籤時，系統會顯示與建立資料外洩防護 (DLP) 原則時相同的原則範本清單。 每個原則範本預設會尋找特定類型的敏感性資訊。 例如本文顯示的範本會尋找美國 ITIN、SSN 和護照號碼。 若要深入了解 DLP，請參閱[資料外洩防護原則概觀](data-loss-prevention-policies.md)。
  
![敏感資訊類型的原則範本](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
選取原則範本後，可以新增或移除任何類型的敏感資訊，且可以變更例項計數和比對精確度。此處所示的範例中，只有符合以下條件時，才會自動套用保留標籤：
  
- 內容包含 1 到 9 個下列三種敏感資訊類型。您可以刪除 **max ** (上限) 值，條件就會變成 **any** (任何)。
    
- 偵測到的敏感資訊類型的比對精確度 (或信賴等級) 下限為 75。許多敏感資訊類型會定義多個模式，模式的比對精確度愈高，便需要尋找愈多證據 (例如關鍵字、日期、地址)，而較低比對精確度的模式則需要較少的證據。簡單來說，比對精確度的 **min** (下限) 愈低，就越容易找到與條件相符的內容。 
    
如需這些選項的詳細資訊，請參閱[調整規則，讓規則更容易或更難相符](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。
    
![用於識別機密資訊類型的選項](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>自動將標籤套用至包含關鍵字或可搜尋屬性的內容

您可以自動將標籤套用至符合特定條件的內容。現在可用的條件支援將標籤套用至包含特定字詞、片語或可搜尋屬性的值。您可以使用 AND、OR、NOT 等搜尋運算子來精簡查詢。

如需查詢語法的詳細資訊，請參閱：

- [關鍵字查詢語言 (KQL) 語法參考](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

查詢式標籤使用搜尋索引來識別內容。如需有效可搜尋屬性的詳細資訊，請參閱：

- [內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
- [SharePoint 伺服器中的編目及受控屬性概觀](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

範例查詢：

- Exchange
    - subject:"Quarterly Financials"
    - recipients:garthf<!--nolink-->@contoso.com
- SharePoint 和 OneDrive
    - contenttype:contract
    - site:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract

![查詢編輯器](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>使用可訓練分類器自動將標籤套用至內容

選擇用於可訓練分類器的選項時，可以選取其中一個內建分類器或自訂分類器。 內建分類器包括 [履歷]****、[原始程式碼]****、[針對性騷擾]****、[粗話]**** 和 [威脅]****：

![選擇可訓練分類器](../media/retention-label-classifers.png)

若要使用此選項自動套用標籤，SharePoint Online 網站和信箱必須有至少 10 MB 的資料。

如需有關可訓練分類器的詳細資訊，請參閱[開始使用可訓練分類器 (預覽)](classifier-getting-started-with.md)。

如需組態範例，請參閱[如何準備及使用內建分類器](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)。

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>保留標籤要多久才會生效

當您發佈或自動套用保留標籤時，標籤不會立即生效：
  
1. 首先，標籤原則必須先將系統管理中心與原則中的位置同步。
    
2. 接著，位置可能會需要一些時間，將已發佈的保留標籤提供給使用者，或是將標籤自動套用到內容。 實際所需的時間取決於保留標籤的位置和類型。
    
### <a name="published-retention-labels"></a>已發佈的保留標籤

如果您將保留標籤發佈到 SharePoint 或 OneDrive，需要一天的時間讓這些保留標籤向使用者顯示。此外，如果您將保留標籤發佈到 Exchange，可能需要 7 天來向使用者顯示這些保留標籤，且信箱至少必須包含 10 MB 的資料。
  
![手動標籤生效的圖](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a>自動套用保留標籤

如果您將保留標籤自動套用至符合特定條件的內容，保留標籤套用至符合條件的所有現有內容可能需要 7 天。
  
![自動標籤生效時的圖表](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>如何檢查發佈至 Exchange 之保留標籤的狀態

在 Exchange Online 中，是透過每 7 天執行一次的程序，將保留標籤提供給使用者。您可以使用 Powershell 查看此程序上次執行的時間，依此判斷下一次執行時間。
  
1. [連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773)。
    
2. 執行下列命令。
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

結果：`ELCLastSuccessTimeStamp` (UTC) 屬性會顯示系統上次處理您信箱的時間。 如果系統在您建立原則後都還未處理信箱，標籤就無法顯示。 若要強制處理信箱，請執行 `Start-ManagedFolderAssistant -Identity <user>`。
    
如果標籤沒有出現在 Outlook 網頁版中，而您認為應該要出現，請務必清除瀏覽器中的快取 (CTRL + F5)。
    

## <a name="updating-retention-labels-and-their-policies"></a>更新保留標籤及其原則

如果您編輯保留標籤、保留標籤原則或自動套用原則，且保留標籤已套用至內容，除了新標示的內容以外，您更新的設定會自動套用到此內容。

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a>尋找保留標籤的 PowerShell Cmdlet

若要使用保留標籤 Cmdlet：
  
1. [連接到 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. 使用這些 Office 365 安全性與合規性中心 Cmdlet：
    
    - [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetag)
    
    - [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-compliancetag)
    
    - [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-compliancetag)
    
    - [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-compliancetag)
    
    - [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/enable-compliancetagstorage)
    
    - [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetagstorage)
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)
