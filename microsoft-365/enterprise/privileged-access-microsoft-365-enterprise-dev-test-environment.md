---
title: Microsoft 365 企業版測試環境的特殊權限存取管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: 若要啟用權限的存取管理 Microsoft 365 企業版測試環境使用此測試實驗室指南。
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866127"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企業版測試環境的特殊權限存取管理

使用本文中的指示，您可以設定以增加安全性 Microsoft 365 企業版測試環境中的權限的存取管理。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境

如果只想要設定權限的存取管理的基本需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您要設定模擬企業中的存取權限的管理，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。
  
> [!NOTE]
> 測試權限的存取管理不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。這裡提供選項，讓您可以測試權限存取管理並代表的典型組織的環境中實驗。 

## <a name="phase-2-configure-privileged-access-management"></a>階段 2： 設定權限的存取管理

在此階段中，您可以設定核准者群組及權限的存取管理啟用 Microsoft 365 企業版測試環境。如需其他詳細資料及權限的概觀存取管理，請參閱[Office 365 中的權限的存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)。

請遵循下列步驟來設定和 Office 365 組織中使用特殊權限的存取：

- [步驟 1： 建立核准者群組](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    在您開始使用最低權限存取之前，請決定誰將擁有的傳入要求提高權限與權限工作的存取權核准授權單位。任何已核准者的群組之一部分的使用者將能夠核准存取要求。這會啟用在 Office 365 中建立擁有郵件功能的安全性群組。建立測試環境中名為 」 權限存取核准者"的新安全性群組並新增"使用者 3"先前在先前的測試實驗室指南步驟中建立。

- [步驟 2： 啟用權限的存取](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    權限的存取必須明確開啟 Office 365 中使用的預設核准者群組與包括一組您想要排除的權限的存取管理存取控制的系統帳戶。請務必啟用之前先啟動本指南的階段 3： 在 Office 365 組織中的權限的存取。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>階段 3： 確認核准需要提高權限和權限工作
在此階段中，您可以確認運作的權限的存取原則及使用者需要核准執行已定義的提高權限和權限工作。

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>測試能夠執行的特殊權限的存取原則中未定義的工作

首先，設定為在測試環境中的全域管理員使用者的認證以連線至 Exchange Management PowerShell 並嘗試建立新的日誌規則。[New-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps)任務目前未定義在您的組織權限的存取原則。

1. 在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft**corporation > **Microsoft Exchange Online 遠端 PowerShell 模組**使用全域管理員帳戶的測試環境。

2. 在 Exchange Management Powershell 中建立新的日誌規則的組織：

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. 新的日誌規則已成功建立的 Exchange Management PowerShell] 檢視。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>建立新的權限的存取原則 New-journalrule 工作

> [!NOTE]
> 如果您已經尚未完成步驟 1 和 2 從本指南的階段 2，是確定遵循的步驟來建立名為"最低權限存取核准者 」 的核准者群組以及能在測試環境中的權限的存取。

1. 登入[Microsoft 365 系統管理中心](https://portal.office.com)使用認證測試環境的全域管理員帳戶。

2. 在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。

3. 選取 [**管理存取原則及要求**。

4. 選取 [**設定的原則**，並選取 [**新增原則**。

5. 從下拉式欄位中，選取或輸入下列值：
    
    **原則類型**： 任務

    **原則範圍**： Exchange

    **原則名稱**： 新的日誌規則

    **核准類型**： 能沒有的手冊

    **核准群組**： 權限存取核准者

6. 選取 [**建立**並再**關閉**。可能需要幾分鐘時間可完全設定並啟用原則。請務必允許完全之前測試核准需求下一個步驟中啟用之原則的時間。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>測試核准權限的存取原則所定義的 New-journalrule 工作需求

1. 在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft**corporation > **Microsoft Exchange Online 遠端 PowerShell 模組**使用使用全域管理員帳戶的測試環境。

2. 在 Exchange Management Powershell 中建立新的日誌規則的組織：

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. 在 Exchange Management PowerShell 檢視 「 Insuffient 權限 」 錯誤：

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>若要建立新的日誌規則使用 New-journalrule 工作要求存取

1. 登入[Microsoft 365 系統管理中心](https://portal.office.com)的測試環境中使用的全域管理員帳戶。

2. 在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。

3. 選取 [**管理存取原則及要求**。

4. 選取**新的要求**。從下拉式欄位中，選取您的組織適當的值：

    **要求類型**： 任務

    **要求範圍**： Exchange

    **要求**： 新的日誌規則

    **持續時間 （小時）**: 2

    **註解**： 要求權限可建立新的日誌規則

5. 選取 [**儲存**並再**關閉**。您的要求會傳送到透過電子郵件的核准者群組。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>核准權限的存取要求建立新的日誌規則

1. 登入[Microsoft 365 系統管理中心](https://portal.office.com)使用使用者 3 在測試環境中 （在測試環境中 」 權限存取核准者 」 安全性群組的成員） 的認證。

2. 在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。

3. 選取 [**管理存取原則及要求**。

4. 選取 [擱置的要求，並選取 [建立新的日誌規則的全域管理員帳戶的存取權授與**核准**。通知電子郵件確認您已授與核准就會傳送給全域管理員帳戶 （要求的使用者）。  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>測試與核准 New-journalrule 工作的存取權限建立新的日誌規則

1. 在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft**corporation > **Microsoft Exchange Online 遠端 PowerShell 模組**使用全域管理員帳戶的測試環境。

2. 在 Exchange Management Powershell 中建立新的日誌規則的組織：

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. 新的日誌規則已成功建立的 Exchange Management PowerShell] 檢視。

## <a name="next-step"></a>下一步

探索測試環境的其他[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)特色和功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)