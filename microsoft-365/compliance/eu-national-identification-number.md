---
title: 歐盟國身分識別號碼
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
description: 本主題說明資料遺失防護（DLP）原則在偵測到歐盟國身分識別號碼的敏感資訊類型時，會尋找哪些專案。 這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。
ms.openlocfilehash: 4dac77f129b45f457a82e709cb5a3b846a95cdf4
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938759"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="9c256-104">歐盟國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-104">EU National Identification Number</span></span>

<span data-ttu-id="9c256-105">本主題說明資料遺失防護（DLP）原則在偵測到歐盟國身分識別號碼的敏感資訊類型時，會尋找哪些專案。</span><span class="sxs-lookup"><span data-stu-id="9c256-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="9c256-106">這種敏感資訊類型會定義不同的模式、關鍵字和其他每個國家/地區的證據。</span><span class="sxs-lookup"><span data-stu-id="9c256-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="9c256-107">奧地利</span><span class="sxs-lookup"><span data-stu-id="9c256-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="9c256-108">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-108">Format</span></span>

<span data-ttu-id="9c256-109">字母、數位及特殊字元的24個字元的組合</span><span class="sxs-lookup"><span data-stu-id="9c256-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-110">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-110">Pattern</span></span>

<span data-ttu-id="9c256-111">24個字元：</span><span class="sxs-lookup"><span data-stu-id="9c256-111">24 characters:</span></span>
  
-  <span data-ttu-id="9c256-112">22個字母（不區分大小寫）、數位、反斜線、正斜線或正號</span><span class="sxs-lookup"><span data-stu-id="9c256-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="9c256-113">兩個字母（不區分大小寫）、數位、反斜線、正斜線、加號或等號</span><span class="sxs-lookup"><span data-stu-id="9c256-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-114">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-114">Checksum</span></span>

<span data-ttu-id="9c256-115">不適用</span><span class="sxs-lookup"><span data-stu-id="9c256-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-116">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-116">Definition</span></span>

<span data-ttu-id="9c256-117">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-118">正則運算式`Regex_austria_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-119">找到來自`Keywords_austria_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-120">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-120">Keywords</span></span>

#### <a name="keywords_austria_eu_national_id_card"></a><span data-ttu-id="9c256-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="9c256-122">奧地利身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-122">austrian identity number</span></span>
  
<span data-ttu-id="9c256-123">本國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-123">national identity number</span></span>
  
<span data-ttu-id="9c256-124">身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-124">identity number</span></span>
  
<span data-ttu-id="9c256-125">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="9c256-125">national id</span></span>
  
<span data-ttu-id="9c256-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="9c256-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="9c256-127">比利時</span><span class="sxs-lookup"><span data-stu-id="9c256-127">Belgium</span></span>

<span data-ttu-id="9c256-128">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「比利時國家編號」一節。</span><span class="sxs-lookup"><span data-stu-id="9c256-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="9c256-129">保加利亞</span><span class="sxs-lookup"><span data-stu-id="9c256-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="9c256-130">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-130">Format</span></span>

<span data-ttu-id="9c256-131">10位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="9c256-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-132">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-132">Pattern</span></span>

<span data-ttu-id="9c256-133">10位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="9c256-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="9c256-134">與出生日期對應的六位數（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="9c256-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="9c256-135">對應至出生順序的兩位數</span><span class="sxs-lookup"><span data-stu-id="9c256-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="9c256-136">對應于性別的一個數位：用於男的偶數位數和用於女的奇數數位</span><span class="sxs-lookup"><span data-stu-id="9c256-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="9c256-137">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="9c256-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-138">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-138">Checksum</span></span>

<span data-ttu-id="9c256-139">是</span><span class="sxs-lookup"><span data-stu-id="9c256-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-140">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-140">Definition</span></span>

<span data-ttu-id="9c256-141">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="9c256-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-142">函數`Func_bulgaria_national_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-143">找到來自`Keywords_bulgaria_national_number`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="9c256-144">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-145">函數`Func_bulgaria_national_number`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-146">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-146">Keywords</span></span>

#### <a name="keywords_bulgaria_national_number"></a><span data-ttu-id="9c256-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="9c256-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="9c256-148">egn</span><span class="sxs-lookup"><span data-stu-id="9c256-148">egn</span></span>
  
<span data-ttu-id="9c256-149">egn#</span><span class="sxs-lookup"><span data-stu-id="9c256-149">egn#</span></span>
  
<span data-ttu-id="9c256-150">保加利亞國號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-150">bulgarian national number</span></span>
  
<span data-ttu-id="9c256-151">國家/地區號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-151">national number</span></span>
  
<span data-ttu-id="9c256-152">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-152">social security number</span></span>
  
<span data-ttu-id="9c256-153">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="9c256-153">nationalnumber#</span></span>
  
<span data-ttu-id="9c256-154">Ssn#</span><span class="sxs-lookup"><span data-stu-id="9c256-154">ssn#</span></span>
  
<span data-ttu-id="9c256-155">Ssn</span><span class="sxs-lookup"><span data-stu-id="9c256-155">ssn</span></span>
  
<span data-ttu-id="9c256-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="9c256-156">nationalnumber</span></span>
  
<span data-ttu-id="9c256-157">安娜#</span><span class="sxs-lookup"><span data-stu-id="9c256-157">bnn#</span></span>
  
<span data-ttu-id="9c256-158">安娜</span><span class="sxs-lookup"><span data-stu-id="9c256-158">bnn</span></span>
  
<span data-ttu-id="9c256-159">個人號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-159">personal id number</span></span>
  
<span data-ttu-id="9c256-160">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="9c256-160">personalidnumber#</span></span>
  
