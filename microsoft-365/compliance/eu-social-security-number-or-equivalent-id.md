---
title: 歐盟社會安全號碼或對等項目識別碼
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟社會安全號碼或對等識別碼敏感資訊類型。 此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。
ms.openlocfilehash: b42a8d927e18f813eb6ef6d1d55b2de15ea9dcd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077066"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="1ebad-104">歐盟社會安全號碼或對等項目識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="1ebad-105">本主題顯示什麼資料外洩防護 (DLP) 原則會尋找當它偵測到歐盟社會安全號碼 (SSN) 或對等識別碼敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="1ebad-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="1ebad-106">此敏感資訊類型定義不同模式、 關鍵字、 和其他辨識項的每個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="1ebad-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="1ebad-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="1ebad-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="1ebad-108">格式</span><span class="sxs-lookup"><span data-stu-id="1ebad-108">Format</span></span>

<span data-ttu-id="1ebad-109">10 位數，代表指定之格式</span><span class="sxs-lookup"><span data-stu-id="1ebad-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1ebad-110">模式</span><span class="sxs-lookup"><span data-stu-id="1ebad-110">Pattern</span></span>

<span data-ttu-id="1ebad-111">10 位數：</span><span class="sxs-lookup"><span data-stu-id="1ebad-111">10 digits:</span></span>
  
-  <span data-ttu-id="1ebad-112">會對應至序號的三位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="1ebad-113">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-113">One check digit</span></span>
    
- <span data-ttu-id="1ebad-114">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1ebad-115">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-115">Checksum</span></span>

<span data-ttu-id="1ebad-116">是</span><span class="sxs-lookup"><span data-stu-id="1ebad-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1ebad-117">定義</span><span class="sxs-lookup"><span data-stu-id="1ebad-117">Definition</span></span>

<span data-ttu-id="1ebad-118">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-119">函式`Func_austria_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1ebad-120">從關鍵字`Keywords_austria_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="1ebad-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1ebad-121">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-122">函式`Func_austria_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1ebad-123">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1ebad-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="1ebad-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1ebad-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1ebad-125">社會安全沒有</span><span class="sxs-lookup"><span data-stu-id="1ebad-125">social security no</span></span>
  
<span data-ttu-id="1ebad-126">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-126">social security number</span></span>
  
<span data-ttu-id="1ebad-127">社會安全的程式碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-127">social security code</span></span>
  
<span data-ttu-id="1ebad-128">保險號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-128">insurance number</span></span>
  
<span data-ttu-id="1ebad-129">奧地利 ssn</span><span class="sxs-lookup"><span data-stu-id="1ebad-129">austrian ssn</span></span>
  
<span data-ttu-id="1ebad-130">ssn#</span><span class="sxs-lookup"><span data-stu-id="1ebad-130">ssn#</span></span>
  
<span data-ttu-id="1ebad-131">ssn</span><span class="sxs-lookup"><span data-stu-id="1ebad-131">ssn</span></span>
  
<span data-ttu-id="1ebad-132">保險程式碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-132">insurance code</span></span>
  
<span data-ttu-id="1ebad-133">保險程式碼#</span><span class="sxs-lookup"><span data-stu-id="1ebad-133">insurance code#</span></span>
  
<span data-ttu-id="1ebad-134">socialsecurityno#</span><span class="sxs-lookup"><span data-stu-id="1ebad-134">socialsecurityno#</span></span>
  
<span data-ttu-id="1ebad-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="1ebad-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="1ebad-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="1ebad-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="1ebad-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="1ebad-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="1ebad-138">比利時</span><span class="sxs-lookup"><span data-stu-id="1ebad-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="1ebad-139">格式</span><span class="sxs-lookup"><span data-stu-id="1ebad-139">Format</span></span>

<span data-ttu-id="1ebad-140">11 位數不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="1ebad-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1ebad-141">模式</span><span class="sxs-lookup"><span data-stu-id="1ebad-141">Pattern</span></span>

