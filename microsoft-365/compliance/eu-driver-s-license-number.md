---
title: 歐盟駕照編號
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077081"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="ff907-104">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-104">EU Driver's License Number</span></span>

<span data-ttu-id="ff907-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ff907-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="ff907-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="ff907-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="ff907-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="ff907-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="ff907-108">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-108">Format</span></span>

<span data-ttu-id="ff907-109">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-110">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-110">Pattern</span></span>

<span data-ttu-id="ff907-111">八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ff907-112">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-112">Checksum</span></span>

<span data-ttu-id="ff907-113">否</span><span class="sxs-lookup"><span data-stu-id="ff907-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-114">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-114">Definition</span></span>

<span data-ttu-id="ff907-115">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-116">規則運算式`Regex_austria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-117">從關鍵字`Keywords_austria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="ff907-118">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-118">Keywords</span></span>

<span data-ttu-id="ff907-119">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-119"></span></span>
|<span data-ttu-id="ff907-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-121">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-121">dl#</span></span>  <br/> <span data-ttu-id="ff907-122">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-122">driver license</span></span>  <br/> <span data-ttu-id="ff907-123">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-123">driver license number</span></span>  <br/> <span data-ttu-id="ff907-124">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-124">driver licence</span></span>  <br/> <span data-ttu-id="ff907-125">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-125">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-126">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-126">drivers license</span></span>  <br/> <span data-ttu-id="ff907-127">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="ff907-127">driver's licence</span></span>  <br/> <span data-ttu-id="ff907-128">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-128">driver's license</span></span>  <br/> <span data-ttu-id="ff907-129">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-129">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-130">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="ff907-131">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-131">driving license number</span></span>  <br/> <span data-ttu-id="ff907-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-132">dlno#</span></span>  <br/> <span data-ttu-id="ff907-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="ff907-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="ff907-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="ff907-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="ff907-135">比利時</span><span class="sxs-lookup"><span data-stu-id="ff907-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="ff907-136">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-136">Format</span></span>

<span data-ttu-id="ff907-137">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="ff907-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-138">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-138">Pattern</span></span>

<span data-ttu-id="ff907-139">10 位數</span><span class="sxs-lookup"><span data-stu-id="ff907-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ff907-140">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-140">Checksum</span></span>

<span data-ttu-id="ff907-141">否</span><span class="sxs-lookup"><span data-stu-id="ff907-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-142">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-142">Definition</span></span>

<span data-ttu-id="ff907-143">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-144">規則運算式`Regex_belgium_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-145">從關鍵字`Keywords_belgium_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="ff907-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-146">Keywords</span></span>

<span data-ttu-id="ff907-147">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-147"></span></span>
|<span data-ttu-id="ff907-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-149">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-149">dl#</span></span>  <br/> <span data-ttu-id="ff907-150">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-150">driver license</span></span>  <br/> <span data-ttu-id="ff907-151">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-151">driver license number</span></span>  <br/> <span data-ttu-id="ff907-152">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-152">driver licence</span></span>  <br/> <span data-ttu-id="ff907-153">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-153">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-154">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-154">drivers license</span></span>  <br/> <span data-ttu-id="ff907-155">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-155">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-156">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-156">driver's license</span></span>  <br/> <span data-ttu-id="ff907-157">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-157">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-158">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-158">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-159">dlno#</span></span>  <br/> <span data-ttu-id="ff907-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="ff907-160">rijbewijs</span></span>  <br/> <span data-ttu-id="ff907-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="ff907-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="ff907-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ff907-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="ff907-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ff907-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="ff907-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ff907-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="ff907-165">führerschein 編號</span><span class="sxs-lookup"><span data-stu-id="ff907-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="ff907-166">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="ff907-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="ff907-167">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="ff907-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="ff907-168">保加利亞</span><span class="sxs-lookup"><span data-stu-id="ff907-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="ff907-169">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-169">Format</span></span>

<span data-ttu-id="ff907-170">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="ff907-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-171">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-171">Pattern</span></span>

<span data-ttu-id="ff907-172">九位數</span><span class="sxs-lookup"><span data-stu-id="ff907-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ff907-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-173">Checksum</span></span>

<span data-ttu-id="ff907-174">否</span><span class="sxs-lookup"><span data-stu-id="ff907-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-175">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-175">Definition</span></span>

<span data-ttu-id="ff907-176">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-177">規則運算式`Regex_bulgaria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-178">從關鍵字`Keywords_bulgaria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="ff907-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-179">Keywords</span></span>

<span data-ttu-id="ff907-180">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-180"></span></span>
|<span data-ttu-id="ff907-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-182">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-182">dl#</span></span>  <br/> <span data-ttu-id="ff907-183">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-183">driver license</span></span>  <br/> <span data-ttu-id="ff907-184">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-184">driver license number</span></span>  <br/> <span data-ttu-id="ff907-185">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-185">driver licence</span></span>  <br/> <span data-ttu-id="ff907-186">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-186">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-187">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-187">drivers license</span></span>  <br/> <span data-ttu-id="ff907-188">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-188">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-189">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-189">driver's license</span></span>  <br/> <span data-ttu-id="ff907-190">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-190">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-191">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-191">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-192">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-192">driving license number</span></span>  <br/> <span data-ttu-id="ff907-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-193">dlno#</span></span>  <br/> <span data-ttu-id="ff907-194">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС</span><span class="sxs-lookup"><span data-stu-id="ff907-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="ff907-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="ff907-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="ff907-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="ff907-196">сумпс</span></span>  <br/> <span data-ttu-id="ff907-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="ff907-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="ff907-198">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="ff907-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="ff907-199">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-199">Format</span></span>

<span data-ttu-id="ff907-200">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-201">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-201">Pattern</span></span>

<span data-ttu-id="ff907-202">八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ff907-203">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-203">Checksum</span></span>

<span data-ttu-id="ff907-204">否</span><span class="sxs-lookup"><span data-stu-id="ff907-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-205">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-205">Definition</span></span>

<span data-ttu-id="ff907-206">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-207">規則運算式`Regex_croatia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-208">從關鍵字`Keywords_croatia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="ff907-209">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-209">Keywords</span></span>

