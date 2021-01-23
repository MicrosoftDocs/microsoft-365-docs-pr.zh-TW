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
description: 安全性合規性 (DLP) 中，含有 80 種現成的敏感性資訊類型，可供您用於 &amp; DLP 策略。 本主題列出所有這些敏感性資訊類型，並說明 DLP 在偵測到每種類型時，會尋找什麼 DLP 規則。
ms.openlocfilehash: b70f335fd0742e6bc34957058c6e695530e83507
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927126"
---
# <a name="sensitive-information-type-entity-definitions"></a>敏感資訊類型實體定義

敏感性資訊類型是由正則運算式或函數可以識別的模式所定義。 此外，關鍵字和檢查器等明確辨識項可用來識別敏感性資訊類型。 信賴等級和鄰近程度也會用於評估程式。

敏感性資訊類型需要以下其中一種訂閱：
- Microsoft 365 E3
- Microsoft 365 E5

敏感性資訊類型用於：

- [資料外洩防護原則](data-loss-prevention-policies.md) 
- [敏感性標籤](sensitivity-labels.md)
- [保留標籤](retention.md)
- [通訊合規性](communication-compliance.md)
- [自動標籤策略](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="aba-routing-number"></a>ABA 路由號碼

### <a name="format"></a>格式

九位數，可能是格式已格式化或未格式化的圖樣

### <a name="pattern"></a>模式

格式 化：
- 以 0、1、2、3、6、7 或 8 開頭的四位數
- 連字號
- 四位數
- 連字號
- 一位數

未格式化：以 0、1、2、3、6、7 或 8 為開頭的九個連續數位 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

如果接近 300 個字元時，有一個策略會中信賴地偵測到這類敏感性資訊：
- 函數函數Func_aba_routing找到符合模式的內容。
- 系統找到Keyword_ABA_Routing關鍵字。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數函數Func_aba_routing找到符合模式的內容。

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

- aba number
- 阿壩#
- 阿壩
- abarouting#
- abaroutingnumber
- americanbankassociationrouting#
- americanbankassociationroutingnumber
- bankrouting#
- bankroutingnumber
- 路由#
- 路由否
- 路由號碼
- 路由傳輸號碼
- 路由#
- RTN


## <a name="argentina-national-identity-dni-number"></a>阿根廷國家/ (身分識別) 號碼

### <a name="format"></a>格式

包含或不含句號的八位數

### <a name="pattern"></a>模式

八位數：
- 兩位數
- 選擇性期間
- 三位數
- 選擇性期間
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
- cedula 
- cédula 
- dni 
- documento nacional de identidad 
- documento número 
- documento numero 
- registro nacional de las 角色 
- rnp 
   
## <a name="australia-bank-account-number"></a>澳大利亞銀行帳戶號碼

### <a name="format"></a>格式

包含或不含銀行州分行號碼的六到十位數

### <a name="pattern"></a>模式

帳號是 6 到 10 位數。

澳洲銀行州分行號碼：
- 三位數 
- 連字號 
- 三位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會Regex_australia_bank_account_number找到符合模式的內容。
- 系統找到Keyword_australia_bank_account_number關鍵字。
- 正則運算式會Regex_australia_bank_account_number_bsb找到符合模式的內容。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_australia_bank_account_number找到符合模式的內容。
- 系統找到Keyword_australia_bank_account_number關鍵字。

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
- 通訊銀行
- 基礎貨幣
- usa account
- 擁有者位址
- 銀行位址
- 資訊帳戶
- 資金轉帳
- 銀行費用
- 銀行詳細資料
- 銀行資訊
- 全名
- 國際 原子能 機構

## <a name="australia-business-number"></a>澳大利亞商務號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性


### <a name="format"></a>格式

11 位數與選擇性分隔符號

### <a name="pattern"></a>模式

11 位數與選擇性分隔符號：

- 兩位數
- 選擇性的連字號或空格
- 三位數
- 選擇性的連字號或空格
- 三位數
- 選擇性的連字號或空格
- 三位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數Func_australian_business_number找到符合模式的內容。
- 系統找到Keywords_australian_business_number關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數Func_australian_business_number找到符合模式的內容。

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

- 澳大利亞商務否
- 公司號碼
- 荷蘭#
- businessid#
- 商務識別碼
- 荷蘭
- businessno#

## <a name="australia-company-number"></a>澳大利亞公司編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

包含分隔符號的九位數

### <a name="pattern"></a>模式

包含分隔符號的九位數：

- 三位數
- 一個空格
- 三位數
- 一個空格
- 三位數


### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_Australian_Company_Number找到符合模式的內容。
- 系統找到Keyword_Australian_Company_Number關鍵字。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數函數Func_Australian_Company_Number找到符合模式的內容。

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
- 澳大利亞公司否
- 澳大利亞公司否#
- 澳大利亞公司編號
- 澳洲公司否
- 澳洲公司否#
- 澳洲公司編號

## <a name="australia-drivers-license-number"></a>澳大利亞駕照編號

### <a name="format"></a>格式

九個字母和數位

### <a name="pattern"></a>模式

九個字母和數位： 

- 兩位數或兩個字母 (不區分大小寫)  
- 兩位數 
- 五位數或五位數的字母 (大小寫不區分) 

OR

- 選擇一到兩個不區分大小寫 (字母)  
- 四到九位數

OR

- 九位數或九位數的字母 (不區分大小寫) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_australia_drivers_license_number找到符合模式的內容。
- 系統找到Keyword_australia_drivers_license_number關鍵字。
- 找不到來自Keyword_australia_drivers_license_number_exclusions關鍵字。

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

- 國際駕駛許可
- 澳洲汽車協會
- 國際駕駛許可
- DriverLicence
- DriverLicences
- 驅動程式許可證
- 駕照
- 駕照
- DriversLic
- DriversLicence
- DriversLicences
- 驅動程式 Lic
- 驅動程式 Lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 駕照
- 驅動程式 SLic
- 驅動程式 SLics
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 駕照
- DriverLic#
- DriverLics#
- DriverLicence#
- DriverLicences#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 駕照#
- DriversLic#
- DriversLics#
- DriversLicence#
- DriversLicences#
- 驅動程式 Lic#
- 驅動程式 Lics#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 駕照#
- 驅動程式 SLic#
- 驅動程式 SLics#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 駕照# 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- Aaa
- DriverLicense
- 驅動程式許可證
- 駕照
- 驅動程式授權
- DriversLicense
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式授權
- 駕照
- 驅動程式授權
- 驅動程式的許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- DriverLicense#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- DriversLicense#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式授權#
- 驅動程式的許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
   
## <a name="australia-medical-account-number"></a>澳大利亞醫療帳戶號碼

### <a name="format"></a>格式

10-11 位數

### <a name="pattern"></a>模式

10-11 位數：
- 第一個數位的範圍為 2-6
- 第九位數是一個檢查數位
- 十位數是問題位數
- 第 11 (選擇性) 是個別數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_australian_medical_account_number找到符合模式的內容。
- 系統找到Keyword_Australia_Medical_Account_Number關鍵字。
- 會傳遞檢查和。


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
- 已扣款
- 貸款帳戶
- 銀行付款
- 資訊分支
- 信用卡貸款
- 人力服務部門
- 當地服務
- 醫療

   
## <a name="australia-passport-number"></a>澳洲護照號碼

### <a name="format"></a>格式

字母后面接著七位數

### <a name="pattern"></a>模式

字母 (不區分大小寫) 後接七位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_australia_passport_number模式的內容。
- 系統找到Keyword_passport或Keyword_australia_passport_number關鍵字。

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
- 護照號碼
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
- 傳遞 n °
- Passeport Non
- 傳遞區#
- 傳遞區#
- PasseportNon
- 傳遞區 °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- 護照
- 護照詳細資料
- 好 <2> <2> <3>和 <2> <2> <3> <3>
- 澳大利亞的百分位
- 發自家的部門
- 位址
- 居住和 <3> <2>的部門
- 簽證
- 身分識別卡
- 護照號碼
- 旅遊檔
- 發行授權
   
## <a name="australia-tax-file-number"></a>澳大利亞稅務檔案編號

### <a name="format"></a>格式

八到九位數

### <a name="pattern"></a>模式

8 到 9 位數通常以空格表示，如下所示：
- 三位數 
- 一個選擇性空格 
- 三位數 
- 一個選擇性空格 
- 最後一個數位是檢查數位的 2 到 3 位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_australian_tax_file_number找到符合模式的內容。
- 找不到來自Keyword_Australia_Tax_File_Number或Keyword_number_exclusions關鍵字。
- 會傳遞檢查和。

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

- 澳洲商務號碼
- 營業稅稅率
- 已發還
- 產品群組編號
- 服務需要
- 營業稅
- 個別稅金退回
- 稅務檔案編號
- tfn

## <a name="austria-drivers-license-number"></a>奧地利駕照編號

### <a name="format"></a>格式

不含空格和分隔符號的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
  
- 正則運算式會  `Regex_austria_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_austria_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver s_license_number

- 朘朘
- führerschein
- Führersine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>奧地利身分識別卡
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

字母、數位和特殊字元的 24 個字元組合
  
### <a name="pattern"></a>模式

24 個字元：
  
-  22 個字母 (不區分大小寫) 數位、數位、反斜線、斜線或加號 
    
- 兩個字母 (不區分大小寫) 數位、數位、反斜線、斜線、加號或等號
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
  
- 正則運算式會  `Regex_austria_eu_national_id_card` 尋找符合模式的內容。 
- 找到關鍵字  `Keywords_austria_eu_national_id_card` 。 
   
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
- 國名
- personalaus您用 österreich

## <a name="austria-passport-number"></a>奧地利護照號碼

### <a name="format"></a>格式

一個字母，後面接著一個選擇性空格和七位數
  
### <a name="pattern"></a>模式

一個字母、七位數和一個空格的組合：
  
- 一個字母 (不區分大小寫) 
- 一個空格 (選填) 
- 七位數
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_austria_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_austria_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date1` 尋找 DD.MM.YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_austria_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_austria_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- Reisepasse
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe


## <a name="austria-social-security-number"></a>奧地利社會安全號碼

### <a name="format"></a>格式

指定格式的 10 位數
  
### <a name="pattern"></a>模式

10 位數：
  
- 對應至序號的三位數 
- 一個檢查數位
- 這是對應到 DD一Y (的六位數) 
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_austria_eu_ssn_or_equivalent` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_austria_eu_ssn_or_equivalent` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_austria_eu_ssn_or_equivalent` 會尋找符合模式的內容。 
    
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

- 美國
- ehic number
- ehic no
- 保險代碼
- insurancecode#
- 保險號碼
- 無保險
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno#
- 社會安全否
- 社會安全號碼
- 社會安全碼
- sozialversicherungsnummer
- sozialversicherungsnummer#
- Soziale sicherheit kein
- sozialesicherheitkein#
- Ssn#
- Ssn
- versicherungscode
- versicherungsnummer
- zdravs使用 zavarovanje

## <a name="austria-tax-identification-number"></a>奧地利稅務識別編號

### <a name="format"></a>格式

九位數及選擇性的連字號和斜線
  
### <a name="pattern"></a>模式

九位數以及選擇性的連字號和斜線：
  
- 兩位數
- 連字號或 (選) 
- 三位數
- 斜線 (選填) 
- 四位數
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_austria_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_austria_eu_tax_file_number` 。 
    
DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 此函數  `Func_austria_eu_tax_file_number` 會尋找符合模式的內容。 
    
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
- sterernummer
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#
- 稅號
 
## <a name="austria-value-added-tax"></a>奧地利的加值稅
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

11 個字元的字母數位元模式

### <a name="pattern"></a>模式

11 個字元的字母數位元模式：

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

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_Austria_Value_Added_Tax找到符合模式的內容。
- 系統找到Keyword_Austria_Value_Added_Tax關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_Austria_Value_Added_Tax找到符合模式的內容。

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

- 加值稅 編號
- 加值稅#
- 營業稅編號
- vat no.
- vatno#
- 加值稅編號
- 營業稅
- st
- umsatzststernummer
- <2>stnummer
- ust.-identifidentationsnummer
- umsatzstationer-identifidentationsnummer
- 加值稅 識別碼
- atu number
- uid 數位


## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB 驗證金鑰

### <a name="format"></a>格式

字串 "DocumentDb"，後面接著下圖中概述的字元和字串。

### <a name="pattern"></a>模式

- 字串 "DocumentDb"
- 3-200 個上下字母、數位、符號、特殊字元或空格之間的任何組合
- 大於符號 (>) 、等號 (=) 、引號 (") 或單引號 (') 
- 由 86 個小寫或大寫字母、數位、斜線 (/) 或加號 (+) 
- 兩個等號 (=) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會CEP_Regex_AzureDocumentDBAuthKey找到符合模式的內容。
- 正則運算式 **CEP_CommonExampleKeywords找不到符合** 模式的內容。

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

 (請注意，就技術上來說，這種敏感性資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。) 

- contoso
- fabrikam
- 北風
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure KMS 資料庫連接字串和 Azure SQL 連接字串

### <a name="format"></a>格式

字串 "Server"、"server" 或 "data source"，後面接著下面模式所述的字元和字串，包括字串 "cloudapp.azure"。<!--no-hyperlink-->com" 或 "cloudapp.azure"。<!--no-hyperlink-->net" 或 "database.windows"。<!--no-hyperlink-->net"，以及字串 "Password" 或 "password" 或 "pwd"。

### <a name="pattern"></a>模式

- 字串 "Server"、"server" 或 "資料來源"
- 0 到 2 個空白字元
- 等號 (=) 
- 0 到 2 個空白字元
- 1-200 個上下字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "cloudapp.azure.<!--no-hyperlink-->com"， "cloudapp.azure.<!--no-hyperlink-->net" 或 "database.windows"。<!--no-hyperlink-->net"
- 1-300 個小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "Password"、"password" 或 "pwd"
- 0 到 2 個空白字元
- 等號 (=) 
- 0 到 2 個空白字元
- 一或多個不是分號 (;) 、引號 (") 或單引號 (') 
- 分號 (;) 、引號 (") 或單引號 (') 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會CEP_Regex_AzureConnectionString模式的內容。
- 正則運算式 **CEP_CommonExampleKeywords找不到符合** 模式的內容。

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

 (請注意，就技術上來說，這種敏感性資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。) 

- contoso
- fabrikam
- 北風
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-iot-connection-string"></a>Azure IoT 連接字串

### <a name="format"></a>格式

字串 "HostName"，後面接著下圖中概述的字元和字串，包括字串 "azure-devices。<!--no-hyperlink-->net" 和 "SharedAccessKey"。

### <a name="pattern"></a>模式

- 字串 "HostName"
- 0 到 2 個空白字元
- 等號 (=) 
- 0 到 2 個空白字元
- 1-200 個上下字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "azure-devices"<!--no-hyperlink-->net"
- 1-200 個上下字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "SharedAccessKey"
- 0 到 2 個空白字元
- 等號 (=) 
- 0 到 2 個空白字元
- 由 43 個小寫或大寫字母、數位、斜線 (/) 或加號 (+) 
- 等號 (=) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會CEP_Regex_AzureIoTConnectionString找到符合模式的內容。
- 正則運算式 **CEP_CommonExampleKeywords找不到符合** 模式的內容。

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

 (請注意，就技術上來說，這種敏感性資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。) 

- contoso
- fabrikam
- 北風
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-publish-setting-password"></a>Azure 發佈設定密碼

### <a name="format"></a>格式

字串 "userp="，後面接著一個 Alphanumer 字串。

### <a name="pattern"></a>模式

- 字串 "userp輸入="
- 60 個小寫字母或數位的任何組合
- 引號 (") 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會CEP_Regex_AzurePublishSettingPasswords找到符合模式的內容。
- 正則運算式 **CEP_CommonExampleKeywords找不到符合** 模式的內容。


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

 (請注意，就技術上來說，這種敏感性資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。) 

- contoso
- fabrikam
- 北風
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-redis-cache-connection-string"></a>Azure Redis 緩存連接字串

### <a name="format"></a>格式

字串 "redis.cache.windows.<!--no-hyperlink-->net"，後面接著下圖中概述的字元和字串，包括字串 "password" 或 "pwd"。

### <a name="pattern"></a>模式

- 字串 "redis.cache.windows"。<!--no-hyperlink-->net"
- 1-200 個上下字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "password" 或 "pwd"
- 0 到 2 個空白字元
- 等號 (=) 
- 0 到 2 個空白字元
- 由 43 個字元組成的任何組合，包括小寫或大寫字母、數位、斜線 (/) 或加號 (+) 
- 等號 (=) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會CEP_Regex_AzureRedisCacheConnectionString找到符合模式的內容。
- 正則運算式 **CEP_CommonExampleKeywords找不到符合** 模式的內容。

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

 (請注意，就技術上來說，這種敏感性資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。) 

- contoso
- fabrikam
- 北風
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>格式

字串 "sig"，後面接著下圖中概述的字元和字串。

### <a name="pattern"></a>模式

- 字串 "sig"
- 0 到 2 個空白字元
- 等號 (=) 
- 0 到 2 個空白字元
- 任何由 43-53 個字元到小寫或大寫字母、位數或百分比符號的組合 (%) 
- 字串 "%3d"
- 非小寫或大寫字母、數位或百分比符號的任何字元 (%) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會CEP_Regex_AzureSAS找到符合模式的內容。

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure 服務行連接字串

### <a name="format"></a>格式

字串 "EndPoint"，後面接著下圖中概述的字元和字串，包括字串 "servicebus.windows"。<!--no-hyperlink-->net" 和 "SharedAccesKey"。

### <a name="pattern"></a>模式

- 字串 "EndPoint"
- 0 到 2 個空白字元
- 等號 (=) 
- 0 到 2 個空白字元
- 1-200 個上下字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "servicebus.windows"。<!--no-hyperlink-->net"
- 1-200 個上下字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "SharedAccessKey"
- 0 到 2 個空白字元
- 等號 (=) 
- 0 到 2 個空白字元
- 由 43 個字元組成的任何組合，包括小寫或大寫字母、數位、斜線 (/) 或加號 (+) 
- 等號 (=) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會CEP_Regex_AzureServiceBusConnectionString找到符合模式的內容。
- 正則運算式 **CEP_CommonExampleKeywords找不到符合** 模式的內容。

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

 (請注意，就技術上來說，這種敏感性資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。) 

- contoso
- fabrikam
- 北風
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-storage-account-key"></a>Azure 儲存體帳戶金鑰

### <a name="format"></a>格式

字串 "DefaultEndpointsProtocol"，後面接著下圖中概述的字元和字串，包括字串 "AccountKey"。

### <a name="pattern"></a>模式

- 字串 "DefaultEndpointsProtocol"
- 0 到 2 個空白字元
- 等號 (=) 
- 0 到 2 個空白字元
- 1-200 個上下字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "AccountKey"
- 0 到 2 個空白字元
- 等號 (=) 
- 0 到 2 個空白字元
- 由 86 個字元組成的任何組合，包括小寫或大寫字母、數位、斜線 (/) 或加號 (+) 
- 兩個等號 (=) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會CEP_Regex_AzureStorageAccountKey找到符合模式的內容。
- 正則運算式 **CEP_AzureEmulatorStorageAccountFilter找不到符合** 模式的內容。
- 正則運算式 **CEP_CommonExampleKeywords找不到符合** 模式的內容。

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

 (請注意，就技術上來說，這種敏感性資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。) 

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVEr為4I6tq/K1SZFPTOtr/KBHBeksoGWGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (請注意，就技術上來說，這種敏感性資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。) 

- contoso
- fabrikam
- 北風
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="azure-storage-account-key-generic"></a>Azure 儲存體帳戶金鑰 (一般) 

### <a name="format"></a>格式

由 86 個英文小寫或大寫字母、數位、斜線 (/) 或加號 (+) 的任何組合，前面或後面接著下列模式所概述的字元。

### <a name="pattern"></a>模式

- 零到大於符號 (>) 、單引號 (') 、等號 (=) 、引號 (") 或數位記號 (#) 
- 由 86 個字元組合成小寫或大寫字母、位數、斜線 (/) 或加號 (+) 
- 兩個等號 (=) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會CEP_Regex_AzureStorageAccountKeyGeneric找到符合模式的內容。

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>比利時駕照編號

### <a name="format"></a>格式

不含空格和分隔符號的十位數
  
### <a name="pattern"></a>模式

十位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_belgium_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自 `Keywords_eu_driver's_license_number` `Keywords_belgium_eu_driver's_license_number` 或找到。
    
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


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver s_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füehrerscheinnummer
- 朘朘
- 倌朘
- 朘
- 倌朘朘
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>比利時國號碼

### <a name="format"></a>格式

11 位數加上選擇性分隔符號

### <a name="pattern"></a>模式

11 位數加上分隔符號：
- 格式為 YY 的六位數和兩個選擇性的句號。MM.DD生日的輸入 
- 點、虛線、空格的選擇性分隔符號 
- 三個連續數位 (偶數時為奇數，即使是女性)  
- 點、虛線、空格的選擇性分隔符號 
- 兩個檢查數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_belgium_national_number找到符合模式的內容。
- 系統找到Keyword_belgium_national_number關鍵字。
- 會傳遞檢查和。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數函數Func_belgium_national_number找到符合模式的內容。
- 會傳遞檢查和。

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

- Belasting aantal
- 安娜#
- 安娜
- carte d'identité
- identifiant national
- identifiant一#
- identificatie
- 識別
- identifidentation
- identifidentationsnummer
- identifizierung
- identité
- identit在
- identit一sskaart
- 身份
- 題詞
- 國家/省/市號碼
- national register
- nationalnumber#
- nationalnumber
- Nif#
- Nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'méatriculation
- numéro national
- numéro一#
- 個人識別碼
- personalaus一s
- personalidnumber#
- registratie
- 註冊
- registrationsnumme
- registrierung
- 社會安全號碼
- Ssn#
- Ssn
- sterernummer
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#

## <a name="belgium-passport-number"></a>比利時護照號碼

### <a name="format"></a>格式

兩個字母后面接著沒有空格或分隔符號的六位數
  
### <a name="pattern"></a>模式

兩個字母，後面接著六位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

 DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_belgium_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_belgium_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date2` 尋找 DD MM YY 格式的日期，或找到 `Keywords_eu_passport_date` 或找到 `Keywords_belgium_eu_passport_number` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_belgium_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_belgium_eu_passport_number` 或找到。 

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
- 護照號碼
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
- 傳遞區笛卡
- 傳遞區
- Pass-Nr
- Passnummer
- 重新isepass kein


## <a name="belgium-value-added-tax-number"></a>比利時加值稅編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

12 個字元的字母數位元模式

### <a name="pattern"></a>模式

12 個字元的字母數位元模式：

- 字母 B 或 b
- 字母 E 或 e
- 一位數 0
- 從 1 到 9 的數位
- 選擇性的點、連字號或空格
- 四位數
- 選擇性的點、連字號或空格
- 四位數


### <a name="checksum"></a>校驗

是


### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_belgium_value_added_tax_number找到符合模式的內容。
- 系統找到Keywords_belgium_value_added_tax_number關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_belgium_value_added_tax_number找到符合模式的內容。

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

- n° tva
- 加值稅 編號
- 加值稅 否
- numéro t.v.a
- umsatzstationer-identifidentationsnummer
- umsatzststernummer
- 順便 說 一 句
- 順便 說 一 句#
- 加值稅#


## <a name="brazil-cpf-number"></a>巴西 CPF 號碼

### <a name="format"></a>格式

11 位數，包含一個檢查數位，而且可以格式化為未格式化

### <a name="pattern"></a>模式

格式 化：
- 三位數
- a period
- 三位數
- a period
- 三位數
- 連字號
- 兩位數是檢查數位

未格式化：
- 後兩位數是檢查位數的 11 位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_brazil_cpf找到符合模式的內容。
- 系統找到Keyword_brazil_cpf關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_brazil_cpf找到符合模式的內容。
- 會傳遞檢查和。

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
- 登錄
- 收入
- Cadastro de Pesicas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Rece您 

   
## <a name="brazil-legal-entity-number-cnpj"></a>巴西法律實體編號 (CNPJ) 

### <a name="format"></a>格式

14 位數，包含註冊號碼、分支號碼和檢查數位，以及分隔符號

### <a name="pattern"></a>模式

14 位數，加上分隔符號：

- 兩位數 
- a period 
- 三位數 
- a period 
- 前八 (的三位數是註冊號碼)  
- 斜線 
- 四位數分支號碼 
- 連字號 
- 兩位數是檢查數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_brazil_cnpj找到符合模式的內容。
- 系統找到Keyword_brazil_cnpj關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_brazil_cnpj找到符合模式的內容。
- 會傳遞檢查和。

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
- 法律實體的 National Registry 
- 稅務部註冊 
- 法律實體 
- 法律實體 
- 註冊狀態 
- Business 
- Company
- CNPJ 
- Cadastro Nacional da Pesso 在一起 
- Cadastro為 Contribuintes 
- CGC 
- Pes 有ídica 
- Pess 一一dicas 
- 卡薩 <7> <0> <5> <5> 
- Inscrição 
- 以髮卡達 

   
## <a name="brazil-national-identification-card-rg"></a>巴西國家識別卡 (RG) 

### <a name="format"></a>格式

Registro 提供九位數 (格式) ：九位數

Registro de Identidade (RIC)  (格式) ：11 位數

### <a name="pattern"></a>模式

Registro 提供 (格式) ：
- 兩位數 
- a period 
- 三位數 
- a period 
- 三位數 
- 連字號 
- 一位數是一個檢查數位

Registro de Identidade (RIC)  (格式) ：
- 十位數 
- 連字號 
- 一位數是一個檢查數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_brazil_rg找到符合模式的內容。
- 系統找到Keyword_brazil_rg關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_brazil_rg找到符合模式的內容。
- 會傳遞檢查和。

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
- 國名 
- número de rreútro
- registro de Iidentidade 
- registroal
- RG (此關鍵字會區分大小寫)  
- RIC (此關鍵字會區分大小寫)  


## <a name="bulgaria-drivers-license-number"></a>保加利亞駕照編號

### <a name="format"></a>格式

不含空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_bulgaria_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_bulgaria_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>保加利亞統一編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

不含空格和分隔符號的十位數
  
### <a name="pattern"></a>模式

不含空格和分隔符號的十位數
  
- 對應至 YYMMDD (的六位數)  
- 對應到出生日期的兩位數
- 對應到性別的一位數：男性的偶數和女性的奇數
- 一個檢查數位

### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_bulgaria_eu_national_id_card` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_bulgaria_eu_national_id_card` 。 

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_bulgaria_eu_national_id_card` 會尋找符合模式的內容。 
    
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
- 識別碼
- 國名
- 國家/省/市號碼
- nationalnumber#
- nationalnumber
- 個人識別碼
- 個人否
- 個人號碼
- personalidnumber#
- 社會安全號碼
- Ssn#
- Ssn
- 統一標準標準
- 統一標準否
- 統一標準號碼
- uniformcivilno#
- uniformcivilno
- uniformcivilnumber#
- uniformcivilnumber
- 唯一的唯一數位
- егн#
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униииори id
- униииорм граждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid#
- униформгражданскине.#


## <a name="bulgaria-passport-number"></a>保加利亞護照號碼

### <a name="format"></a>格式

不含空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_bulgaria_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_bulgaria_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date1` 尋找 DD.MM.YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_bulgaria_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_bulgaria_eu_passport_number` 或找到。 

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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日

## <a name="canada-bank-account-number"></a>加拿大銀行帳戶號碼

### <a name="format"></a>格式

7 位數或 12 位數

### <a name="pattern"></a>模式

加拿大銀行帳戶號碼為七位數或十二位數。

加拿大銀行帳戶轉場號碼為：
- 五位數 
- 連字號 
- 三位數 OR
- 零 "0" 
- 八位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會Regex_canada_bank_account_number找到符合模式的內容。
- 系統找到Keyword_canada_bank_account_number關鍵字。
- 正則運算式會Regex_canada_bank_account_transit_number找到符合模式的內容。

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會Regex_canada_bank_account_number找到符合模式的內容。
- 系統找到Keyword_canada_bank_account_number關鍵字。

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

- 加拿大儲蓄存款
- 加拿大營收機構
- 加拿大財務機構
- 直接存款表單
- 加拿大
- 法律代表
- 公證
- 公使者為的萬一
- 子女照護權益
- 通用托兒
- 加拿大子女稅金優惠
- 收入稅福利
- 營業稅
- 社會保險號碼
- 收入稅退款
- 子女稅務優惠
- 付款金額
- 機構號碼
- 存款要求
- 銀行資訊
- 直接存款

   
## <a name="canada-drivers-license-number"></a>加拿大駕照編號

### <a name="format"></a>格式

因省/市而異

### <a name="pattern"></a>模式

各種圖樣涵蓋埃布達、英屬哥倫比亞、曼尼托巴、新伯倫多、紐芬蘭/拉拉多文、新聖科提亞、安地卡、布吉納法索、魁北克及哈克圖萬

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數 Func_[province_name]_drivers_license_number找到符合模式的內容。
- 系統找到 Keyword_[province_name]_drivers_license_name關鍵字。
- 系統找到Keyword_canada_drivers_license關鍵字。

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

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- 省縮寫，例如 AB
- 省名稱，例如 Alberta

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- Dl
- Dls
- 民盟
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- 驅動程式許可證
- DriverLicence
- DriverLicences
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- 驅動程式許可證
- 驅動程式 Lic
- 驅動程式 Lics
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 SLic
- 驅動程式 SLics
- 驅動程式的許可證
- 驅動程式的許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Permis de Conduire
- id
- Id
- idcard number
- 識別碼
- idcard#
- idcard #s
- idcard card
- idcard cards
- idcard
- 識別碼
- 識別碼
- 識別#
- 識別#s
- 識別卡
- 身份證
- 識別 
- Dl#
- Dls# 
- 民盟# 
- CDLS# 
- DriverLic# 
- DriverLics# 
- DriverLicense# 
- 驅動程式許可證# 
- DriverLicence# 
- DriverLicences# 
- 驅動程式許可證#
- 驅動程式許可證# 
- 駕照# 
- 驅動程式授權# 
- 駕照# 
- 駕照# 
- DriversLic# 
- DriversLics# 
- DriversLicense# 
- 驅動程式許可證# 
- DriversLicence# 
- DriversLicences# 
- 驅動程式 Lic# 
- 驅動程式 Lics# 
- 驅動程式授權# 
- 驅動程式授權# 
- 驅動程式授權# 
- 驅動程式授權# 
- 驅動程式許可證# 
- 驅動程式許可證# 
- 駕照# 
- 驅動程式授權# 
- 駕照# 
- 駕照# 
- 驅動程式許可證# 
- 驅動程式許可證# 
- 駕照# 
- 驅動程式授權# 
- 駕照# 
- 駕照# 
- 驅動程式 SLic# 
- 驅動程式 SLics# 
- 驅動程式的許可證# 
- 驅動程式的許可證# 
- 驅動程式許可證# 
- 驅動程式許可證# 
- 驅動程式許可證# 
- 驅動程式的許可證# 
- 駕照# 
- 驅動程式授權# 
- 駕照# 
- 駕照# 
- Permis de Conduire# 
- Id# 
- Id# 
- idcard card# 
- idcard cards# 
- idcard# 
- 識別卡# 
- 身份證# 
- 識別# 

   
## <a name="canada-health-service-number"></a>加拿大健康服務編號

### <a name="format"></a>格式

十位數

### <a name="pattern"></a>模式

十位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_canada_health_service_number找到符合模式的內容。
- 系統找到Keyword_canada_health_service_number關鍵字。

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
- 病患資訊
- 健康服務
- 特殊服務
- 汽車意外
- 病患醫院
- 心理醫生
- 工作者補償
- 殘疾

      
## <a name="canada-passport-number"></a>加拿大護照號碼

### <a name="format"></a>格式

兩個大寫字母，後面接著六位數

### <a name="pattern"></a>模式

兩個大寫字母，後面接著六位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_canada_passport_number找到符合模式的內容。
- 系統找到Keyword_canada_passport_number或Keyword_passport關鍵字。

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

- 加拿大居民
- 加拿大護照
- 護照申請
- 護照相片
- 通過認證的翻譯工具
- 加拿大居民
- 處理時間
- 續約應用程式

#### <a name="keyword_passport"></a>Keyword_passport

- 護照號碼
- 護照號碼
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
- 傳遞 n °
- Passeport Non
- 傳遞區#
- 傳遞區#
- PasseportNon
- 傳遞區 °

   
## <a name="canada-personal-health-identification-number-phin"></a>加拿大個人健康識別號碼 (PHIN) 

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_canada_phin找到符合模式的內容。
- 系統至少找到兩Keyword_canada_phin或Keyword_canada_provinces關鍵字。

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

- 社會保險號碼
- 健康資訊法案
- 營業稅資訊
- manitoba health
- 健康註冊
- 購買專案
- 權益資格
- 個人健康
- 律師權
- 註冊號碼
- 個人健康號碼
- 普通推薦
- 健康專業
- 病患推薦
- 健康

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- 圖拉維特
- 魁北克
- 西北領地省
- 安大略省
- 不列顛哥倫比亞省
- 阿爾比省
- 薩斯喀徹爾省
- 馬尼托巴省
- 育 空
- 紐芬蘭及拉布拉多省
- 新不倫瑞克省
- 新斯科舍省
- 艾德華王子島
- 加拿大

   
## <a name="canada-social-insurance-number"></a>加拿大社會保險號碼

### <a name="format"></a>格式

九位數以及選擇性的連字號或空格

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

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_canadian_sin找到符合模式的內容。
- 至少兩者的任意組合：
    - 系統找到Keyword_sin關鍵字。
    - 系統找到Keyword_sin_collaborative關鍵字。
    - 函數Func_eu_date尋找正確日期格式的日期。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_unformatted_canadian_sin找到符合模式的內容。
- 系統找到Keyword_sin關鍵字。
- 會傳遞檢查和。

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
- 社會保險 
- numero d'assurance sociale 
- 罪 
- Ssn 
- ssns 
- 社會保障 
- numero d'assurance social 
- 國家識別號碼 
- 國名 
- 罪# 
- soc ins 
- 社交資訊 

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- 駕照 
- 驅動程式授權 
- 駕照 
- 驅動程式授權 
- DOB 
- 出生日期 
- 生日 
- 出生日期 

   
## <a name="chile-identity-card-number"></a>智利身分識別卡號碼

### <a name="format"></a>格式

七到八位數加上分隔符號以檢查數位或字母

### <a name="pattern"></a>模式

七到八位數加上分隔符號：
- 一到兩位數 
- 選擇性期間 
- 三位數 
- 選擇性期間 
- 三位數 
- 破折號 
- 一位數或一個字母 (不區分大小寫) 這是一個檢查數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_chile_id_card找到符合模式的內容。
- 系統找到Keyword_chile_id_card關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_chile_id_card找到符合模式的內容。
- 會傳遞檢查和。

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
- 國家識別
- 國家識別號碼
- 國名
- número de identificación nacional
- rol único nacional
- rol único tribu在
- 運行
- 車轍
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tribu一
- 運行#
- 車轍#
- nationaluniqueroleID#
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- 未提供使用者身分識別。
- 身分識別號碼
- 身分識別#
- 唯一稅務註冊表
- 唯一的三方角色
- 唯一稅務角色
- 唯一的三方編號
- 唯一的國號碼
- 唯一的國內角色
- 國家唯一角色
- 智利身分識別否。
- 智利身分識別號碼
- 智利身分識別#

   
## <a name="china-resident-identity-card-prc-number"></a>中國居民身分證 (中國) 號碼

### <a name="format"></a>格式

18 位數

### <a name="pattern"></a>模式

18 位數：
- 六位數是一個位址代碼 
- YYYYMMDD 表單中的八位數，這是生日 
- 三位數即為訂單代碼 
- 一位數是一個檢查數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_china_resident_id找到符合模式的內容。
- 系統找到Keyword_china_resident_id關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_china_resident_id找到符合模式的內容。
- 會傳遞檢查和。

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

- 居住身分識別卡 
- 中國 
- 國家識別卡 
- 身份證 
- 居民 身份證 
- 居民身份證 
- 鑒定 
- 身分證 
- 居民 身份證
- 鑑定 

   
## <a name="credit-card-number"></a>信用卡號碼

### <a name="format"></a>格式

可格式化或未格式化的 14 到 16 位數 (ddddd) 且必須通過 Luhn 檢定。

### <a name="pattern"></a>模式

非常複雜且強大的模式可偵測全球所有主要品牌卡片，包括 Visa、MasterCard、Discover Card、JCB、American Express、禮品卡和快閃卡。

### <a name="checksum"></a>校驗

是，Luhn 檢查程式

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數Func_credit_card找到符合模式的內容。
- 下列其中一個條件成立：
    - 系統找到Keyword_cc_verification關鍵字。
    - 系統找到Keyword_cc_name關鍵字。
    - 函數Func_expiration_date尋找正確日期格式的日期。
- 會傳遞檢查和。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 此函數Func_credit_card找到符合模式的內容。
- 會傳遞檢查和。

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

- 卡片驗證
- 卡片識別號碼
- cvn
- cid
- cvc2
- cvv2
- 圖釘區塊
- 安全性驗證碼
- 安全性號碼
- 安全性否
- 問題編號
- 問題否
- 加密圖法
- numéro de sécurité
- numero de Securite
- kredittentenprüfnummer
- kredittenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- ver一datum
- codice di verifica
- Cod。 sicurezza
- cod sicurezza
- n autorizz一one
- cód一
- cod一
- Cod。 Seg
- cod seg
- cód一 de segurança
- cod一 de seguranca
- cod一 de segurança
- cód一 de seguranca
- cód. segurança
- Cod。 seguranca
- Cod。 segurança
- cód. seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gül在比斯
- gül一keitsdatum
- 加特比斯
- gultigkeitsdatum
- scadenza
- 資料 scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- 資料 de expiracao
- 資料 em que expira
- validade
- 勇氣
- vencimento
- 交易
- 交易號碼
- 參照編號
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番號

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- American Express
- americanexpress
- americano espresso
- 簽證
- 萬事 達
- 主卡片
- Mc
- 主卡
- 主卡
- 百萬人俱樂部
- <2> <3> <3>師俱樂部
- 百分位
- 發現
- 探索卡片
- discovercard
- 探索卡片
- JCB
- BrandSmart
- 日文卡片卡片
- carte blanche
- carteblanche
- 信用卡
- Cc#
- cc#：
- 有效期
- exp date
- 有效期
- 日期 d'expiration
- date d'exp
- 日期到期
- 銀行卡
- bankcard
- 卡號
- card num
- cardnumber
- cardnumbers
- 卡號
- creditcard
- 信用卡
- creditcards
- ccn
- 卡片盒
- 持 卡 人
- 卡片盒
- 持 卡 人
- 檢查卡
- checkcard
- 檢查卡片
- 檢查卡
- 轉帳卡
- 轉帳卡
- 轉帳卡
- 轉帳卡
- 卡
- 方便使用
- 卡
- 為卡
- enroute
- 途中
- 卡片類型
- Cardmember Acct
- Cardmember 帳戶
- Cardno
- 公司卡片
- 公司卡片
- 卡片類型
- 卡片帳戶號碼
- 卡片成員帳戶
- Cardmember Acct.
- 卡片號碼。
- 卡片否
- 卡號
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- n° de la carte
- n° de carte
- kredit功能
- karte
- kartenin使用er
- kartenin一ers
- kredittenin一一er
- kreditteninstitut
- kredittentyp
- eigentümername
- kartennr
- kartennummer
- kredittennummer
- kredit功能區-nummer
- carta di credito
- carta credito
- n. 憲章
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
- tarjeta de
- tarjeta
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- n° de tarjeta
- 不。 de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta 否
- tarjetaientiente
- cartão de créd使用
- cartão de credito
- créd之 cartao de créd之
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- n <7> do cartão
- n <7> do cartao
- n° do cartão
- 否，cartão
- 沒有 cartao
- 不。 do cartão
- 不。 do cartao
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
- Visa カード
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


## <a name="croatia-drivers-license-number"></a>克羅地卡駕照號碼

### <a name="format"></a>格式

不含空格和分隔符號的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
  
- 正則運算式會  `Regex_croatia_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自 `Keywords_eu_driver's_license_number` `Keywords_croatia_eu_driver's_license_number` 或找到。 

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver s_license_number

- voza以ka dozvola
- voza以ke dozvole


## <a name="croatia-identity-card-number"></a>克羅地亞身分識別卡號碼
此敏感性資訊類型實體包含在歐盟國家識別號碼敏感性資訊類型中，而且可做為獨立的敏感性資訊類型實體使用。

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_croatia_id_card找到符合模式的內容。
- 系統找到Keyword_croatia_id_card關鍵字。

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

- majstorski一j graanaana
- 主控號碼
- nacionalni identifikacijski一j
- 國家識別號碼
- oib#
- oib
- osobna iskaznica
- osobni 識別碼
- osobni identifikacijskiikajj
- 個人識別碼
- 一切由來
- identzni identifikacijskiikajj
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#


## <a name="croatia-passport-number"></a>克羅地亞護照號碼

### <a name="format"></a>格式

不含空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_croatia_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_croatia_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date1` 尋找 DD.MM.YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_croatia_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_croatia_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- 將j putov以
- Br。 Putov一
- br putov以
   
## <a name="croatia-personal-identification-oib-number"></a>克羅尼西亞 (OIB) 號碼

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

11 位數：
- 十位數 
- 最後一個數位是一個檢查數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_croatia_oib_number找到符合模式的內容。
- 系統找到Keywords_croatia_eu_tax_file_number關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_croatia_oib_number找到符合模式的內容。
- 會傳遞檢查和。

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

- majstorski一j graanaana
- 主控號碼
- nacionalni identifikacijski一j
- 國家識別號碼
- oib#
- oib
- osobna iskaznica
- osobni 識別碼
- osobni identifikacijskiikajj
- 個人識別碼
- 一切由來
- identzni identifikacijskiikajj
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#


## <a name="cyprus-drivers-license-number"></a>駕照編號

### <a name="format"></a>格式

不含空格和分隔符號的 12 位數
  
### <a name="pattern"></a>模式

12 位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_cyprus_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_cyprus_eu_driver's_license_number` 或找到。

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>身分識別卡
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

不含空格和分隔符號的十位數
  
### <a name="pattern"></a>模式

十位數 
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_cyprus_eu_national_id_card` 尋找符合模式的內容。 
- 找到關鍵字  `Keywords_cyprus_eu_national_id_card` 。 
    
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

- 識別碼卡號
- 身分識別卡號碼
- kim一 karti
- 國家識別號碼
- 個人識別碼
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>護照號碼

### <a name="format"></a>格式

一個字母，後面接著 6 到 8 位數，沒有空格或分隔符號
  
### <a name="pattern"></a>模式

一個字母后面接著六到八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_cyprus_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_cyprus_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_cyprus_eu_passport_date` 尋找 DD/MM/YYYY 格式的日期，或找到 `Keywords_cyprus_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_cyprus_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_cyprus_eu_passport_number` 或找到。  
    
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
- 護照號碼
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
- Pasaport Kimli以i
- pasaport nu使用s
- Pasaport no.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- 將于 2010 年 1 月
- 發行于


## <a name="cyprus-tax-identification-number"></a>賽普勒斯稅務識別號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

指定模式中八位數和一個字母
  
### <a name="pattern"></a>模式

八位數和一個字母：
  
- "0" 或 "9"
- 七位數
- 一個字母 (不區分大小寫) 
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_cyprus_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_cyprus_eu_tax_file_number` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_cyprus_eu_tax_file_number` 會尋找符合模式的內容。 
    
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

- 稅務識別碼
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- 旅遊業 議會#
- 旅遊業 議會
- tin id
- tin no
- 錫#
- vergi kim一 kodu
- vergi kim一 nu以s並
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>捷克駕照編號

### <a name="format"></a>格式

兩個字母后面接著六位數
  
### <a name="pattern"></a>模式

8 個字母和數位：
  
- 字母 'E' (不區分大小寫) 
- 一個字母
- 這是 (選項) 
- 六位數

### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_czech_republic_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_czech_republic_eu_driver's_license_number` 或找到。 

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver s_license_number

- ú一一sksk與 prúkaz
- ühri以ské pr並kazy
- ííslo ü一一skského prükazu
- íísla ü一一sksk用ch prükaz除


## <a name="czech-passport-number"></a>捷克文護照號碼

### <a name="format"></a>格式

不含空格或分隔符號的八位數
  
### <a name="pattern"></a>模式

不含空格或分隔符號的八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_czech_republic_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_czech_republic_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date1` 尋找 DD.MM.YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_czech_republic_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_czech_republic_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- ííslo pasu
- cestovní pasu
- 傳遞區否
- íísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="czech-personal-identity-number"></a>捷克文個人身分識別號碼

### <a name="format"></a>格式

九位數以及選擇性斜線 (舊格式) 十位數，以及新的格式 (斜線) 

### <a name="pattern"></a>模式

使用九位數 (舊格式) ：
- 代表生日的六位數
- 選擇性的斜線
- 三位數

使用新的 (格式的十) ：
- 代表生日的六位數
- 選擇性的斜線 
- 最後一個數位是檢查數位的四位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：

- 函數函數Func_czech_id_card找到符合模式的內容。
- 系統找到Keyword_czech_id_card關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：

- 函數函數Func_czech_id_card_new_format找到符合模式的內容。
- 會傳遞檢查和。

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

- 出生日期
- 捷克共和國識別碼
- czechidno#
- daé ííslo
- identifika以ní ííslo
- 身分識別否
- 身分識別號碼
- identityno#
- identityno
- 保險號碼
- 國家識別號碼
- nationalnumber#
- 國家/省/市號碼
- osobní ííslo
- personalidnumber#
- 個人識別碼
- 個人識別碼
- 個人號碼
- Pid#
- PID
- poji以t/ní ííslo
- r已
- nelo
- é ííslo
- Ssn
- Ssn#
- 社會安全號碼
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#
- 唯一標識號


## <a name="denmark-drivers-license-number"></a>丹麥駕照編號

### <a name="format"></a>格式

不含空格和分隔符號的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_denmark_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_denmark_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver s_license_number

- Kфrekort
- kфrekortnummer


## <a name="denmark-passport-number"></a>丹麥護照號碼

### <a name="format"></a>格式

不含空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_denmark_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_denmark_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date2` 尋找 DD MM YY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_denmark_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_denmark_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- 傳遞 n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="denmark-personal-identification-number"></a>丹麥個人識別碼

### <a name="format"></a>格式

包含連字號的十位數

### <a name="pattern"></a>模式

十位數：
- 格式 DD您用 6 位數表示生日 
- 連字號 
- 最後一個數位是檢查數位的四位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Func_denmark_eu_tax_file_number找到符合模式的內容。
- 系統找到Keyword_denmark_id關鍵字。
- 會傳遞檢查和。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 正則運算式會Func_denmark_eu_tax_file_number找到符合模式的內容。
- 會傳遞檢查和。

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
- gesundheitshete nummer
- gesundheitsversicherunghete nummer
- 健康卡
- 健康保險卡號碼
- 健康保險號碼
- 識別碼
- identifidentationsnummer
- identifidentationsnummer#
- 身分識別號碼
- krankenkassennummer
- nationalid#
- nationalnumber#
- 國家/省/市號碼
- personalidnumber#
- personalidentityno#
- 個人識別碼
- personnummer
- personnummer#
- reisekrankenversicherungstenummer
- rejsesygesskringskort
- Ssn
- Ssn#
- 滑冰識別碼
- 花式滑冰
- skat nummer
- skattenummer
- 社會安全號碼
- sundhedsforsskringskort
- sundhedsfors進一ringsnummer
- sundhedskort
- sundhedskortnummer
- sygesring
- sygesikringkortnummer
- 稅務代碼
- 旅遊保險卡
- uniqueidentityno#
- 稅號
- 稅務註冊編號
- 稅務識別碼
- 稅務識別編號
- 已刪除#
- taxnumber#
- 稅號
- taxno#
- taxnumber
- 稅務識別否
- 錫#
- 已發想#
- ，並#
- 稅號#
- tin id
- tin no
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesviringsbevis
- sygesviringsbevisnr
- sygesviringsbevisnummer
- sygesskringskort
- sygesskringskortnr
- sygesskringskortnummer
- sygesikringsnr
- syges進位snummer


## <a name="drug-enforcement-agency-dea-number"></a>國家調查 (安全) 號碼

### <a name="format"></a>格式

兩個字母后面接著七位數

### <a name="pattern"></a>模式

模式必須包含下列所有專案：
- 一個字母 (不區分大小寫) 一組可能字母：abcdefghjklmnprstux，這是一個註冊表代碼 
- 一個字母 (不區分大小寫) ，即為報名者姓氏或數位 '9' 的第一個字母
- 7 位數，最後一位是檢查數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_dea_number找到符合模式的內容。
- 找到 `Keyword_dea_number` 關鍵字
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_dea_number找到符合模式的內容。
- 會傳遞檢查和。

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
- 稅務強制執行系統
- 政策強制執行機關


## <a name="estonia-drivers-license-number"></a>愛沙尼亞駕照編號

### <a name="format"></a>格式

兩個字母后面接著六位數
  
### <a name="pattern"></a>模式

兩個字母和六位數：
  
- 字母 "ET" (不區分大小寫)  
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_estonia_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_estonia_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver s_license_number

-- permis de conduire
- juhi一adeade numbrid
- juhiloa 數位
- juhi一a


## <a name="estonia-personal-identification-code"></a>愛沙尼亞個人識別碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

不含空格和分隔符號的 11 位數
  
### <a name="pattern"></a>模式

11 位數：
  
- 一位數，對應到性別和一世紀 (奇數男性，偶數女性;1-2：19 世紀;3-4：20 世紀;5-6：21 世紀) 
- 對應至 YYMMDD (生日的六位數) 
- 對應至相同日期的序列值分隔人的三位數
- 一個檢查數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_estonia_eu_national_id_card` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_estonia_eu_national_id_card` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_estonia_eu_national_id_card` 會尋找符合模式的內容。 
    
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

- id-kaart
- 益
- isikukood#
- isikukood
- maksu 識別碼
- maksukohustuslase identifitseerimisnumber
- maksunumber
- 國家識別號碼
- 國家/省/市號碼
- 個人代碼
- 個人識別碼
- 個人識別碼
- 個人識別碼
- personalidnumber#
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#


## <a name="estonia-passport-number"></a>愛沙尼亞護照號碼

### <a name="format"></a>格式

一個字母后面接著沒有空格或分隔符號的七位數
  
### <a name="pattern"></a>模式

一個字母后面接著七位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_estonia_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_estonia_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date1` 尋找 DD.MM.YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_estonia_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_estonia_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku passi number passinumbrid 檔編號檔 no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="eu-debit-card-number"></a>歐盟轉帳卡號碼

### <a name="format"></a>格式

16 位數

### <a name="pattern"></a>模式

非常複雜且強大的模式

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_eu_debit_card找到符合模式的內容。
- 至少下列其中一個條件成立：
    - 系統找到Keyword_eu_debit_card關鍵字。
    - 系統找到Keyword_card_terms_dict關鍵字。
    - 系統找到Keyword_card_security_terms_dict關鍵字。
    - 系統找到Keyword_card_expiration_terms_dict關鍵字。
    - 函數Func_expiration_date尋找正確日期格式的日期。
- 會傳遞檢查和。

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

- 帳號 
- 卡號 
- 卡片號碼。 
- 安全性號碼 
- Cc# 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr 
- acct num 
- acct 否 
- American Express 
- americanexpress 
- americano espresso 
- amex 
- 卡 
- 卡 
- 為卡藝術特 
- 方便使用 
- 為卡 
- 縣/市 
- ·<2>kaarten 
- bancontact 
- 銀行卡 
- bankkaart 
- 卡片盒 
- 卡片盒 
- card num 
- 卡號 
- 卡號 
- 卡片類型 
- Card一 numerico 
- 持 卡 人 
- 持 卡 人 
- cardnumber 
- cardnumbers 
- carta bianca 
- carta credito 
- carta di credito 
- cartao de credito 
- créd之 cartao de créd之 
- cartao de debito 
- cartao de débito 
- carte bancaire 
- carte blanche 
- carte bleue 
- carte de credit 
- carte de crédit 
- carte di credito 
- carteblanche 
- cartão de credito 
- cartão de créd使用 
- cartão de debito 
- cartão de débito 
- cb 
- ccn 
- 檢查卡 
- 檢查卡片 
- checkcard
- 檢查卡 
- 您用的圖說是 
- 卷雲 
- cirrus-edc-maestro 
- controlekaart 
- Controlekten 
- 信用卡 
- 信用卡 
- creditcard 
- creditcards 
- debetkaart 
- debetkaarten 
- 轉帳卡 
- 轉帳卡 
- 轉帳卡 
- 轉帳卡 
- debito automatico 
- <2> <3> <3>師俱樂部 
- 百分位 
- 發現 
- 探索卡片 
- 探索卡片 
- discovercard 
- Discovercards 
- débito automático
- edc 
- eigentümername 
- 歐洲轉帳卡 
- hoofdkaart 
- hoofdkten 
- in viag以 
- 日文卡片卡片 
- japanse kaartdienst 
- jcb 
- kaart 
- kaart num 
- kaartaantal 
- kaartaantallen 
- kaarthouder 
- kaarthouders 
- karte  
- kartenin使用er 
- kartenin一ers
- kartennr 
- kartennummer 
- kredit功能 
- kredit功能區-nummer 
- kredittenin一一er 
- kreditteninstitut 
- kredittennummer 
- kredittentyp 
- 大師 
- 主卡片 
- 主卡 
- 萬事 達 
- 主卡 
- Mc 
- mister cash 
- n carta 
- 憲章 
- no de tarjeta 
- 沒有 cartao 
- 否，cartão 
- 不。 de tarjeta 
- 不。 do cartao 
- 不。 do cartão 
- nr carta 
- 星期日。 憲章 
- numeri di scheda 
- numero carta 
- numero de cartao 
- numero de carte 
- numero de cartão 
- numero de tarjeta
- numero della carta 
- numero di carta 
- numero di scheda 
- numero do cartao 
- numero do cartão 
- numéro de carte 
- n° carta 
- n° de carte 
- n° de la carte 
- n° de tarjeta 
- n <7> do cartao 
- n <7> do cartão 
- n° do cartão 
- número de cartao 
- número de cartão 
- número de tarjeta 
- número do cartao 
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
- 使用管理prono la scheda 
- 以 le schede 為名 
- 獨奏 
- supporti di scheda 
- supporto di scheda 
- 開關 
- tarjeta 
- tarjeta credito 
- tarjeta de 
- tarjeta de credito 
- tarjeta de debito 
- tarjeta debito 
- tarjeta 否
- tarjetaientiente 
- t scheda 
- ufficio giapponese della 
- scheda 
- v pay 
- v-pay 
- 簽證 
- visa plus 
- Visa visa visa 
- Visto 
- visum 
- vpay   

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- 卡片識別號碼
- 卡片驗證 
- cardi la verifica 
- cid 
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
- Cod。 Seg 
- Cod。 seguranca 
- Cod。 segurança 
- Cod。 sicurezza 
- codice di sicurezza 
- codice di verifica 
- cod一 
- cod一 de seguranca 
- cod一 de segurança 
- 長條圖 
- 密碼 
- 加密圖法 
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
- cód一 
- cód一 de seguranca 
- cód一 de segurança 
- de kaart controle 
- 可ft nr uit 
- 問題否 
- 問題編號 
- kaartidentificenummer 
- kredittenprufnummer 
- kredittentenprüfnummer 
- kwestieaantal 
- 不。 dell'edizione 
- 不。 di sicurezza 
- numero de Securite 
- numero de verificacao 
- numero dell'edizione 
- numero di identific一one della 
- scheda 
- numero di sicurezza 
- numero vanheid 
- numéro de sécurité 
- n <8> <8> autorizz一one 
- número de verificação 
- perno il到co 
- 圖釘區塊 
- prufziffer 
- prüfziffer 
- 安全性驗證碼 
- 安全性否 
- 安全性號碼 
- sicherheits kode 
- sicherheitscode 
- sicherheitsnummer 
- speldblok 
- 圲圼 nr 
- 湈圽特 
- idigheidscode 
- 渿圽嫁 
- ver一datum 

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf 
- 資料 de expiracao 
- data de expiração 
- 資料 del exp 
- 資料圼用 
- 資料 di scadenza 
- 資料 em que expira 
- 資料 scad 
- 資料za 
- date de validité 
- datum afloop 
- datum van exp 
- de afloop 
- espira 
- espira 
- exp date 
- exp datum 
- 到期 
- 到期 
- 到期 
- 屆滿 
- fecha de expiracion 
- fecha de venc 
- 加特比斯 
- gultigkeitsdatum 
- gül在比斯 
- gül一keitsdatum 
- la scadenza 
- scadenza 
- 可評估 
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


## <a name="eu-drivers-license-number"></a>歐盟駕照編號

這些是歐盟駕照編號敏感性資訊類型中的實體。

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


## <a name="eu-national-identification-number"></a>歐盟國家識別號碼

這些是歐盟國家識別號碼敏感性資訊類型中的實體。

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

這些是歐盟護照號碼敏感性資訊類型中的實體，是歐盟護照號碼組合中的實體。

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


## <a name="eu-social-security-number-or-equivalent-identification"></a>歐盟社會安全號碼或同等的識別

這些是歐盟社會安全號碼或等同的識別敏感性資訊類型中的實體。

- [奧地利](#austria-social-security-number)
- [比利時](#belgium-national-number)
- [克羅埃西亞](#croatia-personal-identification-oib-number)
- [捷克文](#czech-personal-identity-number)
- [丹麥](#denmark-personal-identification-number)
- [芬蘭](#finland-national-id)
- [法國](#france-social-security-number-insee-or-equivalent-identification)
- [德國](#germany-identity-card-number)
- [希臘](#greece-national-id-card)
- [匈牙利](#hungary-social-security-number-taj)
- [葡萄牙](#portugal-citizen-card-number)
- [西班牙](#spain-social-security-number-ssn)
- [瑞典](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>歐盟稅務識別編號

這些實體為歐盟稅務識別碼敏感性資訊類型。

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

包含連字號的十位數和字母
  
### <a name="pattern"></a>模式

包含連字號的十位數和字母：
  
- 六位數 
- 連字號
- 三位數 
- 數位或字母
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_finland_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_finland_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- Kuljettaja lic.
- Körkort
- Körkortnummer
- fö一e lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>芬蘭歐洲健康保險號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

20 位數號碼

### <a name="pattern"></a>模式

20 位數號碼：

- 十位數 - 8024680246
- 選擇性空格或連字號
- 十位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- RegEx 索引Regex_Finland_European_Health_Insurance_Number找到符合模式的內容。
- 系統找到Keyword_Finland_European_Health_Insurance_Number關鍵字。

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
- 健康卡
- 健康保險卡
- 健康保險號碼
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- s一smen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>芬蘭國識別碼

### <a name="format"></a>格式

六位數加上一個字元，表示一世紀加上三位數加上一個檢查數位

### <a name="pattern"></a>模式

模式必須包含下列所有專案：
- 格式 DD有 6 位數是生日的 DD一 
- century 標記 ('-'、'+' 或 'a')  
- 三位數個人識別碼 
- 這是一個 (大小寫不區分) 數位或字母

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_finnish_national_id尋找符合模式的內容
- 找到您Keyword_finnish_national_id關鍵字
- 檢查和傳遞

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_finnish_national_id尋找符合模式的內容
- 檢查和傳遞

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

- ainutlaatuinen henkilökohtainen Tunnus
- henkilökohtainen Tunnus
- henkilö一nus
- henkilö一點nusnumero#
- henkilö一點nusnumero
- hetu
- 識別碼否
- 識別碼
- 識別碼
- identite以numero
- 身分識別號碼
- idnumber
- 使用一些
- ilisen henkilökortin
- 國家/a0
- 國家/a0> 號碼。
- 個人識別碼
- 個人身分識別碼
- personalidnumber#
- personbeteckning
- personnummer
- 社會安全號碼
- so一aliturva一nus
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#
- Tunnistenumero
- Tunnus numero
- Tunnusl一
- tunnusnumero
- verokortti
- veronumero
- vero一niste
- vero一nunus


## <a name="finland-passport-number"></a>芬蘭護照號碼

### <a name="format"></a>格式
九個字母和數位的組合

### <a name="pattern"></a>模式
九個字母和數位的組合：
- 兩個字母 (不區分大小寫)  
- 七位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_finland_passport_number找到符合模式的內容。
- 系統找到Keywords_eu_passport_number_common或Keyword_finland_passport_number關鍵字。

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keyword_finland_passport_number" />
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suoma一en passi
- Passin numero
- passin numero.#
- Passin numero#
- passin numero.
- Passi#
- Passi 號碼


## <a name="france-drivers-license-number"></a>法國駕照編號

### <a name="format"></a>格式

12 位數

### <a name="pattern"></a>模式

12 位數與驗證以折扣類似模式 ，例如法文電話號碼

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_french_drivers_license找到符合模式的內容。
- 找到您Keyword_french_drivers_license關鍵字。

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

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number
- permis de conduire
- 授權號碼
- 授權號碼
- 授權號碼
- 授權號碼
- numéros de licence


## <a name="france-health-insurance-number"></a>法國健康保險號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

21 位數號碼

### <a name="pattern"></a>模式

21 位數號碼：

- 十位數
- 一個選擇性空格
- 十位數
- 一個選擇性空格
- 一位數


### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- RegEx Regex_France_Health_Insurance_Number找到符合模式的內容。
- 找到您Keyword_France_Health_Insurance_Number關鍵字。

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
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>法國國家/ (資訊) 

### <a name="format"></a>格式

12 位數

### <a name="pattern"></a>模式

12 位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 正則運算式會Regex_france_cni找到符合模式的內容。
- 系統找到Keywords_france_eu_national_id_card關鍵字。

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

- 卡號
- carte nationale d'identité
- carte nationale d'idenite no
- Cni#
- Cni
- compte bancaire
- 國家識別號碼
- 國家身分識別
- nationalidno#
- numéro d'assurance maladie
- numéro de carte vitale

   
## <a name="france-passport-number"></a>法國護照號碼
此敏感性資訊類型實體可在歐盟護照號碼敏感性資訊類型中提供，而且可做為獨立的敏感性資訊類型實體使用。

### <a name="format"></a>格式

九位數和字母

### <a name="pattern"></a>模式

九位數和字母：
- 兩位數 
- 兩個字母 (不區分大小寫)  
- 五位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_fr_passport找到符合模式的內容。
- 系統找到Keyword_passport關鍵字。

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
- 護照號碼
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
- 傳遞 n °
- Passeport Non
- 傳遞區#
- 傳遞區#
- PasseportNon
- 傳遞區 °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>INSEE 中 (或) 的法國社會安全號碼
此敏感性資訊類型實體包含在歐盟社會安全號碼與同等識別碼敏感性資訊類型中，而且可做為獨立的敏感性資訊類型實體使用。

### <a name="format"></a>格式

15 位數

### <a name="pattern"></a>模式

必須符合兩種模式其中之一：
- 13 位數，後接空格後接兩位數<br/>
或
- 連續 15 位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，95% 都表示已偵測到這類敏感性資訊：
- 函數會Func_french_insee或Func_fr_insee尋找符合模式的內容。
- 系統找到Keyword_fr_insee關鍵字。
- 會傳遞檢查和。

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數會Func_french_insee或Func_fr_insee尋找符合模式的內容。
- 找不到來自Keyword_fr_insee關鍵字。
- 會傳遞檢查和。

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
- 安全安全社交
- 國名
- 國家識別
- numéro d'identité
- no d'identité
- 不。 d'identité
- numero d'identite
- no d'identite
- 不。 d'identite
- 社會安全號碼
- 社會安全碼
- 社會保險號碼
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le code de la sécurité sociale
- numéro d'assurance sociale
- numéro de sé市
- code sé郵遞區號 

## <a name="france-tax-identification-number"></a>法國稅務識別編號

### <a name="format"></a>格式

13 位數
  
### <a name="pattern"></a>模式

13 位數
  
- 一位數，必須是 0、1、2 或 3
- 1 位數
- 空格 (選) 
- 2 位數 
- 空格 (選) 
- 3 位數 
- 空格 (選) 
- 3 位數 
- 空格 (選) 
- 3 個檢查數位 

  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_france_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_france_eu_tax_file_number` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_france_eu_tax_file_number` 會尋找符合模式的內容。 
    
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

- numéro d'identificatione
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#


## <a name="france-value-added-tax-number"></a>法國加值稅編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

13 個字元的字母數位元模式

### <a name="pattern"></a>模式

13 個字元的字母數位元模式：

- 兩個字母 - FR (不區分大小寫) 
- 選擇性空格或連字號
- 兩個字母或數位
- 選擇性空格、點、連字號或逗號
- 三位數
- 選擇性空格、點、連字號或逗號
- 三位數
- 選擇性空格、點、連字號或逗號
- 三位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_france_value_added_tax_number找到符合模式的內容。
- 系統找到Keywords_france_value_added_tax_number關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_france_value_added_tax_number找到符合模式的內容。

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

- 加值稅 編號
- 加值稅 否
- 加值稅#
- 加值稅
- 使用不 numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'identification有en


## <a name="germany-drivers-license-number"></a>德國駕照

### <a name="format"></a>格式

11 位數和字母的組合

### <a name="pattern"></a>模式

11 位數和字母 (大小寫不區分) ：
- 數位或字母 
- 兩位數 
- 六位數或字母 
- 一位數 
- 數位或字母

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_german_drivers_license找到符合模式的內容。
- 系統找到Keyword_german_drivers_license_number關鍵字。
- 會傳遞檢查和。

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

- ausstel以sdatum
- ausstel一sort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
- führerschein
- 朘朘
- 倌朘
- führerscheinnummer
- 朘
- 倌朘朘
- führerschein- 
- 朘朘in- 
- 倌朘朘- 
- führerscheinnummernr
- 朘
- 佽朘朘
- führerscheinnummerklasse
- 如果系統沒有提供這些服務，這些程式會提供
- 使用時，會一併重排
- nr-führerschein
- nr-fuhrerschein
- nr-nrehrerschein
- no-führerschein
- no-erschein
- no-fuehrerschein
- n-führerschein
- n-hrerschein
- n-fuehrerschein
- permis de conduire
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dlno


## <a name="germany-identity-card-number"></a>德國身分識別卡號碼

### <a name="format"></a>格式

自 2010 年 11 月 1 日起：九個字母和數位

從 1987 年 4 月 1 日到 2010 年 10 月 31 日：10 位數

### <a name="pattern"></a>模式

自 2010 年 11 月 1 日起：
- 一個字母 (不區分大小寫)  
- 八位數

從 1987 年 4 月 1 日到 2010 年 10 月 31 日：
- 十位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 正則運算式會Regex_germany_id_card找到符合模式的內容。
- 系統找到Keyword_germany_id_card關鍵字。

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

- aus一s
- gpid
- 識別
- identifidentation
- identifizierungsnummer
- 身份證
- 身分識別號碼
- id-nummer
- 個人識別碼
- personalaus一s
- persönliche id nummer
- persönliche identifidentationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>德國護照號碼

### <a name="format"></a>格式

十位數或字母

### <a name="pattern"></a>模式

模式必須包含下列所有專案：
- 第一個字元是這個集合中的數位或字母 (C、F、G、H、J、K)  
- 三位數 
- 此集合中的五位數或英文字母 (C、-H、J-N、P、R、T、V-Z)  
- 一位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_german_passport找到符合模式的內容。
- 關鍵字來自 `Keyword_german_passport` `Keywords_eu_passport_number_common` 或找到。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_german_passport_data找到符合模式的內容。
- 關鍵字來自 `Keyword_german_passport` `Keywords_eu_passport_number_common` 或找到。
- 會傳遞檢查和。

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

- Reisepasse
- reisepassnummer
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe
- 傳遞區否。
- 傳遞區否

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 護照#
- 護照#
- passportid
- 護照
- passportno
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼


## <a name="germany-tax-identification-number"></a>德國稅務識別編號

### <a name="format"></a>格式

不含空格和分隔符號的 11 位數
  
### <a name="pattern"></a>模式

11 位數：
  
- 兩位數 
- 選擇性空格
- 三位數 
- 選擇性空格
- 三位數 
- 選擇性空格
- 兩位數
- 一個檢查數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_germany_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_germany_eu_tax_file_number` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_germany_eu_tax_file_number` 會尋找符合模式的內容。 
    
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

- identifidentationsnummer
- sterer 識別碼
- ststeridentifidentationsnummer
- sterernummer
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#
- 辛#
- 辛
- zinnnummer


## <a name="germany-value-added-tax-number"></a>德國加值稅編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

11 個字元的字母數位元模式

### <a name="pattern"></a>模式

11 個字元的字母數位元模式：

- 字母 D 或 d
- 字母 E 或 e
- 一個選擇性空格
- 三位數
- 這是選擇性的空格或逗號
- 三位數
- 這是選擇性的空格或逗號
- 三位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_germany_value_added_tax_number找到符合模式的內容。
- 系統找到Keywords_germany_value_added_tax_number關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_germany_value_added_tax_number找到符合模式的內容。

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

- 加值稅 編號
- 加值稅 否
- 加值稅#
- vat# mehrwertst
- st
- mehrwertsterter identifidentationsnummer
- mehrwertsterter nummer


## <a name="greece-drivers-license-number"></a>希臘駕照編號

### <a name="format"></a>格式

不含空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_greece_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_greece_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>希臘國識別碼卡片

### <a name="format"></a>格式

7-8 個字母和數位的組合加上虛線

### <a name="pattern"></a>模式

七個字母和數位會 (舊格式) ：
- 一個字母 (希臘字母的任何字母)  
- 虛線 
- 六位數

八個字母和數位會 (格式) ：
- 兩個字母大寫字元同時出現在希臘文和拉丁字母 (ABEZHIKMNOPTYX)  
- 虛線 
- 六位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會Regex_greece_id_card找到符合模式的內容。
- 系統找到Keyword_greece_id_card關鍵字。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 正則運算式會Regex_greece_id_card找到符合模式的內容。

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
- 希臘文識別碼
- 希臘文個人識別碼卡片
- 希臘文的希臘文識別碼
- 身份證
- tautot為
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>希臘護照號碼

### <a name="format"></a>格式

兩個字母后面接著沒有空格或分隔符號的七位數
  
### <a name="pattern"></a>模式

兩個字母后面接著七位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_greece_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_greece_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_greece_eu_passport_date` 尋找 DD MMM YY 格式 (範例 - 28 Aug 19) 或 `Keywords_greece_eu_passport_date` 找到關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_greece_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_greece_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>希臘社會安全號碼 (AMKA) 
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

不含空格和分隔符號的 11 位數
  
### <a name="pattern"></a>模式

- 6 位數作為生日 YYMMDD
- 4 位數
- 一個檢查數位
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_greece_eu_ssn` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_greece_eu_ssn_or_equivalent` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_greece_eu_ssn` 會尋找符合模式的內容。 

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
- 社會安全否
- socialsecurityno#
- 社會安全號碼
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>希臘稅務識別編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

不含空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
  
- 正則運算式會  `Regex_greece_eu_tax_file_number` 尋找符合模式的內容。 
- 找到關鍵字  `Keywords_greece_eu_tax_file_number` 。 
    
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
- aф|aфф αριθμός
- aфф
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 稅務註冊 No
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- taxregistryno#
- tin id
- tin no
- 錫#
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>香港身分識別卡 (HKID) 號碼

### <a name="format"></a>格式

8-9 個字母和數位的組合，再加上最後一個字元的選擇性括弧

### <a name="pattern"></a>模式

8-9 個字母的組合：
- 1 到 2 個字母 (不區分大小寫)  
- 六位數 
- 最後一個字元 (數位或字母 A) ，這是檢查數位，可選擇性地用括弧括住。

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_hong_kong_id_card找到符合模式的內容。
- 系統找到Keyword_hong_kong_id_card關鍵字。
- 會傳遞檢查和。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數函數Func_hong_kong_id_card找到符合模式的內容。
- 會傳遞檢查和。

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
- 香港身分識別卡
- HKIDC
- 身份證
- 身份證
- 香港身分識別卡
- 香港識別碼
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

   
## <a name="hungary-drivers-license-number"></a>匈牙利駕照編號

### <a name="format"></a>格式

兩個字母后面接著六位數
  
### <a name="pattern"></a>模式

兩個字母和六位數：
  
- 兩個字母 (不區分大小寫)  
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
  
- 正則運算式會  `Regex_hungary_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_hungary_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver s_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>匈牙利個人識別碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

11 位數
  
### <a name="pattern"></a>模式

11 位數：
  
- 一位數對應到性別 (1 小時、2 歲、其他數位也可用於 1900 之前所生，或雙母母)  
- 對應至 YYMMDD (出生日期的六位數) 
- 對應至序號的三位數
- 一個檢查數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
  
- 此函數  `Func_hungary_eu_national_id_card` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_hungary_eu_national_id_card` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
  
- 此函數  `Func_hungary_eu_national_id_card` 會尋找符合模式的內容。 
    
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

- 識別碼
- 識別碼
- sz ig
- 深圳。 ig.
- sz.ig.
- személyazonosító igamé
- személyi iga則功能區


## <a name="hungary-passport-number"></a>匈牙利護照號碼

### <a name="format"></a>格式

兩個字母后面接著沒有空格或分隔符號的六位數或七位數
  
### <a name="pattern"></a>模式

兩個字母后面接著六位數或七位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_hungary_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_hungary_eu_passport_number` 或找到。 
- 正則運算式會尋找 `Regex_hungary_eu_passport_date` DD MMM/MMM YY (範例 - 01 MÁR/MAR 12 格式) 或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_hungary_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_hungary_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- út一él száma
- Útlevelek száma
- út一él szám


## <a name="hungary-social-security-number-taj"></a>匈牙利社會安全號碼 (TAJ) 

### <a name="format"></a>格式

不含空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
  
- 此函數  `Func_hungary_eu_ssn_or_equivalent` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_hungary_eu_ssn_or_equivalent` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
  
- 此函數  `Func_hungary_eu_ssn_or_equivalent` 會尋找符合模式的內容。 
    
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

- 匈牙利文社會安全號碼
- 社會安全號碼
- socialsecuritynumber#
- hssn#
- socialsecuritynno
- hssn
- 泰姬陵
- 泰姬陵#
- Ssn
- Ssn#
- 社會安全否
- áfa
- Közösségi adószám
- által使用os forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>匈牙利稅務識別編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

十位數沒有空格或分隔符號
  
### <a name="pattern"></a>模式

十位數：
  
- 一位數必須是 "8" 
- 八位數
- 一個檢查數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
  
- 此函數  `Func_hungary_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_hungary_eu_tax_file_number` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
  
- 此函數  `Func_hungary_eu_tax_file_number` 會尋找符合模式的內容。 
    
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
- 匈牙利文的錫
- 來安那提安#
- 稅務機關無法
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#
- 加值稅 編號


## <a name="hungary-value-added-tax-number"></a>匈牙利加值稅編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

10 個字元的字母數位元模式

### <a name="pattern"></a>模式

10 個字元的字母數位元模式：

- 2 個字母 - HU 或 hu
- 選擇性空格
- 8 位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：

- 函數函數Func_hungarian_value_added_tax_number找到符合模式的內容。
- 系統找到Keywords_hungarian_value_added_tax_number關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：

- 函數函數Func_hungarian_value_added_tax_number找到符合模式的內容。

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
- 加值稅編號
- 加值稅#
- vatno#
- hungarianvatno#
- 稅號。
- 加值稅 áfa
- Közösségi adószám
- által使用os forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>PAN (的印度永久) 

### <a name="format"></a>格式

10 個字母或數位

### <a name="pattern"></a>模式

10 個字母或數位：
- 三個字母 (不區分大小寫)  
- C、P、H、F、A、T、B、L、J、G 中的字母 (區分大小寫) 
- 一個字母
- 四位數 
- 字母 (不區分大小寫) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會Regex_india_permanent_account_number找到符合模式的內容。
- 系統找到Keyword_india_permanent_account_number關鍵字。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 正則運算式會Regex_india_permanent_account_number找到符合模式的內容。


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
   
## <a name="india-unique-identification-aadhaar-number"></a>印度唯一 (Aadhaar) 編號

### <a name="format"></a>格式

包含選擇性空格或虛線的 12 位數

### <a name="pattern"></a>模式

12 位數：
- 不是 0 或 1 的數位
- 三位數 
- 選擇性空格或破折號 
- 四位數 
- 選擇性空格或破折號 
- 最後一個數位，即檢查數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_india_aadhaar找到符合模式的內容。
- 系統找到Keyword_india_aadhar關鍵字。
- 會傳遞檢查和。
- 
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：

- 函數函數Func_india_aadhaar找到符合模式的內容。
- 會傳遞檢查和。

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

包含選擇性句號的 16 位數

### <a name="pattern"></a>模式

16 位數：
- 兩位數的省碼 
- 期間 (選擇性)  
- 兩位數 regency 或城市代碼 
- 兩位數子區碼 
- 期間 (選擇性)  
- DD一Y 格式中的六位數是生日 
- 期間 (選擇性)  
- 四位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：

- 正則運算式會Regex_indonesia_id_card找到符合模式的內容。
- 系統找到Keyword_indonesia_id_card關鍵字。

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
   
## <a name="international-banking-account-number-iban"></a>IBAN (國際) 

### <a name="format"></a>格式

國碼 (兩個字母) 加上 (兩位數) 加上 bban 號碼 (最多 30 個字元) 

### <a name="pattern"></a>模式

模式必須包含下列所有專案：

- 兩個字母的國碼
- 兩個檢查數位 (後接選擇性空格)  
- 1 到 7 個包含四個字母或數位的 (，可以使用空格或空格) 
- 1-3 個字母或數位

每個國家/地區的格式稍有不同。 IBAN 敏感性資訊類型涵蓋這 60 個國家/地區：

ad， ae， al， at， az， ba， be， bg， bh， ch， cr， cy， kw， de， dk， do， ee， es， fi， fo， fr， gb， ge， gi， gl， gr， hr， hu， ie， il， is， it， kw， kz， lb， li， lt， lu， lv， mc， md， me， mk， mr， mt， mu， nl， no， pl， pt， ro， rs， sa， se， si， sk， sm， tn， tr， vg

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：

- 函數函數Func_iban找到符合模式的內容。
- 會傳遞檢查和。

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>國際疾病分類 (ICD-10-CM) 

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 系統找到Dictionary_icd_10_updated關鍵字。
- 系統找到Dictionary_icd_10_codes關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 系統找到Dictionary_icd_10_更新的關鍵字。

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

來自 Dictionary_icd_10_updated 關鍵字字典的任何字詞，該字典是以國際預防分類、第十次修訂、 ([ICD-10-CM ](https://go.microsoft.com/fwlink/?linkid=852604)) 。 此類型只會尋找該術語，不會尋找保險代碼。

任何來自 Dictionary_icd_10_codes 關鍵字字典的字詞，該字典是以國際預防分類、第十次修訂、 ([ICD-10-CM ](https://go.microsoft.com/fwlink/?linkid=852604)) 。 此類型只會尋找保險代碼，不會尋找描述。

## <a name="international-classification-of-diseases-icd-9-cm"></a>國際疾病分類 (ICD-9-CM) 

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 系統找到Dictionary_icd_9_updated關鍵字。
- 系統找到Dictionary_icd_9_codes關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 系統找到Dictionary_icd_9_updated關鍵字。

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

任何來自 Dictionary_icd_9_updated 關鍵字字典的字詞，該字典是以國際醫療分類、第九次修訂、系統 ([ICD-9-CM ](https://go.microsoft.com/fwlink/?linkid=852605)) 。 此類型只會尋找該術語，不會尋找保險代碼。

任何來自 Dictionary_icd_9_codes 關鍵字字典的字詞，該字典是以國際醫療分類、第九次修訂、系統 ([ICD-9-CM ](https://go.microsoft.com/fwlink/?linkid=852605)) 。 此類型只會尋找保險代碼，不會尋找描述。

## <a name="ip-address"></a>IP 位址

### <a name="format"></a>格式

#### <a name="ipv4"></a>IPv4：
複雜模式，此模式適用于格式化 (期間) 格式 (未格式化的) IPv4 位址版本沒有句點

#### <a name="ipv6"></a>IPv6：
將已格式化的 IPv6 數位計算為包含冒號 (複雜模式) 

### <a name="pattern"></a>模式

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

對於 IPv6，DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會Regex_ipv6_address找到符合模式的內容。
- 找不到來自Keyword_ipaddress關鍵字。

對於 IPv4，DLP 政策在 300 個字元的鄰近範圍內，95% 都確信它可偵測到這類敏感性資訊：
- 正則運算式會Regex_ipv4_address找到符合模式的內容。
- 系統找到Keyword_ipaddress關鍵字。

對於 IPv6，DLP 政策在 300 個字元的鄰近範圍內，95% 都確信它可偵測到這類敏感性資訊：
- 正則運算式會Regex_ipv6_address找到符合模式的內容。
- 找不到來自Keyword_ipaddress關鍵字。

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

- IP (此關鍵字會區分大小寫) 
- ip 位址 
- IP 位址
- 網際網路通訊協定
- IP-כתובת ה 

## <a name="ireland-drivers-license-number"></a>愛爾蘭駕照編號

### <a name="format"></a>格式

六位數後面接著四個字母
  
### <a name="pattern"></a>模式

六位數和四個字母：
  
- 六位數
- 四個字母 (不區分大小寫) 
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
  
- 正則運算式會  `Regex_ireland_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_ireland_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver s_license_number

- ceadúnas tiom一a
- ceadúnais tiom一a

## <a name="ireland-passport-number"></a>愛爾蘭護照號碼

### <a name="format"></a>格式

兩個字母或數位，後面接著七位數，沒有空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母或數位，後面接著七位數：
  
- 兩位數或兩個字母 (大小寫不區分) 
- 七位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_ireland_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_ireland_eu_passport_number` 或找到。 
- 正則運算式會尋找 `Regex_ireland_eu_passport_date` DD MMM/MMM YYYY (範例 - 01 BEA/MAY 1988) 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_ireland_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_ireland_eu_passport_number` 或找到。
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uim一 pas
- uim一個
- uimhreacha pas
- uim一 cárta
- uim一 chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="ireland-personal-public-service-pps-number"></a>愛爾蘭個人公用服務 (PPS) 號碼

### <a name="format"></a>格式

舊格式會 (2012 年 12 月 31 日) ：
- 七位數，後面接著 1-2 個字母 

2013 (1 日及之後的新格式) ：
- 七位數後面接著兩個字母

### <a name="pattern"></a>模式

舊格式會 (2012 年 12 月 31 日) ：
- 七位數 
- 一到兩個字母 (不區分大小寫)  

2013 (1 日及之後的新格式) ：
- 七位數 
- 字母 (不區分大小寫) 這是字母檢查數位 
- 範圍 A-I 或 "W" 的選擇性字母

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_ireland_pps找到符合模式的內容。
- 系統找到Keywords_ireland_eu_national_id_card關鍵字。
- 會傳遞檢查和。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數函數Func_ireland_pps找到符合模式的內容。
- 會傳遞檢查和。

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
- 識別碼
- 個人識別碼
- 個人公用服務號碼
- 個人服務否
- phearsanta seirbhíse poiblí
- pps 否
- pps 編號
- pps num
- pps 服務否
- ppsn
- ppsno#
- ppsno
- Psp
- 公用服務否
- publicserviceno#
- publicserviceno
- 營收與社會保險號碼
- rsi no
- rsi 數位
- rsin
- seirbhís aitheantais client
- uimh
- uim一 aitheantais ch當ach
- uim一 aitheantais phearsanta
- uim一 phearsanta seirbhíse poiblí
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#


## <a name="israel-bank-account-number"></a>以色列銀行帳戶號碼

### <a name="format"></a>格式

13 位數

### <a name="pattern"></a>模式

格式 化：
- 兩位數 
- 破折號 
- 三位數 
- 破折號 
- 八位數

未格式化：
- 13 個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_israel_bank_account_number找到符合模式的內容。
- 系統找到Keyword_israel_bank_account_number關鍵字。

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
- 帳號 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>以色列國家識別號碼

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_israeli_national_id_number找到符合模式的內容。
- 系統找到Keyword_Israel_National_ID關鍵字。
- 會傳遞檢查和。

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
-   識別碼
-   身分識別否        
-   identitynumber#
-   身分識別號碼
-   identidentitynumber       
-   個人識別碼
-   唯一識別碼  

   
## <a name="italy-drivers-license-number"></a>義大利駕照編號

### <a name="format"></a>格式

10 個字母和數位的組合

### <a name="pattern"></a>模式

10 個字母和數位的組合：
- 一個字母 (不區分大小寫)  
- 字母 "A" 或 "V" (不區分大小寫)  
- 七位數
- 一個字母 (不區分大小寫) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_italy_drivers_license_number找到符合模式的內容。
- 系統找到Keyword_italy_drivers_license_number關鍵字。

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

- numero di patente
- patente di guida 
- patente guida
- patenti di guida
- patenti guida

## <a name="italy-fiscal-code"></a>義大利會計代碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

指定模式中 16 個字元的字母和數位組合
  
### <a name="pattern"></a>模式

16 個字元的字母和數位組合：
- 三個字母對應到家庭姓名中前三個子音
- 對應到名字中第一個、第三個及第四個子音的三個字母
- 對應至生日年份最後一位數的兩位數
- 一個對應到生日月份字母的字母 —字母是按照字母順序排列，但只會使用 A 到 E、H、L、M、P、R 到 T 的字母 (因此，January 是 A，而十月是 R) 
- 兩位數對應到生日當天，為了區分性別，會為女性在生日加上 40。
- 四位數對應到該人員所生之國家 (區碼特定的區碼，適用于其他國家/) 
- 一個等位數
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_italy_eu_national_id_card` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_italy_eu_national_id_card` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_italy_eu_national_id_card` 會尋找符合模式的內容。 
    
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

- Codice fiscal
- Codice fiscale
- codice 識別碼個人化
- Codice Personale
- 會計代碼
- numero certificific personale
- numero di identific一one fiscale
- numero id personale
- numero personale
- 個人憑證編號
- 個人代碼
- 個人識別碼代碼
- 個人識別碼
- personalcodeno#
- 稅務代碼
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅務身分識別號碼
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#


## <a name="italy-passport-number"></a>義大利護照號碼

### <a name="format"></a>格式

兩個字母或數位，後面接著七位數，沒有空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母或數位，後面接著七位數：
  
- 兩位數或兩個字母 (不區分大小寫) 
- 七位數
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_italy_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_italy_eu_passport_number` 或找到。 
- 正則運算式會尋找 `Regex_italy_eu_passport_date` DD MMM/MMM YYYY (範例 - 01 GEN/JAN 1988) 或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_italy_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_italy_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana Passaporto
- Passaporto italiana
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- 傳遞區

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="italy-value-added-tax-number"></a>義大利加值稅編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

包含選擇性分隔符號的 13 個字元 Alphanumeric 模式

### <a name="pattern"></a>模式

包含選擇性分隔符號的 13 個字元 Alphanumeric 模式：

- I 或 i
- T 或 t
- 選擇性空格、點、連字號或逗號
- 11 位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_italy_value_added_tax_number找到符合模式的內容。
- 系統找到Keywords_italy_value_added_tax_number關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_italy_value_added_tax_number找到符合模式的內容。

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

- 加值稅 編號
- 加值稅 否
- 加值稅#
- 使用
- 使用#


## <a name="japan-bank-account-number"></a>日本銀行帳戶號碼

### <a name="format"></a>格式

7 或 8 位數

### <a name="pattern"></a>模式

銀行帳戶號碼：
- 7 或 8 位數
- 銀行帳戶分支代碼：
- 四位數 
- 這是選擇性的空格 (虛線)  
- 三位數

校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_jp_bank_account找到符合模式的內容。
- 系統找到Keyword_jp_bank_account關鍵字。
- 下列其中一個條件成立：
- 函數函數Func_jp_bank_account_branch_code找到符合模式的內容。
- 系統找到Keyword_jp_bank_branch_code關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_jp_bank_account找到符合模式的內容。
- 系統找到Keyword_jp_bank_account關鍵字。

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
- 檢查 Acct 號碼 
- 檢查 Acct# 
- 檢查 Acct 否。 
- 檢查帳戶號。 
- 銀行帳戶號碼 
- 銀行帳戶 
- 銀行帳戶# 
- 銀行 Acct 號碼 
- Bank Acct# 
- Bank Acct No. 
- 銀行帳戶號。 
- 存款帳戶號碼 
- 儲蓄帳戶 
- 儲蓄帳戶# 
- 儲蓄帳戶號碼 
- 儲蓄帳戶# 
- 儲蓄帳戶否。 
- 儲蓄帳戶號。 
- 轉帳帳戶號碼 
- 轉帳帳戶 
- 轉帳帳戶# 
- 轉帳卡號碼 
- 轉帳帳戶# 
- 轉帳帳戶否。 
- 轉帳帳戶否。 
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

12 位數

### <a name="pattern"></a>模式

12 個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_jp_drivers_license_number找到符合模式的內容。
- 系統找到Keyword_jp_drivers_license_number關鍵字。

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

- 驅動程式許可證
- 驅動程式許可證
- 驅動程式的許可證
- 驅動程式許可證
- 驅動程式的分割區
- 驅動程式許可證
- Dl#
- Dls#
- lic#
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
- 使用転免証no
- 使用転免要求
- 免証no
- 免免
- 運転経歴証明書番號
- 運転経歴証明書
- 使用転免証No。
- 使用転免管理。
- 免証No。
- 免去。
- 運転免許証#
- 運転免許#
- 免許証#
- 免許#


## <a name="japan-my-number---corporate"></a>日本我的號碼 - 公司
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

13 位數號碼

### <a name="pattern"></a>模式

13 位數號碼：

- 一位數到九位數
- 12 位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_japanese_my_number_corporate找到符合模式的內容。
- 系統找到Keywords_japanese_my_number_corporate關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_japanese_my_number_corporate找到符合模式的內容。

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

- 公司編號
- マイナンバー
- 共通番號
- マイナンバーカード
- マイナンバーカード番號
- 個人番號カード
- 個人識別番號
- 個人識別ナンバー
- 法人番號
- 指定通知書


## <a name="japan-my-number---personal"></a>日本我的號碼 - 個人
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

12 位數號碼

### <a name="pattern"></a>模式

12 位數號碼：

- 四位數
- 選擇性空格、點或連字號
- 四位數
- 選擇性空格、點或連字號
- 四位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_japanese_my_number_personal找到符合模式的內容。
- 系統找到Keywords_japanese_my_number_personal關鍵字。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數函數Func_japanese_my_number_personal找到符合模式的內容。

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

兩個字母后面接著七位數

### <a name="pattern"></a>模式

兩個字母 (不區分大小寫) 後面接著七位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_jp_passport找到符合模式的內容。
- 系統找到Keyword_jp_passport關鍵字。

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
- 護照號碼
- 護照#
- パスポート
- パスポート番號
- パスポートナンバー
- パスポート＃
- パスポート#
- パスポートNo。
- 旅券番號
- 旅券番號＃
- 旅券番號♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>日本居住卡號碼

### <a name="format"></a>格式

12 個字母和數位

### <a name="pattern"></a>模式

12 個字母和數位：
- 兩個字母 (不區分大小寫) 
- 八位數 
- 兩個字母 (不區分大小寫) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_jp_residence_card_number找到符合模式的內容。
- 系統找到Keyword_jp_residence_card_number關鍵字。

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

- 居住卡號碼
- 居住卡號碼
- 居住卡#
- 在留カード番號
- 在留カード
- 在留番號

## <a name="japan-resident-registration-number"></a>日本居民註冊號碼

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

連續 11 位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_jp_resident_registration_number找到符合模式的內容。
- 系統找到Keyword_jp_resident_registration_number關鍵字。

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

- 居民註冊號碼
- 居民基本註冊表號碼 
- 居住註冊號碼。 
- 住家註冊人否。 
- 人口基本註冊表否。 
- 基本居住登記簿否。 
- 外國人登録証明書番號
- 証明書番號
- 登録番號
- 外國人登録証

   
## <a name="japan-social-insurance-number-sin"></a>日本社會保險編號 (SIN) 

### <a name="format"></a>格式

7-12 位數

### <a name="pattern"></a>模式

7-12 位數：
- 四位數 
- 連字號或 (選)  
- 六位數 OR
- 7-12 個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_jp_sin找到符合模式的內容。
- 系統找到Keyword_jp_sin關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_jp_sin_pre_1997找到符合模式的內容。
- 系統找到Keyword_jp_sin關鍵字。

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

- 社會保險 No. 
- Social Insurance Num 
- 社會保險號碼 
- 健康保険被保険者番號
- 健保番號
- 基礎年金番號
- 雇用保険被保険者番號
- 雇用保険番號
- 保険証番號
- 社會保険番號
- 可険No。
- 社會保険
- 介護保険
- 介護保険被保険者番號
- 健康保険被保険者整理番號
- 雇用保険被保険者整理番號
- 厚生年金
- 厚生年金被保険者整理番號


## <a name="latvia-drivers-license-number"></a>拉脫維亞駕照編號

### <a name="format"></a>格式

三個字母后面接著六位數
  
### <a name="pattern"></a>模式

三個字母和六位數：
  
- 三個字母 (不區分大小寫)  
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_latvia_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_latvia_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver s_license_number

- autovad以tāja apliec以ba
- autovad以tāja apliec以bas
- vad以tāja apliec以ba

## <a name="latvia-personal-code"></a>拉脫維亞個人代碼

### <a name="format"></a>格式

11 位數及選擇性連字號
  
### <a name="pattern"></a>模式

舊格式

11 位數和連字號：
  
- 這是對應到 DD一Y (的六位數)  
- 連字號
- 對應至 19 世紀之生產世紀 ("0"、20 世紀對應的 "1" 和 22 世紀) 
- 隨機產生的四位數

新格式

11 位數

- 兩位數 "32"
- 九位數
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數  `Func_latvia_eu_national_id_card` 或 RegEx `Regex_latvia_eu_national_id_card_new_format` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_latvia_eu_national_id_card` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數  `Func_latvia_eu_national_id_card` 或 RegEx `Regex_latvia_eu_national_id_card_new_format` 會尋找符合模式的內容。 
    
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

- 系統管理號碼
- alvas nē
- 出生日期
- 百分位號碼
- 社會號碼
- 電子錢號碼
- 電子數位
- 會計代碼
- 醫療保健使用者編號
- Id#
- 識別碼代碼
- 識別碼
- identifikācijas numurs
- 識別碼
- 個別編號
- 拉圖維雅 alva
- nacionālais 識別碼
- 國名
- 國家識別號碼
- 身分識別號碼
- 國家保險號碼
- national register number
- nodokļa數
- nodokļu識別碼
- nodokļu identifikācija numurs
- 個人憑證編號
- 個人代碼
- 個人識別碼代碼
- 個人識別碼
- 個人識別碼
- 個人識別碼
- 個人身分識別號碼
- 個人號碼
- 個人數位代碼
- personalcodeno#
- 角色 kods
- 人口識別碼
- 公用服務號碼
- 註冊號碼
- 營收數位
- 社會保險號碼
- 社會安全號碼
- 州稅碼
- 稅務檔案編號
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#
- 百分位號碼

## <a name="latvia-passport-number"></a>拉脫維亞護照號碼

### <a name="format"></a>格式

兩個字母或數位，後面接著七位數，沒有空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母或數位，後面接著七位數：
  
- 兩位數或兩個字母 (不區分大小寫) 
- 七位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_latvia_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_latvia_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date1` 尋找 DD.MM.YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_latvia_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_latvia_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- 傳遞區否
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="lithuania-drivers-license-number"></a>立陶宛駕照編號

### <a name="format"></a>格式

不含空格和分隔符號的八位數
  
### <a name="pattern"></a>模式

八位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_lithuania_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_lithuania_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver s_license_number

- vair一tojo pažymėjimas
- vair在tojo pažymėjimo numeris
- vair在tojo pažymėjimo num一i

## <a name="lithuania-personal-code"></a>立陶宛個人代碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

不含空格和分隔符號的 11 位數
  
### <a name="pattern"></a>模式

不含空格和分隔符號的 11 位數：
  
- 一位數 (1-6) 表示該人員性別與年齡
- 對應至 YYMMDD (出生日期的六位數)  
- 對應至出生日期序列值三位數
- 一個檢查數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_lithuania_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_lithuania_eu_tax_file_number` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_lithuania_eu_tax_file_number` 會尋找符合模式的內容。 
    
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
- 目前服務編號
- mokesčių識別碼
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių numeris
- 國家識別號碼
- 個人代碼
- 個人數位代碼
- pilie以io paslaugos numeris
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- 唯一標識號
- 唯一身分識別號碼
- uniqueidentityno#

## <a name="lithuania-passport-number"></a>立陶宛護照號碼

### <a name="format"></a>格式

沒有空格或分隔符號的八位數或字母
  
### <a name="pattern"></a>模式

8 位數或 8 (字母，不區分大小寫) 
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_lithuania_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_lithuania_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date3` 尋找 DD MM YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_lithuania_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_lithuania_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso num在i
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="luxemburg-drivers-license-number"></a>百勝堡駕照號碼

### <a name="format"></a>格式

不含空格和分隔符號的六位數
  
### <a name="pattern"></a>模式

六位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_luxemburg_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_luxemburg_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver s_license_number

- fahrerlaubnis
- Führerschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>奇比堡的國 (號碼) 
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

13 位數，沒有空格或分隔符號
  
### <a name="pattern"></a>模式

13 位數：
  
- 11 位數 
- 兩個檢查數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_luxemburg_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_luxemburg_eu_national_id_card` 。 

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_luxemburg_eu_tax_file_number` 會尋找符合模式的內容。 


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

- eindei使用e id
- eindei使用e id-nummer
- eindei使用eid#
- 識別碼個人化
- idperson一e#
- idperson一e
- 個別代碼
- 個別識別碼
- 個別識別
- 個別身分識別
- numéro d'identification personnel
- 個人識別碼
- 個人標識
- 個人身分識別
- personalidno#
- personalidnumber#
- persönliche identifidentationsnummer
- 唯一識別碼
- 唯一身分識別
- uniqueidkey#

## <a name="luxemburg-passport-number"></a>卡比堡護照號碼

### <a name="format"></a>格式

沒有空格或分隔符號的八位數或字母
  
### <a name="pattern"></a>模式

8 位數或 8 (字母，不區分大小寫) 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_luxemburg_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_luxemburg_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date3` 尋找 DD MM YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_luxemburg_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_luxemburg_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- aus一snummer
- luxembourg pass
- luxembourg passeport
- 盧森堡護照
- 沒有通過區
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- 通過 nr
- passnummer
- passeport nombre
- reisepässe
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>奇比堡國家識別號碼 (非自然人士) 

### <a name="format"></a>格式

11 位數
  
### <a name="pattern"></a>模式

11 位數
  
- 兩位數
- 一個選擇性空格 
- 三位數 
- 一個選擇性空格
- 三位數 
- 一個選擇性空格
- 兩位數
- 一個檢查數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_luxemburg_eu_tax_file_number_non_natural` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_luxemburg_eu_tax_file_number` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_luxemburg_eu_tax_file_number_non_natural` 會尋找符合模式的內容。 
    
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

- carte de sécurité sociale
- étain non
- étain#
- identifiant d'imp以t
- luxembourg tax identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxembourgeois
- numéro d'identificatione
- 社會保障
- sozialunterstützung
- sozialversécherung
- sozialversicherungsaus一s
- Steier 識別碼
- steier identifikatiounsnummer
- steier nummer
- sterer 識別碼
- ststeridentifidentationsnummer
- sterernummer
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#
- 辛#
- 辛
- zinnzahl


## <a name="malaysia-identification-card-number"></a>馬來西亞識別卡號碼

### <a name="format"></a>格式

包含選擇性連字號的 12 位數

### <a name="pattern"></a>模式

12 位數：
- 格式為 YYMMDD 的六位數，這是生日 
- 虛線 (選)  
- 兩個字母的出生日期代碼 
- 虛線 (選)  
- 三個亂數字 
- 一位數性別代碼

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會Regex_malaysia_id_card_number模式的內容。
- 系統找到Keyword_malaysia_id_card_number關鍵字。

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

- 數位應用程式卡
- i/c
- i/c 否
- Ic
- ic 否
- 身份證
- 識別卡
- 身份證
- K/p
- K/p 否
- kad akuan d會
- kad aplikasi digital
- kadenalan malaysia
- Kp
- kpi 否
- mykad
- mykas
- mykid
- mypr
- mytentera
- 馬來西亞身分識別卡
- 身分識別卡
- nric
- 個人標識卡

## <a name="malta-drivers-license-number"></a>盧森堡駕照編號

### <a name="format"></a>格式

指定模式中兩個字元和六位數的組合
  
### <a name="pattern"></a>模式

兩個字元和六位數的組合：
  
- 兩個字元 (或字母，不區分大小寫) 
- 這是 (選項) 
- 三位數
- 這是 (選項) 
- 三位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_malta_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_malta_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver s_license_number

- liċenzja tas-sewqan
- liċenzji tas-sewwieq


## <a name="malta-identity-card-number"></a>盧森堡身分識別卡號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

七位數後面接著一個字母
  
### <a name="pattern"></a>模式

七位數，後面接著一個字母：
  
- 七位數 
- 不區分大小寫時，以 "M， G， A， P， L， H， B， Z" 表示 (一個字母) 
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_malta_eu_national_id_card` 尋找符合模式的內容。 
- 找到關鍵字  `Keywords_malta_eu_national_id_card` 。 
    
DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 正則運算式會  `Regex_malta_eu_national_id_card` 尋找符合模式的內容。 
    
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

- 目前服務編號
- id tat-taxxa
- identifika numru tal-jetjett
- kodiċi數位個人i
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità Uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 個人數位代碼
- 唯一標識號
- 唯一身分識別號碼
- uniqueidentityno#


## <a name="malta-passport-number"></a>盧森堡護照號碼

### <a name="format"></a>格式

不含空格或分隔符號的七位數
  
### <a name="pattern"></a>模式

七位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_malta_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_malta_eu_passport_number` 或找到。 
- 找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_malta_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_malta_eu_passport_number` 或找到。 
    
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
- 護照號碼
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


## <a name="malta-tax-identification-number"></a>盧森堡稅務識別號碼

### <a name="format"></a>格式

針對馬德群島：
- 指定模式中七位數和一個字母
  
非馬塞斯群島和馬德群島實體：
- 九位數
  
### <a name="pattern"></a>模式

馬塞文：7 位數和 1 個字母
  
- 七位數 
- 一個字母 (不區分大小寫) 
    
非馬塞群島和馬德群島：九位數
  
- 九位數 
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- RegEx  `Regex_malta_eu_tax_file_number`  或 `Regex_malta_eu_tax_file_number_non_maltese_national` 尋找符合模式的內容。 
- 找到關鍵字  `Keywords_malta_eu_tax_file_number` 。 
    
DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- RegEx  `Regex_malta_eu_tax_file_number` 或 `Regex_malta_eu_tax_file_number_non_maltese_national` 尋找符合模式的內容。 
    
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

- 目前服務編號
- id tat-taxxa
- identifika numru tal-jetjett
- kodiċi數位個人i
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità Uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 個人數位代碼
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#
- 唯一標識號
- 唯一身分識別號碼
- uniqueidentityno#

## <a name="netherlands-citizens-service-bsn-number"></a>荷蘭的服務號碼是 BSN (號碼) 號碼

### <a name="format"></a>格式

包含選擇性空格的八九位數

### <a name="pattern"></a>模式

八九位數：
- 三位數 
- 這是 (選項)  
- 三位數 
- 這是 (選項)  
- 2-3 位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_netherlands_bsn找到符合模式的內容。
- 系統找到Keyword_netherlands_bsn關鍵字。
- 會傳遞檢查和。

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
- servicenummer
- 目前服務編號
- 人員編號
- 個人號碼
- 個人數位代碼
- 人員相關號碼
- persoonlijk nummer
- persoonlijke numerieke code
- persoonsge以登
- persoonsnummer
- sociaal-fiscaal nummer
- 社交會計數位
- sofi
- sofinummer
- uniek identificatienummer
- Uniek identit一snummer
- 唯一標識號
- 唯一身分識別號碼
- uniqueidentityno#

## <a name="netherlands-drivers-license-number"></a>荷蘭駕照編號

### <a name="format"></a>格式

不含空格和分隔符號的十位數
  
### <a name="pattern"></a>模式

十位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_netherlands_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_netherlands_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewij以
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>荷蘭護照號碼

### <a name="format"></a>格式

九個字母或數位，沒有空格或分隔符號
  
### <a name="pattern"></a>模式

九個字母或數位
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_netherlands_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_netherlands_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_netherlands_eu_passport_date` 尋找 DD MMM/MMM YYYY 格式 (範例 - 26 MAA/MAR 2012) 

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_netherlands_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_netherlands_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>荷蘭稅務識別編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

不含空格或分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數 
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_netherlands_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_netherlands_eu_tax_file_number` 。 
    
DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 此函數  `Func_netherlands_eu_tax_file_number` 會尋找符合模式的內容。 
    
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
- hollânske tax identification
- hulandes impuesto id number
- hulandes impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- 下一個識別號碼
- impuesto number
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- 荷蘭稅務識別
- 荷蘭的稅務識別
- 荷蘭錫
- 荷蘭的錫
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅務識別功能
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 稅單
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#


## <a name="netherlands-value-added-tax-number"></a>荷蘭加值稅編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

14 個字元的字母數位元模式

### <a name="pattern"></a>模式

14 個字元的字母數位元模式：

- N 或 n
- L 或 l
- 選擇性空格、點或連字號
- 九位數
- 選擇性空格、點或連字號
- B 或 b
- 兩位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_netherlands_value_added_tax_number找到符合模式的內容。
- 系統找到Keywords_netherlands_value_added_tax_number關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_netherlands_value_added_tax_number找到符合模式的內容。

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

- 加值稅 編號
- 加值稅 否
- 加值稅#
- wearde tafoege tax getal
- btw n與mer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>紐西蘭銀行帳戶號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

包含選擇性分隔符號的 14 到 16 位數模式

### <a name="pattern"></a>模式

包含選擇性分隔符號的 14 到 16 位數模式：

- 兩位數
- 選擇性的連字號或空格
- 三到四位數
- 選擇性的連字號或空格
- 七位數
- 選擇性的連字號或空格
- 2 到 3 位數
- 選項連字號或空格

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_new_zealand_bank_account_number找到符合模式的內容。
- 系統找到Keywords_new_zealand_bank_account_number關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_new_zealand_bank_account_number找到符合模式的內容。

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

- 帳號
- 銀行帳戶
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>紐西蘭駕照編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

八個字元的字母數位元模式

### <a name="pattern"></a>模式

八個字元的字母數位元模式

- 兩個字母 
- 六位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_newzealand_driver_license_number找到符合模式的內容。
- 系統找到Keywords_newzealand_driver_license_number關鍵字。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數函數Func_newzealand_driver_license_number找到符合模式的內容。

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

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 駕照
- 駕照
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 駕照
- 驅動程式#
- 驅動程式#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 駕照#
- 國際駕駛許可
- 國際駕駛許可
- nz 汽車關聯
- 紐西蘭汽車協會


## <a name="new-zealand-inland-revenue-number"></a>紐西蘭內陸營收數位
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

包含選擇性分隔符號的八位數或九位數

### <a name="pattern"></a>模式

包含選擇性分隔符號的八位數或九位數

- 兩位數或三位數
- 選擇性空格或連字號
- 三位數
- 選擇性空格或連字號
- 三位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_new_zealand_inland_revenue_number找到符合模式的內容。
- 系統找到Keywords_new_zealand_inland_revenue_number關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_new_zealand_inland_revenue_number找到符合模式的內容。

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

- ird no.
- ird no#
- nz ird
- 紐西蘭
- 第 i 個編號
- 內陸營收數位


## <a name="new-zealand-ministry-of-health-number"></a>紐西蘭健康號碼的開始

### <a name="format"></a>格式

三個字母、一個空格 (選) 和四位數

### <a name="pattern"></a>模式

- 三個字母 (除了 'I' 和 'O') 不區分大小寫
- 這是 (選項)  
- 四位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_new_zealand_ministry_of_health_number找到符合模式的內容。
- 系統找到Keyword_nz_terms關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_new_zealand_ministry_of_health_number找到符合模式的內容。
- 會傳遞檢查和。

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
- 國家健康指數編號
- nhi number
- nhi 否。
- NHI#
- 國家健康指數 No.
- 國家健康指數識別碼
- 國家健康索引#

## <a name="new-zealand-social-welfare-number"></a>紐西蘭社會號碼

此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九位數

- 三位數
- 選擇性的連字號
- 三位數
- 選擇性的連字號
- 三位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_newzealand_social_welfare_number找到符合模式的內容。
- 系統找到Keywords_newzealand_social_welfare_number關鍵字。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數函數Func_newzealand_social_welfare_number找到符合模式的內容。

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

- 社交要求#
- 社交要求#
- 社交家庭否。
- 社交號碼
- Swn#

   
## <a name="norway-identification-number"></a>挪威標識號

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

11 位數：
- 格式 DD您用 6 位數表示生日 
- 三位數的個別號碼 
- 兩個檢查數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_norway_id_number找到符合模式的內容。
- 系統找到Keyword_norway_id_number關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_norway_id_numbe找到符合模式的內容。
- 會傳遞檢查和。

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

- 個人識別碼
- 挪威文識別碼
- 識別碼
- 識別
- Personnummer
- Fфdselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>菲律賓統一的多重用途標識號

### <a name="format"></a>格式

以連字號分隔的 12 位數

### <a name="pattern"></a>模式

12 位數：
- 四位數 
- 連字號 
- 七位數 
- 連字號 
- 一位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_philippines_unified_id找到符合模式的內容。
- 系統找到Keyword_philippines_id關鍵字。

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
- Pinag-isang Multi-Layunin 識別碼

## <a name="poland-drivers-license-number"></a>波蘭駕照編號

### <a name="format"></a>格式

包含 2 個斜線的 14 位數
  
### <a name="pattern"></a>模式

14 位數和 2 個斜線：
  
- 五位數 
- 斜線
- 兩位數
- 斜線
- 七位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_poland_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_poland_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver s_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>波蘭身分識別卡

### <a name="format"></a>格式

三個字母和六位數

### <a name="pattern"></a>模式

三個字母 (不區分大小寫) 後面接著六位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_polish_national_id找到符合模式的內容。
- 系統找到Keyword_polish_national_id_passport_number關鍵字。
- 會傳遞檢查和。

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

- 道可 osobisty
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- 道可Tożsamości
- 道鐘斯指數。 作業系統。

   
## <a name="poland-national-id-pesel"></a>波蘭國家 (PESEL) 

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

- 以 YYMMDD 格式表示生日的 6 位數
- 4 位數
- 1 個檢查數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_pesel_identification_number找到符合模式的內容。
- 系統找到Keyword_pesel_identification_number關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_pesel_identification_number找到符合模式的內容。
- 會傳遞檢查和。

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

- ód osobisty
- ódosobisty
- niepowtarzalny numer
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- numer identyfikacyjny
- pesel
- tożsamości nar一wej

   
## <a name="poland-passport-number"></a>波蘭護照號碼
此敏感性資訊類型實體包含在歐盟護照號碼敏感性資訊類型中，而且可做為獨立的敏感性資訊類型實體使用。

### <a name="format"></a>格式

兩個字母及七位數

### <a name="pattern"></a>模式

兩個字母 (不區分大小寫) 後接七位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_polish_passport_number找到符合模式的內容。
- 系統找到Keyword_polish_national_id_passport_number關鍵字。
- 會傳遞檢查和。

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

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Numer paszportu
- 星期日。 Paszportu
- Paszport

## <a name="poland-regon-number"></a>波蘭 REGON 號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

九位數或 14 位數號碼

### <a name="pattern"></a>模式

九位數或 14 位數號碼：

- 九位數或 
- 九位數
- 字元
- 五位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_polish_regon_number找到符合模式的內容。
- 系統找到Keywords_polish_regon_number關鍵字。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數函數Func_polish_regon_number找到符合模式的內容。

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
- regon 號碼
- reg已d#
- regonno#
- 公司識別碼
- companyid#
- companyidno#
- numer statysty ltny
- numeru regon
- numerstatysty ltny#
- numeruregon#


## <a name="poland-tax-identification-number"></a>波蘭稅務識別編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

11 位數，沒有空格或分隔符號
  
### <a name="pattern"></a>模式

11 位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_poland_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_poland_eu_tax_file_number` 。 
    
  
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
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej#
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#
- 加值稅 識別碼#
- 加值稅 識別碼
- 加值稅 否
- 加值稅 編號
- vatid#
- vatid
- vatno#
   

## <a name="portugal-citizen-card-number"></a>葡萄牙卡號

### <a name="format"></a>格式

八位數

### <a name="pattern"></a>模式

八位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會Regex_portugal_citizen_card找到符合模式的內容。
- 系統找到Keyword_portugal_citizen_card關鍵字。

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

- 使用 identidade
- cartão de cidadão
- 百分卡
- 檔編號
- documento de identificação
- 識別碼
- 識別否
- 識別碼
- 身分識別卡號碼
- 身分識別卡號碼
- 國家/a0
- 網卡
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- 葡萄牙 bi 號碼


## <a name="portugal-drivers-license-number"></a>葡萄牙駕照編號

### <a name="format"></a>格式

兩個模式 - 兩個字母后面接著 5 到 8 位數的特殊字元
  
### <a name="pattern"></a>模式

模式 1：兩個字母后面接著 5/6 特殊字元：
- 兩個字母 (不區分大小寫) 
- 連字號
- 五或六位數
- 一個空格
- 一位數

模式 2：一個字母后面接著 6/8 位數的特殊字元：
- 一個字母 (不區分大小寫) 
- 連字號
- 六位或八位數
- 一個空格
- 一位數

    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_portugal_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_portugal_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver s_license_number

- cart當機者
- cart cart cartista
- cart一 de 該ilitação
- carted iliilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução Portugal
- carta de condução

## <a name="portugal-passport-number"></a>葡萄牙護照號碼

### <a name="format"></a>格式

一個字母后面接著沒有空格或分隔符號的六位數
  
### <a name="pattern"></a>模式

一個字母后面接著六位數：
  
- 一個字母 (不區分大小寫) 
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_portugal_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_portugal_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date1` 尋找 DD.MM.YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_portugal_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_portugal_eu_passport_number` 或找到。
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do Passaporte
- 葡萄牙文護照
- 葡萄牙文傳遞區
- 葡萄牙文傳遞
- Passaporte n r
- 傳遞 n°
- números de passaporte
- 葡萄牙文護照
- número Passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="portugal-tax-identification-number"></a>葡萄牙稅務識別編號

### <a name="format"></a>格式

九位數及選擇性空格
  
### <a name="pattern"></a>模式

- 3 位數
- 一個選擇性空格
- 3 位數
- 一個選擇性空格
- 3 位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_portugal_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_portugal_eu_tax_file_number` 。 
    
DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 此函數  `Func_portugal_eu_tax_file_number` 會尋找符合模式的內容。 
    
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
- numero fiscal
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#


## <a name="romania-drivers-license-number"></a>羅馬尼亞駕照編號

### <a name="format"></a>格式

一個字元後面接著八位數
  
### <a name="pattern"></a>模式

一個字元後面接著八位數：
- 一個字母 (不區分大小寫的) 數位 
- 八位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_romania_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_romania_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver s_license_number

- permis de conducere
- permis一i de conducere
- permis一i conducere
- permisele de conducere
- permisele conducere
- permis conducere

## <a name="romania-personal-numeric-code-cnp"></a>羅馬尼亞個人數位代碼 (CNP 格式) 
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

不含空格和分隔符號的 13 位數
  
### <a name="pattern"></a>模式

- 1 到 9 的 1 位數
- 代表 YYMMDD (生日的 6 位數) 
- 2 位數，可以是 01-52 或 99
- 4 位數

### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_romania_eu_national_id_card` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_romania_eu_national_id_card` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_romania_eu_national_id_card` 會尋找符合模式的內容。 
    
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
- cod identificare personal
- cod numeric personal
- cod unic identificare
- codnumericpersonal#
- codul fiscal nr.
- identificarea fiscalnr#
- id-ul taxei
- 保險號碼
- insurancenumber#
- 國名#
- 國名
- 國家識別號碼
- num以r identificare personal
- num與 identitate
- num舍r 個人 unic
- num與ridentitate#
- num與ridentitate
- num與rpers一個ic#
- num與rpers一個ic
- num以ru de identificare fiscal除
- num與rul de identificare fiscal除
- 個人數位代碼
- 針#
- 針
- 稅務檔案否
- 稅務檔案編號
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#
- 唯一標識號
- 唯一身分識別號碼
- uniqueidentityno#
- uniqueidentityno

## <a name="romania-passport-number"></a>羅馬尼亞護照號碼

### <a name="format"></a>格式

不含空格和分隔符號的八位數或九位數
  
### <a name="pattern"></a>模式

8 或 9 位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_romania_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_romania_eu_passport_number` 或找到。 
- 正則運算式會尋找 `Regex_romania_eu_passport_date` 格式 DD MMM/MMM YY (Example- 01 FEB/FEB 10) 或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_romania_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_romania_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numportrul pașaportului numarul pasaport一i numerele pașaportului Pașaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="russia-passport-number-domestic"></a>俄羅斯國內護照號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

十位數數位

### <a name="pattern"></a>模式

十位數數位：

- 兩位數
- 選擇性空格或連字號
- 兩位數
- 一個選擇性空格
- 六位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- RegEx 索引Regex_Russian_Passport_Number_Domestic找到符合模式的內容。
- 系統找到Keyword_Russian_Passport_Number關鍵字。

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
- 護照號碼
- 護照#
- 護照識別碼
- passportno#
- passportnumber#
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт#
- паспортid#
- номер паспорта
- номерпаспорта#


## <a name="russia-passport-number-international"></a>俄羅斯護照號碼國際
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

九位數數位

### <a name="pattern"></a>模式

九位數號碼：

- 兩位數
- 選擇性空格或連字號
- 七位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- RegEx 索引Regex_Russian_Passport_Number_International找到符合模式的內容。
- 系統找到Keyword_Russian_Passport_Number關鍵字。

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
- 護照號碼
- 護照#
- 護照識別碼
- passportno#
- passportnumber#
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт#
- паспортid#
- номер паспорта
- номерпаспорта#


## <a name="saudi-arabia-national-id"></a>沙烏地阿拉伯國名

### <a name="format"></a>格式

十位數

### <a name="pattern"></a>模式

十個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_saudi_arabia_national_id找到符合模式的內容。
- 系統找到Keyword_saudi_arabia_national_id關鍵字。

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

- 識別卡 
- I 卡號 
- 識別碼 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>新加坡國家註冊身分識別卡 (NRIC) 號碼

### <a name="format"></a>格式

九個字母和數位

### <a name="pattern"></a>模式

- 九個字母和數位：
- 字母 「F」、「G」、「S」或「T」 (不區分大小寫)  
- 七位數 
- 字母檢查數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會Regex_singapore_nric找到符合模式的內容。
- 系統找到Keyword_singapore_nric關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_singapore_nric找到符合模式的內容。
- 會傳遞檢查和。

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
- 外標識號 
- 翅 
- 身份證 
- 身份證 

## <a name="slovakia-drivers-license-number"></a>斯洛伐克駕照編號

### <a name="format"></a>格式

一個字元後面接著七位數
  
### <a name="pattern"></a>模式

一個字元後面接著七位數
  
- 一個字母 (不區分大小寫的) 數位
- 七位數 
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_slovakia_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_slovakia_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver s_license_number

- vodi以sks pre可z
- vodi以ské pre可zy
- vodi以ského pre一zu
- vodi以skzch pre在一zov

## <a name="slovakia-personal-number"></a>斯洛伐克個人號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

包含選擇性反反杠的九位數或十位數
  
### <a name="pattern"></a>模式

- 代表生日的 6 位數
- 選擇性斜線 (/) 
- 3 位數
- 1 個選擇性的檢查數位
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_slovakia_eu_national_id_card` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_slovakia_eu_national_id_card` 。 
    
DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 此函數  `Func_slovakia_eu_national_id_card` 會尋找符合模式的內容。 
    
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

- asító szám
- 出生日期
- ííslo národnej identifika以nej karty
- ííslo obéianského pre一zu
- daé ííslo
- 識別碼
- 識別否
- 識別碼
- identifika以ná 一 以
- identifika以né ííslo
- 身分識別卡號碼
- 身分識別卡號碼
- národná identifika以ná zna以ka 指定
- 國家/省/市號碼
- nationalnumber#
- nemzeti személyazonosító iga使用使用
- personalidnumber#
- r已
- nelo
- é ííslo
- 社會安全號碼
- Ssn#
- Ssn
- személyi igaméy szám
- személyi igaméy száma
- személy當用用 szám
- 稅務檔案否
- 稅務檔案編號
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#

## <a name="slovakia-passport-number"></a>斯洛伐克護照號碼

### <a name="format"></a>格式

一位數或一個字母，後面接著七位數，沒有空格或分隔符號
  
### <a name="pattern"></a>模式

一位數或一個字母 (不區分大小寫) 後接七位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_slovakia_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_slovakia_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date1` 尋找 DD.MM.YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_slovakia_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_slovakia_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- ííslo pasu
- íísla pasov
- pas 以
- 傳遞 n°
- n° 傳遞區

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="slovenia-drivers-license-number"></a>斯洛洛尼亞駕照編號

### <a name="format"></a>格式

不含空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_slovenia_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_slovenia_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver s_license_number

- vozni以ko dovoljenje
- vozni以ka 以tevilka 授權
- vozni以kih dovoljenj
- 以tevilka vozni以kega dovoljenja
- 以tevilke vozni以kih dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>斯洛洛尼亞唯一主要號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

不含空格或分隔符號的 13 位數
  
### <a name="pattern"></a>模式

指定模式中 13 位數：
  
- 對應至 DDMMLLL (的七位數) ，其中 "LLL" 對應至出生日期的最後三位數 
- 對應到出生日期 "50" 區的兩位數
- 三位數對應同一天所生人士的性別與序列值組合 (男性為 000-499，女性為 500-999) 
- 一個檢查數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_slovenia_eu_national_id_card` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_slovenia_eu_national_id_card` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_slovenia_eu_national_id_card` 會尋找符合模式的內容。 
    
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

- edinsvilka g一nega dr-avljana
- em以o
- enotna maticna 以tevilka obcana
- 身份證
- 識別碼
- identifikacijska 以tevilka
- 身份證
- nacionalna 識別碼
- nacionalni potni 清單
- 國名
- osebna izkaznica
- osebni koda
- osebni ne
- osebni 以tevilka
- 個人代碼
- 個人號碼
- 個人數位代碼
- 以tevilka dr並avl表示a
- 唯一的個數
- 唯一識別碼
- 唯一身分識別號碼
- 唯一的主數
- 唯一登錄號碼
- uniqueidentityno#
- uniqueidentityno#

## <a name="slovenia-passport-number"></a>斯洛洛尼亞護照號碼

### <a name="format"></a>格式

兩個字母后面接著沒有空格或分隔符號的七位數
  
### <a name="pattern"></a>模式

兩個字母后面接著七位數：
  
- 字母 "P"
- 一個大寫字母
- 七位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_slovenia_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_slovenia_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_eu_passport_date1` 尋找 DD.MM.YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_slovenia_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_slovenia_eu_passport_number` 或找到。 
    
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
- 護照號碼
- passportnumber
- 護照號碼
- passportnumbers
- 護照號碼

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- 以tevilka potnega lista
- potek veljavnosti
- potni 清單#
- datum rojstva
- potni 清單
- 以tevilke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="slovenia-tax-identification-number"></a>斯洛洛尼亞稅務識別編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

沒有空格或分隔符號的八位數
  
### <a name="pattern"></a>模式

- 1-9 的一位數
- 六位數
- 一個檢查數位
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_slovenia_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_slovenia_eu_tax_file_number` 。 
    
DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 此函數  `Func_slovenia_eu_tax_file_number` 會尋找符合模式的內容。 
    
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

- dav以na 以tevilka
- identifikacijska 以tevilka davka
- 以tevilka dav並ne d在一起
- 稅務檔案否
- 稅務檔案編號
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#


## <a name="south-africa-identification-number"></a>南非標識號

### <a name="format"></a>格式

可能包含空格的 13 位數

### <a name="pattern"></a>模式

13 位數：
- 格式為 YYMMDD 的六位數，這是生日 
- 四位數 
- 單位數標記 
- 數位 "8" 或 "9" 
- 一位數是一個檢查碼數位

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_south_africa_identification_number找到符合模式的內容。
- 系統找到Keyword_south_africa_identification_number關鍵字。
- 會傳遞檢查和。

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
- 識別碼
- 識別 
   
## <a name="south-korea-resident-registration-number"></a>南韓居民註冊號碼

### <a name="format"></a>格式

包含連字號的 13 位數

### <a name="pattern"></a>模式

13 位數：
- 格式為 YYMMDD 的六位數，這是生日 
- 連字號 
- 一位數由世紀和性別決定 
- 四位數地區碼 
- 用來區分前述號碼相同之人的一位數 
- 一個檢查數位。

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_south_korea_resident_number找到符合模式的內容。
- 系統找到Keyword_south_korea_resident_number關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_south_korea_resident_number找到符合模式的內容。
- 會傳遞檢查和。

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
- 百分位的註冊號碼 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>西班牙駕照編號

### <a name="format"></a>格式

八位數後面接著一個字元
  
### <a name="pattern"></a>模式

八位數後面接著一個字元：
  
- 八位數 
- 一位數或一個字母 (不區分大小寫) 
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_spain_eu_driver's_license_number` 或找到。 

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 尋找符合模式的內容。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver s_license_number

- perm de conducción
- perm conducción
- licencia de cond一r
- licencia cond一r
- perm cond一r
- perm de cond一r
- permisos de cond一r
- permisos cond一r
- carnet cond一r
- carnet de cond一r
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>西班牙 DNI
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

八位數後面接著一個字元
  
### <a name="pattern"></a>模式

七位數後面接著一個字元
  
- 八位數
- 選擇性空格或連字號
- 一個檢查 (字母，不區分大小寫) 
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 尋找符合模式的內容。 
- 找到關鍵字  `Keywords_spain_eu_national_id_card"` 。 

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 尋找符合模式的內容。 

    
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
- 國家身分識別
- nationalid#
- nationalidno#
- 聶#
- 聶
- nienúmero#
- número de identificación
- número nacional identidad
- 個人識別碼
- 個人身分識別否
- 唯一身分識別號碼
- uniqueid#

## <a name="spain-passport-number"></a>西班牙護照號碼

### <a name="format"></a>格式

字母和數位的八個字元或九個字元組合，沒有空格或分隔符號
  
### <a name="pattern"></a>模式

由八個字元或九個字元所組合的字母和數位：
  
- 兩位數或兩個字母 
- 一位數或一個字母 (選填) 
- 六位數
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會  `Regex_spain_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_spain_eu_passport_number` 或找到。 
- 正則運算式會 `Regex_spain_eu_passport_date` 尋找 DD-MM-YYYY 格式的日期，或找到 `Keywords_eu_passport_date` 關鍵字

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_spain_eu_passport_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_passport_number` `Keywords_spain_eu_passport_number` 或找到。
    
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
- 護照號碼
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
- pasaporte no
- 傳遞 n°
- n° 傳遞區
- pasaporte no.
- pasaporte n°
- 西班牙護照

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 發行日期
- 到期日


## <a name="spain-social-security-number-ssn"></a>西班牙社會安全號碼 (SSN) 

### <a name="format"></a>格式

11-12 位數

### <a name="pattern"></a>模式

11-12 位數：
- 兩位數 
- 斜線 (選填)  
- 七到八位數 
- 斜線 (選填)  
- 兩位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_spanish_social_security_number找到符合模式的內容。
- 會傳遞檢查和。

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

## <a name="spain-tax-identification-number"></a>西班牙稅務識別號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

指定模式中七位或八位數，以及一或兩個字母
  
### <a name="pattern"></a>模式

具有西班牙國家身分識別卡的西班牙文自然人員：
  
- 八位數 
- 一個大小寫字母 (區分大小寫的)  
    
沒有西班牙身分識別卡的非居民
  
- 一個大小寫字母"L" (區分大小寫的) 
- 七位數
- 一個大小寫字母 (區分大小寫的)  
    
沒有西班牙身分識別卡且年齡不足 14 歲之居民.
  
- 一個大小寫字母"K" (區分大小寫的) 
- 七位數 
- 一個大小寫字母 (區分大小寫的) 
    
有百分位的識別號碼的人
  
- 這是區分大小寫的一個大寫字母「X」、「Y」或「Z」 (大寫)  
- 七位數
- 一個大小寫字母 (區分大小寫的)  
    
沒有百分位人士識別號碼的號碼
  
- 一個大小寫為「M」的字母， (區分大小寫的)  
- 七位數
- 一個大小寫字母 (區分大小寫的)  
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數  `Func_spain_eu_tax_file_number` 或 `Func_spain_eu_DL_and_NI_number_citizen` 尋找符合模式的內容。 
- 找到關鍵字  `Keywords_spain_eu_tax_file_number` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數  `Func_spain_eu_tax_file_number` 或 `Func_spain_eu_DL_and_NI_number_citizen` 尋找符合模式的內容。 
    
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
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid#
- spanishcifid
- spanishcifno#
- spanishcifno
- 稅務檔案否
- 稅務檔案編號
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#


## <a name="sql-server-connection-string"></a>SQL Server 連接字串

### <a name="format"></a>格式

字串「使用者識別碼」、「使用者識別碼」、「uid」或「UserId」，後面接著下圖中概述的字元和字串。

### <a name="pattern"></a>模式

- 字串 "User Id"、"User ID"、"uid" 或 "UserId"
- 1-200 個上下字母、數位、符號、特殊字元或空格之間的任何組合
- 字串 "Password" 或 "pwd"，其中 "pwd" 前面沒有小寫字母
- 等號 (=) 
- 任何不是貨幣符號的字元 ($) 、百分比符號 (%) 、大於符號 (>) 、符號 (@) 、引號 (") 、分號 (;) 、左大括弧 ([) 或左中括弧 ({) 
- 任何 7-128 個字元的組合，不是分號 (;) 、斜線 (/) 或引號 (") 
- 分號 (;) 引號 (") 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 正則運算式會CEP_Regex_SQLServerConnectionString找到符合模式的內容。
- 找不到您CEP_GlobalFilter **關鍵字** 。
- 正則運算式 **CEP_PasswordPlaceHolder找不到符合** 模式的內容。
- 正則運算式 **CEP_CommonExampleKeywords找不到符合** 模式的內容。

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

 (請注意，就技術上來說，這種敏感性資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。) 

- 密碼或 pd 後面接著 0-2 個空格、等號 (=) 、0-2 個空格，以及一個星號 (*) --OR--
- 密碼或 ppd 後面接著：
    - 等號 (=) 
    - 小於符號 (<) 
    - 任何由 1-200 個字元組合成大寫或小寫字母、數位、星號 (*) 、連字號 (-) 、 (_) 或空白字元
    - 大於符號 (>) 

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

 (請注意，就技術上來說，這種敏感性資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。) 

- contoso
- fabrikam
- 北風
- 沙 箱
- onebox
- 本地 主機
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int。<!--no-hyperlink-->網

## <a name="sweden-drivers-license-number"></a>瑞典駕照編號

### <a name="format"></a>格式

包含連字號的十位數
  
### <a name="pattern"></a>模式

包含連字號的十位數：
  
- 六位數 
- 連字號
- 四位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會  `Regex_sweden_eu_driver's_license_number` 尋找符合模式的內容。 
- 關鍵字來自  `Keywords_eu_driver's_license_number` `Keywords_sweden_eu_driver's_license_number` 或找到。 
    
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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式
- 驅動程式
- 驅動程式資料
- 驅動程式
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式許可證
- 驅動程式授權
- 驅動程式授權
- 驅動程式授權
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式許可證
- 驅動程式許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- 驅動程式 Slic
- 驅動程式 Slics
- 驅動程式的許可證
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式的分割區
- 驅動程式許可證
- 驅動程式的許可證
- 駕照
- 驅動程式授權
- 駕照
- 駕照
- Dl#
- Dls#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 驅動程式#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式資料#
- 驅動程式#
- 驅動程式許可證#
- 驅動程式許可證#
- 驅動程式授權#
- 驅動程式授權#
- 驅動程式授權#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式許可證#
- 驅動程式許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 驅動程式 Slic#
- 驅動程式 Slics#
- 驅動程式的許可證#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式的分割區#
- 驅動程式許可證#
- 驅動程式的許可證#
- 駕照#
- 驅動程式授權#
- 駕照#
- 駕照#
- 駕照 
- 駕照
- dlno#
- 使用時，會一次刪除
- 一些細明的利器
- 時，會獲得授權
- 使用者授權
- 已授權
- 已授權
- 驅動程式設計
- 驅動程式限制
- 驅動程式的系統管理
- 駕駛許可證
- 駕駛者就位
- 駕駛授權
- 駕照
- 駕照
- 駕駛許可證
- dl 否
- dlno
- dl number


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver s_license_number

- ajokortti
- permis de conducere
- ajokortin numero
- Kuljettajat lic.
- 驅動程式許可證。
- Körkort
- num並rul permis一i de conducere
-  שאָפער דערלויבעניש נומער
- fö一e lic.
-  דריווערס דערלויבעניש
- Körkortsnummer

## <a name="sweden-national-id"></a>瑞典國識別碼

### <a name="format"></a>格式

十位數或 12 位數以及選擇性分隔符號

### <a name="pattern"></a>模式

十位數或 12 位數以及選擇性分隔符號：
- 兩位數 (選)  
- 日期格式 YYMMDD 的六位數 
- 選擇性選項之 "-" 或 "+" (分隔) 
- 四位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數 `Func_swedish_national_identifier` 會尋找符合模式的內容。
- 找到 `Keywords_swedish_national_identifier` 關鍵字
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數 `Func_swedish_national_identifier` 會尋找符合模式的內容。
- 會傳遞檢查和。


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

- 識別碼否
- 識別碼
- Id#
- 識別否
- 識別碼
- identifidentationsnumret#
- identifidentationsnumret
- 身分驗證
- 身分識別檔
- 身分識別否
- 身分識別號碼
- id-nummer
- 個人識別碼
- personnummer#
- personnummer
- skatteidentifidentationsnummer
   
## <a name="sweden-passport-number"></a>瑞典護照號碼
此敏感性資訊類型實體包含在歐盟護照號碼敏感性資訊類型中，而且可做為獨立的敏感性資訊類型實體使用。

### <a name="format"></a>格式

八位數

### <a name="pattern"></a>模式

八個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_sweden_passport_number找到符合模式的內容。
- 下列其中一個條件成立：
    - 找到您Keyword_passport關鍵字。
    - 找到您Keyword_sweden_passport關鍵字。

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

- 護照需求 
- 大本註冊卡 
- 百分卡 
- 百分卡 
- Visa Processing 
- Visa 類型 
- 單一專案 
- 多個專案 
- G3 處理費用 

#### <a name="keyword_passport"></a>Keyword_passport

- 護照號碼 
- 護照號碼 
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
- 傳遞 n ° 
- Passeport Non 
- 傳遞區# 
- 傳遞區# 
- PasseportNon 
- 傳遞區 ° 


## <a name="sweden-tax-identification-number"></a>瑞典稅務識別編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

指定圖樣中的十位數和符號
  
### <a name="pattern"></a>模式

十位數和一個符號：
  
- 對應至 YYMMDD (的六位數)  
- 加號或減號
- 讓識別號碼獨一無二的三位數： 
  - 對於 1990 之前所發行的數位，第七位數和第八位數會指出出生日期或外縣/市
  - 第九個位置的位數會以奇數表示男性或甚至女性
- 一個檢查數位
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 此函數  `Func_sweden_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_sweden_eu_tax_file_number` 。 
    
DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_sweden_eu_tax_file_number` 會尋找符合模式的內容。 
    
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

- 個人識別碼
- personnummer
- skatt id nummer
- skatt identifidentation
- skatteBetalarens identifidentationsnummer
- Sverige tin
- 稅務檔案
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#


## <a name="swift-code"></a>SWIFT 代碼

### <a name="format"></a>格式

四個字母，後面接著 5-31 個字母或數位

### <a name="pattern"></a>模式

四個字母，後面接著 5-31 個字母或數位：
- 四個字母的銀行帳戶 (大小寫不區分)  
- 一個選擇性空格 
- BBAN (基本銀行帳戶號碼 (4-28) )  
- 一個選擇性空格 
- BBAN (餘數的 1 到 3) 

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_swift找到符合模式的內容。
- 系統找到Keyword_swift關鍵字。

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

- 國際標準組織 9362
- iso 9362
- iso9362
- 迅速#
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift 代碼
- swift 號碼#
- swift 路由號碼
- bic number
- bic 代碼
- bic#
- bic#
- 銀行識別碼代碼
- 國際取消標準 9362
- rapide#
- 代碼 SWIFT
- le numéro de swift
- swift numéro d'aineinement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFTコード
- SWIFT 番號
- BIC 番號
- BICコード
- SWIFT コード
- SWIFT 番號
- BIC 番號
- BIC コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>瑞士 SSN AHV 號碼
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

13 位數號碼

### <a name="pattern"></a>模式

13 位數號碼：

- 三位數 - 756
- 選擇性的點
- 四位數
- 選擇性的點
- 四位數
- 選擇性的點
- 兩位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_swiss_social_security_number_ahv找到符合模式的內容。
- 系統找到Keywords_swiss_social_security_number_ahv關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_swiss_social_security_number_ahv找到符合模式的內容。

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
- 個人識別碼
- 個人識別碼。
- insuranceno#
- uniqueidno#
- 唯一識別否。
- avs number
- 個人身分識別沒有 versicherungsnummer
- identifidentationsnummer
- 以igige identität ni一一
- sozialversicherungsnummer
- 識別碼
- numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>臺灣國標識號

### <a name="format"></a>格式

一個字母 (英文) 後面接著九位數

### <a name="pattern"></a>模式

一個字母 (英文) 後面接著九位數：
- 一個字母 (英文，不區分大小寫)  
- 數位 "1" 或 "2" 
- 八位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_taiwanese_national_id找到符合模式的內容。
- 系統找到Keyword_taiwanese_national_id關鍵字。
- 會傳遞檢查和。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_taiwanese_national_id找到符合模式的內容。
- 會傳遞檢查和。

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

- 護照號碼：九位數
- 非護照號碼：九位數

### <a name="pattern"></a>模式
護照號碼：
- 字元 "3" 
- 八位數

非護照號碼：
- 九位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_taiwan_passport找到符合模式的內容。
- 系統找到Keyword_taiwan_passport關鍵字。

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

- 公司護照號碼 
- 護照號碼 
- 護照號碼 
- Passport Num 
- 護照# 
- 護照 
- 中華民國護照 
- Zhzhnghuá Mzhguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>臺灣居民憑證 (ARC/TARC) 號碼

### <a name="format"></a>格式

十個字母和數位

### <a name="pattern"></a>模式

十個字母和數位：
- 兩個字母 (不區分大小寫)  
- 八位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_taiwan_resident_certificate找到符合模式的內容。
- 系統找到Keyword_taiwan_resident_certificate關鍵字。

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

- 居住憑證 
- 居住認證 
- 居住認證。 
- 識別卡 
- 因此，系統也提供居住憑證 
- ARC 
- 臺灣地區居民證書 
- TARC 
- 居留證 
- 外僑居留證 
- 台灣地區居留證 

## <a name="thai-population-identification-code"></a>泰文人口識別碼

### <a name="format"></a>格式

13 位數

### <a name="pattern"></a>模式

13 位數：
- 第一位數不是零或九 
- 12 位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_Thai_Citizen_Id找到符合模式的內容。
- 系統找到Keyword_Thai_Citizen_Id關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_Thai_Citizen_Id找到符合模式的內容。

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
  
## <a name="turkish-national-identification-number"></a>土耳其文國家識別號碼

### <a name="format"></a>格式

11 位數

### <a name="pattern"></a>模式

11 位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_Turkish_National_Id找到符合模式的內容。
- 系統找到Keyword_Turkish_National_Id關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_Turkish_National_Id找到符合模式的內容。

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

- TC Kim會否
- TC Kim一 nu使用s
- Vatanda您用的圖說
- Vatanda與 no

## <a name="uk-drivers-license-number"></a>英國。 駕照編號
此敏感性資訊類型實體包含在歐盟駕照編號敏感性資訊類型中，且可做為獨立敏感性資訊類型實體使用。

### <a name="format"></a>格式

以指定格式結合 18 個字母和數位

### <a name="pattern"></a>模式

18 個字母和數位：
- 五個字母 (不區分大小寫) 或數位 "9" 來表示字母 
- 一位數 
- 如果驅動程式是女性 (，即 51 到 62，而不是 01 到 12) 
- 兩個字母 (不區分大小寫) 或數位 "9" 來表示字母 
- 五位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_uk_drivers_license找到符合模式的內容。
- 系統找到Keyword_uk_drivers_license關鍵字。
- 會傳遞檢查和。

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
- 淺色車 
- 四邊形 
- 車用車 
- 125cc 
- side轉場 
- 三輪車 
- 摩托車 
- photocard 授權 
- 學習者驅動程式 
- 授權擁有者 
- 授權擁有者 
- 駕照 
- 駕照 
- 雙重控制車 
   
## <a name="uk-electoral-roll-number"></a>英國。 側卷號

### <a name="format"></a>格式

兩個字母，後面接著 1 到 4 位數

### <a name="pattern"></a>模式

兩個字母 (不區分大小寫) 後面接著 1 到 4 個數字

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_uk_electoral找到符合模式的內容。
- 系統找到Keyword_uk_electoral關鍵字。

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

- 部所長 
- 百分位表單 
- 您註冊的 
- 側卷

   
## <a name="uk-national-health-service-number"></a>英國。 國家健康服務編號

### <a name="format"></a>格式

以空格分隔的 10-17 位數

### <a name="pattern"></a>模式

10-17 位數：
- 三位數或十位數 
- 一個空格 
- 三位數 
- 一個空格 
- 四位數

### <a name="checksum"></a>校驗

是

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_uk_nhs_number找到符合模式的內容。
- 下列其中一個條件成立：
    - 系統找到Keyword_uk_nhs_number關鍵字。
    - 系統找到Keyword_uk_nhs_number1關鍵字。
    - 系統找到Keyword_uk_nhs_number_dob關鍵字。
- 會傳遞檢查和。

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

- 國家健康服務 
- Nhs 
- 健康服務授權 
- 健康授權

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- 病患識別碼 
- 病患識別 
- 病患否 
- 病患編號

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- Gp 
- DOB 
- D.O.B 
- 出生日期 
- 出生日期 
   
## <a name="uk-national-insurance-number-nino"></a>英國。 國家保險編號 (NINO) 
此敏感性資訊類型實體包含在 EU National Identificaiton 數位敏感性資訊類型中，而且可做為獨立的敏感性資訊類型實體使用。

### <a name="format"></a>格式

以空格或虛線分隔的七個字元或九個字元

### <a name="pattern"></a>模式

兩種可能的模式：

- 兩個字母 (有效的 NINOS 只會使用此首碼中的特定字元，此模式會驗證此字元;不區分大小寫) 
- 六位數
- 如前詞一樣使用 'A'、'B'、C 或 'D' (，尾碼中只允許特定字元;不區分大小寫) 

OR

- 兩個字母
- 空格或破折號
- 兩位數
- 空格或破折號
- 兩位數
- 空格或破折號
- 兩位數
- 空格或破折號
- 可以是 'A'、'B'、'C' 或 'D'

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_uk_nino找到符合模式的內容。
- 系統找到Keyword_uk_nino關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_uk_nino找到符合模式的內容。

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

- 國家保險號碼
- 國家保險捐贈
- 保護法
- 保險
- 社會安全號碼
- 保險申請
- 醫療申請
- 社會保險
- 醫療護理
- 社會保障
- 英國
- NI Number
- NI No.
- 鎳#
- 鎳#
- 保險#
- insurancenumber
- nationalins以#
- nationalins一number

    
## <a name="uk-unique-taxpayer-reference-number"></a>英國。 唯一的稅務參考編號
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

不含空格和分隔符號的 10 位數
 
  
### <a name="pattern"></a>模式

10 位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 此函數  `Func_uk_eu_tax_file_number` 會尋找符合模式的內容。 
- 找到關鍵字  `Keywords_uk_eu_tax_file_number` 。 
    
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

- 稅號
- 稅務檔案
- 稅務識別碼
- 稅務識別否
- 稅務識別編號
- 稅號#
- 稅號
- 稅務註冊編號
- 已刪除#
- 已發想#
- ，並#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- 錫#

## <a name="us-bank-account-number"></a>美國銀行帳戶號碼

### <a name="format"></a>格式

6-17 位數

### <a name="pattern"></a>模式

6-17 個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 正則運算式會Regex_usa_bank_account_number找到符合模式的內容。
- 系統找到Keyword_usa_Bank_Account關鍵字。

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
- 檢查 Acct 號碼 
- 檢查 Acct# 
- 檢查 Acct 否。 
- 檢查帳戶號。 
- 銀行帳戶號碼 
- 銀行帳戶# 
- 銀行 Acct 號碼 
- Bank Acct# 
- Bank Acct No. 
- 銀行帳戶號。 
- 存款帳戶號碼 
- 儲蓄帳戶。 
- 儲蓄帳戶# 
- 儲蓄帳戶號碼 
- 儲蓄帳戶# 
- 儲蓄帳戶否。 
- 儲蓄帳戶號。 
- 轉帳帳戶號碼 
- 轉帳帳戶 
- 轉帳帳戶# 
- 轉帳卡號碼 
- 轉帳帳戶# 
- 轉帳帳戶否。 
- 轉帳帳戶否。 

## <a name="us-drivers-license-number"></a>美國駕照編號

### <a name="format"></a>格式

依省/市

### <a name="pattern"></a>模式

取決於州/省，例如紐約：
- 格式為 ddd ddd d 的九位數會相符。
- 九位數 ，例如 dddd 不相符。

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_new_york_drivers_license_number找到符合模式的內容。
- 系統找到 Keyword_[state_name]_drivers_license_name關鍵字。
- 系統找到Keyword_us_drivers_license關鍵字。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數函數Func_new_york_drivers_license_number找到符合模式的內容。
- 系統找到 Keyword_[state_name]_drivers_license_name關鍵字。
- 系統找到Keyword_us_drivers_license_abbreviations關鍵字。
- 找不到來自Keyword_us_drivers_license關鍵字。

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
- 識別碼 
- Id 
- Dl# 
- Dls# 
- 民盟# 
- CDLS# 
- Id#
- Id# 
- 識別碼 
- 識別碼 
- LIC 
- LIC# 

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- 驅動程式許可證 
- 驅動程式許可證 
- 驅動程式許可證 
- 駕照 
- 驅動程式授權 
- DriversLic 
- DriversLics 
- DriversLicense 
- 驅動程式許可證 
- 驅動程式 Lic 
- 驅動程式 Lics 
- 驅動程式授權 
- 驅動程式授權 
- 驅動程式許可證 
- 驅動程式許可證 
- 駕照 
- 驅動程式授權 
- 驅動程式許可證 
- 驅動程式許可證 
- 駕照 
- 驅動程式授權
- 驅動程式 SLic 
- 驅動程式 SLics 
- 驅動程式的許可證 
- 驅動程式的許可證 
- 驅動程式許可證 
- 驅動程式的許可證 
- 駕照 
- 驅動程式授權 
- 識別碼 
- 識別碼 
- 識別# 
- 身份證 
- 身份證 
- 識別卡 
- 身份證 
- DriverLic# 
- DriverLics# 
- DriverLicense# 
- 驅動程式許可證# 
- 驅動程式許可證# 
- 驅動程式許可證# 
- 駕照# 
- 驅動程式授權# 
- DriversLic# 
- DriversLics# 
- DriversLicense# 
- 驅動程式許可證# 
- 驅動程式 Lic# 
- 驅動程式 Lics# 
- 驅動程式授權# 
- 驅動程式授權# 
- 驅動程式許可證# 
- 驅動程式許可證# 
- 駕照# 
- 驅動程式授權# 
- 驅動程式許可證# 
- 驅動程式許可證# 
- 駕照# 
- 驅動程式授權# 
- 驅動程式 SLic# 
- 驅動程式 SLics# 
- 驅動程式的許可證# 
- 驅動程式的許可證# 
- 驅動程式許可證# 
- 驅動程式的許可證# 
- 駕照# 
- 驅動程式授權# 
- 身份證# 
- 身份證# 
- 識別卡# 
- 身份證# 


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- 州名縮寫 (例如"NY")  
- 州名 (例如「紐約」) 

## <a name="us-individual-taxpayer-identification-number-itin"></a>ITIN (美國 (稅務) 

### <a name="format"></a>格式

以 "9" 開頭且包含 "7" 或 "8" 做為第四位數的九位數，可選擇性地格式化為空格或虛線

### <a name="pattern"></a>模式

格式 化：
- 數位 "9" 
- 兩位數 
- 空格或破折號 
- "7" 或 "8" 
- 一位數 
- 空格或破折號 
- 四位數

未格式化：
- 數位 "9" 
- 兩位數 
- "7" 或 "8" 
- 五位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_formatted_itin找到符合模式的內容。
- 系統找到Keyword_itin關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_unformatted_itin找到符合模式的內容。
- 系統找到Keyword_itin關鍵字。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數會Func_formatted_itin或Func_unformatted_itin尋找符合模式的內容。

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
- 稅務識別碼 
- 稅務識別 
- itin 
- i.t.i.n.
- Ssn 
- 錫 
- 社會保障 
- 納稅人 
- itins 
- 已刪除 
- 個人稅務 


## <a name="us-social-security-number-ssn"></a>美國社會安全號碼 (SSN) 

### <a name="format"></a>格式

九位數，可能是格式已格式化或未格式化的圖樣

> [!NOTE]
> 如果在 2011 年中之前發行，SSN 具有強大的格式，其中數位的某些部分必須落在特定範圍內才能有效 (但沒有檢查) 。

### <a name="pattern"></a>模式

四個函數會以四種不同的模式尋找 SSN：
- Func_ssn SSN 具有 2011 之前強式格式，格式已格式化為虛線或空格 (ddd-dd-dd OR ddd dd dd) 
- Func_unformatted_ssn 2011 之前格式未格式化為九位數的 SSN (ddddd) 
- Func_randomized_formatted_ssn會找出格式為虛線或空格的 2011 後 SSN (ddd-dd OR ddd dd dd) 
- Func_randomized_unformatted_ssn 2011 後 SSN 會找出未格式化為九位數的連續數位 (dddd) 

### <a name="checksum"></a>校驗

否


### <a name="definition"></a>定義

DLP 政策在鄰近 300 個字元時，會非常信賴地偵測到這類敏感性資訊：
- 函數函數Func_ssn找到符合模式的內容。
- 系統找到Keyword_ssn關鍵字。

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_unformatted_ssn找到符合模式的內容。
- 系統找到Keyword_ssn關鍵字。

DLP 政策在鄰近 300 個字元時，可偵測到這類敏感性資訊的信賴度較低：
- 函數函數Func_randomized_formatted_ssn找到符合模式的內容。
- 系統找到Keyword_ssn關鍵字。

如果鄰近 300 個字元，DLP 政策 55% 可確信它可偵測到這類敏感性資訊：
- 函數函數Func_randomized_unformatted_ssn找到符合模式的內容。
- 系統找到Keyword_ssn關鍵字。


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

- SSA 號碼
- 社會安全號碼
- 社會保障#
- 社會保障#
- 社會安全否
- 社會保障#
- Soc Sec
- Ssn
- SSNS
- Ssn#
- SS#
- Ssid
   
## <a name="us--uk-passport-number"></a>美國/英國 護照號碼
英國 護照號碼的敏感性資訊類型實體可在歐盟護照號碼敏感性資訊類型中提供，並做為獨立的敏感性資訊類型實體使用。

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九個連續數位

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- 函數函數Func_usa_uk_passport找到符合模式的內容。
- 系統找到Keyword_passport關鍵字。

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
- 護照號碼 
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
- 傳遞 n ° 
- Passeport Non 
- 傳遞區# 
- 傳遞區# 
- PasseportNon 
- 傳遞區 ° 

## <a name="ukraine-passport-domestic"></a>烏克蘭護照國內
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

九位數

### <a name="pattern"></a>模式

九位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- RegEx 索引Regex_Ukraine_Passport_Domestic找到符合模式的內容。
- 系統找到Keyword_Ukraine_Passport_Domestic關鍵字。

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
- 護照號碼
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>烏克蘭護照國際
此敏感性資訊類型僅適用于：
- 資料外遺失防護政策
- 通訊合規性政策
- 資訊管理
- 記錄管理
- Microsoft 雲端 App 安全性

### <a name="format"></a>格式

八個字元的 Alphanumeric 模式

### <a name="pattern"></a>模式

八個字元的 Alphanumeric 模式：
- 兩個字母或數位
- 六位數

### <a name="checksum"></a>校驗

否

### <a name="definition"></a>定義

DLP 策略在鄰近 300 個字元時，有中度信賴度可偵測到這類敏感性資訊：
- RegEx Regex_Ukraine_Passport_International找到符合模式的內容。
- 系統找到Keyword_Ukraine_Passport_International關鍵字。

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
- 護照號碼
- паспорт України
- номер паспорта