<span data-ttu-id="1ebad-142">11 位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1ebad-143">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-143">Checksum</span></span>

<span data-ttu-id="1ebad-144">是</span><span class="sxs-lookup"><span data-stu-id="1ebad-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1ebad-145">定義</span><span class="sxs-lookup"><span data-stu-id="1ebad-145">Definition</span></span>

<span data-ttu-id="1ebad-146">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-147">函式`Func_belgium_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1ebad-148">從關鍵字`Keywords_belgium_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="1ebad-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1ebad-149">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-150">函式`Func_belgium_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1ebad-151">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1ebad-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="1ebad-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1ebad-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1ebad-153">比利時國民身分的數字</span><span class="sxs-lookup"><span data-stu-id="1ebad-153">belgian national number</span></span>
  
<span data-ttu-id="1ebad-154">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-154">national number</span></span>
  
<span data-ttu-id="1ebad-155">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-155">social security number</span></span>
  
<span data-ttu-id="1ebad-156">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="1ebad-156">nationalnumber#</span></span>
  
<span data-ttu-id="1ebad-157">ssn#</span><span class="sxs-lookup"><span data-stu-id="1ebad-157">ssn#</span></span>
  
<span data-ttu-id="1ebad-158">ssn</span><span class="sxs-lookup"><span data-stu-id="1ebad-158">ssn</span></span>
  
<span data-ttu-id="1ebad-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="1ebad-159">nationalnumber</span></span>
  
<span data-ttu-id="1ebad-160">bnn#</span><span class="sxs-lookup"><span data-stu-id="1ebad-160">bnn#</span></span>
  
<span data-ttu-id="1ebad-161">bnn</span><span class="sxs-lookup"><span data-stu-id="1ebad-161">bnn</span></span>
  
<span data-ttu-id="1ebad-162">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-162">personal id number</span></span>
  
<span data-ttu-id="1ebad-163">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="1ebad-163">personalidnumber#</span></span>
  
<span data-ttu-id="1ebad-164">numéro 國際電話</span><span class="sxs-lookup"><span data-stu-id="1ebad-164">numéro national</span></span>
  
<span data-ttu-id="1ebad-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="1ebad-165">numéro de sécurité</span></span>
  
<span data-ttu-id="1ebad-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="1ebad-166">numéro d'assuré</span></span>
  
<span data-ttu-id="1ebad-167">identifiant 國際電話</span><span class="sxs-lookup"><span data-stu-id="1ebad-167">identifiant national</span></span>
  
<span data-ttu-id="1ebad-168">identifiantnational#</span><span class="sxs-lookup"><span data-stu-id="1ebad-168">identifiantnational#</span></span>
  
<span data-ttu-id="1ebad-169">numéronational#</span><span class="sxs-lookup"><span data-stu-id="1ebad-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="1ebad-170">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="1ebad-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="1ebad-171">格式</span><span class="sxs-lookup"><span data-stu-id="1ebad-171">Format</span></span>

<span data-ttu-id="1ebad-172">11 位數不含空格和分隔符號</span><span class="sxs-lookup"><span data-stu-id="1ebad-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1ebad-173">模式</span><span class="sxs-lookup"><span data-stu-id="1ebad-173">Pattern</span></span>

 <span data-ttu-id="1ebad-174">11 位數：</span><span class="sxs-lookup"><span data-stu-id="1ebad-174">11 digits:</span></span> 
  
-  <span data-ttu-id="1ebad-175">十位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-175">Ten digits</span></span> 
    
- <span data-ttu-id="1ebad-176">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1ebad-177">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-177">Checksum</span></span>

<span data-ttu-id="1ebad-178">是</span><span class="sxs-lookup"><span data-stu-id="1ebad-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1ebad-179">定義</span><span class="sxs-lookup"><span data-stu-id="1ebad-179">Definition</span></span>

