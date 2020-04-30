---
title: 歐盟納稅識別號碼
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
description: 本主題顯示資料遺失防護（DLP）原則在偵測到歐盟納稅識別號碼機密資訊類型時所尋找的功能。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
ms.openlocfilehash: 5f779974266045d7099b599700c7168162d9d81e
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938669"
---
# <a name="eu-tax-identification-number"></a>歐盟納稅識別號碼

本主題說明資料遺失防護（DLP）原則在偵測到歐盟納稅識別號碼（TIN）機密資訊類型時，會尋找哪些專案。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

具有選擇性連字號及正斜線的九位數
  
### <a name="pattern"></a>模式

具有選擇性連字號及正斜線的九位數：
  
-  兩位數 
    
- 連字號（選用）
    
- 三位數
    
- 一個正斜線（選用）
    
- 四位數
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_austria_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_austria_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_austria_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
number
  
稅務登記編號
  
納稅識別碼
  
st.nr。
  
steuernummer
  
## <a name="belgium"></a>比利時

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
  
- 正則運算式`Regex_belgium_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_belgium_eu_tax_file_number`的關鍵字。 
    
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

納稅號碼
  
國家註冊號碼
  
稅務登記編號
  
納稅識別碼
  
Nif
  
Nif#
  
numéro de registre （本國）
  
numéro d'identification fiscale
  
## <a name="bulgaria"></a>保加利亞

### <a name="format"></a>格式

10位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

10位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_bulgaria_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_bulgaria_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_bulgaria_eu_tax_file_number`會找到符合模式的內容。 
    
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
  
統一的民事編號
  
bucn#
  
uniformcivilnumber#
  
統一的民事識別碼
  
統一的民事未
  
egn
  
保加利亞文統一民事號碼
  
uniformcivilno#
  
egn#
  
униформ граждански номер
  
униформ識別碼
  
униформграждански id
  
униформ граждански не
  
## <a name="croatia"></a>克羅埃西亞

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
  
- 函數`Func_croatia_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_croatia_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_croatia_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
稅
  
納稅識別碼
  
OID
  
老#
  
porezni broj
  
## <a name="cyprus"></a>賽普勒斯

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
  
- 函數`Func_cyprus_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_cyprus_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_cyprus_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
稅
  
納稅識別碼
  
納稅識別碼
  
旅遊業 議會
  
旅遊業 議會#
  
αριθμός φορολογικού μητρώου
  
φορολογική ταυτότητα
  
κωδικός φορολογικού μητρώου
  
## <a name="czech-republic"></a>捷克共和國

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
  
- 正則運算式`Regex_czech_republic_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_czech_republic_eu_tax_file_number`的關鍵字。 
    
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

納稅號碼
  
稅
  
納稅識別碼
  
個人號碼
  
daňové číslo
  
osobní číslo
  
## <a name="denmark"></a>丹麥

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
  
- 函數`Func_denmark_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_denmark_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_denmark_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
稅
  
納稅識別碼
  
cpr 編號
  
Cpr#
  
skat nummer
  
skat 識別碼
  
## <a name="estonia"></a>愛沙尼亞

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
  
- 函數`Func_estonia_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_estonia_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_estonia_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
稅
  
納稅識別碼
  
個人程式碼
  
maksunumber
  
maksu 識別碼
  
isikukood
  
## <a name="finland"></a>芬蘭

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
  
- 函數`Func_finland_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_finland_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_finland_eu_tax_file_number`會找到符合模式的內容。 
    
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

識別號碼
  
個人識別碼
  
身分識別號碼
  
芬蘭文身分識別號碼
  
personalidnumber#
  
國家識別號碼
  
識別碼號碼
  
國家識別碼
  
本國識別碼
  
識別碼 no
  
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
  
- 函數`Func_france_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_france_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_france_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅識別號碼
  
納稅號碼
  
納稅識別碼
  
numéro d'identification fiscale
  
## <a name="germany"></a>德國

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
  
- 函數`Func_germany_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_germany_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_germany_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
納稅編號
  
taxno#
  
taxnumber#
  
taxnumber
  
納稅識別碼
  
taxid#
  
納稅識別號碼
  
納稅識別碼
  
steuernummer
  
steuer 識別碼
  
steueridentifikationsnummer
  
## <a name="greece"></a>希臘

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_greece_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_greece_eu_tax_file_number`的關鍵字。 
    
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

Afm
  
錫
  
納稅識別碼
  
納稅識別碼否
  
納稅識別號碼
  
納稅登錄號碼
  
納稅登錄編號
  
Afm#
  
錫#
  
taxidno#
  
taxregistryno#
  
αριθμός φορολογικού μητρώου
  
