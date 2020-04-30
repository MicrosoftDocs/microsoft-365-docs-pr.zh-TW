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
# <a name="eu-passport-number"></a><span data-ttu-id="23073-104">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-104">EU Passport Number</span></span>

<span data-ttu-id="23073-105">本主題說明資料遺失防護（DLP）原則在偵測到歐盟護照號碼機密資訊類型時，會尋找什麼。</span><span class="sxs-lookup"><span data-stu-id="23073-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="23073-106">這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。</span><span class="sxs-lookup"><span data-stu-id="23073-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="23073-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="23073-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="23073-108">格式</span><span class="sxs-lookup"><span data-stu-id="23073-108">Format</span></span>

<span data-ttu-id="23073-109">一個字母后接一個選擇性的空格和七位數</span><span class="sxs-lookup"><span data-stu-id="23073-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-110">模式</span><span class="sxs-lookup"><span data-stu-id="23073-110">Pattern</span></span>

<span data-ttu-id="23073-111">一個字母、七位數和一個空格的組合：</span><span class="sxs-lookup"><span data-stu-id="23073-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="23073-112">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="23073-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="23073-113">一個空格（選用）</span><span class="sxs-lookup"><span data-stu-id="23073-113">One space (optional)</span></span>
    
- <span data-ttu-id="23073-114">七位數</span><span class="sxs-lookup"><span data-stu-id="23073-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="23073-115">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-115">Checksum</span></span>

<span data-ttu-id="23073-116">不適用</span><span class="sxs-lookup"><span data-stu-id="23073-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-117">定義</span><span class="sxs-lookup"><span data-stu-id="23073-117">Definition</span></span>

<span data-ttu-id="23073-118">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-119">正則運算式`Regex_austria_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-120">找到來自`Keywords_austria_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-121">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-121">Keywords</span></span>

<span data-ttu-id="23073-122">| |</span><span class="sxs-lookup"><span data-stu-id="23073-122">| |</span></span>
|<span data-ttu-id="23073-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-124">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-124">passport number</span></span>  <br/> <span data-ttu-id="23073-125">奧地利護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-125">austrian passport number</span></span>  <br/> <span data-ttu-id="23073-126">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-126">passport no</span></span>  <br/> <span data-ttu-id="23073-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="23073-127">reisepass</span></span>  <br/> <span data-ttu-id="23073-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="23073-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="23073-129">比利時</span><span class="sxs-lookup"><span data-stu-id="23073-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="23073-130">格式</span><span class="sxs-lookup"><span data-stu-id="23073-130">Format</span></span>

<span data-ttu-id="23073-131">兩個字母后接六位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-132">模式</span><span class="sxs-lookup"><span data-stu-id="23073-132">Pattern</span></span>

<span data-ttu-id="23073-133">兩個字母后接六位數</span><span class="sxs-lookup"><span data-stu-id="23073-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="23073-134">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-134">Checksum</span></span>

<span data-ttu-id="23073-135">不適用</span><span class="sxs-lookup"><span data-stu-id="23073-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-136">定義</span><span class="sxs-lookup"><span data-stu-id="23073-136">Definition</span></span>

<span data-ttu-id="23073-137">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-138">正則運算式`Regex_belgium_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-139">找到來自`Keywords_belgium_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-140">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-140">Keywords</span></span>

<span data-ttu-id="23073-141">| |</span><span class="sxs-lookup"><span data-stu-id="23073-141">| |</span></span>
|<span data-ttu-id="23073-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-143">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-143">passport number</span></span>  <br/> <span data-ttu-id="23073-144">比利時護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-144">belgian passport number</span></span>  <br/> <span data-ttu-id="23073-145">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-145">passport no</span></span>  <br/> <span data-ttu-id="23073-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="23073-146">paspoort</span></span>  <br/> <span data-ttu-id="23073-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="23073-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="23073-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="23073-148">reisepass kein</span></span>  <br/> <span data-ttu-id="23073-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="23073-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="23073-150">保加利亞</span><span class="sxs-lookup"><span data-stu-id="23073-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="23073-151">格式</span><span class="sxs-lookup"><span data-stu-id="23073-151">Format</span></span>

<span data-ttu-id="23073-152">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-153">模式</span><span class="sxs-lookup"><span data-stu-id="23073-153">Pattern</span></span>

 <span data-ttu-id="23073-154">九位數</span><span class="sxs-lookup"><span data-stu-id="23073-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="23073-155">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-155">Checksum</span></span>

