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
ms.openlocfilehash: 72f667b970b4257a3a540fb74a121c620892b56d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922527"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a>使用「保留鎖定」來限制變更保留原則和保留標籤原則

>*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

「保留鎖定」可確保您的組織能夠符合這類法規需求，因為它會鎖定保留原則或保留標籤原則，使得沒有任何人 (包括系統管理員) 可以關閉原則、刪除原則或降低限制。 可能有法規需求需要此設定，並有助於防範惡意系統管理員。

鎖定保留原則時：

- 任何人都不能停用或刪除原則
- 可以新增位置但不能移除位置
- 您可以延長保留期間，但不能減少保留期間

鎖定保留標籤原則時：

- 任何人都不能停用或刪除原則
- 可以新增位置但不能移除位置
- 可以新增標籤但不能移除標籤

總的來説，鎖定的保留原則可以增加或延長，但是不能減少或關閉。

> [!IMPORTANT]
> 在您鎖定保留原則或保留標籤原則之前，請務必了解其影響，並確認您的組織是否需要它。 例如，可能需要它來滿足法規需求。 套用保留鎖定之後，系統管理員將無法停用或刪除保留原則。

請在您建立[保留原則](create-retention-policies.md)，或[發佈](create-apply-retention-labels.md)或[自動套用](apply-retention-labels-automatically.md)保留標籤原則之後，再設定保留鎖定。 

> [!NOTE]
> 鎖定標籤原則不會妨礙系統管理員縮短包含在鎖定原則中的標籤的保留期。 當您設定標籤以將項目標記為[監管記錄](records-management.md#records)時，可以滿足該要求和其他限制。

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a>如何鎖定保留原則或保留標籤原則

如果您需要使用保留鎖定，您必須使用 PowerShell。 因為系統管理員無法在套用保留鎖定之後停用或刪除保留原則，因此在 UI 中無法使用此功能來防範意外的設定。

具有任何設定的所有保留原則都支持保留鎖定。

1. [連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

2. 執行 [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy) ，並尋找您想要鎖定的原則名稱。 例如：
    
   ![PowerShell 中保留原則的清單](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. 若要將保留鎖定置於保留原則上，請以保留原則名稱執行 [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet，並將 *RestrictiveRetention* 參數設為 true：
    
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

您應該會看到 **RestrictiveRetention** 設定為 **True**。 例如：

![PowerShell 中顯示所有參數的鎖定原則](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a>另請參閱

[協助您符合資訊管理與記錄管理法規需求的資源](retention-regulatory-requirements.md)