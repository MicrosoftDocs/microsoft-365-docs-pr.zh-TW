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
# <a name="eu-passport-number"></a><span data-ttu-id="e1743-104">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-104">EU Passport Number</span></span>

<span data-ttu-id="e1743-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟護照號碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="e1743-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="e1743-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="e1743-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="e1743-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="e1743-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="e1743-108">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-108">Format</span></span>

<span data-ttu-id="e1743-109">一個字母後尾隨一個選用空格和七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-110">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-110">Pattern</span></span>

<span data-ttu-id="e1743-111">一個字母、 七位數和一個空格的組合：</span><span class="sxs-lookup"><span data-stu-id="e1743-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="e1743-112">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e1743-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="e1743-113">一個空格 （選用）</span><span class="sxs-lookup"><span data-stu-id="e1743-113">One space (optional)</span></span>
    
- <span data-ttu-id="e1743-114">七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e1743-115">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-115">Checksum</span></span>

<span data-ttu-id="e1743-116">不適用</span><span class="sxs-lookup"><span data-stu-id="e1743-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-117">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-117">Definition</span></span>

<span data-ttu-id="e1743-118">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-119">規則運算式`Regex_austria_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-120">從關鍵字`Keywords_austria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-121">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-121">Keywords</span></span>

<span data-ttu-id="e1743-122">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-122"></span></span>
|<span data-ttu-id="e1743-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-124">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-124">passport number</span></span>  <br/> <span data-ttu-id="e1743-125">奧地利護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-125">austrian passport number</span></span>  <br/> <span data-ttu-id="e1743-126">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-126">passport no</span></span>  <br/> <span data-ttu-id="e1743-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="e1743-127">reisepass</span></span>  <br/> <span data-ttu-id="e1743-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="e1743-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="e1743-129">比利時</span><span class="sxs-lookup"><span data-stu-id="e1743-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="e1743-130">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-130">Format</span></span>

<span data-ttu-id="e1743-131">兩個字母後尾隨六位數，代表不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-132">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-132">Pattern</span></span>

<span data-ttu-id="e1743-133">兩個字母後尾隨六位數和</span><span class="sxs-lookup"><span data-stu-id="e1743-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e1743-134">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-134">Checksum</span></span>

<span data-ttu-id="e1743-135">不適用</span><span class="sxs-lookup"><span data-stu-id="e1743-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-136">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-136">Definition</span></span>

<span data-ttu-id="e1743-137">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-138">規則運算式`Regex_belgium_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-139">從關鍵字`Keywords_belgium_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-140">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-140">Keywords</span></span>

<span data-ttu-id="e1743-141">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-141"></span></span>
|<span data-ttu-id="e1743-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-143">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-143">passport number</span></span>  <br/> <span data-ttu-id="e1743-144">比利時護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-144">belgian passport number</span></span>  <br/> <span data-ttu-id="e1743-145">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-145">passport no</span></span>  <br/> <span data-ttu-id="e1743-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="e1743-146">paspoort</span></span>  <br/> <span data-ttu-id="e1743-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="e1743-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="e1743-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="e1743-148">reisepass kein</span></span>  <br/> <span data-ttu-id="e1743-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="e1743-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="e1743-150">保加利亞</span><span class="sxs-lookup"><span data-stu-id="e1743-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="e1743-151">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-151">Format</span></span>

<span data-ttu-id="e1743-152">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="e1743-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-153">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-153">Pattern</span></span>

 <span data-ttu-id="e1743-154">九位數</span><span class="sxs-lookup"><span data-stu-id="e1743-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e1743-155">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-155">Checksum</span></span>

<span data-ttu-id="e1743-156">否</span><span class="sxs-lookup"><span data-stu-id="e1743-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-157">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-157">Definition</span></span>