<span data-ttu-id="23073-156">否</span><span class="sxs-lookup"><span data-stu-id="23073-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-157">定義</span><span class="sxs-lookup"><span data-stu-id="23073-157">Definition</span></span>

<span data-ttu-id="23073-158">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-159">正則運算式`Regex_bulgaria_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-160">找到來自`Keywords_bulgaria_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-161">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-161">Keywords</span></span>

<span data-ttu-id="23073-162">| |</span><span class="sxs-lookup"><span data-stu-id="23073-162">| |</span></span>
|<span data-ttu-id="23073-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-164">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-164">passport number</span></span>  <br/> <span data-ttu-id="23073-165">保加利亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="23073-166">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-166">passport no</span></span>  <br/> <span data-ttu-id="23073-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="23073-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="23073-168">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="23073-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="23073-169">格式</span><span class="sxs-lookup"><span data-stu-id="23073-169">Format</span></span>

<span data-ttu-id="23073-170">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-171">模式</span><span class="sxs-lookup"><span data-stu-id="23073-171">Pattern</span></span>

 <span data-ttu-id="23073-172">九位數</span><span class="sxs-lookup"><span data-stu-id="23073-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="23073-173">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-173">Checksum</span></span>

<span data-ttu-id="23073-174">否</span><span class="sxs-lookup"><span data-stu-id="23073-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-175">定義</span><span class="sxs-lookup"><span data-stu-id="23073-175">Definition</span></span>

<span data-ttu-id="23073-176">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-177">正則運算式`Regex_croatia_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-178">找到來自`Keywords_croatia_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-179">Keywords</span></span>

<span data-ttu-id="23073-180">| |</span><span class="sxs-lookup"><span data-stu-id="23073-180">| |</span></span>
|<span data-ttu-id="23073-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-182">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-182">passport number</span></span>  <br/> <span data-ttu-id="23073-183">克羅地亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-183">croatian passport number</span></span>  <br/> <span data-ttu-id="23073-184">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-184">passport no</span></span>  <br/> <span data-ttu-id="23073-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="23073-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="23073-186">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="23073-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="23073-187">格式</span><span class="sxs-lookup"><span data-stu-id="23073-187">Format</span></span>

<span data-ttu-id="23073-188">一個字母后接6-8 位數，沒有空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-189">模式</span><span class="sxs-lookup"><span data-stu-id="23073-189">Pattern</span></span>

<span data-ttu-id="23073-190">一個字母后接六個到八位數</span><span class="sxs-lookup"><span data-stu-id="23073-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="23073-191">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-191">Checksum</span></span>

<span data-ttu-id="23073-192">否</span><span class="sxs-lookup"><span data-stu-id="23073-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-193">定義</span><span class="sxs-lookup"><span data-stu-id="23073-193">Definition</span></span>

<span data-ttu-id="23073-194">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-195">正則運算式`Regex_cyprus_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-196">找到來自`Keywords_cyprus_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-197">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-197">Keywords</span></span>

<span data-ttu-id="23073-198">| |</span><span class="sxs-lookup"><span data-stu-id="23073-198">| |</span></span>
|<span data-ttu-id="23073-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-200">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-200">passport number</span></span>  <br/> <span data-ttu-id="23073-201">賽普勒斯護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="23073-202">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-202">passport no</span></span>  <br/> <span data-ttu-id="23073-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="23073-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="23073-204">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="23073-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="23073-205">格式</span><span class="sxs-lookup"><span data-stu-id="23073-205">Format</span></span>

<span data-ttu-id="23073-206">不含空格或分隔符號的八位數</span><span class="sxs-lookup"><span data-stu-id="23073-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-207">模式</span><span class="sxs-lookup"><span data-stu-id="23073-207">Pattern</span></span>

<span data-ttu-id="23073-208">不含空格或分隔符號的八位數</span><span class="sxs-lookup"><span data-stu-id="23073-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="23073-209">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-209">Checksum</span></span>

<span data-ttu-id="23073-210">否</span><span class="sxs-lookup"><span data-stu-id="23073-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-211">定義</span><span class="sxs-lookup"><span data-stu-id="23073-211">Definition</span></span>

<span data-ttu-id="23073-212">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-213">正則運算式`Regex_czech_republic_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-214">找到來自`Keywords_czech_republic_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-215">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-215">Keywords</span></span>

