---
title: 歐盟稅務識別碼
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟稅務識別號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: 0ee76fa46bb22b2754098d053ab769b862fdd3f2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805846"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="df32b-104">歐盟稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-104">EU Tax Identification Number</span></span>

<span data-ttu-id="df32b-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟稅務識別號碼 （錫） 敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="df32b-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="df32b-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="df32b-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="df32b-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="df32b-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="df32b-108">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-108">Format</span></span>

<span data-ttu-id="df32b-109">選擇性連字號和正斜線的九位數</span><span class="sxs-lookup"><span data-stu-id="df32b-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-110">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-110">Pattern</span></span>

<span data-ttu-id="df32b-111">選擇性連字號和正斜線的九位數：</span><span class="sxs-lookup"><span data-stu-id="df32b-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="df32b-112">兩位數</span><span class="sxs-lookup"><span data-stu-id="df32b-112">Two digits</span></span> 
    
- <span data-ttu-id="df32b-113">連字號 （選用）</span><span class="sxs-lookup"><span data-stu-id="df32b-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="df32b-114">三位數</span><span class="sxs-lookup"><span data-stu-id="df32b-114">Three digits</span></span>
    
- <span data-ttu-id="df32b-115">正斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="df32b-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="df32b-116">四位數</span><span class="sxs-lookup"><span data-stu-id="df32b-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-117">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-117">Checksum</span></span>

<span data-ttu-id="df32b-118">是</span><span class="sxs-lookup"><span data-stu-id="df32b-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-119">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-119">Definition</span></span>

<span data-ttu-id="df32b-120">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-121">函式`Func_austria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-122">從關鍵字`Keywords_austria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-123">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-124">函式`Func_austria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-125">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="df32b-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-127">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-127">tax number</span></span>
  
<span data-ttu-id="df32b-128">number</span><span class="sxs-lookup"><span data-stu-id="df32b-128">number</span></span>
  
<span data-ttu-id="df32b-129">稅務登記號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-129">tax registration number</span></span>
  
<span data-ttu-id="df32b-130">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-130">tax id</span></span>
  
<span data-ttu-id="df32b-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="df32b-131">st.nr.</span></span>
  
<span data-ttu-id="df32b-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="df32b-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="df32b-133">比利時</span><span class="sxs-lookup"><span data-stu-id="df32b-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="df32b-134">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-134">Format</span></span>

<span data-ttu-id="df32b-135">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="df32b-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-136">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-136">Pattern</span></span>

<span data-ttu-id="df32b-137">11 位數：</span><span class="sxs-lookup"><span data-stu-id="df32b-137">11 digits:</span></span>
  
- <span data-ttu-id="df32b-138">兩位數</span><span class="sxs-lookup"><span data-stu-id="df32b-138">Two digits</span></span>
    
- <span data-ttu-id="df32b-139">「 0 」 或者 「 1 」</span><span class="sxs-lookup"><span data-stu-id="df32b-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="df32b-140">一位數</span><span class="sxs-lookup"><span data-stu-id="df32b-140">One digit</span></span>
    
- <span data-ttu-id="df32b-141">"0"或"1"或"2"或者"3"</span><span class="sxs-lookup"><span data-stu-id="df32b-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="df32b-142">六位數</span><span class="sxs-lookup"><span data-stu-id="df32b-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-143">Checksum</span></span>

<span data-ttu-id="df32b-144">不適用</span><span class="sxs-lookup"><span data-stu-id="df32b-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-145">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-145">Definition</span></span>

<span data-ttu-id="df32b-146">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-147">規則運算式`Regex_belgium_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-148">從關鍵字`Keywords_belgium_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="df32b-149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="df32b-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-151">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-151">tax number</span></span>
  
<span data-ttu-id="df32b-152">國民登記號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-152">national registration number</span></span>
  
<span data-ttu-id="df32b-153">稅務登記號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-153">tax registration number</span></span>
  
<span data-ttu-id="df32b-154">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-154">tax id</span></span>
  
<span data-ttu-id="df32b-155">n 如果</span><span class="sxs-lookup"><span data-stu-id="df32b-155">nif</span></span>
  
<span data-ttu-id="df32b-156">n 如果#</span><span class="sxs-lookup"><span data-stu-id="df32b-156">nif#</span></span>
  
<span data-ttu-id="df32b-157">numéro de registre 國際電話</span><span class="sxs-lookup"><span data-stu-id="df32b-157">numéro de registre national</span></span>
  
<span data-ttu-id="df32b-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="df32b-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="df32b-159">保加利亞</span><span class="sxs-lookup"><span data-stu-id="df32b-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="df32b-160">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-160">Format</span></span>

<span data-ttu-id="df32b-161">如果沒有空格和分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="df32b-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-162">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-162">Pattern</span></span>

<span data-ttu-id="df32b-163">10 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="df32b-164">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-164">Checksum</span></span>

<span data-ttu-id="df32b-165">是</span><span class="sxs-lookup"><span data-stu-id="df32b-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-166">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-166">Definition</span></span>

<span data-ttu-id="df32b-167">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-168">函式`Func_bulgaria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-169">從關鍵字`Keywords_bulgaria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-170">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-171">函式`Func_bulgaria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-172">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="df32b-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-174">bucn</span><span class="sxs-lookup"><span data-stu-id="df32b-174">bucn</span></span>
  
<span data-ttu-id="df32b-175">統一民事數目</span><span class="sxs-lookup"><span data-stu-id="df32b-175">uniform civil number</span></span>
  
<span data-ttu-id="df32b-176">bucn#</span><span class="sxs-lookup"><span data-stu-id="df32b-176">bucn#</span></span>
  
<span data-ttu-id="df32b-177">uniformcivilnumber#</span><span class="sxs-lookup"><span data-stu-id="df32b-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="df32b-178">統一民事識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-178">uniform civil id</span></span>
  
<span data-ttu-id="df32b-179">統一民事否</span><span class="sxs-lookup"><span data-stu-id="df32b-179">uniform civil no</span></span>
  
<span data-ttu-id="df32b-180">egn</span><span class="sxs-lookup"><span data-stu-id="df32b-180">egn</span></span>
  
<span data-ttu-id="df32b-181">保加利亞文統一民事數目</span><span class="sxs-lookup"><span data-stu-id="df32b-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="df32b-182">uniformcivilno#</span><span class="sxs-lookup"><span data-stu-id="df32b-182">uniformcivilno#</span></span>
  
<span data-ttu-id="df32b-183">egn#</span><span class="sxs-lookup"><span data-stu-id="df32b-183">egn#</span></span>
  
<span data-ttu-id="df32b-184">УНИФОРМ ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="df32b-184">униформ граждански номер</span></span>
  
<span data-ttu-id="df32b-185">Униформ 識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-185">униформ id</span></span>
  
<span data-ttu-id="df32b-186">Униформ граждански 識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-186">униформ граждански id</span></span>
  
<span data-ttu-id="df32b-187">УНИФОРМ ГРАЖДАНСКИ НЕ</span><span class="sxs-lookup"><span data-stu-id="df32b-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="df32b-188">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="df32b-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="df32b-189">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-189">Format</span></span>

<span data-ttu-id="df32b-190">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="df32b-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-191">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-191">Pattern</span></span>

<span data-ttu-id="df32b-192">11 位數：</span><span class="sxs-lookup"><span data-stu-id="df32b-192">11 digits:</span></span>
  
- <span data-ttu-id="df32b-193">十位數，隨機選擇</span><span class="sxs-lookup"><span data-stu-id="df32b-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="df32b-194">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-195">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-195">Checksum</span></span>

<span data-ttu-id="df32b-196">是</span><span class="sxs-lookup"><span data-stu-id="df32b-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-197">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-197">Definition</span></span>

<span data-ttu-id="df32b-198">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-199">函式`Func_croatia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-200">從關鍵字`Keywords_croatia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-201">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-202">函式`Func_croatia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-203">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="df32b-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-205">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-205">tax number</span></span>
  
<span data-ttu-id="df32b-206">稅務</span><span class="sxs-lookup"><span data-stu-id="df32b-206">tax</span></span>
  
<span data-ttu-id="df32b-207">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-207">tax id</span></span>
  
<span data-ttu-id="df32b-208">OID</span><span class="sxs-lookup"><span data-stu-id="df32b-208">oid</span></span>
  
