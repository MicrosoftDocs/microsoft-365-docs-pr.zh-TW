---
title: 歐盟護照號碼
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
description: 本主題說明資料遺失防護（DLP）原則在偵測到歐盟護照號碼機密資訊類型時，會尋找什麼。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
ms.openlocfilehash: 56eb79dd067ca89600f92ea57eaaf01e562f9388
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938737"
---
# <a name="eu-passport-number"></a>歐盟護照號碼

本主題說明資料遺失防護（DLP）原則在偵測到歐盟護照號碼機密資訊類型時，會尋找什麼。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
  
## <a name="austria"></a>奧地利

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
  
- 正則運算式`Regex_austria_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_austria_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_austria_eu_passport_number**|
|:-----|
|護照號碼  <br/> 奧地利護照號碼  <br/> 護照否  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>比利時

### <a name="format"></a>格式

兩個字母后接六位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母后接六位數
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_belgium_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_belgium_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_belgium_eu_passport_number**|
|:-----|
|護照號碼  <br/> 比利時護照號碼  <br/> 護照否  <br/> paspoort  <br/> paspoortnummer  <br/> reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>保加利亞

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_bulgaria_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_bulgaria_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_bulgaria_eu_passport_number**|
|:-----|
|護照號碼  <br/> 保加利亞文護照號碼  <br/> 護照否  <br/> номер на паспорта  <br/> |
   
## <a name="croatia"></a>克羅埃西亞

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_croatia_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_croatia_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_croatia_eu_passport_number**|
|:-----|
|護照號碼  <br/> 克羅地亞護照號碼  <br/> 護照否  <br/> broj putovnice  <br/> |
   
## <a name="cyprus"></a>賽普勒斯

### <a name="format"></a>格式

一個字母后接6-8 位數，沒有空格或分隔符號
  
### <a name="pattern"></a>模式

一個字母后接六個到八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_cyprus_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_cyprus_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_cyprus_eu_passport_number**|
|:-----|
|護照號碼  <br/> 賽普勒斯護照號碼  <br/> 護照否  <br/> αριθμό διαβατηρίου  <br/> |
   
## <a name="czech-republic"></a>捷克共和國

### <a name="format"></a>格式

不含空格或分隔符號的八位數
  
### <a name="pattern"></a>模式

不含空格或分隔符號的八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_czech_republic_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_czech_republic_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_czech_republic_eu_passport_number**|
|:-----|
|護照號碼  <br/> 捷克護照號碼  <br/> 護照否  <br/> cestovní pas  <br/> Pas  <br/> |
   
## <a name="denmark"></a>丹麥

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_denmark_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_denmark_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_denmark_eu_passport_number**|
|:-----|
|護照號碼  <br/> 丹麥文護照號碼  <br/> 護照否  <br/> Pas  <br/> pasnummer  <br/> |
   
## <a name="estonia"></a>愛沙尼亞

### <a name="format"></a>格式

一個字母后接7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

一個字母后接7位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_estonia_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_estonia_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_estonia_eu_passport_number**|
|:-----|
|護照號碼  <br/> 愛沙尼亞文護照號碼  <br/> 護照否  <br/> eesti kodaniku 傳遞  <br/> |
   
## <a name="finland"></a>芬蘭

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「芬蘭護照號碼」一節。
  
## <a name="france"></a>法國

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「法國護照號碼」一節。
  
## <a name="germany"></a>德國

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「德文護照號碼」一節。
  
## <a name="greece"></a>希臘

### <a name="format"></a>格式

兩個字母后接7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母后接7位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_greece_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_greece_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_greece_eu_passport_number**|
|:-----|
|護照號碼  <br/> 希臘文護照號碼  <br/> 護照否  <br/> διαβατηριο  <br/> |
   
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

兩個字母后接六個或7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母后接六位數或七位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_hungary_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_hungary_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_hungary_eu_passport_number**|
|:-----|
|護照號碼  <br/> 匈牙利文護照號碼  <br/> 護照否  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>愛爾蘭

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
  
- 正則運算式`Regex_ireland_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_ireland_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_ireland_eu_passport_number**|
|:-----|
|護照號碼  <br/> 愛爾蘭護照號碼  <br/> 護照否  <br/> Pas  <br/> 護照  <br/> passeport  <br/> passeport numero  <br/> |
   
