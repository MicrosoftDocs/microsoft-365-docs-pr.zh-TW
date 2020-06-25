---
title: 建立及設定保留原則以自動保留或刪除內容
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
description: 透過保留原則，您可以主動決定要保留內容、刪除內容，還是兩者 (保留然後刪除內容)；將單一原則套用到整個組織或套用到特定位置或使用者；以及將原則套用到所有內容或套用到符合特定條件的內容。
ms.openlocfilehash: 12b0c15186a27a1583403214a657367c1dd3b1a9
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844749"
---
# <a name="create-and-configure-retention-policies"></a>建立及設定保留原則

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

使用保留原則主動決定是否要保留內容、刪除內容，還是兩者，即保留然後刪除內容。 

如需保留原則運作方式的相關資訊，請參閱[了解保留原則](retention-policies.md)。

## <a name="before-you-begin"></a>開始之前

您的合規性團隊中負責建立和管理保留原則的成員，必須具備 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)的權限。 根據預設，租用戶系統管理員 (全域系統管理員) 能夠存取此位置，並可讓法務人員和其他人員存取，而不需要為其提供租用戶系統管理員的所有權限。若要授與此受限制的系統管理權限，建議您將使用者新增至 [合規性系統管理員]**** 系統管理員角色群組。 如需相關指示，請參閱[讓使用者能夠存取安全性與合規性中心的權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。

需要這些權限才能建立及套用保留原則。 設定保留原則的人員不需要存取內容。

## <a name="create-and-configure-a-retention-policy"></a>建立及設定保留原則

1. 從 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 [原則]****  >  [保留]****。

2. 選取 [新增保留原則]**** 或編輯現有的保留原則。

3. 針對 [設定]****，先指定保留及刪除內容的設定選項。 您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。 如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定](#settings-for-retaining-and-deleting-content)：
    
    然後決定應該將保留原則套用至所有內容，或套用至符合特定條件的內容。 如需有關這些進階保留設定的詳細資訊，請參閱此頁面上的[用來識別符合特定條件內容的進階設定](#advanced-settings-to-identify-content-that-meets-specific-conditions)。 

4. 針對 [選擇位置]**** 頁面，選取保留原則是否應套用至組織中所有支援的位置，或您想要指定位置。 如果您選擇特定位置，則也可以指定包含和排除。 
    
    若為 Microsoft Teams： 
    - 如果您想要刪除或保留 Teams 頻道訊息或Teams 聊天，您必須選取選擇特定位置的選項。 當您選取這些選項的其中一個做為位置時，即會自動排除其他位置，因為包含此 Teams 資料的保留原則不能包含其他位置。 
    - 請注意，針對 **Teams 頻道訊息**，會包含來自標準頻道的訊息，但不會包含[私人頻道](https://docs.microsoft.com/microsoftteams/private-channels)的訊息。 當您選取 [Teams 聊天]**** 位置時，會將來自私人頻道的訊息包含為群組聊天。
    
    如需在組織的保留原則或特定位置之間選擇的詳細資訊，請參閱此頁面上的[將保留原則套用到整個組織或特定位置](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。
    
    如需 **Office 365 群組**和**商務用 Skype**的特定資訊，請參閱下列小節：[Microsoft 365 群組的設定資訊](#configuration-information-for-microsoft-365-groups)和[商務用 Skype 的設定資訊](#configuration-information-for-skype-for-business)。

5. 完成精靈以儲存您的設定。

當您有多個保留原則時，請參閱[系統會優先處理保留原則嗎？](retention-policies.md#the-principles-of-retention-or-what-takes-precedence)

### <a name="configuration-information-for-microsoft-365-groups"></a>Microsoft 365 群組的設定資訊

若要保留或刪除 Microsoft 365 群組 (先前稱為 Office 365 群組) 的內容，請在選擇保留原則的位置時，選取 [Office 365 群組]**** 位置。 即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件**位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。 此外，雖然 **Exchange 電子郵件**位置一開始會允許您指定要包含或排除的群組信箱，但是當您嘗試儲存保留原則時，您會收到 "RemoteGroupMailbox" 不是Exchange 位置的有效選項錯誤訊息。

套用到 Microsoft 365 群組的保留原則同時包含群組信箱和網站。 套用至 Microsoft 365 群組的保留原則可保護由 Microsoft 365 群組所建立的資源，其中包括 Microsoft Teams。

### <a name="configuration-information-for-skype-for-business"></a>商務用 Skype 的設定資訊

不同於 Exchange 電子郵件，您無法將 Skype 位置的狀態切換為開啟以包含所有使用者，但當您開啟該位置時，可以手動選擇您想要保留其交談的使用者：

![為保留原則選擇 Skype 位置](../media/skype-location-retention-policies.png)
  
當您選取 [選擇使用者]**** 時，您可以選取欄標題中的 [名稱]**** 方塊，快速包含所有使用者。 不過，請務必了解，會將每個使用者算成原則中的一個特定包含。 因此，如果您包含超過 1,000 個使用者，則會套用上一節提及的限制。 在這裡選取所有 Skype 使用者，和整個組織的原則能夠根據預設包含所有 Skype 使用者並不一樣。 
  
![選擇 Skype 使用者頁面](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.


## <a name="settings-for-retaining-and-deleting-content"></a>保留和刪除內容的設定

透過在保留原則中選擇用於保留和刪除內容的設定，您的保留原則會具有下列其中一個設定達一段指定的期間：

- 僅保留
- 保留然後刪除
- 僅刪除

### <a name="retaining-content-for-a-specific-period-of-time"></a>將內容保留特定的一段時間

設定保留原則時，您會選擇無限期保留內容，或將內容保留特定數天、數月或數年。 保留內容的持續時間是從內容的存留期起算，而不是從套用保留原則的時間起算。 您可以選擇存留期是否要根據內容建立的時間，或前次修改的時間 (針對 OneDrive 和 SharePoint)。

範例：
  
- SharePoint：如果您在將網站集合中的內容自上次修改起保留七年，而該網站集合中的某文件已有六年未曾修改，如果後續仍未修改該文件，則只會再保留該文件一年。 如果該文件重新編輯，則其存留期將會從新的前次修改日期起算，因而會再保留七年。
  
- Exchange：同樣地，如果您要讓信箱中的內容保留七年，而六年前已傳送過某封郵件，該郵件則只會再保留一年。 若為 Exchange 內容，時限是以收到內送電子郵件的日期，或傳送外寄電子郵件的日期為基礎。 根據前次修改時間保留內容只會套用到 OneDrive 和 SharePoint 中的網站內容。
  
在保留期間結束時，您會選擇是否要永久刪除內容：
  
![保留設定頁面](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a>刪除早於特定存留期的內容

保留原則可以保留然後刪除內容，或刪除舊內容而不保留它。
  
如果您的保留原則刪 內容，請務必了解，文件刪除原則所指定的期限並不是從指派原則的時間算起，而是從建立或修改內容的時間算起。
  
![刪除設定](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
例如，假設您建立一個刪除超過三年時間之內容的保留原則，然後將該原則指派給所有 OneDrive 帳戶，而此帳戶包含許多四或五年前建立的內容。 在此情況下，第一次指派保留原則後，很快地許多內容將會遭到刪除。 基於這個原因，請務必了解，會刪除內容的保留原則會對您的內容造成相當大的影響。 
  
Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content. You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact. Note this warning that appears when you review the settings for your retention policy just before creating it.
  
![有關刪除內容的警告](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a>用來識別符合特定條件內容的進階設定

保留原則可以套用至其包含之位置中的所有內容，或您可以選擇只將保留原則套用到包含特定關鍵字或[特定類型的敏感資訊](what-the-sensitive-information-types-look-for.md)的內容。
  
![進階保留選項](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a>識別包含特定關鍵字的內容

您可以將保留原則套用到僅符合特定條件的內容，然後針對該內容執行保留動作。 可用的條件可支援將保留原則套用至包含特定字詞或詞組的內容。 您可以使用 AND、OR 和 NOT 這類搜尋運算子來精簡您的查詢。 如需有關這些運算子的詳細資訊，請參閱[內容查詢的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。
  
即將推出對新增可搜尋屬性 (例如 **subject:**) 的支援。
  
查詢型保留會使用搜尋索引來識別內容。
  
![查詢編輯器](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a>識別包含敏感性資訊的內容

You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md). For example, you can choose to apply unique retention requirements only to content that contains personally identifiable information (PII) such as taxpayer identification numbers, social security numbers, or passport numbers.
  
![敏感資訊類型頁面](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
附註：
  
- 敏感資訊的進階保留不適用於 Exchange 公用資料夾或商務用 Skype，因為這些位置不支援敏感資訊類型。
    
- Exchange Online 使用郵件流程規則來識別敏感性資訊 (也稱為傳輸規則)，因此這只適用於傳輸過程中的郵件，而不是所有已儲存在信箱中的項目。 對於 Exchange Online，這表示保留原則可識別機密資訊，並只對在原則套用到信箱「之後」**** 收到的郵件執行保留動作。 上一節所述之以查詢為基礎的保留沒有此限制，因為它使用搜尋索引來識別內容。 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>將保留原則套用到整個組織或特定位置

您可以輕鬆地將保留原則套用到整個組織、整個位置，或只套用到特定位置或使用者。
  
### <a name="org-wide-policy"></a>全組織原則

保留原則最強大的功能之一，就是它可套用至 Microsoft 365 中的各個位置，包括：
  
- Exchange 電子郵件
    
- SharePoint 網站集合
    
- OneDrive 帳戶
    
- Microsoft 365 群組 (適用群組信箱和相關聯的 SharePoint 網站中的內容)。
    
- Exchange 公用資料夾
    

![所有位置選項](../media/retention-policies-all-locations.png)

全組織保留原則的其他重要功能包含：
  
- 原則可以包含的信箱或網站數目沒有任何限制。
    
- 對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承此原則。
  
### <a name="a-policy-that-applies-to-entire-locations"></a>套用到整個組織的原則

當您選擇位置時，您可以輕鬆地包含或排除整個位置，例如 Exchange 電子郵件或 OneDrive 帳戶。 若要這麼做，請將該位置的 [狀態]**** 切換到開啟或關閉。 
  
就像整個組織的原則一樣，如果將原則套用到整個組織的任何組合，原則可包含的信箱或網站數量則沒有限制。 

例如，如果原則包含所有 Exchange 電子郵件和所有 SharePoint 網站，無論有多少個網站和信箱都會全部包含。 而對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承原則。

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>具有特定包含或排除的原則

您也可以將保留原則套用至特定使用者、特定 Microsoft 365 群組或特定網站。 若要這麼做，請將該位置的 [狀態]**** 切換到開啟，然後使用連結來包含或排除特定使用者、Microsoft 365 群組或網站。 
  
不過，使用此設定時，如果您的保留原則包含或排除超過 1,000 個特定位置，則會有一些限制：
  
- 保留原則的數目上限：
    - 1000 個信箱
    - 1,000 個 Microsoft 365 群組
    - 1000 個 Teams 私人聊天使用者
    - 100 個網站 (OneDrive 或 SharePoint)

針對一個租用戶支援的原則數目上限：10,000 個。 這些項目包括保留原則、保留標籤原則，以及自動套用保留原則。

如果您的保留原則可能受限於這些限制，請選擇適用於整個位置的設定選項，或使用整個組織的原則。

## <a name="updating-retention-policies"></a>更新保留原則

如果您編輯保留原則，且內容已受限於保留原則中的原始設定，則除了新識別的內容以外，還會將您的更新設定自動套用至此內容。

此更新通常相當快，但可能需要數天的時間。 當您的 Microsoft 365 位置間的原則複寫完成時，您會在 Microsoft 365 合規性中心看到保留原則的狀態從**開啟 (處理中)** 變成**開啟 (成功)**。

## <a name="find-the-powershell-cmdlets-for-retention-policies"></a>尋找保留原則的 PowerShell Cmdlet

若要使用保留原則 Cmdlet：
  
1. [連接到 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. 使用這些 Office 365 安全性與合規性中心 Cmdlet：
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)


## <a name="lock-a-retention-policy-by-using-powershell"></a>使用 PowerShell 鎖定保留原則

如果您需要使用[保留鎖定](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)才能符合法規要求，您必須使用 PowerShell。

1. [連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

2. 執行 `Get-RetentionCompliancePolicy` 來列出您的保留原則清單，並尋找您想要鎖定的原則名稱。
    
    ![PowerShell 中保留原則的清單](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. 若要在保留原則上放置保留鎖定，請執行 `Set-RetentionCompliancePolicy` 時將 `RestrictiveRetention` 參數設為 True。 例如：
    
        Set-RetentionCompliancePolicy -Identity "<Name of Policy>" – RestrictiveRetention $true
    
    ![PowerShell 中的 RestrictiveRetention 參數](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
    執行完該 Cmdlet 之後，請選擇 [全部皆是]****：
    
    ![確認您在 PowerShell 想要鎖定保留原則的提示。](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

保留鎖定現在放置於保留原則上。 如果您執行 `Get-RetentionCompliancePolicy`，`RestrictiveRetention` 參數會設為 true。 例如：

`Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl`

![PowerShell 中顯示所有參數的鎖定原則](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

