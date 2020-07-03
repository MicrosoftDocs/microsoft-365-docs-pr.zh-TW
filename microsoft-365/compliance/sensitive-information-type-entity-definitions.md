---
title: 敏感資訊類型實體定義
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 安全規範中心中的資料遺失防護（DLP） &amp; 包括80機密資訊類型，可供您在 DLP 原則中使用。 本主題列出所有敏感資訊類型，並顯示 DLP 原則在偵測到每種類型時所尋找的功能。
ms.openlocfilehash: a91459652d785f6536cb50e381ab139057a3eae8
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024641"
---
# <a name="sensitive-information-type-entity-definitions"></a>敏感資訊類型實體定義

規範中心的資料遺失防護（DLP）包含許多可供您在 DLP 原則中使用的機密資訊類型。 本主題列出所有敏感資訊類型，並顯示 DLP 原則在偵測到每種類型時所尋找的功能。 敏感資訊類型是由正則運算式或函數所識別的模式所定義。 此外，您也可以使用確切證據（如關鍵字及校驗和）來識別敏感資訊類型。 評估程式中也會使用信賴等級和近程。
  
## <a name="aba-routing-number"></a>ABA 路由號碼

### <a name="format"></a>格式

格式或未格式化的模式中的9位數

### <a name="pattern"></a>模式

格式 化：
- 以0、1、2、3、6、7或8開頭的四位數
- 連字號
- 四位數
- 連字號
- 一個數位

未格式化：9以0、1、2、3、6、7或8開頭的連續數位 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_aba_routing 找到符合模式的內容。
- 會找到來自 Keyword_ABA_Routing 的關鍵字。

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>關鍵字

#### <a name="keyword_aba_routing"></a>Keyword_ABA_Routing

- 阿壩
- 阿壩#
- aba 路由#
- aba 路由號碼
- 阿壩#
- abarouting#
- aba 編號
- abaroutingnumber
- 美洲銀行協會路由#
- 美洲銀行關聯性路由編號
- americanbankassociationrouting#
- americanbankassociationroutingnumber
- 銀行路由編號
- bankrouting#
- bankroutingnumber
- 路由轉口號碼
- RTN 
   
## <a name="argentina-national-identity-dni-number"></a>阿根廷國內身分識別（DNI）號碼

### <a name="format"></a>格式

以句點隔開的八位數

### <a name="pattern"></a>模式

八位數：
- 兩位數
- 一個句點
- 三位數
- 一個句點
- 三位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_argentina_national_id 找到符合模式的內容。
- 會找到來自 Keyword_argentina_national_id 的關鍵字。

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

- 阿根廷國內身分識別號碼 
- 身分識別 
- 身分識別的國內身分識別卡片 
- DNI 
- 個人的 NIC 註冊人員 
- Documento Nacional de Identidad 
- Registro Nacional de 拉斯維加斯角色 
- Identidad 
- Identificación 
   
## <a name="australia-bank-account-number"></a>澳大利亞銀行帳戶號碼

### <a name="format"></a>格式

包含或不含銀行狀態分公司號碼的6-10 位數

### <a name="pattern"></a>模式

帳戶號碼是6-10 位數。
澳大利亞銀行狀態分支編號：
- 三位數 
- 連字號 
- 三位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 Regex_australia_bank_account_number 找到符合模式的內容。
- 會找到來自 Keyword_australia_bank_account_number 的關鍵字。
- 正則運算式 Regex_australia_bank_account_number_bsb 找到符合模式的內容。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_australia_bank_account_number 找到符合模式的內容。
- 會找到來自 Keyword_australia_bank_account_number 的關鍵字。

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift 銀行代碼
- 通信銀行
- 基礎貨幣
- 美國帳戶
- 持有者位址
- 銀行位址
- 資訊帳戶
- 基金轉移
- 銀行費用
- 銀行詳細資料
- 銀行資訊
- 完整名稱
- 國際 原子能 機構

   
## <a name="australia-drivers-license-number"></a>澳大利亞駕駛執照號碼

### <a name="format"></a>格式

九個字母和數位

### <a name="pattern"></a>模式

九個字母和數位： 

- 兩位數或字母（不區分大小寫） 
- 兩位數 
- 五個數字或字母（不區分大小寫）

OR

- 1-2 選用的字母（不區分大小寫） 
- 4-9 位數

OR

- 九個數字或字母（不區分大小寫）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_australia_drivers_license_number 找到符合模式的內容。
- 會找到來自 Keyword_australia_drivers_license_number 的關鍵字。
- 找不到 Keyword_australia_drivers_license_number_exclusions 的關鍵字。

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- 國際動力允許
- 澳大利亞汽車協會
- 國際駕駛允許
- DriverLicence
- DriverLicences
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- DriversLic
- DriversLicence
- DriversLicences
- 驅動程式 .Lic
- 驅動程式 Lics
- 驅動程式許可證
- 驅動程式授權
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
- 驅動程式「.Lic
- 驅動程式 ' Lics
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- 驅動程式的 .Lic
- 驅動程式的 Lics
- 駕駛執照
- 駕駛執照
- DriverLic#
- DriverLics#
- DriverLicence#
- DriverLicences#
- 驅動程式許可證#
- 驅動程式 Lics#
- 驅動程式許可證#
- 驅動程式授權#
- DriversLic#
- DriversLics#
- DriversLicence#
- DriversLicences#
- 驅動程式 .Lic#
- 驅動程式 Lics#
- 驅動程式許可證#
- 驅動程式授權#
- Driver'Lic#
- Driver'Lics#
- Driver'Licence#
- Driver'Licences#
- 驅動程式「.Lic#
- 驅動程式 ' Lics#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- Driver'sLic#
- Driver'sLics#
- Driver'sLicence#
- Driver'sLicences#
- 驅動程式的 .Lic#
- 驅動程式的 Lics#
- 駕駛執照#
- 駕駛執照# 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- Aaa
- DriverLicense
- DriverLicenses
- 駕照
- 驅動程式授權
- DriversLicense
- DriversLicenses
- 驅動程式授權
- 驅動程式授權
- Driver'License
- Driver'Licenses
- 駕駛執照
- 驅動程式的授權
- Driver'sLicense
- Driver'sLicenses
- 駕駛執照
- 駕駛執照
- DriverLicense#
- DriverLicenses#
- 駕照#
- 驅動程式授權#
- DriversLicense#
- DriversLicenses#
- 驅動程式授權#
- 驅動程式授權#
- Driver'License#
- Driver'Licenses#
- 駕駛執照#
- 驅動程式的授權#
- Driver'sLicense#
- Driver'sLicenses#
- 駕駛執照#
- 駕駛執照#
   
## <a name="australia-medical-account-number"></a>澳大利亞醫療帳戶號碼

### <a name="format"></a>格式

10-11 位數

### <a name="pattern"></a>模式

10-11 位數：
- 第一個數位是在2-6 範圍內
- 第九位數是檢查碼
- 第十個數字是問題的位數
- 第十位數（選用）是個別數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：
- 函數 Func_australian_medical_account_number 找到符合模式的內容。
- 會找到來自 Keyword_Australia_Medical_Account_Number 的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_australian_medical_account_number 找到符合模式的內容。
- 校驗和通過。

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- 銀行帳戶詳細資料
- medicare 付款
- 抵押帳戶
- 銀行付款
- 資訊分支
- 信用卡貸款
- 人體服務部門
- 本機服務
- 醫療

   
## <a name="australia-passport-number"></a>澳大利亞護照號碼

### <a name="format"></a>格式

字母后接7位數

### <a name="pattern"></a>模式

字母（不區分大小寫）後接7位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_australia_passport_number 找到符合模式的內容。
- 會找到 Keyword_passport 或 Keyword_australia_passport_number 中的關鍵字。

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_passport"></a>Keyword_passport

- 護照號碼
- 護照否
- 護照#
- 護照#
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番號
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport 非
- Passeport#
- Passeport#
- PasseportNon
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- 護照
- 護照詳細資料
- immigration 與公民
- 澳大利亞英聯邦
- immigration 部門
- 住家住址
- immigration 和公民的部門
- 簽證
- 本國身分識別卡片
- 護照號碼
- 旅遊檔
- 頒發機構單位
   
## <a name="australia-tax-file-number"></a>澳大利亞稅收檔編號

### <a name="format"></a>格式

8-9 位數

### <a name="pattern"></a>模式

通常會以空格呈現的8-9 位數，如下所示：
- 三位數 
- 選擇性的空格 
- 三位數 
- 選擇性的空格 
- 最後一個數位是檢查碼的2-3 位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_australian_tax_file_number 找到符合模式的內容。
- 找不到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 的關鍵字。
- 校驗和通過。

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_tax_file_number"></a>Keyword_Australia_Tax_File_Number

- 澳大利亞商務電話號碼
- 邊際稅率
- medicare levy
- 產品群組編號
- 服務 veterans
- 預繳稅金
- 個人稅收返還
- 稅收檔案編號

#### <a name="keyword_number_exclusions"></a>Keyword_number_exclusions

- 00000000
- 11111111
- 22222222
- 33333333
- 44444444
- 55555555
- 66666666
- 77777777
- 88888888
- 99999999
- 000000000
- 111111111
- 222222222
- 333333333
- 444444444
- 555555555
- 666666666
- 777777777
- 888888888
- 999999999
- 0000000000
- 1111111111
- 2222222222
- 3333333333
- 4444444444
- 5555555555
- 6666666666
- 7777777777
- 8888888888
- 9999999999

## <a name="austria-drivers-license-number"></a>奧地利駕駛執照號碼
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

不含空格及分隔符號的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_austria_eu_driver's_license_number` 找到符合模式的內容。 
    
- 找到來自的關鍵字 `Keywords_austria_eu_driver's_license_number` 。 
    
```xml
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_austria_eu_driver ' s_license_number**
- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 駕駛執照
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- fuhrerschein
- fuhrerschein republik osterreich

## <a name="austria-national-identification-number"></a>奧地利國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

字母、數位及特殊字元的24個字元的組合
  
### <a name="pattern"></a>模式

24個字元：
  
-  22個字母（不區分大小寫）、數位、反斜線、正斜線或正號 
    
- 兩個字母（不區分大小寫）、數位、反斜線、正斜線、加號或等號
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_austria_eu_national_id_card` 找到符合模式的內容。 
    
- 找到來自的關鍵字 `Keywords_austria_eu_national_id_card` 。 
   
```xml
<!-- EU austria_eu_national_id -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- 身分識別號碼
- 國家識別碼
- personalausweis republik österreich

## <a name="austria-passport-number"></a>奧地利護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼 sensitiveinformation type。

### <a name="format"></a>格式

一個字母后接一個選擇性的空格和七位數
  
### <a name="pattern"></a>模式

一個字母、七位數和一個空格的組合：
  
- 一個字母（不區分大小寫）
    
- 一個空格（選用）
    
- 七位數
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_austria_eu_passport_number` 找到符合模式的內容。 
    
- 找到來自的關鍵字 `Keywords_austria_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_austria_eu_passport_number**
- 護照號碼
- 奧地利護照號碼
- 護照否
- reisepass
- österreichisch reisepass

## <a name="austria-social-security-number-or-equivalent-identification"></a>奧地利的社會安全號碼或同等身分識別
這個敏感資訊類型實體只有歐盟社會保險號碼或同等識別碼的敏感資訊類型提供。

### <a name="format"></a>格式

指定之格式的10位數
  
### <a name="pattern"></a>模式

10位數：
  
-  對應至序列值的三位數 
- 一個檢查碼
- 與出生日期對應的六位數（DDMMYY）
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_austria_eu_ssn_or_equivalent` 會找到符合模式的內容。 
    
- 找到來自的關鍵字 `Keywords_austria_eu_ssn_or_equivalent` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_austria_eu_ssn_or_equivalent` 會找到符合模式的內容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- 社會安全性否
- 社會安全號碼
- 社會安全性碼
- 保險號碼
- 奧地利 ssn
- Ssn#
- Ssn
- 保險業代碼
- 保險業代碼#
- socialsecurityno#
- sozialversicherungsnummer
- soziale sicherheit kein
- versicherungsnummer

## <a name="austria-tax-identification-number"></a>奧地利納稅識別號碼
這個敏感資訊類型實體只適用于歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

具有選擇性連字號及正斜線的九位數
  
### <a name="pattern"></a>模式

具有選擇性連字號及正斜線的九位數：
  
- 兩位數
- 連字號（選用）
- 三位數
- 一個正斜線（選用）
- 四位數
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_austria_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_austria_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_austria_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr。
- steuernummer
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- 納稅號碼

## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB 驗證金鑰

### <a name="format"></a>格式

字串 "DocumentDb"，後面加上下列模式中所述的字元及字串。

### <a name="pattern"></a>模式

- 字串 "DocumentDb"
- 介於3-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 大於符號（>）、等號（=）、引號（"）或撇號（'）
- 任何86的小寫字母或大寫字母、數位、正斜線（/）或加號（+）組合
- 兩個等號（=）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 CEP_Regex_AzureDocumentDBAuthKey 找到符合模式的內容。
- 正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）

- 尚未
- 送交
- 資料庫
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS 資料庫連接字串和 Azure SQL 連接字串

### <a name="format"></a>格式

字串 "Server"、"server" 或 "data source"，後面加上模式中所述的字元及字串（包括字串 "cloudapp"）。<!--no-hyperlink-->com "或" cloudapp。<!--no-hyperlink-->net "或" database。<!--no-hyperlink-->net "，及字串" Password "或" password "或" pwd "。

### <a name="pattern"></a>模式

- 字串「伺服器」、「伺服器」或「資料來源」
- 0-2 空白字元
- 等號（=）
- 0-2 空白字元
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "cloudapp"。<!--no-hyperlink-->com "，" cloudapp。<!--no-hyperlink-->net "或" database。<!--no-hyperlink-->真實
- 介於1-300 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "Password"、"password" 或 "pwd"
- 0-2 空白字元
- 等號（=）
- 0-2 空白字元
- 一個或多個字元，不是分號（;)、引號（"）或單引號（'）
- 分號（;)、引號（"）或撇號（'）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 CEP_Regex_AzureConnectionString 找到符合模式的內容。
- 正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）

- 尚未
- 送交
- 資料庫
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-iot-connection-string"></a>Azure IoT 連接字串

### <a name="format"></a>格式

字串 "HostName"，後面加上下列模式中所述的字元及字串，包括字串 "azure 裝置。<!--no-hyperlink-->net "和" SharedAccessKey "。

### <a name="pattern"></a>模式

- 字串 "HostName"
- 0-2 空白字元
- 等號（=）
- 0-2 空白字元
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- "Azure 裝置" 字串。<!--no-hyperlink-->真實
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "SharedAccessKey"
- 0-2 空白字元
- 等號（=）
- 0-2 空白字元
- 任何43的小寫字母或大寫字母、數位、正斜線（/）或加號（+）組合
- 等號（=）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 CEP_Regex_AzureIoTConnectionString 找到符合模式的內容。
- 正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）

- 尚未
- 送交
- 資料庫
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-publish-setting-password"></a>Azure 發佈設定密碼

### <a name="format"></a>格式

字串 "userpwd ="，後面加上字母元字串。

### <a name="pattern"></a>模式

- 字串 "userpwd ="
- 任何60小寫字母或數位的組合
- 引號（"）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 CEP_Regex_AzurePublishSettingPasswords 找到符合模式的內容。
- 正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）

- 尚未
- 送交
- 資料庫
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-redis-cache-connection-string"></a>Azure Redis cache connection string

### <a name="format"></a>格式

字串 "redis。<!--no-hyperlink-->net "後接下列模式中所述的字元和字串，包含字串" password "或" pwd "。

### <a name="pattern"></a>模式

- 字串 "redis。<!--no-hyperlink-->真實
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "password" 或 "pwd"
- 0-2 空白字元
- 等號（=）
- 0-2 空白字元
- 43個字元的任何組合，其為小寫或大寫字母、數位、正斜線（/）或加號（+）
- 等號（=）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 CEP_Regex_AzureRedisCacheConnectionString 找到符合模式的內容。
- 正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）

- 尚未
- 送交
- 資料庫
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>格式

字串 "sig"，後面加上下列模式中所述的字元及字串。

### <a name="pattern"></a>模式

- 字串 "sig"
- 0-2 空白字元
- 等號（=）
- 0-2 空白字元
- 介於43-53 個字元、小寫字母、數位或百分比符號（%）之間的任何組合
- 字串 "% 三維"
- 非小寫或大寫字母、數位或百分號（%）以外的任何字元

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 CEP_Regex_AzureSAS 找到符合模式的內容。

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure 服務匯流排連接字串

### <a name="format"></a>格式

字串 "EndPoint" 後接下列模式中所述的字元及字串，包含字串 "<!--no-hyperlink-->net "和" SharedAccesKey "。

### <a name="pattern"></a>模式

- 字串 "EndPoint"
- 0-2 空白字元
- 等號（=）
- 0-2 空白字元
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "<!--no-hyperlink-->真實
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "SharedAccessKey"
- 0-2 空白字元
- 等號（=）
- 0-2 空白字元
- 43個字元的任何組合，其為小寫或大寫字母、數位、正斜線（/）或加號（+）
- 等號（=）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 CEP_Regex_AzureServiceBusConnectionString 找到符合模式的內容。
- 正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）

- 尚未
- 送交
- 資料庫
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-storage-account-key"></a>Azure 儲存體帳戶金鑰

### <a name="format"></a>格式

字串 "DefaultEndpointsProtocol"，後面加上下列模式中所述的字元及字串（包括字串 "AccountKey"）。

### <a name="pattern"></a>模式

- 字串 "DefaultEndpointsProtocol"
- 0-2 空白字元
- 等號（=）
- 0-2 空白字元
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "AccountKey"
- 0-2 空白字元
- 等號（=）
- 0-2 空白字元
- 86個字元的任何組合，其為小寫或大寫字母、數位、正斜線（/）或加號（+）
- 兩個等號（=）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 CEP_Regex_AzureStorageAccountKey 找到符合模式的內容。
- 正則運算式**CEP_AzureEmulatorStorageAccountFilter 不會找到符合**模式的內容。
- 正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_azureemulatorstorageaccountfilter"></a>CEP_AzureEmulatorStorageAccountFilter

（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）

- 尚未
- 送交
- 資料庫
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-storage-account-key-generic"></a>Azure 儲存體帳戶金鑰（一般）

### <a name="format"></a>格式

任何86的小寫字母或大寫字母、數位、正斜線（/）或加號（+）的組合，前置或後接下列模式中所述的字元。

### <a name="pattern"></a>模式

- 大於符號（>）、撇號（'）、等號（=）、引號（"）或數位記號（#）的0-1
- 86個字元的任何組合（低或大寫字母、數位、正斜線（/）或加號（+））
- 兩個等號（=）


### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 CEP_Regex_AzureStorageAccountKeyGeneric 找到符合模式的內容。

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>比利時駕駛執照號碼
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

10位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

10位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_belgium_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_belgium_eu_driver's_license_number` 。
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords__belgium_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- rijbewijs
- rijbewijsnummer
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein-nr
- fuehrerschein-Nr
- fuehrerschein-nr

## <a name="belgium-national-number"></a>比利時國號碼
這種敏感資訊類型的實體包含在歐盟國身分識別號碼機密資訊類型中，並可作為獨立的機密資訊類型實體。

### <a name="format"></a>格式

11位數加上分隔符號

### <a name="pattern"></a>模式

11位數加上分隔符號：
- 以 YY 格式表示的六位數和兩個句點。毫米。出生日期的 DD 
- 連字號 
- 三個連續數位（奇數用於男生，即便是女生） 
- 一個句點 
- 兩位數的檢查碼

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_belgium_national_number 找到符合模式的內容。
- 會找到來自 Keyword_belgium_national_number 的關鍵字。
- 校驗和通過。

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- 安娜#
- 安娜
- 購買 d'identité
- 本國 identifiant
- identifiantnational#
- identificatie
- 識別
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- 身份
- 題詞
- 國家/地區號碼
- 本國收銀機
- nationalnumber#
- nationalnumber
- Nif#
- Nif
- numéro d'assuré
- numéro de registre （本國）
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- 本國 numéro
- numéronational#
- 個人號碼
- personalausweis
- personalidnumber#
- registratie
- 註冊
- registrationsnumme
- registrierung
- 社會安全號碼
- Ssn#
- Ssn
- steuernummer
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#

