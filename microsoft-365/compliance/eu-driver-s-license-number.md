---
title: 歐盟駕照編號
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
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592654"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="4cdee-104">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-104">EU Driver's License Number</span></span>

<span data-ttu-id="4cdee-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="4cdee-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="4cdee-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="4cdee-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="4cdee-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="4cdee-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-108">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-108">Format</span></span>

<span data-ttu-id="4cdee-109">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-110">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-110">Pattern</span></span>

<span data-ttu-id="4cdee-111">八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4cdee-112">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-112">Checksum</span></span>

<span data-ttu-id="4cdee-113">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-114">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-114">Definition</span></span>

<span data-ttu-id="4cdee-115">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-116">規則運算式`Regex_austria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-117">從關鍵字`Keywords_austria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="4cdee-118">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-118">Keywords</span></span>

<span data-ttu-id="4cdee-119">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-119">| |</span></span>
|<span data-ttu-id="4cdee-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-121">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-121">dl#</span></span>  <br/> <span data-ttu-id="4cdee-122">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-122">driver license</span></span>  <br/> <span data-ttu-id="4cdee-123">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-123">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-124">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-124">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-125">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-125">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-126">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-126">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-127">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-127">driver's licence</span></span>  <br/> <span data-ttu-id="4cdee-128">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-128">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-129">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-129">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-130">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="4cdee-131">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-131">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-132">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4cdee-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="4cdee-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="4cdee-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="4cdee-135">比利時</span><span class="sxs-lookup"><span data-stu-id="4cdee-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-136">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-136">Format</span></span>

<span data-ttu-id="4cdee-137">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-138">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-138">Pattern</span></span>

<span data-ttu-id="4cdee-139">10 位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4cdee-140">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-140">Checksum</span></span>

<span data-ttu-id="4cdee-141">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-142">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-142">Definition</span></span>

<span data-ttu-id="4cdee-143">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-144">規則運算式`Regex_belgium_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-145">從關鍵字`Keywords_belgium_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="4cdee-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-146">Keywords</span></span>

<span data-ttu-id="4cdee-147">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-147">| |</span></span>
|<span data-ttu-id="4cdee-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-149">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-149">dl#</span></span>  <br/> <span data-ttu-id="4cdee-150">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-150">driver license</span></span>  <br/> <span data-ttu-id="4cdee-151">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-151">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-152">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-152">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-153">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-153">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-154">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-154">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-155">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-155">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-156">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-156">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-157">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-157">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-158">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-158">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-159">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="4cdee-160">rijbewijs</span></span>  <br/> <span data-ttu-id="4cdee-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="4cdee-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="4cdee-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="4cdee-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="4cdee-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="4cdee-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="4cdee-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="4cdee-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="4cdee-165">führerschein 編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="4cdee-166">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="4cdee-167">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="4cdee-168">保加利亞</span><span class="sxs-lookup"><span data-stu-id="4cdee-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-169">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-169">Format</span></span>

<span data-ttu-id="4cdee-170">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-171">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-171">Pattern</span></span>

<span data-ttu-id="4cdee-172">九位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4cdee-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-173">Checksum</span></span>

<span data-ttu-id="4cdee-174">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-175">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-175">Definition</span></span>

<span data-ttu-id="4cdee-176">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-177">規則運算式`Regex_bulgaria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-178">從關鍵字`Keywords_bulgaria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="4cdee-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-179">Keywords</span></span>

<span data-ttu-id="4cdee-180">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-180">| |</span></span>
|<span data-ttu-id="4cdee-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-182">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-182">dl#</span></span>  <br/> <span data-ttu-id="4cdee-183">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-183">driver license</span></span>  <br/> <span data-ttu-id="4cdee-184">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-184">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-185">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-185">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-186">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-186">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-187">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-187">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-188">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-188">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-189">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-189">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-190">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-190">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-191">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-191">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-192">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-192">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-193">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-194">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС</span><span class="sxs-lookup"><span data-stu-id="4cdee-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="4cdee-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="4cdee-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="4cdee-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="4cdee-196">сумпс</span></span>  <br/> <span data-ttu-id="4cdee-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="4cdee-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="4cdee-198">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="4cdee-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-199">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-199">Format</span></span>

<span data-ttu-id="4cdee-200">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-201">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-201">Pattern</span></span>

<span data-ttu-id="4cdee-202">八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4cdee-203">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-203">Checksum</span></span>

<span data-ttu-id="4cdee-204">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-205">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-205">Definition</span></span>

<span data-ttu-id="4cdee-206">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-207">規則運算式`Regex_croatia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-208">從關鍵字`Keywords_croatia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="4cdee-209">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-209">Keywords</span></span>

