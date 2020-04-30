---
title: 歐盟納稅識別號碼
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
description: 本主題顯示資料遺失防護（DLP）原則在偵測到歐盟納稅識別號碼機密資訊類型時所尋找的功能。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
ms.openlocfilehash: 5f779974266045d7099b599700c7168162d9d81e
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938669"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="62f7d-104">歐盟納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-104">EU Tax Identification Number</span></span>

<span data-ttu-id="62f7d-105">本主題說明資料遺失防護（DLP）原則在偵測到歐盟納稅識別號碼（TIN）機密資訊類型時，會尋找哪些專案。</span><span class="sxs-lookup"><span data-stu-id="62f7d-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="62f7d-106">這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。</span><span class="sxs-lookup"><span data-stu-id="62f7d-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="62f7d-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="62f7d-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-108">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-108">Format</span></span>

<span data-ttu-id="62f7d-109">具有選擇性連字號及正斜線的九位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-110">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-110">Pattern</span></span>

<span data-ttu-id="62f7d-111">具有選擇性連字號及正斜線的九位數：</span><span class="sxs-lookup"><span data-stu-id="62f7d-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="62f7d-112">兩位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-112">Two digits</span></span> 
    
- <span data-ttu-id="62f7d-113">連字號（選用）</span><span class="sxs-lookup"><span data-stu-id="62f7d-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="62f7d-114">三位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-114">Three digits</span></span>
    
- <span data-ttu-id="62f7d-115">一個正斜線（選用）</span><span class="sxs-lookup"><span data-stu-id="62f7d-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="62f7d-116">四位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-117">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-117">Checksum</span></span>

<span data-ttu-id="62f7d-118">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-119">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-119">Definition</span></span>

<span data-ttu-id="62f7d-120">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-121">函數`Func_austria_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-122">找到來自`Keywords_austria_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-123">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-124">函數`Func_austria_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-125">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="62f7d-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-127">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-127">tax number</span></span>
  
<span data-ttu-id="62f7d-128">number</span><span class="sxs-lookup"><span data-stu-id="62f7d-128">number</span></span>
  
<span data-ttu-id="62f7d-129">稅務登記編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-129">tax registration number</span></span>
  
<span data-ttu-id="62f7d-130">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-130">tax id</span></span>
  
<span data-ttu-id="62f7d-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="62f7d-131">st.nr.</span></span>
  
<span data-ttu-id="62f7d-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="62f7d-133">比利時</span><span class="sxs-lookup"><span data-stu-id="62f7d-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-134">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-134">Format</span></span>

<span data-ttu-id="62f7d-135">11位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-136">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-136">Pattern</span></span>

<span data-ttu-id="62f7d-137">11位數：</span><span class="sxs-lookup"><span data-stu-id="62f7d-137">11 digits:</span></span>
  
- <span data-ttu-id="62f7d-138">兩位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-138">Two digits</span></span>
    
- <span data-ttu-id="62f7d-139">"0" 或 "1"</span><span class="sxs-lookup"><span data-stu-id="62f7d-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="62f7d-140">一個數位</span><span class="sxs-lookup"><span data-stu-id="62f7d-140">One digit</span></span>
    
- <span data-ttu-id="62f7d-141">"0" 或 "1" 或 "2" 或 "3"</span><span class="sxs-lookup"><span data-stu-id="62f7d-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="62f7d-142">六位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-143">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-143">Checksum</span></span>

<span data-ttu-id="62f7d-144">不適用</span><span class="sxs-lookup"><span data-stu-id="62f7d-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-145">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-145">Definition</span></span>

<span data-ttu-id="62f7d-146">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-147">正則運算式`Regex_belgium_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-148">找到來自`Keywords_belgium_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="62f7d-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-151">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-151">tax number</span></span>
  
<span data-ttu-id="62f7d-152">國家註冊號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-152">national registration number</span></span>
  
<span data-ttu-id="62f7d-153">稅務登記編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-153">tax registration number</span></span>
  
<span data-ttu-id="62f7d-154">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-154">tax id</span></span>
  
<span data-ttu-id="62f7d-155">Nif</span><span class="sxs-lookup"><span data-stu-id="62f7d-155">nif</span></span>
  
<span data-ttu-id="62f7d-156">Nif#</span><span class="sxs-lookup"><span data-stu-id="62f7d-156">nif#</span></span>
  
<span data-ttu-id="62f7d-157">numéro de registre （本國）</span><span class="sxs-lookup"><span data-stu-id="62f7d-157">numéro de registre national</span></span>
  
<span data-ttu-id="62f7d-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="62f7d-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="62f7d-159">保加利亞</span><span class="sxs-lookup"><span data-stu-id="62f7d-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-160">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-160">Format</span></span>

<span data-ttu-id="62f7d-161">10位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-162">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-162">Pattern</span></span>

<span data-ttu-id="62f7d-163">10位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62f7d-164">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-164">Checksum</span></span>

<span data-ttu-id="62f7d-165">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-166">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-166">Definition</span></span>

<span data-ttu-id="62f7d-167">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-168">函數`Func_bulgaria_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-169">找到來自`Keywords_bulgaria_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-170">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-171">函數`Func_bulgaria_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-172">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="62f7d-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-174">bucn</span><span class="sxs-lookup"><span data-stu-id="62f7d-174">bucn</span></span>
  
<span data-ttu-id="62f7d-175">統一的民事編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-175">uniform civil number</span></span>
  
<span data-ttu-id="62f7d-176">bucn#</span><span class="sxs-lookup"><span data-stu-id="62f7d-176">bucn#</span></span>
  
<span data-ttu-id="62f7d-177">uniformcivilnumber#</span><span class="sxs-lookup"><span data-stu-id="62f7d-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="62f7d-178">統一的民事識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-178">uniform civil id</span></span>
  
<span data-ttu-id="62f7d-179">統一的民事未</span><span class="sxs-lookup"><span data-stu-id="62f7d-179">uniform civil no</span></span>
  
<span data-ttu-id="62f7d-180">egn</span><span class="sxs-lookup"><span data-stu-id="62f7d-180">egn</span></span>
  
<span data-ttu-id="62f7d-181">保加利亞文統一民事號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="62f7d-182">uniformcivilno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-182">uniformcivilno#</span></span>
  
<span data-ttu-id="62f7d-183">egn#</span><span class="sxs-lookup"><span data-stu-id="62f7d-183">egn#</span></span>
  
<span data-ttu-id="62f7d-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="62f7d-184">униформ граждански номер</span></span>
  
<span data-ttu-id="62f7d-185">униформ識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-185">униформ id</span></span>
  
<span data-ttu-id="62f7d-186">униформграждански id</span><span class="sxs-lookup"><span data-stu-id="62f7d-186">униформ граждански id</span></span>
  
<span data-ttu-id="62f7d-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="62f7d-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="62f7d-188">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="62f7d-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-189">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-189">Format</span></span>

<span data-ttu-id="62f7d-190">11位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-191">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-191">Pattern</span></span>

<span data-ttu-id="62f7d-192">11位數：</span><span class="sxs-lookup"><span data-stu-id="62f7d-192">11 digits:</span></span>
  
- <span data-ttu-id="62f7d-193">10位數（隨機播放）</span><span class="sxs-lookup"><span data-stu-id="62f7d-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="62f7d-194">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-195">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-195">Checksum</span></span>

<span data-ttu-id="62f7d-196">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-197">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-197">Definition</span></span>

<span data-ttu-id="62f7d-198">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-199">函數`Func_croatia_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-200">找到來自`Keywords_croatia_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-201">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-202">函數`Func_croatia_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-203">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="62f7d-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-205">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-205">tax number</span></span>
  
<span data-ttu-id="62f7d-206">稅</span><span class="sxs-lookup"><span data-stu-id="62f7d-206">tax</span></span>
  
<span data-ttu-id="62f7d-207">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-207">tax id</span></span>
  
