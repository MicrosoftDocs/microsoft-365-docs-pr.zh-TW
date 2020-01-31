---
title: 歐盟稅務識別碼
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
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟稅務識別號碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: 5467db921bd518eeeab18a36ee2de473f9017358
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41591014"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="fe08a-104">歐盟稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-104">EU Tax Identification Number</span></span>

<span data-ttu-id="fe08a-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟稅務識別號碼 （錫） 敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="fe08a-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="fe08a-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="fe08a-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="fe08a-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="fe08a-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-108">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-108">Format</span></span>

<span data-ttu-id="fe08a-109">選擇性連字號和正斜線的九位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-110">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-110">Pattern</span></span>

<span data-ttu-id="fe08a-111">選擇性連字號和正斜線的九位數：</span><span class="sxs-lookup"><span data-stu-id="fe08a-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="fe08a-112">兩位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-112">Two digits</span></span> 
    
- <span data-ttu-id="fe08a-113">連字號 （選用）</span><span class="sxs-lookup"><span data-stu-id="fe08a-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="fe08a-114">三位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-114">Three digits</span></span>
    
- <span data-ttu-id="fe08a-115">正斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="fe08a-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="fe08a-116">四位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-117">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-117">Checksum</span></span>

<span data-ttu-id="fe08a-118">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-119">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-119">Definition</span></span>

<span data-ttu-id="fe08a-120">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-121">函式`Func_austria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-122">從關鍵字`Keywords_austria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-123">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-124">函式`Func_austria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-125">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="fe08a-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-127">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-127">tax number</span></span>
  
<span data-ttu-id="fe08a-128">number</span><span class="sxs-lookup"><span data-stu-id="fe08a-128">number</span></span>
  
<span data-ttu-id="fe08a-129">稅務登記號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-129">tax registration number</span></span>
  
<span data-ttu-id="fe08a-130">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-130">tax id</span></span>
  
<span data-ttu-id="fe08a-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="fe08a-131">st.nr.</span></span>
  
<span data-ttu-id="fe08a-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="fe08a-133">比利時</span><span class="sxs-lookup"><span data-stu-id="fe08a-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-134">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-134">Format</span></span>

<span data-ttu-id="fe08a-135">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="fe08a-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-136">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-136">Pattern</span></span>

<span data-ttu-id="fe08a-137">11 位數：</span><span class="sxs-lookup"><span data-stu-id="fe08a-137">11 digits:</span></span>
  
- <span data-ttu-id="fe08a-138">兩位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-138">Two digits</span></span>
    
- <span data-ttu-id="fe08a-139">「 0 」 或者 「 1 」</span><span class="sxs-lookup"><span data-stu-id="fe08a-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="fe08a-140">一位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-140">One digit</span></span>
    
- <span data-ttu-id="fe08a-141">"0"或"1"或"2"或者"3"</span><span class="sxs-lookup"><span data-stu-id="fe08a-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="fe08a-142">六位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-143">Checksum</span></span>

<span data-ttu-id="fe08a-144">不適用</span><span class="sxs-lookup"><span data-stu-id="fe08a-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-145">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-145">Definition</span></span>

<span data-ttu-id="fe08a-146">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-147">規則運算式`Regex_belgium_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-148">從關鍵字`Keywords_belgium_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fe08a-149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="fe08a-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-151">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-151">tax number</span></span>
  
<span data-ttu-id="fe08a-152">國民登記號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-152">national registration number</span></span>
  
<span data-ttu-id="fe08a-153">稅務登記號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-153">tax registration number</span></span>
  
<span data-ttu-id="fe08a-154">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-154">tax id</span></span>
  
<span data-ttu-id="fe08a-155">n 如果</span><span class="sxs-lookup"><span data-stu-id="fe08a-155">nif</span></span>
  
<span data-ttu-id="fe08a-156">n 如果#</span><span class="sxs-lookup"><span data-stu-id="fe08a-156">nif#</span></span>
  
<span data-ttu-id="fe08a-157">numéro de registre 國際電話</span><span class="sxs-lookup"><span data-stu-id="fe08a-157">numéro de registre national</span></span>
  
<span data-ttu-id="fe08a-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="fe08a-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="fe08a-159">保加利亞</span><span class="sxs-lookup"><span data-stu-id="fe08a-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-160">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-160">Format</span></span>

<span data-ttu-id="fe08a-161">如果沒有空格和分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-162">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-162">Pattern</span></span>

<span data-ttu-id="fe08a-163">10 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fe08a-164">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-164">Checksum</span></span>

<span data-ttu-id="fe08a-165">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-166">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-166">Definition</span></span>

<span data-ttu-id="fe08a-167">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-168">函式`Func_bulgaria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-169">從關鍵字`Keywords_bulgaria_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-170">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-171">函式`Func_bulgaria_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-172">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="fe08a-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-174">bucn</span><span class="sxs-lookup"><span data-stu-id="fe08a-174">bucn</span></span>
  
<span data-ttu-id="fe08a-175">統一民事數目</span><span class="sxs-lookup"><span data-stu-id="fe08a-175">uniform civil number</span></span>
  
<span data-ttu-id="fe08a-176">bucn#</span><span class="sxs-lookup"><span data-stu-id="fe08a-176">bucn#</span></span>
  
<span data-ttu-id="fe08a-177">uniformcivilnumber#</span><span class="sxs-lookup"><span data-stu-id="fe08a-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="fe08a-178">統一民事識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-178">uniform civil id</span></span>
  
<span data-ttu-id="fe08a-179">統一民事否</span><span class="sxs-lookup"><span data-stu-id="fe08a-179">uniform civil no</span></span>
  
<span data-ttu-id="fe08a-180">egn</span><span class="sxs-lookup"><span data-stu-id="fe08a-180">egn</span></span>
  
<span data-ttu-id="fe08a-181">保加利亞文統一民事數目</span><span class="sxs-lookup"><span data-stu-id="fe08a-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="fe08a-182">uniformcivilno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-182">uniformcivilno#</span></span>
  
<span data-ttu-id="fe08a-183">egn#</span><span class="sxs-lookup"><span data-stu-id="fe08a-183">egn#</span></span>
  
<span data-ttu-id="fe08a-184">УНИФОРМ ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="fe08a-184">униформ граждански номер</span></span>
  
<span data-ttu-id="fe08a-185">Униформ 識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-185">униформ id</span></span>
  
<span data-ttu-id="fe08a-186">Униформ граждански 識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-186">униформ граждански id</span></span>
  
<span data-ttu-id="fe08a-187">УНИФОРМ ГРАЖДАНСКИ НЕ</span><span class="sxs-lookup"><span data-stu-id="fe08a-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="fe08a-188">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="fe08a-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-189">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-189">Format</span></span>

<span data-ttu-id="fe08a-190">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="fe08a-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-191">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-191">Pattern</span></span>

<span data-ttu-id="fe08a-192">11 位數：</span><span class="sxs-lookup"><span data-stu-id="fe08a-192">11 digits:</span></span>
  
- <span data-ttu-id="fe08a-193">十位數，隨機選擇</span><span class="sxs-lookup"><span data-stu-id="fe08a-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="fe08a-194">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-195">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-195">Checksum</span></span>

<span data-ttu-id="fe08a-196">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-197">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-197">Definition</span></span>

<span data-ttu-id="fe08a-198">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-199">函式`Func_croatia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-200">從關鍵字`Keywords_croatia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-201">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-202">函式`Func_croatia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-203">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="fe08a-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-205">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-205">tax number</span></span>
  
<span data-ttu-id="fe08a-206">稅務</span><span class="sxs-lookup"><span data-stu-id="fe08a-206">tax</span></span>
  
<span data-ttu-id="fe08a-207">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-207">tax id</span></span>
  
<span data-ttu-id="fe08a-208">OID</span><span class="sxs-lookup"><span data-stu-id="fe08a-208">oid</span></span>
  
<span data-ttu-id="fe08a-209">oid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-209">oid#</span></span>
  
