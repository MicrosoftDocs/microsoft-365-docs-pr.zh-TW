---
title: 歐盟社會安全號碼或同等識別碼
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
description: 本主題說明資料遺失防護（DLP）原則在偵測到歐盟社會保險號碼或對等身分識別敏感資訊類型時，會尋找哪些專案。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
ms.openlocfilehash: 276b9f2d20c2c682df2a2072c1103ab9fc67a098
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938691"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="71511-104">歐盟社會安全號碼或同等識別碼</span><span class="sxs-lookup"><span data-stu-id="71511-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="71511-105">本主題說明資料遺失防護（DLP）原則在偵測到歐盟社會安全號碼（SSN）或對等識別碼敏感資訊類型時，會尋找的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="71511-106">這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。</span><span class="sxs-lookup"><span data-stu-id="71511-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="71511-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="71511-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="71511-108">格式</span><span class="sxs-lookup"><span data-stu-id="71511-108">Format</span></span>

<span data-ttu-id="71511-109">指定之格式的10位數</span><span class="sxs-lookup"><span data-stu-id="71511-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="71511-110">模式</span><span class="sxs-lookup"><span data-stu-id="71511-110">Pattern</span></span>

<span data-ttu-id="71511-111">10位數：</span><span class="sxs-lookup"><span data-stu-id="71511-111">10 digits:</span></span>
  
-  <span data-ttu-id="71511-112">對應至序列值的三位數</span><span class="sxs-lookup"><span data-stu-id="71511-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="71511-113">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="71511-113">One check digit</span></span>
    
- <span data-ttu-id="71511-114">與出生日期對應的六位數（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="71511-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="71511-115">校驗</span><span class="sxs-lookup"><span data-stu-id="71511-115">Checksum</span></span>

<span data-ttu-id="71511-116">是</span><span class="sxs-lookup"><span data-stu-id="71511-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="71511-117">定義</span><span class="sxs-lookup"><span data-stu-id="71511-117">Definition</span></span>

<span data-ttu-id="71511-118">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="71511-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-119">函數`Func_austria_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="71511-120">找到來自`Keywords_austria_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="71511-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="71511-121">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="71511-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-122">函數`Func_austria_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="71511-123">關鍵字</span><span class="sxs-lookup"><span data-stu-id="71511-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="71511-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="71511-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="71511-125">社會安全性否</span><span class="sxs-lookup"><span data-stu-id="71511-125">social security no</span></span>
  
<span data-ttu-id="71511-126">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="71511-126">social security number</span></span>
  
<span data-ttu-id="71511-127">社會安全性碼</span><span class="sxs-lookup"><span data-stu-id="71511-127">social security code</span></span>
  
<span data-ttu-id="71511-128">保險號碼</span><span class="sxs-lookup"><span data-stu-id="71511-128">insurance number</span></span>
  
<span data-ttu-id="71511-129">奧地利 ssn</span><span class="sxs-lookup"><span data-stu-id="71511-129">austrian ssn</span></span>
  
<span data-ttu-id="71511-130">Ssn#</span><span class="sxs-lookup"><span data-stu-id="71511-130">ssn#</span></span>
  
<span data-ttu-id="71511-131">Ssn</span><span class="sxs-lookup"><span data-stu-id="71511-131">ssn</span></span>
  
<span data-ttu-id="71511-132">保險業代碼</span><span class="sxs-lookup"><span data-stu-id="71511-132">insurance code</span></span>
  
<span data-ttu-id="71511-133">保險業代碼#</span><span class="sxs-lookup"><span data-stu-id="71511-133">insurance code#</span></span>
  
<span data-ttu-id="71511-134">socialsecurityno#</span><span class="sxs-lookup"><span data-stu-id="71511-134">socialsecurityno#</span></span>
  
<span data-ttu-id="71511-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="71511-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="71511-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="71511-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="71511-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="71511-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="71511-138">比利時</span><span class="sxs-lookup"><span data-stu-id="71511-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="71511-139">格式</span><span class="sxs-lookup"><span data-stu-id="71511-139">Format</span></span>

