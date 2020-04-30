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
# <a name="eu-drivers-license-number"></a><span data-ttu-id="30200-104">歐盟駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-104">EU Driver's License Number</span></span>

<span data-ttu-id="30200-105">本主題說明資料遺失防護（DLP）原則在偵測到歐盟駕駛執照的敏感資訊類型時，會尋找哪些專案。</span><span class="sxs-lookup"><span data-stu-id="30200-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="30200-106">這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。</span><span class="sxs-lookup"><span data-stu-id="30200-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="30200-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="30200-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="30200-108">格式</span><span class="sxs-lookup"><span data-stu-id="30200-108">Format</span></span>

<span data-ttu-id="30200-109">不含空格及分隔符號的八位數</span><span class="sxs-lookup"><span data-stu-id="30200-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-110">模式</span><span class="sxs-lookup"><span data-stu-id="30200-110">Pattern</span></span>

<span data-ttu-id="30200-111">八位數</span><span class="sxs-lookup"><span data-stu-id="30200-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="30200-112">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-112">Checksum</span></span>

<span data-ttu-id="30200-113">否</span><span class="sxs-lookup"><span data-stu-id="30200-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-114">定義</span><span class="sxs-lookup"><span data-stu-id="30200-114">Definition</span></span>

<span data-ttu-id="30200-115">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-116">正則運算式`Regex_austria_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-117">找到來自`Keywords_austria_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="30200-118">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-118">Keywords</span></span>

<span data-ttu-id="30200-119">| |</span><span class="sxs-lookup"><span data-stu-id="30200-119">| |</span></span>
|<span data-ttu-id="30200-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-121">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-121">dl#</span></span>  <br/> <span data-ttu-id="30200-122">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-122">driver license</span></span>  <br/> <span data-ttu-id="30200-123">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-123">driver license number</span></span>  <br/> <span data-ttu-id="30200-124">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-124">driver licence</span></span>  <br/> <span data-ttu-id="30200-125">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-125">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-126">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-126">drivers license</span></span>  <br/> <span data-ttu-id="30200-127">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-127">driver's licence</span></span>  <br/> <span data-ttu-id="30200-128">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-128">driver's license</span></span>  <br/> <span data-ttu-id="30200-129">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-129">driver's license number</span></span>  <br/> <span data-ttu-id="30200-130">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="30200-131">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-131">driving license number</span></span>  <br/> <span data-ttu-id="30200-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-132">dlno#</span></span>  <br/> <span data-ttu-id="30200-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="30200-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="30200-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="30200-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="30200-135">比利時</span><span class="sxs-lookup"><span data-stu-id="30200-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="30200-136">格式</span><span class="sxs-lookup"><span data-stu-id="30200-136">Format</span></span>

<span data-ttu-id="30200-137">10位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="30200-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-138">模式</span><span class="sxs-lookup"><span data-stu-id="30200-138">Pattern</span></span>

<span data-ttu-id="30200-139">10位數</span><span class="sxs-lookup"><span data-stu-id="30200-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="30200-140">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-140">Checksum</span></span>

<span data-ttu-id="30200-141">否</span><span class="sxs-lookup"><span data-stu-id="30200-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-142">定義</span><span class="sxs-lookup"><span data-stu-id="30200-142">Definition</span></span>

<span data-ttu-id="30200-143">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-144">正則運算式`Regex_belgium_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-145">找到來自`Keywords_belgium_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="30200-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-146">Keywords</span></span>

<span data-ttu-id="30200-147">| |</span><span class="sxs-lookup"><span data-stu-id="30200-147">| |</span></span>
|<span data-ttu-id="30200-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-149">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-149">dl#</span></span>  <br/> <span data-ttu-id="30200-150">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-150">driver license</span></span>  <br/> <span data-ttu-id="30200-151">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-151">driver license number</span></span>  <br/> <span data-ttu-id="30200-152">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-152">driver licence</span></span>  <br/> <span data-ttu-id="30200-153">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-153">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-154">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-154">drivers license</span></span>  <br/> <span data-ttu-id="30200-155">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-155">drivers licence</span></span>  <br/> <span data-ttu-id="30200-156">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-156">driver's license</span></span>  <br/> <span data-ttu-id="30200-157">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-157">driver's license number</span></span>  <br/> <span data-ttu-id="30200-158">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-158">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-159">dlno#</span></span>  <br/> <span data-ttu-id="30200-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="30200-160">rijbewijs</span></span>  <br/> <span data-ttu-id="30200-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="30200-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="30200-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="30200-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="30200-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="30200-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="30200-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="30200-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="30200-165">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="30200-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="30200-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="30200-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="30200-167">fuehrerschein-nr</span><span class="sxs-lookup"><span data-stu-id="30200-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="30200-168">保加利亞</span><span class="sxs-lookup"><span data-stu-id="30200-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="30200-169">格式</span><span class="sxs-lookup"><span data-stu-id="30200-169">Format</span></span>

<span data-ttu-id="30200-170">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="30200-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-171">模式</span><span class="sxs-lookup"><span data-stu-id="30200-171">Pattern</span></span>

<span data-ttu-id="30200-172">九位數</span><span class="sxs-lookup"><span data-stu-id="30200-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="30200-173">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-173">Checksum</span></span>

<span data-ttu-id="30200-174">否</span><span class="sxs-lookup"><span data-stu-id="30200-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-175">定義</span><span class="sxs-lookup"><span data-stu-id="30200-175">Definition</span></span>

<span data-ttu-id="30200-176">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-177">正則運算式`Regex_bulgaria_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-178">找到來自`Keywords_bulgaria_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="30200-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-179">Keywords</span></span>

<span data-ttu-id="30200-180">| |</span><span class="sxs-lookup"><span data-stu-id="30200-180">| |</span></span>
|<span data-ttu-id="30200-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-182">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-182">dl#</span></span>  <br/> <span data-ttu-id="30200-183">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-183">driver license</span></span>  <br/> <span data-ttu-id="30200-184">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-184">driver license number</span></span>  <br/> <span data-ttu-id="30200-185">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-185">driver licence</span></span>  <br/> <span data-ttu-id="30200-186">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-186">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-187">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-187">drivers license</span></span>  <br/> <span data-ttu-id="30200-188">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-188">drivers licence</span></span>  <br/> <span data-ttu-id="30200-189">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-189">driver's license</span></span>  <br/> <span data-ttu-id="30200-190">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-190">driver's license number</span></span>  <br/> <span data-ttu-id="30200-191">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-191">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-192">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-192">driving license number</span></span>  <br/> <span data-ttu-id="30200-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-193">dlno#</span></span>  <br/> <span data-ttu-id="30200-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="30200-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="30200-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="30200-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="30200-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="30200-196">сумпс</span></span>  <br/> <span data-ttu-id="30200-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="30200-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="30200-198">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="30200-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="30200-199">格式</span><span class="sxs-lookup"><span data-stu-id="30200-199">Format</span></span>

<span data-ttu-id="30200-200">不含空格及分隔符號的八位數</span><span class="sxs-lookup"><span data-stu-id="30200-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-201">模式</span><span class="sxs-lookup"><span data-stu-id="30200-201">Pattern</span></span>

<span data-ttu-id="30200-202">八位數</span><span class="sxs-lookup"><span data-stu-id="30200-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="30200-203">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-203">Checksum</span></span>

<span data-ttu-id="30200-204">否</span><span class="sxs-lookup"><span data-stu-id="30200-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-205">定義</span><span class="sxs-lookup"><span data-stu-id="30200-205">Definition</span></span>

<span data-ttu-id="30200-206">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-207">正則運算式`Regex_croatia_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-208">找到來自`Keywords_croatia_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="30200-209">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-209">Keywords</span></span>

