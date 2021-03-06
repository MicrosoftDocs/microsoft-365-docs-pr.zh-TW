---
title: 管理稽核記錄保留原則
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 稽核記錄保留原則是 Microsoft 365 中新增的「進階稽核」功能的一部分。 稽核記錄保留原則可讓您指定要在組織中保留稽核記錄的時間長度。
ms.openlocfilehash: 8df2e240440ad33ac82d926b63cc495d1aaef692
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925148"
---
# <a name="manage-audit-log-retention-policies"></a>管理稽核記錄保留原則

您可以在安全性與合規性中心中建立及管理稽核記錄保留原則。 稽核記錄保留原則是 Microsoft 365 中新增的「進階稽核」功能的一部分。 稽核記錄保留原則可讓您指定要在組織中保留稽核記錄的時間長度。 您最多可以保留稽核記錄達 10 年的時間。 您可以根據下列準則來建立原則：

- 一或多個 Microsoft 365 服務中的所有活動
- 所有使用者或特定使用者執行的特定活動 (Microsoft 365 服務中)
- 優先順序層級，指定若您在組織中有多個原則，要優先處理的原則

## <a name="default-audit-log-retention-policy"></a>預設稽核記錄保留原則

Microsoft 365 中的「進階稽核」可為所有組織提供預設的稽核記錄保留原則。 此原則會將所有 Exchange Online、SharePoint Online、商務用 OneDrive 和 Azure Active Directory 稽核記錄保留一年。 此預設原則會保留包含 **Workload** 屬性 (此即活動發生所在的服務) 的 **Exchange**、**SharePoint**、**OneDrive**、**AzureActiveDirectory** 值的稽核記錄。 您無法修改預設原則。 如需預設原則中所包含每個工作負載的記錄類型的清單，請參閱本文的[詳細資訊](#more-information)一節。

> [!NOTE]
> 預設的稽核記錄保留原則僅適用獲指派 Office 365 或 Microsoft 365 E5 授權或擁有 Microsoft 365 E5 合規性或 E5 電子文件探索和稽核附加元件授權的使用者所執行活動的稽核記錄。 如果組織中有非 E5 使用者或來賓使用者，其對應的稽核記錄會保留 90 天。

## <a name="before-you-create-an-audit-log-retention-policy"></a>在建立稽核記錄保留原則之前

- 您必須獲指派安全性與合規性中心中的「組織組態」角色，以才能建立或修改稽核保留原則。

- 您可以在組織中有最多 50 個稽核記錄保留原則。

- 若要保留稽核記錄超過 90 天 (最多 1 年)，產生稽核記錄 (透過執行稽核活動) 的使用者必須獲指派 Office 365 E5 或 Microsoft 365 E5 授權，或擁有 365 Microsoft E5 合規性或 E5 電子文件探索與稽核附加元件授權。 若要保留稽核記錄 10 年，除了 E5 授權之外，還必須指派 10 年的稽核記錄保留附加元件授權給產生稽核記錄的使用者。

- 所有自訂稽核記錄保留原則 (由您的組織建立) 會優先於預設保留原則。例如，如果您為具有的保留期間少於一年的 Exchange 信箱活動建立稽核記錄保留原則，則 Exchange 信箱活動的稽核記錄將會保留較自訂原則所指定更短的持續時間。

## <a name="create-an-audit-log-retention-policy"></a>建立稽核記錄保留原則

1. 移至 <https://compliance.microsoft.com>，並使用獲指派安全性與合規性中心的權限頁面中的「組織組態」角色的使用者帳戶登入。

2. 在 Microsoft 365 合規性中心的左窗格中，按一下 [顯示全部 **]**，然後按一下 [稽核 **]**。

3. 按一下 **[稽核保留原則]** 索引標籤。

4. 按一下 **[建立稽核保留原則]**，然後在飛出視窗頁面中填寫下列欄位：

   ![新的稽核保留原則飛出視窗頁面](../media/CreateAuditLogRetentionPolicy.png)

   1. **原則名稱：** 稽核記錄保留原則的名稱。 這個名稱需為貴組織中的唯一名稱，而且在建立原則之後即無法變更。

   2. **描述：** 選用，但對於提供原則相關資訊 (例如記錄類型或工作負載)、原則中指定的使用者和持續時間有幫助。

   3. **使用者：** 選取一或多個要套用原則的使用者。 如果將此方塊保留空白，則原則會套用至所有使用者。 如果將 [記錄類型 **]** 保留空白，則必須選取使用者。

   4. **記錄類型：** 原則適用的稽核記錄類型。 如果將此屬性保留空白，則必須在 [使用者 **]** 方塊中選取使用者。 您可以選取單一記錄類型或多個記錄類型：
      - 如果您選取單一記錄類型，則會動態顯示 [活動 **]** 欄位。 您可以使用下拉式清單從選取的記錄類型中選取活動，以便套用原則。 如果您未選擇特定活動，則原則會套用至所選記錄類型的所有活動。
      - 如果您選取多個記錄類型，就無法選取活動。 原則會套用至所選記錄類型的所有活動。

   5. **持續時間：** 保留符合原則準則之稽核記錄的時間量。

   6. **優先順序：** 此值會決定組織中稽核記錄保留原則的處理順序。 較低的值表示優先順序較高。 有效的優先順序是介於 **1** 到 **10000** 之間的數值。 值為 **1** 代表最高優先順序，而值為 **10000** 代表最低優先順序。 例如，值為 **5** 的原則優先於值為 **10** 的原則。 如先前所述，任何自訂稽核記錄保留原則的優先順序都會高於組織的預設原則。

5. 按一下 [儲存] 建立新的稽核記錄保留原則。

新原則會顯示在 **[稽核保留原則]** 索引標籤的清單中。

## <a name="manage-audit-log-retention-policies-in-the-microsoft-365-compliance-center"></a>在 Microsoft 365 合規性中心管理稽核記錄保留原則

稽核記錄保留原則列在 **[稽核保留原則]** 索引標籤中 (又稱為 *[儀表板]*) 您可以使用儀表板來查看、編輯及刪除稽核保留原則。

### <a name="view-policies-in-the-dashboard"></a>在儀表板中查看原則

稽核記錄保留原則列在儀表板中。 在儀表板中查看原則的優點之一，就是您可以按一下 **[先順序]** 欄，以按照套用的優先順序列出原則。 如先前所述，較高的值表示優先順序較高。

![[稽核保留原則] 儀表板中的 [優先順序] 欄](../media/AuditLogRetentionDashboardPriority.png)

您也可以選取要在彈出式頁面上顯示其設定的原則。

> [!NOTE]
> 儀表板中不會顯示貴組織的預設稽核記錄保留原則。

### <a name="edit-policies-in-the-dashboard"></a>在儀表板中編輯原則

若要編輯原則，請選取該原則以顯示彈出式頁面。 您可以修改一個或多個設定，然後儲存變更。

> [!IMPORTANT]
>
> 若使用 **New UnifiedAuditLogRetentionPolicy** Cmdlet，則可以為儀表版中的 **[建立稽核保留原則]** 工具中不可用的記錄類型或活動建立稽核記錄保留原則。 在這種情況下，您將無法從儀表板中的 **[稽核保留原則]** 中編輯原則 (例如，變更保留期或新增和移除活動)。 您只能在 [合規性中心] 中檢視及刪除原則。 若要編輯策略，必須在安全性與合規性中心 PowerShell 中使用[Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet。>
>
> **提示：** 彈出式頁面頂端會顯示一則訊息，指出必須使用 PowerShell 編輯的原則。

### <a name="delete-policies-in-the-dashboard"></a>在儀表板中刪除原則

若要刪除原則，請按一下 **[刪除]** ![[刪除圖示]](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)圖示，然後確認想要刪除原則。 該原則會從儀表板中移除，但您可能需要長達 30 分鐘的時間，該原則才會從貴組織中移除。

## <a name="create-and-manage-audit-log-retention-policies-in-powershell"></a>在 PowerShell 中建立並管理稽核記錄保留原則

您也可以使用安全性與合規性中心 PowerShell 來建立並管理稽核記錄保留原則。 使用 PowerShell 的一個原因是，您可以為無法在 UI 中使用的記錄類型或活動建立原則。

### <a name="create-an-audit-log-retention-policy-in-powershell"></a>在 PowerShell 中建立稽核記錄保留原則

請依照以下步驟，在 PowerShell 中建立稽核記錄保留原則：

1. [連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

2. 執行下列命令以建立稽核記錄保留原則:

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TenYears -Priority 100
   ```

   此範例會建立名為「Microsoft Teams 稽核原則」的稽核記錄保留原則，其中具有這些設定：

   - 原則的描述。
   - 保留所有 Microsoft Teams 活動 (如 *RecordType* 參數所定義)。
   - 保留 Microsoft Teams 稽核記錄 10 年。
   - 優先順序為 100。

以下是建立稽核記錄保留原則的另一個範例。 此原則會保留使用者 admin@contoso.onmicrosoft.com 的「使用者已登入」活動稽核記錄六個月。

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

如需詳細資訊，請參閱 [New-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/new-unifiedauditlogretentionpolicy)。

### <a name="view-policies-in-powershell"></a>在 PowerShell 中查看原則

在安全性與合規性中心 PowerShell 中使用 [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) Cmdlet 來檢視稽核記錄保留原則。

以下的範例命令可用來顯示組織中所有的稽核記錄保留原則設定。 此命令會將原則的優先順序從最高到最低排序。

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> **Get-UnifiedAuditLogRetentionPolicy** Cmdlet 不會傳回組織的預設稽核記錄保留原則。

### <a name="edit-policies-in-powershell"></a>在 PowerShell 中編輯原則

在安全性與合規性中心 PowerShell 中使用 [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) Cmdlet 來編輯現有的稽核記錄保留原則。

### <a name="delete-policies-in-powershell"></a>在 PowerShell 中刪除原則

在安全性與合規性中心 PowerShell 中使用 [Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) Cmdlet 來刪除稽核記錄保留原則。 從貴組織中移除原則可能需要多達 30 分鐘的時間。

## <a name="more-information"></a>其他資訊

如先前所述，根據預設，Azure Active Directory、Exchange、SharePoint Online 和商務用 OneDrive 中的作業稽核記錄會保留一年。 下表列出預設稽核記錄保留原則中(針對各項服務)所包含的所有記錄類型。 這表示具有此記錄類型的稽核記錄將保留一年，除非特定記錄類型、作業或使用者的自訂稽核記錄保留原則具有優先順序。 每種記錄類型的 Enum 值 (在稽核記錄中顯示為 RecordType 屬性的值) 會顯示在括弧中。

<br>

****

|AzureActiveDirectory|Exchange |SharePoint 或 OneDrive|
|---|---|---|
|AzureActiveDirectory (8)|ExchangeAdmin (1)|ComplianceDLPSharePoint (11)|
|AzureActiveDirectoryAccountLogon (9)|ExchangeItem (2)|ComplianceDLPSharePointClassification (33)|
|AzureActiveDirectoryStsLogon (15)|行銷活動 (62)|Project (35)|
||ComplianceDLPExchange (13)|SharePoint (4)|
||ComplianceSupervisionExchange (68)|SharePointCommentOperation (37)|
||CustomerKeyServiceEncryption (69)|SharePointContentTypeOperation (55)|
||ExchangeAggregatedOperation (19)|SharePointFieldOperation (56)|
||ExchangeItemAggregated (50)|SharePointFileOperation (6)|
||ExchangeItemGroup (3)|SharePointListOperation (36)|
||InformationBarrierPolicyApplication (53)|SharePointSharingOperation (14)|
||||
