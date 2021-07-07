---
title: 使用 PowerShell 修改自訂機密資訊類型
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
description: 瞭解如何使用 PowerShell 修改自訂機密資訊。
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322565"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>使用 PowerShell 修改自訂機密資訊類型

在合規性中心 PowerShell 中，修改自訂機密資訊類型，需要您執行：

1. 將包含自訂機密資訊類型的現有規則套件匯出至 XML 檔 (或使用現有的 XML 檔，若您有一個的話)。

2. 修改已匯出之 XML 檔中的自訂機密資訊類型。

3. 將更新的 XML 檔匯入至現有的規則套件。

若要連線到合規性中心 PowerShell，請參閱[連線到合規性中心 PowerShell](/powershell/exchange/exchange-online-powershell)。

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>步驟 1：將現有規則套件匯出至 XML 檔

> [!NOTE]
> 如果您有 XML 檔的複本 (例如，您剛建立並匯入它)，則可以跳到下一個步驟來修改 XML 檔。

1. 如果您不清楚，請執行 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) Cmdlet 來尋找自訂規則套件的名稱：

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > 包含內建機密資訊類型的內建規則套件稱為 Microsoft 規則套件。此規則套件名為 Microsoft.SCCManaged.CustomRulePack，其中包含您已在合規性中心 UI 中建立的自訂機密資訊類型。

2. 使用 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) Cmdlet，將自訂規則套件儲存至變數：

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   例如，如果規則套件的名稱為 "Employee ID Custom Rule Pack"，請執行下列 Cmdlet：

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. 請使用 [Set-Content](/powershell/module/microsoft.powershell.management/set-content) Cmdlet 將自訂規則套件匯出至 XML 檔：

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   此範例會將此規則套件匯出至 C:\My Documents 資料夾中名為 ExportedRulePackage.xml 的檔案。

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>步驟 2：修改已匯出之 XML 檔中的機密資訊類型。

稍早已在本主題中描述 XML 檔中的機密資訊類型和檔案中的其他元素。

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>步驟 3：將更新的 XML 檔匯入至現有的規則套件。

若要更新的 XML 重新匯入現有規則套件，請使用 [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) Cmdlet：

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

如需詳細的語法和參數資訊，請參閱 [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage)。


## <a name="more-information"></a>詳細資訊

- [深入了解資料外洩防護](dlp-learn-about-dlp.md)

- [敏感性資訊類型實體定義](sensitive-information-type-entity-definitions.md)

- [DLP 功能所尋找的項目](what-the-dlp-functions-look-for.md)