<span data-ttu-id="30200-210">| |</span><span class="sxs-lookup"><span data-stu-id="30200-210">| |</span></span>
|<span data-ttu-id="30200-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-212">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-212">dl#</span></span>  <br/> <span data-ttu-id="30200-213">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-213">driver license</span></span>  <br/> <span data-ttu-id="30200-214">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-214">driver license number</span></span>  <br/> <span data-ttu-id="30200-215">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-215">driver licence</span></span>  <br/> <span data-ttu-id="30200-216">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-216">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-217">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-217">drivers license</span></span>  <br/> <span data-ttu-id="30200-218">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-218">drivers licence</span></span>  <br/> <span data-ttu-id="30200-219">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-219">driver's license</span></span>  <br/> <span data-ttu-id="30200-220">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-220">driver's license number</span></span>  <br/> <span data-ttu-id="30200-221">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-221">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-222">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-222">driving license number</span></span>  <br/> <span data-ttu-id="30200-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-223">dlno#</span></span>  <br/> <span data-ttu-id="30200-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="30200-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="30200-225">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="30200-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="30200-226">格式</span><span class="sxs-lookup"><span data-stu-id="30200-226">Format</span></span>

<span data-ttu-id="30200-227">12位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="30200-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-228">模式</span><span class="sxs-lookup"><span data-stu-id="30200-228">Pattern</span></span>

<span data-ttu-id="30200-229">12位數</span><span class="sxs-lookup"><span data-stu-id="30200-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="30200-230">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-230">Checksum</span></span>

<span data-ttu-id="30200-231">否</span><span class="sxs-lookup"><span data-stu-id="30200-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-232">定義</span><span class="sxs-lookup"><span data-stu-id="30200-232">Definition</span></span>

<span data-ttu-id="30200-233">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-234">正則運算式`Regex_cyprus_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-235">找到來自`Keywords_cyprus_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-236">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-236">Keywords</span></span>

<span data-ttu-id="30200-237">| |</span><span class="sxs-lookup"><span data-stu-id="30200-237">| |</span></span>
|<span data-ttu-id="30200-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-239">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-239">dl#</span></span>  <br/> <span data-ttu-id="30200-240">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-240">driver license</span></span>  <br/> <span data-ttu-id="30200-241">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-241">driver license number</span></span>  <br/> <span data-ttu-id="30200-242">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-242">driver licence</span></span>  <br/> <span data-ttu-id="30200-243">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-243">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-244">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-244">drivers license</span></span>  <br/> <span data-ttu-id="30200-245">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-245">drivers licence</span></span>  <br/> <span data-ttu-id="30200-246">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-246">driver's license number</span></span>  <br/> <span data-ttu-id="30200-247">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-247">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-248">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-248">driving license number</span></span>  <br/> <span data-ttu-id="30200-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-249">dlno#</span></span>  <br/> <span data-ttu-id="30200-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="30200-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="30200-251">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="30200-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="30200-252">格式</span><span class="sxs-lookup"><span data-stu-id="30200-252">Format</span></span>

<span data-ttu-id="30200-253">兩個字母后接六位數</span><span class="sxs-lookup"><span data-stu-id="30200-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-254">模式</span><span class="sxs-lookup"><span data-stu-id="30200-254">Pattern</span></span>

<span data-ttu-id="30200-255">8個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="30200-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="30200-256">兩個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="30200-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="30200-257">一個空格（選用）</span><span class="sxs-lookup"><span data-stu-id="30200-257">A space (optional)</span></span>
    
- <span data-ttu-id="30200-258">六位數</span><span class="sxs-lookup"><span data-stu-id="30200-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="30200-259">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-259">Checksum</span></span>

<span data-ttu-id="30200-260">否</span><span class="sxs-lookup"><span data-stu-id="30200-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-261">定義</span><span class="sxs-lookup"><span data-stu-id="30200-261">Definition</span></span>

<span data-ttu-id="30200-262">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-263">正則運算式`Regex_czech_republic_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-264">找到來自`Keywords_czech_republic_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="30200-265">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-265">Keywords</span></span>

<span data-ttu-id="30200-266">| |</span><span class="sxs-lookup"><span data-stu-id="30200-266">| |</span></span>
|<span data-ttu-id="30200-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-268">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-268">dl#</span></span>  <br/> <span data-ttu-id="30200-269">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-269">driver license</span></span>  <br/> <span data-ttu-id="30200-270">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-270">driver license number</span></span>  <br/> <span data-ttu-id="30200-271">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-271">driver licence</span></span>  <br/> <span data-ttu-id="30200-272">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-272">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-273">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-273">drivers license</span></span>  <br/> <span data-ttu-id="30200-274">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-274">drivers licence</span></span>  <br/> <span data-ttu-id="30200-275">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-275">driver's license</span></span>  <br/> <span data-ttu-id="30200-276">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-276">driver's license number</span></span>  <br/> <span data-ttu-id="30200-277">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-277">driver's license number</span></span>  <br/> <span data-ttu-id="30200-278">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-278">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-279">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-279">driving license number</span></span>  <br/> <span data-ttu-id="30200-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-280">dlno#</span></span>  <br/> <span data-ttu-id="30200-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="30200-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="30200-282">丹麥</span><span class="sxs-lookup"><span data-stu-id="30200-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="30200-283">格式</span><span class="sxs-lookup"><span data-stu-id="30200-283">Format</span></span>

<span data-ttu-id="30200-284">不含空格及分隔符號的八位數</span><span class="sxs-lookup"><span data-stu-id="30200-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-285">模式</span><span class="sxs-lookup"><span data-stu-id="30200-285">Pattern</span></span>

<span data-ttu-id="30200-286">八位數</span><span class="sxs-lookup"><span data-stu-id="30200-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="30200-287">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-287">Checksum</span></span>

<span data-ttu-id="30200-288">是</span><span class="sxs-lookup"><span data-stu-id="30200-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-289">定義</span><span class="sxs-lookup"><span data-stu-id="30200-289">Definition</span></span>

