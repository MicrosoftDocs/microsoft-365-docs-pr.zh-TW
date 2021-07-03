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
hideEdit: true
feedback_system: None
recommendations: false
description: 您準備好用於 DLP 原則中的200機密資訊類型。 本文列出所有敏感資訊類型，並顯示 DLP 原則在偵測到每種類型時所尋找的功能。
ms.openlocfilehash: 614649367e72766d8df210fccbb4e3cdc9cdb4b6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287464"
---
# <a name="sensitive-information-type-entity-definitions"></a>敏感資訊類型實體定義

本文列出所有敏感資訊類型的實體定義。 每個定義都顯示 DLP 原則針對偵測每種類型所尋找的功能。 若要深入瞭解敏感資訊類型，請參閱 [敏感資訊類型](sensitive-information-type-learn-about.md)

## <a name="aba-routing-number"></a>ABA 路由號碼

### <a name="format"></a>格式

格式或未格式化的模式中的九位數

### <a name="pattern"></a>模式

- 在00-12、21-32、61-72 或80範圍內的兩位數
- 兩位數
- 選用的連字號
- 四位數
- 選用的連字號
- 一個數位


### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當接近300個字元以內時，原則就會偵測到這種敏感資訊類型：
- 函數 Func_aba_routing 找到符合模式的內容。
- 會找到來自 Keyword_ABA_Routing 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 Func_aba_routing 找到符合模式的內容。

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```


### <a name="keywords"></a>關鍵字

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba 編號
- 阿壩#
- 阿壩
- abarouting#
- abaroutingnumber
- americanbankassociationrouting#
- americanbankassociationroutingnumber
- bankrouting#
- bankroutingnumber
- 路由#
- 路由編號
- 路由編號
- 路由轉口號碼
- 路由#
- RTN


## <a name="argentina-national-identity-dni-number"></a>阿根廷國家身分識別 (DNI) 號碼

### <a name="format"></a>格式

包含或不含句點的八位數

### <a name="pattern"></a>模式

八位數：
- 兩位數
- 選用期間
- 三位數
- 選用期間
- 三位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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
- cedula
- cédula
- dni
- documento nacional de identidad
- documento número
- documento numero
- registro nacional de 拉斯維加斯角色
- rnp

## <a name="argentina-unique-tax-identification-key-cuitcuil"></a>阿根廷唯一納稅識別機碼 (CUIT/CUIL) 

### <a name="format"></a>格式

11位數的破折號

### <a name="pattern"></a>模式

11位數，具有短劃線：
- 兩位數的20，23，24，27，30，33或34
- 連字號 ( ) 
- 八位數
- 連字號 ( ) 
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 `Func_Argentina_Unique_Tax_Key` 會找到符合模式的內容。
- 找到來自的關鍵字 `Keyword_Argentina_Unique_Tax_Key` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 `Func_Argentina_Unique_Tax_Key` 會找到符合模式的內容。

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Tributaria
- CUIT
- 勞動節識別碼的唯一程式碼 
- Clave Única de Identificación Tributaria
- 獨特的勞動節識別碼
- CUIL
- 唯一稅務識別機碼
- 獨特的勞動節識別機碼
- 集約型識別碼的唯一鍵
- 唯一的工作識別碼
- 工作識別碼的唯一代碼
- 唯一的工作識別機碼
- 工作識別碼的唯一索引鍵
- 納稅識別的唯一代碼
- 納稅識別的唯一金鑰
- 唯一勞動身分識別碼
- 勞動識別碼的唯一代碼
- 唯一勞動識別機碼
- 勞動識別碼的唯一鍵
- 納稅識別碼
- taxID#
- taxId
- taxidnumber
- 納稅號碼
- 納稅否
- 稅#
- 稅#
- 納稅人識別碼
- 納稅人編號
- 納稅人編號
- 納稅人#
- 納稅人#
- 納稅身分識別
- 納稅識別
- Número de Identificación 會計
- número de contribuyente


## <a name="australia-bank-account-number"></a>澳大利亞銀行帳戶號碼

### <a name="format"></a>格式

具有或不含銀行狀態分公司號碼的六到10位數

### <a name="pattern"></a>模式

帳戶號碼是6到10位數。

澳大利亞銀行狀態分支編號：
- 三位數
- 連字號
- 三位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 Regex_australia_bank_account_number 找到符合模式的內容。
- 會找到來自 Keyword_australia_bank_account_number 的關鍵字。
- 正則運算式 Regex_australia_bank_account_number_bsb 找到符合模式的內容。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

## <a name="australia-business-number"></a>澳大利亞商務電話號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security


### <a name="format"></a>格式

11位數（選用分隔符號）

### <a name="pattern"></a>模式

11位數（選用分隔符號）：

- 兩位數
- 選用的連字號或空格
- 三位數
- 選用的連字號或空格
- 三位數
- 選用的連字號或空格
- 三位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_australian_business_number 找到符合模式的內容。
- 會找到來自 Keywords_australian_business_number 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_australian_business_number 找到符合模式的內容。

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- 澳大利亞商務版否
- 商務電話號碼
- 荷蘭#
- businessid#
- 業務識別碼
- 荷蘭
- businessno#

## <a name="australia-company-number"></a>澳大利亞公司號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

具有分隔符號的九位數

### <a name="pattern"></a>模式

九位數的分隔符號：

- 三位數
- 一個空格
- 三位數
- 一個空格
- 三位數


### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_Australian_Company_Number 找到符合模式的內容。
- 會找到來自 Keyword_Australian_Company_Number 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 Func_Australian_Company_Number 找到符合模式的內容。

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- 可以
- 澳大利亞公司 no
- 澳大利亞公司 no#
- 澳大利亞公司號碼
- 澳大利亞公司無
- 澳大利亞公司無#
- 澳大利亞公司號碼

## <a name="australia-drivers-license-number"></a>澳大利亞駕駛執照號碼

### <a name="format"></a>格式

九個字母和數位

### <a name="pattern"></a>模式

九個字母和數位：

- 兩位數的數位或字母 (不區分大小寫) 
- 兩位數
- 五個數字或字母 (不區分大小寫) 

或

- 一個至兩個選用的字母 (不區分大小寫) 
- 四到九位數

或

- 九個數字或字母 (不區分大小寫) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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
- 第十個數字 (選用) 是個別數位

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_australian_medical_account_number 找到符合模式的內容。
- 會找到來自 Keyword_Australia_Medical_Account_Number 的關鍵字。
- 校驗和通過。


```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
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

八或9個字母數位元

### <a name="pattern"></a>模式

- 一個字母 (N，E，D，F，A，C，U，X) 後接7位數或
- 兩個字母 (PA，PB，PC，PD，PE，PF，PU，PW，PX，PZ) 後接7位數。

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會 `Regex_australia_passport_number` 找到符合模式的內容。
- 找到來自的關鍵字 `Keyword_australia_passport_number` 。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 正則運算式會 `Regex_australia_passport_number` 找到符合模式的內容。

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼
- 護照詳細資料
- immigration 與公民
- 澳大利亞英聯邦
- immigration 部門
- 本國身分識別卡片
- 旅遊檔
- 頒發機構單位


## <a name="australia-tax-file-number"></a>澳大利亞稅收檔編號

### <a name="format"></a>格式

8至九位數

### <a name="pattern"></a>模式

通常會以空格呈現的八至九位數，如下所示：
- 三位數
- 選擇性的空格
- 三位數
- 選擇性的空格
- 二到三位數的最後一個數位是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_australian_tax_file_number 找到符合模式的內容。
- 找不到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 的關鍵字。
- 校驗和通過。

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- 澳大利亞商務電話號碼
- 邊際稅率
- medicare levy
- 產品群組編號
- 服務 veterans
- 預繳稅金
- 個人稅收返還
- 稅收檔案編號
- tfn

## <a name="austria-drivers-license-number"></a>奧地利駕駛執照號碼

### <a name="format"></a>格式

不含空格及分隔符號的八位數

### <a name="pattern"></a>模式

八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 正則運算式會  `Regex_austria_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_austria_eu_driver's_license_number` 。

```xml
      <!-- Austria Driver's License Number -->
      <Entity id="682f18ce-44eb-482b-8198-2bcb96a0761e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_austria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver ' s_license_number

- fuhrerschein
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>奧地利身分識別卡
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

字母、數位及特殊字元的24個字元的組合

### <a name="pattern"></a>模式

24個字元：

-  22個字母 (不區分大小寫) 、數位、反斜線、正斜線或正號）

- 兩個字母 (不區分大小寫) 、數位、反斜線、正斜線、加號或等號）

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 正則運算式會  `Regex_austria_eu_national_id_card` 找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_austria_eu_national_id_card` 。

```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
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
- personalausweis republik österreich

## <a name="austria-passport-number"></a>奧地利護照號碼

### <a name="format"></a>格式

一個字母后接一個選擇性的空格和七位數

### <a name="pattern"></a>模式

一個字母、七位數和一個空格的組合：

- 一個字母 (不區分大小寫) 
- 一個空格 (選用) 
- 七位數

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_austria_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_austria_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date1` 會發現日期格式為 DD YYYY 或關鍵字 from `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_austria_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_austria_eu_passport_number` 。

```xml
      <!-- Austria Passport Number -->
      <Entity id="1c96ae4e-303b-447d-86c7-77113ac266bf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日

## <a name="austria-social-security-number"></a>奧地利的社會安全號碼

### <a name="format"></a>格式

指定之格式的10位數

### <a name="pattern"></a>模式

10位數：

- 對應至序列值的三位數
- 一個檢查碼
- 對應至出生日期 (DDMMYY 的六位數) 

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_austria_eu_ssn_or_equivalent` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_austria_eu_ssn_or_equivalent` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_austria_eu_ssn_or_equivalent` 會找到符合模式的內容。

```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- 奧地利 ssn
- ehic 編號
- ehic 否
- 保險業代碼
- insurancecode#
- 保險號碼
- 保險否
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno#
- 社會安全性否
- 社會安全號碼
- 社會安全性碼
- sozialversicherungsnummer
- sozialversicherungsnummer#
- soziale sicherheit kein
- sozialesicherheitkein#
- Ssn#
- Ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje

## <a name="austria-tax-identification-number"></a>奧地利納稅識別號碼

### <a name="format"></a>格式

具有選擇性連字號及正斜線的九位數

### <a name="pattern"></a>模式

具有選擇性連字號及正斜線的九位數：

- 兩位數
- 連字號 (選用) 
- 三位數
- 轉寄斜線 (選用) 
- 四位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_austria_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_austria_eu_tax_file_number` 。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數  `Func_austria_eu_tax_file_number` 會找到符合模式的內容。

```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
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

## <a name="austria-value-added-tax"></a>奧地利加值稅
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

11個字元的數位元格式

### <a name="pattern"></a>模式

11個字元的字母數位模式：

- A 或 a
- T 或 t
- 選擇性空格
- U 或 u
- 選擇性空格
- 兩位數或三位數
- 選擇性空格
- 四位數
- 選擇性空格
- 一或兩位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_Austria_Value_Added_Tax 找到符合模式的內容。
- 會找到來自 Keyword_Austria_Value_Added_Tax 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_Austria_Value_Added_Tax 找到符合模式的內容。

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- 加值稅號碼
- 加值稅#
- 奧地利加值稅號碼
- 加值稅編號
- vatno#
- 增值納稅號碼
- 奧地利加值稅
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- 加值稅識別號碼
- atu 編號
- uid 編號


## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB 驗證金鑰

### <a name="format"></a>格式

字串 "DocumentDb"，後面加上下列模式中所述的字元及字串。

### <a name="pattern"></a>模式

- 字串 "DocumentDb"
- 介於3-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 大於符號 (>) 、等號 (=) 、引號 ( ") 或撇號 ( ' ) 
- 任何86小寫或大寫字母、數位、正斜線 (/) 或加號 (+) 的組合
- 兩個等號 (=) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 CEP_Regex_AzureDocumentDBAuthKey 找到符合模式的內容。
- 正則運算式 CEP_CommonExampleKeywords 找不到符合模式的內容。

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

 (技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。 ) 

- 尚未
- 送交
- 資料庫
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>azure IAAS 資料庫連接字串和 azure SQL 連接字串

### <a name="format"></a>格式

字串 "Server"、"server" 或 "data source"，後面加上模式中所述的字元及字串（包括字串 "cloudapp"）。<!--no-hyperlink-->com "或" cloudapp。<!--no-hyperlink-->net "或" database。<!--no-hyperlink-->net "，及字串" Password "或" password "或" pwd "。

### <a name="pattern"></a>模式

- 字串「伺服器」、「伺服器」或「資料來源」
- 零至兩個空白字元
- 等號 (=) 
- 零至兩個空白字元
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "cloudapp"。<!--no-hyperlink-->com "，" cloudapp。<!--no-hyperlink-->net "或" database。<!--no-hyperlink-->真實
- 介於1-300 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "Password"、"password" 或 "pwd"
- 零至兩個空白字元
- 等號 (=) 
- 零至兩個空白字元
- 一個或多個不是分號的字元 (; ) 、引號 ( ") 或單引號 ( ' ) 
- 分號 (; ) ，引號 ( ") 或單引號 ( ' ) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 CEP_Regex_AzureConnectionString 找到符合模式的內容。
- 正則運算式 CEP_CommonExampleKeywords 找不到符合模式的內容。

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

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。 ) 

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
- 零至兩個空白字元
- 等號 (=) 
- 零至兩個空白字元
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- "azure 裝置" 字串。<!--no-hyperlink-->真實
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "SharedAccessKey"
- 零至兩個空白字元
- 等號 (=) 
- 零至兩個空白字元
- 任何43小寫或大寫字母、數位、正斜線 (/) 或加號 (+) 的組合
- 等號 (=) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 CEP_Regex_AzureIoTConnectionString 找到符合模式的內容。
- 正則運算式 CEP_CommonExampleKeywords 找不到符合模式的內容。

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

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。 ) 

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
- 引號 ( ") 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 CEP_Regex_AzurePublishSettingPasswords 找到符合模式的內容。
- 正則運算式 CEP_CommonExampleKeywords 找不到符合模式的內容。


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

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。 ) 

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
- 零至兩個空白字元
- 等號 (=) 
- 零至兩個空白字元
- 43個字元的任何組合，其為小寫或大寫字母、數位、正斜線 (/) 或加號 (+) 
- 等號 (=) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 CEP_Regex_AzureRedisCacheConnectionString 找到符合模式的內容。
- 正則運算式 CEP_CommonExampleKeywords 找不到符合模式的內容。

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

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。 ) 

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
- 零至兩個空白字元
- 等號 (=) 
- 零至兩個空白字元
- 介於43-53 個字元、小寫字母、數位或百分號 (% ) 之間的任何組合
- 字串 "% 三維"
- 不是小寫或大寫字母、數位或百分號的任何字元 (% ) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
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
- 零至兩個空白字元
- 等號 (=) 
- 零至兩個空白字元
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "<!--no-hyperlink-->真實
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "SharedAccessKey"
- 零至兩個空白字元
- 等號 (=) 
- 零至兩個空白字元
- 43個字元的任何組合，其為小寫或大寫字母、數位、正斜線 (/) 或加號 (+) 
- 等號 (=) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 CEP_Regex_AzureServiceBusConnectionString 找到符合模式的內容。
- 正則運算式 CEP_CommonExampleKeywords 找不到符合模式的內容。

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

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。 ) 

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
- 零至兩個空白字元
- 等號 (=) 
- 零至兩個空白字元
- 介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "AccountKey"
- 零至兩個空白字元
- 等號 (=) 
- 零至兩個空白字元
- 86個字元的任何組合，其為小寫或大寫字母、數位、正斜線 (/) 或加號 (+) 
- 兩個等號 (=) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 CEP_Regex_AzureStorageAccountKey 找到符合模式的內容。
- 正則運算式 CEP_AzureEmulatorStorageAccountFilter 找不到符合模式的內容。
- 正則運算式 CEP_CommonExampleKeywords 找不到符合模式的內容。

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

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

 (技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。 ) 

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。 ) 

- 尚未
- 送交
- 資料庫
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-storage-account-key-generic"></a>Azure 儲存體帳戶金鑰 (泛型) 

### <a name="format"></a>格式

任何86的小寫字母或大寫字母、數位、正 )  (斜線 (+) 的任何組合，前面或後面接著所列模式中所述的字元。

### <a name="pattern"></a>模式

- 0到大於符號 (>) 、撇號 ( ' ) 、等號 (=) 、引號 ( ") 或數位簽章 ( # ) 
- 86個字元的任何組合，其小寫或大寫字母、數位、正斜線 (/) 或加號 (+) 
- 兩個等號 (=) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
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

### <a name="format"></a>格式

10位數，不含空格及分隔符號

### <a name="pattern"></a>模式

10位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_belgium_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_belgium_eu_driver's_license_number` 。

