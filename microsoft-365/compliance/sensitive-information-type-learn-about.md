---
title: 瞭解敏感性資訊類型
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: 896a529d67faddb45b2672ca077f5a8e3b19827e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933077"
---
# <a name="learn-about-sensitive-information-types"></a>瞭解敏感性資訊類型

識別及分類組織控制下的機密專案，是資訊保護分項 [的第一個步驟](protect-information.md)。  Microsoft 365 提供三種識別專案的方式，以便分類：

- 使用者手動
- 自動化模式識別，例如敏感性資訊類型
- [機器學習](classifier-learn-about.md)

敏感性資訊類型是以模式為基礎的分類器。 它們可偵測敏感性資訊 ，例如社會安全、信用卡或銀行帳戶號碼以識別敏感性專案，請參閱敏感性 [資訊類型實體定義](sensitive-information-type-entity-definitions.md)

## <a name="sensitive-information-types-are-used-in"></a>敏感性資訊類型用於

- [資料外洩防護原則](data-loss-prevention-policies.md) 
- [敏感性標籤](sensitivity-labels.md)
- [保留標籤](retention.md)
- [通訊合規性](communication-compliance.md)
- [自動標籤策略](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>敏感性資訊類型的基本部分

每個敏感性資訊類型實體是由這些欄位定義：

- 名稱：如何參考敏感性資訊類型
- 描述：描述敏感性資訊類型尋找的內容
- 模式：模式會定義敏感性資訊類型偵測到的資訊。 它包含下列元件
    - 主要元素是敏感性資訊類型要尋找的主要元素。 它可以是 **包含或不含檢查** 和驗證、關鍵字清單 **、關鍵字字典** 或函數的 **正則運算式**。
    - 支援元素 – 做為支援證據的元素，可協助提高比對的信賴度。 例如，鄰近 SSN 數位的關鍵字 "SSN"。 它可以是包含或不含檢查和驗證、關鍵字清單、關鍵字字典的正則運算式。
    - 信賴等級 - 信賴等級 (、中、低) 反應與主要元素一起偵測到的支援證據量。 專案包含的支援證據越多，相符專案的信賴度越高，就表示您正在尋找的敏感性資訊。
    - 鄰近-主要與支援元素之間的字元數

![確切辨識項和近似值視窗的圖表](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

在這段影片中深入瞭解信賴等級


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>敏感性資訊類型範例


## <a name="argentina-national-identity-dni-number"></a>阿根廷國家/ (身分識別) 號碼

### <a name="format"></a>格式

以句點分隔的八位數

### <a name="pattern"></a>模式

八位數：
- 兩位數
- a period
- 三位數
- a period
- 三位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_argentina_national_id找到符合模式的內容。
- 系統找到Keyword_argentina_national_id關鍵字。

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- 阿根廷國家身分識別號碼 
- 身分識別 
- 身分識別身分識別卡 
- DNI 
- NIC National Registry of Persons 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>進一步瞭解信賴等級

在敏感性資訊類型實體定義中，信賴 **等級會反映** 除了主要元素外，還偵測到多少支援證據。 專案包含的支援證據越多，相符專案的信賴度越高，就表示您正在尋找的敏感性資訊。 例如，高信賴等級的比對值會包含較接近主要元素的更多支援證據，而信賴等級低的比對值在接近鄰近區中則包含很少或沒有支援證據。 

高信賴等級會回回最小的誤誤，但可能會導致漏報。 低或中信賴等級會回回更多的誤誤，但少到零的漏報。

- **低信賴** 度：值 65，相符的專案會包含最小的漏報，但負數最多。  
- **中信賴**：值 75，相符的專案會包含平均的誤正和負數。  
- **高信賴** 度：值 85，相符的專案會包含最小的誤數，但負數最高。  

您應使用高信賴等級模式與低計數，例如 5 到 10 個，以及計數較高的低信賴度模式 ，例如 20 或更多。

## <a name="creating-custom-sensitive-information-types"></a>建立自訂敏感性資訊類型

若要在安全性與合規性中心建立自訂敏感性資訊類型，您可以從數個選項中選擇：

- **使用 UI** 您可以使用安全性與合規性中心 UI 來設定自訂敏感性資訊類型。 使用此方法，您可以使用規則運算式、關鍵字和關鍵字字典。 若要進一步了解，請參閱[建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type.md)。

- **使用 EDM** 您可以使用以精確資料比對 (EDM) 為基礎的分類來設定自訂敏感性資訊類型。 此方法可讓您使用您可以定期更新的安全資料庫來建立動態敏感性資訊類型。 請參閱[使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。

- **使用 PowerShell** 您可以使用 PowerShell 來設定自訂敏感性資訊類型。 雖然此方法比使用 UI 更複雜，但是您有多個組態選項。 請參閱[在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。



> [!NOTE]
> Microsoft 365 資訊保護目前在預覽版中支援下列雙位元組字元集語言：
> - 中文 (簡體)
> - 中文 (繁體)
> - 韓文
> - 日文

>這項支援適用於敏感性資訊類型。 如需詳細資訊，請參閱[資訊保護支援雙位元組字元集的版本資訊 (預覽版)](mip-dbcs-relnotes.md)。

## <a name="for-further-information"></a>進一步資訊
- [敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)
- [建立自訂的敏感性資訊類型](create-a-custom-sensitive-information-type.md)
- [在 PowerShell 中建立自訂的敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->