<span data-ttu-id="fe08a-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="fe08a-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="fe08a-211">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="fe08a-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-212">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-212">Format</span></span>

<span data-ttu-id="fe08a-213">八位數與所指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="fe08a-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-214">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-214">Pattern</span></span>

<span data-ttu-id="fe08a-215">八位數和一個字母：</span><span class="sxs-lookup"><span data-stu-id="fe08a-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="fe08a-216">「 0 」</span><span class="sxs-lookup"><span data-stu-id="fe08a-216">A "0"</span></span> 
    
- <span data-ttu-id="fe08a-217">七位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-217">Seven digits</span></span>
    
- <span data-ttu-id="fe08a-218">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-219">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-219">Checksum</span></span>

<span data-ttu-id="fe08a-220">不適用</span><span class="sxs-lookup"><span data-stu-id="fe08a-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-221">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-221">Definition</span></span>

<span data-ttu-id="fe08a-222">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-223">函式`Func_cyprus_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-224">從關鍵字`Keywords_cyprus_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-225">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-226">函式`Func_cyprus_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="fe08a-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-229">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-229">tax number</span></span>
  
<span data-ttu-id="fe08a-230">稅務</span><span class="sxs-lookup"><span data-stu-id="fe08a-230">tax</span></span>
  
<span data-ttu-id="fe08a-231">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-231">tax id</span></span>
  
<span data-ttu-id="fe08a-232">稅務識別程式碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-232">tax identification code</span></span>
  
<span data-ttu-id="fe08a-233">tic</span><span class="sxs-lookup"><span data-stu-id="fe08a-233">tic</span></span>
  
<span data-ttu-id="fe08a-234">tic#</span><span class="sxs-lookup"><span data-stu-id="fe08a-234">tic#</span></span>
  
<span data-ttu-id="fe08a-235">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="fe08a-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="fe08a-236">ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="fe08a-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="fe08a-237">ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="fe08a-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="fe08a-238">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="fe08a-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-239">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-239">Format</span></span>

<span data-ttu-id="fe08a-240">具有選用反斜線的九個或十位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-241">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-241">Pattern</span></span>

<span data-ttu-id="fe08a-242">具有選用 backslashl 九個或十位數：</span><span class="sxs-lookup"><span data-stu-id="fe08a-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="fe08a-243">六位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-243">Six digits</span></span> 
    
- <span data-ttu-id="fe08a-244">反斜線 （選用）</span><span class="sxs-lookup"><span data-stu-id="fe08a-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="fe08a-245">三或四位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-246">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-246">Checksum</span></span>

<span data-ttu-id="fe08a-247">不適用</span><span class="sxs-lookup"><span data-stu-id="fe08a-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-248">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-248">Definition</span></span>

<span data-ttu-id="fe08a-249">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-250">規則運算式`Regex_czech_republic_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-251">從關鍵字`Keywords_czech_republic_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fe08a-252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="fe08a-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-254">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-254">tax number</span></span>
  
<span data-ttu-id="fe08a-255">稅務</span><span class="sxs-lookup"><span data-stu-id="fe08a-255">tax</span></span>
  
<span data-ttu-id="fe08a-256">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-256">tax id</span></span>
  
<span data-ttu-id="fe08a-257">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-257">personal number</span></span>
  
<span data-ttu-id="fe08a-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="fe08a-258">daňové číslo</span></span>
  
<span data-ttu-id="fe08a-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="fe08a-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="fe08a-260">丹麥</span><span class="sxs-lookup"><span data-stu-id="fe08a-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-261">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-261">Format</span></span>

<span data-ttu-id="fe08a-262">10 位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="fe08a-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-263">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-263">Pattern</span></span>

<span data-ttu-id="fe08a-264">10 位數包含 hyphenl:</span><span class="sxs-lookup"><span data-stu-id="fe08a-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="fe08a-265">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="fe08a-266">連字號</span><span class="sxs-lookup"><span data-stu-id="fe08a-266">A hyphen</span></span>
    
- <span data-ttu-id="fe08a-267">會對應至其中的第一個數字會對應至的出生世紀序號的四位數，最後一個數字會對應至個別的性別 （如 1 女 2 男以及即使女性奇數）</span><span class="sxs-lookup"><span data-stu-id="fe08a-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-268">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-268">Checksum</span></span>

<span data-ttu-id="fe08a-269">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-270">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-270">Definition</span></span>

<span data-ttu-id="fe08a-271">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-272">函式`Func_denmark_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-273">從關鍵字`Keywords_denmark_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-274">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-275">函式`Func_denmark_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-276">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="fe08a-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-278">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-278">tax number</span></span>
  
<span data-ttu-id="fe08a-279">稅務</span><span class="sxs-lookup"><span data-stu-id="fe08a-279">tax</span></span>
  
<span data-ttu-id="fe08a-280">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-280">tax id</span></span>
  
<span data-ttu-id="fe08a-281">cpr 數目</span><span class="sxs-lookup"><span data-stu-id="fe08a-281">cpr number</span></span>
  
<span data-ttu-id="fe08a-282">cpr#</span><span class="sxs-lookup"><span data-stu-id="fe08a-282">cpr#</span></span>
  
<span data-ttu-id="fe08a-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-283">skat nummer</span></span>
  
<span data-ttu-id="fe08a-284">skat 識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="fe08a-285">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="fe08a-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-286">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-286">Format</span></span>

<span data-ttu-id="fe08a-287">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="fe08a-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-288">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-288">Pattern</span></span>

<span data-ttu-id="fe08a-289">11 位數：</span><span class="sxs-lookup"><span data-stu-id="fe08a-289">11 digits:</span></span>
  
-  <span data-ttu-id="fe08a-290">會對應至性別和世紀的出生其中奇數的數字表示 1 女 2 男並偶數指出女性，如下所示的一個數字： 1，2 代表 19 世紀;3、 4 20 的 century;5，6 第 21 世紀</span><span class="sxs-lookup"><span data-stu-id="fe08a-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="fe08a-291">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="fe08a-292">會對應至分隔出生日期相同的人員序號的三位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="fe08a-293">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-294">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-294">Checksum</span></span>

<span data-ttu-id="fe08a-295">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-296">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-296">Definition</span></span>

<span data-ttu-id="fe08a-297">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-298">函式`Func_estonia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-299">從關鍵字`Keywords_estonia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-300">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-301">函式`Func_estonia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-302">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="fe08a-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-304">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-304">tax number</span></span>
  
<span data-ttu-id="fe08a-305">稅務</span><span class="sxs-lookup"><span data-stu-id="fe08a-305">tax</span></span>
  
<span data-ttu-id="fe08a-306">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-306">tax id</span></span>
  
<span data-ttu-id="fe08a-307">個人的程式碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-307">personal code</span></span>
  
<span data-ttu-id="fe08a-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="fe08a-308">maksunumber</span></span>
  
<span data-ttu-id="fe08a-309">maksu 識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-309">maksu id</span></span>
  
<span data-ttu-id="fe08a-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="fe08a-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="fe08a-311">芬蘭</span><span class="sxs-lookup"><span data-stu-id="fe08a-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-312">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-312">Format</span></span>

<span data-ttu-id="fe08a-313">字母的數字，11 個字元組合，以及加號與減號</span><span class="sxs-lookup"><span data-stu-id="fe08a-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-314">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-314">Pattern</span></span>

<span data-ttu-id="fe08a-315">字母的數字，11 個字元組合，以及加號與減號：</span><span class="sxs-lookup"><span data-stu-id="fe08a-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="fe08a-316">六位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-316">Six digits</span></span>
    
- <span data-ttu-id="fe08a-317">下列其中之一： 加上加號、 減號或其中加號表示字母"A"（不區分大小寫） 之間 1800年 1899 年出生減號登入表示出生之間 1999 1900 年和"A"表示出生 2000年和之後</span><span class="sxs-lookup"><span data-stu-id="fe08a-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="fe08a-318">三位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-318">Three digits</span></span>
    