<span data-ttu-id="df32b-209">oid#</span><span class="sxs-lookup"><span data-stu-id="df32b-209">oid#</span></span>
  
<span data-ttu-id="df32b-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="df32b-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="df32b-211">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="df32b-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="df32b-212">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-212">Format</span></span>

<span data-ttu-id="df32b-213">八位數與所指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="df32b-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-214">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-214">Pattern</span></span>

<span data-ttu-id="df32b-215">八位數和一個字母：</span><span class="sxs-lookup"><span data-stu-id="df32b-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="df32b-216">「 0 」</span><span class="sxs-lookup"><span data-stu-id="df32b-216">A "0"</span></span> 
    
- <span data-ttu-id="df32b-217">七位數</span><span class="sxs-lookup"><span data-stu-id="df32b-217">Seven digits</span></span>
    
- <span data-ttu-id="df32b-218">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-219">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-219">Checksum</span></span>

<span data-ttu-id="df32b-220">不適用</span><span class="sxs-lookup"><span data-stu-id="df32b-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-221">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-221">Definition</span></span>

<span data-ttu-id="df32b-222">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-223">函式`Func_cyprus_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-224">從關鍵字`Keywords_cyprus_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-225">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-226">函式`Func_cyprus_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="df32b-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-229">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-229">tax number</span></span>
  
<span data-ttu-id="df32b-230">稅務</span><span class="sxs-lookup"><span data-stu-id="df32b-230">tax</span></span>
  
<span data-ttu-id="df32b-231">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-231">tax id</span></span>
  
<span data-ttu-id="df32b-232">稅務識別程式碼</span><span class="sxs-lookup"><span data-stu-id="df32b-232">tax identification code</span></span>
  
<span data-ttu-id="df32b-233">tic</span><span class="sxs-lookup"><span data-stu-id="df32b-233">tic</span></span>
  
<span data-ttu-id="df32b-234">tic#</span><span class="sxs-lookup"><span data-stu-id="df32b-234">tic#</span></span>
  
<span data-ttu-id="df32b-235">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="df32b-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="df32b-236">ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="df32b-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="df32b-237">ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="df32b-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="df32b-238">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="df32b-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="df32b-239">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-239">Format</span></span>

<span data-ttu-id="df32b-240">具有選用反斜線的九個或十位數</span><span class="sxs-lookup"><span data-stu-id="df32b-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-241">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-241">Pattern</span></span>

<span data-ttu-id="df32b-242">具有選用 backslashl 九個或十位數：</span><span class="sxs-lookup"><span data-stu-id="df32b-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="df32b-243">六位數</span><span class="sxs-lookup"><span data-stu-id="df32b-243">Six digits</span></span> 
    
- <span data-ttu-id="df32b-244">反斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="df32b-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="df32b-245">三或四位數</span><span class="sxs-lookup"><span data-stu-id="df32b-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-246">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-246">Checksum</span></span>

<span data-ttu-id="df32b-247">不適用</span><span class="sxs-lookup"><span data-stu-id="df32b-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-248">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-248">Definition</span></span>

<span data-ttu-id="df32b-249">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-250">規則運算式`Regex_czech_republic_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-251">從關鍵字`Keywords_czech_republic_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="df32b-252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="df32b-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-254">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-254">tax number</span></span>
  
<span data-ttu-id="df32b-255">稅務</span><span class="sxs-lookup"><span data-stu-id="df32b-255">tax</span></span>
  
<span data-ttu-id="df32b-256">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-256">tax id</span></span>
  
<span data-ttu-id="df32b-257">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-257">personal number</span></span>
  
<span data-ttu-id="df32b-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="df32b-258">daňové číslo</span></span>
  
<span data-ttu-id="df32b-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="df32b-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="df32b-260">丹麥</span><span class="sxs-lookup"><span data-stu-id="df32b-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="df32b-261">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-261">Format</span></span>

<span data-ttu-id="df32b-262">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="df32b-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-263">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-263">Pattern</span></span>

<span data-ttu-id="df32b-264">10 位數包含 hyphenl:</span><span class="sxs-lookup"><span data-stu-id="df32b-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="df32b-265">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="df32b-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="df32b-266">連字號</span><span class="sxs-lookup"><span data-stu-id="df32b-266">A hyphen</span></span>
    
- <span data-ttu-id="df32b-267">會對應至其中的第一個數字會對應至的出生世紀序號的四位數，最後一個數字會對應至個別的性別 （如 1 女 2 男以及即使女性奇數）</span><span class="sxs-lookup"><span data-stu-id="df32b-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-268">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-268">Checksum</span></span>

<span data-ttu-id="df32b-269">是</span><span class="sxs-lookup"><span data-stu-id="df32b-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-270">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-270">Definition</span></span>

<span data-ttu-id="df32b-271">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-272">函式`Func_denmark_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-273">從關鍵字`Keywords_denmark_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-274">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-275">函式`Func_denmark_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-276">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="df32b-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-278">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-278">tax number</span></span>
  
<span data-ttu-id="df32b-279">稅務</span><span class="sxs-lookup"><span data-stu-id="df32b-279">tax</span></span>
  
<span data-ttu-id="df32b-280">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-280">tax id</span></span>
  
<span data-ttu-id="df32b-281">cpr 數目</span><span class="sxs-lookup"><span data-stu-id="df32b-281">cpr number</span></span>
  
<span data-ttu-id="df32b-282">cpr#</span><span class="sxs-lookup"><span data-stu-id="df32b-282">cpr#</span></span>
  
<span data-ttu-id="df32b-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="df32b-283">skat nummer</span></span>
  
<span data-ttu-id="df32b-284">skat 識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="df32b-285">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="df32b-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="df32b-286">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-286">Format</span></span>

<span data-ttu-id="df32b-287">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="df32b-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-288">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-288">Pattern</span></span>

<span data-ttu-id="df32b-289">11 位數：</span><span class="sxs-lookup"><span data-stu-id="df32b-289">11 digits:</span></span>
  
-  <span data-ttu-id="df32b-290">會對應至性別和世紀的出生其中奇數的數字表示 1 女 2 男並偶數指出女性，如下所示的一個數字： 1，2 代表 19 世紀;3、 4 20 的 century;5，6 第 21 世紀</span><span class="sxs-lookup"><span data-stu-id="df32b-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="df32b-291">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="df32b-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="df32b-292">會對應至分隔出生日期相同的人員序號的三位數</span><span class="sxs-lookup"><span data-stu-id="df32b-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="df32b-293">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-294">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-294">Checksum</span></span>

<span data-ttu-id="df32b-295">是</span><span class="sxs-lookup"><span data-stu-id="df32b-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-296">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-296">Definition</span></span>

<span data-ttu-id="df32b-297">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-298">函式`Func_estonia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-299">從關鍵字`Keywords_estonia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-300">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-301">函式`Func_estonia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-302">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="df32b-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-304">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-304">tax number</span></span>
  
<span data-ttu-id="df32b-305">稅務</span><span class="sxs-lookup"><span data-stu-id="df32b-305">tax</span></span>
  
<span data-ttu-id="df32b-306">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-306">tax id</span></span>
  
<span data-ttu-id="df32b-307">個人的程式碼</span><span class="sxs-lookup"><span data-stu-id="df32b-307">personal code</span></span>
  
<span data-ttu-id="df32b-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="df32b-308">maksunumber</span></span>
  
<span data-ttu-id="df32b-309">maksu 識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-309">maksu id</span></span>
  
<span data-ttu-id="df32b-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="df32b-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="df32b-311">芬蘭</span><span class="sxs-lookup"><span data-stu-id="df32b-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="df32b-312">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-312">Format</span></span>

<span data-ttu-id="df32b-313">字母的數字，11 個字元組合，以及加號與減號</span><span class="sxs-lookup"><span data-stu-id="df32b-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-314">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-314">Pattern</span></span>

<span data-ttu-id="df32b-315">字母的數字，11 個字元組合，以及加號與減號：</span><span class="sxs-lookup"><span data-stu-id="df32b-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="df32b-316">六位數</span><span class="sxs-lookup"><span data-stu-id="df32b-316">Six digits</span></span>
    
