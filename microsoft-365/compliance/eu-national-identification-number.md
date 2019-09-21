---
title: 歐盟國家識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟國民身分識別號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: cbcacb3f85877f5a84238468fb52d612d90f5f0b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077073"
---
# <a name="eu-national-identification-number"></a>歐盟國家識別碼

本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟國民身分識別號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

24 個字元組合的字母、 數字和特殊字元
  
### <a name="pattern"></a>模式

24 個字元：
  
-  22 字母 （不區分大小寫）、 數字、 反斜線、 正斜線或加號 
    
- 兩個字母 （不區分大小寫）、 數字、 反斜線、 正斜線、 加號或等號
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_austria_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_austria_eu_national_id_card`找到。 
    
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
  
國民身分識別號碼
  
身分識別號碼
  
國民身分證
  
personalausweis republik österreich
  
## <a name="belgium"></a>比利時

如需詳細資訊，請參閱 「 比利時國民編碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="bulgaria"></a>保加利亞

### <a name="format"></a>格式

如果沒有空格和分隔符號十位數
  
### <a name="pattern"></a>模式

如果沒有空格和分隔符號十位數
  
-  會對應至 (YYMMDD) 的出生日期的六位數 
    
- 對應至出生順序的兩位數
    
- 會對應至性別的一個數字： 1 女 2 男和女性奇數數字偶數數字
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_bulgaria_national_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_bulgaria_national_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_bulgaria_national_number`找到符合模式的內容。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
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
  
保加利亞文的國際電話號碼
  
國際電話號碼
  
社會安全號碼
  
nationalnumber#
  
ssn#
  
ssn
  
nationalnumber
  
bnn#
  
bnn
  
個人識別碼
  
personalidnumber#
  
ЕДИНЕН ГРАЖДАНСКИ НОМЕР
  
edinen grazhdanski nomer
  
ЕГН
  
ЕГН#
  
## <a name="croatia"></a>克羅埃西亞

如需詳細資訊，請參閱 「 克羅埃西亞身分識別號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="cyprus"></a>賽普勒斯

### <a name="format"></a>格式

如果沒有空格和分隔符號十位數
  
