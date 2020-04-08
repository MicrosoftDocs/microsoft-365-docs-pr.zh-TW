---
title: 歐盟社會安全號碼或同等識別碼
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
description: 本主題說明資料遺失防護（DLP）原則在偵測到歐盟社會保險號碼或對等身分識別敏感資訊類型時，會尋找哪些專案。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
ms.openlocfilehash: 1f2d1d9c61f27fb47b0c7ac0ce544b17175d4254
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2020
ms.locfileid: "41591224"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="09ad0-104">歐盟社會安全號碼或同等識別碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="09ad0-105">本主題說明資料遺失防護（DLP）原則在偵測到歐盟社會安全號碼（SSN）或對等識別碼敏感資訊類型時，會尋找的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="09ad0-106">這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。</span><span class="sxs-lookup"><span data-stu-id="09ad0-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="09ad0-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="09ad0-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="09ad0-108">格式</span><span class="sxs-lookup"><span data-stu-id="09ad0-108">Format</span></span>

<span data-ttu-id="09ad0-109">指定之格式的10位數</span><span class="sxs-lookup"><span data-stu-id="09ad0-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09ad0-110">模式</span><span class="sxs-lookup"><span data-stu-id="09ad0-110">Pattern</span></span>

<span data-ttu-id="09ad0-111">10位數：</span><span class="sxs-lookup"><span data-stu-id="09ad0-111">10 digits:</span></span>
  
-  <span data-ttu-id="09ad0-112">對應至序列值的三位數</span><span class="sxs-lookup"><span data-stu-id="09ad0-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="09ad0-113">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-113">One check digit</span></span>
    
- <span data-ttu-id="09ad0-114">與出生日期對應的六位數（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="09ad0-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09ad0-115">校驗</span><span class="sxs-lookup"><span data-stu-id="09ad0-115">Checksum</span></span>

<span data-ttu-id="09ad0-116">是</span><span class="sxs-lookup"><span data-stu-id="09ad0-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="09ad0-117">定義</span><span class="sxs-lookup"><span data-stu-id="09ad0-117">Definition</span></span>

<span data-ttu-id="09ad0-118">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-119">函數`Func_austria_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09ad0-120">找到來自`Keywords_austria_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="09ad0-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="09ad0-121">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-122">函數`Func_austria_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="09ad0-123">關鍵字</span><span class="sxs-lookup"><span data-stu-id="09ad0-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="09ad0-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="09ad0-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="09ad0-125">社會安全性否</span><span class="sxs-lookup"><span data-stu-id="09ad0-125">social security no</span></span>
  
<span data-ttu-id="09ad0-126">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-126">social security number</span></span>
  
<span data-ttu-id="09ad0-127">社會安全性碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-127">social security code</span></span>
  
<span data-ttu-id="09ad0-128">保險號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-128">insurance number</span></span>
  
<span data-ttu-id="09ad0-129">奧地利 ssn</span><span class="sxs-lookup"><span data-stu-id="09ad0-129">austrian ssn</span></span>
  
<span data-ttu-id="09ad0-130">Ssn#</span><span class="sxs-lookup"><span data-stu-id="09ad0-130">ssn#</span></span>
  
<span data-ttu-id="09ad0-131">Ssn</span><span class="sxs-lookup"><span data-stu-id="09ad0-131">ssn</span></span>
  
<span data-ttu-id="09ad0-132">保險業代碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-132">insurance code</span></span>
  
<span data-ttu-id="09ad0-133">保險業代碼#</span><span class="sxs-lookup"><span data-stu-id="09ad0-133">insurance code#</span></span>
  
<span data-ttu-id="09ad0-134">socialsecurityno#</span><span class="sxs-lookup"><span data-stu-id="09ad0-134">socialsecurityno#</span></span>
  
<span data-ttu-id="09ad0-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="09ad0-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="09ad0-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="09ad0-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="09ad0-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="09ad0-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="09ad0-138">比利時</span><span class="sxs-lookup"><span data-stu-id="09ad0-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="09ad0-139">格式</span><span class="sxs-lookup"><span data-stu-id="09ad0-139">Format</span></span>