<span data-ttu-id="9c256-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="9c256-161">единен граждански номер</span></span>
  
<span data-ttu-id="9c256-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="9c256-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="9c256-163">егн</span><span class="sxs-lookup"><span data-stu-id="9c256-163">егн</span></span>
  
<span data-ttu-id="9c256-164">егн#</span><span class="sxs-lookup"><span data-stu-id="9c256-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="9c256-165">克羅埃西亞</span><span class="sxs-lookup"><span data-stu-id="9c256-165">Croatia</span></span>

<span data-ttu-id="9c256-166">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「克羅地亞身分識別號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="9c256-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="9c256-167">賽普勒斯</span><span class="sxs-lookup"><span data-stu-id="9c256-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="9c256-168">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-168">Format</span></span>

<span data-ttu-id="9c256-169">10位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="9c256-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-170">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-170">Pattern</span></span>

 <span data-ttu-id="9c256-171">10位數</span><span class="sxs-lookup"><span data-stu-id="9c256-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9c256-172">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-172">Checksum</span></span>

<span data-ttu-id="9c256-173">不適用</span><span class="sxs-lookup"><span data-stu-id="9c256-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-174">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-174">Definition</span></span>

<span data-ttu-id="9c256-175">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-176">正則運算式`Regex_cyprus_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-177">找到來自`Keywords_cyprus_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-178">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-178">Keywords</span></span>

#### <a name="keywords_cyprus_eu_national_id_card"></a><span data-ttu-id="9c256-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="9c256-180">id 卡號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-180">id card number</span></span>
  
<span data-ttu-id="9c256-181">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-181">national identification number</span></span>
  
<span data-ttu-id="9c256-182">個人號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-182">personal id number</span></span>
  
<span data-ttu-id="9c256-183">身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-183">identity card number</span></span>
  
<span data-ttu-id="9c256-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="9c256-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="9c256-185">捷克共和國</span><span class="sxs-lookup"><span data-stu-id="9c256-185">Czech Republic</span></span>

<span data-ttu-id="9c256-186">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「捷克國身分識別號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="9c256-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="9c256-187">丹麥</span><span class="sxs-lookup"><span data-stu-id="9c256-187">Denmark</span></span>

<span data-ttu-id="9c256-188">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「丹麥個人身分識別號碼」一節。</span><span class="sxs-lookup"><span data-stu-id="9c256-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="9c256-189">愛沙尼亞</span><span class="sxs-lookup"><span data-stu-id="9c256-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="9c256-190">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-190">Format</span></span>

<span data-ttu-id="9c256-191">11位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="9c256-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-192">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-192">Pattern</span></span>

<span data-ttu-id="9c256-193">11位數：</span><span class="sxs-lookup"><span data-stu-id="9c256-193">11 digits:</span></span>
  
- <span data-ttu-id="9c256-194">對應于性別和世紀的一位數（奇數號男，甚至是數位女; 1-2：19世紀; 3-4：20世紀; 5-6：21世紀）</span><span class="sxs-lookup"><span data-stu-id="9c256-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="9c256-195">對應至出生日期的六位數（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="9c256-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="9c256-196">三位數，對應至在相同日期出生的人員的序號</span><span class="sxs-lookup"><span data-stu-id="9c256-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="9c256-197">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="9c256-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-198">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-198">Checksum</span></span>

<span data-ttu-id="9c256-199">是</span><span class="sxs-lookup"><span data-stu-id="9c256-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-200">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-200">Definition</span></span>

<span data-ttu-id="9c256-201">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="9c256-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-202">函數`Func_estonia_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-203">找到來自`Keywords_estonia_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9c256-204">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-205">函數`Func_estonia_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-206">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-206">Keywords</span></span>

#### <a name="keywords_estonia_eu_national_id_card"></a><span data-ttu-id="9c256-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="9c256-208">個人身分識別碼</span><span class="sxs-lookup"><span data-stu-id="9c256-208">personal identification code</span></span>
  
<span data-ttu-id="9c256-209">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-209">personal identification number</span></span>
  
<span data-ttu-id="9c256-210">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-210">national identification number</span></span>
  
<span data-ttu-id="9c256-211">國家/地區號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-211">national number</span></span>
  
<span data-ttu-id="9c256-212">個人號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-212">personal id number</span></span>
  
<span data-ttu-id="9c256-213">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="9c256-213">personalidnumber#</span></span>
  
<span data-ttu-id="9c256-214">益</span><span class="sxs-lookup"><span data-stu-id="9c256-214">ik</span></span>
  
<span data-ttu-id="9c256-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="9c256-215">isikukood</span></span>
  
<span data-ttu-id="9c256-216">識別碼-kaart</span><span class="sxs-lookup"><span data-stu-id="9c256-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="9c256-217">芬蘭</span><span class="sxs-lookup"><span data-stu-id="9c256-217">Finland</span></span>

<span data-ttu-id="9c256-218">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「芬蘭國 ID」一節。</span><span class="sxs-lookup"><span data-stu-id="9c256-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="9c256-219">法國</span><span class="sxs-lookup"><span data-stu-id="9c256-219">France</span></span>

<span data-ttu-id="9c256-220">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「法國全國身分識別卡（CNI）」一節。</span><span class="sxs-lookup"><span data-stu-id="9c256-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="9c256-221">德國</span><span class="sxs-lookup"><span data-stu-id="9c256-221">Germany</span></span>

<span data-ttu-id="9c256-222">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「德國身分識別卡片編號」一節。</span><span class="sxs-lookup"><span data-stu-id="9c256-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="9c256-223">希臘</span><span class="sxs-lookup"><span data-stu-id="9c256-223">Greece</span></span>