<span data-ttu-id="1ebad-180">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-181">函式`Func_croatia_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1ebad-182">從關鍵字`Keywords_croatia_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="1ebad-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1ebad-183">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-184">函式`Func_croatia_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1ebad-185">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1ebad-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="1ebad-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1ebad-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1ebad-187">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-187">personal identification number</span></span>
  
<span data-ttu-id="1ebad-188">主版公民數目</span><span class="sxs-lookup"><span data-stu-id="1ebad-188">master citizen number</span></span>
  
<span data-ttu-id="1ebad-189">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-189">national identification number</span></span>
  
<span data-ttu-id="1ebad-190">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-190">social security number</span></span>
  
<span data-ttu-id="1ebad-191">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="1ebad-191">nationalnumber#</span></span>
  
<span data-ttu-id="1ebad-192">ssn#</span><span class="sxs-lookup"><span data-stu-id="1ebad-192">ssn#</span></span>
  
<span data-ttu-id="1ebad-193">ssn</span><span class="sxs-lookup"><span data-stu-id="1ebad-193">ssn</span></span>
  
<span data-ttu-id="1ebad-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="1ebad-194">nationalnumber</span></span>
  
<span data-ttu-id="1ebad-195">bnn#</span><span class="sxs-lookup"><span data-stu-id="1ebad-195">bnn#</span></span>
  
<span data-ttu-id="1ebad-196">bnn</span><span class="sxs-lookup"><span data-stu-id="1ebad-196">bnn</span></span>
  
<span data-ttu-id="1ebad-197">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-197">personal id number</span></span>
  
<span data-ttu-id="1ebad-198">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="1ebad-198">personalidnumber#</span></span>
  
<span data-ttu-id="1ebad-199">oib 碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-199">oib</span></span>
  
<span data-ttu-id="1ebad-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="1ebad-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="1ebad-201">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="1ebad-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="1ebad-202">格式</span><span class="sxs-lookup"><span data-stu-id="1ebad-202">Format</span></span>

<span data-ttu-id="1ebad-203">十個數字和中指定的型態的反斜線</span><span class="sxs-lookup"><span data-stu-id="1ebad-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1ebad-204">模式</span><span class="sxs-lookup"><span data-stu-id="1ebad-204">Pattern</span></span>

<span data-ttu-id="1ebad-205">十位數和一個反斜線：</span><span class="sxs-lookup"><span data-stu-id="1ebad-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="1ebad-206">會對應至 (YYMMDD) 的出生日期的六位數：</span><span class="sxs-lookup"><span data-stu-id="1ebad-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="1ebad-207">反斜線</span><span class="sxs-lookup"><span data-stu-id="1ebad-207">A backslash</span></span>
    
- <span data-ttu-id="1ebad-208">會對應至分隔出生日期相同的人員序號的三位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="1ebad-209">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1ebad-210">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-210">Checksum</span></span>

<span data-ttu-id="1ebad-211">是</span><span class="sxs-lookup"><span data-stu-id="1ebad-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1ebad-212">定義</span><span class="sxs-lookup"><span data-stu-id="1ebad-212">Definition</span></span>

<span data-ttu-id="1ebad-213">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-214">函式`Func_czech_republic_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1ebad-215">從關鍵字`Keywords_czech_republic_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="1ebad-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1ebad-216">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-217">函式`Func_czech_republic_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1ebad-218">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1ebad-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="1ebad-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1ebad-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1ebad-220">出生數目</span><span class="sxs-lookup"><span data-stu-id="1ebad-220">birth number</span></span>
  
<span data-ttu-id="1ebad-221">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-221">national identification number</span></span>
  
<span data-ttu-id="1ebad-222">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-222">personal identification number</span></span>
  
<span data-ttu-id="1ebad-223">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-223">social security number</span></span>
  
<span data-ttu-id="1ebad-224">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="1ebad-224">nationalnumber#</span></span>
  
