---
title: 歐盟社會安全號碼或同等識別碼
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題說明資料遺失防護（DLP）原則在偵測到歐盟社會保險號碼或對等身分識別敏感資訊類型時，會尋找哪些專案。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
ms.openlocfilehash: 1f2d1d9c61f27fb47b0c7ac0ce544b17175d4254
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2020
ms.locfileid: "41591224"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>歐盟社會安全號碼或同等識別碼

本主題說明資料遺失防護（DLP）原則在偵測到歐盟社會安全號碼（SSN）或對等識別碼敏感資訊類型時，會尋找的內容。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
  
## <a name="austria"></a>奧地利

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
  
- 函數`Func_austria_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
- 找到來自`Keywords_austria_eu_ssn_or_equivalent`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_austria_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
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

社會安全性否
  
社會安全號碼
  
社會安全性碼
  
保險號碼
  
奧地利 ssn
  
Ssn#
  
Ssn
  
保險業代碼
  
保險業代碼#
  
socialsecurityno#
  
sozialversicherungsnummer
  
soziale sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>比利時

### <a name="format"></a>格式

11位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

11位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_belgium_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
- 找到來自`Keywords_belgium_eu_ssn_or_equivalent`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_belgium_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
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

比利時國號碼
  
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
  
本國 numéro
  
numéro de sécurité
  
numéro d'assuré
  
本國 identifiant
  
identifiantnational#
  
numéronational#
  
## <a name="croatia"></a>克羅埃西亞

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
  
- 函數`Func_croatia_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
- 找到來自`Keywords_croatia_eu_ssn_or_equivalent`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_croatia_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
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

個人身分識別號碼
  
主機公民號碼
  
國家識別號碼
  
社會安全號碼
  
nationalnumber#
  
Ssn#
  
Ssn
  
nationalnumber
  
安娜#
  
安娜
  
個人號碼
  
personalidnumber#
  
oib
  
osobni identifikacijski broj
  
## <a name="czech-republic"></a>捷克共和國

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
  
- 函數`Func_czech_republic_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
- 找到來自`Keywords_czech_republic_eu_ssn_or_equivalent`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_czech_republic_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
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
  
## <a name="denmark"></a>丹麥

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
  
- 函數`Func_denmark_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
- 找到來自`Keywords_denmark_eu_ssn_or_equivalent`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_denmark_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
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

個人身分識別號碼
  
國家識別號碼
  
社會安全號碼
  
nationalnumber#
  
Ssn#
  
Ssn
  
國家/地區號碼
  
個人號碼
  
personalidnumber#
  
cpr-nummer
  
personnummer
  
## <a name="finland"></a>芬蘭

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
  
- 函數`Func_finland_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
- 找到來自`Keywords_finland_eu_ssn_or_equivalent`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_finland_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
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
  
hetu
  
## <a name="france"></a>法國

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「法國社會安全性號碼（INSEE）」一節。
  
## <a name="germany"></a>德國

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「德國身分識別卡片編號」一節。
  
## <a name="greece"></a>希臘

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「希臘國 ID 卡」一節。
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：
  
- 函數`Func_hungary_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
- 找到來自`Keywords_hungary_eu_ssn_or_equivalent`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_hungary_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
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

匈牙利文社交安全性號碼
  
社會安全號碼
  
socialsecuritynumber#
  
hssn#
  
socialsecuritynno
  
hssn
  
泰姬陵
  
泰姬陵#
  
Ssn
  
Ssn#
  
社會安全性否
  
áfa
  
közösségi adószám
  
általános forgalmi adó szám
  
hozzáadottérték adó
  
áfa szám
  
magyar áfa szám
  
## <a name="portugal"></a>葡萄牙

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「葡萄牙公民卡片編號」一節。
  
## <a name="spain"></a>西班牙

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「西班牙社會安全性號碼（SSN）」一節。
  
## <a name="sweden"></a>瑞典

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
  
- 函數`Func_sweden_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
- 找到來自`Keywords_sweden_eu_ssn_or_equivalent`的關鍵字。 
    
如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_sweden_eu_ssn_or_equivalent`會找到符合模式的內容。 
    
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

個人號碼
  
識別號碼
  
個人識別碼否
  
identity no
  
識別碼否
  
個人身分識別否
  
personnummer 識別碼
  
personligt id-nummer
  
unikt id-nummer
  
personnummer
  
identifikationsnumret
  
personnummer#
  
identifikationsnumret#
  
## <a name="see-also"></a>請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