<span data-ttu-id="71511-140">11位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="71511-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="71511-141">模式</span><span class="sxs-lookup"><span data-stu-id="71511-141">Pattern</span></span>

<span data-ttu-id="71511-142">11位數</span><span class="sxs-lookup"><span data-stu-id="71511-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="71511-143">校驗</span><span class="sxs-lookup"><span data-stu-id="71511-143">Checksum</span></span>

<span data-ttu-id="71511-144">是</span><span class="sxs-lookup"><span data-stu-id="71511-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="71511-145">定義</span><span class="sxs-lookup"><span data-stu-id="71511-145">Definition</span></span>

<span data-ttu-id="71511-146">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="71511-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-147">函數`Func_belgium_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="71511-148">找到來自`Keywords_belgium_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="71511-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="71511-149">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="71511-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-150">函數`Func_belgium_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="71511-151">關鍵字</span><span class="sxs-lookup"><span data-stu-id="71511-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="71511-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="71511-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="71511-153">比利時國號碼</span><span class="sxs-lookup"><span data-stu-id="71511-153">belgian national number</span></span>
  
<span data-ttu-id="71511-154">國家/地區號碼</span><span class="sxs-lookup"><span data-stu-id="71511-154">national number</span></span>
  
<span data-ttu-id="71511-155">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="71511-155">social security number</span></span>
  
<span data-ttu-id="71511-156">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="71511-156">nationalnumber#</span></span>
  
<span data-ttu-id="71511-157">Ssn#</span><span class="sxs-lookup"><span data-stu-id="71511-157">ssn#</span></span>
  
<span data-ttu-id="71511-158">Ssn</span><span class="sxs-lookup"><span data-stu-id="71511-158">ssn</span></span>
  
<span data-ttu-id="71511-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="71511-159">nationalnumber</span></span>
  
<span data-ttu-id="71511-160">安娜#</span><span class="sxs-lookup"><span data-stu-id="71511-160">bnn#</span></span>
  
<span data-ttu-id="71511-161">安娜</span><span class="sxs-lookup"><span data-stu-id="71511-161">bnn</span></span>
  
<span data-ttu-id="71511-162">個人號碼</span><span class="sxs-lookup"><span data-stu-id="71511-162">personal id number</span></span>
  
<span data-ttu-id="71511-163">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="71511-163">personalidnumber#</span></span>
  
<span data-ttu-id="71511-164">本國 numéro</span><span class="sxs-lookup"><span data-stu-id="71511-164">numéro national</span></span>
  
<span data-ttu-id="71511-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="71511-165">numéro de sécurité</span></span>
  
<span data-ttu-id="71511-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="71511-166">numéro d'assuré</span></span>
  
<span data-ttu-id="71511-167">本國 identifiant</span><span class="sxs-lookup"><span data-stu-id="71511-167">identifiant national</span></span>
  
<span data-ttu-id="71511-168">identifiantnational#</span><span class="sxs-lookup"><span data-stu-id="71511-168">identifiantnational#</span></span>
  
<span data-ttu-id="71511-169">numéronational#</span><span class="sxs-lookup"><span data-stu-id="71511-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="71511-170">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="71511-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="71511-171">格式</span><span class="sxs-lookup"><span data-stu-id="71511-171">Format</span></span>

<span data-ttu-id="71511-172">11位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="71511-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="71511-173">模式</span><span class="sxs-lookup"><span data-stu-id="71511-173">Pattern</span></span>

 <span data-ttu-id="71511-174">11位數：</span><span class="sxs-lookup"><span data-stu-id="71511-174">11 digits:</span></span> 
  
-  <span data-ttu-id="71511-175">10位數</span><span class="sxs-lookup"><span data-stu-id="71511-175">Ten digits</span></span> 
    
- <span data-ttu-id="71511-176">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="71511-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="71511-177">校驗</span><span class="sxs-lookup"><span data-stu-id="71511-177">Checksum</span></span>