<span data-ttu-id="1ebad-225">ssn#</span><span class="sxs-lookup"><span data-stu-id="1ebad-225">ssn#</span></span>
  
<span data-ttu-id="1ebad-226">ssn</span><span class="sxs-lookup"><span data-stu-id="1ebad-226">ssn</span></span>
  
<span data-ttu-id="1ebad-227">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-227">national number</span></span>
  
<span data-ttu-id="1ebad-228">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-228">personal id number</span></span>
  
<span data-ttu-id="1ebad-229">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="1ebad-229">personalidnumber#</span></span>
  
<span data-ttu-id="1ebad-230">rč</span><span class="sxs-lookup"><span data-stu-id="1ebad-230">rč</span></span>
  
<span data-ttu-id="1ebad-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="1ebad-231">rodné číslo</span></span>
  
<span data-ttu-id="1ebad-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="1ebad-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="1ebad-233">丹麥</span><span class="sxs-lookup"><span data-stu-id="1ebad-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="1ebad-234">格式</span><span class="sxs-lookup"><span data-stu-id="1ebad-234">Format</span></span>

<span data-ttu-id="1ebad-235">十個數字和中指定的型態連字號</span><span class="sxs-lookup"><span data-stu-id="1ebad-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1ebad-236">模式</span><span class="sxs-lookup"><span data-stu-id="1ebad-236">Pattern</span></span>

<span data-ttu-id="1ebad-237">十位數，並連字號：</span><span class="sxs-lookup"><span data-stu-id="1ebad-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="1ebad-238">會對應至 (DDMMYY) 的出生日期的六位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="1ebad-239">連字號</span><span class="sxs-lookup"><span data-stu-id="1ebad-239">A hyphen</span></span>
    
- <span data-ttu-id="1ebad-240">會對應至序號的四位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1ebad-241">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-241">Checksum</span></span>

<span data-ttu-id="1ebad-242">是</span><span class="sxs-lookup"><span data-stu-id="1ebad-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1ebad-243">定義</span><span class="sxs-lookup"><span data-stu-id="1ebad-243">Definition</span></span>

<span data-ttu-id="1ebad-244">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-245">函式`Func_denmark_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1ebad-246">從關鍵字`Keywords_denmark_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="1ebad-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1ebad-247">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-248">函式`Func_denmark_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1ebad-249">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1ebad-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="1ebad-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1ebad-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1ebad-251">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-251">personal identification number</span></span>
  
<span data-ttu-id="1ebad-252">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-252">national identification number</span></span>
  
<span data-ttu-id="1ebad-253">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-253">social security number</span></span>
  
<span data-ttu-id="1ebad-254">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="1ebad-254">nationalnumber#</span></span>
  
<span data-ttu-id="1ebad-255">ssn#</span><span class="sxs-lookup"><span data-stu-id="1ebad-255">ssn#</span></span>
  
<span data-ttu-id="1ebad-256">ssn</span><span class="sxs-lookup"><span data-stu-id="1ebad-256">ssn</span></span>
  
<span data-ttu-id="1ebad-257">國際電話號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-257">national number</span></span>
  
<span data-ttu-id="1ebad-258">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-258">personal id number</span></span>
  
<span data-ttu-id="1ebad-259">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="1ebad-259">personalidnumber#</span></span>
  
<span data-ttu-id="1ebad-260">cpr nummer</span><span class="sxs-lookup"><span data-stu-id="1ebad-260">cpr-nummer</span></span>
  
<span data-ttu-id="1ebad-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="1ebad-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="1ebad-262">芬蘭</span><span class="sxs-lookup"><span data-stu-id="1ebad-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="1ebad-263">格式</span><span class="sxs-lookup"><span data-stu-id="1ebad-263">Format</span></span>

<span data-ttu-id="1ebad-264">11 個字元組合，以指定的格式</span><span class="sxs-lookup"><span data-stu-id="1ebad-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1ebad-265">模式</span><span class="sxs-lookup"><span data-stu-id="1ebad-265">Pattern</span></span>