<span data-ttu-id="62f7d-208">OID</span><span class="sxs-lookup"><span data-stu-id="62f7d-208">oid</span></span>
  
<span data-ttu-id="62f7d-209">老#</span><span class="sxs-lookup"><span data-stu-id="62f7d-209">oid#</span></span>
  
<span data-ttu-id="62f7d-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="62f7d-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="62f7d-211">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="62f7d-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-212">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-212">Format</span></span>

<span data-ttu-id="62f7d-213">指定的模式中的八位數和一個字母</span><span class="sxs-lookup"><span data-stu-id="62f7d-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-214">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-214">Pattern</span></span>

<span data-ttu-id="62f7d-215">八位數和一個字母：</span><span class="sxs-lookup"><span data-stu-id="62f7d-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="62f7d-216">為 "0"</span><span class="sxs-lookup"><span data-stu-id="62f7d-216">A "0"</span></span> 
    
- <span data-ttu-id="62f7d-217">七位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-217">Seven digits</span></span>
    
- <span data-ttu-id="62f7d-218">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-219">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-219">Checksum</span></span>

<span data-ttu-id="62f7d-220">不適用</span><span class="sxs-lookup"><span data-stu-id="62f7d-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-221">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-221">Definition</span></span>

<span data-ttu-id="62f7d-222">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-223">函數`Func_cyprus_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-224">找到來自`Keywords_cyprus_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-225">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-226">函數`Func_cyprus_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="62f7d-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-229">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-229">tax number</span></span>
  
<span data-ttu-id="62f7d-230">稅</span><span class="sxs-lookup"><span data-stu-id="62f7d-230">tax</span></span>
  
<span data-ttu-id="62f7d-231">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-231">tax id</span></span>
  
<span data-ttu-id="62f7d-232">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-232">tax identification code</span></span>
  
<span data-ttu-id="62f7d-233">旅遊業 議會</span><span class="sxs-lookup"><span data-stu-id="62f7d-233">tic</span></span>
  
<span data-ttu-id="62f7d-234">旅遊業 議會#</span><span class="sxs-lookup"><span data-stu-id="62f7d-234">tic#</span></span>
  
<span data-ttu-id="62f7d-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="62f7d-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="62f7d-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="62f7d-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="62f7d-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="62f7d-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="62f7d-238">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="62f7d-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-239">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-239">Format</span></span>

<span data-ttu-id="62f7d-240">九位數和10位數（選用反斜線）</span><span class="sxs-lookup"><span data-stu-id="62f7d-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-241">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-241">Pattern</span></span>

<span data-ttu-id="62f7d-242">九位數或十位數，具有選用的 backslashl：</span><span class="sxs-lookup"><span data-stu-id="62f7d-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="62f7d-243">六位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-243">Six digits</span></span> 
    
- <span data-ttu-id="62f7d-244">反斜線（選用）</span><span class="sxs-lookup"><span data-stu-id="62f7d-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="62f7d-245">三位數或四位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-246">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-246">Checksum</span></span>

<span data-ttu-id="62f7d-247">不適用</span><span class="sxs-lookup"><span data-stu-id="62f7d-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-248">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-248">Definition</span></span>

<span data-ttu-id="62f7d-249">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-250">正則運算式`Regex_czech_republic_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-251">找到來自`Keywords_czech_republic_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="62f7d-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-254">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-254">tax number</span></span>
  
<span data-ttu-id="62f7d-255">稅</span><span class="sxs-lookup"><span data-stu-id="62f7d-255">tax</span></span>
  
<span data-ttu-id="62f7d-256">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-256">tax id</span></span>
  
<span data-ttu-id="62f7d-257">個人號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-257">personal number</span></span>
  
<span data-ttu-id="62f7d-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="62f7d-258">daňové číslo</span></span>
  
<span data-ttu-id="62f7d-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="62f7d-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="62f7d-260">丹麥</span><span class="sxs-lookup"><span data-stu-id="62f7d-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-261">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-261">Format</span></span>

<span data-ttu-id="62f7d-262">10位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="62f7d-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-263">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-263">Pattern</span></span>

<span data-ttu-id="62f7d-264">10位數包含 hyphenl：</span><span class="sxs-lookup"><span data-stu-id="62f7d-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="62f7d-265">與出生日期對應的六位數（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="62f7d-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="62f7d-266">連字號</span><span class="sxs-lookup"><span data-stu-id="62f7d-266">A hyphen</span></span>
    
- <span data-ttu-id="62f7d-267">四位數的數位，其中第一個數位對應到出生的世紀，最後一個數位對應于個人的性別（對男為奇數，甚至是女）。</span><span class="sxs-lookup"><span data-stu-id="62f7d-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-268">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-268">Checksum</span></span>

<span data-ttu-id="62f7d-269">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-270">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-270">Definition</span></span>

<span data-ttu-id="62f7d-271">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-272">函數`Func_denmark_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-273">找到來自`Keywords_denmark_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-274">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-275">函數`Func_denmark_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-276">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="62f7d-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-278">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-278">tax number</span></span>
  
<span data-ttu-id="62f7d-279">稅</span><span class="sxs-lookup"><span data-stu-id="62f7d-279">tax</span></span>
  
<span data-ttu-id="62f7d-280">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-280">tax id</span></span>
  
<span data-ttu-id="62f7d-281">cpr 編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-281">cpr number</span></span>
  
<span data-ttu-id="62f7d-282">Cpr#</span><span class="sxs-lookup"><span data-stu-id="62f7d-282">cpr#</span></span>
  
<span data-ttu-id="62f7d-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-283">skat nummer</span></span>
  
<span data-ttu-id="62f7d-284">skat 識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="62f7d-285">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="62f7d-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-286">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-286">Format</span></span>

<span data-ttu-id="62f7d-287">11位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-288">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-288">Pattern</span></span>

<span data-ttu-id="62f7d-289">11位數：</span><span class="sxs-lookup"><span data-stu-id="62f7d-289">11 digits:</span></span>
  
-  <span data-ttu-id="62f7d-290">一種對應到性別和世紀的數位，其奇數表示男和偶數表示女，如下所示：1，2代表19世紀;3，4代表20世紀;21世紀的5，6</span><span class="sxs-lookup"><span data-stu-id="62f7d-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="62f7d-291">對應至出生日期的六位數（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="62f7d-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="62f7d-292">三位數，對應至在相同日期出生的人員的序號</span><span class="sxs-lookup"><span data-stu-id="62f7d-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="62f7d-293">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-294">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-294">Checksum</span></span>

<span data-ttu-id="62f7d-295">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-296">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-296">Definition</span></span>

<span data-ttu-id="62f7d-297">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-298">函數`Func_estonia_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-299">找到來自`Keywords_estonia_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-300">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-301">函數`Func_estonia_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-302">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="62f7d-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-304">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-304">tax number</span></span>
  
<span data-ttu-id="62f7d-305">稅</span><span class="sxs-lookup"><span data-stu-id="62f7d-305">tax</span></span>
  
<span data-ttu-id="62f7d-306">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-306">tax id</span></span>
  
<span data-ttu-id="62f7d-307">個人程式碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-307">personal code</span></span>
  
<span data-ttu-id="62f7d-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="62f7d-308">maksunumber</span></span>
  
<span data-ttu-id="62f7d-309">maksu 識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-309">maksu id</span></span>
  
<span data-ttu-id="62f7d-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="62f7d-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="62f7d-311">芬蘭</span><span class="sxs-lookup"><span data-stu-id="62f7d-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-312">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-312">Format</span></span>

<span data-ttu-id="62f7d-313">一個11個字元的位數、字母和正負號組合</span><span class="sxs-lookup"><span data-stu-id="62f7d-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-314">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-314">Pattern</span></span>

<span data-ttu-id="62f7d-315">一個11個字元的位數、字母和正負號組合：</span><span class="sxs-lookup"><span data-stu-id="62f7d-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="62f7d-316">六位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-316">Six digits</span></span>
    