<span data-ttu-id="09ad0-140">11位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="09ad0-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09ad0-141">模式</span><span class="sxs-lookup"><span data-stu-id="09ad0-141">Pattern</span></span>

<span data-ttu-id="09ad0-142">11位數</span><span class="sxs-lookup"><span data-stu-id="09ad0-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09ad0-143">校驗</span><span class="sxs-lookup"><span data-stu-id="09ad0-143">Checksum</span></span>

<span data-ttu-id="09ad0-144">是</span><span class="sxs-lookup"><span data-stu-id="09ad0-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="09ad0-145">定義</span><span class="sxs-lookup"><span data-stu-id="09ad0-145">Definition</span></span>

<span data-ttu-id="09ad0-146">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-147">函數`Func_belgium_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09ad0-148">找到來自`Keywords_belgium_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="09ad0-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="09ad0-149">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-150">函數`Func_belgium_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="09ad0-151">關鍵字</span><span class="sxs-lookup"><span data-stu-id="09ad0-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="09ad0-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="09ad0-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="09ad0-153">比利時國號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-153">belgian national number</span></span>
  
<span data-ttu-id="09ad0-154">國家/地區號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-154">national number</span></span>
  
<span data-ttu-id="09ad0-155">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-155">social security number</span></span>
  
<span data-ttu-id="09ad0-156">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="09ad0-156">nationalnumber#</span></span>
  
<span data-ttu-id="09ad0-157">Ssn#</span><span class="sxs-lookup"><span data-stu-id="09ad0-157">ssn#</span></span>
  
<span data-ttu-id="09ad0-158">Ssn</span><span class="sxs-lookup"><span data-stu-id="09ad0-158">ssn</span></span>
  
<span data-ttu-id="09ad0-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="09ad0-159">nationalnumber</span></span>
  
<span data-ttu-id="09ad0-160">安娜#</span><span class="sxs-lookup"><span data-stu-id="09ad0-160">bnn#</span></span>
  
<span data-ttu-id="09ad0-161">安娜</span><span class="sxs-lookup"><span data-stu-id="09ad0-161">bnn</span></span>
  
<span data-ttu-id="09ad0-162">個人號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-162">personal id number</span></span>
  
<span data-ttu-id="09ad0-163">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="09ad0-163">personalidnumber#</span></span>
  
<span data-ttu-id="09ad0-164">本國 numéro</span><span class="sxs-lookup"><span data-stu-id="09ad0-164">numéro national</span></span>
  
<span data-ttu-id="09ad0-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="09ad0-165">numéro de sécurité</span></span>
  
<span data-ttu-id="09ad0-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="09ad0-166">numéro d'assuré</span></span>
  
<span data-ttu-id="09ad0-167">本國 identifiant</span><span class="sxs-lookup"><span data-stu-id="09ad0-167">identifiant national</span></span>
  
<span data-ttu-id="09ad0-168">identifiantnational#</span><span class="sxs-lookup"><span data-stu-id="09ad0-168">identifiantnational#</span></span>
  
<span data-ttu-id="09ad0-169">numéronational#</span><span class="sxs-lookup"><span data-stu-id="09ad0-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="09ad0-170">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="09ad0-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="09ad0-171">格式</span><span class="sxs-lookup"><span data-stu-id="09ad0-171">Format</span></span>

<span data-ttu-id="09ad0-172">11位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="09ad0-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09ad0-173">模式</span><span class="sxs-lookup"><span data-stu-id="09ad0-173">Pattern</span></span>

 <span data-ttu-id="09ad0-174">11位數：</span><span class="sxs-lookup"><span data-stu-id="09ad0-174">11 digits:</span></span> 
  
-  <span data-ttu-id="09ad0-175">10位數</span><span class="sxs-lookup"><span data-stu-id="09ad0-175">Ten digits</span></span> 
    
- <span data-ttu-id="09ad0-176">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09ad0-177">校驗</span><span class="sxs-lookup"><span data-stu-id="09ad0-177">Checksum</span></span>