<span data-ttu-id="ff907-210">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-210"></span></span>
|<span data-ttu-id="ff907-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-212">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-212">dl#</span></span>  <br/> <span data-ttu-id="ff907-213">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-213">driver license</span></span>  <br/> <span data-ttu-id="ff907-214">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-214">driver license number</span></span>  <br/> <span data-ttu-id="ff907-215">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-215">driver licence</span></span>  <br/> <span data-ttu-id="ff907-216">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-216">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-217">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-217">drivers license</span></span>  <br/> <span data-ttu-id="ff907-218">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-218">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-219">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-219">driver's license</span></span>  <br/> <span data-ttu-id="ff907-220">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-220">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-221">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-221">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-222">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-222">driving license number</span></span>  <br/> <span data-ttu-id="ff907-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-223">dlno#</span></span>  <br/> <span data-ttu-id="ff907-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="ff907-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="ff907-225">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="ff907-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="ff907-226">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-226">Format</span></span>

<span data-ttu-id="ff907-227">如果沒有空格和分隔符號的 12 位數</span><span class="sxs-lookup"><span data-stu-id="ff907-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-228">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-228">Pattern</span></span>

<span data-ttu-id="ff907-229">12 位數</span><span class="sxs-lookup"><span data-stu-id="ff907-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ff907-230">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-230">Checksum</span></span>

<span data-ttu-id="ff907-231">否</span><span class="sxs-lookup"><span data-stu-id="ff907-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-232">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-232">Definition</span></span>

<span data-ttu-id="ff907-233">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-234">規則運算式`Regex_cyprus_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-235">從關鍵字`Keywords_cyprus_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-236">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-236">Keywords</span></span>

<span data-ttu-id="ff907-237">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-237"></span></span>
|<span data-ttu-id="ff907-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-239">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-239">dl#</span></span>  <br/> <span data-ttu-id="ff907-240">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-240">driver license</span></span>  <br/> <span data-ttu-id="ff907-241">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-241">driver license number</span></span>  <br/> <span data-ttu-id="ff907-242">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-242">driver licence</span></span>  <br/> <span data-ttu-id="ff907-243">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-243">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-244">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-244">drivers license</span></span>  <br/> <span data-ttu-id="ff907-245">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-245">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-246">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-246">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-247">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-247">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-248">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-248">driving license number</span></span>  <br/> <span data-ttu-id="ff907-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-249">dlno#</span></span>  <br/> <span data-ttu-id="ff907-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="ff907-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="ff907-251">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="ff907-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="ff907-252">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-252">Format</span></span>

<span data-ttu-id="ff907-253">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-254">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-254">Pattern</span></span>

<span data-ttu-id="ff907-255">八個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="ff907-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="ff907-256">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="ff907-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="ff907-257">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="ff907-257">A space (optional)</span></span>
    
- <span data-ttu-id="ff907-258">六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ff907-259">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-259">Checksum</span></span>

<span data-ttu-id="ff907-260">否</span><span class="sxs-lookup"><span data-stu-id="ff907-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-261">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-261">Definition</span></span>

<span data-ttu-id="ff907-262">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-263">規則運算式`Regex_czech_republic_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-264">從關鍵字`Keywords_czech_republic_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="ff907-265">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-265">Keywords</span></span>

<span data-ttu-id="ff907-266">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-266"></span></span>
|<span data-ttu-id="ff907-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-268">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-268">dl#</span></span>  <br/> <span data-ttu-id="ff907-269">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-269">driver license</span></span>  <br/> <span data-ttu-id="ff907-270">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-270">driver license number</span></span>  <br/> <span data-ttu-id="ff907-271">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-271">driver licence</span></span>  <br/> <span data-ttu-id="ff907-272">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-272">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-273">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-273">drivers license</span></span>  <br/> <span data-ttu-id="ff907-274">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-274">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-275">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-275">driver's license</span></span>  <br/> <span data-ttu-id="ff907-276">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-276">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-277">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-277">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-278">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-278">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-279">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-279">driving license number</span></span>  <br/> <span data-ttu-id="ff907-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-280">dlno#</span></span>  <br/> <span data-ttu-id="ff907-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="ff907-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="ff907-282">丹麥</span><span class="sxs-lookup"><span data-stu-id="ff907-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="ff907-283">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-283">Format</span></span>

<span data-ttu-id="ff907-284">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-285">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-285">Pattern</span></span>

<span data-ttu-id="ff907-286">八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ff907-287">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-287">Checksum</span></span>

<span data-ttu-id="ff907-288">是</span><span class="sxs-lookup"><span data-stu-id="ff907-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-289">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-289">Definition</span></span>