<span data-ttu-id="4cdee-210">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-210">| |</span></span>
|<span data-ttu-id="4cdee-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-212">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-212">dl#</span></span>  <br/> <span data-ttu-id="4cdee-213">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-213">driver license</span></span>  <br/> <span data-ttu-id="4cdee-214">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-214">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-215">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-215">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-216">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-216">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-217">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-217">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-218">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-218">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-219">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-219">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-220">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-220">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-221">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-221">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-222">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-222">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-223">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="4cdee-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="4cdee-225">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="4cdee-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-226">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-226">Format</span></span>

<span data-ttu-id="4cdee-227">如果沒有空格和分隔符號的 12 位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-228">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-228">Pattern</span></span>

<span data-ttu-id="4cdee-229">12 位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4cdee-230">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-230">Checksum</span></span>

<span data-ttu-id="4cdee-231">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-232">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-232">Definition</span></span>

<span data-ttu-id="4cdee-233">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-234">規則運算式`Regex_cyprus_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-235">從關鍵字`Keywords_cyprus_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-236">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-236">Keywords</span></span>

<span data-ttu-id="4cdee-237">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-237">| |</span></span>
|<span data-ttu-id="4cdee-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-239">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-239">dl#</span></span>  <br/> <span data-ttu-id="4cdee-240">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-240">driver license</span></span>  <br/> <span data-ttu-id="4cdee-241">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-241">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-242">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-242">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-243">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-243">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-244">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-244">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-245">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-245">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-246">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-246">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-247">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-247">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-248">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-248">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-249">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="4cdee-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="4cdee-251">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="4cdee-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-252">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-252">Format</span></span>

<span data-ttu-id="4cdee-253">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-254">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-254">Pattern</span></span>

<span data-ttu-id="4cdee-255">八個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="4cdee-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="4cdee-256">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="4cdee-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="4cdee-257">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="4cdee-257">A space (optional)</span></span>
    
- <span data-ttu-id="4cdee-258">六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4cdee-259">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-259">Checksum</span></span>

<span data-ttu-id="4cdee-260">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-261">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-261">Definition</span></span>

<span data-ttu-id="4cdee-262">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-263">規則運算式`Regex_czech_republic_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-264">從關鍵字`Keywords_czech_republic_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="4cdee-265">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-265">Keywords</span></span>

<span data-ttu-id="4cdee-266">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-266">| |</span></span>
|<span data-ttu-id="4cdee-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-268">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-268">dl#</span></span>  <br/> <span data-ttu-id="4cdee-269">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-269">driver license</span></span>  <br/> <span data-ttu-id="4cdee-270">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-270">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-271">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-271">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-272">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-272">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-273">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-273">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-274">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-274">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-275">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-275">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-276">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-276">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-277">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-277">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-278">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-278">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-279">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-279">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-280">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="4cdee-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="4cdee-282">丹麥</span><span class="sxs-lookup"><span data-stu-id="4cdee-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-283">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-283">Format</span></span>

<span data-ttu-id="4cdee-284">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-285">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-285">Pattern</span></span>

<span data-ttu-id="4cdee-286">八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4cdee-287">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-287">Checksum</span></span>

<span data-ttu-id="4cdee-288">是</span><span class="sxs-lookup"><span data-stu-id="4cdee-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-289">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-289">Definition</span></span>

<span data-ttu-id="4cdee-290">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-291">規則運算式`Regex_denmark_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-292">從關鍵字`Keywords_denmark_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="4cdee-293">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-293">Keywords</span></span>

<span data-ttu-id="4cdee-294">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-294">| |</span></span>
|<span data-ttu-id="4cdee-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-296">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-296">dl#</span></span>  <br/> <span data-ttu-id="4cdee-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-297">driver license</span></span>  <br/> <span data-ttu-id="4cdee-298">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-298">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-299">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-299">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-300">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-300">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-301">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-302">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-302">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-303">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-303">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-304">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-304">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-305">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-305">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-306">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-306">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-307">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="4cdee-308">kørekort</span></span>  <br/> <span data-ttu-id="4cdee-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="4cdee-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="4cdee-310">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="4cdee-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-311">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-311">Format</span></span>

<span data-ttu-id="4cdee-312">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-313">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-313">Pattern</span></span>

<span data-ttu-id="4cdee-314">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="4cdee-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="4cdee-315">字母"ET 」 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="4cdee-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="4cdee-316">六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4cdee-317">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-317">Checksum</span></span>

<span data-ttu-id="4cdee-318">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-319">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-319">Definition</span></span>

<span data-ttu-id="4cdee-320">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-321">規則運算式`Regex_estonia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-322">從關鍵字`Keywords_estonia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-323">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-323">Keywords</span></span>

