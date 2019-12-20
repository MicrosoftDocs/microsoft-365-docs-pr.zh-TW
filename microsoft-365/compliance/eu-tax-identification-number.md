---
title: 歐盟稅務識別碼
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟稅務識別號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: 0ee76fa46bb22b2754098d053ab769b862fdd3f2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805846"
---
# <a name="eu-tax-identification-number"></a>歐盟稅務識別碼

本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟稅務識別號碼 （錫） 敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

選擇性連字號和正斜線的九位數
  
### <a name="pattern"></a>模式

選擇性連字號和正斜線的九位數：
  
-  兩位數 
    
- 連字號 （選用）
    
- 三位數
    
- 正斜線 （選用）
    
- 四位數
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_austria_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_austria_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_austria_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
number
  
稅務登記號碼
  
稅務識別碼
  
st.nr。
  
steuernummer
  
## <a name="belgium"></a>比利時

### <a name="format"></a>格式

11 位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

11 位數：
  
- 兩位數
    
- 「 0 」 或者 「 1 」
    
- 一位數
    
- "0"或"1"或"2"或者"3" 
    
- 六位數
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_belgium_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_belgium_eu_tax_file_number`找到。 
    
```
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

稅務編號
  
國民登記號碼
  
稅務登記號碼
  
稅務識別碼
  
n 如果
  
n 如果#
  
numéro de registre 國際電話
  
numéro d'identification fiscale
  
## <a name="bulgaria"></a>保加利亞

### <a name="format"></a>格式

如果沒有空格和分隔符號十位數
  
### <a name="pattern"></a>模式

10 位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_bulgaria_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_bulgaria_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_bulgaria_eu_tax_file_number`找到符合模式的內容。 
    
```
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

bucn
  
統一民事數目
  
bucn#
  
uniformcivilnumber#
  
統一民事識別碼
  
統一民事否
  
egn
  
保加利亞文統一民事數目
  
uniformcivilno#
  
egn#
  
УНИФОРМ ГРАЖДАНСКИ НОМЕР
  
Униформ 識別碼
  
Униформ граждански 識別碼
  
УНИФОРМ ГРАЖДАНСКИ НЕ
  
## <a name="croatia"></a>克羅埃西亞

### <a name="format"></a>格式

11 位數不含空格或分隔符號
  
### <a name="pattern"></a>模式

11 位數：
  
- 十位數，隨機選擇
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_croatia_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_croatia_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_croatia_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務
  
稅務識別碼
  
OID
  
oid#
  
porezni broj
  
## <a name="cyprus"></a>賽普勒斯

### <a name="format"></a>格式

八位數與所指定的型態的其中一個字母
  
### <a name="pattern"></a>模式

八位數和一個字母：
  
-  「 0 」 
    
- 七位數
    
- 一個字母 （不區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_cyprus_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_cyprus_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_cyprus_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務
  
稅務識別碼
  
稅務識別程式碼
  
tic
  
tic#
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ
  
ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="czech-republic"></a>捷克共和國

### <a name="format"></a>格式

具有選用反斜線的九個或十位數
  
### <a name="pattern"></a>模式

具有選用 backslashl 九個或十位數：
  
- 六位數 
    
- 反斜線 （選用）
    
- 三或四位數
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_czech_republic_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_czech_republic_eu_tax_file_number`找到。 
    
```
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

稅務編號
  
稅務
  
稅務識別碼
  
個人識別碼
  
daňové číslo
  
osobní číslo
  
## <a name="denmark"></a>丹麥

### <a name="format"></a>格式

10 位數包含連字號
  
### <a name="pattern"></a>模式

10 位數包含 hyphenl:
  
-  會對應至 (DDMMYY) 的出生日期的六位數 
    
- 連字號
    
- 會對應至其中的第一個數字會對應至的出生世紀序號的四位數，最後一個數字會對應至個別的性別 （如 1 女 2 男以及即使女性奇數）
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_denmark_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_denmark_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_denmark_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務
  
稅務識別碼
  
cpr 數目
  
cpr#
  
skat nummer
  
skat 識別碼
  
## <a name="estonia"></a>愛沙尼亞

### <a name="format"></a>格式

11 位數不含空格或分隔符號
  
### <a name="pattern"></a>模式

11 位數：
  
-  會對應至性別和世紀的出生其中奇數的數字表示 1 女 2 男並偶數指出女性，如下所示的一個數字： 1，2 代表 19 世紀;3、 4 20 的 century;5，6 第 21 世紀 
    
- 會對應至 (YYMMDD) 的出生日期的六位數
    
- 會對應至分隔出生日期相同的人員序號的三位數
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_estonia_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_estonia_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_estonia_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務
  
稅務識別碼
  
個人的程式碼
  
maksunumber
  
maksu 識別碼
  
isikukood
  