<span data-ttu-id="09ad0-178">是</span><span class="sxs-lookup"><span data-stu-id="09ad0-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="09ad0-179">定義</span><span class="sxs-lookup"><span data-stu-id="09ad0-179">Definition</span></span>

<span data-ttu-id="09ad0-180">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-181">函數`Func_croatia_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09ad0-182">找到來自`Keywords_croatia_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="09ad0-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="09ad0-183">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-184">函數`Func_croatia_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="09ad0-185">關鍵字</span><span class="sxs-lookup"><span data-stu-id="09ad0-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="09ad0-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="09ad0-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="09ad0-187">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-187">personal identification number</span></span>
  
<span data-ttu-id="09ad0-188">主機公民號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-188">master citizen number</span></span>
  
<span data-ttu-id="09ad0-189">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-189">national identification number</span></span>
  
<span data-ttu-id="09ad0-190">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-190">social security number</span></span>
  
<span data-ttu-id="09ad0-191">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="09ad0-191">nationalnumber#</span></span>
  
<span data-ttu-id="09ad0-192">Ssn#</span><span class="sxs-lookup"><span data-stu-id="09ad0-192">ssn#</span></span>
  
<span data-ttu-id="09ad0-193">Ssn</span><span class="sxs-lookup"><span data-stu-id="09ad0-193">ssn</span></span>
  
<span data-ttu-id="09ad0-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="09ad0-194">nationalnumber</span></span>
  
<span data-ttu-id="09ad0-195">安娜#</span><span class="sxs-lookup"><span data-stu-id="09ad0-195">bnn#</span></span>
  
<span data-ttu-id="09ad0-196">安娜</span><span class="sxs-lookup"><span data-stu-id="09ad0-196">bnn</span></span>
  
<span data-ttu-id="09ad0-197">個人號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-197">personal id number</span></span>
  
<span data-ttu-id="09ad0-198">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="09ad0-198">personalidnumber#</span></span>
  
<span data-ttu-id="09ad0-199">oib</span><span class="sxs-lookup"><span data-stu-id="09ad0-199">oib</span></span>
  
<span data-ttu-id="09ad0-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="09ad0-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="09ad0-201">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="09ad0-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="09ad0-202">格式</span><span class="sxs-lookup"><span data-stu-id="09ad0-202">Format</span></span>

<span data-ttu-id="09ad0-203">指定之模式中的10位數和反斜線</span><span class="sxs-lookup"><span data-stu-id="09ad0-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09ad0-204">模式</span><span class="sxs-lookup"><span data-stu-id="09ad0-204">Pattern</span></span>

<span data-ttu-id="09ad0-205">10位數和反斜線：</span><span class="sxs-lookup"><span data-stu-id="09ad0-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="09ad0-206">對應至出生日期的六位數（YYMMDD）：</span><span class="sxs-lookup"><span data-stu-id="09ad0-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="09ad0-207">反斜線</span><span class="sxs-lookup"><span data-stu-id="09ad0-207">A backslash</span></span>
    
- <span data-ttu-id="09ad0-208">三位數的數位，對應至在相同日期出生的人員</span><span class="sxs-lookup"><span data-stu-id="09ad0-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="09ad0-209">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09ad0-210">校驗</span><span class="sxs-lookup"><span data-stu-id="09ad0-210">Checksum</span></span>

<span data-ttu-id="09ad0-211">是</span><span class="sxs-lookup"><span data-stu-id="09ad0-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="09ad0-212">定義</span><span class="sxs-lookup"><span data-stu-id="09ad0-212">Definition</span></span>

<span data-ttu-id="09ad0-213">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-214">函數`Func_czech_republic_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09ad0-215">找到來自`Keywords_czech_republic_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="09ad0-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="09ad0-216">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-217">函數`Func_czech_republic_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="09ad0-218">關鍵字</span><span class="sxs-lookup"><span data-stu-id="09ad0-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="09ad0-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="09ad0-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="09ad0-220">出生號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-220">birth number</span></span>
  
<span data-ttu-id="09ad0-221">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-221">national identification number</span></span>
  
<span data-ttu-id="09ad0-222">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-222">personal identification number</span></span>
  
