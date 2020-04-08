---
title: 歐盟護照號碼
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題說明資料遺失防護（DLP）原則在偵測到歐盟護照號碼機密資訊類型時，會尋找什麼。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
ms.openlocfilehash: 0032d3e50d7dab0b696d9000242e70956469052e
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2020
ms.locfileid: "41592114"
---
# <a name="eu-passport-number"></a><span data-ttu-id="db480-104">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-104">EU Passport Number</span></span>

<span data-ttu-id="db480-105">本主題說明資料遺失防護（DLP）原則在偵測到歐盟護照號碼機密資訊類型時，會尋找什麼。</span><span class="sxs-lookup"><span data-stu-id="db480-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="db480-106">這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。</span><span class="sxs-lookup"><span data-stu-id="db480-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="db480-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="db480-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="db480-108">格式</span><span class="sxs-lookup"><span data-stu-id="db480-108">Format</span></span>

<span data-ttu-id="db480-109">一個字母后接一個選擇性的空格和七位數</span><span class="sxs-lookup"><span data-stu-id="db480-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-110">模式</span><span class="sxs-lookup"><span data-stu-id="db480-110">Pattern</span></span>

<span data-ttu-id="db480-111">一個字母、七位數和一個空格的組合：</span><span class="sxs-lookup"><span data-stu-id="db480-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="db480-112">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="db480-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="db480-113">一個空格（選用）</span><span class="sxs-lookup"><span data-stu-id="db480-113">One space (optional)</span></span>
    
- <span data-ttu-id="db480-114">七位數</span><span class="sxs-lookup"><span data-stu-id="db480-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db480-115">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-115">Checksum</span></span>

<span data-ttu-id="db480-116">不適用</span><span class="sxs-lookup"><span data-stu-id="db480-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-117">定義</span><span class="sxs-lookup"><span data-stu-id="db480-117">Definition</span></span>

<span data-ttu-id="db480-118">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-119">正則運算式`Regex_austria_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-120">找到來自`Keywords_austria_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-121">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-121">Keywords</span></span>

<span data-ttu-id="db480-122">| |</span><span class="sxs-lookup"><span data-stu-id="db480-122">| |</span></span>
|<span data-ttu-id="db480-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-124">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-124">passport number</span></span>  <br/> <span data-ttu-id="db480-125">奧地利護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-125">austrian passport number</span></span>  <br/> <span data-ttu-id="db480-126">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-126">passport no</span></span>  <br/> <span data-ttu-id="db480-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="db480-127">reisepass</span></span>  <br/> <span data-ttu-id="db480-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="db480-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="db480-129">比利時</span><span class="sxs-lookup"><span data-stu-id="db480-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="db480-130">格式</span><span class="sxs-lookup"><span data-stu-id="db480-130">Format</span></span>

<span data-ttu-id="db480-131">兩個字母后接六位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-132">模式</span><span class="sxs-lookup"><span data-stu-id="db480-132">Pattern</span></span>

<span data-ttu-id="db480-133">兩個字母后接六位數</span><span class="sxs-lookup"><span data-stu-id="db480-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db480-134">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-134">Checksum</span></span>

<span data-ttu-id="db480-135">不適用</span><span class="sxs-lookup"><span data-stu-id="db480-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-136">定義</span><span class="sxs-lookup"><span data-stu-id="db480-136">Definition</span></span>

<span data-ttu-id="db480-137">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-138">正則運算式`Regex_belgium_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-139">找到來自`Keywords_belgium_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-140">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-140">Keywords</span></span>

<span data-ttu-id="db480-141">| |</span><span class="sxs-lookup"><span data-stu-id="db480-141">| |</span></span>
|<span data-ttu-id="db480-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-143">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-143">passport number</span></span>  <br/> <span data-ttu-id="db480-144">比利時護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-144">belgian passport number</span></span>  <br/> <span data-ttu-id="db480-145">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-145">passport no</span></span>  <br/> <span data-ttu-id="db480-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="db480-146">paspoort</span></span>  <br/> <span data-ttu-id="db480-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="db480-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="db480-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="db480-148">reisepass kein</span></span>  <br/> <span data-ttu-id="db480-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="db480-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="db480-150">保加利亞</span><span class="sxs-lookup"><span data-stu-id="db480-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="db480-151">格式</span><span class="sxs-lookup"><span data-stu-id="db480-151">Format</span></span>

