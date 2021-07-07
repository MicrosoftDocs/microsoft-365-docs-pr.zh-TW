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
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="21f6e-103">使用 PowerShell 移除自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="21f6e-103">Remove a custom sensitive information type using PowerShell</span></span>



<span data-ttu-id="21f6e-104">在合規性中心 PowerShell 中，有兩種方法可以移除自訂機密資訊類型：</span><span class="sxs-lookup"><span data-stu-id="21f6e-104">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="21f6e-105">**移除個別的自訂敏感資訊類型**：使用 [PowerShell 修改自訂機密資訊類型](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)中所述的方法。</span><span class="sxs-lookup"><span data-stu-id="21f6e-105">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type using PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span></span> <span data-ttu-id="21f6e-106">您匯出自訂的規則套件，其中包含自訂機密資訊類型、從 XML 檔案中移除敏感資訊類型，並將更新的 XML 檔案重新匯入現有的自訂規則套件。</span><span class="sxs-lookup"><span data-stu-id="21f6e-106">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="21f6e-107">**移除自訂規則套件及其包含的所有自訂機密資訊類型**：本節會描述此方法。</span><span class="sxs-lookup"><span data-stu-id="21f6e-107">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

> [!NOTE]
> <span data-ttu-id="21f6e-108">在您移除自訂機密資訊類型之前，請確認沒有 DLP 原則或 Exchange 郵件流程規則 (也稱為傳輸規則) 仍參照機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="21f6e-108">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="21f6e-109">[連線到合規性中心 PowerShell](/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="21f6e-109">[Connect to Compliance center PowerShell](/powershell/exchange/exchange-online-powershell)</span></span>

2. <span data-ttu-id="21f6e-110">若要移除自訂規則套件，請使用 [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="21f6e-110">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="21f6e-111">您可以使用名稱值 (適用於任何語言) 或 `RulePack id` (GUID) 值，來識別規則套件。</span><span class="sxs-lookup"><span data-stu-id="21f6e-111">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="21f6e-112">此範例會移除名為 "Employee ID Custom Rule Pack" 的規則套件。</span><span class="sxs-lookup"><span data-stu-id="21f6e-112">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="21f6e-113">如需詳細的語法和參數資訊，請參閱 [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage)。</span><span class="sxs-lookup"><span data-stu-id="21f6e-113">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="21f6e-114">若要確認您已成功移除自訂機密資訊類型，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="21f6e-114">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="21f6e-115">執行 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) Cmdlet，並驗證規則套件，不再列於：</span><span class="sxs-lookup"><span data-stu-id="21f6e-115">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="21f6e-116">執行 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) Cmdlet，並驗證不再列出已移除之規則套件中的機密資訊類型：</span><span class="sxs-lookup"><span data-stu-id="21f6e-116">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="21f6e-117">針對自訂機密資訊類型，Publisher 屬性值將為 Microsoft Corporation 以外的值。</span><span class="sxs-lookup"><span data-stu-id="21f6e-117">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="21f6e-118">將 \<Name\> 取代為機密資訊類型的 [名稱] 值（例如：員工識別碼），然後執行 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet，以驗證不再列出機密資訊類型：</span><span class="sxs-lookup"><span data-stu-id="21f6e-118">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a><span data-ttu-id="21f6e-119">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="21f6e-119">More information</span></span>

- [<span data-ttu-id="21f6e-120">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="21f6e-120">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="21f6e-121">敏感性資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="21f6e-121">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="21f6e-122">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="21f6e-122">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