- <span data-ttu-id="62f7d-317">下列其中一項：加號、減號或字母 "A" （不區分大小寫），其中加號表示介於1800-1899 之間，減號表示出生于1900-1999，而 "A" 表示出生2000和之後</span><span class="sxs-lookup"><span data-stu-id="62f7d-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="62f7d-318">三位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-318">Three digits</span></span>
    
- <span data-ttu-id="62f7d-319">一個字母或一個數位</span><span class="sxs-lookup"><span data-stu-id="62f7d-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-320">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-320">Checksum</span></span>

<span data-ttu-id="62f7d-321">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-322">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-322">Definition</span></span>

<span data-ttu-id="62f7d-323">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-324">函數`Func_finland_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-325">找到來自`Keywords_finland_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-326">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-327">函數`Func_finland_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-328">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="62f7d-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-330">識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-330">identification number</span></span>
  
<span data-ttu-id="62f7d-331">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-331">personal id</span></span>
  
<span data-ttu-id="62f7d-332">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-332">identity number</span></span>
  
<span data-ttu-id="62f7d-333">芬蘭文身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-333">finnish national id number</span></span>
  
<span data-ttu-id="62f7d-334">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="62f7d-334">personalidnumber#</span></span>
  
<span data-ttu-id="62f7d-335">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-335">national identification number</span></span>
  
<span data-ttu-id="62f7d-336">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-336">id number</span></span>
  
<span data-ttu-id="62f7d-337">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-337">national id no.</span></span>
  
<span data-ttu-id="62f7d-338">本國識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-338">national id number</span></span>
  
<span data-ttu-id="62f7d-339">識別碼 no</span><span class="sxs-lookup"><span data-stu-id="62f7d-339">id no</span></span>
  
<span data-ttu-id="62f7d-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="62f7d-340">tunnistenumero</span></span>
  
<span data-ttu-id="62f7d-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="62f7d-341">henkilötunnus</span></span>
  
<span data-ttu-id="62f7d-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="62f7d-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="62f7d-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="62f7d-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="62f7d-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="62f7d-344">identiteetti numero</span></span>
  
<span data-ttu-id="62f7d-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="62f7d-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="62f7d-346">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="62f7d-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="62f7d-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="62f7d-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="62f7d-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="62f7d-348">tunnusnumero</span></span>
  
<span data-ttu-id="62f7d-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="62f7d-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="62f7d-350">法國</span><span class="sxs-lookup"><span data-stu-id="62f7d-350">France</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-351">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-351">Format</span></span>

<span data-ttu-id="62f7d-352">每個人13位數，實體的九位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-353">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-353">Pattern</span></span>

<span data-ttu-id="62f7d-354">個人13位數：</span><span class="sxs-lookup"><span data-stu-id="62f7d-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="62f7d-355">一個位數必須是0、1、2或3</span><span class="sxs-lookup"><span data-stu-id="62f7d-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="62f7d-356">12位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-356">12 digits</span></span>
    
<span data-ttu-id="62f7d-357">實體的九位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62f7d-358">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-358">Checksum</span></span>

<span data-ttu-id="62f7d-359">不適用</span><span class="sxs-lookup"><span data-stu-id="62f7d-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-360">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-360">Definition</span></span>

<span data-ttu-id="62f7d-361">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-362">函數`Func_france_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-363">找到來自`Keywords_france_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-364">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-365">函數`Func_france_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-366">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="62f7d-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-368">納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-368">tax identification number</span></span>
  
<span data-ttu-id="62f7d-369">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-369">tax number</span></span>
  
<span data-ttu-id="62f7d-370">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-370">tax id</span></span>
  
<span data-ttu-id="62f7d-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="62f7d-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="62f7d-372">德國</span><span class="sxs-lookup"><span data-stu-id="62f7d-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-373">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-373">Format</span></span>

<span data-ttu-id="62f7d-374">11位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-375">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-375">Pattern</span></span>

<span data-ttu-id="62f7d-376">11位數：</span><span class="sxs-lookup"><span data-stu-id="62f7d-376">11 digits :</span></span>
  
-  <span data-ttu-id="62f7d-377">10位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-377">Ten digits</span></span> 
    
- <span data-ttu-id="62f7d-378">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-379">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-379">Checksum</span></span>

<span data-ttu-id="62f7d-380">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-381">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-381">Definition</span></span>

<span data-ttu-id="62f7d-382">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-383">函數`Func_germany_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-384">找到來自`Keywords_germany_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-385">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-386">函數`Func_germany_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-387">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="62f7d-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-389">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-389">tax number</span></span>
  
<span data-ttu-id="62f7d-390">納稅編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-390">tax no.</span></span>
  
<span data-ttu-id="62f7d-391">taxno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-391">taxno#</span></span>
  
<span data-ttu-id="62f7d-392">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="62f7d-392">taxnumber#</span></span>
  
<span data-ttu-id="62f7d-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="62f7d-393">taxnumber</span></span>
  
<span data-ttu-id="62f7d-394">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-394">tax id</span></span>
  
<span data-ttu-id="62f7d-395">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-395">taxid#</span></span>
  
<span data-ttu-id="62f7d-396">納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-396">tax identification number</span></span>
  
<span data-ttu-id="62f7d-397">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-397">tax identification no.</span></span>
  
<span data-ttu-id="62f7d-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-398">steuernummer</span></span>
  
<span data-ttu-id="62f7d-399">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-399">steuer id</span></span>
  
<span data-ttu-id="62f7d-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="62f7d-401">希臘</span><span class="sxs-lookup"><span data-stu-id="62f7d-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-402">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-402">Format</span></span>

<span data-ttu-id="62f7d-403">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-404">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-404">Pattern</span></span>

<span data-ttu-id="62f7d-405">九位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62f7d-406">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-406">Checksum</span></span>

<span data-ttu-id="62f7d-407">不適用</span><span class="sxs-lookup"><span data-stu-id="62f7d-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-408">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-408">Definition</span></span>

<span data-ttu-id="62f7d-409">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-410">正則運算式`Regex_greece_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-411">找到來自`Keywords_greece_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-412">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="62f7d-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-414">Afm</span><span class="sxs-lookup"><span data-stu-id="62f7d-414">afm</span></span>
  
<span data-ttu-id="62f7d-415">錫</span><span class="sxs-lookup"><span data-stu-id="62f7d-415">tin</span></span>
  
<span data-ttu-id="62f7d-416">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-416">tax id no.</span></span>
  
<span data-ttu-id="62f7d-417">納稅識別碼否</span><span class="sxs-lookup"><span data-stu-id="62f7d-417">tax id no</span></span>
  
<span data-ttu-id="62f7d-418">納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-418">tax identification number</span></span>
  
<span data-ttu-id="62f7d-419">納稅登錄號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-419">tax registry number</span></span>
  
<span data-ttu-id="62f7d-420">納稅登錄編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-420">tax registry no.</span></span>
  
<span data-ttu-id="62f7d-421">Afm#</span><span class="sxs-lookup"><span data-stu-id="62f7d-421">afm#</span></span>
  
<span data-ttu-id="62f7d-422">錫#</span><span class="sxs-lookup"><span data-stu-id="62f7d-422">tin#</span></span>
  
<span data-ttu-id="62f7d-423">taxidno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-423">taxidno#</span></span>
  
<span data-ttu-id="62f7d-424">taxregistryno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-424">taxregistryno#</span></span>
  
<span data-ttu-id="62f7d-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="62f7d-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="62f7d-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="62f7d-426">aφμ</span></span>
  
<span data-ttu-id="62f7d-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="62f7d-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="62f7d-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="62f7d-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="62f7d-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="62f7d-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="62f7d-430">匈牙利</span><span class="sxs-lookup"><span data-stu-id="62f7d-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-431">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-431">Format</span></span>

<span data-ttu-id="62f7d-432">沒有空格或分隔符號的10位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-433">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-433">Pattern</span></span>

<span data-ttu-id="62f7d-434">10位數：</span><span class="sxs-lookup"><span data-stu-id="62f7d-434">Ten digits:</span></span>
  
-  <span data-ttu-id="62f7d-435">一個位數，必須是 "8"</span><span class="sxs-lookup"><span data-stu-id="62f7d-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="62f7d-436">代表日期01/01/1867 和個人出生日期之間的天數所對應的5位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="62f7d-437">三位數的值，對應于因有機會讓個別人出生于同一天所產生的數目</span><span class="sxs-lookup"><span data-stu-id="62f7d-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="62f7d-438">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-439">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-439">Checksum</span></span>

<span data-ttu-id="62f7d-440">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-441">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-441">Definition</span></span>

<span data-ttu-id="62f7d-442">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-443">函數`Func_hungary_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-444">找到來自`Keywords_hungary_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-445">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-446">函數`Func_hungary_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-447">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="62f7d-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-449">匈牙利文納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="62f7d-450">匈牙利文 tin</span><span class="sxs-lookup"><span data-stu-id="62f7d-450">hungarian tin</span></span>
  