<span data-ttu-id="db480-152">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-153">模式</span><span class="sxs-lookup"><span data-stu-id="db480-153">Pattern</span></span>

 <span data-ttu-id="db480-154">九位數</span><span class="sxs-lookup"><span data-stu-id="db480-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="db480-155">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-155">Checksum</span></span>

<span data-ttu-id="db480-156">否</span><span class="sxs-lookup"><span data-stu-id="db480-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-157">定義</span><span class="sxs-lookup"><span data-stu-id="db480-157">Definition</span></span>

<span data-ttu-id="db480-158">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-159">正則運算式`Regex_bulgaria_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-160">找到來自`Keywords_bulgaria_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-161">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-161">Keywords</span></span>

<span data-ttu-id="db480-162">| |</span><span class="sxs-lookup"><span data-stu-id="db480-162">| |</span></span>
|<span data-ttu-id="db480-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-164">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-164">passport number</span></span>  <br/> <span data-ttu-id="db480-165">保加利亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="db480-166">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-166">passport no</span></span>  <br/> <span data-ttu-id="db480-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="db480-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="db480-168">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="db480-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="db480-169">格式</span><span class="sxs-lookup"><span data-stu-id="db480-169">Format</span></span>

<span data-ttu-id="db480-170">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-171">模式</span><span class="sxs-lookup"><span data-stu-id="db480-171">Pattern</span></span>

 <span data-ttu-id="db480-172">九位數</span><span class="sxs-lookup"><span data-stu-id="db480-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="db480-173">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-173">Checksum</span></span>

<span data-ttu-id="db480-174">否</span><span class="sxs-lookup"><span data-stu-id="db480-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-175">定義</span><span class="sxs-lookup"><span data-stu-id="db480-175">Definition</span></span>

<span data-ttu-id="db480-176">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-177">正則運算式`Regex_croatia_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-178">找到來自`Keywords_croatia_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-179">Keywords</span></span>

<span data-ttu-id="db480-180">| |</span><span class="sxs-lookup"><span data-stu-id="db480-180">| |</span></span>
|<span data-ttu-id="db480-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-182">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-182">passport number</span></span>  <br/> <span data-ttu-id="db480-183">克羅地亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-183">croatian passport number</span></span>  <br/> <span data-ttu-id="db480-184">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-184">passport no</span></span>  <br/> <span data-ttu-id="db480-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="db480-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="db480-186">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="db480-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="db480-187">格式</span><span class="sxs-lookup"><span data-stu-id="db480-187">Format</span></span>

<span data-ttu-id="db480-188">一個字母后接6-8 位數，沒有空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-189">模式</span><span class="sxs-lookup"><span data-stu-id="db480-189">Pattern</span></span>

<span data-ttu-id="db480-190">一個字母后接六個到八位數</span><span class="sxs-lookup"><span data-stu-id="db480-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db480-191">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-191">Checksum</span></span>

<span data-ttu-id="db480-192">否</span><span class="sxs-lookup"><span data-stu-id="db480-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-193">定義</span><span class="sxs-lookup"><span data-stu-id="db480-193">Definition</span></span>

<span data-ttu-id="db480-194">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-195">正則運算式`Regex_cyprus_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-196">找到來自`Keywords_cyprus_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-197">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-197">Keywords</span></span>

<span data-ttu-id="db480-198">| |</span><span class="sxs-lookup"><span data-stu-id="db480-198">| |</span></span>
|<span data-ttu-id="db480-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-200">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-200">passport number</span></span>  <br/> <span data-ttu-id="db480-201">賽普勒斯護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="db480-202">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-202">passport no</span></span>  <br/> <span data-ttu-id="db480-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="db480-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="db480-204">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="db480-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="db480-205">格式</span><span class="sxs-lookup"><span data-stu-id="db480-205">Format</span></span>

<span data-ttu-id="db480-206">不含空格或分隔符號的八位數</span><span class="sxs-lookup"><span data-stu-id="db480-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-207">模式</span><span class="sxs-lookup"><span data-stu-id="db480-207">Pattern</span></span>

<span data-ttu-id="db480-208">不含空格或分隔符號的八位數</span><span class="sxs-lookup"><span data-stu-id="db480-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db480-209">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-209">Checksum</span></span>

<span data-ttu-id="db480-210">否</span><span class="sxs-lookup"><span data-stu-id="db480-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-211">定義</span><span class="sxs-lookup"><span data-stu-id="db480-211">Definition</span></span>

<span data-ttu-id="db480-212">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-213">正則運算式`Regex_czech_republic_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-214">找到來自`Keywords_czech_republic_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-215">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-215">Keywords</span></span>