<span data-ttu-id="09ad0-223">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-223">social security number</span></span>
  
<span data-ttu-id="09ad0-224">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="09ad0-224">nationalnumber#</span></span>
  
<span data-ttu-id="09ad0-225">Ssn#</span><span class="sxs-lookup"><span data-stu-id="09ad0-225">ssn#</span></span>
  
<span data-ttu-id="09ad0-226">Ssn</span><span class="sxs-lookup"><span data-stu-id="09ad0-226">ssn</span></span>
  
<span data-ttu-id="09ad0-227">國家/地區號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-227">national number</span></span>
  
<span data-ttu-id="09ad0-228">個人號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-228">personal id number</span></span>
  
<span data-ttu-id="09ad0-229">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="09ad0-229">personalidnumber#</span></span>
  
<span data-ttu-id="09ad0-230">rč</span><span class="sxs-lookup"><span data-stu-id="09ad0-230">rč</span></span>
  
<span data-ttu-id="09ad0-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="09ad0-231">rodné číslo</span></span>
  
<span data-ttu-id="09ad0-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="09ad0-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="09ad0-233">丹麥</span><span class="sxs-lookup"><span data-stu-id="09ad0-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="09ad0-234">格式</span><span class="sxs-lookup"><span data-stu-id="09ad0-234">Format</span></span>

<span data-ttu-id="09ad0-235">在指定的模式中，10位數和連字號</span><span class="sxs-lookup"><span data-stu-id="09ad0-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09ad0-236">模式</span><span class="sxs-lookup"><span data-stu-id="09ad0-236">Pattern</span></span>

<span data-ttu-id="09ad0-237">10位數和連字號：</span><span class="sxs-lookup"><span data-stu-id="09ad0-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="09ad0-238">與出生日期對應的六位數（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="09ad0-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="09ad0-239">連字號</span><span class="sxs-lookup"><span data-stu-id="09ad0-239">A hyphen</span></span>
    
- <span data-ttu-id="09ad0-240">對應至序號的四位數</span><span class="sxs-lookup"><span data-stu-id="09ad0-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09ad0-241">校驗</span><span class="sxs-lookup"><span data-stu-id="09ad0-241">Checksum</span></span>

<span data-ttu-id="09ad0-242">是</span><span class="sxs-lookup"><span data-stu-id="09ad0-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="09ad0-243">定義</span><span class="sxs-lookup"><span data-stu-id="09ad0-243">Definition</span></span>

<span data-ttu-id="09ad0-244">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-245">函數`Func_denmark_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09ad0-246">找到來自`Keywords_denmark_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="09ad0-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="09ad0-247">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-248">函數`Func_denmark_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="09ad0-249">關鍵字</span><span class="sxs-lookup"><span data-stu-id="09ad0-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="09ad0-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="09ad0-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="09ad0-251">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-251">personal identification number</span></span>
  
<span data-ttu-id="09ad0-252">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-252">national identification number</span></span>
  
<span data-ttu-id="09ad0-253">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-253">social security number</span></span>
  
<span data-ttu-id="09ad0-254">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="09ad0-254">nationalnumber#</span></span>
  
<span data-ttu-id="09ad0-255">Ssn#</span><span class="sxs-lookup"><span data-stu-id="09ad0-255">ssn#</span></span>
  
<span data-ttu-id="09ad0-256">Ssn</span><span class="sxs-lookup"><span data-stu-id="09ad0-256">ssn</span></span>
  
<span data-ttu-id="09ad0-257">國家/地區號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-257">national number</span></span>
  
<span data-ttu-id="09ad0-258">個人號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-258">personal id number</span></span>
  
<span data-ttu-id="09ad0-259">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="09ad0-259">personalidnumber#</span></span>
  
<span data-ttu-id="09ad0-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="09ad0-260">cpr-nummer</span></span>
  
<span data-ttu-id="09ad0-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="09ad0-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="09ad0-262">芬蘭</span><span class="sxs-lookup"><span data-stu-id="09ad0-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="09ad0-263">格式</span><span class="sxs-lookup"><span data-stu-id="09ad0-263">Format</span></span>

