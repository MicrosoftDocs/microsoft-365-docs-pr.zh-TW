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
# <a name="eu-drivers-license-number"></a><span data-ttu-id="e9b8f-104">歐盟駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-104">EU Driver's License Number</span></span>

<span data-ttu-id="e9b8f-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟駕駛執照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="e9b8f-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="e9b8f-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="e9b8f-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-108">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-108">Format</span></span>

<span data-ttu-id="e9b8f-109">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-110">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-110">Pattern</span></span>

<span data-ttu-id="e9b8f-111">八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e9b8f-112">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-112">Checksum</span></span>

<span data-ttu-id="e9b8f-113">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-114">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-114">Definition</span></span>

<span data-ttu-id="e9b8f-115">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-116">規則運算式`Regex_austria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-117">從關鍵字`Keywords_austria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="e9b8f-118">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-118">Keywords</span></span>

<span data-ttu-id="e9b8f-119">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-119"></span></span>
|<span data-ttu-id="e9b8f-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-121">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-121">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-122">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-122">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-123">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-123">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-124">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-124">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-125">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-125">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-126">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-126">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-127">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-127">driver's licence</span></span>  <br/> <span data-ttu-id="e9b8f-128">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-128">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-129">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-129">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-130">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="e9b8f-131">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-131">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-132">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="e9b8f-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="e9b8f-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="e9b8f-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="e9b8f-135">比利時</span><span class="sxs-lookup"><span data-stu-id="e9b8f-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-136">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-136">Format</span></span>

<span data-ttu-id="e9b8f-137">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-138">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-138">Pattern</span></span>

<span data-ttu-id="e9b8f-139">10 位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e9b8f-140">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-140">Checksum</span></span>

<span data-ttu-id="e9b8f-141">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-142">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-142">Definition</span></span>

<span data-ttu-id="e9b8f-143">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-144">規則運算式`Regex_belgium_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-145">從關鍵字`Keywords_belgium_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="e9b8f-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-146">Keywords</span></span>

<span data-ttu-id="e9b8f-147">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-147"></span></span>
|<span data-ttu-id="e9b8f-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-149">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-149">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-150">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-150">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-151">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-151">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-152">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-152">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-153">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-153">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-154">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-154">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-155">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-155">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-156">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-156">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-157">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-157">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-158">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-158">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-159">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="e9b8f-160">rijbewijs</span></span>  <br/> <span data-ttu-id="e9b8f-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="e9b8f-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="e9b8f-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="e9b8f-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="e9b8f-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="e9b8f-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="e9b8f-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="e9b8f-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="e9b8f-165">führerschein 編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="e9b8f-166">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="e9b8f-167">fuehrerschein 編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="e9b8f-168">保加利亞</span><span class="sxs-lookup"><span data-stu-id="e9b8f-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-169">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-169">Format</span></span>

<span data-ttu-id="e9b8f-170">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-171">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-171">Pattern</span></span>

<span data-ttu-id="e9b8f-172">九位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e9b8f-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-173">Checksum</span></span>

<span data-ttu-id="e9b8f-174">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-175">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-175">Definition</span></span>

<span data-ttu-id="e9b8f-176">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-177">規則運算式`Regex_bulgaria_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-178">從關鍵字`Keywords_bulgaria_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="e9b8f-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-179">Keywords</span></span>

<span data-ttu-id="e9b8f-180">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-180"></span></span>
|<span data-ttu-id="e9b8f-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-182">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-182">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-183">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-183">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-184">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-184">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-185">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-185">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-186">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-186">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-187">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-187">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-188">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-188">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-189">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-189">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-190">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-190">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-191">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-191">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-192">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-192">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-193">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-194">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС</span><span class="sxs-lookup"><span data-stu-id="e9b8f-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="e9b8f-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="e9b8f-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="e9b8f-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="e9b8f-196">сумпс</span></span>  <br/> <span data-ttu-id="e9b8f-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="e9b8f-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="e9b8f-198">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="e9b8f-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-199">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-199">Format</span></span>

<span data-ttu-id="e9b8f-200">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-201">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-201">Pattern</span></span>

<span data-ttu-id="e9b8f-202">八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e9b8f-203">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-203">Checksum</span></span>

<span data-ttu-id="e9b8f-204">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-205">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-205">Definition</span></span>

<span data-ttu-id="e9b8f-206">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-207">規則運算式`Regex_croatia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-208">從關鍵字`Keywords_croatia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="e9b8f-209">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-209">Keywords</span></span>