<span data-ttu-id="db480-216">| |</span><span class="sxs-lookup"><span data-stu-id="db480-216">| |</span></span>
|<span data-ttu-id="db480-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-218">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-218">passport number</span></span>  <br/> <span data-ttu-id="db480-219">捷克護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-219">czech passport number</span></span>  <br/> <span data-ttu-id="db480-220">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-220">passport no</span></span>  <br/> <span data-ttu-id="db480-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="db480-221">cestovní pas</span></span>  <br/> <span data-ttu-id="db480-222">Pas</span><span class="sxs-lookup"><span data-stu-id="db480-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="db480-223">丹麥</span><span class="sxs-lookup"><span data-stu-id="db480-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="db480-224">格式</span><span class="sxs-lookup"><span data-stu-id="db480-224">Format</span></span>

<span data-ttu-id="db480-225">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-226">模式</span><span class="sxs-lookup"><span data-stu-id="db480-226">Pattern</span></span>

 <span data-ttu-id="db480-227">九位數</span><span class="sxs-lookup"><span data-stu-id="db480-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="db480-228">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-228">Checksum</span></span>

<span data-ttu-id="db480-229">否</span><span class="sxs-lookup"><span data-stu-id="db480-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-230">定義</span><span class="sxs-lookup"><span data-stu-id="db480-230">Definition</span></span>

<span data-ttu-id="db480-231">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-232">正則運算式`Regex_denmark_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-233">找到來自`Keywords_denmark_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-234">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-234">Keywords</span></span>

<span data-ttu-id="db480-235">| |</span><span class="sxs-lookup"><span data-stu-id="db480-235">| |</span></span>
|<span data-ttu-id="db480-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-237">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-237">passport number</span></span>  <br/> <span data-ttu-id="db480-238">丹麥文護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-238">danish passport number</span></span>  <br/> <span data-ttu-id="db480-239">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-239">passport no</span></span>  <br/> <span data-ttu-id="db480-240">Pas</span><span class="sxs-lookup"><span data-stu-id="db480-240">pas</span></span>  <br/> <span data-ttu-id="db480-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="db480-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="db480-242">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="db480-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="db480-243">格式</span><span class="sxs-lookup"><span data-stu-id="db480-243">Format</span></span>

<span data-ttu-id="db480-244">一個字母后接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-245">模式</span><span class="sxs-lookup"><span data-stu-id="db480-245">Pattern</span></span>

<span data-ttu-id="db480-246">一個字母后接7位數</span><span class="sxs-lookup"><span data-stu-id="db480-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db480-247">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-247">Checksum</span></span>

<span data-ttu-id="db480-248">否</span><span class="sxs-lookup"><span data-stu-id="db480-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-249">定義</span><span class="sxs-lookup"><span data-stu-id="db480-249">Definition</span></span>

<span data-ttu-id="db480-250">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-251">正則運算式`Regex_estonia_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-252">找到來自`Keywords_estonia_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-253">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-253">Keywords</span></span>

<span data-ttu-id="db480-254">| |</span><span class="sxs-lookup"><span data-stu-id="db480-254">| |</span></span>
|<span data-ttu-id="db480-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-256">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-256">passport number</span></span>  <br/> <span data-ttu-id="db480-257">愛沙尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-257">estonian passport number</span></span>  <br/> <span data-ttu-id="db480-258">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-258">passport no</span></span>  <br/> <span data-ttu-id="db480-259">eesti kodaniku 傳遞</span><span class="sxs-lookup"><span data-stu-id="db480-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="db480-260">芬蘭</span><span class="sxs-lookup"><span data-stu-id="db480-260">Finland</span></span>

<span data-ttu-id="db480-261">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「芬蘭護照號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="db480-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="db480-262">法國</span><span class="sxs-lookup"><span data-stu-id="db480-262">France</span></span>

<span data-ttu-id="db480-263">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「法國護照號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="db480-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="db480-264">德國</span><span class="sxs-lookup"><span data-stu-id="db480-264">Germany</span></span>

<span data-ttu-id="db480-265">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「德文護照號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="db480-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="db480-266">希臘</span><span class="sxs-lookup"><span data-stu-id="db480-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="db480-267">格式</span><span class="sxs-lookup"><span data-stu-id="db480-267">Format</span></span>

