---
title: DLP 的自訂敏感性資訊類型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 取得資料遺失防護（DLP）的自訂機密資訊類型概覽，例如 [主要模式]、[字元近似] 和 [信任等級]。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6934edba6eef03bc9d4bfc5c1c69f127a7d3a0e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817962"
---
# <a name="custom-sensitive-information-types"></a>自訂敏感性資訊類型

Microsoft 365 包含可供您在組織中使用的許多內建的敏感性資訊類型，例如[資料外洩防護](data-loss-prevention-policies.md) (DLP)，或是 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)。 內建的敏感性資訊類型會根據規則運算式 (regex) 或函數所定義的模式，協助識別及保護信用卡卡號、銀行帳戶號碼、護照號碼等。 若要深入了解，請參閱[機密資訊類型尋找的目標為何](what-the-sensitive-information-types-look-for.md)。

不過，如果您需要識別及保護不同類型的敏感性資訊，例如使用您組織特定格式的員工識別碼或專案編號，該怎麼辦？ 若要這麼做，您可以建立自訂敏感性資訊類型。

自訂機密資訊類型的基礎部分如下：

- **主要模式**：員工識別碼、專案編號等等。這通常由規則運算式 (RegEx) 識別，但它也可以是關鍵字清單。

- **Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.

- **Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:

    ![確切辨識項和近似值視窗的圖表](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.

  When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:

    ![執行個體計數和比對正確性選項](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a>建立自訂敏感性資訊類型

若要在安全性與合規性中心建立自訂敏感性資訊類型，您可以從數個選項中選擇：

- **使用 EDM** (新增！) 您可以使用以精確資料比對 (EDM) 為基礎的分類來設定自訂敏感性資訊類型。 此方法可讓您使用您可以定期更新的安全資料庫來建立動態敏感性資訊類型。 請參閱[使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。

- **使用 PowerShell** 您可以使用 PowerShell 來設定自訂敏感性資訊類型。 雖然此方法比使用 UI 更複雜，但是您有多個組態選項。 請參閱[在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。

- **使用 UI** 您可以使用安全性與合規性中心 UI 來設定自訂敏感性資訊類型。 使用此方法，您可以使用規則運算式、關鍵字和關鍵字字典。 若要進一步了解，請參閱[建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type.md)。