```xml
      <!-- Belgium Driver's License Number -->
      <Entity id="d89fd329-9324-433c-b687-2c37bd5166f3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_belgium_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver ' s_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füehrerscheinnummer
- fuhrerschein
- fuehrerschein
- fuhrerscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>比利時國號碼

### <a name="format"></a>格式

11位數加上選擇性分隔符號

### <a name="pattern"></a>模式

11位數加上分隔符號：
- 六位數和兩個選用句點，格式為 YY。出生日期為 MM
- 自點、破折號、空間的選擇性分隔符號
- 三個連續數位 (奇數男生，即便是女生) 
- 自點、破折號、空間的選擇性分隔符號
- 兩個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_belgium_national_number 找到符合模式的內容。
- 會找到來自 Keyword_belgium_national_number 的關鍵字。
- 校驗和通過。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 Func_belgium_national_number 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
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
- numéro d'assuré
- numéro de registre （本國）
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
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

### <a name="format"></a>格式

兩個字母后接六位數，不含空格或分隔符號

### <a name="pattern"></a>模式

兩個字母后接六位數

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

 當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_belgium_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_belgium_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date2` 會找到格式為 DD MM YY 的日期，或 `Keywords_eu_passport_date` 找到來自或的關鍵字。 `Keywords_belgium_eu_passport_number`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_belgium_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_belgium_eu_passport_number` 。

```xml
      <!-- Belgium Passport Number -->
      <Entity id="d7b1315b-21ca-4774-a32a-596010ff78fd" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
            <Match idRef="Keywords_belgium_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport 購買
- Passeport livre
- Pass-Nr
- Passnummer
- reisepass kein

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日

## <a name="belgium-value-added-tax-number"></a>比利時增值的納稅號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

12個字元的數位元格式

### <a name="pattern"></a>模式

12個字元的字母數位樣式：

- a 字母 B 或 B
- 字母 E 或 E
- 數位0
- 從1到9的數位
- 選用的點或連字號或空格
- 四位數
- 選用的點或連字號或空格
- 四位數


### <a name="checksum"></a>總和檢查碼

是


### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_belgium_value_added_tax_number 找到符合模式的內容。
- 會找到來自 Keywords_belgium_value_added_tax_number 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_belgium_value_added_tax_number 找到符合模式的內容。

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
### <a name="keywords"></a>關鍵字

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- n º tva
- 加值稅號碼
- 加值稅否
- numéro。
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- 順便 說 一 句
- 順便 說 一 句#
- 加值稅#


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

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_brazil_cpf 找到符合模式的內容。
- 會找到來自 Keyword_brazil_cpf 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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


## <a name="brazil-legal-entity-number-cnpj"></a>巴西法人編號 (CNPJ) 

### <a name="format"></a>格式

14位數包含登記編號、分支編號及檢查數位，加上分隔符號

### <a name="pattern"></a>模式

14位數，加上分隔符號：

- 兩位數
- 一個句點
- 三位數
- 一個句點
- 三位數 (這些前八位數是登記編號) 
- 一個正斜線
- 四位數的分支編號
- 連字號
- 兩位數的檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_brazil_cnpj 找到符合模式的內容。
- 會找到來自 Keyword_brazil_cnpj 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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
- Business
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


## <a name="brazil-national-identification-card-rg"></a>巴西國身分識別卡 (RG) 

### <a name="format"></a>格式

Registro Geral (舊格式) ：九位數

Registro de Identidade (RIC)  (新格式) ：11位數

### <a name="pattern"></a>模式

Registro Geral (舊格式) ：
- 兩位數
- 一個句點
- 三位數
- 一個句點
- 三位數
- 連字號
- 一種檢查碼的數位

Registro de Identidade (RIC)  (新格式) ：
- 10位數
- 連字號
- 一種檢查碼的數位

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_brazil_rg 找到符合模式的內容。
- 會找到來自 Keyword_brazil_rg 的關鍵字。
- 校驗和通過。


```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
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
- RG (此關鍵字區分大小寫) 
- RIC (此關鍵字區分大小寫) 


## <a name="bulgaria-drivers-license-number"></a>保加利亞駕駛執照號碼

### <a name="format"></a>格式

九位數，不含空格及分隔符號

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_bulgaria_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_bulgaria_eu_driver's_license_number` 。

```xml
      <!-- Bulgaria Driver's License Number -->
      <Entity id="66d39258-94c2-43b2-804b-aa312258e54b" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver ' s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>保加利亞統一的民事編號
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

10位數，不含空格及分隔符號

### <a name="pattern"></a>模式

10位數，不含空格及分隔符號

- 對應至出生日期 (YYMMDD 的六位數) 
- 對應至出生順序的兩位數
- 對應于性別的一個數位：用於男的偶數位數和用於女的奇數數位
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_bulgaria_eu_national_id_card` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_bulgaria_eu_national_id_card` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_bulgaria_eu_national_id_card` 會找到符合模式的內容。

```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- 安娜#
- 安娜
- bucn#
- bucn
- edinen grazhdanski nomer
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
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ識別碼
- униформграждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid#
- униформгражданскине.#


## <a name="bulgaria-passport-number"></a>保加利亞護照號碼

### <a name="format"></a>格式

九位數，不含空格及分隔符號

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_bulgaria_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_bulgaria_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date1` 會發現日期格式為 DD YYYY 或關鍵字 from `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_bulgaria_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_bulgaria_eu_passport_number` 。

```xml
      <!-- Bulgaria Passport Number -->
      <Entity id="f7172b82-c588-4216-845e-4e54e397f29a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт否

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日

## <a name="canada-bank-account-number"></a>加拿大銀行帳戶號碼

### <a name="format"></a>格式

7或12位數

### <a name="pattern"></a>模式

加拿大銀行帳戶號碼是7或12位數。

加拿大銀行帳戶中轉號碼為：
- 五位數
- 連字號
- 三位數或
- 零 "0"
- 八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 Regex_canada_bank_account_number 找到符合模式的內容。
- 會找到來自 Keyword_canada_bank_account_number 的關鍵字。
- 正則運算式 Regex_canada_bank_account_transit_number 找到符合模式的內容。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
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

涵蓋的各種模式：
- 阿爾比省
- 不列顛哥倫比亞省
- 馬尼托巴省
- 新不倫瑞克省
- Newfoundland/Labrador
- 新斯科舍省
- 安大略省
- 艾德華王子島
- 魁北克
- 薩斯喀徹爾省

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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


## <a name="canada-personal-health-identification-number-phin"></a>加拿大個人健康身分識別號碼 (PHIN) 

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式 Regex_canada_phin 找到符合模式的內容。
- 找到 Keyword_canada_phin 或 Keyword_canada_provinces 中至少有兩個關鍵字。

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

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_canadian_sin 找到符合模式的內容。
- 至少下列兩種模式：
    - 會找到來自 Keyword_sin 的關鍵字。
    - 會找到來自 Keyword_sin_collaborative 的關鍵字。
    - 函數 Func_eu_date 會找到正確日期格式的日期。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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
- Birthday
- 出生日期


## <a name="chile-identity-card-number"></a>智利身分識別卡號碼

### <a name="format"></a>格式

七到八位數加上分隔符號 a check digits 或字母

### <a name="pattern"></a>模式

7到8位數加上分隔符號：
- 一到兩位數
- 選用期間
- 三位數
- 選用期間
- 三位數
- 虛線
- 一個數位或字母 (不區分大小寫) （該碼是檢查碼）

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_chile_id_card 找到符合模式的內容。
- 會找到來自 Keyword_chile_id_card 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

- cédula de identidad
- identificación
- 本國身分識別
- 國家識別號碼
- 國家識別碼
- número de identificación nacional
- rol único nacional
- rol único tributario
- 運行
- 車轍
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tributario
- 運行#
- 車轍#
- nationaluniqueroleID#
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- 智利 identity no。
- 智利身分識別號碼
- 智利身分識別#
- 唯一稅務登錄
- 唯一的 Tributary 角色
- 唯一稅務角色
- 唯一的 Tributary 編號
- 唯一的國家/地區號碼
- 獨特的本國角色
- 本國獨特角色
- 智利身分識別
- 智利身分識別號碼
- 智利身分識別#


## <a name="china-resident-identity-card-prc-number"></a>中國居民身分識別卡 (中國) 號碼

### <a name="format"></a>格式

18位數

### <a name="pattern"></a>模式

18位數：
- 六位數的位址碼
- 形式為 YYYYMMDD 的八位數，也就是出生日期
- 三位數的訂單碼
- 一種檢查碼的數位

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_china_resident_id 找到符合模式的內容。
- 會找到來自 Keyword_china_resident_id 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

可以格式化或未格式化的14到16位數 (dddddddddddddddd) ，且必須透過 Luhn 測試。

### <a name="pattern"></a>模式

偵測來自全球所有主要品牌的卡片，包括簽證、MasterCard、探索卡、JCB、美洲 Express、禮品卡和 diner 卡。

### <a name="checksum"></a>總和檢查碼

是，Luhn 檢查碼

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_credit_card 找到符合模式的內容。
- 下列其中一項為真：
    - 會找到來自 Keyword_cc_verification 的關鍵字。
    - 會找到來自 Keyword_cc_name 的關鍵字。
    - 函數 Func_expiration_date 會找到正確日期格式的日期。
- 校驗和通過。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
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
- Cod。 seguranca
- Cod。 segurança
- cód. seguranca
- cód segurança
- 貨至 seguranca
- 貨至 segurança
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
- 交易
- 交易編號
- 參考編號
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番號

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- 美洲 express
- americanexpress
- americano espresso
- 簽證
- 萬事 達
- 主卡
- Mc
- mastercards
- 主卡
- diner 俱樂部
- diners 俱樂部
- dinersclub
- 發現
- 探索卡片
- discovercard
- 探索卡片
- JCB
- BrandSmart
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
- Cardmember 帳戶
- cardmember 帳戶
- Cardno
- 公司卡片
- 公司卡片
- 卡片類型
- 信用卡帳戶號碼
- 卡片成員帳戶
- Cardmember 帳戶。
- 卡片編號
- 無卡
- 卡號碼
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
- \r\n. 憲章
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
- クレジットカード番號
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番號
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visaカード
- 簽證カード
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード


## <a name="croatia-drivers-license-number"></a>克羅地亞駕駛執照號碼

### <a name="format"></a>格式

不含空格及分隔符號的八位數

### <a name="pattern"></a>模式

八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 正則運算式會  `Regex_croatia_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_croatia_eu_driver's_license_number` 。

```xml
      <!-- Croatia Driver's License Number -->
      <Entity id="005b3ef1-47dd-4e68-bb02-c6db484d00f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_croatia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver ' s_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>克羅地亞身分識別卡號碼
此實體包含在歐盟國身分識別號碼的敏感資訊類型中。 它可以做為獨立的機密資訊類型實體。

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數位

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

- majstorski broj građana
- 主機公民號碼
- nacionalni identifikacijski broj
- 國家識別號碼
- oib#
- oib
- osobna iskaznica
- osobni 識別碼
- osobni identifikacijski broj
- 個人身分識別號碼
- porezni broj
- porezni identifikacijski broj
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

### <a name="format"></a>格式

九位數，不含空格及分隔符號

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_croatia_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_croatia_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date1` 會發現日期格式為 DD YYYY 或關鍵字 from `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_croatia_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_croatia_eu_passport_number` 。

```xml
      <!-- Croatia Passport Number -->
      <Entity id="7d7a729d-32d8-4204-8d01-d5e6a6c25581" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- Br。 Putovnice
- br putovnice

## <a name="croatia-personal-identification-oib-number"></a>克羅地亞個人身分識別 (OIB) 號碼

### <a name="format"></a>格式

11位數

### <a name="pattern"></a>模式

11位數：
- 10位數
- 最後一個數位是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_croatia_oib_number 找到符合模式的內容。
- 會找到來自 Keywords_croatia_eu_tax_file_number 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_croatia_oib_number 找到符合模式的內容。
- 校驗和通過。

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj građana
- 主機公民號碼
- nacionalni identifikacijski broj
- 國家識別號碼
- oib#
- oib
- osobna iskaznica
- osobni 識別碼
- osobni identifikacijski broj
- 個人身分識別號碼
- porezni broj
- porezni identifikacijski broj
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

### <a name="format"></a>格式

12位數，不含空格及分隔符號

### <a name="pattern"></a>模式

12位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_cyprus_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_cyprus_eu_driver's_license_number` 。

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver ' s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>賽普勒斯身分識別卡片
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

10位數，不含空格及分隔符號

### <a name="pattern"></a>模式

10位數

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_cyprus_eu_national_id_card` 找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_cyprus_eu_national_id_card` 。

```xml
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
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
- kimlik karti
- 國家識別號碼
- 個人號碼
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>賽普勒斯護照號碼

### <a name="format"></a>格式

一個字母后接6-8 位數，沒有空格或分隔符號

### <a name="pattern"></a>模式

一個字母后接六個到八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_cyprus_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_cyprus_eu_passport_number` 。
- 正則運算式 `Regex_cyprus_eu_passport_date` 會找到日期格式為 DD/MM/YYYY 或找到關鍵字 from `Keywords_cyprus_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_cyprus_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_cyprus_eu_passport_number` 。

```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο#
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport numarası
- Pasaport 編號
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- 到期日
- 發行日期


## <a name="cyprus-tax-identification-number"></a>賽普勒斯納稅識別號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

指定的模式中的八位數和一個字母

### <a name="pattern"></a>模式

八位數和一個字母：

- "0" 或 "9"
- 七位數
- 一個字母 (不區分大小寫) 

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_cyprus_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_cyprus_eu_tax_file_number` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_cyprus_eu_tax_file_number` 會找到符合模式的內容。

```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
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
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>捷克文駕駛執照號碼

### <a name="format"></a>格式

兩個字母后接六位數

### <a name="pattern"></a>模式

8個字母和數位：

- 字母 ' E ' (不區分大小寫) 
- 一個字母
- 空格 (選用) 
- 六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_czech_republic_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_czech_republic_eu_driver's_license_number` 。

```xml
      <Entity id="86b40d3b-d8ea-4c36-aab0-ef9416a6769c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver ' s_license_number

- řidičský prúkaz
- řidičské průkazy
- číslo řidičského průkazu
- čísla řidičských průkazů


## <a name="czech-passport-number"></a>捷克護照號碼

### <a name="format"></a>格式

不含空格或分隔符號的八位數

### <a name="pattern"></a>模式

不含空格或分隔符號的八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_czech_republic_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_czech_republic_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date1` 會發現日期格式為 DD YYYY 或關鍵字 from `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_czech_republic_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_czech_republic_eu_passport_number` 。

