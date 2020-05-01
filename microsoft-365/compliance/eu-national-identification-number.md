---
title: 歐盟國身分識別號碼
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題說明資料遺失防護（DLP）原則在偵測到歐盟國身分識別號碼的敏感資訊類型時，會尋找哪些專案。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
ms.openlocfilehash: c83644fc8870975634651e44e114f2a8e0cf7692
ms.sourcegitcommit: a2dd93943f68362220b123e3e4b0f7b3facbdd03
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2020
ms.locfileid: "43955300"
---
# <a name="eu-national-identification-number"></a>歐盟國身分識別號碼

本主題說明資料遺失防護（DLP）原則在偵測到歐盟國身分識別號碼的敏感資訊類型時，會尋找哪些專案。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
  
## <a name="austria"></a>奧地利

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
  
- 正則運算式`Regex_austria_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_austria_eu_national_id_card`的關鍵字。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

奧地利身分識別號碼
  
本國身分識別號碼
  
身分識別號碼
  
國家識別碼
  
personalausweis republik österreich
  
## <a name="belgium"></a>比利時

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「比利時國家編號」一節。
  
## <a name="bulgaria"></a>保加利亞

### <a name="format"></a>格式

10位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

10位數，不含空格及分隔符號
  
-  與出生日期對應的六位數（YYMMDD） 
    
- 對應至出生順序的兩位數
    
- 對應于性別的一個數位：用於男的偶數位數和用於女的奇數數位
    
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_bulgaria_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_bulgaria_national_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_bulgaria_eu_national_id_card`會找到符合模式的內容。 
    
```
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

egn
  
egn#
  
保加利亞國號碼
  
國家/地區號碼
  
社會安全號碼
  
nationalnumber#
  
Ssn#
  
Ssn
  
nationalnumber
  
安娜#
  
安娜
  
個人號碼
  
personalidnumber#
  
единен граждански номер
  
edinen grazhdanski nomer
  
егн
  
егн#
  
## <a name="croatia"></a>克羅埃西亞

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「克羅地亞身分識別號碼」一節。
  
## <a name="cyprus"></a>賽普勒斯

### <a name="format"></a>格式

10位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 10位數 
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_cyprus_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_cyprus_eu_national_id_card`的關鍵字。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

id 卡號碼
  
國家識別號碼
  
個人號碼
  
身分識別卡號碼
  
ταυτοτητασ
  
## <a name="czech-republic"></a>捷克共和國

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「捷克國身分識別號碼」一節。
  
## <a name="denmark"></a>丹麥

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「丹麥個人身分識別號碼」一節。
  
## <a name="estonia"></a>愛沙尼亞

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
  
- 函數`Func_estonia_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_estonia_eu_national_id_card`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_estonia_eu_national_id_card`會找到符合模式的內容。 
    
```
 
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

個人身分識別碼
  
個人身分識別號碼
  
國家識別號碼
  
國家/地區號碼
  
個人號碼
  
personalidnumber#
  
益
  
isikukood
  
識別碼-kaart
  
## <a name="finland"></a>芬蘭

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「芬蘭國 ID」一節。
  
## <a name="france"></a>法國

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「法國全國身分識別卡（CNI）」一節。
  
## <a name="germany"></a>德國

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「德國身分識別卡片編號」一節。
  
## <a name="greece"></a>希臘

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「希臘國 ID 卡」一節。
  
## <a name="hungary"></a>匈牙利

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
  
- 函數`Func_hungary_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_hungary_eu_national_id_card`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_hungary_eu_national_id_card`會找到符合模式的內容。 
    
```
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

個人身分識別號碼
  
識別號碼
  
個人號碼
  
személyazonosító igazolvány
  
## <a name="ireland"></a>愛爾蘭

### <a name="format"></a>格式

在指定的模式中，字母、數位及空格的九個字元組合
  
### <a name="pattern"></a>模式

在指定的模式中，字母、數位及空格的九個字元組合
  
從01年1月2013至現在：
  
-  七位數 
    
- 一個檢查碼
    
- 一個空格或大寫字母 "W" （區分大小寫）
    
在2013年1月1日之前：
  
-  七位數 
    
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
    
```
 
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

個人公開服務號碼
  
pps 否
  
收入與社交保險號碼
  
rsi 否
  
個人身分識別號碼
  
識別號碼
  
個人號碼
  
uimhir phearsanta seirbhíse poiblí
  
uimh. Psp
  
## <a name="italy"></a>義大利

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
  
- 函數`Func_italy_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_italy_eu_national_id_card`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_italy_eu_national_id_card`會找到符合模式的內容。 
    
```
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

個人程式碼
  
個人碼編號
  
個人憑證號碼
  
會計代碼
  
personalcodeno#
  
個人號碼
  
個人識別碼代碼
  
codice personale
  
numero certificato personale
  
numero personale
  
numero 識別碼 personale
  
codice 識別碼 personale
  
codice fiscale
  
## <a name="latvia"></a>拉脫維亞

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
  
- 函數`Func_latvia_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_latvia_eu_national_id_card`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_latvia_eu_national_id_card`會找到符合模式的內容。 
    
```
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

個人程式碼
  
個人碼編號
  
個人憑證號碼
  
personalcodeno#
  
個人號碼
  
個人識別碼代碼
  
角色 kods
  
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