<span data-ttu-id="db480-268">兩個字母后接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-269">模式</span><span class="sxs-lookup"><span data-stu-id="db480-269">Pattern</span></span>

<span data-ttu-id="db480-270">兩個字母后接7位數</span><span class="sxs-lookup"><span data-stu-id="db480-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db480-271">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-271">Checksum</span></span>

<span data-ttu-id="db480-272">否</span><span class="sxs-lookup"><span data-stu-id="db480-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-273">定義</span><span class="sxs-lookup"><span data-stu-id="db480-273">Definition</span></span>

<span data-ttu-id="db480-274">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-275">正則運算式`Regex_greece_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-276">找到來自`Keywords_greece_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-277">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-277">Keywords</span></span>

<span data-ttu-id="db480-278">| |</span><span class="sxs-lookup"><span data-stu-id="db480-278">| |</span></span>
|<span data-ttu-id="db480-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-280">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-280">passport number</span></span>  <br/> <span data-ttu-id="db480-281">希臘文護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-281">greek passport number</span></span>  <br/> <span data-ttu-id="db480-282">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-282">passport no</span></span>  <br/> <span data-ttu-id="db480-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="db480-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="db480-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="db480-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="db480-285">格式</span><span class="sxs-lookup"><span data-stu-id="db480-285">Format</span></span>

<span data-ttu-id="db480-286">兩個字母后接六個或7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-287">模式</span><span class="sxs-lookup"><span data-stu-id="db480-287">Pattern</span></span>

<span data-ttu-id="db480-288">兩個字母后接六位數或七位數</span><span class="sxs-lookup"><span data-stu-id="db480-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db480-289">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-289">Checksum</span></span>

<span data-ttu-id="db480-290">否</span><span class="sxs-lookup"><span data-stu-id="db480-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-291">定義</span><span class="sxs-lookup"><span data-stu-id="db480-291">Definition</span></span>

<span data-ttu-id="db480-292">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-293">正則運算式`Regex_hungary_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-294">找到來自`Keywords_hungary_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-295">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-295">Keywords</span></span>

<span data-ttu-id="db480-296">| |</span><span class="sxs-lookup"><span data-stu-id="db480-296">| |</span></span>
|<span data-ttu-id="db480-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-298">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-298">passport number</span></span>  <br/> <span data-ttu-id="db480-299">匈牙利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="db480-300">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-300">passport no</span></span>  <br/> <span data-ttu-id="db480-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="db480-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="db480-302">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="db480-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="db480-303">格式</span><span class="sxs-lookup"><span data-stu-id="db480-303">Format</span></span>

<span data-ttu-id="db480-304">兩個字母或數位後接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-305">模式</span><span class="sxs-lookup"><span data-stu-id="db480-305">Pattern</span></span>

<span data-ttu-id="db480-306">兩個字母或數位後接7位數：</span><span class="sxs-lookup"><span data-stu-id="db480-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="db480-307">兩位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="db480-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="db480-308">七位數</span><span class="sxs-lookup"><span data-stu-id="db480-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db480-309">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-309">Checksum</span></span>

<span data-ttu-id="db480-310">否</span><span class="sxs-lookup"><span data-stu-id="db480-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-311">定義</span><span class="sxs-lookup"><span data-stu-id="db480-311">Definition</span></span>

<span data-ttu-id="db480-312">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-313">正則運算式`Regex_ireland_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-314">找到來自`Keywords_ireland_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-315">Keywords</span></span>

<span data-ttu-id="db480-316">| |</span><span class="sxs-lookup"><span data-stu-id="db480-316">| |</span></span>
|<span data-ttu-id="db480-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-318">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-318">passport number</span></span>  <br/> <span data-ttu-id="db480-319">愛爾蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-319">irish passport number</span></span>  <br/> <span data-ttu-id="db480-320">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-320">passport no</span></span>  <br/> <span data-ttu-id="db480-321">Pas</span><span class="sxs-lookup"><span data-stu-id="db480-321">pas</span></span>  <br/> <span data-ttu-id="db480-322">護照</span><span class="sxs-lookup"><span data-stu-id="db480-322">passport</span></span>  <br/> <span data-ttu-id="db480-323">passeport</span><span class="sxs-lookup"><span data-stu-id="db480-323">passeport</span></span>  <br/> <span data-ttu-id="db480-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="db480-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="db480-325">義大利</span><span class="sxs-lookup"><span data-stu-id="db480-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="db480-326">格式</span><span class="sxs-lookup"><span data-stu-id="db480-326">Format</span></span>

<span data-ttu-id="db480-327">兩個字母或數位後接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-328">模式</span><span class="sxs-lookup"><span data-stu-id="db480-328">Pattern</span></span>

<span data-ttu-id="db480-329">兩個字母或數位後接7位數：</span><span class="sxs-lookup"><span data-stu-id="db480-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="db480-330">兩位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="db480-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="db480-331">七位數</span><span class="sxs-lookup"><span data-stu-id="db480-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db480-332">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-332">Checksum</span></span>

<span data-ttu-id="db480-333">不適用</span><span class="sxs-lookup"><span data-stu-id="db480-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-334">定義</span><span class="sxs-lookup"><span data-stu-id="db480-334">Definition</span></span>

<span data-ttu-id="db480-335">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-336">正則運算式`Regex_italy_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-337">找到來自`Keywords_italy_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-338">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-338">Keywords</span></span>