<span data-ttu-id="9c256-224">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「希臘國 ID 卡」一節。</span><span class="sxs-lookup"><span data-stu-id="9c256-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="9c256-225">匈牙利</span><span class="sxs-lookup"><span data-stu-id="9c256-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="9c256-226">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-226">Format</span></span>

<span data-ttu-id="9c256-227">11位數</span><span class="sxs-lookup"><span data-stu-id="9c256-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-228">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-228">Pattern</span></span>

<span data-ttu-id="9c256-229">11位數：</span><span class="sxs-lookup"><span data-stu-id="9c256-229">11 digits:</span></span>
  
-  <span data-ttu-id="9c256-230">對應于性別（1-男，2-女，其他號碼）的一種數位，也可能是公民之前出生的公民，具有雙公民的1900或公民。</span><span class="sxs-lookup"><span data-stu-id="9c256-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="9c256-231">對應至出生日期的六位數（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="9c256-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="9c256-232">對應至序列值的三位數</span><span class="sxs-lookup"><span data-stu-id="9c256-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="9c256-233">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="9c256-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-234">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-234">Checksum</span></span>

<span data-ttu-id="9c256-235">是</span><span class="sxs-lookup"><span data-stu-id="9c256-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-236">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-236">Definition</span></span>

<span data-ttu-id="9c256-237">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="9c256-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-238">函數`Func_hungary_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-239">找到來自`Keywords_hungary_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9c256-240">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-241">函數`Func_hungary_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-242">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-242">Keywords</span></span>

#### <a name="keywords_hungary_eu_national_id_card"></a><span data-ttu-id="9c256-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="9c256-244">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-244">personal identification number</span></span>
  
<span data-ttu-id="9c256-245">識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-245">identification number</span></span>
  
<span data-ttu-id="9c256-246">個人號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-246">personal id number</span></span>
  
<span data-ttu-id="9c256-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="9c256-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="9c256-248">愛爾蘭</span><span class="sxs-lookup"><span data-stu-id="9c256-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="9c256-249">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-249">Format</span></span>

<span data-ttu-id="9c256-250">在指定的模式中，字母、數位及空格的九個字元組合</span><span class="sxs-lookup"><span data-stu-id="9c256-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-251">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-251">Pattern</span></span>

<span data-ttu-id="9c256-252">在指定的模式中，字母、數位及空格的九個字元組合</span><span class="sxs-lookup"><span data-stu-id="9c256-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="9c256-253">從01年1月2013至現在：</span><span class="sxs-lookup"><span data-stu-id="9c256-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="9c256-254">七位數</span><span class="sxs-lookup"><span data-stu-id="9c256-254">Seven digits</span></span> 
    
- <span data-ttu-id="9c256-255">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="9c256-255">One check digit</span></span>
    
- <span data-ttu-id="9c256-256">一個空格或大寫字母 "W" （區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="9c256-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="9c256-257">在2013年1月1日之前：</span><span class="sxs-lookup"><span data-stu-id="9c256-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="9c256-258">七位數</span><span class="sxs-lookup"><span data-stu-id="9c256-258">Seven digits</span></span> 
    
- <span data-ttu-id="9c256-259">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="9c256-259">One check digit</span></span>
    
- <span data-ttu-id="9c256-260">一個空格或大寫字母（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="9c256-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-261">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-261">Checksum</span></span>

<span data-ttu-id="9c256-262">是</span><span class="sxs-lookup"><span data-stu-id="9c256-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-263">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-263">Definition</span></span>

<span data-ttu-id="9c256-264">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="9c256-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-265">函數會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="9c256-266">找到來自的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-266">A keyword from is found.</span></span>
    
<span data-ttu-id="9c256-267">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-268">函數會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-268">The function finds content that matches the pattern.</span></span>
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-269">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-269">Keywords</span></span>

#### <a name="keywords_ireland_eu_national_id_card"></a><span data-ttu-id="9c256-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="9c256-271">個人公開服務號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-271">personal public service number</span></span>
  
<span data-ttu-id="9c256-272">pps 否</span><span class="sxs-lookup"><span data-stu-id="9c256-272">pps no</span></span>
  
<span data-ttu-id="9c256-273">收入與社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="9c256-274">rsi 否</span><span class="sxs-lookup"><span data-stu-id="9c256-274">rsi no</span></span>
  
<span data-ttu-id="9c256-275">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-275">personal identification number</span></span>
  
<span data-ttu-id="9c256-276">識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-276">identification number</span></span>
  
<span data-ttu-id="9c256-277">個人號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-277">personal id number</span></span>
  
<span data-ttu-id="9c256-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="9c256-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="9c256-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="9c256-279">uimh.</span></span> <span data-ttu-id="9c256-280">Psp</span><span class="sxs-lookup"><span data-stu-id="9c256-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="9c256-281">義大利</span><span class="sxs-lookup"><span data-stu-id="9c256-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="9c256-282">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-282">Format</span></span>

<span data-ttu-id="9c256-283">指定之模式中字母和數位的16個字元組合</span><span class="sxs-lookup"><span data-stu-id="9c256-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-284">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-284">Pattern</span></span>

<span data-ttu-id="9c256-285">字母和數位的16個字元的組合：</span><span class="sxs-lookup"><span data-stu-id="9c256-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="9c256-286">與系列名稱中的前三個雙子音相對應的三個字母</span><span class="sxs-lookup"><span data-stu-id="9c256-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="9c256-287">與名字中的第一個、第三個和第四個雙子音相對應的三個字母</span><span class="sxs-lookup"><span data-stu-id="9c256-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="9c256-288">與出生年份的最後一個數位相對應的兩位數</span><span class="sxs-lookup"><span data-stu-id="9c256-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="9c256-289">對應至出生月份之字母的一個字母，在字母順序中使用字母，但是只會使用字母 A 到 E、H、L、M、P、P、R 到 T （即，一月份是 A，10月是 R）</span><span class="sxs-lookup"><span data-stu-id="9c256-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="9c256-290">兩位數的出生月份天數，為了區別 genders，40會新增到女士的出生日。</span><span class="sxs-lookup"><span data-stu-id="9c256-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="9c256-291">相對於 municipality 人員專屬之地區代碼的四位數（國家/地區的碼用於外國國家）</span><span class="sxs-lookup"><span data-stu-id="9c256-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="9c256-292">一個同位數位</span><span class="sxs-lookup"><span data-stu-id="9c256-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-293">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-293">Checksum</span></span>

<span data-ttu-id="9c256-294">是</span><span class="sxs-lookup"><span data-stu-id="9c256-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-295">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-295">Definition</span></span>

<span data-ttu-id="9c256-296">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="9c256-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-297">函數`Func_italy_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-298">找到來自`Keywords_italy_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9c256-299">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-300">函數`Func_italy_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-301">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-301">Keywords</span></span>

