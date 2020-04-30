---
title: 歐盟駕駛執照號碼
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題說明資料遺失防護（DLP）原則在偵測到歐盟駕駛執照的敏感資訊類型時，會尋找哪些專案。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
ms.openlocfilehash: 2e75a8724dc91ef2d895c977fdd5fcc21e7a1da4
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938827"
---
# <a name="eu-drivers-license-number"></a>歐盟駕駛執照號碼

本主題說明資料遺失防護（DLP）原則在偵測到歐盟駕駛執照的敏感資訊類型時，會尋找哪些專案。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

不含空格及分隔符號的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_austria_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_austria_eu_driver's_license_number`的關鍵字。 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_austria_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 駕駛執照  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/>  駕駛執照號碼  <br/> dlno#  <br/> fuhrerschein  <br/> fuhrerschein republik osterreich  <br/> |
   
## <a name="belgium"></a>比利時

### <a name="format"></a>格式

10位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

10位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_belgium_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_belgium_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>關鍵字

| |
|**Keywords__belgium_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> führerscheinnummer  <br/> fuhrerscheinnummer  <br/> fuehrerscheinnummer  <br/> führerschein-nr  <br/> fuehrerschein-Nr  <br/> fuehrerschein-nr  <br/> |
   
## <a name="bulgaria"></a>保加利亞

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_bulgaria_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_bulgaria_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_bulgaria_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> свидетелство за управление на мпс  <br/> свидетелство за управление на моторно превозно средство  <br/> сумпс  <br/> шофьорска книжка  <br/> |
   
## <a name="croatia"></a>克羅埃西亞

### <a name="format"></a>格式

不含空格及分隔符號的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_croatia_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_croatia_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_croatia_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> vozačka dozvola  <br/> |
   
## <a name="cyprus"></a>賽普勒斯

### <a name="format"></a>格式

12位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

12位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_cyprus_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_cyprus_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_cyprus_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> άδεια οδήγησης  <br/> |
   
## <a name="czech-republic"></a>捷克共和國

### <a name="format"></a>格式

兩個字母后接六位數
  
### <a name="pattern"></a>模式

8個字母和數位：
  
- 兩個字母（不區分大小寫）
    
- 一個空格（選用）
    
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_czech_republic_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_czech_republic_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_czech_republic_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> řidičský prúkaz  <br/> |
   
## <a name="denmark"></a>丹麥

### <a name="format"></a>格式

不含空格及分隔符號的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_denmark_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_denmark_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_denmark_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> kørekort  <br/> kørekortnummer  <br/> |
   
## <a name="estonia"></a>愛沙尼亞

### <a name="format"></a>格式

兩個字母后接六位數
  
### <a name="pattern"></a>模式

兩個字母和六位數：
  
-  字母 "ET" （不區分大小寫） 
    
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_estonia_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_estonia_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_estonia_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> permis de conduire  <br/> |
   
## <a name="finland"></a>芬蘭

### <a name="format"></a>格式

10位數包含連字號
  
### <a name="pattern"></a>模式

10位數包含連字號：
  
-  六位數 
    
- 連字號
    
-  四位數 
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_finland_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_finland_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_finland_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> ajokortti  <br/> |
   
## <a name="france"></a>法國

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「法國駕照編號」一節。
  
## <a name="germany"></a>德國

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「德文駕執照號碼」一節。
  
## <a name="greece"></a>希臘

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_greece_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_greece_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_greece_eu_driver ' s_license_number**|
|:-----|
|Dll#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> δεια οδήγησης  <br/> Adeia odigisis  <br/> |
   
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

兩個字母后接六位數
  
### <a name="pattern"></a>模式

兩個字母和六位數：
  
-  兩個字母（不區分大小寫） 
    
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_hungary_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_hungary_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_hungary_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> vezetoi engedely  <br/> |
   
## <a name="ireland"></a>愛爾蘭

### <a name="format"></a>格式

六位數後接四個字母
  
### <a name="pattern"></a>模式

六位數和四個字母：
  
- 六位數
    
- 四個字母（不區分大小寫）
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_ireland_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_ireland_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_ireland_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> ceadúnas tiomána  <br/> |
   
## <a name="italy"></a>義大利

如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「義大利駕照編號」一節。
  
## <a name="latvia"></a>拉脫維亞

### <a name="format"></a>格式

三個字母后接六位數
  
### <a name="pattern"></a>模式

三個字母和六位數：
  
-  三個字母（不區分大小寫） 
    
- 六位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_latvia_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_latvia_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_latvia_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> autovadītāja apliecība  <br/> |
   
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

不含空格及分隔符號的八位數
  
### <a name="pattern"></a>模式

 八位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_lithuania_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_lithuania_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_lithuania_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> vairuotojo pažymėjimas  <br/> |
   
## <a name="luxemburg"></a>盧森堡

### <a name="format"></a>格式