<span data-ttu-id="4cdee-324">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-324">| |</span></span>
|<span data-ttu-id="4cdee-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-326">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-326">dl#</span></span>  <br/> <span data-ttu-id="4cdee-327">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-327">driver license</span></span>  <br/> <span data-ttu-id="4cdee-328">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-328">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-329">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-329">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-330">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-330">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-331">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-331">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-332">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-332">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-333">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-333">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-334">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-334">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-335">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-335">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-336">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-336">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-337">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="4cdee-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="4cdee-339">芬蘭</span><span class="sxs-lookup"><span data-stu-id="4cdee-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-340">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-340">Format</span></span>

<span data-ttu-id="4cdee-341">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="4cdee-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-342">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-342">Pattern</span></span>

<span data-ttu-id="4cdee-343">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="4cdee-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="4cdee-344">六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-344">Six digits</span></span> 
    
- <span data-ttu-id="4cdee-345">連字號</span><span class="sxs-lookup"><span data-stu-id="4cdee-345">A hyphen</span></span>
    
-  <span data-ttu-id="4cdee-346">四位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4cdee-347">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-347">Checksum</span></span>

<span data-ttu-id="4cdee-348">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-349">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-349">Definition</span></span>

<span data-ttu-id="4cdee-350">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-351">規則運算式`Regex_finland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-352">從關鍵字`Keywords_finland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-353">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-353">Keywords</span></span>

<span data-ttu-id="4cdee-354">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-354">| |</span></span>
|<span data-ttu-id="4cdee-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-356">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-356">dl#</span></span>  <br/> <span data-ttu-id="4cdee-357">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-357">driver license</span></span>  <br/> <span data-ttu-id="4cdee-358">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-358">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-359">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-359">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-360">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-360">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-361">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-361">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-362">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-362">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-363">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-363">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-364">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-364">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-365">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-365">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-366">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-366">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-367">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="4cdee-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="4cdee-369">法國</span><span class="sxs-lookup"><span data-stu-id="4cdee-369">France</span></span>

<span data-ttu-id="4cdee-370">如需詳細資訊，請參閱 「 法國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="4cdee-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="4cdee-371">德國</span><span class="sxs-lookup"><span data-stu-id="4cdee-371">Germany</span></span>

<span data-ttu-id="4cdee-372">如需詳細資訊，請參閱 「 德國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="4cdee-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="4cdee-373">希臘</span><span class="sxs-lookup"><span data-stu-id="4cdee-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-374">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-374">Format</span></span>

<span data-ttu-id="4cdee-375">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-376">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-376">Pattern</span></span>

 <span data-ttu-id="4cdee-377">九位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="4cdee-378">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-378">Checksum</span></span>

<span data-ttu-id="4cdee-379">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-380">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-380">Definition</span></span>

<span data-ttu-id="4cdee-381">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-382">規則運算式`Regex_greece_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-383">從關鍵字`Keywords_greece_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-384">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-384">Keywords</span></span>

<span data-ttu-id="4cdee-385">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-385">| |</span></span>
|<span data-ttu-id="4cdee-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-387">dlL#</span><span class="sxs-lookup"><span data-stu-id="4cdee-387">dlL#</span></span>  <br/> <span data-ttu-id="4cdee-388">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-388">driver license</span></span>  <br/> <span data-ttu-id="4cdee-389">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-389">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-390">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-390">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-391">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-391">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-392">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-392">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-393">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-393">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-394">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-394">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-395">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-395">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-396">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-396">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-397">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-397">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-398">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="4cdee-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="4cdee-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="4cdee-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="4cdee-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="4cdee-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-402">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-402">Format</span></span>

<span data-ttu-id="4cdee-403">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-404">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-404">Pattern</span></span>

<span data-ttu-id="4cdee-405">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="4cdee-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="4cdee-406">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="4cdee-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="4cdee-407">六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4cdee-408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-408">Checksum</span></span>