<span data-ttu-id="23073-216">| |</span><span class="sxs-lookup"><span data-stu-id="23073-216">| |</span></span>
|<span data-ttu-id="23073-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-218">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-218">passport number</span></span>  <br/> <span data-ttu-id="23073-219">捷克護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-219">czech passport number</span></span>  <br/> <span data-ttu-id="23073-220">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-220">passport no</span></span>  <br/> <span data-ttu-id="23073-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="23073-221">cestovní pas</span></span>  <br/> <span data-ttu-id="23073-222">Pas</span><span class="sxs-lookup"><span data-stu-id="23073-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="23073-223">丹麥</span><span class="sxs-lookup"><span data-stu-id="23073-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="23073-224">格式</span><span class="sxs-lookup"><span data-stu-id="23073-224">Format</span></span>

<span data-ttu-id="23073-225">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-226">模式</span><span class="sxs-lookup"><span data-stu-id="23073-226">Pattern</span></span>

 <span data-ttu-id="23073-227">九位數</span><span class="sxs-lookup"><span data-stu-id="23073-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="23073-228">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-228">Checksum</span></span>

<span data-ttu-id="23073-229">否</span><span class="sxs-lookup"><span data-stu-id="23073-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-230">定義</span><span class="sxs-lookup"><span data-stu-id="23073-230">Definition</span></span>

<span data-ttu-id="23073-231">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-232">正則運算式`Regex_denmark_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-233">找到來自`Keywords_denmark_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-234">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-234">Keywords</span></span>

<span data-ttu-id="23073-235">| |</span><span class="sxs-lookup"><span data-stu-id="23073-235">| |</span></span>
|<span data-ttu-id="23073-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-237">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-237">passport number</span></span>  <br/> <span data-ttu-id="23073-238">丹麥文護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-238">danish passport number</span></span>  <br/> <span data-ttu-id="23073-239">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-239">passport no</span></span>  <br/> <span data-ttu-id="23073-240">Pas</span><span class="sxs-lookup"><span data-stu-id="23073-240">pas</span></span>  <br/> <span data-ttu-id="23073-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="23073-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="23073-242">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="23073-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="23073-243">格式</span><span class="sxs-lookup"><span data-stu-id="23073-243">Format</span></span>

<span data-ttu-id="23073-244">一個字母后接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-245">模式</span><span class="sxs-lookup"><span data-stu-id="23073-245">Pattern</span></span>

<span data-ttu-id="23073-246">一個字母后接7位數</span><span class="sxs-lookup"><span data-stu-id="23073-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="23073-247">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-247">Checksum</span></span>

<span data-ttu-id="23073-248">否</span><span class="sxs-lookup"><span data-stu-id="23073-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-249">定義</span><span class="sxs-lookup"><span data-stu-id="23073-249">Definition</span></span>

<span data-ttu-id="23073-250">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-251">正則運算式`Regex_estonia_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-252">找到來自`Keywords_estonia_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-253">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-253">Keywords</span></span>

<span data-ttu-id="23073-254">| |</span><span class="sxs-lookup"><span data-stu-id="23073-254">| |</span></span>
|<span data-ttu-id="23073-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-256">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-256">passport number</span></span>  <br/> <span data-ttu-id="23073-257">愛沙尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-257">estonian passport number</span></span>  <br/> <span data-ttu-id="23073-258">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-258">passport no</span></span>  <br/> <span data-ttu-id="23073-259">eesti kodaniku 傳遞</span><span class="sxs-lookup"><span data-stu-id="23073-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="23073-260">芬蘭</span><span class="sxs-lookup"><span data-stu-id="23073-260">Finland</span></span>

<span data-ttu-id="23073-261">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「芬蘭護照號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="23073-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="23073-262">法國</span><span class="sxs-lookup"><span data-stu-id="23073-262">France</span></span>

<span data-ttu-id="23073-263">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「法國護照號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="23073-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="23073-264">德國</span><span class="sxs-lookup"><span data-stu-id="23073-264">Germany</span></span>

<span data-ttu-id="23073-265">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「德文護照號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="23073-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="23073-266">希臘</span><span class="sxs-lookup"><span data-stu-id="23073-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="23073-267">格式</span><span class="sxs-lookup"><span data-stu-id="23073-267">Format</span></span>

<span data-ttu-id="23073-268">兩個字母后接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-269">模式</span><span class="sxs-lookup"><span data-stu-id="23073-269">Pattern</span></span>