<span data-ttu-id="e9b8f-210">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-210"></span></span>
|<span data-ttu-id="e9b8f-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-212">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-212">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-213">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-213">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-214">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-214">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-215">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-215">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-216">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-216">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-217">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-217">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-218">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-218">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-219">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-219">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-220">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-220">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-221">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-221">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-222">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-222">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-223">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="e9b8f-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="e9b8f-225">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="e9b8f-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-226">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-226">Format</span></span>

<span data-ttu-id="e9b8f-227">如果沒有空格和分隔符號的 12 位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-228">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-228">Pattern</span></span>

<span data-ttu-id="e9b8f-229">12 位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e9b8f-230">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-230">Checksum</span></span>

<span data-ttu-id="e9b8f-231">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-232">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-232">Definition</span></span>

<span data-ttu-id="e9b8f-233">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-234">規則運算式`Regex_cyprus_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-235">從關鍵字`Keywords_cyprus_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-236">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-236">Keywords</span></span>

<span data-ttu-id="e9b8f-237">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-237"></span></span>
|<span data-ttu-id="e9b8f-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-239">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-239">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-240">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-240">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-241">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-241">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-242">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-242">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-243">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-243">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-244">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-244">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-245">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-245">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-246">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-246">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-247">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-247">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-248">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-248">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-249">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="e9b8f-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="e9b8f-251">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="e9b8f-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-252">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-252">Format</span></span>

<span data-ttu-id="e9b8f-253">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-254">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-254">Pattern</span></span>

<span data-ttu-id="e9b8f-255">八個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="e9b8f-256">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e9b8f-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="e9b8f-257">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="e9b8f-257">A space (optional)</span></span>
    
- <span data-ttu-id="e9b8f-258">六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-259">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-259">Checksum</span></span>

<span data-ttu-id="e9b8f-260">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-261">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-261">Definition</span></span>

<span data-ttu-id="e9b8f-262">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-263">規則運算式`Regex_czech_republic_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-264">從關鍵字`Keywords_czech_republic_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="e9b8f-265">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-265">Keywords</span></span>

<span data-ttu-id="e9b8f-266">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-266"></span></span>
|<span data-ttu-id="e9b8f-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-268">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-268">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-269">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-269">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-270">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-270">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-271">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-271">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-272">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-272">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-273">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-273">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-274">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-274">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-275">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-275">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-276">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-276">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-277">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-277">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-278">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-278">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-279">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-279">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-280">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="e9b8f-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="e9b8f-282">丹麥</span><span class="sxs-lookup"><span data-stu-id="e9b8f-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-283">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-283">Format</span></span>

<span data-ttu-id="e9b8f-284">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-285">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-285">Pattern</span></span>

<span data-ttu-id="e9b8f-286">八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e9b8f-287">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-287">Checksum</span></span>

<span data-ttu-id="e9b8f-288">是</span><span class="sxs-lookup"><span data-stu-id="e9b8f-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-289">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-289">Definition</span></span>

