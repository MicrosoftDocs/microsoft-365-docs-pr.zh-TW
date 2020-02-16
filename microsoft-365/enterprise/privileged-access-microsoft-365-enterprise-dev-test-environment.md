---
title: Microsoft 365 企業版測試環境的特殊權限存取管理
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
description: 使用此測試實驗室指南來啟用特殊權限的存取管理 Microsoft 365 企業版測試環境。
ms.openlocfilehash: ce637b94333f088d25e479e61ad2a98176a2f7c6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085372"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企業版測試環境的特殊權限存取管理

*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*

透過本文中的指示，您可以設定若要提高安全性，Microsoft 365 企業版測試環境中的特殊權限的存取管理。

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
>按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1：建置您的 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式設定特殊權限的存取管理，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要在模擬的企業中設定特殊權限的存取管理，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。
  
>[!NOTE]
>測試特殊權限的存取管理，不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 AD DS 樹系。 它提供了以下選項，以便您可以測試權限存取管理及實驗它代表典型組織的環境中。 

## <a name="phase-2-configure-privileged-access-management"></a>階段 2： 設定特殊權限的存取管理

在這個階段，您可以設定的核准者群組，並啟用適用於 Microsoft 365 企業版測試環境的特殊權限的存取管理。 其他詳細資料和概觀權限存取管理，請參閱[Office 365 中的特殊權限的存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)。

請遵循下列步驟來設定和使用 Office 365 組織中的特殊權限的存取：

- [步驟 1： 建立核准者群組](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    開始使用權限存取之前，請決定誰會具有存取提升權限和特殊權限的工作的傳入要求的核准授權。 屬於核准者群組的任何使用者將能夠核准存取要求。 這會啟用在 Office 365 中建立擁有郵件功能的安全性群組。 建立測試環境中名為 「 特殊權限存取核准者 」 的新安全性群組並新增 「 使用者 3 」 先前在先前的測試實驗室指南步驟中建立。

- [步驟 2： 啟用特殊權限的存取](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    特殊權限的存取必須明確中開啟 Office 365 與預設的核准者群組包含一組您想要排除的特殊權限的存取管理存取控制的系統帳戶。 請務必啟用 Office 365 組織才能開始進行本指南的階段 3 中的特殊權限的存取。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>階段 3： 確認核准需要提高權限和特殊權限工作

在這個階段，您可以驗證的特殊權限的存取原則的運作，而且使用者要求核准] 若要執行已定義的提升權限和特殊權限工作。

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>測試能夠執行的特殊權限的存取原則中未定義的工作

首先，以設定測試環境中的全域系統管理員身分的使用者的認證連線到 Exchange Management PowerShell，並嘗試建立新的日誌規則。 該[New-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps)任務是目前中未定義貴組織的特殊權限的存取原則。

1. 在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft Corporation**在 > **Microsoft Exchange Online 遠端 PowerShell 模組**使用全域系統管理員帳戶的測試環境。

2. 在 Exchange Management PowerShell 中建立新的日誌規則，為您的組織：

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. 檢視的新日誌規則已順利建立在 Exchange Management PowerShell。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>建立新的特殊權限的存取原則，針對該 New-journalrule 任務

>[!NOTE]
>如果您已經完成步驟 1 和 2 從本指南的階段 2，是確定遵循的步驟來建立名為 」 權限存取核准者 」 的核准者群組，並讓測試環境中的特殊權限的存取。

1. 適用於測試環境的全域系統管理員帳戶登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用認證。

2. 在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。

3. 選取 [**管理存取原則和要求**。

4. 選取 [**設定原則**，然後選取 [**新增原則**。

5. 從下拉式清單的欄位，選取或輸入下列值：

    **原則類型**： 工作

    **原則範圍**： Exchange

    **原則名稱**： 新的日誌規則

    **核准類型**： 手冊

    **核准群組**： 特殊權限存取核准者

6. 選取 [**建立**，然後**關閉**。 可能需要幾分鐘的完整設定並啟用原則。 請務必讓測試的核准要求在下一個步驟之前要完全啟用原則的時間。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>測試特殊權限的存取原則中定義該 New-journalrule 任務核准的需求

1. 在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft Corporation**在 > **Microsoft Exchange Online 遠端 PowerShell 模組**使用使用全域系統管理員帳戶的測試環境。

2. 在 Exchange Management PowerShell 中建立新的日誌規則，為您的組織：

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. 在 Exchange Management PowerShell 中的檢視 」 權限不足 」 錯誤：

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>若要建立新的日誌規則，使用該 New-journalrule 任務要求存取

1. 登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)的測試環境中使用的全域系統管理員帳戶。

2. 在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。

3. 選取 [**管理存取原則和要求**。

4. 選取**新的要求**。 從下拉式清單的欄位，選取適當的值為您的組織：

    **要求類型**： 工作

    **要求範圍**： Exchange

    **要求**： 新的日誌規則

    **持續時間 （小時）**: 2

    **註解**： 要求權限以建立新的日誌規則

5. 選取**儲存**，然後**關閉**。 您的要求會傳送至透過電子郵件的核准者群組。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>核准建立新的日誌規則的特殊權限的存取要求

1. 登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用 User 3 在測試環境 （測試環境中的 「 特殊權限存取核准者 」 安全性] 群組的成員） 的認證。

2. 在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。

3. 選取 [**管理存取原則和要求**。

4. 選取 [擱置的要求，然後選取 [授與存取權的全域系統管理員帳戶，來建立新的日誌規則的**核准**。 全域系統管理員帳戶 （要求使用者） 時，會將傳送通知電子郵件，確認已授與核准。  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>測試與核准該 New-journalrule 任務的特殊權限存取建立新的日誌規則

1. 在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft Corporation**在 > **Microsoft Exchange Online 遠端 PowerShell 模組**使用全域系統管理員帳戶的測試環境。

2. 在 Exchange Management PowerShell 中建立新的日誌規則，為您的組織：

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. 檢視的新日誌規則已順利建立在 Exchange Management PowerShell。

## <a name="next-step"></a>下一步

瀏覽額外的[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)功能和測試環境中的功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