- <span data-ttu-id="fe08a-319">一個字母或一個數字</span><span class="sxs-lookup"><span data-stu-id="fe08a-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-320">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-320">Checksum</span></span>

<span data-ttu-id="fe08a-321">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-322">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-322">Definition</span></span>

<span data-ttu-id="fe08a-323">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-324">函式`Func_finland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-325">從關鍵字`Keywords_finland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-326">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-327">函式`Func_finland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-328">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="fe08a-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-330">識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-330">identification number</span></span>
  
<span data-ttu-id="fe08a-331">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-331">personal id</span></span>
  
<span data-ttu-id="fe08a-332">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-332">identity number</span></span>
  
<span data-ttu-id="fe08a-333">芬蘭國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-333">finnish national id number</span></span>
  
<span data-ttu-id="fe08a-334">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="fe08a-334">personalidnumber#</span></span>
  
<span data-ttu-id="fe08a-335">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-335">national identification number</span></span>
  
<span data-ttu-id="fe08a-336">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-336">id number</span></span>
  
<span data-ttu-id="fe08a-337">國民身分證沒有。</span><span class="sxs-lookup"><span data-stu-id="fe08a-337">national id no.</span></span>
  
<span data-ttu-id="fe08a-338">國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-338">national id number</span></span>
  
<span data-ttu-id="fe08a-339">識別碼不</span><span class="sxs-lookup"><span data-stu-id="fe08a-339">id no</span></span>
  
<span data-ttu-id="fe08a-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="fe08a-340">tunnistenumero</span></span>
  
<span data-ttu-id="fe08a-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="fe08a-341">henkilötunnus</span></span>
  
<span data-ttu-id="fe08a-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="fe08a-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="fe08a-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="fe08a-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="fe08a-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="fe08a-344">identiteetti numero</span></span>
  
<span data-ttu-id="fe08a-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="fe08a-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="fe08a-346">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="fe08a-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="fe08a-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="fe08a-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="fe08a-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="fe08a-348">tunnusnumero</span></span>
  
<span data-ttu-id="fe08a-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="fe08a-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="fe08a-350">法國</span><span class="sxs-lookup"><span data-stu-id="fe08a-350">France</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-351">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-351">Format</span></span>

<span data-ttu-id="fe08a-352">13 位數個人與實體的九位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-353">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-353">Pattern</span></span>

<span data-ttu-id="fe08a-354">針對個人的 13 位數：</span><span class="sxs-lookup"><span data-stu-id="fe08a-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="fe08a-355">必須是 0、 1、 2 或 3 的一個數字</span><span class="sxs-lookup"><span data-stu-id="fe08a-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="fe08a-356">12 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-356">12 digits</span></span>
    
<span data-ttu-id="fe08a-357">實體的九位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fe08a-358">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-358">Checksum</span></span>

<span data-ttu-id="fe08a-359">不適用</span><span class="sxs-lookup"><span data-stu-id="fe08a-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-360">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-360">Definition</span></span>

<span data-ttu-id="fe08a-361">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-362">函式`Func_france_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-363">從關鍵字`Keywords_france_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-364">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-365">函式`Func_france_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-366">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="fe08a-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-368">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-368">tax identification number</span></span>
  
<span data-ttu-id="fe08a-369">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-369">tax number</span></span>
  
<span data-ttu-id="fe08a-370">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-370">tax id</span></span>
  
<span data-ttu-id="fe08a-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="fe08a-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="fe08a-372">德國</span><span class="sxs-lookup"><span data-stu-id="fe08a-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-373">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-373">Format</span></span>

<span data-ttu-id="fe08a-374">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="fe08a-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-375">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-375">Pattern</span></span>

<span data-ttu-id="fe08a-376">11 位數：</span><span class="sxs-lookup"><span data-stu-id="fe08a-376">11 digits :</span></span>
  
-  <span data-ttu-id="fe08a-377">十位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-377">Ten digits</span></span> 
    
- <span data-ttu-id="fe08a-378">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-379">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-379">Checksum</span></span>

<span data-ttu-id="fe08a-380">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-381">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-381">Definition</span></span>

<span data-ttu-id="fe08a-382">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-383">函式`Func_germany_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-384">從關鍵字`Keywords_germany_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-385">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-386">函式`Func_germany_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-387">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="fe08a-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-389">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-389">tax number</span></span>
  
<span data-ttu-id="fe08a-390">稅務否。</span><span class="sxs-lookup"><span data-stu-id="fe08a-390">tax no.</span></span>
  
<span data-ttu-id="fe08a-391">taxno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-391">taxno#</span></span>
  
<span data-ttu-id="fe08a-392">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="fe08a-392">taxnumber#</span></span>
  
<span data-ttu-id="fe08a-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fe08a-393">taxnumber</span></span>
  
<span data-ttu-id="fe08a-394">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-394">tax id</span></span>
  
<span data-ttu-id="fe08a-395">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-395">taxid#</span></span>
  
<span data-ttu-id="fe08a-396">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-396">tax identification number</span></span>
  
<span data-ttu-id="fe08a-397">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="fe08a-397">tax identification no.</span></span>
  
<span data-ttu-id="fe08a-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-398">steuernummer</span></span>
  
<span data-ttu-id="fe08a-399">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-399">steuer id</span></span>
  
<span data-ttu-id="fe08a-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="fe08a-401">希臘</span><span class="sxs-lookup"><span data-stu-id="fe08a-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-402">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-402">Format</span></span>

<span data-ttu-id="fe08a-403">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-404">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-404">Pattern</span></span>

<span data-ttu-id="fe08a-405">九位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fe08a-406">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-406">Checksum</span></span>

<span data-ttu-id="fe08a-407">不適用</span><span class="sxs-lookup"><span data-stu-id="fe08a-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-408">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-408">Definition</span></span>

<span data-ttu-id="fe08a-409">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-410">規則運算式`Regex_greece_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-411">從關鍵字`Keywords_greece_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fe08a-412">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="fe08a-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-414">afm</span><span class="sxs-lookup"><span data-stu-id="fe08a-414">afm</span></span>
  
<span data-ttu-id="fe08a-415">錫</span><span class="sxs-lookup"><span data-stu-id="fe08a-415">tin</span></span>
  
<span data-ttu-id="fe08a-416">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="fe08a-416">tax id no.</span></span>
  
<span data-ttu-id="fe08a-417">不稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-417">tax id no</span></span>
  
<span data-ttu-id="fe08a-418">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-418">tax identification number</span></span>
  
<span data-ttu-id="fe08a-419">稅務登錄編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-419">tax registry number</span></span>
  
<span data-ttu-id="fe08a-420">不稅務登錄。</span><span class="sxs-lookup"><span data-stu-id="fe08a-420">tax registry no.</span></span>
  
<span data-ttu-id="fe08a-421">afm#</span><span class="sxs-lookup"><span data-stu-id="fe08a-421">afm#</span></span>
  
<span data-ttu-id="fe08a-422">錫#</span><span class="sxs-lookup"><span data-stu-id="fe08a-422">tin#</span></span>
  
<span data-ttu-id="fe08a-423">taxidno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-423">taxidno#</span></span>
  
<span data-ttu-id="fe08a-424">taxregistryno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-424">taxregistryno#</span></span>
  
<span data-ttu-id="fe08a-425">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="fe08a-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="fe08a-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="fe08a-426">aφμ</span></span>
  
<span data-ttu-id="fe08a-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="fe08a-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="fe08a-428">ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。</span><span class="sxs-lookup"><span data-stu-id="fe08a-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="fe08a-429">ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="fe08a-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="fe08a-430">匈牙利</span><span class="sxs-lookup"><span data-stu-id="fe08a-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-431">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-431">Format</span></span>

<span data-ttu-id="fe08a-432">不含空格或分隔符號十位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-433">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-433">Pattern</span></span>

<span data-ttu-id="fe08a-434">十位數：</span><span class="sxs-lookup"><span data-stu-id="fe08a-434">Ten digits:</span></span>
  
-  <span data-ttu-id="fe08a-435">必須是"8"的一個數字</span><span class="sxs-lookup"><span data-stu-id="fe08a-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="fe08a-436">會對應至日期之間的天數的五位數 01/01/1867年和個別的出生日期</span><span class="sxs-lookup"><span data-stu-id="fe08a-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="fe08a-437">會對應至數來區分個人在同一天出生巧產生的三位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="fe08a-438">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-439">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-439">Checksum</span></span>

<span data-ttu-id="fe08a-440">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-441">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-441">Definition</span></span>

<span data-ttu-id="fe08a-442">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-443">函式`Func_hungary_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-444">從關鍵字`Keywords_hungary_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-445">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-446">函式`Func_hungary_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-447">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="fe08a-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-449">匈牙利文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="fe08a-450">匈牙利文錫</span><span class="sxs-lookup"><span data-stu-id="fe08a-450">hungarian tin</span></span>
  
