---
title: 歐盟社會安全號碼或對等項目識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟社會安全號碼或對等識別碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: b42a8d927e18f813eb6ef6d1d55b2de15ea9dcd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077066"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>歐盟社會安全號碼或對等項目識別碼

本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟社會安全號碼 (SSN) 或對等識別碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

10 位數，代表指定之格式
  
### <a name="pattern"></a>模式

10 位數：
  
-  會對應至序號的三位數 
    
- 一個檢查碼
    
- 會對應至 (DDMMYY) 的出生日期的六位數
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_austria_eu_ssn_or_equivalent`找到符合模式的內容。 
    
- 從關鍵字`Keywords_austria_eu_ssn_or_equivalent`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_austria_eu_ssn_or_equivalent`找到符合模式的內容。 
    
```
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

社會安全沒有
  
社會安全號碼
  
社會安全的程式碼
  
保險號碼
  
奧地利 ssn
  
ssn#
  
ssn
  
保險程式碼
  
保險程式碼#
  
socialsecurityno#
  
sozialversicherungsnummer
  
soziale sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>比利時

### <a name="format"></a>格式

11 位數不含空格或分隔符號
  
### <a name="pattern"></a>模式

11 位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_belgium_eu_ssn_or_equivalent`找到符合模式的內容。 
    
- 從關鍵字`Keywords_belgium_eu_ssn_or_equivalent`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_belgium_eu_ssn_or_equivalent`找到符合模式的內容。 
    
```
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

比利時國民身分的數字
  
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
  
numéro 國際電話
  
numéro de sécurité
  
numéro d'assuré
  
identifiant 國際電話
  
identifiantnational#
  
numéronational#
  
## <a name="croatia"></a>克羅埃西亞

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
  
- 函式`Func_croatia_eu_ssn_or_equivalent`找到符合模式的內容。 
    
- 從關鍵字`Keywords_croatia_eu_ssn_or_equivalent`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_croatia_eu_ssn_or_equivalent`找到符合模式的內容。 
    
```
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

個人識別碼
  
主版公民數目
  
國家識別碼
  
社會安全號碼
  
nationalnumber#
  
ssn#
  
ssn
  
nationalnumber
  
bnn#
  
bnn
  
個人識別碼
  
personalidnumber#
  
oib 碼
  
osobni identifikacijski broj
  
## <a name="czech-republic"></a>捷克共和國

### <a name="format"></a>格式

十個數字和中指定的型態的反斜線
  
### <a name="pattern"></a>模式

十位數和一個反斜線：
  
- 會對應至 (YYMMDD) 的出生日期的六位數： 
    
- 反斜線
    
- 會對應至分隔出生日期相同的人員序號的三位數
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_czech_republic_eu_ssn_or_equivalent`找到符合模式的內容。 
    
- 從關鍵字`Keywords_czech_republic_eu_ssn_or_equivalent`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_czech_republic_eu_ssn_or_equivalent`找到符合模式的內容。 
    
```
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
  
## <a name="denmark"></a>丹麥

### <a name="format"></a>格式

十個數字和中指定的型態連字號
  
### <a name="pattern"></a>模式

十位數，並連字號：
  
- 會對應至 (DDMMYY) 的出生日期的六位數 
    
- 連字號
    
- 會對應至序號的四位數
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_denmark_eu_ssn_or_equivalent`找到符合模式的內容。 
    
- 從關鍵字`Keywords_denmark_eu_ssn_or_equivalent`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_denmark_eu_ssn_or_equivalent`找到符合模式的內容。 
    
```
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

個人識別碼
  
國家識別碼
  
社會安全號碼
  
nationalnumber#
  
ssn#
  
ssn
  
國際電話號碼
  
個人識別碼
  
personalidnumber#
  
cpr nummer
  
personnummer
  
## <a name="finland"></a>芬蘭

### <a name="format"></a>格式

11 個字元組合，以指定的格式
  
### <a name="pattern"></a>模式

以指定的格式 11 個字元組合：
  
-  六位數 
    
- 實例的其中一項：
    
  - 加上符號
    
  - 減號
    
  - 字母"A"（不區分大小寫）
    
- 三位數
    
- 一個字母或一個數字
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_finland_eu_ssn_or_equivalent`找到符合模式的內容。 
    
- 從關鍵字`Keywords_finland_eu_ssn_or_equivalent`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_finland_eu_ssn_or_equivalent`找到符合模式的內容。 
    
```
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
  
hetu
  
## <a name="france"></a>法國

如需詳細資訊，請參閱 「 法國社會安全號碼 (INSEE) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="germany"></a>德國

如需詳細資訊，請參閱 「 德國身分證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="greece"></a>希臘

如需詳細資訊，請參閱 「 希臘國民身分證 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

如果沒有空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_hungary_eu_ssn_or_equivalent`找到符合模式的內容。 
    
- 從關鍵字`Keywords_hungary_eu_ssn_or_equivalent`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_hungary_eu_ssn_or_equivalent`找到符合模式的內容。 
    
```
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

匈牙利文社會安全號碼
  
社會安全號碼
  
socialsecuritynumber#
  
hssn#
  
socialsecuritynno
  
hssn
  
泰
  
泰#
  
ssn
  
ssn#
  
社會安全沒有
  
áfa
  
közösségi adószám
  
általános forgalmi adó szám
  
hozzáadottérték adó
  
áfa szám
  
magyar áfa szám
  
## <a name="portugal"></a>葡萄牙

如需詳細資訊，請參閱 「 葡萄牙公民證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="spain"></a>西班牙

如需詳細資訊，請參閱 「 西班牙社會安全號碼 (SSN) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="sweden"></a>瑞典

### <a name="format"></a>格式

如果沒有空格和分隔符號的 12 位數
  
### <a name="pattern"></a>模式

12 位數：
  
-  會對應至出生日期 (YYYYMMDD) 的八位數 
    
- 會對應至序號的三位數其中： 
    
  - 序號中的最後一個數字表示性別因 1 女 2 男奇數和偶數女性的工作分派
    
  - 最多 1990，工作分派的序號採納郡出生數字的承載或 （如果出生之前 1947年） 其中他有已住，根據稅務記錄上 1947 年 1 月 1，具有特殊的程式碼 (通常為 7th 的數字 9) 的immigrants 
    
- 一個檢查碼
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_sweden_eu_ssn_or_equivalent`找到符合模式的內容。 
    
- 從關鍵字`Keywords_sweden_eu_ssn_or_equivalent`找到。 
    
DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_sweden_eu_ssn_or_equivalent`找到符合模式的內容。 
    
```
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

個人識別碼
  
識別碼
  
個人識別碼沒有
  
身分識別沒有
  
識別任何
  
個人識別碼沒有
  
personnummer 識別碼
  
personligt 識別碼 nummer
  
unikt 識別碼 nummer
  
personnummer
  
identifikationsnumret
  
personnummer#
  
identifikationsnumret#
  
## <a name="see-also"></a>請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