<span data-ttu-id="e1743-158">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-159">規則運算式`Regex_bulgaria_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-160">從關鍵字`Keywords_bulgaria_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-161">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-161">Keywords</span></span>

<span data-ttu-id="e1743-162">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-162"></span></span>
|<span data-ttu-id="e1743-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-164">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-164">passport number</span></span>  <br/> <span data-ttu-id="e1743-165">保加利亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="e1743-166">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-166">passport no</span></span>  <br/> <span data-ttu-id="e1743-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="e1743-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="e1743-168">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="e1743-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="e1743-169">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-169">Format</span></span>

<span data-ttu-id="e1743-170">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="e1743-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-171">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-171">Pattern</span></span>

 <span data-ttu-id="e1743-172">九位數</span><span class="sxs-lookup"><span data-stu-id="e1743-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e1743-173">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-173">Checksum</span></span>

<span data-ttu-id="e1743-174">否</span><span class="sxs-lookup"><span data-stu-id="e1743-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-175">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-175">Definition</span></span>

<span data-ttu-id="e1743-176">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-177">規則運算式`Regex_croatia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-178">從關鍵字`Keywords_croatia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-179">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-179">Keywords</span></span>

<span data-ttu-id="e1743-180">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-180"></span></span>
|<span data-ttu-id="e1743-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-182">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-182">passport number</span></span>  <br/> <span data-ttu-id="e1743-183">克羅埃西亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-183">croatian passport number</span></span>  <br/> <span data-ttu-id="e1743-184">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-184">passport no</span></span>  <br/> <span data-ttu-id="e1743-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="e1743-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="e1743-186">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="e1743-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="e1743-187">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-187">Format</span></span>

<span data-ttu-id="e1743-188">一個字母後尾隨不含空格或分隔符號 6-8 位數</span><span class="sxs-lookup"><span data-stu-id="e1743-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-189">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-189">Pattern</span></span>

<span data-ttu-id="e1743-190">一個字母後尾隨六至八位數</span><span class="sxs-lookup"><span data-stu-id="e1743-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e1743-191">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-191">Checksum</span></span>

<span data-ttu-id="e1743-192">否</span><span class="sxs-lookup"><span data-stu-id="e1743-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-193">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-193">Definition</span></span>

<span data-ttu-id="e1743-194">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-195">規則運算式`Regex_cyprus_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-196">從關鍵字`Keywords_cyprus_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-197">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-197">Keywords</span></span>

<span data-ttu-id="e1743-198">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-198"></span></span>
|<span data-ttu-id="e1743-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-200">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-200">passport number</span></span>  <br/> <span data-ttu-id="e1743-201">賽普勒斯護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="e1743-202">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-202">passport no</span></span>  <br/> <span data-ttu-id="e1743-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="e1743-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="e1743-204">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="e1743-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="e1743-205">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-205">Format</span></span>

<span data-ttu-id="e1743-206">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="e1743-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-207">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-207">Pattern</span></span>

<span data-ttu-id="e1743-208">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="e1743-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e1743-209">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-209">Checksum</span></span>

<span data-ttu-id="e1743-210">否</span><span class="sxs-lookup"><span data-stu-id="e1743-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-211">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-211">Definition</span></span>

<span data-ttu-id="e1743-212">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-213">規則運算式`Regex_czech_republic_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-214">從關鍵字`Keywords_czech_republic_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-215">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-215">Keywords</span></span>

<span data-ttu-id="e1743-216">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-216"></span></span>
|<span data-ttu-id="e1743-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-218">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-218">passport number</span></span>  <br/> <span data-ttu-id="e1743-219">捷克護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-219">czech passport number</span></span>  <br/> <span data-ttu-id="e1743-220">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-220">passport no</span></span>  <br/> <span data-ttu-id="e1743-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="e1743-221">cestovní pas</span></span>  <br/> <span data-ttu-id="e1743-222">pas</span><span class="sxs-lookup"><span data-stu-id="e1743-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="e1743-223">丹麥</span><span class="sxs-lookup"><span data-stu-id="e1743-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="e1743-224">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-224">Format</span></span>

<span data-ttu-id="e1743-225">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="e1743-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-226">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-226">Pattern</span></span>

 <span data-ttu-id="e1743-227">九位數</span><span class="sxs-lookup"><span data-stu-id="e1743-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e1743-228">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-228">Checksum</span></span>

<span data-ttu-id="e1743-229">否</span><span class="sxs-lookup"><span data-stu-id="e1743-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-230">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-230">Definition</span></span>