<span data-ttu-id="62f7d-451">納稅識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-451">tax id number</span></span>
  
<span data-ttu-id="62f7d-452">加值稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-452">vat number</span></span>
  
<span data-ttu-id="62f7d-453">稅務授權單位否</span><span class="sxs-lookup"><span data-stu-id="62f7d-453">tax authority no</span></span>
  
<span data-ttu-id="62f7d-454">納稅識別碼納稅身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-454">tax id tax identity number</span></span>
  
<span data-ttu-id="62f7d-455">taxidnumber#</span><span class="sxs-lookup"><span data-stu-id="62f7d-455">taxidnumber#</span></span>
  
<span data-ttu-id="62f7d-456">錫#</span><span class="sxs-lookup"><span data-stu-id="62f7d-456">tin#</span></span>
  
<span data-ttu-id="62f7d-457">hungatiantin#</span><span class="sxs-lookup"><span data-stu-id="62f7d-457">hungatiantin#</span></span>
  
<span data-ttu-id="62f7d-458">納稅識別碼否</span><span class="sxs-lookup"><span data-stu-id="62f7d-458">tax identification no</span></span>
  
<span data-ttu-id="62f7d-459">taxidno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-459">taxidno#</span></span>
  
<span data-ttu-id="62f7d-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="62f7d-460">adóazonosító szám</span></span>
  
<span data-ttu-id="62f7d-461">adószám</span><span class="sxs-lookup"><span data-stu-id="62f7d-461">adószám</span></span>
  
<span data-ttu-id="62f7d-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="62f7d-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="62f7d-463">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="62f7d-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-464">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-464">Format</span></span>

<span data-ttu-id="62f7d-465">七位數後接字母，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-466">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-466">Pattern</span></span>

<span data-ttu-id="62f7d-467">七位數後接字母：</span><span class="sxs-lookup"><span data-stu-id="62f7d-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="62f7d-468">七位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-468">Seven digits</span></span> 
    
- <span data-ttu-id="62f7d-469">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-470">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-470">Checksum</span></span>

<span data-ttu-id="62f7d-471">不適用</span><span class="sxs-lookup"><span data-stu-id="62f7d-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-472">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-472">Definition</span></span>

<span data-ttu-id="62f7d-473">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-474">函數`Func_ireland_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-475">找到來自`Keywords_ireland_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-476">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-477">函數`Func_ireland_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="62f7d-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-480">公用服務否</span><span class="sxs-lookup"><span data-stu-id="62f7d-480">public service no</span></span>
  
<span data-ttu-id="62f7d-481">個人公開服務否</span><span class="sxs-lookup"><span data-stu-id="62f7d-481">personal public service no</span></span>
  
<span data-ttu-id="62f7d-482">pps 否</span><span class="sxs-lookup"><span data-stu-id="62f7d-482">pps no</span></span>
  
<span data-ttu-id="62f7d-483">個人服務否</span><span class="sxs-lookup"><span data-stu-id="62f7d-483">personal service no</span></span>
  
<span data-ttu-id="62f7d-484">pps 服務否</span><span class="sxs-lookup"><span data-stu-id="62f7d-484">pps service no</span></span>
  
<span data-ttu-id="62f7d-485">ppsno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-485">ppsno#</span></span>
  
<span data-ttu-id="62f7d-486">愛爾蘭 pps 否</span><span class="sxs-lookup"><span data-stu-id="62f7d-486">irish pps no</span></span>
  
<span data-ttu-id="62f7d-487">publicserviceno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-487">publicserviceno#</span></span>
  
<span data-ttu-id="62f7d-488">個人公開服務號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-488">personal public service number</span></span>
  
<span data-ttu-id="62f7d-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="62f7d-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="62f7d-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="62f7d-490">pps uimh</span></span>
  
<span data-ttu-id="62f7d-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="62f7d-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="62f7d-492">義大利</span><span class="sxs-lookup"><span data-stu-id="62f7d-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-493">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-493">Format</span></span>

<span data-ttu-id="62f7d-494">在指定的模式中有16個字母和數位</span><span class="sxs-lookup"><span data-stu-id="62f7d-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-495">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-495">Pattern</span></span>

<span data-ttu-id="62f7d-496">16個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="62f7d-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="62f7d-497">與系列名稱中的前三個雙子音相對應的三個字母</span><span class="sxs-lookup"><span data-stu-id="62f7d-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="62f7d-498">與名字中的第一個、第三個和第四個雙子音相對應的三個字母</span><span class="sxs-lookup"><span data-stu-id="62f7d-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="62f7d-499">與出生年份的最後一個數位相對應的兩位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="62f7d-500">對應至出生月份的一個數位（字母的使用字母順序），但是只會使用字母 A 到 E、H、L、M、P、P、R to T （即，一月份為 A，10月是 R）</span><span class="sxs-lookup"><span data-stu-id="62f7d-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="62f7d-501">兩位數，對應至出生的出生一天，40會新增至女生中，以區別于男生</span><span class="sxs-lookup"><span data-stu-id="62f7d-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="62f7d-502">對應至某人出生之 municipality 之特定區功能變數代碼的四位數（國家/地區的碼是用於國外國家/地區）。</span><span class="sxs-lookup"><span data-stu-id="62f7d-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="62f7d-503">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-504">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-504">Checksum</span></span>

<span data-ttu-id="62f7d-505">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-506">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-506">Definition</span></span>

<span data-ttu-id="62f7d-507">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-508">函數`Func_italy_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-509">找到來自`Keywords_italy_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-510">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-511">函數`Func_italy_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-512">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="62f7d-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-514">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-514">tax number</span></span>
  
<span data-ttu-id="62f7d-515">納稅編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-515">tax no.</span></span>
  
<span data-ttu-id="62f7d-516">taxno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-516">taxno#</span></span>
  
<span data-ttu-id="62f7d-517">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="62f7d-517">taxnumber#</span></span>
  
<span data-ttu-id="62f7d-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="62f7d-518">taxnumber</span></span>
  
<span data-ttu-id="62f7d-519">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-519">tax id</span></span>
  
<span data-ttu-id="62f7d-520">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-520">taxid#</span></span>
  
<span data-ttu-id="62f7d-521">會計代碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-521">fiscal code</span></span>
  
<span data-ttu-id="62f7d-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="62f7d-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="62f7d-523">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="62f7d-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-524">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-524">Format</span></span>

<span data-ttu-id="62f7d-525">11位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-526">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-526">Pattern</span></span>

<span data-ttu-id="62f7d-527">指定的模式中的11位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="62f7d-528">與出生日期相對應的六位數（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="62f7d-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="62f7d-529">對應至出生世紀的一個數位，其中 "0" 對應于19世紀，"1" 對應于20世紀，"2" 對應于21世紀。</span><span class="sxs-lookup"><span data-stu-id="62f7d-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="62f7d-530">四位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-531">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-531">Checksum</span></span>

