---
title: 使用「保留鎖定」來限制變更保留原則和保留標籤原則
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 將「保留鎖定」搭配保留原則和保留標籤原則使用，以協助您符合法規需求，並防範惡意系統管理員。
ms.openlocfilehash: 6f6cfc5bef9b93af08fcc9b703b29facb9a7c576
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920689"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a>使用「保留鎖定」來限制變更保留原則和保留標籤原則

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

「保留鎖定」可確保您的組織能夠符合這類法規需求，因為它會鎖定保留原則或保留標籤原則，使得沒有任何人 (包括系統管理員) 可以關閉原則、刪除原則或降低限制。 可能有法規需求需要此設定，並有助於防範惡意系統管理員。

當保留原則鎖定時：

- 沒有人可以將它關閉
- 可以新增位置但不能移除位置
- 您可以延長保留期間，但不能減少保留期間

總的來説，鎖定的保留原則可以增加或延長，但是不能減少或關閉。
  
> [!IMPORTANT]
> 在您鎖定保留原則或保留標籤原則之前，請務必了解其影響，並確認您的組織是否需要它。 例如，可能需要它來滿足法規需求。 套用保留鎖定之後，系統管理員將無法停用或刪除保留原則。

請在您建立[保留原則](create-retention-policies.md)，或[發佈](create-apply-retention-labels.md)或[自動套用](apply-retention-labels-automatically.md)保留標籤原則之後，再設定保留鎖定。 

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a>如何鎖定保留原則或保留標籤原則

如果您需要使用保留鎖定，您必須使用 PowerShell。 因為系統管理員無法在套用保留鎖定之後停用或刪除保留原則，因此在 UI 中無法使用此功能來防範意外的設定。

具有任何設定的所有保留原則都支持保留鎖定。

1. [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. 執行 [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy) ，並尋找您想要鎖定的原則名稱。 例如：
    
   ![PowerShell 中保留原則的清單](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. 若要將保留鎖定置於保留原則上，請以保留原則名稱執行 [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet，並將 *RestrictiveRetention* 參數設為 true：
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    例如：
    
    ![PowerShell 中的 RestrictiveRetention 參數](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     當系統提示時，請閱讀並輸入 **Y** 來認可此設定隨附的限制：
    
   ![確認您在 PowerShell 想要鎖定保留原則的提示。](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

保留鎖定現在放置於保留原則上。 若要確認，請再次執行 `Get-RetentionCompliancePolicy`，但指定保留原則名稱並顯示原則參數：

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

您應該會看到 **RestrictiveRetention** 設定為 **True** 。 例如：

![PowerShell 中顯示所有參數的鎖定原則](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a>另請參閱

[協助您符合資訊管理與記錄管理法規需求的資源](retention-regulatory-requirements.md)