<span data-ttu-id="e1743-231">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-232">規則運算式`Regex_denmark_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-233">從關鍵字`Keywords_denmark_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-234">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-234">Keywords</span></span>

<span data-ttu-id="e1743-235">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-235"></span></span>
|<span data-ttu-id="e1743-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-237">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-237">passport number</span></span>  <br/> <span data-ttu-id="e1743-238">丹麥文護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-238">danish passport number</span></span>  <br/> <span data-ttu-id="e1743-239">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-239">passport no</span></span>  <br/> <span data-ttu-id="e1743-240">pas</span><span class="sxs-lookup"><span data-stu-id="e1743-240">pas</span></span>  <br/> <span data-ttu-id="e1743-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="e1743-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="e1743-242">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="e1743-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="e1743-243">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-243">Format</span></span>

<span data-ttu-id="e1743-244">一個字母後尾隨七位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-245">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-245">Pattern</span></span>

<span data-ttu-id="e1743-246">一個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e1743-247">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-247">Checksum</span></span>

<span data-ttu-id="e1743-248">否</span><span class="sxs-lookup"><span data-stu-id="e1743-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-249">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-249">Definition</span></span>

<span data-ttu-id="e1743-250">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-251">規則運算式`Regex_estonia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-252">從關鍵字`Keywords_estonia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-253">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-253">Keywords</span></span>

<span data-ttu-id="e1743-254">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-254"></span></span>
|<span data-ttu-id="e1743-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-256">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-256">passport number</span></span>  <br/> <span data-ttu-id="e1743-257">愛沙尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-257">estonian passport number</span></span>  <br/> <span data-ttu-id="e1743-258">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-258">passport no</span></span>  <br/> <span data-ttu-id="e1743-259">eesti kodaniku 複雜</span><span class="sxs-lookup"><span data-stu-id="e1743-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="e1743-260">芬蘭</span><span class="sxs-lookup"><span data-stu-id="e1743-260">Finland</span></span>

<span data-ttu-id="e1743-261">如需詳細資訊，請參閱 「 芬蘭護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e1743-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="e1743-262">法國</span><span class="sxs-lookup"><span data-stu-id="e1743-262">France</span></span>

<span data-ttu-id="e1743-263">如需詳細資訊，請參閱 「 法國護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e1743-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="e1743-264">德國</span><span class="sxs-lookup"><span data-stu-id="e1743-264">Germany</span></span>

<span data-ttu-id="e1743-265">如需詳細資訊，請參閱 「 德國護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e1743-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="e1743-266">希臘</span><span class="sxs-lookup"><span data-stu-id="e1743-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="e1743-267">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-267">Format</span></span>

<span data-ttu-id="e1743-268">兩個字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-269">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-269">Pattern</span></span>

<span data-ttu-id="e1743-270">兩個字母後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e1743-271">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-271">Checksum</span></span>

<span data-ttu-id="e1743-272">否</span><span class="sxs-lookup"><span data-stu-id="e1743-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-273">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-273">Definition</span></span>

<span data-ttu-id="e1743-274">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-275">規則運算式`Regex_greece_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-276">從關鍵字`Keywords_greece_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-277">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-277">Keywords</span></span>

<span data-ttu-id="e1743-278">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-278"></span></span>
|<span data-ttu-id="e1743-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-280">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-280">passport number</span></span>  <br/> <span data-ttu-id="e1743-281">希臘文護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-281">greek passport number</span></span>  <br/> <span data-ttu-id="e1743-282">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-282">passport no</span></span>  <br/> <span data-ttu-id="e1743-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="e1743-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="e1743-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="e1743-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="e1743-285">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-285">Format</span></span>

<span data-ttu-id="e1743-286">兩個字母後尾隨六個或七位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-287">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-287">Pattern</span></span>

<span data-ttu-id="e1743-288">兩個字母後尾隨六個或七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e1743-289">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-289">Checksum</span></span>

<span data-ttu-id="e1743-290">否</span><span class="sxs-lookup"><span data-stu-id="e1743-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-291">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-291">Definition</span></span>

<span data-ttu-id="e1743-292">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-293">規則運算式`Regex_hungary_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-294">從關鍵字`Keywords_hungary_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-295">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-295">Keywords</span></span>

<span data-ttu-id="e1743-296">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-296"></span></span>
|<span data-ttu-id="e1743-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-298">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-298">passport number</span></span>  <br/> <span data-ttu-id="e1743-299">匈牙利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="e1743-300">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-300">passport no</span></span>  <br/> <span data-ttu-id="e1743-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="e1743-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="e1743-302">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="e1743-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="e1743-303">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-303">Format</span></span>