#### <a name="keywords_italy_eu_national_id_card"></a><span data-ttu-id="9c256-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="9c256-303">個人程式碼</span><span class="sxs-lookup"><span data-stu-id="9c256-303">personal code</span></span>
  
<span data-ttu-id="9c256-304">個人碼編號</span><span class="sxs-lookup"><span data-stu-id="9c256-304">personal code number</span></span>
  
<span data-ttu-id="9c256-305">個人憑證號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-305">personal certificate number</span></span>
  
<span data-ttu-id="9c256-306">會計代碼</span><span class="sxs-lookup"><span data-stu-id="9c256-306">fiscal code</span></span>
  
<span data-ttu-id="9c256-307">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="9c256-307">personalcodeno#</span></span>
  
<span data-ttu-id="9c256-308">個人號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-308">personal id number</span></span>
  
<span data-ttu-id="9c256-309">個人識別碼代碼</span><span class="sxs-lookup"><span data-stu-id="9c256-309">personal id code</span></span>
  
<span data-ttu-id="9c256-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="9c256-310">codice personale</span></span>
  
<span data-ttu-id="9c256-311">numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="9c256-311">numero certificato personale</span></span>
  
<span data-ttu-id="9c256-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="9c256-312">numero personale</span></span>
  
<span data-ttu-id="9c256-313">numero 識別碼 personale</span><span class="sxs-lookup"><span data-stu-id="9c256-313">numero id personale</span></span>
  
<span data-ttu-id="9c256-314">codice 識別碼 personale</span><span class="sxs-lookup"><span data-stu-id="9c256-314">codice id personale</span></span>
  
<span data-ttu-id="9c256-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="9c256-315">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="9c256-316">拉脫維亞</span><span class="sxs-lookup"><span data-stu-id="9c256-316">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="9c256-317">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-317">Format</span></span>

<span data-ttu-id="9c256-318">11位數和指定格式的連字號</span><span class="sxs-lookup"><span data-stu-id="9c256-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-319">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-319">Pattern</span></span>

<span data-ttu-id="9c256-320">11位數和連字號：</span><span class="sxs-lookup"><span data-stu-id="9c256-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="9c256-321">與出生日期對應的六位數（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="9c256-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="9c256-322">連字號</span><span class="sxs-lookup"><span data-stu-id="9c256-322">A hyphen</span></span>
    
- <span data-ttu-id="9c256-323">一個數位，對應至出生世紀（"0" 代表19世紀，"1" 代表20世紀，而 "2" 代表21世紀）</span><span class="sxs-lookup"><span data-stu-id="9c256-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="9c256-324">四位數（隨機產生）</span><span class="sxs-lookup"><span data-stu-id="9c256-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-325">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-325">Checksum</span></span>

<span data-ttu-id="9c256-326">是</span><span class="sxs-lookup"><span data-stu-id="9c256-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-327">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-327">Definition</span></span>

<span data-ttu-id="9c256-328">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="9c256-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-329">函數`Func_latvia_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-330">找到來自`Keywords_latvia_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9c256-331">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-332">函數`Func_latvia_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-333">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-333">Keywords</span></span>

#### <a name="keywords_latvia_eu_national_id_card"></a><span data-ttu-id="9c256-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="9c256-335">個人程式碼</span><span class="sxs-lookup"><span data-stu-id="9c256-335">personal code</span></span>
  
<span data-ttu-id="9c256-336">個人碼編號</span><span class="sxs-lookup"><span data-stu-id="9c256-336">personal code number</span></span>
  
<span data-ttu-id="9c256-337">個人憑證號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-337">personal certificate number</span></span>
  
<span data-ttu-id="9c256-338">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="9c256-338">personalcodeno#</span></span>
  
<span data-ttu-id="9c256-339">個人號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-339">personal id number</span></span>
  
<span data-ttu-id="9c256-340">個人識別碼代碼</span><span class="sxs-lookup"><span data-stu-id="9c256-340">personal id code</span></span>
  
<span data-ttu-id="9c256-341">角色 kods</span><span class="sxs-lookup"><span data-stu-id="9c256-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="9c256-342">立陶宛</span><span class="sxs-lookup"><span data-stu-id="9c256-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="9c256-343">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-343">Format</span></span>

<span data-ttu-id="9c256-344">11位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="9c256-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-345">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-345">Pattern</span></span>

<span data-ttu-id="9c256-346">11位數，不含空格及分隔符號：</span><span class="sxs-lookup"><span data-stu-id="9c256-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="9c256-347">對應至人員性別和出生世紀的一個數位</span><span class="sxs-lookup"><span data-stu-id="9c256-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="9c256-348">對應至出生日期的六位數（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="9c256-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="9c256-349">對應至出生日期之序號的三位數</span><span class="sxs-lookup"><span data-stu-id="9c256-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="9c256-350">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="9c256-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-351">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-351">Checksum</span></span>

<span data-ttu-id="9c256-352">是</span><span class="sxs-lookup"><span data-stu-id="9c256-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-353">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-353">Definition</span></span>

<span data-ttu-id="9c256-354">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="9c256-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-355">函數`Func_lithuania_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-356">找到來自`Keywords_lithuania_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9c256-357">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-358">函數`Func_lithuania_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-359">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-359">Keywords</span></span>