<span data-ttu-id="1ebad-266">以指定的格式 11 個字元組合：</span><span class="sxs-lookup"><span data-stu-id="1ebad-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="1ebad-267">六位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-267">Six digits</span></span> 
    
- <span data-ttu-id="1ebad-268">實例的其中一項：</span><span class="sxs-lookup"><span data-stu-id="1ebad-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="1ebad-269">加上符號</span><span class="sxs-lookup"><span data-stu-id="1ebad-269">Plus symbol</span></span>
    
  - <span data-ttu-id="1ebad-270">減號</span><span class="sxs-lookup"><span data-stu-id="1ebad-270">Minus symbol</span></span>
    
  - <span data-ttu-id="1ebad-271">字母"A"（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="1ebad-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="1ebad-272">三位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-272">Three digits</span></span>
    
- <span data-ttu-id="1ebad-273">一個字母或一個數字</span><span class="sxs-lookup"><span data-stu-id="1ebad-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1ebad-274">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-274">Checksum</span></span>

<span data-ttu-id="1ebad-275">是</span><span class="sxs-lookup"><span data-stu-id="1ebad-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1ebad-276">定義</span><span class="sxs-lookup"><span data-stu-id="1ebad-276">Definition</span></span>

<span data-ttu-id="1ebad-277">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-278">函式`Func_finland_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1ebad-279">從關鍵字`Keywords_finland_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="1ebad-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1ebad-280">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-281">函式`Func_finland_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1ebad-282">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1ebad-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="1ebad-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1ebad-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1ebad-284">識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-284">identification number</span></span>
  
<span data-ttu-id="1ebad-285">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-285">personal id</span></span>
  
<span data-ttu-id="1ebad-286">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-286">identity number</span></span>
  
<span data-ttu-id="1ebad-287">芬蘭國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-287">finnish national id number</span></span>
  
<span data-ttu-id="1ebad-288">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="1ebad-288">personalidnumber#</span></span>
  
<span data-ttu-id="1ebad-289">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-289">national identification number</span></span>
  
<span data-ttu-id="1ebad-290">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-290">id number</span></span>
  
<span data-ttu-id="1ebad-291">國民身分證沒有。</span><span class="sxs-lookup"><span data-stu-id="1ebad-291">national id no.</span></span>
  
<span data-ttu-id="1ebad-292">國民身分證號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-292">national id number</span></span>
  
<span data-ttu-id="1ebad-293">識別碼不</span><span class="sxs-lookup"><span data-stu-id="1ebad-293">id no</span></span>
  
<span data-ttu-id="1ebad-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="1ebad-294">tunnistenumero</span></span>
  
<span data-ttu-id="1ebad-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="1ebad-295">henkilötunnus</span></span>
  
<span data-ttu-id="1ebad-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="1ebad-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="1ebad-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="1ebad-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="1ebad-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="1ebad-298">identiteetti numero</span></span>
  
<span data-ttu-id="1ebad-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="1ebad-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="1ebad-300">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="1ebad-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="1ebad-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="1ebad-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="1ebad-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="1ebad-302">tunnusnumero</span></span>
  
<span data-ttu-id="1ebad-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="1ebad-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="1ebad-304">hetu</span><span class="sxs-lookup"><span data-stu-id="1ebad-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="1ebad-305">法國</span><span class="sxs-lookup"><span data-stu-id="1ebad-305">France</span></span>

<span data-ttu-id="1ebad-306">如需詳細資訊，請參閱 「 法國社會安全號碼 (INSEE) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1ebad-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="1ebad-307">德國</span><span class="sxs-lookup"><span data-stu-id="1ebad-307">Germany</span></span>

<span data-ttu-id="1ebad-308">如需詳細資訊，請參閱 「 德國身分證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1ebad-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="1ebad-309">希臘</span><span class="sxs-lookup"><span data-stu-id="1ebad-309">Greece</span></span>