<span data-ttu-id="e1743-304">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-305">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-305">Pattern</span></span>

<span data-ttu-id="e1743-306">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="e1743-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="e1743-307">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e1743-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="e1743-308">七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e1743-309">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-309">Checksum</span></span>

<span data-ttu-id="e1743-310">否</span><span class="sxs-lookup"><span data-stu-id="e1743-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-311">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-311">Definition</span></span>

<span data-ttu-id="e1743-312">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-313">規則運算式`Regex_ireland_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-314">從關鍵字`Keywords_ireland_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-315">Keywords</span></span>

<span data-ttu-id="e1743-316">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-316"></span></span>
|<span data-ttu-id="e1743-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-318">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-318">passport number</span></span>  <br/> <span data-ttu-id="e1743-319">愛爾蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-319">irish passport number</span></span>  <br/> <span data-ttu-id="e1743-320">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-320">passport no</span></span>  <br/> <span data-ttu-id="e1743-321">pas</span><span class="sxs-lookup"><span data-stu-id="e1743-321">pas</span></span>  <br/> <span data-ttu-id="e1743-322">passport</span><span class="sxs-lookup"><span data-stu-id="e1743-322">passport</span></span>  <br/> <span data-ttu-id="e1743-323">passeport</span><span class="sxs-lookup"><span data-stu-id="e1743-323">passeport</span></span>  <br/> <span data-ttu-id="e1743-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="e1743-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="e1743-325">義大利</span><span class="sxs-lookup"><span data-stu-id="e1743-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="e1743-326">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-326">Format</span></span>

<span data-ttu-id="e1743-327">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-328">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-328">Pattern</span></span>

<span data-ttu-id="e1743-329">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="e1743-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="e1743-330">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e1743-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="e1743-331">七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e1743-332">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-332">Checksum</span></span>

<span data-ttu-id="e1743-333">不適用</span><span class="sxs-lookup"><span data-stu-id="e1743-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-334">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-334">Definition</span></span>

<span data-ttu-id="e1743-335">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-336">規則運算式`Regex_italy_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-337">從關鍵字`Keywords_italy_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-338">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-338">Keywords</span></span>

<span data-ttu-id="e1743-339">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-339"></span></span>
|<span data-ttu-id="e1743-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-341">義大利文護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-341">italian passport number</span></span>  <br/> <span data-ttu-id="e1743-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="e1743-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="e1743-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="e1743-343">passaporto</span></span>  <br/> <span data-ttu-id="e1743-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="e1743-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="e1743-345">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-345">passport number</span></span>  <br/> <span data-ttu-id="e1743-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="e1743-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="e1743-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="e1743-347">passaporto numero</span></span>  <br/> <span data-ttu-id="e1743-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="e1743-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="e1743-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="e1743-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="e1743-350">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="e1743-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="e1743-351">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-351">Format</span></span>

<span data-ttu-id="e1743-352">兩個字母或位數後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-353">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-353">Pattern</span></span>

<span data-ttu-id="e1743-354">兩個字母或位數後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="e1743-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="e1743-355">兩個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e1743-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="e1743-356">七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e1743-357">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-357">Checksum</span></span>

<span data-ttu-id="e1743-358">否</span><span class="sxs-lookup"><span data-stu-id="e1743-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-359">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-359">Definition</span></span>

<span data-ttu-id="e1743-360">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-361">規則運算式`Regex_latvia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-362">從關鍵字`Keywords_latvia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-363">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-363">Keywords</span></span>

<span data-ttu-id="e1743-364">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-364"></span></span>
|<span data-ttu-id="e1743-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-366">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-366">passport number</span></span>  <br/> <span data-ttu-id="e1743-367">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-367">latvian passport number</span></span>  <br/> <span data-ttu-id="e1743-368">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-368">passport no</span></span>  <br/> <span data-ttu-id="e1743-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="e1743-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="e1743-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="e1743-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="e1743-371">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-371">Format</span></span>

<span data-ttu-id="e1743-372">八個個數字或字母不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-373">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-373">Pattern</span></span>

<span data-ttu-id="e1743-374">八個個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e1743-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e1743-375">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-375">Checksum</span></span>

<span data-ttu-id="e1743-376">不適用</span><span class="sxs-lookup"><span data-stu-id="e1743-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-377">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-377">Definition</span></span>

<span data-ttu-id="e1743-378">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-379">規則運算式`Regex_lithuania_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-380">從關鍵字`Keywords_lithuania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-381">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-381">Keywords</span></span>