- <span data-ttu-id="df32b-317">下列其中之一： 加上加號、 減號或其中加號表示字母"A"（不區分大小寫） 之間 1800年 1899 年出生減號登入表示出生之間 1999 1900 年和"A"表示出生 2000年和之後</span><span class="sxs-lookup"><span data-stu-id="df32b-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="df32b-318">三位數</span><span class="sxs-lookup"><span data-stu-id="df32b-318">Three digits</span></span>
    
- <span data-ttu-id="df32b-319">一個字母或一個數字</span><span class="sxs-lookup"><span data-stu-id="df32b-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-320">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-320">Checksum</span></span>

<span data-ttu-id="df32b-321">是</span><span class="sxs-lookup"><span data-stu-id="df32b-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-322">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-322">Definition</span></span>

<span data-ttu-id="df32b-323">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-324">函式`Func_finland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-325">從關鍵字`Keywords_finland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-326">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-327">函式`Func_finland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-328">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="df32b-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-330">識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-330">identification number</span></span>
  
<span data-ttu-id="df32b-331">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-331">personal id</span></span>
  
<span data-ttu-id="df32b-332">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-332">identity number</span></span>
  
<span data-ttu-id="df32b-333">芬蘭國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-333">finnish national id number</span></span>
  
<span data-ttu-id="df32b-334">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="df32b-334">personalidnumber#</span></span>
  
<span data-ttu-id="df32b-335">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-335">national identification number</span></span>
  
<span data-ttu-id="df32b-336">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-336">id number</span></span>
  
<span data-ttu-id="df32b-337">國民身分證沒有。</span><span class="sxs-lookup"><span data-stu-id="df32b-337">national id no.</span></span>
  
<span data-ttu-id="df32b-338">國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-338">national id number</span></span>
  
<span data-ttu-id="df32b-339">識別碼不</span><span class="sxs-lookup"><span data-stu-id="df32b-339">id no</span></span>
  
<span data-ttu-id="df32b-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="df32b-340">tunnistenumero</span></span>
  
<span data-ttu-id="df32b-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="df32b-341">henkilötunnus</span></span>
  
<span data-ttu-id="df32b-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="df32b-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="df32b-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="df32b-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="df32b-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="df32b-344">identiteetti numero</span></span>
  
<span data-ttu-id="df32b-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="df32b-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="df32b-346">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="df32b-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="df32b-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="df32b-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="df32b-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="df32b-348">tunnusnumero</span></span>
  
<span data-ttu-id="df32b-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="df32b-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="df32b-350">法國</span><span class="sxs-lookup"><span data-stu-id="df32b-350">France</span></span>

### <a name="format"></a><span data-ttu-id="df32b-351">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-351">Format</span></span>

<span data-ttu-id="df32b-352">13 位數個人與實體的九位數</span><span class="sxs-lookup"><span data-stu-id="df32b-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-353">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-353">Pattern</span></span>

<span data-ttu-id="df32b-354">針對個人的 13 位數：</span><span class="sxs-lookup"><span data-stu-id="df32b-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="df32b-355">必須是 0、 1、 2 或 3 的一個數字</span><span class="sxs-lookup"><span data-stu-id="df32b-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="df32b-356">12 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-356">12 digits</span></span>
    
<span data-ttu-id="df32b-357">實體的九位數</span><span class="sxs-lookup"><span data-stu-id="df32b-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="df32b-358">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-358">Checksum</span></span>

<span data-ttu-id="df32b-359">不適用</span><span class="sxs-lookup"><span data-stu-id="df32b-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-360">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-360">Definition</span></span>

<span data-ttu-id="df32b-361">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-362">函式`Func_france_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-363">從關鍵字`Keywords_france_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-364">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-365">函式`Func_france_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-366">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="df32b-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-368">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-368">tax identification number</span></span>
  
<span data-ttu-id="df32b-369">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-369">tax number</span></span>
  
<span data-ttu-id="df32b-370">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-370">tax id</span></span>
  
<span data-ttu-id="df32b-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="df32b-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="df32b-372">德國</span><span class="sxs-lookup"><span data-stu-id="df32b-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="df32b-373">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-373">Format</span></span>

<span data-ttu-id="df32b-374">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="df32b-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-375">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-375">Pattern</span></span>

<span data-ttu-id="df32b-376">11 位數：</span><span class="sxs-lookup"><span data-stu-id="df32b-376">11 digits :</span></span>
  
-  <span data-ttu-id="df32b-377">十位數</span><span class="sxs-lookup"><span data-stu-id="df32b-377">Ten digits</span></span> 
    
- <span data-ttu-id="df32b-378">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-379">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-379">Checksum</span></span>

<span data-ttu-id="df32b-380">是</span><span class="sxs-lookup"><span data-stu-id="df32b-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-381">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-381">Definition</span></span>

<span data-ttu-id="df32b-382">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-383">函式`Func_germany_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-384">從關鍵字`Keywords_germany_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-385">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-386">函式`Func_germany_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-387">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="df32b-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-389">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-389">tax number</span></span>
  
<span data-ttu-id="df32b-390">稅務否。</span><span class="sxs-lookup"><span data-stu-id="df32b-390">tax no.</span></span>
  
<span data-ttu-id="df32b-391">taxno#</span><span class="sxs-lookup"><span data-stu-id="df32b-391">taxno#</span></span>
  
<span data-ttu-id="df32b-392">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="df32b-392">taxnumber#</span></span>
  
<span data-ttu-id="df32b-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="df32b-393">taxnumber</span></span>
  
<span data-ttu-id="df32b-394">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-394">tax id</span></span>
  
<span data-ttu-id="df32b-395">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-395">taxid#</span></span>
  
<span data-ttu-id="df32b-396">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-396">tax identification number</span></span>
  
<span data-ttu-id="df32b-397">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="df32b-397">tax identification no.</span></span>
  
<span data-ttu-id="df32b-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="df32b-398">steuernummer</span></span>
  
<span data-ttu-id="df32b-399">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-399">steuer id</span></span>
  
<span data-ttu-id="df32b-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="df32b-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="df32b-401">希臘</span><span class="sxs-lookup"><span data-stu-id="df32b-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="df32b-402">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-402">Format</span></span>

<span data-ttu-id="df32b-403">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="df32b-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-404">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-404">Pattern</span></span>

<span data-ttu-id="df32b-405">九位數</span><span class="sxs-lookup"><span data-stu-id="df32b-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="df32b-406">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-406">Checksum</span></span>

<span data-ttu-id="df32b-407">不適用</span><span class="sxs-lookup"><span data-stu-id="df32b-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-408">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-408">Definition</span></span>

<span data-ttu-id="df32b-409">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-410">規則運算式`Regex_greece_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-411">從關鍵字`Keywords_greece_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="df32b-412">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="df32b-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-414">afm</span><span class="sxs-lookup"><span data-stu-id="df32b-414">afm</span></span>
  
<span data-ttu-id="df32b-415">錫</span><span class="sxs-lookup"><span data-stu-id="df32b-415">tin</span></span>
  
<span data-ttu-id="df32b-416">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="df32b-416">tax id no.</span></span>
  
<span data-ttu-id="df32b-417">不稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-417">tax id no</span></span>
  
<span data-ttu-id="df32b-418">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-418">tax identification number</span></span>
  
<span data-ttu-id="df32b-419">稅務登錄編號</span><span class="sxs-lookup"><span data-stu-id="df32b-419">tax registry number</span></span>
  
<span data-ttu-id="df32b-420">不稅務登錄。</span><span class="sxs-lookup"><span data-stu-id="df32b-420">tax registry no.</span></span>
  
<span data-ttu-id="df32b-421">afm#</span><span class="sxs-lookup"><span data-stu-id="df32b-421">afm#</span></span>
  
<span data-ttu-id="df32b-422">錫#</span><span class="sxs-lookup"><span data-stu-id="df32b-422">tin#</span></span>
  
<span data-ttu-id="df32b-423">taxidno#</span><span class="sxs-lookup"><span data-stu-id="df32b-423">taxidno#</span></span>
  
<span data-ttu-id="df32b-424">taxregistryno#</span><span class="sxs-lookup"><span data-stu-id="df32b-424">taxregistryno#</span></span>
  
<span data-ttu-id="df32b-425">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="df32b-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="df32b-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="df32b-426">aφμ</span></span>
  
<span data-ttu-id="df32b-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="df32b-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="df32b-428">ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。</span><span class="sxs-lookup"><span data-stu-id="df32b-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="df32b-429">ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="df32b-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="df32b-430">匈牙利</span><span class="sxs-lookup"><span data-stu-id="df32b-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="df32b-431">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-431">Format</span></span>

<span data-ttu-id="df32b-432">不含空格或分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="df32b-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-433">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-433">Pattern</span></span>

<span data-ttu-id="df32b-434">十位數：</span><span class="sxs-lookup"><span data-stu-id="df32b-434">Ten digits:</span></span>
  
-  <span data-ttu-id="df32b-435">必須是"8"的一個數字</span><span class="sxs-lookup"><span data-stu-id="df32b-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="df32b-436">會對應至日期之間的天數的五位數 01/01/1867年和個別的出生日期</span><span class="sxs-lookup"><span data-stu-id="df32b-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="df32b-437">會對應至數來區分個人在同一天出生巧產生的三位數</span><span class="sxs-lookup"><span data-stu-id="df32b-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="df32b-438">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-439">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-439">Checksum</span></span>

<span data-ttu-id="df32b-440">是</span><span class="sxs-lookup"><span data-stu-id="df32b-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-441">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-441">Definition</span></span>

<span data-ttu-id="df32b-442">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-443">函式`Func_hungary_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-444">從關鍵字`Keywords_hungary_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-445">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-446">函式`Func_hungary_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-447">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="df32b-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-449">匈牙利文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="df32b-450">匈牙利文錫</span><span class="sxs-lookup"><span data-stu-id="df32b-450">hungarian tin</span></span>
  