### <a name="pattern"></a>模式

 十位數 
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_cyprus_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_cyprus_eu_national_id_card`找到。 
    
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

證號碼
  
國家識別碼
  
個人識別碼
  
身分證號碼
  
ΤΑΥΤΟΤΗΤΑΣ
  
## <a name="czech-republic"></a>捷克共和國

如需詳細資訊，請參閱 「 捷克國民身分識別號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="denmark"></a>丹麥

如需詳細資訊，請參閱 「 丹麥個人識別碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="estonia"></a>愛沙尼亞

### <a name="format"></a>格式

11 位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

11 位數：
  
- 會對應至性別和世紀的出生的一個數字 (奇數數字 1 女 2 男、 偶數 [女; 1-2: 19 世紀; 3-4: 20 世紀; 5-6： 第 21 世紀)
    
- 會對應至 (YYMMDD) 出生日期的六位數
    
- 會對應至分隔出生日期相同的人員序號的三位數
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_estonia_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_estonia_eu_national_id_card`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_estonia_eu_national_id_card`找到符合模式的內容。 
    
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

個人識別碼的程式碼
  
個人識別碼
  
國家識別碼
  
國際電話號碼
  
個人識別碼
  
personalidnumber#
  
ik
  
isikukood
  
識別碼 kaart
  
## <a name="finland"></a>芬蘭

如需詳細資訊，請參閱 「 芬蘭國民身分證 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="france"></a>法國

如需詳細資訊，請參閱 「 法國國民身分證 (CNI) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="germany"></a>德國

如需詳細資訊，請參閱 「 德國身分證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="greece"></a>希臘

如需詳細資訊，請參閱 「 希臘國民身分證 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

11 位數
  
### <a name="pattern"></a>模式

11 位數：
  
-  會對應至性別 （1-1 女 2 男 2 女性、 其他的數字是也可能公民出生 1900年之前或具有雙公民公民） 的一個數字 
    
- 會對應至 (YYMMDD) 的出生日期的六位數
    
- 會對應至序號的三位數
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_hungary_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_hungary_eu_national_id_card`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_hungary_eu_national_id_card`找到符合模式的內容。 
    
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

個人識別碼
  
識別碼
  
個人識別碼
  
személyazonosító igazolvány
  
## <a name="ireland"></a>愛爾蘭

### <a name="format"></a>格式

九個字元字母、 數字，與組合中所指定的型態的空間
  
### <a name="pattern"></a>模式

九個字元字母、 數字，與組合中所指定的型態的空間
  
從 01 到現在的年 1 月 2013:
  
-  七位數 
    
- 一個檢查碼
    
- 一個空格或大寫字母"W"（區分大小寫）
    
之前 01 年 1 月 2013:
  
-  七位數 
    
- 一個檢查碼
    
- 一個空格或大寫字母 （區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函數找到符合模式的內容。
    
- 找到來自於關鍵字。
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函數找到符合模式的內容。
    
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

個人公用服務號碼
  
pps 沒有
  
收益及社會保險號碼
  
rsi 不
  
個人識別碼
  
識別碼
  
個人識別碼
  
uimhir phearsanta seirbhíse poiblí
  
uimh。 psp
  
## <a name="italy"></a>義大利

### <a name="format"></a>格式

字母和數字中指定的型態的 16 個字元組合
  
### <a name="pattern"></a>模式

字母和數字 16 個字元組合：
  
- 會對應到前三個母音系列名稱中的三個字母
    
- 會對應至第一、 第三個和第四個的三個字母母音在名字
    
- 會對應至最後一位數的出生年份的兩位數
    
- 對應於信件的出生的月份的一個字母 — 字母可用依字母順序，但只字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （因此，一月是的而且年 10 月 R）
    
- 會對應至出生的月份日期的兩位數 — 為了區別 genders，40 會新增至的女性的出生日期
    
- 會對應至 municipality 出生之人員的特定區域的程式碼的四個位數 （國家/地區全代碼用於外部國家/地區提供）
    
- 一個同位檢查數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_italy_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_italy_eu_national_id_card`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_italy_eu_national_id_card`找到符合模式的內容。 
    
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

個人的程式碼
  
個人代碼數字
  
個人的憑證數目
  
會計年度的程式碼
  
personalcodeno#
  
個人識別碼
  
個人識別碼的程式碼
  
codice personale
  
numero certificato personale
  
numero personale
  
numero 識別碼 personale
  
codice 識別碼 personale
  
codice fiscale
  
## <a name="latvia"></a>拉脫維亞

### <a name="format"></a>格式

11 個數字和以指定的格式為連字號
  
### <a name="pattern"></a>模式

11 位數，並連字號：
  
-  會對應至 (DDMMYY) 的出生日期的六位數 
    
- 連字號
    
- 會對應至的出生 （"0"19 世紀的、 20 世紀的"1"和"2"的第 21 世紀） 世紀的一個數字
    
- 四位數，隨機產生
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_latvia_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_latvia_eu_national_id_card`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_latvia_eu_national_id_card`找到符合模式的內容。 
    
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

個人的程式碼
  
個人代碼數字
  
個人的憑證數目
  
personalcodeno#
  
個人識別碼
  
個人識別碼的程式碼
  
人物代表 kods
  
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

11 位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

如果沒有空格和分隔符號的 11 位數：
  
- 會對應至該人員的性別和世紀的出生的一個數字
    
-  會對應至 (YYMMDD) 的出生日期的六位數 
    
- 會對應至出生日期序號的三位數
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_lithuania_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_lithuania_eu_national_id_card`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_lithuania_eu_national_id_card`找到符合模式的內容。 
    
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

個人數字碼
  
唯一識別數字
  
公民健保號碼
  
唯一識別數字
  
uniqueidentityno#
  
個人的程式碼。
  
asmeninis skaitmeninis kodas
  
unikalus identifikavimo numeris
  
piliečio paslaugos numeris
  
unikalus identifikavimo kodas
  
asmens kodas。
  
## <a name="luxemburg"></a>盧森堡

### <a name="format"></a>格式

11 位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

11 位數
  
- 會對應至該人員的性別和世紀的出生的一個數字
    
-  會對應至 (YYMMDD) 的出生日期的六位數 
    
- 會對應至出生日期序號的三位數
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_luxemburg_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_luxemburg_eu_national_id_card`找到。 
    
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
  
個人識別碼
  
personalidno#
  
唯一識別碼
  
personalidnumber#
  
唯一識別碼機碼
  
個人識別碼的程式碼
  
uniqueidkey#
  
個別的程式碼
  
個別的識別碼
  
eindeutige 識別碼 nummer
  
eindeutige 識別碼
  
識別碼 personnelle
  
numéro d'identification 人員
  
idpersonnelle#
  
persönliche identifikationsnummer
  
eindeutigeid#
  
