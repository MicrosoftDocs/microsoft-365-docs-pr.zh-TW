---
title: 使用 PowerShell 移除自訂機密資訊類型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 瞭解如何使用 PowerShell 移除自訂機密資訊類型
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322562"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>使用 PowerShell 移除自訂機密資訊類型



在合規性中心 PowerShell 中，有兩種方法可以移除自訂機密資訊類型：

- **移除個別的自訂敏感資訊類型**：使用 [PowerShell 修改自訂機密資訊類型](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)中所述的方法。 您匯出自訂的規則套件，其中包含自訂機密資訊類型、從 XML 檔案中移除敏感資訊類型，並將更新的 XML 檔案重新匯入現有的自訂規則套件。

- **移除自訂規則套件及其包含的所有自訂機密資訊類型**：本節會描述此方法。

> [!NOTE]
> 在您移除自訂機密資訊類型之前，請確認沒有 DLP 原則或 Exchange 郵件流程規則 (也稱為傳輸規則) 仍參照機密資訊類型。

1. [連線到合規性中心 PowerShell](/powershell/exchange/exchange-online-powershell)。

2. 若要移除自訂規則套件，請使用 [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) Cmdlet：

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   您可以使用名稱值 (適用於任何語言) 或 `RulePack id` (GUID) 值，來識別規則套件。

   此範例會移除名為 "Employee ID Custom Rule Pack" 的規則套件。

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   如需詳細的語法和參數資訊，請參閱 [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage)。

3. 若要確認您已成功移除自訂機密資訊類型，請執行下列任一步驟：

   - 執行 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) Cmdlet，並驗證規則套件，不再列於：

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - 執行 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) Cmdlet，並驗證不再列出已移除之規則套件中的機密資訊類型：

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     針對自訂機密資訊類型，Publisher 屬性值將為 Microsoft Corporation 以外的值。

   - 將 \<Name\> 取代為機密資訊類型的 [名稱] 值（例如：員工識別碼），然後執行 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet，以驗證不再列出機密資訊類型：

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a>詳細資訊

- [深入了解資料外洩防護](dlp-learn-about-dlp.md)

- [敏感性資訊類型實體定義](sensitive-information-type-entity-definitions.md)

- [DLP 功能所尋找的項目](what-the-dlp-functions-look-for.md)