## <a name="finland"></a>芬蘭

### <a name="format"></a>格式

字母的數字，11 個字元組合，以及加號與減號
  
### <a name="pattern"></a>模式

字母的數字，11 個字元組合，以及加號與減號：
  
- 六位數
    
- 下列其中之一： 加上加號、 減號或其中加號表示字母"A"（不區分大小寫） 之間 1800年 1899 年出生減號登入表示出生之間 1999 1900 年和"A"表示出生 2000年和之後
    
- 三位數
    
- 一個字母或一個數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_finland_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_finland_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_finland_eu_tax_file_number`找到符合模式的內容。 
    
```
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

識別碼
  
個人識別碼
  
身分識別號碼
  
芬蘭國民身分證號碼
  
personalidnumber#
  
國家識別碼
  
識別碼號碼
  
國民身分證沒有。
  
國民身分證號碼
  
識別碼不
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
identiteetti numero
  
suomen kansallinen henkilötunnus
  
henkilötunnusnumero#
  
kansallisen tunnistenumero
  
tunnusnumero
  
kansallinen tunnus numero
  
## <a name="france"></a>法國

### <a name="format"></a>格式

13 位數個人與實體的九位數
  
### <a name="pattern"></a>模式

針對個人的 13 位數：
  
- 必須是 0、 1、 2 或 3 的一個數字
    
- 12 位數
    
實體的九位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_france_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_france_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_france_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務識別碼
  
稅務編號
  
稅務識別碼
  
numéro d'identification fiscale
  
## <a name="germany"></a>德國

### <a name="format"></a>格式

11 位數不含空格和分隔符號
  
### <a name="pattern"></a>模式

11 位數：
  
-  十位數 
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_germany_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_germany_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_germany_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務否。
  
taxno#
  
taxnumber#
  
taxnumber
  
稅務識別碼
  
taxid#
  
稅務識別碼
  
不稅務識別碼。
  
steuernummer
  
steuer 識別碼
  
steueridentifikationsnummer
  
## <a name="greece"></a>希臘

### <a name="format"></a>格式

如果沒有空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_greece_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_greece_eu_tax_file_number`找到。 
    
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

afm
  
錫
  
不稅務識別碼。
  
不稅務識別碼
  
稅務識別碼
  
稅務登錄編號
  
不稅務登錄。
  
afm#
  
錫#
  
taxidno#
  
taxregistryno#
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
aφμ
  
aφμ αριθμός
  
ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。
  
ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

不含空格或分隔符號十位數
  
### <a name="pattern"></a>模式

十位數：
  
-  必須是"8"的一個數字 
    
- 會對應至日期之間的天數的五位數 01/01/1867年和個別的出生日期
    
- 會對應至數來區分個人在同一天出生巧產生的三位數
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_hungary_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_hungary_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_hungary_eu_tax_file_number`找到符合模式的內容。 
    
```
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

匈牙利文的稅務識別碼
  
匈牙利文錫
  
稅務 id 號碼
  
vat 編號
  
不稅務授權單位
  
稅務識別碼稅務身分識別號碼
  
taxidnumber#
  
錫#
  
hungatiantin#
  
不稅務識別碼
  
taxidno#
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>愛爾蘭

### <a name="format"></a>格式

七位數後尾隨不含空格或分隔符號的字母
  
### <a name="pattern"></a>模式

七位數後尾隨字母：
  
-  七位數 
    
- 一個字母 （不區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_ireland_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_ireland_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_ireland_eu_tax_file_number`找到符合模式的內容。 
    