## <a name="italy"></a>義大利

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
  
- 正則運算式`Regex_italy_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_italy_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_italy_eu_passport_number**|
|:-----|
|義大利護照號碼  <br/> repubblica italiana passaporto  <br/> passaporto  <br/> passaporto italiana  <br/> 護照號碼  <br/> italiana passaporto numero  <br/> passaporto numero  <br/> numéro passeport italien  <br/> numéro passeport  <br/> |
   
## <a name="latvia"></a>拉脫維亞

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
  
- 正則運算式`Regex_latvia_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_latvia_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_latvia_eu_passport_number**|
|:-----|
|護照號碼  <br/> 拉脫維亞文護照號碼  <br/> 護照否  <br/> pase numurs  <br/> |
   
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

八位數的數位或字母，不含空格或分隔符號
  
### <a name="pattern"></a>模式

八位數或字母（不區分大小寫）
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_lithuania_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_lithuania_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_lithuania_eu_passport_number**|
|:-----|
|護照號碼  <br/> lithunian 護照號碼  <br/> 護照否  <br/> paso numeris  <br/> |
   
## <a name="luxemburg"></a>盧森堡

### <a name="format"></a>格式

八位數的數位或字母，不含空格或分隔符號
  
### <a name="pattern"></a>模式

八位數或字母（不區分大小寫）
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_nation_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_nation_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_nation_eu_passport_number**|
|:-----|
|護照號碼  <br/> 拉脫維亞文護照號碼  <br/> 護照否  <br/> passnummer  <br/> |
   
## <a name="malta"></a>馬爾他

### <a name="format"></a>格式

七位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

 七位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_malta_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_malta_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_malta_eu_passport_number**|
|:-----|
|護照號碼  <br/> 馬爾他護照號碼  <br/> 護照否  <br/> numru tal-passaport  <br/> |
   
## <a name="netherlands"></a>荷蘭

### <a name="format"></a>格式

不含空格或分隔符號的九個字母或數位
  
### <a name="pattern"></a>模式

九個字母或數位
  
### <a name="checksum"></a>校驗

不適用
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_netherlands_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_netherlands_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_netherlands_eu_passport_number**|
|:-----|
|荷蘭護照號碼  <br/> 護照號碼  <br/> 荷蘭護照號碼  <br/> nederlanden paspoort nummer  <br/> paspoort  <br/> nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>波蘭

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「波蘭護照號碼」一節。
  
## <a name="portugal"></a>葡萄牙

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
  
- 正則運算式`Regex_portugal_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_portugal_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_portugal_eu_passport_number**|
|:-----|
|護照號碼  <br/> 葡萄牙文護照號碼  <br/> 護照否  <br/> número 執行 passaporte  <br/> |
   
## <a name="romania"></a>羅馬尼亞

### <a name="format"></a>格式

8或9位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

8或9位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_romania_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_romania_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_romania_eu_passport_number**|
|:-----|
|護照號碼  <br/> 羅馬尼亞護照號碼  <br/> 護照否  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

一個數位或字母后接7位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

一個數位或字母（不區分大小寫）後接7位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_slovakia_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_slovakia_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_slovakia_eu_passport_number**|
|:-----|
|護照號碼  <br/> 斯洛伐克護照號碼  <br/> 護照否  <br/> číslo pasu  <br/> |
   
## <a name="slovenia"></a>斯洛維尼亞

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
  
- 正則運算式`Regex_slovenia_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_slovenia_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_slovenia_eu_passport_number**|
|:-----|
|護照號碼  <br/> 斯洛維尼亞護照號碼  <br/> 護照否  <br/> številka potnega lista  <br/> |
   
## <a name="spain"></a>西班牙

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
  
- 正則運算式`Regex_spain_eu_passport_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_spain_eu_passport_number`的關鍵字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_spain_eu_passport_number**|
|:-----|
|護照  <br/> 西班牙護照  <br/> 護照手冊  <br/> 護照號碼  <br/> 護照否  <br/> libreta pasaporte  <br/> número pasaporte  <br/> españa pasaporte  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>瑞典

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「瑞典護照號碼」一節。
  
## <a name="uk"></a>英國

如需詳細資訊，請參閱 section/英國 「[機密資訊類型](what-the-sensitive-information-types-look-for.md)」所尋找的「護照號碼」。
  
## <a name="see-also"></a>另請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