<span data-ttu-id="1ebad-310">如需詳細資訊，請參閱 「 希臘國民身分證 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1ebad-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="1ebad-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="1ebad-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="1ebad-312">格式</span><span class="sxs-lookup"><span data-stu-id="1ebad-312">Format</span></span>

<span data-ttu-id="1ebad-313">如果沒有空格和分隔符號的九位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1ebad-314">模式</span><span class="sxs-lookup"><span data-stu-id="1ebad-314">Pattern</span></span>

<span data-ttu-id="1ebad-315">九位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1ebad-316">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-316">Checksum</span></span>

<span data-ttu-id="1ebad-317">是</span><span class="sxs-lookup"><span data-stu-id="1ebad-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1ebad-318">定義</span><span class="sxs-lookup"><span data-stu-id="1ebad-318">Definition</span></span>

<span data-ttu-id="1ebad-319">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-320">函式`Func_hungary_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1ebad-321">從關鍵字`Keywords_hungary_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="1ebad-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1ebad-322">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-323">函式`Func_hungary_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1ebad-324">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1ebad-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="1ebad-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1ebad-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1ebad-326">匈牙利文社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-326">hungarian social security number</span></span>
  
<span data-ttu-id="1ebad-327">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-327">social security number</span></span>
  
<span data-ttu-id="1ebad-328">socialsecuritynumber#</span><span class="sxs-lookup"><span data-stu-id="1ebad-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="1ebad-329">hssn#</span><span class="sxs-lookup"><span data-stu-id="1ebad-329">hssn#</span></span>
  
<span data-ttu-id="1ebad-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="1ebad-330">socialsecuritynno</span></span>
  
<span data-ttu-id="1ebad-331">hssn</span><span class="sxs-lookup"><span data-stu-id="1ebad-331">hssn</span></span>
  
<span data-ttu-id="1ebad-332">泰</span><span class="sxs-lookup"><span data-stu-id="1ebad-332">taj</span></span>
  
<span data-ttu-id="1ebad-333">泰#</span><span class="sxs-lookup"><span data-stu-id="1ebad-333">taj#</span></span>
  
<span data-ttu-id="1ebad-334">ssn</span><span class="sxs-lookup"><span data-stu-id="1ebad-334">ssn</span></span>
  
<span data-ttu-id="1ebad-335">ssn#</span><span class="sxs-lookup"><span data-stu-id="1ebad-335">ssn#</span></span>
  
<span data-ttu-id="1ebad-336">社會安全沒有</span><span class="sxs-lookup"><span data-stu-id="1ebad-336">social security no</span></span>
  
<span data-ttu-id="1ebad-337">áfa</span><span class="sxs-lookup"><span data-stu-id="1ebad-337">áfa</span></span>
  
<span data-ttu-id="1ebad-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="1ebad-338">közösségi adószám</span></span>
  
<span data-ttu-id="1ebad-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="1ebad-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="1ebad-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="1ebad-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="1ebad-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="1ebad-341">áfa szám</span></span>
  
<span data-ttu-id="1ebad-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="1ebad-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="1ebad-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="1ebad-343">Portugal</span></span>

<span data-ttu-id="1ebad-344">如需詳細資訊，請參閱 「 葡萄牙公民證號碼 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1ebad-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="1ebad-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="1ebad-345">Spain</span></span>