<span data-ttu-id="fe08a-451">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-451">tax id number</span></span>
  
<span data-ttu-id="fe08a-452">vat 編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-452">vat number</span></span>
  
<span data-ttu-id="fe08a-453">不稅務授權單位</span><span class="sxs-lookup"><span data-stu-id="fe08a-453">tax authority no</span></span>
  
<span data-ttu-id="fe08a-454">稅務識別碼稅務身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-454">tax id tax identity number</span></span>
  
<span data-ttu-id="fe08a-455">taxidnumber#</span><span class="sxs-lookup"><span data-stu-id="fe08a-455">taxidnumber#</span></span>
  
<span data-ttu-id="fe08a-456">錫#</span><span class="sxs-lookup"><span data-stu-id="fe08a-456">tin#</span></span>
  
<span data-ttu-id="fe08a-457">hungatiantin#</span><span class="sxs-lookup"><span data-stu-id="fe08a-457">hungatiantin#</span></span>
  
<span data-ttu-id="fe08a-458">不稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-458">tax identification no</span></span>
  
<span data-ttu-id="fe08a-459">taxidno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-459">taxidno#</span></span>
  
<span data-ttu-id="fe08a-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="fe08a-460">adóazonosító szám</span></span>
  
<span data-ttu-id="fe08a-461">adószám</span><span class="sxs-lookup"><span data-stu-id="fe08a-461">adószám</span></span>
  
<span data-ttu-id="fe08a-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="fe08a-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="fe08a-463">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="fe08a-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-464">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-464">Format</span></span>

<span data-ttu-id="fe08a-465">七位數後尾隨不含空格或分隔符號的字母</span><span class="sxs-lookup"><span data-stu-id="fe08a-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-466">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-466">Pattern</span></span>

<span data-ttu-id="fe08a-467">七位數後尾隨字母：</span><span class="sxs-lookup"><span data-stu-id="fe08a-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="fe08a-468">七位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-468">Seven digits</span></span> 
    
- <span data-ttu-id="fe08a-469">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-470">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-470">Checksum</span></span>

<span data-ttu-id="fe08a-471">不適用</span><span class="sxs-lookup"><span data-stu-id="fe08a-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-472">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-472">Definition</span></span>

<span data-ttu-id="fe08a-473">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-474">函式`Func_ireland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-475">從關鍵字`Keywords_ireland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-476">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-477">函式`Func_ireland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-478">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="fe08a-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-480">公用服務沒有</span><span class="sxs-lookup"><span data-stu-id="fe08a-480">public service no</span></span>
  
<span data-ttu-id="fe08a-481">個人公用服務沒有</span><span class="sxs-lookup"><span data-stu-id="fe08a-481">personal public service no</span></span>
  
<span data-ttu-id="fe08a-482">pps 沒有</span><span class="sxs-lookup"><span data-stu-id="fe08a-482">pps no</span></span>
  
<span data-ttu-id="fe08a-483">個人服務否</span><span class="sxs-lookup"><span data-stu-id="fe08a-483">personal service no</span></span>
  
<span data-ttu-id="fe08a-484">pps service 否</span><span class="sxs-lookup"><span data-stu-id="fe08a-484">pps service no</span></span>
  
<span data-ttu-id="fe08a-485">ppsno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-485">ppsno#</span></span>
  
<span data-ttu-id="fe08a-486">愛爾蘭 pps 沒有</span><span class="sxs-lookup"><span data-stu-id="fe08a-486">irish pps no</span></span>
  
<span data-ttu-id="fe08a-487">publicserviceno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-487">publicserviceno#</span></span>
  
<span data-ttu-id="fe08a-488">個人公用服務號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-488">personal public service number</span></span>
  
<span data-ttu-id="fe08a-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="fe08a-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="fe08a-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="fe08a-490">pps uimh</span></span>
  
<span data-ttu-id="fe08a-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="fe08a-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="fe08a-492">義大利</span><span class="sxs-lookup"><span data-stu-id="fe08a-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-493">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-493">Format</span></span>

<span data-ttu-id="fe08a-494">16 個字母和數字中指定的型態</span><span class="sxs-lookup"><span data-stu-id="fe08a-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-495">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-495">Pattern</span></span>

<span data-ttu-id="fe08a-496">16 個字母和數字：</span><span class="sxs-lookup"><span data-stu-id="fe08a-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="fe08a-497">會對應到前三個母音系列名稱中的三個字母</span><span class="sxs-lookup"><span data-stu-id="fe08a-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="fe08a-498">會對應至第一、 第三個和第四個的三個字母母音在名字</span><span class="sxs-lookup"><span data-stu-id="fe08a-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="fe08a-499">會對應至最後一位數的出生年份的兩位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="fe08a-500">會對應至出生的月份的一個數字 — 字母可用依字母順序，但只字母 A 到 E、 H、 L、 M、 P、 R 以 T 可用 （因此，一月是的而且年 10 月 R）</span><span class="sxs-lookup"><span data-stu-id="fe08a-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="fe08a-501">會對應至出生其中 40 加入的來區分從男生女生出生日期的月份日期的兩位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="fe08a-502">會對應至特定出生人員 municipality 區域代碼的四位數 — 全國家/地區的代碼可用外部國家/地區</span><span class="sxs-lookup"><span data-stu-id="fe08a-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="fe08a-503">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-504">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-504">Checksum</span></span>

<span data-ttu-id="fe08a-505">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-506">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-506">Definition</span></span>

<span data-ttu-id="fe08a-507">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-508">函式`Func_italy_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-509">從關鍵字`Keywords_italy_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-510">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-511">函式`Func_italy_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-512">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="fe08a-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-514">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-514">tax number</span></span>
  
<span data-ttu-id="fe08a-515">稅務否。</span><span class="sxs-lookup"><span data-stu-id="fe08a-515">tax no.</span></span>
  
<span data-ttu-id="fe08a-516">taxno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-516">taxno#</span></span>
  
<span data-ttu-id="fe08a-517">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="fe08a-517">taxnumber#</span></span>
  
<span data-ttu-id="fe08a-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fe08a-518">taxnumber</span></span>
  
<span data-ttu-id="fe08a-519">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-519">tax id</span></span>
  
<span data-ttu-id="fe08a-520">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-520">taxid#</span></span>
  
<span data-ttu-id="fe08a-521">會計年度的程式碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-521">fiscal code</span></span>
  
<span data-ttu-id="fe08a-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fe08a-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="fe08a-523">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="fe08a-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-524">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-524">Format</span></span>

<span data-ttu-id="fe08a-525">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="fe08a-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-526">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-526">Pattern</span></span>

<span data-ttu-id="fe08a-527">11 位數，代表所指定模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="fe08a-528">會對應至 (DDMMYY) 出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="fe08a-529">會對應至的出生其中"0"會對應至 19 世紀"1"會對應至 20 世紀，，"2"會對應至第 21 世紀世紀的一個數字</span><span class="sxs-lookup"><span data-stu-id="fe08a-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="fe08a-530">四位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-531">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-531">Checksum</span></span>

<span data-ttu-id="fe08a-532">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-533">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-533">Definition</span></span>