<span data-ttu-id="4cdee-409">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-410">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-410">Definition</span></span>

<span data-ttu-id="4cdee-411">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-412">規則運算式`Regex_hungary_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-413">從關鍵字`Keywords_hungary_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-414">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-414">Keywords</span></span>

<span data-ttu-id="4cdee-415">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-415">| |</span></span>
|<span data-ttu-id="4cdee-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-417">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-417">dl#</span></span>  <br/> <span data-ttu-id="4cdee-418">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-418">driver license</span></span>  <br/> <span data-ttu-id="4cdee-419">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-419">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-420">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-420">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-421">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-421">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-422">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-422">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-423">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-423">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-424">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-424">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-425">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-425">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-426">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-426">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-427">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-427">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-428">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="4cdee-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="4cdee-430">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="4cdee-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-431">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-431">Format</span></span>

<span data-ttu-id="4cdee-432">四個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-433">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-433">Pattern</span></span>

<span data-ttu-id="4cdee-434">六位數和四個字母：</span><span class="sxs-lookup"><span data-stu-id="4cdee-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="4cdee-435">六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-435">Six digits</span></span>
    
- <span data-ttu-id="4cdee-436">四個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="4cdee-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4cdee-437">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-437">Checksum</span></span>

<span data-ttu-id="4cdee-438">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-439">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-439">Definition</span></span>

<span data-ttu-id="4cdee-440">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-441">規則運算式`Regex_ireland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-442">從關鍵字`Keywords_ireland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-443">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-443">Keywords</span></span>

<span data-ttu-id="4cdee-444">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-444">| |</span></span>
|<span data-ttu-id="4cdee-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-446">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-446">dl#</span></span>  <br/> <span data-ttu-id="4cdee-447">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-447">driver license</span></span>  <br/> <span data-ttu-id="4cdee-448">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-448">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-449">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-449">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-450">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-450">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-451">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-451">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-452">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-452">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-453">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-453">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-454">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-454">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-455">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-455">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-456">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-456">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-457">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="4cdee-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="4cdee-459">義大利</span><span class="sxs-lookup"><span data-stu-id="4cdee-459">Italy</span></span>

<span data-ttu-id="4cdee-460">如需詳細資訊，請參閱 「 義大利駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="4cdee-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="4cdee-461">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="4cdee-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-462">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-462">Format</span></span>

<span data-ttu-id="4cdee-463">三個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-464">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-464">Pattern</span></span>

<span data-ttu-id="4cdee-465">三個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="4cdee-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="4cdee-466">三個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="4cdee-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="4cdee-467">六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4cdee-468">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-468">Checksum</span></span>

<span data-ttu-id="4cdee-469">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-470">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-470">Definition</span></span>

<span data-ttu-id="4cdee-471">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-472">規則運算式`Regex_latvia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-473">從關鍵字`Keywords_latvia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-474">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-474">Keywords</span></span>

<span data-ttu-id="4cdee-475">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-475">| |</span></span>
|<span data-ttu-id="4cdee-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-477">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-477">dl#</span></span>  <br/> <span data-ttu-id="4cdee-478">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-478">driver license</span></span>  <br/> <span data-ttu-id="4cdee-479">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-479">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-480">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-480">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-481">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-481">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-482">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-482">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-483">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-483">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-484">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-484">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-485">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-485">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-486">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-486">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-487">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-487">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-488">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="4cdee-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="4cdee-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="4cdee-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-491">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-491">Format</span></span>

<span data-ttu-id="4cdee-492">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-493">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-493">Pattern</span></span>

 <span data-ttu-id="4cdee-494">八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="4cdee-495">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-495">Checksum</span></span>

<span data-ttu-id="4cdee-496">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-497">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-497">Definition</span></span>

<span data-ttu-id="4cdee-498">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-499">規則運算式`Regex_lithuania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-500">從關鍵字`Keywords_lithuania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-501">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-501">Keywords</span></span>

<span data-ttu-id="4cdee-502">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-502">| |</span></span>
|<span data-ttu-id="4cdee-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-504">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-504">dl#</span></span>  <br/> <span data-ttu-id="4cdee-505">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-505">driver license</span></span>  <br/> <span data-ttu-id="4cdee-506">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-506">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-507">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-507">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-508">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-508">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-509">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-509">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-510">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-510">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-511">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-511">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-512">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-512">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-513">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-513">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-514">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-514">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-515">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="4cdee-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="4cdee-517">盧森堡</span><span class="sxs-lookup"><span data-stu-id="4cdee-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-518">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-518">Format</span></span>