<span data-ttu-id="e9b8f-290">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-291">規則運算式`Regex_denmark_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-292">從關鍵字`Keywords_denmark_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="e9b8f-293">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-293">Keywords</span></span>

<span data-ttu-id="e9b8f-294">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-294"></span></span>
|<span data-ttu-id="e9b8f-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-296">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-296">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-297">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-298">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-298">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-299">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-299">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-300">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-300">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-301">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-302">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-302">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-303">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-303">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-304">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-304">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-305">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-305">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-306">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-306">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-307">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="e9b8f-308">kørekort</span></span>  <br/> <span data-ttu-id="e9b8f-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="e9b8f-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="e9b8f-310">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="e9b8f-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-311">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-311">Format</span></span>

<span data-ttu-id="e9b8f-312">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-313">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-313">Pattern</span></span>

<span data-ttu-id="e9b8f-314">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="e9b8f-315">字母"ET 」 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e9b8f-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="e9b8f-316">六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-317">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-317">Checksum</span></span>

<span data-ttu-id="e9b8f-318">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-319">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-319">Definition</span></span>

<span data-ttu-id="e9b8f-320">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-321">規則運算式`Regex_estonia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-322">從關鍵字`Keywords_estonia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-323">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-323">Keywords</span></span>

<span data-ttu-id="e9b8f-324">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-324"></span></span>
|<span data-ttu-id="e9b8f-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-326">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-326">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-327">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-327">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-328">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-328">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-329">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-329">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-330">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-330">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-331">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-331">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-332">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-332">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-333">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-333">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-334">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-334">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-335">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-335">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-336">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-336">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-337">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="e9b8f-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="e9b8f-339">芬蘭</span><span class="sxs-lookup"><span data-stu-id="e9b8f-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-340">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-340">Format</span></span>

<span data-ttu-id="e9b8f-341">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-342">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-342">Pattern</span></span>

<span data-ttu-id="e9b8f-343">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="e9b8f-344">六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-344">Six digits</span></span> 
    
- <span data-ttu-id="e9b8f-345">連字號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-345">A hyphen</span></span>
    
-  <span data-ttu-id="e9b8f-346">四位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-347">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-347">Checksum</span></span>

<span data-ttu-id="e9b8f-348">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-349">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-349">Definition</span></span>

<span data-ttu-id="e9b8f-350">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-351">規則運算式`Regex_finland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-352">從關鍵字`Keywords_finland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-353">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-353">Keywords</span></span>

<span data-ttu-id="e9b8f-354">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-354"></span></span>
|<span data-ttu-id="e9b8f-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-356">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-356">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-357">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-357">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-358">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-358">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-359">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-359">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-360">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-360">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-361">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-361">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-362">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-362">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-363">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-363">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-364">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-364">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-365">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-365">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-366">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-366">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-367">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="e9b8f-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="e9b8f-369">法國</span><span class="sxs-lookup"><span data-stu-id="e9b8f-369">France</span></span>

<span data-ttu-id="e9b8f-370">如需詳細資訊，請參閱 「 法國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="e9b8f-371">德國</span><span class="sxs-lookup"><span data-stu-id="e9b8f-371">Germany</span></span>

<span data-ttu-id="e9b8f-372">如需詳細資訊，請參閱 「 德國駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="e9b8f-373">希臘</span><span class="sxs-lookup"><span data-stu-id="e9b8f-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-374">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-374">Format</span></span>

<span data-ttu-id="e9b8f-375">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-376">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-376">Pattern</span></span>

 <span data-ttu-id="e9b8f-377">九位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e9b8f-378">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-378">Checksum</span></span>

<span data-ttu-id="e9b8f-379">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-380">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-380">Definition</span></span>

<span data-ttu-id="e9b8f-381">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-382">規則運算式`Regex_greece_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-383">從關鍵字`Keywords_greece_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-384">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-384">Keywords</span></span>

<span data-ttu-id="e9b8f-385">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-385"></span></span>
|<span data-ttu-id="e9b8f-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-387">dlL#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-387">dlL#</span></span>  <br/> <span data-ttu-id="e9b8f-388">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-388">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-389">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-389">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-390">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-390">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-391">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-391">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-392">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-392">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-393">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-393">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-394">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-394">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-395">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-395">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-396">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-396">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-397">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-397">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-398">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="e9b8f-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="e9b8f-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="e9b8f-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="e9b8f-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="e9b8f-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-402">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-402">Format</span></span>

<span data-ttu-id="e9b8f-403">兩個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-404">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-404">Pattern</span></span>