<span data-ttu-id="1ebad-346">如需詳細資訊，請參閱 「 西班牙社會安全號碼 (SSN) 」 中[的敏感資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="1ebad-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="1ebad-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="1ebad-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="1ebad-348">格式</span><span class="sxs-lookup"><span data-stu-id="1ebad-348">Format</span></span>

<span data-ttu-id="1ebad-349">如果沒有空格和分隔符號的 12 位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1ebad-350">模式</span><span class="sxs-lookup"><span data-stu-id="1ebad-350">Pattern</span></span>

<span data-ttu-id="1ebad-351">12 位數：</span><span class="sxs-lookup"><span data-stu-id="1ebad-351">12 digits:</span></span>
  
-  <span data-ttu-id="1ebad-352">會對應至出生日期 (YYYYMMDD) 的八位數</span><span class="sxs-lookup"><span data-stu-id="1ebad-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="1ebad-353">會對應至序號的三位數其中：</span><span class="sxs-lookup"><span data-stu-id="1ebad-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="1ebad-354">序號中的最後一個數字表示性別因 1 女 2 男奇數和偶數女性的工作分派</span><span class="sxs-lookup"><span data-stu-id="1ebad-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="1ebad-355">最多 1990，工作分派的序號採納郡出生數字的承載或 （如果出生之前 1947年） 其中他有已住，根據稅務記錄上 1947 年 1 月 1，具有特殊的程式碼 (通常為 7th 的數字 9) 的immigrants</span><span class="sxs-lookup"><span data-stu-id="1ebad-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="1ebad-356">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1ebad-357">總和檢查碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-357">Checksum</span></span>

<span data-ttu-id="1ebad-358">是</span><span class="sxs-lookup"><span data-stu-id="1ebad-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1ebad-359">定義</span><span class="sxs-lookup"><span data-stu-id="1ebad-359">Definition</span></span>

<span data-ttu-id="1ebad-360">DLP 原則是 85%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-361">函式`Func_sweden_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1ebad-362">從關鍵字`Keywords_sweden_eu_ssn_or_equivalent`找到。</span><span class="sxs-lookup"><span data-stu-id="1ebad-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="1ebad-363">DLP 原則是 75%以內，已偵測到此敏感資訊類型的如果鄰近性是 300 個字元：</span><span class="sxs-lookup"><span data-stu-id="1ebad-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1ebad-364">函式`Func_sweden_eu_ssn_or_equivalent`找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="1ebad-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="1ebad-365">關鍵字</span><span class="sxs-lookup"><span data-stu-id="1ebad-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="1ebad-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="1ebad-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="1ebad-367">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-367">personal id number</span></span>
  
<span data-ttu-id="1ebad-368">識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-368">identification number</span></span>
  
<span data-ttu-id="1ebad-369">個人識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="1ebad-369">personal id no</span></span>
  
<span data-ttu-id="1ebad-370">身分識別沒有</span><span class="sxs-lookup"><span data-stu-id="1ebad-370">identity no</span></span>
  
<span data-ttu-id="1ebad-371">識別任何</span><span class="sxs-lookup"><span data-stu-id="1ebad-371">identification no</span></span>
  
<span data-ttu-id="1ebad-372">個人識別碼沒有</span><span class="sxs-lookup"><span data-stu-id="1ebad-372">personal identification no</span></span>
  
<span data-ttu-id="1ebad-373">personnummer 識別碼</span><span class="sxs-lookup"><span data-stu-id="1ebad-373">personnummer id</span></span>
  
<span data-ttu-id="1ebad-374">personligt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="1ebad-374">personligt id-nummer</span></span>
  
<span data-ttu-id="1ebad-375">unikt 識別碼 nummer</span><span class="sxs-lookup"><span data-stu-id="1ebad-375">unikt id-nummer</span></span>
  
<span data-ttu-id="1ebad-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="1ebad-376">personnummer</span></span>
  
<span data-ttu-id="1ebad-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="1ebad-377">identifikationsnumret</span></span>
  
<span data-ttu-id="1ebad-378">personnummer#</span><span class="sxs-lookup"><span data-stu-id="1ebad-378">personnummer#</span></span>
  
<span data-ttu-id="1ebad-379">identifikationsnumret#</span><span class="sxs-lookup"><span data-stu-id="1ebad-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1ebad-380">請參閱</span><span class="sxs-lookup"><span data-stu-id="1ebad-380">See also</span></span>

[<span data-ttu-id="1ebad-381">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="1ebad-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