<span data-ttu-id="fe08a-534">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-535">函式`Func_latvia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-536">從關鍵字`Keywords_latvia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-537">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-538">函式`Func_latvia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-539">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="fe08a-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-541">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-541">tax number</span></span>
  
<span data-ttu-id="fe08a-542">稅務否。</span><span class="sxs-lookup"><span data-stu-id="fe08a-542">tax no.</span></span>
  
<span data-ttu-id="fe08a-543">taxno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-543">taxno#</span></span>
  
<span data-ttu-id="fe08a-544">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="fe08a-544">taxnumber#</span></span>
  
<span data-ttu-id="fe08a-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fe08a-545">taxnumber</span></span>
  
<span data-ttu-id="fe08a-546">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-546">tax id</span></span>
  
<span data-ttu-id="fe08a-547">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-547">taxid#</span></span>
  
<span data-ttu-id="fe08a-548">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-548">tax identification number</span></span>
  
<span data-ttu-id="fe08a-549">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="fe08a-549">tax identification no.</span></span>
  
<span data-ttu-id="fe08a-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="fe08a-550">nodokļa numurs</span></span>
  
<span data-ttu-id="fe08a-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="fe08a-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="fe08a-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="fe08a-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="fe08a-553">立陶宛</span><span class="sxs-lookup"><span data-stu-id="fe08a-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-554">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-554">Format</span></span>

<span data-ttu-id="fe08a-555">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="fe08a-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-556">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-556">Pattern</span></span>

<span data-ttu-id="fe08a-557">11 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fe08a-558">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-558">Checksum</span></span>

<span data-ttu-id="fe08a-559">不適用</span><span class="sxs-lookup"><span data-stu-id="fe08a-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-560">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-560">Definition</span></span>

<span data-ttu-id="fe08a-561">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-562">函式`Func_lithuania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-563">從關鍵字`Keywords_lithuania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-564">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-565">函式`Func_lithuania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-566">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="fe08a-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-568">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-568">tax number</span></span>
  
<span data-ttu-id="fe08a-569">稅務否。</span><span class="sxs-lookup"><span data-stu-id="fe08a-569">tax no.</span></span>
  
<span data-ttu-id="fe08a-570">稅務否#</span><span class="sxs-lookup"><span data-stu-id="fe08a-570">tax no#</span></span>
  
<span data-ttu-id="fe08a-571">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="fe08a-571">taxnumber#</span></span>
  
<span data-ttu-id="fe08a-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fe08a-572">taxnumber</span></span>
  
<span data-ttu-id="fe08a-573">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-573">tax id</span></span>
  
<span data-ttu-id="fe08a-574">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-574">taxid#</span></span>
  
<span data-ttu-id="fe08a-575">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-575">tax identification number</span></span>
  
<span data-ttu-id="fe08a-576">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="fe08a-576">tax identification no.</span></span>
  
<span data-ttu-id="fe08a-577">mokesčių 識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-577">mokesčių id</span></span>
  
<span data-ttu-id="fe08a-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="fe08a-578">mokesčių numeris</span></span>
  
<span data-ttu-id="fe08a-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="fe08a-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="fe08a-580">盧森堡</span><span class="sxs-lookup"><span data-stu-id="fe08a-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-581">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-581">Format</span></span>

<span data-ttu-id="fe08a-582">不含空格或分隔符號的 13 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-583">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-583">Pattern</span></span>

<span data-ttu-id="fe08a-584">13 位數：</span><span class="sxs-lookup"><span data-stu-id="fe08a-584">13 digits:</span></span>
  
-  <span data-ttu-id="fe08a-585">11 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-585">11 digits</span></span> 
    
- <span data-ttu-id="fe08a-586">二位數檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-587">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-587">Checksum</span></span>

<span data-ttu-id="fe08a-588">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-589">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-589">Definition</span></span>

<span data-ttu-id="fe08a-590">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-591">函式`Func_luxemburg_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-592">從關鍵字`Keywords_luxemburg_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-593">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-594">函式`Func_luxemburg_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-595">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="fe08a-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-597">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-597">tax number</span></span>
  
<span data-ttu-id="fe08a-598">稅務否。</span><span class="sxs-lookup"><span data-stu-id="fe08a-598">tax no.</span></span>
  
<span data-ttu-id="fe08a-599">taxno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-599">taxno#</span></span>
  
<span data-ttu-id="fe08a-600">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="fe08a-600">taxnumber#</span></span>
  
<span data-ttu-id="fe08a-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fe08a-601">taxnumber</span></span>
  
<span data-ttu-id="fe08a-602">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-602">tax id</span></span>
  
<span data-ttu-id="fe08a-603">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-603">taxid#</span></span>
  
<span data-ttu-id="fe08a-604">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-604">tax identification number</span></span>
  
<span data-ttu-id="fe08a-605">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="fe08a-605">tax identification no.</span></span>
  
<span data-ttu-id="fe08a-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-606">steuernummer</span></span>
  
<span data-ttu-id="fe08a-607">steuer 識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-607">steuer id</span></span>
  
<span data-ttu-id="fe08a-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="fe08a-609">馬爾他</span><span class="sxs-lookup"><span data-stu-id="fe08a-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-610">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-610">Format</span></span>

<span data-ttu-id="fe08a-611">針對馬爾他 nationals: 7 位數與所指定的型態的其中一個字母</span><span class="sxs-lookup"><span data-stu-id="fe08a-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="fe08a-612">非馬爾他文 nationals 和馬爾他實體： 9 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-613">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-613">Pattern</span></span>

<span data-ttu-id="fe08a-614">馬爾他 nationals: 7 位數和一個字母</span><span class="sxs-lookup"><span data-stu-id="fe08a-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="fe08a-615">七位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-615">Seven digits</span></span> 
    
- <span data-ttu-id="fe08a-616">一個字母 （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="fe08a-617">非馬爾他文 nationals 和馬爾他實體： 9 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="fe08a-618">九位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="fe08a-619">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-619">Checksum</span></span>

<span data-ttu-id="fe08a-620">不適用</span><span class="sxs-lookup"><span data-stu-id="fe08a-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-621">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-621">Definition</span></span>

<span data-ttu-id="fe08a-622">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-623">函式`Func_malta_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-624">從關鍵字`Keywords_malta_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-625">DLP 原則是 65%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-626">函式`Func_malta_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-627">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="fe08a-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-629">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-629">tax number</span></span>
  
<span data-ttu-id="fe08a-630">稅務否。</span><span class="sxs-lookup"><span data-stu-id="fe08a-630">tax no.</span></span>
  
<span data-ttu-id="fe08a-631">taxno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-631">taxno#</span></span>
  
<span data-ttu-id="fe08a-632">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="fe08a-632">taxnumber#</span></span>
  
<span data-ttu-id="fe08a-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fe08a-633">taxnumber</span></span>
  
<span data-ttu-id="fe08a-634">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-634">tax id</span></span>
  
<span data-ttu-id="fe08a-635">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-635">taxid#</span></span>
  
<span data-ttu-id="fe08a-636">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-636">tax identification number</span></span>
  
<span data-ttu-id="fe08a-637">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="fe08a-637">tax identification no.</span></span>
  
<span data-ttu-id="fe08a-638">numru 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="fe08a-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="fe08a-639">識別碼且 taxxa</span><span class="sxs-lookup"><span data-stu-id="fe08a-639">id tat-taxxa</span></span>
  
<span data-ttu-id="fe08a-640">numru 東西 ' identifikazzjoni 且 taxxa</span><span class="sxs-lookup"><span data-stu-id="fe08a-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="fe08a-641">荷蘭</span><span class="sxs-lookup"><span data-stu-id="fe08a-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-642">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-642">Format</span></span>

<span data-ttu-id="fe08a-643">不含空格或分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-644">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-644">Pattern</span></span>

<span data-ttu-id="fe08a-645">九位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="fe08a-646">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-646">Checksum</span></span>