<span data-ttu-id="62f7d-532">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-533">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-533">Definition</span></span>

<span data-ttu-id="62f7d-534">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-535">函數`Func_latvia_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-536">找到來自`Keywords_latvia_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-537">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-538">函數`Func_latvia_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-539">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="62f7d-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-541">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-541">tax number</span></span>
  
<span data-ttu-id="62f7d-542">納稅編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-542">tax no.</span></span>
  
<span data-ttu-id="62f7d-543">taxno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-543">taxno#</span></span>
  
<span data-ttu-id="62f7d-544">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="62f7d-544">taxnumber#</span></span>
  
<span data-ttu-id="62f7d-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="62f7d-545">taxnumber</span></span>
  
<span data-ttu-id="62f7d-546">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-546">tax id</span></span>
  
<span data-ttu-id="62f7d-547">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-547">taxid#</span></span>
  
<span data-ttu-id="62f7d-548">納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-548">tax identification number</span></span>
  
<span data-ttu-id="62f7d-549">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-549">tax identification no.</span></span>
  
<span data-ttu-id="62f7d-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="62f7d-550">nodokļa numurs</span></span>
  
<span data-ttu-id="62f7d-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="62f7d-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="62f7d-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="62f7d-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="62f7d-553">立陶宛</span><span class="sxs-lookup"><span data-stu-id="62f7d-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-554">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-554">Format</span></span>

<span data-ttu-id="62f7d-555">11位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-556">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-556">Pattern</span></span>

<span data-ttu-id="62f7d-557">11位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62f7d-558">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-558">Checksum</span></span>

<span data-ttu-id="62f7d-559">不適用</span><span class="sxs-lookup"><span data-stu-id="62f7d-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-560">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-560">Definition</span></span>

<span data-ttu-id="62f7d-561">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-562">函數`Func_lithuania_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-563">找到來自`Keywords_lithuania_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-564">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-565">函數`Func_lithuania_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-566">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="62f7d-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-568">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-568">tax number</span></span>
  
<span data-ttu-id="62f7d-569">納稅編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-569">tax no.</span></span>
  
<span data-ttu-id="62f7d-570">納稅否#</span><span class="sxs-lookup"><span data-stu-id="62f7d-570">tax no#</span></span>
  
<span data-ttu-id="62f7d-571">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="62f7d-571">taxnumber#</span></span>
  
<span data-ttu-id="62f7d-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="62f7d-572">taxnumber</span></span>
  
<span data-ttu-id="62f7d-573">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-573">tax id</span></span>
  
<span data-ttu-id="62f7d-574">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-574">taxid#</span></span>
  
<span data-ttu-id="62f7d-575">納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-575">tax identification number</span></span>
  
<span data-ttu-id="62f7d-576">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-576">tax identification no.</span></span>
  
<span data-ttu-id="62f7d-577">mokesčių識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-577">mokesčių id</span></span>
  
<span data-ttu-id="62f7d-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="62f7d-578">mokesčių numeris</span></span>
  
<span data-ttu-id="62f7d-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="62f7d-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="62f7d-580">盧森堡</span><span class="sxs-lookup"><span data-stu-id="62f7d-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-581">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-581">Format</span></span>

<span data-ttu-id="62f7d-582">13位數沒有空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-583">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-583">Pattern</span></span>

<span data-ttu-id="62f7d-584">13位數：</span><span class="sxs-lookup"><span data-stu-id="62f7d-584">13 digits:</span></span>
  
-  <span data-ttu-id="62f7d-585">11位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-585">11 digits</span></span> 
    
- <span data-ttu-id="62f7d-586">兩個檢查碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-587">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-587">Checksum</span></span>

<span data-ttu-id="62f7d-588">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-589">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-589">Definition</span></span>

<span data-ttu-id="62f7d-590">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-591">函數`Func_luxemburg_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-592">找到來自`Keywords_luxemburg_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-593">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-594">函數`Func_luxemburg_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-595">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="62f7d-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-597">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-597">tax number</span></span>
  
<span data-ttu-id="62f7d-598">納稅編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-598">tax no.</span></span>
  
<span data-ttu-id="62f7d-599">taxno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-599">taxno#</span></span>
  
<span data-ttu-id="62f7d-600">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="62f7d-600">taxnumber#</span></span>
  
<span data-ttu-id="62f7d-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="62f7d-601">taxnumber</span></span>
  
<span data-ttu-id="62f7d-602">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-602">tax id</span></span>
  
<span data-ttu-id="62f7d-603">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-603">taxid#</span></span>
  
<span data-ttu-id="62f7d-604">納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-604">tax identification number</span></span>
  
<span data-ttu-id="62f7d-605">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-605">tax identification no.</span></span>
  
<span data-ttu-id="62f7d-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-606">steuernummer</span></span>
  
<span data-ttu-id="62f7d-607">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-607">steuer id</span></span>
  
<span data-ttu-id="62f7d-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="62f7d-609">馬爾他</span><span class="sxs-lookup"><span data-stu-id="62f7d-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-610">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-610">Format</span></span>

<span data-ttu-id="62f7d-611">在馬爾他 nationals 中：7位數和指定的模式中的一個字母</span><span class="sxs-lookup"><span data-stu-id="62f7d-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="62f7d-612">非馬爾他 nationals 及馬爾他式實體：9位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-613">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-613">Pattern</span></span>

<span data-ttu-id="62f7d-614">馬爾他 nationals：7位數和一個字母</span><span class="sxs-lookup"><span data-stu-id="62f7d-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="62f7d-615">七位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-615">Seven digits</span></span> 
    
- <span data-ttu-id="62f7d-616">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="62f7d-617">非馬爾他 nationals 及馬爾他式實體：9位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="62f7d-618">九位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="62f7d-619">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-619">Checksum</span></span>

<span data-ttu-id="62f7d-620">不適用</span><span class="sxs-lookup"><span data-stu-id="62f7d-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-621">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-621">Definition</span></span>

<span data-ttu-id="62f7d-622">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-623">函數`Func_malta_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-624">找到來自`Keywords_malta_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-625">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-626">函數`Func_malta_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-627">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="62f7d-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-629">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-629">tax number</span></span>
  
<span data-ttu-id="62f7d-630">納稅編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-630">tax no.</span></span>
  
<span data-ttu-id="62f7d-631">taxno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-631">taxno#</span></span>
  
<span data-ttu-id="62f7d-632">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="62f7d-632">taxnumber#</span></span>
  
<span data-ttu-id="62f7d-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="62f7d-633">taxnumber</span></span>
  
<span data-ttu-id="62f7d-634">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-634">tax id</span></span>
  
<span data-ttu-id="62f7d-635">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-635">taxid#</span></span>
  
<span data-ttu-id="62f7d-636">納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-636">tax identification number</span></span>
  
<span data-ttu-id="62f7d-637">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-637">tax identification no.</span></span>
  
<span data-ttu-id="62f7d-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="62f7d-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="62f7d-639">識別碼 tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="62f7d-639">id tat-taxxa</span></span>
  
<span data-ttu-id="62f7d-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="62f7d-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="62f7d-641">荷蘭</span><span class="sxs-lookup"><span data-stu-id="62f7d-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-642">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-642">Format</span></span>

<span data-ttu-id="62f7d-643">九位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-644">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-644">Pattern</span></span>

<span data-ttu-id="62f7d-645">九位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="62f7d-646">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-646">Checksum</span></span>

<span data-ttu-id="62f7d-647">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-648">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-648">Definition</span></span>

<span data-ttu-id="62f7d-649">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-650">函數`Func_netherlands_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-651">找到來自`Keywords_netherlands_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-652">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-653">函數`Func_netherlands_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-654">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="62f7d-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-656">荷蘭稅務識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="62f7d-657">荷蘭稅務識別</span><span class="sxs-lookup"><span data-stu-id="62f7d-657">netherlands tax identification</span></span>
  