<span data-ttu-id="df32b-451">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-451">tax id number</span></span>
  
<span data-ttu-id="df32b-452">vat 編號</span><span class="sxs-lookup"><span data-stu-id="df32b-452">vat number</span></span>
  
<span data-ttu-id="df32b-453">不稅務授權單位</span><span class="sxs-lookup"><span data-stu-id="df32b-453">tax authority no</span></span>
  
<span data-ttu-id="df32b-454">稅務識別碼稅務身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-454">tax id tax identity number</span></span>
  
<span data-ttu-id="df32b-455">taxidnumber#</span><span class="sxs-lookup"><span data-stu-id="df32b-455">taxidnumber#</span></span>
  
<span data-ttu-id="df32b-456">錫#</span><span class="sxs-lookup"><span data-stu-id="df32b-456">tin#</span></span>
  
<span data-ttu-id="df32b-457">hungatiantin#</span><span class="sxs-lookup"><span data-stu-id="df32b-457">hungatiantin#</span></span>
  
<span data-ttu-id="df32b-458">不稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-458">tax identification no</span></span>
  
<span data-ttu-id="df32b-459">taxidno#</span><span class="sxs-lookup"><span data-stu-id="df32b-459">taxidno#</span></span>
  
<span data-ttu-id="df32b-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="df32b-460">adóazonosító szám</span></span>
  
<span data-ttu-id="df32b-461">adószám</span><span class="sxs-lookup"><span data-stu-id="df32b-461">adószám</span></span>
  
<span data-ttu-id="df32b-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="df32b-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="df32b-463">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="df32b-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="df32b-464">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-464">Format</span></span>

<span data-ttu-id="df32b-465">七位數後尾隨不含空格或分隔符號的字母</span><span class="sxs-lookup"><span data-stu-id="df32b-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-466">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-466">Pattern</span></span>

<span data-ttu-id="df32b-467">七位數後尾隨字母：</span><span class="sxs-lookup"><span data-stu-id="df32b-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="df32b-468">七位數</span><span class="sxs-lookup"><span data-stu-id="df32b-468">Seven digits</span></span> 
    
- <span data-ttu-id="df32b-469">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-470">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-470">Checksum</span></span>

<span data-ttu-id="df32b-471">不適用</span><span class="sxs-lookup"><span data-stu-id="df32b-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-472">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-472">Definition</span></span>

<span data-ttu-id="df32b-473">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-474">函式`Func_ireland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-475">從關鍵字`Keywords_ireland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-476">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-477">函式`Func_ireland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="df32b-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-480">公用服務沒有</span><span class="sxs-lookup"><span data-stu-id="df32b-480">public service no</span></span>
  
<span data-ttu-id="df32b-481">個人公用服務沒有</span><span class="sxs-lookup"><span data-stu-id="df32b-481">personal public service no</span></span>
  
<span data-ttu-id="df32b-482">pps 沒有</span><span class="sxs-lookup"><span data-stu-id="df32b-482">pps no</span></span>
  
<span data-ttu-id="df32b-483">個人服務否</span><span class="sxs-lookup"><span data-stu-id="df32b-483">personal service no</span></span>
  
<span data-ttu-id="df32b-484">pps service 否</span><span class="sxs-lookup"><span data-stu-id="df32b-484">pps service no</span></span>
  
<span data-ttu-id="df32b-485">ppsno#</span><span class="sxs-lookup"><span data-stu-id="df32b-485">ppsno#</span></span>
  
<span data-ttu-id="df32b-486">愛爾蘭 pps 沒有</span><span class="sxs-lookup"><span data-stu-id="df32b-486">irish pps no</span></span>
  
<span data-ttu-id="df32b-487">publicserviceno#</span><span class="sxs-lookup"><span data-stu-id="df32b-487">publicserviceno#</span></span>
  
<span data-ttu-id="df32b-488">個人公用服務號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-488">personal public service number</span></span>
  
<span data-ttu-id="df32b-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="df32b-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="df32b-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="df32b-490">pps uimh</span></span>
  
<span data-ttu-id="df32b-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="df32b-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="df32b-492">義大利</span><span class="sxs-lookup"><span data-stu-id="df32b-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="df32b-493">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-493">Format</span></span>

<span data-ttu-id="df32b-494">16 個字母和數字中指定的型態</span><span class="sxs-lookup"><span data-stu-id="df32b-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-495">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-495">Pattern</span></span>

<span data-ttu-id="df32b-496">16 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="df32b-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="df32b-497">會對應到前三個母音系列名稱中的三個字母</span><span class="sxs-lookup"><span data-stu-id="df32b-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="df32b-498">會對應至第一、 第三個和第四個的三個字母母音在名字</span><span class="sxs-lookup"><span data-stu-id="df32b-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="df32b-499">會對應至最後一位數的出生年份的兩位數</span><span class="sxs-lookup"><span data-stu-id="df32b-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="df32b-500">會對應至出生的月份的一個數字 — 字母可用依字母順序，但只字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （因此，一月是的而且年 10 月 R）</span><span class="sxs-lookup"><span data-stu-id="df32b-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="df32b-501">會對應至出生其中 40 加入的來區分從男生女生出生日期的月份日期的兩位數</span><span class="sxs-lookup"><span data-stu-id="df32b-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="df32b-502">會對應至特定出生人員 municipality 區域代碼的四位數 — 全國家/地區的代碼可用外部國家/地區</span><span class="sxs-lookup"><span data-stu-id="df32b-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="df32b-503">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-504">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-504">Checksum</span></span>

<span data-ttu-id="df32b-505">是</span><span class="sxs-lookup"><span data-stu-id="df32b-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-506">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-506">Definition</span></span>

<span data-ttu-id="df32b-507">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-508">函式`Func_italy_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-509">從關鍵字`Keywords_italy_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-510">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-511">函式`Func_italy_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-512">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="df32b-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-514">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-514">tax number</span></span>
  
<span data-ttu-id="df32b-515">稅務否。</span><span class="sxs-lookup"><span data-stu-id="df32b-515">tax no.</span></span>
  
<span data-ttu-id="df32b-516">taxno#</span><span class="sxs-lookup"><span data-stu-id="df32b-516">taxno#</span></span>
  
<span data-ttu-id="df32b-517">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="df32b-517">taxnumber#</span></span>
  
<span data-ttu-id="df32b-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="df32b-518">taxnumber</span></span>
  
<span data-ttu-id="df32b-519">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-519">tax id</span></span>
  
<span data-ttu-id="df32b-520">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-520">taxid#</span></span>
  
<span data-ttu-id="df32b-521">會計年度的程式碼</span><span class="sxs-lookup"><span data-stu-id="df32b-521">fiscal code</span></span>
  