<span data-ttu-id="fe08a-647">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-648">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-648">Definition</span></span>

<span data-ttu-id="fe08a-649">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-650">函式`Func_netherlands_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-651">從關鍵字`Keywords_netherlands_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-652">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-653">函式`Func_netherlands_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-654">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="fe08a-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-656">荷蘭稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="fe08a-657">荷蘭稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-657">netherlands tax identification</span></span>
  
<span data-ttu-id="fe08a-658">荷屬安的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="fe08a-659">荷屬安的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-659">netherland's tax identification</span></span>
  
<span data-ttu-id="fe08a-660">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-660">tax identification number</span></span>
  
<span data-ttu-id="fe08a-661">荷蘭文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-661">dutch tax id</span></span>
  
<span data-ttu-id="fe08a-662">荷蘭文的稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-662">dutch tax identification number</span></span>
  
<span data-ttu-id="fe08a-663">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-663">tax id</span></span>
  
<span data-ttu-id="fe08a-664">稅務識別碼#</span><span class="sxs-lookup"><span data-stu-id="fe08a-664">tax id#</span></span>
  
<span data-ttu-id="fe08a-665">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-665">tax number</span></span>
  
<span data-ttu-id="fe08a-666">稅務否#</span><span class="sxs-lookup"><span data-stu-id="fe08a-666">tax no#</span></span>
  
<span data-ttu-id="fe08a-667">稅務#</span><span class="sxs-lookup"><span data-stu-id="fe08a-667">tax#</span></span>
  
<span data-ttu-id="fe08a-668">錫</span><span class="sxs-lookup"><span data-stu-id="fe08a-668">tin</span></span>
  
<span data-ttu-id="fe08a-669">錫#</span><span class="sxs-lookup"><span data-stu-id="fe08a-669">tin#</span></span>
  
<span data-ttu-id="fe08a-670">荷蘭錫</span><span class="sxs-lookup"><span data-stu-id="fe08a-670">netherlands tin</span></span>
  
<span data-ttu-id="fe08a-671">荷屬安的錫</span><span class="sxs-lookup"><span data-stu-id="fe08a-671">netherland's tin</span></span>
  
<span data-ttu-id="fe08a-672">荷蘭 belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="fe08a-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="fe08a-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="fe08a-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="fe08a-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="fe08a-675">荷蘭 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="fe08a-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="fe08a-676">荷蘭 belasting 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="fe08a-677">荷蘭 belastingnummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="fe08a-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-678">btw nummer</span></span>
  
<span data-ttu-id="fe08a-679">文拚字檢查 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="fe08a-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="fe08a-680">波蘭</span><span class="sxs-lookup"><span data-stu-id="fe08a-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-681">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-681">Format</span></span>

<span data-ttu-id="fe08a-682">不含空格或分隔符號十一份數字</span><span class="sxs-lookup"><span data-stu-id="fe08a-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-683">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-683">Pattern</span></span>

<span data-ttu-id="fe08a-684">十一份數字</span><span class="sxs-lookup"><span data-stu-id="fe08a-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fe08a-685">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-685">Checksum</span></span>

<span data-ttu-id="fe08a-686">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-687">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-687">Definition</span></span>

<span data-ttu-id="fe08a-688">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-689">函式`Func_poland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-690">從關鍵字`Keywords_poland_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-691">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-692">函式`Func_poland_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-693">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="fe08a-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-695">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-695">tax number</span></span>
  
<span data-ttu-id="fe08a-696">稅務否。</span><span class="sxs-lookup"><span data-stu-id="fe08a-696">tax no.</span></span>
  
<span data-ttu-id="fe08a-697">taxno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-697">taxno#</span></span>
  
<span data-ttu-id="fe08a-698">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="fe08a-698">taxnumber#</span></span>
  
<span data-ttu-id="fe08a-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fe08a-699">taxnumber</span></span>
  
<span data-ttu-id="fe08a-700">nip</span><span class="sxs-lookup"><span data-stu-id="fe08a-700">nip</span></span>
  
<span data-ttu-id="fe08a-701">nip#</span><span class="sxs-lookup"><span data-stu-id="fe08a-701">nip#</span></span>
  
<span data-ttu-id="fe08a-702">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-702">tax id</span></span>
  
<span data-ttu-id="fe08a-703">稅務識別碼#</span><span class="sxs-lookup"><span data-stu-id="fe08a-703">tax id#</span></span>
  
<span data-ttu-id="fe08a-704">nip 識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-704">nip id</span></span>
  
<span data-ttu-id="fe08a-705">nip 識別碼#</span><span class="sxs-lookup"><span data-stu-id="fe08a-705">nip id#</span></span>
  
<span data-ttu-id="fe08a-706">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-706">tax identification number</span></span>
  
<span data-ttu-id="fe08a-707">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="fe08a-707">tax identification no.</span></span>
  
<span data-ttu-id="fe08a-708">vat 編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-708">vat number</span></span>
  
<span data-ttu-id="fe08a-709">vat 否。</span><span class="sxs-lookup"><span data-stu-id="fe08a-709">vat no.</span></span>
  
<span data-ttu-id="fe08a-710">vatno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-710">vatno#</span></span>
  
<span data-ttu-id="fe08a-711">vat 識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-711">vat id</span></span>
  
<span data-ttu-id="fe08a-712">vat 識別碼#</span><span class="sxs-lookup"><span data-stu-id="fe08a-712">vat id#</span></span>
  
<span data-ttu-id="fe08a-713">數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="fe08a-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="fe08a-714">polski 數目 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="fe08a-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="fe08a-715">numeridentyfikacjipodatkowej#</span><span class="sxs-lookup"><span data-stu-id="fe08a-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="fe08a-716">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="fe08a-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-717">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-717">Format</span></span>

<span data-ttu-id="fe08a-718">不含空格或分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-719">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-719">Pattern</span></span>

<span data-ttu-id="fe08a-720">九位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fe08a-721">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-721">Checksum</span></span>

<span data-ttu-id="fe08a-722">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-723">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-723">Definition</span></span>

<span data-ttu-id="fe08a-724">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-725">函式`Func_portugal_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-726">從關鍵字`Keywords_portugal_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-727">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-728">函式`Func_portugal_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-729">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="fe08a-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-731">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-731">tax number</span></span>
  
<span data-ttu-id="fe08a-732">稅務否。</span><span class="sxs-lookup"><span data-stu-id="fe08a-732">tax no.</span></span>
  
<span data-ttu-id="fe08a-733">taxno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-733">taxno#</span></span>
  
<span data-ttu-id="fe08a-734">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="fe08a-734">taxnumber#</span></span>
  
<span data-ttu-id="fe08a-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fe08a-735">taxnumber</span></span>
  
<span data-ttu-id="fe08a-736">n 如果</span><span class="sxs-lookup"><span data-stu-id="fe08a-736">nif</span></span>
  
<span data-ttu-id="fe08a-737">n 如果#</span><span class="sxs-lookup"><span data-stu-id="fe08a-737">nif#</span></span>
  
<span data-ttu-id="fe08a-738">numero 會計</span><span class="sxs-lookup"><span data-stu-id="fe08a-738">numero fiscal</span></span>
  
<span data-ttu-id="fe08a-739">número de identificação 會計</span><span class="sxs-lookup"><span data-stu-id="fe08a-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="fe08a-740">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="fe08a-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-741">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-741">Format</span></span>

<span data-ttu-id="fe08a-742">不含空格或分隔符號的 13 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-743">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-743">Pattern</span></span>

<span data-ttu-id="fe08a-744">13 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fe08a-745">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-745">Checksum</span></span>

<span data-ttu-id="fe08a-746">不適用</span><span class="sxs-lookup"><span data-stu-id="fe08a-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-747">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-747">Definition</span></span>