<span data-ttu-id="ff907-290">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-291">規則運算式`Regex_denmark_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-292">從關鍵字`Keywords_denmark_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="ff907-293">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-293">Keywords</span></span>

<span data-ttu-id="ff907-294">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-294"></span></span>
|<span data-ttu-id="ff907-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-296">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-296">dl#</span></span>  <br/> <span data-ttu-id="ff907-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-297">driver license</span></span>  <br/> <span data-ttu-id="ff907-298">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-298">driver license number</span></span>  <br/> <span data-ttu-id="ff907-299">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-299">driver licence</span></span>  <br/> <span data-ttu-id="ff907-300">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-300">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-301">drivers license</span></span>  <br/> <span data-ttu-id="ff907-302">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-302">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-303">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-303">driver's license</span></span>  <br/> <span data-ttu-id="ff907-304">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-304">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-305">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-305">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-306">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-306">driving license number</span></span>  <br/> <span data-ttu-id="ff907-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-307">dlno#</span></span>  <br/> <span data-ttu-id="ff907-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="ff907-308">kørekort</span></span>  <br/> <span data-ttu-id="ff907-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="ff907-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="ff907-310">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="ff907-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="ff907-311">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-311">Format</span></span>

<span data-ttu-id="ff907-312">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-313">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-313">Pattern</span></span>

<span data-ttu-id="ff907-314">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="ff907-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="ff907-315">字母"ET 」 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="ff907-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="ff907-316">六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ff907-317">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-317">Checksum</span></span>

<span data-ttu-id="ff907-318">否</span><span class="sxs-lookup"><span data-stu-id="ff907-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-319">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-319">Definition</span></span>

<span data-ttu-id="ff907-320">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-321">規則運算式`Regex_estonia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-322">從關鍵字`Keywords_estonia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-323">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-323">Keywords</span></span>

<span data-ttu-id="ff907-324">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-324"></span></span>
|<span data-ttu-id="ff907-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-326">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-326">dl#</span></span>  <br/> <span data-ttu-id="ff907-327">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-327">driver license</span></span>  <br/> <span data-ttu-id="ff907-328">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-328">driver license number</span></span>  <br/> <span data-ttu-id="ff907-329">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-329">driver license number</span></span>  <br/> <span data-ttu-id="ff907-330">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-330">driver licence</span></span>  <br/> <span data-ttu-id="ff907-331">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-331">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-332">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-332">drivers license</span></span>  <br/> <span data-ttu-id="ff907-333">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-333">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-334">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-334">driver's license</span></span>  <br/> <span data-ttu-id="ff907-335">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-335">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-336">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-336">driving license number</span></span>  <br/> <span data-ttu-id="ff907-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-337">dlno#</span></span>  <br/> <span data-ttu-id="ff907-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="ff907-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="ff907-339">芬蘭</span><span class="sxs-lookup"><span data-stu-id="ff907-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="ff907-340">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-340">Format</span></span>

<span data-ttu-id="ff907-341">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="ff907-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-342">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-342">Pattern</span></span>

<span data-ttu-id="ff907-343">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="ff907-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="ff907-344">六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-344">Six digits</span></span> 
    
- <span data-ttu-id="ff907-345">連字號</span><span class="sxs-lookup"><span data-stu-id="ff907-345">A hyphen</span></span>
    
-  <span data-ttu-id="ff907-346">四位數</span><span class="sxs-lookup"><span data-stu-id="ff907-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="ff907-347">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-347">Checksum</span></span>

<span data-ttu-id="ff907-348">否</span><span class="sxs-lookup"><span data-stu-id="ff907-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-349">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-349">Definition</span></span>

<span data-ttu-id="ff907-350">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-351">規則運算式`Regex_finland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-352">從關鍵字`Keywords_finland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-353">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-353">Keywords</span></span>

<span data-ttu-id="ff907-354">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-354"></span></span>
|<span data-ttu-id="ff907-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-356">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-356">dl#</span></span>  <br/> <span data-ttu-id="ff907-357">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-357">driver license</span></span>  <br/> <span data-ttu-id="ff907-358">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-358">driver license number</span></span>  <br/> <span data-ttu-id="ff907-359">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-359">driver licence</span></span>  <br/> <span data-ttu-id="ff907-360">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-360">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-361">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-361">drivers license</span></span>  <br/> <span data-ttu-id="ff907-362">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-362">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-363">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-363">driver's license</span></span>  <br/> <span data-ttu-id="ff907-364">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-364">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-365">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-365">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-366">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-366">driving license number</span></span>  <br/> <span data-ttu-id="ff907-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-367">dlno#</span></span>  <br/> <span data-ttu-id="ff907-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="ff907-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="ff907-369">法國</span><span class="sxs-lookup"><span data-stu-id="ff907-369">France</span></span>

<span data-ttu-id="ff907-370">如需詳細資訊，請參閱 「 法國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="ff907-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="ff907-371">德國</span><span class="sxs-lookup"><span data-stu-id="ff907-371">Germany</span></span>

<span data-ttu-id="ff907-372">如需詳細資訊，請參閱 「 德國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="ff907-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="ff907-373">希臘</span><span class="sxs-lookup"><span data-stu-id="ff907-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="ff907-374">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-374">Format</span></span>

<span data-ttu-id="ff907-375">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="ff907-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-376">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-376">Pattern</span></span>

 <span data-ttu-id="ff907-377">九位數</span><span class="sxs-lookup"><span data-stu-id="ff907-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="ff907-378">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-378">Checksum</span></span>

<span data-ttu-id="ff907-379">否</span><span class="sxs-lookup"><span data-stu-id="ff907-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-380">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-380">Definition</span></span>

<span data-ttu-id="ff907-381">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-382">規則運算式`Regex_greece_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-383">從關鍵字`Keywords_greece_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-384">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-384">Keywords</span></span>

<span data-ttu-id="ff907-385">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-385"></span></span>
|<span data-ttu-id="ff907-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-387">dlL#</span><span class="sxs-lookup"><span data-stu-id="ff907-387">dlL#</span></span>  <br/> <span data-ttu-id="ff907-388">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-388">driver license</span></span>  <br/> <span data-ttu-id="ff907-389">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-389">driver license number</span></span>  <br/> <span data-ttu-id="ff907-390">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-390">driver licence</span></span>  <br/> <span data-ttu-id="ff907-391">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-391">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-392">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-392">drivers license</span></span>  <br/> <span data-ttu-id="ff907-393">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-393">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-394">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-394">driver's license</span></span>  <br/> <span data-ttu-id="ff907-395">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-395">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-396">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-396">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-397">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-397">driving license number</span></span>  <br/> <span data-ttu-id="ff907-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-398">dlno#</span></span>  <br/> <span data-ttu-id="ff907-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="ff907-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="ff907-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="ff907-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="ff907-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="ff907-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="ff907-402">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-402">Format</span></span>