<span data-ttu-id="db480-339">| |</span><span class="sxs-lookup"><span data-stu-id="db480-339">| |</span></span>
|<span data-ttu-id="db480-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-341">義大利護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-341">italian passport number</span></span>  <br/> <span data-ttu-id="db480-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="db480-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="db480-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="db480-343">passaporto</span></span>  <br/> <span data-ttu-id="db480-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="db480-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="db480-345">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-345">passport number</span></span>  <br/> <span data-ttu-id="db480-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="db480-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="db480-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="db480-347">passaporto numero</span></span>  <br/> <span data-ttu-id="db480-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="db480-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="db480-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="db480-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="db480-350">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="db480-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="db480-351">格式</span><span class="sxs-lookup"><span data-stu-id="db480-351">Format</span></span>

<span data-ttu-id="db480-352">兩個字母或數位後接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-353">模式</span><span class="sxs-lookup"><span data-stu-id="db480-353">Pattern</span></span>

<span data-ttu-id="db480-354">兩個字母或數位後接7位數：</span><span class="sxs-lookup"><span data-stu-id="db480-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="db480-355">兩位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="db480-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="db480-356">七位數</span><span class="sxs-lookup"><span data-stu-id="db480-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db480-357">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-357">Checksum</span></span>

<span data-ttu-id="db480-358">否</span><span class="sxs-lookup"><span data-stu-id="db480-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-359">定義</span><span class="sxs-lookup"><span data-stu-id="db480-359">Definition</span></span>

<span data-ttu-id="db480-360">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-361">正則運算式`Regex_latvia_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-362">找到來自`Keywords_latvia_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-363">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-363">Keywords</span></span>

<span data-ttu-id="db480-364">| |</span><span class="sxs-lookup"><span data-stu-id="db480-364">| |</span></span>
|<span data-ttu-id="db480-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-366">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-366">passport number</span></span>  <br/> <span data-ttu-id="db480-367">拉脫維亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-367">latvian passport number</span></span>  <br/> <span data-ttu-id="db480-368">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-368">passport no</span></span>  <br/> <span data-ttu-id="db480-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="db480-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="db480-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="db480-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="db480-371">格式</span><span class="sxs-lookup"><span data-stu-id="db480-371">Format</span></span>

<span data-ttu-id="db480-372">八位數的數位或字母，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-373">模式</span><span class="sxs-lookup"><span data-stu-id="db480-373">Pattern</span></span>

<span data-ttu-id="db480-374">八位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="db480-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db480-375">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-375">Checksum</span></span>

<span data-ttu-id="db480-376">不適用</span><span class="sxs-lookup"><span data-stu-id="db480-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-377">定義</span><span class="sxs-lookup"><span data-stu-id="db480-377">Definition</span></span>

<span data-ttu-id="db480-378">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-379">正則運算式`Regex_lithuania_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-380">找到來自`Keywords_lithuania_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-381">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-381">Keywords</span></span>

<span data-ttu-id="db480-382">| |</span><span class="sxs-lookup"><span data-stu-id="db480-382">| |</span></span>
|<span data-ttu-id="db480-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-384">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-384">passport number</span></span>  <br/> <span data-ttu-id="db480-385">lithunian 護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="db480-386">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-386">passport no</span></span>  <br/> <span data-ttu-id="db480-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="db480-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="db480-388">盧森堡</span><span class="sxs-lookup"><span data-stu-id="db480-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="db480-389">格式</span><span class="sxs-lookup"><span data-stu-id="db480-389">Format</span></span>

