---
title: 適用于企業測試環境的 Microsoft 365 的特殊許可權存取管理
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: 使用此測試實驗室指南可啟用企業測試環境的 Microsoft 365 的許可權存取管理。
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126414"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>適用于企業測試環境的 Microsoft 365 的特殊許可權存取管理

*此測試實驗室指南可用於 enterprise 和 Office 365 企業版測試環境的 Microsoft 365。*

本文說明如何設定特殊許可權存取管理，以提升企業測試環境中 Microsoft 365 的安全性。

設定 priviledged 存取管理包括三個階段：
- [階段1：組建您的企業測試環境 Microsoft 365](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [階段2：設定特殊許可權存取管理](#phase-2-configure-privileged-access-management)
- [階段3：確認是否需要核准以進行提升和特權工作](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 如需適用于企業測試實驗室指南堆疊的 Microsoft 365 中的所有文章的視覺對應，請移至[Microsoft 365 for enterprise test lab guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的企業測試環境 Microsoft 365

若要以輕量的方式設定特殊許可權存取管理，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。
  
如果您想要在模擬的企業中設定特殊許可權存取管理，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
>[!NOTE]
>測試特殊許可權存取管理不需要模擬的企業測試環境，包括連接至網際網路的模擬內部網路和 Active Directory 網域服務樹系的目錄同步處理。 它是以選項形式提供，讓您可以在代表一般組織的環境中測試特殊許可權的存取管理，並進行試驗。

## <a name="phase-2-configure-privileged-access-management"></a>階段2：設定特殊許可權存取管理

在這個階段中，設定 [核准者] 群組，並為您的 Microsoft 365 企業測試環境啟用特殊許可權存取管理。 如需詳細資訊及特殊許可權存取管理的概要資訊，請參閱「特殊許可權 [存取管理](../compliance/privileged-access-management-overview.md)」。

若要在組織中設定及使用特殊許可權存取，請執行下列步驟。

#### <a name="step-1-create-an-approvers-group"></a>[步驟1：建立核准者的群組](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

在開始使用「特殊許可權存取」之前，請先決定誰將有權存取已升高和特權任務的傳入要求。 所有屬於核准者群組的使用者都可以核准存取要求。 若要使用特殊許可權存取，您必須在 Microsoft 365 中建立擁有郵件功能的安全性群組。 在測試環境中，將新的安全性群組命名為「特權存取核准者」，並新增先前在先前的測試實驗室指南步驟中所建立的「使用者3」。

#### <a name="step-2-enable-privileged-access"></a>[步驟2：啟用特殊許可權存取](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

在具有預設核准群組的 Microsoft 365 中，必須明確地開啟特殊許可權存取，而且必須包含您要從特殊許可權存取管理存取控制中排除的一組系統帳戶。 請務必在您的組織中啟用特殊許可權的存取，再開始本指南的第3階段。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>階段3：確認是否需要核准以進行提升和特權工作

在這個階段中，請確認 [許可權存取原則] 正常運作，且使用者需要核准，才能執行已定義的高許可權和特權工作。

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>測試執行非特權存取原則中所定義之工作的能力

首先，以您的測試環境中已設定為全域系統管理員之使用者的認證，連接至 Exchange 管理 PowerShell，並嘗試建立新的日誌規則。 目前未在組織的特殊許可權存取原則中定義 [New-JournalRule](/powershell/module/exchange/new-journalrule) 任務。

1. 在您的本機電腦上，使用您測試環境的全域系統管理員帳戶，開啟並登入 **Microsoft Corporation**  >  **Microsoft Exchange Online remote PowerShell 模組** 的 Exchange Online remote PowerShell 模組。

1. 在 Exchange 管理 PowerShell 中，為您的組織建立新的日誌規則：

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. 在 Exchange 管理 PowerShell 中，查看是否已成功建立新的日誌規則。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>為 New-JournalRule 工作建立新的許可權存取原則

>[!NOTE]
>如果您還沒有完成本指南第2階段的步驟1和2，請務必遵循下列步驟，建立名為「許可權存取核准者」的核准者群組，以在您的測試環境中啟用特殊許可權存取。

1. 使用認證來登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)您的測試環境全域管理員帳戶。

2. 在系統管理中心，移至 **設定**  >  **安全性 & 隱私權** 的特殊許可權  >  **存取**。

3. 選取 [ **管理存取原則和要求**]。

4. 選取 [ **設定原則**]，然後選取 [ **新增原則**]。

5. 從下拉欄位中，選取或輸入下列值：

    **原則類型**：任務

    **原則範圍**：Exchange

    **原則名稱**：新增日誌規則

    **核准類型**：手動

    **核准群組**：許可權存取核准者

6. 選取 **[建立]**，然後選取 **[關閉]**。 可能需要幾分鐘的時間，才能完全設定或啟用原則。 在下一個步驟中測試核准需求之前，請務必允許完整啟用該原則的時間。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>測試許可權存取原則中所定義之 New-JournalRule 工作的核准需求

1. 在您的本機電腦上，使用為測試環境使用全域系統管理員帳戶，開啟並登入 **Microsoft Corporation** 的 Exchange Online remote PowerShell 模組  >  **Microsoft Exchange Online remote PowerShell Module** 。

2. 在 Exchange 管理 PowerShell 中，為您的組織建立新的日誌規則：

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. 在 Exchange 管理 PowerShell: 中查看「許可權不足」的錯誤

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>要求存取使用 New-JournalRule 任務建立新的日誌規則

1. 使用測試環境的全域系統管理員帳戶登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。

2. 在系統管理中心，移至 **設定**  >  **安全性 & 隱私權** 的特殊許可權  >  **存取**。

3. 選取 [ **管理存取原則和要求**]。

4. 選取 [ **新增要求**]。 從下拉欄位中，為您的組織選取適當的值：

    **要求類型**：任務

    **要求範圍**：Exchange

    **要求**：新增日誌規則

    **Duration (小時)**：2

    **批註**：要求許可權以建立新的日誌規則

5. 選取 [ **儲存**]，然後選取 [ **關閉**]。 您的要求將透過電子郵件傳送給核准者的群組。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>核准建立新的日誌規則的特殊許可權存取要求

1. 在測試環境中，使用使用者3的認證 () 測試環境中的「特權存取核准者」安全性群組的成員，登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。

2. 在系統管理中心，移至 **設定**  >  **安全性 & 隱私權** 的特殊許可權  >  **存取**。

3. 選取 [ **管理存取原則和要求**]。

4. 選取 [擱置的要求]，然後選取 [ **核准** ]，以將存取權授與全域管理員帳戶，以建立新的日誌規則。 「全域管理員帳戶」 (要求使用者) 會收到核准已授與的電子郵件確認。

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>測試使用 New-JournalRule 工作核准的特殊存取權來建立新的日誌規則

1. 在您的本機電腦上，使用您測試環境的全域系統管理員帳戶，開啟並登入 **Microsoft Corporation**  >  **Microsoft Exchange Online remote PowerShell 模組** 的 Exchange Online remote PowerShell 模組。

1. 在 Exchange 管理 PowerShell 中，為您的組織建立新的日誌規則：

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. 在 Exchange 管理 PowerShell 中，查看是否已成功建立新的日誌規則。

## <a name="next-step"></a>下一步

在您的測試環境中探索其他 [資訊保護](m365-enterprise-test-lab-guides.md#information-protection) 功能和功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Microsoft 365 企業版文件](/microsoft-365-enterprise/)