<span data-ttu-id="30200-290">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-291">正則運算式`Regex_denmark_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-292">找到來自`Keywords_denmark_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="30200-293">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-293">Keywords</span></span>

<span data-ttu-id="30200-294">| |</span><span class="sxs-lookup"><span data-stu-id="30200-294">| |</span></span>
|<span data-ttu-id="30200-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-296">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-296">dl#</span></span>  <br/> <span data-ttu-id="30200-297">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-297">driver license</span></span>  <br/> <span data-ttu-id="30200-298">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-298">driver license number</span></span>  <br/> <span data-ttu-id="30200-299">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-299">driver licence</span></span>  <br/> <span data-ttu-id="30200-300">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-300">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-301">drivers license</span></span>  <br/> <span data-ttu-id="30200-302">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-302">drivers licence</span></span>  <br/> <span data-ttu-id="30200-303">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-303">driver's license</span></span>  <br/> <span data-ttu-id="30200-304">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-304">driver's license number</span></span>  <br/> <span data-ttu-id="30200-305">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-305">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-306">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-306">driving license number</span></span>  <br/> <span data-ttu-id="30200-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-307">dlno#</span></span>  <br/> <span data-ttu-id="30200-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="30200-308">kørekort</span></span>  <br/> <span data-ttu-id="30200-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="30200-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="30200-310">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="30200-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="30200-311">格式</span><span class="sxs-lookup"><span data-stu-id="30200-311">Format</span></span>

<span data-ttu-id="30200-312">兩個字母后接六位數</span><span class="sxs-lookup"><span data-stu-id="30200-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-313">模式</span><span class="sxs-lookup"><span data-stu-id="30200-313">Pattern</span></span>

<span data-ttu-id="30200-314">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="30200-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="30200-315">字母 "ET" （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="30200-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="30200-316">六位數</span><span class="sxs-lookup"><span data-stu-id="30200-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="30200-317">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-317">Checksum</span></span>

<span data-ttu-id="30200-318">否</span><span class="sxs-lookup"><span data-stu-id="30200-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-319">定義</span><span class="sxs-lookup"><span data-stu-id="30200-319">Definition</span></span>

<span data-ttu-id="30200-320">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-321">正則運算式`Regex_estonia_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-322">找到來自`Keywords_estonia_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-323">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-323">Keywords</span></span>

<span data-ttu-id="30200-324">| |</span><span class="sxs-lookup"><span data-stu-id="30200-324">| |</span></span>
|<span data-ttu-id="30200-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-326">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-326">dl#</span></span>  <br/> <span data-ttu-id="30200-327">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-327">driver license</span></span>  <br/> <span data-ttu-id="30200-328">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-328">driver license number</span></span>  <br/> <span data-ttu-id="30200-329">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-329">driver license number</span></span>  <br/> <span data-ttu-id="30200-330">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-330">driver licence</span></span>  <br/> <span data-ttu-id="30200-331">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-331">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-332">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-332">drivers license</span></span>  <br/> <span data-ttu-id="30200-333">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-333">drivers licence</span></span>  <br/> <span data-ttu-id="30200-334">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-334">driver's license</span></span>  <br/> <span data-ttu-id="30200-335">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-335">driver's license number</span></span>  <br/> <span data-ttu-id="30200-336">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-336">driving license number</span></span>  <br/> <span data-ttu-id="30200-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-337">dlno#</span></span>  <br/> <span data-ttu-id="30200-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="30200-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="30200-339">芬蘭</span><span class="sxs-lookup"><span data-stu-id="30200-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="30200-340">格式</span><span class="sxs-lookup"><span data-stu-id="30200-340">Format</span></span>

<span data-ttu-id="30200-341">10位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="30200-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-342">模式</span><span class="sxs-lookup"><span data-stu-id="30200-342">Pattern</span></span>

<span data-ttu-id="30200-343">10位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="30200-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="30200-344">六位數</span><span class="sxs-lookup"><span data-stu-id="30200-344">Six digits</span></span> 
    
- <span data-ttu-id="30200-345">連字號</span><span class="sxs-lookup"><span data-stu-id="30200-345">A hyphen</span></span>
    
-  <span data-ttu-id="30200-346">四位數</span><span class="sxs-lookup"><span data-stu-id="30200-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="30200-347">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-347">Checksum</span></span>

<span data-ttu-id="30200-348">否</span><span class="sxs-lookup"><span data-stu-id="30200-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-349">定義</span><span class="sxs-lookup"><span data-stu-id="30200-349">Definition</span></span>

<span data-ttu-id="30200-350">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-351">正則運算式`Regex_finland_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-352">找到來自`Keywords_finland_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-353">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-353">Keywords</span></span>

<span data-ttu-id="30200-354">| |</span><span class="sxs-lookup"><span data-stu-id="30200-354">| |</span></span>
|<span data-ttu-id="30200-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-356">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-356">dl#</span></span>  <br/> <span data-ttu-id="30200-357">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-357">driver license</span></span>  <br/> <span data-ttu-id="30200-358">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-358">driver license number</span></span>  <br/> <span data-ttu-id="30200-359">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-359">driver licence</span></span>  <br/> <span data-ttu-id="30200-360">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-360">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-361">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-361">drivers license</span></span>  <br/> <span data-ttu-id="30200-362">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-362">drivers licence</span></span>  <br/> <span data-ttu-id="30200-363">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-363">driver's license</span></span>  <br/> <span data-ttu-id="30200-364">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-364">driver's license number</span></span>  <br/> <span data-ttu-id="30200-365">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-365">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-366">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-366">driving license number</span></span>  <br/> <span data-ttu-id="30200-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-367">dlno#</span></span>  <br/> <span data-ttu-id="30200-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="30200-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="30200-369">法國</span><span class="sxs-lookup"><span data-stu-id="30200-369">France</span></span>

<span data-ttu-id="30200-370">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「法國駕照編號」一節。</span><span class="sxs-lookup"><span data-stu-id="30200-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="30200-371">德國</span><span class="sxs-lookup"><span data-stu-id="30200-371">Germany</span></span>

<span data-ttu-id="30200-372">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「德文駕執照號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="30200-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="30200-373">希臘</span><span class="sxs-lookup"><span data-stu-id="30200-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="30200-374">格式</span><span class="sxs-lookup"><span data-stu-id="30200-374">Format</span></span>

<span data-ttu-id="30200-375">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="30200-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-376">模式</span><span class="sxs-lookup"><span data-stu-id="30200-376">Pattern</span></span>

 <span data-ttu-id="30200-377">九位數</span><span class="sxs-lookup"><span data-stu-id="30200-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="30200-378">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-378">Checksum</span></span>

<span data-ttu-id="30200-379">否</span><span class="sxs-lookup"><span data-stu-id="30200-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-380">定義</span><span class="sxs-lookup"><span data-stu-id="30200-380">Definition</span></span>

<span data-ttu-id="30200-381">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-382">正則運算式`Regex_greece_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-383">找到來自`Keywords_greece_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-384">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-384">Keywords</span></span>