<span data-ttu-id="62f7d-658">netherland 的納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="62f7d-659">netherland 的納稅識別</span><span class="sxs-lookup"><span data-stu-id="62f7d-659">netherland's tax identification</span></span>
  
<span data-ttu-id="62f7d-660">納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-660">tax identification number</span></span>
  
<span data-ttu-id="62f7d-661">荷蘭稅號</span><span class="sxs-lookup"><span data-stu-id="62f7d-661">dutch tax id</span></span>
  
<span data-ttu-id="62f7d-662">荷蘭稅務識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-662">dutch tax identification number</span></span>
  
<span data-ttu-id="62f7d-663">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-663">tax id</span></span>
  
<span data-ttu-id="62f7d-664">納稅識別碼#</span><span class="sxs-lookup"><span data-stu-id="62f7d-664">tax id#</span></span>
  
<span data-ttu-id="62f7d-665">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-665">tax number</span></span>
  
<span data-ttu-id="62f7d-666">納稅否#</span><span class="sxs-lookup"><span data-stu-id="62f7d-666">tax no#</span></span>
  
<span data-ttu-id="62f7d-667">稅#</span><span class="sxs-lookup"><span data-stu-id="62f7d-667">tax#</span></span>
  
<span data-ttu-id="62f7d-668">錫</span><span class="sxs-lookup"><span data-stu-id="62f7d-668">tin</span></span>
  
<span data-ttu-id="62f7d-669">錫#</span><span class="sxs-lookup"><span data-stu-id="62f7d-669">tin#</span></span>
  
<span data-ttu-id="62f7d-670">荷屬安的納稅人</span><span class="sxs-lookup"><span data-stu-id="62f7d-670">netherlands tin</span></span>
  
<span data-ttu-id="62f7d-671">netherland 的納稅人標識號</span><span class="sxs-lookup"><span data-stu-id="62f7d-671">netherland's tin</span></span>
  
<span data-ttu-id="62f7d-672">nederlands belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="62f7d-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="62f7d-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="62f7d-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="62f7d-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="62f7d-675">nederlands belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="62f7d-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="62f7d-676">nederlands belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="62f7d-677">nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="62f7d-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-678">btw nummer</span></span>
  
<span data-ttu-id="62f7d-679">nederlandse belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="62f7d-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="62f7d-680">波蘭</span><span class="sxs-lookup"><span data-stu-id="62f7d-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-681">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-681">Format</span></span>

<span data-ttu-id="62f7d-682">不含空格或分隔符號的11位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-683">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-683">Pattern</span></span>

<span data-ttu-id="62f7d-684">11位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62f7d-685">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-685">Checksum</span></span>

<span data-ttu-id="62f7d-686">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-687">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-687">Definition</span></span>

<span data-ttu-id="62f7d-688">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-689">函數`Func_poland_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-690">找到來自`Keywords_poland_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-691">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-692">函數`Func_poland_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-693">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="62f7d-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-695">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-695">tax number</span></span>
  
<span data-ttu-id="62f7d-696">納稅編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-696">tax no.</span></span>
  
<span data-ttu-id="62f7d-697">taxno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-697">taxno#</span></span>
  
<span data-ttu-id="62f7d-698">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="62f7d-698">taxnumber#</span></span>
  
<span data-ttu-id="62f7d-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="62f7d-699">taxnumber</span></span>
  
<span data-ttu-id="62f7d-700">咬</span><span class="sxs-lookup"><span data-stu-id="62f7d-700">nip</span></span>
  
<span data-ttu-id="62f7d-701">咬#</span><span class="sxs-lookup"><span data-stu-id="62f7d-701">nip#</span></span>
  
<span data-ttu-id="62f7d-702">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-702">tax id</span></span>
  
<span data-ttu-id="62f7d-703">納稅識別碼#</span><span class="sxs-lookup"><span data-stu-id="62f7d-703">tax id#</span></span>
  
<span data-ttu-id="62f7d-704">nip 識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-704">nip id</span></span>
  
<span data-ttu-id="62f7d-705">nip 識別碼#</span><span class="sxs-lookup"><span data-stu-id="62f7d-705">nip id#</span></span>
  
<span data-ttu-id="62f7d-706">納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-706">tax identification number</span></span>
  
<span data-ttu-id="62f7d-707">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-707">tax identification no.</span></span>
  
<span data-ttu-id="62f7d-708">加值稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-708">vat number</span></span>
  
<span data-ttu-id="62f7d-709">加值稅編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-709">vat no.</span></span>
  
<span data-ttu-id="62f7d-710">vatno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-710">vatno#</span></span>
  
<span data-ttu-id="62f7d-711">加值稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-711">vat id</span></span>
  
<span data-ttu-id="62f7d-712">加值稅識別碼#</span><span class="sxs-lookup"><span data-stu-id="62f7d-712">vat id#</span></span>
  
<span data-ttu-id="62f7d-713">轉寄 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="62f7d-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="62f7d-714">polski 轉寄 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="62f7d-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="62f7d-715">numeridentyfikacjipodatkowej#</span><span class="sxs-lookup"><span data-stu-id="62f7d-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="62f7d-716">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="62f7d-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-717">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-717">Format</span></span>

<span data-ttu-id="62f7d-718">九位數（沒有空格或分隔符號）</span><span class="sxs-lookup"><span data-stu-id="62f7d-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-719">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-719">Pattern</span></span>

<span data-ttu-id="62f7d-720">九位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62f7d-721">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-721">Checksum</span></span>

<span data-ttu-id="62f7d-722">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-723">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-723">Definition</span></span>

<span data-ttu-id="62f7d-724">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-725">函數`Func_portugal_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-726">找到來自`Keywords_portugal_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-727">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-728">函數`Func_portugal_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-729">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="62f7d-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-731">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-731">tax number</span></span>
  
<span data-ttu-id="62f7d-732">納稅編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-732">tax no.</span></span>
  
<span data-ttu-id="62f7d-733">taxno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-733">taxno#</span></span>
  
<span data-ttu-id="62f7d-734">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="62f7d-734">taxnumber#</span></span>
  
<span data-ttu-id="62f7d-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="62f7d-735">taxnumber</span></span>
  
<span data-ttu-id="62f7d-736">Nif</span><span class="sxs-lookup"><span data-stu-id="62f7d-736">nif</span></span>
  
<span data-ttu-id="62f7d-737">Nif#</span><span class="sxs-lookup"><span data-stu-id="62f7d-737">nif#</span></span>
  
<span data-ttu-id="62f7d-738">numero 會計</span><span class="sxs-lookup"><span data-stu-id="62f7d-738">numero fiscal</span></span>
  
<span data-ttu-id="62f7d-739">número de identificação 會計</span><span class="sxs-lookup"><span data-stu-id="62f7d-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="62f7d-740">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="62f7d-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-741">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-741">Format</span></span>

<span data-ttu-id="62f7d-742">13位數沒有空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-743">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-743">Pattern</span></span>

<span data-ttu-id="62f7d-744">13位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62f7d-745">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-745">Checksum</span></span>

<span data-ttu-id="62f7d-746">不適用</span><span class="sxs-lookup"><span data-stu-id="62f7d-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-747">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-747">Definition</span></span>