<span data-ttu-id="ff907-403">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-404">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-404">Pattern</span></span>

<span data-ttu-id="ff907-405">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="ff907-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="ff907-406">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="ff907-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="ff907-407">六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ff907-408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-408">Checksum</span></span>

<span data-ttu-id="ff907-409">否</span><span class="sxs-lookup"><span data-stu-id="ff907-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-410">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-410">Definition</span></span>

<span data-ttu-id="ff907-411">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-412">規則運算式`Regex_hungary_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-413">從關鍵字`Keywords_hungary_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-414">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-414">Keywords</span></span>

<span data-ttu-id="ff907-415">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-415"></span></span>
|<span data-ttu-id="ff907-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-417">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-417">dl#</span></span>  <br/> <span data-ttu-id="ff907-418">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-418">driver license</span></span>  <br/> <span data-ttu-id="ff907-419">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-419">driver license number</span></span>  <br/> <span data-ttu-id="ff907-420">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-420">driver licence</span></span>  <br/> <span data-ttu-id="ff907-421">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-421">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-422">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-422">drivers license</span></span>  <br/> <span data-ttu-id="ff907-423">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-423">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-424">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-424">driver's license</span></span>  <br/> <span data-ttu-id="ff907-425">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-425">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-426">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-426">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-427">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-427">driving license number</span></span>  <br/> <span data-ttu-id="ff907-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-428">dlno#</span></span>  <br/> <span data-ttu-id="ff907-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="ff907-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="ff907-430">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="ff907-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="ff907-431">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-431">Format</span></span>

<span data-ttu-id="ff907-432">四個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-433">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-433">Pattern</span></span>

<span data-ttu-id="ff907-434">六位數和四個字母：</span><span class="sxs-lookup"><span data-stu-id="ff907-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="ff907-435">六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-435">Six digits</span></span>
    
- <span data-ttu-id="ff907-436">四個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="ff907-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ff907-437">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-437">Checksum</span></span>

<span data-ttu-id="ff907-438">否</span><span class="sxs-lookup"><span data-stu-id="ff907-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-439">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-439">Definition</span></span>

<span data-ttu-id="ff907-440">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-441">規則運算式`Regex_ireland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-442">從關鍵字`Keywords_ireland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-443">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-443">Keywords</span></span>

<span data-ttu-id="ff907-444">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-444"></span></span>
|<span data-ttu-id="ff907-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-446">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-446">dl#</span></span>  <br/> <span data-ttu-id="ff907-447">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-447">driver license</span></span>  <br/> <span data-ttu-id="ff907-448">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-448">driver license number</span></span>  <br/> <span data-ttu-id="ff907-449">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-449">driver licence</span></span>  <br/> <span data-ttu-id="ff907-450">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-450">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-451">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-451">drivers license</span></span>  <br/> <span data-ttu-id="ff907-452">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-452">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-453">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-453">driver's license</span></span>  <br/> <span data-ttu-id="ff907-454">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-454">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-455">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-455">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-456">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-456">driving license number</span></span>  <br/> <span data-ttu-id="ff907-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-457">dlno#</span></span>  <br/> <span data-ttu-id="ff907-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="ff907-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="ff907-459">義大利</span><span class="sxs-lookup"><span data-stu-id="ff907-459">Italy</span></span>

<span data-ttu-id="ff907-460">如需詳細資訊，請參閱 「 義大利駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="ff907-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="ff907-461">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="ff907-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="ff907-462">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-462">Format</span></span>

<span data-ttu-id="ff907-463">三個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-464">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-464">Pattern</span></span>

<span data-ttu-id="ff907-465">三個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="ff907-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="ff907-466">三個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="ff907-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="ff907-467">六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ff907-468">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-468">Checksum</span></span>

<span data-ttu-id="ff907-469">否</span><span class="sxs-lookup"><span data-stu-id="ff907-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-470">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-470">Definition</span></span>

<span data-ttu-id="ff907-471">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-472">規則運算式`Regex_latvia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-473">從關鍵字`Keywords_latvia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-474">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-474">Keywords</span></span>

<span data-ttu-id="ff907-475">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-475"></span></span>
|<span data-ttu-id="ff907-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-477">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-477">dl#</span></span>  <br/> <span data-ttu-id="ff907-478">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-478">driver license</span></span>  <br/> <span data-ttu-id="ff907-479">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-479">driver license number</span></span>  <br/> <span data-ttu-id="ff907-480">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-480">driver licence</span></span>  <br/> <span data-ttu-id="ff907-481">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-481">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-482">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-482">drivers license</span></span>  <br/> <span data-ttu-id="ff907-483">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-483">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-484">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-484">driver's license</span></span>  <br/> <span data-ttu-id="ff907-485">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-485">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-486">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-486">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-487">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-487">driving license number</span></span>  <br/> <span data-ttu-id="ff907-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-488">dlno#</span></span>  <br/> <span data-ttu-id="ff907-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="ff907-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="ff907-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="ff907-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="ff907-491">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-491">Format</span></span>

<span data-ttu-id="ff907-492">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-493">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-493">Pattern</span></span>

 <span data-ttu-id="ff907-494">八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="ff907-495">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-495">Checksum</span></span>

<span data-ttu-id="ff907-496">否</span><span class="sxs-lookup"><span data-stu-id="ff907-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-497">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-497">Definition</span></span>

<span data-ttu-id="ff907-498">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-499">規則運算式`Regex_lithuania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-500">從關鍵字`Keywords_lithuania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-501">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-501">Keywords</span></span>

