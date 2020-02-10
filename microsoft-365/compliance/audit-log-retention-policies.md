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
ms.openlocfilehash: 00e3ba527ee72fced0d264457375210e138b006e
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862386"
---
# <a name="manage-audit-log-retention-policies"></a>管理稽核記錄保留原則

您可以在安全性與合規性中心中建立及管理稽核記錄保留原則。 稽核記錄保留原則是 Microsoft 365 中新增的「進階稽核」功能的一部分。 稽核記錄保留原則可讓您指定要在組織中保留稽核記錄的時間長度。 您最多可以保留稽核記錄達一年的時間。 您可以根據下列準則來建立原則：

- 一或多個 Microsoft 365 服務中的所有活動

- 所有使用者或特定使用者執行的特定活動 (特定服務中)

- 優先順序層級，指定若您在組織中有多個原則，要優先處理的原則

## <a name="default-audit-log-retention-policy"></a>預設稽核記錄保留原則

Microsoft 365 中的「進階稽核」可為所有組織提供預設的稽核記錄保留原則。 此原則會保留所有 Exchange、SharePoint 和 Azure Active Directory 稽核記錄一年。 此預設原則會保留包含 **Workload** 屬性 (這是發生活動所在的服務) 的 **AzureActiveDirectory**、**Exchange**或 **SharePoint** 值的稽核記錄。 您無法修改預設原則。 如需預設原則中所包含每個工作負載的記錄類型的清單，請參閱本文的[詳細資訊](#more-information)一節。

> [!NOTE]
> 預設的稽核記錄保留原則僅適用獲指派 Office 365 或 Microsoft 365 E5 授權或擁有 Microsoft 365 E5 合規性附加元件授權的使用者所執行活動的稽核記錄。 如果組織中有非 E5 使用者，其對應的稽核記錄則會保留 90 天。

## <a name="before-you-begin"></a>開始之前

- 您必須獲指派安全性與合規性中心中的「組織組態」角色，以才能建立或修改稽核保留原則。

- 您可以在組織中有最多 50 個稽核記錄保留原則。

- 若要保留稽核記錄超過 90 天，產生稽核記錄的使用者必須獲指派 Office 365 或 Microsoft 365 E5 授權，或擁有 365 Microsoft E5 合規性附加元件授權。

- 所有自訂稽核記錄保留原則 (由您的組織建立) 會優先於預設保留原則。 例如，如果您為具有的保留期間少於一年的建Exchange 信箱活動立稽核記錄保留原則，則 Exchange 信箱活動的稽核記錄將會保留較自訂原則所指定更短的持續時間。

## <a name="create-an-audit-log-retention-policy-in-the-security--compliance-center"></a>在安全性與合規性中心中建立稽核記錄保留原則

1. 移至 [https://protection.office.com](https://protection.office.com)，並使用獲指派安全性與合規性中心中的「組織組態」角色的使用者帳戶登入。 

2. 在安全性與合規性中心的左窗格中，按一下 [搜尋]****  >  [稽核記錄搜尋]****。

    [稽核記錄搜尋]**** 頁面隨即顯示。

    ![稽核記錄搜尋頁面](media/AuditLogRetentionPolicy1.png)

3. 按一下 [新增保留原則]****，然後在飛出視窗中填寫下列欄位：

    ![稽核記錄保留原則飛出視窗頁面](media/AuditLogRetentionPolicy2.png)

   a. **名稱：** 稽核記錄保留原則的名稱。 此名稱在組織中必須是唯一的。
   
   b. **描述：** 選用，但對於提供原則相關資訊 (例如記錄類型或工作負載)、原則中指定的使用者和持續時間有幫助。

   c. **記錄類型：** 原則適用的稽核記錄類型。 如果選取多個記錄類型，則無法選取活動，因為原則會套用至所選記錄類型的所有活動。 此外，如果將此屬性保留空白，您必須在 [使用者]**** 方塊中選取使用者。

   d. **活動：** 使用此方塊，從您選取的記錄類型中選擇活動。 您可以選擇要套用原則的特定活動。 如果您未選擇特定活動，則原則會套用至所選記錄類型的所有活動。

   e. **使用者：** 選取一或多個要套用原則的使用者。 如果將此方塊保留空白，則原則會套用至所有使用者。 如果將 [記錄類型]**** 保留空白，則必須選取使用者。

   f. **持續時間：** 保留符合原則準則之稽核記錄的時間量。

   g. **優先順序：** 此值會決定組織中稽核記錄保留原則的處理順序。 較高的值表示優先順序較高。 例如，優先順序值為 **5** 的原則會優先於優先順序值為 **0** 的原則。 如先前所述，任何自訂稽核記錄保留原則的優先順序都會高於組織的預設原則。

6. 按一下 [儲存]**** 建立新的稽核記錄保留原則。 

此時並不表示保留原則已成功建立。 請參閱下一節，了解如何檢視稽核記錄保留原則的內容。

## <a name="create-an-audit-log-retention-policy-in-powershell"></a>在 PowerShell 中建立稽核記錄保留原則

您也可以使用 Office 365 安全性與合規性中心 PowerShell 來建立稽核記錄保留原則。 

1. [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

2. 執行下列命令以建立稽核記錄保留原則。 

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TwelveMonths -Priority 100
   ```
    
    此範例會建立名為「Microsoft Teams 稽核原則」的稽核記錄保留原則，其中具有這些設定：

   - 原則的描述。

   - 保留所有 Microsoft Teams 活動 (如 *RecordType* 參數所定義)。

   - 保留 Microsoft Teams 稽核記錄一年。

   - 優先順序為 100。

以下是建立稽核記錄保留原則的另一個範例。 此原則會保留使用者 admin@contoso.onmicrosoft.com 的「使用者已登入」活動稽核記錄六個月。

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

如需詳細資訊，請參閱 [New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-unifiedauditlogretentionpolicy)。

## <a name="view-audit-log-retention-policies"></a>檢視稽核記錄保留原則

此時，要檢視自訂稽核記錄保留原則的唯一方法，就是在安全性與合規性中心 PowerShell 中使用 **Get-UnifiedAuditRetentionPolicy** Cmdlet。 以下的範例命令可用來顯示組織中稽核記錄保留原則設定 (您在上一個步驟中所設定)。 此命令會將原則的優先順序從最高到最低排序。

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> 此時，**Get-UnifiedAuditLogRetentionPolicy** Cmdlet 不會傳回組織的預設稽核記錄原則。

如需詳細資訊，請參閱 [Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-unifiedauditlogretentionpolicy)。

## <a name="more-information"></a>詳細資訊

- 在安全性與合規性中心 PowerShell 中使用 **Set-UnifiedAuditLogRetentionPolicy** Cmdlet 來修改現有的稽核記錄保留原則。 如需詳細資訊，請參閱 [Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/set-unifiedauditlogretentionpolicy)。

- 在安全性與合規性中心 PowerShell 中使用 **Remove-UnifiedAuditLogRetentionPolicy** Cmdlet 來刪除稽核記錄保留原則。 完全移除原則最多可能需要最多 30 分鐘的時間。 如需詳細資訊，請參閱 [Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/remove-unifiedauditlogretentionpolicy)。

- 如先前所述，Azure Active Directory、Exchange 和 SharePoint 中的作業稽核記錄會保留一年。 下表列出預設稽核記錄保留原則中包含的所有記錄類型 (針對各項服務)。 這表示具有此記錄類型的稽核記錄將保留一年，除非特定記錄類型、作業或使用者的自訂稽核記錄保留原則具有優先順序。 每種記錄類型的 Enum 值 (在稽核記錄中顯示為 RecordType 屬性的值) 會顯示在括弧中。

   |AzureActiveDirectory |Exchange  |SharePoint|
   |:---------|:---------|:---------|
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