<span data-ttu-id="df32b-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="df32b-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="df32b-523">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="df32b-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="df32b-524">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-524">Format</span></span>

<span data-ttu-id="df32b-525">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="df32b-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-526">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-526">Pattern</span></span>

<span data-ttu-id="df32b-527">11 位數，代表所指定模式</span><span class="sxs-lookup"><span data-stu-id="df32b-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="df32b-528">會對應至 (DDMMYY) 出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="df32b-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="df32b-529">會對應至的出生其中"0"會對應至 19 世紀"1"會對應至 20 世紀，，"2"會對應至第 21 世紀世紀的一個數字</span><span class="sxs-lookup"><span data-stu-id="df32b-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="df32b-530">四位數</span><span class="sxs-lookup"><span data-stu-id="df32b-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-531">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-531">Checksum</span></span>

<span data-ttu-id="df32b-532">是</span><span class="sxs-lookup"><span data-stu-id="df32b-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-533">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-533">Definition</span></span>

<span data-ttu-id="df32b-534">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-535">函式`Func_latvia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-536">從關鍵字`Keywords_latvia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-537">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-538">函式`Func_latvia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-539">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="df32b-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-541">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-541">tax number</span></span>
  
<span data-ttu-id="df32b-542">稅務否。</span><span class="sxs-lookup"><span data-stu-id="df32b-542">tax no.</span></span>
  
<span data-ttu-id="df32b-543">taxno#</span><span class="sxs-lookup"><span data-stu-id="df32b-543">taxno#</span></span>
  
<span data-ttu-id="df32b-544">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="df32b-544">taxnumber#</span></span>
  
<span data-ttu-id="df32b-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="df32b-545">taxnumber</span></span>
  
<span data-ttu-id="df32b-546">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-546">tax id</span></span>
  
<span data-ttu-id="df32b-547">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-547">taxid#</span></span>
  
<span data-ttu-id="df32b-548">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-548">tax identification number</span></span>
  
<span data-ttu-id="df32b-549">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="df32b-549">tax identification no.</span></span>
  
<span data-ttu-id="df32b-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="df32b-550">nodokļa numurs</span></span>
  
<span data-ttu-id="df32b-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="df32b-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="df32b-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="df32b-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="df32b-553">立陶宛</span><span class="sxs-lookup"><span data-stu-id="df32b-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="df32b-554">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-554">Format</span></span>

<span data-ttu-id="df32b-555">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="df32b-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-556">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-556">Pattern</span></span>

<span data-ttu-id="df32b-557">11 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="df32b-558">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-558">Checksum</span></span>

<span data-ttu-id="df32b-559">不適用</span><span class="sxs-lookup"><span data-stu-id="df32b-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-560">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-560">Definition</span></span>

<span data-ttu-id="df32b-561">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-562">函式`Func_lithuania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-563">從關鍵字`Keywords_lithuania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-564">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-565">函式`Func_lithuania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-566">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="df32b-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-568">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-568">tax number</span></span>
  
<span data-ttu-id="df32b-569">稅務否。</span><span class="sxs-lookup"><span data-stu-id="df32b-569">tax no.</span></span>
  
<span data-ttu-id="df32b-570">稅務否#</span><span class="sxs-lookup"><span data-stu-id="df32b-570">tax no#</span></span>
  
<span data-ttu-id="df32b-571">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="df32b-571">taxnumber#</span></span>
  
<span data-ttu-id="df32b-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="df32b-572">taxnumber</span></span>
  
<span data-ttu-id="df32b-573">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-573">tax id</span></span>
  
<span data-ttu-id="df32b-574">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-574">taxid#</span></span>
  
<span data-ttu-id="df32b-575">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-575">tax identification number</span></span>
  
<span data-ttu-id="df32b-576">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="df32b-576">tax identification no.</span></span>
  
<span data-ttu-id="df32b-577">mokesčių 識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-577">mokesčių id</span></span>
  
<span data-ttu-id="df32b-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="df32b-578">mokesčių numeris</span></span>
  
<span data-ttu-id="df32b-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="df32b-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="df32b-580">盧森堡</span><span class="sxs-lookup"><span data-stu-id="df32b-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="df32b-581">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-581">Format</span></span>

<span data-ttu-id="df32b-582">不含空格或分隔符號的 13 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-583">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-583">Pattern</span></span>

<span data-ttu-id="df32b-584">13 位數：</span><span class="sxs-lookup"><span data-stu-id="df32b-584">13 digits:</span></span>
  
-  <span data-ttu-id="df32b-585">11 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-585">11 digits</span></span> 
    
- <span data-ttu-id="df32b-586">二位數檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-587">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-587">Checksum</span></span>

<span data-ttu-id="df32b-588">是</span><span class="sxs-lookup"><span data-stu-id="df32b-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-589">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-589">Definition</span></span>

<span data-ttu-id="df32b-590">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-591">函式`Func_luxemburg_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-592">從關鍵字`Keywords_luxemburg_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-593">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-594">函式`Func_luxemburg_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-595">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="df32b-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-597">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-597">tax number</span></span>
  
<span data-ttu-id="df32b-598">稅務否。</span><span class="sxs-lookup"><span data-stu-id="df32b-598">tax no.</span></span>
  
<span data-ttu-id="df32b-599">taxno#</span><span class="sxs-lookup"><span data-stu-id="df32b-599">taxno#</span></span>
  
<span data-ttu-id="df32b-600">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="df32b-600">taxnumber#</span></span>
  
<span data-ttu-id="df32b-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="df32b-601">taxnumber</span></span>
  
<span data-ttu-id="df32b-602">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-602">tax id</span></span>
  
<span data-ttu-id="df32b-603">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-603">taxid#</span></span>
  
<span data-ttu-id="df32b-604">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-604">tax identification number</span></span>
  
<span data-ttu-id="df32b-605">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="df32b-605">tax identification no.</span></span>
  
<span data-ttu-id="df32b-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="df32b-606">steuernummer</span></span>
  
<span data-ttu-id="df32b-607">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-607">steuer id</span></span>
  
<span data-ttu-id="df32b-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="df32b-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="df32b-609">馬爾他</span><span class="sxs-lookup"><span data-stu-id="df32b-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="df32b-610">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-610">Format</span></span>

<span data-ttu-id="df32b-611">針對馬爾他 nationals: 7 位數與所指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="df32b-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="df32b-612">非馬爾他文 nationals 和馬爾他實體： 9 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-613">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-613">Pattern</span></span>

<span data-ttu-id="df32b-614">馬爾他 nationals: 7 位數和一個字母</span><span class="sxs-lookup"><span data-stu-id="df32b-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="df32b-615">七位數</span><span class="sxs-lookup"><span data-stu-id="df32b-615">Seven digits</span></span> 
    
- <span data-ttu-id="df32b-616">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="df32b-617">非馬爾他文 nationals 和馬爾他實體： 9 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="df32b-618">九位數</span><span class="sxs-lookup"><span data-stu-id="df32b-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="df32b-619">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-619">Checksum</span></span>

<span data-ttu-id="df32b-620">不適用</span><span class="sxs-lookup"><span data-stu-id="df32b-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-621">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-621">Definition</span></span>

<span data-ttu-id="df32b-622">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-623">函式`Func_malta_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-624">從關鍵字`Keywords_malta_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-625">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-626">函式`Func_malta_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-627">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="df32b-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-629">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-629">tax number</span></span>
  
<span data-ttu-id="df32b-630">稅務否。</span><span class="sxs-lookup"><span data-stu-id="df32b-630">tax no.</span></span>
  
<span data-ttu-id="df32b-631">taxno#</span><span class="sxs-lookup"><span data-stu-id="df32b-631">taxno#</span></span>
  
<span data-ttu-id="df32b-632">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="df32b-632">taxnumber#</span></span>
  
<span data-ttu-id="df32b-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="df32b-633">taxnumber</span></span>
  
<span data-ttu-id="df32b-634">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-634">tax id</span></span>
  
<span data-ttu-id="df32b-635">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-635">taxid#</span></span>
  
<span data-ttu-id="df32b-636">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-636">tax identification number</span></span>
  
<span data-ttu-id="df32b-637">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="df32b-637">tax identification no.</span></span>
  
<span data-ttu-id="df32b-638">numru 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="df32b-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="df32b-639">識別碼且 taxxa</span><span class="sxs-lookup"><span data-stu-id="df32b-639">id tat-taxxa</span></span>
  