## <a name="malta"></a>馬爾他

### <a name="format"></a>格式

一個字母後尾隨七位數
  
### <a name="pattern"></a>模式

一個字母後尾隨七位數：
  
-  七位數 
    
- 一個大寫字母 （區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_malta_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_malta_eu_national_id_card`找到。 
    
DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_malta_eu_national_id_card`找到符合模式的內容。 
    
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

個人數字碼
  
唯一識別數字
  
公民健保號碼
  
唯一識別數字
  
uniqueidentityno#
  
kodiċi numerali personali
  
numru 東西 ' identifikazzjoni uniku
  
numru 塔司 servizz taċ ċittadin
  
numru 東西 ' identità uniku
  
## <a name="netherlands"></a>荷蘭

### <a name="format"></a>格式

不含空格或分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_netherlands_eu_national_id_card`找到符合模式的內容。 
    
- 找到來自於關鍵字。
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_netherlands_eu_national_id_card`找到符合模式的內容。 
    
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

個人數字碼
  
唯一識別數字
  
公民健保號碼
  
唯一識別數字
  
uniqueidentityno#
  
bsn
  
bsn#
  
persoonlijke numerieke 程式碼
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>波蘭

如需詳細資訊，請參閱 「 波蘭國家識別碼 (PESEL) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="portugal"></a>葡萄牙

如需詳細資訊，請參閱 「 葡萄牙公民證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="romania"></a>羅馬尼亞

### <a name="format"></a>格式

如果沒有空格和分隔符號的 13 位數
  
### <a name="pattern"></a>模式

13 位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_romania_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_romania_eu_national_id_card`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_romania_eu_national_id_card`找到符合模式的內容。 
    
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

個人數字碼
  
唯一識別數字
  
cnp
  
cnp#
  
pin 碼
  
pin 碼#
  
保險號碼
  
insurancenumber#
  
唯一識別數字
  
uniqueidentityno#
  
cod 數值個人
  
cod identificare 個人
  
cod unic identificare
  
număr 個人 unic
  
număr identitate
  
număr identificare 個人
  
număridentitate#
  
codnumericpersonal#
  
numărpersonalunic#
  
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

10 位數包含一個反斜線
  
### <a name="pattern"></a>模式

10 位數包含一個反斜線：
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_slovakia_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_slovakia_eu_national_id_card`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_slovakia_eu_national_id_card`找到符合模式的內容。 
    
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

出生數目
  
國家識別碼
  
個人識別碼
  
社會安全號碼
  
nationalnumber#
  
ssn#
  
ssn
  
國際電話號碼
  
個人識別碼
  
personalidnumber#
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="slovenia"></a>斯洛維尼亞

### <a name="format"></a>格式

不含空格或分隔符號的 13 位數
  
### <a name="pattern"></a>模式

13 位數，代表所指定的型態：
  
-  會對應至出生日期 (DDMMLLL) 」 LLL 」 對應至最後一個三位數的出生年份的七位數 
    
- 會對應至出生的區域中的兩位數
    
- 在同一天 (000-如 1 女 2 男的 499) 和 500-999 名為女性出生的人會對應至性別及序號的組合的三位數
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_slovenia_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_slovenia_eu_national_id_card`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_slovenia_eu_national_id_card`找到符合模式的內容。 
    
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

個人數字碼
  
唯一識別數字
  
唯一登記號碼
  
唯一識別數字
  
uniqueidentityno#
  
唯一的主版公民數目
  
edinstvena identifikacijska številka
  
uniqueidentityno#
  
edinstvena številka glavnega državljana
  
emšo
  
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

七位數後尾隨一個字元
  
### <a name="pattern"></a>模式

七位數後尾隨一個字元
  
- 七位數
    
- 一個數字或字母 （不區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_spain_eu_national_id_card`找到符合模式的內容。 
    
- 從關鍵字`Keywords_spain_eu_national_id_card"`找到。 
    
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
  
國家識別碼
  
國民身分識別號碼
  
保險號碼
  
個人識別碼
  
國民身分識別
  
個人身分識別沒有
  
唯一識別數字
  
nationalidno#
  
uniqueid#
  
dni#
  
nationalid#
  
nie#
  
nie
  
nienúmero#
  
nie número
  
documento nacional de identidad
  
identidad único
  
número nacional identidad
  
dni número
  
dninúmero#
  
identidadúnico#
  
## <a name="sweden"></a>瑞典

如需詳細資訊，請參閱 「 瑞典國民身分證 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="see-also"></a>請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