<span data-ttu-id="db480-390">八位數的數位或字母，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-391">模式</span><span class="sxs-lookup"><span data-stu-id="db480-391">Pattern</span></span>

<span data-ttu-id="db480-392">八位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="db480-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db480-393">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-393">Checksum</span></span>

<span data-ttu-id="db480-394">否</span><span class="sxs-lookup"><span data-stu-id="db480-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-395">定義</span><span class="sxs-lookup"><span data-stu-id="db480-395">Definition</span></span>

<span data-ttu-id="db480-396">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-397">正則運算式`Regex_nation_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-398">找到來自`Keywords_nation_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-399">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-399">Keywords</span></span>

<span data-ttu-id="db480-400">| |</span><span class="sxs-lookup"><span data-stu-id="db480-400">| |</span></span>
|<span data-ttu-id="db480-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-402">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-402">passport number</span></span>  <br/> <span data-ttu-id="db480-403">拉脫維亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-403">latvian passport number</span></span>  <br/> <span data-ttu-id="db480-404">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-404">passport no</span></span>  <br/> <span data-ttu-id="db480-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="db480-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="db480-406">馬爾他</span><span class="sxs-lookup"><span data-stu-id="db480-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="db480-407">格式</span><span class="sxs-lookup"><span data-stu-id="db480-407">Format</span></span>

<span data-ttu-id="db480-408">七位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-409">模式</span><span class="sxs-lookup"><span data-stu-id="db480-409">Pattern</span></span>

 <span data-ttu-id="db480-410">七位數</span><span class="sxs-lookup"><span data-stu-id="db480-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="db480-411">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-411">Checksum</span></span>

<span data-ttu-id="db480-412">否</span><span class="sxs-lookup"><span data-stu-id="db480-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-413">定義</span><span class="sxs-lookup"><span data-stu-id="db480-413">Definition</span></span>

<span data-ttu-id="db480-414">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-415">正則運算式`Regex_malta_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-416">找到來自`Keywords_malta_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-417">Keywords</span></span>

<span data-ttu-id="db480-418">| |</span><span class="sxs-lookup"><span data-stu-id="db480-418">| |</span></span>
|<span data-ttu-id="db480-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-420">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-420">passport number</span></span>  <br/> <span data-ttu-id="db480-421">馬爾他護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-421">maltese passport number</span></span>  <br/> <span data-ttu-id="db480-422">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-422">passport no</span></span>  <br/> <span data-ttu-id="db480-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="db480-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="db480-424">荷蘭</span><span class="sxs-lookup"><span data-stu-id="db480-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="db480-425">格式</span><span class="sxs-lookup"><span data-stu-id="db480-425">Format</span></span>

<span data-ttu-id="db480-426">不含空格或分隔符號的九個字母或數位</span><span class="sxs-lookup"><span data-stu-id="db480-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-427">模式</span><span class="sxs-lookup"><span data-stu-id="db480-427">Pattern</span></span>

<span data-ttu-id="db480-428">九個字母或數位</span><span class="sxs-lookup"><span data-stu-id="db480-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db480-429">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-429">Checksum</span></span>

<span data-ttu-id="db480-430">不適用</span><span class="sxs-lookup"><span data-stu-id="db480-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-431">定義</span><span class="sxs-lookup"><span data-stu-id="db480-431">Definition</span></span>

<span data-ttu-id="db480-432">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-433">正則運算式`Regex_netherlands_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-434">找到來自`Keywords_netherlands_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-435">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-435">Keywords</span></span>

<span data-ttu-id="db480-436">| |</span><span class="sxs-lookup"><span data-stu-id="db480-436">| |</span></span>
|<span data-ttu-id="db480-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-438">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-438">dutch passport number</span></span>  <br/> <span data-ttu-id="db480-439">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-439">passport number</span></span>  <br/> <span data-ttu-id="db480-440">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="db480-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="db480-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="db480-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="db480-442">paspoort</span></span>  <br/> <span data-ttu-id="db480-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="db480-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="db480-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="db480-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="db480-445">波蘭</span><span class="sxs-lookup"><span data-stu-id="db480-445">Poland</span></span>

<span data-ttu-id="db480-446">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「波蘭護照號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="db480-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="db480-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="db480-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="db480-448">格式</span><span class="sxs-lookup"><span data-stu-id="db480-448">Format</span></span>

<span data-ttu-id="db480-449">一個字母后接六位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-450">模式</span><span class="sxs-lookup"><span data-stu-id="db480-450">Pattern</span></span>

<span data-ttu-id="db480-451">一個字母后接六位數：</span><span class="sxs-lookup"><span data-stu-id="db480-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="db480-452">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="db480-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="db480-453">六位數</span><span class="sxs-lookup"><span data-stu-id="db480-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db480-454">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-454">Checksum</span></span>

<span data-ttu-id="db480-455">否</span><span class="sxs-lookup"><span data-stu-id="db480-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-456">定義</span><span class="sxs-lookup"><span data-stu-id="db480-456">Definition</span></span>

<span data-ttu-id="db480-457">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-458">正則運算式`Regex_portugal_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-459">找到來自`Keywords_portugal_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-460">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-460">Keywords</span></span>