<span data-ttu-id="e1743-382">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-382"></span></span>
|<span data-ttu-id="e1743-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-384">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-384">passport number</span></span>  <br/> <span data-ttu-id="e1743-385">lithunian 護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="e1743-386">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-386">passport no</span></span>  <br/> <span data-ttu-id="e1743-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="e1743-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="e1743-388">盧森堡</span><span class="sxs-lookup"><span data-stu-id="e1743-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="e1743-389">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-389">Format</span></span>

<span data-ttu-id="e1743-390">八個個數字或字母不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-391">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-391">Pattern</span></span>

<span data-ttu-id="e1743-392">八個個數字或字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e1743-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e1743-393">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-393">Checksum</span></span>

<span data-ttu-id="e1743-394">否</span><span class="sxs-lookup"><span data-stu-id="e1743-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-395">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-395">Definition</span></span>

<span data-ttu-id="e1743-396">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-397">規則運算式`Regex_nation_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-398">從關鍵字`Keywords_nation_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-399">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-399">Keywords</span></span>

<span data-ttu-id="e1743-400">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-400"></span></span>
|<span data-ttu-id="e1743-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-402">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-402">passport number</span></span>  <br/> <span data-ttu-id="e1743-403">拉脫維亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-403">latvian passport number</span></span>  <br/> <span data-ttu-id="e1743-404">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-404">passport no</span></span>  <br/> <span data-ttu-id="e1743-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="e1743-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="e1743-406">馬爾他</span><span class="sxs-lookup"><span data-stu-id="e1743-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="e1743-407">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-407">Format</span></span>

<span data-ttu-id="e1743-408">不含空格或分隔符號七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-409">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-409">Pattern</span></span>

 <span data-ttu-id="e1743-410">七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e1743-411">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-411">Checksum</span></span>

<span data-ttu-id="e1743-412">否</span><span class="sxs-lookup"><span data-stu-id="e1743-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-413">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-413">Definition</span></span>

<span data-ttu-id="e1743-414">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-415">規則運算式`Regex_malta_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-416">從關鍵字`Keywords_malta_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-417">Keywords</span></span>

<span data-ttu-id="e1743-418">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-418"></span></span>
|<span data-ttu-id="e1743-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-420">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-420">passport number</span></span>  <br/> <span data-ttu-id="e1743-421">馬爾他護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-421">maltese passport number</span></span>  <br/> <span data-ttu-id="e1743-422">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-422">passport no</span></span>  <br/> <span data-ttu-id="e1743-423">numru tal passaport</span><span class="sxs-lookup"><span data-stu-id="e1743-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="e1743-424">荷蘭</span><span class="sxs-lookup"><span data-stu-id="e1743-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="e1743-425">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-425">Format</span></span>

<span data-ttu-id="e1743-426">九個字母或不含空格或分隔符號的數字</span><span class="sxs-lookup"><span data-stu-id="e1743-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-427">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-427">Pattern</span></span>

<span data-ttu-id="e1743-428">九個字母或四位數</span><span class="sxs-lookup"><span data-stu-id="e1743-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e1743-429">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-429">Checksum</span></span>

<span data-ttu-id="e1743-430">不適用</span><span class="sxs-lookup"><span data-stu-id="e1743-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-431">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-431">Definition</span></span>