<span data-ttu-id="23073-270">兩個字母后接7位數</span><span class="sxs-lookup"><span data-stu-id="23073-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="23073-271">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-271">Checksum</span></span>

<span data-ttu-id="23073-272">否</span><span class="sxs-lookup"><span data-stu-id="23073-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-273">定義</span><span class="sxs-lookup"><span data-stu-id="23073-273">Definition</span></span>

<span data-ttu-id="23073-274">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-275">正則運算式`Regex_greece_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-276">找到來自`Keywords_greece_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-277">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-277">Keywords</span></span>

<span data-ttu-id="23073-278">| |</span><span class="sxs-lookup"><span data-stu-id="23073-278">| |</span></span>
|<span data-ttu-id="23073-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-280">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-280">passport number</span></span>  <br/> <span data-ttu-id="23073-281">希臘文護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-281">greek passport number</span></span>  <br/> <span data-ttu-id="23073-282">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-282">passport no</span></span>  <br/> <span data-ttu-id="23073-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="23073-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="23073-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="23073-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="23073-285">格式</span><span class="sxs-lookup"><span data-stu-id="23073-285">Format</span></span>

<span data-ttu-id="23073-286">兩個字母后接六個或7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-287">模式</span><span class="sxs-lookup"><span data-stu-id="23073-287">Pattern</span></span>

<span data-ttu-id="23073-288">兩個字母后接六位數或七位數</span><span class="sxs-lookup"><span data-stu-id="23073-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="23073-289">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-289">Checksum</span></span>

<span data-ttu-id="23073-290">否</span><span class="sxs-lookup"><span data-stu-id="23073-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-291">定義</span><span class="sxs-lookup"><span data-stu-id="23073-291">Definition</span></span>

<span data-ttu-id="23073-292">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-293">正則運算式`Regex_hungary_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-294">找到來自`Keywords_hungary_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-295">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-295">Keywords</span></span>

<span data-ttu-id="23073-296">| |</span><span class="sxs-lookup"><span data-stu-id="23073-296">| |</span></span>
|<span data-ttu-id="23073-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-298">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-298">passport number</span></span>  <br/> <span data-ttu-id="23073-299">匈牙利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="23073-300">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-300">passport no</span></span>  <br/> <span data-ttu-id="23073-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="23073-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="23073-302">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="23073-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="23073-303">格式</span><span class="sxs-lookup"><span data-stu-id="23073-303">Format</span></span>

<span data-ttu-id="23073-304">兩個字母或數位後接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-305">模式</span><span class="sxs-lookup"><span data-stu-id="23073-305">Pattern</span></span>

<span data-ttu-id="23073-306">兩個字母或數位後接7位數：</span><span class="sxs-lookup"><span data-stu-id="23073-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="23073-307">兩位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="23073-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="23073-308">七位數</span><span class="sxs-lookup"><span data-stu-id="23073-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="23073-309">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-309">Checksum</span></span>

<span data-ttu-id="23073-310">否</span><span class="sxs-lookup"><span data-stu-id="23073-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-311">定義</span><span class="sxs-lookup"><span data-stu-id="23073-311">Definition</span></span>

<span data-ttu-id="23073-312">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-313">正則運算式`Regex_ireland_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-314">找到來自`Keywords_ireland_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-315">Keywords</span></span>

<span data-ttu-id="23073-316">| |</span><span class="sxs-lookup"><span data-stu-id="23073-316">| |</span></span>
|<span data-ttu-id="23073-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-318">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-318">passport number</span></span>  <br/> <span data-ttu-id="23073-319">愛爾蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-319">irish passport number</span></span>  <br/> <span data-ttu-id="23073-320">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-320">passport no</span></span>  <br/> <span data-ttu-id="23073-321">Pas</span><span class="sxs-lookup"><span data-stu-id="23073-321">pas</span></span>  <br/> <span data-ttu-id="23073-322">護照</span><span class="sxs-lookup"><span data-stu-id="23073-322">passport</span></span>  <br/> <span data-ttu-id="23073-323">passeport</span><span class="sxs-lookup"><span data-stu-id="23073-323">passeport</span></span>  <br/> <span data-ttu-id="23073-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="23073-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="23073-325">義大利</span><span class="sxs-lookup"><span data-stu-id="23073-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="23073-326">格式</span><span class="sxs-lookup"><span data-stu-id="23073-326">Format</span></span>

<span data-ttu-id="23073-327">兩個字母或數位後接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-328">模式</span><span class="sxs-lookup"><span data-stu-id="23073-328">Pattern</span></span>

<span data-ttu-id="23073-329">兩個字母或數位後接7位數：</span><span class="sxs-lookup"><span data-stu-id="23073-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="23073-330">兩位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="23073-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="23073-331">七位數</span><span class="sxs-lookup"><span data-stu-id="23073-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="23073-332">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-332">Checksum</span></span>

<span data-ttu-id="23073-333">不適用</span><span class="sxs-lookup"><span data-stu-id="23073-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-334">定義</span><span class="sxs-lookup"><span data-stu-id="23073-334">Definition</span></span>

<span data-ttu-id="23073-335">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-336">正則運算式`Regex_italy_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-337">找到來自`Keywords_italy_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-338">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-338">Keywords</span></span>

