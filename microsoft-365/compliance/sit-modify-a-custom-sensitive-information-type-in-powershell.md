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
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="f4dc3-103">使用 PowerShell 修改自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="f4dc3-103">Modify a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="f4dc3-104">在合規性中心 PowerShell 中，修改自訂機密資訊類型，需要您執行：</span><span class="sxs-lookup"><span data-stu-id="f4dc3-104">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="f4dc3-105">將包含自訂機密資訊類型的現有規則套件匯出至 XML 檔 (或使用現有的 XML 檔，若您有一個的話)。</span><span class="sxs-lookup"><span data-stu-id="f4dc3-105">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="f4dc3-106">修改已匯出之 XML 檔中的自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="f4dc3-106">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="f4dc3-107">將更新的 XML 檔匯入至現有的規則套件。</span><span class="sxs-lookup"><span data-stu-id="f4dc3-107">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="f4dc3-108">若要連線到合規性中心 PowerShell，請參閱[連線到合規性中心 PowerShell](/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f4dc3-108">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="f4dc3-109">步驟 1：將現有規則套件匯出至 XML 檔</span><span class="sxs-lookup"><span data-stu-id="f4dc3-109">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="f4dc3-110">如果您有 XML 檔的複本 (例如，您剛建立並匯入它)，則可以跳到下一個步驟來修改 XML 檔。</span><span class="sxs-lookup"><span data-stu-id="f4dc3-110">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="f4dc3-111">如果您不清楚，請執行 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) Cmdlet 來尋找自訂規則套件的名稱：</span><span class="sxs-lookup"><span data-stu-id="f4dc3-111">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="f4dc3-p101">包含內建機密資訊類型的內建規則套件稱為 Microsoft 規則套件。此規則套件名為 Microsoft.SCCManaged.CustomRulePack，其中包含您已在合規性中心 UI 中建立的自訂機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="f4dc3-p101">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package. The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="f4dc3-114">使用 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) Cmdlet，將自訂規則套件儲存至變數：</span><span class="sxs-lookup"><span data-stu-id="f4dc3-114">Use the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="f4dc3-115">例如，如果規則套件的名稱為 "Employee ID Custom Rule Pack"，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f4dc3-115">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="f4dc3-116">請使用 [Set-Content](/powershell/module/microsoft.powershell.management/set-content) Cmdlet 將自訂規則套件匯出至 XML 檔：</span><span class="sxs-lookup"><span data-stu-id="f4dc3-116">Use the [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="f4dc3-117">此範例會將此規則套件匯出至 C:\My Documents 資料夾中名為 ExportedRulePackage.xml 的檔案。</span><span class="sxs-lookup"><span data-stu-id="f4dc3-117">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="f4dc3-118">步驟 2：修改已匯出之 XML 檔中的機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="f4dc3-118">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="f4dc3-119">稍早已在本主題中描述 XML 檔中的機密資訊類型和檔案中的其他元素。</span><span class="sxs-lookup"><span data-stu-id="f4dc3-119">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="f4dc3-120">步驟 3：將更新的 XML 檔匯入至現有的規則套件。</span><span class="sxs-lookup"><span data-stu-id="f4dc3-120">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="f4dc3-121">若要更新的 XML 重新匯入現有規則套件，請使用 [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f4dc3-121">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="f4dc3-122">如需詳細的語法和參數資訊，請參閱 [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage)。</span><span class="sxs-lookup"><span data-stu-id="f4dc3-122">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>


## <a name="more-information"></a><span data-ttu-id="f4dc3-123">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="f4dc3-123">More information</span></span>

- [<span data-ttu-id="f4dc3-124">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="f4dc3-124">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="f4dc3-125">敏感性資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="f4dc3-125">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="f4dc3-126">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="f4dc3-126">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