<span data-ttu-id="df32b-640">numru 東西 ' identifikazzjoni 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="df32b-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="df32b-641">荷蘭</span><span class="sxs-lookup"><span data-stu-id="df32b-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="df32b-642">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-642">Format</span></span>

<span data-ttu-id="df32b-643">不含空格或分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="df32b-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-644">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-644">Pattern</span></span>

<span data-ttu-id="df32b-645">九位數</span><span class="sxs-lookup"><span data-stu-id="df32b-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="df32b-646">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-646">Checksum</span></span>

<span data-ttu-id="df32b-647">是</span><span class="sxs-lookup"><span data-stu-id="df32b-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-648">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-648">Definition</span></span>

<span data-ttu-id="df32b-649">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-650">函式`Func_netherlands_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-651">從關鍵字`Keywords_netherlands_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-652">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-653">函式`Func_netherlands_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-654">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="df32b-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-656">荷蘭稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="df32b-657">荷蘭稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-657">netherlands tax identification</span></span>
  
<span data-ttu-id="df32b-658">荷屬安的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="df32b-659">荷屬安的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-659">netherland's tax identification</span></span>
  
<span data-ttu-id="df32b-660">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-660">tax identification number</span></span>
  
<span data-ttu-id="df32b-661">荷蘭文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-661">dutch tax id</span></span>
  
<span data-ttu-id="df32b-662">荷蘭文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-662">dutch tax identification number</span></span>
  
<span data-ttu-id="df32b-663">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-663">tax id</span></span>
  
<span data-ttu-id="df32b-664">稅務識別碼#</span><span class="sxs-lookup"><span data-stu-id="df32b-664">tax id#</span></span>
  
<span data-ttu-id="df32b-665">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-665">tax number</span></span>
  
<span data-ttu-id="df32b-666">稅務否#</span><span class="sxs-lookup"><span data-stu-id="df32b-666">tax no#</span></span>
  
<span data-ttu-id="df32b-667">稅務#</span><span class="sxs-lookup"><span data-stu-id="df32b-667">tax#</span></span>
  
<span data-ttu-id="df32b-668">錫</span><span class="sxs-lookup"><span data-stu-id="df32b-668">tin</span></span>
  
<span data-ttu-id="df32b-669">錫#</span><span class="sxs-lookup"><span data-stu-id="df32b-669">tin#</span></span>
  
<span data-ttu-id="df32b-670">荷蘭錫</span><span class="sxs-lookup"><span data-stu-id="df32b-670">netherlands tin</span></span>
  
<span data-ttu-id="df32b-671">荷屬安的錫</span><span class="sxs-lookup"><span data-stu-id="df32b-671">netherland's tin</span></span>
  
<span data-ttu-id="df32b-672">荷蘭 belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="df32b-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="df32b-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="df32b-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="df32b-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="df32b-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="df32b-675">荷蘭 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="df32b-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="df32b-676">荷蘭 belasting 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="df32b-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="df32b-677">荷蘭 belastingnummer</span><span class="sxs-lookup"><span data-stu-id="df32b-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="df32b-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="df32b-678">btw nummer</span></span>
  
<span data-ttu-id="df32b-679">文拚字檢查 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="df32b-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="df32b-680">波蘭</span><span class="sxs-lookup"><span data-stu-id="df32b-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="df32b-681">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-681">Format</span></span>

<span data-ttu-id="df32b-682">不含空格或分隔符號十一份數字</span><span class="sxs-lookup"><span data-stu-id="df32b-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-683">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-683">Pattern</span></span>

<span data-ttu-id="df32b-684">十一份數字</span><span class="sxs-lookup"><span data-stu-id="df32b-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="df32b-685">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-685">Checksum</span></span>

<span data-ttu-id="df32b-686">是</span><span class="sxs-lookup"><span data-stu-id="df32b-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-687">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-687">Definition</span></span>

<span data-ttu-id="df32b-688">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-689">函式`Func_poland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-690">從關鍵字`Keywords_poland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-691">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-692">函式`Func_poland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-693">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="df32b-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-695">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-695">tax number</span></span>
  
<span data-ttu-id="df32b-696">稅務否。</span><span class="sxs-lookup"><span data-stu-id="df32b-696">tax no.</span></span>
  
<span data-ttu-id="df32b-697">taxno#</span><span class="sxs-lookup"><span data-stu-id="df32b-697">taxno#</span></span>
  
<span data-ttu-id="df32b-698">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="df32b-698">taxnumber#</span></span>
  
<span data-ttu-id="df32b-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="df32b-699">taxnumber</span></span>
  
<span data-ttu-id="df32b-700">nip</span><span class="sxs-lookup"><span data-stu-id="df32b-700">nip</span></span>
  
<span data-ttu-id="df32b-701">nip#</span><span class="sxs-lookup"><span data-stu-id="df32b-701">nip#</span></span>
  
<span data-ttu-id="df32b-702">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-702">tax id</span></span>
  
<span data-ttu-id="df32b-703">稅務識別碼#</span><span class="sxs-lookup"><span data-stu-id="df32b-703">tax id#</span></span>
  
<span data-ttu-id="df32b-704">nip 識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-704">nip id</span></span>
  
<span data-ttu-id="df32b-705">nip 識別碼#</span><span class="sxs-lookup"><span data-stu-id="df32b-705">nip id#</span></span>
  
<span data-ttu-id="df32b-706">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-706">tax identification number</span></span>
  
<span data-ttu-id="df32b-707">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="df32b-707">tax identification no.</span></span>
  
<span data-ttu-id="df32b-708">vat 編號</span><span class="sxs-lookup"><span data-stu-id="df32b-708">vat number</span></span>
  
<span data-ttu-id="df32b-709">vat 否。</span><span class="sxs-lookup"><span data-stu-id="df32b-709">vat no.</span></span>
  
<span data-ttu-id="df32b-710">vatno#</span><span class="sxs-lookup"><span data-stu-id="df32b-710">vatno#</span></span>
  
<span data-ttu-id="df32b-711">vat 識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-711">vat id</span></span>
  
<span data-ttu-id="df32b-712">vat 識別碼#</span><span class="sxs-lookup"><span data-stu-id="df32b-712">vat id#</span></span>
  
<span data-ttu-id="df32b-713">數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="df32b-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="df32b-714">polski 數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="df32b-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="df32b-715">numeridentyfikacjipodatkowej#</span><span class="sxs-lookup"><span data-stu-id="df32b-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="df32b-716">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="df32b-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="df32b-717">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-717">Format</span></span>

<span data-ttu-id="df32b-718">不含空格或分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="df32b-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-719">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-719">Pattern</span></span>

<span data-ttu-id="df32b-720">九位數</span><span class="sxs-lookup"><span data-stu-id="df32b-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="df32b-721">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-721">Checksum</span></span>

<span data-ttu-id="df32b-722">是</span><span class="sxs-lookup"><span data-stu-id="df32b-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-723">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-723">Definition</span></span>

<span data-ttu-id="df32b-724">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-725">函式`Func_portugal_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-726">從關鍵字`Keywords_portugal_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-727">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-728">函式`Func_portugal_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-729">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="df32b-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-731">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-731">tax number</span></span>
  
<span data-ttu-id="df32b-732">稅務否。</span><span class="sxs-lookup"><span data-stu-id="df32b-732">tax no.</span></span>
  
<span data-ttu-id="df32b-733">taxno#</span><span class="sxs-lookup"><span data-stu-id="df32b-733">taxno#</span></span>
  
<span data-ttu-id="df32b-734">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="df32b-734">taxnumber#</span></span>
  
<span data-ttu-id="df32b-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="df32b-735">taxnumber</span></span>
  
<span data-ttu-id="df32b-736">n 如果</span><span class="sxs-lookup"><span data-stu-id="df32b-736">nif</span></span>
  
<span data-ttu-id="df32b-737">n 如果#</span><span class="sxs-lookup"><span data-stu-id="df32b-737">nif#</span></span>
  
<span data-ttu-id="df32b-738">numero 會計</span><span class="sxs-lookup"><span data-stu-id="df32b-738">numero fiscal</span></span>
  