<span data-ttu-id="23073-339">| |</span><span class="sxs-lookup"><span data-stu-id="23073-339">| |</span></span>
|<span data-ttu-id="23073-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-341">義大利護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-341">italian passport number</span></span>  <br/> <span data-ttu-id="23073-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="23073-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="23073-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="23073-343">passaporto</span></span>  <br/> <span data-ttu-id="23073-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="23073-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="23073-345">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-345">passport number</span></span>  <br/> <span data-ttu-id="23073-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="23073-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="23073-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="23073-347">passaporto numero</span></span>  <br/> <span data-ttu-id="23073-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="23073-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="23073-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="23073-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="23073-350">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="23073-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="23073-351">格式</span><span class="sxs-lookup"><span data-stu-id="23073-351">Format</span></span>

<span data-ttu-id="23073-352">兩個字母或數位後接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-353">模式</span><span class="sxs-lookup"><span data-stu-id="23073-353">Pattern</span></span>

<span data-ttu-id="23073-354">兩個字母或數位後接7位數：</span><span class="sxs-lookup"><span data-stu-id="23073-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="23073-355">兩位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="23073-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="23073-356">七位數</span><span class="sxs-lookup"><span data-stu-id="23073-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="23073-357">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-357">Checksum</span></span>

<span data-ttu-id="23073-358">否</span><span class="sxs-lookup"><span data-stu-id="23073-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-359">定義</span><span class="sxs-lookup"><span data-stu-id="23073-359">Definition</span></span>

<span data-ttu-id="23073-360">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-361">正則運算式`Regex_latvia_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-362">找到來自`Keywords_latvia_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-363">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-363">Keywords</span></span>

<span data-ttu-id="23073-364">| |</span><span class="sxs-lookup"><span data-stu-id="23073-364">| |</span></span>
|<span data-ttu-id="23073-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-366">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-366">passport number</span></span>  <br/> <span data-ttu-id="23073-367">拉脫維亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-367">latvian passport number</span></span>  <br/> <span data-ttu-id="23073-368">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-368">passport no</span></span>  <br/> <span data-ttu-id="23073-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="23073-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="23073-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="23073-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="23073-371">格式</span><span class="sxs-lookup"><span data-stu-id="23073-371">Format</span></span>

<span data-ttu-id="23073-372">八位數的數位或字母，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-373">模式</span><span class="sxs-lookup"><span data-stu-id="23073-373">Pattern</span></span>

<span data-ttu-id="23073-374">八位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="23073-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="23073-375">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-375">Checksum</span></span>

<span data-ttu-id="23073-376">不適用</span><span class="sxs-lookup"><span data-stu-id="23073-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-377">定義</span><span class="sxs-lookup"><span data-stu-id="23073-377">Definition</span></span>

<span data-ttu-id="23073-378">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-379">正則運算式`Regex_lithuania_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-380">找到來自`Keywords_lithuania_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-381">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-381">Keywords</span></span>

<span data-ttu-id="23073-382">| |</span><span class="sxs-lookup"><span data-stu-id="23073-382">| |</span></span>
|<span data-ttu-id="23073-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-384">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-384">passport number</span></span>  <br/> <span data-ttu-id="23073-385">lithunian 護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="23073-386">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-386">passport no</span></span>  <br/> <span data-ttu-id="23073-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="23073-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="23073-388">盧森堡</span><span class="sxs-lookup"><span data-stu-id="23073-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="23073-389">格式</span><span class="sxs-lookup"><span data-stu-id="23073-389">Format</span></span>

