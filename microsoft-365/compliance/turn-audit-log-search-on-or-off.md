---
title: 開啟或關閉 Office 365 稽核記錄搜尋
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
description: 您可以在安全性 & 規範中心開啟「審核記錄搜尋」功能。 如果您變更了主意，您可以在任何時候關閉此功能。 當「審核記錄搜尋」關閉時，系統管理員無法在您的組織中搜尋使用者和系統管理員活動的 Office 365 審核記錄。
ms.openlocfilehash: 92a781ddb1fd4f5b41198f31ebff6bba9745d21d
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240212"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>開啟或關閉 Office 365 稽核記錄搜尋

您（或另一個系統管理員）必須先開啟審核記錄，才可開始搜尋 Office 365 審核記錄。 當安全性 & 規範中心開啟審核記錄搜尋時，您組織中的使用者和系統管理員活動會記錄在審核記錄中，並在90天內保留，而且會根據指派給使用者的授權，最多一年。 不過，您的組織可能會有不想要記錄和保留審核記錄資料的原因。 在這種情況下，全域系統管理員可能會決定關閉 Office 365 中的審計。

> [!IMPORTANT]
> 如果您關閉 Office 365 中的「審計記錄搜尋」，您就無法使用 Office 365 管理活動 API 或 Azure Sentinel 來存取您組織的審計資料。 依照本文中的步驟關閉審核記錄搜尋，表示當您使用安全性 & 合規性中心或在 Exchange Online PowerShell 中執行**Search-UnifiedAuditLog** Cmdlet 來搜尋審核記錄時，不會傳回任何結果。 這也表示無法透過 Office 365 管理活動 API 或 Azure Sentinel 使用審核記錄。
  
## <a name="before-you-begin"></a>開始之前

- 您必須在 Exchange Online 中指派「審核記錄」角色，才能在 Office 365 組織中開啟或關閉審核記錄搜尋。 根據預設，此角色會指派給 Exchange 系統管理中心的 [**許可權**] 頁面上的 [規範管理] 和 [組織管理] 角色群組。 Office 365 中的全域系統管理員是 Exchange Online 中「組織管理」角色群組的成員。 
    
    > [!NOTE]
    > 在 Exchange Online 中，必須將許可權指派給使用者，以開啟或關閉審核記錄搜尋。 如果您在安全性 & 合規性中心的 [**許可權**] 頁面上指派「審核記錄」角色，則使用者將無法開啟或關閉審核記錄搜尋。 這是因為基準 Cmdlet 是 Exchange Online Cmdlet。 
    
- 如需搜尋 Office 365 審核記錄的逐步指示，請參閱在[安全性 & 規範中心搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。 如需有關 Office 365 管理活動 API 的詳細資訊，請參閱[office 365 管理 APIs 快速入門](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。
    
## <a name="turn-on-audit-log-search"></a>開啟審計記錄搜尋

您可以使用安全性 & 合規性中心或 PowerShell，在 Office 365 中開啟審核記錄搜尋。 在您開啟審核記錄搜尋後，可能需要數小時的時間，才能在搜尋審核記錄檔時傳回結果。 您必須在 Exchange Online 中指派「審核記錄」角色，才能開啟審核記錄搜尋。
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>使用安全性 & 規範中心開啟審核記錄搜尋

1. 在 [安全性 & 規範中心] 中，移至 [**搜尋** \> **審核記錄搜尋**]。
    
   顯示旗標，指出必須開啟審計，以錄製使用者和系統管理員活動。

2. 按一下 [**開啟審計**]。
    
    ![按一下 [開啟審計]](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    橫幅已更新，表示已準備好審核記錄，而且您可以在數小時內搜尋使用者和系統管理員活動。
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>使用 PowerShell 開啟審計記錄搜尋

1. [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 執行下列 PowerShell 命令，在 Office 365 中開啟審計記錄搜尋。
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    隨即顯示一則訊息，指出可能需要長達60分鐘的時間，變更才會生效。
  
## <a name="turn-off-audit-log-search"></a>關閉審核記錄搜尋

您必須使用連線至 Exchange Online 組織的遠端 PowerShell，關閉「審核記錄搜尋」。 與開啟審計記錄搜尋類似，您必須在 Exchange Online 中指派「審計記錄」角色，以關閉「審核記錄搜尋」。
  
1. [連線到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 執行下列 PowerShell 命令，關閉 Office 365 中的「審核記錄搜尋」。
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 經過一段時間後，請確認已關閉審計記錄搜尋（停用）。 方法有兩種：
    
    - 在 PowerShell 中，執行下列命令：

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      UnifiedAuditLogIngestionEnabled 屬性的`False`值表示_UnifiedAuditLogIngestionEnabled_已關閉審核記錄搜尋。 
    
    - 在 [安全性 & 規範中心] 中，移至 [**搜尋** \> **審核記錄搜尋**]。
    
      顯示旗標，指出必須開啟審計，才能錄製使用者和系統管理員活動。