<span data-ttu-id="ff907-502">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-502"></span></span>
|<span data-ttu-id="ff907-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-504">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-504">dl#</span></span>  <br/> <span data-ttu-id="ff907-505">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-505">driver license</span></span>  <br/> <span data-ttu-id="ff907-506">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-506">driver license number</span></span>  <br/> <span data-ttu-id="ff907-507">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-507">driver licence</span></span>  <br/> <span data-ttu-id="ff907-508">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-508">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-509">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-509">drivers license</span></span>  <br/> <span data-ttu-id="ff907-510">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-510">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-511">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-511">driver's license</span></span>  <br/> <span data-ttu-id="ff907-512">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-512">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-513">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-513">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-514">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-514">driving license number</span></span>  <br/> <span data-ttu-id="ff907-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-515">dlno#</span></span>  <br/> <span data-ttu-id="ff907-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="ff907-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="ff907-517">盧森堡</span><span class="sxs-lookup"><span data-stu-id="ff907-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="ff907-518">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-518">Format</span></span>

<span data-ttu-id="ff907-519">六位數，代表不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="ff907-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-520">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-520">Pattern</span></span>

 <span data-ttu-id="ff907-521">六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="ff907-522">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-522">Checksum</span></span>

<span data-ttu-id="ff907-523">否</span><span class="sxs-lookup"><span data-stu-id="ff907-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-524">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-524">Definition</span></span>

<span data-ttu-id="ff907-525">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-526">規則運算式`Regex_luxemburg_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-527">從關鍵字`Keywords_luxemburg_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-528">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-528">Keywords</span></span>

<span data-ttu-id="ff907-529">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-529"></span></span>
|<span data-ttu-id="ff907-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-531">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-531">dl#</span></span>  <br/> <span data-ttu-id="ff907-532">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-532">driver license</span></span>  <br/> <span data-ttu-id="ff907-533">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-533">driver license number</span></span>  <br/> <span data-ttu-id="ff907-534">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-534">driver licence</span></span>  <br/> <span data-ttu-id="ff907-535">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-535">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-536">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-536">drivers license</span></span>  <br/> <span data-ttu-id="ff907-537">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-537">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-538">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-538">driver's license</span></span>  <br/> <span data-ttu-id="ff907-539">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-539">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-540">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-540">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-541">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-541">driving license number</span></span>  <br/> <span data-ttu-id="ff907-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-542">dlno#</span></span>  <br/> <span data-ttu-id="ff907-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="ff907-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="ff907-544">馬爾他</span><span class="sxs-lookup"><span data-stu-id="ff907-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="ff907-545">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-545">Format</span></span>

<span data-ttu-id="ff907-546">兩個字元和六位數，代表所指定的型態的組合</span><span class="sxs-lookup"><span data-stu-id="ff907-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-547">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-547">Pattern</span></span>

<span data-ttu-id="ff907-548">兩個字元和六位數的組合：</span><span class="sxs-lookup"><span data-stu-id="ff907-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="ff907-549">兩個字元 （數字或字母、 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="ff907-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="ff907-550">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="ff907-550">A space (optional)</span></span>
    
- <span data-ttu-id="ff907-551">三位數</span><span class="sxs-lookup"><span data-stu-id="ff907-551">Three digits</span></span>
    
- <span data-ttu-id="ff907-552">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="ff907-552">A space (optional)</span></span>
    
- <span data-ttu-id="ff907-553">三位數</span><span class="sxs-lookup"><span data-stu-id="ff907-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ff907-554">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-554">Checksum</span></span>

<span data-ttu-id="ff907-555">否</span><span class="sxs-lookup"><span data-stu-id="ff907-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-556">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-556">Definition</span></span>

<span data-ttu-id="ff907-557">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-558">規則運算式`Regex_malta_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-559">從關鍵字`Keywords_malta_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-560">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-560">Keywords</span></span>

<span data-ttu-id="ff907-561">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-561"></span></span>
|<span data-ttu-id="ff907-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-563">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-563">dl#</span></span>  <br/> <span data-ttu-id="ff907-564">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-564">driver license</span></span>  <br/> <span data-ttu-id="ff907-565">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-565">driver license number</span></span>  <br/> <span data-ttu-id="ff907-566">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-566">driver licence</span></span>  <br/> <span data-ttu-id="ff907-567">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-567">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-568">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-568">drivers license</span></span>  <br/> <span data-ttu-id="ff907-569">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-569">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-570">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-570">driver's license</span></span>  <br/> <span data-ttu-id="ff907-571">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-571">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-572">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-572">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-573">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-573">driving license number</span></span>  <br/> <span data-ttu-id="ff907-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-574">dlno#</span></span>  <br/> <span data-ttu-id="ff907-575">liċenzja 塔司 sewqan</span><span class="sxs-lookup"><span data-stu-id="ff907-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="ff907-576">荷蘭</span><span class="sxs-lookup"><span data-stu-id="ff907-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="ff907-577">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-577">Format</span></span>

<span data-ttu-id="ff907-578">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="ff907-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-579">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-579">Pattern</span></span>

<span data-ttu-id="ff907-580">10 位數</span><span class="sxs-lookup"><span data-stu-id="ff907-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ff907-581">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-581">Checksum</span></span>

<span data-ttu-id="ff907-582">否</span><span class="sxs-lookup"><span data-stu-id="ff907-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-583">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-583">Definition</span></span>