<span data-ttu-id="db480-461">| |</span><span class="sxs-lookup"><span data-stu-id="db480-461">| |</span></span>
|<span data-ttu-id="db480-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-463">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-463">passport number</span></span>  <br/> <span data-ttu-id="db480-464">葡萄牙文護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="db480-465">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-465">passport no</span></span>  <br/> <span data-ttu-id="db480-466">número 執行 passaporte</span><span class="sxs-lookup"><span data-stu-id="db480-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="db480-467">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="db480-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="db480-468">格式</span><span class="sxs-lookup"><span data-stu-id="db480-468">Format</span></span>

<span data-ttu-id="db480-469">8或9位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-470">模式</span><span class="sxs-lookup"><span data-stu-id="db480-470">Pattern</span></span>

<span data-ttu-id="db480-471">8或9位數</span><span class="sxs-lookup"><span data-stu-id="db480-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db480-472">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-472">Checksum</span></span>

<span data-ttu-id="db480-473">否</span><span class="sxs-lookup"><span data-stu-id="db480-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-474">定義</span><span class="sxs-lookup"><span data-stu-id="db480-474">Definition</span></span>

<span data-ttu-id="db480-475">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-476">正則運算式`Regex_romania_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-477">找到來自`Keywords_romania_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-478">Keywords</span></span>

<span data-ttu-id="db480-479">| |</span><span class="sxs-lookup"><span data-stu-id="db480-479">| |</span></span>
|<span data-ttu-id="db480-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-481">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-481">passport number</span></span>  <br/> <span data-ttu-id="db480-482">羅馬尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-482">romanian passport number</span></span>  <br/> <span data-ttu-id="db480-483">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-483">passport no</span></span>  <br/> <span data-ttu-id="db480-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="db480-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="db480-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="db480-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="db480-486">格式</span><span class="sxs-lookup"><span data-stu-id="db480-486">Format</span></span>

<span data-ttu-id="db480-487">一個數位或字母后接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-488">模式</span><span class="sxs-lookup"><span data-stu-id="db480-488">Pattern</span></span>

<span data-ttu-id="db480-489">一個數位或字母（不區分大小寫）後接7位數</span><span class="sxs-lookup"><span data-stu-id="db480-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="db480-490">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-490">Checksum</span></span>

<span data-ttu-id="db480-491">否</span><span class="sxs-lookup"><span data-stu-id="db480-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-492">定義</span><span class="sxs-lookup"><span data-stu-id="db480-492">Definition</span></span>

<span data-ttu-id="db480-493">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-494">正則運算式`Regex_slovakia_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-495">找到來自`Keywords_slovakia_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-496">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-496">Keywords</span></span>

<span data-ttu-id="db480-497">| |</span><span class="sxs-lookup"><span data-stu-id="db480-497">| |</span></span>
|<span data-ttu-id="db480-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-499">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-499">passport number</span></span>  <br/> <span data-ttu-id="db480-500">斯洛伐克護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="db480-501">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-501">passport no</span></span>  <br/> <span data-ttu-id="db480-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="db480-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="db480-503">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="db480-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="db480-504">格式</span><span class="sxs-lookup"><span data-stu-id="db480-504">Format</span></span>

<span data-ttu-id="db480-505">兩個字母后接7位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-506">模式</span><span class="sxs-lookup"><span data-stu-id="db480-506">Pattern</span></span>

<span data-ttu-id="db480-507">兩個字母后接7位數：</span><span class="sxs-lookup"><span data-stu-id="db480-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="db480-508">字母 "P"</span><span class="sxs-lookup"><span data-stu-id="db480-508">The letter "P"</span></span>
    