<span data-ttu-id="fe08a-748">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-749">規則運算式`Regex_romania_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-750">從關鍵字`Keywords_romania_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fe08a-751">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="fe08a-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-753">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-753">tax id</span></span>
  
<span data-ttu-id="fe08a-754">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-754">tax id number</span></span>
  
<span data-ttu-id="fe08a-755">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="fe08a-755">tax file no</span></span>
  
<span data-ttu-id="fe08a-756">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-756">tax file number</span></span>
  
<span data-ttu-id="fe08a-757">稅務否</span><span class="sxs-lookup"><span data-stu-id="fe08a-757">tax no</span></span>
  
<span data-ttu-id="fe08a-758">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-758">tax number</span></span>
  
<span data-ttu-id="fe08a-759">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-759">taxid#</span></span>
  
<span data-ttu-id="fe08a-760">taxno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-760">taxno#</span></span>
  
<span data-ttu-id="fe08a-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="fe08a-761">id-ul taxei</span></span>
  
<span data-ttu-id="fe08a-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="fe08a-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="fe08a-763">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="fe08a-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-764">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-764">Format</span></span>

<span data-ttu-id="fe08a-765">不含空格或分隔符號的 10 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-766">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-766">Pattern</span></span>

<span data-ttu-id="fe08a-767">10 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fe08a-768">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-768">Checksum</span></span>

<span data-ttu-id="fe08a-769">不適用</span><span class="sxs-lookup"><span data-stu-id="fe08a-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-770">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-770">Definition</span></span>

<span data-ttu-id="fe08a-771">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-772">規則運算式`Regex_slovakia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-773">從關鍵字`Keywords_slovakia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fe08a-774">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="fe08a-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-776">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-776">tax id</span></span>
  
<span data-ttu-id="fe08a-777">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-777">tax id number</span></span>
  
<span data-ttu-id="fe08a-778">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-778">tin id</span></span>
  
<span data-ttu-id="fe08a-779">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="fe08a-779">tin no</span></span>
  
<span data-ttu-id="fe08a-780">斯洛伐克鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-780">slovakian tin id</span></span>
  
<span data-ttu-id="fe08a-781">錫</span><span class="sxs-lookup"><span data-stu-id="fe08a-781">tin</span></span>
  
<span data-ttu-id="fe08a-782">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="fe08a-782">tax file no</span></span>
  
<span data-ttu-id="fe08a-783">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-783">tax file number</span></span>
  
<span data-ttu-id="fe08a-784">稅務否</span><span class="sxs-lookup"><span data-stu-id="fe08a-784">tax no</span></span>
  
<span data-ttu-id="fe08a-785">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-785">tax number</span></span>
  
<span data-ttu-id="fe08a-786">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-786">taxid#</span></span>
  
<span data-ttu-id="fe08a-787">taxno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-787">taxno#</span></span>
  
<span data-ttu-id="fe08a-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="fe08a-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="fe08a-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="fe08a-789">daňové číslo</span></span>
  
<span data-ttu-id="fe08a-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="fe08a-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="fe08a-791">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="fe08a-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-792">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-792">Format</span></span>

<span data-ttu-id="fe08a-793">不含空格或分隔字元的八位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-794">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-794">Pattern</span></span>

<span data-ttu-id="fe08a-795">八位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fe08a-796">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-796">Checksum</span></span>

<span data-ttu-id="fe08a-797">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-798">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-798">Definition</span></span>

<span data-ttu-id="fe08a-799">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-800">函式`Func_slovenia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-801">從關鍵字`Keywords_slovenia_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-802">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-803">函式`Func_slovenia_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-804">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="fe08a-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-806">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-806">tax id</span></span>
  
<span data-ttu-id="fe08a-807">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-807">tax id number</span></span>
  
<span data-ttu-id="fe08a-808">鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-808">tin id</span></span>
  
<span data-ttu-id="fe08a-809">鐵皮否</span><span class="sxs-lookup"><span data-stu-id="fe08a-809">tin no</span></span>
  
<span data-ttu-id="fe08a-810">斯洛維尼亞文鐵皮識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-810">slovenian tin id</span></span>
  
<span data-ttu-id="fe08a-811">錫</span><span class="sxs-lookup"><span data-stu-id="fe08a-811">tin</span></span>
  
<span data-ttu-id="fe08a-812">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="fe08a-812">tax file no</span></span>
  
<span data-ttu-id="fe08a-813">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-813">tax file number</span></span>
  
<span data-ttu-id="fe08a-814">稅務否</span><span class="sxs-lookup"><span data-stu-id="fe08a-814">tax no</span></span>
  
<span data-ttu-id="fe08a-815">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-815">tax number</span></span>
  
<span data-ttu-id="fe08a-816">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-816">taxid#</span></span>
  
<span data-ttu-id="fe08a-817">taxno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-817">taxno#</span></span>
  
<span data-ttu-id="fe08a-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="fe08a-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="fe08a-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="fe08a-819">davčna številka</span></span>
  
<span data-ttu-id="fe08a-820">Številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="fe08a-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="fe08a-821">西班牙</span><span class="sxs-lookup"><span data-stu-id="fe08a-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-822">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-822">Format</span></span>

<span data-ttu-id="fe08a-823">7 或 8 位數與所指定的型態的一或兩個字母</span><span class="sxs-lookup"><span data-stu-id="fe08a-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-824">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-824">Pattern</span></span>

<span data-ttu-id="fe08a-825">西班牙文自然人西班牙國民身分證與：</span><span class="sxs-lookup"><span data-stu-id="fe08a-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="fe08a-826">八位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-826">Eight digits</span></span> 
    
- <span data-ttu-id="fe08a-827">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="fe08a-828">非駐留西班牙人沒有西班牙國民身分證</span><span class="sxs-lookup"><span data-stu-id="fe08a-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="fe08a-829">一個大寫字母"L"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="fe08a-830">七位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-830">Seven digits</span></span>
    
- <span data-ttu-id="fe08a-831">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="fe08a-832">[] 下的保留天數 14 年沒有西班牙國民身分證駐留西班牙人：</span><span class="sxs-lookup"><span data-stu-id="fe08a-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="fe08a-833">一個大寫字母"K"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="fe08a-834">七位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-834">Seven digits</span></span> 
    
- <span data-ttu-id="fe08a-835">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="fe08a-836">外國人與因此識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="fe08a-837">一個大寫也就是字母 「 X 」、 「 Y"或"Z"（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="fe08a-838">七位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-838">Seven digits</span></span>
    
- <span data-ttu-id="fe08a-839">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="fe08a-840">外國人沒有因此識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="fe08a-841">一個大寫字母，為 「 M 」 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="fe08a-842">七位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-842">Seven digits</span></span>
    
- <span data-ttu-id="fe08a-843">一個大寫字母 （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="fe08a-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="fe08a-844">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-844">Checksum</span></span>

<span data-ttu-id="fe08a-845">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-846">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-846">Definition</span></span>

<span data-ttu-id="fe08a-847">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-848">函式`Func_spain_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-849">從關鍵字`Keywords_spain_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-850">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-851">函式`Func_spain_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-852">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="fe08a-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-854">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-854">tax id</span></span>
  
<span data-ttu-id="fe08a-855">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-855">tax id number</span></span>
  
<span data-ttu-id="fe08a-856">cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-856">cif id</span></span>
  
<span data-ttu-id="fe08a-857">cif 沒有</span><span class="sxs-lookup"><span data-stu-id="fe08a-857">cif no</span></span>
  
<span data-ttu-id="fe08a-858">西班牙文的 cif 識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-858">spanish cif id</span></span>
  
<span data-ttu-id="fe08a-859">cif</span><span class="sxs-lookup"><span data-stu-id="fe08a-859">cif</span></span>
  
<span data-ttu-id="fe08a-860">不稅務檔案</span><span class="sxs-lookup"><span data-stu-id="fe08a-860">tax file no</span></span>
  
<span data-ttu-id="fe08a-861">西班牙文的 cif 數目</span><span class="sxs-lookup"><span data-stu-id="fe08a-861">spanish cif number</span></span>
  
<span data-ttu-id="fe08a-862">稅務檔案編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-862">tax file number</span></span>
  
