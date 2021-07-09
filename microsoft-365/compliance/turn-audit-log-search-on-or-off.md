---
title: 開啟或關閉稽核
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: 如何在 Microsoft 365 合規性中心中開啟或關閉「審核記錄搜尋」功能，以啟用或停用系統管理員搜尋審核記錄的能力。
ms.openlocfilehash: dd39b883036ce6060aef71c6a927c03f391d827f
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341493"
---
# <a name="turn-auditing-on-or-off"></a>開啟或關閉稽核

使用 Microsoft 365 和 Office 365 企業版的組織，預設會開啟 [稽核記錄]。 當 Microsoft 365 合規性中心中的審計開啟時，您組織中的使用者和系統管理員活動會記錄在審核記錄中，並在90天內保留，視指派給使用者的授權而定到一年。 不過，您的組織可能會有不想要記錄和保留審核記錄資料的原因。 在這種情況下，全域管理員可能會決定在 Microsoft 365 中關閉審核。

當您設定新的 Microsoft 365 或 Office 365 組織時，您可以確認組織的審核狀態。 如需相關指示，請參閱本文中的 [驗證您的組織的審計狀態](#verify-the-auditing-status-for-your-organization) 一節。

> [!IMPORTANT]
> 如果您在 Microsoft 365 中關閉審核，您就無法使用 Office 365 管理活動 API 或 Azure Sentinel 來存取組織的審計資料。 遵循本文中的步驟關閉審計，表示當您使用 Microsoft 365 合規性中心搜尋審計記錄檔時，或在 Exchange Online PowerShell 中執行 **Search-UnifiedAuditLog** Cmdlet 時，不會傳回任何結果。 這也表示無法透過 Office 365 管理活動 API 或 Azure Sentinel 使用審核記錄。
  
## <a name="before-you-turn-auditing-on-or-off"></a>開啟或關閉審計之前

- 您必須在 Exchange Online 中指派「審計記錄」角色，才能在 Microsoft 365 組織中開啟或關閉審計。 根據預設，此角色會指派給 Exchange 系統管理中心的 [**許可權**] 頁面上的 [規範管理] 和 [組織管理] 角色群組。 Microsoft 365 中的全域系統管理員是 Exchange Online 中的「組織管理」角色群組的成員。

    > [!NOTE]
    > 在 Exchange Online 開啟或關閉審核時，必須將許可權指派給使用者。 如果您在 Microsoft 365 合規性中心中的 [**許可權**] 頁面上指派「審核記錄」角色，使用者將無法開啟或關閉審計。 這是因為基準 Cmdlet 是 Exchange Online PowerShell Cmdlet。

- 如需搜尋審核記錄的逐步指示，請參閱 [搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。 如需 Microsoft 365 管理活動 API 的詳細資訊，請參閱[開始使用 Microsoft 365 管理 APIs](/office/office-365-management-api/get-started-with-office-365-management-apis)。

## <a name="verify-the-auditing-status-for-your-organization"></a>驗證組織的審計狀態

若要確認已開啟組織的審計，您可以在[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中執行下列命令：

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

`True` _UnifiedAuditLogIngestionEnabled_ 屬性的值表示已開啟審計。 值 `False` 表示未開啟審計。

## <a name="turn-on-auditing"></a>開啟審計

如果您的組織未開啟審核，您可以在 Microsoft 365 合規性中心中或使用 Exchange Online PowerShell 將其開啟。 在您開啟審核後，可能需要數小時的時間，才能在搜尋審核記錄檔時傳回結果。
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>使用規範中心來開啟審計

1. 移至 <https://compliance.microsoft.com> 並登入。

2. 在 Microsoft 365 合規性中心的左導覽窗格中，按一下 [**審計**]。

   如果您的組織未開啟審核，就會顯示橫幅，提示您開始錄製使用者和系統管理員活動。

   ![在審核頁面上的橫幅](../media/AuditingBanner.png)

3. 按一下 [ **開始錄製使用者和系統管理員] 活動** 橫幅。

   可能需要長達60分鐘，變更才會生效。

### <a name="use-powershell-to-turn-on-auditing"></a>使用 PowerShell 開啟審計

1. [連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 執行下列 PowerShell 命令以開啟審計。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    隨即顯示一則訊息，指出可能需要長達60分鐘的時間，變更才會生效。
  
## <a name="turn-off-auditing"></a>關閉審計

您必須使用 Exchange Online PowerShell 關閉審核。
  
1. [連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 執行下列 PowerShell 命令以關閉審計。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 經過一段時間後，請確認已停用 (停用) 的審計功能。 執行這項作業的方法有兩種：

    - 在 Exchange Online PowerShell 中，執行下列命令：

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      `False` _UnifiedAuditLogIngestionEnabled_ 屬性的值表示已關閉的審計功能。

    - 移至 Microsoft 365 合規性中心中的 [**審計**] 頁面。

      如果您的組織未開啟審核，就會顯示橫幅，提示您開始錄製使用者和系統管理員活動。