- <span data-ttu-id="db480-509">單一大寫字母</span><span class="sxs-lookup"><span data-stu-id="db480-509">One uppercase letter</span></span>
    
- <span data-ttu-id="db480-510">七位數</span><span class="sxs-lookup"><span data-stu-id="db480-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db480-511">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-511">Checksum</span></span>

<span data-ttu-id="db480-512">否</span><span class="sxs-lookup"><span data-stu-id="db480-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-513">定義</span><span class="sxs-lookup"><span data-stu-id="db480-513">Definition</span></span>

<span data-ttu-id="db480-514">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-515">正則運算式`Regex_slovenia_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-516">找到來自`Keywords_slovenia_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-517">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-517">Keywords</span></span>

<span data-ttu-id="db480-518">| |</span><span class="sxs-lookup"><span data-stu-id="db480-518">| |</span></span>
|<span data-ttu-id="db480-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-520">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-520">passport number</span></span>  <br/> <span data-ttu-id="db480-521">斯洛維尼亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="db480-522">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-522">passport no</span></span>  <br/> <span data-ttu-id="db480-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="db480-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="db480-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="db480-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="db480-525">格式</span><span class="sxs-lookup"><span data-stu-id="db480-525">Format</span></span>

<span data-ttu-id="db480-526">8或9個字元組合的字母和數位，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="db480-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="db480-527">模式</span><span class="sxs-lookup"><span data-stu-id="db480-527">Pattern</span></span>

<span data-ttu-id="db480-528">字母和數位的8或9個字元組合：</span><span class="sxs-lookup"><span data-stu-id="db480-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="db480-529">兩位數或字母</span><span class="sxs-lookup"><span data-stu-id="db480-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="db480-530">一個數位或字母（選用）</span><span class="sxs-lookup"><span data-stu-id="db480-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="db480-531">六位數</span><span class="sxs-lookup"><span data-stu-id="db480-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="db480-532">校驗</span><span class="sxs-lookup"><span data-stu-id="db480-532">Checksum</span></span>

<span data-ttu-id="db480-533">不適用</span><span class="sxs-lookup"><span data-stu-id="db480-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="db480-534">定義</span><span class="sxs-lookup"><span data-stu-id="db480-534">Definition</span></span>

<span data-ttu-id="db480-535">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="db480-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="db480-536">正則運算式`Regex_spain_eu_passport_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="db480-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="db480-537">找到來自`Keywords_spain_eu_passport_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="db480-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="db480-538">關鍵字</span><span class="sxs-lookup"><span data-stu-id="db480-538">Keywords</span></span>

<span data-ttu-id="db480-539">| |</span><span class="sxs-lookup"><span data-stu-id="db480-539">| |</span></span>
|<span data-ttu-id="db480-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="db480-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="db480-541">護照</span><span class="sxs-lookup"><span data-stu-id="db480-541">passport</span></span>  <br/> <span data-ttu-id="db480-542">西班牙護照</span><span class="sxs-lookup"><span data-stu-id="db480-542">spain passport</span></span>  <br/> <span data-ttu-id="db480-543">護照手冊</span><span class="sxs-lookup"><span data-stu-id="db480-543">passport book</span></span>  <br/> <span data-ttu-id="db480-544">護照號碼</span><span class="sxs-lookup"><span data-stu-id="db480-544">passport number</span></span>  <br/> <span data-ttu-id="db480-545">護照否</span><span class="sxs-lookup"><span data-stu-id="db480-545">passport no</span></span>  <br/> <span data-ttu-id="db480-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="db480-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="db480-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="db480-547">número pasaporte</span></span>  <br/> <span data-ttu-id="db480-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="db480-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="db480-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="db480-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="db480-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="db480-550">Sweden</span></span>

<span data-ttu-id="db480-551">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「瑞典護照號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="db480-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="db480-552">英國</span><span class="sxs-lookup"><span data-stu-id="db480-552">UK</span></span>

<span data-ttu-id="db480-553">如需詳細資訊，請參閱 section/英國</span><span class="sxs-lookup"><span data-stu-id="db480-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="db480-554">「[機密資訊類型](what-the-sensitive-information-types-look-for.md)」所尋找的「護照號碼」。</span><span class="sxs-lookup"><span data-stu-id="db480-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db480-555">請參閱</span><span class="sxs-lookup"><span data-stu-id="db480-555">See also</span></span>

[<span data-ttu-id="db480-556">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="db480-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