## <a name="belgium-passport-number"></a>比利時護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

兩個字母后接六位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母后接六位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_belgium_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_belgium_eu_passport_number` 。

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_belgium_eu_passport_number**
- 護照號碼
- 比利時護照號碼
- 護照否
- paspoort
- paspoortnummer
- reisepass kein
- reisepass

## <a name="belgium-social-security-number-or-equivalent-identification"></a>比利時社會安全號碼或對等身分識別
這個敏感資訊類型實體只有歐盟社會保險號碼或同等識別碼的敏感資訊類型提供。

### <a name="format"></a>格式

11位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

11位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_belgium_eu_ssn_or_equivalent` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_belgium_eu_ssn_or_equivalent` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_belgium_eu_ssn_or_equivalent` 會找到符合模式的內容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

- 比利時國號碼
- 國家/地區號碼
- 社會安全號碼
- nationalnumber#
- Ssn#
- Ssn
- nationalnumber
- 安娜#
- 安娜
- 個人號碼
- personalidnumber#
- 本國 numéro
- numéro de sécurité
- numéro d'assuré
- 本國 identifiant
- identifiantnational#
- numéronational#

## <a name="belgium-tax-identification-number"></a>比利時納稅識別號碼
這個敏感資訊類型實體只適用于歐盟稅收 Identificaiton 號碼機密資訊類型。

### <a name="format"></a>格式

11位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

11位數：
  
- 兩位數
- "0" 或 "1"
- 一個數位
- "0" 或 "1" 或 "2" 或 "3" 
- 六位數
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_belgium_eu_tax_file_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_belgium_eu_tax_file_number` 。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_belgium_eu_tax_file_number"></a>Keywords_belgium_eu_tax_file_number

- belasting aantal
- 安娜#
- 安娜
- 購買 d'identité
- 本國 identifiant
- identifiantnational#
- identificatie
- 識別
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- 身份
- 題詞
- 國家/地區號碼
- 本國收銀機
- nationalnumber#
- nationalnumber
- Nif#
- Nif
- numéro d'assuré
- numéro de registre （本國）
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- 本國 numéro
- numéronational#
- 個人號碼
- personalausweis
- personalidnumber#
- registratie
- 註冊
- registrationsnumme
- registrierung
- 社會安全號碼
- Ssn#
- Ssn
- steuernummer
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#


## <a name="brazil-cpf-number"></a>巴西 CPF 號碼

### <a name="format"></a>格式

11位數包含檢查碼，可格式化或未格式化

### <a name="pattern"></a>模式

格式 化：
- 三位數
- 一個句點
- 三位數
- 一個句點
- 三位數
- 連字號
- 兩位數的檢查碼

非
- 11位數的最後兩位數的檢查碼

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_brazil_cpf 找到符合模式的內容。
- 會找到來自 Keyword_brazil_cpf 的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_brazil_cpf 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- 公積金
- 識別
- 註冊
- 收入
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 
   
## <a name="brazil-legal-entity-number-cnpj"></a>巴西法律實體編號（CNPJ）

### <a name="format"></a>格式

14位數包含登記編號、分支編號及檢查數位，加上分隔符號

### <a name="pattern"></a>模式
14位數，加上分隔符號：
- 兩位數 
- 一個句點 
- 三位數 
- 一個句點 
- 三位數（前八位數為註冊碼） 
- 一個正斜線 
- 四位數的分支編號 
- 連字號 
- 兩位數的檢查碼

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_brazil_cnpj 找到符合模式的內容。
- 會找到來自 Keyword_brazil_cnpj 的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_brazil_cnpj 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ 
- CNPJ/MF 
- CNPJ-MF 
- 法律實體的本國登錄 
- Taxpayers 登錄 
- 法律實體 
- 法律實體 
- 註冊狀態 
- 商務版 
- Company
- CNPJ 
- Cadastro Nacional da Pessoa Jurídica 
- Cadastro Geral de Contribuintes 
- CGC 
- Pessoa jurídica 
- Pessoas jurídicas 
- Situação cadastral 
- Inscrição 
- Empresa 
   
## <a name="brazil-national-identification-card-rg"></a>巴西國身分識別卡（RG）

### <a name="format"></a>格式

Registro Geral （舊格式）：九位數

Registro de Identidade （RIC）（新格式）：11位數

### <a name="pattern"></a>模式

Registro Geral （舊格式）：
- 兩位數 
- 一個句點 
- 三位數 
- 一個句點 
- 三位數 
- 連字號 
- 一位數的檢查碼

Registro de Identidade （RIC）（新格式）：
- 10位數 
- 連字號 
- 一位數的檢查碼

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_brazil_rg 找到符合模式的內容。
- 會找到來自 Keyword_brazil_rg 的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_brazil_rg 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- 身份證
- 國家識別碼 
- número de rregistro
- registro de Iidentidade 
- registro geral
- RG （此關鍵字區分大小寫） 
- RIC （此關鍵字區分大小寫） 


## <a name="bulgaria-drivers-license-number"></a>保加利亞駕駛執照號碼
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_bulgaria_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_bulgaria_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    
```

### <a name="keywords"></a>關鍵字

**Keywords_bulgaria_eu_driver ' s_license_number**
- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка

## <a name="bulgaria-national-identification-number"></a>保加利亞國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

10位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

10位數，不含空格及分隔符號
  
- 與出生日期對應的六位數（YYMMDD） 
- 對應至出生順序的兩位數
- 對應于性別的一個數位：用於男的偶數位數和用於女的奇數數位
- 一個檢查碼

### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_bulgaria_eu_national_id_card` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_bulgaria_national_number` 。 

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_bulgaria_eu_national_id_card` 會找到符合模式的內容。 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_bulgaria_national_number"></a>Keywords_bulgaria_national_number

- 安娜#
- 安娜
- bucn#
- bucn
- edinen grazhdanski nomer
- egn#
- egn
- 識別號碼
- 國家識別碼
- 國家/地區號碼
- nationalnumber#
- nationalnumber
- 個人識別碼
- 個人編號
- 個人號碼
- personalidnumber#
- 社會安全號碼
- Ssn#
- Ssn
- 統一的民事識別碼
- 統一的民事未
- 統一的民事編號
- uniformcivilno#
- uniformcivilno
- uniformcivilnumber#
- uniformcivilnumber
- 獨特的公民人數
- егн#
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ識別碼
- униформграждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid#
- униформгражданскине.#

## <a name="bulgaria-passport-number"></a>保加利亞護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_bulgaria_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_bulgaria_eu_passport_number` 。 

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>關鍵字

**Keywords_bulgaria_eu_passport_number**
- 護照號碼
- 保加利亞文護照號碼
- 護照否
- номер на паспорта

## <a name="bulgaria-tax-identification-number"></a>保加利亞納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

10位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

10位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_bulgaria_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_bulgaria_eu_tax_file_number` 。 

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_bulgaria_eu_tax_file_number` 會找到符合模式的內容。 

```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_bulgaria_eu_tax_file_number"></a>Keywords_bulgaria_eu_tax_file_number
- 安娜#
- 安娜
- bucn#
- bucn
- edinen grazhdanski nomer
- egn#
- egn
- 識別號碼
- 國家識別碼
- 國家/地區號碼
- nationalnumber#
- nationalnumber
- 個人識別碼
- 個人編號
- 個人號碼
- personalidnumber#
- 社會安全號碼
- Ssn#
- Ssn
- 統一的民事識別碼
- 統一的民事未
- 統一的民事編號
- uniformcivilno#
- uniformcivilno
- uniformcivilnumber#
- uniformcivilnumber
- 獨特的公民人數
- егн#
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ識別碼
- униформграждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid#
- униформгражданскине.#


## <a name="canada-bank-account-number"></a>加拿大銀行帳戶號碼

### <a name="format"></a>格式

七位數或十二位數

### <a name="pattern"></a>模式

加拿大銀行帳戶號碼為七位數或十二位數。

加拿大銀行帳戶中轉號碼為：
- 五位數 
- 連字號 
- 三位數或
- 零 "0" 
- 八位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 Regex_canada_bank_account_number 找到符合模式的內容。
- 會找到來自 Keyword_canada_bank_account_number 的關鍵字。
- 正則運算式 Regex_canada_bank_account_transit_number 找到符合模式的內容。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 Regex_canada_bank_account_number 找到符合模式的內容。
- 會找到來自 Keyword_canada_bank_account_number 的關鍵字。

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- 加拿大節約 bonds
- 加拿大收入代理商
- 加拿大金融機構
- 直接存放表單
- 加拿大公民
- 法律代表
- 公證
- oaths 的英國專員辦公室
- 兒童護理權益
- 通用子級護理
- 加拿大子稅務權益
- 所得稅權益
- 已調和銷售稅
- 社交保險號碼
- 所得稅退款
- 子稅務權益
- territorial 付款
- 機構號碼
- 放入要求
- 銀行資訊
- 直接存款
   
## <a name="canada-drivers-license-number"></a>加拿大駕駛執照號碼

### <a name="format"></a>格式

依省份

### <a name="pattern"></a>模式

涵蓋 Alberta、英屬哥倫比亞、Manitoba、新的 Brunswick、Newfoundland/Labrador、Nova Scotia、安大略、Prince Edward 孤島、魁北克和薩斯的各種模式

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_ [province_name] _drivers_license_number 找到符合模式的內容。
- 找到來自 Keyword_ [province_name] _drivers_license_name 的關鍵字。
- 會找到來自 Keyword_canada_drivers_license 的關鍵字。

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_ [province_name] _drivers_license_name

- 省/直轄市縮寫，例如 AB
- 省/市名稱，例如 Alberta

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- Dl
- Dls
- 民盟
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- 驅動程式許可證
- 驅動程式 Lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- 驅動程式 .Lic
- 驅動程式 Lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- 驅動程式「.Lic
- 驅動程式 ' Lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- 驅動程式的 .Lic
- 驅動程式的 Lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Permis de Conduire
- id
- Id
- idcard 編號
- idcard 編號
- idcard#
- idcard #s
- idcard 卡片
- idcard 卡片
- idcard
- 識別號碼
- 識別號碼
- 識別#
- 識別 #s
- 身分識別卡
- 身份證
- 識別 
- Dl#
- Dls# 
- 民盟# 
- CDLS# 
- DriverLic# 
- DriverLics# 
- DriverLicense# 
- DriverLicenses# 
- DriverLicence# 
- DriverLicences# 
- 驅動程式許可證#
- 驅動程式 Lics# 
- 駕照# 
- 驅動程式授權# 
- 駕照# 
- 驅動程式授權# 
- DriversLic# 
- DriversLics# 
- DriversLicense# 
- DriversLicenses# 
- DriversLicence# 
- DriversLicences# 
- 驅動程式 .Lic# 
- 驅動程式 Lics# 
- 驅動程式授權# 
- 驅動程式授權# 
- 驅動程式許可證# 
- 驅動程式授權# 
- Driver'Lic# 
- Driver'Lics# 
- Driver'License# 
- Driver'Licenses# 
- Driver'Licence# 
- Driver'Licences# 
- 驅動程式「.Lic# 
- 驅動程式 ' Lics# 
- 駕駛執照# 
- 驅動程式的授權# 
- 驅動程式 ' 許可證# 
- 驅動程式 ' 授權# 
- Driver'sLic# 
- Driver'sLics# 
- Driver'sLicense# 
- Driver'sLicenses# 
- Driver'sLicence# 
- Driver'sLicences# 
- 驅動程式的 .Lic# 
- 驅動程式的 Lics# 
- 駕駛執照# 
- 駕駛執照# 
- 駕駛執照# 
- 駕駛執照# 
- Permis de Conduire# 
- Id# 
- Id# 
- idcard 卡片# 
- idcard 卡片# 
- idcard# 
- 身分識別卡# 
- 身份證# 
- 識別# 
   
## <a name="canada-health-service-number"></a>加拿大健康情況服務號碼

### <a name="format"></a>格式

10位數

### <a name="pattern"></a>模式

10位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_canada_health_service_number 找到符合模式的內容。
- 會找到來自 Keyword_canada_health_service_number 的關鍵字。

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- 個人健康號碼
- 患者資訊
- 健康情況服務
- speciality 服務
- 汽車意外
- 病人醫院
- 心理醫生
- 工作人員薪酬
- 殘疾
      
## <a name="canada-passport-number"></a>加拿大護照號碼

### <a name="format"></a>格式

兩個大寫字母後接六位數

### <a name="pattern"></a>模式

兩個大寫字母後接六位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_canada_passport_number 找到符合模式的內容。
- 會找到 Keyword_canada_passport_number 或 Keyword_passport 中的關鍵字。

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- 加拿大公民
- 加拿大護照
- 護照應用程式
- 護照相片
- 認證的翻譯員
- 加拿大公民
- 處理時間
- 更新應用程式

#### <a name="keyword_passport"></a>Keyword_passport

- 護照號碼
- 護照否
- 護照#
- 護照#
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番號
- パスポートのNum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport 非
- Passeport#
- Passeport#
- PasseportNon
- Passeportn °
   
## <a name="canada-personal-health-identification-number-phin"></a>加拿大個人健康身分識別號碼（PHIN）

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：正則運算式 Regex_canada_phin 找到符合模式的內容。
至少會找到兩個 Keyword_canada_phin 或 Keyword_canada_provinces 中的關鍵字。

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- 社交保險號碼
- 狀況資訊法案
- 所得稅資訊
- manitoba 健康情況
- 健康情況登記
- 處方購買
- 效益資格
- 個人健康情況
- 律師的權力
- 登記編號
- 個人健康號碼
- practitioner 參照
- wellness 專業版
- 患者參考
- 健康情況與 wellness

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- Nunavut
- 魁北克
- 西北領地
- 安大略省
- 不列顛哥倫比亞省
- 阿爾比省
- 薩斯喀徹爾省
- 馬尼托巴省
- 育 空
- 紐芬蘭和 Labrador
- 新不倫瑞克省
- 新斯科舍省
- 艾德華王子島
- 加拿大
   
## <a name="canada-social-insurance-number"></a>加拿大社交保險號碼

### <a name="format"></a>格式

具有選擇性連字號或空格的九位數

### <a name="pattern"></a>模式

格式 化：
- 三位數 
- 連字號或空格 
- 三位數 
- 連字號或空格 
- 三位數

未格式化：九位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_canadian_sin 找到符合模式的內容。
- 下列其中一種組合，至少有兩種：
    - 會找到來自 Keyword_sin 的關鍵字。
    - 會找到來自 Keyword_sin_collaborative 的關鍵字。
    - 函數 Func_eu_date 會找到正確日期格式的日期。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_unformatted_canadian_sin 找到符合模式的內容。
- 會找到來自 Keyword_sin 的關鍵字。
- 校驗和通過。

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_sin"></a>Keyword_sin

- 罪 
- 社交保險 
- numero d'assurance sociale 
- 罪 
- Ssn 
- 主旨 ssn 
- 社會保障 
- numero d'assurance 社交 
- 國家識別號碼 
- 國家識別碼 
- 罪# 
- soc ins 
- 社交 ins 

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- 駕駛執照 
- 驅動程式授權 
- 駕駛執照 
- 驅動程式許可證 
- DOB 
- 出生日期 
- 生日 
- 出生日期 
   
## <a name="chile-identity-card-number"></a>智利身分識別卡號碼

### <a name="format"></a>格式

7-8 位數加上分隔符號 a check digits 或字母

### <a name="pattern"></a>模式

7-8 位數加上分隔符號：
- 1-2 位數 
- 一個句點 
- 三位數 
- 一個句點 
- 三位數 
- 虛線 
- 一個數位或字母（不區分大小寫），這是一種檢查碼

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_chile_id_card 找到符合模式的內容。
- 會找到來自 Keyword_chile_id_card 的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_chile_id_card 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- 國家識別號碼 
- 身份證 
- ID 
- 識別 
- Rol Único Nacional 
- 運行 
- Rol Único Tributario 
- 車轍 
- Cédula de Identidad 
- Número De Identificación Nacional 
- Tarjeta de identificación 
- Identificación 
   
## <a name="china-resident-identity-card-prc-number"></a>中國居民身分識別卡片（中國）號碼

### <a name="format"></a>格式

18位數

### <a name="pattern"></a>模式

18位數：
- 六位數的位址碼 
- 在 YYYYMMDD 中的八位數（出生日期） 
- 三位數的訂單碼 
- 一位數的檢查碼

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_china_resident_id 找到符合模式的內容。
- 會找到來自 Keyword_china_resident_id 的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_china_resident_id 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- 常駐身分識別卡 
- 中國 
- 全國身分識別卡 
- 身份證 
- 居民 身份證 
- 居民身份證 
- 鑒定 
- 身分證 
- 居民 身份證
- 鑑定 
   
## <a name="credit-card-number"></a>信用卡號碼

### <a name="format"></a>格式

14至16位數，可格式化或未格式化（dddddddddddddddd），且必須透過 Luhn 測試。

### <a name="pattern"></a>模式

非常複雜且健全的模式，可偵測全球所有主要品牌的卡，包括簽證、MasterCard、探索卡、JCB、美洲 Express、禮品卡和 diner 卡。

### <a name="checksum"></a>校驗

是，Luhn 檢查碼

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_credit_card 找到符合模式的內容。
- 下列其中一項為真：
    - 會找到來自 Keyword_cc_verification 的關鍵字。
    - 會找到來自 Keyword_cc_name 的關鍵字。
    - 函數 Func_expiration_date 會找到正確日期格式的日期。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：
- 函數 Func_credit_card 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- 名片驗證
- 卡片識別碼
- cvn
- cid
- cvc2
- cvv2
- pin 區區塊
- 安全性代碼
- 安全性號碼
- 安全性否
- 發行編號
- 問題否
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- Cod。 sicurezza
- 貨至 sicurezza
- n autorizzazione
- código
- codigo
- Cod。 Seg
- 貨至 seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. segurança
- Cod。 seguranca 貨。 segurança
- cód. seguranca
- cód segurança
- 貨至付款 seguranca，segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- 資料 scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- 資料 de expiração
- 資料 de expiracao
- 資料 em mail.que expira
- validade
- 勇氣
- vencimento
- Venc 

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- 美洲 express
- americanexpress
- 簽證
- 萬事 達
- 主卡
- Mc 
- mastercards
- 主卡
- diner 俱樂部
- diners 俱樂部
- dinersclub
- 探索卡片
- discovercard
- 探索卡片
- JCB
- 日本卡片局
- 購買 blanche
- carteblanche
- 信用卡
- Cc#
- 抄送 #：
- 有效期
- 到期日
- 有效期
- 日期 d'expiration
- 日期 d'exp
- 到期日
- 銀行卡
- bankcard
- 卡號碼
- 卡號
- cardnumber
- cardnumbers
- 卡號碼
- creditcard
- 信用卡
- creditcards
- ccn
- 持卡人
- 持 卡 人
- 持卡人
- 持 卡 人
- 檢查卡片
- checkcard
- 檢查卡片
- checkcards
- 轉帳卡
- debitcard
- 轉帳卡
- debitcards
- atm 卡
- atmcard
- atm 卡
- atmcards
- enroute
- 途中
- 卡片類型
- 購買 bancaire
- 反 crédit
- 購買退款
- numéro 的重複購買
- numero 的重複購買
- de 照購買
- 消除購買的 n º
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr 
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- 憲章
- n carta
- 星期日。 憲章
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- 消除 tarjeta 的 n º
- 不。 de tarjeta
- 無 de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta 否
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número 執行 cartão
- numero 執行 cartão 
- número 執行 cartao
- numero 執行 cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- n º do cartão
- n º do cartao
- n º。 執行 cartão
- 無 do cartão
- 無 do cartao
- 不。 執行 cartão
- 不。 執行 cartao 

## <a name="croatia-drivers-license-number"></a>克羅地亞駕駛執照號碼
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

不含空格及分隔符號的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_croatia_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_croatia_eu_driver's_license_number` 。 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_croatia_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- vozačka dozvola

## <a name="croatia-identity-card-number"></a>克羅地亞身分識別卡號碼
這種敏感資訊類型的實體包含在歐盟國身分識別號碼機密資訊類型中，並可作為獨立的機密資訊類型實體。


### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_croatia_id_card 找到符合模式的內容。
- 會找到來自 Keyword_croatia_id_card 的關鍵字。

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- 主機公民號碼
- nacionalni identifikacijski broj
- 國家識別號碼
- oib#
- oib
- osobna iskaznica
- osobni 識別碼
- osobni identifikacijski broj
- 個人身分識別號碼
- porezni broj
- porezni identifikacijski broj
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#