<span data-ttu-id="09ad0-264">以指定格式為11個字元的組合</span><span class="sxs-lookup"><span data-stu-id="09ad0-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09ad0-265">模式</span><span class="sxs-lookup"><span data-stu-id="09ad0-265">Pattern</span></span>

<span data-ttu-id="09ad0-266">以指定格式為11個字元的組合：</span><span class="sxs-lookup"><span data-stu-id="09ad0-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="09ad0-267">六位數</span><span class="sxs-lookup"><span data-stu-id="09ad0-267">Six digits</span></span> 
    
- <span data-ttu-id="09ad0-268">下列其中一個範例：</span><span class="sxs-lookup"><span data-stu-id="09ad0-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="09ad0-269">加號</span><span class="sxs-lookup"><span data-stu-id="09ad0-269">Plus symbol</span></span>
    
  - <span data-ttu-id="09ad0-270">負號</span><span class="sxs-lookup"><span data-stu-id="09ad0-270">Minus symbol</span></span>
    
  - <span data-ttu-id="09ad0-271">字母 "A" （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="09ad0-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="09ad0-272">三位數</span><span class="sxs-lookup"><span data-stu-id="09ad0-272">Three digits</span></span>
    
- <span data-ttu-id="09ad0-273">一個字母或一個數位</span><span class="sxs-lookup"><span data-stu-id="09ad0-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09ad0-274">校驗</span><span class="sxs-lookup"><span data-stu-id="09ad0-274">Checksum</span></span>

<span data-ttu-id="09ad0-275">是</span><span class="sxs-lookup"><span data-stu-id="09ad0-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="09ad0-276">定義</span><span class="sxs-lookup"><span data-stu-id="09ad0-276">Definition</span></span>

<span data-ttu-id="09ad0-277">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-278">函數`Func_finland_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09ad0-279">找到來自`Keywords_finland_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="09ad0-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="09ad0-280">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-281">函數`Func_finland_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="09ad0-282">關鍵字</span><span class="sxs-lookup"><span data-stu-id="09ad0-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="09ad0-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="09ad0-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="09ad0-284">識別號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-284">identification number</span></span>
  
<span data-ttu-id="09ad0-285">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-285">personal id</span></span>
  
<span data-ttu-id="09ad0-286">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-286">identity number</span></span>
  
<span data-ttu-id="09ad0-287">芬蘭文身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-287">finnish national id number</span></span>
  
<span data-ttu-id="09ad0-288">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="09ad0-288">personalidnumber#</span></span>
  
<span data-ttu-id="09ad0-289">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-289">national identification number</span></span>
  
<span data-ttu-id="09ad0-290">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-290">id number</span></span>
  
<span data-ttu-id="09ad0-291">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-291">national id no.</span></span>
  
<span data-ttu-id="09ad0-292">本國識別碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-292">national id number</span></span>
  
<span data-ttu-id="09ad0-293">識別碼 no</span><span class="sxs-lookup"><span data-stu-id="09ad0-293">id no</span></span>
  
<span data-ttu-id="09ad0-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="09ad0-294">tunnistenumero</span></span>
  
<span data-ttu-id="09ad0-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="09ad0-295">henkilötunnus</span></span>
  
<span data-ttu-id="09ad0-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="09ad0-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="09ad0-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="09ad0-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="09ad0-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="09ad0-298">identiteetti numero</span></span>
  
<span data-ttu-id="09ad0-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="09ad0-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="09ad0-300">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="09ad0-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="09ad0-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="09ad0-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="09ad0-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="09ad0-302">tunnusnumero</span></span>
  
<span data-ttu-id="09ad0-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="09ad0-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="09ad0-304">hetu</span><span class="sxs-lookup"><span data-stu-id="09ad0-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="09ad0-305">法國</span><span class="sxs-lookup"><span data-stu-id="09ad0-305">France</span></span>

<span data-ttu-id="09ad0-306">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「法國社會安全性號碼（INSEE）」一節。</span><span class="sxs-lookup"><span data-stu-id="09ad0-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="09ad0-307">德國</span><span class="sxs-lookup"><span data-stu-id="09ad0-307">Germany</span></span>