<span data-ttu-id="4cdee-519">六位數，代表不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="4cdee-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-520">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-520">Pattern</span></span>

 <span data-ttu-id="4cdee-521">六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="4cdee-522">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-522">Checksum</span></span>

<span data-ttu-id="4cdee-523">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-524">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-524">Definition</span></span>

<span data-ttu-id="4cdee-525">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-526">規則運算式`Regex_luxemburg_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-527">從關鍵字`Keywords_luxemburg_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-528">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-528">Keywords</span></span>

<span data-ttu-id="4cdee-529">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-529">| |</span></span>
|<span data-ttu-id="4cdee-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-531">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-531">dl#</span></span>  <br/> <span data-ttu-id="4cdee-532">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-532">driver license</span></span>  <br/> <span data-ttu-id="4cdee-533">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-533">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-534">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-534">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-535">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-535">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-536">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-536">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-537">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-537">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-538">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-538">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-539">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-539">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-540">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-540">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-541">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-541">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-542">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="4cdee-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="4cdee-544">馬爾他</span><span class="sxs-lookup"><span data-stu-id="4cdee-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-545">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-545">Format</span></span>

<span data-ttu-id="4cdee-546">兩個字元和六位數，代表所指定的型態的組合</span><span class="sxs-lookup"><span data-stu-id="4cdee-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-547">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-547">Pattern</span></span>

<span data-ttu-id="4cdee-548">兩個字元和六位數的組合：</span><span class="sxs-lookup"><span data-stu-id="4cdee-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="4cdee-549">兩個字元 （數字或字母、 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="4cdee-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="4cdee-550">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="4cdee-550">A space (optional)</span></span>
    
- <span data-ttu-id="4cdee-551">三位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-551">Three digits</span></span>
    
- <span data-ttu-id="4cdee-552">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="4cdee-552">A space (optional)</span></span>
    
- <span data-ttu-id="4cdee-553">三位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4cdee-554">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-554">Checksum</span></span>

<span data-ttu-id="4cdee-555">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-556">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-556">Definition</span></span>

<span data-ttu-id="4cdee-557">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-558">規則運算式`Regex_malta_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-559">從關鍵字`Keywords_malta_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-560">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-560">Keywords</span></span>

<span data-ttu-id="4cdee-561">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-561">| |</span></span>
|<span data-ttu-id="4cdee-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-563">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-563">dl#</span></span>  <br/> <span data-ttu-id="4cdee-564">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-564">driver license</span></span>  <br/> <span data-ttu-id="4cdee-565">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-565">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-566">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-566">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-567">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-567">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-568">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-568">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-569">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-569">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-570">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-570">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-571">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-571">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-572">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-572">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-573">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-573">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-574">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-575">liċenzja 塔司 sewqan</span><span class="sxs-lookup"><span data-stu-id="4cdee-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="4cdee-576">荷蘭</span><span class="sxs-lookup"><span data-stu-id="4cdee-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-577">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-577">Format</span></span>

<span data-ttu-id="4cdee-578">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-579">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-579">Pattern</span></span>

<span data-ttu-id="4cdee-580">10 位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4cdee-581">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-581">Checksum</span></span>

<span data-ttu-id="4cdee-582">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-583">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-583">Definition</span></span>