<span data-ttu-id="30200-385">| |</span><span class="sxs-lookup"><span data-stu-id="30200-385">| |</span></span>
|<span data-ttu-id="30200-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-387">Dll#</span><span class="sxs-lookup"><span data-stu-id="30200-387">dlL#</span></span>  <br/> <span data-ttu-id="30200-388">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-388">driver license</span></span>  <br/> <span data-ttu-id="30200-389">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-389">driver license number</span></span>  <br/> <span data-ttu-id="30200-390">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-390">driver licence</span></span>  <br/> <span data-ttu-id="30200-391">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-391">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-392">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-392">drivers license</span></span>  <br/> <span data-ttu-id="30200-393">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-393">drivers licence</span></span>  <br/> <span data-ttu-id="30200-394">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-394">driver's license</span></span>  <br/> <span data-ttu-id="30200-395">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-395">driver's license number</span></span>  <br/> <span data-ttu-id="30200-396">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-396">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-397">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-397">driving license number</span></span>  <br/> <span data-ttu-id="30200-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-398">dlno#</span></span>  <br/> <span data-ttu-id="30200-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="30200-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="30200-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="30200-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="30200-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="30200-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="30200-402">格式</span><span class="sxs-lookup"><span data-stu-id="30200-402">Format</span></span>

<span data-ttu-id="30200-403">兩個字母后接六位數</span><span class="sxs-lookup"><span data-stu-id="30200-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-404">模式</span><span class="sxs-lookup"><span data-stu-id="30200-404">Pattern</span></span>

<span data-ttu-id="30200-405">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="30200-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="30200-406">兩個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="30200-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="30200-407">六位數</span><span class="sxs-lookup"><span data-stu-id="30200-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="30200-408">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-408">Checksum</span></span>

<span data-ttu-id="30200-409">否</span><span class="sxs-lookup"><span data-stu-id="30200-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-410">定義</span><span class="sxs-lookup"><span data-stu-id="30200-410">Definition</span></span>

<span data-ttu-id="30200-411">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-412">正則運算式`Regex_hungary_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-413">找到來自`Keywords_hungary_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-414">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-414">Keywords</span></span>

<span data-ttu-id="30200-415">| |</span><span class="sxs-lookup"><span data-stu-id="30200-415">| |</span></span>
|<span data-ttu-id="30200-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-417">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-417">dl#</span></span>  <br/> <span data-ttu-id="30200-418">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-418">driver license</span></span>  <br/> <span data-ttu-id="30200-419">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-419">driver license number</span></span>  <br/> <span data-ttu-id="30200-420">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-420">driver licence</span></span>  <br/> <span data-ttu-id="30200-421">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-421">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-422">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-422">drivers license</span></span>  <br/> <span data-ttu-id="30200-423">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-423">drivers licence</span></span>  <br/> <span data-ttu-id="30200-424">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-424">driver's license</span></span>  <br/> <span data-ttu-id="30200-425">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-425">driver's license number</span></span>  <br/> <span data-ttu-id="30200-426">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-426">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-427">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-427">driving license number</span></span>  <br/> <span data-ttu-id="30200-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-428">dlno#</span></span>  <br/> <span data-ttu-id="30200-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="30200-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="30200-430">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="30200-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="30200-431">格式</span><span class="sxs-lookup"><span data-stu-id="30200-431">Format</span></span>

<span data-ttu-id="30200-432">六位數後接四個字母</span><span class="sxs-lookup"><span data-stu-id="30200-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-433">模式</span><span class="sxs-lookup"><span data-stu-id="30200-433">Pattern</span></span>

<span data-ttu-id="30200-434">六位數和四個字母：</span><span class="sxs-lookup"><span data-stu-id="30200-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="30200-435">六位數</span><span class="sxs-lookup"><span data-stu-id="30200-435">Six digits</span></span>
    
- <span data-ttu-id="30200-436">四個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="30200-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="30200-437">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-437">Checksum</span></span>

<span data-ttu-id="30200-438">否</span><span class="sxs-lookup"><span data-stu-id="30200-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-439">定義</span><span class="sxs-lookup"><span data-stu-id="30200-439">Definition</span></span>

<span data-ttu-id="30200-440">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-441">正則運算式`Regex_ireland_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-442">找到來自`Keywords_ireland_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-443">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-443">Keywords</span></span>

<span data-ttu-id="30200-444">| |</span><span class="sxs-lookup"><span data-stu-id="30200-444">| |</span></span>
|<span data-ttu-id="30200-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-446">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-446">dl#</span></span>  <br/> <span data-ttu-id="30200-447">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-447">driver license</span></span>  <br/> <span data-ttu-id="30200-448">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-448">driver license number</span></span>  <br/> <span data-ttu-id="30200-449">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-449">driver licence</span></span>  <br/> <span data-ttu-id="30200-450">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-450">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-451">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-451">drivers license</span></span>  <br/> <span data-ttu-id="30200-452">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-452">drivers licence</span></span>  <br/> <span data-ttu-id="30200-453">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-453">driver's license</span></span>  <br/> <span data-ttu-id="30200-454">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-454">driver's license number</span></span>  <br/> <span data-ttu-id="30200-455">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-455">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-456">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-456">driving license number</span></span>  <br/> <span data-ttu-id="30200-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-457">dlno#</span></span>  <br/> <span data-ttu-id="30200-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="30200-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="30200-459">義大利</span><span class="sxs-lookup"><span data-stu-id="30200-459">Italy</span></span>

<span data-ttu-id="30200-460">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「義大利駕照編號」一節。</span><span class="sxs-lookup"><span data-stu-id="30200-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="30200-461">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="30200-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="30200-462">格式</span><span class="sxs-lookup"><span data-stu-id="30200-462">Format</span></span>

<span data-ttu-id="30200-463">三個字母后接六位數</span><span class="sxs-lookup"><span data-stu-id="30200-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-464">模式</span><span class="sxs-lookup"><span data-stu-id="30200-464">Pattern</span></span>

<span data-ttu-id="30200-465">三個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="30200-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="30200-466">三個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="30200-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="30200-467">六位數</span><span class="sxs-lookup"><span data-stu-id="30200-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="30200-468">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-468">Checksum</span></span>

<span data-ttu-id="30200-469">否</span><span class="sxs-lookup"><span data-stu-id="30200-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-470">定義</span><span class="sxs-lookup"><span data-stu-id="30200-470">Definition</span></span>