<span data-ttu-id="71511-178">是</span><span class="sxs-lookup"><span data-stu-id="71511-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="71511-179">定義</span><span class="sxs-lookup"><span data-stu-id="71511-179">Definition</span></span>

<span data-ttu-id="71511-180">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="71511-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-181">函數`Func_croatia_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="71511-182">找到來自`Keywords_croatia_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="71511-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="71511-183">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="71511-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-184">函數`Func_croatia_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="71511-185">關鍵字</span><span class="sxs-lookup"><span data-stu-id="71511-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="71511-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="71511-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="71511-187">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="71511-187">personal identification number</span></span>
  
<span data-ttu-id="71511-188">主機公民號碼</span><span class="sxs-lookup"><span data-stu-id="71511-188">master citizen number</span></span>
  
<span data-ttu-id="71511-189">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="71511-189">national identification number</span></span>
  
<span data-ttu-id="71511-190">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="71511-190">social security number</span></span>
  
<span data-ttu-id="71511-191">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="71511-191">nationalnumber#</span></span>
  
<span data-ttu-id="71511-192">Ssn#</span><span class="sxs-lookup"><span data-stu-id="71511-192">ssn#</span></span>
  
<span data-ttu-id="71511-193">Ssn</span><span class="sxs-lookup"><span data-stu-id="71511-193">ssn</span></span>
  
<span data-ttu-id="71511-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="71511-194">nationalnumber</span></span>
  
<span data-ttu-id="71511-195">安娜#</span><span class="sxs-lookup"><span data-stu-id="71511-195">bnn#</span></span>
  
<span data-ttu-id="71511-196">安娜</span><span class="sxs-lookup"><span data-stu-id="71511-196">bnn</span></span>
  
<span data-ttu-id="71511-197">個人號碼</span><span class="sxs-lookup"><span data-stu-id="71511-197">personal id number</span></span>
  
<span data-ttu-id="71511-198">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="71511-198">personalidnumber#</span></span>
  
<span data-ttu-id="71511-199">oib</span><span class="sxs-lookup"><span data-stu-id="71511-199">oib</span></span>
  
<span data-ttu-id="71511-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="71511-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="71511-201">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="71511-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="71511-202">格式</span><span class="sxs-lookup"><span data-stu-id="71511-202">Format</span></span>

<span data-ttu-id="71511-203">指定之模式中的10位數和反斜線</span><span class="sxs-lookup"><span data-stu-id="71511-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="71511-204">模式</span><span class="sxs-lookup"><span data-stu-id="71511-204">Pattern</span></span>

<span data-ttu-id="71511-205">10位數和反斜線：</span><span class="sxs-lookup"><span data-stu-id="71511-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="71511-206">對應至出生日期的六位數（YYMMDD）：</span><span class="sxs-lookup"><span data-stu-id="71511-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="71511-207">反斜線</span><span class="sxs-lookup"><span data-stu-id="71511-207">A backslash</span></span>
    
- <span data-ttu-id="71511-208">三位數的數位，對應至在相同日期出生的人員</span><span class="sxs-lookup"><span data-stu-id="71511-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="71511-209">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="71511-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="71511-210">校驗</span><span class="sxs-lookup"><span data-stu-id="71511-210">Checksum</span></span>

<span data-ttu-id="71511-211">是</span><span class="sxs-lookup"><span data-stu-id="71511-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="71511-212">定義</span><span class="sxs-lookup"><span data-stu-id="71511-212">Definition</span></span>

<span data-ttu-id="71511-213">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="71511-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-214">函數`Func_czech_republic_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="71511-215">找到來自`Keywords_czech_republic_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="71511-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="71511-216">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="71511-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-217">函數`Func_czech_republic_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="71511-218">關鍵字</span><span class="sxs-lookup"><span data-stu-id="71511-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="71511-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="71511-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="71511-220">出生號碼</span><span class="sxs-lookup"><span data-stu-id="71511-220">birth number</span></span>
  