```
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

公用服務沒有
  
個人公用服務沒有
  
pps 沒有
  
個人服務否
  
pps service 否
  
ppsno#
  
愛爾蘭 pps 沒有
  
publicserviceno#
  
個人公用服務號碼
  
uimhir phearsanta seirbhíse poiblí
  
pps uimh
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>義大利

### <a name="format"></a>格式

16 個字母和數字中指定的型態
  
### <a name="pattern"></a>模式

16 個字母和數字：
  
-  會對應到前三個母音系列名稱中的三個字母 
    
- 會對應至第一、 第三個和第四個的三個字母母音在名字
    
- 會對應至最後一位數的出生年份的兩位數
    
- 會對應至出生的月份的一個數字 — 字母可用依字母順序，但只字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （因此，一月是的而且年 10 月 R）
    
- 會對應至出生其中 40 加入的來區分從男生女生出生日期的月份日期的兩位數
    
- 會對應至特定出生人員 municipality 區域代碼的四位數 — 全國家/地區的代碼可用外部國家/地區
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_italy_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_italy_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_italy_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務否。
  
taxno#
  
taxnumber#
  
taxnumber
  
稅務識別碼
  
taxid#
  
會計年度的程式碼
  
codice fiscale
  
## <a name="latvia"></a>拉脫維亞

### <a name="format"></a>格式

11 位數不含空格或分隔符號
  
### <a name="pattern"></a>模式

11 位數，代表所指定模式
  
-  會對應至 (DDMMYY) 出生日期的六位數 
    
- 會對應至的出生其中"0"會對應至 19 世紀"1"會對應至 20 世紀，，"2"會對應至第 21 世紀世紀的一個數字
    
- 四位數
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_latvia_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_latvia_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_latvia_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務否。
  
taxno#
  
taxnumber#
  
taxnumber
  
稅務識別碼
  
taxid#
  
稅務識別碼
  
不稅務識別碼。
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

11 位數不含空格或分隔符號
  
### <a name="pattern"></a>模式

11 位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_lithuania_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_lithuania_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_lithuania_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務否。
  
稅務否#
  
taxnumber#
  
taxnumber
  
稅務識別碼
  
taxid#
  
稅務識別碼
  
不稅務識別碼。
  
mokesčių 識別碼
  
mokesčių numeris
  
mokesčių identifikavimas numeris
  
## <a name="luxemburg"></a>盧森堡

### <a name="format"></a>格式

不含空格或分隔符號的 13 位數
  
### <a name="pattern"></a>模式

13 位數：
  
-  11 位數 
    
- 二位數檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_luxemburg_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_luxemburg_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_luxemburg_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務否。
  
taxno#
  
taxnumber#
  
taxnumber
  
稅務識別碼
  
taxid#
  
稅務識別碼
  
不稅務識別碼。
  
steuernummer
  
steuer 識別碼
  
steueridentifikationsnummer
  
## <a name="malta"></a>馬爾他

### <a name="format"></a>格式

針對馬爾他 nationals: 7 位數與所指定的型態的其中一個字母
  
非馬爾他文 nationals 和馬爾他實體： 9 位數
  
### <a name="pattern"></a>模式

馬爾他 nationals: 7 位數和一個字母
  
-  七位數 
    
- 一個字母 （不區分大小寫）
    
非馬爾他文 nationals 和馬爾他實體： 9 位數
  
-  九位數 
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_malta_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_malta_eu_tax_file_number`找到。 
    
DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_malta_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務否。
  
taxno#
  
taxnumber#
  
taxnumber
  
稅務識別碼
  
taxid#
  
稅務識別碼
  
不稅務識別碼。
  
numru 且 taxxa
  
識別碼且 taxxa
  
numru 東西 ' identifikazzjoni 且 taxxa
  
## <a name="netherlands"></a>荷蘭

### <a name="format"></a>格式

不含空格或分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數 
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_netherlands_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_netherlands_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_netherlands_eu_tax_file_number`找到符合模式的內容。 
    
```
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

荷蘭稅務識別碼
  
荷蘭稅務識別碼
  
荷屬安的稅務識別碼
  
荷屬安的稅務識別碼
  
稅務識別碼
  
荷蘭文的稅務識別碼
  
荷蘭文的稅務識別碼
  
稅務識別碼
  
稅務識別碼#
  
稅務編號
  
稅務否#
  
稅務#
  
錫
  
錫#
  
荷蘭錫
  
荷屬安的錫
  
荷蘭 belasting identificatienummer
  
identificatienummer van belasting
  
identificatienummer belasting
  
荷蘭 belasting identificatie
  
荷蘭 belasting 識別碼 nummer
  
荷蘭 belastingnummer
  
btw nummer
  
文拚字檢查 belasting identificatie
  
## <a name="poland"></a>波蘭

### <a name="format"></a>格式

不含空格或分隔符號十一份數字
  
### <a name="pattern"></a>模式

十一份數字
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_poland_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_poland_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_poland_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務否。
  
taxno#
  
taxnumber#
  
taxnumber
  
nip
  
nip#
  
稅務識別碼
  
稅務識別碼#
  
nip 識別碼
  
nip 識別碼#
  
稅務識別碼
  
不稅務識別碼。
  
vat 編號
  
vat 否。
  
vatno#
  
vat 識別碼
  
vat 識別碼#
  
數目 identyfikacji podatkowej
  
polski 數目 identyfikacji podatkowej
  
numeridentyfikacjipodatkowej#
  
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

不含空格或分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_portugal_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_portugal_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_portugal_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務編號
  
稅務否。
  
taxno#
  
taxnumber#
  
taxnumber
  
n 如果
  
n 如果#
  
numero 會計
  
número de identificação 會計
  
## <a name="romania"></a>羅馬尼亞

### <a name="format"></a>格式

不含空格或分隔符號的 13 位數
  
### <a name="pattern"></a>模式

13 位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_romania_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_romania_eu_tax_file_number`找到。 
    
```
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

稅務識別碼
  
稅務 id 號碼
  
不稅務檔案
  
稅務檔案編號
  
稅務否
  
稅務編號
  