<span data-ttu-id="30200-471">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-472">正則運算式`Regex_latvia_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-473">找到來自`Keywords_latvia_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-474">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-474">Keywords</span></span>

<span data-ttu-id="30200-475">| |</span><span class="sxs-lookup"><span data-stu-id="30200-475">| |</span></span>
|<span data-ttu-id="30200-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-477">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-477">dl#</span></span>  <br/> <span data-ttu-id="30200-478">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-478">driver license</span></span>  <br/> <span data-ttu-id="30200-479">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-479">driver license number</span></span>  <br/> <span data-ttu-id="30200-480">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-480">driver licence</span></span>  <br/> <span data-ttu-id="30200-481">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-481">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-482">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-482">drivers license</span></span>  <br/> <span data-ttu-id="30200-483">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-483">drivers licence</span></span>  <br/> <span data-ttu-id="30200-484">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-484">driver's license</span></span>  <br/> <span data-ttu-id="30200-485">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-485">driver's license number</span></span>  <br/> <span data-ttu-id="30200-486">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-486">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-487">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-487">driving license number</span></span>  <br/> <span data-ttu-id="30200-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-488">dlno#</span></span>  <br/> <span data-ttu-id="30200-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="30200-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="30200-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="30200-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="30200-491">格式</span><span class="sxs-lookup"><span data-stu-id="30200-491">Format</span></span>

<span data-ttu-id="30200-492">不含空格及分隔符號的八位數</span><span class="sxs-lookup"><span data-stu-id="30200-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-493">模式</span><span class="sxs-lookup"><span data-stu-id="30200-493">Pattern</span></span>

 <span data-ttu-id="30200-494">八位數</span><span class="sxs-lookup"><span data-stu-id="30200-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="30200-495">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-495">Checksum</span></span>

<span data-ttu-id="30200-496">否</span><span class="sxs-lookup"><span data-stu-id="30200-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-497">定義</span><span class="sxs-lookup"><span data-stu-id="30200-497">Definition</span></span>

<span data-ttu-id="30200-498">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-499">正則運算式`Regex_lithuania_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-500">找到來自`Keywords_lithuania_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-501">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-501">Keywords</span></span>

<span data-ttu-id="30200-502">| |</span><span class="sxs-lookup"><span data-stu-id="30200-502">| |</span></span>
|<span data-ttu-id="30200-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-504">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-504">dl#</span></span>  <br/> <span data-ttu-id="30200-505">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-505">driver license</span></span>  <br/> <span data-ttu-id="30200-506">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-506">driver license number</span></span>  <br/> <span data-ttu-id="30200-507">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-507">driver licence</span></span>  <br/> <span data-ttu-id="30200-508">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-508">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-509">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-509">drivers license</span></span>  <br/> <span data-ttu-id="30200-510">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-510">drivers licence</span></span>  <br/> <span data-ttu-id="30200-511">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-511">driver's license</span></span>  <br/> <span data-ttu-id="30200-512">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-512">driver's license number</span></span>  <br/> <span data-ttu-id="30200-513">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-513">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-514">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-514">driving license number</span></span>  <br/> <span data-ttu-id="30200-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-515">dlno#</span></span>  <br/> <span data-ttu-id="30200-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="30200-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="30200-517">盧森堡</span><span class="sxs-lookup"><span data-stu-id="30200-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="30200-518">格式</span><span class="sxs-lookup"><span data-stu-id="30200-518">Format</span></span>

<span data-ttu-id="30200-519">六位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="30200-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-520">模式</span><span class="sxs-lookup"><span data-stu-id="30200-520">Pattern</span></span>

 <span data-ttu-id="30200-521">六位數</span><span class="sxs-lookup"><span data-stu-id="30200-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="30200-522">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-522">Checksum</span></span>

<span data-ttu-id="30200-523">否</span><span class="sxs-lookup"><span data-stu-id="30200-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-524">定義</span><span class="sxs-lookup"><span data-stu-id="30200-524">Definition</span></span>

<span data-ttu-id="30200-525">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-526">正則運算式`Regex_luxemburg_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-527">找到來自`Keywords_luxemburg_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-528">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-528">Keywords</span></span>

<span data-ttu-id="30200-529">| |</span><span class="sxs-lookup"><span data-stu-id="30200-529">| |</span></span>
|<span data-ttu-id="30200-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-531">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-531">dl#</span></span>  <br/> <span data-ttu-id="30200-532">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-532">driver license</span></span>  <br/> <span data-ttu-id="30200-533">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-533">driver license number</span></span>  <br/> <span data-ttu-id="30200-534">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-534">driver licence</span></span>  <br/> <span data-ttu-id="30200-535">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-535">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-536">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-536">drivers license</span></span>  <br/> <span data-ttu-id="30200-537">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-537">drivers licence</span></span>  <br/> <span data-ttu-id="30200-538">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-538">driver's license</span></span>  <br/> <span data-ttu-id="30200-539">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-539">driver's license number</span></span>  <br/> <span data-ttu-id="30200-540">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-540">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-541">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-541">driving license number</span></span>  <br/> <span data-ttu-id="30200-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-542">dlno#</span></span>  <br/> <span data-ttu-id="30200-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="30200-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="30200-544">馬爾他</span><span class="sxs-lookup"><span data-stu-id="30200-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="30200-545">格式</span><span class="sxs-lookup"><span data-stu-id="30200-545">Format</span></span>

<span data-ttu-id="30200-546">兩個字元的組合，並在指定的模式中包含六位數</span><span class="sxs-lookup"><span data-stu-id="30200-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-547">模式</span><span class="sxs-lookup"><span data-stu-id="30200-547">Pattern</span></span>

<span data-ttu-id="30200-548">兩個字元和六位數的組合：</span><span class="sxs-lookup"><span data-stu-id="30200-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="30200-549">兩個字元（數位或字母，不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="30200-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="30200-550">一個空格（選用）</span><span class="sxs-lookup"><span data-stu-id="30200-550">A space (optional)</span></span>
    
- <span data-ttu-id="30200-551">三位數</span><span class="sxs-lookup"><span data-stu-id="30200-551">Three digits</span></span>
    
- <span data-ttu-id="30200-552">一個空格（選用）</span><span class="sxs-lookup"><span data-stu-id="30200-552">A space (optional)</span></span>
    
- <span data-ttu-id="30200-553">三位數</span><span class="sxs-lookup"><span data-stu-id="30200-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="30200-554">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-554">Checksum</span></span>

<span data-ttu-id="30200-555">否</span><span class="sxs-lookup"><span data-stu-id="30200-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-556">定義</span><span class="sxs-lookup"><span data-stu-id="30200-556">Definition</span></span>

<span data-ttu-id="30200-557">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-558">正則運算式`Regex_malta_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-559">找到來自`Keywords_malta_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-560">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-560">Keywords</span></span>

<span data-ttu-id="30200-561">| |</span><span class="sxs-lookup"><span data-stu-id="30200-561">| |</span></span>
|<span data-ttu-id="30200-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-563">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-563">dl#</span></span>  <br/> <span data-ttu-id="30200-564">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-564">driver license</span></span>  <br/> <span data-ttu-id="30200-565">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-565">driver license number</span></span>  <br/> <span data-ttu-id="30200-566">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-566">driver licence</span></span>  <br/> <span data-ttu-id="30200-567">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-567">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-568">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-568">drivers license</span></span>  <br/> <span data-ttu-id="30200-569">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-569">drivers licence</span></span>  <br/> <span data-ttu-id="30200-570">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-570">driver's license</span></span>  <br/> <span data-ttu-id="30200-571">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-571">driver's license number</span></span>  <br/> <span data-ttu-id="30200-572">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-572">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-573">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-573">driving license number</span></span>  <br/> <span data-ttu-id="30200-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-574">dlno#</span></span>  <br/> <span data-ttu-id="30200-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="30200-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="30200-576">荷蘭</span><span class="sxs-lookup"><span data-stu-id="30200-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="30200-577">格式</span><span class="sxs-lookup"><span data-stu-id="30200-577">Format</span></span>