<span data-ttu-id="23073-390">八位數的數位或字母，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-391">模式</span><span class="sxs-lookup"><span data-stu-id="23073-391">Pattern</span></span>

<span data-ttu-id="23073-392">八位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="23073-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="23073-393">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-393">Checksum</span></span>

<span data-ttu-id="23073-394">否</span><span class="sxs-lookup"><span data-stu-id="23073-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-395">定義</span><span class="sxs-lookup"><span data-stu-id="23073-395">Definition</span></span>

<span data-ttu-id="23073-396">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-397">正則運算式`Regex_nation_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-398">找到來自`Keywords_nation_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-399">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-399">Keywords</span></span>

<span data-ttu-id="23073-400">| |</span><span class="sxs-lookup"><span data-stu-id="23073-400">| |</span></span>
|<span data-ttu-id="23073-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-402">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-402">passport number</span></span>  <br/> <span data-ttu-id="23073-403">拉脫維亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-403">latvian passport number</span></span>  <br/> <span data-ttu-id="23073-404">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-404">passport no</span></span>  <br/> <span data-ttu-id="23073-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="23073-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="23073-406">馬爾他</span><span class="sxs-lookup"><span data-stu-id="23073-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="23073-407">格式</span><span class="sxs-lookup"><span data-stu-id="23073-407">Format</span></span>

<span data-ttu-id="23073-408">七位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-409">模式</span><span class="sxs-lookup"><span data-stu-id="23073-409">Pattern</span></span>

 <span data-ttu-id="23073-410">七位數</span><span class="sxs-lookup"><span data-stu-id="23073-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="23073-411">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-411">Checksum</span></span>

<span data-ttu-id="23073-412">否</span><span class="sxs-lookup"><span data-stu-id="23073-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-413">定義</span><span class="sxs-lookup"><span data-stu-id="23073-413">Definition</span></span>

<span data-ttu-id="23073-414">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-415">正則運算式`Regex_malta_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-416">找到來自`Keywords_malta_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-417">Keywords</span></span>

<span data-ttu-id="23073-418">| |</span><span class="sxs-lookup"><span data-stu-id="23073-418">| |</span></span>
|<span data-ttu-id="23073-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-420">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-420">passport number</span></span>  <br/> <span data-ttu-id="23073-421">馬爾他護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-421">maltese passport number</span></span>  <br/> <span data-ttu-id="23073-422">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-422">passport no</span></span>  <br/> <span data-ttu-id="23073-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="23073-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="23073-424">荷蘭</span><span class="sxs-lookup"><span data-stu-id="23073-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="23073-425">格式</span><span class="sxs-lookup"><span data-stu-id="23073-425">Format</span></span>

<span data-ttu-id="23073-426">不含空格或分隔符號的九個字母或數位</span><span class="sxs-lookup"><span data-stu-id="23073-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-427">模式</span><span class="sxs-lookup"><span data-stu-id="23073-427">Pattern</span></span>

<span data-ttu-id="23073-428">九個字母或數位</span><span class="sxs-lookup"><span data-stu-id="23073-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="23073-429">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-429">Checksum</span></span>

<span data-ttu-id="23073-430">不適用</span><span class="sxs-lookup"><span data-stu-id="23073-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-431">定義</span><span class="sxs-lookup"><span data-stu-id="23073-431">Definition</span></span>

<span data-ttu-id="23073-432">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-433">正則運算式`Regex_netherlands_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-434">找到來自`Keywords_netherlands_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-435">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-435">Keywords</span></span>

<span data-ttu-id="23073-436">| |</span><span class="sxs-lookup"><span data-stu-id="23073-436">| |</span></span>
|<span data-ttu-id="23073-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-438">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-438">dutch passport number</span></span>  <br/> <span data-ttu-id="23073-439">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-439">passport number</span></span>  <br/> <span data-ttu-id="23073-440">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="23073-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="23073-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="23073-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="23073-442">paspoort</span></span>  <br/> <span data-ttu-id="23073-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="23073-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="23073-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="23073-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="23073-445">波蘭</span><span class="sxs-lookup"><span data-stu-id="23073-445">Poland</span></span>

<span data-ttu-id="23073-446">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「波蘭護照號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="23073-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="23073-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="23073-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="23073-448">格式</span><span class="sxs-lookup"><span data-stu-id="23073-448">Format</span></span>

<span data-ttu-id="23073-449">一個字母后接六位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-450">模式</span><span class="sxs-lookup"><span data-stu-id="23073-450">Pattern</span></span>

<span data-ttu-id="23073-451">一個字母后接六位數：</span><span class="sxs-lookup"><span data-stu-id="23073-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="23073-452">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="23073-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="23073-453">六位數</span><span class="sxs-lookup"><span data-stu-id="23073-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="23073-454">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-454">Checksum</span></span>

<span data-ttu-id="23073-455">否</span><span class="sxs-lookup"><span data-stu-id="23073-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-456">定義</span><span class="sxs-lookup"><span data-stu-id="23073-456">Definition</span></span>

<span data-ttu-id="23073-457">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-458">正則運算式`Regex_portugal_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-459">找到來自`Keywords_portugal_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-460">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-460">Keywords</span></span>