<span data-ttu-id="e9b8f-405">兩個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="e9b8f-406">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e9b8f-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="e9b8f-407">六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-408">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-408">Checksum</span></span>

<span data-ttu-id="e9b8f-409">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-410">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-410">Definition</span></span>

<span data-ttu-id="e9b8f-411">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-412">規則運算式`Regex_hungary_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-413">從關鍵字`Keywords_hungary_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-414">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-414">Keywords</span></span>

<span data-ttu-id="e9b8f-415">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-415"></span></span>
|<span data-ttu-id="e9b8f-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-417">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-417">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-418">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-418">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-419">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-419">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-420">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-420">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-421">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-421">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-422">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-422">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-423">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-423">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-424">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-424">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-425">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-425">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-426">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-426">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-427">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-427">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-428">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="e9b8f-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="e9b8f-430">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="e9b8f-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-431">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-431">Format</span></span>

<span data-ttu-id="e9b8f-432">四個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-433">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-433">Pattern</span></span>

<span data-ttu-id="e9b8f-434">六位數和四個字母：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="e9b8f-435">六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-435">Six digits</span></span>
    
- <span data-ttu-id="e9b8f-436">四個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e9b8f-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-437">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-437">Checksum</span></span>

<span data-ttu-id="e9b8f-438">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-439">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-439">Definition</span></span>

<span data-ttu-id="e9b8f-440">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-441">規則運算式`Regex_ireland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-442">從關鍵字`Keywords_ireland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-443">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-443">Keywords</span></span>

<span data-ttu-id="e9b8f-444">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-444"></span></span>
|<span data-ttu-id="e9b8f-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-446">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-446">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-447">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-447">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-448">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-448">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-449">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-449">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-450">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-450">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-451">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-451">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-452">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-452">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-453">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-453">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-454">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-454">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-455">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-455">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-456">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-456">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-457">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="e9b8f-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="e9b8f-459">義大利</span><span class="sxs-lookup"><span data-stu-id="e9b8f-459">Italy</span></span>

<span data-ttu-id="e9b8f-460">如需詳細資訊，請參閱 「 義大利駕照編號 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="e9b8f-461">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="e9b8f-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-462">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-462">Format</span></span>

<span data-ttu-id="e9b8f-463">三個字母後尾隨六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-464">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-464">Pattern</span></span>

<span data-ttu-id="e9b8f-465">三個字母和六位數：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="e9b8f-466">三個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e9b8f-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="e9b8f-467">六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-468">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-468">Checksum</span></span>

<span data-ttu-id="e9b8f-469">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-470">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-470">Definition</span></span>

<span data-ttu-id="e9b8f-471">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-472">規則運算式`Regex_latvia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-473">從關鍵字`Keywords_latvia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-474">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-474">Keywords</span></span>

<span data-ttu-id="e9b8f-475">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-475"></span></span>
|<span data-ttu-id="e9b8f-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-477">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-477">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-478">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-478">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-479">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-479">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-480">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-480">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-481">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-481">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-482">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-482">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-483">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-483">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-484">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-484">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-485">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-485">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-486">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-486">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-487">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-487">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-488">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="e9b8f-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="e9b8f-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="e9b8f-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-491">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-491">Format</span></span>

<span data-ttu-id="e9b8f-492">不含空格，並讓分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-493">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-493">Pattern</span></span>

 <span data-ttu-id="e9b8f-494">八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e9b8f-495">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-495">Checksum</span></span>

<span data-ttu-id="e9b8f-496">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-497">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-497">Definition</span></span>

<span data-ttu-id="e9b8f-498">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-499">規則運算式`Regex_lithuania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-500">從關鍵字`Keywords_lithuania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-501">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-501">Keywords</span></span>

<span data-ttu-id="e9b8f-502">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-502"></span></span>
|<span data-ttu-id="e9b8f-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-504">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-504">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-505">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-505">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-506">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-506">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-507">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-507">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-508">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-508">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-509">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-509">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-510">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-510">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-511">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-511">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-512">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-512">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-513">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-513">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-514">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-514">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-515">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="e9b8f-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="e9b8f-517">盧森堡</span><span class="sxs-lookup"><span data-stu-id="e9b8f-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-518">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-518">Format</span></span>