<span data-ttu-id="4cdee-584">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-585">規則運算式`Regex_netherlands_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-586">從關鍵字`Keywords_netherlands_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-587">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-587">Keywords</span></span>

<span data-ttu-id="4cdee-588">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-588">| |</span></span>
|<span data-ttu-id="4cdee-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-590">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-590">dl#</span></span>  <br/> <span data-ttu-id="4cdee-591">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-591">driver license</span></span>  <br/> <span data-ttu-id="4cdee-592">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-592">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-593">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-593">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-594">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-594">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-595">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-595">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-596">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-596">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-597">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-597">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-598">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-598">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-599">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-599">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-600">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-600">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-601">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="4cdee-602">permis de conduire</span></span>  <br/> <span data-ttu-id="4cdee-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="4cdee-603">rijbewijs</span></span>  <br/> <span data-ttu-id="4cdee-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="4cdee-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="4cdee-605">波蘭</span><span class="sxs-lookup"><span data-stu-id="4cdee-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-606">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-606">Format</span></span>

<span data-ttu-id="4cdee-607">14 位數包含正斜線，2</span><span class="sxs-lookup"><span data-stu-id="4cdee-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-608">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-608">Pattern</span></span>

<span data-ttu-id="4cdee-609">14 位數和 2 的正斜線：</span><span class="sxs-lookup"><span data-stu-id="4cdee-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="4cdee-610">五位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-610">Five digits</span></span> 
    
- <span data-ttu-id="4cdee-611">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="4cdee-611">A forward slash</span></span>
    
- <span data-ttu-id="4cdee-612">兩位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-612">Two digits</span></span>
    
- <span data-ttu-id="4cdee-613">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="4cdee-613">A forward slash</span></span>
    
- <span data-ttu-id="4cdee-614">七位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4cdee-615">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-615">Checksum</span></span>

<span data-ttu-id="4cdee-616">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-617">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-617">Definition</span></span>

<span data-ttu-id="4cdee-618">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-619">規則運算式`Regex_poland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-620">從關鍵字`Keywords_poland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-621">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-621">Keywords</span></span>

<span data-ttu-id="4cdee-622">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-622">| |</span></span>
|<span data-ttu-id="4cdee-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-624">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-624">dl#</span></span>  <br/> <span data-ttu-id="4cdee-625">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-625">driver license</span></span>  <br/> <span data-ttu-id="4cdee-626">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-626">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-627">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-627">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-628">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-628">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-629">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-629">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-630">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-630">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-631">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-631">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-632">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-632">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-633">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-633">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-634">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-634">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-635">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="4cdee-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="4cdee-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="4cdee-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-638">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-638">Format</span></span>

<span data-ttu-id="4cdee-639">兩個字母後尾隨七個的數字中指定的型態</span><span class="sxs-lookup"><span data-stu-id="4cdee-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-640">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-640">Pattern</span></span>

<span data-ttu-id="4cdee-641">兩個字母後尾隨七個具有特殊字元的數字：</span><span class="sxs-lookup"><span data-stu-id="4cdee-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="4cdee-642">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="4cdee-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="4cdee-643">連字號</span><span class="sxs-lookup"><span data-stu-id="4cdee-643">A hyphen</span></span>
    
- <span data-ttu-id="4cdee-644">六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-644">Six digits</span></span>
    
- <span data-ttu-id="4cdee-645">一個空格</span><span class="sxs-lookup"><span data-stu-id="4cdee-645">A space</span></span>
    
- <span data-ttu-id="4cdee-646">一位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4cdee-647">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-647">Checksum</span></span>

<span data-ttu-id="4cdee-648">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-649">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-649">Definition</span></span>

<span data-ttu-id="4cdee-650">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-651">規則運算式`Regex_portugal_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-652">從關鍵字`Keywords_portugal_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-653">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-653">Keywords</span></span>

<span data-ttu-id="4cdee-654">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-654">| |</span></span>
|<span data-ttu-id="4cdee-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-656">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-656">dl#</span></span>  <br/> <span data-ttu-id="4cdee-657">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-657">driver license</span></span>  <br/> <span data-ttu-id="4cdee-658">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-658">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-659">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-659">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-660">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-660">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-661">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-661">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-662">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-662">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-663">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-663">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-664">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-664">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-665">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-665">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-666">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-666">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-667">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="4cdee-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="4cdee-669">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="4cdee-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-670">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-670">Format</span></span>

<span data-ttu-id="4cdee-671">一個字元尾隨八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-672">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-672">Pattern</span></span>

<span data-ttu-id="4cdee-673">尾隨八位數的一個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="4cdee-674">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="4cdee-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="4cdee-675">八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4cdee-676">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-676">Checksum</span></span>

<span data-ttu-id="4cdee-677">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-678">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-678">Definition</span></span>

<span data-ttu-id="4cdee-679">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-680">規則運算式`Regex_romania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-681">從關鍵字`Keywords_romania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-682">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-682">Keywords</span></span>

<span data-ttu-id="4cdee-683">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-683">| |</span></span>
|<span data-ttu-id="4cdee-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-685">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-685">dl#</span></span>  <br/> <span data-ttu-id="4cdee-686">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-686">driver license</span></span>  <br/> <span data-ttu-id="4cdee-687">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-687">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-688">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-688">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-689">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-689">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-690">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-690">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-691">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-691">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-692">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-692">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-693">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-693">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-694">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-694">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-695">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-695">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-696">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="4cdee-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="4cdee-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="4cdee-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-699">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-699">Format</span></span>