<span data-ttu-id="23073-461">| |</span><span class="sxs-lookup"><span data-stu-id="23073-461">| |</span></span>
|<span data-ttu-id="23073-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-463">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-463">passport number</span></span>  <br/> <span data-ttu-id="23073-464">葡萄牙文護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="23073-465">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-465">passport no</span></span>  <br/> <span data-ttu-id="23073-466">número 執行 passaporte</span><span class="sxs-lookup"><span data-stu-id="23073-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="23073-467">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="23073-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="23073-468">格式</span><span class="sxs-lookup"><span data-stu-id="23073-468">Format</span></span>

<span data-ttu-id="23073-469">8或9位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-470">模式</span><span class="sxs-lookup"><span data-stu-id="23073-470">Pattern</span></span>

<span data-ttu-id="23073-471">8或9位數</span><span class="sxs-lookup"><span data-stu-id="23073-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="23073-472">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-472">Checksum</span></span>

<span data-ttu-id="23073-473">否</span><span class="sxs-lookup"><span data-stu-id="23073-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-474">定義</span><span class="sxs-lookup"><span data-stu-id="23073-474">Definition</span></span>

<span data-ttu-id="23073-475">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-476">正則運算式`Regex_romania_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-477">找到來自`Keywords_romania_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-478">Keywords</span></span>

<span data-ttu-id="23073-479">| |</span><span class="sxs-lookup"><span data-stu-id="23073-479">| |</span></span>
|<span data-ttu-id="23073-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-481">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-481">passport number</span></span>  <br/> <span data-ttu-id="23073-482">羅馬尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-482">romanian passport number</span></span>  <br/> <span data-ttu-id="23073-483">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-483">passport no</span></span>  <br/> <span data-ttu-id="23073-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="23073-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="23073-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="23073-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="23073-486">格式</span><span class="sxs-lookup"><span data-stu-id="23073-486">Format</span></span>

<span data-ttu-id="23073-487">一個數位或字母后接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-488">模式</span><span class="sxs-lookup"><span data-stu-id="23073-488">Pattern</span></span>

<span data-ttu-id="23073-489">一個數位或字母（不區分大小寫）後接7位數</span><span class="sxs-lookup"><span data-stu-id="23073-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="23073-490">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-490">Checksum</span></span>

<span data-ttu-id="23073-491">否</span><span class="sxs-lookup"><span data-stu-id="23073-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-492">定義</span><span class="sxs-lookup"><span data-stu-id="23073-492">Definition</span></span>

<span data-ttu-id="23073-493">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-494">正則運算式`Regex_slovakia_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-495">找到來自`Keywords_slovakia_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-496">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-496">Keywords</span></span>

<span data-ttu-id="23073-497">| |</span><span class="sxs-lookup"><span data-stu-id="23073-497">| |</span></span>
|<span data-ttu-id="23073-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-499">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-499">passport number</span></span>  <br/> <span data-ttu-id="23073-500">斯洛伐克護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="23073-501">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-501">passport no</span></span>  <br/> <span data-ttu-id="23073-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="23073-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="23073-503">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="23073-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="23073-504">格式</span><span class="sxs-lookup"><span data-stu-id="23073-504">Format</span></span>

<span data-ttu-id="23073-505">兩個字母后接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-506">模式</span><span class="sxs-lookup"><span data-stu-id="23073-506">Pattern</span></span>

<span data-ttu-id="23073-507">兩個字母后接7位數：</span><span class="sxs-lookup"><span data-stu-id="23073-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="23073-508">字母 "P"</span><span class="sxs-lookup"><span data-stu-id="23073-508">The letter "P"</span></span>
    