<span data-ttu-id="df32b-739">número de identificação 會計</span><span class="sxs-lookup"><span data-stu-id="df32b-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="df32b-740">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="df32b-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="df32b-741">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-741">Format</span></span>

<span data-ttu-id="df32b-742">不含空格或分隔符號的 13 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-743">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-743">Pattern</span></span>

<span data-ttu-id="df32b-744">13 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="df32b-745">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-745">Checksum</span></span>

<span data-ttu-id="df32b-746">不適用</span><span class="sxs-lookup"><span data-stu-id="df32b-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-747">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-747">Definition</span></span>

<span data-ttu-id="df32b-748">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-749">規則運算式`Regex_romania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-750">從關鍵字`Keywords_romania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="df32b-751">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="df32b-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-753">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-753">tax id</span></span>
  
<span data-ttu-id="df32b-754">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-754">tax id number</span></span>
  
<span data-ttu-id="df32b-755">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="df32b-755">tax file no</span></span>
  
<span data-ttu-id="df32b-756">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="df32b-756">tax file number</span></span>
  
<span data-ttu-id="df32b-757">稅務否</span><span class="sxs-lookup"><span data-stu-id="df32b-757">tax no</span></span>
  
<span data-ttu-id="df32b-758">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-758">tax number</span></span>
  
<span data-ttu-id="df32b-759">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-759">taxid#</span></span>
  
<span data-ttu-id="df32b-760">taxno#</span><span class="sxs-lookup"><span data-stu-id="df32b-760">taxno#</span></span>
  
<span data-ttu-id="df32b-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="df32b-761">id-ul taxei</span></span>
  
<span data-ttu-id="df32b-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="df32b-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="df32b-763">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="df32b-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="df32b-764">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-764">Format</span></span>

<span data-ttu-id="df32b-765">不含空格或分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-766">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-766">Pattern</span></span>

<span data-ttu-id="df32b-767">10 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="df32b-768">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-768">Checksum</span></span>

<span data-ttu-id="df32b-769">不適用</span><span class="sxs-lookup"><span data-stu-id="df32b-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-770">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-770">Definition</span></span>

<span data-ttu-id="df32b-771">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-772">規則運算式`Regex_slovakia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-773">從關鍵字`Keywords_slovakia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="df32b-774">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="df32b-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-776">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-776">tax id</span></span>
  
<span data-ttu-id="df32b-777">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-777">tax id number</span></span>
  
<span data-ttu-id="df32b-778">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-778">tin id</span></span>
  
<span data-ttu-id="df32b-779">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="df32b-779">tin no</span></span>
  
<span data-ttu-id="df32b-780">斯洛伐克鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-780">slovakian tin id</span></span>
  
<span data-ttu-id="df32b-781">錫</span><span class="sxs-lookup"><span data-stu-id="df32b-781">tin</span></span>
  
<span data-ttu-id="df32b-782">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="df32b-782">tax file no</span></span>
  
<span data-ttu-id="df32b-783">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="df32b-783">tax file number</span></span>
  
<span data-ttu-id="df32b-784">稅務否</span><span class="sxs-lookup"><span data-stu-id="df32b-784">tax no</span></span>
  
<span data-ttu-id="df32b-785">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-785">tax number</span></span>
  
<span data-ttu-id="df32b-786">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-786">taxid#</span></span>
  
<span data-ttu-id="df32b-787">taxno#</span><span class="sxs-lookup"><span data-stu-id="df32b-787">taxno#</span></span>
  
<span data-ttu-id="df32b-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="df32b-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="df32b-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="df32b-789">daňové číslo</span></span>
  
<span data-ttu-id="df32b-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="df32b-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="df32b-791">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="df32b-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="df32b-792">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-792">Format</span></span>

<span data-ttu-id="df32b-793">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="df32b-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-794">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-794">Pattern</span></span>

<span data-ttu-id="df32b-795">八位數</span><span class="sxs-lookup"><span data-stu-id="df32b-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="df32b-796">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-796">Checksum</span></span>

<span data-ttu-id="df32b-797">是</span><span class="sxs-lookup"><span data-stu-id="df32b-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-798">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-798">Definition</span></span>

<span data-ttu-id="df32b-799">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-800">函式`Func_slovenia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-801">從關鍵字`Keywords_slovenia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-802">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-803">函式`Func_slovenia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-804">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="df32b-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-806">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-806">tax id</span></span>
  
<span data-ttu-id="df32b-807">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-807">tax id number</span></span>
  
<span data-ttu-id="df32b-808">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-808">tin id</span></span>
  
<span data-ttu-id="df32b-809">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="df32b-809">tin no</span></span>
  
<span data-ttu-id="df32b-810">斯洛維尼亞文鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-810">slovenian tin id</span></span>
  
<span data-ttu-id="df32b-811">錫</span><span class="sxs-lookup"><span data-stu-id="df32b-811">tin</span></span>
  
<span data-ttu-id="df32b-812">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="df32b-812">tax file no</span></span>
  
<span data-ttu-id="df32b-813">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="df32b-813">tax file number</span></span>
  
<span data-ttu-id="df32b-814">稅務否</span><span class="sxs-lookup"><span data-stu-id="df32b-814">tax no</span></span>
  
<span data-ttu-id="df32b-815">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-815">tax number</span></span>
  
<span data-ttu-id="df32b-816">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-816">taxid#</span></span>
  
<span data-ttu-id="df32b-817">taxno#</span><span class="sxs-lookup"><span data-stu-id="df32b-817">taxno#</span></span>
  
<span data-ttu-id="df32b-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="df32b-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="df32b-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="df32b-819">davčna številka</span></span>
  
<span data-ttu-id="df32b-820">Številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="df32b-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="df32b-821">西班牙</span><span class="sxs-lookup"><span data-stu-id="df32b-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="df32b-822">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-822">Format</span></span>

<span data-ttu-id="df32b-823">7 或 8 位數與所指定的型態的一或兩個字母</span><span class="sxs-lookup"><span data-stu-id="df32b-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-824">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-824">Pattern</span></span>

<span data-ttu-id="df32b-825">西班牙文自然人西班牙國民身分證與：</span><span class="sxs-lookup"><span data-stu-id="df32b-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="df32b-826">八位數</span><span class="sxs-lookup"><span data-stu-id="df32b-826">Eight digits</span></span> 
    
- <span data-ttu-id="df32b-827">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="df32b-828">非駐留西班牙人沒有西班牙國民身分證</span><span class="sxs-lookup"><span data-stu-id="df32b-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="df32b-829">一個大寫字母"L"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="df32b-830">七位數</span><span class="sxs-lookup"><span data-stu-id="df32b-830">Seven digits</span></span>
    
- <span data-ttu-id="df32b-831">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="df32b-832">[] 下的保留天數 14 年沒有西班牙國民身分證駐留西班牙人：</span><span class="sxs-lookup"><span data-stu-id="df32b-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="df32b-833">一個大寫字母"K"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="df32b-834">七位數</span><span class="sxs-lookup"><span data-stu-id="df32b-834">Seven digits</span></span> 
    
- <span data-ttu-id="df32b-835">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="df32b-836">外國人與因此識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="df32b-837">一個大寫也就是字母 「 X 」、 「 Y"或"Z"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="df32b-838">七位數</span><span class="sxs-lookup"><span data-stu-id="df32b-838">Seven digits</span></span>
    
- <span data-ttu-id="df32b-839">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="df32b-840">外國人沒有因此識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="df32b-841">一個大寫字母，為 「 M 」 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="df32b-842">七位數</span><span class="sxs-lookup"><span data-stu-id="df32b-842">Seven digits</span></span>
    
- <span data-ttu-id="df32b-843">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="df32b-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="df32b-844">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-844">Checksum</span></span>

<span data-ttu-id="df32b-845">是</span><span class="sxs-lookup"><span data-stu-id="df32b-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-846">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-846">Definition</span></span>

<span data-ttu-id="df32b-847">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-848">函式`Func_spain_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-849">從關鍵字`Keywords_spain_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-850">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-851">函式`Func_spain_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-852">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="df32b-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-854">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-854">tax id</span></span>
  
<span data-ttu-id="df32b-855">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-855">tax id number</span></span>
  
<span data-ttu-id="df32b-856">cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-856">cif id</span></span>
  
<span data-ttu-id="df32b-857">cif 沒有</span><span class="sxs-lookup"><span data-stu-id="df32b-857">cif no</span></span>
  