#### <a name="keywords_lithuania_eu_national_id_card"></a><span data-ttu-id="9c256-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="9c256-361">個人數位代碼</span><span class="sxs-lookup"><span data-stu-id="9c256-361">personal numeric code</span></span>
  
<span data-ttu-id="9c256-362">唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9c256-362">unique identification number</span></span>
  
<span data-ttu-id="9c256-363">公民服務號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-363">citizen service number</span></span>
  
<span data-ttu-id="9c256-364">唯一的身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-364">unique identity number</span></span>
  
<span data-ttu-id="9c256-365">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="9c256-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="9c256-366">個人程式碼。</span><span class="sxs-lookup"><span data-stu-id="9c256-366">personal code.</span></span>
  
<span data-ttu-id="9c256-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="9c256-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="9c256-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="9c256-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="9c256-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="9c256-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="9c256-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="9c256-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="9c256-371">asmens kodas.</span><span class="sxs-lookup"><span data-stu-id="9c256-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="9c256-372">盧森堡</span><span class="sxs-lookup"><span data-stu-id="9c256-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="9c256-373">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-373">Format</span></span>

<span data-ttu-id="9c256-374">11位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="9c256-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-375">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-375">Pattern</span></span>

<span data-ttu-id="9c256-376">11位數</span><span class="sxs-lookup"><span data-stu-id="9c256-376">11 digits</span></span>
  
- <span data-ttu-id="9c256-377">對應至人員性別和出生世紀的一個數位</span><span class="sxs-lookup"><span data-stu-id="9c256-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="9c256-378">對應至出生日期的六位數（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="9c256-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="9c256-379">對應至出生日期之序號的三位數</span><span class="sxs-lookup"><span data-stu-id="9c256-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="9c256-380">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="9c256-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-381">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-381">Checksum</span></span>

<span data-ttu-id="9c256-382">不適用</span><span class="sxs-lookup"><span data-stu-id="9c256-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-383">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-383">Definition</span></span>

<span data-ttu-id="9c256-384">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-385">正則運算式`Regex_luxemburg_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-386">找到來自`Keywords_luxemburg_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-387">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-387">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_national_id_card"></a><span data-ttu-id="9c256-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="9c256-389">個人識別碼</span><span class="sxs-lookup"><span data-stu-id="9c256-389">personal id</span></span>
  
<span data-ttu-id="9c256-390">個人號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-390">personal id number</span></span>
  
<span data-ttu-id="9c256-391">personalidno#</span><span class="sxs-lookup"><span data-stu-id="9c256-391">personalidno#</span></span>
  
<span data-ttu-id="9c256-392">唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9c256-392">unique id number</span></span>
  
<span data-ttu-id="9c256-393">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="9c256-393">personalidnumber#</span></span>
  
<span data-ttu-id="9c256-394">唯一識別碼機碼</span><span class="sxs-lookup"><span data-stu-id="9c256-394">unique id key</span></span>
  
<span data-ttu-id="9c256-395">個人識別碼代碼</span><span class="sxs-lookup"><span data-stu-id="9c256-395">personal id code</span></span>
  
<span data-ttu-id="9c256-396">uniqueidkey#</span><span class="sxs-lookup"><span data-stu-id="9c256-396">uniqueidkey#</span></span>
  
<span data-ttu-id="9c256-397">個別程式碼</span><span class="sxs-lookup"><span data-stu-id="9c256-397">individual code</span></span>
  
<span data-ttu-id="9c256-398">個別識別碼</span><span class="sxs-lookup"><span data-stu-id="9c256-398">individual id</span></span>
  
<span data-ttu-id="9c256-399">eindeutige id-nummer</span><span class="sxs-lookup"><span data-stu-id="9c256-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="9c256-400">eindeutige 識別碼</span><span class="sxs-lookup"><span data-stu-id="9c256-400">eindeutige id</span></span>
  
<span data-ttu-id="9c256-401">識別碼 personnelle</span><span class="sxs-lookup"><span data-stu-id="9c256-401">id personnelle</span></span>
  
<span data-ttu-id="9c256-402">numéro d'identification 人員</span><span class="sxs-lookup"><span data-stu-id="9c256-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="9c256-403">idpersonnelle#</span><span class="sxs-lookup"><span data-stu-id="9c256-403">idpersonnelle#</span></span>
  
<span data-ttu-id="9c256-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="9c256-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="9c256-405">eindeutigeid#</span><span class="sxs-lookup"><span data-stu-id="9c256-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="9c256-406">馬爾他</span><span class="sxs-lookup"><span data-stu-id="9c256-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="9c256-407">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-407">Format</span></span>

<span data-ttu-id="9c256-408">七位數後接一個字母</span><span class="sxs-lookup"><span data-stu-id="9c256-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-409">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-409">Pattern</span></span>

<span data-ttu-id="9c256-410">七位數後接一個字母：</span><span class="sxs-lookup"><span data-stu-id="9c256-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="9c256-411">七位數</span><span class="sxs-lookup"><span data-stu-id="9c256-411">Seven digits</span></span> 
    
- <span data-ttu-id="9c256-412">單一大寫字母（區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="9c256-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-413">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-413">Checksum</span></span>

<span data-ttu-id="9c256-414">不適用</span><span class="sxs-lookup"><span data-stu-id="9c256-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-415">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-415">Definition</span></span>

<span data-ttu-id="9c256-416">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-417">正則運算式`Regex_malta_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-418">找到來自`Keywords_malta_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9c256-419">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="9c256-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-420">正則運算式`Regex_malta_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-421">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-421">Keywords</span></span>

#### <a name="keywords_malta_eu_national_id_card"></a><span data-ttu-id="9c256-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="9c256-423">個人數位代碼</span><span class="sxs-lookup"><span data-stu-id="9c256-423">personal numeric code</span></span>
  
<span data-ttu-id="9c256-424">唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9c256-424">unique identification number</span></span>
  
<span data-ttu-id="9c256-425">公民服務號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-425">citizen service number</span></span>
  
<span data-ttu-id="9c256-426">唯一的身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-426">unique identity number</span></span>
  
<span data-ttu-id="9c256-427">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="9c256-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="9c256-428">kodiċi numerali personali</span><span class="sxs-lookup"><span data-stu-id="9c256-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="9c256-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="9c256-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="9c256-430">numru tas-servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="9c256-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="9c256-431">numru ta ' identità uniku</span><span class="sxs-lookup"><span data-stu-id="9c256-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="9c256-432">荷蘭</span><span class="sxs-lookup"><span data-stu-id="9c256-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="9c256-433">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-433">Format</span></span>

<span data-ttu-id="9c256-434">九位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="9c256-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-435">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-435">Pattern</span></span>

<span data-ttu-id="9c256-436">九位數</span><span class="sxs-lookup"><span data-stu-id="9c256-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9c256-437">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-437">Checksum</span></span>

<span data-ttu-id="9c256-438">是</span><span class="sxs-lookup"><span data-stu-id="9c256-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-439">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-439">Definition</span></span>

<span data-ttu-id="9c256-440">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="9c256-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-441">函數`Func_netherlands_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-442">找到來自的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-442">A keyword from is found.</span></span>
    