aφμ
  
aφμ αριθμός
  
φορολογικού μητρώου νο.
  
τον αριθμό φορολογικού μητρώου
  
## <a name="hungary"></a>匈牙利

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
  
- 函數`Func_hungary_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_hungary_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_hungary_eu_tax_file_number`會找到符合模式的內容。 
    
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

匈牙利文納稅識別號碼
  
匈牙利文 tin
  
納稅識別碼號碼
  
加值稅號碼
  
稅務授權單位否
  
納稅識別碼納稅身分識別號碼
  
taxidnumber#
  
錫#
  
hungatiantin#
  
納稅識別碼否
  
taxidno#
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>愛爾蘭

### <a name="format"></a>格式

七位數後接字母，不含空格或分隔符號
  
### <a name="pattern"></a>模式

七位數後接字母：
  
-  七位數 
    
- 一個字母（不區分大小寫）
    
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_ireland_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_ireland_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_ireland_eu_tax_file_number`會找到符合模式的內容。 
    
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

公用服務否
  
個人公開服務否
  
pps 否
  
個人服務否
  
pps 服務否
  
ppsno#
  
愛爾蘭 pps 否
  
publicserviceno#
  
個人公開服務號碼
  
uimhir phearsanta seirbhíse poiblí
  
pps uimh
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>義大利

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
  
- 函數`Func_italy_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_italy_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_italy_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
納稅編號
  
taxno#
  
taxnumber#
  
taxnumber
  
納稅識別碼
  
taxid#
  
會計代碼
  
codice fiscale
  
## <a name="latvia"></a>拉脫維亞

### <a name="format"></a>格式

11位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

指定的模式中的11位數
  
-  與出生日期相對應的六位數（DDMMYY） 
    
- 對應至出生世紀的一個數位，其中 "0" 對應于19世紀，"1" 對應于20世紀，"2" 對應于21世紀。
    
- 四位數
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_latvia_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_latvia_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_latvia_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
納稅編號
  
taxno#
  
taxnumber#
  
taxnumber
  
納稅識別碼
  
taxid#
  
納稅識別號碼
  
納稅識別碼
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

11位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

11位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_lithuania_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_lithuania_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_lithuania_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
納稅編號
  
納稅否#
  
taxnumber#
  
taxnumber
  
納稅識別碼
  
taxid#
  
納稅識別號碼
  
納稅識別碼
  
mokesčių識別碼
  
mokesčių numeris
  
mokesčių identifikavimas numeris
  
## <a name="luxemburg"></a>盧森堡

### <a name="format"></a>格式

13位數沒有空格或分隔符號
  
### <a name="pattern"></a>模式

13位數：
  
-  11位數 
    
- 兩個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_luxemburg_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_luxemburg_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_luxemburg_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
納稅編號
  
taxno#
  
taxnumber#
  
taxnumber
  
納稅識別碼
  
taxid#
  
納稅識別號碼
  
納稅識別碼
  
steuernummer
  
steuer 識別碼
  
steueridentifikationsnummer
  
## <a name="malta"></a>馬爾他

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
  
- 函數`Func_malta_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_malta_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：
  
- 函數`Func_malta_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
納稅編號
  
taxno#
  
taxnumber#
  
taxnumber
  
納稅識別碼
  
taxid#
  
納稅識別號碼
  
納稅識別碼
  
numru tat-taxxa
  
識別碼 tat-taxxa
  
numru ta ' identifikazzjoni tat-taxxa
  
## <a name="netherlands"></a>荷蘭

### <a name="format"></a>格式

九位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

九位數 
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_netherlands_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_netherlands_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_netherlands_eu_tax_file_number`會找到符合模式的內容。 
    
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

荷蘭稅務識別號碼
  
荷蘭稅務識別
  
netherland 的納稅識別號碼
  
netherland 的納稅識別
  
納稅識別號碼
  
荷蘭稅號
  
荷蘭稅務識別號碼
  
納稅識別碼
  
納稅識別碼#
  
納稅號碼
  
納稅否#
  
稅#
  
錫
  
錫#
  
荷屬安的納稅人
  
netherland 的納稅人標識號
  
nederlands belasting identificatienummer
  
identificatienummer van belasting
  
identificatienummer belasting
  
nederlands belasting identificatie
  
nederlands belasting id nummer
  
nederlands belastingnummer
  
btw nummer
  
nederlandse belasting identificatie
  
## <a name="poland"></a>波蘭

### <a name="format"></a>格式

不含空格或分隔符號的11位數
  
### <a name="pattern"></a>模式

11位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_poland_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_poland_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_poland_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
納稅編號
  
taxno#
  
taxnumber#
  
taxnumber
  
咬
  
咬#
  
納稅識別碼
  
納稅識別碼#
  
nip 識別碼
  
nip 識別碼#
  
納稅識別號碼
  
納稅識別碼
  
加值稅號碼
  
加值稅編號
  
vatno#
  
加值稅識別碼
  
加值稅識別碼#
  
轉寄 identyfikacji podatkowej
  
polski 轉寄 identyfikacji podatkowej
  
numeridentyfikacjipodatkowej#
  
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

九位數（沒有空格或分隔符號）
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_portugal_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_portugal_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_portugal_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅號碼
  
納稅編號
  
taxno#
  
taxnumber#
  
taxnumber
  
Nif
  
Nif#
  
numero 會計
  
número de identificação 會計
  
## <a name="romania"></a>羅馬尼亞

### <a name="format"></a>格式

13位數沒有空格或分隔符號
  
### <a name="pattern"></a>模式

13位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_romania_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_romania_eu_tax_file_number`的關鍵字。 
    
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