- <span data-ttu-id="23073-509">單一大寫字母</span><span class="sxs-lookup"><span data-stu-id="23073-509">One uppercase letter</span></span>
    
- <span data-ttu-id="23073-510">七位數</span><span class="sxs-lookup"><span data-stu-id="23073-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="23073-511">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-511">Checksum</span></span>

<span data-ttu-id="23073-512">否</span><span class="sxs-lookup"><span data-stu-id="23073-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-513">定義</span><span class="sxs-lookup"><span data-stu-id="23073-513">Definition</span></span>

<span data-ttu-id="23073-514">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-515">正則運算式`Regex_slovenia_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-516">找到來自`Keywords_slovenia_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-517">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-517">Keywords</span></span>

<span data-ttu-id="23073-518">| |</span><span class="sxs-lookup"><span data-stu-id="23073-518">| |</span></span>
|<span data-ttu-id="23073-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-520">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-520">passport number</span></span>  <br/> <span data-ttu-id="23073-521">斯洛維尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="23073-522">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-522">passport no</span></span>  <br/> <span data-ttu-id="23073-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="23073-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="23073-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="23073-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="23073-525">格式</span><span class="sxs-lookup"><span data-stu-id="23073-525">Format</span></span>

<span data-ttu-id="23073-526">8或9個字元組合的字母和數位，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="23073-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="23073-527">模式</span><span class="sxs-lookup"><span data-stu-id="23073-527">Pattern</span></span>

<span data-ttu-id="23073-528">字母和數位的8或9個字元組合：</span><span class="sxs-lookup"><span data-stu-id="23073-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="23073-529">兩位數或字母</span><span class="sxs-lookup"><span data-stu-id="23073-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="23073-530">一個數位或字母（選用）</span><span class="sxs-lookup"><span data-stu-id="23073-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="23073-531">六位數</span><span class="sxs-lookup"><span data-stu-id="23073-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="23073-532">校驗</span><span class="sxs-lookup"><span data-stu-id="23073-532">Checksum</span></span>

<span data-ttu-id="23073-533">不適用</span><span class="sxs-lookup"><span data-stu-id="23073-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="23073-534">定義</span><span class="sxs-lookup"><span data-stu-id="23073-534">Definition</span></span>

<span data-ttu-id="23073-535">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="23073-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="23073-536">正則運算式`Regex_spain_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="23073-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="23073-537">找到來自`Keywords_spain_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="23073-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="23073-538">關鍵字</span><span class="sxs-lookup"><span data-stu-id="23073-538">Keywords</span></span>

<span data-ttu-id="23073-539">| |</span><span class="sxs-lookup"><span data-stu-id="23073-539">| |</span></span>
|<span data-ttu-id="23073-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="23073-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="23073-541">護照</span><span class="sxs-lookup"><span data-stu-id="23073-541">passport</span></span>  <br/> <span data-ttu-id="23073-542">西班牙護照</span><span class="sxs-lookup"><span data-stu-id="23073-542">spain passport</span></span>  <br/> <span data-ttu-id="23073-543">護照手冊</span><span class="sxs-lookup"><span data-stu-id="23073-543">passport book</span></span>  <br/> <span data-ttu-id="23073-544">護照號碼</span><span class="sxs-lookup"><span data-stu-id="23073-544">passport number</span></span>  <br/> <span data-ttu-id="23073-545">護照否</span><span class="sxs-lookup"><span data-stu-id="23073-545">passport no</span></span>  <br/> <span data-ttu-id="23073-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="23073-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="23073-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="23073-547">número pasaporte</span></span>  <br/> <span data-ttu-id="23073-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="23073-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="23073-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="23073-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="23073-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="23073-550">Sweden</span></span>

<span data-ttu-id="23073-551">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「瑞典護照號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="23073-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="23073-552">英國</span><span class="sxs-lookup"><span data-stu-id="23073-552">UK</span></span>

<span data-ttu-id="23073-553">如需詳細資訊，請參閱 section/英國</span><span class="sxs-lookup"><span data-stu-id="23073-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="23073-554">「[機密資訊類型](what-the-sensitive-information-types-look-for.md)」所尋找的「護照號碼」。</span><span class="sxs-lookup"><span data-stu-id="23073-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="23073-555">另請參閱</span><span class="sxs-lookup"><span data-stu-id="23073-555">See also</span></span>

[<span data-ttu-id="23073-556">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="23073-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