六位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

 六位數 
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_luxemburg_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_luxemburg_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_luxemburg_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> fahrerlaubnis  <br/> |
   
## <a name="malta"></a>馬爾他

### <a name="format"></a>格式

兩個字元的組合，並在指定的模式中包含六位數
  
### <a name="pattern"></a>模式

兩個字元和六位數的組合：
  
- 兩個字元（數位或字母，不區分大小寫）
    
- 一個空格（選用）
    
- 三位數
    
- 一個空格（選用）
    
- 三位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_malta_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_malta_eu_driver's_license_number`的關鍵字。 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_malta_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> liċenzja tas-sewqan  <br/> |
   
## <a name="netherlands"></a>荷蘭

### <a name="format"></a>格式

10位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

10位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_netherlands_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_netherlands_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_netherlands_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> permis de conduire  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> |
   
## <a name="poland"></a>波蘭

### <a name="format"></a>格式

14位數包含2個正斜杠
  
### <a name="pattern"></a>模式

14位數和2轉寄斜線：
  
-  五位數 
    
- 一個正斜線
    
- 兩位數
    
- 一個正斜線
    
- 七位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_poland_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_poland_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_poland_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> prawo jazdy  <br/> |
   
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

兩個字母后接指定的模式中的七個數字
  
### <a name="pattern"></a>模式

兩個字母后接7個含特殊字元的數位：
  
-  兩個字母（不區分大小寫） 
    
- 連字號
    
- 六位數
    
- 一個空格
    
- 一個數位
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_portugal_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_portugal_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_portugal_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> carteira de motorista  <br/> |
   
## <a name="romania"></a>羅馬尼亞

### <a name="format"></a>格式

一個字元後接八位數
  
### <a name="pattern"></a>模式

一個字元後接八位數：
  
-  一個字母（不區分大小寫）或數位 
    
- 八位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_romania_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_romania_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_romania_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> permis de conducere  <br/> |
   
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

一個字元後接7位數
  
### <a name="pattern"></a>模式

一個字元後接7位數
  
- 一個字母（不區分大小寫）或數位
    
-  七位數 
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_slovakia_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_slovakia_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_slovakia_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> vodičský preukaz  <br/> |
   
## <a name="slovenia"></a>斯洛維尼亞

### <a name="format"></a>格式

九位數，不含空格及分隔符號
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_slovenia_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_slovenia_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_slovenia_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> vozniško dovoljenje  <br/> |
   
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

八位數後接一個字元
  
### <a name="pattern"></a>模式

八位數後接一個字元：
  
-  八位數 
    
- 一個數位或字母（不區分大小寫）
    
### <a name="checksum"></a>校驗

是
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 函數`Func_spain_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_spain_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_spain_eu_driver ' s_license_number**|
|:-----|
|dlno#  <br/> Dl#  <br/> 驅動程式 .lic。  <br/> 驅動程式許可證  <br/> 駕照  <br/> 驅動程式許可證  <br/> 驅動程式授權  <br/> 駕駛執照  <br/> 駕駛執照  <br/> 駕駛許可證  <br/> 駕照  <br/> 驅動程式許可證號碼  <br/> 駕駛執照號碼  <br/> 驅動程式許可證數目  <br/> 驅動程式授權號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛許可證號碼  <br/> 駕駛執照號碼  <br/> 駕駛允許  <br/> 駕駛允許號碼  <br/> permiso de conducción  <br/> permiso conducción  <br/> número licencia conducir  <br/> número de carnet de conducir  <br/> número carnet conducir  <br/> licencia conducir  <br/> número de permiso de conducir  <br/> número de permiso conducir  <br/> número permiso conducir  <br/> permiso conducir  <br/> licencia de manejo  <br/> el carnet de conducir  <br/> carnet conducir  <br/> |
   
## <a name="sweden"></a>瑞典

### <a name="format"></a>格式

10位數包含連字號
  
### <a name="pattern"></a>模式

10位數包含連字號：
  
-  六位數 
    
- 連字號
    
- 四位數
    
### <a name="checksum"></a>校驗

否
  
### <a name="definition"></a>定義

如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：
  
- 正則運算式`Regex_sweden_eu_driver's_license_number`會找到符合模式的內容。 
    
- 找到來自`Keywords_sweden_eu_driver's_license_number`的關鍵字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>關鍵字

| |
|**Keywords_sweden_eu_driver ' s_license_number**|
|:-----|
|Dl#  <br/> 駕照  <br/> 駕駛執照號碼  <br/> 驅動程式許可證  <br/> 驅動程式 .lic。  <br/> 驅動程式授權  <br/> 驅動程式許可證  <br/> 駕駛執照  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> 駕駛執照號碼  <br/> dlno#  <br/> körkort  <br/> |
   
## <a name="uk"></a>英國

如需詳細資訊，請參閱 section "英 「[敏感資訊類型](what-the-sensitive-information-types-look-for.md)」所尋找的「駕照編號」。
  
## <a name="see-also"></a>另請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