<span data-ttu-id="71511-221">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="71511-221">national identification number</span></span>
  
<span data-ttu-id="71511-222">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="71511-222">personal identification number</span></span>
  
<span data-ttu-id="71511-223">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="71511-223">social security number</span></span>
  
<span data-ttu-id="71511-224">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="71511-224">nationalnumber#</span></span>
  
<span data-ttu-id="71511-225">Ssn#</span><span class="sxs-lookup"><span data-stu-id="71511-225">ssn#</span></span>
  
<span data-ttu-id="71511-226">Ssn</span><span class="sxs-lookup"><span data-stu-id="71511-226">ssn</span></span>
  
<span data-ttu-id="71511-227">國家/地區號碼</span><span class="sxs-lookup"><span data-stu-id="71511-227">national number</span></span>
  
<span data-ttu-id="71511-228">個人號碼</span><span class="sxs-lookup"><span data-stu-id="71511-228">personal id number</span></span>
  
<span data-ttu-id="71511-229">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="71511-229">personalidnumber#</span></span>
  
<span data-ttu-id="71511-230">rč</span><span class="sxs-lookup"><span data-stu-id="71511-230">rč</span></span>
  
<span data-ttu-id="71511-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="71511-231">rodné číslo</span></span>
  
<span data-ttu-id="71511-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="71511-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="71511-233">丹麥</span><span class="sxs-lookup"><span data-stu-id="71511-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="71511-234">格式</span><span class="sxs-lookup"><span data-stu-id="71511-234">Format</span></span>

<span data-ttu-id="71511-235">在指定的模式中，10位數和連字號</span><span class="sxs-lookup"><span data-stu-id="71511-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="71511-236">模式</span><span class="sxs-lookup"><span data-stu-id="71511-236">Pattern</span></span>

<span data-ttu-id="71511-237">10位數和連字號：</span><span class="sxs-lookup"><span data-stu-id="71511-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="71511-238">與出生日期對應的六位數（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="71511-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="71511-239">連字號</span><span class="sxs-lookup"><span data-stu-id="71511-239">A hyphen</span></span>
    
- <span data-ttu-id="71511-240">對應至序號的四位數</span><span class="sxs-lookup"><span data-stu-id="71511-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="71511-241">校驗</span><span class="sxs-lookup"><span data-stu-id="71511-241">Checksum</span></span>

<span data-ttu-id="71511-242">是</span><span class="sxs-lookup"><span data-stu-id="71511-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="71511-243">定義</span><span class="sxs-lookup"><span data-stu-id="71511-243">Definition</span></span>

<span data-ttu-id="71511-244">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="71511-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-245">函數`Func_denmark_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="71511-246">找到來自`Keywords_denmark_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="71511-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="71511-247">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="71511-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-248">函數`Func_denmark_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="71511-249">關鍵字</span><span class="sxs-lookup"><span data-stu-id="71511-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="71511-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="71511-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="71511-251">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="71511-251">personal identification number</span></span>
  
<span data-ttu-id="71511-252">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="71511-252">national identification number</span></span>
  
<span data-ttu-id="71511-253">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="71511-253">social security number</span></span>
  
<span data-ttu-id="71511-254">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="71511-254">nationalnumber#</span></span>
  
<span data-ttu-id="71511-255">Ssn#</span><span class="sxs-lookup"><span data-stu-id="71511-255">ssn#</span></span>
  
<span data-ttu-id="71511-256">Ssn</span><span class="sxs-lookup"><span data-stu-id="71511-256">ssn</span></span>
  
<span data-ttu-id="71511-257">國家/地區號碼</span><span class="sxs-lookup"><span data-stu-id="71511-257">national number</span></span>
  
<span data-ttu-id="71511-258">個人號碼</span><span class="sxs-lookup"><span data-stu-id="71511-258">personal id number</span></span>
  
<span data-ttu-id="71511-259">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="71511-259">personalidnumber#</span></span>
  
<span data-ttu-id="71511-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="71511-260">cpr-nummer</span></span>
  