## <a name="croatia-passport-number"></a>克羅地亞護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_croatia_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_croatia_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>關鍵字

**Keywords_croatia_eu_passport_number**

- 護照號碼
- 克羅地亞護照號碼
- 護照否
- broj putovnice

   
## <a name="croatia-personal-identification-oib-number"></a>克羅地亞個人身分識別（OIB）號碼

### <a name="format"></a>格式

11位數

### <a name="pattern"></a>模式

11位數：
- 10位數 
- 最後一個數位是檢查碼用於國際資料交換的目的，在11位數之前新增字母「HR」。

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_croatia_oib_number 找到符合模式的內容。
- 會找到來自 Keyword_croatia_oib_number 的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_croatia_oib_number 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- 個人身分識別號碼
- Osobni identifikacijski broj 
- OIB 

## <a name="croatia-social-security-number-or-equivalent-identification"></a>克羅地亞社會安全號碼或同等身分識別
這個敏感資訊類型實體只有歐盟社會保險號碼或同等識別碼的敏感資訊類型提供。

### <a name="format"></a>格式

11位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 11位數：
  
- 10位數
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_croatia_eu_ssn_or_equivalent` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_croatia_eu_ssn_or_equivalent` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_croatia_eu_ssn_or_equivalent` 會找到符合模式的內容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

- 個人身分識別號碼
- 主機公民號碼
- 國家識別號碼
- 社會安全號碼
- nationalnumber#
- Ssn#
- Ssn
- nationalnumber
- 安娜#
- 安娜
- 個人號碼
- personalidnumber#
- oib
- osobni identifikacijski broj
   
## <a name="croatia-tax-identification-number"></a>克羅地亞納稅識別號碼
這個敏感資訊類型實體只適用于歐盟稅收 Identificaiton 號碼機密資訊類型。

### <a name="format"></a>格式

11位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

11位數：
  
- 10位數（隨機播放）
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_croatia_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_croatia_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_croatia_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_croatia_eu_tax_file_number"></a>Keywords_croatia_eu_tax_file_number

- majstorski broj građana
- 主機公民號碼
- nacionalni identifikacijski broj
- 國家識別號碼
- oib#
- oib
- osobna iskaznica
- osobni 識別碼
- osobni identifikacijski broj
- 個人身分識別號碼
- porezni broj
- porezni identifikacijski broj
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#

## <a name="cyprus-drivers-license-number"></a>賽普勒斯驅動程式授權號碼
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

12位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

12位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_cyprus_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_cyprus_eu_driver's_license_number` 。

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_cyprus_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- άδεια οδήγησης

## <a name="cyprus-national-identification-number"></a>賽普勒斯國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

10位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 10位數 
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_cyprus_eu_national_id_card` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_cyprus_eu_national_id_card` 。 
    
```xml 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- id 卡號碼
- 身分識別卡號碼
- kimlik karti
- 國家識別號碼
- 個人號碼
- ταυτοτητασ

## <a name="cyprus-passport-number"></a>賽普勒斯護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

一個字母后接6-8 位數，沒有空格或分隔符號
  
### <a name="pattern"></a>模式

一個字母后接六個到八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_cyprus_eu_passport_number` 找到符合模式的內容。
- 找到來自的關鍵字 `Keywords_cyprus_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_cyprus_eu_passport_number**

- 護照號碼
- 賽普勒斯護照號碼
- 護照否
- αριθμό διαβατηρίου

## <a name="cyprus-tax-identification-number"></a>賽普勒斯納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

指定的模式中的八位數和一個字母
  
### <a name="pattern"></a>模式

八位數和一個字母：
  
-  為 "0" 
- 七位數
- 一個字母（不區分大小寫）
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_cyprus_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_cyprus_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_cyprus_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- 納稅識別碼
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 旅遊業 議會#
- 旅遊業 議會
- 納稅人識別碼
- tin no
- 錫#
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού
- 納稅號碼

## <a name="czech-drivers-license-number"></a>捷克文駕駛執照號碼
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

兩個字母后接六位數
  
### <a name="pattern"></a>模式

8個字母和數位：
  
- 兩個字母（不區分大小寫）
- 一個空格（選用）
- 六位數

### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_czech_republic_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_czech_republic_eu_driver's_license_number` 。 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>關鍵字

**Keywords_czech_republic_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- řidičský prúkaz

## <a name="czech-passport-number"></a>捷克護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

不含空格或分隔符號的八位數
  
### <a name="pattern"></a>模式

不含空格或分隔符號的八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_czech_republic_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_czech_republic_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_czech_republic_eu_passport_number**

- 護照號碼
- 捷克護照號碼
- 護照否
- cestovní pas
- Pas

## <a name="czech-personal-identity-number"></a>捷克個人身分識別號碼
這種機密資訊類型的實體包含在歐盟的身分識別號碼束中，並可作為獨立的敏感資訊類型實體。

### <a name="format"></a>格式

具有選用正斜線的九位數（舊格式）10位數（選用反斜線（新格式））

### <a name="pattern"></a>模式

九位數（舊格式）：
- 九位數

OR

- 六位數代表出生日期
- 一個正斜線
- 三位數

10位數（新格式）：
- 10位數

OR

- 六位數代表出生日期
- 一個正斜線 
- 最後一個數位是檢查碼的四位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：函數 Func_czech_id_card 找到符合模式的內容。
會找到來自 Keyword_czech_id_card 的關鍵字。
校驗和通過。

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a>關鍵字

- 捷克個人身分識別號碼
- Rodné číslo



## <a name="czech-social-security-number-or-equivalent-identification"></a>捷克社會安全號碼或同等身分識別
這個敏感資訊類型實體只有歐盟社會保險號碼或同等識別碼的敏感資訊類型提供。

### <a name="format"></a>格式

指定之模式中的10位數和反斜線
  
### <a name="pattern"></a>模式

10位數和反斜線：
  
- 對應至出生日期的六位數（YYMMDD）： 
    
- 反斜線
    
- 三位數的數位，對應至在相同日期出生的人員
    
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_czech_republic_eu_ssn_or_equivalent` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_czech_republic_eu_ssn_or_equivalent` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_czech_republic_eu_ssn_or_equivalent` 會找到符合模式的內容。 

```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

- 出生號碼
- 國家識別號碼
- 個人身分識別號碼
- 社會安全號碼
- nationalnumber#
- Ssn#
- Ssn
- 國家/地區號碼
- 個人號碼
- personalidnumber#
- rč
- rodné číslo
- rodne cislo

## <a name="czech-tax-identification-number"></a>捷克納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

九位數和10位數（選用反斜線）
  
### <a name="pattern"></a>模式

九位數或十位數，具有選用的 backslashl：
  
- 六位數 
- 反斜線（選用）
- 三位數或四位數
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_czech_republic_eu_tax_file_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_czech_republic_eu_tax_file_number` 。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_czech_republic_eu_tax_file_number"></a>Keywords_czech_republic_eu_tax_file_number

- 捷克共和國識別碼
- czechidno#
- daňové číslo
- identifikační číslo
- identity no
- 身分識別號碼
- identityno#
- identityno
- 保險號碼
- 國家識別號碼
- 國家/地區號碼
- osobní číslo
- 個人號碼
- 個人號碼
- Pid#
- PID
- pojištění číslo
- rodné číslo
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- 唯一識別碼
- 納稅號碼

## <a name="denmark-drivers-license-number"></a>丹麥駕照編號
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

不含空格及分隔符號的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_denmark_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_denmark_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_denmark_eu_driver ' s_license_number**

- | dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>丹麥護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_denmark_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_denmark_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_denmark_eu_passport_number**

- 護照號碼
- 丹麥文護照號碼
- 護照否
- Pas
- pasnummer

## <a name="denmark-personal-identification-number"></a>丹麥個人身分識別號碼
這種敏感資訊類型的實體包含在歐盟國身分識別號碼機密資訊類型中，並可作為獨立的機密資訊類型實體。

### <a name="format"></a>格式

10位數包含連字號

### <a name="pattern"></a>模式

10位數：
- DDMMYY 之日期格式的六位數 
- 連字號 
- 四位數的最後一個數位是檢查碼

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：正則運算式 Regex_denmark_id 找到符合模式的內容。
會找到來自 Keyword_denmark_id 的關鍵字。
校驗和通過。

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- Cpr
- Cpr#
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- 健康情況卡片
- 健康情況保險卡號碼
- 健康情況保險號碼
- 識別號碼
- identifikationsnummer
- identifikationsnummer#
- 身分識別號碼
- krankenkassennummer
- nationalid#
- personalidentityno#
- personnummer
- personnummer#
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- skat 識別碼
- skat kode
- skat nummer
- skattenummer
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- 稅碼
- 旅遊健康情況保險卡
- uniqueidentityno#
- 納稅號碼
- 稅務登記編號
- 納稅識別碼
- 納稅識別號碼
- taxid#
- taxnumber#
- 納稅否
- taxno#
- taxnumber
- 納稅識別碼否
- 錫#
- taxidno#
- taxidnumber#
- 納稅否#
- 納稅人識別碼
- tin no

## <a name="denmark-social-security-number-or-equivalent-identification"></a>丹麥社會安全號碼或對等身分識別
這個敏感資訊類型實體只有歐盟社會保險號碼或同等識別碼的敏感資訊類型。

### <a name="format"></a>格式

在指定的模式中，10位數和連字號
  
### <a name="pattern"></a>模式

10位數和連字號：
  
- 與出生日期對應的六位數（DDMMYY） 
- 連字號
- 對應至序號的四位數
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_denmark_eu_ssn_or_equivalent` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_denmark_eu_ssn_or_equivalent` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_denmark_eu_ssn_or_equivalent` 會找到符合模式的內容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

- 個人身分識別號碼
- 國家識別號碼
- 社會安全號碼
- nationalnumber#
- Ssn#
- Ssn
- 國家/地區號碼
- 個人號碼
- personalidnumber#
- cpr-nummer
- personnummer

## <a name="denmark-tax-identification-number"></a>丹麥納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

10位數包含連字號
  
### <a name="pattern"></a>模式

10位數包含 hyphenl：
  
-  與出生日期對應的六位數（DDMMYY）
- 連字號
- 四位數的數位，其中第一個數位對應到出生的世紀，最後一個數位對應于個人的性別（對男為奇數，甚至是女）。
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_denmark_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_denmark_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_denmark_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_denmark_eu_tax_file_number"></a>Keywords_denmark_eu_tax_file_number

- centrale personregister
- civilt registreringssystem
- Cpr
- Cpr#
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- 健康情況卡片
- 健康情況保險卡號碼
- 健康情況保險號碼
- 識別號碼
- identifikationsnummer
- identifikationsnummer#
- 身分識別號碼
- krankenkassennummer
- nationalid#
- personalidentityno#
- personnummer
- personnummer#
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- skat 識別碼
- skat kode
- skat nummer
- skattenummer
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- 稅碼
- 旅遊健康情況保險卡
- uniqueidentityno#
- 納稅號碼
- 稅務登記編號
- 納稅識別碼
- 納稅識別號碼
- taxid#
- taxnumber#
- 納稅否
- taxno#
- taxnumber
- 納稅識別碼否
- 錫#
- taxidno#
- taxidnumber#
- 納稅否#
- 納稅人識別碼
- tin no


## <a name="drug-enforcement-agency-dea-number"></a>藥品強制代理人（DEA）號碼

### <a name="format"></a>格式

兩個字母后接7位數

### <a name="pattern"></a>模式

模式必須包含下列各項：
- 這組可能字母的一個字母（不區分大小寫）： abcdefghjklmnprstux，也就是報名者程式碼 
- 一個字母（不區分大小寫），這是報名者姓氏的第一個字母 
- 七位數，最後一個是檢查碼

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_dea_number 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無

## <a name="estonia-drivers-license-number"></a>愛沙尼亞駕照編號
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

兩個字母后接六位數
  
### <a name="pattern"></a>模式

兩個字母和六位數：
  
-  字母 "ET" （不區分大小寫） 
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_estonia_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_estonia_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_estonia_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- permis de conduire

## <a name="estonia-national-identification-number"></a>愛沙尼亞國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

11位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

11位數：
  
- 對應于性別和世紀的一位數（奇數號男，甚至是數位女; 1-2：19世紀; 3-4：20世紀; 5-6：21世紀）
    
- 對應至出生日期的六位數（YYMMDD）
- 三位數，對應至在相同日期出生的人員的序號
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_estonia_eu_national_id_card` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_estonia_eu_national_id_card` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_estonia_eu_national_id_card` 會找到符合模式的內容。 
    
```xml
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- 識別碼-kaart
- 益
- isikukood#
- isikukood
- maksu 識別碼
- maksukohustuslase identifitseerimisnumber
- maksunumber
- 國家識別號碼
- 國家/地區號碼
- 個人程式碼
- 個人號碼
- 個人身分識別碼
- 個人身分識別號碼
- personalidnumber#
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#

## <a name="estonia-passport-number"></a>愛沙尼亞護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

一個字母后接7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

一個字母后接7位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_estonia_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_estonia_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_estonia_eu_passport_number**

- 護照號碼
- 愛沙尼亞文護照號碼
- 護照否
- eesti kodaniku 傳遞

## <a name="estonia-tax-identification-number"></a>愛沙尼亞納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

11位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

11位數：
  
-  一種對應到性別和世紀的數位，其奇數表示男和偶數表示女，如下所示：1，2代表19世紀;3，4代表20世紀;21世紀的5，6 
    
- 對應至出生日期的六位數（YYMMDD）
- 三位數，對應至在相同日期出生的人員的序號
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_estonia_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_estonia_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_estonia_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_estonia_eu_tax_file_number"></a>Keywords_estonia_eu_tax_file_number

- 識別碼-kaart
- 益
- isikukood#
- isikukood
- maksu 識別碼
- maksukohustuslase identifitseerimisnumber
- maksunumber
- 國家識別號碼
- 國家/地區號碼
- 個人程式碼
- 個人號碼
- 個人身分識別碼
- 個人身分識別號碼
- personalidnumber#
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#

## <a name="eu-debit-card-number"></a>歐盟借方卡號碼

### <a name="format"></a>格式

16位數

### <a name="pattern"></a>模式

非常複雜且健全的模式

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_eu_debit_card 找到符合模式的內容。
- 下列專案中至少有一個為真：
    - 會找到來自 Keyword_eu_debit_card 的關鍵字。
    - 會找到來自 Keyword_card_terms_dict 的關鍵字。
    - 會找到來自 Keyword_card_security_terms_dict 的關鍵字。
    - 會找到來自 Keyword_card_expiration_terms_dict 的關鍵字。
    - 函數 Func_expiration_date 會找到正確日期格式的日期。
- 校驗和通過。

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- 帳戶號碼 
- 卡號碼 
- 卡片編號 
- 安全性號碼 
- Cc# 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- 帳戶 nbr 
- 帳戶號 
- 帳戶編號 
- 美洲 express 
- americanexpress 
- americano espresso 
- amex 
- atm 卡 
- atm 卡 
- atm kaart 
- atmcard 
- atmcards 
- atmkaart 
- atmkaarten 
- bancontact 
- 銀行卡 
- bankkaart 
- 持卡人 
- 持卡人 
- 卡號 
- 卡號碼 
- 卡號碼 
- 卡片類型 
- cardano numerico 
- 持 卡 人 
- 持 卡 人 
- cardnumber 
- cardnumbers 
- carta bianca 
- carta credito 
- carta di credito 
- cartao de credito 
- cartao de crédito 
- cartao de debito 
- cartao de débito 
- 購買 bancaire 
- 購買 blanche 
- 購買 bleue 
- 購買退款 
- 反 crédit 
- 購買 di credito 
- carteblanche 
- cartão de credito 
- cartão de crédito 
- cartão de debito 
- cartão de débito 
- cb 
- ccn 
- 檢查卡片 
- 檢查卡片 
- checkcard
- checkcards 
- chequekaart 
- 卷雲 
- cirrus-edc-maestro 
- controlekaart 
- controlekaarten 
- 信用卡 
- 信用卡 
- creditcard 
- creditcards 
- debetkaart 
- debetkaarten 
- 轉帳卡 
- 轉帳卡 
- debitcard 
- debitcards 
- debito automatico 
- diners 俱樂部 
- dinersclub 
- 發現 
- 探索卡片 
- 探索卡片 
- discovercard 
- discovercards 
- débito automático
- edc 
- eigentümername 
- 歐洲借貸卡 
- hoofdkaart 
- hoofdkaarten 
- 在 viaggio 
- 日本卡片局 
- japanse kaartdienst 
- jcb 
- kaart 
- kaart 編號 
- kaartaantal 
- kaartaantallen 
- kaarthouder 
- kaarthouders 
- karte  
- karteninhaber 
- karteninhabers
- kartennr 
- kartennummer 
- kreditkarte 
- kreditkarten-nummer 
- kreditkarteninhaber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- 大師 
- 主卡 
- 主卡 
- 萬事 達 
- mastercards 
- Mc 
- mister 現金 
- n carta 
- 憲章 
- 無 de tarjeta 
- 無 do cartao 
- 無 do cartão 
- 不。 de tarjeta 
- 不。 執行 cartao 
- 不。 執行 cartão 
- nr carta 
- 星期日。 憲章 
- numeri di scheda 
- numero carta 
- numero de cartao 
- numero 的重複購買 
- numero de cartão 
- numero de tarjeta
- numero della carta 
- numero di carta 
- numero di scheda 
- numero 執行 cartao 
- numero 執行 cartão 
- numéro 的重複購買 
- n º carta 
- 消除購買的 n º 
- de 照購買 
- 消除 tarjeta 的 n º 
- n º do cartao 
- n º do cartão 
- n º。 執行 cartão 
- número de cartao 
- número de cartão 
- número de tarjeta 
- número 執行 cartao 
- scheda dell'assegno 
- scheda dell'atmosfera 
- scheda dell'atmosfera 
- scheda della banca 
- scheda di controllo 
- scheda di debito 
- scheda matrice 
- schede dell'atmosfera 
- schede di controllo 
- schede di debito 
- schede matrici 
- scoprono la scheda 
- scoprono le schede 
- 獨奏 
- supporti di scheda 
- supporto di scheda 
- 開關 
- tarjeta atm 
- tarjeta credito 
- tarjeta de atm 
- tarjeta de credito 
- tarjeta de debito 
- tarjeta debito 
- tarjeta 否
- tarjetahabiente 
- tipo della scheda 
- ufficio giapponese della 
- scheda 
- v 支付 
- v-支付 
- 簽證 
- 簽證加 
- 簽證電 
- visto 
- visum 
- vpay   

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- 卡片識別碼
- 名片驗證 
- cardi la verifica 
- cid 
- 貨至 seg 
- 貨至 seguranca 
- 貨至 segurança 
- 貨至 sicurezza 
- Cod。 Seg 
- Cod。 seguranca 
- Cod。 segurança 
- Cod。 sicurezza 
- codice di sicurezza 
- codice di verifica 
- codigo 
- codigo de seguranca 
- codigo de segurança 
- crittogramma 
- 密碼 
- cryptogramme 
- cv2 
- Cvc 
- cvc2 
- cvn 
- cvv 
- cvv2 
- cód seguranca 
- cód segurança 
- cód. seguranca 
- cód. segurança 
- código 
- código de seguranca 
- código de segurança 
- de kaart controle 
- geeft nr uit 
- 問題否 
- 發行編號 
- kaartidentificatienummer 
- kreditkartenprufnummer 
- kreditkartenprüfnummer 
- kwestieaantal 
- 不。 dell'edizione 
- 不。 di sicurezza 
- numero de securite 
- numero de verificacao 
- numero dell'edizione 
- numero di identificazione della 
- scheda 
- numero di sicurezza 
- numero van veiligheid 
- numéro de sécurité 
- n º autorizzazione 
- número de verificação 
- perno il blocco 
- pin 區區塊 
- prufziffer 
- prüfziffer 
- 安全性代碼 
- 安全性否 
- 安全性號碼 
- sicherheits kode 
- sicherheitscode 
- sicherheitsnummer 
- speldblok 
- veiligheid nr 
- veiligheidsaantal 
- veiligheidscode 
- veiligheidsnummer 
- verfalldatum 

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf 
- 資料 de expiracao 
- 資料 de expiração 
- 資料 del exp 
- 資料 di exp 
- 資料 di scadenza 
- 資料 em mail.que expira 
- 資料 scad 
- 資料 scadenza 
- 日期 de validité 
- 基準 afloop 
- 基準 van exp 
- de afloop 
- espira 
- espira 
- 到期日 
- exp 基準 
- 到期 
- 到期 
- 到期 
- 屆滿 
- fecha de expiracion 
- fecha de venc 
- gultig bis 
- gultigkeitsdatum 
- gültig bis 
- gültigkeitsdatum 
- la scadenza 
- scadenza 
- valable 
- validade 
- valido hasta 
- 勇氣 
- venc 
- vencimento 
- vencimiento 
- verloopt 
- vervaldag 
- vervaldatum 
- vto 
- válido hasta 