<span data-ttu-id="9c256-443">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-444">函數`Func_netherlands_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-445">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-445">Keywords</span></span>

#### <a name="keywords_netherlands_eu_national_id_card"></a><span data-ttu-id="9c256-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="9c256-447">個人數位代碼</span><span class="sxs-lookup"><span data-stu-id="9c256-447">personal numeric code</span></span>
  
<span data-ttu-id="9c256-448">唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9c256-448">unique identification number</span></span>
  
<span data-ttu-id="9c256-449">公民服務號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-449">citizen service number</span></span>
  
<span data-ttu-id="9c256-450">唯一的身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-450">unique identity number</span></span>
  
<span data-ttu-id="9c256-451">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="9c256-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="9c256-452">bsn</span><span class="sxs-lookup"><span data-stu-id="9c256-452">bsn</span></span>
  
<span data-ttu-id="9c256-453">bsn#</span><span class="sxs-lookup"><span data-stu-id="9c256-453">bsn#</span></span>
  
<span data-ttu-id="9c256-454">persoonlijke numerieke 程式碼</span><span class="sxs-lookup"><span data-stu-id="9c256-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="9c256-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="9c256-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="9c256-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="9c256-456">burgerservicenummer</span></span>
  
<span data-ttu-id="9c256-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="9c256-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="9c256-458">波蘭</span><span class="sxs-lookup"><span data-stu-id="9c256-458">Poland</span></span>

<span data-ttu-id="9c256-459">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「波蘭國家識別碼（PESEL）」一節。</span><span class="sxs-lookup"><span data-stu-id="9c256-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="9c256-460">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="9c256-460">Portugal</span></span>

<span data-ttu-id="9c256-461">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「葡萄牙公民卡片編號」一節。</span><span class="sxs-lookup"><span data-stu-id="9c256-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="9c256-462">羅馬尼亞</span><span class="sxs-lookup"><span data-stu-id="9c256-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="9c256-463">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-463">Format</span></span>

<span data-ttu-id="9c256-464">13位數，不含空格及分隔符號</span><span class="sxs-lookup"><span data-stu-id="9c256-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-465">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-465">Pattern</span></span>

<span data-ttu-id="9c256-466">13位數</span><span class="sxs-lookup"><span data-stu-id="9c256-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9c256-467">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-467">Checksum</span></span>

<span data-ttu-id="9c256-468">是</span><span class="sxs-lookup"><span data-stu-id="9c256-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-469">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-469">Definition</span></span>