<span data-ttu-id="71511-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="71511-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="71511-262">芬蘭</span><span class="sxs-lookup"><span data-stu-id="71511-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="71511-263">格式</span><span class="sxs-lookup"><span data-stu-id="71511-263">Format</span></span>

<span data-ttu-id="71511-264">以指定格式為11個字元的組合</span><span class="sxs-lookup"><span data-stu-id="71511-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="71511-265">模式</span><span class="sxs-lookup"><span data-stu-id="71511-265">Pattern</span></span>

<span data-ttu-id="71511-266">以指定格式為11個字元的組合：</span><span class="sxs-lookup"><span data-stu-id="71511-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="71511-267">六位數</span><span class="sxs-lookup"><span data-stu-id="71511-267">Six digits</span></span> 
    
- <span data-ttu-id="71511-268">下列其中一個範例：</span><span class="sxs-lookup"><span data-stu-id="71511-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="71511-269">加號</span><span class="sxs-lookup"><span data-stu-id="71511-269">Plus symbol</span></span>
    
  - <span data-ttu-id="71511-270">負號</span><span class="sxs-lookup"><span data-stu-id="71511-270">Minus symbol</span></span>
    
  - <span data-ttu-id="71511-271">字母 "A" （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="71511-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="71511-272">三位數</span><span class="sxs-lookup"><span data-stu-id="71511-272">Three digits</span></span>
    
- <span data-ttu-id="71511-273">一個字母或一個數位</span><span class="sxs-lookup"><span data-stu-id="71511-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="71511-274">校驗</span><span class="sxs-lookup"><span data-stu-id="71511-274">Checksum</span></span>

<span data-ttu-id="71511-275">是</span><span class="sxs-lookup"><span data-stu-id="71511-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="71511-276">定義</span><span class="sxs-lookup"><span data-stu-id="71511-276">Definition</span></span>

<span data-ttu-id="71511-277">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="71511-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-278">函數`Func_finland_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="71511-279">找到來自`Keywords_finland_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="71511-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="71511-280">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="71511-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-281">函數`Func_finland_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="71511-282">關鍵字</span><span class="sxs-lookup"><span data-stu-id="71511-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="71511-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="71511-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="71511-284">識別號碼</span><span class="sxs-lookup"><span data-stu-id="71511-284">identification number</span></span>
  
<span data-ttu-id="71511-285">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="71511-285">personal id</span></span>
  
<span data-ttu-id="71511-286">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="71511-286">identity number</span></span>
  
<span data-ttu-id="71511-287">芬蘭文身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="71511-287">finnish national id number</span></span>
  
<span data-ttu-id="71511-288">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="71511-288">personalidnumber#</span></span>
  
<span data-ttu-id="71511-289">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="71511-289">national identification number</span></span>
  
<span data-ttu-id="71511-290">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="71511-290">id number</span></span>
  
<span data-ttu-id="71511-291">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="71511-291">national id no.</span></span>
  
<span data-ttu-id="71511-292">本國識別碼</span><span class="sxs-lookup"><span data-stu-id="71511-292">national id number</span></span>
  
<span data-ttu-id="71511-293">識別碼 no</span><span class="sxs-lookup"><span data-stu-id="71511-293">id no</span></span>
  
<span data-ttu-id="71511-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="71511-294">tunnistenumero</span></span>
  
<span data-ttu-id="71511-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="71511-295">henkilötunnus</span></span>
  
<span data-ttu-id="71511-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="71511-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="71511-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="71511-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="71511-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="71511-298">identiteetti numero</span></span>
  
<span data-ttu-id="71511-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="71511-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="71511-300">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="71511-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="71511-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="71511-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="71511-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="71511-302">tunnusnumero</span></span>
  
<span data-ttu-id="71511-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="71511-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="71511-304">hetu</span><span class="sxs-lookup"><span data-stu-id="71511-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="71511-305">法國</span><span class="sxs-lookup"><span data-stu-id="71511-305">France</span></span>