<span data-ttu-id="30200-578">10位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="30200-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-579">模式</span><span class="sxs-lookup"><span data-stu-id="30200-579">Pattern</span></span>

<span data-ttu-id="30200-580">10位數</span><span class="sxs-lookup"><span data-stu-id="30200-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="30200-581">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-581">Checksum</span></span>

<span data-ttu-id="30200-582">否</span><span class="sxs-lookup"><span data-stu-id="30200-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-583">定義</span><span class="sxs-lookup"><span data-stu-id="30200-583">Definition</span></span>

<span data-ttu-id="30200-584">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-585">正則運算式`Regex_netherlands_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-586">找到來自`Keywords_netherlands_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-587">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-587">Keywords</span></span>

<span data-ttu-id="30200-588">| |</span><span class="sxs-lookup"><span data-stu-id="30200-588">| |</span></span>
|<span data-ttu-id="30200-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-590">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-590">dl#</span></span>  <br/> <span data-ttu-id="30200-591">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-591">driver license</span></span>  <br/> <span data-ttu-id="30200-592">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-592">driver license number</span></span>  <br/> <span data-ttu-id="30200-593">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-593">driver licence</span></span>  <br/> <span data-ttu-id="30200-594">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-594">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-595">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-595">drivers license</span></span>  <br/> <span data-ttu-id="30200-596">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-596">drivers licence</span></span>  <br/> <span data-ttu-id="30200-597">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-597">driver's license</span></span>  <br/> <span data-ttu-id="30200-598">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-598">driver's license number</span></span>  <br/> <span data-ttu-id="30200-599">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-599">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-600">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-600">driving license number</span></span>  <br/> <span data-ttu-id="30200-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-601">dlno#</span></span>  <br/> <span data-ttu-id="30200-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="30200-602">permis de conduire</span></span>  <br/> <span data-ttu-id="30200-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="30200-603">rijbewijs</span></span>  <br/> <span data-ttu-id="30200-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="30200-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="30200-605">波蘭</span><span class="sxs-lookup"><span data-stu-id="30200-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="30200-606">格式</span><span class="sxs-lookup"><span data-stu-id="30200-606">Format</span></span>

<span data-ttu-id="30200-607">14位數包含2個正斜杠</span><span class="sxs-lookup"><span data-stu-id="30200-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-608">模式</span><span class="sxs-lookup"><span data-stu-id="30200-608">Pattern</span></span>

<span data-ttu-id="30200-609">14位數和2轉寄斜線：</span><span class="sxs-lookup"><span data-stu-id="30200-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="30200-610">五位數</span><span class="sxs-lookup"><span data-stu-id="30200-610">Five digits</span></span> 
    
- <span data-ttu-id="30200-611">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="30200-611">A forward slash</span></span>
    
- <span data-ttu-id="30200-612">兩位數</span><span class="sxs-lookup"><span data-stu-id="30200-612">Two digits</span></span>
    
- <span data-ttu-id="30200-613">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="30200-613">A forward slash</span></span>
    
- <span data-ttu-id="30200-614">七位數</span><span class="sxs-lookup"><span data-stu-id="30200-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="30200-615">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-615">Checksum</span></span>

<span data-ttu-id="30200-616">否</span><span class="sxs-lookup"><span data-stu-id="30200-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-617">定義</span><span class="sxs-lookup"><span data-stu-id="30200-617">Definition</span></span>

<span data-ttu-id="30200-618">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-619">正則運算式`Regex_poland_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-620">找到來自`Keywords_poland_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-621">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-621">Keywords</span></span>

<span data-ttu-id="30200-622">| |</span><span class="sxs-lookup"><span data-stu-id="30200-622">| |</span></span>
|<span data-ttu-id="30200-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-624">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-624">dl#</span></span>  <br/> <span data-ttu-id="30200-625">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-625">driver license</span></span>  <br/> <span data-ttu-id="30200-626">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-626">driver license number</span></span>  <br/> <span data-ttu-id="30200-627">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-627">driver licence</span></span>  <br/> <span data-ttu-id="30200-628">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-628">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-629">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-629">drivers license</span></span>  <br/> <span data-ttu-id="30200-630">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-630">drivers licence</span></span>  <br/> <span data-ttu-id="30200-631">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-631">driver's license</span></span>  <br/> <span data-ttu-id="30200-632">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-632">driver's license number</span></span>  <br/> <span data-ttu-id="30200-633">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-633">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-634">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-634">driving license number</span></span>  <br/> <span data-ttu-id="30200-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-635">dlno#</span></span>  <br/> <span data-ttu-id="30200-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="30200-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="30200-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="30200-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="30200-638">格式</span><span class="sxs-lookup"><span data-stu-id="30200-638">Format</span></span>

<span data-ttu-id="30200-639">兩個字母后接指定的模式中的七個數字</span><span class="sxs-lookup"><span data-stu-id="30200-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-640">模式</span><span class="sxs-lookup"><span data-stu-id="30200-640">Pattern</span></span>

<span data-ttu-id="30200-641">兩個字母后接7個含特殊字元的數位：</span><span class="sxs-lookup"><span data-stu-id="30200-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="30200-642">兩個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="30200-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="30200-643">連字號</span><span class="sxs-lookup"><span data-stu-id="30200-643">A hyphen</span></span>
    
- <span data-ttu-id="30200-644">六位數</span><span class="sxs-lookup"><span data-stu-id="30200-644">Six digits</span></span>
    
- <span data-ttu-id="30200-645">一個空格</span><span class="sxs-lookup"><span data-stu-id="30200-645">A space</span></span>
    
- <span data-ttu-id="30200-646">一個數位</span><span class="sxs-lookup"><span data-stu-id="30200-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="30200-647">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-647">Checksum</span></span>

<span data-ttu-id="30200-648">否</span><span class="sxs-lookup"><span data-stu-id="30200-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-649">定義</span><span class="sxs-lookup"><span data-stu-id="30200-649">Definition</span></span>