<span data-ttu-id="9c256-470">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="9c256-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-471">函數`Func_romania_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-472">找到來自`Keywords_romania_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9c256-473">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-474">函數`Func_romania_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-475">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-475">Keywords</span></span>

#### <a name="keywords_romania_eu_national_id_card"></a><span data-ttu-id="9c256-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="9c256-477">個人數位代碼</span><span class="sxs-lookup"><span data-stu-id="9c256-477">personal numeric code</span></span>
  
<span data-ttu-id="9c256-478">唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9c256-478">unique identification number</span></span>
  
<span data-ttu-id="9c256-479">Cnp</span><span class="sxs-lookup"><span data-stu-id="9c256-479">cnp</span></span>
  
<span data-ttu-id="9c256-480">Cnp#</span><span class="sxs-lookup"><span data-stu-id="9c256-480">cnp#</span></span>
  
<span data-ttu-id="9c256-481">針</span><span class="sxs-lookup"><span data-stu-id="9c256-481">pin</span></span>
  
<span data-ttu-id="9c256-482">針#</span><span class="sxs-lookup"><span data-stu-id="9c256-482">pin#</span></span>
  
<span data-ttu-id="9c256-483">保險號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-483">insurance number</span></span>
  
<span data-ttu-id="9c256-484">insurancenumber#</span><span class="sxs-lookup"><span data-stu-id="9c256-484">insurancenumber#</span></span>
  
<span data-ttu-id="9c256-485">唯一的身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-485">unique identity number</span></span>
  
<span data-ttu-id="9c256-486">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="9c256-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="9c256-487">貨到數值的個人</span><span class="sxs-lookup"><span data-stu-id="9c256-487">cod numeric personal</span></span>
  
<span data-ttu-id="9c256-488">identificare 個人</span><span class="sxs-lookup"><span data-stu-id="9c256-488">cod identificare personal</span></span>
  
<span data-ttu-id="9c256-489">貨至 unic identificare</span><span class="sxs-lookup"><span data-stu-id="9c256-489">cod unic identificare</span></span>
  
<span data-ttu-id="9c256-490">număr 個人 unic</span><span class="sxs-lookup"><span data-stu-id="9c256-490">număr personal unic</span></span>
  
<span data-ttu-id="9c256-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="9c256-491">număr identitate</span></span>
  
<span data-ttu-id="9c256-492">număr identificare 個人</span><span class="sxs-lookup"><span data-stu-id="9c256-492">număr identificare personal</span></span>
  
<span data-ttu-id="9c256-493">număridentitate#</span><span class="sxs-lookup"><span data-stu-id="9c256-493">număridentitate#</span></span>
  
<span data-ttu-id="9c256-494">codnumericpersonal#</span><span class="sxs-lookup"><span data-stu-id="9c256-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="9c256-495">numărpersonalunic#</span><span class="sxs-lookup"><span data-stu-id="9c256-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="9c256-496">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="9c256-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="9c256-497">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-497">Format</span></span>

<span data-ttu-id="9c256-498">10位數包含一個反斜線</span><span class="sxs-lookup"><span data-stu-id="9c256-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-499">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-499">Pattern</span></span>

<span data-ttu-id="9c256-500">10位數包含一個反斜線：</span><span class="sxs-lookup"><span data-stu-id="9c256-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9c256-501">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-501">Checksum</span></span>

<span data-ttu-id="9c256-502">是</span><span class="sxs-lookup"><span data-stu-id="9c256-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-503">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-503">Definition</span></span>

<span data-ttu-id="9c256-504">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="9c256-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-505">函數`Func_slovakia_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-506">找到來自`Keywords_slovakia_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9c256-507">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-508">函數`Func_slovakia_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-509">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-509">Keywords</span></span>

#### <a name="keywords_slovakia_eu_national_id_card"></a><span data-ttu-id="9c256-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="9c256-511">出生號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-511">birth number</span></span>
  
<span data-ttu-id="9c256-512">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-512">national identification number</span></span>
  
<span data-ttu-id="9c256-513">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-513">personal identification number</span></span>
  
<span data-ttu-id="9c256-514">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-514">social security number</span></span>
  
<span data-ttu-id="9c256-515">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="9c256-515">nationalnumber#</span></span>
  
<span data-ttu-id="9c256-516">Ssn#</span><span class="sxs-lookup"><span data-stu-id="9c256-516">ssn#</span></span>
  
<span data-ttu-id="9c256-517">Ssn</span><span class="sxs-lookup"><span data-stu-id="9c256-517">ssn</span></span>
  
<span data-ttu-id="9c256-518">國家/地區號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-518">national number</span></span>
  
<span data-ttu-id="9c256-519">個人號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-519">personal id number</span></span>
  
<span data-ttu-id="9c256-520">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="9c256-520">personalidnumber#</span></span>
  
<span data-ttu-id="9c256-521">rč</span><span class="sxs-lookup"><span data-stu-id="9c256-521">rč</span></span>
  
<span data-ttu-id="9c256-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="9c256-522">rodné číslo</span></span>
  
<span data-ttu-id="9c256-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="9c256-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="9c256-524">斯洛維尼亞</span><span class="sxs-lookup"><span data-stu-id="9c256-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="9c256-525">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-525">Format</span></span>

<span data-ttu-id="9c256-526">13位數，不含空格或分隔符號</span><span class="sxs-lookup"><span data-stu-id="9c256-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-527">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-527">Pattern</span></span>

<span data-ttu-id="9c256-528">指定的模式中的13位數：</span><span class="sxs-lookup"><span data-stu-id="9c256-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="9c256-529">對應至出生日期（DDMMLLL）的7位數，其中 "LLL" 會對應至出生年份的後三位數</span><span class="sxs-lookup"><span data-stu-id="9c256-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="9c256-530">對應至出生區域的兩位數</span><span class="sxs-lookup"><span data-stu-id="9c256-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="9c256-531">三個數字，對應于一天出生的性別和序號碼組合（000-499 的插頭和500-999 的女）</span><span class="sxs-lookup"><span data-stu-id="9c256-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="9c256-532">一個檢查碼</span><span class="sxs-lookup"><span data-stu-id="9c256-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-533">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-533">Checksum</span></span>

<span data-ttu-id="9c256-534">是</span><span class="sxs-lookup"><span data-stu-id="9c256-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-535">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-535">Definition</span></span>

<span data-ttu-id="9c256-536">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="9c256-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-537">函數`Func_slovenia_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-538">找到來自`Keywords_slovenia_eu_national_id_card`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9c256-539">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-540">函數`Func_slovenia_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-541">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-541">Keywords</span></span>

#### <a name="keywords_slovenia_eu_national_id_card"></a><span data-ttu-id="9c256-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="9c256-543">個人數位代碼</span><span class="sxs-lookup"><span data-stu-id="9c256-543">personal numeric code</span></span>
  
