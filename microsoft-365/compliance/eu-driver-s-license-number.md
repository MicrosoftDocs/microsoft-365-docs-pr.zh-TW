---
title: 歐盟駕照編號
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: 6df025caf8d06c617e09a3b53dc6c82d69aaf5a8
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805956"
---
# <a name="eu-drivers-license-number"></a>歐盟駕照編號

本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
  
## <a name="austria"></a>奧地利

### <a name="format"></a>格式

不含空格，並讓分隔字元的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_austria_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_austria_eu_driver's_license_number`找到。 
    
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
|**Keywords_austria_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式的授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/>  駕駛執照號碼  <br/> dlno#  <br/> fuhrerschein  <br/> fuhrerschein republik osterreich  <br/> |
   
## <a name="belgium"></a>比利時

### <a name="format"></a>格式

如果沒有空格和分隔符號的 10 位數
  
### <a name="pattern"></a>模式

10 位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_belgium_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_belgium_eu_driver's_license_number`找到。 
    
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
|**Keywords__belgium_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> dlno#  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> führerscheinnummer  <br/> fuhrerscheinnummer  <br/> fuehrerscheinnummer  <br/> führerschein 編號  <br/> fuehrerschein 編號  <br/> fuehrerschein 編號  <br/> |
   
## <a name="bulgaria"></a>保加利亞

### <a name="format"></a>格式

如果沒有空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_bulgaria_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_bulgaria_eu_driver's_license_number`找到。 
    
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
|**Keywords_bulgaria_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС  <br/> СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО  <br/> СУМПС  <br/> ШОФЬОРСКА КНИЖКА  <br/> |
   
## <a name="croatia"></a>克羅埃西亞

### <a name="format"></a>格式

不含空格，並讓分隔字元的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_croatia_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_croatia_eu_driver's_license_number`找到。 
    
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
|**Keywords_croatia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> vozačka dozvola  <br/> |
   
## <a name="cyprus"></a>賽普勒斯

### <a name="format"></a>格式

如果沒有空格和分隔符號的 12 位數
  
### <a name="pattern"></a>模式

12 位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_cyprus_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_cyprus_eu_driver's_license_number`找到。 
    
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
|**Keywords_cyprus_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ  <br/> |
   
## <a name="czech-republic"></a>捷克共和國

### <a name="format"></a>格式

兩個字母後尾隨六位數
  
### <a name="pattern"></a>模式

八個字母和數字：
  
- 兩個字母 （不區分大小寫）
    
- 一個空格 （選用）
    
- 六位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_czech_republic_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_czech_republic_eu_driver's_license_number`找到。 
    
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
|**Keywords_czech_republic_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> Řidičský prúkaz  <br/> |
   
## <a name="denmark"></a>丹麥

### <a name="format"></a>格式

不含空格，並讓分隔字元的八位數
  
### <a name="pattern"></a>模式

八位數
  
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_denmark_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_denmark_eu_driver's_license_number`找到。 
    
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
|**Keywords_denmark_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> kørekort  <br/> kørekortnummer  <br/> |
   
## <a name="estonia"></a>愛沙尼亞

### <a name="format"></a>格式

兩個字母後尾隨六位數
  
### <a name="pattern"></a>模式

兩個字母和六位數：
  
-  字母"ET 」 （不區分大小寫） 
    
- 六位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_estonia_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_estonia_eu_driver's_license_number`找到。 
    
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
|**Keywords_estonia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 駕駛執照號碼  <br/> dlno#  <br/> permis de conduire  <br/> |
   
## <a name="finland"></a>芬蘭

### <a name="format"></a>格式

10 位數包含連字號
  
### <a name="pattern"></a>模式

10 位數包含連字號：
  
-  六位數 
    
- 連字號
    
-  四位數 
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_finland_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_finland_eu_driver's_license_number`找到。 
    
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
|**Keywords_finland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> ajokortti  <br/> |
   