<span data-ttu-id="30200-650">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-651">正則運算式`Regex_portugal_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-652">找到來自`Keywords_portugal_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-653">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-653">Keywords</span></span>

<span data-ttu-id="30200-654">| |</span><span class="sxs-lookup"><span data-stu-id="30200-654">| |</span></span>
|<span data-ttu-id="30200-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-656">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-656">dl#</span></span>  <br/> <span data-ttu-id="30200-657">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-657">driver license</span></span>  <br/> <span data-ttu-id="30200-658">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-658">driver license number</span></span>  <br/> <span data-ttu-id="30200-659">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-659">driver licence</span></span>  <br/> <span data-ttu-id="30200-660">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-660">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-661">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-661">drivers license</span></span>  <br/> <span data-ttu-id="30200-662">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-662">drivers licence</span></span>  <br/> <span data-ttu-id="30200-663">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-663">driver's license</span></span>  <br/> <span data-ttu-id="30200-664">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-664">driver's license number</span></span>  <br/> <span data-ttu-id="30200-665">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-665">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-666">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-666">driving license number</span></span>  <br/> <span data-ttu-id="30200-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-667">dlno#</span></span>  <br/> <span data-ttu-id="30200-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="30200-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="30200-669">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="30200-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="30200-670">格式</span><span class="sxs-lookup"><span data-stu-id="30200-670">Format</span></span>

<span data-ttu-id="30200-671">一個字元後接八位數</span><span class="sxs-lookup"><span data-stu-id="30200-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-672">模式</span><span class="sxs-lookup"><span data-stu-id="30200-672">Pattern</span></span>

<span data-ttu-id="30200-673">一個字元後接八位數：</span><span class="sxs-lookup"><span data-stu-id="30200-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="30200-674">一個字母（不區分大小寫）或數位</span><span class="sxs-lookup"><span data-stu-id="30200-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="30200-675">八位數</span><span class="sxs-lookup"><span data-stu-id="30200-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="30200-676">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-676">Checksum</span></span>

<span data-ttu-id="30200-677">否</span><span class="sxs-lookup"><span data-stu-id="30200-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-678">定義</span><span class="sxs-lookup"><span data-stu-id="30200-678">Definition</span></span>

<span data-ttu-id="30200-679">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-680">正則運算式`Regex_romania_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-681">找到來自`Keywords_romania_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-682">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-682">Keywords</span></span>

<span data-ttu-id="30200-683">| |</span><span class="sxs-lookup"><span data-stu-id="30200-683">| |</span></span>
|<span data-ttu-id="30200-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-685">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-685">dl#</span></span>  <br/> <span data-ttu-id="30200-686">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-686">driver license</span></span>  <br/> <span data-ttu-id="30200-687">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-687">driver license number</span></span>  <br/> <span data-ttu-id="30200-688">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-688">driver licence</span></span>  <br/> <span data-ttu-id="30200-689">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-689">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-690">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-690">drivers license</span></span>  <br/> <span data-ttu-id="30200-691">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-691">drivers licence</span></span>  <br/> <span data-ttu-id="30200-692">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-692">driver's license</span></span>  <br/> <span data-ttu-id="30200-693">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-693">driver's license number</span></span>  <br/> <span data-ttu-id="30200-694">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-694">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-695">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-695">driving license number</span></span>  <br/> <span data-ttu-id="30200-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-696">dlno#</span></span>  <br/> <span data-ttu-id="30200-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="30200-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="30200-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="30200-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="30200-699">格式</span><span class="sxs-lookup"><span data-stu-id="30200-699">Format</span></span>

<span data-ttu-id="30200-700">一個字元後接7位數</span><span class="sxs-lookup"><span data-stu-id="30200-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-701">模式</span><span class="sxs-lookup"><span data-stu-id="30200-701">Pattern</span></span>

<span data-ttu-id="30200-702">一個字元後接7位數</span><span class="sxs-lookup"><span data-stu-id="30200-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="30200-703">一個字母（不區分大小寫）或數位</span><span class="sxs-lookup"><span data-stu-id="30200-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="30200-704">七位數</span><span class="sxs-lookup"><span data-stu-id="30200-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="30200-705">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-705">Checksum</span></span>

<span data-ttu-id="30200-706">否</span><span class="sxs-lookup"><span data-stu-id="30200-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-707">定義</span><span class="sxs-lookup"><span data-stu-id="30200-707">Definition</span></span>

<span data-ttu-id="30200-708">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-709">正則運算式`Regex_slovakia_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-710">找到來自`Keywords_slovakia_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-711">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-711">Keywords</span></span>

<span data-ttu-id="30200-712">| |</span><span class="sxs-lookup"><span data-stu-id="30200-712">| |</span></span>
|<span data-ttu-id="30200-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-714">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-714">dl#</span></span>  <br/> <span data-ttu-id="30200-715">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-715">driver license</span></span>  <br/> <span data-ttu-id="30200-716">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-716">driver license number</span></span>  <br/> <span data-ttu-id="30200-717">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-717">driver licence</span></span>  <br/> <span data-ttu-id="30200-718">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-718">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-719">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-719">drivers license</span></span>  <br/> <span data-ttu-id="30200-720">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-720">drivers licence</span></span>  <br/> <span data-ttu-id="30200-721">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-721">driver's license</span></span>  <br/> <span data-ttu-id="30200-722">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-722">driver's license number</span></span>  <br/> <span data-ttu-id="30200-723">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-723">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-724">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-724">driving license number</span></span>  <br/> <span data-ttu-id="30200-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-725">dlno#</span></span>  <br/> <span data-ttu-id="30200-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="30200-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="30200-727">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="30200-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="30200-728">格式</span><span class="sxs-lookup"><span data-stu-id="30200-728">Format</span></span>

<span data-ttu-id="30200-729">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="30200-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-730">模式</span><span class="sxs-lookup"><span data-stu-id="30200-730">Pattern</span></span>

<span data-ttu-id="30200-731">九位數</span><span class="sxs-lookup"><span data-stu-id="30200-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="30200-732">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-732">Checksum</span></span>

<span data-ttu-id="30200-733">否</span><span class="sxs-lookup"><span data-stu-id="30200-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-734">定義</span><span class="sxs-lookup"><span data-stu-id="30200-734">Definition</span></span>

<span data-ttu-id="30200-735">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-736">正則運算式`Regex_slovenia_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-737">找到來自`Keywords_slovenia_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-738">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-738">Keywords</span></span>

<span data-ttu-id="30200-739">| |</span><span class="sxs-lookup"><span data-stu-id="30200-739">| |</span></span>
|<span data-ttu-id="30200-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-741">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-741">dl#</span></span>  <br/> <span data-ttu-id="30200-742">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-742">driver license</span></span>  <br/> <span data-ttu-id="30200-743">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-743">driver license number</span></span>  <br/> <span data-ttu-id="30200-744">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-744">driver licence</span></span>  <br/> <span data-ttu-id="30200-745">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-745">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-746">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-746">drivers license</span></span>  <br/> <span data-ttu-id="30200-747">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-747">drivers licence</span></span>  <br/> <span data-ttu-id="30200-748">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-748">driver's license</span></span>  <br/> <span data-ttu-id="30200-749">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-749">driver's license number</span></span>  <br/> <span data-ttu-id="30200-750">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-750">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-751">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-751">driving license number</span></span>  <br/> <span data-ttu-id="30200-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-752">dlno#</span></span>  <br/> <span data-ttu-id="30200-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="30200-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="30200-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="30200-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="30200-755">格式</span><span class="sxs-lookup"><span data-stu-id="30200-755">Format</span></span>

<span data-ttu-id="30200-756">八位數後接一個字元</span><span class="sxs-lookup"><span data-stu-id="30200-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-757">模式</span><span class="sxs-lookup"><span data-stu-id="30200-757">Pattern</span></span>

<span data-ttu-id="30200-758">八位數後接一個字元：</span><span class="sxs-lookup"><span data-stu-id="30200-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="30200-759">八位數</span><span class="sxs-lookup"><span data-stu-id="30200-759">Eight digits</span></span> 
    