<span data-ttu-id="9c256-544">唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9c256-544">unique identification number</span></span>
  
<span data-ttu-id="9c256-545">唯一註冊號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-545">unique registration number</span></span>
  
<span data-ttu-id="9c256-546">唯一的身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-546">unique identity number</span></span>
  
<span data-ttu-id="9c256-547">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="9c256-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="9c256-548">唯一主公民號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-548">unique master citizen number</span></span>
  
<span data-ttu-id="9c256-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="9c256-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="9c256-550">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="9c256-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="9c256-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="9c256-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="9c256-552">emšo</span><span class="sxs-lookup"><span data-stu-id="9c256-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="9c256-553">西班牙</span><span class="sxs-lookup"><span data-stu-id="9c256-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="9c256-554">格式</span><span class="sxs-lookup"><span data-stu-id="9c256-554">Format</span></span>

<span data-ttu-id="9c256-555">七位數後接一個字元</span><span class="sxs-lookup"><span data-stu-id="9c256-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9c256-556">模式</span><span class="sxs-lookup"><span data-stu-id="9c256-556">Pattern</span></span>

<span data-ttu-id="9c256-557">七位數後接一個字元</span><span class="sxs-lookup"><span data-stu-id="9c256-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="9c256-558">七位數</span><span class="sxs-lookup"><span data-stu-id="9c256-558">Seven digits</span></span>
    
- <span data-ttu-id="9c256-559">一個數位或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="9c256-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9c256-560">校驗</span><span class="sxs-lookup"><span data-stu-id="9c256-560">Checksum</span></span>

<span data-ttu-id="9c256-561">不適用</span><span class="sxs-lookup"><span data-stu-id="9c256-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9c256-562">定義</span><span class="sxs-lookup"><span data-stu-id="9c256-562">Definition</span></span>

<span data-ttu-id="9c256-563">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="9c256-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9c256-564">正則運算式`Regex_spain_eu_national_id_card`會找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="9c256-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9c256-565">找到來自`Keywords_spain_eu_national_id_card"`的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="9c256-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9c256-566">關鍵字</span><span class="sxs-lookup"><span data-stu-id="9c256-566">Keywords</span></span>

#### <a name="keywords_spain_eu_national_id_card"></a><span data-ttu-id="9c256-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9c256-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="9c256-568">dni</span><span class="sxs-lookup"><span data-stu-id="9c256-568">dni</span></span>
  
<span data-ttu-id="9c256-569">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-569">national identification number</span></span>
  
<span data-ttu-id="9c256-570">本國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-570">national identity number</span></span>
  
<span data-ttu-id="9c256-571">保險號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-571">insurance number</span></span>
  
<span data-ttu-id="9c256-572">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-572">personal identification number</span></span>
  
<span data-ttu-id="9c256-573">本國身分識別</span><span class="sxs-lookup"><span data-stu-id="9c256-573">national identity</span></span>
  
<span data-ttu-id="9c256-574">個人身分識別</span><span class="sxs-lookup"><span data-stu-id="9c256-574">personal identity no</span></span>
  
<span data-ttu-id="9c256-575">唯一的身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="9c256-575">unique identity number</span></span>
  
<span data-ttu-id="9c256-576">nationalidno#</span><span class="sxs-lookup"><span data-stu-id="9c256-576">nationalidno#</span></span>
  
<span data-ttu-id="9c256-577">uniqueid#</span><span class="sxs-lookup"><span data-stu-id="9c256-577">uniqueid#</span></span>
  
<span data-ttu-id="9c256-578">dni#</span><span class="sxs-lookup"><span data-stu-id="9c256-578">dni#</span></span>
  
<span data-ttu-id="9c256-579">nationalid#</span><span class="sxs-lookup"><span data-stu-id="9c256-579">nationalid#</span></span>
  
<span data-ttu-id="9c256-580">聶#</span><span class="sxs-lookup"><span data-stu-id="9c256-580">nie#</span></span>
  
<span data-ttu-id="9c256-581">聶</span><span class="sxs-lookup"><span data-stu-id="9c256-581">nie</span></span>
  
<span data-ttu-id="9c256-582">nienúmero#</span><span class="sxs-lookup"><span data-stu-id="9c256-582">nienúmero#</span></span>
  
<span data-ttu-id="9c256-583">nie número</span><span class="sxs-lookup"><span data-stu-id="9c256-583">nie número</span></span>
  
<span data-ttu-id="9c256-584">documento nacional de identidad</span><span class="sxs-lookup"><span data-stu-id="9c256-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="9c256-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="9c256-585">identidad único</span></span>
  
<span data-ttu-id="9c256-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="9c256-586">número nacional identidad</span></span>
  
<span data-ttu-id="9c256-587">dni número</span><span class="sxs-lookup"><span data-stu-id="9c256-587">dni número</span></span>
  
<span data-ttu-id="9c256-588">dninúmero#</span><span class="sxs-lookup"><span data-stu-id="9c256-588">dninúmero#</span></span>
  
<span data-ttu-id="9c256-589">identidadúnico#</span><span class="sxs-lookup"><span data-stu-id="9c256-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="9c256-590">瑞典</span><span class="sxs-lookup"><span data-stu-id="9c256-590">Sweden</span></span>

<span data-ttu-id="9c256-591">如需詳細資訊，請參閱[敏感資訊類型所尋找](what-the-sensitive-information-types-look-for.md)的「瑞典全國識別碼」一節。</span><span class="sxs-lookup"><span data-stu-id="9c256-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9c256-592">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9c256-592">See also</span></span>

[<span data-ttu-id="9c256-593">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="9c256-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