<span data-ttu-id="e1743-432">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-433">規則運算式`Regex_netherlands_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-434">從關鍵字`Keywords_netherlands_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-435">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-435">Keywords</span></span>

<span data-ttu-id="e1743-436">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-436"></span></span>
|<span data-ttu-id="e1743-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-438">荷蘭文護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-438">dutch passport number</span></span>  <br/> <span data-ttu-id="e1743-439">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-439">passport number</span></span>  <br/> <span data-ttu-id="e1743-440">荷蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="e1743-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="e1743-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="e1743-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="e1743-442">paspoort</span></span>  <br/> <span data-ttu-id="e1743-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="e1743-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="e1743-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="e1743-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="e1743-445">波蘭</span><span class="sxs-lookup"><span data-stu-id="e1743-445">Poland</span></span>

<span data-ttu-id="e1743-446">如需詳細資訊，請參閱 「 波蘭護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e1743-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="e1743-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="e1743-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="e1743-448">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-448">Format</span></span>

<span data-ttu-id="e1743-449">一個字母後尾隨六位數，代表不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-450">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-450">Pattern</span></span>

<span data-ttu-id="e1743-451">一個字母後尾隨六位數：</span><span class="sxs-lookup"><span data-stu-id="e1743-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="e1743-452">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="e1743-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="e1743-453">六位數</span><span class="sxs-lookup"><span data-stu-id="e1743-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e1743-454">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-454">Checksum</span></span>

<span data-ttu-id="e1743-455">否</span><span class="sxs-lookup"><span data-stu-id="e1743-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-456">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-456">Definition</span></span>

<span data-ttu-id="e1743-457">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-458">規則運算式`Regex_portugal_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-459">從關鍵字`Keywords_portugal_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-460">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-460">Keywords</span></span>

<span data-ttu-id="e1743-461">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-461"></span></span>
|<span data-ttu-id="e1743-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-463">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-463">passport number</span></span>  <br/> <span data-ttu-id="e1743-464">葡萄牙文護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="e1743-465">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-465">passport no</span></span>  <br/> <span data-ttu-id="e1743-466">número 不要 passaporte</span><span class="sxs-lookup"><span data-stu-id="e1743-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="e1743-467">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="e1743-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="e1743-468">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-468">Format</span></span>

<span data-ttu-id="e1743-469">不含空格，並讓分隔字元的八個或九位數</span><span class="sxs-lookup"><span data-stu-id="e1743-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-470">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-470">Pattern</span></span>

<span data-ttu-id="e1743-471">八個或九位數</span><span class="sxs-lookup"><span data-stu-id="e1743-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e1743-472">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-472">Checksum</span></span>

<span data-ttu-id="e1743-473">否</span><span class="sxs-lookup"><span data-stu-id="e1743-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-474">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-474">Definition</span></span>

<span data-ttu-id="e1743-475">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-476">規則運算式`Regex_romania_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-477">從關鍵字`Keywords_romania_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-478">Keywords</span></span>

<span data-ttu-id="e1743-479">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-479"></span></span>
|<span data-ttu-id="e1743-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-481">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-481">passport number</span></span>  <br/> <span data-ttu-id="e1743-482">羅馬尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-482">romanian passport number</span></span>  <br/> <span data-ttu-id="e1743-483">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-483">passport no</span></span>  <br/> <span data-ttu-id="e1743-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="e1743-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="e1743-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="e1743-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="e1743-486">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-486">Format</span></span>

<span data-ttu-id="e1743-487">一個數字或字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-488">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-488">Pattern</span></span>

<span data-ttu-id="e1743-489">一個數字或字母 （不區分大小寫） 後尾隨七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e1743-490">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-490">Checksum</span></span>

<span data-ttu-id="e1743-491">否</span><span class="sxs-lookup"><span data-stu-id="e1743-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-492">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-492">Definition</span></span>

<span data-ttu-id="e1743-493">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-494">規則運算式`Regex_slovakia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-495">從關鍵字`Keywords_slovakia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-496">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-496">Keywords</span></span>

<span data-ttu-id="e1743-497">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-497"></span></span>
|<span data-ttu-id="e1743-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-499">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-499">passport number</span></span>  <br/> <span data-ttu-id="e1743-500">斯洛伐克護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="e1743-501">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-501">passport no</span></span>  <br/> <span data-ttu-id="e1743-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="e1743-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="e1743-503">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="e1743-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="e1743-504">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-504">Format</span></span>

<span data-ttu-id="e1743-505">兩個字母後尾隨七位數後不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-506">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-506">Pattern</span></span>

<span data-ttu-id="e1743-507">兩個字母後尾隨七位數：</span><span class="sxs-lookup"><span data-stu-id="e1743-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="e1743-508">字母"P"</span><span class="sxs-lookup"><span data-stu-id="e1743-508">The letter "P"</span></span>
    
- <span data-ttu-id="e1743-509">一個大寫字母</span><span class="sxs-lookup"><span data-stu-id="e1743-509">One uppercase letter</span></span>
    