## <a name="eu-drivers-license-number"></a>歐盟駕駛執照號碼
這些是歐盟駕駛執照號碼敏感資訊類型中的實體。

- [奧地利](#austria-drivers-license-number) 
- [比利時](#belgium-drivers-license-number)
- [保加利亞](#bulgaria-drivers-license-number)
- [克羅埃西亞](#croatia-drivers-license-number)
- [賽普勒斯](#cyprus-drivers-license-number)
- [捷克文](#czech-drivers-license-number)
- [丹麥](#denmark-drivers-license-number)
- [愛沙尼亞](#estonia-drivers-license-number)
- [芬蘭](#finland-drivers-license-number)
- [法國](#france-drivers-license-number) 
- [德國](#germany-drivers-license-number)
- [希臘](#greece-drivers-license-number)
- [匈牙利](#hungary-drivers-license-number)
- [愛爾蘭](#ireland-drivers-license-number)
- [義大利](#italy-drivers-license-number)
- [拉脫維亞](#latvia-drivers-license-number)
- [立陶宛](#lithuania-drivers-license-number)
- [盧森堡](#luxemburg-drivers-license-number)
- [馬爾他](#malta-drivers-license-number)
- [荷蘭](#netherlands-drivers-license-number)
- [波蘭](#poland-drivers-license-number) 
- [葡萄牙](#portugal-drivers-license-number)
- [羅馬尼亞](#romania-drivers-license-number)
- [斯洛伐克](#slovakia-drivers-license-number)
- [斯洛維尼亞](#slovenia-drivers-license-number)
- [西班牙](#spain-drivers-license-number)
- [瑞典](#sweden-drivers-license-number)
- [英國。](#uk-drivers-license-number)

## <a name="eu-national-identification-number"></a>歐盟國身分識別號碼
這些是歐盟國身分識別號碼機密資訊類型中的實體。

- [奧地利](#austria-national-identification-number)
- [比利時](#belgium-national-number)
- [保加利亞](#bulgaria-national-identification-number)
- [克羅埃西亞](#croatia-identity-card-number)
- [賽普勒斯](#cyprus-national-identification-number)
- [捷克文](#czech-personal-identity-number)
- [丹麥](#denmark-personal-identification-number)
- [愛沙尼亞](#estonia-national-identification-number)
- [芬蘭](#finland-national-identification-number)
- [法國](#france-national-identification-card-cni)
- [德國](#germany-identity-card-number)
- [希臘](#greece-national-id-card)
- [匈牙利](#hungary-national-identification-number)
- [愛爾蘭](#ireland-national-identification-number)
- [義大利](#italy-national-identification-number)
- [拉脫維亞](#latvia-national-identification-number)
- [立陶宛](#lithuania-national-identification-number)
- [盧森堡](#luxemburg-national-identification-number)
- [馬爾他](#malta-national-identification-number)
- [荷蘭](#netherlands-national-identification-number)
- [波蘭](#poland-national-id-pesel)
- [葡萄牙](#portugal-citizen-card-number)
- [羅馬尼亞](#romania-national-identification-number)
- [斯洛伐克](#slovakia-national-identification-number)
- [斯洛維尼亞](#slovenia-national-identification-number)
- [西班牙](#spain-national-identification-number)
- [英國。](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>歐盟護照號碼 
在歐盟護照號碼機密資訊 typeThese 中的實體是歐盟護照號碼捆綁中的實體。

- [奧地利](#austria-passport-number)
- [比利時](#belgium-passport-number)
- [保加利亞](#bulgaria-passport-number)
- [克羅埃西亞](#croatia-passport-number)
- [賽普勒斯](#cyprus-passport-number)
- [捷克文](#czech-passport-number)
- [丹麥](#denmark-passport-number)
- [愛沙尼亞](#estonia-passport-number)
- [芬蘭](#finland-passport-number)
- [法國](#france-passport-number)
- [德國](#germany-passport-number)
- [希臘](#greece-passport-number)
- [匈牙利](#hungary-passport-number)
- [愛爾蘭](#ireland-passport-number)
- [義大利](#italy-passport-number)
- [拉脫維亞](#latvia-passport-number)
- [立陶宛](#lithuania-passport-number)
- [盧森堡](#luxemburg-passport-number)
- [馬爾他](#malta-passport-number)
- [荷蘭](#netherlands-passport-number)
- [波蘭](#poland-passport-number)
- [葡萄牙](#portugal-passport-number)
- [羅馬尼亞](#romania-passport-number)
- [斯洛伐克](#slovakia-passport-number)
- [斯洛維尼亞](#slovenia-passport-number)
- [西班牙](#spain-passport-number)
- [瑞典](#sweden-passport-number)
- [英國。](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>歐盟社會安全號碼或對等身分識別
這些是歐盟社會保險號碼或對等身分識別敏感資訊類型中的實體。

- [奧地利](#austria-social-security-number-or-equivalent-identification)
- [比利時](#belgium-social-security-number-or-equivalent-identification)
- [克羅埃西亞](#croatia-social-security-number-or-equivalent-identification)
- [捷克文](#czech-social-security-number-or-equivalent-identification)
- [丹麥](#denmark-social-security-number-or-equivalent-identification)
- [芬蘭](#finland-social-security-number-or-equivalent-identification)
- [法國](#france-social-security-number-insee-or-equivalent-identification)
- [德國](#germany-identity-card-number)
- [希臘](#greece-national-id-card)
- [匈牙利](#hungary-social-security-number-or-equivalent-identification)
- [葡萄牙](#portugal-citizen-card-number)
- [西班牙](#spain-social-security-number-ssn)
- [瑞典](#sweden-social-security-number-or-equivalent-identification)

## <a name="eu-tax-identification-number"></a>歐盟納稅識別號碼

hese 實體屬於歐盟納稅身分識別號碼的敏感資訊類型。

- [奧地利](#austria-tax-identification-number)
- [比利時](#belgium-tax-identification-number)
- [保加利亞](#bulgaria-tax-identification-number)
- [克羅埃西亞](#croatia-tax-identification-number)
- [賽普勒斯](#cyprus-tax-identification-number)
- [捷克文](#czech-tax-identification-number)
- [丹麥](#denmark-tax-identification-number)
- [愛沙尼亞](#estonia-tax-identification-number)
- [芬蘭](#finland-tax-identification-number)
- [法國](#france-tax-identification-number)
- [德國](#germany-tax-identification-number)
- [希臘](#greece-tax-identification-number)
- [匈牙利](#hungary-tax-identification-number)
- [愛爾蘭](#ireland-tax-identification-number)
- [義大利](#italy-tax-identification-number)
- [拉脫維亞](#latvia-tax-identification-number)
- [立陶宛](#lithuania-tax-identification-number)
- [盧森堡](#luxemburg-tax-identification-number)
- [馬爾他](#malta-tax-identification-number)
- [荷蘭](#netherlands-tax-identification-number)
- [波蘭](#poland-tax-identification-number)
- [葡萄牙](#portugal-tax-identification-number)
- [羅馬尼亞](#romania-tax-identification-number)
- [斯洛伐克](#slovakia-tax-identification-number)
- [斯洛維尼亞](#slovenia-tax-identification-number)
- [西班牙](#spain-tax-identification-number)
- [瑞典](#sweden-tax-identification-number)
- [英國。](#uk-tax-identification-number)


## <a name="finland-drivers-license-number"></a>芬蘭駕照編號
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

10位數包含連字號
  
### <a name="pattern"></a>模式

10位數包含連字號：
  
-  六位數 
- 連字號
-  四位數 
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_finland_eu_driver's_license_number` 找到符合模式的內容。 
    
- 找到來自的關鍵字 `Keywords_finland_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_finland_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- ajokortti

## <a name="finland-national-identification-number"></a>芬蘭國身分識別號碼
這種敏感資訊類型的實體包含在歐盟國身分識別號碼機密資訊類型中，並可作為獨立的機密資訊類型實體。

### <a name="format"></a>格式

六位數加上一個表示世紀的字元加上三個數字加上檢查碼

### <a name="pattern"></a>模式

模式必須包含下列各項：
- DDMMYY 出生日期格式格式的六位數 
- 世紀標記（'-'、' + ' 或 ' a '） 
- 三位數的個人身分識別號碼 
- 一種檢查碼的數位或字母（不區分大小寫）

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_finnish_national_id 找到符合模式的內容。
- 會找到來自 Keyword_finnish_national_id 的關鍵字。
- 校驗和通過。

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero#
- henkilötunnusnumero
- hetu
- 識別碼 no
- 識別碼號碼
- 識別號碼
- identiteetti numero
- 身分識別號碼
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- 國際身分識別卡
- 國家識別碼
- 個人識別碼
- 個人身分識別碼
- personalidnumber#
- personbeteckning
- personnummer
- 社會安全號碼
- sosiaaliturvatunnus
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus

## <a name="finland-passport-number"></a>芬蘭護照號碼
您可以在歐盟護照號碼機密資訊類型中使用此機密資訊類型實體，也可以做為獨立機密資訊類型實體。

### <a name="format"></a>格式
九個字母和數位的組合

### <a name="pattern"></a>模式
九個字母和數位的組合：兩個字母（不區分大小寫）七位數

### <a name="checksum"></a>校驗
否

### <a name="definition"></a>定義
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_finland_passport_number 找到符合模式的內容。
- 會找到來自 Keyword_finland_passport_number 的關鍵字。

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>關鍵字
- Keyword_finland_passport_number
- 護照
- Passi

## <a name="finland-social-security-number-or-equivalent-identification"></a>芬蘭社會安全號碼或對等身分識別
這個敏感資訊類型實體只有歐盟社會保險號碼或同等識別碼的敏感資訊類型提供。

### <a name="format"></a>格式

以指定格式為11個字元的組合
  
### <a name="pattern"></a>模式

以指定格式為11個字元的組合：
  
-  六位數 
- 下列其中一個範例：
  - 加號
  - 負號
  - 字母 "A" （不區分大小寫）
- 三位數
- 一個字母或一個數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_finland_eu_ssn_or_equivalent` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_finland_eu_ssn_or_equivalent` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_finland_eu_ssn_or_equivalent` 會找到符合模式的內容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a>Keywords_finland_eu_ssn_or_equivalent

- 識別號碼
- 個人識別碼
- 身分識別號碼
- 芬蘭文身分識別號碼
- personalidnumber#
- 國家識別號碼
- 識別碼號碼
- 國家識別碼
- 本國識別碼
- 識別碼 no
- tunnistenumero
- henkilötunnus
- yksilöllinen henkilökohtainen tunnistenumero
- ainutlaatuinen henkilökohtainen tunnus
- identiteetti numero
- suomen kansallinen henkilötunnus
- henkilötunnusnumero#
- kansallisen tunnistenumero
- tunnusnumero
- kansallinen tunnus numero
- hetu

## <a name="finland-tax-identification-number"></a>芬蘭納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

一個11個字元的位數、字母和正負號組合
  
### <a name="pattern"></a>模式

一個11個字元的位數、字母和正負號組合：
  
- 六位數
- 下列其中一項：加號、減號或字母 "A" （不區分大小寫），其中加號表示介於1800-1899 之間，減號表示出生于1900-1999，而 "A" 表示出生2000和之後
- 三位數
- 一個字母或一個數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_finland_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_finland_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_finland_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_finland_eu_tax_file_number"></a>Keywords_finland_eu_tax_file_number

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero#
- henkilötunnusnumero
- hetu
- 識別碼 no
- 識別碼號碼
- 識別號碼
- identiteetti numero
- 身分識別號碼
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- 國際身分識別卡
- 國家識別碼
- 個人識別碼
- 個人身分識別碼
- personalidnumber#
- personbeteckning
- personnummer
- 社會安全號碼
- sosiaaliturvatunnus
- suomen kansallinen henkilötunnus
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="france-drivers-license-number"></a>法國駕駛執照號碼
您可以在歐盟駕駛執照號碼的敏感資訊類型中取得此機密資訊類型實體，也可以作為獨立的機密資訊類型實體使用。

### <a name="format"></a>格式

12位數

### <a name="pattern"></a>模式

12位數與折扣類似的模式，例如法國電話號碼

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_french_drivers_license 找到符合模式的內容。
- 下列專案中至少有一個為真：
- 會找到來自 Keyword_french_drivers_license 的關鍵字。
- 函數 Func_eu_date 會找到正確日期格式的日期。

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- 驅動程式許可證
- 驅動程式授權
- 駕駛許可證
- 駕照
- permis de conduire
- 許可號碼
- 授權號碼
- 許可證號碼
- 授權號碼

## <a name="france-national-identification-card-cni"></a>法國國身分識別卡片（CNI）
這種敏感資訊類型的實體包含在歐盟國身分識別號碼機密資訊類型中，並可作為獨立的機密資訊類型實體。

### <a name="format"></a>格式

12位數

### <a name="pattern"></a>模式

12位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：
- 正則運算式 Regex_france_cni 找到符合模式的內容。

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

- 卡號碼
- 購買 nationale d'identité
- nationale d'idenite 否
- Cni#
- Cni
- compte bancaire
- 國家識別號碼
- 本國身分識別
- nationalidno#
- numéro d'assurance maladie
- numéro 購買 vitale

   
## <a name="france-passport-number"></a>法國護照號碼
您可以在歐盟護照號碼機密資訊類型中使用此機密資訊類型實體，也可以做為獨立機密資訊類型實體。

### <a name="format"></a>格式

九個數字和字母

### <a name="pattern"></a>模式

九個數字和字母：
- 兩位數 
- 兩個字母（不區分大小寫） 
- 五位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_fr_passport 找到符合模式的內容。
- 會找到來自 Keyword_passport 的關鍵字。

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_passport"></a>Keyword_passport

- 護照號碼
- 護照否
- 護照#
- 護照#
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番號
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport 非
- Passeport#
- Passeport#
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>法國社會安全號碼（INSEE）或對等身分識別
此機密資訊類型的實體包含在歐盟社會保險號碼和對等識別碼的敏感資訊類型中，並可作為獨立機密資訊類型實體。

### <a name="format"></a>格式

15位數

### <a name="pattern"></a>模式

必須符合下列其中一種模式：
- 13位數後接一個空格後接兩位數<br/>
或
- 15個連續數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：
- 函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。
- 會找到來自 Keyword_fr_insee 的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。
- 找不到 Keyword_fr_insee 的關鍵字。
- 校驗和通過。

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- insee
- securité sociale
- securite sociale
- 國家識別碼
- 本國身分識別
- numéro d'identité
- 無 d'identité
- 不。 d'identité
- numero d'identite
- 無 d'identite
- 不。 d'identite
- 社會安全號碼
- 社會安全性碼
- 社交保險號碼
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le 程式碼 de la sécurité sociale
- numéro d'assurance sociale
- numéro de sécu
- 程式碼 sécu 

## <a name="france-tax-identification-number"></a>法國納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

每個人13位數，實體的九位數
  
### <a name="pattern"></a>模式

個人13位數：
  
- 一個位數必須是0、1、2或3
- 12位數
    
實體的九位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_france_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_france_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_france_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'identification fiscale
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#

## <a name="germany-drivers-license-number"></a>德國駕駛執照號碼
這種敏感資訊類型的實體包含在歐盟駕駛執照號碼的敏感資訊類型中，可作為獨立的敏感資訊類型實體。

### <a name="format"></a>格式

11位數和字母的組合

### <a name="pattern"></a>模式

11個數字和字母（不區分大小寫）：
- 一個數位或字母 
- 兩位數 
- 六個數字或字母 
- 一個數位 
- 一個數位或字母

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_german_drivers_license 找到符合模式的內容。
- 下列專案中至少有一個為真：
    - 會找到來自 Keyword_german_drivers_license_number 的關鍵字。
    - 會找到來自 Keyword_german_drivers_license_collaborative 的關鍵字。
    - 會找到來自 Keyword_german_drivers_license 的關鍵字。
- 校驗和通過。

```xml
<!-- Germany Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- Führerschein
- Fuhrerschein
- Fuehrerschein
- Führerscheinnummer
- Fuhrerscheinnummer
- Fuehrerscheinnummer
- Führerschein- 
- Fuhrerschein- 
- Fuehrerschein- 
- FührerscheinnummerNr
- FuhrerscheinnummerNr
- FuehrerscheinnummerNr
- FührerscheinnummerKlasse
- FuhrerscheinnummerKlasse
- FuehrerscheinnummerKlasse
- Führerschein-Nr
- Fuhrerschein-Nr
- Fuehrerschein-Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse
- FührerscheinnummerNr 
- FuhrerscheinnummerNr 
- FuehrerscheinnummerNr 
- FührerscheinnummerKlasse 
- FuhrerscheinnummerKlasse 
- FuehrerscheinnummerKlasse 
- Führerschein-Nr 
- Fuhrerschein-Nr 
- Fuehrerschein-Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse 
- Dl 
- Dls
- Driv 許可證 
- Driv Licen 
- Driv 授權
- Driv 授權 
- Driv 許可證 
- Driv 許可證 
- Driv 許可證 
- 驅動程式 Licen 
- 駕照 
- 驅動程式授權 
- 驅動程式許可證 
- 驅動程式授權 
- 驅動程式 .Lic 
- 驅動程式 Licen 
- 驅動程式授權 
- 驅動程式授權 
- 驅動程式許可證 
- 驅動程式授權 
- 驅動程式的 .Lic 
- 驅動程式的 Licen 
- 駕駛執照 
- 駕駛執照 
- 駕駛執照 
- 駕駛執照 
- 駕駛許可證 
- 驅車 Licen 
- 駕照 
- 駕駛授權 
- 駕駛許可證 
- 駕駛許可證

#### <a name="keyword_german_drivers_license_collaborative"></a>Keyword_german_drivers_license_collaborative

- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- 非 Führerschein 
- 非 Fuhrerschein 
- 非 Fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-Fuehrerschein
- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- 非 Führerschein 
- 非 Fuhrerschein 
- 非 Fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-Fuehrerschein 

#### <a name="keyword_german_drivers_license"></a>Keyword_german_drivers_license

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde

## <a name="germany-identity-card-number"></a>德國身分識別卡號碼
- 這種敏感資訊類型的實體包含在歐盟國身分識別號碼機密資訊類型中，並可作為獨立的機密資訊類型實體。
- 這種敏感資訊類型實體包含在歐盟社會保險號碼或同等識別碼的敏感資訊類型中。

### <a name="format"></a>格式

自11月2010：9個字母和數位

從1年4月1987至31年10月2010：10位數

### <a name="pattern"></a>模式

自11月1日2010：
- 一個字母（不區分大小寫） 
- 八位數

從1年4月1987至31年10月2010：
- 10位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：
- 正則運算式 Regex_germany_id_card 找到符合模式的內容。
- 會找到來自 Keyword_germany_id_card 的關鍵字。

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- 識別
- identifikation
- identifizierungsnummer
- 身份證
- 身分識別號碼
- 識別碼-nummer
- 個人識別碼
- personalausweis
- persönliche 識別碼 nummer
- persönliche identifikationsnummer
- persönliche-識別碼-nummer


## <a name="germany-passport-number"></a>德國護照號碼
這個敏感資訊類型實體包含在歐盟護照號碼機密資訊類型中，並可作為獨立的敏感資訊類型實體。

### <a name="format"></a>格式

10位數或字母

### <a name="pattern"></a>模式

模式必須包含下列各項：
- 第一個字元是來自此集合的數位或字母（C、F、G、H、J、K） 
- 三位數 
- 來自此集合的五個數字或字母（C、-H、J-N、P、R、T、V-Z） 
- 一個數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_german_passport 找到符合模式的內容。
- 找到任何五個關鍵字清單中的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_german_passport_data 找到符合模式的內容。
- 找到任何五個關鍵字清單中的關鍵字。
- 校驗和通過。

```xml
<!-- Germany Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepass
- reisepasse
- reisepassnummer
- 護照
- 護照

#### <a name="keyword_german_passport_collaborative"></a>Keyword_german_passport_collaborative

- geburtsdatum
- ausstellungsdatum
- ausstellungsort

#### <a name="keyword_german_passport_number"></a>Keyword_german_passport_number

Reisepass Nr-Reisepass

#### <a name="keyword_german_passport1"></a>Keyword_german_passport1

Reisepass-Nr

#### <a name="keyword_german_passport2"></a>Keyword_german_passport2

bnationalit

## <a name="germany-tax-identification-number"></a>德國納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

11位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

11位數：
  
-  10位數 
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_germany_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_germany_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_germany_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- steuer 識別碼
- steueridentifikationsnummer
- steuernummer
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- 辛#
- 辛
- zinnnummer

## <a name="greece-drivers-license-number"></a>希臘駕駛執照號碼
這種敏感資訊類型的實體包含在歐盟駕駛執照號碼的敏感資訊類型中，可作為獨立的敏感資訊類型實體。

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_greece_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_greece_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_greece_eu_driver ' s_license_number**

- Dll#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- δεια οδήγησης
- Adeia odigisis


## <a name="greece-national-id-card"></a>希臘國民身分證
這種敏感資訊類型的實體包含在歐盟國身分識別號碼機密資訊類型中，並可作為獨立的機密資訊類型實體。

### <a name="format"></a>格式

7-8 字母和數位的組合，加上破折號

### <a name="pattern"></a>模式

七個字母和數位（舊格式）：
- 一個字母（希臘文字母表的任何字母） 
- 虛線 
- 六位數

八個字母和數位（新格式）：
- 兩個字母大寫字元會同時出現于希臘字母和拉丁字母表中（ABEZHIKMNOPTYX） 
- 虛線 
- 六位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 Regex_greece_id_card 找到符合模式的內容。
- 會找到來自 Keyword_greece_id_card 的關鍵字。

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- 希臘文識別碼
- 希臘國識別碼
- 希臘文個人編碼卡
- 希臘警方識別碼
- 身份證
- tautotita
- ταυτότητα
- ταυτότητας

## <a name="greece-passport-number"></a>希臘護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

兩個字母后接7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母后接7位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_greece_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_greece_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_greece_eu_passport_number**

- 護照號碼
- 希臘文護照號碼
- 護照否
- διαβατηριο

## <a name="greece-tax-identification-number"></a>希臘納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_greece_eu_tax_file_number` 找到符合模式的內容。 
    
- 找到來自的關鍵字 `Keywords_greece_eu_tax_file_number` 。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- Afm#
- Afm
- aφμ | aφμαριθμός
- aφμ
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- 納稅登錄否
- 納稅登錄號碼
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- taxregistryno#
- 納稅人識別碼
- tin no
- 錫#
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>中國香港身分識別卡（HKID）號碼

### <a name="format"></a>格式

8-9 字母和數位的組合，以及最後一個字元兩邊的 optional 括弧

### <a name="pattern"></a>模式

8-9 個字母的組合：
- 1-2 個字母（不區分大小寫） 
- 六位數 
- 最後一個字元（任何數位或字母 A），也就是檢查碼，也可以以括弧括住。

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_hong_kong_id_card 找到符合模式的內容。
- 會找到來自 Keyword_hong_kong_id_card 的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：
- 函數 Func_hong_kong_id_card 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- 中國香港身分識別卡
- HKIDC
- 身份證
- 身份證
- hk 身分識別卡
- 中國香港號
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証
   
## <a name="hungary-drivers-license-number"></a>匈牙利駕照號碼
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

兩個字母后接六位數
  
### <a name="pattern"></a>模式

兩個字母和六位數：
  
- 兩個字母（不區分大小寫） 
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_hungary_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_hungary_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_hungary_eu_driver ' s_license_number**
- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- vezetoi engedely

## <a name="hungary-national-identification-number"></a>匈牙利國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

11位數
  
### <a name="pattern"></a>模式

11位數：
  
-  對應于性別（1-男，2-女，其他號碼）的一種數位，也可能是公民之前出生的公民，具有雙公民的1900或公民。 
- 對應至出生日期的六位數（YYMMDD）
- 對應至序列值的三位數
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_hungary_eu_national_id_card` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_hungary_eu_national_id_card` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_hungary_eu_national_id_card` 會找到符合模式的內容。 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- 識別碼號碼
- 識別號碼
- sz ig
- 深圳。ig.
- ig。
- személyazonosító igazolvány
- személyi igazolvány

## <a name="hungary-passport-number"></a>匈牙利護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

兩個字母后接六個或7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母后接六位數或七位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_hungary_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_hungary_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>關鍵字

**Keywords_hungary_eu_passport_number**

- 護照號碼
- 匈牙利文護照號碼
- 護照否
- útlevél száma

## <a name="hungary-social-security-number-or-equivalent-identification"></a>匈牙利社會安全號碼或同等身分識別
這個敏感資訊類型實體只有歐盟社會保險號碼或同等識別碼的敏感資訊類型提供。

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_hungary_eu_ssn_or_equivalent` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_hungary_eu_ssn_or_equivalent` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_hungary_eu_ssn_or_equivalent` 會找到符合模式的內容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- 匈牙利文社交安全性號碼
- 社會安全號碼
- socialsecuritynumber#
- hssn#
- socialsecuritynno
- hssn
- 泰姬陵
- 泰姬陵#
- Ssn
- Ssn#
- 社會安全性否
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>匈牙利納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

沒有空格或分隔符號的10位數
  
### <a name="pattern"></a>模式

10位數：
  
-  一個位數，必須是 "8" 
- 代表日期01/01/1867 和個人出生日期之間的天數所對應的5位數
- 三位數的值，對應于因有機會讓個別人出生于同一天所產生的數目
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_hungary_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_hungary_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_hungary_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- 匈牙利文 tin
- hungatiantin#
- 稅務授權單位否
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- 加值稅號碼

## <a name="india-permanent-account-number-pan"></a>印度永久帳戶號碼（PAN）

### <a name="format"></a>格式

10個字母或數位

### <a name="pattern"></a>模式

10個字母或數位：
- 五個字母（不區分大小寫） 
- 四位數 
- 以字母檢查碼表示的字母

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 Regex_india_permanent_account_number 找到符合模式的內容。
- 會找到來自 Keyword_india_permanent_account_number 的關鍵字。
- 校驗和通過。

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- 永久帳戶號碼 
- 泛 
   
## <a name="india-unique-identification-aadhaar-number"></a>印度唯一識別碼（Aadhaar）號碼

### <a name="format"></a>格式

12位數包含選擇性空格或短杠

### <a name="pattern"></a>模式

12位數：
- 四位數 
- 選擇性的空格或破折號 
- 四位數 
- 選擇性的空格或破折號 
- 最後一位數的檢查碼

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：函數 Func_india_aadhaar 找到符合模式的內容。
會找到來自 Keyword_india_aadhar 的關鍵字。
校驗和通過。
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：函數 Func_india_aadhaar 找到符合模式的內容。
校驗和通過。
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- Uid
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>印尼身分識別卡（KTP）號碼

### <a name="format"></a>格式

包含選用句點的16位數

### <a name="pattern"></a>模式

16位數：
- 兩位數的省碼 
- 一個句點（選用） 
- 兩位數攝政或城市碼 
- 兩位數的 subdistrict 程式碼 
- 一個句點（選用） 
- DDMMYY 之日期格式的六位數 
- 一個句點（選用） 
- 四位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_indonesia_id_card 找到符合模式的內容。
- 會找到來自 Keyword_indonesia_id_card 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_indonesia_id_card 找到符合模式的內容。

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- Ktp
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## <a name="international-banking-account-number-iban"></a>國際銀行帳戶號碼（IBAN）

### <a name="format"></a>格式

國家/地區代碼（兩個字母）加上檢查碼（兩位數）加上 bban 號碼（最多30個字元）

### <a name="pattern"></a>模式

模式必須包含下列各項：

- 兩個字母的國家/地區碼
- 兩個檢查碼位數（後面接著選擇性的空格） 
- 1-7 四個字母或數位的群組（可以以空格隔開）
- 1-3 個字母或數位

每個國家/地區的格式稍有不同。 IBAN 敏感資訊類型涵蓋下列60個國家/地區：

ad，ae，al，at，az，ba，a，bg，bh，ch，cr，cy，cz，de，深色，do，ee，es，es，fo，fr，gb，ge，gi，gl，gr，hr，hu，ie，il，為，it，kw，kz，lb，li，lt，lu，lv，mt，mu，nl-nl，no，pl，mt，ro，rs-232c，tn，tr，vg

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_iban 找到符合模式的內容。
- 校驗和通過。

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無

   

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>國際分類的疾病（ICD-10-釐米）

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 會找到來自 Dictionary_icd_10_updated 的關鍵字。
- 會找到來自 Dictionary_icd_10_codes 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 會找到 Dictionary_icd_10_ 更新的關鍵字。

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

關鍵字

Dictionary_icd_10_updated 關鍵字字典中的任何字詞，其基礎是以[疾病的國際分類，第十個修訂版本、臨床修改（icd-10 釐米）](https://go.microsoft.com/fwlink/?linkid=852604)為基礎。 這種類型只會尋找字詞，而不是保險碼。

Dictionary_icd_10_codes 關鍵字字典中的任何字詞，其基礎是以[疾病的國際分類，第十個修訂版本、臨床修改（icd-10 釐米）](https://go.microsoft.com/fwlink/?linkid=852604)為基礎。 這種類型只會查看保險業代碼，而不是描述。

## <a name="international-classification-of-diseases-icd-9-cm"></a>國際疾病（ICD-9 CM）分類

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 會找到來自 Dictionary_icd_9_updated 的關鍵字。
- 會找到來自 Dictionary_icd_9_codes 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 會找到來自 Dictionary_icd_9_updated 的關鍵字。

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

Dictionary_icd_9_updated 關鍵字字典中的任何字詞，其基礎是根據[疾病的國際分類，第九個修訂版本，臨床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。 這種類型只會尋找字詞，而不是保險碼。

Dictionary_icd_9_codes 關鍵字字典中的任何字詞，其基礎是根據[疾病的國際分類，第九個修訂版本，臨床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。 這種類型只會查看保險業代碼，而不是描述。

## <a name="ip-address"></a>IP 位址

### <a name="format"></a>格式

#### <a name="ipv4"></a>IPv4：
用於格式化（句點）及未格式化（無期間）的 IPv4 位址版本的複雜模式

#### <a name="ipv6"></a>IPv6：
IPv6 數位格式（包含冒號）的複雜模式

### <a name="pattern"></a>模式

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

針對 IPv6，如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 Regex_ipv6_address 找到符合模式的內容。
- 找不到 Keyword_ipaddress 的關鍵字。

針對 IPv4，如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：
- 正則運算式 Regex_ipv4_address 找到符合模式的內容。
- 會找到來自 Keyword_ipaddress 的關鍵字。

針對 IPv6，如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：
- 正則運算式 Regex_ipv6_address 找到符合模式的內容。
- 找不到 Keyword_ipaddress 的關鍵字。

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP （此關鍵字區分大小寫）
- ip 位址 
- ip 位址
- 網際網路通訊協定
- IP-כתובתה 

## <a name="ireland-drivers-license-number"></a>愛爾蘭駕照編號
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

六位數後接四個字母
  
### <a name="pattern"></a>模式

六位數和四個字母：
  
- 六位數
- 四個字母（不區分大小寫）
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_ireland_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_ireland_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_ireland_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- ceadúnas tiomána

## <a name="ireland-national-identification-number"></a>愛爾蘭國身分識別號碼
這個敏感資訊類型實體只包含在歐盟國身分識別號碼的敏感資訊類型中。

### <a name="format"></a>格式

在指定的模式中，字母、數位及空格的九個字元組合
  
### <a name="pattern"></a>模式

在指定的模式中，字母、數位及空格的九個字元組合
  
從01年1月2013至現在：
  
-  七位數 
- 一個檢查碼
- 一個空格或大寫字母 "W" （區分大小寫）
    
在2013年1月1日之前：
  
- 七位數 
- 一個檢查碼
- 一個空格或大寫字母（區分大小寫）
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數會找到符合模式的內容。
- 找到來自的關鍵字。
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數會找到符合模式的內容。
    
```xml
 <!--Ireland national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- 用戶端身分識別服務
- 識別號碼
- 個人號碼
- 個人公開服務號碼
- 個人服務否
- phearsanta seirbhíse poiblí
- pps 否
- pps 號碼
- pps 服務否
- pps uimh
- ppsn
- ppsno#
- ppsno
- 公用服務否
- publicserviceno#
- publicserviceno
- 收入與社交保險號碼
- rsi 否
- rsi 編號
- rsin
- seirbhís aitheantais 用戶端
- uimh.Psp
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí

## <a name="ireland-passport-number"></a>愛爾蘭護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

兩個字母或數位後接7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母或數位後接7位數：
  
- 兩位數或字母（不區分大小寫）
- 七位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_ireland_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_ireland_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_ireland_eu_passport_number**

- 護照號碼
- 愛爾蘭護照號碼
- 護照否
- Pas
- 護照
- passeport
- passeport numero

## <a name="ireland-personal-public-service-pps-number"></a>愛爾蘭個人公開服務（PPS）號碼

### <a name="format"></a>格式

舊格式（直到12月2012日）：
- 七位數後接1-2 個字母 

新格式（1月2013日和之後）：
- 七位數後接兩個字母

### <a name="pattern"></a>模式

舊格式（直到12月2012日）：
- 七位數 
- 1-2 個字母（不區分大小寫） 

新格式（1月2013日和之後）：
- 七位數 
- 字母（不區分大小寫）是字母檢查碼 
- 字母 "A" 或 "H" （不區分大小寫）

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_ireland_pps 找到符合模式的內容。
- 下列其中一項為真：
    - 會找到來自 Keyword_ireland_pps 的關鍵字。
    - 函數 Func_eu_date 會找到正確日期格式的日期。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：
- 函數 Func_ireland_pps 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_ireland_pps"></a>Keyword_ireland_pps

- 個人公開服務號碼 
- PPS 號碼 
- PPS 數位 
- PPS No。 
- Pps# 
- Pps# 
- PPSN 
- 公用服務卡片 
- Uimhir Phearsanta Seirbhíse Poiblí 
- Uimh. Psp 
- Psp 


## <a name="ireland-tax-identification-number"></a>愛爾蘭納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

七位數後接字母，不含空格或分隔符號
  
### <a name="pattern"></a>模式

七位數後接字母：
  
- 七位數 
- 一個字母（不區分大小寫）
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_ireland_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_ireland_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_ireland_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_ireland_eu_tax_file_number"></a>Keywords_ireland_eu_tax_file_number

- 用戶端身分識別服務
- 識別號碼
- 個人號碼
- 個人公開服務號碼
- 個人服務否
- phearsanta seirbhíse poiblí
- pps 否
- pps 號碼
- pps 服務否
- pps uimh
- ppsn
- ppsno#
- ppsno
- 公用服務否
- publicserviceno#
- publicserviceno
- 收入與社交保險號碼
- rsi 否
- rsi 編號
- rsin
- seirbhís aitheantais 用戶端
- uimh.Psp
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí


## <a name="israel-bank-account-number"></a>以色列銀行帳戶號碼

### <a name="format"></a>格式

13位數

### <a name="pattern"></a>模式

格式 化：
- 兩位數 
- 虛線 
- 三位數 
- 虛線 
- 八位數

非
- 13個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_israel_bank_account_number 找到符合模式的內容。
- 會找到來自 Keyword_israel_bank_account_number 的關鍵字。

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- 銀行帳戶號碼 
- 銀行帳戶 
- 帳戶號碼 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>以色列國身分識別號碼

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_israeli_national_id_number 找到符合模式的內容。
- 會找到來自 Keyword_Israel_National_ID 的關鍵字。
- 校驗和通過。

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

- מספר זהות 
- 本國識別碼
   
## <a name="italy-drivers-license-number"></a>義大利駕照編號
這種敏感資訊類型的實體包含在歐盟駕駛執照號碼的敏感資訊類型中，可作為獨立的敏感資訊類型實體。

### <a name="format"></a>格式

10個字母和數位的組合

### <a name="pattern"></a>模式

- 10個字母和數位的組合：
- 一個字母（不區分大小寫） 
- 字母 "A" 或 "V" （不區分大小寫） 
- 七個字母（不區分大小寫）、數位或底線字元 
- 一個字母（不區分大小寫）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_italy_drivers_license_number 找到符合模式的內容。
- 會找到來自 Keyword_italy_drivers_license_number 的關鍵字。

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente di guida 
- patente di guida 

## <a name="italy-national-identification-number"></a>義大利國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

指定之模式中字母和數位的16個字元組合
  
### <a name="pattern"></a>模式

字母和數位的16個字元的組合：
  
- 與系列名稱中的前三個雙子音相對應的三個字母
- 與名字中的第一個、第三個和第四個雙子音相對應的三個字母
- 與出生年份的最後一個數位相對應的兩位數
- 對應至出生月份之字母的一個字母，在字母順序中使用字母，但是只會使用字母 A 到 E、H、L、M、P、P、R 到 T （即，一月份是 A，10月是 R）
- 兩位數的出生月份天數，為了區別 genders，40會新增到女士的出生日。
- 相對於 municipality 人員專屬之地區代碼的四位數（國家/地區的碼用於外國國家）
- 一個同位數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_italy_eu_national_id_card` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_italy_eu_national_id_card` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_italy_eu_national_id_card` 會找到符合模式的內容。 
    
```xml
<!-- Italy national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice 會計
- codice fiscale
- codice 識別碼 personale
- codice personale
- 會計代碼
- numero certificato personale
- numero di identificazione fiscale
- numero 識別碼 personale
- numero personale
- 個人憑證號碼
- 個人程式碼
- 個人識別碼代碼
- 個人號碼
- personalcodeno#
- 稅碼
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅身分識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#

## <a name="italy-passport-number"></a>義大利護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

兩個字母或數位後接7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母或數位後接7位數：
  
- 兩位數或字母（不區分大小寫）
- 七位數
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_italy_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_italy_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_italy_eu_passport_number**

- 義大利護照號碼
- repubblica italiana passaporto
- passaporto
- passaporto italiana
- 護照號碼
- italiana passaporto numero
- passaporto numero
- numéro passeport italien
- numéro passeport

## <a name="italy-tax-identification-number"></a>義大利納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

在指定的模式中有16個字母和數位
  
### <a name="pattern"></a>模式

16個字母和數位：
  
-  與系列名稱中的前三個雙子音相對應的三個字母 
- 與名字中的第一個、第三個和第四個雙子音相對應的三個字母
- 與出生年份的最後一個數位相對應的兩位數
- 對應至出生月份的一個數位（字母的使用字母順序），但是只會使用字母 A 到 E、H、L、M、P、P、R to T （即，一月份為 A，10月是 R）
- 兩位數，對應至出生的出生一天，40會新增至女生中，以區別于男生
- 對應至某人出生之 municipality 之特定區功能變數代碼的四位數（國家/地區的碼是用於國外國家/地區）。
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_italy_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_italy_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_italy_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_italy_eu_tax_file_number"></a>Keywords_italy_eu_tax_file_number

- codice 會計
- codice fiscale
- codice 識別碼 personale
- codice personale
- 會計代碼
- numero certificato personale
- numero di identificazione fiscale
- numero 識別碼 personale
- numero personale
- 個人憑證號碼
- 個人程式碼
- 個人識別碼代碼
- 個人號碼
- personalcodeno#
- 稅碼
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅身分識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#


## <a name="japan-bank-account-number"></a>日本銀行帳戶號碼

### <a name="format"></a>格式

7或8位數

### <a name="pattern"></a>模式

銀行帳戶號碼：
- 7或8位數
- 銀行帳戶分支程式碼：
- 四位數 
- 一個空格或破折號（選用） 
- 三位數

校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_jp_bank_account 找到符合模式的內容。
- 會找到來自 Keyword_jp_bank_account 的關鍵字。
- 下列其中一項為真：
- 函數 Func_jp_bank_account_branch_code 找到符合模式的內容。
- 會找到來自 Keyword_jp_bank_branch_code 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_jp_bank_account 找到符合模式的內容。
- 會找到來自 Keyword_jp_bank_account 的關鍵字。

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- 檢查帳戶號碼 
- 檢查帳戶 
- 檢查帳戶# 
- 檢查帳戶號碼 
- 檢查帳戶# 
- 檢查帳戶否。 
- 檢查帳戶否 
- 銀行帳戶號碼 
- 銀行帳戶 
- 銀行帳戶# 
- 銀行帳戶號碼 
- 銀行帳戶# 
- 銀行帳戶編號 
- 銀行帳戶編號 
- 儲蓄帳戶號碼 
- 儲蓄帳戶 
- 儲蓄帳戶# 
- 儲蓄帳戶編號 
- 儲蓄帳戶# 
- 儲蓄帳戶編號 
- 儲蓄帳戶編號 
- 借方科目編號 
- 借方科目 
- 借方科目# 
- 借方帳戶號碼 
- 借方帳戶# 
- 借方帳戶編號 
- 借方科目編號 
- 口座番號を當座預金口座の確認 
- #アカウントの確認、勘定番號の確認 
- #勘定の確認 
- 勘定番號の確認 
- 口座番號の確認 
- 銀行口座番號 
- 銀行口座 
- 銀行口座＃ 
- 銀行の勘定番號 
- 銀行のacct＃ 
- 銀行の勘定いいえ 
- 銀行口座番號
- 普通預金口座番號 
- 預金口座 
- 貯蓄口座＃ 
- 貯蓄勘定の數 
- 貯蓄勘定＃ 
- 貯蓄勘定番號 
- 普通預金口座番號 
- 引き落とし口座番號 
- 口座番號 
- 口座番號＃ 
- デビットのacct番號 
- デビット勘定＃ 
- デビットACCTの番號 
- デビット口座番號 

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

Otemachi

## <a name="japan-drivers-license-number"></a>日本駕照編號

### <a name="format"></a>格式

12位數

### <a name="pattern"></a>模式

12個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_jp_drivers_license_number 找到符合模式的內容。
- 會找到來自 Keyword_jp_drivers_license_number 的關鍵字。

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- Dl# 
- DL 
- Dls# 
- DL 
- 駕照 
- 驅動程式授權 
- 驅動程式授權 
- 駕駛執照 
- 驅動程式授權 
- 駕駛執照 
- 駕駛許可證 
- 許可證# 
- 許可證 
- lics# 
- 狀態識別碼 
- 狀態識別碼 
- 狀態識別碼 
- 低所得國＃ 
- 免許証 
- 狀態ID
- 狀態の識別 
- 狀態の識別番號 
- 運転免許 
- 運転免許証 
- 運転免許証番號 
   
## <a name="japan-passport-number"></a>日本護照號碼

### <a name="format"></a>格式

兩個字母后接7位數

### <a name="pattern"></a>模式

兩個字母（不區分大小寫）後接7位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_jp_passport 找到符合模式的內容。
- 會找到來自 Keyword_jp_passport 的關鍵字。

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- パスポート 
- パスポート番號 
- パスポートのNum 
- パスポート＃ 

## <a name="japan-residence-card-number"></a>日本住家電話卡號碼

### <a name="format"></a>格式

12個字母和數位

### <a name="pattern"></a>模式

12個字母和數位：
- 兩個字母（不區分大小寫）
- 八位數 
- 兩個字母（不區分大小寫）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_jp_residence_card_number 找到符合模式的內容。
- 會找到來自 Keyword_jp_residence_card_number 的關鍵字。

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- 住家電話卡號碼
- 不含住宅卡片
- 住宅卡片#
- 在留カード番號

## <a name="japan-resident-registration-number"></a>日本居民登記號碼

### <a name="format"></a>格式

11位數

### <a name="pattern"></a>模式

11個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_jp_resident_registration_number 找到符合模式的內容。
- 會找到來自 Keyword_jp_resident_registration_number 的關鍵字。

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- 常駐登記編號
- 常駐寄存器號碼 
- 居民基本登錄號碼 
- 常駐登記編號 
- 居民收銀機否。 
- 居民基本登錄否。 
- 基本居民收銀機 No。 
- 住民登録番號、登録番號をレジデント 
- 住民基本登録番號、登録番號 
- 住民基本レジストリ番號を常駐 
- 登録番號を常駐住民基本台帳登録番號 

   
## <a name="japan-social-insurance-number-sin"></a>日本社交保險號碼（SIN）

### <a name="format"></a>格式

7-12 位數

### <a name="pattern"></a>模式

7-12 位數：
- 四位數 
- 連字號（選用） 
- 六位數或
- 7-12 連續位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_jp_sin 找到符合模式的內容。
- 會找到來自 Keyword_jp_sin 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_jp_sin_pre_1997 找到符合模式的內容。
- 會找到來自 Keyword_jp_sin 的關鍵字。

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- 社交保險保險編號 
- 社交保險編號 
- 社交保險號碼 
- 社會保険のテンキー 
- 社會保険番號 

## <a name="latvia-drivers-license-number"></a>拉脫維亞駕駛執照號碼
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

三個字母后接六位數
  
### <a name="pattern"></a>模式

三個字母和六位數：
  
-  三個字母（不區分大小寫） 
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_latvia_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_latvia_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_latvia_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- autovadītāja apliecība

## <a name="latvia-national-identification-number"></a>拉脫維亞國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

11位數和指定格式的連字號
  
### <a name="pattern"></a>模式

11位數和連字號：
  
-  與出生日期對應的六位數（DDMMYY） 
- 連字號
- 一個數位，對應至出生世紀（"0" 代表19世紀，"1" 代表20世紀，而 "2" 代表21世紀）
- 四位數（隨機產生）
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_latvia_eu_national_id_card` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_latvia_eu_national_id_card` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_latvia_eu_national_id_card` 會找到符合模式的內容。 
    
```xml
<!-- Latvia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- 管理號碼
- alvas nē
- 出生號碼
- 公民編號
- 民事號碼
- 電子人口普查編號
- 電子號碼
- 會計代碼
- 醫療保健使用者號碼
- Id#
- 識別碼-程式碼
- 識別號碼
- identifikācijas numurs
- 識別碼-號碼
- 個別號碼
- latvija alva
- nacionālais 識別碼
- 國家識別碼
- 本國識別號碼
- 本國身分識別號碼
- 本國保險號碼
- 本國收銀機號碼
- nodokļa numurs
- nodokļu 識別碼
- nodokļu identifikācija numurs
- 個人憑證號碼
- 個人程式碼
- 個人識別碼代碼
- 個人號碼
- 個人身分識別碼
- 個人識別碼
- 個人身分識別號碼
- 個人號碼
- 個人數位代碼
- personalcodeno#
- 角色 kods
- 人口識別代碼
- 公用服務號碼
- 登記編號
- 收入數目
- 社交保險號碼
- 社會安全號碼
- 州稅碼
- 稅收檔案編號
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- voter 的號碼

## <a name="latvia-passport-number"></a>拉脫維亞護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

兩個字母或數位後接7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母或數位後接7位數：
  
- 兩位數或字母（不區分大小寫）
- 七位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_latvia_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_latvia_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_latvia_eu_passport_number**

- 護照號碼
- 拉脫維亞文護照號碼
- 護照否
- pase numurs    

## <a name="latvia-tax-identification-number"></a>拉脫維亞納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

11位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

指定的模式中的11位數
  
- 與出生日期相對應的六位數（DDMMYY） 
- 對應至出生世紀的一個數位，其中 "0" 對應于19世紀，"1" 對應于20世紀，"2" 對應于21世紀。
- 四位數
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_latvia_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_latvia_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_latvia_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_latvia_eu_tax_file_number"></a>Keywords_latvia_eu_tax_file_number

- 管理號碼
- alvas nē
- 出生號碼
- 公民編號
- 民事號碼
- 電子人口普查編號
- 電子號碼
- 會計代碼
- 醫療保健使用者號碼
- Id#
- 識別碼-程式碼
- 識別號碼
- identifikācijas numurs
- 識別碼-號碼
- 個別號碼
- latvija alva
- nacionālais 識別碼
- 國家識別碼
- 本國識別號碼
- 本國身分識別號碼
- 本國保險號碼
- 本國收銀機號碼
- nodokļa numurs
- nodokļu 識別碼
- nodokļu identifikācija numurs
- 個人憑證號碼
- 個人程式碼
- 個人識別碼代碼
- 個人號碼
- 個人身分識別碼
- 個人識別碼
- 個人身分識別號碼
- 個人號碼
- 個人數位代碼
- personalcodeno#
- 角色 kods
- 人口識別代碼
- 公用服務號碼
- 登記編號
- 收入數目
- 社交保險號碼
- 社會安全號碼
- 州稅碼
- 稅收檔案編號
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- voter 的號碼

## <a name="lithuania-drivers-license-number"></a>立陶宛駕照編號
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

不含空格及分隔符號的八位數
  
### <a name="pattern"></a>模式

 八位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_lithuania_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_lithuania_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_lithuania_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- vairuotojo pažymėjimas

## <a name="lithuania-national-identification-number"></a>立陶宛國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

11位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

11位數，不含空格及分隔符號：
  
- 對應至人員性別和出生世紀的一個數位
- 對應至出生日期的六位數（YYMMDD） 
- 對應至出生日期之序號的三位數
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_lithuania_eu_national_id_card` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_lithuania_eu_national_id_card` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_lithuania_eu_national_id_card` 會找到符合模式的內容。 
    
```xml
<!-- Lithuania national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- asmens kodas
- 公民服務號碼
- mokesčių識別碼
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių numeris
- 國家識別號碼
- 個人程式碼
- 個人數位代碼
- piliečio paslaugos numeris
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- 唯一識別碼
- 唯一的身分識別號碼
- uniqueidentityno#

## <a name="lithuania-passport-number"></a>立陶宛護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

八位數的數位或字母，不含空格或分隔符號
  
### <a name="pattern"></a>模式

八位數或字母（不區分大小寫）
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_lithuania_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_lithuania_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_lithuania_eu_passport_number**

護照號碼 lithunian 護照號碼護照 no paso numeris

## <a name="lithuania-tax-identification-number"></a>立陶宛納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

11位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

11位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_lithuania_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_lithuania_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_lithuania_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_lithuania_eu_tax_file_number"></a>Keywords_lithuania_eu_tax_file_number

- asmeninis skaitmeninis kodas
- asmens kodas
- 公民服務號碼
- mokesčių識別碼
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių numeris
- 國家識別號碼
- 個人程式碼
- piliečio paslaugos numeris
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- 唯一識別碼
- 唯一的身分識別號碼
- uniqueidentityno#

## <a name="luxemburg-drivers-license-number"></a>Luxemburg 駕駛執照號碼
他的敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

六位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 六位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_luxemburg_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_luxemburg_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_luxemburg_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- fahrerlaubnis

## <a name="luxemburg-national-identification-number"></a>Luxemburg 國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

11位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

11位數
  
- 對應至人員性別和出生世紀的一個數位
- 對應至出生日期的六位數（YYMMDD） 
- 對應至出生日期之序號的三位數
- 一個檢查碼
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_luxemburg_eu_national_id_card` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_luxemburg_eu_national_id_card` 。 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige 識別碼
- eindeutige id-nummer
- eindeutigeid#
- 識別碼 personnelle
- idpersonnelle#
- idpersonnelle
- 個別程式碼
- 個別識別碼
- 個人身分識別
- 個人身分識別
- numéro d'identification 人員
- 個人識別碼
- 個人身分識別
- 個人身分識別
- personalidno#
- personalidnumber#
- persönliche identifikationsnummer
- 唯一識別碼
- 唯一身分識別
- uniqueidkey#

## <a name="luxemburg-passport-number"></a>Luxemburg 護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

八位數的數位或字母，不含空格或分隔符號
  
### <a name="pattern"></a>模式

八位數或字母（不區分大小寫）
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_nation_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_nation_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_nation_eu_passport_number**

護照號碼拉脫維亞文號碼護照 no passnummer

## <a name="luxemburg-tax-identification-number"></a>Luxemburg 納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

13位數沒有空格或分隔符號
  
### <a name="pattern"></a>模式

13位數：
  
- 11位數 
- 兩個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_luxemburg_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_luxemburg_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_luxemburg_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- sécurité sociale 的回收
- étain 非
- étain#
- identifiant d'impôt
- 盧森堡稅收 identifikatiounsnummer
- numéro d'étain
- numéro d'identification 會計 luxembourgeois
- numéro d'identification fiscale
- 社會保障
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- steier 識別碼
- steier identifikatiounsnummer
- steier nummer
- steuer 識別碼
- steueridentifikationsnummer
- steuernummer
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- 辛#
- 辛
- zinnzahl


## <a name="malaysia-identification-card-number"></a>馬來西亞身分識別卡號碼

### <a name="format"></a>格式

12位數包含選擇性連字號

### <a name="pattern"></a>模式

12位數：
- YYMMDD 之日期格式的六位數 
- 破折號（選用） 
- 兩個字母的出生代碼 
- 破折號（選用） 
- 三個亂數字 
- 一位數的性別碼

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 Regex_malaysia_id_card_number 找到符合模式的內容。
- 會找到來自 Keyword_malaysia_id_card_number 的關鍵字。

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- 數位 application 卡片
- i/c
- i/c 否
- Ic
- 內部公司編號
- 身份證
- 身分識別卡
- 身份證
- k/p
- k/p 否
- kad akuan diri
- kad aplikasi 數位
- kad pengenalan 馬來西亞
- Kp
- kp 否
- mykad
- mykas
- mykid
- mypr
- mytentera
- 馬來西亞身分識別卡
- 馬來西亞身分識別卡
- nric
- 個人身分識別卡

## <a name="malta-drivers-license-number"></a>馬爾他駕照編號
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

兩個字元的組合，並在指定的模式中包含六位數
  
### <a name="pattern"></a>模式

兩個字元和六位數的組合：
  
- 兩個字元（數位或字母，不區分大小寫）
- 一個空格（選用）
- 三位數
- 一個空格（選用）
- 三位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_malta_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_malta_eu_driver's_license_number` 。 
    
```xml
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_malta_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- liċenzja tas-sewqan

## <a name="malta-national-identification-number"></a>馬爾他國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

七位數後接一個字母
  
### <a name="pattern"></a>模式

七位數後接一個字母：
  
-  七位數 
- 單一大寫字母（區分大小寫）
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_malta_eu_national_id_card` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_malta_eu_national_id_card` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：
  
- 正則運算式會 `Regex_malta_eu_national_id_card` 找到符合模式的內容。 
    
```xml
 <!--Malta national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- 公民服務號碼
- 識別碼 tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni tat-taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 個人數位代碼
- 唯一識別碼
- 唯一的身分識別號碼
- uniqueidentityno#


## <a name="malta-passport-number"></a>馬爾他護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

七位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

 七位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_malta_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_malta_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_malta_eu_passport_number**

- 護照號碼
- 馬爾他護照號碼
- 護照否
- numru tal-passaport

## <a name="malta-tax-identification-number"></a>馬爾他納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

在馬爾他 nationals 中：7位數和指定的模式中的一個字母
  
非馬爾他 nationals 及馬爾他式實體：9位數
  
### <a name="pattern"></a>模式

馬爾他 nationals：7位數和一個字母
  
-  七位數 
- 一個字母（不區分大小寫）
    
非馬爾他 nationals 及馬爾他式實體：9位數
  
-  九位數 
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_malta_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_malta_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：
  
- 函數 `Func_malta_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- 公民服務號碼
- 識別碼 tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni tat-taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 個人數位代碼
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- 唯一識別碼
- 唯一的身分識別號碼
- uniqueidentityno#

## <a name="netherlands-citizens-service-bsn-number"></a>荷蘭公民服務（BSN）號碼

### <a name="format"></a>格式

8-9 位數包含選擇性空格

### <a name="pattern"></a>模式

8-9 位數：
- 三位數 
- 一個空格（選用） 
- 三位數 
- 一個空格（選用） 
- 2-3 位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_netherlands_bsn 找到符合模式的內容。
- 會找到來自 Keyword_netherlands_bsn 的關鍵字。
- 函數 Func_eu_date2 會找到正確日期格式的日期。
- 校驗和通過。

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_netherlands_bsn"></a>Keyword_netherlands_bsn
  
- bsn#
- bsn
- burgerservicenummer
- 公民服務號碼
- 人員號碼
- 個人號碼
- 個人數位代碼
- 人員相關號碼
- persoonlijk nummer
- persoonlijke numerieke 程式碼
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- 社交會計編號
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- 唯一識別碼
- 唯一的身分識別號碼
- uniqueidentityno#

## <a name="netherlands-drivers-license-number"></a>荷蘭駕駛執照號碼
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

10位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

10位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_netherlands_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_netherlands_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_netherlands_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- permis de conduire
- rijbewijs
- rijbewijsnummer

## <a name="netherlands-national-identification-number"></a>荷蘭國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

九位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_netherlands_eu_national_id_card` 會找到符合模式的內容。 
- 找到來自的關鍵字。
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_netherlands_eu_national_id_card` 會找到符合模式的內容。 
    
```xml
 <!--Netherland national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- bsn#
- bsn
- burgerservicenummer
- 公民服務號碼
- 人員號碼
- 個人號碼
- 個人數位代碼
- 人員相關號碼
- persoonlijk nummer
- persoonlijke numerieke 程式碼
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- 社交會計編號
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- 唯一識別碼
- 唯一的身分識別號碼
- uniqueidentityno#

## <a name="netherlands-passport-number"></a>荷蘭護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

不含空格或分隔符號的九個字母或數位
  
### <a name="pattern"></a>模式

九個字母或數位
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_netherlands_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_netherlands_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_netherlands_eu_passport_number**

- 荷蘭護照號碼
- 護照號碼
- 荷蘭護照號碼
- nederlanden paspoort nummer
- paspoort
- nederlanden paspoortnummer
- paspoortnummer

## <a name="netherlands-tax-identification-number"></a>荷蘭稅務識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

九位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

九位數 
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_netherlands_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_netherlands_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_netherlands_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- hollânske 納稅識別
- hulandes impuesto id 號碼
- hulandes impuesto 識別
- identificatienummer belasting
- identificatienummer van belasting
- impuesto 識別碼
- impuesto 編號
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- 荷蘭稅務識別
- netherland 的納稅識別
- 荷屬安的納稅人
- netherland 的納稅人標識號
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅識別 tal
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- 稅收 tal
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#

## <a name="new-zealand-ministry-of-health-number"></a>紐西蘭健康情況號碼的部

### <a name="format"></a>格式

三個字母、一個空格（選用）及四位數

### <a name="pattern"></a>模式

三個字母（不區分大小寫）一個空格（選用）四位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。
- 會找到來自 Keyword_nz_terms 的關鍵字。
- 校驗和通過。

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

關鍵字

Keyword_nz_terms

- NHI 
- 紐西蘭 
- 健康情況 
- 治療 
   
## <a name="norway-identification-number"></a>挪威身分識別號碼

### <a name="format"></a>格式

11位數

### <a name="pattern"></a>模式

11位數：
- DDMMYY 之日期格式的六位數 
- 三位數個人號碼 
- 兩個檢查碼

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_norway_id_number 找到符合模式的內容。
- 會找到來自 Keyword_norway_id_number 的關鍵字。
- 校驗和通過。
- 如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_norway_id_numbe 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- 個人身分識別號碼
- 挪威文識別碼
- 識別碼號碼
- 識別
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>菲律賓統一多用途識別號碼

### <a name="format"></a>格式

以連字號隔開的12位數

### <a name="pattern"></a>模式

12位數：
- 四位數 
- 連字號 
- 七位數 
- 連字號 
- 一個數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_philippines_unified_id 找到符合模式的內容。
- 會找到來自 Keyword_philippines_id 的關鍵字。

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- 統一的多重用途識別碼 
- UMID 
- 身份證 
- Pinag-isang 多 Layunin 識別碼

## <a name="poland-drivers-license-number"></a>波蘭駕照編號
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

14位數包含2個正斜杠
  
### <a name="pattern"></a>模式

14位數和2轉寄斜線：
  
-  五位數 
- 一個正斜線
- 兩位數
- 一個正斜線
- 七位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_poland_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_poland_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_poland_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- prawo jazdy

## <a name="poland-identity-card"></a>波蘭身分識別卡片

### <a name="format"></a>格式

三個字母和六位數

### <a name="pattern"></a>模式

三個字母（不區分大小寫）後接六位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：函數 Func_polish_national_id 找到符合模式的內容。
會找到來自 Keyword_polish_national_id_passport_number 的關鍵字。
校驗和通過。

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

- Dowód osobisty
- 轉寄 dowodu osobistego
- Nazwa i 轉寄 dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- 道鐘斯指數。 作業系統。

   
## <a name="poland-national-id-pesel"></a>波蘭國民身分證 (PESEL)
這種敏感資訊類型的實體包含在歐盟國身分識別號碼機密資訊類型中，並可作為獨立的機密資訊類型實體。

### <a name="format"></a>格式

11位數

### <a name="pattern"></a>模式

11個連續數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_pesel_identification_number 找到符合模式的內容。
- 會找到來自 Keyword_pesel_identification_number 的關鍵字。
- 校驗和通過。

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- niepowtarzalny 轉寄
- niepowtarzalnynumer
- nr。-pesel
- nr-pesel
- 轉寄 identyfikacyjny
- pesel
- tożsamości narodowej

   
## <a name="poland-passport-number"></a>波蘭護照號碼
這個敏感資訊類型實體包含在歐盟護照號碼機密資訊類型中，並可作為獨立的敏感資訊類型實體。

### <a name="format"></a>格式

兩個字母和七位數

### <a name="pattern"></a>模式

兩個字母（不區分大小寫）後接7位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_polish_passport_number 找到符合模式的內容。
- 會找到來自 Keyword_polish_national_id_passport_number 的關鍵字。
- 校驗和通過。

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

- 轉寄 paszportu
- 星期日。 Paszportu
- Paszport

## <a name="poland-tax-identification-number"></a>波蘭納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

不含空格或分隔符號的11位數
  
### <a name="pattern"></a>模式

11位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_poland_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_poland_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_poland_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

咬#
- 咬
- 轉寄 identyfikacji podatkowej
- numeridentyfikacjipodatkowej#
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- 加值稅識別碼#
- 加值稅識別碼
- 加值稅否
- 加值稅號碼
- vatid#
- vatid
- vatno#
   

## <a name="portugal-citizen-card-number"></a>葡萄牙公民卡片號碼
- 這種敏感資訊類型的實體包含在歐盟國身分識別號碼機密資訊類型中，並可作為獨立的機密資訊類型實體。
- 這種敏感資訊類型實體包含在歐盟社會保險號碼或同等識別碼的敏感資訊類型中。


### <a name="format"></a>格式

八位數

### <a name="pattern"></a>模式

八位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 Regex_portugal_citizen_card 找到符合模式的內容。
- 會找到來自 Keyword_portugal_citizen_card 的關鍵字。

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- 公民卡片
- 檔編號
- documento de identificação
- 識別碼號碼
- 識別碼否
- 識別號碼
- 身分識別卡
- 身分識別卡號碼
- 國際身分識別卡
- 網卡
- número bi de
- número de identificação （民事）
- número de identificação 會計
- número 執行 documento
- 葡萄牙 bi 號碼


## <a name="portugal-drivers-license-number"></a>葡萄牙駕駛執照號碼
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

兩個字母后接指定的模式中的七個數字
  
### <a name="pattern"></a>模式

兩個字母后接7個含特殊字元的數位：
  
- 兩個字母（不區分大小寫） 
- 連字號
- 六位數
- 一個空格
- 一個數位
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_portugal_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_portugal_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_portugal_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- carteira de motorista

## <a name="portugal-passport-number"></a>葡萄牙護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

一個字母后接六位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

一個字母后接六位數：
  
- 一個字母（不區分大小寫）
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_portugal_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_portugal_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_portugal_eu_passport_number**

護照號碼葡萄牙文護照號碼護照 no número do passaporte

## <a name="portugal-tax-identification-number"></a>葡萄牙納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

九位數（沒有空格或分隔符號）
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_portugal_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_portugal_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_portugal_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- 公積金#
- 公積金
- Nif#
- Nif
- número de identificação fisca
- numero 會計
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#


## <a name="romania-drivers-license-number"></a>羅馬尼亞駕照編號
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

一個字元後接八位數
  
### <a name="pattern"></a>模式

一個字元後接八位數：
  
- 一個字母（不區分大小寫）或數位 
- 八位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_romania_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_romania_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_romania_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- permis de conducere

## <a name="romania-national-identification-number"></a>羅馬尼亞國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

13位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

13位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_romania_eu_national_id_card` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_romania_eu_national_id_card` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_romania_eu_national_id_card` 會找到符合模式的內容。 
    
```xml
 <!--Romania national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- Cnp#
- Cnp
- identificare 個人
- 貨到數值的個人
- 貨至 unic identificare
- codnumericpersonal#
- codul 會計 nr。
- identificarea fiscală nr#
- id-ul taxei
- 保險號碼
- insurancenumber#
- 國家識別碼#
- 國家識別碼
- 國家識別號碼
- număr identificare 個人
- număr identitate
- număr 個人 unic
- număridentitate#
- număridentitate
- numărpersonalunic#
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- 個人數位代碼
- 針#
- 針
- 納稅檔案編號
- 稅收檔案編號
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- 唯一識別碼
- 唯一的身分識別號碼
- uniqueidentityno#
- uniqueidentityno

## <a name="romania-passport-number"></a>羅馬尼亞護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

8或9位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

8或9位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_romania_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_romania_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_romania_eu_passport_number**

- 護照號碼
- 羅馬尼亞護照號碼
- 護照否
- numărul pașaportului

## <a name="romania-tax-identification-number"></a>羅馬尼亞納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

13位數沒有空格或分隔符號
  
### <a name="pattern"></a>模式

13位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_romania_eu_tax_file_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_romania_eu_tax_file_number` 。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_romania_eu_tax_file_number"></a>Keywords_romania_eu_tax_file_number

- Cnp#
- Cnp
- identificare 個人
- 貨到數值的個人
- 貨至 unic identificare
- codnumericpersonal#
- codul 會計 nr。
- identificarea fiscală nr#
- id-ul taxei
- 保險號碼
- insurancenumber#
- 國家識別碼#
- 國家識別碼
- 國家識別號碼
- număr identificare 個人
- număr identitate
- număr 個人 unic
- număridentitate#
- număridentitate
- numărpersonalunic#
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- 個人數位代碼
- 針#
- 針
- 納稅檔案編號
- 稅收檔案編號
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#
- 唯一識別碼
- 唯一的身分識別號碼
- uniqueidentityno#
- uniqueidentityno



## <a name="saudi-arabia-national-id"></a>沙烏地阿拉伯國際身分識別

### <a name="format"></a>格式

10位數

### <a name="pattern"></a>模式

10個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_saudi_arabia_national_id 找到符合模式的內容。
- 會找到來自 Keyword_saudi_arabia_national_id 的關鍵字。

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- 身分識別卡 
- 我的卡片編號 
- 識別碼 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>新加坡國家註冊身分識別卡片（NRIC）號碼

### <a name="format"></a>格式

九個字母和數位

### <a name="pattern"></a>模式

- 九個字母和數位：
- 字母 "F"、"G"、"S" 或 "T" （不區分大小寫） 
- 七位數 
- 字母檢查碼

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 Regex_singapore_nric 找到符合模式的內容。
- 會找到來自 Keyword_singapore_nric 的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_singapore_nric 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- 國家註冊身分識別卡 
- 身分識別卡號碼 
- NRIC 
- Ic 
- 外識別碼 
- 翅 
- 身份證 
- 身份證 

## <a name="slovakia-drivers-license-number"></a>斯洛伐克駕照編號
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

一個字元後接7位數
  
### <a name="pattern"></a>模式

一個字元後接7位數
  
- 一個字母（不區分大小寫）或數位
-  七位數 
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_slovakia_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_slovakia_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_slovakia_eu_driver ' s_license_number**

「dl # 驅動程式授權驅動程式授權號碼驅動程式授權驅動程式 .lic。
驅動程式授權驅動程式授權驅動程式的授權號碼駕駛執照號碼駕駛執照號碼 dlno # vodičský preukaz

## <a name="slovakia-national-identification-number"></a>斯洛伐克國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

10位數包含一個反斜線
  
### <a name="pattern"></a>模式

10位數包含一個反斜線：
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_slovakia_eu_national_id_card` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_slovakia_eu_national_id_card` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_slovakia_eu_national_id_card` 會找到符合模式的內容。 
    
```xml
 <!-- Slovakia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- 出生號碼
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- 識別碼號碼
- 識別碼否
- 識別號碼
- identifikačná karta č
- identifikačné číslo
- 身分識別卡
- 身分識別卡號碼
- národná identifikačná značka č
- 國家/地區號碼
- nationalnumber#
- nemzeti személyazonosító igazolvány
- personalidnumber#
- rč
- rodne cislo
- rodné číslo
- 社會安全號碼
- Ssn#
- Ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- 納稅檔案編號
- 稅收檔案編號
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#

## <a name="slovakia-passport-number"></a>斯洛伐克護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

一個數位或字母后接7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

一個數位或字母（不區分大小寫）後接7位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_slovakia_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_slovakia_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_slovakia_eu_passport_number**

- 護照號碼
- 斯洛伐克護照號碼
- 護照否
- číslo pasu

## <a name="slovakia-tax-identification-number"></a>斯洛伐克納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

10位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

10位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_slovakia_eu_tax_file_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_slovakia_eu_tax_file_number` 。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_slovakia_eu_tax_file_number"></a>Keywords_slovakia_eu_tax_file_number

- azonosító szám
- 出生號碼
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- 識別碼號碼
- 識別碼否
- 識別號碼
- identifikačná karta č
- identifikačné číslo
- 身分識別卡
- 身分識別卡號碼
- národná identifikačná značka č
- 國家/地區號碼
- nationalnumber#
- nemzeti személyazonosító igazolvány
- personalidnumber#
- rč
- rodne cislo
- rodné číslo
- 社會安全號碼
- Ssn#
- Ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- 納稅檔案編號
- 稅收檔案編號
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#


## <a name="slovenia-drivers-license-number"></a>斯洛維尼亞駕照編號
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_slovenia_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_slovenia_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_slovenia_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照 
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- vozniško dovoljenje

## <a name="slovenia-national-identification-number"></a>斯洛維尼亞國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

13位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

指定的模式中的13位數：
  
-  對應至出生日期（DDMMLLL）的7位數，其中 "LLL" 會對應至出生年份的後三位數 
- 對應至出生區域的兩位數
- 三個數字，對應于一天出生的性別和序號碼組合（000-499 的插頭和500-999 的女）
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_slovenia_eu_national_id_card` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_slovenia_eu_national_id_card` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_slovenia_eu_national_id_card` 會找到符合模式的內容。 
    
```xml
 <!-- Slovenia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- 身份證
- 識別號碼
- identifikacijska številka
- 身份證
- nacionalna 識別碼
- nacionalni potni 清單
- 國家識別碼
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- 個人程式碼
- 個人號碼
- 個人數位代碼
- številka državljana
- 唯一公民編號
- 唯一識別碼
- 唯一的身分識別號碼
- 唯一主公民號碼
- 唯一註冊號碼
- uniqueidentityno#
- uniqueidentityno#

## <a name="slovenia-passport-number"></a>斯洛維尼亞護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

兩個字母后接7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母后接7位數：
  
- 字母 "P"
- 單一大寫字母
- 七位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_slovenia_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_slovenia_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_slovenia_eu_passport_number**

護照號碼斯洛維尼亞護照號碼護照 no številka potnega lista

## <a name="slovenia-tax-identification-number"></a>斯洛維尼亞納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

八位數沒有空格或分隔符號
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_slovenia_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_slovenia_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_slovenia_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- 納稅檔案編號
- 稅收檔案編號
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#



## <a name="south-africa-identification-number"></a>南非識別號碼

### <a name="format"></a>格式

可以包含空格的13位數

### <a name="pattern"></a>模式

13位數：
- YYMMDD 之日期格式的六位數 
- 四位數 
- 單一數位的公民指示器 
- 數位 "8" 或 "9" 
- 一個數位的校驗和位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_south_africa_identification_number 找到符合模式的內容。
- 會找到來自 Keyword_south_africa_identification_number 的關鍵字。
- 校驗和通過。

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- 身份證
- ID
- 識別 
   
## <a name="south-korea-resident-registration-number"></a>韓國居民登記號碼

### <a name="format"></a>格式

13位數包含連字號

### <a name="pattern"></a>模式

13位數：
- YYMMDD 之日期格式的六位數 
- 連字號 
- 一個數位是由世紀和性別決定 
- 四位數的出生區功能變數代碼 
- 一種用來區分先前號碼相同之人員的數位 
- 檢查碼。

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_south_korea_resident_number 找到符合模式的內容。
- 會找到來自 Keyword_south_korea_resident_number 的關鍵字。
- 校驗和通過。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_south_korea_resident_number 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- 國民身分證 
- 公民註冊號碼 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>西班牙駕照編號
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

八位數後接一個字元
  
### <a name="pattern"></a>模式

八位數後接一個字元：
  
- 八位數 
- 一個數位或字母（不區分大小寫）
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_spain_eu_driver's_license_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_spain_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_spain_eu_driver ' s_license_number**

- dlno#
- Dl#
- 驅動程式 .lic。
- 驅動程式許可證
- 駕照
- 驅動程式許可證
- 驅動程式授權
- 駕駛執照
- 駕駛執照
- 駕駛許可證
- 駕照
- 驅動程式許可證號碼
- 駕駛執照號碼
- 驅動程式許可證數目
- 驅動程式授權號碼
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛許可證號碼
- 駕駛執照號碼
- 駕駛允許
- 駕駛允許號碼
- permiso de conducción
- permiso conducción
- número licencia conducir
- número de carnet de conducir
- número carnet conducir
- licencia conducir
- número de permiso de conducir
- número de permiso conducir
- número permiso conducir
- permiso conducir
- licencia de manejo
- el carnet de conducir
- carnet conducir

## <a name="spain-national-identification-number"></a>西班牙國身分識別號碼
這個敏感資訊類型實體僅可用於歐盟國身分識別號碼的敏感資訊類型。

### <a name="format"></a>格式

七位數後接一個字元
  
### <a name="pattern"></a>模式

七位數後接一個字元
  
- 七位數
- 一個數位或字母（不區分大小寫）
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_spain_eu_national_id_card` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_spain_eu_national_id_card"` 。 
    
```xml
<!-- Spain national identification number -->
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni#
- dni
- dninúmero#
- documento nacional de identidad
- identidad único
- identidadúnico#
- 保險號碼
- 國家識別號碼
- 本國身分識別
- nationalid#
- nationalidno#
- 聶#
- 聶
- nienúmero#
- número de identificación
- número nacional identidad
- 個人身分識別號碼
- 個人身分識別
- 唯一的身分識別號碼
- uniqueid#

## <a name="spain-passport-number"></a>西班牙護照號碼
這個敏感資訊類型實體只適用于歐盟護照號碼機密資訊類型。

### <a name="format"></a>格式

8或9個字元組合的字母和數位，不含空格或分隔符號
  
### <a name="pattern"></a>模式

字母和數位的8或9個字元組合：
  
-  兩位數或字母 
- 一個數位或字母（選用）
- 六位數
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_spain_eu_passport_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_spain_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

**Keywords_spain_eu_passport_number**

- 護照
- 西班牙護照
- 護照手冊
- 護照號碼
- 護照否
- libreta pasaporte
- número pasaporte
- españa pasaporte
- pasaporte


## <a name="spain-social-security-number-ssn"></a>西班牙社會安全號碼（SSN）
此機密資訊類型的實體包含在歐盟社會保險號碼或同等識別碼的敏感資訊類型中，並可作為獨立的敏感資訊類型實體。

### <a name="format"></a>格式

11-12 位數

### <a name="pattern"></a>模式

11-12 位數：
- 兩位數 
- 一個正斜線（選用） 
- 7-8 位數 
- 一個正斜線（選用） 
- 兩位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_spanish_social_security_number 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無

## <a name="spain-tax-identification-number"></a>西班牙納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

指定的模式中的7或8位數，以及一或兩個字母
  
### <a name="pattern"></a>模式

具有西班牙國身分識別卡的西班牙文自然人員：
  
-  八位數 
- 單一大寫字母（區分大小寫） 
    
沒有西班牙國身分身分身分識別卡的非居民 Spaniards
  
- 一個大寫字母 "L" （區分大小寫）
- 七位數
- 單一大寫字母（區分大小寫） 
    
在沒有西班牙國身分識別卡的14年年齡底下的居民 Spaniards：
  
- 一個大寫字母 "K" （區分大小寫）
-  七位數 
- 單一大寫字母（區分大小寫）
    
Foreigners 與 Foreigner 的識別號碼
  
- 一個大寫的字母，為 "X"、"Y" 或 "Z" （區分大小寫） 
- 七位數
- 單一大寫字母（區分大小寫） 
    
沒有 Foreigner 識別碼的 Foreigners
  
- 一個大寫的字母 "M" （區分大小寫） 
- 七位數
- 單一大寫字母（區分大小寫） 
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_spain_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_spain_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_spain_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- Cif
- cifid#
- cifnúmero#
- número de contribuyente
- número de identificación 會計
- número de impuesto corporativo
- spanishcifid#
- spanishcifid
- spanishcifno#
- spanishcifno
- 納稅檔案編號
- 稅收檔案編號
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#


## <a name="sql-server-connection-string"></a>SQL Server 連接字串

### <a name="format"></a>格式

字串 "User Id"、"User ID"、"uid" 或 "UserId"，後面加上下列模式中所述的字元及字串。

### <a name="pattern"></a>模式

- 字串 "User Id"、"User ID"、"uid" 或 "UserId"
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "Password" 或 "pwd"，其中 "pwd" 前面不是小寫字母
- 等號（=）
- 不是貨幣符號（$）的任何字元、百分比符號（%）、大於符號（>）、符號（@）、引號（"）、分號（;)、左大括弧（[）或左中括弧（{）
- 任何7-128 個字元的組合，不是分號（;)、正斜線（/）或引號（"）
- 一個分號（;)或引號（"）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 正則運算式 CEP_Regex_SQLServerConnectionString 找到符合模式的內容。
- 找**不**到來自 CEP_GlobalFilter 的關鍵字。
- 正則運算式**CEP_PasswordPlaceHolder 不會找到符合**模式的內容。
- 正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- 部分密碼
- somepassword
- secretPassword
- 樣品

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）

- 密碼或密碼後接0-2 個空格、等號（=）、0-2 空間及星號（*）-OR------------------
- 密碼或密碼，接著：
    - 等號（=）
    - 小於符號（<）
    - 1-200 個字元的任何組合，其大小大寫或小寫字母、數位、星號（*）、連字號（-）、底線（_）或空白字元
    - 大於符號（>）

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）

- 尚未
- 送交
- 資料庫
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="sweden-drivers-license-number"></a>瑞典駕駛執照號碼
這個敏感資訊類型實體只有歐盟駕駛執照號碼機密資訊類型提供。

### <a name="format"></a>格式

10位數包含連字號
  
### <a name="pattern"></a>模式

10位數包含連字號：
  
-  六位數 
- 連字號
- 四位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式會 `Regex_sweden_eu_driver's_license_number` 找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_sweden_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>關鍵字

**Keywords_sweden_eu_driver ' s_license_number**

- Dl#
- 駕照
- 駕駛執照號碼
- 驅動程式許可證
- 驅動程式 .lic。
- 驅動程式授權
- 驅動程式許可證
- 駕駛執照
- 駕駛執照號碼
- 駕駛執照號碼
- 駕駛執照號碼
- dlno#
- körkort

## <a name="sweden-national-id"></a>瑞典國民身分證號
這種敏感資訊類型的實體包含在歐盟國身分識別號碼機密資訊類型中，並可作為獨立的機密資訊類型實體。

### <a name="format"></a>格式

10或12位數和選擇性分隔符號

### <a name="pattern"></a>模式

10或12位數和選用的分隔符號：
- 2-4 位數（選用） 
- 日期格式 YYMMDD 的六位數 
- 分隔符號 "-" 或 "+" （選用），加上
- 四位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_swedish_national_identifier 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

否
   
## <a name="sweden-passport-number"></a>瑞典護照號碼
這個敏感資訊類型實體包含在歐盟護照號碼機密資訊類型中，並可作為獨立的敏感資訊類型實體。

### <a name="format"></a>格式

八位數

### <a name="pattern"></a>模式

八個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_sweden_passport_number 找到符合模式的內容。
- 下列其中一項為真：
    - 會找到來自 Keyword_passport 的關鍵字。
    - 會找到來自 Keyword_sweden_passport 的關鍵字。

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- 簽證要求 
- 外部註冊卡 
- Schengen 簽證 
- Schengen 簽證 
- 簽證處理 
- 簽證類型 
- 單一專案 
- 多重專案 
- G3 處理費用 

#### <a name="keyword_passport"></a>Keyword_passport

- 護照號碼 
- 護照否 
- 護照# 
- 護照# 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番號 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport 非 
- Passeport# 
- Passeport# 
- PasseportNon 
- Passeportn ° 

## <a name="sweden-social-security-number-or-equivalent-identification"></a>瑞典社會安全號碼或對等身分識別
這個敏感資訊類型實體只有歐盟社會保險號碼或同等識別碼的敏感資訊類型提供。

### <a name="format"></a>格式

12位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

12位數：
  
-  對應至出生日期的八位數（YYYYMMDD） 
- 對應至序數的三位數，其中： 
  - 序數中的最後一個數位是由為男指派的奇數和偶數的女數位來表示性別
  - 最多1990，corresponded 序數的指派給在該縣內，號碼的持有者是出生的，或（如果是在1947之前出生），在該縣中，根據稅收記錄，在年1月 1 1947 日，使用特殊的程式碼（通常是9，7位數）進行 immigrants 
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_sweden_eu_ssn_or_equivalent` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_sweden_eu_ssn_or_equivalent` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_sweden_eu_ssn_or_equivalent` 會找到符合模式的內容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

- 個人號碼
- 識別號碼
- 個人識別碼否
- identity no
- 識別碼否
- 個人身分識別否
- personnummer 識別碼
- personligt id-nummer
- unikt id-nummer
- personnummer
- identifikationsnumret
- personnummer#
- identifikationsnumret#

## <a name="sweden-tax-identification-number"></a>瑞典納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。

### <a name="format"></a>格式

指定之模式中的10位數和符號
  
### <a name="pattern"></a>模式

10位數和符號：
  
- 與出生日期對應的六位數（YYMMDD） 
- 正負號或反斜線
- 在下列情況下，識別號碼唯一的三位數： 
  - 若為1990之前所簽發的號碼，第七和第八位數識別出生的縣或對外出生的人員
  - 第九個位置中的位數會以奇數為單位表示，甚至是對女的性別
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數 `Func_sweden_eu_tax_file_number` 會找到符合模式的內容。 
- 找到來自的關鍵字 `Keywords_sweden_eu_tax_file_number` 。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_sweden_eu_tax_file_number` 會找到符合模式的內容。 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- 個人號碼
- personnummer
- skatt 識別碼 nummer
- skatt identifikation
- skatteBetalarens identifikationsnummer
- sverige tin
- 納稅檔案
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 納稅號碼
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#



## <a name="swift-code"></a>SWIFT 程式碼

### <a name="format"></a>格式

四個字母后接5-31 個字母或數位

### <a name="pattern"></a>模式

四個字母后接5-31 個字母或數位：
- 四個字母的銀行代碼（不區分大小寫） 
- 選擇性的空格 
- 4-28 個字母或數位（基本銀行帳戶號碼（BBAN）） 
- 選擇性的空格 
- 1-3 個字母或數位（BBAN 的其餘部分）

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_swift 找到符合模式的內容。
- 會找到來自 Keyword_swift 的關鍵字。

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_swift"></a>Keyword_swift

- 標準化9362的國際組織 
- iso 9362 
- iso9362 
- 迅速\# 
- swiftcode 
- swiftnumber 
- swiftroutingnumber 
- swift 程式碼 
- swift 號碼# 
- swift 路由編號 
- bic 編號 
- bic 程式碼 
- bic\# 
- bic\# 
- 銀行識別碼代碼 
- 標準化9362 
- 迅速＃ 
- SWIFTコード 
- SWIFT番號 
- 迅速なルーティング番號 
- BIC番號 
- BICコード 
- 銀行識別コードのための國際組織 
- 組織 internationale de normalisation 9362 
- rapide\# 
- 程式碼 SWIFT 
- le numéro 解除的 swift 
- swift numéro d'acheminement 
- le numéro BIC 
- \#BIC 
- 程式碼 identificateur de banque 
   
## <a name="taiwan-national-identification-number"></a>臺灣國身分識別號碼

### <a name="format"></a>格式

一個字母（英文）後後的九位數

### <a name="pattern"></a>模式

一個字母（英文）後接9位數：
- 一個字母（英文、不區分大小寫） 
- 數位 "1" 或 "2" 
- 八位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_taiwanese_national_id 找到符合模式的內容。
- 會找到來自 Keyword_taiwanese_national_id 的關鍵字。
- 校驗和通過。

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_taiwanese_national_id"></a>Keyword_taiwanese_national_id

- 身份證字號 
- 身份證 
- 身份證號碼 
- 身份證號 
- 身分證字號 
- 身分證 
- 身分證號碼 
- 身份證號 
- 身分證統一編號 
- 國民身分證統一編號 
- 簽名 
- 蓋章 
- 簽名或蓋章 
- 簽章   
   
## <a name="taiwan-passport-number"></a>臺灣護照號碼

### <a name="format"></a>格式

- 生物識別護照號碼：9位數
- 非生物識別護照號碼：9位數

### <a name="pattern"></a>模式
生物識別護照號碼：
- 數位 "3" 
- 八位數

無生物識別護照號碼：
- 九位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_taiwan_passport 找到符合模式的內容。
- 會找到來自 Keyword_taiwan_passport 的關鍵字。

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC 護照號碼 
- 護照號碼 
- 護照否 
- 護照編號 
- 護照# 
- 護照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>臺灣居民憑證（ARC/TARC）號碼

### <a name="format"></a>格式

10個字母和數位

### <a name="pattern"></a>模式

10個字母和數位：
- 兩個字母（不區分大小寫） 
- 八位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_taiwan_resident_certificate 找到符合模式的內容。
- 會找到來自 Keyword_taiwan_resident_certificate 的關鍵字。

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- 常駐憑證 
- 常駐 Cert 
- 常駐 Cert。 
- 身分識別卡 
- 外部居民憑證 
- ARC 
- 臺灣地區常駐憑證 
- TARC 
- 居留證 
- 外僑居留證 
- 台灣地區居留證 

## <a name="thai-population-identification-code"></a>泰國人口識別碼

### <a name="format"></a>格式

13位數

### <a name="pattern"></a>模式

13位數：
- 第一個數位不是0或9 
- 12位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_Thai_Citizen_Id 找到符合模式的內容。
- 會找到來自 Keyword_Thai_Citizen_Id 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_Thai_Citizen_Id 找到符合模式的內容。

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_thai_citizen_id"></a>Keyword_Thai_Citizen_Id

- 識別碼號碼
- 識別號碼
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>土耳其國身分識別號碼

### <a name="format"></a>格式

11位數

### <a name="pattern"></a>模式

11位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_Turkish_National_Id 找到符合模式的內容。
- 會找到來自 Keyword_Turkish_National_Id 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_Turkish_National_Id 找到符合模式的內容。

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_turkish_national_id"></a>Keyword_Turkish_National_Id

- TC Kimlik 否
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık 否

## <a name="uk-drivers-license-number"></a>英國。 駕駛執照號碼
這種敏感資訊類型的實體包含在歐盟駕駛執照號碼的敏感資訊類型中，可作為獨立的敏感資訊類型實體。

### <a name="format"></a>格式

以指定格式的18個字母和數位的組合

### <a name="pattern"></a>模式

18個字母和數位：
- 五個字母（不區分大小寫）或數位 "9" 取代字母 
- 一個數位 
- MMDDY 日期格式中的5位數（如果驅動程式是女，則為第7個字元 62 51，而不是1到12，則增加50）
- 兩個字母（不區分大小寫）或數位 "9" 取代字母 
- 五位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_uk_drivers_license 找到符合模式的內容。
- 會找到來自 Keyword_uk_drivers_license 的關鍵字。
- 校驗和通過。

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_uk_drivers_license"></a>Keyword_uk_drivers_license

- DVLA 
- 淺 vans 
- quadbikes 
- 汽車轎車 
- 125cc 
- sidecar 
- 三輪車 
- 摩托車 
- photocard 許可證 
- learner 驅動程式 
- 許可證持有者 
- 許可證持有人 
- 駕駛許可證 
- 駕駛許可證 
- 雙控制汽車 
   
## <a name="uk-electoral-roll-number"></a>英國。 electoral 編號

### <a name="format"></a>格式

兩個字母后接1-4 位數

### <a name="pattern"></a>模式

兩個字母（不區分大小寫）後接1-4 數目

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_uk_electoral 找到符合模式的內容。
- 會找到來自 Keyword_uk_electoral 的關鍵字。

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- 理事會提名 
- 提名表單 
- electoral 寄存器 
- electoral 輥

   
## <a name="uk-national-health-service-number"></a>英國。 本國健康情況服務號碼

### <a name="format"></a>格式

以空格分隔的10-17 位數

### <a name="pattern"></a>模式

10-17 位數：
- 3或10位數 
- 一個空格 
- 三位數 
- 一個空格 
- 四位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_uk_nhs_number 找到符合模式的內容。
- 下列其中一項為真：
    - 會找到來自 Keyword_uk_nhs_number 的關鍵字。
    - 會找到來自 Keyword_uk_nhs_number1 的關鍵字。
    - 會找到來自 Keyword_uk_nhs_number_dob 的關鍵字。
- 校驗和通過。

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- 全國健康情況服務 
- Nhs 
- 健康情況服務授權 
- 健康情況授權單位

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- 患者識別碼 
- 患者識別 
- 患者否 
- 病人編號

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- Gp 
- DOB 
- D. B 
- 出生日期 
- 出生日期 
   
## <a name="uk-national-insurance-number-nino"></a>英國。 本國保險號碼（NINO）
此機密資訊類型的實體包含在歐盟國家 Identificaiton 號碼機密資訊類型中，也可作為獨立機密資訊類型實體使用。

### <a name="format"></a>格式

以空格或破折號分隔的7個字元或9個字元

### <a name="pattern"></a>模式

兩種可能的模式：

- 兩個字母（有效的 NINOs 只會使用此前置詞中的特定字元，此模式會驗證; 不區分大小寫）
- 六位數
- "A"、"B"、"C" 或 "d" （類似前置詞）只允許在尾碼中使用某些字元; 不區分大小寫）

OR

- 兩個字母
- 一個空格或破折號
- 兩位數
- 一個空格或破折號
- 兩位數
- 一個空格或破折號
- 兩位數
- 一個空格或破折號
- ' A '、' B '、' C ' 或 ' d ' 是 '

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_uk_nino 找到符合模式的內容。
- 會找到來自 Keyword_uk_nino 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_uk_nino 找到符合模式的內容。
- 找不到 Keyword_uk_nino 的關鍵字。

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- 本國保險號碼
- 全國保險貢獻
- 保護法案
- 保險
- 社會安全號碼
- 保險費應用程式
- 醫療應用程式
- 社交保險
- 醫療注意力
- 社會保障
- 英國
- 保險
    
## <a name="uk-tax-identification-number"></a>英國。 納稅識別號碼
此機密資訊類型實體僅可用於歐盟納稅識別碼的敏感資訊類型。


### <a name="format"></a>格式

唯一的納稅人參考（UTR）：10位數，不含空格及分隔符號
 
  
### <a name="pattern"></a>模式

唯一的納稅人參考（UTR）：10位數

  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數 `Func_uk_eu_tax_file_number` 會找到符合模式的內容。 
    
- 找到來自的關鍵字 `Keywords_uk_eu_tax_file_number` 。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- 納稅號碼
- 納稅檔案
- 納稅識別碼
- 納稅識別碼否
- 納稅識別號碼
- 納稅否#
- 納稅否
- 稅務登記編號
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 納稅人識別碼
- tin no
- 錫#

## <a name="us-bank-account-number"></a>美國銀行帳戶號碼

### <a name="format"></a>格式

8-17 位數

### <a name="pattern"></a>模式

8-17 連續位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 正則運算式 Regex_usa_bank_account_number 找到符合模式的內容。
- 會找到來自 Keyword_usa_Bank_Account 的關鍵字。

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- 檢查帳戶號碼 
- 檢查帳戶 
- 檢查帳戶# 
- 檢查帳戶號碼 
- 檢查帳戶# 
- 檢查帳戶否。 
- 檢查帳戶否 
- 銀行帳戶號碼 
- 銀行帳戶# 
- 銀行帳戶號碼 
- 銀行帳戶# 
- 銀行帳戶編號 
- 銀行帳戶編號 
- 儲蓄帳戶號碼 
- 儲蓄帳戶。 
- 儲蓄帳戶# 
- 儲蓄帳戶編號 
- 儲蓄帳戶# 
- 儲蓄帳戶編號 
- 儲蓄帳戶編號 
- 借方科目編號 
- 借方科目 
- 借方科目# 
- 借方帳戶號碼 
- 借方帳戶# 
- 借方帳戶編號 
- 借方科目編號 

## <a name="us-drivers-license-number"></a>美國駕駛執照號碼

### <a name="format"></a>格式

取決於狀態

### <a name="pattern"></a>模式

取決於狀態--例如紐約：
- 已格式化的九位數，如 ddd ddd ddd 會相符。
- 九位數的 ddddddddd 不相符。

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_new_york_drivers_license_number 找到符合模式的內容。
- 找到來自 Keyword_ [state_name] _drivers_license_name 的關鍵字。
- 會找到來自 Keyword_us_drivers_license 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：
- 函數 Func_new_york_drivers_license_number 找到符合模式的內容。
- 找到來自 Keyword_ [state_name] _drivers_license_name 的關鍵字。
- 會找到來自 Keyword_us_drivers_license_abbreviations 的關鍵字。
- 找不到 Keyword_us_drivers_license 的關鍵字。

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- Dl 
- Dls 
- 民盟 
- CDLS 
- ID 
- IDs 
- Dl# 
- Dls# 
- 民盟# 
- CDLS# 
- ID:#
- IDs# 
- 識別碼 
- 識別碼號碼 
- 許可證 
- 許可證# 

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- DriverLicenses 
- 驅動程式許可證 
- 驅動程式 Lics 
- 駕照 
- 驅動程式授權 
- DriversLic 
- DriversLics 
- DriversLicense 
- DriversLicenses 
- 驅動程式 .Lic 
- 驅動程式 Lics 
- 驅動程式授權 
- 驅動程式授權 
- Driver'Lic 
- Driver'Lics 
- Driver'License 
- Driver'Licenses 
- 驅動程式「.Lic 
- 驅動程式 ' Lics 
- 駕駛執照 
- 驅動程式的授權
- Driver'sLic 
- Driver'sLics 
- Driver'sLicense 
- Driver'sLicenses 
- 驅動程式的 .Lic 
- 驅動程式的 Lics 
- 駕駛執照 
- 駕駛執照 
- 識別號碼 
- 識別號碼 
- 識別# 
- 身份證 
- 身份證 
- 身分識別卡 
- 身份證 
- DriverLic# 
- DriverLics# 
- DriverLicense# 
- DriverLicenses# 
- 驅動程式許可證# 
- 驅動程式 Lics# 
- 駕照# 
- 驅動程式授權# 
- DriversLic# 
- DriversLics# 
- DriversLicense# 
- DriversLicenses# 
- 驅動程式 .Lic# 
- 驅動程式 Lics# 
- 驅動程式授權# 
- 驅動程式授權# 
- Driver'Lic# 
- Driver'Lics# 
- Driver'License# 
- Driver'Licenses# 
- 驅動程式「.Lic# 
- 驅動程式 ' Lics# 
- 駕駛執照# 
- 驅動程式的授權# 
- Driver'sLic# 
- Driver'sLics# 
- Driver'sLicense# 
- Driver'sLicenses# 
- 驅動程式的 .Lic# 
- 驅動程式的 Lics# 
- 駕駛執照# 
- 駕駛執照# 
- 身份證# 
- 身份證# 
- 身分識別卡# 
- 身份證# 


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_ [state_name] _drivers_license_name

- 省/市/自治區縮寫（例如，"NY"） 
- 狀態名稱（例如，"紐約"）

## <a name="us-individual-taxpayer-identification-number-itin"></a>美國個別的納稅人識別號碼（ITIN）

### <a name="format"></a>格式

以 "9" 開頭且包含 "7" 或 "8" 的九位數做為第四位數，可選擇性地使用空格或破折號格式化

### <a name="pattern"></a>模式

格式 化：
- 數位 "9" 
- 兩位數 
- 一個空格或破折號 
- "7" 或 "8" 
- 一個數位 
- 一個空格或破折號 
- 四位數

非
- 數位 "9" 
- 兩位數 
- "7" 或 "8" 
- 五位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_formatted_itin 找到符合模式的內容。
- 下列專案中至少有一個為真：
    - 會找到來自 Keyword_itin 的關鍵字。
    - 函數 Func_us_address 會找到正確日期格式的位址。
    - 函數 Func_us_date 會找到正確日期格式的日期。
    - 會找到來自 Keyword_itin_collaborative 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_unformatted_itin 找到符合模式的內容。
- 下列專案中至少有一個為真：
    - 會找到來自 Keyword_itin_collaborative 的關鍵字。
    - 函數 Func_us_address 會找到正確日期格式的位址。
    - 函數 Func_us_date 會找到正確日期格式的日期。

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_itin"></a>Keyword_itin

- 納稅人 
- 納稅識別碼 
- 納稅識別 
- itin 
- Ssn 
- 錫 
- 社會保障 
- 納稅人 
- itins 
- taxid 
- 個別納稅人 

#### <a name="keyword_itin_collaborative"></a>Keyword_itin_collaborative

- License 
- Dl 
- DOB 
- 出生日期 
- 生日 
- 出生日期 

## <a name="us-social-security-number-ssn"></a>U.S. 社會安全號碼（SSN）

### <a name="format"></a>格式

9位數（可能是格式化或未格式化的模式）

> [!NOTE]
> 如果在2011之前發出，則 SSN 具有強格式，其中的號碼的某些部分必須介於一定範圍內，才是有效的（但沒有任何 checksum）。

### <a name="pattern"></a>模式

四種功能會在四種不同的模式中尋找主旨 ssn：
- Func_ssn 會2011以主旨 ssn 的強格式格式化，並以短劃線或空格格式化（ddd-dd-dddd 或 ddd dd dddd）來尋找
- Func_unformatted_ssn 會以預先2011的強格式格式化，以格式化為九個連續數位（ddddddddd）的主旨 ssn，來尋找
- Func_randomized_formatted_ssn 會找到以短劃線或空格格式化的2011後主旨 ssn （ddd-dd-dddd 或 ddd dd dddd）
- Func_randomized_unformatted_ssn 尋找未格式化為九個連續數位的2011後主旨 ssn （ddddddddd）

### <a name="checksum"></a>校驗

否


### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
- 函數 Func_ssn 找到符合模式的內容。
- 會找到來自 Keyword_ssn 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_unformatted_ssn 找到符合模式的內容。
- 會找到來自 Keyword_ssn 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：
- 函數 Func_randomized_formatted_ssn 找到符合模式的內容。
- 會找到來自 Keyword_ssn 的關鍵字。

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是55%：
- 函數 Func_randomized_unformatted_ssn 找到符合模式的內容。
- 會找到來自 Keyword_ssn 的關鍵字。


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_ssn"></a>Keyword_ssn

- 社會保障 
- 社會保障# 
- Soc Sec 
- Ssn 
- 主旨 SSN 
- Ssn# 
- 秒# 
- Ssid 
   
## <a name="us--uk-passport-number"></a>美國/英國 護照號碼
英國 護照號碼機密資訊類型實體可用於歐盟護照號碼機密資訊類型，並可作為獨立的機密資訊類型實體使用。

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
- 函數 Func_usa_uk_passport 找到符合模式的內容。
- 會找到來自 Keyword_passport 的關鍵字。

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_passport"></a>Keyword_passport

- 護照號碼 
- 護照否 
- 護照# 
- 護照# 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番號 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport 非 
- Passeport# 
- Passeport# 
- PasseportNon 
- Passeportn ° 