<span data-ttu-id="e9b8f-519">六位數，代表不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-520">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-520">Pattern</span></span>

 <span data-ttu-id="e9b8f-521">六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e9b8f-522">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-522">Checksum</span></span>

<span data-ttu-id="e9b8f-523">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-524">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-524">Definition</span></span>

<span data-ttu-id="e9b8f-525">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-526">規則運算式`Regex_luxemburg_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-527">從關鍵字`Keywords_luxemburg_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-528">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-528">Keywords</span></span>

<span data-ttu-id="e9b8f-529">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-529"></span></span>
|<span data-ttu-id="e9b8f-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-531">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-531">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-532">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-532">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-533">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-533">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-534">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-534">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-535">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-535">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-536">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-536">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-537">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-537">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-538">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-538">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-539">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-539">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-540">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-540">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-541">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-541">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-542">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="e9b8f-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="e9b8f-544">馬爾他</span><span class="sxs-lookup"><span data-stu-id="e9b8f-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-545">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-545">Format</span></span>

<span data-ttu-id="e9b8f-546">兩個字元和六位數，代表所指定的型態的組合</span><span class="sxs-lookup"><span data-stu-id="e9b8f-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-547">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-547">Pattern</span></span>

<span data-ttu-id="e9b8f-548">兩個字元和六位數的組合：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="e9b8f-549">兩個字元 （數字或字母、 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e9b8f-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="e9b8f-550">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="e9b8f-550">A space (optional)</span></span>
    
- <span data-ttu-id="e9b8f-551">三位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-551">Three digits</span></span>
    
- <span data-ttu-id="e9b8f-552">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="e9b8f-552">A space (optional)</span></span>
    
- <span data-ttu-id="e9b8f-553">三位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-554">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-554">Checksum</span></span>

<span data-ttu-id="e9b8f-555">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-556">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-556">Definition</span></span>

<span data-ttu-id="e9b8f-557">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-558">規則運算式`Regex_malta_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-559">從關鍵字`Keywords_malta_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-560">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-560">Keywords</span></span>

<span data-ttu-id="e9b8f-561">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-561"></span></span>
|<span data-ttu-id="e9b8f-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-563">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-563">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-564">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-564">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-565">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-565">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-566">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-566">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-567">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-567">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-568">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-568">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-569">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-569">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-570">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-570">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-571">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-571">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-572">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-572">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-573">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-573">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-574">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-575">liċenzja 塔司 sewqan</span><span class="sxs-lookup"><span data-stu-id="e9b8f-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="e9b8f-576">荷蘭</span><span class="sxs-lookup"><span data-stu-id="e9b8f-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-577">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-577">Format</span></span>

<span data-ttu-id="e9b8f-578">如果沒有空格和分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-579">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-579">Pattern</span></span>

<span data-ttu-id="e9b8f-580">10 位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e9b8f-581">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-581">Checksum</span></span>

<span data-ttu-id="e9b8f-582">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-583">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-583">Definition</span></span>