<span data-ttu-id="ff907-584">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-585">規則運算式`Regex_netherlands_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-586">從關鍵字`Keywords_netherlands_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-587">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-587">Keywords</span></span>

<span data-ttu-id="ff907-588">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-588"></span></span>
|<span data-ttu-id="ff907-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-590">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-590">dl#</span></span>  <br/> <span data-ttu-id="ff907-591">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-591">driver license</span></span>  <br/> <span data-ttu-id="ff907-592">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-592">driver license number</span></span>  <br/> <span data-ttu-id="ff907-593">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-593">driver licence</span></span>  <br/> <span data-ttu-id="ff907-594">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-594">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-595">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-595">drivers license</span></span>  <br/> <span data-ttu-id="ff907-596">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-596">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-597">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-597">driver's license</span></span>  <br/> <span data-ttu-id="ff907-598">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-598">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-599">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-599">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-600">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-600">driving license number</span></span>  <br/> <span data-ttu-id="ff907-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-601">dlno#</span></span>  <br/> <span data-ttu-id="ff907-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="ff907-602">permis de conduire</span></span>  <br/> <span data-ttu-id="ff907-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="ff907-603">rijbewijs</span></span>  <br/> <span data-ttu-id="ff907-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="ff907-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="ff907-605">波蘭</span><span class="sxs-lookup"><span data-stu-id="ff907-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="ff907-606">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-606">Format</span></span>

<span data-ttu-id="ff907-607">14 位數包含正斜線，2</span><span class="sxs-lookup"><span data-stu-id="ff907-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-608">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-608">Pattern</span></span>

<span data-ttu-id="ff907-609">14 位數和 2 的正斜線：</span><span class="sxs-lookup"><span data-stu-id="ff907-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="ff907-610">五位數</span><span class="sxs-lookup"><span data-stu-id="ff907-610">Five digits</span></span> 
    
- <span data-ttu-id="ff907-611">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="ff907-611">A forward slash</span></span>
    
- <span data-ttu-id="ff907-612">兩位數</span><span class="sxs-lookup"><span data-stu-id="ff907-612">Two digits</span></span>
    
- <span data-ttu-id="ff907-613">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="ff907-613">A forward slash</span></span>
    
- <span data-ttu-id="ff907-614">七位數</span><span class="sxs-lookup"><span data-stu-id="ff907-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ff907-615">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-615">Checksum</span></span>

<span data-ttu-id="ff907-616">否</span><span class="sxs-lookup"><span data-stu-id="ff907-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-617">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-617">Definition</span></span>

<span data-ttu-id="ff907-618">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-619">規則運算式`Regex_poland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-620">從關鍵字`Keywords_poland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-621">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-621">Keywords</span></span>

<span data-ttu-id="ff907-622">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-622"></span></span>
|<span data-ttu-id="ff907-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-624">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-624">dl#</span></span>  <br/> <span data-ttu-id="ff907-625">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-625">driver license</span></span>  <br/> <span data-ttu-id="ff907-626">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-626">driver license number</span></span>  <br/> <span data-ttu-id="ff907-627">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-627">driver licence</span></span>  <br/> <span data-ttu-id="ff907-628">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-628">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-629">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-629">drivers license</span></span>  <br/> <span data-ttu-id="ff907-630">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-630">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-631">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-631">driver's license</span></span>  <br/> <span data-ttu-id="ff907-632">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-632">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-633">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-633">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-634">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-634">driving license number</span></span>  <br/> <span data-ttu-id="ff907-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-635">dlno#</span></span>  <br/> <span data-ttu-id="ff907-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="ff907-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="ff907-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="ff907-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="ff907-638">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-638">Format</span></span>

<span data-ttu-id="ff907-639">兩個字母後尾隨七個的數字中指定的型態</span><span class="sxs-lookup"><span data-stu-id="ff907-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-640">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-640">Pattern</span></span>

<span data-ttu-id="ff907-641">兩個字母後尾隨七個具有特殊字元的數字：</span><span class="sxs-lookup"><span data-stu-id="ff907-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="ff907-642">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="ff907-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="ff907-643">連字號</span><span class="sxs-lookup"><span data-stu-id="ff907-643">A hyphen</span></span>
    
- <span data-ttu-id="ff907-644">六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-644">Six digits</span></span>
    
- <span data-ttu-id="ff907-645">一個空格</span><span class="sxs-lookup"><span data-stu-id="ff907-645">A space</span></span>
    
- <span data-ttu-id="ff907-646">一位數</span><span class="sxs-lookup"><span data-stu-id="ff907-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ff907-647">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-647">Checksum</span></span>

<span data-ttu-id="ff907-648">否</span><span class="sxs-lookup"><span data-stu-id="ff907-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-649">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-649">Definition</span></span>

<span data-ttu-id="ff907-650">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-651">規則運算式`Regex_portugal_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-652">從關鍵字`Keywords_portugal_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-653">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-653">Keywords</span></span>

<span data-ttu-id="ff907-654">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-654"></span></span>
|<span data-ttu-id="ff907-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-656">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-656">dl#</span></span>  <br/> <span data-ttu-id="ff907-657">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-657">driver license</span></span>  <br/> <span data-ttu-id="ff907-658">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-658">driver license number</span></span>  <br/> <span data-ttu-id="ff907-659">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-659">driver licence</span></span>  <br/> <span data-ttu-id="ff907-660">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-660">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-661">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-661">drivers license</span></span>  <br/> <span data-ttu-id="ff907-662">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-662">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-663">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-663">driver's license</span></span>  <br/> <span data-ttu-id="ff907-664">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-664">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-665">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-665">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-666">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-666">driving license number</span></span>  <br/> <span data-ttu-id="ff907-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-667">dlno#</span></span>  <br/> <span data-ttu-id="ff907-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="ff907-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="ff907-669">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="ff907-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="ff907-670">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-670">Format</span></span>

<span data-ttu-id="ff907-671">一個字元尾隨八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-672">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-672">Pattern</span></span>

<span data-ttu-id="ff907-673">尾隨八位數的一個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="ff907-674">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="ff907-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="ff907-675">八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ff907-676">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-676">Checksum</span></span>

<span data-ttu-id="ff907-677">否</span><span class="sxs-lookup"><span data-stu-id="ff907-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-678">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-678">Definition</span></span>

<span data-ttu-id="ff907-679">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-680">規則運算式`Regex_romania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-681">從關鍵字`Keywords_romania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-682">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-682">Keywords</span></span>