<span data-ttu-id="09ad0-308">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「德國身分識別卡片編號」一節。</span><span class="sxs-lookup"><span data-stu-id="09ad0-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="09ad0-309">希臘</span><span class="sxs-lookup"><span data-stu-id="09ad0-309">Greece</span></span>

<span data-ttu-id="09ad0-310">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「希臘國 ID 卡」一節。</span><span class="sxs-lookup"><span data-stu-id="09ad0-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="09ad0-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="09ad0-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="09ad0-312">格式</span><span class="sxs-lookup"><span data-stu-id="09ad0-312">Format</span></span>

<span data-ttu-id="09ad0-313">九位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="09ad0-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09ad0-314">模式</span><span class="sxs-lookup"><span data-stu-id="09ad0-314">Pattern</span></span>

<span data-ttu-id="09ad0-315">九位數</span><span class="sxs-lookup"><span data-stu-id="09ad0-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09ad0-316">校驗</span><span class="sxs-lookup"><span data-stu-id="09ad0-316">Checksum</span></span>

<span data-ttu-id="09ad0-317">是</span><span class="sxs-lookup"><span data-stu-id="09ad0-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="09ad0-318">定義</span><span class="sxs-lookup"><span data-stu-id="09ad0-318">Definition</span></span>

<span data-ttu-id="09ad0-319">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-320">函數`Func_hungary_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09ad0-321">找到來自`Keywords_hungary_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="09ad0-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="09ad0-322">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-323">函數`Func_hungary_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="09ad0-324">關鍵字</span><span class="sxs-lookup"><span data-stu-id="09ad0-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="09ad0-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="09ad0-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="09ad0-326">匈牙利文社交安全性號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-326">hungarian social security number</span></span>
  
<span data-ttu-id="09ad0-327">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-327">social security number</span></span>
  
<span data-ttu-id="09ad0-328">socialsecuritynumber#</span><span class="sxs-lookup"><span data-stu-id="09ad0-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="09ad0-329">hssn#</span><span class="sxs-lookup"><span data-stu-id="09ad0-329">hssn#</span></span>
  
<span data-ttu-id="09ad0-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="09ad0-330">socialsecuritynno</span></span>
  
<span data-ttu-id="09ad0-331">hssn</span><span class="sxs-lookup"><span data-stu-id="09ad0-331">hssn</span></span>
  
<span data-ttu-id="09ad0-332">泰姬陵</span><span class="sxs-lookup"><span data-stu-id="09ad0-332">taj</span></span>
  
<span data-ttu-id="09ad0-333">泰姬陵#</span><span class="sxs-lookup"><span data-stu-id="09ad0-333">taj#</span></span>
  
<span data-ttu-id="09ad0-334">Ssn</span><span class="sxs-lookup"><span data-stu-id="09ad0-334">ssn</span></span>
  
<span data-ttu-id="09ad0-335">Ssn#</span><span class="sxs-lookup"><span data-stu-id="09ad0-335">ssn#</span></span>
  
<span data-ttu-id="09ad0-336">社會安全性否</span><span class="sxs-lookup"><span data-stu-id="09ad0-336">social security no</span></span>
  
<span data-ttu-id="09ad0-337">áfa</span><span class="sxs-lookup"><span data-stu-id="09ad0-337">áfa</span></span>
  
<span data-ttu-id="09ad0-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="09ad0-338">közösségi adószám</span></span>
  
<span data-ttu-id="09ad0-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="09ad0-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="09ad0-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="09ad0-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="09ad0-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="09ad0-341">áfa szám</span></span>
  
<span data-ttu-id="09ad0-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="09ad0-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="09ad0-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="09ad0-343">Portugal</span></span>

<span data-ttu-id="09ad0-344">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「葡萄牙公民卡片編號」一節。</span><span class="sxs-lookup"><span data-stu-id="09ad0-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="09ad0-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="09ad0-345">Spain</span></span>

