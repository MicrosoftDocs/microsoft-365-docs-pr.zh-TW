---
title: 歐盟護照號碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟護照號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077069"
---
# <a name="eu-passport-number"></a>歐盟護照號碼

本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟護照號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

一個字母後尾隨一個選用空格和七位數
  
### <a name="pattern"></a>模式

一個字母、 七位數和一個空格的組合：
  
- 一個字母 （不區分大小寫）
    
- 一個空格 （選用）
    
- 七位數
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_austria_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_austria_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 奧地利護照號碼  <br/> passport 沒有  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>比利時

### <a name="format"></a>格式

兩個字母後尾隨六位數，代表不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母後尾隨六位數和
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_belgium_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_belgium_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 比利時護照號碼  <br/> passport 沒有  <br/> paspoort  <br/> paspoortnummer  <br/> reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>保加利亞

### <a name="format"></a>格式

如果沒有空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_bulgaria_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_bulgaria_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 保加利亞文護照號碼  <br/> passport 沒有  <br/> НОМЕР НА ПАСПОРТА  <br/> |
   
## <a name="croatia"></a>克羅埃西亞

### <a name="format"></a>格式

如果沒有空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_croatia_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_croatia_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 克羅埃西亞文護照號碼  <br/> passport 沒有  <br/> broj putovnice  <br/> |
   
## <a name="cyprus"></a>賽普勒斯

### <a name="format"></a>格式

一個字母後尾隨不含空格或分隔符號 6-8 位數
  
### <a name="pattern"></a>模式

一個字母後尾隨六至八位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_cyprus_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_cyprus_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 賽普勒斯護照號碼  <br/> passport 沒有  <br/> ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ  <br/> |
   
## <a name="czech-republic"></a>捷克共和國

### <a name="format"></a>格式

不含空格或分隔字元的八位數
  
### <a name="pattern"></a>模式

不含空格或分隔字元的八位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_czech_republic_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_czech_republic_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 捷克護照號碼  <br/> passport 沒有  <br/> cestovní pas  <br/> pas  <br/> |
   
## <a name="denmark"></a>丹麥

### <a name="format"></a>格式

如果沒有空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_denmark_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_denmark_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 丹麥文護照號碼  <br/> passport 沒有  <br/> pas  <br/> pasnummer  <br/> |
   
## <a name="estonia"></a>愛沙尼亞

### <a name="format"></a>格式

一個字母後尾隨七位數不含空格或分隔符號
  
### <a name="pattern"></a>模式

一個字母後尾隨七位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_estonia_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_estonia_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 愛沙尼亞文護照號碼  <br/> passport 沒有  <br/> eesti kodaniku 複雜  <br/> |
   
## <a name="finland"></a>芬蘭

如需詳細資訊，請參閱 「 芬蘭護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="france"></a>法國

如需詳細資訊，請參閱 「 法國護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="germany"></a>德國

如需詳細資訊，請參閱 「 德國護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="greece"></a>希臘

### <a name="format"></a>格式

兩個字母後尾隨七位數後不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母後尾隨七位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_greece_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_greece_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 希臘文護照號碼  <br/> passport 沒有  <br/> ΔΙΑΒΑΤΗΡΙΟ  <br/> |
   
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

兩個字母後尾隨六個或七位數，不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母後尾隨六個或七位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_hungary_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_hungary_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 匈牙利文護照號碼  <br/> passport 沒有  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>愛爾蘭

### <a name="format"></a>格式

兩個字母或位數後尾隨七位數後不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母或位數後尾隨七位數：
  
- 兩個數字或字母 （不區分大小寫）
    
- 七位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_ireland_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_ireland_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 愛爾蘭護照號碼  <br/> passport 沒有  <br/> pas  <br/> passport  <br/> passeport  <br/> passeport numero  <br/> |
   
## <a name="italy"></a>義大利

### <a name="format"></a>格式

兩個字母或位數後尾隨七位數後不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母或位數後尾隨七位數：
  
- 兩個數字或字母 （不區分大小寫）
    