<span data-ttu-id="71511-306">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「法國社會安全性號碼（INSEE）」一節。</span><span class="sxs-lookup"><span data-stu-id="71511-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="71511-307">德國</span><span class="sxs-lookup"><span data-stu-id="71511-307">Germany</span></span>

<span data-ttu-id="71511-308">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「德國身分識別卡片編號」一節。</span><span class="sxs-lookup"><span data-stu-id="71511-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="71511-309">希臘</span><span class="sxs-lookup"><span data-stu-id="71511-309">Greece</span></span>

<span data-ttu-id="71511-310">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「希臘國 ID 卡」一節。</span><span class="sxs-lookup"><span data-stu-id="71511-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="71511-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="71511-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="71511-312">格式</span><span class="sxs-lookup"><span data-stu-id="71511-312">Format</span></span>

<span data-ttu-id="71511-313">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="71511-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="71511-314">模式</span><span class="sxs-lookup"><span data-stu-id="71511-314">Pattern</span></span>

<span data-ttu-id="71511-315">九位數</span><span class="sxs-lookup"><span data-stu-id="71511-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="71511-316">校驗</span><span class="sxs-lookup"><span data-stu-id="71511-316">Checksum</span></span>

<span data-ttu-id="71511-317">是</span><span class="sxs-lookup"><span data-stu-id="71511-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="71511-318">定義</span><span class="sxs-lookup"><span data-stu-id="71511-318">Definition</span></span>

<span data-ttu-id="71511-319">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="71511-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-320">函數`Func_hungary_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="71511-321">找到來自`Keywords_hungary_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="71511-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="71511-322">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="71511-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-323">函數`Func_hungary_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="71511-324">關鍵字</span><span class="sxs-lookup"><span data-stu-id="71511-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="71511-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="71511-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="71511-326">匈牙利文社交安全性號碼</span><span class="sxs-lookup"><span data-stu-id="71511-326">hungarian social security number</span></span>
  
<span data-ttu-id="71511-327">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="71511-327">social security number</span></span>
  
<span data-ttu-id="71511-328">socialsecuritynumber#</span><span class="sxs-lookup"><span data-stu-id="71511-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="71511-329">hssn#</span><span class="sxs-lookup"><span data-stu-id="71511-329">hssn#</span></span>
  
<span data-ttu-id="71511-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="71511-330">socialsecuritynno</span></span>
  
<span data-ttu-id="71511-331">hssn</span><span class="sxs-lookup"><span data-stu-id="71511-331">hssn</span></span>
  
<span data-ttu-id="71511-332">泰姬陵</span><span class="sxs-lookup"><span data-stu-id="71511-332">taj</span></span>
  
<span data-ttu-id="71511-333">泰姬陵#</span><span class="sxs-lookup"><span data-stu-id="71511-333">taj#</span></span>
  
<span data-ttu-id="71511-334">Ssn</span><span class="sxs-lookup"><span data-stu-id="71511-334">ssn</span></span>
  
<span data-ttu-id="71511-335">Ssn#</span><span class="sxs-lookup"><span data-stu-id="71511-335">ssn#</span></span>
  
<span data-ttu-id="71511-336">社會安全性否</span><span class="sxs-lookup"><span data-stu-id="71511-336">social security no</span></span>
  
<span data-ttu-id="71511-337">áfa</span><span class="sxs-lookup"><span data-stu-id="71511-337">áfa</span></span>
  
<span data-ttu-id="71511-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="71511-338">közösségi adószám</span></span>
  
<span data-ttu-id="71511-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="71511-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="71511-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="71511-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="71511-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="71511-341">áfa szám</span></span>
  
<span data-ttu-id="71511-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="71511-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="71511-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="71511-343">Portugal</span></span>

<span data-ttu-id="71511-344">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「葡萄牙公民卡片編號」一節。</span><span class="sxs-lookup"><span data-stu-id="71511-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="71511-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="71511-345">Spain</span></span>