<span data-ttu-id="e9b8f-584">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-585">規則運算式`Regex_netherlands_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-586">從關鍵字`Keywords_netherlands_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-587">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-587">Keywords</span></span>

<span data-ttu-id="e9b8f-588">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-588"></span></span>
|<span data-ttu-id="e9b8f-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-590">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-590">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-591">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-591">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-592">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-592">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-593">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-593">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-594">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-594">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-595">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-595">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-596">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-596">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-597">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-597">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-598">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-598">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-599">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-599">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-600">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-600">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-601">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="e9b8f-602">permis de conduire</span></span>  <br/> <span data-ttu-id="e9b8f-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="e9b8f-603">rijbewijs</span></span>  <br/> <span data-ttu-id="e9b8f-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="e9b8f-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="e9b8f-605">波蘭</span><span class="sxs-lookup"><span data-stu-id="e9b8f-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-606">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-606">Format</span></span>

<span data-ttu-id="e9b8f-607">14 位數包含正斜線，2</span><span class="sxs-lookup"><span data-stu-id="e9b8f-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-608">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-608">Pattern</span></span>

<span data-ttu-id="e9b8f-609">14 位數和 2 的正斜線：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="e9b8f-610">五位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-610">Five digits</span></span> 
    
- <span data-ttu-id="e9b8f-611">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="e9b8f-611">A forward slash</span></span>
    
- <span data-ttu-id="e9b8f-612">兩位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-612">Two digits</span></span>
    
- <span data-ttu-id="e9b8f-613">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="e9b8f-613">A forward slash</span></span>
    
- <span data-ttu-id="e9b8f-614">七位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-615">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-615">Checksum</span></span>

<span data-ttu-id="e9b8f-616">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-617">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-617">Definition</span></span>

<span data-ttu-id="e9b8f-618">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-619">規則運算式`Regex_poland_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-620">從關鍵字`Keywords_poland_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-621">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-621">Keywords</span></span>

<span data-ttu-id="e9b8f-622">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-622"></span></span>
|<span data-ttu-id="e9b8f-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-624">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-624">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-625">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-625">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-626">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-626">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-627">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-627">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-628">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-628">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-629">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-629">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-630">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-630">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-631">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-631">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-632">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-632">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-633">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-633">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-634">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-634">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-635">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="e9b8f-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="e9b8f-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="e9b8f-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-638">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-638">Format</span></span>

<span data-ttu-id="e9b8f-639">兩個字母後尾隨七個的數字中指定的型態</span><span class="sxs-lookup"><span data-stu-id="e9b8f-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-640">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-640">Pattern</span></span>

<span data-ttu-id="e9b8f-641">兩個字母後尾隨七個具有特殊字元的數字：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="e9b8f-642">兩個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e9b8f-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="e9b8f-643">連字號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-643">A hyphen</span></span>
    
- <span data-ttu-id="e9b8f-644">六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-644">Six digits</span></span>
    
- <span data-ttu-id="e9b8f-645">一個空格</span><span class="sxs-lookup"><span data-stu-id="e9b8f-645">A space</span></span>
    
- <span data-ttu-id="e9b8f-646">一位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-647">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-647">Checksum</span></span>

<span data-ttu-id="e9b8f-648">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-649">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-649">Definition</span></span>

<span data-ttu-id="e9b8f-650">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-651">規則運算式`Regex_portugal_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-652">從關鍵字`Keywords_portugal_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-653">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-653">Keywords</span></span>

<span data-ttu-id="e9b8f-654">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-654"></span></span>
|<span data-ttu-id="e9b8f-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-656">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-656">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-657">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-657">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-658">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-658">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-659">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-659">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-660">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-660">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-661">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-661">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-662">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-662">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-663">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-663">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-664">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-664">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-665">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-665">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-666">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-666">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-667">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="e9b8f-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="e9b8f-669">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="e9b8f-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-670">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-670">Format</span></span>

<span data-ttu-id="e9b8f-671">一個字元尾隨八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-672">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-672">Pattern</span></span>

<span data-ttu-id="e9b8f-673">尾隨八位數的一個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="e9b8f-674">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="e9b8f-675">八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-676">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-676">Checksum</span></span>

<span data-ttu-id="e9b8f-677">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-678">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-678">Definition</span></span>

<span data-ttu-id="e9b8f-679">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-680">規則運算式`Regex_romania_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-681">從關鍵字`Keywords_romania_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-682">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-682">Keywords</span></span>

<span data-ttu-id="e9b8f-683">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-683"></span></span>
|<span data-ttu-id="e9b8f-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-685">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-685">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-686">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-686">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-687">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-687">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-688">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-688">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-689">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-689">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-690">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-690">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-691">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-691">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-692">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-692">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-693">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-693">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-694">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-694">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-695">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-695">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-696">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="e9b8f-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="e9b8f-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="e9b8f-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-699">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-699">Format</span></span>

<span data-ttu-id="e9b8f-700">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-701">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-701">Pattern</span></span>