taxid#
  
taxno#
  
id-ul taxei
  
numărul de identificare fiscală
  
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

不含空格或分隔符號的 10 位數
  
### <a name="pattern"></a>模式

10 位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_slovakia_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_slovakia_eu_tax_file_number`找到。 
    
```
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

稅務識別碼
  
稅務 id 號碼
  
鐵皮識別碼
  
鐵皮否
  
斯洛伐克鐵皮識別碼
  
錫
  
不稅務檔案
  
稅務檔案編號
  
稅務否
  
稅務編號
  
taxid#
  
taxno#
  
daňové identifikačné číslo
  
daňové číslo
  
daňové číslo súboru
  
## <a name="slovenia"></a>斯洛維尼亞

### <a name="format"></a>格式

不含空格或分隔字元的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_slovenia_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_slovenia_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_slovenia_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務識別碼
  
稅務 id 號碼
  
鐵皮識別碼
  
鐵皮否
  
斯洛維尼亞文鐵皮識別碼
  
錫
  
不稅務檔案
  
稅務檔案編號
  
稅務否
  
稅務編號
  
taxid#
  
taxno#
  
identifikacijska številka davka
  
davčna številka
  
Številka davčne datoteke
  
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

7 或 8 位數與所指定的型態的一或兩個字母
  
### <a name="pattern"></a>模式

西班牙文自然人西班牙國民身分證與：
  
-  八位數 
    
- 一個大寫字母 （區分大小寫） 
    
非駐留西班牙人沒有西班牙國民身分證
  
- 一個大寫字母"L"（區分大小寫）
    
- 七位數
    
- 一個大寫字母 （區分大小寫） 
    
[] 下的保留天數 14 年沒有西班牙國民身分證駐留西班牙人：
  
- 一個大寫字母"K"（區分大小寫）
    
-  七位數 
    
- 一個大寫字母 （區分大小寫）
    
外國人與因此識別碼
  
- 一個大寫也就是字母 「 X 」、 「 Y"或"Z"（區分大小寫） 
    
- 七位數
    
- 一個大寫字母 （區分大小寫） 
    
外國人沒有因此識別碼
  
- 一個大寫字母，為 「 M 」 （區分大小寫） 
    
- 七位數
    
- 一個大寫字母 （區分大小寫） 
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_spain_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_spain_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_spain_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務識別碼
  
稅務 id 號碼
  
cif 識別碼
  
cif 沒有
  
西班牙文的 cif 識別碼
  
cif
  
不稅務檔案
  
西班牙文的 cif 數目
  
稅務檔案編號
  
西班牙文的 cif 沒有
  
稅務否
  
稅務編號
  
taxid#
  
taxno#
  
cifid#
  
spanishcifid#
  
spanishcifno#
  
número de contribuyente
  
número de impuesto corporativo
  
número de identificación 會計
  
cif número
  
cifnúmero#
  
## <a name="sweden"></a>瑞典

### <a name="format"></a>格式

十個數字和中指定的型態的符號
  
### <a name="pattern"></a>模式

十個數字和符號：
  
-  會對應至 (YYMMDD) 的出生日期的六位數 
    
- 加號、 減號或反斜線
    
- 請識別的三位數數字唯一的位置： 
    
  - 發行之前 1990年數字，如第七個和第八個數字識別出生或 foreign-born 人員郡
    
  - 在第九個位置的數字，表示女性 1 女 2 男或甚至是任一奇數性別
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_sweden_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_sweden_eu_tax_file_number`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_sweden_eu_tax_file_number`找到符合模式的內容。 
    
```
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

稅務識別碼
  
不稅務識別碼。
  
稅務 id 號碼
  
稅務識別碼
  
稅務識別碼#
  
稅務否。
  
稅務#
  
taxid#
  
稅務檔案
  
不稅務檔案。
  
個人識別碼
  
skatt 識別碼 nummer
  
skatt identifikation
  
personnummer
  
## <a name="uk"></a>英國

### <a name="format"></a>格式

如果沒有空格和分隔符號的唯一 Taxpayer 參照 (UTR): 10 位數
  
國家保險號碼 (NINO): 如需詳細資訊，請參閱區段 」 英國 國家保險號碼 (NINO) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
### <a name="pattern"></a>模式

唯一 Taxpayer 參照 (UTR): 10 位數
  
國家保險號碼 (NINO): 如需詳細資訊，請參閱區段 」 英國 國家保險號碼 (NINO) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_uk_eu_tax_file_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_uk_eu_tax_file_number`找到。 
    
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

稅務識別碼
  
不稅務識別碼。
  
稅務 id 號碼
  
稅務識別碼
  
稅務識別碼#
  
稅務否。
  
稅務#
  
taxid#
  
稅務檔案
  
不稅務檔案。
  
## <a name="see-also"></a>另請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