<span data-ttu-id="df32b-858">西班牙文的 cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-858">spanish cif id</span></span>
  
<span data-ttu-id="df32b-859">cif</span><span class="sxs-lookup"><span data-stu-id="df32b-859">cif</span></span>
  
<span data-ttu-id="df32b-860">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="df32b-860">tax file no</span></span>
  
<span data-ttu-id="df32b-861">西班牙文的 cif 數目</span><span class="sxs-lookup"><span data-stu-id="df32b-861">spanish cif number</span></span>
  
<span data-ttu-id="df32b-862">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="df32b-862">tax file number</span></span>
  
<span data-ttu-id="df32b-863">西班牙文的 cif 沒有</span><span class="sxs-lookup"><span data-stu-id="df32b-863">spanish cif no</span></span>
  
<span data-ttu-id="df32b-864">稅務否</span><span class="sxs-lookup"><span data-stu-id="df32b-864">tax no</span></span>
  
<span data-ttu-id="df32b-865">稅務編號</span><span class="sxs-lookup"><span data-stu-id="df32b-865">tax number</span></span>
  
<span data-ttu-id="df32b-866">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-866">taxid#</span></span>
  
<span data-ttu-id="df32b-867">taxno#</span><span class="sxs-lookup"><span data-stu-id="df32b-867">taxno#</span></span>
  
<span data-ttu-id="df32b-868">cifid#</span><span class="sxs-lookup"><span data-stu-id="df32b-868">cifid#</span></span>
  
<span data-ttu-id="df32b-869">spanishcifid#</span><span class="sxs-lookup"><span data-stu-id="df32b-869">spanishcifid#</span></span>
  
<span data-ttu-id="df32b-870">spanishcifno#</span><span class="sxs-lookup"><span data-stu-id="df32b-870">spanishcifno#</span></span>
  
<span data-ttu-id="df32b-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="df32b-871">número de contribuyente</span></span>
  
<span data-ttu-id="df32b-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="df32b-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="df32b-873">número de identificación 會計</span><span class="sxs-lookup"><span data-stu-id="df32b-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="df32b-874">cif número</span><span class="sxs-lookup"><span data-stu-id="df32b-874">cif número</span></span>
  
<span data-ttu-id="df32b-875">cifnúmero#</span><span class="sxs-lookup"><span data-stu-id="df32b-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="df32b-876">瑞典</span><span class="sxs-lookup"><span data-stu-id="df32b-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="df32b-877">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-877">Format</span></span>

<span data-ttu-id="df32b-878">十個數字和中指定的型態的符號</span><span class="sxs-lookup"><span data-stu-id="df32b-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-879">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-879">Pattern</span></span>

<span data-ttu-id="df32b-880">十個數字和符號：</span><span class="sxs-lookup"><span data-stu-id="df32b-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="df32b-881">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="df32b-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="df32b-882">加號、 減號或反斜線</span><span class="sxs-lookup"><span data-stu-id="df32b-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="df32b-883">請識別的三位數數字唯一的位置：</span><span class="sxs-lookup"><span data-stu-id="df32b-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="df32b-884">發行之前 1990年數字，如第七個和第八個數字識別出生或 foreign-born 人員郡</span><span class="sxs-lookup"><span data-stu-id="df32b-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="df32b-885">在第九個位置的數字，表示女性 1 女 2 男或甚至是任一奇數性別</span><span class="sxs-lookup"><span data-stu-id="df32b-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="df32b-886">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="df32b-887">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-887">Checksum</span></span>

<span data-ttu-id="df32b-888">是</span><span class="sxs-lookup"><span data-stu-id="df32b-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-889">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-889">Definition</span></span>

<span data-ttu-id="df32b-890">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-891">函式`Func_sweden_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-892">從關鍵字`Keywords_sweden_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="df32b-893">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-894">函式`Func_sweden_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="df32b-895">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="df32b-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-897">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-897">tax id</span></span>
  
<span data-ttu-id="df32b-898">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="df32b-898">tax id no.</span></span>
  
<span data-ttu-id="df32b-899">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-899">tax id number</span></span>
  
<span data-ttu-id="df32b-900">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-900">tax identification</span></span>
  
<span data-ttu-id="df32b-901">稅務識別碼#</span><span class="sxs-lookup"><span data-stu-id="df32b-901">tax identification#</span></span>
  
<span data-ttu-id="df32b-902">稅務否。</span><span class="sxs-lookup"><span data-stu-id="df32b-902">tax no.</span></span>
  
<span data-ttu-id="df32b-903">稅務#</span><span class="sxs-lookup"><span data-stu-id="df32b-903">tax#</span></span>
  
<span data-ttu-id="df32b-904">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-904">taxid#</span></span>
  
<span data-ttu-id="df32b-905">稅務檔案</span><span class="sxs-lookup"><span data-stu-id="df32b-905">tax file</span></span>
  
<span data-ttu-id="df32b-906">不稅務檔案。</span><span class="sxs-lookup"><span data-stu-id="df32b-906">tax file no.</span></span>
  
<span data-ttu-id="df32b-907">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-907">personal id number</span></span>
  
<span data-ttu-id="df32b-908">skatt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="df32b-908">skatt id nummer</span></span>
  
<span data-ttu-id="df32b-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="df32b-909">skatt identifikation</span></span>
  
<span data-ttu-id="df32b-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="df32b-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="df32b-911">英國</span><span class="sxs-lookup"><span data-stu-id="df32b-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="df32b-912">格式</span><span class="sxs-lookup"><span data-stu-id="df32b-912">Format</span></span>

<span data-ttu-id="df32b-913">如果沒有空格和分隔符號的唯一 Taxpayer 參照 (UTR): 10 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="df32b-914">國家保險號碼 (NINO): 如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="df32b-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="df32b-915">國家保險號碼 (NINO) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="df32b-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="df32b-916">模式</span><span class="sxs-lookup"><span data-stu-id="df32b-916">Pattern</span></span>

<span data-ttu-id="df32b-917">唯一 Taxpayer 參照 (UTR): 10 位數</span><span class="sxs-lookup"><span data-stu-id="df32b-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="df32b-918">國家保險號碼 (NINO): 如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="df32b-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="df32b-919">國家保險號碼 (NINO) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="df32b-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="df32b-920">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="df32b-920">Checksum</span></span>

<span data-ttu-id="df32b-921">是</span><span class="sxs-lookup"><span data-stu-id="df32b-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="df32b-922">定義</span><span class="sxs-lookup"><span data-stu-id="df32b-922">Definition</span></span>

<span data-ttu-id="df32b-923">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="df32b-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="df32b-924">函式`Func_uk_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="df32b-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="df32b-925">從關鍵字`Keywords_uk_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="df32b-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="df32b-926">關鍵字</span><span class="sxs-lookup"><span data-stu-id="df32b-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="df32b-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="df32b-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="df32b-928">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-928">tax id</span></span>
  
<span data-ttu-id="df32b-929">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="df32b-929">tax id no.</span></span>
  
<span data-ttu-id="df32b-930">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="df32b-930">tax id number</span></span>
  
<span data-ttu-id="df32b-931">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="df32b-931">tax identification</span></span>
  
<span data-ttu-id="df32b-932">稅務識別碼#</span><span class="sxs-lookup"><span data-stu-id="df32b-932">tax identification#</span></span>
  
<span data-ttu-id="df32b-933">稅務否。</span><span class="sxs-lookup"><span data-stu-id="df32b-933">tax no.</span></span>
  
<span data-ttu-id="df32b-934">稅務#</span><span class="sxs-lookup"><span data-stu-id="df32b-934">tax#</span></span>
  
<span data-ttu-id="df32b-935">taxid#</span><span class="sxs-lookup"><span data-stu-id="df32b-935">taxid#</span></span>
  
<span data-ttu-id="df32b-936">稅務檔案</span><span class="sxs-lookup"><span data-stu-id="df32b-936">tax file</span></span>
  
<span data-ttu-id="df32b-937">不稅務檔案。</span><span class="sxs-lookup"><span data-stu-id="df32b-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="df32b-938">另請參閱</span><span class="sxs-lookup"><span data-stu-id="df32b-938">See also</span></span>

[<span data-ttu-id="df32b-939">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="df32b-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