<span data-ttu-id="4cdee-700">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-701">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-701">Pattern</span></span>

<span data-ttu-id="4cdee-702">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="4cdee-703">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="4cdee-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="4cdee-704">七位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="4cdee-705">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-705">Checksum</span></span>

<span data-ttu-id="4cdee-706">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-707">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-707">Definition</span></span>

<span data-ttu-id="4cdee-708">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-709">規則運算式`Regex_slovakia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-710">從關鍵字`Keywords_slovakia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-711">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-711">Keywords</span></span>

<span data-ttu-id="4cdee-712">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-712">| |</span></span>
|<span data-ttu-id="4cdee-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-714">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-714">dl#</span></span>  <br/> <span data-ttu-id="4cdee-715">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-715">driver license</span></span>  <br/> <span data-ttu-id="4cdee-716">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-716">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-717">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-717">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-718">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-718">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-719">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-719">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-720">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-720">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-721">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-721">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-722">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-722">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-723">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-723">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-724">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-724">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-725">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="4cdee-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="4cdee-727">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="4cdee-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-728">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-728">Format</span></span>

<span data-ttu-id="4cdee-729">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-730">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-730">Pattern</span></span>

<span data-ttu-id="4cdee-731">九位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4cdee-732">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-732">Checksum</span></span>

<span data-ttu-id="4cdee-733">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-734">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-734">Definition</span></span>

<span data-ttu-id="4cdee-735">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-736">規則運算式`Regex_slovenia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-737">從關鍵字`Keywords_slovenia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-738">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-738">Keywords</span></span>

<span data-ttu-id="4cdee-739">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-739">| |</span></span>
|<span data-ttu-id="4cdee-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-741">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-741">dl#</span></span>  <br/> <span data-ttu-id="4cdee-742">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-742">driver license</span></span>  <br/> <span data-ttu-id="4cdee-743">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-743">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-744">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-744">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-745">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-745">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-746">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-746">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-747">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-747">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-748">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-748">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-749">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-749">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-750">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-750">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-751">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-751">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-752">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="4cdee-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="4cdee-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="4cdee-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-755">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-755">Format</span></span>

<span data-ttu-id="4cdee-756">後面接著一個字元的八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-757">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-757">Pattern</span></span>

<span data-ttu-id="4cdee-758">後面接著一個字元的八位數：</span><span class="sxs-lookup"><span data-stu-id="4cdee-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="4cdee-759">八位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-759">Eight digits</span></span> 
    
- <span data-ttu-id="4cdee-760">一個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="4cdee-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4cdee-761">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-761">Checksum</span></span>

<span data-ttu-id="4cdee-762">是</span><span class="sxs-lookup"><span data-stu-id="4cdee-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-763">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-763">Definition</span></span>