```xml
      <!-- Czech Republic Passport Number -->
      <Entity id="7bcd8ce8-5e92-4bbe-bc92-fa669f0369fa" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- číslo pasu
- cestovní pasu
- passeport 否
- čísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="czech-personal-identity-number"></a>捷克個人身分識別號碼

### <a name="format"></a>格式

具有選用正斜線的九位數 (舊格式) 10 位數，選用正斜線 (新的格式) 

### <a name="pattern"></a>模式

 (舊格式的九位數) ：
- 六位數代表出生日期
- 選用的正斜線
- 三位數

10位數 (新的格式) ：
- 六位數代表出生日期
- 選用的正斜線
- 最後一個數位是檢查碼的四位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：

- 函數 Func_czech_id_card 找到符合模式的內容。
- 會找到來自 Keyword_czech_id_card 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 函數 Func_czech_id_card_new_format 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- 出生號碼
- 捷克共和國識別碼
- czechidno#
- daňové číslo
- identifikační číslo
- identity no
- 身分識別號碼
- identityno#
- identityno
- 保險號碼
- 國家識別號碼
- nationalnumber#
- 國家/地區號碼
- osobní číslo
- personalidnumber#
- 個人號碼
- 個人身分識別號碼
- 個人號碼
- Pid#
- PID
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- Ssn
- Ssn#
- 社會安全號碼
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


## <a name="denmark-drivers-license-number"></a>丹麥駕照編號

### <a name="format"></a>格式

不含空格及分隔符號的八位數

### <a name="pattern"></a>模式

八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_denmark_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_denmark_eu_driver's_license_number` 。

```xml
      <!-- Denmark Driver's License Number -->
      <Entity id="98a95812-6203-451a-a220-d39870ebef0e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_denmark_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver ' s_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>丹麥護照號碼

### <a name="format"></a>格式

九位數，不含空格及分隔符號

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_denmark_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_denmark_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date2` 找到的日期格式為 DD MM YY 或關鍵字 from。 `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_denmark_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_denmark_eu_passport_number` 。

```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n °
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="denmark-personal-identification-number"></a>丹麥個人身分識別號碼

### <a name="format"></a>格式

10位數包含連字號

### <a name="pattern"></a>模式

10位數：
- DDMMYY 格式的六位數（出生日期）
- 連字號
- 四位數的最後一個數位是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式 Func_denmark_eu_tax_file_number 找到符合模式的內容。
- 會找到來自 Keyword_denmark_id 的關鍵字。
- 校驗和通過。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 正則運算式 Func_denmark_eu_tax_file_number 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Denmark Personal Identification Number -->
    <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- Cpr
- Cpr#
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- 健康情況卡片
- 健康情況保險卡號碼
- 健康情況保險號碼
- 識別號碼
- identifikationsnummer
- identifikationsnummer#
- 身分識別號碼
- krankenkassennummer
- nationalid#
- nationalnumber#
- 國家/地區號碼
- personalidnumber#
- personalidentityno#
- 個人號碼
- personnummer
- personnummer#
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- Ssn
- Ssn#
- skat 識別碼
- skat kode
- skat nummer
- skattenummer
- 社會安全號碼
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
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer


## <a name="drug-enforcement-agency-dea-number"></a>藥物執行代理商 (DEA) 號碼

### <a name="format"></a>格式

兩個字母后接7位數

### <a name="pattern"></a>模式

模式必須包含下列各項：
- 一個字母 (不區分大小寫) 這組可能的字母： abcdefghjklmnprstux，也就是註冊碼程式碼
- 一個字母 (不區分大小寫) ，也就是報名者姓氏或數位 ' 9 ' 的第一個字母。
- 七位數，最後一個是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_dea_number 找到符合模式的內容。
- 找到來自的關鍵字 `Keyword_dea_number`
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_dea_number 找到符合模式的內容。
- 校驗和通過。

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_dea_number"></a>Keyword_dea_number

- Dea
- Dea#
- 藥物強制管理
- 藥品強制代理人


## <a name="estonia-drivers-license-number"></a>愛沙尼亞駕照編號

### <a name="format"></a>格式

兩個字母后接六位數

### <a name="pattern"></a>模式

兩個字母和六位數：

- 字母 "ET" (不區分大小寫) 
- 六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_estonia_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_estonia_eu_driver's_license_number` 。

```xml
      <!-- Estonia Driver's License Number -->
      <Entity id="51da8171-da70-4cc1-9d65-055a59ca4f83" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_estonia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver ' s_license_number

--permis de conduire
- juhilubade numbrid
- juhiloa 編號
- juhiluba


## <a name="estonia-personal-identification-code"></a>愛沙尼亞個人識別碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

11位數，不含空格及分隔符號

### <a name="pattern"></a>模式

11位數：

- 對應到性別和世紀的一位數 (奇數號碼，甚至號碼女;1-2：19世紀;3-4：20世紀;5-6：21世紀) 
- 對應至出生日期 (YYMMDD 的六位數) 
- 三位數，對應至在相同日期出生的人員的序號
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_estonia_eu_national_id_card` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_estonia_eu_national_id_card` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_estonia_eu_national_id_card` 會找到符合模式的內容。

```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
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
- maksukohustuslase identifitseerimisnumber
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

### <a name="format"></a>格式

一個字母后接7位數，不含空格或分隔符號

### <a name="pattern"></a>模式

一個字母后接7位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_estonia_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_estonia_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date1` 會發現日期格式為 DD YYYY 或關鍵字 from `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_estonia_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_estonia_eu_passport_number` 。

```xml
      <!-- Estonia Passport Number -->
      <Entity id="61f7073a-509e-425b-a754-bc01bb5d5b8c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku pass passi number passinumbrid 檔編號檔無 dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="eu-debit-card-number"></a>歐盟轉帳卡號碼

### <a name="format"></a>格式

16位數

### <a name="pattern"></a>模式

複雜且可靠的模式

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
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

這些實體是在歐盟駕駛執照號碼中，也是敏感資訊類型。

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

這些實體屬於歐盟國內身分識別號碼，且是敏感資訊類型。

- [奧地利](#austria-identity-card)
- [比利時](#belgium-national-number)
- [保加利亞](#bulgaria-uniform-civil-number)
- [克羅埃西亞](#croatia-identity-card-number)
- [賽普勒斯](#cyprus-identity-card)
- [捷克文](#czech-personal-identity-number)
- [丹麥](#denmark-personal-identification-number)
- [愛沙尼亞](#estonia-personal-identification-code)
- [芬蘭](#finland-national-id)
- [法國](#france-national-id-card-cni)
- [德國](#germany-identity-card-number)
- [希臘](#greece-national-id-card)
- [匈牙利](#hungary-personal-identification-number)
- [愛爾蘭](#ireland-personal-public-service-pps-number)
- [義大利](#italy-fiscal-code)
- [拉脫維亞](#latvia-personal-code)
- [立陶宛](#lithuania-personal-code)
- [盧森堡](#luxemburg-national-identification-number-natural-persons)
- [馬爾他](#malta-identity-card-number)
- [荷蘭](#netherlands-citizens-service-bsn-number)
- [波蘭](#poland-national-id-pesel)
- [葡萄牙](#portugal-citizen-card-number)
- [羅馬尼亞](#romania-personal-numeric-code-cnp)
- [斯洛伐克](#slovakia-personal-number)
- [斯洛維尼亞](#slovenia-unique-master-citizen-number)
- [西班牙](#spain-dni)
- [英國。](#uk-national-insurance-number-nino)


## <a name="eu-passport-number"></a>歐盟護照號碼

這些實體位於歐盟護照號碼中，且為敏感資訊類型。 這些實體位於歐盟護照號碼捆綁中。

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

這些位於歐盟社會保險號碼或對等身分識別中的實體為敏感資訊類型。

- [奧地利](#austria-social-security-number)
- [比利時](#belgium-national-number)
- [克羅埃西亞](#croatia-personal-identification-oib-number)
- [捷克文](#czech-personal-identity-number)
- [丹麥](#denmark-personal-identification-number)
- [芬蘭](#finland-national-id)
- [法國](#france-social-security-number-insee)
- [德國](#germany-identity-card-number)
- [希臘](#greece-national-id-card)
- [匈牙利](#hungary-social-security-number-taj)
- [葡萄牙](#portugal-citizen-card-number)
- [西班牙](#spain-social-security-number-ssn)
- [瑞典](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>歐盟納稅識別號碼

這些實體屬於歐盟納稅身分識別號碼的敏感資訊類型。

- [奧地利](#austria-tax-identification-number)
- [比利時](#belgium-national-number)
- [保加利亞](#bulgaria-uniform-civil-number)
- [克羅埃西亞](#croatia-identity-card-number)
- [賽普勒斯](#cyprus-tax-identification-number)
- [捷克文](#czech-personal-identity-number)
- [丹麥](#denmark-personal-identification-number)
- [愛沙尼亞](#estonia-personal-identification-code)
- [芬蘭](#finland-national-id)
- [法國](#france-tax-identification-number)
- [德國](#germany-tax-identification-number)
- [希臘](#greece-tax-identification-number)
- [匈牙利](#hungary-tax-identification-number)
- [愛爾蘭](#ireland-personal-public-service-pps-number)
- [義大利](#italy-fiscal-code)
- [拉脫維亞](#latvia-personal-code)
- [立陶宛](#lithuania-personal-code)
- [盧森堡](#luxemburg-national-identification-number-non-natural-persons)
- [馬爾他](#malta-tax-identification-number)
- [荷蘭](#netherlands-tax-identification-number)
- [波蘭](#poland-tax-identification-number)
- [葡萄牙](#portugal-tax-identification-number)
- [羅馬尼亞](#romania-personal-numeric-code-cnp)
- [斯洛伐克](#slovakia-personal-number)
- [斯洛維尼亞](#slovenia-tax-identification-number)
- [西班牙](#spain-tax-identification-number)
- [瑞典](#sweden-tax-identification-number)
- [英國。](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>芬蘭駕照編號

### <a name="format"></a>格式

10位數包含連字號

### <a name="pattern"></a>模式

10位數包含連字號：

- 六位數
- 連字號
- 三位數
- 一個數位或字母

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_finland_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_finland_eu_driver's_license_number` 。

```xml
      <!-- Finland Driver's License Number -->
      <Entity id="bb3b27a3-79bd-4ac4-81a7-f9fca3c7d1a7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_finland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver ' s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja 許可證。
- körkort
- körkortnummer
- förare 許可證。
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>芬蘭歐洲健康情況保險業號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

20位數數位

### <a name="pattern"></a>模式

20位數數位：

- 10位數-8024680246
- 選擇性空格或連字號
- 10位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- Regex Regex_Finland_European_Health_Insurance_Number 找到符合模式的內容。
- 會找到來自 Keyword_Finland_European_Health_Insurance_Number 的關鍵字。

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic#
- ehic
- finlandehicnumber#
- finska sjukförsäkringskort
- 健康情況卡片
- 健康情況保險卡
- 健康情況保險號碼
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>芬蘭國 ID

### <a name="format"></a>格式

六位數加上一個表示世紀的字元加上三個數字加上檢查碼

### <a name="pattern"></a>模式

模式必須包含下列各項：
- DDMMYY 格式的六位數，也就是出生日期
- 世紀標記 ('-'、' + ' 或 ' a ' ) 
- 三位數的個人身分識別號碼
- 不區分大小寫) （即檢查碼）的數位或字母 (

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_finnish_national_id 找到符合模式的內容
- 找到來自 Keyword_finnish_national_id 的關鍵字
- checksum 會通過

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_finnish_national_id 找到符合模式的內容
- checksum 會通過

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero#
- henkilötunnusnumero
- hetu
- 識別碼 no
- 識別碼號碼
- 識別號碼
- identiteetti numero
- 身分識別號碼
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
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
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>芬蘭護照號碼

這個實體可以在歐盟護照號碼機密資訊類型中使用，並可做為獨立的機密資訊類型實體。

### <a name="format"></a>格式
九個字母和數位的組合

### <a name="pattern"></a>模式
九個字母和數位的組合：
- 兩個字母 (不區分大小寫) 
- 七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會 `Regex_finland_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keyword_finland_passport_number` 。
- 正則運算式 `Regex_eu_passport_date1` 會發現日期格式為 DD YYYY 或關鍵字 from `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會 `Regex_finland_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keyword_finland_passport_number` 。

```xml
      <!-- Finland Passport Number -->
      <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- passin numero.#
- passin numero#
- passin numero.
- passi#
- passi 編號

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日

## <a name="france-drivers-license-number"></a>法國駕駛執照號碼

您可以在歐盟駕駛執照號碼的敏感資訊類型中使用此實體，也可以作為獨立的機密資訊類型實體使用。

### <a name="format"></a>格式

12位數

### <a name="pattern"></a>模式

12位數與折扣類似的模式，例如法國電話號碼

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_french_drivers_license 找到符合模式的內容。
- 會找到來自 Keyword_french_drivers_license 的關鍵字。

```xml
    <!-- France Driver's License Number -->
    <Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Match idRef="Keyword_french_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號
- permis de conduire
- 許可號碼
- 授權號碼
- 許可證號碼
- 授權號碼
- numéros 解除許可證


## <a name="france-health-insurance-number"></a>法國健康保險業號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

21位數的數位

### <a name="pattern"></a>模式

21位數編號：

- 10位數
- 選擇性的空格
- 10位數
- 選擇性的空格
- 一個數位


### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- RegEx Regex_France_Health_Insurance_Number 找到符合模式的內容。
- 會找到來自 Keyword_France_Health_Insurance_Number 的關鍵字。

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- 保險卡
- 購買 vitale
- d'assuré社交


## <a name="france-national-id-card-cni"></a>法國全國身分識別卡 (CNI) 

### <a name="format"></a>格式

12位數

### <a name="pattern"></a>模式

12位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 正則運算式 Regex_france_cni 找到符合模式的內容。
- 會找到來自 Keywords_france_eu_national_id_card 的關鍵字。

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- 卡號碼
- 購買 nationale d'identité
- nationale d'idenite 否
- Cni#
- Cni
- compte bancaire
- 國家識別號碼
- 本國身分識別
- nationalidno#
- numéro d'assurance maladie
- numéro 購買 vitale


## <a name="france-passport-number"></a>法國護照號碼
您可以在歐盟護照號碼機密資訊類型中使用此實體。 它也可以當成獨立的機密資訊類型實體。

### <a name="format"></a>格式

九個數字和字母

### <a name="pattern"></a>模式