11位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

11位數，不含空格及分隔符號：
  
- 對應至人員性別和出生世紀的一個數位
    
-  對應至出生日期的六位數（YYMMDD） 
    
- 對應至出生日期之序號的三位數
    
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_lithuania_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_lithuania_eu_national_id_card`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_lithuania_eu_national_id_card`會找到符合模式的內容。 
    
```
 
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

個人數位代碼
  
唯一識別碼
  
公民服務號碼
  
唯一的身分識別號碼
  
uniqueidentityno#
  
個人程式碼。
  
asmeninis skaitmeninis kodas
  
unikalus identifikavimo numeris
  
piliečio paslaugos numeris
  
unikalus identifikavimo kodas
  
asmens kodas.
  
## <a name="luxemburg"></a>盧森堡

### <a name="format"></a>格式

11位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

11位數
  
- 對應至人員性別和出生世紀的一個數位
    
-  對應至出生日期的六位數（YYMMDD） 
    
- 對應至出生日期之序號的三位數
    
- 一個檢查碼
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_luxemburg_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_luxemburg_eu_national_id_card`的關鍵字。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

個人識別碼
  
個人號碼
  
personalidno#
  
唯一識別碼
  
personalidnumber#
  
唯一識別碼機碼
  
個人識別碼代碼
  
uniqueidkey#
  
個別程式碼
  
個別識別碼
  
eindeutige id-nummer
  
eindeutige 識別碼
  
識別碼 personnelle
  
numéro d'identification 人員
  
idpersonnelle#
  
persönliche identifikationsnummer
  
eindeutigeid#
  
## <a name="malta"></a>馬爾他

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
  
- 正則運算式`Regex_malta_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_malta_eu_national_id_card`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：
  
- 正則運算式`Regex_malta_eu_national_id_card`會找到符合模式的內容。 
    
```
 
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

個人數位代碼
  
唯一識別碼
  
公民服務號碼
  
唯一的身分識別號碼
  
uniqueidentityno#
  
kodiċi numerali personali
  
numru ta ' identifikazzjoni uniku
  
numru tas-servizz taċ-ċittadin
  
numru ta ' identità uniku
  
## <a name="netherlands"></a>荷蘭

### <a name="format"></a>格式

九位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_netherlands_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自的關鍵字。
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_netherlands_eu_national_id_card`會找到符合模式的內容。 
    
```
 
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

個人數位代碼
  
唯一識別碼
  
公民服務號碼
  
唯一的身分識別號碼
  
uniqueidentityno#
  
bsn
  
bsn#
  
persoonlijke numerieke 程式碼
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>波蘭

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「波蘭國家識別碼（PESEL）」一節。
  
## <a name="portugal"></a>葡萄牙

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「葡萄牙公民卡片編號」一節。
  
## <a name="romania"></a>羅馬尼亞

### <a name="format"></a>格式

13位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

13位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_romania_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_romania_eu_national_id_card`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_romania_eu_national_id_card`會找到符合模式的內容。 
    
```
 
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

個人數位代碼
  
唯一識別碼
  
Cnp
  
Cnp#
  
針
  
針#
  
保險號碼
  
insurancenumber#
  
唯一的身分識別號碼
  
uniqueidentityno#
  
貨到數值的個人
  
identificare 個人
  
貨至 unic identificare
  
număr 個人 unic
  
număr identitate
  
număr identificare 個人
  
număridentitate#
  
codnumericpersonal#
  
numărpersonalunic#
  
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

10位數包含一個反斜線
  
### <a name="pattern"></a>模式

10位數包含一個反斜線：
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_slovakia_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_slovakia_eu_national_id_card`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_slovakia_eu_national_id_card`會找到符合模式的內容。 
    
```
 
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

出生號碼
  
國家識別號碼
  
個人身分識別號碼
  
社會安全號碼
  
nationalnumber#
  
Ssn#
  
Ssn
  
國家/地區號碼
  
個人號碼
  
personalidnumber#
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="slovenia"></a>斯洛維尼亞

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
  
- 函數`Func_slovenia_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_slovenia_eu_national_id_card`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_slovenia_eu_national_id_card`會找到符合模式的內容。 
    
```
 
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

個人數位代碼
  
唯一識別碼
  
唯一註冊號碼
  
唯一的身分識別號碼
  
uniqueidentityno#
  
唯一主公民號碼
  
edinstvena identifikacijska številka
  
uniqueidentityno#
  
edinstvena številka glavnega državljana
  
emšo
  
## <a name="spain"></a>西班牙

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
  
- 正則運算式`Regex_spain_eu_national_id_card`會找到符合模式的內容。 
    
- 找到來自`Keywords_spain_eu_national_id_card"`的關鍵字。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

dni
  
國家識別號碼
  
本國身分識別號碼
  
保險號碼
  
個人身分識別號碼
  
本國身分識別
  
個人身分識別
  
唯一的身分識別號碼
  
nationalidno#
  
uniqueid#
  
dni#
  
nationalid#
  
聶#
  
聶
  
nienúmero#
  
nie número
  
documento nacional de identidad
  
identidad único
  
número nacional identidad
  
dni número
  
dninúmero#
  
identidadúnico#
  
## <a name="sweden"></a>瑞典

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「瑞典全國識別碼」一節。
  
## <a name="see-also"></a>另請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