納稅識別碼
  
納稅識別碼號碼
  
納稅檔案編號
  
稅收檔案編號
  
納稅否
  
納稅號碼
  
taxid#
  
taxno#
  
id-ul taxei
  
numărul de identificare fiscală
  
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

10位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

10位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_slovakia_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_slovakia_eu_tax_file_number`的關鍵字。 
    
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

納稅識別碼
  
納稅識別碼號碼
  
納稅人識別碼
  
tin no
  
斯洛伐克納稅人識別碼
  
錫
  
納稅檔案編號
  
稅收檔案編號
  
納稅否
  
納稅號碼
  
taxid#
  
taxno#
  
daňové identifikačné číslo
  
daňové číslo
  
daňové číslo súboru
  
## <a name="slovenia"></a>斯洛維尼亞

### <a name="format"></a>格式

八位數沒有空格或分隔符號
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_slovenia_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_slovenia_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_slovenia_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅識別碼
  
納稅識別碼號碼
  
納稅人識別碼
  
tin no
  
斯洛維尼亞納稅人識別碼
  
錫
  
納稅檔案編號
  
稅收檔案編號
  
納稅否
  
納稅號碼
  
taxid#
  
taxno#
  
identifikacijska številka davka
  
davčna številka
  
številka davčne datoteke
  
## <a name="spain"></a>西班牙

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
  
- 函數`Func_spain_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_spain_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_spain_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅識別碼
  
納稅識別碼號碼
  
cif 識別碼
  
cif 否
  
西班牙文 cif 識別碼
  
Cif
  
納稅檔案編號
  
西班牙文 cif 編號
  
稅收檔案編號
  
西班牙文 cif 否
  
納稅否
  
納稅號碼
  
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

指定之模式中的10位數和符號
  
### <a name="pattern"></a>模式

10位數和符號：
  
-  與出生日期對應的六位數（YYMMDD） 
    
- 正負號或反斜線
    
- 在下列情況下，識別號碼唯一的三位數： 
    
  - 若為1990之前所簽發的號碼，第七和第八位數識別出生的縣或對外出生的人員
    
  - 第九個位置中的位數會以奇數為單位表示，甚至是對女的性別
    
- 一個檢查碼
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_sweden_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_sweden_eu_tax_file_number`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_sweden_eu_tax_file_number`會找到符合模式的內容。 
    
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

納稅識別碼
  
納稅識別碼
  
納稅識別碼號碼
  
納稅識別
  
納稅識別#
  
納稅編號
  
稅#
  
taxid#
  
納稅檔案
  
納稅檔案編號
  
個人號碼
  
skatt 識別碼 nummer
  
skatt identifikation
  
personnummer
  
## <a name="uk"></a>英國

### <a name="format"></a>格式

唯一的納稅人參考（UTR）：10位數，不含空格及分隔符號
  
國家保險號碼（NINO）：如需詳細資訊，請參閱 section "英 「[機密資訊類型](what-the-sensitive-information-types-look-for.md)」所尋找的國家保險編號（NINO）。
  
### <a name="pattern"></a>模式

唯一的納稅人參考（UTR）：10位數
  
國家保險號碼（NINO）：如需詳細資訊，請參閱 section "英 「[機密資訊類型](what-the-sensitive-information-types-look-for.md)」所尋找的國家保險編號（NINO）。
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_uk_eu_tax_file_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_uk_eu_tax_file_number`的關鍵字。 
    
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

納稅識別碼
  
納稅識別碼
  
納稅識別碼號碼
  
納稅識別
  
納稅識別#
  
納稅編號
  
稅#
  
taxid#
  
納稅檔案
  
納稅檔案編號
  
## <a name="see-also"></a>另請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