- <span data-ttu-id="30200-760">一個數位或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="30200-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="30200-761">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-761">Checksum</span></span>

<span data-ttu-id="30200-762">是</span><span class="sxs-lookup"><span data-stu-id="30200-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-763">定義</span><span class="sxs-lookup"><span data-stu-id="30200-763">Definition</span></span>

<span data-ttu-id="30200-764">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-765">函數`Func_spain_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-766">找到來自`Keywords_spain_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="30200-767">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-767">Keywords</span></span>

<span data-ttu-id="30200-768">| |</span><span class="sxs-lookup"><span data-stu-id="30200-768">| |</span></span>
|<span data-ttu-id="30200-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-770">dlno#</span></span>  <br/> <span data-ttu-id="30200-771">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-771">dl#</span></span>  <br/> <span data-ttu-id="30200-772">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-772">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-773">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-773">driver licence</span></span>  <br/> <span data-ttu-id="30200-774">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-774">driver license</span></span>  <br/> <span data-ttu-id="30200-775">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-775">drivers licence</span></span>  <br/> <span data-ttu-id="30200-776">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-776">drivers license</span></span>  <br/> <span data-ttu-id="30200-777">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-777">driver's licence</span></span>  <br/> <span data-ttu-id="30200-778">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-778">driver's license</span></span>  <br/> <span data-ttu-id="30200-779">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="30200-779">driving licence</span></span>  <br/> <span data-ttu-id="30200-780">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-780">driving license</span></span>  <br/> <span data-ttu-id="30200-781">驅動程式許可證號碼</span><span class="sxs-lookup"><span data-stu-id="30200-781">driver licence number</span></span>  <br/> <span data-ttu-id="30200-782">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-782">driver license number</span></span>  <br/> <span data-ttu-id="30200-783">驅動程式許可證數目</span><span class="sxs-lookup"><span data-stu-id="30200-783">drivers licence number</span></span>  <br/> <span data-ttu-id="30200-784">驅動程式授權號碼</span><span class="sxs-lookup"><span data-stu-id="30200-784">drivers license number</span></span>  <br/> <span data-ttu-id="30200-785">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-785">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-786">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-786">driver's license number</span></span>  <br/> <span data-ttu-id="30200-787">駕駛許可證號碼</span><span class="sxs-lookup"><span data-stu-id="30200-787">driving licence number</span></span>  <br/> <span data-ttu-id="30200-788">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-788">driving license number</span></span>  <br/> <span data-ttu-id="30200-789">駕駛允許</span><span class="sxs-lookup"><span data-stu-id="30200-789">driving permit</span></span>  <br/> <span data-ttu-id="30200-790">駕駛允許號碼</span><span class="sxs-lookup"><span data-stu-id="30200-790">driving permit number</span></span>  <br/> <span data-ttu-id="30200-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="30200-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="30200-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="30200-792">permiso conducción</span></span>  <br/> <span data-ttu-id="30200-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="30200-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="30200-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="30200-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="30200-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="30200-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="30200-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="30200-796">licencia conducir</span></span>  <br/> <span data-ttu-id="30200-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="30200-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="30200-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="30200-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="30200-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="30200-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="30200-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="30200-800">permiso conducir</span></span>  <br/> <span data-ttu-id="30200-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="30200-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="30200-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="30200-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="30200-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="30200-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="30200-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="30200-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="30200-805">格式</span><span class="sxs-lookup"><span data-stu-id="30200-805">Format</span></span>

<span data-ttu-id="30200-806">10位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="30200-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="30200-807">模式</span><span class="sxs-lookup"><span data-stu-id="30200-807">Pattern</span></span>

<span data-ttu-id="30200-808">10位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="30200-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="30200-809">六位數</span><span class="sxs-lookup"><span data-stu-id="30200-809">Six digits</span></span> 
    
- <span data-ttu-id="30200-810">連字號</span><span class="sxs-lookup"><span data-stu-id="30200-810">A hyphen</span></span>
    
- <span data-ttu-id="30200-811">四位數</span><span class="sxs-lookup"><span data-stu-id="30200-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="30200-812">校驗</span><span class="sxs-lookup"><span data-stu-id="30200-812">Checksum</span></span>

<span data-ttu-id="30200-813">否</span><span class="sxs-lookup"><span data-stu-id="30200-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="30200-814">定義</span><span class="sxs-lookup"><span data-stu-id="30200-814">Definition</span></span>

<span data-ttu-id="30200-815">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="30200-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="30200-816">正則運算式`Regex_sweden_eu_driver's_license_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="30200-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="30200-817">找到來自`Keywords_sweden_eu_driver's_license_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="30200-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="30200-818">關鍵字</span><span class="sxs-lookup"><span data-stu-id="30200-818">Keywords</span></span>

<span data-ttu-id="30200-819">| |</span><span class="sxs-lookup"><span data-stu-id="30200-819">| |</span></span>
|<span data-ttu-id="30200-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="30200-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="30200-821">Dl#</span><span class="sxs-lookup"><span data-stu-id="30200-821">dl#</span></span>  <br/> <span data-ttu-id="30200-822">駕照</span><span class="sxs-lookup"><span data-stu-id="30200-822">driver license</span></span>  <br/> <span data-ttu-id="30200-823">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-823">driver license number</span></span>  <br/> <span data-ttu-id="30200-824">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-824">driver licence</span></span>  <br/> <span data-ttu-id="30200-825">驅動程式 .lic。</span><span class="sxs-lookup"><span data-stu-id="30200-825">drivers lic.</span></span>  <br/> <span data-ttu-id="30200-826">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="30200-826">drivers license</span></span>  <br/> <span data-ttu-id="30200-827">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="30200-827">drivers licence</span></span>  <br/> <span data-ttu-id="30200-828">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="30200-828">driver's license</span></span>  <br/> <span data-ttu-id="30200-829">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-829">driver's license number</span></span>  <br/> <span data-ttu-id="30200-830">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-830">driver's licence number</span></span>  <br/> <span data-ttu-id="30200-831">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="30200-831">driving license number</span></span>  <br/> <span data-ttu-id="30200-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="30200-832">dlno#</span></span>  <br/> <span data-ttu-id="30200-833">körkort</span><span class="sxs-lookup"><span data-stu-id="30200-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="30200-834">英國</span><span class="sxs-lookup"><span data-stu-id="30200-834">UK</span></span>

<span data-ttu-id="30200-835">如需詳細資訊，請參閱 section "英</span><span class="sxs-lookup"><span data-stu-id="30200-835">For details, see the section "U.K.</span></span> <span data-ttu-id="30200-836">「[敏感資訊類型](what-the-sensitive-information-types-look-for.md)」所尋找的「駕照編號」。</span><span class="sxs-lookup"><span data-stu-id="30200-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="30200-837">另請參閱</span><span class="sxs-lookup"><span data-stu-id="30200-837">See also</span></span>

[<span data-ttu-id="30200-838">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="30200-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