- 七位數
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_italy_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_italy_eu_passport_number`找到。 
    
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
|義大利文護照號碼  <br/> repubblica italiana passaporto  <br/> passaporto  <br/> passaporto italiana  <br/> 護照號碼  <br/> italiana passaporto numero  <br/> passaporto numero  <br/> numéro passeport italien  <br/> numéro passeport  <br/> |
   
## <a name="latvia"></a>拉脫維亞

### <a name="format"></a>格式

兩個字母或位數後尾隨七位數後不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母或位數後尾隨七位數：
  
- 兩個數字或字母 （不區分大小寫）
    
- 七位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_latvia_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_latvia_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 拉脫維亞護照號碼  <br/> passport 沒有  <br/> pase numurs  <br/> |
   
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

八個個數字或字母不含空格或分隔符號
  
### <a name="pattern"></a>模式

八個個數字或字母 （不區分大小寫）
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_lithuania_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_lithuania_eu_passport_number`找到。 
    
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
|護照號碼  <br/> lithunian 護照號碼  <br/> passport 沒有  <br/> paso numeris  <br/> |
   
## <a name="luxemburg"></a>盧森堡

### <a name="format"></a>格式

八個個數字或字母不含空格或分隔符號
  
### <a name="pattern"></a>模式

八個個數字或字母 （不區分大小寫）
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_nation_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_nation_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 拉脫維亞護照號碼  <br/> passport 沒有  <br/> passnummer  <br/> |
   
## <a name="malta"></a>馬爾他

### <a name="format"></a>格式

不含空格或分隔符號七位數
  
### <a name="pattern"></a>模式

 七位數 
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_malta_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_malta_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 馬爾他護照號碼  <br/> passport 沒有  <br/> numru tal passaport  <br/> |
   
## <a name="netherlands"></a>荷蘭

### <a name="format"></a>格式

九個字母或不含空格或分隔符號的數字
  
### <a name="pattern"></a>模式

九個字母或四位數
  
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_netherlands_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_netherlands_eu_passport_number`找到。 
    
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
|荷蘭文護照號碼  <br/> 護照號碼  <br/> 荷蘭護照號碼  <br/> nederlanden paspoort nummer  <br/> paspoort  <br/> nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>波蘭

如需詳細資訊，請參閱 「 波蘭護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

一個字母後尾隨六位數，代表不含空格或分隔符號
  
### <a name="pattern"></a>模式

一個字母後尾隨六位數：
  
- 一個字母 （不區分大小寫）
    
- 六位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_portugal_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_portugal_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 葡萄牙文護照號碼  <br/> passport 沒有  <br/> número 不要 passaporte  <br/> |
   
## <a name="romania"></a>羅馬尼亞

### <a name="format"></a>格式

不含空格，並讓分隔字元的八個或九位數
  
### <a name="pattern"></a>模式

八個或九位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_romania_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_romania_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 羅馬尼亞文護照號碼  <br/> passport 沒有  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

一個數字或字母後尾隨七位數後不含空格或分隔符號
  
### <a name="pattern"></a>模式

一個數字或字母 （不區分大小寫） 後尾隨七位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_slovakia_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_slovakia_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 斯洛伐克護照號碼  <br/> passport 沒有  <br/> Číslo pasu  <br/> |
   
## <a name="slovenia"></a>斯洛維尼亞

### <a name="format"></a>格式

兩個字母後尾隨七位數後不含空格或分隔符號
  
### <a name="pattern"></a>模式

兩個字母後尾隨七位數：
  
- 字母"P"
    
- 一個大寫字母
    
- 七位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_slovenia_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_slovenia_eu_passport_number`找到。 
    
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
|護照號碼  <br/> 斯洛維尼亞文護照號碼  <br/> passport 沒有  <br/> Številka potnega lista  <br/> |
   
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

八個或九個字元組合的字母和數字不含空格或分隔符號
  
### <a name="pattern"></a>模式

字母和數字 8 或九個字元組合：
  
-  兩個數字或字母 
    
- 一個數字或字母 （選用）
    
- 六位數
    
### <a name="checksum"></a>總和檢查碼

不適用
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_spain_eu_passport_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_spain_eu_passport_number`找到。 
    
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
|passport  <br/> 西班牙 passport  <br/> passport 活頁簿  <br/> 護照號碼  <br/> passport 沒有  <br/> libreta pasaporte  <br/> número pasaporte  <br/> españa pasaporte  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>瑞典

如需詳細資訊，請參閱 「 瑞典護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="uk"></a>英國

如需詳細資訊，請參閱 「 美國/英國的區段 護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="see-also"></a>請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