<span data-ttu-id="09ad0-346">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「西班牙社會安全性號碼（SSN）」一節。</span><span class="sxs-lookup"><span data-stu-id="09ad0-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="09ad0-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="09ad0-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="09ad0-348">格式</span><span class="sxs-lookup"><span data-stu-id="09ad0-348">Format</span></span>

<span data-ttu-id="09ad0-349">12位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="09ad0-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09ad0-350">模式</span><span class="sxs-lookup"><span data-stu-id="09ad0-350">Pattern</span></span>

<span data-ttu-id="09ad0-351">12位數：</span><span class="sxs-lookup"><span data-stu-id="09ad0-351">12 digits:</span></span>
  
-  <span data-ttu-id="09ad0-352">對應至出生日期的八位數（YYYYMMDD）</span><span class="sxs-lookup"><span data-stu-id="09ad0-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="09ad0-353">對應至序數的三位數，其中：</span><span class="sxs-lookup"><span data-stu-id="09ad0-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="09ad0-354">序數中的最後一個數位是由為男指派的奇數和偶數的女數位來表示性別</span><span class="sxs-lookup"><span data-stu-id="09ad0-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="09ad0-355">最多1990，corresponded 序數的指派給在該縣內，號碼的持有者是出生的，或（如果是在1947之前出生），在該縣中，根據稅收記錄，在年1月 1 1947 日，使用特殊的程式碼（通常是9，7位數）進行 immigrants</span><span class="sxs-lookup"><span data-stu-id="09ad0-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="09ad0-356">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09ad0-357">校驗</span><span class="sxs-lookup"><span data-stu-id="09ad0-357">Checksum</span></span>

<span data-ttu-id="09ad0-358">是</span><span class="sxs-lookup"><span data-stu-id="09ad0-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="09ad0-359">定義</span><span class="sxs-lookup"><span data-stu-id="09ad0-359">Definition</span></span>

<span data-ttu-id="09ad0-360">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-361">函數`Func_sweden_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09ad0-362">找到來自`Keywords_sweden_eu_ssn_or_equivalent`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="09ad0-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="09ad0-363">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="09ad0-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09ad0-364">函數`Func_sweden_eu_ssn_or_equivalent`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="09ad0-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="09ad0-365">關鍵字</span><span class="sxs-lookup"><span data-stu-id="09ad0-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="09ad0-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="09ad0-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="09ad0-367">個人號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-367">personal id number</span></span>
  
<span data-ttu-id="09ad0-368">識別號碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-368">identification number</span></span>
  
<span data-ttu-id="09ad0-369">個人識別碼否</span><span class="sxs-lookup"><span data-stu-id="09ad0-369">personal id no</span></span>
  
<span data-ttu-id="09ad0-370">identity no</span><span class="sxs-lookup"><span data-stu-id="09ad0-370">identity no</span></span>
  
<span data-ttu-id="09ad0-371">識別碼否</span><span class="sxs-lookup"><span data-stu-id="09ad0-371">identification no</span></span>
  
<span data-ttu-id="09ad0-372">個人身分識別否</span><span class="sxs-lookup"><span data-stu-id="09ad0-372">personal identification no</span></span>
  
<span data-ttu-id="09ad0-373">personnummer 識別碼</span><span class="sxs-lookup"><span data-stu-id="09ad0-373">personnummer id</span></span>
  
<span data-ttu-id="09ad0-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="09ad0-374">personligt id-nummer</span></span>
  
<span data-ttu-id="09ad0-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="09ad0-375">unikt id-nummer</span></span>
  
<span data-ttu-id="09ad0-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="09ad0-376">personnummer</span></span>
  
<span data-ttu-id="09ad0-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="09ad0-377">identifikationsnumret</span></span>
  
<span data-ttu-id="09ad0-378">personnummer#</span><span class="sxs-lookup"><span data-stu-id="09ad0-378">personnummer#</span></span>
  
<span data-ttu-id="09ad0-379">identifikationsnumret#</span><span class="sxs-lookup"><span data-stu-id="09ad0-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="09ad0-380">請參閱</span><span class="sxs-lookup"><span data-stu-id="09ad0-380">See also</span></span>

[<span data-ttu-id="09ad0-381">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="09ad0-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