<span data-ttu-id="e9b8f-702">一個字元尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="e9b8f-703">一個字母 （不區分大小寫） 或數字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="e9b8f-704">七位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-705">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-705">Checksum</span></span>

<span data-ttu-id="e9b8f-706">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-707">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-707">Definition</span></span>

<span data-ttu-id="e9b8f-708">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-709">規則運算式`Regex_slovakia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-710">從關鍵字`Keywords_slovakia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-711">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-711">Keywords</span></span>

<span data-ttu-id="e9b8f-712">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-712"></span></span>
|<span data-ttu-id="e9b8f-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-714">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-714">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-715">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-715">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-716">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-716">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-717">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-717">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-718">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-718">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-719">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-719">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-720">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-720">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-721">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-721">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-722">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-722">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-723">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-723">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-724">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-724">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-725">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="e9b8f-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="e9b8f-727">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="e9b8f-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-728">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-728">Format</span></span>

<span data-ttu-id="e9b8f-729">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-730">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-730">Pattern</span></span>

<span data-ttu-id="e9b8f-731">九位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e9b8f-732">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-732">Checksum</span></span>

<span data-ttu-id="e9b8f-733">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-734">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-734">Definition</span></span>

<span data-ttu-id="e9b8f-735">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-736">規則運算式`Regex_slovenia_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-737">從關鍵字`Keywords_slovenia_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-738">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-738">Keywords</span></span>

<span data-ttu-id="e9b8f-739">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-739"></span></span>
|<span data-ttu-id="e9b8f-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-741">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-741">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-742">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-742">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-743">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-743">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-744">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-744">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-745">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-745">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-746">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-746">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-747">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-747">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-748">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-748">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-749">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-749">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-750">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-750">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-751">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-751">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-752">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="e9b8f-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="e9b8f-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="e9b8f-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-755">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-755">Format</span></span>

<span data-ttu-id="e9b8f-756">後面接著一個字元的八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-757">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-757">Pattern</span></span>

<span data-ttu-id="e9b8f-758">後面接著一個字元的八位數：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="e9b8f-759">八位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-759">Eight digits</span></span> 
    
- <span data-ttu-id="e9b8f-760">一個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e9b8f-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-761">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-761">Checksum</span></span>

<span data-ttu-id="e9b8f-762">是</span><span class="sxs-lookup"><span data-stu-id="e9b8f-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-763">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-763">Definition</span></span>