<span data-ttu-id="ff907-683">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-683"></span></span>
|<span data-ttu-id="ff907-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-685">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-685">dl#</span></span>  <br/> <span data-ttu-id="ff907-686">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-686">driver license</span></span>  <br/> <span data-ttu-id="ff907-687">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-687">driver license number</span></span>  <br/> <span data-ttu-id="ff907-688">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-688">driver licence</span></span>  <br/> <span data-ttu-id="ff907-689">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-689">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-690">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-690">drivers license</span></span>  <br/> <span data-ttu-id="ff907-691">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-691">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-692">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-692">driver's license</span></span>  <br/> <span data-ttu-id="ff907-693">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-693">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-694">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-694">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-695">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-695">driving license number</span></span>  <br/> <span data-ttu-id="ff907-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-696">dlno#</span></span>  <br/> <span data-ttu-id="ff907-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="ff907-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="ff907-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="ff907-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="ff907-699">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-699">Format</span></span>

<span data-ttu-id="ff907-700">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="ff907-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-701">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-701">Pattern</span></span>

<span data-ttu-id="ff907-702">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="ff907-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="ff907-703">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="ff907-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="ff907-704">七位數</span><span class="sxs-lookup"><span data-stu-id="ff907-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="ff907-705">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-705">Checksum</span></span>

<span data-ttu-id="ff907-706">否</span><span class="sxs-lookup"><span data-stu-id="ff907-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-707">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-707">Definition</span></span>

<span data-ttu-id="ff907-708">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-709">規則運算式`Regex_slovakia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-710">從關鍵字`Keywords_slovakia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-711">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-711">Keywords</span></span>

<span data-ttu-id="ff907-712">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-712"></span></span>
|<span data-ttu-id="ff907-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-714">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-714">dl#</span></span>  <br/> <span data-ttu-id="ff907-715">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-715">driver license</span></span>  <br/> <span data-ttu-id="ff907-716">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-716">driver license number</span></span>  <br/> <span data-ttu-id="ff907-717">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-717">driver licence</span></span>  <br/> <span data-ttu-id="ff907-718">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-718">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-719">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-719">drivers license</span></span>  <br/> <span data-ttu-id="ff907-720">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-720">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-721">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-721">driver's license</span></span>  <br/> <span data-ttu-id="ff907-722">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-722">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-723">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-723">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-724">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-724">driving license number</span></span>  <br/> <span data-ttu-id="ff907-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-725">dlno#</span></span>  <br/> <span data-ttu-id="ff907-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="ff907-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="ff907-727">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="ff907-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="ff907-728">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-728">Format</span></span>

<span data-ttu-id="ff907-729">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="ff907-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-730">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-730">Pattern</span></span>

<span data-ttu-id="ff907-731">九位數</span><span class="sxs-lookup"><span data-stu-id="ff907-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ff907-732">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-732">Checksum</span></span>

<span data-ttu-id="ff907-733">否</span><span class="sxs-lookup"><span data-stu-id="ff907-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-734">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-734">Definition</span></span>

<span data-ttu-id="ff907-735">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-736">規則運算式`Regex_slovenia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-737">從關鍵字`Keywords_slovenia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-738">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-738">Keywords</span></span>

<span data-ttu-id="ff907-739">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-739"></span></span>
|<span data-ttu-id="ff907-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-741">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-741">dl#</span></span>  <br/> <span data-ttu-id="ff907-742">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-742">driver license</span></span>  <br/> <span data-ttu-id="ff907-743">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-743">driver license number</span></span>  <br/> <span data-ttu-id="ff907-744">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-744">driver licence</span></span>  <br/> <span data-ttu-id="ff907-745">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-745">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-746">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-746">drivers license</span></span>  <br/> <span data-ttu-id="ff907-747">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-747">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-748">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-748">driver's license</span></span>  <br/> <span data-ttu-id="ff907-749">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-749">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-750">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-750">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-751">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-751">driving license number</span></span>  <br/> <span data-ttu-id="ff907-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-752">dlno#</span></span>  <br/> <span data-ttu-id="ff907-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="ff907-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="ff907-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="ff907-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="ff907-755">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-755">Format</span></span>

<span data-ttu-id="ff907-756">後面接著一個字元的八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-757">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-757">Pattern</span></span>

<span data-ttu-id="ff907-758">後面接著一個字元的八位數：</span><span class="sxs-lookup"><span data-stu-id="ff907-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="ff907-759">八位數</span><span class="sxs-lookup"><span data-stu-id="ff907-759">Eight digits</span></span> 
    
- <span data-ttu-id="ff907-760">一個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="ff907-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ff907-761">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-761">Checksum</span></span>

<span data-ttu-id="ff907-762">是</span><span class="sxs-lookup"><span data-stu-id="ff907-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-763">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-763">Definition</span></span>