<span data-ttu-id="71511-346">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「西班牙社會安全性號碼（SSN）」一節。</span><span class="sxs-lookup"><span data-stu-id="71511-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="71511-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="71511-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="71511-348">格式</span><span class="sxs-lookup"><span data-stu-id="71511-348">Format</span></span>

<span data-ttu-id="71511-349">12位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="71511-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="71511-350">模式</span><span class="sxs-lookup"><span data-stu-id="71511-350">Pattern</span></span>

<span data-ttu-id="71511-351">12位數：</span><span class="sxs-lookup"><span data-stu-id="71511-351">12 digits:</span></span>
  
-  <span data-ttu-id="71511-352">對應至出生日期的八位數（YYYYMMDD）</span><span class="sxs-lookup"><span data-stu-id="71511-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="71511-353">對應至序數的三位數，其中：</span><span class="sxs-lookup"><span data-stu-id="71511-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="71511-354">序數中的最後一個數位是由為男指派的奇數和偶數的女數位來表示性別</span><span class="sxs-lookup"><span data-stu-id="71511-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="71511-355">最多1990，corresponded 序數的指派給在該縣內，號碼的持有者是出生的，或（如果是在1947之前出生），在該縣中，根據稅收記錄，在年1月 1 1947 日，使用特殊的程式碼（通常是9，7位數）進行 immigrants</span><span class="sxs-lookup"><span data-stu-id="71511-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="71511-356">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="71511-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="71511-357">校驗</span><span class="sxs-lookup"><span data-stu-id="71511-357">Checksum</span></span>

<span data-ttu-id="71511-358">是</span><span class="sxs-lookup"><span data-stu-id="71511-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="71511-359">定義</span><span class="sxs-lookup"><span data-stu-id="71511-359">Definition</span></span>

<span data-ttu-id="71511-360">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="71511-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-361">函數`Func_sweden_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="71511-362">找到來自`Keywords_sweden_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="71511-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="71511-363">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="71511-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="71511-364">函數`Func_sweden_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="71511-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="71511-365">關鍵字</span><span class="sxs-lookup"><span data-stu-id="71511-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="71511-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="71511-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="71511-367">個人號碼</span><span class="sxs-lookup"><span data-stu-id="71511-367">personal id number</span></span>
  
<span data-ttu-id="71511-368">識別號碼</span><span class="sxs-lookup"><span data-stu-id="71511-368">identification number</span></span>
  
<span data-ttu-id="71511-369">個人識別碼否</span><span class="sxs-lookup"><span data-stu-id="71511-369">personal id no</span></span>
  
<span data-ttu-id="71511-370">identity no</span><span class="sxs-lookup"><span data-stu-id="71511-370">identity no</span></span>
  
<span data-ttu-id="71511-371">識別碼否</span><span class="sxs-lookup"><span data-stu-id="71511-371">identification no</span></span>
  
<span data-ttu-id="71511-372">個人身分識別否</span><span class="sxs-lookup"><span data-stu-id="71511-372">personal identification no</span></span>
  
<span data-ttu-id="71511-373">personnummer 識別碼</span><span class="sxs-lookup"><span data-stu-id="71511-373">personnummer id</span></span>
  
<span data-ttu-id="71511-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="71511-374">personligt id-nummer</span></span>
  
<span data-ttu-id="71511-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="71511-375">unikt id-nummer</span></span>
  
<span data-ttu-id="71511-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="71511-376">personnummer</span></span>
  
<span data-ttu-id="71511-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="71511-377">identifikationsnumret</span></span>
  
<span data-ttu-id="71511-378">personnummer#</span><span class="sxs-lookup"><span data-stu-id="71511-378">personnummer#</span></span>
  
<span data-ttu-id="71511-379">identifikationsnumret#</span><span class="sxs-lookup"><span data-stu-id="71511-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="71511-380">另請參閱</span><span class="sxs-lookup"><span data-stu-id="71511-380">See also</span></span>

[<span data-ttu-id="71511-381">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="71511-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