<span data-ttu-id="e9b8f-764">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-765">函式`Func_spain_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-766">從關鍵字`Keywords_spain_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-767">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-767">Keywords</span></span>

<span data-ttu-id="e9b8f-768">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-768"></span></span>
|<span data-ttu-id="e9b8f-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-770">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-771">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-771">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-772">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-772">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-773">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-773">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-774">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-774">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-775">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-775">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-776">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-776">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-777">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-777">driver's licence</span></span>  <br/> <span data-ttu-id="e9b8f-778">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-778">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-779">driving 授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-779">driving licence</span></span>  <br/> <span data-ttu-id="e9b8f-780">主導授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-780">driving license</span></span>  <br/> <span data-ttu-id="e9b8f-781">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-781">driver licence number</span></span>  <br/> <span data-ttu-id="e9b8f-782">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-782">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-783">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-783">drivers licence number</span></span>  <br/> <span data-ttu-id="e9b8f-784">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-784">drivers license number</span></span>  <br/> <span data-ttu-id="e9b8f-785">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-785">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-786">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-786">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-787">driving 授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-787">driving licence number</span></span>  <br/> <span data-ttu-id="e9b8f-788">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-788">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-789">主導允許</span><span class="sxs-lookup"><span data-stu-id="e9b8f-789">driving permit</span></span>  <br/> <span data-ttu-id="e9b8f-790">主導允許數字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-790">driving permit number</span></span>  <br/> <span data-ttu-id="e9b8f-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="e9b8f-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="e9b8f-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="e9b8f-792">permiso conducción</span></span>  <br/> <span data-ttu-id="e9b8f-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="e9b8f-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="e9b8f-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="e9b8f-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="e9b8f-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="e9b8f-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="e9b8f-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="e9b8f-796">licencia conducir</span></span>  <br/> <span data-ttu-id="e9b8f-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="e9b8f-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="e9b8f-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="e9b8f-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="e9b8f-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="e9b8f-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="e9b8f-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="e9b8f-800">permiso conducir</span></span>  <br/> <span data-ttu-id="e9b8f-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="e9b8f-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="e9b8f-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="e9b8f-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="e9b8f-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="e9b8f-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="e9b8f-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="e9b8f-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="e9b8f-805">格式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-805">Format</span></span>

<span data-ttu-id="e9b8f-806">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e9b8f-807">模式</span><span class="sxs-lookup"><span data-stu-id="e9b8f-807">Pattern</span></span>

<span data-ttu-id="e9b8f-808">10 位數包含連字號：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="e9b8f-809">六位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-809">Six digits</span></span> 
    
- <span data-ttu-id="e9b8f-810">連字號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-810">A hyphen</span></span>
    
- <span data-ttu-id="e9b8f-811">四位數</span><span class="sxs-lookup"><span data-stu-id="e9b8f-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e9b8f-812">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-812">Checksum</span></span>

<span data-ttu-id="e9b8f-813">否</span><span class="sxs-lookup"><span data-stu-id="e9b8f-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e9b8f-814">定義</span><span class="sxs-lookup"><span data-stu-id="e9b8f-814">Definition</span></span>

<span data-ttu-id="e9b8f-815">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e9b8f-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e9b8f-816">規則運算式`Regex_sweden_eu_driver's_license_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e9b8f-817">從關鍵字`Keywords_sweden_eu_driver's_license_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="e9b8f-818">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e9b8f-818">Keywords</span></span>

<span data-ttu-id="e9b8f-819">| |</span><span class="sxs-lookup"><span data-stu-id="e9b8f-819"></span></span>
|<span data-ttu-id="e9b8f-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="e9b8f-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e9b8f-821">dl#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-821">dl#</span></span>  <br/> <span data-ttu-id="e9b8f-822">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-822">driver license</span></span>  <br/> <span data-ttu-id="e9b8f-823">驅動程式授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-823">driver license number</span></span>  <br/> <span data-ttu-id="e9b8f-824">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-824">driver licence</span></span>  <br/> <span data-ttu-id="e9b8f-825">驅動程式 lic。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-825">drivers lic.</span></span>  <br/> <span data-ttu-id="e9b8f-826">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-826">drivers license</span></span>  <br/> <span data-ttu-id="e9b8f-827">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="e9b8f-827">drivers licence</span></span>  <br/> <span data-ttu-id="e9b8f-828">駕照</span><span class="sxs-lookup"><span data-stu-id="e9b8f-828">driver's license</span></span>  <br/> <span data-ttu-id="e9b8f-829">駕照編號</span><span class="sxs-lookup"><span data-stu-id="e9b8f-829">driver's license number</span></span>  <br/> <span data-ttu-id="e9b8f-830">驅動程式的授權數目</span><span class="sxs-lookup"><span data-stu-id="e9b8f-830">driver's licence number</span></span>  <br/> <span data-ttu-id="e9b8f-831">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-831">driving license number</span></span>  <br/> <span data-ttu-id="e9b8f-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="e9b8f-832">dlno#</span></span>  <br/> <span data-ttu-id="e9b8f-833">körkort</span><span class="sxs-lookup"><span data-stu-id="e9b8f-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="e9b8f-834">英國</span><span class="sxs-lookup"><span data-stu-id="e9b8f-834">UK</span></span>

<span data-ttu-id="e9b8f-835">如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="e9b8f-835">For details, see the section "U.K.</span></span> <span data-ttu-id="e9b8f-836">驅動程式的授權數目 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e9b8f-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e9b8f-837">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e9b8f-837">See also</span></span>

[<span data-ttu-id="e9b8f-838">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="e9b8f-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