<span data-ttu-id="fe08a-863">西班牙文的 cif 沒有</span><span class="sxs-lookup"><span data-stu-id="fe08a-863">spanish cif no</span></span>
  
<span data-ttu-id="fe08a-864">稅務否</span><span class="sxs-lookup"><span data-stu-id="fe08a-864">tax no</span></span>
  
<span data-ttu-id="fe08a-865">稅務編號</span><span class="sxs-lookup"><span data-stu-id="fe08a-865">tax number</span></span>
  
<span data-ttu-id="fe08a-866">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-866">taxid#</span></span>
  
<span data-ttu-id="fe08a-867">taxno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-867">taxno#</span></span>
  
<span data-ttu-id="fe08a-868">cifid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-868">cifid#</span></span>
  
<span data-ttu-id="fe08a-869">spanishcifid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-869">spanishcifid#</span></span>
  
<span data-ttu-id="fe08a-870">spanishcifno#</span><span class="sxs-lookup"><span data-stu-id="fe08a-870">spanishcifno#</span></span>
  
<span data-ttu-id="fe08a-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="fe08a-871">número de contribuyente</span></span>
  
<span data-ttu-id="fe08a-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="fe08a-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="fe08a-873">número de identificación 會計</span><span class="sxs-lookup"><span data-stu-id="fe08a-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="fe08a-874">cif número</span><span class="sxs-lookup"><span data-stu-id="fe08a-874">cif número</span></span>
  
<span data-ttu-id="fe08a-875">cifnúmero#</span><span class="sxs-lookup"><span data-stu-id="fe08a-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="fe08a-876">瑞典</span><span class="sxs-lookup"><span data-stu-id="fe08a-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-877">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-877">Format</span></span>

<span data-ttu-id="fe08a-878">十個數字和中指定的型態的符號</span><span class="sxs-lookup"><span data-stu-id="fe08a-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-879">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-879">Pattern</span></span>

<span data-ttu-id="fe08a-880">十個數字和符號：</span><span class="sxs-lookup"><span data-stu-id="fe08a-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="fe08a-881">會對應至 (YYMMDD) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="fe08a-882">加號、 減號或反斜線</span><span class="sxs-lookup"><span data-stu-id="fe08a-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="fe08a-883">請識別的三位數數字唯一的位置：</span><span class="sxs-lookup"><span data-stu-id="fe08a-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="fe08a-884">發行之前 1990年數字，如第七個和第八個數字識別出生或 foreign-born 人員郡</span><span class="sxs-lookup"><span data-stu-id="fe08a-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="fe08a-885">在第九個位置的數字，表示女性 1 女 2 男或甚至是任一奇數性別</span><span class="sxs-lookup"><span data-stu-id="fe08a-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="fe08a-886">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fe08a-887">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-887">Checksum</span></span>

<span data-ttu-id="fe08a-888">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-889">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-889">Definition</span></span>

<span data-ttu-id="fe08a-890">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-891">函式`Func_sweden_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-892">從關鍵字`Keywords_sweden_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fe08a-893">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-894">函式`Func_sweden_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="fe08a-895">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="fe08a-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-897">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-897">tax id</span></span>
  
<span data-ttu-id="fe08a-898">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="fe08a-898">tax id no.</span></span>
  
<span data-ttu-id="fe08a-899">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-899">tax id number</span></span>
  
<span data-ttu-id="fe08a-900">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-900">tax identification</span></span>
  
<span data-ttu-id="fe08a-901">稅務識別碼#</span><span class="sxs-lookup"><span data-stu-id="fe08a-901">tax identification#</span></span>
  
<span data-ttu-id="fe08a-902">稅務否。</span><span class="sxs-lookup"><span data-stu-id="fe08a-902">tax no.</span></span>
  
<span data-ttu-id="fe08a-903">稅務#</span><span class="sxs-lookup"><span data-stu-id="fe08a-903">tax#</span></span>
  
<span data-ttu-id="fe08a-904">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-904">taxid#</span></span>
  
<span data-ttu-id="fe08a-905">稅務檔案</span><span class="sxs-lookup"><span data-stu-id="fe08a-905">tax file</span></span>
  
<span data-ttu-id="fe08a-906">不稅務檔案。</span><span class="sxs-lookup"><span data-stu-id="fe08a-906">tax file no.</span></span>
  
<span data-ttu-id="fe08a-907">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-907">personal id number</span></span>
  
<span data-ttu-id="fe08a-908">skatt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-908">skatt id nummer</span></span>
  
<span data-ttu-id="fe08a-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="fe08a-909">skatt identifikation</span></span>
  
<span data-ttu-id="fe08a-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="fe08a-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="fe08a-911">英國</span><span class="sxs-lookup"><span data-stu-id="fe08a-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="fe08a-912">格式</span><span class="sxs-lookup"><span data-stu-id="fe08a-912">Format</span></span>

<span data-ttu-id="fe08a-913">如果沒有空格和分隔符號的唯一 Taxpayer 參照 (UTR): 10 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="fe08a-914">國家保險號碼 (NINO): 如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="fe08a-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="fe08a-915">國家保險號碼 (NINO) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="fe08a-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fe08a-916">模式</span><span class="sxs-lookup"><span data-stu-id="fe08a-916">Pattern</span></span>

<span data-ttu-id="fe08a-917">唯一 Taxpayer 參照 (UTR): 10 位數</span><span class="sxs-lookup"><span data-stu-id="fe08a-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="fe08a-918">國家保險號碼 (NINO): 如需詳細資訊，請參閱區段 」 英國</span><span class="sxs-lookup"><span data-stu-id="fe08a-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="fe08a-919">國家保險號碼 (NINO) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="fe08a-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fe08a-920">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-920">Checksum</span></span>

<span data-ttu-id="fe08a-921">是</span><span class="sxs-lookup"><span data-stu-id="fe08a-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fe08a-922">定義</span><span class="sxs-lookup"><span data-stu-id="fe08a-922">Definition</span></span>

<span data-ttu-id="fe08a-923">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="fe08a-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fe08a-924">函式`Func_uk_eu_tax_file_number`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="fe08a-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fe08a-925">從關鍵字`Keywords_uk_eu_tax_file_number`找到。</span><span class="sxs-lookup"><span data-stu-id="fe08a-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fe08a-926">關鍵字</span><span class="sxs-lookup"><span data-stu-id="fe08a-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="fe08a-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fe08a-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="fe08a-928">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-928">tax id</span></span>
  
<span data-ttu-id="fe08a-929">不稅務識別碼。</span><span class="sxs-lookup"><span data-stu-id="fe08a-929">tax id no.</span></span>
  
<span data-ttu-id="fe08a-930">稅務 id 號碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-930">tax id number</span></span>
  
<span data-ttu-id="fe08a-931">稅務識別碼</span><span class="sxs-lookup"><span data-stu-id="fe08a-931">tax identification</span></span>
  
<span data-ttu-id="fe08a-932">稅務識別碼#</span><span class="sxs-lookup"><span data-stu-id="fe08a-932">tax identification#</span></span>
  
<span data-ttu-id="fe08a-933">稅務否。</span><span class="sxs-lookup"><span data-stu-id="fe08a-933">tax no.</span></span>
  
<span data-ttu-id="fe08a-934">稅務#</span><span class="sxs-lookup"><span data-stu-id="fe08a-934">tax#</span></span>
  
<span data-ttu-id="fe08a-935">taxid#</span><span class="sxs-lookup"><span data-stu-id="fe08a-935">taxid#</span></span>
  
<span data-ttu-id="fe08a-936">稅務檔案</span><span class="sxs-lookup"><span data-stu-id="fe08a-936">tax file</span></span>
  
<span data-ttu-id="fe08a-937">不稅務檔案。</span><span class="sxs-lookup"><span data-stu-id="fe08a-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fe08a-938">請參閱</span><span class="sxs-lookup"><span data-stu-id="fe08a-938">See also</span></span>

[<span data-ttu-id="fe08a-939">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="fe08a-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