<span data-ttu-id="4cdee-764">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-765">函式`Func_spain_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-766">從關鍵字`Keywords_spain_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4cdee-767">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-767">Keywords</span></span>

<span data-ttu-id="4cdee-768">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-768">| |</span></span>
|<span data-ttu-id="4cdee-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-770">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-771">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-771">dl#</span></span>  <br/> <span data-ttu-id="4cdee-772">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-772">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-773">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-773">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-774">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-774">driver license</span></span>  <br/> <span data-ttu-id="4cdee-775">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-775">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-776">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-776">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-777">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-777">driver's licence</span></span>  <br/> <span data-ttu-id="4cdee-778">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-778">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-779">driving 授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-779">driving licence</span></span>  <br/> <span data-ttu-id="4cdee-780">主導授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-780">driving license</span></span>  <br/> <span data-ttu-id="4cdee-781">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-781">driver licence number</span></span>  <br/> <span data-ttu-id="4cdee-782">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-782">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-783">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-783">drivers licence number</span></span>  <br/> <span data-ttu-id="4cdee-784">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-784">drivers license number</span></span>  <br/> <span data-ttu-id="4cdee-785">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-785">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-786">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-786">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-787">driving 授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-787">driving licence number</span></span>  <br/> <span data-ttu-id="4cdee-788">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-788">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-789">主導允許</span><span class="sxs-lookup"><span data-stu-id="4cdee-789">driving permit</span></span>  <br/> <span data-ttu-id="4cdee-790">主導允許數字</span><span class="sxs-lookup"><span data-stu-id="4cdee-790">driving permit number</span></span>  <br/> <span data-ttu-id="4cdee-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="4cdee-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="4cdee-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="4cdee-792">permiso conducción</span></span>  <br/> <span data-ttu-id="4cdee-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="4cdee-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="4cdee-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="4cdee-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="4cdee-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="4cdee-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="4cdee-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="4cdee-796">licencia conducir</span></span>  <br/> <span data-ttu-id="4cdee-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="4cdee-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="4cdee-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="4cdee-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="4cdee-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="4cdee-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="4cdee-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="4cdee-800">permiso conducir</span></span>  <br/> <span data-ttu-id="4cdee-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="4cdee-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="4cdee-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="4cdee-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="4cdee-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="4cdee-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="4cdee-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="4cdee-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="4cdee-805">格式</span><span class="sxs-lookup"><span data-stu-id="4cdee-805">Format</span></span>

<span data-ttu-id="4cdee-806">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="4cdee-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4cdee-807">模式</span><span class="sxs-lookup"><span data-stu-id="4cdee-807">Pattern</span></span>

<span data-ttu-id="4cdee-808">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="4cdee-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="4cdee-809">六位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-809">Six digits</span></span> 
    
- <span data-ttu-id="4cdee-810">連字號</span><span class="sxs-lookup"><span data-stu-id="4cdee-810">A hyphen</span></span>
    
- <span data-ttu-id="4cdee-811">四位數</span><span class="sxs-lookup"><span data-stu-id="4cdee-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4cdee-812">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-812">Checksum</span></span>

<span data-ttu-id="4cdee-813">否</span><span class="sxs-lookup"><span data-stu-id="4cdee-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="4cdee-814">定義</span><span class="sxs-lookup"><span data-stu-id="4cdee-814">Definition</span></span>

<span data-ttu-id="4cdee-815">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="4cdee-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4cdee-816">規則運算式`Regex_sweden_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="4cdee-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4cdee-817">從關鍵字`Keywords_sweden_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="4cdee-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="4cdee-818">關鍵字</span><span class="sxs-lookup"><span data-stu-id="4cdee-818">Keywords</span></span>

<span data-ttu-id="4cdee-819">| |</span><span class="sxs-lookup"><span data-stu-id="4cdee-819">| |</span></span>
|<span data-ttu-id="4cdee-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="4cdee-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="4cdee-821">dl#</span><span class="sxs-lookup"><span data-stu-id="4cdee-821">dl#</span></span>  <br/> <span data-ttu-id="4cdee-822">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-822">driver license</span></span>  <br/> <span data-ttu-id="4cdee-823">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-823">driver license number</span></span>  <br/> <span data-ttu-id="4cdee-824">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-824">driver licence</span></span>  <br/> <span data-ttu-id="4cdee-825">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="4cdee-825">drivers lic.</span></span>  <br/> <span data-ttu-id="4cdee-826">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-826">drivers license</span></span>  <br/> <span data-ttu-id="4cdee-827">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="4cdee-827">drivers licence</span></span>  <br/> <span data-ttu-id="4cdee-828">駕照</span><span class="sxs-lookup"><span data-stu-id="4cdee-828">driver's license</span></span>  <br/> <span data-ttu-id="4cdee-829">駕照編號</span><span class="sxs-lookup"><span data-stu-id="4cdee-829">driver's license number</span></span>  <br/> <span data-ttu-id="4cdee-830">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="4cdee-830">driver's licence number</span></span>  <br/> <span data-ttu-id="4cdee-831">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="4cdee-831">driving license number</span></span>  <br/> <span data-ttu-id="4cdee-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="4cdee-832">dlno#</span></span>  <br/> <span data-ttu-id="4cdee-833">körkort</span><span class="sxs-lookup"><span data-stu-id="4cdee-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="4cdee-834">英國</span><span class="sxs-lookup"><span data-stu-id="4cdee-834">UK</span></span>

<span data-ttu-id="4cdee-835">如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="4cdee-835">For details, see the section "U.K.</span></span> <span data-ttu-id="4cdee-836">驅動程式的授權數目 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="4cdee-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4cdee-837">請參閱</span><span class="sxs-lookup"><span data-stu-id="4cdee-837">See also</span></span>

[<span data-ttu-id="4cdee-838">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="4cdee-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