## <a name="france"></a>法國

如需詳細資訊，請參閱 「 法國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="germany"></a>德國

如需詳細資訊，請參閱 「 德國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="greece"></a>希臘

### <a name="format"></a>格式

如果沒有空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

 九位數 
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_greece_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_greece_eu_driver's_license_number`找到。 
    
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
|**Keywords_greece_eu_driver's_license_number**|
|:-----|
|dlL#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> ΔΕΙΑ ΟΔΉΓΗΣΗΣ  <br/> Adeia odigisis  <br/> |
   
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

兩個字母後尾隨六位數
  
### <a name="pattern"></a>模式

兩個字母和六位數：
  
-  兩個字母 （不區分大小寫） 
    
- 六位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_hungary_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_hungary_eu_driver's_license_number`找到。 
    
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
|**Keywords_hungary_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> vezetoi engedely  <br/> |
   
## <a name="ireland"></a>愛爾蘭

### <a name="format"></a>格式

四個字母後尾隨六位數
  
### <a name="pattern"></a>模式

六位數和四個字母：
  
- 六位數
    
- 四個字母 （不區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_ireland_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_ireland_eu_driver's_license_number`找到。 
    
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
|**Keywords_ireland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> ceadúnas tiomána  <br/> |
   
## <a name="italy"></a>義大利

如需詳細資訊，請參閱 「 義大利駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="latvia"></a>拉脫維亞

### <a name="format"></a>格式

三個字母後尾隨六位數
  
### <a name="pattern"></a>模式

三個字母和六位數：
  
-  三個字母 （不區分大小寫） 
    
- 六位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_latvia_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_latvia_eu_driver's_license_number`找到。 
    
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
|**Keywords_latvia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> autovadītāja apliecība  <br/> |
   
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

不含空格，並讓分隔字元的八位數
  
### <a name="pattern"></a>模式

 八位數 
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_lithuania_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_lithuania_eu_driver's_license_number`找到。 
    
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
|**Keywords_lithuania_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> vairuotojo pažymėjimas  <br/> |
   
## <a name="luxemburg"></a>盧森堡

### <a name="format"></a>格式

六位數，代表不含空格和分隔符號
  
### <a name="pattern"></a>模式

 六位數 
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_luxemburg_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_luxemburg_eu_driver's_license_number`找到。 
    
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
|**Keywords_luxemburg_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> fahrerlaubnis  <br/> |
   
## <a name="malta"></a>馬爾他

### <a name="format"></a>格式

兩個字元和六位數，代表所指定的型態的組合
  
### <a name="pattern"></a>模式

兩個字元和六位數的組合：
  
- 兩個字元 （數字或字母、 不區分大小寫）
    
- 一個空格 （選用）
    
- 三位數
    
- 一個空格 （選用）
    
- 三位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_malta_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_malta_eu_driver's_license_number`找到。 
    
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
|**Keywords_malta_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> liċenzja 塔司 sewqan  <br/> |
   
## <a name="netherlands"></a>荷蘭

### <a name="format"></a>格式

如果沒有空格和分隔符號的 10 位數
  
### <a name="pattern"></a>模式

10 位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_netherlands_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_netherlands_eu_driver's_license_number`找到。 
    
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
|**Keywords_netherlands_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> permis de conduire  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> |
   
## <a name="poland"></a>波蘭

### <a name="format"></a>格式

14 位數包含正斜線，2
  
### <a name="pattern"></a>模式

14 位數和 2 的正斜線：
  
-  五位數 
    
- 一個正斜線
    
- 兩位數
    
- 一個正斜線
    
- 七位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_poland_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_poland_eu_driver's_license_number`找到。 
    
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
|**Keywords_poland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> prawo jazdy  <br/> |
   
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

兩個字母後尾隨七個的數字中指定的型態
  
### <a name="pattern"></a>模式

兩個字母後尾隨七個具有特殊字元的數字：
  