- <span data-ttu-id="e1743-510">七位數</span><span class="sxs-lookup"><span data-stu-id="e1743-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e1743-511">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-511">Checksum</span></span>

<span data-ttu-id="e1743-512">否</span><span class="sxs-lookup"><span data-stu-id="e1743-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-513">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-513">Definition</span></span>

<span data-ttu-id="e1743-514">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-515">規則運算式`Regex_slovenia_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-516">從關鍵字`Keywords_slovenia_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-517">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-517">Keywords</span></span>

<span data-ttu-id="e1743-518">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-518"></span></span>
|<span data-ttu-id="e1743-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-520">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-520">passport number</span></span>  <br/> <span data-ttu-id="e1743-521">斯洛維尼亞文護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="e1743-522">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-522">passport no</span></span>  <br/> <span data-ttu-id="e1743-523">Številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="e1743-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="e1743-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="e1743-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="e1743-525">格式</span><span class="sxs-lookup"><span data-stu-id="e1743-525">Format</span></span>

<span data-ttu-id="e1743-526">八個或九個字元組合的字母和數字不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="e1743-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e1743-527">模式</span><span class="sxs-lookup"><span data-stu-id="e1743-527">Pattern</span></span>

<span data-ttu-id="e1743-528">字母和數字 8 或九個字元組合：</span><span class="sxs-lookup"><span data-stu-id="e1743-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="e1743-529">兩個數字或字母</span><span class="sxs-lookup"><span data-stu-id="e1743-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="e1743-530">一個數字或字母 （選用）</span><span class="sxs-lookup"><span data-stu-id="e1743-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="e1743-531">六位數</span><span class="sxs-lookup"><span data-stu-id="e1743-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e1743-532">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="e1743-532">Checksum</span></span>

<span data-ttu-id="e1743-533">不適用</span><span class="sxs-lookup"><span data-stu-id="e1743-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e1743-534">定義</span><span class="sxs-lookup"><span data-stu-id="e1743-534">Definition</span></span>

<span data-ttu-id="e1743-535">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="e1743-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e1743-536">規則運算式`Regex_spain_eu_passport_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="e1743-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e1743-537">從關鍵字`Keywords_spain_eu_passport_number`找到。</span><span class="sxs-lookup"><span data-stu-id="e1743-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e1743-538">關鍵字</span><span class="sxs-lookup"><span data-stu-id="e1743-538">Keywords</span></span>

<span data-ttu-id="e1743-539">| |</span><span class="sxs-lookup"><span data-stu-id="e1743-539"></span></span>
|<span data-ttu-id="e1743-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e1743-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e1743-541">passport</span><span class="sxs-lookup"><span data-stu-id="e1743-541">passport</span></span>  <br/> <span data-ttu-id="e1743-542">西班牙 passport</span><span class="sxs-lookup"><span data-stu-id="e1743-542">spain passport</span></span>  <br/> <span data-ttu-id="e1743-543">passport 活頁簿</span><span class="sxs-lookup"><span data-stu-id="e1743-543">passport book</span></span>  <br/> <span data-ttu-id="e1743-544">護照號碼</span><span class="sxs-lookup"><span data-stu-id="e1743-544">passport number</span></span>  <br/> <span data-ttu-id="e1743-545">passport 沒有</span><span class="sxs-lookup"><span data-stu-id="e1743-545">passport no</span></span>  <br/> <span data-ttu-id="e1743-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="e1743-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="e1743-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="e1743-547">número pasaporte</span></span>  <br/> <span data-ttu-id="e1743-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="e1743-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="e1743-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="e1743-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="e1743-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="e1743-550">Sweden</span></span>

<span data-ttu-id="e1743-551">如需詳細資訊，請參閱 「 瑞典護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e1743-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="e1743-552">英國</span><span class="sxs-lookup"><span data-stu-id="e1743-552">UK</span></span>

<span data-ttu-id="e1743-553">如需詳細資訊，請參閱 「 美國/英國的區段</span><span class="sxs-lookup"><span data-stu-id="e1743-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="e1743-554">護照號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e1743-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e1743-555">請參閱</span><span class="sxs-lookup"><span data-stu-id="e1743-555">See also</span></span>

[<span data-ttu-id="e1743-556">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="e1743-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

