---
title: 在 Microsoft 365 中設定高級審計
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
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 本文說明如何設定高級審核，讓您可以在使用者帳戶受損時執行鑒證調查，或調查其他與安全性相關的事件。
ms.openlocfilehash: d1752ee7714056254a6c0e5c009aa9aa79ddff3b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314300"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a>在 Microsoft 365 中設定高級審計

如果您的組織擁有支援高級審計的訂閱和使用者授權，請執行下列步驟，以在高級審計中設定及使用其他功能。

![設定進階稽核的工作流程](../media/AdvancedAuditWorkflow.png)

## <a name="step1-set-up-advanced-audit-for-users"></a>步驟1：設定使用者的高級審計

進階稽核功能，如記錄重要事件 (如 MailItemsAccessed 和 Send) 功能，需要為使用者指派適當的 E5 授權。 此外，必須為這些使用者啟用 [進階稽核] 應用程式/服務方案。 要驗證 [進階稽核] 應用程式是否已指派給使用者，請對每個使用者執行以下步驟：

1. 在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/Adminportal)中，移至 **[使用者]** > **[作用中的使用者]**，然後選取使用者。

2. 在 [使用者內容] 飛出頁面上，按一下 **[授權和應用程式]**。

3. 在 [ **授權** ] 區段中，確認使用者已獲指派 E5 授權，或已獲指派適當的附加元件授權。 如需支援高級審核的授權清單，請參閱「 [高級審核授權」需求](auditing-solutions-overview.md#advanced-audit-1)。

4. 展開 **[應用程式]** 區段，並驗證是否選中了 **[Microsoft 365 進階稽核]** 核取方塊。

5. 如果未選取此核取方塊，請選取它，然後按一下 [ **儲存變更]。**

   MailItemsAccessed 和 Send 的審計記錄記錄會從24小時內開始。 您必須執行步驟3，以開始記錄其他兩個高級審核重要事件： SearchQueryInitiatedExchange 和 SearchQueryInitiatedSharePoint。

針對使用以群組為基礎授權之指派授權至使用者群組的組織，請務必關閉該群組的 Microsoft 365 進階稽核授權指派。 儲存變更之後，請確認已關閉群組的 Microsoft 365 進階稽核。 然後重新開啟群組的授權指派。 如需以群組為基礎授權的相關指示，請參閱[在 Azure Active Directory 中以群組成員資格指派授權給使用者](/azure/active-directory/users-groups-roles/licensing-groups-assign)。

此外，如果您已自訂使用者信箱或共用信箱上所記錄的信箱動作，則 Microsoft 所發行的任何新重要事件都不會自動在這些信箱上進行審核。 有關變更為每個登入類型稽核的郵箱動作之資訊，請參閱[管理郵箱稽核](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)中的 [變更或還原預設記錄的郵箱動作] 一節。

## <a name="step-2-enable-crucial-events"></a>步驟2：啟用重要事件

您必須啟用兩個重要事件 (SearchQueryInitiatedExchange 和 SearchQueryInitiatedSharePoint) 在使用者于 Exchange Online 和 SharePoint 線上執行搜尋時才會登入。 若要為使用者審核這兩個事件，請針對[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中的每個使用者) 執行下列命令 (：

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

在多地理位置環境中，您必須在使用者信箱所在的樹系中執行先前的 **Set-Mailbox** 命令。 若要識別使用者的信箱位置，請執行下列命令： 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

若啟用搜尋查詢審計的命令先前是在與使用者信箱所在的樹系不同的樹系中執行，則必須執行此作業， `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` 然後再將其新增至使用者信箱所在樹系中的使用者信箱，以移除使用者信箱中的 SearchQueryInitiated 值。

## <a name="step-3-set-up-audit-retention-policies"></a>步驟3：設定審核保留原則

除了保留 Exchange、SharePoint 和 Azure AD 稽核記錄一年的預設原則之外，您還可以建立其他稽核記錄保留原則以符合組織的安全性作業、IT 和合規性小組的需求。 如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md)。

## <a name="step-4-search-for-crucial-events"></a>步驟4：搜尋重要事件

現在您已設定好組織的高級審核，您可以在進行鑒證調查時搜尋重要的事件及其他活動。 完成步驟1和步驟2後，您可以在取證調查遭破壞的帳戶和其他類型的安全性或法規遵從性調查期間，搜尋「審核記錄」，以取得重要的事件及其他活動。 如需使用 MailItemsAccessed 重要事件來進行取證調查已遭破壞之使用者帳戶的詳細資訊，請參閱 [使用 Advanced Audit 調查已遭破壞的帳戶](mailitemsaccessed-forensics-investigations.md)。