<span data-ttu-id="ff907-764">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-765">函式`Func_spain_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-766">從關鍵字`Keywords_spain_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ff907-767">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-767">Keywords</span></span>

<span data-ttu-id="ff907-768">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-768"></span></span>
|<span data-ttu-id="ff907-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-770">dlno#</span></span>  <br/> <span data-ttu-id="ff907-771">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-771">dl#</span></span>  <br/> <span data-ttu-id="ff907-772">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-772">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-773">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-773">driver licence</span></span>  <br/> <span data-ttu-id="ff907-774">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-774">driver license</span></span>  <br/> <span data-ttu-id="ff907-775">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-775">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-776">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-776">drivers license</span></span>  <br/> <span data-ttu-id="ff907-777">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="ff907-777">driver's licence</span></span>  <br/> <span data-ttu-id="ff907-778">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-778">driver's license</span></span>  <br/> <span data-ttu-id="ff907-779">driving 授權</span><span class="sxs-lookup"><span data-stu-id="ff907-779">driving licence</span></span>  <br/> <span data-ttu-id="ff907-780">主導授權</span><span class="sxs-lookup"><span data-stu-id="ff907-780">driving license</span></span>  <br/> <span data-ttu-id="ff907-781">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-781">driver licence number</span></span>  <br/> <span data-ttu-id="ff907-782">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-782">driver license number</span></span>  <br/> <span data-ttu-id="ff907-783">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-783">drivers licence number</span></span>  <br/> <span data-ttu-id="ff907-784">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-784">drivers license number</span></span>  <br/> <span data-ttu-id="ff907-785">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-785">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-786">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-786">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-787">driving 授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-787">driving licence number</span></span>  <br/> <span data-ttu-id="ff907-788">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-788">driving license number</span></span>  <br/> <span data-ttu-id="ff907-789">主導允許</span><span class="sxs-lookup"><span data-stu-id="ff907-789">driving permit</span></span>  <br/> <span data-ttu-id="ff907-790">主導允許數字</span><span class="sxs-lookup"><span data-stu-id="ff907-790">driving permit number</span></span>  <br/> <span data-ttu-id="ff907-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="ff907-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="ff907-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="ff907-792">permiso conducción</span></span>  <br/> <span data-ttu-id="ff907-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="ff907-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="ff907-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="ff907-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="ff907-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="ff907-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="ff907-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="ff907-796">licencia conducir</span></span>  <br/> <span data-ttu-id="ff907-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="ff907-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="ff907-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="ff907-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="ff907-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="ff907-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="ff907-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="ff907-800">permiso conducir</span></span>  <br/> <span data-ttu-id="ff907-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="ff907-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="ff907-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="ff907-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="ff907-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="ff907-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="ff907-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="ff907-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="ff907-805">格式</span><span class="sxs-lookup"><span data-stu-id="ff907-805">Format</span></span>

<span data-ttu-id="ff907-806">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="ff907-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ff907-807">模式</span><span class="sxs-lookup"><span data-stu-id="ff907-807">Pattern</span></span>

<span data-ttu-id="ff907-808">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="ff907-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="ff907-809">六位數</span><span class="sxs-lookup"><span data-stu-id="ff907-809">Six digits</span></span> 
    
- <span data-ttu-id="ff907-810">連字號</span><span class="sxs-lookup"><span data-stu-id="ff907-810">A hyphen</span></span>
    
- <span data-ttu-id="ff907-811">四位數</span><span class="sxs-lookup"><span data-stu-id="ff907-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ff907-812">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="ff907-812">Checksum</span></span>

<span data-ttu-id="ff907-813">否</span><span class="sxs-lookup"><span data-stu-id="ff907-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="ff907-814">定義</span><span class="sxs-lookup"><span data-stu-id="ff907-814">Definition</span></span>

<span data-ttu-id="ff907-815">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="ff907-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ff907-816">規則運算式`Regex_sweden_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="ff907-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ff907-817">從關鍵字`Keywords_sweden_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="ff907-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="ff907-818">關鍵字</span><span class="sxs-lookup"><span data-stu-id="ff907-818">Keywords</span></span>

<span data-ttu-id="ff907-819">| |</span><span class="sxs-lookup"><span data-stu-id="ff907-819"></span></span>
|<span data-ttu-id="ff907-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="ff907-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="ff907-821">dl#</span><span class="sxs-lookup"><span data-stu-id="ff907-821">dl#</span></span>  <br/> <span data-ttu-id="ff907-822">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-822">driver license</span></span>  <br/> <span data-ttu-id="ff907-823">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-823">driver license number</span></span>  <br/> <span data-ttu-id="ff907-824">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-824">driver licence</span></span>  <br/> <span data-ttu-id="ff907-825">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="ff907-825">drivers lic.</span></span>  <br/> <span data-ttu-id="ff907-826">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-826">drivers license</span></span>  <br/> <span data-ttu-id="ff907-827">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="ff907-827">drivers licence</span></span>  <br/> <span data-ttu-id="ff907-828">駕照</span><span class="sxs-lookup"><span data-stu-id="ff907-828">driver's license</span></span>  <br/> <span data-ttu-id="ff907-829">駕照編號</span><span class="sxs-lookup"><span data-stu-id="ff907-829">driver's license number</span></span>  <br/> <span data-ttu-id="ff907-830">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="ff907-830">driver's licence number</span></span>  <br/> <span data-ttu-id="ff907-831">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="ff907-831">driving license number</span></span>  <br/> <span data-ttu-id="ff907-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="ff907-832">dlno#</span></span>  <br/> <span data-ttu-id="ff907-833">körkort</span><span class="sxs-lookup"><span data-stu-id="ff907-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="ff907-834">英國</span><span class="sxs-lookup"><span data-stu-id="ff907-834">UK</span></span>

<span data-ttu-id="ff907-835">如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="ff907-835">For details, see the section "U.K.</span></span> <span data-ttu-id="ff907-836">驅動程式的授權數目 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="ff907-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff907-837">請參閱</span><span class="sxs-lookup"><span data-stu-id="ff907-837">See also</span></span>

[<span data-ttu-id="ff907-838">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="ff907-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