<span data-ttu-id="62f7d-748">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-749">正則運算式`Regex_romania_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-750">找到來自`Keywords_romania_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-751">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="62f7d-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-753">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-753">tax id</span></span>
  
<span data-ttu-id="62f7d-754">納稅識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-754">tax id number</span></span>
  
<span data-ttu-id="62f7d-755">納稅檔案編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-755">tax file no</span></span>
  
<span data-ttu-id="62f7d-756">稅收檔案編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-756">tax file number</span></span>
  
<span data-ttu-id="62f7d-757">納稅否</span><span class="sxs-lookup"><span data-stu-id="62f7d-757">tax no</span></span>
  
<span data-ttu-id="62f7d-758">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-758">tax number</span></span>
  
<span data-ttu-id="62f7d-759">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-759">taxid#</span></span>
  
<span data-ttu-id="62f7d-760">taxno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-760">taxno#</span></span>
  
<span data-ttu-id="62f7d-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="62f7d-761">id-ul taxei</span></span>
  
<span data-ttu-id="62f7d-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="62f7d-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="62f7d-763">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="62f7d-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-764">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-764">Format</span></span>

<span data-ttu-id="62f7d-765">10位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-766">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-766">Pattern</span></span>

<span data-ttu-id="62f7d-767">10位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62f7d-768">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-768">Checksum</span></span>

<span data-ttu-id="62f7d-769">不適用</span><span class="sxs-lookup"><span data-stu-id="62f7d-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-770">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-770">Definition</span></span>

<span data-ttu-id="62f7d-771">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-772">正則運算式`Regex_slovakia_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-773">找到來自`Keywords_slovakia_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-774">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="62f7d-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-776">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-776">tax id</span></span>
  
<span data-ttu-id="62f7d-777">納稅識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-777">tax id number</span></span>
  
<span data-ttu-id="62f7d-778">納稅人識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-778">tin id</span></span>
  
<span data-ttu-id="62f7d-779">tin no</span><span class="sxs-lookup"><span data-stu-id="62f7d-779">tin no</span></span>
  
<span data-ttu-id="62f7d-780">斯洛伐克納稅人識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-780">slovakian tin id</span></span>
  
<span data-ttu-id="62f7d-781">錫</span><span class="sxs-lookup"><span data-stu-id="62f7d-781">tin</span></span>
  
<span data-ttu-id="62f7d-782">納稅檔案編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-782">tax file no</span></span>
  
<span data-ttu-id="62f7d-783">稅收檔案編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-783">tax file number</span></span>
  
<span data-ttu-id="62f7d-784">納稅否</span><span class="sxs-lookup"><span data-stu-id="62f7d-784">tax no</span></span>
  
<span data-ttu-id="62f7d-785">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-785">tax number</span></span>
  
<span data-ttu-id="62f7d-786">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-786">taxid#</span></span>
  
<span data-ttu-id="62f7d-787">taxno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-787">taxno#</span></span>
  
<span data-ttu-id="62f7d-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="62f7d-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="62f7d-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="62f7d-789">daňové číslo</span></span>
  
<span data-ttu-id="62f7d-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="62f7d-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="62f7d-791">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="62f7d-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-792">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-792">Format</span></span>

<span data-ttu-id="62f7d-793">八位數沒有空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-794">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-794">Pattern</span></span>

<span data-ttu-id="62f7d-795">八位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62f7d-796">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-796">Checksum</span></span>

<span data-ttu-id="62f7d-797">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-798">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-798">Definition</span></span>

<span data-ttu-id="62f7d-799">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-800">函數`Func_slovenia_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-801">找到來自`Keywords_slovenia_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-802">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-803">函數`Func_slovenia_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-804">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="62f7d-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-806">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-806">tax id</span></span>
  
<span data-ttu-id="62f7d-807">納稅識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-807">tax id number</span></span>
  
<span data-ttu-id="62f7d-808">納稅人識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-808">tin id</span></span>
  
<span data-ttu-id="62f7d-809">tin no</span><span class="sxs-lookup"><span data-stu-id="62f7d-809">tin no</span></span>
  
<span data-ttu-id="62f7d-810">斯洛維尼亞納稅人識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-810">slovenian tin id</span></span>
  
<span data-ttu-id="62f7d-811">錫</span><span class="sxs-lookup"><span data-stu-id="62f7d-811">tin</span></span>
  
<span data-ttu-id="62f7d-812">納稅檔案編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-812">tax file no</span></span>
  
<span data-ttu-id="62f7d-813">稅收檔案編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-813">tax file number</span></span>
  
<span data-ttu-id="62f7d-814">納稅否</span><span class="sxs-lookup"><span data-stu-id="62f7d-814">tax no</span></span>
  
<span data-ttu-id="62f7d-815">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-815">tax number</span></span>
  
<span data-ttu-id="62f7d-816">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-816">taxid#</span></span>
  
<span data-ttu-id="62f7d-817">taxno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-817">taxno#</span></span>
  
<span data-ttu-id="62f7d-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="62f7d-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="62f7d-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="62f7d-819">davčna številka</span></span>
  
<span data-ttu-id="62f7d-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="62f7d-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="62f7d-821">西班牙</span><span class="sxs-lookup"><span data-stu-id="62f7d-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-822">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-822">Format</span></span>

<span data-ttu-id="62f7d-823">指定的模式中的7或8位數，以及一或兩個字母</span><span class="sxs-lookup"><span data-stu-id="62f7d-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-824">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-824">Pattern</span></span>

<span data-ttu-id="62f7d-825">具有西班牙國身分識別卡的西班牙文自然人員：</span><span class="sxs-lookup"><span data-stu-id="62f7d-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="62f7d-826">八位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-826">Eight digits</span></span> 
    
- <span data-ttu-id="62f7d-827">單一大寫字母（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="62f7d-828">沒有西班牙國身分身分身分識別卡的非居民 Spaniards</span><span class="sxs-lookup"><span data-stu-id="62f7d-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="62f7d-829">一個大寫字母 "L" （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="62f7d-830">七位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-830">Seven digits</span></span>
    
- <span data-ttu-id="62f7d-831">單一大寫字母（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="62f7d-832">在沒有西班牙國身分識別卡的14年年齡底下的居民 Spaniards：</span><span class="sxs-lookup"><span data-stu-id="62f7d-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="62f7d-833">一個大寫字母 "K" （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="62f7d-834">七位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-834">Seven digits</span></span> 
    
- <span data-ttu-id="62f7d-835">單一大寫字母（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="62f7d-836">Foreigners 與 Foreigner 的識別號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="62f7d-837">一個大寫的字母，為 "X"、"Y" 或 "Z" （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="62f7d-838">七位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-838">Seven digits</span></span>
    
- <span data-ttu-id="62f7d-839">單一大寫字母（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="62f7d-840">沒有 Foreigner 識別碼的 Foreigners</span><span class="sxs-lookup"><span data-stu-id="62f7d-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="62f7d-841">一個大寫的字母 "M" （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="62f7d-842">七位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-842">Seven digits</span></span>
    
- <span data-ttu-id="62f7d-843">單一大寫字母（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="62f7d-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="62f7d-844">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-844">Checksum</span></span>

<span data-ttu-id="62f7d-845">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-846">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-846">Definition</span></span>

<span data-ttu-id="62f7d-847">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-848">函數`Func_spain_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-849">找到來自`Keywords_spain_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-850">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-851">函數`Func_spain_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-852">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="62f7d-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-854">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-854">tax id</span></span>
  
<span data-ttu-id="62f7d-855">納稅識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-855">tax id number</span></span>
  
<span data-ttu-id="62f7d-856">cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-856">cif id</span></span>
  
<span data-ttu-id="62f7d-857">cif 否</span><span class="sxs-lookup"><span data-stu-id="62f7d-857">cif no</span></span>
  
<span data-ttu-id="62f7d-858">西班牙文 cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-858">spanish cif id</span></span>
  
<span data-ttu-id="62f7d-859">Cif</span><span class="sxs-lookup"><span data-stu-id="62f7d-859">cif</span></span>
  
<span data-ttu-id="62f7d-860">納稅檔案編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-860">tax file no</span></span>
  
<span data-ttu-id="62f7d-861">西班牙文 cif 編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-861">spanish cif number</span></span>
  
<span data-ttu-id="62f7d-862">稅收檔案編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-862">tax file number</span></span>
  