九個數字和字母：
- 兩位數
- 兩個字母 (不區分大小寫) 
- 五位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 `Func_fr_passport` 會找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_france_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date3` 會找到日期格式為 DD MM YYYY 或關鍵字 from。 `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 `Func_fr_passport` 會找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_france_eu_passport_number` 。


```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passeport
- passeport n °
- passeport 非
- passeport#
- passeport#
- passeportnon
- passeportn °
- passeport français
- passeport livre
- passeport 購買
- numéro passeport
- passeport n °
- n ° du passeport
- n ° passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="france-social-security-number-insee"></a>INSEE)  (的法國社會安全號碼

### <a name="format"></a>格式

15位數

### <a name="pattern"></a>模式

必須符合下列其中一種模式：
- 13位數後接一個空格後接兩位數<br/>
或
- 15個連續數位

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 `Func_french_insee` 會找到符合模式的內容。
- 會找到來自 Keyword_fr_insee 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。
- 校驗和通過。

```xml
    <!-- France INSEE -->
    <Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Keyword_fr_insee" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- 程式碼 sécu
- d'identité nationale
- insee
- fssn#
- le numéro d'identification nationale
- le 程式碼 de la sécurité sociale
- 國家識別碼
- 本國身分識別
- 無 d'identité
- 不。 d'identité
- numéro d'assurance
- numéro d'identité
- numero d'identite
- numéro de sécu
- numéro de sécurité sociale
- 無 d'identite
- 不。 d'identite
- Ssn
- Ssn#
- sécurité sociale
- securité sociale
- securite sociale
- socialsecuritynumber
- 社會安全號碼
- 社會安全性碼
- 社交保險號碼


## <a name="france-tax-identification-number"></a>法國納稅識別號碼

### <a name="format"></a>格式

13位數

### <a name="pattern"></a>模式

13位數

- 一個位數必須是0、1、2或3
- 一個數位
- 空格 (選用) 
- 兩位數
- 空格 (選用) 
- 三位數
- 空格 (選用) 
- 三位數
- 空格 (選用) 
- 三個檢查碼


### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_france_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_france_eu_tax_file_number` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_france_eu_tax_file_number` 會找到符合模式的內容。

```xml
      <!-- France Tax Identification Number (numéro SPI.) -->
      <Entity id="ed59e77e-171d-442c-9ec1-88e2ebcb5b0a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_france_eu_telephone_number" />
            <Match idRef="Keywords_france_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'identification fiscale
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


## <a name="france-value-added-tax-number"></a>法國加值稅收號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

13個字元的字母數位模式

### <a name="pattern"></a>模式

13個字元的字母數位模式：

- 兩個字母-FR (不區分大小寫) 
- 選擇性空格或連字號
- 兩個字母或數位
- 選用的空格、點、連字號或逗號
- 三位數
- 選用的空格、點、連字號或逗號
- 三位數
- 選用的空格、點、連字號或逗號
- 三位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_france_value_added_tax_number 找到符合模式的內容。
- 會找到來自 Keywords_france_value_added_tax_number 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_france_value_added_tax_number 找到符合模式的內容。

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- 加值稅號碼
- 加值稅否
- 加值稅#
- 加值稅
- siren 識別碼 no numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n ° tva
- numéro de tva
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>德國駕駛執照號碼

這種敏感資訊類型實體包含在歐盟駕駛執照號碼的敏感資訊類型中。 它也可以當成獨立的機密資訊類型實體。

### <a name="format"></a>格式

11位數和字母的組合

### <a name="pattern"></a>模式

11個數字和字母 (不區分大小寫) ：
- 一個數位或字母
- 兩位數
- 六個數字或字母
- 一個數位
- 一個數位或字母

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_german_drivers_license 找到符合模式的內容。
- 會找到來自 Keyword_german_drivers_license_number 的關鍵字。
- 校驗和通過。

```xml
    <!-- German Driver's License Number -->
    <Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Match idRef="Keyword_german_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
- führerschein
- fuhrerschein
- fuehrerschein
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein- 
- fuhrerschein- 
- fuehrerschein- 
- führerscheinnummernr
- fuhrerscheinnummernr
- fuehrerscheinnummernr
- führerscheinnummerklasse
- fuhrerscheinnummerklasse
- fuehrerscheinnummerklasse
- nr-führerschein
- nr-fuhrerschein
- nr-fuehrerschein
- 非 führerschein
- 非 fuhrerschein
- 非 fuehrerschein
- n-führerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dlno


## <a name="germany-identity-card-number"></a>德國身分識別卡號碼

### <a name="format"></a>格式

自11月2010：9個字母和數位

從1年4月1987至31年10月2010：10位數

### <a name="pattern"></a>模式

自11月1日2010：
- 一個字母 (不區分大小寫) 
- 八位數

從1年4月1987至31年10月2010：
- 10位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
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
- persönliche identifikationsnummer
- persönliche-識別碼-nummer


## <a name="germany-passport-number"></a>德國護照號碼

此實體包含在歐盟護照號碼機密資訊類型中，並可做為獨立機密資訊類型實體。

### <a name="format"></a>格式

10位數或字母

### <a name="pattern"></a>模式

模式必須包含下列各項：
- 第一個字元是此集合中的數位或字母。 (C、F、G、H、J、K) 
- 三位數
- 此集合中有五個數字或字母 (C、-H、J-N、P、R、T、V-Z) 
- 一個數位

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_german_passport 找到符合模式的內容。
- `Keyword_german_passport`找到或的關鍵字 `Keywords_eu_passport_number_common` 。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_german_passport_data 找到符合模式的內容。
- `Keyword_german_passport`找到或的關鍵字 `Keywords_eu_passport_number_common` 。
- 校驗和通過。

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe
- passeport 編號
- passeport 否

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼


## <a name="germany-tax-identification-number"></a>德國納稅識別號碼

### <a name="format"></a>格式

11位數，不含空格及分隔符號

### <a name="pattern"></a>模式

11位數

- 兩位數
- 選擇性的空格
- 三位數
- 選擇性的空格
- 三位數
- 選擇性的空格
- 兩位數
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_germany_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_germany_eu_tax_file_number` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_germany_eu_tax_file_number` 會找到符合模式的內容。

```xml
      <!-- Germany Tax Identification Number -->
      <Entity id="43316a89-9880-40cf-b980-04bc7eefcec5" patternsProximity="300" recommendedConfidence="85">
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


## <a name="germany-value-added-tax-number"></a>德國加值稅號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

11個字元的字母數位模式

### <a name="pattern"></a>模式

11個字元的字母數位模式：

- 字母 D 或 D
- 字母 E 或 E
- 選擇性的空格
- 三位數
- 選擇性空格或逗號
- 三位數
- 選擇性空格或逗號
- 三位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_germany_value_added_tax_number 找到符合模式的內容。
- 會找到來自 Keywords_germany_value_added_tax_number 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_germany_value_added_tax_number 找到符合模式的內容。

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- 加值稅號碼
- 加值稅否
- 加值稅#
- 加值稅 # mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>希臘駕駛執照號碼

此實體包含在歐盟駕駛執照號碼的敏感資訊類型中。 它也可以當成獨立的機密資訊類型實體。

### <a name="format"></a>格式

九位數，不含空格及分隔符號

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_greece_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_greece_eu_driver's_license_number` 。

```xml
      <!-- Greece Driver's License Number -->
      <Entity id="7a2200b5-aacf-4e3c-ab36-136d3e68b7da" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_greece_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver ' s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>希臘國身分識別卡

### <a name="format"></a>格式

7-8 字母和數位的組合，加上破折號

### <a name="pattern"></a>模式

 (舊格式) 有七個字母和數位：
-  (希臘字母的任何字母的一個字母) 
- 虛線
- 六位數

 (新格式) 為八個字母和數位：
- 兩個字母大寫字元會同時出現于希臘字母和拉丁字母表中 (ABEZHIKMNOPTYX) 
- 虛線
- 六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 Regex_greece_id_card 找到符合模式的內容。
- 會找到來自 Keyword_greece_id_card 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 正則運算式 Regex_greece_id_card 找到符合模式的內容。

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
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

### <a name="format"></a>格式

兩個字母后接7位數，不含空格或分隔符號

### <a name="pattern"></a>模式

兩個字母后接7位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_greece_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_greece_eu_passport_number` 。
- 正則運算式 `Regex_greece_eu_passport_date` 會以 DD MMM YY 的格式來找到日期 (範例-28 月19日) 或 `Keywords_greece_eu_passport_date` 找到關鍵字 from

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_greece_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_greece_eu_passport_number` 。

```xml
      <!-- Greece Passport Number -->
      <Entity id="7e65eb47-cdf9-4f52-8f90-2a27d5ee67e3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_greece_eu_passport_date" />
            <Match idRef="Keywords_greece_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a> (AMKA) 的希臘社會安全號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

11位數，不含空格及分隔符號

### <a name="pattern"></a>模式

- 六位數的出生日期 YYMMDD
- 四位數
- 檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_greece_eu_ssn` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_greece_eu_ssn_or_equivalent` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_greece_eu_ssn` 會找到符合模式的內容。

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- Ssn
- Ssn#
- 社會安全性否
- socialsecurityno#
- 社會安全號碼
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>希臘納稅識別號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

九位數，不含空格及分隔符號

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 正則運算式會  `Regex_greece_eu_tax_file_number` 找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_greece_eu_tax_file_number` 。

```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
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
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>香港身分識別卡 (HKID) 號碼

### <a name="format"></a>格式

8-9 字母和數位的組合，以及最後一個字元兩邊的 optional 括弧

### <a name="pattern"></a>模式

8-9 個字母的組合：
- 1-2 字母 (不區分大小寫) 
- 六位數
- 最後一個字元 (任何數位或字母 A) ，也就是檢查碼，也可以以括弧括住。

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_hong_kong_id_card 找到符合模式的內容。
- 會找到來自 Keyword_hong_kong_id_card 的關鍵字。
- 校驗和通過。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
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

### <a name="format"></a>格式

兩個字母后接六位數

### <a name="pattern"></a>模式

兩個字母和六位數：

- 兩個字母 (不區分大小寫) 
- 六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 正則運算式會  `Regex_hungary_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_hungary_eu_driver's_license_number` 。

```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver ' s_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>匈牙利個人身分識別號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

11位數

### <a name="pattern"></a>模式

11位數：

- 一個數位，對應至性別，1代表雌雄，2代表女。 其他數位也可能是公民1900之前出生的公民，具有雙公民的公民。
- 對應至出生日期 (YYMMDD 的六位數) 
- 對應至序列值的三位數
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：

- 函數  `Func_hungary_eu_national_id_card` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_hungary_eu_national_id_card` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 函數  `Func_hungary_eu_national_id_card` 會找到符合模式的內容。

```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- 識別碼號碼
- 識別號碼
- sz ig
- 深圳。 ig.
- ig。
- személyazonosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>匈牙利護照號碼

### <a name="format"></a>格式

兩個字母后接六個或7位數，不含空格或分隔符號

### <a name="pattern"></a>模式

兩個字母后接六位數或七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_hungary_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_hungary_eu_passport_number` 。
- 正則運算式 `Regex_hungary_eu_passport_date` 會找到以 DD MMM/MMM YY 格式的日期 (範例-01 MÁR/MAR 12) 或找到關鍵字 `Keywords_eu_passport_date` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_hungary_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_hungary_eu_passport_number` 。

```xml
      <!-- Hungary Passport Number -->
      <Entity id="5b483910-9aa7-4c99-9917-f4001464bda7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_hungary_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="hungary-social-security-number-taj"></a>匈牙利社會安全號碼 (TAJ) 

### <a name="format"></a>格式

九位數，不含空格及分隔符號

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：

- 函數  `Func_hungary_eu_ssn_or_equivalent` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_hungary_eu_ssn_or_equivalent` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 函數  `Func_hungary_eu_ssn_or_equivalent` 會找到符合模式的內容。

```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
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
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

10位數，不含空格或分隔符號

### <a name="pattern"></a>模式

10位數：

- 一個位數，必須是 "8"
- 8 位數
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：

- 函數  `Func_hungary_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_hungary_eu_tax_file_number` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 函數  `Func_hungary_eu_tax_file_number` 會找到符合模式的內容。

```xml
      <!-- Hungary Tax Identification Number -->
      <Entity id="ede42eb4-59d9-49eb-9603-d7853fbda91d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
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


## <a name="hungary-value-added-tax-number"></a>匈牙利增值的納稅號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

10個字元的字母數位模式

### <a name="pattern"></a>模式

10個字元的字母數位模式：

- 兩個字母-HU 或 hu
- 選擇性空格
- 八位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：

- 函數 Func_hungarian_value_added_tax_number 找到符合模式的內容。
- 會找到來自 Keywords_hungarian_value_added_tax_number 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 函數 Func_hungarian_value_added_tax_number 找到符合模式的內容。

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- 加值稅
- 增值納稅號碼
- 加值稅#
- vatno#
- hungarianvatno#
- 納稅編號
- 加值稅收áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a> (平移) 的印度永久帳戶號碼

### <a name="format"></a>格式

10個字母或數位

### <a name="pattern"></a>模式

10個字母或數位：
- 不區分大小寫的 (三個字母) 
- C、P、H、F、A、T、B、L、J、G (不區分大小寫的字母) 
- 一個字母
- 四位數
- 字母檢查碼字母

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 Regex_india_permanent_account_number 找到符合模式的內容。
- 會找到來自 Keyword_india_permanent_account_number 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 正則運算式 Regex_india_permanent_account_number 找到符合模式的內容。


```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- 永久帳戶號碼
- 泛

## <a name="india-unique-identification-aadhaar-number"></a>印度唯一識別碼 (Aadhaar) 號碼

### <a name="format"></a>格式

12位數包含選擇性空格或短杠

### <a name="pattern"></a>模式

12位數：
- 不是0或1的數位
- 三位數
- 選擇性的空格或破折號
- 四位數
- 選擇性的空格或破折號
- 最後一個數位，也就是檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_india_aadhaar 找到符合模式的內容。
- 會找到來自 Keyword_india_aadhar 的關鍵字。
- 校驗和通過。
-
當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 函數 Func_india_aadhaar 找到符合模式的內容。
- 校驗和通過。

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
- aadhaar
- aadhar
- aadhar#
- Uid
- आधार
- uidai

## <a name="indonesia-identity-card-ktp-number"></a>印尼身分識別卡 (KTP) 號碼

### <a name="format"></a>格式

包含選用句點的16位數

### <a name="pattern"></a>模式

16位數：
- 兩位數的省碼
- 期間 (選用) 
- 兩位數攝政或城市碼
- 兩位數的 subdistrict 程式碼
- 期間 (選用) 
- DDMMYY 格式的六位數（出生日期）
- 期間 (選用) 
- 四位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：

- 正則運算式 Regex_indonesia_id_card 找到符合模式的內容。
- 會找到來自 Keyword_indonesia_id_card 的關鍵字。

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- Ktp
- Kartu Tanda Penduduk
- Nomor Induk Kependudukan

## <a name="international-banking-account-number-iban"></a> (IBAN) 的國際銀行帳戶號碼

### <a name="format"></a>格式

國家/地區碼 (兩個字母) 加上檢查位數 (兩位數) 加上 bban 號 (最多30個字元) 

### <a name="pattern"></a>模式

模式必須包含下列各項：

- 兩個字母的國家/地區碼
- 兩個檢查碼位數 (後接一個選擇性的空格) 
- 1-7 四個字母或數位的群組可以以空格分隔 () 
- 1-3 個字母或數位

每個國家/地區的格式稍有不同。 IBAN 敏感資訊類型涵蓋下列60個國家/地區：

- AD
- Ae
- 鋁
- 在
- Az
- 八
- 將要
- Bg
- Bh
- ch
- 鉻
- cy
- Cz
- 德
- Dk
- 完成
- Ee
- e
- wi-fi
- 佛
- fr
- G b
- 通用 電氣
- Gi
- Gl
- Gr
- hr
- 胡
- 即
- I l
- 是
- 會
- 千瓦
- kz
- 磅
- 李
- 淺色
- 路
- 低壓
- Mc
- md
- 我
- Mk
- 先生
- mt.exe
- 木
- 吧
- 否
- Pl
- 鉑
- Ro
- Rs
- Sa
- 硒
- 四
- Sk
- Sm
- Tn
- Tr
- Vg

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：

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


## <a name="international-classification-of-diseases-icd-10-cm"></a>國際分類的疾病 (ICD-10-釐米) 

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 會找到來自 Dictionary_icd_10_updated 的關鍵字。
- 會找到來自 Dictionary_icd_10_codes 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

### <a name="keywords"></a>關鍵字

Dictionary_icd_10_updated 關鍵字字典中的任何字詞，都是以 [國際分類的疾病、第十個修訂版本、臨床修改 (icd-10 釐米) ](https://go.microsoft.com/fwlink/?linkid=852604)為基礎。 這種類型只會尋找字詞，而不是保險碼。

Dictionary_icd_10_codes 關鍵字字典中的任何字詞，都是以 [國際分類的疾病、第十個修訂版本、臨床修改 (icd-10 釐米) ](https://go.microsoft.com/fwlink/?linkid=852604)為基礎。 這種類型只會查看保險業代碼，而不是描述。

## <a name="international-classification-of-diseases-icd-9-cm"></a>疾病 (ICD-9 釐米) 的國際分類

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 會找到來自 Dictionary_icd_9_updated 的關鍵字。
- 會找到來自 Dictionary_icd_9_codes 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

Dictionary_icd_9_updated 關鍵字字典中的任何字詞，都是以 [國際分類的疾病、第九份版本、臨床修改 (icd-9 釐米) ](https://go.microsoft.com/fwlink/?linkid=852605)為基礎。 這種類型只會尋找字詞，而不是保險碼。

Dictionary_icd_9_codes 關鍵字字典中的任何字詞，都是以 [國際分類的疾病、第九份版本、臨床修改 (icd-9 釐米) ](https://go.microsoft.com/fwlink/?linkid=852605)為基礎。 這種類型只會查看保險業代碼，而不是描述。

## <a name="ip-address"></a>IP 位址

### <a name="format"></a>格式

#### <a name="ipv4"></a>IPv4：
用於格式化 (期間的複雜模式) 及未格式化 (不) IPv4 位址的版本

#### <a name="ipv6"></a>IPv6：
IPv6 數位格式的複雜模式，其中包含冒號 () 

### <a name="pattern"></a>模式

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

針對 IPv6，當鄰近300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的高可信度：
- 正則運算式 Regex_ipv6_address 找到符合模式的內容。
- 找不到 Keyword_ipaddress 的關鍵字。

針對 IPv4，當鄰近300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的高可信度：
- 正則運算式 Regex_ipv4_address 找到符合模式的內容。
- 會找到來自 Keyword_ipaddress 的關鍵字。

針對 IPv6，當鄰近300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的高可信度：
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

- IP (此關鍵字區分大小寫) 
- ip 位址
- ip 位址
- 網際網路通訊協定
- IP-כתובתה

## <a name="ireland-drivers-license-number"></a>愛爾蘭駕照編號

### <a name="format"></a>格式

六位數後接四個字母

### <a name="pattern"></a>模式

六位數和四個字母：

- 六位數
- 四個字母 (不區分大小寫) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。

- 正則運算式會  `Regex_ireland_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_ireland_eu_driver's_license_number` 。

```xml
      <!-- Ireland Driver's License Number -->
      <Entity id="e01bccd9-eb4d-414f-ace1-e9b6a4c4a2ca" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_ireland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver ' s_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>愛爾蘭護照號碼

### <a name="format"></a>格式

兩個字母或數位後接7位數，不含空格或分隔符號

### <a name="pattern"></a>模式

兩個字母或數位後接7位數：

- 兩位數的數位或字母 (不區分大小寫) 
- 七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_ireland_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_ireland_eu_passport_number` 。
- 正則運算式 `Regex_ireland_eu_passport_date` 會以 DD MMM/MMM YYYY 的格式尋找日期 (範例-01 BEA/1988) 或找到關鍵字。 `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_ireland_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_ireland_eu_passport_number` 。

```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="ireland-personal-public-service-pps-number"></a>愛爾蘭個人公開服務 (PPS) 號碼

### <a name="format"></a>格式

舊格式 (直到2012年12月31日) ：
- 七位數後接1-2 個字母

新格式 (1 月2013日和之後) ：
- 七位數後接兩個字母

### <a name="pattern"></a>模式

舊格式 (直到2012年12月31日) ：
- 七位數
- 一個至兩個字母 (不區分大小寫) 

新格式 (1 月2013日和之後) ：
- 七位數
- 信 (不區分大小寫) （字母檢查碼）
- 範圍 A-I 或 "W" 中的選用字母

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_ireland_pps 找到符合模式的內容。
- 會找到來自 Keywords_ireland_eu_national_id_card 的關鍵字。
- 校驗和通過。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 Func_ireland_pps 找到符合模式的內容。
- 校驗和通過。

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
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
- phearsanta seirbhíse poiblí
- pps 否
- pps 號碼
- pps 數位
- pps 服務否
- ppsn
- ppsno#
- ppsno
- Psp
- 公用服務否
- publicserviceno#
- publicserviceno
- 收入與社交保險號碼
- rsi 否
- rsi 編號
- rsin
- seirbhís aitheantais 用戶端
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
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

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

-   מספר זהות
-   מספר זיה וי
-   מספר זיהוי ישר אלי      
-   זהותישר אלית
-   هو ية اسرائيل ية عدد
-   هوية إسرائ يلية
-   رقم الهوية
-   عدد هوية فريدة من نوعها
-   idnumber#
-   識別碼號碼
-   identity no        
-   identitynumber#
-   身分識別號碼
-   israeliidentitynumber       
-   個人識別碼
-   唯一識別碼  


## <a name="italy-drivers-license-number"></a>義大利駕照編號

這種類型的實體包含在歐盟駕駛執照號碼的敏感資訊類型中。 它也可以當成獨立的機密資訊類型實體。

### <a name="format"></a>格式

10個字母和數位的組合

### <a name="pattern"></a>模式

10個字母和數位的組合：
- 一個字母 (不區分大小寫) 
- 字母 "A" 或 "V" (不區分大小寫) 
- 七位數
- 一個字母 (不區分大小寫) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會 `Regex_italy_drivers_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keyword_italy_drivers_license_number` 。

```xml
    <!-- Italy Driver's license Number -->
    <Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keyword_italy_drivers_license_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente
- patente di guida
- patente guida
- patenti di guida
- patenti guida


## <a name="italy-fiscal-code"></a>義大利會計代碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

指定之模式中字母和數位的16個字元組合

### <a name="pattern"></a>模式

字母和數位的16個字元的組合：
- 與系列名稱中的前三個雙子音相對應的三個字母
- 與名字中的第一個、第三個和第四個雙子音相對應的三個字母
- 與出生年份的最後一個數位相對應的兩位數
- 對應至出生月份之字母的一個字母，在字母順序中使用字母，但是只會使用字母 A 到 E、H、L、M、P、P、R (所以，一月份為 A，10月是 R) 
- 對應至出生月份天的兩位數，以便區別 genders，40會加入女士的出生日。
- 相對於 municipality 人員專屬之地區代碼的四位數，在國外國家/地區使用 (全國的碼) 
- 一個同位數位

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_italy_eu_national_id_card` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_italy_eu_national_id_card` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_italy_eu_national_id_card` 會找到符合模式的內容。

```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
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
- codice fiscale
- codice 識別碼 personale
- codice personale
- 會計代碼
- numero certificato personale
- numero di identificazione fiscale
- numero 識別碼 personale
- numero personale
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

### <a name="format"></a>格式

兩個字母或數位後接7位數，不含空格或分隔符號

### <a name="pattern"></a>模式

兩個字母或數位後接7位數：

- 兩位數的數位或字母 (不區分大小寫) 
- 七位數

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_italy_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_italy_eu_passport_number` 。
- 正則運算式 `Regex_italy_eu_passport_date` 會以 DD MMM/MMM YYYY 的格式來找到日期。 (範例-01 GEN/JAN 1988) 或 `Keywords_eu_passport_date` 找到關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_italy_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_italy_eu_passport_number` 。

```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="italy-value-added-tax-number"></a>義大利值增加的納稅號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

13個字元的字母元字母模式，選用分隔符號

### <a name="pattern"></a>模式

13個字元的字母數位模式，具有選用的分隔符號：

- I 或 i
- T 或 t
- 選用空格、點、連字號或逗號
- 11位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_italy_value_added_tax_number 找到符合模式的內容。
- 會找到來自 Keywords_italy_value_added_tax_number 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_italy_value_added_tax_number 找到符合模式的內容。

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- 加值稅號碼
- 加值稅否
- 加值稅#
- iva
- iva#


## <a name="japan-bank-account-number"></a>日本銀行帳戶號碼

### <a name="format"></a>格式

7或8位數

### <a name="pattern"></a>模式

銀行帳戶號碼：
- 7或8位數
- 銀行帳戶分支程式碼：
- 四位數
- 一個空格或破折號 (選用) 
- 三位數

總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_jp_bank_account 找到符合模式的內容。
- 會找到來自 Keyword_jp_bank_account 的關鍵字。
- 下列其中一項為真：
- 函數 Func_jp_bank_account_branch_code 找到符合模式的內容。
- 會找到來自 Keyword_jp_bank_branch_code 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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
- 口座番號
- 銀行口座
- 銀行口座番號
- 総合口座
- 普通預金口座
- 普通口座
- 當座預金口座
- 當座口座
- 預金口座
- 振替口座
- 銀行
- バンク

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番號
- 支店コード
- 店番號

## <a name="japan-drivers-license-number"></a>日本駕照編號

### <a name="format"></a>格式

12位數

### <a name="pattern"></a>模式

12個連續數位

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- driver'slicenses
- driverlicenses
- Dl#
- Dls#
- 許可證#
- lics#
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番號
- 運転免許番號
- 免許証番號
- 免許番號
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- 運転免許証no
- 運転免許no
- 免許証no
- 免許no
- 運転経歴証明書番號
- 運転経歴証明書
- 運転免許証No.
- 運転免許No.
- 免許証No.
- 免許No.
- 運転免許証#
- 運転免許#
- 免許証#
- 免許#


## <a name="japan-my-number---corporate"></a>日本我的號碼-公司
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

13位數數位

### <a name="pattern"></a>模式

13位數數位：

- 一位數從1到9
- 12位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_japanese_my_number_corporate 找到符合模式的內容。
- 會找到來自 Keywords_japanese_my_number_corporate 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_japanese_my_number_corporate 找到符合模式的內容。

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- 公司號碼
- マイナンバー
- 共通番號
- マイナンバーカード
- マイナンバーカード番號
- 個人番號カード
- 個人識別番號
- 個人識別ナンバー
- 法人番號
- 指定通知書


## <a name="japan-my-number---personal"></a>日本我的號碼-個人
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

12位數數位

### <a name="pattern"></a>模式

12位數數位：

- 四位數
- 選擇性的空格、點或連字號
- 四位數
- 選擇性的空格、點或連字號
- 四位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_japanese_my_number_personal 找到符合模式的內容。
- 會找到來自 Keywords_japanese_my_number_personal 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 Func_japanese_my_number_personal 找到符合模式的內容。

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- 我的號碼
- マイナンバー
- 個人番號
- 共通番號
- マイナンバーカード
- マイナンバーカード番號
- 個人番號カード
- 個人識別番號
- 個人識別ナンバー
- 通知カード


## <a name="japan-passport-number"></a>日本護照號碼

### <a name="format"></a>格式

兩個字母后接7位數

### <a name="pattern"></a>模式

兩個字母 (不區分大小寫) 後接7位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

- 護照
- 護照號碼
- 護照編號
- 護照#
- パスポート
- パスポート番號
- パスポートナンバー
- パスポート＃
- パスポート#
- パスポートNo.
- 旅券番號
- 旅券番號＃
- 旅券番號♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>日本住家電話卡號碼

### <a name="format"></a>格式

12個字母和數位

### <a name="pattern"></a>模式

12個字母和數位：
- 兩個字母 (不區分大小寫) 
- 八位數
- 兩個字母 (不區分大小寫) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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
- 在留カード
- 在留番號

## <a name="japan-resident-registration-number"></a>日本居民登記號碼

### <a name="format"></a>格式

11位數

### <a name="pattern"></a>模式

11個連續數位

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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
- 居民基本登錄號碼
- 常駐登記編號
- 居民收銀機否。
- 居民基本登錄否。
- 基本居民收銀機 No。
- 外國人登録証明書番號
- 証明書番號
- 登録番號
- 外國人登録証


## <a name="japan-social-insurance-number-sin"></a>日本社交保險號碼 (SIN) 

### <a name="format"></a>格式

7-12 位數

### <a name="pattern"></a>模式

7-12 位數：
- 四位數
- 連字號 (選用) 
- 六位數或
- 7-12 連續位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_jp_sin 找到符合模式的內容。
- 會找到來自 Keyword_jp_sin 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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
- 健康保険被保険者番號
- 健保番號
- 基礎年金番號
- 雇用保険被保険者番號
- 雇用保険番號
- 保険証番號
- 社會保険番號
- 社會保険No.
- 社會保険
- 介護保険
- 介護保険被保険者番號
- 健康保険被保険者整理番號
- 雇用保険被保険者整理番號
- 厚生年金
- 厚生年金被保険者整理番號


## <a name="latvia-drivers-license-number"></a>拉脫維亞駕駛執照號碼

### <a name="format"></a>格式

三個字母后接六位數

### <a name="pattern"></a>模式

三個字母和六位數：

- 不區分大小寫的 (三個字母) 
- 六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_latvia_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_latvia_eu_driver's_license_number` 。

```xml
      <!-- Latvia Driver's License Number -->
      <Entity id="ec996de0-30f2-46b1-b192-4d2ff8805fa7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_latvia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver ' s_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>拉脫維亞個人程式碼

### <a name="format"></a>格式

11位數和選擇性連字號

### <a name="pattern"></a>模式

舊格式

11位數和連字號：

- 對應至出生日期 (DDMMYY 的六位數) 
- 連字號
- 一個數位，對應至出生的世紀 ( "0"，第5個世紀，"1" 表示20世紀，而 "2" 表示21世紀) 
- 四位數（隨機產生）

新格式

11位數

- 兩位數 "32"
- 九位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_latvia_eu_national_id_card` 或正則運算式 `Regex_latvia_eu_national_id_card_new_format` 找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_latvia_eu_national_id_card` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_latvia_eu_national_id_card` 或正則運算式 `Regex_latvia_eu_national_id_card_new_format` 找到符合模式的內容。

```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- 管理號碼
- alvas nē
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
- identifikācijas numurs
- 識別碼-號碼
- 個別號碼
- latvija alva
- nacionālais 識別碼
- 國家識別碼
- 本國識別號碼
- 本國身分識別號碼
- 本國保險號碼
- 本國收銀機號碼
- nodokļa numurs
- nodokļu 識別碼
- nodokļu identifikācija numurs
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

### <a name="format"></a>格式

兩個字母或數位後接7位數，不含空格或分隔符號

### <a name="pattern"></a>模式

兩個字母或數位後接7位數：

- 兩位數的數位或字母 (不區分大小寫) 
- 七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_latvia_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_latvia_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date1` 會發現日期格式為 DD YYYY 或關鍵字 from `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_latvia_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_latvia_eu_passport_number` 。

```xml
      <!-- Latvia Passport Number -->
      <Entity id="23ae25ec-cc28-421b-b77a-3054eadf1ede" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport 否
- n ° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="lithuania-drivers-license-number"></a>立陶宛駕照編號

### <a name="format"></a>格式

不含空格及分隔符號的八位數

### <a name="pattern"></a>模式

八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_lithuania_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_lithuania_eu_driver's_license_number` 。

```xml
      <!-- Lithuania Driver's License Number -->
      <Entity id="86f7628b-e0f4-4dc3-9fbc-e4300e4c7d78" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver ' s_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo numeris
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>立陶宛個人程式碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

11位數，不含空格及分隔符號

### <a name="pattern"></a>模式

11位數，不含空格及分隔符號：

- 對應至人員性別和出生世紀的一個數位 (1-6) 
- 對應至出生日期 (YYMMDD 的六位數) 
- 對應至出生日期之序號的三位數
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_lithuania_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_lithuania_eu_tax_file_number` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_lithuania_eu_tax_file_number` 會找到符合模式的內容。

```xml
      <!-- Lithuania Personal Code -->
      <Entity id="cd6d3786-8ec3-4524-a2cf-1e0095379171" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_lithuania_eu_telephone_number" />
            <Match idRef="Keywords_lithuania_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- asmens kodas
- 公民服務號碼
- mokesčių識別碼
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių numeris
- 國家識別號碼
- 個人程式碼
- 個人數位代碼
- piliečio paslaugos numeris
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
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- 唯一識別碼
- 唯一的身分識別號碼
- uniqueidentityno#

## <a name="lithuania-passport-number"></a>立陶宛護照號碼

### <a name="format"></a>格式

八位數的數位或字母，不含空格或分隔符號

### <a name="pattern"></a>模式

八位數的數位或字母 (不區分大小寫) 

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_lithuania_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_lithuania_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date3` 會找到日期格式為 DD MM YYYY 或關鍵字 from。 `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_lithuania_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_lithuania_eu_passport_number` 。

```xml
      <!-- Lithuania Passport Number -->
      <Entity id="1b79900f-047b-4c3f-846f-7d73b5534bce" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="luxemburg-drivers-license-number"></a>Luxemburg 駕駛執照號碼

### <a name="format"></a>格式

六位數，不含空格及分隔符號

### <a name="pattern"></a>模式

六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_luxemburg_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_luxemburg_eu_driver's_license_number` 。

```xml
      <!-- Luxemburg Driver's License Number -->
      <Entity id="89daf717-1544-4860-9a2e-fc9166dd8852" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver ' s_license_number

- fahrerlaubnis
- Führerschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Luxemburg (自然個人的國家識別號碼) 
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

13位數沒有空格或分隔符號

### <a name="pattern"></a>模式

13位數：

- 11位數
- 兩個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_luxemburg_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_luxemburg_eu_national_id_card` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_luxemburg_eu_tax_file_number` 會找到符合模式的內容。


```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
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
- persönliche identifikationsnummer
- 唯一識別碼
- 唯一身分識別
- uniqueidkey#

## <a name="luxemburg-passport-number"></a>Luxemburg 護照號碼

### <a name="format"></a>格式

八位數的數位或字母，不含空格或分隔符號

### <a name="pattern"></a>模式

八位數的數位或字母 (不區分大小寫) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_luxemburg_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_luxemburg_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date3` 會找到日期格式為 DD MM YYYY 或關鍵字 from。 `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_luxemburg_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_luxemburg_eu_passport_number` 。

```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- 盧森堡通
- 盧森堡 passeport
- 盧森堡護照
- 無 de passeport
- 非 reisepass
- nr-reisepass
- numéro de passeport
- 傳遞 net
- 傳遞 nr
- passnummer
- passeport nombre
- reisepässe
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Luxemburg 非自然人員 (的本國識別碼) 

### <a name="format"></a>格式

11位數

### <a name="pattern"></a>模式

11位數

- 兩位數
- 選擇性的空格
- 三位數
- 選擇性的空格
- 三位數
- 選擇性的空格
- 兩位數
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_luxemburg_eu_tax_file_number_non_natural` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_luxemburg_eu_tax_file_number` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_luxemburg_eu_tax_file_number_non_natural` 會找到符合模式的內容。

```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- sécurité sociale 的回收
- étain 非
- étain#
- identifiant d'impôt
- 盧森堡稅收 identifikatiounsnummer
- numéro d'étain
- numéro d'identification 會計 luxembourgeois
- numéro d'identification fiscale
- 社會保障
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- steier 識別碼
- steier identifikatiounsnummer
- steier nummer
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
- YYMMDD 格式的六位數（出生日期）
- 虛線 (選用) 
- 兩個字母的出生代碼
- 虛線 (選用) 
- 三個亂數字
- 一位數的性別碼

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
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

### <a name="format"></a>格式

兩個字元的組合，並在指定的模式中包含六位數

### <a name="pattern"></a>模式

兩個字元和六位數的組合：

-  (位數或字母的兩個字元，而不區分大小寫) 
- 空格 (選用) 
- 三位數
- 空格 (選用) 
- 三位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_malta_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_malta_eu_driver's_license_number` 。

```xml
      <!-- Malta Driver's License Number -->
      <Entity id="a3bdaa4a-8371-4735-8fa5-56ee0fb4afc4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_malta_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver ' s_license_number

- liċenzja tas-sewqan
- liċenzji tas-sewwieq


## <a name="malta-identity-card-number"></a>馬爾他身分識別卡號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

七位數後接一個字母

### <a name="pattern"></a>模式

七位數後接一個字母：

- 七位數
- "M，G，A，P，L，H，B，Z" (不區分大小寫的一個字母) 

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_malta_eu_national_id_card` 找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_malta_eu_national_id_card` 。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 正則運算式會  `Regex_malta_eu_national_id_card` 找到符合模式的內容。

```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
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
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni tat-taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 個人數位代碼
- 唯一識別碼
- 唯一的身分識別號碼
- uniqueidentityno#


## <a name="malta-passport-number"></a>馬爾他護照號碼

### <a name="format"></a>格式

七位數，不含空格或分隔符號

### <a name="pattern"></a>模式

七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_malta_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_malta_eu_passport_number` 。
- 找到來自的關鍵字 `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_malta_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_malta_eu_passport_number` 。

```xml
      <!-- Malta Passport Number -->
      <Entity id="b2b21198-48f9-4d13-b2a5-03969bff0fb8" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
          <Match idRef="Keywords_eu_passport_date" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="malta-tax-identification-number"></a>馬爾他納稅識別號碼

### <a name="format"></a>格式

針對馬爾他 nationals：
- 指定的模式中的七位數和一個字母

非馬爾他 nationals 及馬爾他式實體：
- 九位數

### <a name="pattern"></a>模式

馬爾他 nationals：7位數和一個字母

- 七位數
- 一個字母 (不區分大小寫) 

非馬爾他 nationals 和馬爾他圖元：九位數

- 九位數

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- Regex  `Regex_malta_eu_tax_file_number`  或 `Regex_malta_eu_tax_file_number_non_maltese_national` 找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_malta_eu_tax_file_number` 。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- Regex  `Regex_malta_eu_tax_file_number` 或 `Regex_malta_eu_tax_file_number_non_maltese_national` 找到符合模式的內容。

```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- 公民服務號碼
- 識別碼 tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni tat-taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
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


## <a name="medicare-beneficiary-identifier-mbi-card"></a>Medicare MBI) 卡的受益人識別碼 (

### <a name="format"></a>格式

11個字元的字母數位模式

### <a name="pattern"></a>模式

- 1到9之間的一個數位
- 一個字母排除 S、L、O、I、B、Z
- 一個數位或字母，不包括 S、L、O、I、B、Z
- 一個數位
- 選用的連字號
- 一個字母排除 S、L、O、I、B、Z
- 一個數位或字母，不包括 S、L、O、I、B、Z
- 一個數位
- 選用的連字號
- 兩個字母，不包括 S、L、O、I、B、Z
- 兩位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_mbi_card` 找到符合模式的內容。
- 找到來自的關鍵字  `Keyword_mbi_card` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_mbi_card` 找到符合模式的內容。

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- mbi
- mbi#
- medicare 受益人#
- medicare 受益人識別碼
- medicare 受益人 no
- medicare 受益人編號
- medicare 受益人#


## <a name="mexico-unique-population-registry-code-curp"></a>墨西哥的唯一人口登錄碼 (CURP) 

### <a name="format"></a>格式

18個字元的字母數位模式

### <a name="pattern"></a>模式

- 不區分大小寫 (四個字母) 
- 六位數表示有效的日期
- 字母-H/h 或 M/m
- 兩個字母表示有效的墨西哥狀態碼
- 三個字母
- 一個字母或數位
- 一個數位

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_mexico_population_registry_code` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keyword_mexico_population_registry_code` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_mexico_population_registry_code` 會找到符合模式的內容。

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- Unique 填充登錄代碼 
- 唯一的人口程式碼
- CURP
- 個人識別碼
- 唯一識別碼
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave 個人 Identidad
- 個人 Identidad Clave
- ClaveÚnica
- claveunica
- clavepersonalIdentidad


## <a name="netherlands-citizens-service-bsn-number"></a>荷蘭公民服務 (BSN) 號碼

### <a name="format"></a>格式

8或9位數包含選擇性空格

### <a name="pattern"></a>模式

八-九位數：
- 三位數
- 空格 (選用) 
- 三位數
- 空格 (選用) 
- 兩個三位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_netherlands_bsn 找到符合模式的內容。
- 會找到來自 Keyword_netherlands_bsn 的關鍵字。
- 校驗和通過。

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
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
- persoonlijk nummer
- persoonlijke numerieke 程式碼
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- 社交會計編號
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- 唯一識別碼
- 唯一的身分識別號碼
- uniqueidentityno#

## <a name="netherlands-drivers-license-number"></a>荷蘭駕駛執照號碼

### <a name="format"></a>格式

10位數，不含空格及分隔符號

### <a name="pattern"></a>模式

10位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_netherlands_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_netherlands_eu_driver's_license_number` 。

```xml
      <!-- Netherlands Driver's License Number -->
      <Entity id="6247fbea-ab80-4be5-8233-308b7c031401" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
            </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver ' s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>荷蘭護照號碼

### <a name="format"></a>格式

不含空格或分隔符號的九個字母或數位

### <a name="pattern"></a>模式

九個字母或數位

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_netherlands_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_netherlands_eu_passport_number` 。
- 正則運算式會 `Regex_netherlands_eu_passport_date` 以 DD MMM/mmm YYYY 的格式來找到日期 (範例-26 MAA/MAR 2012) 

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_netherlands_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_netherlands_eu_passport_number` 。

```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>荷蘭稅務識別號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

九位數，不含空格或分隔符號

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_netherlands_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_netherlands_eu_tax_file_number` 。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數  `Func_netherlands_eu_tax_file_number` 會找到符合模式的內容。

```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- hollânske 納稅識別
- hulandes impuesto id 號碼
- hulandes impuesto 識別
- identificatienummer belasting
- identificatienummer van belasting
- impuesto 識別碼
- impuesto 編號
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
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


## <a name="netherlands-value-added-tax-number"></a>荷蘭增值納稅號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

14個字元的字母數位模式

### <a name="pattern"></a>模式

14個字元的字母數位模式：

- N 或 n
- L 或 l
- 選用的空格、點或連字號
- 九位數
- 選用的空格、點或連字號
- B 或 b
- 兩位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_netherlands_value_added_tax_number 找到符合模式的內容。
- 會找到來自 Keywords_netherlands_value_added_tax_number 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_netherlands_value_added_tax_number 找到符合模式的內容。

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- 加值稅號碼
- 加值稅否
- 加值稅#
- wearde tafoege 稅收 getal
- btw nûmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>紐西蘭銀行帳戶號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

14位數至16位數的模式，具有選用的分隔符號

### <a name="pattern"></a>模式

14位數至16位數的模式，具有選用的分隔符號：

- 兩位數
- 選用的連字號或空格
- 三至四位數
- 選用的連字號或空格
- 七位數
- 選用的連字號或空格
- 二到三位數
- 選項連字號或空格

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_new_zealand_bank_account_number 找到符合模式的內容。
- 會找到來自 Keywords_new_zealand_bank_account_number 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_new_zealand_bank_account_number 找到符合模式的內容。

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- 帳戶號碼
- 銀行帳戶
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>紐西蘭駕駛執照號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

八個字元的字母數位模式

### <a name="pattern"></a>模式

八個字元的字母數位模式

- 兩個字母
- 六位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_newzealand_driver_license_number 找到符合模式的內容。
- 會找到來自 Keywords_newzealand_driver_license_number 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 Func_newzealand_driver_license_number 找到符合模式的內容。

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslicence
- driverslicences
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- driverlic#
- driverlics#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 驅動程式許可證#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 國際駕駛允許
- 國際動力允許
- 紐西蘭汽車協會
- 紐西蘭汽車協會


## <a name="new-zealand-inland-revenue-number"></a>紐西蘭 inland 收入數目
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

8或9位數（選用分隔符號）

### <a name="pattern"></a>模式

8或9位數（選用分隔符號）

- 兩位數或三位數
- 選擇性空格或連字號
- 三位數
- 選擇性空格或連字號
- 三位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_new_zealand_inland_revenue_number 找到符合模式的內容。
- 會找到來自 Keywords_new_zealand_inland_revenue_number 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_new_zealand_inland_revenue_number 找到符合模式的內容。

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ird 編號
- ird 否#
- 紐西蘭 ird
- 紐西蘭 ird
- ird 編號
- inland 收入數目


## <a name="new-zealand-ministry-of-health-number"></a>紐西蘭健康情況號碼的部

### <a name="format"></a>格式

三個字母、一個空格 (選用) 及四位數

### <a name="pattern"></a>模式

- 三個字母 (不區分大小寫) 「I ' 和「O ' 除外
- 空格 (選用) 
- 四位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。
- 會找到來自 Keyword_nz_terms 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。
- 校驗和通過。

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- 紐西蘭
- 健康情況
- 治療
- 本國健康情況索引編號
- nhi 編號
- nhi 編號
- NHI#
- 國家健康情況索引否。
- 本國健康情況索引識別碼
- 本國健康情況索引#

## <a name="new-zealand-social-welfare-number"></a>紐西蘭社交 welfare 號碼

此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九位數

- 三位數
- 選用的連字號
- 三位數
- 選用的連字號
- 三位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_newzealand_social_welfare_number 找到符合模式的內容。
- 會找到來自 Keywords_newzealand_social_welfare_number 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 Func_newzealand_social_welfare_number 找到符合模式的內容。

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- 社交 welfare#
- 社交 welfare#
- 社交 welfare 編號
- 社交 welfare 號碼
- swn#


## <a name="norway-identification-number"></a>挪威身分識別號碼

### <a name="format"></a>格式

11位數

### <a name="pattern"></a>模式

11位數：
- DDMMYY 格式的六位數（出生日期）
- 三位數個人號碼
- 兩個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_norway_id_number 找到符合模式的內容。
- 會找到來自 Keyword_norway_id_number 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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
- 識別碼
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

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

### <a name="format"></a>格式

包含兩個正斜線的14位數

### <a name="pattern"></a>模式

14位數和兩個正斜線：

- 五位數
- 一個正斜線
- 兩位數
- 一個正斜線
- 七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_poland_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_poland_eu_driver's_license_number` 。

```xml
      <!-- Poland Driver's License Number -->
      <Entity id="24d51f99-ee9e-4060-a077-cae58cab1ee4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_poland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver ' s_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>波蘭身分識別卡片

### <a name="format"></a>格式

三個字母和六位數

### <a name="pattern"></a>模式

三個字母 (不區分大小寫) 後接六位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_polish_national_id 找到符合模式的內容。
- 會找到來自 Keyword_polish_national_id_passport_number 的關鍵字。
- 校驗和通過。

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

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osobisty
- 轉寄 dowodu osobistego
- Nazwa i 轉寄 dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- 道鐘斯指數。 作業系統。


## <a name="poland-national-id-pesel"></a>波蘭國家識別碼 (PESEL) 

### <a name="format"></a>格式

11位數

### <a name="pattern"></a>模式

- 六位數代表出生日期格式 YYMMDD
- 四位數
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_pesel_identification_number 找到符合模式的內容。
- 會找到來自 Keyword_pesel_identification_number 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_pesel_identification_number 找到符合模式的內容。
- 校驗和通過。

```xml
      <!-- Poland National ID (PESEL) -->
      <Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_pesel_identification_number" />
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
這個敏感資訊類型實體包含在歐盟護照號碼機密資訊類型中。 它也可以當成獨立的機密資訊類型實體。

### <a name="format"></a>格式

兩個字母和七位數

### <a name="pattern"></a>模式

兩個字母 (不區分大小寫) 後接7位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 `Func_polish_passport_number_v2` 會找到符合模式的內容。
- 校驗和通過。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keyword_polish_national_passport_number` 。
- 找到來自的關鍵字 `Keywords_eu_passport_date` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 `Func_polish_passport_number_v2` 會找到符合模式的內容。
- 校驗和通過。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keyword_polish_national_passport_number` 。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 `Func_polish_passport_number_v2` 會找到符合模式的內容。
- 校驗和通過。

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- 轉寄 paszportu
- numery paszportów
- numery paszportowe
- nr paszportu
- 星期日。 paszportu
- nr paszportów
- n ° passeport
- passeport n °

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="poland-regon-number"></a>波蘭 REGON 編號
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

9位數或14位數的數位

### <a name="pattern"></a>模式

九位數數位或14位數：

- 九位數或
- 九位數
- 字元
- 五位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_polish_regon_number 找到符合模式的內容。
- 會找到來自 Keywords_polish_regon_number 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 Func_polish_regon_number 找到符合模式的內容。

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>關鍵字

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon 識別碼
- 統計數字
- 統計識別碼
- 統計否
- regon 編號
- regonid#
- regonno#
- 公司識別碼
- companyid#
- companyidno#
- 轉寄 statystyczny
- numeru regon
- numerstatystyczny#
- numeruregon#


## <a name="poland-tax-identification-number"></a>波蘭納稅識別號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

11位數，不含空格或分隔符號

### <a name="pattern"></a>模式

11位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_poland_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_poland_eu_tax_file_number` 。


```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- 咬#
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

### <a name="format"></a>格式

八位數

### <a name="pattern"></a>模式

八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
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

### <a name="format"></a>格式

兩個模式：兩個字母，後面加上以特殊字元顯示的5-8 位數

### <a name="pattern"></a>模式

模式1：兩個字母后接以特殊字元的5/6：
- 兩個字母 (不區分大小寫) 
- 連字號
- 五或六位數
- 一個空格
- 一個數位

模式2：一個字母后接6/8 位數，含特殊字元：
- 一個字母 (不區分大小寫) 
- 連字號
- 六位數或八位數
- 一個空格
- 一個數位


### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_portugal_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_portugal_eu_driver's_license_number` 。

```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver ' s_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução 葡萄牙
- carta de condução

## <a name="portugal-passport-number"></a>葡萄牙護照號碼

### <a name="format"></a>格式

一個字母后接六位數，不含空格或分隔符號

### <a name="pattern"></a>模式

一個字母后接六位數：

- 一個字母 (不區分大小寫) 
- 六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_portugal_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_portugal_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date1` 會發現日期格式為 DD YYYY 或關鍵字 from `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_portugal_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_portugal_eu_passport_number` 。

```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número 執行 passaporte
- 葡萄牙文護照
- 葡萄牙 passeport
- 葡萄牙 passaporte
- passaporte n º
- passeport n º
- números de passaporte
- 葡萄牙 passports
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="portugal-tax-identification-number"></a>葡萄牙納稅識別號碼

### <a name="format"></a>格式

包含選擇性空格的九位數

### <a name="pattern"></a>模式

- 三位數
- 選擇性的空格
- 三位數
- 選擇性的空格
- 三位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_portugal_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_portugal_eu_tax_file_number` 。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數  `Func_portugal_eu_tax_file_number` 會找到符合模式的內容。

```xml
      <!-- Portugal Tax Identification Number -->
      <Entity id="65372402-3131-4f1e-9983-4439841d1f15" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
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

### <a name="format"></a>格式

一個字元後接八位數

### <a name="pattern"></a>模式

一個字元後接八位數：
- 一個字母 (不區分大小寫) 或數位
- 八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_romania_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_romania_eu_driver's_license_number` 。

```xml
      <!-- Romania Driver's License Number -->
      <Entity id="b5511ace-2fd8-4ae4-b6fc-c7c6e4689e3c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_romania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver ' s_license_number

- permis de conducere
- permisului de conducere
- permisului conducere
- permisele de conducere
- permisele conducere
- permis conducere

## <a name="romania-personal-numeric-code-cnp"></a>羅馬尼亞個人數位代碼 (CNP) 
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

13位數，不含空格及分隔符號

### <a name="pattern"></a>模式

- 1-9 的一個數位
- 六位數代表出生日期 (YYMMDD) 
- 兩位數，可以是01-52 或99
- 四位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_romania_eu_national_id_card` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_romania_eu_national_id_card` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_romania_eu_national_id_card` 會找到符合模式的內容。

```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
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
- număr identitate
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

### <a name="format"></a>格式

8或9位數，不含空格及分隔符號

### <a name="pattern"></a>模式

8或9位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_romania_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_romania_eu_passport_number` 。
- 正則運算式 `Regex_romania_eu_passport_date` 會以 DD MMM/MMM YY 的格式來尋找日期 (範例-01 年2月/2 月 10) 或找到關鍵字]。 `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_romania_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_romania_eu_passport_number` 。

```xml
      <!-- Romania Passport Number -->
      <Entity id="5d31b90c-7fe2-4a76-a14b-767b8fd19d6c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_romania_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul pașaportului numarul pasaportului numerele pașaportului Pașaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="russia-passport-number-domestic"></a>俄羅斯護照號碼國內
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

10位數數位

### <a name="pattern"></a>模式

10位數數位：

- 兩位數
- 選擇性空格或連字號
- 兩位數
- 選擇性的空格
- 六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- Regex Regex_Russian_Passport_Number_Domestic 找到符合模式的內容。
- 會找到來自 Keyword_Russian_Passport_Number 的關鍵字。

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- 護照號碼
- 護照否
- 護照#
- 護照識別碼
- passportno#
- passportnumber#
- паспорт нет
- паспорт識別碼
- pоссийской паспорт
- pусский номер паспорта
- паспорт#
- паспортid#
- номер паспорта
- номерпаспорта#


## <a name="russia-passport-number-international"></a>俄羅斯護照號碼國際
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

九位數數位

### <a name="pattern"></a>模式

九位數數位：

- 兩位數
- 選擇性空格或連字號
- 七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- Regex Regex_Russian_Passport_Number_International 找到符合模式的內容。
- 會找到來自 Keyword_Russian_Passport_Number 的關鍵字。

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- 護照號碼
- 護照否
- 護照#
- 護照識別碼
- passportno#
- passportnumber#
- паспорт нет
- паспорт識別碼
- pоссийской паспорт
- pусский номер паспорта
- паспорт#
- паспортid#
- номер паспорта
- номерпаспорта#


## <a name="saudi-arabia-national-id"></a>沙烏地阿拉伯國際身分識別

### <a name="format"></a>格式

10位數

### <a name="pattern"></a>模式

10個連續數位

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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


## <a name="singapore-national-registration-identity-card-nric-number"></a>新加坡國家註冊身分識別卡 (NRIC) 號碼

### <a name="format"></a>格式

九個字母和數位

### <a name="pattern"></a>模式

- 九個字母和數位：
- 字母 "F"、"G"、"S" 或 "T" (不區分大小寫) 
- 七位數
- 字母檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 Regex_singapore_nric 找到符合模式的內容。
- 會找到來自 Keyword_singapore_nric 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

### <a name="format"></a>格式

一個字元後接7位數

### <a name="pattern"></a>模式

一個字元後接7位數

- 一個字母 (不區分大小寫) 或數位
- 七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_slovakia_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_slovakia_eu_driver's_license_number` 。

```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver ' s_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>斯洛伐克個人號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

包含選擇性反斜線的九或10位數

### <a name="pattern"></a>模式

- 六位數代表出生日期
- 選用斜線 (/) 
- 三位數
- 一個選擇性檢查碼碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_slovakia_eu_national_id_card` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_slovakia_eu_national_id_card` 。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數  `Func_slovakia_eu_national_id_card` 會找到符合模式的內容。

```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- 出生號碼
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- 識別碼號碼
- 識別碼否
- 識別號碼
- identifikačná karta č
- identifikačné číslo
- 身分識別卡
- 身分識別卡號碼
- národná identifikačná značka č
- 國家/地區號碼
- nationalnumber#
- nemzeti személyazonosító igazolvány
- personalidnumber#
- rč
- rodne cislo
- rodné číslo
- 社會安全號碼
- Ssn#
- Ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
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

### <a name="format"></a>格式

一個數位或字母后接7位數，不含空格或分隔符號

### <a name="pattern"></a>模式

一個數位或字母 (不區分大小寫) 後接7位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_slovakia_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_slovakia_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date1` 會發現日期格式為 DD YYYY 或關鍵字 from `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_slovakia_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_slovakia_eu_passport_number` 。

```xml
      <!-- Slovakia Passport Number -->
      <Entity id="238e1f08-d80e-4793-af33-9b57918335b7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- pas č。
- Passeport n °
- n ° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="slovenia-drivers-license-number"></a>斯洛維尼亞駕照編號

### <a name="format"></a>格式

九位數，不含空格及分隔符號

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_slovenia_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_slovenia_eu_driver's_license_number` 。

```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver ' s_license_number

- vozniško dovoljenje
- vozniška številka 許可證
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>斯洛維尼亞唯一主公民號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

13位數，不含空格或分隔符號

### <a name="pattern"></a>模式

指定的模式中的13位數：

- 對應至出生日期 (DDMMLLL) （其中 "LLL" 會對應至出生年份的後三位數）的7位數
- 對應至出生 "50" 區域的兩位數
- 三個數字，對應于一天出生的性別和序數的組合。 000-499 適用于雌雄的插頭和500-999。
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_slovenia_eu_national_id_card` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_slovenia_eu_national_id_card` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_slovenia_eu_national_id_card` 會找到符合模式的內容。

```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
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

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- 身份證
- 識別號碼
- identifikacijska številka
- 身份證
- nacionalna 識別碼
- nacionalni potni 清單
- 國家識別碼
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- 個人程式碼
- 個人號碼
- 個人數位代碼
- številka državljana
- 唯一公民編號
- 唯一識別碼
- 唯一的身分識別號碼
- 唯一主公民號碼
- 唯一註冊號碼
- uniqueidentityno#
- uniqueidentityno#

## <a name="slovenia-passport-number"></a>斯洛維尼亞護照號碼

### <a name="format"></a>格式

兩個字母后接7位數，不含空格或分隔符號

### <a name="pattern"></a>模式

兩個字母后接7位數：

- 字母 "P"
- 單一大寫字母
- 七位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_slovenia_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_slovenia_eu_passport_number` 。
- 正則運算式 `Regex_eu_passport_date1` 會發現日期格式為 DD YYYY 或關鍵字 from `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_slovenia_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_slovenia_eu_passport_number` 。

```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- potni 清單#
- 基準 rojstva
- potni 清單
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="slovenia-tax-identification-number"></a>斯洛維尼亞納稅識別號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

八位數沒有空格或分隔符號

### <a name="pattern"></a>模式

- 1-9 的一個數位
- 六位數
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_slovenia_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_slovenia_eu_tax_file_number` 。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數  `Func_slovenia_eu_tax_file_number` 會找到符合模式的內容。

```xml
      <!-- Slovenia Tax Identification Number -->
      <Entity id="e47b071e-c352-4d70-8241-8c215ad65505" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
          <Match idRef="Keywords_slovenia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
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
- YYMMDD 格式的六位數（出生日期）
- 四位數
- 單一數位的公民指示器
- 數位 "8" 或 "9"
- 一位數，也就是校驗和位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
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
- YYMMDD 格式的六位數（出生日期）
- 連字號
- 一個數位是由世紀和性別決定
- 四位數的出生區功能變數代碼
- 一種用來區分先前號碼相同之人員的數位
- 檢查碼。

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_south_korea_resident_number 找到符合模式的內容。
- 會找到來自 Keyword_south_korea_resident_number 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

### <a name="format"></a>格式

八位數後接一個字元

### <a name="pattern"></a>模式

八位數後接一個字元：

- 八位數
- 一個數位或字母 (不區分大小寫) 

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_spain_eu_driver's_license_number` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 找到符合模式的內容。

```xml
      <!-- Spain Driver's License Number -->
      <Entity id="d5a82922-b501-4f40-8868-341321146aa2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver ' s_license_number

- permiso de conducción
- permiso conducción
- licencia de conducir
- licencia conducir
- permiso conducir
- permiso de conducir
- permisos de conducir
- permisos conducir
- carnet conducir
- carnet de conducir
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>西班牙 DNI
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

八位數後接一個字元

### <a name="pattern"></a>模式

七位數後接一個字元

- 八位數
- 選擇性空格或連字號
- 一個檢查信件 (不區分大小寫) 

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_spain_eu_national_id_card"` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 找到符合模式的內容。


```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
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
- identidad único
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
- número nacional identidad
- 個人身分識別號碼
- 個人身分識別
- 唯一的身分識別號碼
- uniqueid#

## <a name="spain-passport-number"></a>西班牙護照號碼

### <a name="format"></a>格式

8或9個字元組合的字母和數位，不含空格或分隔符號

### <a name="pattern"></a>模式

字母和數位的8或9個字元組合：

- 兩位數或字母
- 一個數位或字母 (選用) 
- 六位數

### <a name="checksum"></a>總和檢查碼

不適用

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式會  `Regex_spain_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_spain_eu_passport_number` 。
- 正則運算式 `Regex_spain_eu_passport_date` 會找到日期格式為 DD-MM-YYYY 或關鍵字 from。 `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_spain_eu_passport_number` 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_spain_eu_passport_number` 。

```xml
      <!-- Spain Passport Number -->
      <Entity id="d17a57de-9fa5-4e9f-85d3-85c26d89686e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_spain_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- españa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte 否
- Passeport n °
- n ° Passeport
- pasaporte 編號
- pasaporte n °
- 西班牙護照

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="spain-social-security-number-ssn"></a> (SSN) 的西班牙社會安全號碼


### <a name="format"></a>格式

11-12 位數

### <a name="pattern"></a>模式

11-12 位數：
- 兩位數
- 轉寄斜線 (選用) 
- 七到八位數
- 轉寄斜線 (選用) 
- 兩位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_spanish_social_security_number 找到符合模式的內容。
- 校驗和通過。
- - 找到來自的關鍵字  `Keywords_spain_eu_ssn_or_equivalent` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_spanish_social_security_number 找到符合模式的內容。
- 校驗和通過。

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- Ssn
- Ssn#
- socialsecurityno
- 社會安全性否
- 社會安全號碼
- número de la seguridad 社交

## <a name="spain-tax-identification-number"></a>西班牙納稅識別號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

指定的模式中的7或8位數，以及一或兩個字母

### <a name="pattern"></a>模式

具有西班牙國身分識別卡的西班牙文自然人員：

- 八位數
- 單一大寫字母 (區分大小寫) 

沒有西班牙國身分身分身分識別卡的非居民 Spaniards

- 一個大寫的字母 "L" (區分大小寫) 
- 七位數
- 單一大寫字母 (區分大小寫) 

在沒有西班牙國身分識別卡的14年年齡底下的居民 Spaniards：

- 一個大寫的字母 "K" (區分大小寫) 
- 七位數
- 單一大寫字母 (區分大小寫) 

Foreigners 與 Foreigner 的識別號碼

- 一個大寫的字母，為 "X"、"Y" 或 "Z" (區分大小寫) 
- 七位數
- 單一大寫字母 (區分大小寫) 

沒有 Foreigner 識別碼的 Foreigners

- 一個大寫的字母，為 "M" (區分大小寫) 
- 七位數
- 單一大寫字母 (區分大小寫) 

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_spain_eu_tax_file_number` 或 `Func_spain_eu_DL_and_NI_number_citizen` 找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_spain_eu_tax_file_number` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_spain_eu_tax_file_number` 或 `Func_spain_eu_DL_and_NI_number_citizen` 找到符合模式的內容。

```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
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
- 等號 (=) 
- 不是貨幣符號的任何字元 ($) ，百分比符號 (% ) ，大於符號 (>) ，符號 ( @ ) ，引號 ( ") ，分號 (; ) ，左大括弧 ( [) ，或左中括弧 ( {) 
- 任何7-128 個字元的組合不是分號 (; ) 、正斜線 (/) 或引號 ( ") 
- 分號 (; ) 或引號 ( ") 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 CEP_Regex_SQLServerConnectionString 找到符合模式的內容。
- 找不到來自 CEP_GlobalFilter 的關鍵字。
- 正則運算式 CEP_PasswordPlaceHolder 找不到符合模式的內容。
- 正則運算式 CEP_CommonExampleKeywords 找不到符合模式的內容。

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

這種敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。

- 密碼或密碼後接0-2 個空格、等號 (=) 、0-2 空間，以及星號 ( * ) -OR-
- 密碼或密碼，接著：
    - 等號 (=) 
    - 小於符號 (<) 
    - 1-200 個字元的任意組合（大小寫字母、數位、星號 ( * ) 、連字號 ( ) 、底線 (_) 或空白字元）
    - 大於符號 (>) 

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

這種敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。

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

### <a name="format"></a>格式

10位數包含連字號

### <a name="pattern"></a>模式

10位數包含連字號：

- 六位數
- 連字號
- 四位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式會  `Regex_sweden_eu_driver's_license_number` 找到符合模式的內容。
- `Keywords_eu_driver's_license_number`找到或的關鍵字 `Keywords_sweden_eu_driver's_license_number` 。

```xml
      <!-- Sweden Driver's License Number -->
      <Entity id="70088720-90dd-47f5-805e-5525f3567391" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_sweden_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver ' s_license_number

- ajokortti
- permis de conducere
- ajokortin numero
- kuljettajat 許可證。
- drivere 許可證。
- körkort
- numărul permisului de conducere
-  שאָפער דערלויבעניש נומער
- förare 許可證。
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>瑞典國家識別碼

### <a name="format"></a>格式

10或12位數和選擇性分隔符號

### <a name="pattern"></a>模式

10或12位數和選用的分隔符號：
- 兩位數 (選用) 
- 日期格式 YYMMDD 的六位數
- "-" 或 "+" 的分隔符號 (選用) 
- 四位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 `Func_swedish_national_identifier` 會找到符合模式的內容。
- 找到來自的關鍵字 `Keywords_swedish_national_identifier`
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 `Func_swedish_national_identifier` 會找到符合模式的內容。
- 校驗和通過。


```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- 識別碼 no
- 識別碼號碼
- Id#
- 識別碼否
- 識別號碼
- identifikationsnumret#
- identifikationsnumret
- identitetshandling
- 身分識別檔
- identity no
- 身分識別號碼
- 識別碼-nummer
- 個人識別碼
- personnummer#
- personnummer
- skatteidentifikationsnummer

## <a name="sweden-passport-number"></a>瑞典護照號碼

### <a name="format"></a>格式

八位數

### <a name="pattern"></a>模式

八個連續數位

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 正則運算式 Regex_sweden_passport_number 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keyword_sweden_passport` 。
- 正則運算式 `Regex_sweden_eu_passport_date` 會找到以 DD MMM/MMM YY 格式 (01 JAN/JAN 12) 或找到關鍵字的日期 `Keywords_eu_passport_date` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 正則運算式 Regex_sweden_passport_number 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keyword_sweden_passport` 。


```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- 外部註冊卡
- g3 處理費用
- 多重專案
- Numéro de passeport
- passeport n °
- passeport 非
- passeport#
- passeport#
- passeportnon
- passeportn °
- passnummer
- 傳遞 nr
- schengen 簽證
- schengen 簽證
- 單一專案
- sverige 傳遞
- 簽證要求
- 簽證處理
- 簽證類型

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="sweden-tax-identification-number"></a>瑞典納稅識別號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

在指定的模式中，10位數和符號

### <a name="pattern"></a>模式

10位數和符號：

- 對應至出生日期 (YYMMDD 的六位數) 
- 加號或減號
- 在下列情況下，識別號碼唯一的三位數：
  - 若為1990之前所簽發的號碼，第七和第八位數識別出生的縣或對外出生的人員
  - 第九個位置中的位數會以奇數為單位表示，甚至是對女的性別
- 一個檢查碼

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數  `Func_sweden_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_sweden_eu_tax_file_number` 。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_sweden_eu_tax_file_number` 會找到符合模式的內容。

```xml
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- 個人號碼
- personnummer
- skatt 識別碼 nummer
- skatt identifikation
- skatteBetalarens identifikationsnummer
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


## <a name="swift-code"></a>SWIFT 代碼

### <a name="format"></a>格式

四個字母后接5-31 個字母或數位

### <a name="pattern"></a>模式

四個字母后接5-31 個字母或數位：
- 四個字母的銀行程式碼 (不區分大小寫) 
- 選擇性的空格
-  ( (BBAN) ) 基本銀行帳戶號碼的4-28 字母或數位
- 選擇性的空格
- BBAN 的其餘部分 (一到三個字母或數位) 

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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
- 迅速#
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift 程式碼
- swift 號碼#
- swift 路由編號
- bic 編號
- bic 程式碼
- bic#
- bic#
- 銀行識別碼代碼
- 組織 internationale de normalisation 9362
- rapide#
- 程式碼 SWIFT
- le numéro 解除的 swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- 程式碼 identificateur de banque
- SWIFTコード
- SWIFT番號
- BIC番號
- BICコード
- SWIFT コード
- SWIFT 番號
- BIC 番號
- BIC コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>瑞士 SSN AHV 號碼
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

13位數數位

### <a name="pattern"></a>模式

13位數數位：

- 三位數-756
- 選用點
- 四位數
- 選用點
- 四位數
- 選用點
- 兩位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_swiss_social_security_number_ahv 找到符合模式的內容。
- 會找到來自 Keywords_swiss_social_security_number_ahv 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_swiss_social_security_number_ahv 找到符合模式的內容。

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- Ssn
- PID
- 保險號碼
- personalidno#
- 社會安全號碼
- 個人號碼
- 個人身分識別
- insuranceno#
- uniqueidno#
- 唯一識別碼
- avs 號碼
- 個人身分識別不 versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- 識別碼 personnelle 識別碼
- numéro de sécurité sociale


## <a name="taiwan-national-identification-number"></a>臺灣國身分識別號碼

### <a name="format"></a>格式

一個英文) 的字母 (後接9位數

### <a name="pattern"></a>模式

一個英文) 的字母 (後接9位數：
- 一個英文字母 (，不區分大小寫) 
- 數位 "1" 或 "2"
- 八位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_taiwanese_national_id 找到符合模式的內容。
- 會找到來自 Keyword_taiwanese_national_id 的關鍵字。
- 校驗和通過。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_taiwanese_national_id 找到符合模式的內容。
- 校驗和通過。

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

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
- 字元 "3"
- 八位數

無生物識別護照號碼：
- 九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

## <a name="taiwan-resident-certificate-arctarc-number"></a>臺灣居民憑證 (ARC/TARC) 號碼

### <a name="format"></a>格式

10個字母和數位

### <a name="pattern"></a>模式

10個字母和數位：
- 兩個字母 (不區分大小寫) 
- 八位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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
- 第一個數位不是零或9
- 12位數

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_Thai_Citizen_Id 找到符合模式的內容。
- 會找到來自 Keyword_Thai_Citizen_Id 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- 識別碼
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

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_Turkish_National_Id 找到符合模式的內容。
- 會找到來自 Keyword_Turkish_National_Id 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- TC Kimlik 否
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık 否

## <a name="uk-drivers-license-number"></a>英國。 駕駛執照號碼

### <a name="format"></a>格式

以指定格式的18個字母和數位的組合

### <a name="pattern"></a>模式

18個字母和數位：
- 五個字母 (不區分大小寫) 或數位 "9" 取代字母。
- 一個數位。
- MMDDY 日期格式的5位數（出生日期）。 如果驅動程式是女，第七個字元會增加50。若為 exampe，51至62，而不是01到12。
- 兩個字母 (不區分大小寫) 或數位 "9" 取代字母。
- 五位數。

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 `Func_uk_drivers_license` 會找到符合模式的內容。
- 找到來自的關鍵字 `Keywords_eu_driver's_license_number` 。
- 校驗和通過。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 `Func_uk_drivers_license` 會找到符合模式的內容。
- 校驗和通過。

```xml
    <!-- U.K. Driver's License Number -->
    <Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75" relaxProximity="true" >
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_drivers_license" />
          <Match idRef="Keywords_eu_driver's_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_uk_drivers_license" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver ' s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- 驅動程式許可證
- 驅動程式 lics
- 駕照
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- 驅動程式 .lic
- 驅動程式 lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式授權
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- 驅動程式「.lic
- 驅動程式 ' lics
- 駕駛執照
- 驅動程式的授權
- 驅動程式 ' 許可證
- 驅動程式 ' 授權
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- 驅動程式的 .lic
- 驅動程式的 lics
- 駕駛執照
- 駕駛執照
- 駕駛執照
- 駕駛執照
- Dl#
- Dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- 驅動程式許可證#
- 驅動程式 lics#
- 駕照#
- 驅動程式授權#
- 驅動程式授權#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- 驅動程式 .lic#
- 驅動程式 lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式授權#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- 驅動程式「.lic#
- 驅動程式 ' lics#
- 駕駛執照#
- 驅動程式的授權#
- 驅動程式 ' 許可證#
- 驅動程式 ' 授權#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- 驅動程式的 .lic#
- 驅動程式的 lics#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛執照#
- 駕駛許可證 
- 駕照
- dlno#
- driv 許可證
- driv licen
- driv 授權
- driv 授權
- driv 許可證
- driv 許可證
- 驅動程式 licen
- 驅動程式 licen
- 驅動程式的 licen
- 駕駛許可證
- 驅車 licen
- 駕駛授權
- 駕駛許可證
- 駕駛許可證
- 駕駛允許
- dl no
- dlno
- dl 編號


## <a name="uk-electoral-roll-number"></a>英國。 electoral 編號

### <a name="format"></a>格式

兩個字母后接1-4 位數

### <a name="pattern"></a>模式

兩個字母 (不區分大小寫) 後接1-4 號碼

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

### <a name="checksum"></a>總和檢查碼

是

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
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

## <a name="uk-national-insurance-number-nino"></a>英國。 本國保險號碼 (NINO) 
這種敏感資訊類型實體包含在歐盟國身分識別號碼的敏感資訊類型中。 它也可以當成獨立的機密資訊類型實體。

### <a name="format"></a>格式

以空格或破折號隔開的七個字元或九個字元

### <a name="pattern"></a>模式

兩種可能的模式：

-  (有效 NINOs 的兩個字母都只使用此前置詞中的特定字元，此方式會驗證;不區分大小寫) 
- 六位數
- "A"、"B"、"C" 或 "d" (類似前置詞，只允許在尾碼中使用特定字元;不區分大小寫) 

或

- 兩個字母
- 一個空格或破折號
- 兩位數
- 一個空格或破折號
- 兩位數
- 一個空格或破折號
- 兩位數
- 一個空格或破折號
- ' A '、' B '、' C ' 或 ' d ' 是 '

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_uk_nino 找到符合模式的內容。
- 會找到來自 Keyword_uk_nino 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_uk_nino 找到符合模式的內容。

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
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
- NI 號碼
- NI 否。
- 鎳#
- 鎳#
- 保險#
- insurancenumber
- nationalinsurance#
- nationalinsurancenumber


## <a name="uk-unique-taxpayer-reference-number"></a>英國。 唯一的納稅人參考編號
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

10位數，不含空格及分隔符號


### <a name="pattern"></a>模式

10位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數  `Func_uk_eu_tax_file_number` 會找到符合模式的內容。
- 找到來自的關鍵字  `Keywords_uk_eu_tax_file_number` 。

```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
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

6-17 位數

### <a name="pattern"></a>模式

6-17 連續位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
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

取決於狀態-例如，紐約：
- 已格式化的九位數，如 ddd ddd ddd 會相符。
- 九位數的 ddddddddd 不相符。

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_new_york_drivers_license_number 找到符合模式的內容。
- 找到來自 Keyword_ [state_name] _drivers_license_name 的關鍵字。
- 會找到來自 Keyword_us_drivers_license 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
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

- 狀態縮寫 (例如 "NY" ) 
- 狀態名稱 (例如，"紐約" ) 

## <a name="us-individual-taxpayer-identification-number-itin"></a>ITIN) 的美國個別納稅人識別號碼 (

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

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_formatted_itin 找到符合模式的內容。
- 會找到來自 Keyword_itin 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_unformatted_itin 找到符合模式的內容。
- 會找到來自 Keyword_itin 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 Func_formatted_itin 或 Func_unformatted_itin 找到符合模式的內容。

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_itin"></a>Keyword_itin

- 納稅人
- 納稅識別碼
- 納稅識別
- itin
- i.t.i.n.
- Ssn
- 錫
- 社會保障
- 納稅人
- itins
- taxid
- 個別納稅人


## <a name="us-social-security-number-ssn"></a> (SSN) 的 U.S. 社會安全號碼

### <a name="format"></a>格式

九位數（可能是格式化或未格式化的模式）

> [!NOTE]
> 若在 2011 mid 之前發出，則 SSN 具有強格式，其中的號碼的某些部分必須在特定範圍內，才能 (，但沒有任何) 校驗和。

### <a name="pattern"></a>模式

四種功能會在四種不同的模式中尋找主旨 ssn：
- Func_ssn 會找到主旨 ssn，其強格式為2011的強格式設定，格式為破折號或空格 (ddd-dd-dddd 或 ddd dd dddd) 
- Func_unformatted_ssn 會以2011的預先設定格式將其強格式設定為九個連續位數 (ddddddddd 的主旨 ssn) 
- Func_randomized_formatted_ssn 會找到以破折號或空格格式化的2011後主旨 ssn， (ddd-dd-dddd 或 ddd dd dddd) 
- Func_randomized_unformatted_ssn (ddddddddd 中尋找未格式化為九個連續數位的2011後主旨 ssn) 

### <a name="checksum"></a>總和檢查碼

否


### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_ssn 找到符合模式的內容。
- 會找到來自 Keyword_ssn 的關鍵字。

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_unformatted_ssn 找到符合模式的內容。
- 會找到來自 Keyword_ssn 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
- 函數 Func_randomized_formatted_ssn 找到符合模式的內容。
- 會找到來自 Keyword_ssn 的關鍵字。

DLP 原則在接近300個字元以內時，偵測到此敏感資訊類型的信賴度很低：
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

- SSA 編號
- 社會安全號碼
- 社會保障#
- 社會保障#
- 社會安全性否
- 社會保障#
- Soc Sec
- Ssn
- 主旨 SSN
- Ssn#
- 秒#
- Ssid

## <a name="us--uk-passport-number"></a>美國/英國 護照號碼

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數位

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型：
- 函數 Func_usa_uk_passport 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_uk_eu_passport_number` 。
- 找到來自的關鍵字 `Keywords_eu_passport_date`

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- 函數 Func_usa_uk_passport 找到符合模式的內容。
- `Keywords_eu_passport_number`找到或的關鍵字 `Keywords_uk_eu_passport_number` 。

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照否
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- 英屬護照
- 英國護照


## <a name="ukraine-passport-domestic"></a>烏克蘭護照（國內）
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- Regex Regex_Ukraine_Passport_Domestic 找到符合模式的內容。
- 會找到來自 Keyword_Ukraine_Passport_Domestic 的關鍵字。

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- 烏克蘭護照
- 護照號碼
- 護照否
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>烏克蘭護照（國際）
此機密資訊類型僅可用於下列專案：
- 資料遺失防護原則
- 通訊相容性原則
- 資訊管理
- 記錄管理
- Microsoft cloud app security

### <a name="format"></a>格式

八個字元的數位元格式

### <a name="pattern"></a>模式

八個字元的字母數位樣式：
- 兩個字母或數位
- 六位數

### <a name="checksum"></a>總和檢查碼

否

### <a name="definition"></a>定義

當鄰近性300個字元以內時，DLP 原則就會偵測到這種敏感資訊類型的信賴度。
- Regex Regex_Ukraine_Passport_International 找到符合模式的內容。
- 會找到來自 Keyword_Ukraine_Passport_International 的關鍵字。

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- 烏克蘭護照
- 護照號碼
- 護照否
- паспорт України
- номер паспорта