-  兩個字母 （不區分大小寫） 
    
- 連字號
    
- 六位數
    
- 一個空格
    
- 一位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_portugal_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_portugal_eu_driver's_license_number`找到。 
    
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
|**Keywords_portugal_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> carteira de motorista  <br/> |
   
## <a name="romania"></a>羅馬尼亞

### <a name="format"></a>格式

一個字元尾隨八位數
  
### <a name="pattern"></a>模式

尾隨八位數的一個字元：
  
-  一個字母 （不區分大小寫） 或數字 
    
- 八位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_romania_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_romania_eu_driver's_license_number`找到。 
    
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
|**Keywords_romania_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> permis de conducere  <br/> |
   
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

一個字元尾隨七位數
  
### <a name="pattern"></a>模式

一個字元尾隨七位數
  
- 一個字母 （不區分大小寫） 或數字
    
-  七位數 
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_slovakia_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_slovakia_eu_driver's_license_number`找到。 
    
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
|**Keywords_slovakia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> vodičský preukaz  <br/> |
   
## <a name="slovenia"></a>斯洛維尼亞

### <a name="format"></a>格式

如果沒有空格和分隔符號的九位數
  
### <a name="pattern"></a>模式

九位數
  
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_slovenia_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_slovenia_eu_driver's_license_number`找到。 
    
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
|**Keywords_slovenia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> vozniško dovoljenje  <br/> |
   
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

後面接著一個字元的八位數
  
### <a name="pattern"></a>模式

後面接著一個字元的八位數：
  
-  八位數 
    
- 一個數字或字母 （不區分大小寫）
    
### <a name="checksum"></a>總和檢查碼

是
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 函式`Func_spain_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_spain_eu_driver's_license_number`找到。 
    
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
|**Keywords_spain_eu_driver's_license_number**|
|:-----|
|dlno#  <br/> dl#  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 驅動程式的授權  <br/> 駕照  <br/> driving 授權  <br/> 主導授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權數目  <br/> 驅動程式授權數目  <br/> 驅動程式授權數目  <br/> 驅動程式的授權數目  <br/> 駕照編號  <br/> driving 授權數目  <br/> 駕駛執照號碼  <br/> 主導允許  <br/> 主導允許數字  <br/> permiso de conducción  <br/> permiso conducción  <br/> número licencia conducir  <br/> número de carnet de conducir  <br/> número carnet conducir  <br/> licencia conducir  <br/> número de permiso de conducir  <br/> número de permiso conducir  <br/> número permiso conducir  <br/> permiso conducir  <br/> licencia de manejo  <br/> el carnet de conducir  <br/> carnet conducir  <br/> |
   
## <a name="sweden"></a>瑞典

### <a name="format"></a>格式

10 位數包含連字號
  
### <a name="pattern"></a>模式

10 位數包含連字號：
  
-  六位數 
    
- 連字號
    
- 四位數
    
### <a name="checksum"></a>總和檢查碼

否
  
### <a name="definition"></a>定義

DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：
  
- 規則運算式`Regex_sweden_eu_driver's_license_number`找到符合模式的內容。 
    
- 從關鍵字`Keywords_sweden_eu_driver's_license_number`找到。 
    
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
|**Keywords_sweden_eu_driver's_license_number**|
|:-----|
|dl#  <br/> 驅動程式授權  <br/> 驅動程式授權數目  <br/> 驅動程式授權  <br/> 驅動程式 lic。  <br/> 驅動程式授權  <br/> 驅動程式授權  <br/> 駕照  <br/> 駕照編號  <br/> 驅動程式的授權數目  <br/> 駕駛執照號碼  <br/> dlno#  <br/> körkort  <br/> |
   
## <a name="uk"></a>英國

如需詳細資訊，請參閱區段 」 英國 驅動程式的授權數目 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。
  
## <a name="see-also"></a>另請參閱

[敏感性資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)