<span data-ttu-id="62f7d-863">西班牙文 cif 否</span><span class="sxs-lookup"><span data-stu-id="62f7d-863">spanish cif no</span></span>
  
<span data-ttu-id="62f7d-864">納稅否</span><span class="sxs-lookup"><span data-stu-id="62f7d-864">tax no</span></span>
  
<span data-ttu-id="62f7d-865">納稅號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-865">tax number</span></span>
  
<span data-ttu-id="62f7d-866">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-866">taxid#</span></span>
  
<span data-ttu-id="62f7d-867">taxno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-867">taxno#</span></span>
  
<span data-ttu-id="62f7d-868">cifid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-868">cifid#</span></span>
  
<span data-ttu-id="62f7d-869">spanishcifid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-869">spanishcifid#</span></span>
  
<span data-ttu-id="62f7d-870">spanishcifno#</span><span class="sxs-lookup"><span data-stu-id="62f7d-870">spanishcifno#</span></span>
  
<span data-ttu-id="62f7d-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="62f7d-871">número de contribuyente</span></span>
  
<span data-ttu-id="62f7d-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="62f7d-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="62f7d-873">número de identificación 會計</span><span class="sxs-lookup"><span data-stu-id="62f7d-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="62f7d-874">cif número</span><span class="sxs-lookup"><span data-stu-id="62f7d-874">cif número</span></span>
  
<span data-ttu-id="62f7d-875">cifnúmero#</span><span class="sxs-lookup"><span data-stu-id="62f7d-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="62f7d-876">瑞典</span><span class="sxs-lookup"><span data-stu-id="62f7d-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-877">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-877">Format</span></span>

<span data-ttu-id="62f7d-878">指定之模式中的10位數和符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-879">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-879">Pattern</span></span>

<span data-ttu-id="62f7d-880">10位數和符號：</span><span class="sxs-lookup"><span data-stu-id="62f7d-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="62f7d-881">與出生日期對應的六位數（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="62f7d-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="62f7d-882">正負號或反斜線</span><span class="sxs-lookup"><span data-stu-id="62f7d-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="62f7d-883">在下列情況下，識別號碼唯一的三位數：</span><span class="sxs-lookup"><span data-stu-id="62f7d-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="62f7d-884">若為1990之前所簽發的號碼，第七和第八位數識別出生的縣或對外出生的人員</span><span class="sxs-lookup"><span data-stu-id="62f7d-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="62f7d-885">第九個位置中的位數會以奇數為單位表示，甚至是對女的性別</span><span class="sxs-lookup"><span data-stu-id="62f7d-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="62f7d-886">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62f7d-887">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-887">Checksum</span></span>

<span data-ttu-id="62f7d-888">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-889">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-889">Definition</span></span>

<span data-ttu-id="62f7d-890">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-891">函數`Func_sweden_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-892">找到來自`Keywords_sweden_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62f7d-893">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-894">函數`Func_sweden_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-895">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="62f7d-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-897">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-897">tax id</span></span>
  
<span data-ttu-id="62f7d-898">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-898">tax id no.</span></span>
  
<span data-ttu-id="62f7d-899">納稅識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-899">tax id number</span></span>
  
<span data-ttu-id="62f7d-900">納稅識別</span><span class="sxs-lookup"><span data-stu-id="62f7d-900">tax identification</span></span>
  
<span data-ttu-id="62f7d-901">納稅識別#</span><span class="sxs-lookup"><span data-stu-id="62f7d-901">tax identification#</span></span>
  
<span data-ttu-id="62f7d-902">納稅編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-902">tax no.</span></span>
  
<span data-ttu-id="62f7d-903">稅#</span><span class="sxs-lookup"><span data-stu-id="62f7d-903">tax#</span></span>
  
<span data-ttu-id="62f7d-904">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-904">taxid#</span></span>
  
<span data-ttu-id="62f7d-905">納稅檔案</span><span class="sxs-lookup"><span data-stu-id="62f7d-905">tax file</span></span>
  
<span data-ttu-id="62f7d-906">納稅檔案編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-906">tax file no.</span></span>
  
<span data-ttu-id="62f7d-907">個人號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-907">personal id number</span></span>
  
<span data-ttu-id="62f7d-908">skatt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-908">skatt id nummer</span></span>
  
<span data-ttu-id="62f7d-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="62f7d-909">skatt identifikation</span></span>
  
<span data-ttu-id="62f7d-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="62f7d-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="62f7d-911">英國</span><span class="sxs-lookup"><span data-stu-id="62f7d-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="62f7d-912">格式</span><span class="sxs-lookup"><span data-stu-id="62f7d-912">Format</span></span>

<span data-ttu-id="62f7d-913">唯一的納稅人參考（UTR）：10位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="62f7d-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="62f7d-914">國家保險號碼（NINO）：如需詳細資訊，請參閱 section "英</span><span class="sxs-lookup"><span data-stu-id="62f7d-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="62f7d-915">「[機密資訊類型](what-the-sensitive-information-types-look-for.md)」所尋找的國家保險編號（NINO）。</span><span class="sxs-lookup"><span data-stu-id="62f7d-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62f7d-916">模式</span><span class="sxs-lookup"><span data-stu-id="62f7d-916">Pattern</span></span>

<span data-ttu-id="62f7d-917">唯一的納稅人參考（UTR）：10位數</span><span class="sxs-lookup"><span data-stu-id="62f7d-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="62f7d-918">國家保險號碼（NINO）：如需詳細資訊，請參閱 section "英</span><span class="sxs-lookup"><span data-stu-id="62f7d-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="62f7d-919">「[機密資訊類型](what-the-sensitive-information-types-look-for.md)」所尋找的國家保險編號（NINO）。</span><span class="sxs-lookup"><span data-stu-id="62f7d-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62f7d-920">校驗</span><span class="sxs-lookup"><span data-stu-id="62f7d-920">Checksum</span></span>

<span data-ttu-id="62f7d-921">是</span><span class="sxs-lookup"><span data-stu-id="62f7d-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62f7d-922">定義</span><span class="sxs-lookup"><span data-stu-id="62f7d-922">Definition</span></span>

<span data-ttu-id="62f7d-923">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="62f7d-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62f7d-924">函數`Func_uk_eu_tax_file_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="62f7d-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62f7d-925">找到來自`Keywords_uk_eu_tax_file_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="62f7d-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62f7d-926">關鍵字</span><span class="sxs-lookup"><span data-stu-id="62f7d-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="62f7d-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62f7d-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="62f7d-928">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-928">tax id</span></span>
  
<span data-ttu-id="62f7d-929">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-929">tax id no.</span></span>
  
<span data-ttu-id="62f7d-930">納稅識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="62f7d-930">tax id number</span></span>
  
<span data-ttu-id="62f7d-931">納稅識別</span><span class="sxs-lookup"><span data-stu-id="62f7d-931">tax identification</span></span>
  
<span data-ttu-id="62f7d-932">納稅識別#</span><span class="sxs-lookup"><span data-stu-id="62f7d-932">tax identification#</span></span>
  
<span data-ttu-id="62f7d-933">納稅編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-933">tax no.</span></span>
  
<span data-ttu-id="62f7d-934">稅#</span><span class="sxs-lookup"><span data-stu-id="62f7d-934">tax#</span></span>
  
<span data-ttu-id="62f7d-935">taxid#</span><span class="sxs-lookup"><span data-stu-id="62f7d-935">taxid#</span></span>
  
<span data-ttu-id="62f7d-936">納稅檔案</span><span class="sxs-lookup"><span data-stu-id="62f7d-936">tax file</span></span>
  
<span data-ttu-id="62f7d-937">納稅檔案編號</span><span class="sxs-lookup"><span data-stu-id="62f7d-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="62f7d-938">另請參閱</span><span class="sxs-lookup"><span data-stu-id="62f7d-938">See also</span></span>

[<span data-ttu-id="62f7d-939">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="62f7d-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

