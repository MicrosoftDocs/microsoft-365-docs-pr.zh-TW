---
title: 敏感資訊類型在找什麼
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 安全性&amp;與合規性中心的資料遺失防護（DLP）包括可供您在 DLP 原則中使用的80機密資訊類型。 本主題列出所有敏感資訊類型，並顯示 DLP 原則在偵測到每種類型時所尋找的功能。
ms.openlocfilehash: aa3a08961ccad92c9986db16c1d8180d9b0cd17e
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240278"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="a243a-104">敏感資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="a243a-104">What the sensitive information types look for</span></span>

<span data-ttu-id="a243a-105">Office 365 安全性&amp;與合規性中心的資料遺失防護（DLP）包含許多機密資訊類型，可供您在 DLP 原則中使用。</span><span class="sxs-lookup"><span data-stu-id="a243a-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="a243a-106">本主題列出所有敏感資訊類型，並顯示 DLP 原則在偵測到每種類型時所尋找的功能。</span><span class="sxs-lookup"><span data-stu-id="a243a-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="a243a-107">敏感資訊類型是由正則運算式或函數所識別的模式所定義。</span><span class="sxs-lookup"><span data-stu-id="a243a-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="a243a-108">此外，您也可以使用確切證據（如關鍵字及校驗和）來識別敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="a243a-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="a243a-109">評估程式中也會使用信賴等級和近程。</span><span class="sxs-lookup"><span data-stu-id="a243a-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="a243a-110">ABA 路由號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-111">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-111">Format</span></span>

<span data-ttu-id="a243a-112">格式或未格式化的模式中的9位數</span><span class="sxs-lookup"><span data-stu-id="a243a-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-113">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-113">Pattern</span></span>

<span data-ttu-id="a243a-114">格式 化：</span><span class="sxs-lookup"><span data-stu-id="a243a-114">Formatted:</span></span>
- <span data-ttu-id="a243a-115">以0、1、2、3、6、7或8開頭的四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="a243a-116">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-116">A hyphen</span></span>
- <span data-ttu-id="a243a-117">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-117">Four digits</span></span>
- <span data-ttu-id="a243a-118">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-118">A hyphen</span></span>
- <span data-ttu-id="a243a-119">一個數位</span><span class="sxs-lookup"><span data-stu-id="a243a-119">A digit</span></span>

<span data-ttu-id="a243a-120">未格式化：9以0、1、2、3、6、7或8開頭的連續數位</span><span class="sxs-lookup"><span data-stu-id="a243a-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="a243a-121">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-121">Checksum</span></span>

<span data-ttu-id="a243a-122">否</span><span class="sxs-lookup"><span data-stu-id="a243a-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-123">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-123">Definition</span></span>

<span data-ttu-id="a243a-124">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-125">函數 Func_aba_routing 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-126">會找到來自 Keyword_ABA_Routing 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="a243a-127">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="a243a-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="a243a-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="a243a-129">阿壩</span><span class="sxs-lookup"><span data-stu-id="a243a-129">aba</span></span>
- <span data-ttu-id="a243a-130">阿壩#</span><span class="sxs-lookup"><span data-stu-id="a243a-130">aba #</span></span>
- <span data-ttu-id="a243a-131">aba 路由#</span><span class="sxs-lookup"><span data-stu-id="a243a-131">aba routing #</span></span>
- <span data-ttu-id="a243a-132">aba 路由號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-132">aba routing number</span></span>
- <span data-ttu-id="a243a-133">阿壩#</span><span class="sxs-lookup"><span data-stu-id="a243a-133">aba#</span></span>
- <span data-ttu-id="a243a-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="a243a-134">abarouting#</span></span>
- <span data-ttu-id="a243a-135">aba 編號</span><span class="sxs-lookup"><span data-stu-id="a243a-135">aba number</span></span>
- <span data-ttu-id="a243a-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-136">abaroutingnumber</span></span>
- <span data-ttu-id="a243a-137">美洲銀行協會路由#</span><span class="sxs-lookup"><span data-stu-id="a243a-137">american bank association routing #</span></span>
- <span data-ttu-id="a243a-138">美洲銀行關聯性路由編號</span><span class="sxs-lookup"><span data-stu-id="a243a-138">american bank association routing number</span></span>
- <span data-ttu-id="a243a-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="a243a-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="a243a-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="a243a-141">銀行路由編號</span><span class="sxs-lookup"><span data-stu-id="a243a-141">bank routing number</span></span>
- <span data-ttu-id="a243a-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="a243a-142">bankrouting#</span></span>
- <span data-ttu-id="a243a-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-143">bankroutingnumber</span></span>
- <span data-ttu-id="a243a-144">路由轉口號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-144">routing transit number</span></span>
- <span data-ttu-id="a243a-145">RTN</span><span class="sxs-lookup"><span data-stu-id="a243a-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="a243a-146">阿根廷國內身分識別（DNI）號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-147">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-147">Format</span></span>

<span data-ttu-id="a243a-148">以句點隔開的八位數</span><span class="sxs-lookup"><span data-stu-id="a243a-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-149">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-149">Pattern</span></span>

<span data-ttu-id="a243a-150">八位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-150">Eight digits:</span></span>
- <span data-ttu-id="a243a-151">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-151">Two digits</span></span>
- <span data-ttu-id="a243a-152">一個句點</span><span class="sxs-lookup"><span data-stu-id="a243a-152">A period</span></span>
- <span data-ttu-id="a243a-153">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-153">Three digits</span></span>
- <span data-ttu-id="a243a-154">一個句點</span><span class="sxs-lookup"><span data-stu-id="a243a-154">A period</span></span>
- <span data-ttu-id="a243a-155">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-156">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-156">Checksum</span></span>

<span data-ttu-id="a243a-157">否</span><span class="sxs-lookup"><span data-stu-id="a243a-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-158">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-158">Definition</span></span>

<span data-ttu-id="a243a-159">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-160">正則運算式 Regex_argentina_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-161">會找到來自 Keyword_argentina_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-162">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="a243a-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="a243a-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="a243a-164">阿根廷國內身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="a243a-165">身分識別</span><span class="sxs-lookup"><span data-stu-id="a243a-165">Identity</span></span> 
- <span data-ttu-id="a243a-166">身分識別的國內身分識別卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="a243a-167">DNI</span><span class="sxs-lookup"><span data-stu-id="a243a-167">DNI</span></span> 
- <span data-ttu-id="a243a-168">個人的 NIC 註冊人員</span><span class="sxs-lookup"><span data-stu-id="a243a-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="a243a-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="a243a-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="a243a-170">Registro Nacional de 拉斯維加斯角色</span><span class="sxs-lookup"><span data-stu-id="a243a-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="a243a-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="a243a-171">Identidad</span></span> 
- <span data-ttu-id="a243a-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="a243a-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="a243a-173">澳大利亞銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-174">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-174">Format</span></span>

<span data-ttu-id="a243a-175">包含或不含銀行狀態分公司號碼的6-10 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-176">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-176">Pattern</span></span>

<span data-ttu-id="a243a-177">帳戶號碼是6-10 位數。</span><span class="sxs-lookup"><span data-stu-id="a243a-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="a243a-178">澳大利亞銀行狀態分支編號：</span><span class="sxs-lookup"><span data-stu-id="a243a-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="a243a-179">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-179">Three digits</span></span> 
- <span data-ttu-id="a243a-180">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-180">A hyphen</span></span> 
- <span data-ttu-id="a243a-181">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-182">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-182">Checksum</span></span>

<span data-ttu-id="a243a-183">否</span><span class="sxs-lookup"><span data-stu-id="a243a-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-184">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-184">Definition</span></span>

<span data-ttu-id="a243a-185">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-186">正則運算式 Regex_australia_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="a243a-187">會找到來自 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="a243a-188">正則運算式 Regex_australia_bank_account_number_bsb 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="a243a-189">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-190">正則運算式 Regex_australia_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="a243a-191">會找到來自 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-192">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="a243a-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a243a-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="a243a-194">swift 銀行代碼</span><span class="sxs-lookup"><span data-stu-id="a243a-194">swift bank code</span></span>
- <span data-ttu-id="a243a-195">通信銀行</span><span class="sxs-lookup"><span data-stu-id="a243a-195">correspondent bank</span></span>
- <span data-ttu-id="a243a-196">基礎貨幣</span><span class="sxs-lookup"><span data-stu-id="a243a-196">base currency</span></span>
- <span data-ttu-id="a243a-197">美國帳戶</span><span class="sxs-lookup"><span data-stu-id="a243a-197">usa account</span></span>
- <span data-ttu-id="a243a-198">持有者位址</span><span class="sxs-lookup"><span data-stu-id="a243a-198">holder address</span></span>
- <span data-ttu-id="a243a-199">銀行位址</span><span class="sxs-lookup"><span data-stu-id="a243a-199">bank address</span></span>
- <span data-ttu-id="a243a-200">資訊帳戶</span><span class="sxs-lookup"><span data-stu-id="a243a-200">information account</span></span>
- <span data-ttu-id="a243a-201">基金轉移</span><span class="sxs-lookup"><span data-stu-id="a243a-201">fund transfers</span></span>
- <span data-ttu-id="a243a-202">銀行費用</span><span class="sxs-lookup"><span data-stu-id="a243a-202">bank charges</span></span>
- <span data-ttu-id="a243a-203">銀行詳細資料</span><span class="sxs-lookup"><span data-stu-id="a243a-203">bank details</span></span>
- <span data-ttu-id="a243a-204">銀行資訊</span><span class="sxs-lookup"><span data-stu-id="a243a-204">banking information</span></span>
- <span data-ttu-id="a243a-205">完整名稱</span><span class="sxs-lookup"><span data-stu-id="a243a-205">full names</span></span>
- <span data-ttu-id="a243a-206">國際 原子能 機構</span><span class="sxs-lookup"><span data-stu-id="a243a-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="a243a-207">澳大利亞駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-208">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-208">Format</span></span>

<span data-ttu-id="a243a-209">九個字母和數位</span><span class="sxs-lookup"><span data-stu-id="a243a-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-210">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-210">Pattern</span></span>

<span data-ttu-id="a243a-211">九個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="a243a-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="a243a-212">兩位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="a243a-213">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-213">Two digits</span></span> 
- <span data-ttu-id="a243a-214">五個數字或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="a243a-215">OR</span><span class="sxs-lookup"><span data-stu-id="a243a-215">OR</span></span>

- <span data-ttu-id="a243a-216">1-2 選用的字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="a243a-217">4-9 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-217">4-9 digits</span></span>

<span data-ttu-id="a243a-218">OR</span><span class="sxs-lookup"><span data-stu-id="a243a-218">OR</span></span>

- <span data-ttu-id="a243a-219">九個數字或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-220">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-220">Checksum</span></span>

<span data-ttu-id="a243a-221">否</span><span class="sxs-lookup"><span data-stu-id="a243a-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-222">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-222">Definition</span></span>

<span data-ttu-id="a243a-223">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-224">正則運算式 Regex_australia_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-225">會找到來自 Keyword_australia_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="a243a-226">找不到 Keyword_australia_drivers_license_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="a243a-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a243a-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="a243a-229">國際動力允許</span><span class="sxs-lookup"><span data-stu-id="a243a-229">international driving permits</span></span>
- <span data-ttu-id="a243a-230">澳大利亞汽車協會</span><span class="sxs-lookup"><span data-stu-id="a243a-230">australian automobile association</span></span>
- <span data-ttu-id="a243a-231">國際駕駛允許</span><span class="sxs-lookup"><span data-stu-id="a243a-231">international driving permit</span></span>
- <span data-ttu-id="a243a-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="a243a-232">DriverLicence</span></span>
- <span data-ttu-id="a243a-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="a243a-233">DriverLicences</span></span>
- <span data-ttu-id="a243a-234">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-234">Driver Lic</span></span>
- <span data-ttu-id="a243a-235">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-235">Driver Licence</span></span>
- <span data-ttu-id="a243a-236">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-236">Driver Licences</span></span>
- <span data-ttu-id="a243a-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a243a-237">DriversLic</span></span>
- <span data-ttu-id="a243a-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="a243a-238">DriversLicence</span></span>
- <span data-ttu-id="a243a-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="a243a-239">DriversLicences</span></span>
- <span data-ttu-id="a243a-240">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-240">Drivers Lic</span></span>
- <span data-ttu-id="a243a-241">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-241">Drivers Lics</span></span>
- <span data-ttu-id="a243a-242">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-242">Drivers Licence</span></span>
- <span data-ttu-id="a243a-243">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-243">Drivers Licences</span></span>
- <span data-ttu-id="a243a-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-244">Driver'Lic</span></span>
- <span data-ttu-id="a243a-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-245">Driver'Lics</span></span>
- <span data-ttu-id="a243a-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="a243a-246">Driver'Licence</span></span>
- <span data-ttu-id="a243a-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="a243a-247">Driver'Licences</span></span>
- <span data-ttu-id="a243a-248">驅動程式「.Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-248">Driver' Lic</span></span>
- <span data-ttu-id="a243a-249">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-249">Driver' Lics</span></span>
- <span data-ttu-id="a243a-250">驅動程式 ' 許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-250">Driver' Licence</span></span>
- <span data-ttu-id="a243a-251">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="a243a-251">Driver' Licences</span></span>
- <span data-ttu-id="a243a-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a243a-252">Driver'sLic</span></span>
- <span data-ttu-id="a243a-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a243a-253">Driver'sLics</span></span>
- <span data-ttu-id="a243a-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="a243a-254">Driver'sLicence</span></span>
- <span data-ttu-id="a243a-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="a243a-255">Driver'sLicences</span></span>
- <span data-ttu-id="a243a-256">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-256">Driver's Lic</span></span>
- <span data-ttu-id="a243a-257">驅動程式的 Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-257">Driver's Lics</span></span>
- <span data-ttu-id="a243a-258">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-258">Driver's Licence</span></span>
- <span data-ttu-id="a243a-259">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-259">Driver's Licences</span></span>
- <span data-ttu-id="a243a-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="a243a-260">DriverLic#</span></span>
- <span data-ttu-id="a243a-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="a243a-261">DriverLics#</span></span>
- <span data-ttu-id="a243a-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="a243a-262">DriverLicence#</span></span>
- <span data-ttu-id="a243a-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="a243a-263">DriverLicences#</span></span>
- <span data-ttu-id="a243a-264">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="a243a-264">Driver Lic#</span></span>
- <span data-ttu-id="a243a-265">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-265">Driver Lics#</span></span>
- <span data-ttu-id="a243a-266">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="a243a-266">Driver Licence#</span></span>
- <span data-ttu-id="a243a-267">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-267">Driver Licences#</span></span>
- <span data-ttu-id="a243a-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="a243a-268">DriversLic#</span></span>
- <span data-ttu-id="a243a-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="a243a-269">DriversLics#</span></span>
- <span data-ttu-id="a243a-270">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="a243a-270">DriversLicence#</span></span>
- <span data-ttu-id="a243a-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="a243a-271">DriversLicences#</span></span>
- <span data-ttu-id="a243a-272">驅動程式 .Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-272">Drivers Lic#</span></span>
- <span data-ttu-id="a243a-273">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-273">Drivers Lics#</span></span>
- <span data-ttu-id="a243a-274">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="a243a-274">Drivers Licence#</span></span>
- <span data-ttu-id="a243a-275">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-275">Drivers Licences#</span></span>
- <span data-ttu-id="a243a-276">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-276">Driver'Lic#</span></span>
- <span data-ttu-id="a243a-277">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-277">Driver'Lics#</span></span>
- <span data-ttu-id="a243a-278">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="a243a-278">Driver'Licence#</span></span>
- <span data-ttu-id="a243a-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="a243a-279">Driver'Licences#</span></span>
- <span data-ttu-id="a243a-280">驅動程式「.Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-280">Driver' Lic#</span></span>
- <span data-ttu-id="a243a-281">驅動程式 ' Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-281">Driver' Lics#</span></span>
- <span data-ttu-id="a243a-282">驅動程式 ' 許可證#</span><span class="sxs-lookup"><span data-stu-id="a243a-282">Driver' Licence#</span></span>
- <span data-ttu-id="a243a-283">驅動程式 ' 授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-283">Driver' Licences#</span></span>
- <span data-ttu-id="a243a-284">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="a243a-284">Driver'sLic#</span></span>
- <span data-ttu-id="a243a-285">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="a243a-285">Driver'sLics#</span></span>
- <span data-ttu-id="a243a-286">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="a243a-286">Driver'sLicence#</span></span>
- <span data-ttu-id="a243a-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="a243a-287">Driver'sLicences#</span></span>
- <span data-ttu-id="a243a-288">驅動程式的 .Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-288">Driver's Lic#</span></span>
- <span data-ttu-id="a243a-289">驅動程式的 Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-289">Driver's Lics#</span></span>
- <span data-ttu-id="a243a-290">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-290">Driver's Licence#</span></span>
- <span data-ttu-id="a243a-291">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="a243a-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="a243a-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="a243a-293">Aaa</span><span class="sxs-lookup"><span data-stu-id="a243a-293">aaa</span></span>
- <span data-ttu-id="a243a-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a243a-294">DriverLicense</span></span>
- <span data-ttu-id="a243a-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a243a-295">DriverLicenses</span></span>
- <span data-ttu-id="a243a-296">駕照</span><span class="sxs-lookup"><span data-stu-id="a243a-296">Driver License</span></span>
- <span data-ttu-id="a243a-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-297">Driver Licenses</span></span>
- <span data-ttu-id="a243a-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="a243a-298">DriversLicense</span></span>
- <span data-ttu-id="a243a-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a243a-299">DriversLicenses</span></span>
- <span data-ttu-id="a243a-300">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-300">Drivers License</span></span>
- <span data-ttu-id="a243a-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-301">Drivers Licenses</span></span>
- <span data-ttu-id="a243a-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="a243a-302">Driver'License</span></span>
- <span data-ttu-id="a243a-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="a243a-303">Driver'Licenses</span></span>
- <span data-ttu-id="a243a-304">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-304">Driver' License</span></span>
- <span data-ttu-id="a243a-305">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="a243a-305">Driver' Licenses</span></span>
- <span data-ttu-id="a243a-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a243a-306">Driver'sLicense</span></span>
- <span data-ttu-id="a243a-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a243a-307">Driver'sLicenses</span></span>
- <span data-ttu-id="a243a-308">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-308">Driver's License</span></span>
- <span data-ttu-id="a243a-309">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-309">Driver's Licenses</span></span>
- <span data-ttu-id="a243a-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="a243a-310">DriverLicense#</span></span>
- <span data-ttu-id="a243a-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-311">DriverLicenses#</span></span>
- <span data-ttu-id="a243a-312">駕照#</span><span class="sxs-lookup"><span data-stu-id="a243a-312">Driver License#</span></span>
- <span data-ttu-id="a243a-313">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-313">Driver Licenses#</span></span>
- <span data-ttu-id="a243a-314">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="a243a-314">DriversLicense#</span></span>
- <span data-ttu-id="a243a-315">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-315">DriversLicenses#</span></span>
- <span data-ttu-id="a243a-316">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-316">Drivers License#</span></span>
- <span data-ttu-id="a243a-317">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-317">Drivers Licenses#</span></span>
- <span data-ttu-id="a243a-318">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="a243a-318">Driver'License#</span></span>
- <span data-ttu-id="a243a-319">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-319">Driver'Licenses#</span></span>
- <span data-ttu-id="a243a-320">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-320">Driver' License#</span></span>
- <span data-ttu-id="a243a-321">驅動程式的授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-321">Driver' Licenses#</span></span>
- <span data-ttu-id="a243a-322">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="a243a-322">Driver'sLicense#</span></span>
- <span data-ttu-id="a243a-323">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="a243a-324">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-324">Driver's License#</span></span>
- <span data-ttu-id="a243a-325">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="a243a-326">澳大利亞醫療帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-327">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-327">Format</span></span>

<span data-ttu-id="a243a-328">10-11 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-329">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-329">Pattern</span></span>

<span data-ttu-id="a243a-330">10-11 位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-330">10-11 digits:</span></span>
- <span data-ttu-id="a243a-331">第一個數位是在2-6 範圍內</span><span class="sxs-lookup"><span data-stu-id="a243a-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="a243a-332">第九位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="a243a-333">第十個數字是問題的位數</span><span class="sxs-lookup"><span data-stu-id="a243a-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="a243a-334">第十位數（選用）是個別數位</span><span class="sxs-lookup"><span data-stu-id="a243a-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-335">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-335">Checksum</span></span>

<span data-ttu-id="a243a-336">是</span><span class="sxs-lookup"><span data-stu-id="a243a-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-337">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-337">Definition</span></span>

<span data-ttu-id="a243a-338">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：</span><span class="sxs-lookup"><span data-stu-id="a243a-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-339">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-340">會找到來自 Keyword_Australia_Medical_Account_Number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="a243a-341">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-341">The checksum passes.</span></span>

<span data-ttu-id="a243a-342">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-343">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-344">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-344">The checksum passes.</span></span>

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-345">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="a243a-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="a243a-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="a243a-347">銀行帳戶詳細資料</span><span class="sxs-lookup"><span data-stu-id="a243a-347">bank account details</span></span>
- <span data-ttu-id="a243a-348">medicare 付款</span><span class="sxs-lookup"><span data-stu-id="a243a-348">medicare payments</span></span>
- <span data-ttu-id="a243a-349">抵押帳戶</span><span class="sxs-lookup"><span data-stu-id="a243a-349">mortgage account</span></span>
- <span data-ttu-id="a243a-350">銀行付款</span><span class="sxs-lookup"><span data-stu-id="a243a-350">bank payments</span></span>
- <span data-ttu-id="a243a-351">資訊分支</span><span class="sxs-lookup"><span data-stu-id="a243a-351">information branch</span></span>
- <span data-ttu-id="a243a-352">信用卡貸款</span><span class="sxs-lookup"><span data-stu-id="a243a-352">credit card loan</span></span>
- <span data-ttu-id="a243a-353">人體服務部門</span><span class="sxs-lookup"><span data-stu-id="a243a-353">department of human services</span></span>
- <span data-ttu-id="a243a-354">本機服務</span><span class="sxs-lookup"><span data-stu-id="a243a-354">local service</span></span>
- <span data-ttu-id="a243a-355">醫療</span><span class="sxs-lookup"><span data-stu-id="a243a-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="a243a-356">澳大利亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-357">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-357">Format</span></span>

<span data-ttu-id="a243a-358">字母后接7位數</span><span class="sxs-lookup"><span data-stu-id="a243a-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-359">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-359">Pattern</span></span>

<span data-ttu-id="a243a-360">字母（不區分大小寫）後接7位數</span><span class="sxs-lookup"><span data-stu-id="a243a-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-361">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-361">Checksum</span></span>

<span data-ttu-id="a243a-362">否</span><span class="sxs-lookup"><span data-stu-id="a243a-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-363">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-363">Definition</span></span>

<span data-ttu-id="a243a-364">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-365">正則運算式 Regex_australia_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-366">會找到 Keyword_passport 或 Keyword_australia_passport_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="a243a-367">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a243a-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a243a-368">Keyword_passport</span></span>

- <span data-ttu-id="a243a-369">護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-369">Passport Number</span></span>
- <span data-ttu-id="a243a-370">護照否</span><span class="sxs-lookup"><span data-stu-id="a243a-370">Passport No</span></span>
- <span data-ttu-id="a243a-371">護照#</span><span class="sxs-lookup"><span data-stu-id="a243a-371">Passport #</span></span>
- <span data-ttu-id="a243a-372">護照#</span><span class="sxs-lookup"><span data-stu-id="a243a-372">Passport#</span></span>
- <span data-ttu-id="a243a-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="a243a-373">PassportID</span></span>
- <span data-ttu-id="a243a-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="a243a-374">Passportno</span></span>
- <span data-ttu-id="a243a-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-375">passportnumber</span></span>
- <span data-ttu-id="a243a-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="a243a-376">パスポート</span></span>
- <span data-ttu-id="a243a-377">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="a243a-377">パスポート番号</span></span>
- <span data-ttu-id="a243a-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a243a-378">パスポートのNum</span></span>
- <span data-ttu-id="a243a-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="a243a-379">パスポート ＃</span></span> 
- <span data-ttu-id="a243a-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a243a-380">Numéro de passeport</span></span>
- <span data-ttu-id="a243a-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a243a-381">Passeport n °</span></span>
- <span data-ttu-id="a243a-382">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="a243a-382">Passeport Non</span></span>
- <span data-ttu-id="a243a-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="a243a-383">Passeport #</span></span>
- <span data-ttu-id="a243a-384">Passeport#</span><span class="sxs-lookup"><span data-stu-id="a243a-384">Passeport#</span></span>
- <span data-ttu-id="a243a-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a243a-385">PasseportNon</span></span>
- <span data-ttu-id="a243a-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a243a-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="a243a-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="a243a-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="a243a-388">護照</span><span class="sxs-lookup"><span data-stu-id="a243a-388">passport</span></span>
- <span data-ttu-id="a243a-389">護照詳細資料</span><span class="sxs-lookup"><span data-stu-id="a243a-389">passport details</span></span>
- <span data-ttu-id="a243a-390">immigration 與公民</span><span class="sxs-lookup"><span data-stu-id="a243a-390">immigration and citizenship</span></span>
- <span data-ttu-id="a243a-391">澳大利亞英聯邦</span><span class="sxs-lookup"><span data-stu-id="a243a-391">commonwealth of australia</span></span>
- <span data-ttu-id="a243a-392">immigration 部門</span><span class="sxs-lookup"><span data-stu-id="a243a-392">department of immigration</span></span>
- <span data-ttu-id="a243a-393">住家住址</span><span class="sxs-lookup"><span data-stu-id="a243a-393">residential address</span></span>
- <span data-ttu-id="a243a-394">immigration 和公民的部門</span><span class="sxs-lookup"><span data-stu-id="a243a-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="a243a-395">簽證</span><span class="sxs-lookup"><span data-stu-id="a243a-395">visa</span></span>
- <span data-ttu-id="a243a-396">本國身分識別卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-396">national identity card</span></span>
- <span data-ttu-id="a243a-397">護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-397">passport number</span></span>
- <span data-ttu-id="a243a-398">旅遊檔</span><span class="sxs-lookup"><span data-stu-id="a243a-398">travel document</span></span>
- <span data-ttu-id="a243a-399">頒發機構單位</span><span class="sxs-lookup"><span data-stu-id="a243a-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="a243a-400">澳大利亞稅收檔編號</span><span class="sxs-lookup"><span data-stu-id="a243a-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-401">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-401">Format</span></span>

<span data-ttu-id="a243a-402">8-9 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-403">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-403">Pattern</span></span>

<span data-ttu-id="a243a-404">通常會以空格呈現的8-9 位數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a243a-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="a243a-405">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-405">Three digits</span></span> 
- <span data-ttu-id="a243a-406">選擇性的空格</span><span class="sxs-lookup"><span data-stu-id="a243a-406">An optional space</span></span> 
- <span data-ttu-id="a243a-407">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-407">Three digits</span></span> 
- <span data-ttu-id="a243a-408">選擇性的空格</span><span class="sxs-lookup"><span data-stu-id="a243a-408">An optional space</span></span> 
- <span data-ttu-id="a243a-409">最後一個數位是檢查碼的2-3 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-410">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-410">Checksum</span></span>

<span data-ttu-id="a243a-411">是</span><span class="sxs-lookup"><span data-stu-id="a243a-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-412">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-412">Definition</span></span>

<span data-ttu-id="a243a-413">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-414">函數 Func_australian_tax_file_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-415">找不到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="a243a-416">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="a243a-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="a243a-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="a243a-419">澳大利亞商務電話號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-419">australian business number</span></span>
- <span data-ttu-id="a243a-420">邊際稅率</span><span class="sxs-lookup"><span data-stu-id="a243a-420">marginal tax rate</span></span>
- <span data-ttu-id="a243a-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="a243a-421">medicare levy</span></span>
- <span data-ttu-id="a243a-422">產品群組編號</span><span class="sxs-lookup"><span data-stu-id="a243a-422">portfolio number</span></span>
- <span data-ttu-id="a243a-423">服務 veterans</span><span class="sxs-lookup"><span data-stu-id="a243a-423">service veterans</span></span>
- <span data-ttu-id="a243a-424">預繳稅金</span><span class="sxs-lookup"><span data-stu-id="a243a-424">withholding tax</span></span>
- <span data-ttu-id="a243a-425">個人稅收返還</span><span class="sxs-lookup"><span data-stu-id="a243a-425">individual tax return</span></span>
- <span data-ttu-id="a243a-426">稅收檔案編號</span><span class="sxs-lookup"><span data-stu-id="a243a-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="a243a-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="a243a-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="a243a-428">00000000</span><span class="sxs-lookup"><span data-stu-id="a243a-428">00000000</span></span>
- <span data-ttu-id="a243a-429">11111111</span><span class="sxs-lookup"><span data-stu-id="a243a-429">11111111</span></span>
- <span data-ttu-id="a243a-430">22222222</span><span class="sxs-lookup"><span data-stu-id="a243a-430">22222222</span></span>
- <span data-ttu-id="a243a-431">33333333</span><span class="sxs-lookup"><span data-stu-id="a243a-431">33333333</span></span>
- <span data-ttu-id="a243a-432">44444444</span><span class="sxs-lookup"><span data-stu-id="a243a-432">44444444</span></span>
- <span data-ttu-id="a243a-433">55555555</span><span class="sxs-lookup"><span data-stu-id="a243a-433">55555555</span></span>
- <span data-ttu-id="a243a-434">66666666</span><span class="sxs-lookup"><span data-stu-id="a243a-434">66666666</span></span>
- <span data-ttu-id="a243a-435">77777777</span><span class="sxs-lookup"><span data-stu-id="a243a-435">77777777</span></span>
- <span data-ttu-id="a243a-436">88888888</span><span class="sxs-lookup"><span data-stu-id="a243a-436">88888888</span></span>
- <span data-ttu-id="a243a-437">99999999</span><span class="sxs-lookup"><span data-stu-id="a243a-437">99999999</span></span>
- <span data-ttu-id="a243a-438">000000000</span><span class="sxs-lookup"><span data-stu-id="a243a-438">000000000</span></span>
- <span data-ttu-id="a243a-439">111111111</span><span class="sxs-lookup"><span data-stu-id="a243a-439">111111111</span></span>
- <span data-ttu-id="a243a-440">222222222</span><span class="sxs-lookup"><span data-stu-id="a243a-440">222222222</span></span>
- <span data-ttu-id="a243a-441">333333333</span><span class="sxs-lookup"><span data-stu-id="a243a-441">333333333</span></span>
- <span data-ttu-id="a243a-442">444444444</span><span class="sxs-lookup"><span data-stu-id="a243a-442">444444444</span></span>
- <span data-ttu-id="a243a-443">555555555</span><span class="sxs-lookup"><span data-stu-id="a243a-443">555555555</span></span>
- <span data-ttu-id="a243a-444">666666666</span><span class="sxs-lookup"><span data-stu-id="a243a-444">666666666</span></span>
- <span data-ttu-id="a243a-445">777777777</span><span class="sxs-lookup"><span data-stu-id="a243a-445">777777777</span></span>
- <span data-ttu-id="a243a-446">888888888</span><span class="sxs-lookup"><span data-stu-id="a243a-446">888888888</span></span>
- <span data-ttu-id="a243a-447">999999999</span><span class="sxs-lookup"><span data-stu-id="a243a-447">999999999</span></span>
- <span data-ttu-id="a243a-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="a243a-448">0000000000</span></span>
- <span data-ttu-id="a243a-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="a243a-449">1111111111</span></span>
- <span data-ttu-id="a243a-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="a243a-450">2222222222</span></span>
- <span data-ttu-id="a243a-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="a243a-451">3333333333</span></span>
- <span data-ttu-id="a243a-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="a243a-452">4444444444</span></span>
- <span data-ttu-id="a243a-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="a243a-453">5555555555</span></span>
- <span data-ttu-id="a243a-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="a243a-454">6666666666</span></span>
- <span data-ttu-id="a243a-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="a243a-455">7777777777</span></span>
- <span data-ttu-id="a243a-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="a243a-456">8888888888</span></span>
- <span data-ttu-id="a243a-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="a243a-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="a243a-458">Azure DocumentDB 驗證金鑰</span><span class="sxs-lookup"><span data-stu-id="a243a-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="a243a-459">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-459">Format</span></span>

<span data-ttu-id="a243a-460">字串 "DocumentDb"，後面加上下列模式中所述的字元及字串。</span><span class="sxs-lookup"><span data-stu-id="a243a-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-461">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-461">Pattern</span></span>

- <span data-ttu-id="a243a-462">字串 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="a243a-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="a243a-463">介於3-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="a243a-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a243a-464">大於符號（>）、等號（=）、引號（"）或撇號（'）</span><span class="sxs-lookup"><span data-stu-id="a243a-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="a243a-465">任何86的小寫字母或大寫字母、數位、正斜線（/）或加號（+）組合</span><span class="sxs-lookup"><span data-stu-id="a243a-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a243a-466">兩個等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-467">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-467">Checksum</span></span>

<span data-ttu-id="a243a-468">否</span><span class="sxs-lookup"><span data-stu-id="a243a-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-469">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-469">Definition</span></span>

<span data-ttu-id="a243a-470">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-471">正則運算式 CEP_Regex_AzureDocumentDBAuthKey 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-472">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-473">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a243a-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a243a-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a243a-475">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="a243a-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a243a-476">尚未</span><span class="sxs-lookup"><span data-stu-id="a243a-476">contoso</span></span>
- <span data-ttu-id="a243a-477">送交</span><span class="sxs-lookup"><span data-stu-id="a243a-477">fabrikam</span></span>
- <span data-ttu-id="a243a-478">資料庫</span><span class="sxs-lookup"><span data-stu-id="a243a-478">northwind</span></span>
- <span data-ttu-id="a243a-479">沙 箱</span><span class="sxs-lookup"><span data-stu-id="a243a-479">sandbox</span></span>
- <span data-ttu-id="a243a-480">onebox</span><span class="sxs-lookup"><span data-stu-id="a243a-480">onebox</span></span>
- <span data-ttu-id="a243a-481">本地 主機</span><span class="sxs-lookup"><span data-stu-id="a243a-481">localhost</span></span>
- <span data-ttu-id="a243a-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a243a-482">127.0.0.1</span></span>
- <span data-ttu-id="a243a-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="a243a-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-484">Com</span><span class="sxs-lookup"><span data-stu-id="a243a-484">com</span></span>
- <span data-ttu-id="a243a-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="a243a-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-486">網</span><span class="sxs-lookup"><span data-stu-id="a243a-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="a243a-487">Azure IAAS 資料庫連接字串和 Azure SQL 連接字串</span><span class="sxs-lookup"><span data-stu-id="a243a-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a243a-488">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-488">Format</span></span>

<span data-ttu-id="a243a-489">字串 "Server"、"server" 或 "data source"，後面加上模式中所述的字元及字串（包括字串 "cloudapp"）。</span><span class="sxs-lookup"><span data-stu-id="a243a-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-490">com "或" cloudapp。</span><span class="sxs-lookup"><span data-stu-id="a243a-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-491">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="a243a-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-492">net "，及字串" Password "或" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="a243a-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-493">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-493">Pattern</span></span>

- <span data-ttu-id="a243a-494">字串「伺服器」、「伺服器」或「資料來源」</span><span class="sxs-lookup"><span data-stu-id="a243a-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="a243a-495">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-496">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-496">An equal sign (=)</span></span>
- <span data-ttu-id="a243a-497">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-498">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="a243a-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a243a-499">字串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="a243a-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-500">com "，" cloudapp。</span><span class="sxs-lookup"><span data-stu-id="a243a-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-501">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="a243a-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-502">真實</span><span class="sxs-lookup"><span data-stu-id="a243a-502">net"</span></span>
- <span data-ttu-id="a243a-503">介於1-300 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="a243a-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a243a-504">字串 "Password"、"password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="a243a-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="a243a-505">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-506">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-506">An equal sign (=)</span></span>
- <span data-ttu-id="a243a-507">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-508">一個或多個字元，不是分號（;)、引號（"）或單引號（'）</span><span class="sxs-lookup"><span data-stu-id="a243a-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="a243a-509">分號（;)、引號（"）或撇號（'）</span><span class="sxs-lookup"><span data-stu-id="a243a-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-510">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-510">Checksum</span></span>

<span data-ttu-id="a243a-511">否</span><span class="sxs-lookup"><span data-stu-id="a243a-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-512">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-512">Definition</span></span>

<span data-ttu-id="a243a-513">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-514">正則運算式 CEP_Regex_AzureConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-515">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-516">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a243a-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a243a-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a243a-518">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="a243a-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a243a-519">尚未</span><span class="sxs-lookup"><span data-stu-id="a243a-519">contoso</span></span>
- <span data-ttu-id="a243a-520">送交</span><span class="sxs-lookup"><span data-stu-id="a243a-520">fabrikam</span></span>
- <span data-ttu-id="a243a-521">資料庫</span><span class="sxs-lookup"><span data-stu-id="a243a-521">northwind</span></span>
- <span data-ttu-id="a243a-522">沙 箱</span><span class="sxs-lookup"><span data-stu-id="a243a-522">sandbox</span></span>
- <span data-ttu-id="a243a-523">onebox</span><span class="sxs-lookup"><span data-stu-id="a243a-523">onebox</span></span>
- <span data-ttu-id="a243a-524">本地 主機</span><span class="sxs-lookup"><span data-stu-id="a243a-524">localhost</span></span>
- <span data-ttu-id="a243a-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a243a-525">127.0.0.1</span></span>
- <span data-ttu-id="a243a-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="a243a-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-527">Com</span><span class="sxs-lookup"><span data-stu-id="a243a-527">com</span></span>
- <span data-ttu-id="a243a-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="a243a-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-529">網</span><span class="sxs-lookup"><span data-stu-id="a243a-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="a243a-530">Azure IoT 連接字串</span><span class="sxs-lookup"><span data-stu-id="a243a-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a243a-531">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-531">Format</span></span>

<span data-ttu-id="a243a-532">字串 "HostName"，後面加上下列模式中所述的字元及字串，包括字串 "azure 裝置。</span><span class="sxs-lookup"><span data-stu-id="a243a-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-533">net "和" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="a243a-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-534">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-534">Pattern</span></span>

- <span data-ttu-id="a243a-535">字串 "HostName"</span><span class="sxs-lookup"><span data-stu-id="a243a-535">The string "HostName"</span></span>
- <span data-ttu-id="a243a-536">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-537">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-537">An equal sign (=)</span></span>
- <span data-ttu-id="a243a-538">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-539">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="a243a-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a243a-540">"Azure 裝置" 字串。</span><span class="sxs-lookup"><span data-stu-id="a243a-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-541">真實</span><span class="sxs-lookup"><span data-stu-id="a243a-541">net"</span></span>
- <span data-ttu-id="a243a-542">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="a243a-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a243a-543">字串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="a243a-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="a243a-544">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-545">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-545">An equal sign (=)</span></span>
- <span data-ttu-id="a243a-546">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-547">任何43的小寫字母或大寫字母、數位、正斜線（/）或加號（+）組合</span><span class="sxs-lookup"><span data-stu-id="a243a-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a243a-548">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-549">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-549">Checksum</span></span>

<span data-ttu-id="a243a-550">否</span><span class="sxs-lookup"><span data-stu-id="a243a-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-551">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-551">Definition</span></span>

<span data-ttu-id="a243a-552">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-553">正則運算式 CEP_Regex_AzureIoTConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-554">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-555">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a243a-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a243a-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a243a-557">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="a243a-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a243a-558">尚未</span><span class="sxs-lookup"><span data-stu-id="a243a-558">contoso</span></span>
- <span data-ttu-id="a243a-559">送交</span><span class="sxs-lookup"><span data-stu-id="a243a-559">fabrikam</span></span>
- <span data-ttu-id="a243a-560">資料庫</span><span class="sxs-lookup"><span data-stu-id="a243a-560">northwind</span></span>
- <span data-ttu-id="a243a-561">沙 箱</span><span class="sxs-lookup"><span data-stu-id="a243a-561">sandbox</span></span>
- <span data-ttu-id="a243a-562">onebox</span><span class="sxs-lookup"><span data-stu-id="a243a-562">onebox</span></span>
- <span data-ttu-id="a243a-563">本地 主機</span><span class="sxs-lookup"><span data-stu-id="a243a-563">localhost</span></span>
- <span data-ttu-id="a243a-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a243a-564">127.0.0.1</span></span>
- <span data-ttu-id="a243a-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="a243a-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-566">Com</span><span class="sxs-lookup"><span data-stu-id="a243a-566">com</span></span>
- <span data-ttu-id="a243a-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="a243a-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-568">網</span><span class="sxs-lookup"><span data-stu-id="a243a-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="a243a-569">Azure 發佈設定密碼</span><span class="sxs-lookup"><span data-stu-id="a243a-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="a243a-570">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-570">Format</span></span>

<span data-ttu-id="a243a-571">字串 "userpwd ="，後面加上字母元字串。</span><span class="sxs-lookup"><span data-stu-id="a243a-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-572">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-572">Pattern</span></span>

- <span data-ttu-id="a243a-573">字串 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="a243a-573">The string "userpwd="</span></span>
- <span data-ttu-id="a243a-574">任何60小寫字母或數位的組合</span><span class="sxs-lookup"><span data-stu-id="a243a-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="a243a-575">引號（"）</span><span class="sxs-lookup"><span data-stu-id="a243a-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-576">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-576">Checksum</span></span>

<span data-ttu-id="a243a-577">否</span><span class="sxs-lookup"><span data-stu-id="a243a-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-578">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-578">Definition</span></span>

<span data-ttu-id="a243a-579">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-580">正則運算式 CEP_Regex_AzurePublishSettingPasswords 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-581">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-582">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a243a-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a243a-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a243a-584">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="a243a-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a243a-585">尚未</span><span class="sxs-lookup"><span data-stu-id="a243a-585">contoso</span></span>
- <span data-ttu-id="a243a-586">送交</span><span class="sxs-lookup"><span data-stu-id="a243a-586">fabrikam</span></span>
- <span data-ttu-id="a243a-587">資料庫</span><span class="sxs-lookup"><span data-stu-id="a243a-587">northwind</span></span>
- <span data-ttu-id="a243a-588">沙 箱</span><span class="sxs-lookup"><span data-stu-id="a243a-588">sandbox</span></span>
- <span data-ttu-id="a243a-589">onebox</span><span class="sxs-lookup"><span data-stu-id="a243a-589">onebox</span></span>
- <span data-ttu-id="a243a-590">本地 主機</span><span class="sxs-lookup"><span data-stu-id="a243a-590">localhost</span></span>
- <span data-ttu-id="a243a-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a243a-591">127.0.0.1</span></span>
- <span data-ttu-id="a243a-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="a243a-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-593">Com</span><span class="sxs-lookup"><span data-stu-id="a243a-593">com</span></span>
- <span data-ttu-id="a243a-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="a243a-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-595">網</span><span class="sxs-lookup"><span data-stu-id="a243a-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="a243a-596">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="a243a-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a243a-597">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-597">Format</span></span>

<span data-ttu-id="a243a-598">字串 "redis。</span><span class="sxs-lookup"><span data-stu-id="a243a-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-599">net "後接下列模式中所述的字元和字串，包含字串" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="a243a-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-600">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-600">Pattern</span></span>

- <span data-ttu-id="a243a-601">字串 "redis。</span><span class="sxs-lookup"><span data-stu-id="a243a-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-602">真實</span><span class="sxs-lookup"><span data-stu-id="a243a-602">net"</span></span>
- <span data-ttu-id="a243a-603">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="a243a-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a243a-604">字串 "password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="a243a-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="a243a-605">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-606">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-606">An equal sign (=)</span></span>
- <span data-ttu-id="a243a-607">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-608">43個字元的任何組合，其為小寫或大寫字母、數位、正斜線（/）或加號（+）</span><span class="sxs-lookup"><span data-stu-id="a243a-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a243a-609">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-610">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-610">Checksum</span></span>

<span data-ttu-id="a243a-611">否</span><span class="sxs-lookup"><span data-stu-id="a243a-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-612">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-612">Definition</span></span>

<span data-ttu-id="a243a-613">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-614">正則運算式 CEP_Regex_AzureRedisCacheConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="a243a-615">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-616">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a243a-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a243a-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a243a-618">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="a243a-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a243a-619">尚未</span><span class="sxs-lookup"><span data-stu-id="a243a-619">contoso</span></span>
- <span data-ttu-id="a243a-620">送交</span><span class="sxs-lookup"><span data-stu-id="a243a-620">fabrikam</span></span>
- <span data-ttu-id="a243a-621">資料庫</span><span class="sxs-lookup"><span data-stu-id="a243a-621">northwind</span></span>
- <span data-ttu-id="a243a-622">沙 箱</span><span class="sxs-lookup"><span data-stu-id="a243a-622">sandbox</span></span>
- <span data-ttu-id="a243a-623">onebox</span><span class="sxs-lookup"><span data-stu-id="a243a-623">onebox</span></span>
- <span data-ttu-id="a243a-624">本地 主機</span><span class="sxs-lookup"><span data-stu-id="a243a-624">localhost</span></span>
- <span data-ttu-id="a243a-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a243a-625">127.0.0.1</span></span>
- <span data-ttu-id="a243a-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="a243a-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-627">Com</span><span class="sxs-lookup"><span data-stu-id="a243a-627">com</span></span>
- <span data-ttu-id="a243a-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="a243a-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-629">網</span><span class="sxs-lookup"><span data-stu-id="a243a-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="a243a-630">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="a243a-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="a243a-631">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-631">Format</span></span>

<span data-ttu-id="a243a-632">字串 "sig"，後面加上下列模式中所述的字元及字串。</span><span class="sxs-lookup"><span data-stu-id="a243a-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-633">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-633">Pattern</span></span>

- <span data-ttu-id="a243a-634">字串 "sig"</span><span class="sxs-lookup"><span data-stu-id="a243a-634">The string "sig"</span></span>
- <span data-ttu-id="a243a-635">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-636">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-636">An equal sign (=)</span></span>
- <span data-ttu-id="a243a-637">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-638">介於43-53 個字元、小寫字母、數位或百分比符號（%）之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="a243a-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="a243a-639">字串 "% 三維"</span><span class="sxs-lookup"><span data-stu-id="a243a-639">The string "%3d"</span></span>
- <span data-ttu-id="a243a-640">非小寫或大寫字母、數位或百分號（%）以外的任何字元</span><span class="sxs-lookup"><span data-stu-id="a243a-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-641">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-641">Checksum</span></span>

<span data-ttu-id="a243a-642">否</span><span class="sxs-lookup"><span data-stu-id="a243a-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-643">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-643">Definition</span></span>

<span data-ttu-id="a243a-644">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-645">正則運算式 CEP_Regex_AzureSAS 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="a243a-646">Azure 服務匯流排連接字串</span><span class="sxs-lookup"><span data-stu-id="a243a-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a243a-647">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-647">Format</span></span>

<span data-ttu-id="a243a-648">字串 "EndPoint" 後接下列模式中所述的字元及字串，包含字串 "</span><span class="sxs-lookup"><span data-stu-id="a243a-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-649">net "和" SharedAccesKey "。</span><span class="sxs-lookup"><span data-stu-id="a243a-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-650">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-650">Pattern</span></span>

- <span data-ttu-id="a243a-651">字串 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="a243a-651">The string "EndPoint"</span></span>
- <span data-ttu-id="a243a-652">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-653">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-653">An equal sign (=)</span></span>
- <span data-ttu-id="a243a-654">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-655">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="a243a-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a243a-656">字串 "</span><span class="sxs-lookup"><span data-stu-id="a243a-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-657">真實</span><span class="sxs-lookup"><span data-stu-id="a243a-657">net"</span></span>
- <span data-ttu-id="a243a-658">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="a243a-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a243a-659">字串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="a243a-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="a243a-660">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-661">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-661">An equal sign (=)</span></span>
- <span data-ttu-id="a243a-662">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-663">43個字元的任何組合，其為小寫或大寫字母、數位、正斜線（/）或加號（+）</span><span class="sxs-lookup"><span data-stu-id="a243a-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a243a-664">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-665">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-665">Checksum</span></span>

<span data-ttu-id="a243a-666">否</span><span class="sxs-lookup"><span data-stu-id="a243a-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-667">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-667">Definition</span></span>

<span data-ttu-id="a243a-668">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-669">正則運算式 CEP_Regex_AzureServiceBusConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="a243a-670">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-671">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a243a-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a243a-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a243a-673">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="a243a-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a243a-674">尚未</span><span class="sxs-lookup"><span data-stu-id="a243a-674">contoso</span></span>
- <span data-ttu-id="a243a-675">送交</span><span class="sxs-lookup"><span data-stu-id="a243a-675">fabrikam</span></span>
- <span data-ttu-id="a243a-676">資料庫</span><span class="sxs-lookup"><span data-stu-id="a243a-676">northwind</span></span>
- <span data-ttu-id="a243a-677">沙 箱</span><span class="sxs-lookup"><span data-stu-id="a243a-677">sandbox</span></span>
- <span data-ttu-id="a243a-678">onebox</span><span class="sxs-lookup"><span data-stu-id="a243a-678">onebox</span></span>
- <span data-ttu-id="a243a-679">本地 主機</span><span class="sxs-lookup"><span data-stu-id="a243a-679">localhost</span></span>
- <span data-ttu-id="a243a-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a243a-680">127.0.0.1</span></span>
- <span data-ttu-id="a243a-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="a243a-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-682">Com</span><span class="sxs-lookup"><span data-stu-id="a243a-682">com</span></span>
- <span data-ttu-id="a243a-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="a243a-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-684">網</span><span class="sxs-lookup"><span data-stu-id="a243a-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="a243a-685">Azure 儲存體帳戶金鑰</span><span class="sxs-lookup"><span data-stu-id="a243a-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="a243a-686">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-686">Format</span></span>

<span data-ttu-id="a243a-687">字串 "DefaultEndpointsProtocol"，後面加上下列模式中所述的字元及字串（包括字串 "AccountKey"）。</span><span class="sxs-lookup"><span data-stu-id="a243a-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-688">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-688">Pattern</span></span>

- <span data-ttu-id="a243a-689">字串 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="a243a-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="a243a-690">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-691">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-691">An equal sign (=)</span></span>
- <span data-ttu-id="a243a-692">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-693">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="a243a-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a243a-694">字串 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="a243a-694">The string "AccountKey"</span></span>
- <span data-ttu-id="a243a-695">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-696">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-696">An equal sign (=)</span></span>
- <span data-ttu-id="a243a-697">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="a243a-698">86個字元的任何組合，其為小寫或大寫字母、數位、正斜線（/）或加號（+）</span><span class="sxs-lookup"><span data-stu-id="a243a-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a243a-699">兩個等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-700">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-700">Checksum</span></span>

<span data-ttu-id="a243a-701">否</span><span class="sxs-lookup"><span data-stu-id="a243a-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-702">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-702">Definition</span></span>

<span data-ttu-id="a243a-703">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-704">正則運算式 CEP_Regex_AzureStorageAccountKey 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-705">正則運算式**CEP_AzureEmulatorStorageAccountFilter 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-706">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-707">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="a243a-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="a243a-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="a243a-709">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="a243a-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a243a-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="a243a-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a243a-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a243a-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a243a-712">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="a243a-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a243a-713">尚未</span><span class="sxs-lookup"><span data-stu-id="a243a-713">contoso</span></span>
- <span data-ttu-id="a243a-714">送交</span><span class="sxs-lookup"><span data-stu-id="a243a-714">fabrikam</span></span>
- <span data-ttu-id="a243a-715">資料庫</span><span class="sxs-lookup"><span data-stu-id="a243a-715">northwind</span></span>
- <span data-ttu-id="a243a-716">沙 箱</span><span class="sxs-lookup"><span data-stu-id="a243a-716">sandbox</span></span>
- <span data-ttu-id="a243a-717">onebox</span><span class="sxs-lookup"><span data-stu-id="a243a-717">onebox</span></span>
- <span data-ttu-id="a243a-718">本地 主機</span><span class="sxs-lookup"><span data-stu-id="a243a-718">localhost</span></span>
- <span data-ttu-id="a243a-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a243a-719">127.0.0.1</span></span>
- <span data-ttu-id="a243a-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="a243a-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-721">Com</span><span class="sxs-lookup"><span data-stu-id="a243a-721">com</span></span>
- <span data-ttu-id="a243a-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="a243a-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-723">網</span><span class="sxs-lookup"><span data-stu-id="a243a-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="a243a-724">Azure 儲存體帳戶金鑰（一般）</span><span class="sxs-lookup"><span data-stu-id="a243a-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-725">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-725">Format</span></span>

<span data-ttu-id="a243a-726">任何86的小寫字母或大寫字母、數位、正斜線（/）或加號（+）的組合，前置或後接下列模式中所述的字元。</span><span class="sxs-lookup"><span data-stu-id="a243a-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-727">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-727">Pattern</span></span>

- <span data-ttu-id="a243a-728">大於符號（>）、撇號（'）、等號（=）、引號（"）或數位記號（#）的0-1</span><span class="sxs-lookup"><span data-stu-id="a243a-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="a243a-729">86個字元的任何組合（低或大寫字母、數位、正斜線（/）或加號（+））</span><span class="sxs-lookup"><span data-stu-id="a243a-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="a243a-730">兩個等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="a243a-731">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-731">Checksum</span></span>

<span data-ttu-id="a243a-732">否</span><span class="sxs-lookup"><span data-stu-id="a243a-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-733">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-733">Definition</span></span>

<span data-ttu-id="a243a-734">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-735">正則運算式 CEP_Regex_AzureStorageAccountKeyGeneric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="a243a-736">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="a243a-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-737">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-737">Format</span></span>

<span data-ttu-id="a243a-738">11位數加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="a243a-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-739">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-739">Pattern</span></span>

<span data-ttu-id="a243a-740">11位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="a243a-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="a243a-741">以 YY 格式表示的六位數和兩個句點。毫米。出生日期的 DD</span><span class="sxs-lookup"><span data-stu-id="a243a-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="a243a-742">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-742">A hyphen</span></span> 
- <span data-ttu-id="a243a-743">三個連續數位（奇數用於男生，即便是女生）</span><span class="sxs-lookup"><span data-stu-id="a243a-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="a243a-744">一個句點</span><span class="sxs-lookup"><span data-stu-id="a243a-744">A period</span></span> 
- <span data-ttu-id="a243a-745">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-746">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-746">Checksum</span></span>

<span data-ttu-id="a243a-747">是</span><span class="sxs-lookup"><span data-stu-id="a243a-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-748">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-748">Definition</span></span>

<span data-ttu-id="a243a-749">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-750">函數 Func_belgium_national_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-751">會找到來自 Keyword_belgium_national_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="a243a-752">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-753">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="a243a-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="a243a-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="a243a-755">身分識別</span><span class="sxs-lookup"><span data-stu-id="a243a-755">Identity</span></span>
- <span data-ttu-id="a243a-756">註冊</span><span class="sxs-lookup"><span data-stu-id="a243a-756">Registration</span></span>
- <span data-ttu-id="a243a-757">識別</span><span class="sxs-lookup"><span data-stu-id="a243a-757">Identification</span></span> 
- <span data-ttu-id="a243a-758">ID</span><span class="sxs-lookup"><span data-stu-id="a243a-758">ID</span></span> 
- <span data-ttu-id="a243a-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="a243a-759">Identiteitskaart</span></span>
- <span data-ttu-id="a243a-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="a243a-760">Registratie nummer</span></span> 
- <span data-ttu-id="a243a-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="a243a-761">Identificatie nummer</span></span> 
- <span data-ttu-id="a243a-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="a243a-762">Identiteit</span></span>
- <span data-ttu-id="a243a-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="a243a-763">Registratie</span></span>
- <span data-ttu-id="a243a-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="a243a-764">Identificatie</span></span> 
- <span data-ttu-id="a243a-765">購買 d'identité</span><span class="sxs-lookup"><span data-stu-id="a243a-765">Carte d'identité</span></span> 
- <span data-ttu-id="a243a-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="a243a-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="a243a-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="a243a-767">numéro d'identification</span></span>
- <span data-ttu-id="a243a-768">identité</span><span class="sxs-lookup"><span data-stu-id="a243a-768">identité</span></span> 
- <span data-ttu-id="a243a-769">題詞</span><span class="sxs-lookup"><span data-stu-id="a243a-769">inscription</span></span> 
- <span data-ttu-id="a243a-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="a243a-770">Identifikation</span></span>
- <span data-ttu-id="a243a-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="a243a-771">Identifizierung</span></span>
- <span data-ttu-id="a243a-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-772">Identifikationsnummer</span></span>
- <span data-ttu-id="a243a-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="a243a-773">Personalausweis</span></span>
- <span data-ttu-id="a243a-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="a243a-774">Registrierung</span></span>
- <span data-ttu-id="a243a-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="a243a-776">巴西 CPF 號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-777">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-777">Format</span></span>

<span data-ttu-id="a243a-778">11位數包含檢查碼，可格式化或未格式化</span><span class="sxs-lookup"><span data-stu-id="a243a-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-779">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-779">Pattern</span></span>

<span data-ttu-id="a243a-780">格式 化：</span><span class="sxs-lookup"><span data-stu-id="a243a-780">Formatted:</span></span>
- <span data-ttu-id="a243a-781">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-781">Three digits</span></span> 
- <span data-ttu-id="a243a-782">一個句點</span><span class="sxs-lookup"><span data-stu-id="a243a-782">A period</span></span> 
- <span data-ttu-id="a243a-783">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-783">Three digits</span></span> 
- <span data-ttu-id="a243a-784">一個句點</span><span class="sxs-lookup"><span data-stu-id="a243a-784">A period</span></span> 
- <span data-ttu-id="a243a-785">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-785">Three digits</span></span> 
- <span data-ttu-id="a243a-786">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-786">A hyphen</span></span> 
- <span data-ttu-id="a243a-787">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-787">Two digits which are check digits</span></span>

<span data-ttu-id="a243a-788">非</span><span class="sxs-lookup"><span data-stu-id="a243a-788">Unformatted:</span></span>
- <span data-ttu-id="a243a-789">11位數的最後兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-790">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-790">Checksum</span></span>

<span data-ttu-id="a243a-791">是</span><span class="sxs-lookup"><span data-stu-id="a243a-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-792">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-792">Definition</span></span>

<span data-ttu-id="a243a-793">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-794">函數 Func_brazil_cpf 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-795">會找到來自 Keyword_brazil_cpf 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="a243a-796">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-796">The checksum passes.</span></span>

<span data-ttu-id="a243a-797">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-798">函數 Func_brazil_cpf 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-799">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-799">The checksum passes.</span></span>

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-800">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="a243a-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="a243a-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="a243a-802">公積金</span><span class="sxs-lookup"><span data-stu-id="a243a-802">CPF</span></span>
- <span data-ttu-id="a243a-803">識別</span><span class="sxs-lookup"><span data-stu-id="a243a-803">Identification</span></span>
- <span data-ttu-id="a243a-804">註冊</span><span class="sxs-lookup"><span data-stu-id="a243a-804">Registration</span></span>
- <span data-ttu-id="a243a-805">收入</span><span class="sxs-lookup"><span data-stu-id="a243a-805">Revenue</span></span>
- <span data-ttu-id="a243a-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="a243a-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="a243a-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="a243a-807">Imposto</span></span> 
- <span data-ttu-id="a243a-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="a243a-808">Identificação</span></span> 
- <span data-ttu-id="a243a-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="a243a-809">Inscrição</span></span> 
- <span data-ttu-id="a243a-810">Receita</span><span class="sxs-lookup"><span data-stu-id="a243a-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="a243a-811">巴西法律實體編號（CNPJ）</span><span class="sxs-lookup"><span data-stu-id="a243a-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-812">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-812">Format</span></span>

<span data-ttu-id="a243a-813">14位數包含登記編號、分支編號及檢查數位，加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="a243a-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-814">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-814">Pattern</span></span>
<span data-ttu-id="a243a-815">14位數，加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="a243a-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="a243a-816">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-816">Two digits</span></span> 
- <span data-ttu-id="a243a-817">一個句點</span><span class="sxs-lookup"><span data-stu-id="a243a-817">A period</span></span> 
- <span data-ttu-id="a243a-818">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-818">Three digits</span></span> 
- <span data-ttu-id="a243a-819">一個句點</span><span class="sxs-lookup"><span data-stu-id="a243a-819">A period</span></span> 
- <span data-ttu-id="a243a-820">三位數（前八位數為註冊碼）</span><span class="sxs-lookup"><span data-stu-id="a243a-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="a243a-821">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="a243a-821">A forward slash</span></span> 
- <span data-ttu-id="a243a-822">四位數的分支編號</span><span class="sxs-lookup"><span data-stu-id="a243a-822">Four-digit branch number</span></span> 
- <span data-ttu-id="a243a-823">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-823">A hyphen</span></span> 
- <span data-ttu-id="a243a-824">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-825">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-825">Checksum</span></span>

<span data-ttu-id="a243a-826">是</span><span class="sxs-lookup"><span data-stu-id="a243a-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-827">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-827">Definition</span></span>

<span data-ttu-id="a243a-828">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-829">函數 Func_brazil_cnpj 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-830">會找到來自 Keyword_brazil_cnpj 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="a243a-831">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-831">The checksum passes.</span></span>

<span data-ttu-id="a243a-832">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-833">函數 Func_brazil_cnpj 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-834">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-834">The checksum passes.</span></span>

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-835">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="a243a-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="a243a-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="a243a-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="a243a-837">CNPJ</span></span> 
- <span data-ttu-id="a243a-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="a243a-838">CNPJ/MF</span></span> 
- <span data-ttu-id="a243a-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="a243a-839">CNPJ-MF</span></span> 
- <span data-ttu-id="a243a-840">法律實體的本國登錄</span><span class="sxs-lookup"><span data-stu-id="a243a-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="a243a-841">Taxpayers 登錄</span><span class="sxs-lookup"><span data-stu-id="a243a-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="a243a-842">法律實體</span><span class="sxs-lookup"><span data-stu-id="a243a-842">Legal entity</span></span> 
- <span data-ttu-id="a243a-843">法律實體</span><span class="sxs-lookup"><span data-stu-id="a243a-843">Legal entities</span></span> 
- <span data-ttu-id="a243a-844">註冊狀態</span><span class="sxs-lookup"><span data-stu-id="a243a-844">Registration Status</span></span> 
- <span data-ttu-id="a243a-845">商務版</span><span class="sxs-lookup"><span data-stu-id="a243a-845">Business</span></span> 
- <span data-ttu-id="a243a-846">Company</span><span class="sxs-lookup"><span data-stu-id="a243a-846">Company</span></span>
- <span data-ttu-id="a243a-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="a243a-847">CNPJ</span></span> 
- <span data-ttu-id="a243a-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="a243a-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="a243a-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="a243a-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="a243a-850">CGC</span><span class="sxs-lookup"><span data-stu-id="a243a-850">CGC</span></span> 
- <span data-ttu-id="a243a-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="a243a-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="a243a-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="a243a-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="a243a-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="a243a-853">Situação cadastral</span></span> 
- <span data-ttu-id="a243a-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="a243a-854">Inscrição</span></span> 
- <span data-ttu-id="a243a-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="a243a-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="a243a-856">巴西國身分識別卡（RG）</span><span class="sxs-lookup"><span data-stu-id="a243a-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-857">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-857">Format</span></span>

<span data-ttu-id="a243a-858">Registro Geral （舊格式）：九位數</span><span class="sxs-lookup"><span data-stu-id="a243a-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="a243a-859">Registro de Identidade （RIC）（新格式）：11位數</span><span class="sxs-lookup"><span data-stu-id="a243a-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-860">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-860">Pattern</span></span>

<span data-ttu-id="a243a-861">Registro Geral （舊格式）：</span><span class="sxs-lookup"><span data-stu-id="a243a-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="a243a-862">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-862">Two digits</span></span> 
- <span data-ttu-id="a243a-863">一個句點</span><span class="sxs-lookup"><span data-stu-id="a243a-863">A period</span></span> 
- <span data-ttu-id="a243a-864">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-864">Three digits</span></span> 
- <span data-ttu-id="a243a-865">一個句點</span><span class="sxs-lookup"><span data-stu-id="a243a-865">A period</span></span> 
- <span data-ttu-id="a243a-866">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-866">Three digits</span></span> 
- <span data-ttu-id="a243a-867">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-867">A hyphen</span></span> 
- <span data-ttu-id="a243a-868">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-868">One digit which is a check digit</span></span>

<span data-ttu-id="a243a-869">Registro de Identidade （RIC）（新格式）：</span><span class="sxs-lookup"><span data-stu-id="a243a-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="a243a-870">10位數</span><span class="sxs-lookup"><span data-stu-id="a243a-870">10 digits</span></span> 
- <span data-ttu-id="a243a-871">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-871">A hyphen</span></span> 
- <span data-ttu-id="a243a-872">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-873">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-873">Checksum</span></span>

<span data-ttu-id="a243a-874">是</span><span class="sxs-lookup"><span data-stu-id="a243a-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-875">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-875">Definition</span></span>

<span data-ttu-id="a243a-876">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-877">函數 Func_brazil_rg 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-878">會找到來自 Keyword_brazil_rg 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="a243a-879">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-879">The checksum passes.</span></span>

<span data-ttu-id="a243a-880">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-881">函數 Func_brazil_rg 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-882">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-882">The checksum passes.</span></span>

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-883">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="a243a-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="a243a-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="a243a-885">Cédula de identidade identity 持卡國 id número de rregistro registro de Iidentidade registro geral RG （此關鍵字區分大小寫） RIC （此關鍵字區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="a243a-886">加拿大銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-887">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-887">Format</span></span>

<span data-ttu-id="a243a-888">七位數或十二位數</span><span class="sxs-lookup"><span data-stu-id="a243a-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-889">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-889">Pattern</span></span>

<span data-ttu-id="a243a-890">加拿大銀行帳戶號碼為七位數或十二位數。</span><span class="sxs-lookup"><span data-stu-id="a243a-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="a243a-891">加拿大銀行帳戶中轉號碼為：</span><span class="sxs-lookup"><span data-stu-id="a243a-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="a243a-892">五位數</span><span class="sxs-lookup"><span data-stu-id="a243a-892">Five digits</span></span> 
- <span data-ttu-id="a243a-893">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-893">A hyphen</span></span> 
- <span data-ttu-id="a243a-894">三位數或</span><span class="sxs-lookup"><span data-stu-id="a243a-894">Three digits OR</span></span>
- <span data-ttu-id="a243a-895">零 "0"</span><span class="sxs-lookup"><span data-stu-id="a243a-895">A zero "0"</span></span> 
- <span data-ttu-id="a243a-896">八位數</span><span class="sxs-lookup"><span data-stu-id="a243a-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-897">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-897">Checksum</span></span>

<span data-ttu-id="a243a-898">否</span><span class="sxs-lookup"><span data-stu-id="a243a-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-899">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-899">Definition</span></span>

<span data-ttu-id="a243a-900">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-901">正則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-902">會找到來自 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="a243a-903">正則運算式 Regex_canada_bank_account_transit_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="a243a-904">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-905">正則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-906">會找到來自 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-907">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="a243a-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a243a-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="a243a-909">加拿大節約 bonds</span><span class="sxs-lookup"><span data-stu-id="a243a-909">canada savings bonds</span></span>
- <span data-ttu-id="a243a-910">加拿大收入代理商</span><span class="sxs-lookup"><span data-stu-id="a243a-910">canada revenue agency</span></span>
- <span data-ttu-id="a243a-911">加拿大金融機構</span><span class="sxs-lookup"><span data-stu-id="a243a-911">canadian financial institution</span></span>
- <span data-ttu-id="a243a-912">直接存放表單</span><span class="sxs-lookup"><span data-stu-id="a243a-912">direct deposit form</span></span>
- <span data-ttu-id="a243a-913">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="a243a-913">canadian citizen</span></span>
- <span data-ttu-id="a243a-914">法律代表</span><span class="sxs-lookup"><span data-stu-id="a243a-914">legal representative</span></span>
- <span data-ttu-id="a243a-915">公證</span><span class="sxs-lookup"><span data-stu-id="a243a-915">notary public</span></span>
- <span data-ttu-id="a243a-916">oaths 的英國專員辦公室</span><span class="sxs-lookup"><span data-stu-id="a243a-916">commissioner for oaths</span></span>
- <span data-ttu-id="a243a-917">兒童護理權益</span><span class="sxs-lookup"><span data-stu-id="a243a-917">child care benefit</span></span>
- <span data-ttu-id="a243a-918">通用子級護理</span><span class="sxs-lookup"><span data-stu-id="a243a-918">universal child care</span></span>
- <span data-ttu-id="a243a-919">加拿大子稅務權益</span><span class="sxs-lookup"><span data-stu-id="a243a-919">canada child tax benefit</span></span>
- <span data-ttu-id="a243a-920">所得稅權益</span><span class="sxs-lookup"><span data-stu-id="a243a-920">income tax benefit</span></span>
- <span data-ttu-id="a243a-921">已調和銷售稅</span><span class="sxs-lookup"><span data-stu-id="a243a-921">harmonized sales tax</span></span>
- <span data-ttu-id="a243a-922">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-922">social insurance number</span></span>
- <span data-ttu-id="a243a-923">所得稅退款</span><span class="sxs-lookup"><span data-stu-id="a243a-923">income tax refund</span></span>
- <span data-ttu-id="a243a-924">子稅務權益</span><span class="sxs-lookup"><span data-stu-id="a243a-924">child tax benefit</span></span>
- <span data-ttu-id="a243a-925">territorial 付款</span><span class="sxs-lookup"><span data-stu-id="a243a-925">territorial payments</span></span>
- <span data-ttu-id="a243a-926">機構號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-926">institution number</span></span>
- <span data-ttu-id="a243a-927">放入要求</span><span class="sxs-lookup"><span data-stu-id="a243a-927">deposit request</span></span>
- <span data-ttu-id="a243a-928">銀行資訊</span><span class="sxs-lookup"><span data-stu-id="a243a-928">banking information</span></span>
- <span data-ttu-id="a243a-929">直接存款</span><span class="sxs-lookup"><span data-stu-id="a243a-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="a243a-930">加拿大駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-931">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-931">Format</span></span>

<span data-ttu-id="a243a-932">依省份</span><span class="sxs-lookup"><span data-stu-id="a243a-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-933">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-933">Pattern</span></span>

<span data-ttu-id="a243a-934">涵蓋 Alberta、英屬哥倫比亞、Manitoba、新的 Brunswick、Newfoundland/Labrador、Nova Scotia、安大略、Prince Edward 孤島、魁北克和薩斯的各種模式</span><span class="sxs-lookup"><span data-stu-id="a243a-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-935">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-935">Checksum</span></span>

<span data-ttu-id="a243a-936">否</span><span class="sxs-lookup"><span data-stu-id="a243a-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-937">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-937">Definition</span></span>

<span data-ttu-id="a243a-938">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-939">函數 Func_ [province_name] _drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-940">找到來自 Keyword_ [province_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a243a-941">會找到來自 Keyword_canada_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-942">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="a243a-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="a243a-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="a243a-944">省/直轄市縮寫，例如 AB</span><span class="sxs-lookup"><span data-stu-id="a243a-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="a243a-945">省/市名稱，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="a243a-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="a243a-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a243a-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="a243a-947">Dl</span><span class="sxs-lookup"><span data-stu-id="a243a-947">DL</span></span>
- <span data-ttu-id="a243a-948">Dls</span><span class="sxs-lookup"><span data-stu-id="a243a-948">DLS</span></span>
- <span data-ttu-id="a243a-949">民盟</span><span class="sxs-lookup"><span data-stu-id="a243a-949">CDL</span></span>
- <span data-ttu-id="a243a-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="a243a-950">CDLS</span></span>
- <span data-ttu-id="a243a-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="a243a-951">DriverLic</span></span>
- <span data-ttu-id="a243a-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="a243a-952">DriverLics</span></span>
- <span data-ttu-id="a243a-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a243a-953">DriverLicense</span></span>
- <span data-ttu-id="a243a-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a243a-954">DriverLicenses</span></span>
- <span data-ttu-id="a243a-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="a243a-955">DriverLicence</span></span>
- <span data-ttu-id="a243a-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="a243a-956">DriverLicences</span></span>
- <span data-ttu-id="a243a-957">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-957">Driver Lic</span></span>
- <span data-ttu-id="a243a-958">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-958">Driver Lics</span></span>
- <span data-ttu-id="a243a-959">駕照</span><span class="sxs-lookup"><span data-stu-id="a243a-959">Driver License</span></span>
- <span data-ttu-id="a243a-960">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-960">Driver Licenses</span></span>
- <span data-ttu-id="a243a-961">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-961">Driver Licence</span></span>
- <span data-ttu-id="a243a-962">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-962">Driver Licences</span></span>
- <span data-ttu-id="a243a-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a243a-963">DriversLic</span></span>
- <span data-ttu-id="a243a-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="a243a-964">DriversLics</span></span>
- <span data-ttu-id="a243a-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="a243a-965">DriversLicence</span></span>
- <span data-ttu-id="a243a-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="a243a-966">DriversLicences</span></span>
- <span data-ttu-id="a243a-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="a243a-967">DriversLicense</span></span>
- <span data-ttu-id="a243a-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a243a-968">DriversLicenses</span></span>
- <span data-ttu-id="a243a-969">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-969">Drivers Lic</span></span>
- <span data-ttu-id="a243a-970">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-970">Drivers Lics</span></span>
- <span data-ttu-id="a243a-971">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-971">Drivers License</span></span>
- <span data-ttu-id="a243a-972">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-972">Drivers Licenses</span></span>
- <span data-ttu-id="a243a-973">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-973">Drivers Licence</span></span>
- <span data-ttu-id="a243a-974">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-974">Drivers Licences</span></span>
- <span data-ttu-id="a243a-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-975">Driver'Lic</span></span>
- <span data-ttu-id="a243a-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-976">Driver'Lics</span></span>
- <span data-ttu-id="a243a-977">Driver'License</span><span class="sxs-lookup"><span data-stu-id="a243a-977">Driver'License</span></span>
- <span data-ttu-id="a243a-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="a243a-978">Driver'Licenses</span></span>
- <span data-ttu-id="a243a-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="a243a-979">Driver'Licence</span></span>
- <span data-ttu-id="a243a-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="a243a-980">Driver'Licences</span></span>
- <span data-ttu-id="a243a-981">驅動程式「.Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-981">Driver' Lic</span></span>
- <span data-ttu-id="a243a-982">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-982">Driver' Lics</span></span>
- <span data-ttu-id="a243a-983">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-983">Driver' License</span></span>
- <span data-ttu-id="a243a-984">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="a243a-984">Driver' Licenses</span></span>
- <span data-ttu-id="a243a-985">驅動程式 ' 許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-985">Driver' Licence</span></span>
- <span data-ttu-id="a243a-986">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="a243a-986">Driver' Licences</span></span>
- <span data-ttu-id="a243a-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a243a-987">Driver'sLic</span></span>
- <span data-ttu-id="a243a-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a243a-988">Driver'sLics</span></span>
- <span data-ttu-id="a243a-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a243a-989">Driver'sLicense</span></span>
- <span data-ttu-id="a243a-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a243a-990">Driver'sLicenses</span></span>
- <span data-ttu-id="a243a-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="a243a-991">Driver'sLicence</span></span>
- <span data-ttu-id="a243a-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="a243a-992">Driver'sLicences</span></span>
- <span data-ttu-id="a243a-993">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-993">Driver's Lic</span></span>
- <span data-ttu-id="a243a-994">驅動程式的 Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-994">Driver's Lics</span></span>
- <span data-ttu-id="a243a-995">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-995">Driver's License</span></span>
- <span data-ttu-id="a243a-996">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-996">Driver's Licenses</span></span>
- <span data-ttu-id="a243a-997">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-997">Driver's Licence</span></span>
- <span data-ttu-id="a243a-998">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-998">Driver's Licences</span></span>
- <span data-ttu-id="a243a-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="a243a-999">Permis de Conduire</span></span>
- <span data-ttu-id="a243a-1000">id</span><span class="sxs-lookup"><span data-stu-id="a243a-1000">id</span></span>
- <span data-ttu-id="a243a-1001">Id</span><span class="sxs-lookup"><span data-stu-id="a243a-1001">ids</span></span>
- <span data-ttu-id="a243a-1002">idcard 編號</span><span class="sxs-lookup"><span data-stu-id="a243a-1002">idcard number</span></span>
- <span data-ttu-id="a243a-1003">idcard 編號</span><span class="sxs-lookup"><span data-stu-id="a243a-1003">idcard numbers</span></span>
- <span data-ttu-id="a243a-1004">idcard#</span><span class="sxs-lookup"><span data-stu-id="a243a-1004">idcard #</span></span>
- <span data-ttu-id="a243a-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="a243a-1005">idcard #s</span></span>
- <span data-ttu-id="a243a-1006">idcard 卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-1006">idcard card</span></span>
- <span data-ttu-id="a243a-1007">idcard 卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-1007">idcard cards</span></span>
- <span data-ttu-id="a243a-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="a243a-1008">idcard</span></span>
- <span data-ttu-id="a243a-1009">識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1009">identification number</span></span>
- <span data-ttu-id="a243a-1010">識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1010">identification numbers</span></span>
- <span data-ttu-id="a243a-1011">識別#</span><span class="sxs-lookup"><span data-stu-id="a243a-1011">identification #</span></span>
- <span data-ttu-id="a243a-1012">識別 #s</span><span class="sxs-lookup"><span data-stu-id="a243a-1012">identification #s</span></span>
- <span data-ttu-id="a243a-1013">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1013">identification card</span></span>
- <span data-ttu-id="a243a-1014">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-1014">identification cards</span></span>
- <span data-ttu-id="a243a-1015">識別</span><span class="sxs-lookup"><span data-stu-id="a243a-1015">identification</span></span> 
- <span data-ttu-id="a243a-1016">Dl#</span><span class="sxs-lookup"><span data-stu-id="a243a-1016">DL#</span></span>
- <span data-ttu-id="a243a-1017">Dls#</span><span class="sxs-lookup"><span data-stu-id="a243a-1017">DLS#</span></span> 
- <span data-ttu-id="a243a-1018">民盟#</span><span class="sxs-lookup"><span data-stu-id="a243a-1018">CDL#</span></span> 
- <span data-ttu-id="a243a-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="a243a-1019">CDLS#</span></span> 
- <span data-ttu-id="a243a-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="a243a-1020">DriverLic#</span></span> 
- <span data-ttu-id="a243a-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="a243a-1021">DriverLics#</span></span> 
- <span data-ttu-id="a243a-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="a243a-1022">DriverLicense#</span></span> 
- <span data-ttu-id="a243a-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="a243a-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="a243a-1024">DriverLicence#</span></span> 
- <span data-ttu-id="a243a-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="a243a-1025">DriverLicences#</span></span> 
- <span data-ttu-id="a243a-1026">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="a243a-1026">Driver Lic#</span></span>
- <span data-ttu-id="a243a-1027">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-1027">Driver Lics#</span></span> 
- <span data-ttu-id="a243a-1028">駕照#</span><span class="sxs-lookup"><span data-stu-id="a243a-1028">Driver License#</span></span> 
- <span data-ttu-id="a243a-1029">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="a243a-1030">駕照#</span><span class="sxs-lookup"><span data-stu-id="a243a-1030">Driver License#</span></span> 
- <span data-ttu-id="a243a-1031">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-1031">Driver Licences#</span></span> 
- <span data-ttu-id="a243a-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="a243a-1032">DriversLic#</span></span> 
- <span data-ttu-id="a243a-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="a243a-1033">DriversLics#</span></span> 
- <span data-ttu-id="a243a-1034">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="a243a-1034">DriversLicense#</span></span> 
- <span data-ttu-id="a243a-1035">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="a243a-1036">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="a243a-1036">DriversLicence#</span></span> 
- <span data-ttu-id="a243a-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="a243a-1037">DriversLicences#</span></span> 
- <span data-ttu-id="a243a-1038">驅動程式 .Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="a243a-1039">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="a243a-1040">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-1040">Drivers License#</span></span> 
- <span data-ttu-id="a243a-1041">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="a243a-1042">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="a243a-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="a243a-1043">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="a243a-1044">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="a243a-1045">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="a243a-1046">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="a243a-1046">Driver'License#</span></span> 
- <span data-ttu-id="a243a-1047">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="a243a-1048">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="a243a-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="a243a-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="a243a-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="a243a-1050">驅動程式「.Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="a243a-1051">驅動程式 ' Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="a243a-1052">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-1052">Driver' License#</span></span> 
- <span data-ttu-id="a243a-1053">驅動程式的授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="a243a-1054">驅動程式 ' 許可證#</span><span class="sxs-lookup"><span data-stu-id="a243a-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="a243a-1055">驅動程式 ' 授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="a243a-1056">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="a243a-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="a243a-1057">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="a243a-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="a243a-1058">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="a243a-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="a243a-1059">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="a243a-1060">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="a243a-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="a243a-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="a243a-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="a243a-1062">驅動程式的 .Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="a243a-1063">驅動程式的 Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="a243a-1064">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-1064">Driver's License#</span></span> 
- <span data-ttu-id="a243a-1065">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="a243a-1066">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="a243a-1067">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="a243a-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="a243a-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="a243a-1069">Id#</span><span class="sxs-lookup"><span data-stu-id="a243a-1069">id#</span></span> 
- <span data-ttu-id="a243a-1070">Id#</span><span class="sxs-lookup"><span data-stu-id="a243a-1070">ids#</span></span> 
- <span data-ttu-id="a243a-1071">idcard 卡片#</span><span class="sxs-lookup"><span data-stu-id="a243a-1071">idcard card#</span></span> 
- <span data-ttu-id="a243a-1072">idcard 卡片#</span><span class="sxs-lookup"><span data-stu-id="a243a-1072">idcard cards#</span></span> 
- <span data-ttu-id="a243a-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="a243a-1073">idcard#</span></span> 
- <span data-ttu-id="a243a-1074">身分識別卡#</span><span class="sxs-lookup"><span data-stu-id="a243a-1074">identification card#</span></span> 
- <span data-ttu-id="a243a-1075">身份證#</span><span class="sxs-lookup"><span data-stu-id="a243a-1075">identification cards#</span></span> 
- <span data-ttu-id="a243a-1076">識別#</span><span class="sxs-lookup"><span data-stu-id="a243a-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="a243a-1077">加拿大健康情況服務號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1078">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1078">Format</span></span>

<span data-ttu-id="a243a-1079">10位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1080">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1080">Pattern</span></span>

<span data-ttu-id="a243a-1081">10位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1082">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1082">Checksum</span></span>

<span data-ttu-id="a243a-1083">否</span><span class="sxs-lookup"><span data-stu-id="a243a-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1084">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1084">Definition</span></span>

<span data-ttu-id="a243a-1085">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1086">正則運算式 Regex_canada_health_service_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1087">會找到來自 Keyword_canada_health_service_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1088">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="a243a-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="a243a-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="a243a-1090">個人健康號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1090">personal health number</span></span>
- <span data-ttu-id="a243a-1091">患者資訊</span><span class="sxs-lookup"><span data-stu-id="a243a-1091">patient information</span></span>
- <span data-ttu-id="a243a-1092">健康情況服務</span><span class="sxs-lookup"><span data-stu-id="a243a-1092">health services</span></span>
- <span data-ttu-id="a243a-1093">speciality 服務</span><span class="sxs-lookup"><span data-stu-id="a243a-1093">speciality services</span></span>
- <span data-ttu-id="a243a-1094">汽車意外</span><span class="sxs-lookup"><span data-stu-id="a243a-1094">automobile accident</span></span>
- <span data-ttu-id="a243a-1095">病人醫院</span><span class="sxs-lookup"><span data-stu-id="a243a-1095">patient hospital</span></span>
- <span data-ttu-id="a243a-1096">心理醫生</span><span class="sxs-lookup"><span data-stu-id="a243a-1096">psychiatrist</span></span>
- <span data-ttu-id="a243a-1097">工作人員薪酬</span><span class="sxs-lookup"><span data-stu-id="a243a-1097">workers compensation</span></span>
- <span data-ttu-id="a243a-1098">殘疾</span><span class="sxs-lookup"><span data-stu-id="a243a-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="a243a-1099">加拿大護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1100">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1100">Format</span></span>

<span data-ttu-id="a243a-1101">兩個大寫字母後接六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1102">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1102">Pattern</span></span>

<span data-ttu-id="a243a-1103">兩個大寫字母後接六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1104">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1104">Checksum</span></span>

<span data-ttu-id="a243a-1105">否</span><span class="sxs-lookup"><span data-stu-id="a243a-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1106">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1106">Definition</span></span>

<span data-ttu-id="a243a-1107">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1108">正則運算式 Regex_canada_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1109">會找到 Keyword_canada_passport_number 或 Keyword_passport 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1110">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="a243a-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="a243a-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="a243a-1112">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="a243a-1112">canadian citizenship</span></span>
- <span data-ttu-id="a243a-1113">加拿大護照</span><span class="sxs-lookup"><span data-stu-id="a243a-1113">canadian passport</span></span>
- <span data-ttu-id="a243a-1114">護照應用程式</span><span class="sxs-lookup"><span data-stu-id="a243a-1114">passport application</span></span>
- <span data-ttu-id="a243a-1115">護照相片</span><span class="sxs-lookup"><span data-stu-id="a243a-1115">passport photos</span></span>
- <span data-ttu-id="a243a-1116">認證的翻譯員</span><span class="sxs-lookup"><span data-stu-id="a243a-1116">certified translator</span></span>
- <span data-ttu-id="a243a-1117">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="a243a-1117">canadian citizens</span></span>
- <span data-ttu-id="a243a-1118">處理時間</span><span class="sxs-lookup"><span data-stu-id="a243a-1118">processing times</span></span>
- <span data-ttu-id="a243a-1119">更新應用程式</span><span class="sxs-lookup"><span data-stu-id="a243a-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a243a-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a243a-1120">Keyword_passport</span></span>

- <span data-ttu-id="a243a-1121">護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1121">Passport Number</span></span>
- <span data-ttu-id="a243a-1122">護照否</span><span class="sxs-lookup"><span data-stu-id="a243a-1122">Passport No</span></span>
- <span data-ttu-id="a243a-1123">護照#</span><span class="sxs-lookup"><span data-stu-id="a243a-1123">Passport #</span></span>
- <span data-ttu-id="a243a-1124">護照#</span><span class="sxs-lookup"><span data-stu-id="a243a-1124">Passport#</span></span>
- <span data-ttu-id="a243a-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="a243a-1125">PassportID</span></span>
- <span data-ttu-id="a243a-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="a243a-1126">Passportno</span></span>
- <span data-ttu-id="a243a-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-1127">passportnumber</span></span>
- <span data-ttu-id="a243a-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="a243a-1128">パスポート</span></span>
- <span data-ttu-id="a243a-1129">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="a243a-1129">パスポート番号</span></span>
- <span data-ttu-id="a243a-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a243a-1130">パスポートのNum</span></span>
- <span data-ttu-id="a243a-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a243a-1131">パスポート＃</span></span>
- <span data-ttu-id="a243a-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a243a-1132">Numéro de passeport</span></span>
- <span data-ttu-id="a243a-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a243a-1133">Passeport n °</span></span>
- <span data-ttu-id="a243a-1134">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="a243a-1134">Passeport Non</span></span>
- <span data-ttu-id="a243a-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="a243a-1135">Passeport #</span></span>
- <span data-ttu-id="a243a-1136">Passeport#</span><span class="sxs-lookup"><span data-stu-id="a243a-1136">Passeport#</span></span>
- <span data-ttu-id="a243a-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a243a-1137">PasseportNon</span></span>
- <span data-ttu-id="a243a-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a243a-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="a243a-1139">加拿大個人健康身分識別號碼（PHIN）</span><span class="sxs-lookup"><span data-stu-id="a243a-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1140">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1140">Format</span></span>

<span data-ttu-id="a243a-1141">九位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1142">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1142">Pattern</span></span>

<span data-ttu-id="a243a-1143">九位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1144">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1144">Checksum</span></span>

<span data-ttu-id="a243a-1145">否</span><span class="sxs-lookup"><span data-stu-id="a243a-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1146">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1146">Definition</span></span>

<span data-ttu-id="a243a-1147">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：正則運算式 Regex_canada_phin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="a243a-1148">至少會找到兩個 Keyword_canada_phin 或 Keyword_canada_provinces 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="a243a-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="a243a-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="a243a-1151">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1151">social insurance number</span></span>
- <span data-ttu-id="a243a-1152">狀況資訊法案</span><span class="sxs-lookup"><span data-stu-id="a243a-1152">health information act</span></span>
- <span data-ttu-id="a243a-1153">所得稅資訊</span><span class="sxs-lookup"><span data-stu-id="a243a-1153">income tax information</span></span>
- <span data-ttu-id="a243a-1154">manitoba 健康情況</span><span class="sxs-lookup"><span data-stu-id="a243a-1154">manitoba health</span></span>
- <span data-ttu-id="a243a-1155">健康情況登記</span><span class="sxs-lookup"><span data-stu-id="a243a-1155">health registration</span></span>
- <span data-ttu-id="a243a-1156">處方購買</span><span class="sxs-lookup"><span data-stu-id="a243a-1156">prescription purchases</span></span>
- <span data-ttu-id="a243a-1157">效益資格</span><span class="sxs-lookup"><span data-stu-id="a243a-1157">benefit eligibility</span></span>
- <span data-ttu-id="a243a-1158">個人健康情況</span><span class="sxs-lookup"><span data-stu-id="a243a-1158">personal health</span></span>
- <span data-ttu-id="a243a-1159">律師的權力</span><span class="sxs-lookup"><span data-stu-id="a243a-1159">power of attorney</span></span>
- <span data-ttu-id="a243a-1160">登記編號</span><span class="sxs-lookup"><span data-stu-id="a243a-1160">registration number</span></span>
- <span data-ttu-id="a243a-1161">個人健康號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1161">personal health number</span></span>
- <span data-ttu-id="a243a-1162">practitioner 參照</span><span class="sxs-lookup"><span data-stu-id="a243a-1162">practitioner referral</span></span>
- <span data-ttu-id="a243a-1163">wellness 專業版</span><span class="sxs-lookup"><span data-stu-id="a243a-1163">wellness professional</span></span>
- <span data-ttu-id="a243a-1164">患者參考</span><span class="sxs-lookup"><span data-stu-id="a243a-1164">patient referral</span></span>
- <span data-ttu-id="a243a-1165">健康情況與 wellness</span><span class="sxs-lookup"><span data-stu-id="a243a-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="a243a-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="a243a-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="a243a-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="a243a-1167">Nunavut</span></span>
- <span data-ttu-id="a243a-1168">魁北克</span><span class="sxs-lookup"><span data-stu-id="a243a-1168">Quebec</span></span>
- <span data-ttu-id="a243a-1169">西北領地</span><span class="sxs-lookup"><span data-stu-id="a243a-1169">Northwest Territories</span></span>
- <span data-ttu-id="a243a-1170">安大略省</span><span class="sxs-lookup"><span data-stu-id="a243a-1170">Ontario</span></span>
- <span data-ttu-id="a243a-1171">不列顛哥倫比亞省</span><span class="sxs-lookup"><span data-stu-id="a243a-1171">British Columbia</span></span>
- <span data-ttu-id="a243a-1172">阿爾比省</span><span class="sxs-lookup"><span data-stu-id="a243a-1172">Alberta</span></span>
- <span data-ttu-id="a243a-1173">薩斯喀徹爾省</span><span class="sxs-lookup"><span data-stu-id="a243a-1173">Saskatchewan</span></span>
- <span data-ttu-id="a243a-1174">馬尼托巴省</span><span class="sxs-lookup"><span data-stu-id="a243a-1174">Manitoba</span></span>
- <span data-ttu-id="a243a-1175">育 空</span><span class="sxs-lookup"><span data-stu-id="a243a-1175">Yukon</span></span>
- <span data-ttu-id="a243a-1176">紐芬蘭和 Labrador</span><span class="sxs-lookup"><span data-stu-id="a243a-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="a243a-1177">新不倫瑞克省</span><span class="sxs-lookup"><span data-stu-id="a243a-1177">New Brunswick</span></span>
- <span data-ttu-id="a243a-1178">新斯科舍省</span><span class="sxs-lookup"><span data-stu-id="a243a-1178">Nova Scotia</span></span>
- <span data-ttu-id="a243a-1179">艾德華王子島</span><span class="sxs-lookup"><span data-stu-id="a243a-1179">Prince Edward Island</span></span>
- <span data-ttu-id="a243a-1180">加拿大</span><span class="sxs-lookup"><span data-stu-id="a243a-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="a243a-1181">加拿大社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1182">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1182">Format</span></span>

<span data-ttu-id="a243a-1183">具有選擇性連字號或空格的九位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1184">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1184">Pattern</span></span>

<span data-ttu-id="a243a-1185">格式 化：</span><span class="sxs-lookup"><span data-stu-id="a243a-1185">Formatted:</span></span>
- <span data-ttu-id="a243a-1186">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1186">Three digits</span></span> 
- <span data-ttu-id="a243a-1187">連字號或空格</span><span class="sxs-lookup"><span data-stu-id="a243a-1187">A hyphen or space</span></span> 
- <span data-ttu-id="a243a-1188">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1188">Three digits</span></span> 
- <span data-ttu-id="a243a-1189">連字號或空格</span><span class="sxs-lookup"><span data-stu-id="a243a-1189">A hyphen or space</span></span> 
- <span data-ttu-id="a243a-1190">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1190">Three digits</span></span>

<span data-ttu-id="a243a-1191">未格式化：九位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1192">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1192">Checksum</span></span>

<span data-ttu-id="a243a-1193">是</span><span class="sxs-lookup"><span data-stu-id="a243a-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1194">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1194">Definition</span></span>

<span data-ttu-id="a243a-1195">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1196">函數 Func_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1197">下列其中一種組合，至少有兩種：</span><span class="sxs-lookup"><span data-stu-id="a243a-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="a243a-1198">會找到來自 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="a243a-1199">會找到來自 Keyword_sin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="a243a-1200">函數 Func_eu_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a243a-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a243a-1201">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1201">The checksum passes.</span></span>

<span data-ttu-id="a243a-1202">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1203">函數 Func_unformatted_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1204">會找到來自 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="a243a-1205">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1205">The checksum passes.</span></span>

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1206">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="a243a-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="a243a-1207">Keyword_sin</span></span>

- <span data-ttu-id="a243a-1208">罪</span><span class="sxs-lookup"><span data-stu-id="a243a-1208">sin</span></span> 
- <span data-ttu-id="a243a-1209">社交保險</span><span class="sxs-lookup"><span data-stu-id="a243a-1209">social insurance</span></span> 
- <span data-ttu-id="a243a-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="a243a-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="a243a-1211">罪</span><span class="sxs-lookup"><span data-stu-id="a243a-1211">sins</span></span> 
- <span data-ttu-id="a243a-1212">Ssn</span><span class="sxs-lookup"><span data-stu-id="a243a-1212">ssn</span></span> 
- <span data-ttu-id="a243a-1213">主旨 ssn</span><span class="sxs-lookup"><span data-stu-id="a243a-1213">ssns</span></span> 
- <span data-ttu-id="a243a-1214">社會保障</span><span class="sxs-lookup"><span data-stu-id="a243a-1214">social security</span></span> 
- <span data-ttu-id="a243a-1215">numero d'assurance 社交</span><span class="sxs-lookup"><span data-stu-id="a243a-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="a243a-1216">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1216">national identification number</span></span> 
- <span data-ttu-id="a243a-1217">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1217">national id</span></span> 
- <span data-ttu-id="a243a-1218">罪#</span><span class="sxs-lookup"><span data-stu-id="a243a-1218">sin#</span></span> 
- <span data-ttu-id="a243a-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="a243a-1219">soc ins</span></span> 
- <span data-ttu-id="a243a-1220">社交 ins</span><span class="sxs-lookup"><span data-stu-id="a243a-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="a243a-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="a243a-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="a243a-1222">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-1222">driver's license</span></span> 
- <span data-ttu-id="a243a-1223">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-1223">drivers license</span></span> 
- <span data-ttu-id="a243a-1224">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-1224">driver's licence</span></span> 
- <span data-ttu-id="a243a-1225">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-1225">drivers licence</span></span> 
- <span data-ttu-id="a243a-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="a243a-1226">DOB</span></span> 
- <span data-ttu-id="a243a-1227">出生日期</span><span class="sxs-lookup"><span data-stu-id="a243a-1227">Birthdate</span></span> 
- <span data-ttu-id="a243a-1228">生日</span><span class="sxs-lookup"><span data-stu-id="a243a-1228">Birthday</span></span> 
- <span data-ttu-id="a243a-1229">出生日期</span><span class="sxs-lookup"><span data-stu-id="a243a-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="a243a-1230">智利身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1231">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1231">Format</span></span>

<span data-ttu-id="a243a-1232">7-8 位數加上分隔符號 a check digits 或字母</span><span class="sxs-lookup"><span data-stu-id="a243a-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1233">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1233">Pattern</span></span>

<span data-ttu-id="a243a-1234">7-8 位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="a243a-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="a243a-1235">1-2 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1235">1-2 digits</span></span> 
- <span data-ttu-id="a243a-1236">一個句點</span><span class="sxs-lookup"><span data-stu-id="a243a-1236">A period</span></span> 
- <span data-ttu-id="a243a-1237">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1237">Three digits</span></span> 
- <span data-ttu-id="a243a-1238">一個句點</span><span class="sxs-lookup"><span data-stu-id="a243a-1238">A period</span></span> 
- <span data-ttu-id="a243a-1239">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1239">Three digits</span></span> 
- <span data-ttu-id="a243a-1240">虛線</span><span class="sxs-lookup"><span data-stu-id="a243a-1240">A dash</span></span> 
- <span data-ttu-id="a243a-1241">一個數位或字母（不區分大小寫），這是一種檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1242">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1242">Checksum</span></span>

<span data-ttu-id="a243a-1243">是</span><span class="sxs-lookup"><span data-stu-id="a243a-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1244">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1244">Definition</span></span>

<span data-ttu-id="a243a-1245">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1246">函數 Func_chile_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1247">會找到來自 Keyword_chile_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="a243a-1248">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1248">The checksum passes.</span></span>

<span data-ttu-id="a243a-1249">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1250">函數 Func_chile_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1251">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1251">The checksum passes.</span></span>

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="a243a-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="a243a-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="a243a-1254">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1254">National Identification Number</span></span> 
- <span data-ttu-id="a243a-1255">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-1255">Identity card</span></span> 
- <span data-ttu-id="a243a-1256">ID</span><span class="sxs-lookup"><span data-stu-id="a243a-1256">ID</span></span> 
- <span data-ttu-id="a243a-1257">識別</span><span class="sxs-lookup"><span data-stu-id="a243a-1257">Identification</span></span> 
- <span data-ttu-id="a243a-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="a243a-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="a243a-1259">運行</span><span class="sxs-lookup"><span data-stu-id="a243a-1259">RUN</span></span> 
- <span data-ttu-id="a243a-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="a243a-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="a243a-1261">車轍</span><span class="sxs-lookup"><span data-stu-id="a243a-1261">RUT</span></span> 
- <span data-ttu-id="a243a-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="a243a-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="a243a-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="a243a-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="a243a-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="a243a-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="a243a-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="a243a-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="a243a-1266">中國居民身分識別卡片（中國）號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1267">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1267">Format</span></span>

<span data-ttu-id="a243a-1268">18位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1269">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1269">Pattern</span></span>

<span data-ttu-id="a243a-1270">18位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-1270">18 digits:</span></span>
- <span data-ttu-id="a243a-1271">六位數的位址碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="a243a-1272">在 YYYYMMDD 中的八位數（出生日期）</span><span class="sxs-lookup"><span data-stu-id="a243a-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a243a-1273">三位數的訂單碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="a243a-1274">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1275">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1275">Checksum</span></span>

<span data-ttu-id="a243a-1276">是</span><span class="sxs-lookup"><span data-stu-id="a243a-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1277">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1277">Definition</span></span>

<span data-ttu-id="a243a-1278">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1279">函數 Func_china_resident_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1280">會找到來自 Keyword_china_resident_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="a243a-1281">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1281">The checksum passes.</span></span>

<span data-ttu-id="a243a-1282">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1283">函數 Func_china_resident_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1284">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1284">The checksum passes.</span></span>

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1285">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="a243a-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="a243a-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="a243a-1287">常駐身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="a243a-1288">中國</span><span class="sxs-lookup"><span data-stu-id="a243a-1288">PRC</span></span> 
- <span data-ttu-id="a243a-1289">全國身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1289">National Identification Card</span></span> 
- <span data-ttu-id="a243a-1290">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-1290">身份证</span></span> 
- <span data-ttu-id="a243a-1291">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-1291">居民 身份证</span></span> 
- <span data-ttu-id="a243a-1292">居民身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-1292">居民身份证</span></span> 
- <span data-ttu-id="a243a-1293">鑒定</span><span class="sxs-lookup"><span data-stu-id="a243a-1293">鉴定</span></span> 
- <span data-ttu-id="a243a-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-1294">身分證</span></span> 
- <span data-ttu-id="a243a-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-1295">居民 身份證</span></span>
- <span data-ttu-id="a243a-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="a243a-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="a243a-1297">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1298">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1298">Format</span></span>

<span data-ttu-id="a243a-1299">14至16位數，可格式化或未格式化（dddddddddddddddd），且必須透過 Luhn 測試。</span><span class="sxs-lookup"><span data-stu-id="a243a-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1300">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1300">Pattern</span></span>

<span data-ttu-id="a243a-1301">非常複雜且健全的模式，可偵測全球所有主要品牌的卡，包括簽證、MasterCard、探索卡、JCB、美洲 Express、禮品卡和 diner 卡。</span><span class="sxs-lookup"><span data-stu-id="a243a-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1302">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1302">Checksum</span></span>

<span data-ttu-id="a243a-1303">是，Luhn 檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1304">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1304">Definition</span></span>

<span data-ttu-id="a243a-1305">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1306">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1307">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="a243a-1307">One of the following is true:</span></span>
    - <span data-ttu-id="a243a-1308">會找到來自 Keyword_cc_verification 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="a243a-1309">會找到來自 Keyword_cc_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="a243a-1310">函數 Func_expiration_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a243a-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a243a-1311">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1311">The checksum passes.</span></span>

<span data-ttu-id="a243a-1312">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1313">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1314">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1314">The checksum passes.</span></span>

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="a243a-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="a243a-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="a243a-1317">名片驗證</span><span class="sxs-lookup"><span data-stu-id="a243a-1317">card verification</span></span>
- <span data-ttu-id="a243a-1318">卡片識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1318">card identification number</span></span>
- <span data-ttu-id="a243a-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="a243a-1319">cvn</span></span>
- <span data-ttu-id="a243a-1320">cid</span><span class="sxs-lookup"><span data-stu-id="a243a-1320">cid</span></span>
- <span data-ttu-id="a243a-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="a243a-1321">cvc2</span></span>
- <span data-ttu-id="a243a-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="a243a-1322">cvv2</span></span>
- <span data-ttu-id="a243a-1323">pin 區區塊</span><span class="sxs-lookup"><span data-stu-id="a243a-1323">pin block</span></span>
- <span data-ttu-id="a243a-1324">安全性代碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1324">security code</span></span>
- <span data-ttu-id="a243a-1325">安全性號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1325">security number</span></span>
- <span data-ttu-id="a243a-1326">安全性否</span><span class="sxs-lookup"><span data-stu-id="a243a-1326">security no</span></span>
- <span data-ttu-id="a243a-1327">發行編號</span><span class="sxs-lookup"><span data-stu-id="a243a-1327">issue number</span></span>
- <span data-ttu-id="a243a-1328">問題否</span><span class="sxs-lookup"><span data-stu-id="a243a-1328">issue no</span></span>
- <span data-ttu-id="a243a-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="a243a-1329">cryptogramme</span></span>
- <span data-ttu-id="a243a-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="a243a-1330">numéro de sécurité</span></span>
- <span data-ttu-id="a243a-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="a243a-1331">numero de securite</span></span>
- <span data-ttu-id="a243a-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="a243a-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="a243a-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="a243a-1334">prüfziffer</span></span>
- <span data-ttu-id="a243a-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="a243a-1335">prufziffer</span></span>
- <span data-ttu-id="a243a-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="a243a-1336">sicherheits Kode</span></span>
- <span data-ttu-id="a243a-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="a243a-1337">sicherheitscode</span></span>
- <span data-ttu-id="a243a-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="a243a-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="a243a-1339">verfalldatum</span></span>
- <span data-ttu-id="a243a-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="a243a-1340">codice di verifica</span></span>
- <span data-ttu-id="a243a-1341">Cod。</span><span class="sxs-lookup"><span data-stu-id="a243a-1341">cod.</span></span> <span data-ttu-id="a243a-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="a243a-1342">sicurezza</span></span>
- <span data-ttu-id="a243a-1343">貨至 sicurezza</span><span class="sxs-lookup"><span data-stu-id="a243a-1343">cod sicurezza</span></span>
- <span data-ttu-id="a243a-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a243a-1344">n autorizzazione</span></span>
- <span data-ttu-id="a243a-1345">código</span><span class="sxs-lookup"><span data-stu-id="a243a-1345">código</span></span>
- <span data-ttu-id="a243a-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="a243a-1346">codigo</span></span>
- <span data-ttu-id="a243a-1347">Cod。</span><span class="sxs-lookup"><span data-stu-id="a243a-1347">cod.</span></span> <span data-ttu-id="a243a-1348">Seg</span><span class="sxs-lookup"><span data-stu-id="a243a-1348">seg</span></span>
- <span data-ttu-id="a243a-1349">貨至 seg</span><span class="sxs-lookup"><span data-stu-id="a243a-1349">cod seg</span></span>
- <span data-ttu-id="a243a-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1350">código de segurança</span></span>
- <span data-ttu-id="a243a-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="a243a-1351">codigo de seguranca</span></span>
- <span data-ttu-id="a243a-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1352">codigo de segurança</span></span>
- <span data-ttu-id="a243a-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="a243a-1353">código de seguranca</span></span>
- <span data-ttu-id="a243a-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="a243a-1354">cód.</span></span> <span data-ttu-id="a243a-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1355">segurança</span></span>
- <span data-ttu-id="a243a-1356">Cod。</span><span class="sxs-lookup"><span data-stu-id="a243a-1356">cod.</span></span> <span data-ttu-id="a243a-1357">seguranca 貨。</span><span class="sxs-lookup"><span data-stu-id="a243a-1357">seguranca cod.</span></span> <span data-ttu-id="a243a-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1358">segurança</span></span>
- <span data-ttu-id="a243a-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="a243a-1359">cód.</span></span> <span data-ttu-id="a243a-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="a243a-1360">seguranca</span></span>
- <span data-ttu-id="a243a-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1361">cód segurança</span></span>
- <span data-ttu-id="a243a-1362">貨至付款 seguranca，segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="a243a-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="a243a-1363">cód seguranca</span></span>
- <span data-ttu-id="a243a-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="a243a-1364">número de verificação</span></span>
- <span data-ttu-id="a243a-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="a243a-1365">numero de verificacao</span></span>
- <span data-ttu-id="a243a-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="a243a-1366">ablauf</span></span>
- <span data-ttu-id="a243a-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="a243a-1367">gültig bis</span></span>
- <span data-ttu-id="a243a-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a243a-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="a243a-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="a243a-1369">gultig bis</span></span>
- <span data-ttu-id="a243a-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a243a-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="a243a-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="a243a-1371">scadenza</span></span>
- <span data-ttu-id="a243a-1372">資料 scad</span><span class="sxs-lookup"><span data-stu-id="a243a-1372">data scad</span></span>
- <span data-ttu-id="a243a-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="a243a-1373">fecha de expiracion</span></span>
- <span data-ttu-id="a243a-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="a243a-1374">fecha de venc</span></span>
- <span data-ttu-id="a243a-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="a243a-1375">vencimiento</span></span>
- <span data-ttu-id="a243a-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="a243a-1376">válido hasta</span></span>
- <span data-ttu-id="a243a-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="a243a-1377">valido hasta</span></span>
- <span data-ttu-id="a243a-1378">vto</span><span class="sxs-lookup"><span data-stu-id="a243a-1378">vto</span></span>
- <span data-ttu-id="a243a-1379">資料 de expiração</span><span class="sxs-lookup"><span data-stu-id="a243a-1379">data de expiração</span></span>
- <span data-ttu-id="a243a-1380">資料 de expiracao</span><span class="sxs-lookup"><span data-stu-id="a243a-1380">data de expiracao</span></span>
- <span data-ttu-id="a243a-1381">資料 em mail.que expira</span><span class="sxs-lookup"><span data-stu-id="a243a-1381">data em que expira</span></span>
- <span data-ttu-id="a243a-1382">validade</span><span class="sxs-lookup"><span data-stu-id="a243a-1382">validade</span></span>
- <span data-ttu-id="a243a-1383">勇氣</span><span class="sxs-lookup"><span data-stu-id="a243a-1383">valor</span></span>
- <span data-ttu-id="a243a-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="a243a-1384">vencimento</span></span>
- <span data-ttu-id="a243a-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="a243a-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="a243a-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="a243a-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="a243a-1387">amex</span><span class="sxs-lookup"><span data-stu-id="a243a-1387">amex</span></span>
- <span data-ttu-id="a243a-1388">美洲 express</span><span class="sxs-lookup"><span data-stu-id="a243a-1388">american express</span></span>
- <span data-ttu-id="a243a-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="a243a-1389">americanexpress</span></span>
- <span data-ttu-id="a243a-1390">簽證</span><span class="sxs-lookup"><span data-stu-id="a243a-1390">Visa</span></span>
- <span data-ttu-id="a243a-1391">萬事 達</span><span class="sxs-lookup"><span data-stu-id="a243a-1391">mastercard</span></span>
- <span data-ttu-id="a243a-1392">主卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1392">master card</span></span>
- <span data-ttu-id="a243a-1393">Mc</span><span class="sxs-lookup"><span data-stu-id="a243a-1393">mc</span></span> 
- <span data-ttu-id="a243a-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="a243a-1394">mastercards</span></span>
- <span data-ttu-id="a243a-1395">主卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1395">master cards</span></span>
- <span data-ttu-id="a243a-1396">diner 俱樂部</span><span class="sxs-lookup"><span data-stu-id="a243a-1396">diner's Club</span></span>
- <span data-ttu-id="a243a-1397">diners 俱樂部</span><span class="sxs-lookup"><span data-stu-id="a243a-1397">diners club</span></span>
- <span data-ttu-id="a243a-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="a243a-1398">dinersclub</span></span>
- <span data-ttu-id="a243a-1399">探索卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-1399">discover card</span></span>
- <span data-ttu-id="a243a-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="a243a-1400">discovercard</span></span>
- <span data-ttu-id="a243a-1401">探索卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-1401">discover cards</span></span>
- <span data-ttu-id="a243a-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="a243a-1402">JCB</span></span>
- <span data-ttu-id="a243a-1403">日本卡片局</span><span class="sxs-lookup"><span data-stu-id="a243a-1403">japanese card bureau</span></span>
- <span data-ttu-id="a243a-1404">購買 blanche</span><span class="sxs-lookup"><span data-stu-id="a243a-1404">carte blanche</span></span>
- <span data-ttu-id="a243a-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="a243a-1405">carteblanche</span></span>
- <span data-ttu-id="a243a-1406">信用卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1406">credit card</span></span>
- <span data-ttu-id="a243a-1407">Cc#</span><span class="sxs-lookup"><span data-stu-id="a243a-1407">cc#</span></span>
- <span data-ttu-id="a243a-1408">抄送 #：</span><span class="sxs-lookup"><span data-stu-id="a243a-1408">cc#:</span></span>
- <span data-ttu-id="a243a-1409">有效期</span><span class="sxs-lookup"><span data-stu-id="a243a-1409">expiration date</span></span>
- <span data-ttu-id="a243a-1410">到期日</span><span class="sxs-lookup"><span data-stu-id="a243a-1410">exp date</span></span>
- <span data-ttu-id="a243a-1411">有效期</span><span class="sxs-lookup"><span data-stu-id="a243a-1411">expiry date</span></span>
- <span data-ttu-id="a243a-1412">日期 d'expiration</span><span class="sxs-lookup"><span data-stu-id="a243a-1412">date d'expiration</span></span>
- <span data-ttu-id="a243a-1413">日期 d'exp</span><span class="sxs-lookup"><span data-stu-id="a243a-1413">date d'exp</span></span>
- <span data-ttu-id="a243a-1414">到期日</span><span class="sxs-lookup"><span data-stu-id="a243a-1414">date expiration</span></span>
- <span data-ttu-id="a243a-1415">銀行卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1415">bank card</span></span>
- <span data-ttu-id="a243a-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="a243a-1416">bankcard</span></span>
- <span data-ttu-id="a243a-1417">卡號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1417">card number</span></span>
- <span data-ttu-id="a243a-1418">卡號</span><span class="sxs-lookup"><span data-stu-id="a243a-1418">card num</span></span>
- <span data-ttu-id="a243a-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-1419">cardnumber</span></span>
- <span data-ttu-id="a243a-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="a243a-1420">cardnumbers</span></span>
- <span data-ttu-id="a243a-1421">卡號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1421">card numbers</span></span>
- <span data-ttu-id="a243a-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="a243a-1422">creditcard</span></span>
- <span data-ttu-id="a243a-1423">信用卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1423">credit cards</span></span>
- <span data-ttu-id="a243a-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="a243a-1424">creditcards</span></span>
- <span data-ttu-id="a243a-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="a243a-1425">ccn</span></span>
- <span data-ttu-id="a243a-1426">持卡人</span><span class="sxs-lookup"><span data-stu-id="a243a-1426">card holder</span></span>
- <span data-ttu-id="a243a-1427">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="a243a-1427">cardholder</span></span>
- <span data-ttu-id="a243a-1428">持卡人</span><span class="sxs-lookup"><span data-stu-id="a243a-1428">card holders</span></span>
- <span data-ttu-id="a243a-1429">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="a243a-1429">cardholders</span></span>
- <span data-ttu-id="a243a-1430">檢查卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-1430">check card</span></span>
- <span data-ttu-id="a243a-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="a243a-1431">checkcard</span></span>
- <span data-ttu-id="a243a-1432">檢查卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-1432">check cards</span></span>
- <span data-ttu-id="a243a-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="a243a-1433">checkcards</span></span>
- <span data-ttu-id="a243a-1434">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1434">debit card</span></span>
- <span data-ttu-id="a243a-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="a243a-1435">debitcard</span></span>
- <span data-ttu-id="a243a-1436">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1436">debit cards</span></span>
- <span data-ttu-id="a243a-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="a243a-1437">debitcards</span></span>
- <span data-ttu-id="a243a-1438">atm 卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1438">atm card</span></span>
- <span data-ttu-id="a243a-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="a243a-1439">atmcard</span></span>
- <span data-ttu-id="a243a-1440">atm 卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1440">atm cards</span></span>
- <span data-ttu-id="a243a-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="a243a-1441">atmcards</span></span>
- <span data-ttu-id="a243a-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="a243a-1442">enroute</span></span>
- <span data-ttu-id="a243a-1443">途中</span><span class="sxs-lookup"><span data-stu-id="a243a-1443">en route</span></span>
- <span data-ttu-id="a243a-1444">卡片類型</span><span class="sxs-lookup"><span data-stu-id="a243a-1444">card type</span></span>
- <span data-ttu-id="a243a-1445">購買 bancaire</span><span class="sxs-lookup"><span data-stu-id="a243a-1445">carte bancaire</span></span>
- <span data-ttu-id="a243a-1446">反 crédit</span><span class="sxs-lookup"><span data-stu-id="a243a-1446">carte de crédit</span></span>
- <span data-ttu-id="a243a-1447">購買退款</span><span class="sxs-lookup"><span data-stu-id="a243a-1447">carte de credit</span></span>
- <span data-ttu-id="a243a-1448">numéro 的重複購買</span><span class="sxs-lookup"><span data-stu-id="a243a-1448">numéro de carte</span></span>
- <span data-ttu-id="a243a-1449">numero 的重複購買</span><span class="sxs-lookup"><span data-stu-id="a243a-1449">numero de carte</span></span>
- <span data-ttu-id="a243a-1450">de 照購買</span><span class="sxs-lookup"><span data-stu-id="a243a-1450">nº de la carte</span></span>
- <span data-ttu-id="a243a-1451">消除購買的 n º</span><span class="sxs-lookup"><span data-stu-id="a243a-1451">nº de carte</span></span>
- <span data-ttu-id="a243a-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="a243a-1452">kreditkarte</span></span>
- <span data-ttu-id="a243a-1453">karte</span><span class="sxs-lookup"><span data-stu-id="a243a-1453">karte</span></span>
- <span data-ttu-id="a243a-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="a243a-1454">karteninhaber</span></span>
- <span data-ttu-id="a243a-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="a243a-1455">karteninhabers</span></span>
- <span data-ttu-id="a243a-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="a243a-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="a243a-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="a243a-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="a243a-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="a243a-1458">kreditkartentyp</span></span>
- <span data-ttu-id="a243a-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="a243a-1459">eigentümername</span></span>
- <span data-ttu-id="a243a-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="a243a-1460">kartennr</span></span> 
- <span data-ttu-id="a243a-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1461">kartennummer</span></span>
- <span data-ttu-id="a243a-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1462">kreditkartennummer</span></span>
- <span data-ttu-id="a243a-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="a243a-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1464">carta di credito</span></span>
- <span data-ttu-id="a243a-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1465">carta credito</span></span>
- <span data-ttu-id="a243a-1466">憲章</span><span class="sxs-lookup"><span data-stu-id="a243a-1466">carta</span></span>
- <span data-ttu-id="a243a-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="a243a-1467">n carta</span></span>
- <span data-ttu-id="a243a-1468">星期日。</span><span class="sxs-lookup"><span data-stu-id="a243a-1468">nr.</span></span> <span data-ttu-id="a243a-1469">憲章</span><span class="sxs-lookup"><span data-stu-id="a243a-1469">carta</span></span>
- <span data-ttu-id="a243a-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="a243a-1470">nr carta</span></span>
- <span data-ttu-id="a243a-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="a243a-1471">numero carta</span></span>
- <span data-ttu-id="a243a-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="a243a-1472">numero della carta</span></span>
- <span data-ttu-id="a243a-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="a243a-1473">numero di carta</span></span>
- <span data-ttu-id="a243a-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1474">tarjeta credito</span></span>
- <span data-ttu-id="a243a-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1475">tarjeta de credito</span></span>
- <span data-ttu-id="a243a-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="a243a-1476">tarjeta crédito</span></span>
- <span data-ttu-id="a243a-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="a243a-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="a243a-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="a243a-1478">tarjeta de atm</span></span>
- <span data-ttu-id="a243a-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="a243a-1479">tarjeta atm</span></span>
- <span data-ttu-id="a243a-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="a243a-1480">tarjeta debito</span></span>
- <span data-ttu-id="a243a-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="a243a-1481">tarjeta de debito</span></span>
- <span data-ttu-id="a243a-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="a243a-1482">tarjeta débito</span></span>
- <span data-ttu-id="a243a-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="a243a-1483">tarjeta de débito</span></span>
- <span data-ttu-id="a243a-1484">消除 tarjeta 的 n º</span><span class="sxs-lookup"><span data-stu-id="a243a-1484">nº de tarjeta</span></span>
- <span data-ttu-id="a243a-1485">不。</span><span class="sxs-lookup"><span data-stu-id="a243a-1485">no.</span></span> <span data-ttu-id="a243a-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a243a-1486">de tarjeta</span></span>
- <span data-ttu-id="a243a-1487">無 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a243a-1487">no de tarjeta</span></span>
- <span data-ttu-id="a243a-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a243a-1488">numero de tarjeta</span></span>
- <span data-ttu-id="a243a-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a243a-1489">número de tarjeta</span></span>
- <span data-ttu-id="a243a-1490">tarjeta 否</span><span class="sxs-lookup"><span data-stu-id="a243a-1490">tarjeta no</span></span>
- <span data-ttu-id="a243a-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="a243a-1491">tarjetahabiente</span></span>
- <span data-ttu-id="a243a-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="a243a-1492">cartão de crédito</span></span>
- <span data-ttu-id="a243a-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1493">cartão de credito</span></span>
- <span data-ttu-id="a243a-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="a243a-1494">cartao de crédito</span></span>
- <span data-ttu-id="a243a-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1495">cartao de credito</span></span>
- <span data-ttu-id="a243a-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="a243a-1496">cartão de débito</span></span>
- <span data-ttu-id="a243a-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="a243a-1497">cartao de débito</span></span>
- <span data-ttu-id="a243a-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="a243a-1498">cartão de debito</span></span>
- <span data-ttu-id="a243a-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="a243a-1499">cartao de debito</span></span>
- <span data-ttu-id="a243a-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="a243a-1500">débito automático</span></span>
- <span data-ttu-id="a243a-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="a243a-1501">debito automatico</span></span>
- <span data-ttu-id="a243a-1502">número 執行 cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1502">número do cartão</span></span>
- <span data-ttu-id="a243a-1503">numero 執行 cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1503">numero do cartão</span></span> 
- <span data-ttu-id="a243a-1504">número 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1504">número do cartao</span></span>
- <span data-ttu-id="a243a-1505">numero 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1505">numero do cartao</span></span>
- <span data-ttu-id="a243a-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1506">número de cartão</span></span>
- <span data-ttu-id="a243a-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1507">numero de cartão</span></span>
- <span data-ttu-id="a243a-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1508">número de cartao</span></span>
- <span data-ttu-id="a243a-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1509">numero de cartao</span></span>
- <span data-ttu-id="a243a-1510">n º do cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1510">nº do cartão</span></span>
- <span data-ttu-id="a243a-1511">n º do cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1511">nº do cartao</span></span>
- <span data-ttu-id="a243a-1512">n º。</span><span class="sxs-lookup"><span data-stu-id="a243a-1512">nº.</span></span> <span data-ttu-id="a243a-1513">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1513">do cartão</span></span>
- <span data-ttu-id="a243a-1514">無 do cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1514">no do cartão</span></span>
- <span data-ttu-id="a243a-1515">無 do cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1515">no do cartao</span></span>
- <span data-ttu-id="a243a-1516">不。</span><span class="sxs-lookup"><span data-stu-id="a243a-1516">no.</span></span> <span data-ttu-id="a243a-1517">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1517">do cartão</span></span>
- <span data-ttu-id="a243a-1518">不。</span><span class="sxs-lookup"><span data-stu-id="a243a-1518">no.</span></span> <span data-ttu-id="a243a-1519">執行 cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="a243a-1520">克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1521">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1521">Format</span></span>

<span data-ttu-id="a243a-1522">九位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1523">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1523">Pattern</span></span>

<span data-ttu-id="a243a-1524">九個連續數位</span><span class="sxs-lookup"><span data-stu-id="a243a-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1525">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1525">Checksum</span></span>

<span data-ttu-id="a243a-1526">否</span><span class="sxs-lookup"><span data-stu-id="a243a-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1527">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1527">Definition</span></span>

<span data-ttu-id="a243a-1528">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1529">函數 Func_croatia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1530">會找到來自 Keyword_croatia_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1531">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="a243a-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="a243a-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="a243a-1533">克羅地亞身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1533">Croatian identity card</span></span>
- <span data-ttu-id="a243a-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="a243a-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="a243a-1535">克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1536">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1536">Format</span></span>

<span data-ttu-id="a243a-1537">11位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1538">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1538">Pattern</span></span>

<span data-ttu-id="a243a-1539">11位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-1539">11 digits:</span></span>
- <span data-ttu-id="a243a-1540">10位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1540">10 digits</span></span> 
- <span data-ttu-id="a243a-1541">最後一個數位是檢查碼用於國際資料交換的目的，在11位數之前新增字母「HR」。</span><span class="sxs-lookup"><span data-stu-id="a243a-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1542">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1542">Checksum</span></span>

<span data-ttu-id="a243a-1543">是</span><span class="sxs-lookup"><span data-stu-id="a243a-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1544">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1544">Definition</span></span>

<span data-ttu-id="a243a-1545">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1546">函數 Func_croatia_oib_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1547">會找到來自 Keyword_croatia_oib_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="a243a-1548">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1548">The checksum passes.</span></span>

<span data-ttu-id="a243a-1549">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1550">函數 Func_croatia_oib_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1551">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1551">The checksum passes.</span></span>

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1552">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="a243a-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="a243a-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="a243a-1554">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1554">Personal Identification Number</span></span>
- <span data-ttu-id="a243a-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="a243a-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="a243a-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="a243a-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="a243a-1557">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1558">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1558">Format</span></span>

<span data-ttu-id="a243a-1559">具有選用正斜線的九位數（舊格式）10位數（選用反斜線（新格式））</span><span class="sxs-lookup"><span data-stu-id="a243a-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1560">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1560">Pattern</span></span>

<span data-ttu-id="a243a-1561">九位數（舊格式）：</span><span class="sxs-lookup"><span data-stu-id="a243a-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="a243a-1562">九位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1562">Nine digits</span></span>

<span data-ttu-id="a243a-1563">OR</span><span class="sxs-lookup"><span data-stu-id="a243a-1563">OR</span></span>

- <span data-ttu-id="a243a-1564">六位數代表出生日期</span><span class="sxs-lookup"><span data-stu-id="a243a-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="a243a-1565">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="a243a-1565">A forward slash</span></span>
- <span data-ttu-id="a243a-1566">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1566">Three digits</span></span>

<span data-ttu-id="a243a-1567">10位數（新格式）：</span><span class="sxs-lookup"><span data-stu-id="a243a-1567">10 digits (new format):</span></span>
- <span data-ttu-id="a243a-1568">10位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1568">10 digits</span></span>

<span data-ttu-id="a243a-1569">OR</span><span class="sxs-lookup"><span data-stu-id="a243a-1569">OR</span></span>

- <span data-ttu-id="a243a-1570">六位數代表出生日期</span><span class="sxs-lookup"><span data-stu-id="a243a-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="a243a-1571">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="a243a-1571">A forward slash</span></span> 
- <span data-ttu-id="a243a-1572">最後一個數位是檢查碼的四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1573">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1573">Checksum</span></span>

<span data-ttu-id="a243a-1574">是</span><span class="sxs-lookup"><span data-stu-id="a243a-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1575">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1575">Definition</span></span>

<span data-ttu-id="a243a-1576">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：函數 Func_czech_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="a243a-1577">會找到來自 Keyword_czech_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="a243a-1578">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="a243a-1579">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1579">Keywords</span></span>

- <span data-ttu-id="a243a-1580">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1580">czech personal identity number</span></span>
- <span data-ttu-id="a243a-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="a243a-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="a243a-1582">丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1583">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1583">Format</span></span>

<span data-ttu-id="a243a-1584">10位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1585">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1585">Pattern</span></span>

<span data-ttu-id="a243a-1586">10位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-1586">10 digits:</span></span>
- <span data-ttu-id="a243a-1587">DDMMYY 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a243a-1588">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-1588">A hyphen</span></span> 
- <span data-ttu-id="a243a-1589">四位數的最後一個數位是檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1590">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1590">Checksum</span></span>

<span data-ttu-id="a243a-1591">是</span><span class="sxs-lookup"><span data-stu-id="a243a-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1592">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1592">Definition</span></span>

<span data-ttu-id="a243a-1593">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：正則運算式 Regex_denmark_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="a243a-1594">會找到來自 Keyword_denmark_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="a243a-1595">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1596">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="a243a-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="a243a-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="a243a-1598">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1598">Personal Identification Number</span></span>
- <span data-ttu-id="a243a-1599">Cpr</span><span class="sxs-lookup"><span data-stu-id="a243a-1599">CPR</span></span>
- <span data-ttu-id="a243a-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="a243a-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="a243a-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="a243a-1602">藥品強制代理人（DEA）號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1603">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1603">Format</span></span>

<span data-ttu-id="a243a-1604">兩個字母后接7位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1605">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1605">Pattern</span></span>

<span data-ttu-id="a243a-1606">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="a243a-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a243a-1607">這組可能字母的一個字母（不區分大小寫）： abcdefghjklmnprstux，也就是報名者程式碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="a243a-1608">一個字母（不區分大小寫），這是報名者姓氏的第一個字母</span><span class="sxs-lookup"><span data-stu-id="a243a-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="a243a-1609">七位數，最後一個是檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1610">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1610">Checksum</span></span>

<span data-ttu-id="a243a-1611">是</span><span class="sxs-lookup"><span data-stu-id="a243a-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1612">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1612">Definition</span></span>

<span data-ttu-id="a243a-1613">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1614">函數 Func_dea_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1615">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1616">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1616">Keywords</span></span>

<span data-ttu-id="a243a-1617">無</span><span class="sxs-lookup"><span data-stu-id="a243a-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="a243a-1618">歐盟轉帳卡號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1619">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1619">Format</span></span>

<span data-ttu-id="a243a-1620">16位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1621">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1621">Pattern</span></span>

<span data-ttu-id="a243a-1622">非常複雜且健全的模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1623">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1623">Checksum</span></span>

<span data-ttu-id="a243a-1624">是</span><span class="sxs-lookup"><span data-stu-id="a243a-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1625">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1625">Definition</span></span>

<span data-ttu-id="a243a-1626">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1627">函數 Func_eu_debit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1628">下列專案中至少有一個為真：</span><span class="sxs-lookup"><span data-stu-id="a243a-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="a243a-1629">會找到來自 Keyword_eu_debit_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="a243a-1630">會找到來自 Keyword_card_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="a243a-1631">會找到來自 Keyword_card_security_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="a243a-1632">會找到來自 Keyword_card_expiration_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="a243a-1633">函數 Func_expiration_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a243a-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a243a-1634">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1634">The checksum passes.</span></span>

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1635">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="a243a-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="a243a-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="a243a-1637">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1637">account number</span></span> 
- <span data-ttu-id="a243a-1638">卡號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1638">card number</span></span> 
- <span data-ttu-id="a243a-1639">卡片編號</span><span class="sxs-lookup"><span data-stu-id="a243a-1639">card no.</span></span> 
- <span data-ttu-id="a243a-1640">安全性號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1640">security number</span></span> 
- <span data-ttu-id="a243a-1641">Cc#</span><span class="sxs-lookup"><span data-stu-id="a243a-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="a243a-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a243a-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="a243a-1643">帳戶 nbr</span><span class="sxs-lookup"><span data-stu-id="a243a-1643">acct nbr</span></span> 
- <span data-ttu-id="a243a-1644">帳戶號</span><span class="sxs-lookup"><span data-stu-id="a243a-1644">acct num</span></span> 
- <span data-ttu-id="a243a-1645">帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-1645">acct no</span></span> 
- <span data-ttu-id="a243a-1646">美洲 express</span><span class="sxs-lookup"><span data-stu-id="a243a-1646">american express</span></span> 
- <span data-ttu-id="a243a-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="a243a-1647">americanexpress</span></span> 
- <span data-ttu-id="a243a-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="a243a-1648">americano espresso</span></span> 
- <span data-ttu-id="a243a-1649">amex</span><span class="sxs-lookup"><span data-stu-id="a243a-1649">amex</span></span> 
- <span data-ttu-id="a243a-1650">atm 卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1650">atm card</span></span> 
- <span data-ttu-id="a243a-1651">atm 卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1651">atm cards</span></span> 
- <span data-ttu-id="a243a-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="a243a-1652">atm kaart</span></span> 
- <span data-ttu-id="a243a-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="a243a-1653">atmcard</span></span> 
- <span data-ttu-id="a243a-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="a243a-1654">atmcards</span></span> 
- <span data-ttu-id="a243a-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="a243a-1655">atmkaart</span></span> 
- <span data-ttu-id="a243a-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="a243a-1656">atmkaarten</span></span> 
- <span data-ttu-id="a243a-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="a243a-1657">bancontact</span></span> 
- <span data-ttu-id="a243a-1658">銀行卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1658">bank card</span></span> 
- <span data-ttu-id="a243a-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="a243a-1659">bankkaart</span></span> 
- <span data-ttu-id="a243a-1660">持卡人</span><span class="sxs-lookup"><span data-stu-id="a243a-1660">card holder</span></span> 
- <span data-ttu-id="a243a-1661">持卡人</span><span class="sxs-lookup"><span data-stu-id="a243a-1661">card holders</span></span> 
- <span data-ttu-id="a243a-1662">卡號</span><span class="sxs-lookup"><span data-stu-id="a243a-1662">card num</span></span> 
- <span data-ttu-id="a243a-1663">卡號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1663">card number</span></span> 
- <span data-ttu-id="a243a-1664">卡號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1664">card numbers</span></span> 
- <span data-ttu-id="a243a-1665">卡片類型</span><span class="sxs-lookup"><span data-stu-id="a243a-1665">card type</span></span> 
- <span data-ttu-id="a243a-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="a243a-1666">cardano numerico</span></span> 
- <span data-ttu-id="a243a-1667">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="a243a-1667">cardholder</span></span> 
- <span data-ttu-id="a243a-1668">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="a243a-1668">cardholders</span></span> 
- <span data-ttu-id="a243a-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-1669">cardnumber</span></span> 
- <span data-ttu-id="a243a-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="a243a-1670">cardnumbers</span></span> 
- <span data-ttu-id="a243a-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="a243a-1671">carta bianca</span></span> 
- <span data-ttu-id="a243a-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1672">carta credito</span></span> 
- <span data-ttu-id="a243a-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1673">carta di credito</span></span> 
- <span data-ttu-id="a243a-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1674">cartao de credito</span></span> 
- <span data-ttu-id="a243a-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="a243a-1675">cartao de crédito</span></span> 
- <span data-ttu-id="a243a-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="a243a-1676">cartao de debito</span></span> 
- <span data-ttu-id="a243a-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="a243a-1677">cartao de débito</span></span> 
- <span data-ttu-id="a243a-1678">購買 bancaire</span><span class="sxs-lookup"><span data-stu-id="a243a-1678">carte bancaire</span></span> 
- <span data-ttu-id="a243a-1679">購買 blanche</span><span class="sxs-lookup"><span data-stu-id="a243a-1679">carte blanche</span></span> 
- <span data-ttu-id="a243a-1680">購買 bleue</span><span class="sxs-lookup"><span data-stu-id="a243a-1680">carte bleue</span></span> 
- <span data-ttu-id="a243a-1681">購買退款</span><span class="sxs-lookup"><span data-stu-id="a243a-1681">carte de credit</span></span> 
- <span data-ttu-id="a243a-1682">反 crédit</span><span class="sxs-lookup"><span data-stu-id="a243a-1682">carte de crédit</span></span> 
- <span data-ttu-id="a243a-1683">購買 di credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1683">carte di credito</span></span> 
- <span data-ttu-id="a243a-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="a243a-1684">carteblanche</span></span> 
- <span data-ttu-id="a243a-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1685">cartão de credito</span></span> 
- <span data-ttu-id="a243a-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="a243a-1686">cartão de crédito</span></span> 
- <span data-ttu-id="a243a-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="a243a-1687">cartão de debito</span></span> 
- <span data-ttu-id="a243a-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="a243a-1688">cartão de débito</span></span> 
- <span data-ttu-id="a243a-1689">cb</span><span class="sxs-lookup"><span data-stu-id="a243a-1689">cb</span></span> 
- <span data-ttu-id="a243a-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="a243a-1690">ccn</span></span> 
- <span data-ttu-id="a243a-1691">檢查卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-1691">check card</span></span> 
- <span data-ttu-id="a243a-1692">檢查卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-1692">check cards</span></span> 
- <span data-ttu-id="a243a-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="a243a-1693">checkcard</span></span>
- <span data-ttu-id="a243a-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="a243a-1694">checkcards</span></span> 
- <span data-ttu-id="a243a-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="a243a-1695">chequekaart</span></span> 
- <span data-ttu-id="a243a-1696">卷雲</span><span class="sxs-lookup"><span data-stu-id="a243a-1696">cirrus</span></span> 
- <span data-ttu-id="a243a-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="a243a-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="a243a-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="a243a-1698">controlekaart</span></span> 
- <span data-ttu-id="a243a-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="a243a-1699">controlekaarten</span></span> 
- <span data-ttu-id="a243a-1700">信用卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1700">credit card</span></span> 
- <span data-ttu-id="a243a-1701">信用卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1701">credit cards</span></span> 
- <span data-ttu-id="a243a-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="a243a-1702">creditcard</span></span> 
- <span data-ttu-id="a243a-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="a243a-1703">creditcards</span></span> 
- <span data-ttu-id="a243a-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="a243a-1704">debetkaart</span></span> 
- <span data-ttu-id="a243a-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="a243a-1705">debetkaarten</span></span> 
- <span data-ttu-id="a243a-1706">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1706">debit card</span></span> 
- <span data-ttu-id="a243a-1707">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1707">debit cards</span></span> 
- <span data-ttu-id="a243a-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="a243a-1708">debitcard</span></span> 
- <span data-ttu-id="a243a-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="a243a-1709">debitcards</span></span> 
- <span data-ttu-id="a243a-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="a243a-1710">debito automatico</span></span> 
- <span data-ttu-id="a243a-1711">diners 俱樂部</span><span class="sxs-lookup"><span data-stu-id="a243a-1711">diners club</span></span> 
- <span data-ttu-id="a243a-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="a243a-1712">dinersclub</span></span> 
- <span data-ttu-id="a243a-1713">發現</span><span class="sxs-lookup"><span data-stu-id="a243a-1713">discover</span></span> 
- <span data-ttu-id="a243a-1714">探索卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-1714">discover card</span></span> 
- <span data-ttu-id="a243a-1715">探索卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-1715">discover cards</span></span> 
- <span data-ttu-id="a243a-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="a243a-1716">discovercard</span></span> 
- <span data-ttu-id="a243a-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="a243a-1717">discovercards</span></span> 
- <span data-ttu-id="a243a-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="a243a-1718">débito automático</span></span>
- <span data-ttu-id="a243a-1719">edc</span><span class="sxs-lookup"><span data-stu-id="a243a-1719">edc</span></span> 
- <span data-ttu-id="a243a-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="a243a-1720">eigentümername</span></span> 
- <span data-ttu-id="a243a-1721">歐洲借貸卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1721">european debit card</span></span> 
- <span data-ttu-id="a243a-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="a243a-1722">hoofdkaart</span></span> 
- <span data-ttu-id="a243a-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="a243a-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="a243a-1724">在 viaggio</span><span class="sxs-lookup"><span data-stu-id="a243a-1724">in viaggio</span></span> 
- <span data-ttu-id="a243a-1725">日本卡片局</span><span class="sxs-lookup"><span data-stu-id="a243a-1725">japanese card bureau</span></span> 
- <span data-ttu-id="a243a-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="a243a-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="a243a-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="a243a-1727">jcb</span></span> 
- <span data-ttu-id="a243a-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="a243a-1728">kaart</span></span> 
- <span data-ttu-id="a243a-1729">kaart 編號</span><span class="sxs-lookup"><span data-stu-id="a243a-1729">kaart num</span></span> 
- <span data-ttu-id="a243a-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="a243a-1730">kaartaantal</span></span> 
- <span data-ttu-id="a243a-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="a243a-1731">kaartaantallen</span></span> 
- <span data-ttu-id="a243a-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="a243a-1732">kaarthouder</span></span> 
- <span data-ttu-id="a243a-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="a243a-1733">kaarthouders</span></span> 
- <span data-ttu-id="a243a-1734">karte</span><span class="sxs-lookup"><span data-stu-id="a243a-1734">karte</span></span>  
- <span data-ttu-id="a243a-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="a243a-1735">karteninhaber</span></span> 
- <span data-ttu-id="a243a-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="a243a-1736">karteninhabers</span></span>
- <span data-ttu-id="a243a-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="a243a-1737">kartennr</span></span> 
- <span data-ttu-id="a243a-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1738">kartennummer</span></span> 
- <span data-ttu-id="a243a-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="a243a-1739">kreditkarte</span></span> 
- <span data-ttu-id="a243a-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="a243a-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="a243a-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="a243a-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="a243a-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="a243a-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="a243a-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="a243a-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="a243a-1745">大師</span><span class="sxs-lookup"><span data-stu-id="a243a-1745">maestro</span></span> 
- <span data-ttu-id="a243a-1746">主卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1746">master card</span></span> 
- <span data-ttu-id="a243a-1747">主卡</span><span class="sxs-lookup"><span data-stu-id="a243a-1747">master cards</span></span> 
- <span data-ttu-id="a243a-1748">萬事 達</span><span class="sxs-lookup"><span data-stu-id="a243a-1748">mastercard</span></span> 
- <span data-ttu-id="a243a-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="a243a-1749">mastercards</span></span> 
- <span data-ttu-id="a243a-1750">Mc</span><span class="sxs-lookup"><span data-stu-id="a243a-1750">mc</span></span> 
- <span data-ttu-id="a243a-1751">mister 現金</span><span class="sxs-lookup"><span data-stu-id="a243a-1751">mister cash</span></span> 
- <span data-ttu-id="a243a-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="a243a-1752">n carta</span></span> 
- <span data-ttu-id="a243a-1753">憲章</span><span class="sxs-lookup"><span data-stu-id="a243a-1753">carta</span></span> 
- <span data-ttu-id="a243a-1754">無 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a243a-1754">no de tarjeta</span></span> 
- <span data-ttu-id="a243a-1755">無 do cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1755">no do cartao</span></span> 
- <span data-ttu-id="a243a-1756">無 do cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1756">no do cartão</span></span> 
- <span data-ttu-id="a243a-1757">不。</span><span class="sxs-lookup"><span data-stu-id="a243a-1757">no.</span></span> <span data-ttu-id="a243a-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a243a-1758">de tarjeta</span></span> 
- <span data-ttu-id="a243a-1759">不。</span><span class="sxs-lookup"><span data-stu-id="a243a-1759">no.</span></span> <span data-ttu-id="a243a-1760">執行 cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1760">do cartao</span></span> 
- <span data-ttu-id="a243a-1761">不。</span><span class="sxs-lookup"><span data-stu-id="a243a-1761">no.</span></span> <span data-ttu-id="a243a-1762">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1762">do cartão</span></span> 
- <span data-ttu-id="a243a-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="a243a-1763">nr carta</span></span> 
- <span data-ttu-id="a243a-1764">星期日。</span><span class="sxs-lookup"><span data-stu-id="a243a-1764">nr.</span></span> <span data-ttu-id="a243a-1765">憲章</span><span class="sxs-lookup"><span data-stu-id="a243a-1765">carta</span></span> 
- <span data-ttu-id="a243a-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="a243a-1766">numeri di scheda</span></span> 
- <span data-ttu-id="a243a-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="a243a-1767">numero carta</span></span> 
- <span data-ttu-id="a243a-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1768">numero de cartao</span></span> 
- <span data-ttu-id="a243a-1769">numero 的重複購買</span><span class="sxs-lookup"><span data-stu-id="a243a-1769">numero de carte</span></span> 
- <span data-ttu-id="a243a-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1770">numero de cartão</span></span> 
- <span data-ttu-id="a243a-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a243a-1771">numero de tarjeta</span></span>
- <span data-ttu-id="a243a-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="a243a-1772">numero della carta</span></span> 
- <span data-ttu-id="a243a-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="a243a-1773">numero di carta</span></span> 
- <span data-ttu-id="a243a-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="a243a-1774">numero di scheda</span></span> 
- <span data-ttu-id="a243a-1775">numero 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1775">numero do cartao</span></span> 
- <span data-ttu-id="a243a-1776">numero 執行 cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1776">numero do cartão</span></span> 
- <span data-ttu-id="a243a-1777">numéro 的重複購買</span><span class="sxs-lookup"><span data-stu-id="a243a-1777">numéro de carte</span></span> 
- <span data-ttu-id="a243a-1778">n º carta</span><span class="sxs-lookup"><span data-stu-id="a243a-1778">nº carta</span></span> 
- <span data-ttu-id="a243a-1779">消除購買的 n º</span><span class="sxs-lookup"><span data-stu-id="a243a-1779">nº de carte</span></span> 
- <span data-ttu-id="a243a-1780">de 照購買</span><span class="sxs-lookup"><span data-stu-id="a243a-1780">nº de la carte</span></span> 
- <span data-ttu-id="a243a-1781">消除 tarjeta 的 n º</span><span class="sxs-lookup"><span data-stu-id="a243a-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="a243a-1782">n º do cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1782">nº do cartao</span></span> 
- <span data-ttu-id="a243a-1783">n º do cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1783">nº do cartão</span></span> 
- <span data-ttu-id="a243a-1784">n º。</span><span class="sxs-lookup"><span data-stu-id="a243a-1784">nº.</span></span> <span data-ttu-id="a243a-1785">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1785">do cartão</span></span> 
- <span data-ttu-id="a243a-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1786">número de cartao</span></span> 
- <span data-ttu-id="a243a-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="a243a-1787">número de cartão</span></span> 
- <span data-ttu-id="a243a-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="a243a-1788">número de tarjeta</span></span> 
- <span data-ttu-id="a243a-1789">número 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="a243a-1789">número do cartao</span></span> 
- <span data-ttu-id="a243a-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="a243a-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="a243a-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="a243a-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="a243a-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="a243a-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="a243a-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="a243a-1793">scheda della banca</span></span> 
- <span data-ttu-id="a243a-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="a243a-1794">scheda di controllo</span></span> 
- <span data-ttu-id="a243a-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="a243a-1795">scheda di debito</span></span> 
- <span data-ttu-id="a243a-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="a243a-1796">scheda matrice</span></span> 
- <span data-ttu-id="a243a-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="a243a-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="a243a-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="a243a-1798">schede di controllo</span></span> 
- <span data-ttu-id="a243a-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="a243a-1799">schede di debito</span></span> 
- <span data-ttu-id="a243a-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="a243a-1800">schede matrici</span></span> 
- <span data-ttu-id="a243a-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="a243a-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="a243a-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="a243a-1802">scoprono le schede</span></span> 
- <span data-ttu-id="a243a-1803">獨奏</span><span class="sxs-lookup"><span data-stu-id="a243a-1803">solo</span></span> 
- <span data-ttu-id="a243a-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="a243a-1804">supporti di scheda</span></span> 
- <span data-ttu-id="a243a-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="a243a-1805">supporto di scheda</span></span> 
- <span data-ttu-id="a243a-1806">開關</span><span class="sxs-lookup"><span data-stu-id="a243a-1806">switch</span></span> 
- <span data-ttu-id="a243a-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="a243a-1807">tarjeta atm</span></span> 
- <span data-ttu-id="a243a-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1808">tarjeta credito</span></span> 
- <span data-ttu-id="a243a-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="a243a-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="a243a-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="a243a-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="a243a-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="a243a-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="a243a-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="a243a-1812">tarjeta debito</span></span> 
- <span data-ttu-id="a243a-1813">tarjeta 否</span><span class="sxs-lookup"><span data-stu-id="a243a-1813">tarjeta no</span></span>
- <span data-ttu-id="a243a-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="a243a-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="a243a-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="a243a-1815">tipo della scheda</span></span> 
- <span data-ttu-id="a243a-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="a243a-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="a243a-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="a243a-1817">scheda</span></span> 
- <span data-ttu-id="a243a-1818">v 支付</span><span class="sxs-lookup"><span data-stu-id="a243a-1818">v pay</span></span> 
- <span data-ttu-id="a243a-1819">v-支付</span><span class="sxs-lookup"><span data-stu-id="a243a-1819">v-pay</span></span> 
- <span data-ttu-id="a243a-1820">簽證</span><span class="sxs-lookup"><span data-stu-id="a243a-1820">visa</span></span> 
- <span data-ttu-id="a243a-1821">簽證加</span><span class="sxs-lookup"><span data-stu-id="a243a-1821">visa plus</span></span> 
- <span data-ttu-id="a243a-1822">簽證電</span><span class="sxs-lookup"><span data-stu-id="a243a-1822">visa electron</span></span> 
- <span data-ttu-id="a243a-1823">visto</span><span class="sxs-lookup"><span data-stu-id="a243a-1823">visto</span></span> 
- <span data-ttu-id="a243a-1824">visum</span><span class="sxs-lookup"><span data-stu-id="a243a-1824">visum</span></span> 
- <span data-ttu-id="a243a-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="a243a-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="a243a-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a243a-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="a243a-1827">卡片識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1827">card identification number</span></span>
- <span data-ttu-id="a243a-1828">名片驗證</span><span class="sxs-lookup"><span data-stu-id="a243a-1828">card verification</span></span> 
- <span data-ttu-id="a243a-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="a243a-1829">cardi la verifica</span></span> 
- <span data-ttu-id="a243a-1830">cid</span><span class="sxs-lookup"><span data-stu-id="a243a-1830">cid</span></span> 
- <span data-ttu-id="a243a-1831">貨至 seg</span><span class="sxs-lookup"><span data-stu-id="a243a-1831">cod seg</span></span> 
- <span data-ttu-id="a243a-1832">貨至 seguranca</span><span class="sxs-lookup"><span data-stu-id="a243a-1832">cod seguranca</span></span> 
- <span data-ttu-id="a243a-1833">貨至 segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1833">cod segurança</span></span> 
- <span data-ttu-id="a243a-1834">貨至 sicurezza</span><span class="sxs-lookup"><span data-stu-id="a243a-1834">cod sicurezza</span></span> 
- <span data-ttu-id="a243a-1835">Cod。</span><span class="sxs-lookup"><span data-stu-id="a243a-1835">cod.</span></span> <span data-ttu-id="a243a-1836">Seg</span><span class="sxs-lookup"><span data-stu-id="a243a-1836">seg</span></span> 
- <span data-ttu-id="a243a-1837">Cod。</span><span class="sxs-lookup"><span data-stu-id="a243a-1837">cod.</span></span> <span data-ttu-id="a243a-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="a243a-1838">seguranca</span></span> 
- <span data-ttu-id="a243a-1839">Cod。</span><span class="sxs-lookup"><span data-stu-id="a243a-1839">cod.</span></span> <span data-ttu-id="a243a-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1840">segurança</span></span> 
- <span data-ttu-id="a243a-1841">Cod。</span><span class="sxs-lookup"><span data-stu-id="a243a-1841">cod.</span></span> <span data-ttu-id="a243a-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="a243a-1842">sicurezza</span></span> 
- <span data-ttu-id="a243a-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a243a-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="a243a-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="a243a-1844">codice di verifica</span></span> 
- <span data-ttu-id="a243a-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="a243a-1845">codigo</span></span> 
- <span data-ttu-id="a243a-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="a243a-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="a243a-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1847">codigo de segurança</span></span> 
- <span data-ttu-id="a243a-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="a243a-1848">crittogramma</span></span> 
- <span data-ttu-id="a243a-1849">密碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1849">cryptogram</span></span> 
- <span data-ttu-id="a243a-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="a243a-1850">cryptogramme</span></span> 
- <span data-ttu-id="a243a-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="a243a-1851">cv2</span></span> 
- <span data-ttu-id="a243a-1852">Cvc</span><span class="sxs-lookup"><span data-stu-id="a243a-1852">cvc</span></span> 
- <span data-ttu-id="a243a-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="a243a-1853">cvc2</span></span> 
- <span data-ttu-id="a243a-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="a243a-1854">cvn</span></span> 
- <span data-ttu-id="a243a-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="a243a-1855">cvv</span></span> 
- <span data-ttu-id="a243a-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="a243a-1856">cvv2</span></span> 
- <span data-ttu-id="a243a-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="a243a-1857">cód seguranca</span></span> 
- <span data-ttu-id="a243a-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1858">cód segurança</span></span> 
- <span data-ttu-id="a243a-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="a243a-1859">cód.</span></span> <span data-ttu-id="a243a-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="a243a-1860">seguranca</span></span> 
- <span data-ttu-id="a243a-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="a243a-1861">cód.</span></span> <span data-ttu-id="a243a-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1862">segurança</span></span> 
- <span data-ttu-id="a243a-1863">código</span><span class="sxs-lookup"><span data-stu-id="a243a-1863">código</span></span> 
- <span data-ttu-id="a243a-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="a243a-1864">código de seguranca</span></span> 
- <span data-ttu-id="a243a-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="a243a-1865">código de segurança</span></span> 
- <span data-ttu-id="a243a-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="a243a-1866">de kaart controle</span></span> 
- <span data-ttu-id="a243a-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="a243a-1867">geeft nr uit</span></span> 
- <span data-ttu-id="a243a-1868">問題否</span><span class="sxs-lookup"><span data-stu-id="a243a-1868">issue no</span></span> 
- <span data-ttu-id="a243a-1869">發行編號</span><span class="sxs-lookup"><span data-stu-id="a243a-1869">issue number</span></span> 
- <span data-ttu-id="a243a-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="a243a-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="a243a-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="a243a-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="a243a-1873">kwestieaantal</span></span> 
- <span data-ttu-id="a243a-1874">不。</span><span class="sxs-lookup"><span data-stu-id="a243a-1874">no.</span></span> <span data-ttu-id="a243a-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="a243a-1875">dell'edizione</span></span> 
- <span data-ttu-id="a243a-1876">不。</span><span class="sxs-lookup"><span data-stu-id="a243a-1876">no.</span></span> <span data-ttu-id="a243a-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a243a-1877">di sicurezza</span></span> 
- <span data-ttu-id="a243a-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="a243a-1878">numero de securite</span></span> 
- <span data-ttu-id="a243a-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="a243a-1879">numero de verificacao</span></span> 
- <span data-ttu-id="a243a-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="a243a-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="a243a-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="a243a-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="a243a-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="a243a-1882">scheda</span></span> 
- <span data-ttu-id="a243a-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a243a-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="a243a-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="a243a-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="a243a-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="a243a-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="a243a-1886">n º autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a243a-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="a243a-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="a243a-1887">número de verificação</span></span> 
- <span data-ttu-id="a243a-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="a243a-1888">perno il blocco</span></span> 
- <span data-ttu-id="a243a-1889">pin 區區塊</span><span class="sxs-lookup"><span data-stu-id="a243a-1889">pin block</span></span> 
- <span data-ttu-id="a243a-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="a243a-1890">prufziffer</span></span> 
- <span data-ttu-id="a243a-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="a243a-1891">prüfziffer</span></span> 
- <span data-ttu-id="a243a-1892">安全性代碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1892">security code</span></span> 
- <span data-ttu-id="a243a-1893">安全性否</span><span class="sxs-lookup"><span data-stu-id="a243a-1893">security no</span></span> 
- <span data-ttu-id="a243a-1894">安全性號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1894">security number</span></span> 
- <span data-ttu-id="a243a-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="a243a-1895">sicherheits kode</span></span> 
- <span data-ttu-id="a243a-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="a243a-1896">sicherheitscode</span></span> 
- <span data-ttu-id="a243a-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="a243a-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="a243a-1898">speldblok</span></span> 
- <span data-ttu-id="a243a-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="a243a-1899">veiligheid nr</span></span> 
- <span data-ttu-id="a243a-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="a243a-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="a243a-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="a243a-1901">veiligheidscode</span></span> 
- <span data-ttu-id="a243a-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="a243a-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="a243a-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="a243a-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a243a-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="a243a-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="a243a-1905">ablauf</span></span> 
- <span data-ttu-id="a243a-1906">資料 de expiracao</span><span class="sxs-lookup"><span data-stu-id="a243a-1906">data de expiracao</span></span> 
- <span data-ttu-id="a243a-1907">資料 de expiração</span><span class="sxs-lookup"><span data-stu-id="a243a-1907">data de expiração</span></span> 
- <span data-ttu-id="a243a-1908">資料 del exp</span><span class="sxs-lookup"><span data-stu-id="a243a-1908">data del exp</span></span> 
- <span data-ttu-id="a243a-1909">資料 di exp</span><span class="sxs-lookup"><span data-stu-id="a243a-1909">data di exp</span></span> 
- <span data-ttu-id="a243a-1910">資料 di scadenza</span><span class="sxs-lookup"><span data-stu-id="a243a-1910">data di scadenza</span></span> 
- <span data-ttu-id="a243a-1911">資料 em mail.que expira</span><span class="sxs-lookup"><span data-stu-id="a243a-1911">data em que expira</span></span> 
- <span data-ttu-id="a243a-1912">資料 scad</span><span class="sxs-lookup"><span data-stu-id="a243a-1912">data scad</span></span> 
- <span data-ttu-id="a243a-1913">資料 scadenza</span><span class="sxs-lookup"><span data-stu-id="a243a-1913">data scadenza</span></span> 
- <span data-ttu-id="a243a-1914">日期 de validité</span><span class="sxs-lookup"><span data-stu-id="a243a-1914">date de validité</span></span> 
- <span data-ttu-id="a243a-1915">基準 afloop</span><span class="sxs-lookup"><span data-stu-id="a243a-1915">datum afloop</span></span> 
- <span data-ttu-id="a243a-1916">基準 van exp</span><span class="sxs-lookup"><span data-stu-id="a243a-1916">datum van exp</span></span> 
- <span data-ttu-id="a243a-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="a243a-1917">de afloop</span></span> 
- <span data-ttu-id="a243a-1918">espira</span><span class="sxs-lookup"><span data-stu-id="a243a-1918">espira</span></span> 
- <span data-ttu-id="a243a-1919">espira</span><span class="sxs-lookup"><span data-stu-id="a243a-1919">espira</span></span> 
- <span data-ttu-id="a243a-1920">到期日</span><span class="sxs-lookup"><span data-stu-id="a243a-1920">exp date</span></span> 
- <span data-ttu-id="a243a-1921">exp 基準</span><span class="sxs-lookup"><span data-stu-id="a243a-1921">exp datum</span></span> 
- <span data-ttu-id="a243a-1922">到期</span><span class="sxs-lookup"><span data-stu-id="a243a-1922">expiration</span></span> 
- <span data-ttu-id="a243a-1923">到期</span><span class="sxs-lookup"><span data-stu-id="a243a-1923">expire</span></span> 
- <span data-ttu-id="a243a-1924">到期</span><span class="sxs-lookup"><span data-stu-id="a243a-1924">expires</span></span> 
- <span data-ttu-id="a243a-1925">屆滿</span><span class="sxs-lookup"><span data-stu-id="a243a-1925">expiry</span></span> 
- <span data-ttu-id="a243a-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="a243a-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="a243a-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="a243a-1927">fecha de venc</span></span> 
- <span data-ttu-id="a243a-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="a243a-1928">gultig bis</span></span> 
- <span data-ttu-id="a243a-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a243a-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="a243a-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="a243a-1930">gültig bis</span></span> 
- <span data-ttu-id="a243a-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="a243a-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="a243a-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="a243a-1932">la scadenza</span></span> 
- <span data-ttu-id="a243a-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="a243a-1933">scadenza</span></span> 
- <span data-ttu-id="a243a-1934">valable</span><span class="sxs-lookup"><span data-stu-id="a243a-1934">valable</span></span> 
- <span data-ttu-id="a243a-1935">validade</span><span class="sxs-lookup"><span data-stu-id="a243a-1935">validade</span></span> 
- <span data-ttu-id="a243a-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="a243a-1936">valido hasta</span></span> 
- <span data-ttu-id="a243a-1937">勇氣</span><span class="sxs-lookup"><span data-stu-id="a243a-1937">valor</span></span> 
- <span data-ttu-id="a243a-1938">venc</span><span class="sxs-lookup"><span data-stu-id="a243a-1938">venc</span></span> 
- <span data-ttu-id="a243a-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="a243a-1939">vencimento</span></span> 
- <span data-ttu-id="a243a-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="a243a-1940">vencimiento</span></span> 
- <span data-ttu-id="a243a-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="a243a-1941">verloopt</span></span> 
- <span data-ttu-id="a243a-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="a243a-1942">vervaldag</span></span> 
- <span data-ttu-id="a243a-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="a243a-1943">vervaldatum</span></span> 
- <span data-ttu-id="a243a-1944">vto</span><span class="sxs-lookup"><span data-stu-id="a243a-1944">vto</span></span> 
- <span data-ttu-id="a243a-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="a243a-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="a243a-1946">歐盟駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1946">EU Driver's License Number</span></span>

<span data-ttu-id="a243a-1947">若要深入瞭解，請參閱[歐盟駕駛執照號碼的敏感資訊類型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="a243a-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="a243a-1948">歐盟國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1948">EU National Identification Number</span></span>

<span data-ttu-id="a243a-1949">若要深入瞭解，請參閱《[歐盟全國身分識別號碼機密資訊類型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="a243a-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="a243a-1950">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1950">EU Passport Number</span></span>

<span data-ttu-id="a243a-1951">若要深入瞭解，請參閱[歐盟護照號碼機密資訊類型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="a243a-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="a243a-1952">歐盟社會安全號碼或同等識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="a243a-1953">若要深入瞭解，請參閱[歐盟社會安全號碼或對等識別碼機密資訊類型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="a243a-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="a243a-1954">歐盟納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="a243a-1955">若要深入瞭解，請參閱[歐盟納稅識別號碼機密資訊類型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="a243a-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="a243a-1956">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1957">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1957">Format</span></span>

<span data-ttu-id="a243a-1958">六位數加上一個表示世紀的字元加上三個數字加上檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1959">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1959">Pattern</span></span>

<span data-ttu-id="a243a-1960">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="a243a-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a243a-1961">DDMMYY 出生日期格式格式的六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="a243a-1962">世紀標記（'-'、' + ' 或 ' a '）</span><span class="sxs-lookup"><span data-stu-id="a243a-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="a243a-1963">三位數的個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="a243a-1964">一種檢查碼的數位或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1965">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1965">Checksum</span></span>

<span data-ttu-id="a243a-1966">是</span><span class="sxs-lookup"><span data-stu-id="a243a-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1967">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1967">Definition</span></span>

<span data-ttu-id="a243a-1968">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1969">函數 Func_finnish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1970">會找到來自 Keyword_finnish_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="a243a-1971">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-1972">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1972">Keywords</span></span>

- <span data-ttu-id="a243a-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="a243a-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="a243a-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="a243a-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="a243a-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="a243a-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="a243a-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="a243a-1976">Personbeteckning</span></span>
- <span data-ttu-id="a243a-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="a243a-1978">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1978">Finland Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1979">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1979">Format</span></span>
<span data-ttu-id="a243a-1980">九個字母和數位的組合</span><span class="sxs-lookup"><span data-stu-id="a243a-1980">Combination of nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1981">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1981">Pattern</span></span>
<span data-ttu-id="a243a-1982">九個字母和數位的組合：兩個字母（不區分大小寫）七位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1982">Combination of nine letters and digits: Two letters (not case sensitive) Seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1983">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1983">Checksum</span></span>
<span data-ttu-id="a243a-1984">否</span><span class="sxs-lookup"><span data-stu-id="a243a-1984">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-1985">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-1985">Definition</span></span>
<span data-ttu-id="a243a-1986">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-1986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-1987">正則運算式 Regex_finland_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-1987">The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-1988">會找到來自 Keyword_finland_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-1988">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
```xml
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="a243a-1989">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-1989">Keywords</span></span>
- <span data-ttu-id="a243a-1990">Keyword_finland_passport_number</span><span class="sxs-lookup"><span data-stu-id="a243a-1990">Keyword_finland_passport_number</span></span>
- <span data-ttu-id="a243a-1991">護照</span><span class="sxs-lookup"><span data-stu-id="a243a-1991">Passport</span></span>
- <span data-ttu-id="a243a-1992">Passi</span><span class="sxs-lookup"><span data-stu-id="a243a-1992">Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="a243a-1993">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="a243a-1993">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-1994">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-1994">Format</span></span>

<span data-ttu-id="a243a-1995">12位數</span><span class="sxs-lookup"><span data-stu-id="a243a-1995">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-1996">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-1996">Pattern</span></span>

<span data-ttu-id="a243a-1997">12位數與折扣類似的模式，例如法國電話號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-1997">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-1998">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-1998">Checksum</span></span>

<span data-ttu-id="a243a-1999">否</span><span class="sxs-lookup"><span data-stu-id="a243a-1999">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2000">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2000">Definition</span></span>

<span data-ttu-id="a243a-2001">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2001">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2002">函數 Func_french_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2002">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2003">下列專案中至少有一個為真：</span><span class="sxs-lookup"><span data-stu-id="a243a-2003">At least one of the following is true:</span></span>
- <span data-ttu-id="a243a-2004">會找到來自 Keyword_french_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2004">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="a243a-2005">函數 Func_eu_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a243a-2005">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2006">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2006">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="a243a-2007">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a243a-2007">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="a243a-2008">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2008">drivers licence</span></span>
- <span data-ttu-id="a243a-2009">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2009">drivers license</span></span>
- <span data-ttu-id="a243a-2010">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2010">driving licence</span></span>
- <span data-ttu-id="a243a-2011">駕照</span><span class="sxs-lookup"><span data-stu-id="a243a-2011">driving license</span></span>
- <span data-ttu-id="a243a-2012">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="a243a-2012">permis de conduire</span></span>
- <span data-ttu-id="a243a-2013">許可號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2013">licence number</span></span>
- <span data-ttu-id="a243a-2014">授權號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2014">license number</span></span>
- <span data-ttu-id="a243a-2015">許可證號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2015">licence numbers</span></span>
- <span data-ttu-id="a243a-2016">授權號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2016">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="a243a-2017">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="a243a-2017">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2018">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2018">Format</span></span>

<span data-ttu-id="a243a-2019">12位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2019">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2020">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2020">Pattern</span></span>

<span data-ttu-id="a243a-2021">12位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2021">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2022">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2022">Checksum</span></span>

<span data-ttu-id="a243a-2023">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2023">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2024">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2024">Definition</span></span>

<span data-ttu-id="a243a-2025">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2025">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2026">正則運算式 Regex_france_cni 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2026">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2027">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2027">Keywords</span></span>

<span data-ttu-id="a243a-2028">無</span><span class="sxs-lookup"><span data-stu-id="a243a-2028">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="a243a-2029">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2029">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2030">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2030">Format</span></span>

<span data-ttu-id="a243a-2031">九個數字和字母</span><span class="sxs-lookup"><span data-stu-id="a243a-2031">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2032">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2032">Pattern</span></span>

<span data-ttu-id="a243a-2033">九個數字和字母：</span><span class="sxs-lookup"><span data-stu-id="a243a-2033">Nine digits and letters:</span></span>
- <span data-ttu-id="a243a-2034">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2034">Two digits</span></span> 
- <span data-ttu-id="a243a-2035">兩個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2035">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="a243a-2036">五位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2036">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2037">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2037">Checksum</span></span>

<span data-ttu-id="a243a-2038">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2038">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2039">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2039">Definition</span></span>

<span data-ttu-id="a243a-2040">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2040">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2041">函數 Func_fr_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2041">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2042">會找到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2042">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2043">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2043">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a243a-2044">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a243a-2044">Keyword_passport</span></span>

- <span data-ttu-id="a243a-2045">護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2045">Passport Number</span></span>
- <span data-ttu-id="a243a-2046">護照否</span><span class="sxs-lookup"><span data-stu-id="a243a-2046">Passport No</span></span>
- <span data-ttu-id="a243a-2047">護照#</span><span class="sxs-lookup"><span data-stu-id="a243a-2047">Passport #</span></span>
- <span data-ttu-id="a243a-2048">護照#</span><span class="sxs-lookup"><span data-stu-id="a243a-2048">Passport#</span></span>
- <span data-ttu-id="a243a-2049">PassportID</span><span class="sxs-lookup"><span data-stu-id="a243a-2049">PassportID</span></span>
- <span data-ttu-id="a243a-2050">Passportno</span><span class="sxs-lookup"><span data-stu-id="a243a-2050">Passportno</span></span>
- <span data-ttu-id="a243a-2051">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-2051">passportnumber</span></span>
- <span data-ttu-id="a243a-2052">パスポート</span><span class="sxs-lookup"><span data-stu-id="a243a-2052">パスポート</span></span>
- <span data-ttu-id="a243a-2053">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2053">パスポート番号</span></span>
- <span data-ttu-id="a243a-2054">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a243a-2054">パスポートのNum</span></span>
- <span data-ttu-id="a243a-2055">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="a243a-2055">パスポート ＃</span></span> 
- <span data-ttu-id="a243a-2056">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a243a-2056">Numéro de passeport</span></span>
- <span data-ttu-id="a243a-2057">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a243a-2057">Passeport n °</span></span>
- <span data-ttu-id="a243a-2058">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="a243a-2058">Passeport Non</span></span>
- <span data-ttu-id="a243a-2059">Passeport#</span><span class="sxs-lookup"><span data-stu-id="a243a-2059">Passeport #</span></span>
- <span data-ttu-id="a243a-2060">Passeport#</span><span class="sxs-lookup"><span data-stu-id="a243a-2060">Passeport#</span></span>
- <span data-ttu-id="a243a-2061">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a243a-2061">PasseportNon</span></span>
- <span data-ttu-id="a243a-2062">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a243a-2062">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="a243a-2063">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="a243a-2063">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2064">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2064">Format</span></span>

<span data-ttu-id="a243a-2065">15位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2065">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2066">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2066">Pattern</span></span>

<span data-ttu-id="a243a-2067">必須符合下列其中一種模式：</span><span class="sxs-lookup"><span data-stu-id="a243a-2067">Must match one of two patterns:</span></span>
- <span data-ttu-id="a243a-2068">13位數後接一個空格後接兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2068">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="a243a-2069">或</span><span class="sxs-lookup"><span data-stu-id="a243a-2069">or</span></span>
- <span data-ttu-id="a243a-2070">15個連續數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2070">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2071">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2071">Checksum</span></span>

<span data-ttu-id="a243a-2072">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2072">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2073">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2073">Definition</span></span>

<span data-ttu-id="a243a-2074">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2074">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2075">函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2075">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2076">會找到來自 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2076">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="a243a-2077">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2077">The checksum passes.</span></span>

<span data-ttu-id="a243a-2078">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2078">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2079">函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2079">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2080">找不到 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2080">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="a243a-2081">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2081">The checksum passes.</span></span>

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2082">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2082">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="a243a-2083">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="a243a-2083">Keyword_fr_insee</span></span>

- <span data-ttu-id="a243a-2084">insee</span><span class="sxs-lookup"><span data-stu-id="a243a-2084">insee</span></span>
- <span data-ttu-id="a243a-2085">securité sociale</span><span class="sxs-lookup"><span data-stu-id="a243a-2085">securité sociale</span></span>
- <span data-ttu-id="a243a-2086">securite sociale</span><span class="sxs-lookup"><span data-stu-id="a243a-2086">securite sociale</span></span>
- <span data-ttu-id="a243a-2087">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2087">national id</span></span>
- <span data-ttu-id="a243a-2088">本國身分識別</span><span class="sxs-lookup"><span data-stu-id="a243a-2088">national identification</span></span>
- <span data-ttu-id="a243a-2089">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="a243a-2089">numéro d'identité</span></span>
- <span data-ttu-id="a243a-2090">無 d'identité</span><span class="sxs-lookup"><span data-stu-id="a243a-2090">no d'identité</span></span>
- <span data-ttu-id="a243a-2091">不。</span><span class="sxs-lookup"><span data-stu-id="a243a-2091">no.</span></span> <span data-ttu-id="a243a-2092">d'identité</span><span class="sxs-lookup"><span data-stu-id="a243a-2092">d'identité</span></span>
- <span data-ttu-id="a243a-2093">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="a243a-2093">numero d'identite</span></span>
- <span data-ttu-id="a243a-2094">無 d'identite</span><span class="sxs-lookup"><span data-stu-id="a243a-2094">no d'identite</span></span>
- <span data-ttu-id="a243a-2095">不。</span><span class="sxs-lookup"><span data-stu-id="a243a-2095">no.</span></span> <span data-ttu-id="a243a-2096">d'identite</span><span class="sxs-lookup"><span data-stu-id="a243a-2096">d'identite</span></span>
- <span data-ttu-id="a243a-2097">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2097">social security number</span></span>
- <span data-ttu-id="a243a-2098">社會安全性碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2098">social security code</span></span>
- <span data-ttu-id="a243a-2099">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2099">social insurance number</span></span>
- <span data-ttu-id="a243a-2100">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="a243a-2100">le numéro d'identification nationale</span></span>
- <span data-ttu-id="a243a-2101">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="a243a-2101">d'identité nationale</span></span>
- <span data-ttu-id="a243a-2102">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="a243a-2102">numéro de sécurité sociale</span></span>
- <span data-ttu-id="a243a-2103">le 程式碼 de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="a243a-2103">le code de la sécurité sociale</span></span>
- <span data-ttu-id="a243a-2104">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="a243a-2104">numéro d'assurance sociale</span></span>
- <span data-ttu-id="a243a-2105">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="a243a-2105">numéro de sécu</span></span>
- <span data-ttu-id="a243a-2106">程式碼 sécu</span><span class="sxs-lookup"><span data-stu-id="a243a-2106">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="a243a-2107">德文駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2107">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2108">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2108">Format</span></span>

<span data-ttu-id="a243a-2109">11位數和字母的組合</span><span class="sxs-lookup"><span data-stu-id="a243a-2109">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2110">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2110">Pattern</span></span>

<span data-ttu-id="a243a-2111">11個數字和字母（不區分大小寫）：</span><span class="sxs-lookup"><span data-stu-id="a243a-2111">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="a243a-2112">一個數位或字母</span><span class="sxs-lookup"><span data-stu-id="a243a-2112">A digit or letter</span></span> 
- <span data-ttu-id="a243a-2113">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2113">Two digits</span></span> 
- <span data-ttu-id="a243a-2114">六個數字或字母</span><span class="sxs-lookup"><span data-stu-id="a243a-2114">Six digits or letters</span></span> 
- <span data-ttu-id="a243a-2115">一個數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2115">A digit</span></span> 
- <span data-ttu-id="a243a-2116">一個數位或字母</span><span class="sxs-lookup"><span data-stu-id="a243a-2116">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2117">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2117">Checksum</span></span>

<span data-ttu-id="a243a-2118">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2118">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2119">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2119">Definition</span></span>

<span data-ttu-id="a243a-2120">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2120">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2121">函數 Func_german_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2121">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2122">下列專案中至少有一個為真：</span><span class="sxs-lookup"><span data-stu-id="a243a-2122">At least one of the following is true:</span></span>
    - <span data-ttu-id="a243a-2123">會找到來自 Keyword_german_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2123">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="a243a-2124">會找到來自 Keyword_german_drivers_license_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2124">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="a243a-2125">會找到來自 Keyword_german_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2125">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="a243a-2126">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2126">The checksum passes.</span></span>

```xml
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2127">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2127">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="a243a-2128">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2128">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="a243a-2129">Führerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2129">Führerschein</span></span>
- <span data-ttu-id="a243a-2130">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2130">Fuhrerschein</span></span>
- <span data-ttu-id="a243a-2131">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2131">Fuehrerschein</span></span>
- <span data-ttu-id="a243a-2132">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-2132">Führerscheinnummer</span></span>
- <span data-ttu-id="a243a-2133">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-2133">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="a243a-2134">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-2134">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="a243a-2135">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="a243a-2135">Führerschein-</span></span> 
- <span data-ttu-id="a243a-2136">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="a243a-2136">Fuhrerschein-</span></span> 
- <span data-ttu-id="a243a-2137">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="a243a-2137">Fuehrerschein-</span></span> 
- <span data-ttu-id="a243a-2138">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a243a-2138">FührerscheinnummerNr</span></span>
- <span data-ttu-id="a243a-2139">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a243a-2139">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="a243a-2140">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a243a-2140">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="a243a-2141">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2141">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="a243a-2142">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2142">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="a243a-2143">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2143">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="a243a-2144">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="a243a-2144">Führerschein- Nr</span></span>
- <span data-ttu-id="a243a-2145">Fuhrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="a243a-2145">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="a243a-2146">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="a243a-2146">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="a243a-2147">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2147">Führerschein- Klasse</span></span> 
- <span data-ttu-id="a243a-2148">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2148">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="a243a-2149">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2149">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="a243a-2150">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a243a-2150">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="a243a-2151">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a243a-2151">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="a243a-2152">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a243a-2152">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="a243a-2153">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2153">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a243a-2154">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2154">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a243a-2155">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2155">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a243a-2156">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="a243a-2156">Führerschein- Nr</span></span> 
- <span data-ttu-id="a243a-2157">Fuhrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="a243a-2157">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="a243a-2158">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="a243a-2158">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="a243a-2159">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2159">Führerschein- Klasse</span></span> 
- <span data-ttu-id="a243a-2160">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2160">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="a243a-2161">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2161">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="a243a-2162">Dl</span><span class="sxs-lookup"><span data-stu-id="a243a-2162">DL</span></span> 
- <span data-ttu-id="a243a-2163">Dls</span><span class="sxs-lookup"><span data-stu-id="a243a-2163">DLS</span></span>
- <span data-ttu-id="a243a-2164">Driv 許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2164">Driv Lic</span></span> 
- <span data-ttu-id="a243a-2165">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="a243a-2165">Driv Licen</span></span> 
- <span data-ttu-id="a243a-2166">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2166">Driv License</span></span>
- <span data-ttu-id="a243a-2167">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2167">Driv Licenses</span></span> 
- <span data-ttu-id="a243a-2168">Driv 許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2168">Driv Licence</span></span> 
- <span data-ttu-id="a243a-2169">Driv 許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2169">Driv Licences</span></span> 
- <span data-ttu-id="a243a-2170">Driv 許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2170">Driv Lic</span></span> 
- <span data-ttu-id="a243a-2171">驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="a243a-2171">Driver Licen</span></span> 
- <span data-ttu-id="a243a-2172">駕照</span><span class="sxs-lookup"><span data-stu-id="a243a-2172">Driver License</span></span> 
- <span data-ttu-id="a243a-2173">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2173">Driver Licenses</span></span> 
- <span data-ttu-id="a243a-2174">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2174">Driver Licence</span></span> 
- <span data-ttu-id="a243a-2175">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2175">Driver Licences</span></span> 
- <span data-ttu-id="a243a-2176">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-2176">Drivers Lic</span></span> 
- <span data-ttu-id="a243a-2177">驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="a243a-2177">Drivers Licen</span></span> 
- <span data-ttu-id="a243a-2178">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2178">Drivers License</span></span> 
- <span data-ttu-id="a243a-2179">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2179">Drivers Licenses</span></span> 
- <span data-ttu-id="a243a-2180">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2180">Drivers Licence</span></span> 
- <span data-ttu-id="a243a-2181">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2181">Drivers Licences</span></span> 
- <span data-ttu-id="a243a-2182">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-2182">Driver's Lic</span></span> 
- <span data-ttu-id="a243a-2183">驅動程式的 Licen</span><span class="sxs-lookup"><span data-stu-id="a243a-2183">Driver's Licen</span></span> 
- <span data-ttu-id="a243a-2184">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-2184">Driver's License</span></span> 
- <span data-ttu-id="a243a-2185">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-2185">Driver's Licenses</span></span> 
- <span data-ttu-id="a243a-2186">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-2186">Driver's Licence</span></span> 
- <span data-ttu-id="a243a-2187">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-2187">Driver's Licences</span></span> 
- <span data-ttu-id="a243a-2188">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2188">Driving Lic</span></span> 
- <span data-ttu-id="a243a-2189">驅車 Licen</span><span class="sxs-lookup"><span data-stu-id="a243a-2189">Driving Licen</span></span> 
- <span data-ttu-id="a243a-2190">駕照</span><span class="sxs-lookup"><span data-stu-id="a243a-2190">Driving License</span></span> 
- <span data-ttu-id="a243a-2191">駕駛授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2191">Driving Licenses</span></span> 
- <span data-ttu-id="a243a-2192">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2192">Driving Licence</span></span> 
- <span data-ttu-id="a243a-2193">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2193">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="a243a-2194">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="a243a-2194">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="a243a-2195">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2195">Nr-Führerschein</span></span> 
- <span data-ttu-id="a243a-2196">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2196">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="a243a-2197">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2197">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="a243a-2198">非 Führerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2198">No-Führerschein</span></span> 
- <span data-ttu-id="a243a-2199">非 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2199">No-Fuhrerschein</span></span> 
- <span data-ttu-id="a243a-2200">非 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2200">No-Fuehrerschein</span></span> 
- <span data-ttu-id="a243a-2201">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2201">N-Führerschein</span></span> 
- <span data-ttu-id="a243a-2202">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2202">N-Fuhrerschein</span></span> 
- <span data-ttu-id="a243a-2203">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2203">N-Fuehrerschein</span></span>
- <span data-ttu-id="a243a-2204">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2204">Nr-Führerschein</span></span> 
- <span data-ttu-id="a243a-2205">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2205">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="a243a-2206">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2206">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="a243a-2207">非 Führerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2207">No-Führerschein</span></span> 
- <span data-ttu-id="a243a-2208">非 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2208">No-Fuhrerschein</span></span> 
- <span data-ttu-id="a243a-2209">非 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2209">No-Fuehrerschein</span></span> 
- <span data-ttu-id="a243a-2210">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2210">N-Führerschein</span></span> 
- <span data-ttu-id="a243a-2211">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2211">N-Fuhrerschein</span></span> 
- <span data-ttu-id="a243a-2212">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a243a-2212">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="a243a-2213">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a243a-2213">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="a243a-2214">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="a243a-2214">ausstellungsdatum</span></span>
- <span data-ttu-id="a243a-2215">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="a243a-2215">ausstellungsort</span></span>
- <span data-ttu-id="a243a-2216">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="a243a-2216">ausstellende behöde</span></span>
- <span data-ttu-id="a243a-2217">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="a243a-2217">ausstellende behorde</span></span>
- <span data-ttu-id="a243a-2218">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="a243a-2218">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="a243a-2219">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2219">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2220">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2220">Format</span></span>

<span data-ttu-id="a243a-2221">10位數或字母</span><span class="sxs-lookup"><span data-stu-id="a243a-2221">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2222">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2222">Pattern</span></span>

<span data-ttu-id="a243a-2223">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="a243a-2223">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a243a-2224">第一個字元是來自此集合的數位或字母（C、F、G、H、J、K）</span><span class="sxs-lookup"><span data-stu-id="a243a-2224">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="a243a-2225">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2225">Three digits</span></span> 
- <span data-ttu-id="a243a-2226">來自此集合的五個數字或字母（C、-H、J-N、P、R、T、V-Z）</span><span class="sxs-lookup"><span data-stu-id="a243a-2226">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="a243a-2227">一個數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2227">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2228">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2228">Checksum</span></span>

<span data-ttu-id="a243a-2229">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2229">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2230">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2230">Definition</span></span>

<span data-ttu-id="a243a-2231">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2231">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2232">函數 Func_german_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2232">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2233">找到任何五個關鍵字清單中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2233">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="a243a-2234">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2234">The checksum passes.</span></span>

<span data-ttu-id="a243a-2235">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2236">函數 Func_german_passport_data 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2236">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2237">找到任何五個關鍵字清單中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2237">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="a243a-2238">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2238">The checksum passes.</span></span>

```xml
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2239">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2239">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="a243a-2240">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="a243a-2240">Keyword_german_passport</span></span>

- <span data-ttu-id="a243a-2241">reisepass</span><span class="sxs-lookup"><span data-stu-id="a243a-2241">reisepass</span></span>
- <span data-ttu-id="a243a-2242">reisepasse</span><span class="sxs-lookup"><span data-stu-id="a243a-2242">reisepasse</span></span>
- <span data-ttu-id="a243a-2243">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-2243">reisepassnummer</span></span>
- <span data-ttu-id="a243a-2244">護照</span><span class="sxs-lookup"><span data-stu-id="a243a-2244">passport</span></span>
- <span data-ttu-id="a243a-2245">護照</span><span class="sxs-lookup"><span data-stu-id="a243a-2245">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="a243a-2246">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="a243a-2246">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="a243a-2247">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="a243a-2247">geburtsdatum</span></span>
- <span data-ttu-id="a243a-2248">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="a243a-2248">ausstellungsdatum</span></span>
- <span data-ttu-id="a243a-2249">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="a243a-2249">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="a243a-2250">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2250">Keyword_german_passport_number</span></span>

<span data-ttu-id="a243a-2251">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="a243a-2251">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="a243a-2252">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="a243a-2252">Keyword_german_passport1</span></span>

<span data-ttu-id="a243a-2253">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="a243a-2253">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="a243a-2254">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="a243a-2254">Keyword_german_passport2</span></span>

<span data-ttu-id="a243a-2255">bnationalit</span><span class="sxs-lookup"><span data-stu-id="a243a-2255">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="a243a-2256">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2256">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2257">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2257">Format</span></span>

<span data-ttu-id="a243a-2258">自11月2010：9個字母和數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2258">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="a243a-2259">從1年4月1987至31年10月2010：10位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2259">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2260">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2260">Pattern</span></span>

<span data-ttu-id="a243a-2261">自11月1日2010：</span><span class="sxs-lookup"><span data-stu-id="a243a-2261">Since 1 November 2010:</span></span>
- <span data-ttu-id="a243a-2262">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2262">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="a243a-2263">八位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2263">Eight digits</span></span>

<span data-ttu-id="a243a-2264">從1年4月1987至31年10月2010：</span><span class="sxs-lookup"><span data-stu-id="a243a-2264">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="a243a-2265">10位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2265">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2266">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2266">Checksum</span></span>

<span data-ttu-id="a243a-2267">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2267">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2268">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2268">Definition</span></span>

<span data-ttu-id="a243a-2269">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2269">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2270">正則運算式 Regex_germany_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2270">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2271">會找到來自 Keyword_germany_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2271">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2272">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2272">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="a243a-2273">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="a243a-2273">Keyword_germany_id_card</span></span>

- <span data-ttu-id="a243a-2274">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2274">Identity Card</span></span>
- <span data-ttu-id="a243a-2275">ID</span><span class="sxs-lookup"><span data-stu-id="a243a-2275">ID</span></span>
- <span data-ttu-id="a243a-2276">識別</span><span class="sxs-lookup"><span data-stu-id="a243a-2276">Identification</span></span>
- <span data-ttu-id="a243a-2277">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="a243a-2277">Personalausweis</span></span>
- <span data-ttu-id="a243a-2278">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-2278">Identifizierungsnummer</span></span>
- <span data-ttu-id="a243a-2279">Ausweis</span><span class="sxs-lookup"><span data-stu-id="a243a-2279">Ausweis</span></span>
- <span data-ttu-id="a243a-2280">Identifikation</span><span class="sxs-lookup"><span data-stu-id="a243a-2280">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="a243a-2281">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-2281">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2282">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2282">Format</span></span>

<span data-ttu-id="a243a-2283">7-8 字母和數位的組合，加上破折號</span><span class="sxs-lookup"><span data-stu-id="a243a-2283">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2284">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2284">Pattern</span></span>

<span data-ttu-id="a243a-2285">七個字母和數位（舊格式）：</span><span class="sxs-lookup"><span data-stu-id="a243a-2285">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="a243a-2286">一個字母（希臘文字母表的任何字母）</span><span class="sxs-lookup"><span data-stu-id="a243a-2286">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="a243a-2287">虛線</span><span class="sxs-lookup"><span data-stu-id="a243a-2287">A dash</span></span> 
- <span data-ttu-id="a243a-2288">六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2288">Six digits</span></span>

<span data-ttu-id="a243a-2289">八個字母和數位（新格式）：</span><span class="sxs-lookup"><span data-stu-id="a243a-2289">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="a243a-2290">兩個字母大寫字元會同時出現于希臘字母和拉丁字母表中（ABEZHIKMNOPTYX）</span><span class="sxs-lookup"><span data-stu-id="a243a-2290">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="a243a-2291">虛線</span><span class="sxs-lookup"><span data-stu-id="a243a-2291">A dash</span></span> 
- <span data-ttu-id="a243a-2292">六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2292">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2293">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2293">Checksum</span></span>

<span data-ttu-id="a243a-2294">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2294">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2295">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2295">Definition</span></span>

<span data-ttu-id="a243a-2296">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2297">正則運算式 Regex_greece_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2297">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2298">會找到來自 Keyword_greece_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2298">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2299">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2299">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="a243a-2300">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="a243a-2300">Keyword_greece_id_card</span></span>

- <span data-ttu-id="a243a-2301">希臘文身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-2301">Greek identity Card</span></span>
- <span data-ttu-id="a243a-2302">Tautotita</span><span class="sxs-lookup"><span data-stu-id="a243a-2302">Tautotita</span></span>
- <span data-ttu-id="a243a-2303">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="a243a-2303">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="a243a-2304">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="a243a-2304">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="a243a-2305">中國香港身分識別卡（HKID）號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2305">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2306">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2306">Format</span></span>

<span data-ttu-id="a243a-2307">8-9 字母和數位的組合，以及最後一個字元兩邊的 optional 括弧</span><span class="sxs-lookup"><span data-stu-id="a243a-2307">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2308">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2308">Pattern</span></span>

<span data-ttu-id="a243a-2309">8-9 個字母的組合：</span><span class="sxs-lookup"><span data-stu-id="a243a-2309">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="a243a-2310">1-2 個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2310">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="a243a-2311">六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2311">Six digits</span></span> 
- <span data-ttu-id="a243a-2312">最後一個字元（任何數位或字母 A），也就是檢查碼，也可以以括弧括住。</span><span class="sxs-lookup"><span data-stu-id="a243a-2312">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2313">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2313">Checksum</span></span>

<span data-ttu-id="a243a-2314">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2314">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2315">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2315">Definition</span></span>

<span data-ttu-id="a243a-2316">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2317">函數 Func_hong_kong_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2317">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2318">會找到來自 Keyword_hong_kong_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2318">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="a243a-2319">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2319">The checksum passes.</span></span>

<span data-ttu-id="a243a-2320">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2320">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2321">函數 Func_hong_kong_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2321">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2322">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2322">The checksum passes.</span></span>

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2323">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2323">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="a243a-2324">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="a243a-2324">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="a243a-2325">中國香港身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-2325">hong kong identity card</span></span>
- <span data-ttu-id="a243a-2326">HKIDC</span><span class="sxs-lookup"><span data-stu-id="a243a-2326">HKIDC</span></span>
- <span data-ttu-id="a243a-2327">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2327">id card</span></span>
- <span data-ttu-id="a243a-2328">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2328">identity card</span></span>
- <span data-ttu-id="a243a-2329">hk 身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-2329">hk identity card</span></span>
- <span data-ttu-id="a243a-2330">中國香港號</span><span class="sxs-lookup"><span data-stu-id="a243a-2330">hong kong id</span></span>
- <span data-ttu-id="a243a-2331">香港身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2331">香港身份證</span></span>
- <span data-ttu-id="a243a-2332">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2332">香港永久性居民身份證</span></span>
- <span data-ttu-id="a243a-2333">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2333">身份證</span></span>
- <span data-ttu-id="a243a-2334">身份証</span><span class="sxs-lookup"><span data-stu-id="a243a-2334">身份証</span></span>
- <span data-ttu-id="a243a-2335">身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-2335">身分證</span></span>
- <span data-ttu-id="a243a-2336">身分証</span><span class="sxs-lookup"><span data-stu-id="a243a-2336">身分証</span></span>
- <span data-ttu-id="a243a-2337">香港身份証</span><span class="sxs-lookup"><span data-stu-id="a243a-2337">香港身份証</span></span>
- <span data-ttu-id="a243a-2338">香港身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-2338">香港身分證</span></span>
- <span data-ttu-id="a243a-2339">香港身分証</span><span class="sxs-lookup"><span data-stu-id="a243a-2339">香港身分証</span></span>
- <span data-ttu-id="a243a-2340">香港身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2340">香港身份證</span></span>
- <span data-ttu-id="a243a-2341">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2341">香港居民身份證</span></span>
- <span data-ttu-id="a243a-2342">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="a243a-2342">香港居民身份証</span></span>
- <span data-ttu-id="a243a-2343">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-2343">香港居民身分證</span></span>
- <span data-ttu-id="a243a-2344">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="a243a-2344">香港居民身分証</span></span>
- <span data-ttu-id="a243a-2345">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a243a-2345">香港永久性居民身份証</span></span>
- <span data-ttu-id="a243a-2346">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-2346">香港永久性居民身分證</span></span>
- <span data-ttu-id="a243a-2347">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a243a-2347">香港永久性居民身分証</span></span>
- <span data-ttu-id="a243a-2348">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2348">香港永久性居民身份證</span></span>
- <span data-ttu-id="a243a-2349">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2349">香港非永久性居民身份證</span></span>
- <span data-ttu-id="a243a-2350">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a243a-2350">香港非永久性居民身份証</span></span>
- <span data-ttu-id="a243a-2351">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-2351">香港非永久性居民身分證</span></span>
- <span data-ttu-id="a243a-2352">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a243a-2352">香港非永久性居民身分証</span></span>
- <span data-ttu-id="a243a-2353">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2353">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="a243a-2354">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a243a-2354">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="a243a-2355">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-2355">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="a243a-2356">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a243a-2356">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="a243a-2357">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2357">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="a243a-2358">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a243a-2358">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="a243a-2359">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-2359">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="a243a-2360">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a243a-2360">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="a243a-2361">印度永久帳戶號碼（PAN）</span><span class="sxs-lookup"><span data-stu-id="a243a-2361">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2362">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2362">Format</span></span>

<span data-ttu-id="a243a-2363">10個字母或數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2363">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2364">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2364">Pattern</span></span>

<span data-ttu-id="a243a-2365">10個字母或數位：</span><span class="sxs-lookup"><span data-stu-id="a243a-2365">10 letters or digits:</span></span>
- <span data-ttu-id="a243a-2366">五個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2366">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="a243a-2367">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2367">Four digits</span></span> 
- <span data-ttu-id="a243a-2368">以字母檢查碼表示的字母</span><span class="sxs-lookup"><span data-stu-id="a243a-2368">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2369">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2369">Checksum</span></span>

<span data-ttu-id="a243a-2370">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2370">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2371">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2371">Definition</span></span>

<span data-ttu-id="a243a-2372">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2372">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2373">正則運算式 Regex_india_permanent_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2373">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2374">會找到來自 Keyword_india_permanent_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2374">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="a243a-2375">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2375">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2376">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2376">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="a243a-2377">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2377">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="a243a-2378">永久帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2378">Permanent Account Number</span></span> 
- <span data-ttu-id="a243a-2379">泛</span><span class="sxs-lookup"><span data-stu-id="a243a-2379">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="a243a-2380">印度唯一識別碼（Aadhaar）號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2380">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2381">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2381">Format</span></span>

<span data-ttu-id="a243a-2382">12位數包含選擇性空格或短杠</span><span class="sxs-lookup"><span data-stu-id="a243a-2382">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2383">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2383">Pattern</span></span>

<span data-ttu-id="a243a-2384">12位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-2384">12 digits:</span></span>
- <span data-ttu-id="a243a-2385">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2385">Four digits</span></span> 
- <span data-ttu-id="a243a-2386">選擇性的空格或破折號</span><span class="sxs-lookup"><span data-stu-id="a243a-2386">An optional space or dash</span></span> 
- <span data-ttu-id="a243a-2387">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2387">Four digits</span></span> 
- <span data-ttu-id="a243a-2388">選擇性的空格或破折號</span><span class="sxs-lookup"><span data-stu-id="a243a-2388">An optional space or dash</span></span> 
- <span data-ttu-id="a243a-2389">最後一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2389">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2390">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2390">Checksum</span></span>

<span data-ttu-id="a243a-2391">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2391">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2392">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2392">Definition</span></span>

<span data-ttu-id="a243a-2393">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：函數 Func_india_aadhaar 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2393">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="a243a-2394">會找到來自 Keyword_india_aadhar 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2394">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="a243a-2395">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2395">The checksum passes.</span></span>
<span data-ttu-id="a243a-2396">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：函數 Func_india_aadhaar 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="a243a-2397">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2397">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="a243a-2398">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2398">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="a243a-2399">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="a243a-2399">Keyword_india_aadhar</span></span>
- <span data-ttu-id="a243a-2400">Aadhar</span><span class="sxs-lookup"><span data-stu-id="a243a-2400">Aadhar</span></span>
- <span data-ttu-id="a243a-2401">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="a243a-2401">Aadhaar</span></span>
- <span data-ttu-id="a243a-2402">Uid</span><span class="sxs-lookup"><span data-stu-id="a243a-2402">UID</span></span>
- <span data-ttu-id="a243a-2403">आधार</span><span class="sxs-lookup"><span data-stu-id="a243a-2403">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="a243a-2404">印尼身分識別卡（KTP）號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2404">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2405">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2405">Format</span></span>

<span data-ttu-id="a243a-2406">包含選用句點的16位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2406">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2407">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2407">Pattern</span></span>

<span data-ttu-id="a243a-2408">16位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-2408">16 digits:</span></span>
- <span data-ttu-id="a243a-2409">兩位數的省碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2409">Two-digit province code</span></span> 
- <span data-ttu-id="a243a-2410">一個句點（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-2410">A period (optional)</span></span> 
- <span data-ttu-id="a243a-2411">兩位數攝政或城市碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2411">Two-digit regency or city code</span></span> 
- <span data-ttu-id="a243a-2412">兩位數的 subdistrict 程式碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2412">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="a243a-2413">一個句點（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-2413">A period (optional)</span></span> 
- <span data-ttu-id="a243a-2414">DDMMYY 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2414">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a243a-2415">一個句點（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-2415">A period (optional)</span></span> 
- <span data-ttu-id="a243a-2416">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2416">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2417">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2417">Checksum</span></span>

<span data-ttu-id="a243a-2418">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2419">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2419">Definition</span></span>

<span data-ttu-id="a243a-2420">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2421">正則運算式 Regex_indonesia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2421">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2422">會找到來自 Keyword_indonesia_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2422">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="a243a-2423">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2423">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2424">正則運算式 Regex_indonesia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2424">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2425">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2425">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="a243a-2426">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="a243a-2426">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="a243a-2427">Ktp</span><span class="sxs-lookup"><span data-stu-id="a243a-2427">KTP</span></span>
- <span data-ttu-id="a243a-2428">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="a243a-2428">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="a243a-2429">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="a243a-2429">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="a243a-2430">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="a243a-2430">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2431">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2431">Format</span></span>

<span data-ttu-id="a243a-2432">國家/地區代碼（兩個字母）加上檢查碼（兩位數）加上 bban 號碼（最多30個字元）</span><span class="sxs-lookup"><span data-stu-id="a243a-2432">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2433">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2433">Pattern</span></span>

<span data-ttu-id="a243a-2434">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="a243a-2434">Pattern must include all of the following:</span></span>

- <span data-ttu-id="a243a-2435">兩個字母的國家/地區碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2435">Two-letter country code</span></span>
- <span data-ttu-id="a243a-2436">兩個檢查碼位數（後面接著選擇性的空格）</span><span class="sxs-lookup"><span data-stu-id="a243a-2436">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="a243a-2437">1-7 四個字母或數位的群組（可以以空格隔開）</span><span class="sxs-lookup"><span data-stu-id="a243a-2437">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="a243a-2438">1-3 個字母或數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2438">1-3 letters or digits</span></span>

<span data-ttu-id="a243a-2439">每個國家/地區的格式稍有不同。</span><span class="sxs-lookup"><span data-stu-id="a243a-2439">The format for each country is slightly different.</span></span> <span data-ttu-id="a243a-2440">IBAN 敏感資訊類型涵蓋下列60個國家/地區：</span><span class="sxs-lookup"><span data-stu-id="a243a-2440">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="a243a-2441">ad，ae，al，at，az，ba，a，bg，bh，ch，cr，cy，cz，de，深色，do，ee，es，es，fo，fr，gb，ge，gi，gl，gr，hr，hu，ie，il，為，it，kw，kz，lb，li，lt，lu，lv，mt，mu，nl-nl，no，pl，mt，ro，rs-232c，tn，tr，vg</span><span class="sxs-lookup"><span data-stu-id="a243a-2441">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2442">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2442">Checksum</span></span>

<span data-ttu-id="a243a-2443">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2443">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2444">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2444">Definition</span></span>

<span data-ttu-id="a243a-2445">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2445">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2446">函數 Func_iban 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2446">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2447">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2447">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2448">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2448">Keywords</span></span>

<span data-ttu-id="a243a-2449">無</span><span class="sxs-lookup"><span data-stu-id="a243a-2449">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="a243a-2450">IP 位址</span><span class="sxs-lookup"><span data-stu-id="a243a-2450">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2451">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2451">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="a243a-2452">IPv4：</span><span class="sxs-lookup"><span data-stu-id="a243a-2452">IPv4:</span></span>
<span data-ttu-id="a243a-2453">用於格式化（句點）及未格式化（無期間）的 IPv4 位址版本的複雜模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2453">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="a243a-2454">IPv6：</span><span class="sxs-lookup"><span data-stu-id="a243a-2454">IPv6:</span></span>
<span data-ttu-id="a243a-2455">IPv6 數位格式（包含冒號）的複雜模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2455">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2456">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2456">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2457">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2457">Checksum</span></span>

<span data-ttu-id="a243a-2458">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2458">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2459">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2459">Definition</span></span>

<span data-ttu-id="a243a-2460">針對 IPv6，如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2460">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2461">正則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2461">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2462">找不到 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2462">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="a243a-2463">針對 IPv4，如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2463">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2464">正則運算式 Regex_ipv4_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2464">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2465">會找到來自 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2465">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="a243a-2466">針對 IPv6，如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2466">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2467">正則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2467">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2468">找不到 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2468">No keyword from Keyword_ipaddress is found.</span></span>

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2469">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2469">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="a243a-2470">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="a243a-2470">Keyword_ipaddress</span></span>

- <span data-ttu-id="a243a-2471">IP （此關鍵字區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2471">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="a243a-2472">ip 位址</span><span class="sxs-lookup"><span data-stu-id="a243a-2472">ip address</span></span> 
- <span data-ttu-id="a243a-2473">ip 位址</span><span class="sxs-lookup"><span data-stu-id="a243a-2473">ip addresses</span></span>
- <span data-ttu-id="a243a-2474">網際網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="a243a-2474">internet protocol</span></span>
- <span data-ttu-id="a243a-2475">IP-כתובתה</span><span class="sxs-lookup"><span data-stu-id="a243a-2475">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="a243a-2476">國際分類的疾病（ICD-10-釐米）</span><span class="sxs-lookup"><span data-stu-id="a243a-2476">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2477">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2477">Format</span></span>

<span data-ttu-id="a243a-2478">Dictionary</span><span class="sxs-lookup"><span data-stu-id="a243a-2478">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2479">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2479">Pattern</span></span>

<span data-ttu-id="a243a-2480">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2480">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2481">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2481">Checksum</span></span>

<span data-ttu-id="a243a-2482">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2482">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2483">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2483">Definition</span></span>

<span data-ttu-id="a243a-2484">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2485">會找到來自 Dictionary_icd_10_updated 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2485">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="a243a-2486">會找到來自 Dictionary_icd_10_codes 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2486">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="a243a-2487">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2487">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2488">會找到 Dictionary_icd_10_ 更新的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2488">A keyword from Dictionary_icd_10_ updated is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

<span data-ttu-id="a243a-2489">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2489">Keywords</span></span>

<span data-ttu-id="a243a-2490">Dictionary_icd_10_updated 關鍵字字典中的任何字詞，其基礎是以[疾病的國際分類，第十個修訂版本、臨床修改（icd-10 釐米）](https://go.microsoft.com/fwlink/?linkid=852604)為基礎。</span><span class="sxs-lookup"><span data-stu-id="a243a-2490">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="a243a-2491">這種類型只會尋找字詞，而不是保險碼。</span><span class="sxs-lookup"><span data-stu-id="a243a-2491">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="a243a-2492">Dictionary_icd_10_codes 關鍵字字典中的任何字詞，其基礎是以[疾病的國際分類，第十個修訂版本、臨床修改（icd-10 釐米）](https://go.microsoft.com/fwlink/?linkid=852604)為基礎。</span><span class="sxs-lookup"><span data-stu-id="a243a-2492">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="a243a-2493">這種類型只會查看保險業代碼，而不是描述。</span><span class="sxs-lookup"><span data-stu-id="a243a-2493">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="a243a-2494">國際疾病（ICD-9 CM）分類</span><span class="sxs-lookup"><span data-stu-id="a243a-2494">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2495">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2495">Format</span></span>

<span data-ttu-id="a243a-2496">Dictionary</span><span class="sxs-lookup"><span data-stu-id="a243a-2496">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2497">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2497">Pattern</span></span>

<span data-ttu-id="a243a-2498">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2498">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2499">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2499">Checksum</span></span>

<span data-ttu-id="a243a-2500">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2500">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2501">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2501">Definition</span></span>

<span data-ttu-id="a243a-2502">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2502">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2503">會找到來自 Dictionary_icd_9_updated 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2503">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="a243a-2504">會找到來自 Dictionary_icd_9_codes 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2504">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="a243a-2505">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2505">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2506">會找到來自 Dictionary_icd_9_updated 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2506">A keyword from Dictionary_icd_9_updated is found.</span></span>

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2507">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2507">Keywords</span></span>

<span data-ttu-id="a243a-2508">Dictionary_icd_9_updated 關鍵字字典中的任何字詞，其基礎是根據[疾病的國際分類，第九個修訂版本，臨床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="a243a-2508">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="a243a-2509">這種類型只會尋找字詞，而不是保險碼。</span><span class="sxs-lookup"><span data-stu-id="a243a-2509">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="a243a-2510">Dictionary_icd_9_codes 關鍵字字典中的任何字詞，其基礎是根據[疾病的國際分類，第九個修訂版本，臨床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="a243a-2510">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="a243a-2511">這種類型只會查看保險業代碼，而不是描述。</span><span class="sxs-lookup"><span data-stu-id="a243a-2511">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="a243a-2512">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2512">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2513">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2513">Format</span></span>

<span data-ttu-id="a243a-2514">舊格式（直到12月2012日）：</span><span class="sxs-lookup"><span data-stu-id="a243a-2514">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="a243a-2515">七位數後接1-2 個字母</span><span class="sxs-lookup"><span data-stu-id="a243a-2515">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="a243a-2516">新格式（1月2013日和之後）：</span><span class="sxs-lookup"><span data-stu-id="a243a-2516">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="a243a-2517">七位數後接兩個字母</span><span class="sxs-lookup"><span data-stu-id="a243a-2517">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2518">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2518">Pattern</span></span>

<span data-ttu-id="a243a-2519">舊格式（直到12月2012日）：</span><span class="sxs-lookup"><span data-stu-id="a243a-2519">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="a243a-2520">七位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2520">Seven digits</span></span> 
- <span data-ttu-id="a243a-2521">1-2 個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2521">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="a243a-2522">新格式（1月2013日和之後）：</span><span class="sxs-lookup"><span data-stu-id="a243a-2522">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="a243a-2523">七位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2523">Seven digits</span></span> 
- <span data-ttu-id="a243a-2524">字母（不區分大小寫）是字母檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2524">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="a243a-2525">字母 "A" 或 "H" （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2525">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2526">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2526">Checksum</span></span>

<span data-ttu-id="a243a-2527">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2527">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2528">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2528">Definition</span></span>

<span data-ttu-id="a243a-2529">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2530">函數 Func_ireland_pps 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2530">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2531">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="a243a-2531">One of the following is true:</span></span>
    - <span data-ttu-id="a243a-2532">會找到來自 Keyword_ireland_pps 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2532">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="a243a-2533">函數 Func_eu_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a243a-2533">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a243a-2534">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2534">The checksum passes.</span></span>

<span data-ttu-id="a243a-2535">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2535">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2536">函數 Func_ireland_pps 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2536">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2537">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2537">The checksum passes.</span></span>

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2538">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2538">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="a243a-2539">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="a243a-2539">Keyword_ireland_pps</span></span>

- <span data-ttu-id="a243a-2540">個人公開服務號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2540">Personal Public Service Number</span></span> 
- <span data-ttu-id="a243a-2541">PPS 號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2541">PPS Number</span></span> 
- <span data-ttu-id="a243a-2542">PPS 數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2542">PPS Num</span></span> 
- <span data-ttu-id="a243a-2543">PPS No。</span><span class="sxs-lookup"><span data-stu-id="a243a-2543">PPS No.</span></span> 
- <span data-ttu-id="a243a-2544">Pps#</span><span class="sxs-lookup"><span data-stu-id="a243a-2544">PPS #</span></span> 
- <span data-ttu-id="a243a-2545">Pps#</span><span class="sxs-lookup"><span data-stu-id="a243a-2545">PPS#</span></span> 
- <span data-ttu-id="a243a-2546">PPSN</span><span class="sxs-lookup"><span data-stu-id="a243a-2546">PPSN</span></span> 
- <span data-ttu-id="a243a-2547">公用服務卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-2547">Public Services Card</span></span> 
- <span data-ttu-id="a243a-2548">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="a243a-2548">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="a243a-2549">Uimh.</span><span class="sxs-lookup"><span data-stu-id="a243a-2549">Uimh.</span></span> <span data-ttu-id="a243a-2550">Psp</span><span class="sxs-lookup"><span data-stu-id="a243a-2550">PSP</span></span> 
- <span data-ttu-id="a243a-2551">Psp</span><span class="sxs-lookup"><span data-stu-id="a243a-2551">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="a243a-2552">以色列銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2552">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2553">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2553">Format</span></span>

<span data-ttu-id="a243a-2554">13位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2554">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2555">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2555">Pattern</span></span>

<span data-ttu-id="a243a-2556">格式 化：</span><span class="sxs-lookup"><span data-stu-id="a243a-2556">Formatted:</span></span>
- <span data-ttu-id="a243a-2557">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2557">Two digits</span></span> 
- <span data-ttu-id="a243a-2558">虛線</span><span class="sxs-lookup"><span data-stu-id="a243a-2558">A dash</span></span> 
- <span data-ttu-id="a243a-2559">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2559">Three digits</span></span> 
- <span data-ttu-id="a243a-2560">虛線</span><span class="sxs-lookup"><span data-stu-id="a243a-2560">A dash</span></span> 
- <span data-ttu-id="a243a-2561">八位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2561">Eight digits</span></span>

<span data-ttu-id="a243a-2562">非</span><span class="sxs-lookup"><span data-stu-id="a243a-2562">Unformatted:</span></span>
- <span data-ttu-id="a243a-2563">13個連續數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2563">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2564">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2564">Checksum</span></span>

<span data-ttu-id="a243a-2565">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2565">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2566">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2566">Definition</span></span>

<span data-ttu-id="a243a-2567">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2568">正則運算式 Regex_israel_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2568">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2569">會找到來自 Keyword_israel_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2569">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2570">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2570">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="a243a-2571">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2571">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="a243a-2572">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2572">Bank Account Number</span></span> 
- <span data-ttu-id="a243a-2573">銀行帳戶</span><span class="sxs-lookup"><span data-stu-id="a243a-2573">Bank Account</span></span> 
- <span data-ttu-id="a243a-2574">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2574">Account Number</span></span> 
- <span data-ttu-id="a243a-2575">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="a243a-2575">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="a243a-2576">以色列國家識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2576">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2577">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2577">Format</span></span>

<span data-ttu-id="a243a-2578">九位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2578">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2579">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2579">Pattern</span></span>

<span data-ttu-id="a243a-2580">九個連續數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2580">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2581">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2581">Checksum</span></span>

<span data-ttu-id="a243a-2582">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2582">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2583">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2583">Definition</span></span>

<span data-ttu-id="a243a-2584">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2585">函數 Func_israeli_national_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2585">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2586">會找到來自 Keyword_Israel_National_ID 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2586">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="a243a-2587">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2587">The checksum passes.</span></span>

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2588">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2588">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="a243a-2589">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="a243a-2589">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="a243a-2590">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="a243a-2590">מספר זהות</span></span> 
- <span data-ttu-id="a243a-2591">本國識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2591">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="a243a-2592">義大利駕照編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2592">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2593">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2593">Format</span></span>

<span data-ttu-id="a243a-2594">10個字母和數位的組合</span><span class="sxs-lookup"><span data-stu-id="a243a-2594">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2595">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2595">Pattern</span></span>

- <span data-ttu-id="a243a-2596">10個字母和數位的組合：</span><span class="sxs-lookup"><span data-stu-id="a243a-2596">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="a243a-2597">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2597">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="a243a-2598">字母 "A" 或 "V" （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2598">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="a243a-2599">七個字母（不區分大小寫）、數位或底線字元</span><span class="sxs-lookup"><span data-stu-id="a243a-2599">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="a243a-2600">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2600">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2601">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2601">Checksum</span></span>

<span data-ttu-id="a243a-2602">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2602">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2603">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2603">Definition</span></span>

<span data-ttu-id="a243a-2604">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2604">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2605">正則運算式 Regex_italy_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2605">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2606">會找到來自 Keyword_italy_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2606">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2607">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2607">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="a243a-2608">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2608">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="a243a-2609">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="a243a-2609">numero di patente di guida</span></span> 
- <span data-ttu-id="a243a-2610">patente di guida</span><span class="sxs-lookup"><span data-stu-id="a243a-2610">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="a243a-2611">日本銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2611">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2612">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2612">Format</span></span>

<span data-ttu-id="a243a-2613">7或8位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2613">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2614">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2614">Pattern</span></span>

<span data-ttu-id="a243a-2615">銀行帳戶號碼：</span><span class="sxs-lookup"><span data-stu-id="a243a-2615">Bank account number:</span></span>
- <span data-ttu-id="a243a-2616">7或8位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2616">Seven or eight digits</span></span>
- <span data-ttu-id="a243a-2617">銀行帳戶分支程式碼：</span><span class="sxs-lookup"><span data-stu-id="a243a-2617">Bank account branch code:</span></span>
- <span data-ttu-id="a243a-2618">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2618">Four digits</span></span> 
- <span data-ttu-id="a243a-2619">一個空格或破折號（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-2619">A space or dash (optional)</span></span> 
- <span data-ttu-id="a243a-2620">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2620">Three digits</span></span>

<span data-ttu-id="a243a-2621">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2621">Checksum</span></span>

<span data-ttu-id="a243a-2622">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2622">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2623">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2623">Definition</span></span>

<span data-ttu-id="a243a-2624">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2625">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2625">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2626">會找到來自 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2626">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="a243a-2627">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="a243a-2627">One of the following is true:</span></span>
- <span data-ttu-id="a243a-2628">函數 Func_jp_bank_account_branch_code 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2628">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2629">會找到來自 Keyword_jp_bank_branch_code 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2629">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="a243a-2630">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2630">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2631">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2631">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2632">會找到來自 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2632">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2633">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2633">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="a243a-2634">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="a243a-2634">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="a243a-2635">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2635">Checking Account Number</span></span> 
- <span data-ttu-id="a243a-2636">檢查帳戶</span><span class="sxs-lookup"><span data-stu-id="a243a-2636">Checking Account</span></span> 
- <span data-ttu-id="a243a-2637">檢查帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-2637">Checking Account #</span></span> 
- <span data-ttu-id="a243a-2638">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2638">Checking Acct Number</span></span> 
- <span data-ttu-id="a243a-2639">檢查帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-2639">Checking Acct #</span></span> 
- <span data-ttu-id="a243a-2640">檢查帳戶否。</span><span class="sxs-lookup"><span data-stu-id="a243a-2640">Checking Acct No.</span></span> 
- <span data-ttu-id="a243a-2641">檢查帳戶否</span><span class="sxs-lookup"><span data-stu-id="a243a-2641">Checking Account No.</span></span> 
- <span data-ttu-id="a243a-2642">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2642">Bank Account Number</span></span> 
- <span data-ttu-id="a243a-2643">銀行帳戶</span><span class="sxs-lookup"><span data-stu-id="a243a-2643">Bank Account</span></span> 
- <span data-ttu-id="a243a-2644">銀行帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-2644">Bank Account #</span></span> 
- <span data-ttu-id="a243a-2645">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2645">Bank Acct Number</span></span> 
- <span data-ttu-id="a243a-2646">銀行帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-2646">Bank Acct #</span></span> 
- <span data-ttu-id="a243a-2647">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2647">Bank Acct No.</span></span> 
- <span data-ttu-id="a243a-2648">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2648">Bank Account No.</span></span> 
- <span data-ttu-id="a243a-2649">儲蓄帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2649">Savings Account Number</span></span> 
- <span data-ttu-id="a243a-2650">儲蓄帳戶</span><span class="sxs-lookup"><span data-stu-id="a243a-2650">Savings Account</span></span> 
- <span data-ttu-id="a243a-2651">儲蓄帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-2651">Savings Account #</span></span> 
- <span data-ttu-id="a243a-2652">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2652">Savings Acct Number</span></span> 
- <span data-ttu-id="a243a-2653">儲蓄帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-2653">Savings Acct #</span></span> 
- <span data-ttu-id="a243a-2654">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2654">Savings Acct No.</span></span> 
- <span data-ttu-id="a243a-2655">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2655">Savings Account No.</span></span> 
- <span data-ttu-id="a243a-2656">借方科目編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2656">Debit Account Number</span></span> 
- <span data-ttu-id="a243a-2657">借方科目</span><span class="sxs-lookup"><span data-stu-id="a243a-2657">Debit Account</span></span> 
- <span data-ttu-id="a243a-2658">借方科目#</span><span class="sxs-lookup"><span data-stu-id="a243a-2658">Debit Account #</span></span> 
- <span data-ttu-id="a243a-2659">借方帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2659">Debit Acct Number</span></span> 
- <span data-ttu-id="a243a-2660">借方帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-2660">Debit Acct #</span></span> 
- <span data-ttu-id="a243a-2661">借方帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2661">Debit Acct No.</span></span> 
- <span data-ttu-id="a243a-2662">借方科目編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2662">Debit Account No.</span></span> 
- <span data-ttu-id="a243a-2663">口座番號を當座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="a243a-2663">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="a243a-2664">#アカウントの確認、勘定番號の確認</span><span class="sxs-lookup"><span data-stu-id="a243a-2664">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="a243a-2665">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="a243a-2665">＃勘定の確認</span></span> 
- <span data-ttu-id="a243a-2666">勘定番號の確認</span><span class="sxs-lookup"><span data-stu-id="a243a-2666">勘定番号の確認</span></span> 
- <span data-ttu-id="a243a-2667">口座番號の確認</span><span class="sxs-lookup"><span data-stu-id="a243a-2667">口座番号の確認</span></span> 
- <span data-ttu-id="a243a-2668">銀行口座番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2668">銀行口座番号</span></span> 
- <span data-ttu-id="a243a-2669">銀行口座</span><span class="sxs-lookup"><span data-stu-id="a243a-2669">銀行口座</span></span> 
- <span data-ttu-id="a243a-2670">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="a243a-2670">銀行口座＃</span></span> 
- <span data-ttu-id="a243a-2671">銀行の勘定番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2671">銀行の勘定番号</span></span> 
- <span data-ttu-id="a243a-2672">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="a243a-2672">銀行のacct＃</span></span> 
- <span data-ttu-id="a243a-2673">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="a243a-2673">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="a243a-2674">銀行口座番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2674">銀行口座番号</span></span>
- <span data-ttu-id="a243a-2675">普通預金口座番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2675">普通預金口座番号</span></span> 
- <span data-ttu-id="a243a-2676">預金口座</span><span class="sxs-lookup"><span data-stu-id="a243a-2676">預金口座</span></span> 
- <span data-ttu-id="a243a-2677">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="a243a-2677">貯蓄口座＃</span></span> 
- <span data-ttu-id="a243a-2678">貯蓄勘定の數</span><span class="sxs-lookup"><span data-stu-id="a243a-2678">貯蓄勘定の数</span></span> 
- <span data-ttu-id="a243a-2679">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="a243a-2679">貯蓄勘定＃</span></span> 
- <span data-ttu-id="a243a-2680">貯蓄勘定番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2680">貯蓄勘定番号</span></span> 
- <span data-ttu-id="a243a-2681">普通預金口座番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2681">普通預金口座番号</span></span> 
- <span data-ttu-id="a243a-2682">引き落とし口座番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2682">引き落とし口座番号</span></span> 
- <span data-ttu-id="a243a-2683">口座番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2683">口座番号</span></span> 
- <span data-ttu-id="a243a-2684">口座番號＃</span><span class="sxs-lookup"><span data-stu-id="a243a-2684">口座番号＃</span></span> 
- <span data-ttu-id="a243a-2685">デビットのacct番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2685">デビットのacct番号</span></span> 
- <span data-ttu-id="a243a-2686">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="a243a-2686">デビット勘定＃</span></span> 
- <span data-ttu-id="a243a-2687">デビットACCTの番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2687">デビットACCTの番号</span></span> 
- <span data-ttu-id="a243a-2688">デビット口座番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2688">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="a243a-2689">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="a243a-2689">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="a243a-2690">Otemachi</span><span class="sxs-lookup"><span data-stu-id="a243a-2690">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="a243a-2691">日本駕照編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2691">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2692">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2692">Format</span></span>

<span data-ttu-id="a243a-2693">12位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2693">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2694">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2694">Pattern</span></span>

<span data-ttu-id="a243a-2695">12個連續數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2695">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2696">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2696">Checksum</span></span>

<span data-ttu-id="a243a-2697">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2697">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2698">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2698">Definition</span></span>

<span data-ttu-id="a243a-2699">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2699">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2700">函數 Func_jp_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2700">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2701">會找到來自 Keyword_jp_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2701">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2702">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2702">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="a243a-2703">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2703">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="a243a-2704">Dl#</span><span class="sxs-lookup"><span data-stu-id="a243a-2704">dl#</span></span> 
- <span data-ttu-id="a243a-2705">DL</span><span class="sxs-lookup"><span data-stu-id="a243a-2705">DL＃</span></span> 
- <span data-ttu-id="a243a-2706">Dls#</span><span class="sxs-lookup"><span data-stu-id="a243a-2706">dls#</span></span> 
- <span data-ttu-id="a243a-2707">DL</span><span class="sxs-lookup"><span data-stu-id="a243a-2707">DLS＃</span></span> 
- <span data-ttu-id="a243a-2708">駕照</span><span class="sxs-lookup"><span data-stu-id="a243a-2708">driver license</span></span> 
- <span data-ttu-id="a243a-2709">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2709">driver licenses</span></span> 
- <span data-ttu-id="a243a-2710">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2710">drivers license</span></span> 
- <span data-ttu-id="a243a-2711">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-2711">driver's license</span></span> 
- <span data-ttu-id="a243a-2712">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-2712">drivers licenses</span></span> 
- <span data-ttu-id="a243a-2713">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-2713">driver's licenses</span></span> 
- <span data-ttu-id="a243a-2714">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2714">driving licence</span></span> 
- <span data-ttu-id="a243a-2715">許可證#</span><span class="sxs-lookup"><span data-stu-id="a243a-2715">lic#</span></span> 
- <span data-ttu-id="a243a-2716">許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-2716">LIC＃</span></span> 
- <span data-ttu-id="a243a-2717">lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-2717">lics#</span></span> 
- <span data-ttu-id="a243a-2718">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2718">state id</span></span> 
- <span data-ttu-id="a243a-2719">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2719">state identification</span></span> 
- <span data-ttu-id="a243a-2720">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2720">state identification number</span></span> 
- <span data-ttu-id="a243a-2721">低所得國＃</span><span class="sxs-lookup"><span data-stu-id="a243a-2721">低所得国＃</span></span> 
- <span data-ttu-id="a243a-2722">免許証</span><span class="sxs-lookup"><span data-stu-id="a243a-2722">免許証</span></span> 
- <span data-ttu-id="a243a-2723">狀態ID</span><span class="sxs-lookup"><span data-stu-id="a243a-2723">状態ID</span></span>
- <span data-ttu-id="a243a-2724">狀態の識別</span><span class="sxs-lookup"><span data-stu-id="a243a-2724">状態の識別</span></span> 
- <span data-ttu-id="a243a-2725">狀態の識別番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2725">状態の識別番号</span></span> 
- <span data-ttu-id="a243a-2726">運転免許</span><span class="sxs-lookup"><span data-stu-id="a243a-2726">運転免許</span></span> 
- <span data-ttu-id="a243a-2727">運転免許証</span><span class="sxs-lookup"><span data-stu-id="a243a-2727">運転免許証</span></span> 
- <span data-ttu-id="a243a-2728">運転免許証番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2728">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="a243a-2729">日本護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2729">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2730">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2730">Format</span></span>

<span data-ttu-id="a243a-2731">兩個字母后接7位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2731">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2732">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2732">Pattern</span></span>

<span data-ttu-id="a243a-2733">兩個字母（不區分大小寫）後接7位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2733">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2734">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2734">Checksum</span></span>

<span data-ttu-id="a243a-2735">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2736">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2736">Definition</span></span>

<span data-ttu-id="a243a-2737">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2737">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2738">函數 Func_jp_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2738">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2739">會找到來自 Keyword_jp_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2739">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2740">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2740">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="a243a-2741">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="a243a-2741">Keyword_jp_passport</span></span>

- <span data-ttu-id="a243a-2742">パスポート</span><span class="sxs-lookup"><span data-stu-id="a243a-2742">パスポート</span></span> 
- <span data-ttu-id="a243a-2743">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2743">パスポート番号</span></span> 
- <span data-ttu-id="a243a-2744">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a243a-2744">パスポートのNum</span></span> 
- <span data-ttu-id="a243a-2745">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a243a-2745">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="a243a-2746">日本居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2746">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2747">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2747">Format</span></span>

<span data-ttu-id="a243a-2748">11位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2748">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2749">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2749">Pattern</span></span>

<span data-ttu-id="a243a-2750">11個連續數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2750">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2751">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2751">Checksum</span></span>

<span data-ttu-id="a243a-2752">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2752">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2753">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2753">Definition</span></span>

<span data-ttu-id="a243a-2754">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2755">函數 Func_jp_resident_registration_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2755">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2756">會找到來自 Keyword_jp_resident_registration_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2756">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2757">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2757">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="a243a-2758">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2758">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="a243a-2759">常駐登記編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2759">Resident Registration Number</span></span>
- <span data-ttu-id="a243a-2760">常駐寄存器號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2760">Resident Register Number</span></span> 
- <span data-ttu-id="a243a-2761">居民基本登錄號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2761">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="a243a-2762">常駐登記編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2762">Resident Registration No.</span></span> 
- <span data-ttu-id="a243a-2763">居民收銀機否。</span><span class="sxs-lookup"><span data-stu-id="a243a-2763">Resident Register No.</span></span> 
- <span data-ttu-id="a243a-2764">居民基本登錄否。</span><span class="sxs-lookup"><span data-stu-id="a243a-2764">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="a243a-2765">基本居民收銀機 No。</span><span class="sxs-lookup"><span data-stu-id="a243a-2765">Basic Resident Register No.</span></span> 
- <span data-ttu-id="a243a-2766">住民登録番號、登録番號をレジデント</span><span class="sxs-lookup"><span data-stu-id="a243a-2766">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="a243a-2767">住民基本登録番號、登録番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2767">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="a243a-2768">住民基本レジストリ番號を常駐</span><span class="sxs-lookup"><span data-stu-id="a243a-2768">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="a243a-2769">登録番號を常駐住民基本台帳登録番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2769">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="a243a-2770">日本社交保險號碼（SIN）</span><span class="sxs-lookup"><span data-stu-id="a243a-2770">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2771">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2771">Format</span></span>

<span data-ttu-id="a243a-2772">7-12 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2772">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2773">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2773">Pattern</span></span>

<span data-ttu-id="a243a-2774">7-12 位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-2774">7-12 digits:</span></span>
- <span data-ttu-id="a243a-2775">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2775">Four digits</span></span> 
- <span data-ttu-id="a243a-2776">連字號（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-2776">A hyphen (optional)</span></span> 
- <span data-ttu-id="a243a-2777">六位數或</span><span class="sxs-lookup"><span data-stu-id="a243a-2777">Six digits OR</span></span>
- <span data-ttu-id="a243a-2778">7-12 連續位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2778">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2779">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2779">Checksum</span></span>

<span data-ttu-id="a243a-2780">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2780">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2781">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2781">Definition</span></span>

<span data-ttu-id="a243a-2782">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2782">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2783">函數 Func_jp_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2783">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2784">會找到來自 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2784">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="a243a-2785">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2785">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2786">函數 Func_jp_sin_pre_1997 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2786">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2787">會找到來自 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2787">A keyword from Keyword_jp_sin is found.</span></span>

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2788">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2788">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="a243a-2789">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="a243a-2789">Keyword_jp_sin</span></span>

- <span data-ttu-id="a243a-2790">社交保險保險編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2790">Social Insurance No.</span></span> 
- <span data-ttu-id="a243a-2791">社交保險編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2791">Social Insurance Num</span></span> 
- <span data-ttu-id="a243a-2792">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2792">Social Insurance Number</span></span> 
- <span data-ttu-id="a243a-2793">社會保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="a243a-2793">社会保険のテンキー</span></span> 
- <span data-ttu-id="a243a-2794">社會保険番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2794">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="a243a-2795">日本住家電話卡號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2795">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2796">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2796">Format</span></span>

<span data-ttu-id="a243a-2797">12個字母和數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2797">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2798">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2798">Pattern</span></span>

<span data-ttu-id="a243a-2799">12個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="a243a-2799">12 letters and digits:</span></span>
- <span data-ttu-id="a243a-2800">兩個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2800">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="a243a-2801">八位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2801">Eight digits</span></span> 
- <span data-ttu-id="a243a-2802">兩個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-2802">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2803">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2803">Checksum</span></span>

<span data-ttu-id="a243a-2804">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2804">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2805">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2805">Definition</span></span>

<span data-ttu-id="a243a-2806">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2807">正則運算式 Regex_jp_residence_card_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2807">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2808">會找到來自 Keyword_jp_residence_card_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2808">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2809">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2809">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="a243a-2810">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2810">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="a243a-2811">住家電話卡號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2811">Residence card number</span></span>
- <span data-ttu-id="a243a-2812">不含住宅卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-2812">Residence card no</span></span>
- <span data-ttu-id="a243a-2813">住宅卡片#</span><span class="sxs-lookup"><span data-stu-id="a243a-2813">Residence card #</span></span>
- <span data-ttu-id="a243a-2814">在留カード番號</span><span class="sxs-lookup"><span data-stu-id="a243a-2814">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="a243a-2815">馬來西亞識別碼卡片編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2815">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2816">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2816">Format</span></span>

<span data-ttu-id="a243a-2817">12位數包含選擇性連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-2817">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2818">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2818">Pattern</span></span>

<span data-ttu-id="a243a-2819">12位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-2819">12 digits:</span></span>
- <span data-ttu-id="a243a-2820">YYMMDD 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2820">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a243a-2821">破折號（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-2821">A dash (optional)</span></span> 
- <span data-ttu-id="a243a-2822">兩個字母的出生代碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2822">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="a243a-2823">破折號（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-2823">A dash (optional)</span></span> 
- <span data-ttu-id="a243a-2824">三個亂數字</span><span class="sxs-lookup"><span data-stu-id="a243a-2824">Three random digits</span></span> 
- <span data-ttu-id="a243a-2825">一位數的性別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2825">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2826">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2826">Checksum</span></span>

<span data-ttu-id="a243a-2827">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2827">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2828">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2828">Definition</span></span>

<span data-ttu-id="a243a-2829">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2829">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2830">正則運算式 Regex_malaysia_id_card_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2830">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2831">會找到來自 Keyword_malaysia_id_card_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2831">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2832">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2832">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="a243a-2833">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2833">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="a243a-2834">數位 application 卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-2834">digital application card</span></span>
- <span data-ttu-id="a243a-2835">i/c</span><span class="sxs-lookup"><span data-stu-id="a243a-2835">i/c</span></span>
- <span data-ttu-id="a243a-2836">i/c 否</span><span class="sxs-lookup"><span data-stu-id="a243a-2836">i/c no</span></span>
- <span data-ttu-id="a243a-2837">Ic</span><span class="sxs-lookup"><span data-stu-id="a243a-2837">ic</span></span>
- <span data-ttu-id="a243a-2838">內部公司編號</span><span class="sxs-lookup"><span data-stu-id="a243a-2838">ic no</span></span>
- <span data-ttu-id="a243a-2839">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2839">id card</span></span>
- <span data-ttu-id="a243a-2840">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-2840">identification Card</span></span>
- <span data-ttu-id="a243a-2841">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2841">identity card</span></span>
- <span data-ttu-id="a243a-2842">k/p</span><span class="sxs-lookup"><span data-stu-id="a243a-2842">k/p</span></span>
- <span data-ttu-id="a243a-2843">k/p 否</span><span class="sxs-lookup"><span data-stu-id="a243a-2843">k/p no</span></span>
- <span data-ttu-id="a243a-2844">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="a243a-2844">kad akuan diri</span></span>
- <span data-ttu-id="a243a-2845">kad aplikasi 數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2845">kad aplikasi digital</span></span>
- <span data-ttu-id="a243a-2846">kad pengenalan 馬來西亞</span><span class="sxs-lookup"><span data-stu-id="a243a-2846">kad pengenalan malaysia</span></span>
- <span data-ttu-id="a243a-2847">Kp</span><span class="sxs-lookup"><span data-stu-id="a243a-2847">kp</span></span>
- <span data-ttu-id="a243a-2848">kp 否</span><span class="sxs-lookup"><span data-stu-id="a243a-2848">kp no</span></span>
- <span data-ttu-id="a243a-2849">mykad</span><span class="sxs-lookup"><span data-stu-id="a243a-2849">mykad</span></span>
- <span data-ttu-id="a243a-2850">mykas</span><span class="sxs-lookup"><span data-stu-id="a243a-2850">mykas</span></span>
- <span data-ttu-id="a243a-2851">mykid</span><span class="sxs-lookup"><span data-stu-id="a243a-2851">mykid</span></span>
- <span data-ttu-id="a243a-2852">mypr</span><span class="sxs-lookup"><span data-stu-id="a243a-2852">mypr</span></span>
- <span data-ttu-id="a243a-2853">mytentera</span><span class="sxs-lookup"><span data-stu-id="a243a-2853">mytentera</span></span>
- <span data-ttu-id="a243a-2854">馬來西亞身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-2854">malaysia identity card</span></span>
- <span data-ttu-id="a243a-2855">馬來西亞身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-2855">malaysian identity card</span></span>
- <span data-ttu-id="a243a-2856">nric</span><span class="sxs-lookup"><span data-stu-id="a243a-2856">nric</span></span>
- <span data-ttu-id="a243a-2857">個人身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-2857">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="a243a-2858">荷蘭公民服務（BSN）號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2858">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2859">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2859">Format</span></span>

<span data-ttu-id="a243a-2860">8-9 位數包含選擇性空格</span><span class="sxs-lookup"><span data-stu-id="a243a-2860">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2861">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2861">Pattern</span></span>

<span data-ttu-id="a243a-2862">8-9 位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-2862">8-9 digits:</span></span>
- <span data-ttu-id="a243a-2863">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2863">Three digits</span></span> 
- <span data-ttu-id="a243a-2864">一個空格（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-2864">A space (optional)</span></span> 
- <span data-ttu-id="a243a-2865">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2865">Three digits</span></span> 
- <span data-ttu-id="a243a-2866">一個空格（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-2866">A space (optional)</span></span> 
- <span data-ttu-id="a243a-2867">2-3 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2867">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2868">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2868">Checksum</span></span>

<span data-ttu-id="a243a-2869">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2869">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2870">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2870">Definition</span></span>

<span data-ttu-id="a243a-2871">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2871">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2872">函數 Func_netherlands_bsn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2872">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2873">會找到來自 Keyword_netherlands_bsn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2873">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="a243a-2874">函數 Func_eu_date2 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a243a-2874">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="a243a-2875">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2875">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2876">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2876">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="a243a-2877">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="a243a-2877">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="a243a-2878">公民服務號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2878">Citizen service number</span></span> 
- <span data-ttu-id="a243a-2879">BSN</span><span class="sxs-lookup"><span data-stu-id="a243a-2879">BSN</span></span> 
- <span data-ttu-id="a243a-2880">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="a243a-2880">Burgerservicenummer</span></span> 
- <span data-ttu-id="a243a-2881">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="a243a-2881">Sofinummer</span></span> 
- <span data-ttu-id="a243a-2882">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="a243a-2882">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="a243a-2883">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-2883">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="a243a-2884">紐西蘭健康情況號碼的部</span><span class="sxs-lookup"><span data-stu-id="a243a-2884">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2885">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2885">Format</span></span>

<span data-ttu-id="a243a-2886">三個字母、一個空格（選用）及四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2886">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2887">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2887">Pattern</span></span>

<span data-ttu-id="a243a-2888">三個字母（不區分大小寫）一個空格（選用）四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2888">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2889">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2889">Checksum</span></span>

<span data-ttu-id="a243a-2890">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2890">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2891">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2891">Definition</span></span>

<span data-ttu-id="a243a-2892">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2892">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2893">函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2893">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2894">會找到來自 Keyword_nz_terms 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2894">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="a243a-2895">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2895">The checksum passes.</span></span>

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="a243a-2896">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2896">Keywords</span></span>

<span data-ttu-id="a243a-2897">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="a243a-2897">Keyword_nz_terms</span></span>

- <span data-ttu-id="a243a-2898">NHI</span><span class="sxs-lookup"><span data-stu-id="a243a-2898">NHI</span></span> 
- <span data-ttu-id="a243a-2899">紐西蘭</span><span class="sxs-lookup"><span data-stu-id="a243a-2899">New Zealand</span></span> 
- <span data-ttu-id="a243a-2900">醫療保健</span><span class="sxs-lookup"><span data-stu-id="a243a-2900">Health</span></span> 
- <span data-ttu-id="a243a-2901">治療</span><span class="sxs-lookup"><span data-stu-id="a243a-2901">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="a243a-2902">挪威身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2902">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2903">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2903">Format</span></span>

<span data-ttu-id="a243a-2904">11位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2904">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2905">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2905">Pattern</span></span>

<span data-ttu-id="a243a-2906">11位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-2906">11 digits:</span></span>
- <span data-ttu-id="a243a-2907">DDMMYY 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2907">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a243a-2908">三位數個人號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2908">Three-digit individual number</span></span> 
- <span data-ttu-id="a243a-2909">兩個檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2909">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2910">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2910">Checksum</span></span>

<span data-ttu-id="a243a-2911">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2912">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2912">Definition</span></span>

<span data-ttu-id="a243a-2913">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2913">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2914">函數 Func_norway_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2914">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2915">會找到來自 Keyword_norway_id_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2915">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="a243a-2916">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2916">The checksum passes.</span></span>
- <span data-ttu-id="a243a-2917">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2917">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2918">函數 Func_norway_id_numbe 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2918">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2919">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2919">The checksum passes.</span></span>

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2920">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2920">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="a243a-2921">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2921">Keyword_norway_id_number</span></span>

- <span data-ttu-id="a243a-2922">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2922">Personal identification number</span></span>
- <span data-ttu-id="a243a-2923">挪威文識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2923">Norwegian ID Number</span></span>
- <span data-ttu-id="a243a-2924">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2924">ID Number</span></span>
- <span data-ttu-id="a243a-2925">識別</span><span class="sxs-lookup"><span data-stu-id="a243a-2925">Identification</span></span>
- <span data-ttu-id="a243a-2926">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-2926">Personnummer</span></span>
- <span data-ttu-id="a243a-2927">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="a243a-2927">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="a243a-2928">菲律賓統一多用途識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2928">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2929">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2929">Format</span></span>

<span data-ttu-id="a243a-2930">以連字號隔開的12位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2930">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2931">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2931">Pattern</span></span>

<span data-ttu-id="a243a-2932">12位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-2932">12 digits:</span></span>
- <span data-ttu-id="a243a-2933">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2933">Four digits</span></span> 
- <span data-ttu-id="a243a-2934">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-2934">A hyphen</span></span> 
- <span data-ttu-id="a243a-2935">七位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2935">Seven digits</span></span> 
- <span data-ttu-id="a243a-2936">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-2936">A hyphen</span></span> 
- <span data-ttu-id="a243a-2937">一個數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2937">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2938">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2938">Checksum</span></span>

<span data-ttu-id="a243a-2939">否</span><span class="sxs-lookup"><span data-stu-id="a243a-2939">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2940">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2940">Definition</span></span>

<span data-ttu-id="a243a-2941">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2942">正則運算式 Regex_philippines_unified_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2942">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2943">會找到來自 Keyword_philippines_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2943">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2944">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2944">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="a243a-2945">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="a243a-2945">Keyword_philippines_id</span></span>

- <span data-ttu-id="a243a-2946">統一的多重用途識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2946">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="a243a-2947">UMID</span><span class="sxs-lookup"><span data-stu-id="a243a-2947">UMID</span></span> 
- <span data-ttu-id="a243a-2948">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-2948">Identity Card</span></span> 
- <span data-ttu-id="a243a-2949">Pinag-isang 多 Layunin 識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-2949">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="a243a-2950">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="a243a-2950">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2951">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2951">Format</span></span>

<span data-ttu-id="a243a-2952">三個字母和六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2952">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2953">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2953">Pattern</span></span>

<span data-ttu-id="a243a-2954">三個字母（不區分大小寫）後接六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2954">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2955">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2955">Checksum</span></span>

<span data-ttu-id="a243a-2956">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2956">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2957">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2957">Definition</span></span>

<span data-ttu-id="a243a-2958">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：函數 Func_polish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2958">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="a243a-2959">會找到來自 Keyword_polish_national_id_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2959">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="a243a-2960">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2960">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2961">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2961">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="a243a-2962">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2962">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="a243a-2963">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="a243a-2963">Dowód osobisty</span></span>
- <span data-ttu-id="a243a-2964">轉寄 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a243a-2964">Numer dowodu osobistego</span></span>
- <span data-ttu-id="a243a-2965">Nazwa i 轉寄 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a243a-2965">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="a243a-2966">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a243a-2966">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="a243a-2967">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="a243a-2967">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="a243a-2968">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="a243a-2968">Dowód Tożsamości</span></span>
- <span data-ttu-id="a243a-2969">道鐘斯指數。</span><span class="sxs-lookup"><span data-stu-id="a243a-2969">dow.</span></span> <span data-ttu-id="a243a-2970">作業系統。</span><span class="sxs-lookup"><span data-stu-id="a243a-2970">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="a243a-2971">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="a243a-2971">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2972">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2972">Format</span></span>

<span data-ttu-id="a243a-2973">11位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2973">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2974">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2974">Pattern</span></span>

<span data-ttu-id="a243a-2975">11個連續數位</span><span class="sxs-lookup"><span data-stu-id="a243a-2975">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2976">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2976">Checksum</span></span>

<span data-ttu-id="a243a-2977">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2977">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2978">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2978">Definition</span></span>

<span data-ttu-id="a243a-2979">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2979">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2980">函數 Func_pesel_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2980">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2981">會找到來自 Keyword_pesel_identification_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2981">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="a243a-2982">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2982">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2983">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2983">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="a243a-2984">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="a243a-2984">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="a243a-2985">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="a243a-2985">Nr PESEL</span></span>
- <span data-ttu-id="a243a-2986">PESEL</span><span class="sxs-lookup"><span data-stu-id="a243a-2986">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="a243a-2987">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="a243a-2987">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="a243a-2988">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-2988">Format</span></span>

<span data-ttu-id="a243a-2989">兩個字母和七位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2989">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-2990">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-2990">Pattern</span></span>

<span data-ttu-id="a243a-2991">兩個字母（不區分大小寫）後接7位數</span><span class="sxs-lookup"><span data-stu-id="a243a-2991">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-2992">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-2992">Checksum</span></span>

<span data-ttu-id="a243a-2993">是</span><span class="sxs-lookup"><span data-stu-id="a243a-2993">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-2994">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-2994">Definition</span></span>

<span data-ttu-id="a243a-2995">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-2995">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-2996">函數 Func_polish_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-2996">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-2997">會找到來自 Keyword_polish_national_id_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-2997">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="a243a-2998">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-2998">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="a243a-2999">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-2999">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="a243a-3000">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="a243a-3000">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="a243a-3001">轉寄 paszportu</span><span class="sxs-lookup"><span data-stu-id="a243a-3001">Numer paszportu</span></span>
- <span data-ttu-id="a243a-3002">星期日。</span><span class="sxs-lookup"><span data-stu-id="a243a-3002">Nr.</span></span> <span data-ttu-id="a243a-3003">Paszportu</span><span class="sxs-lookup"><span data-stu-id="a243a-3003">Paszportu</span></span>
- <span data-ttu-id="a243a-3004">Paszport</span><span class="sxs-lookup"><span data-stu-id="a243a-3004">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="a243a-3005">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3005">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3006">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3006">Format</span></span>

<span data-ttu-id="a243a-3007">八位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3007">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3008">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3008">Pattern</span></span>

<span data-ttu-id="a243a-3009">八位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3009">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3010">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3010">Checksum</span></span>

<span data-ttu-id="a243a-3011">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3011">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3012">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3012">Definition</span></span>

<span data-ttu-id="a243a-3013">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3013">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3014">正則運算式 Regex_portugal_citizen_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3014">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3015">會找到來自 Keyword_portugal_citizen_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3015">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3016">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3016">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="a243a-3017">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="a243a-3017">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="a243a-3018">公民卡片</span><span class="sxs-lookup"><span data-stu-id="a243a-3018">Citizen Card</span></span>
- <span data-ttu-id="a243a-3019">國際身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-3019">National ID Card</span></span>
- <span data-ttu-id="a243a-3020">副本</span><span class="sxs-lookup"><span data-stu-id="a243a-3020">CC</span></span>
- <span data-ttu-id="a243a-3021">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="a243a-3021">Cartão de Cidadão</span></span>
- <span data-ttu-id="a243a-3022">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="a243a-3022">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="a243a-3023">沙烏地阿拉伯國際身分識別</span><span class="sxs-lookup"><span data-stu-id="a243a-3023">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3024">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3024">Format</span></span>

<span data-ttu-id="a243a-3025">10位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3025">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3026">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3026">Pattern</span></span>

<span data-ttu-id="a243a-3027">10個連續數位</span><span class="sxs-lookup"><span data-stu-id="a243a-3027">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3028">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3028">Checksum</span></span>

<span data-ttu-id="a243a-3029">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3029">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3030">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3030">Definition</span></span>

<span data-ttu-id="a243a-3031">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3031">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3032">正則運算式 Regex_saudi_arabia_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3032">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3033">會找到來自 Keyword_saudi_arabia_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3033">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3034">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3034">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="a243a-3035">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="a243a-3035">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="a243a-3036">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-3036">Identification Card</span></span> 
- <span data-ttu-id="a243a-3037">我的卡片編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3037">I card number</span></span> 
- <span data-ttu-id="a243a-3038">識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3038">ID number</span></span> 
- <span data-ttu-id="a243a-3039">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="a243a-3039">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="a243a-3040">新加坡國家註冊身分識別卡片（NRIC）號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3040">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3041">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3041">Format</span></span>

<span data-ttu-id="a243a-3042">九個字母和數位</span><span class="sxs-lookup"><span data-stu-id="a243a-3042">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3043">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3043">Pattern</span></span>

- <span data-ttu-id="a243a-3044">九個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="a243a-3044">Nine letters and digits:</span></span>
- <span data-ttu-id="a243a-3045">字母 "F"、"G"、"S" 或 "T" （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-3045">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="a243a-3046">七位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3046">Seven digits</span></span> 
- <span data-ttu-id="a243a-3047">字母檢查碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3047">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3048">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3048">Checksum</span></span>

<span data-ttu-id="a243a-3049">是</span><span class="sxs-lookup"><span data-stu-id="a243a-3049">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3050">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3050">Definition</span></span>

<span data-ttu-id="a243a-3051">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3051">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3052">正則運算式 Regex_singapore_nric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3052">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3053">會找到來自 Keyword_singapore_nric 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3053">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="a243a-3054">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-3054">The checksum passes.</span></span>

<span data-ttu-id="a243a-3055">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3055">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3056">正則運算式 Regex_singapore_nric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3056">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3057">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-3057">The checksum passes.</span></span>

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3058">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3058">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="a243a-3059">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="a243a-3059">Keyword_singapore_nric</span></span>

- <span data-ttu-id="a243a-3060">國家註冊身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-3060">National Registration Identity Card</span></span> 
- <span data-ttu-id="a243a-3061">身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3061">Identity Card Number</span></span> 
- <span data-ttu-id="a243a-3062">NRIC</span><span class="sxs-lookup"><span data-stu-id="a243a-3062">NRIC</span></span> 
- <span data-ttu-id="a243a-3063">Ic</span><span class="sxs-lookup"><span data-stu-id="a243a-3063">IC</span></span> 
- <span data-ttu-id="a243a-3064">外識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3064">Foreign Identification Number</span></span> 
- <span data-ttu-id="a243a-3065">翅</span><span class="sxs-lookup"><span data-stu-id="a243a-3065">FIN</span></span> 
- <span data-ttu-id="a243a-3066">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-3066">身份证</span></span> 
- <span data-ttu-id="a243a-3067">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-3067">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="a243a-3068">南非識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3068">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3069">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3069">Format</span></span>

<span data-ttu-id="a243a-3070">可以包含空格的13位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3070">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3071">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3071">Pattern</span></span>

<span data-ttu-id="a243a-3072">13位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-3072">13 digits:</span></span>
- <span data-ttu-id="a243a-3073">YYMMDD 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3073">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a243a-3074">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3074">Four digits</span></span> 
- <span data-ttu-id="a243a-3075">單一數位的公民指示器</span><span class="sxs-lookup"><span data-stu-id="a243a-3075">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="a243a-3076">數位 "8" 或 "9"</span><span class="sxs-lookup"><span data-stu-id="a243a-3076">The digit "8" or "9"</span></span> 
- <span data-ttu-id="a243a-3077">一個數位的校驗和位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3077">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3078">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3078">Checksum</span></span>

<span data-ttu-id="a243a-3079">是</span><span class="sxs-lookup"><span data-stu-id="a243a-3079">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3080">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3080">Definition</span></span>

<span data-ttu-id="a243a-3081">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3081">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3082">函數 Func_south_africa_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3082">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3083">會找到來自 Keyword_south_africa_identification_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3083">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="a243a-3084">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-3084">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3085">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3085">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="a243a-3086">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="a243a-3086">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="a243a-3087">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-3087">Identity card</span></span>
- <span data-ttu-id="a243a-3088">ID</span><span class="sxs-lookup"><span data-stu-id="a243a-3088">ID</span></span>
- <span data-ttu-id="a243a-3089">識別</span><span class="sxs-lookup"><span data-stu-id="a243a-3089">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="a243a-3090">韓國居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3090">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3091">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3091">Format</span></span>

<span data-ttu-id="a243a-3092">13位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-3092">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3093">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3093">Pattern</span></span>

<span data-ttu-id="a243a-3094">13位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-3094">13 digits:</span></span>
- <span data-ttu-id="a243a-3095">YYMMDD 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3095">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a243a-3096">連字號</span><span class="sxs-lookup"><span data-stu-id="a243a-3096">A hyphen</span></span> 
- <span data-ttu-id="a243a-3097">一個數位是由世紀和性別決定</span><span class="sxs-lookup"><span data-stu-id="a243a-3097">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="a243a-3098">四位數的出生區功能變數代碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3098">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="a243a-3099">一種用來區分先前號碼相同之人員的數位</span><span class="sxs-lookup"><span data-stu-id="a243a-3099">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="a243a-3100">檢查碼。</span><span class="sxs-lookup"><span data-stu-id="a243a-3100">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3101">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3101">Checksum</span></span>

<span data-ttu-id="a243a-3102">是</span><span class="sxs-lookup"><span data-stu-id="a243a-3102">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3103">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3103">Definition</span></span>

<span data-ttu-id="a243a-3104">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3104">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3105">函數 Func_south_korea_resident_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3105">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3106">會找到來自 Keyword_south_korea_resident_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3106">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="a243a-3107">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-3107">The checksum passes.</span></span>

<span data-ttu-id="a243a-3108">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3108">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3109">函數 Func_south_korea_resident_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3109">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3110">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-3110">The checksum passes.</span></span>

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3111">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3111">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="a243a-3112">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="a243a-3112">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="a243a-3113">國民身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-3113">National ID card</span></span> 
- <span data-ttu-id="a243a-3114">公民註冊號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3114">Citizen's Registration Number</span></span> 
- <span data-ttu-id="a243a-3115">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="a243a-3115">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="a243a-3116">RRN</span><span class="sxs-lookup"><span data-stu-id="a243a-3116">RRN</span></span> 
- <span data-ttu-id="a243a-3117">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="a243a-3117">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="a243a-3118">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="a243a-3118">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3119">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3119">Format</span></span>

<span data-ttu-id="a243a-3120">11-12 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3120">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3121">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3121">Pattern</span></span>

<span data-ttu-id="a243a-3122">11-12 位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-3122">11-12 digits:</span></span>
- <span data-ttu-id="a243a-3123">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3123">Two digits</span></span> 
- <span data-ttu-id="a243a-3124">一個正斜線（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-3124">A forward slash (optional)</span></span> 
- <span data-ttu-id="a243a-3125">7-8 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3125">7-8 digits</span></span> 
- <span data-ttu-id="a243a-3126">一個正斜線（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-3126">A forward slash (optional)</span></span> 
- <span data-ttu-id="a243a-3127">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3127">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3128">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3128">Checksum</span></span>

<span data-ttu-id="a243a-3129">是</span><span class="sxs-lookup"><span data-stu-id="a243a-3129">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3130">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3130">Definition</span></span>

<span data-ttu-id="a243a-3131">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3132">函數 Func_spanish_social_security_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3132">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3133">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-3133">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3134">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3134">Keywords</span></span>

<span data-ttu-id="a243a-3135">無</span><span class="sxs-lookup"><span data-stu-id="a243a-3135">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="a243a-3136">SQL Server 連接字串</span><span class="sxs-lookup"><span data-stu-id="a243a-3136">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3137">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3137">Format</span></span>

<span data-ttu-id="a243a-3138">字串 "User Id"、"User ID"、"uid" 或 "UserId"，後面加上下列模式中所述的字元及字串。</span><span class="sxs-lookup"><span data-stu-id="a243a-3138">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3139">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3139">Pattern</span></span>

- <span data-ttu-id="a243a-3140">字串 "User Id"、"User ID"、"uid" 或 "UserId"</span><span class="sxs-lookup"><span data-stu-id="a243a-3140">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="a243a-3141">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="a243a-3141">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="a243a-3142">字串 "Password" 或 "pwd"，其中 "pwd" 前面不是小寫字母</span><span class="sxs-lookup"><span data-stu-id="a243a-3142">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="a243a-3143">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-3143">An equal sign (=)</span></span>
- <span data-ttu-id="a243a-3144">不是貨幣符號（$）的任何字元、百分比符號（%）、大於符號（>）、符號（@）、引號（"）、分號（;)、左大括弧（[）或左中括弧（{）</span><span class="sxs-lookup"><span data-stu-id="a243a-3144">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="a243a-3145">任何7-128 個字元的組合，不是分號（;)、正斜線（/）或引號（"）</span><span class="sxs-lookup"><span data-stu-id="a243a-3145">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="a243a-3146">一個分號（;)或引號（"）</span><span class="sxs-lookup"><span data-stu-id="a243a-3146">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3147">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3147">Checksum</span></span>

<span data-ttu-id="a243a-3148">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3148">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3149">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3149">Definition</span></span>

<span data-ttu-id="a243a-3150">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3150">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3151">正則運算式 CEP_Regex_SQLServerConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3151">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3152">找**不**到來自 CEP_GlobalFilter 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3152">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="a243a-3153">正則運算式**CEP_PasswordPlaceHolder 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3153">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3154">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3154">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3155">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3155">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="a243a-3156">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="a243a-3156">CEP_GlobalFilter</span></span>

- <span data-ttu-id="a243a-3157">部分密碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3157">some-password</span></span>
- <span data-ttu-id="a243a-3158">somepassword</span><span class="sxs-lookup"><span data-stu-id="a243a-3158">somepassword</span></span>
- <span data-ttu-id="a243a-3159">secretPassword</span><span class="sxs-lookup"><span data-stu-id="a243a-3159">secretPassword</span></span>
- <span data-ttu-id="a243a-3160">樣品</span><span class="sxs-lookup"><span data-stu-id="a243a-3160">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="a243a-3161">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="a243a-3161">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="a243a-3162">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="a243a-3162">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a243a-3163">密碼或密碼後接0-2 個空格、等號（=）、0-2 空間及星號（\*）-OR------------------</span><span class="sxs-lookup"><span data-stu-id="a243a-3163">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="a243a-3164">密碼或密碼，接著：</span><span class="sxs-lookup"><span data-stu-id="a243a-3164">Password or pwd followed by:</span></span>
    - <span data-ttu-id="a243a-3165">等號（=）</span><span class="sxs-lookup"><span data-stu-id="a243a-3165">Equal sign (=)</span></span>
    - <span data-ttu-id="a243a-3166">小於符號（<）</span><span class="sxs-lookup"><span data-stu-id="a243a-3166">Less than symbol (<)</span></span>
    - <span data-ttu-id="a243a-3167">1-200 個字元的任何組合，其大小大寫或小寫字母、數位、星號（\*）、連字號（-）、底線（_）或空白字元</span><span class="sxs-lookup"><span data-stu-id="a243a-3167">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="a243a-3168">大於符號（>）</span><span class="sxs-lookup"><span data-stu-id="a243a-3168">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="a243a-3169">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="a243a-3169">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="a243a-3170">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="a243a-3170">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="a243a-3171">尚未</span><span class="sxs-lookup"><span data-stu-id="a243a-3171">contoso</span></span>
- <span data-ttu-id="a243a-3172">送交</span><span class="sxs-lookup"><span data-stu-id="a243a-3172">fabrikam</span></span>
- <span data-ttu-id="a243a-3173">資料庫</span><span class="sxs-lookup"><span data-stu-id="a243a-3173">northwind</span></span>
- <span data-ttu-id="a243a-3174">沙 箱</span><span class="sxs-lookup"><span data-stu-id="a243a-3174">sandbox</span></span>
- <span data-ttu-id="a243a-3175">onebox</span><span class="sxs-lookup"><span data-stu-id="a243a-3175">onebox</span></span>
- <span data-ttu-id="a243a-3176">本地 主機</span><span class="sxs-lookup"><span data-stu-id="a243a-3176">localhost</span></span>
- <span data-ttu-id="a243a-3177">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="a243a-3177">127.0.0.1</span></span>
- <span data-ttu-id="a243a-3178">testacs.</span><span class="sxs-lookup"><span data-stu-id="a243a-3178">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-3179">Com</span><span class="sxs-lookup"><span data-stu-id="a243a-3179">com</span></span>
- <span data-ttu-id="a243a-3180">s-int。</span><span class="sxs-lookup"><span data-stu-id="a243a-3180">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="a243a-3181">網</span><span class="sxs-lookup"><span data-stu-id="a243a-3181">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="a243a-3182">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="a243a-3182">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3183">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3183">Format</span></span>

<span data-ttu-id="a243a-3184">10或12位數和選擇性分隔符號</span><span class="sxs-lookup"><span data-stu-id="a243a-3184">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3185">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3185">Pattern</span></span>

<span data-ttu-id="a243a-3186">10或12位數和選用的分隔符號：</span><span class="sxs-lookup"><span data-stu-id="a243a-3186">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="a243a-3187">2-4 位數（選用）</span><span class="sxs-lookup"><span data-stu-id="a243a-3187">2-4 digits (optional)</span></span> 
- <span data-ttu-id="a243a-3188">日期格式 YYMMDD 的六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3188">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="a243a-3189">分隔符號 "-" 或 "+" （選用），加上</span><span class="sxs-lookup"><span data-stu-id="a243a-3189">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="a243a-3190">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3190">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3191">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3191">Checksum</span></span>

<span data-ttu-id="a243a-3192">是</span><span class="sxs-lookup"><span data-stu-id="a243a-3192">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3193">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3193">Definition</span></span>

<span data-ttu-id="a243a-3194">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3194">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3195">函數 Func_swedish_national_identifier 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3195">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3196">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-3196">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3197">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3197">Keywords</span></span>

<span data-ttu-id="a243a-3198">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3198">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="a243a-3199">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3199">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3200">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3200">Format</span></span>

<span data-ttu-id="a243a-3201">八位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3201">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3202">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3202">Pattern</span></span>

<span data-ttu-id="a243a-3203">八個連續數位</span><span class="sxs-lookup"><span data-stu-id="a243a-3203">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3204">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3204">Checksum</span></span>

<span data-ttu-id="a243a-3205">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3205">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3206">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3206">Definition</span></span>

<span data-ttu-id="a243a-3207">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3208">正則運算式 Regex_sweden_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3208">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3209">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="a243a-3209">One of the following is true:</span></span>
    - <span data-ttu-id="a243a-3210">會找到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3210">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="a243a-3211">會找到來自 Keyword_sweden_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3211">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3212">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3212">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="a243a-3213">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="a243a-3213">Keyword_sweden_passport</span></span>

- <span data-ttu-id="a243a-3214">簽證要求</span><span class="sxs-lookup"><span data-stu-id="a243a-3214">visa requirements</span></span> 
- <span data-ttu-id="a243a-3215">外部註冊卡</span><span class="sxs-lookup"><span data-stu-id="a243a-3215">Alien Registration Card</span></span> 
- <span data-ttu-id="a243a-3216">Schengen 簽證</span><span class="sxs-lookup"><span data-stu-id="a243a-3216">Schengen visas</span></span> 
- <span data-ttu-id="a243a-3217">Schengen 簽證</span><span class="sxs-lookup"><span data-stu-id="a243a-3217">Schengen visa</span></span> 
- <span data-ttu-id="a243a-3218">簽證處理</span><span class="sxs-lookup"><span data-stu-id="a243a-3218">Visa Processing</span></span> 
- <span data-ttu-id="a243a-3219">簽證類型</span><span class="sxs-lookup"><span data-stu-id="a243a-3219">Visa Type</span></span> 
- <span data-ttu-id="a243a-3220">單一專案</span><span class="sxs-lookup"><span data-stu-id="a243a-3220">Single Entry</span></span> 
- <span data-ttu-id="a243a-3221">多重專案</span><span class="sxs-lookup"><span data-stu-id="a243a-3221">Multiple Entry</span></span> 
- <span data-ttu-id="a243a-3222">G3 處理費用</span><span class="sxs-lookup"><span data-stu-id="a243a-3222">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="a243a-3223">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a243a-3223">Keyword_passport</span></span>

- <span data-ttu-id="a243a-3224">護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3224">Passport Number</span></span> 
- <span data-ttu-id="a243a-3225">護照否</span><span class="sxs-lookup"><span data-stu-id="a243a-3225">Passport No</span></span> 
- <span data-ttu-id="a243a-3226">護照#</span><span class="sxs-lookup"><span data-stu-id="a243a-3226">Passport #</span></span> 
- <span data-ttu-id="a243a-3227">護照#</span><span class="sxs-lookup"><span data-stu-id="a243a-3227">Passport#</span></span> 
- <span data-ttu-id="a243a-3228">PassportID</span><span class="sxs-lookup"><span data-stu-id="a243a-3228">PassportID</span></span> 
- <span data-ttu-id="a243a-3229">Passportno</span><span class="sxs-lookup"><span data-stu-id="a243a-3229">Passportno</span></span> 
- <span data-ttu-id="a243a-3230">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-3230">passportnumber</span></span> 
- <span data-ttu-id="a243a-3231">パスポート</span><span class="sxs-lookup"><span data-stu-id="a243a-3231">パスポート</span></span> 
- <span data-ttu-id="a243a-3232">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="a243a-3232">パスポート番号</span></span> 
- <span data-ttu-id="a243a-3233">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a243a-3233">パスポートのNum</span></span> 
- <span data-ttu-id="a243a-3234">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a243a-3234">パスポート＃</span></span> 
- <span data-ttu-id="a243a-3235">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a243a-3235">Numéro de passeport</span></span> 
- <span data-ttu-id="a243a-3236">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a243a-3236">Passeport n °</span></span> 
- <span data-ttu-id="a243a-3237">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="a243a-3237">Passeport Non</span></span> 
- <span data-ttu-id="a243a-3238">Passeport#</span><span class="sxs-lookup"><span data-stu-id="a243a-3238">Passeport #</span></span> 
- <span data-ttu-id="a243a-3239">Passeport#</span><span class="sxs-lookup"><span data-stu-id="a243a-3239">Passeport#</span></span> 
- <span data-ttu-id="a243a-3240">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a243a-3240">PasseportNon</span></span> 
- <span data-ttu-id="a243a-3241">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a243a-3241">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="a243a-3242">SWIFT 程式碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3242">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3243">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3243">Format</span></span>

<span data-ttu-id="a243a-3244">四個字母后接5-31 個字母或數位</span><span class="sxs-lookup"><span data-stu-id="a243a-3244">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3245">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3245">Pattern</span></span>

<span data-ttu-id="a243a-3246">四個字母后接5-31 個字母或數位：</span><span class="sxs-lookup"><span data-stu-id="a243a-3246">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="a243a-3247">四個字母的銀行代碼（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-3247">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="a243a-3248">選擇性的空格</span><span class="sxs-lookup"><span data-stu-id="a243a-3248">An optional space</span></span> 
- <span data-ttu-id="a243a-3249">4-28 個字母或數位（基本銀行帳戶號碼（BBAN））</span><span class="sxs-lookup"><span data-stu-id="a243a-3249">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="a243a-3250">選擇性的空格</span><span class="sxs-lookup"><span data-stu-id="a243a-3250">An optional space</span></span> 
- <span data-ttu-id="a243a-3251">1-3 個字母或數位（BBAN 的其餘部分）</span><span class="sxs-lookup"><span data-stu-id="a243a-3251">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3252">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3252">Checksum</span></span>

<span data-ttu-id="a243a-3253">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3253">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3254">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3254">Definition</span></span>

<span data-ttu-id="a243a-3255">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3256">正則運算式 Regex_swift 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3256">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3257">會找到來自 Keyword_swift 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3257">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3258">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3258">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="a243a-3259">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="a243a-3259">Keyword_swift</span></span>

- <span data-ttu-id="a243a-3260">標準化9362的國際組織</span><span class="sxs-lookup"><span data-stu-id="a243a-3260">international organization for standardization 9362</span></span> 
- <span data-ttu-id="a243a-3261">iso 9362</span><span class="sxs-lookup"><span data-stu-id="a243a-3261">iso 9362</span></span> 
- <span data-ttu-id="a243a-3262">iso9362</span><span class="sxs-lookup"><span data-stu-id="a243a-3262">iso9362</span></span> 
- <span data-ttu-id="a243a-3263">迅速\#</span><span class="sxs-lookup"><span data-stu-id="a243a-3263">swift\#</span></span> 
- <span data-ttu-id="a243a-3264">swiftcode</span><span class="sxs-lookup"><span data-stu-id="a243a-3264">swiftcode</span></span> 
- <span data-ttu-id="a243a-3265">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-3265">swiftnumber</span></span> 
- <span data-ttu-id="a243a-3266">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-3266">swiftroutingnumber</span></span> 
- <span data-ttu-id="a243a-3267">swift 程式碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3267">swift code</span></span> 
- <span data-ttu-id="a243a-3268">swift 號碼#</span><span class="sxs-lookup"><span data-stu-id="a243a-3268">swift number #</span></span> 
- <span data-ttu-id="a243a-3269">swift 路由編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3269">swift routing number</span></span> 
- <span data-ttu-id="a243a-3270">bic 編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3270">bic number</span></span> 
- <span data-ttu-id="a243a-3271">bic 程式碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3271">bic code</span></span> 
- <span data-ttu-id="a243a-3272">bic\#</span><span class="sxs-lookup"><span data-stu-id="a243a-3272">bic \#</span></span> 
- <span data-ttu-id="a243a-3273">bic\#</span><span class="sxs-lookup"><span data-stu-id="a243a-3273">bic\#</span></span> 
- <span data-ttu-id="a243a-3274">銀行識別碼代碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3274">bank identifier code</span></span> 
- <span data-ttu-id="a243a-3275">標準化9362</span><span class="sxs-lookup"><span data-stu-id="a243a-3275">標準化9362</span></span> 
- <span data-ttu-id="a243a-3276">迅速＃</span><span class="sxs-lookup"><span data-stu-id="a243a-3276">迅速＃</span></span> 
- <span data-ttu-id="a243a-3277">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="a243a-3277">SWIFTコード</span></span> 
- <span data-ttu-id="a243a-3278">SWIFT番號</span><span class="sxs-lookup"><span data-stu-id="a243a-3278">SWIFT番号</span></span> 
- <span data-ttu-id="a243a-3279">迅速なルーティング番號</span><span class="sxs-lookup"><span data-stu-id="a243a-3279">迅速なルーティング番号</span></span> 
- <span data-ttu-id="a243a-3280">BIC番號</span><span class="sxs-lookup"><span data-stu-id="a243a-3280">BIC番号</span></span> 
- <span data-ttu-id="a243a-3281">BICコード</span><span class="sxs-lookup"><span data-stu-id="a243a-3281">BICコード</span></span> 
- <span data-ttu-id="a243a-3282">銀行識別コードのための國際組織</span><span class="sxs-lookup"><span data-stu-id="a243a-3282">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="a243a-3283">組織 internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="a243a-3283">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="a243a-3284">rapide\#</span><span class="sxs-lookup"><span data-stu-id="a243a-3284">rapide \#</span></span> 
- <span data-ttu-id="a243a-3285">程式碼 SWIFT</span><span class="sxs-lookup"><span data-stu-id="a243a-3285">code SWIFT</span></span> 
- <span data-ttu-id="a243a-3286">le numéro 解除的 swift</span><span class="sxs-lookup"><span data-stu-id="a243a-3286">le numéro de swift</span></span> 
- <span data-ttu-id="a243a-3287">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="a243a-3287">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="a243a-3288">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="a243a-3288">le numéro BIC</span></span> 
- <span data-ttu-id="a243a-3289">\#BIC</span><span class="sxs-lookup"><span data-stu-id="a243a-3289">\# BIC</span></span> 
- <span data-ttu-id="a243a-3290">程式碼 identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="a243a-3290">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="a243a-3291">臺灣國家 ID</span><span class="sxs-lookup"><span data-stu-id="a243a-3291">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3292">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3292">Format</span></span>

<span data-ttu-id="a243a-3293">一個字母（英文）後後的九位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3293">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3294">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3294">Pattern</span></span>

<span data-ttu-id="a243a-3295">一個字母（英文）後接9位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-3295">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="a243a-3296">一個字母（英文、不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-3296">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="a243a-3297">數位 "1" 或 "2"</span><span class="sxs-lookup"><span data-stu-id="a243a-3297">The digit "1" or "2"</span></span> 
- <span data-ttu-id="a243a-3298">八位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3298">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3299">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3299">Checksum</span></span>

<span data-ttu-id="a243a-3300">是</span><span class="sxs-lookup"><span data-stu-id="a243a-3300">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3301">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3301">Definition</span></span>

<span data-ttu-id="a243a-3302">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3302">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3303">函數 Func_taiwanese_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3303">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3304">會找到來自 Keyword_taiwanese_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3304">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="a243a-3305">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-3305">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3306">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3306">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="a243a-3307">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="a243a-3307">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="a243a-3308">身份證字號</span><span class="sxs-lookup"><span data-stu-id="a243a-3308">身份證字號</span></span> 
- <span data-ttu-id="a243a-3309">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-3309">身份證</span></span> 
- <span data-ttu-id="a243a-3310">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3310">身份證號碼</span></span> 
- <span data-ttu-id="a243a-3311">身份證號</span><span class="sxs-lookup"><span data-stu-id="a243a-3311">身份證號</span></span> 
- <span data-ttu-id="a243a-3312">身分證字號</span><span class="sxs-lookup"><span data-stu-id="a243a-3312">身分證字號</span></span> 
- <span data-ttu-id="a243a-3313">身分證</span><span class="sxs-lookup"><span data-stu-id="a243a-3313">身分證</span></span> 
- <span data-ttu-id="a243a-3314">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3314">身分證號碼</span></span> 
- <span data-ttu-id="a243a-3315">身份證號</span><span class="sxs-lookup"><span data-stu-id="a243a-3315">身份證號</span></span> 
- <span data-ttu-id="a243a-3316">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3316">身分證統一編號</span></span> 
- <span data-ttu-id="a243a-3317">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3317">國民身分證統一編號</span></span> 
- <span data-ttu-id="a243a-3318">簽名</span><span class="sxs-lookup"><span data-stu-id="a243a-3318">簽名</span></span> 
- <span data-ttu-id="a243a-3319">蓋章</span><span class="sxs-lookup"><span data-stu-id="a243a-3319">蓋章</span></span> 
- <span data-ttu-id="a243a-3320">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="a243a-3320">簽名或蓋章</span></span> 
- <span data-ttu-id="a243a-3321">簽章</span><span class="sxs-lookup"><span data-stu-id="a243a-3321">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="a243a-3322">臺灣護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3322">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3323">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3323">Format</span></span>

- <span data-ttu-id="a243a-3324">生物識別護照號碼：9位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3324">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="a243a-3325">非生物識別護照號碼：9位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3325">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3326">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3326">Pattern</span></span>
<span data-ttu-id="a243a-3327">生物識別護照號碼：</span><span class="sxs-lookup"><span data-stu-id="a243a-3327">Biometric passport number:</span></span>
- <span data-ttu-id="a243a-3328">數位 "3"</span><span class="sxs-lookup"><span data-stu-id="a243a-3328">The digit "3"</span></span> 
- <span data-ttu-id="a243a-3329">八位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3329">Eight digits</span></span>

<span data-ttu-id="a243a-3330">無生物識別護照號碼：</span><span class="sxs-lookup"><span data-stu-id="a243a-3330">Non-biometric passport number:</span></span>
- <span data-ttu-id="a243a-3331">九位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3331">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3332">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3332">Checksum</span></span>

<span data-ttu-id="a243a-3333">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3333">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3334">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3334">Definition</span></span>

<span data-ttu-id="a243a-3335">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3336">正則運算式 Regex_taiwan_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3336">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3337">會找到來自 Keyword_taiwan_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3337">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3338">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3338">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="a243a-3339">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="a243a-3339">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="a243a-3340">ROC 護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3340">ROC passport number</span></span> 
- <span data-ttu-id="a243a-3341">護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3341">Passport number</span></span> 
- <span data-ttu-id="a243a-3342">護照否</span><span class="sxs-lookup"><span data-stu-id="a243a-3342">Passport no</span></span> 
- <span data-ttu-id="a243a-3343">護照編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3343">Passport Num</span></span> 
- <span data-ttu-id="a243a-3344">護照#</span><span class="sxs-lookup"><span data-stu-id="a243a-3344">Passport #</span></span> 
- <span data-ttu-id="a243a-3345">護照</span><span class="sxs-lookup"><span data-stu-id="a243a-3345">护照</span></span> 
- <span data-ttu-id="a243a-3346">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="a243a-3346">中華民國護照</span></span> 
- <span data-ttu-id="a243a-3347">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="a243a-3347">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="a243a-3348">臺灣居民憑證（ARC/TARC）號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3348">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3349">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3349">Format</span></span>

<span data-ttu-id="a243a-3350">10個字母和數位</span><span class="sxs-lookup"><span data-stu-id="a243a-3350">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3351">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3351">Pattern</span></span>

<span data-ttu-id="a243a-3352">10個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="a243a-3352">10 letters and digits:</span></span>
- <span data-ttu-id="a243a-3353">兩個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-3353">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="a243a-3354">八位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3354">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3355">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3355">Checksum</span></span>

<span data-ttu-id="a243a-3356">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3356">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3357">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3357">Definition</span></span>

<span data-ttu-id="a243a-3358">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3358">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3359">正則運算式 Regex_taiwan_resident_certificate 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3359">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3360">會找到來自 Keyword_taiwan_resident_certificate 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3360">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3361">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3361">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="a243a-3362">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="a243a-3362">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="a243a-3363">常駐憑證</span><span class="sxs-lookup"><span data-stu-id="a243a-3363">Resident Certificate</span></span> 
- <span data-ttu-id="a243a-3364">常駐 Cert</span><span class="sxs-lookup"><span data-stu-id="a243a-3364">Resident Cert</span></span> 
- <span data-ttu-id="a243a-3365">常駐 Cert。</span><span class="sxs-lookup"><span data-stu-id="a243a-3365">Resident Cert.</span></span> 
- <span data-ttu-id="a243a-3366">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-3366">Identification card</span></span> 
- <span data-ttu-id="a243a-3367">外部居民憑證</span><span class="sxs-lookup"><span data-stu-id="a243a-3367">Alien Resident Certificate</span></span> 
- <span data-ttu-id="a243a-3368">ARC</span><span class="sxs-lookup"><span data-stu-id="a243a-3368">ARC</span></span> 
- <span data-ttu-id="a243a-3369">臺灣地區常駐憑證</span><span class="sxs-lookup"><span data-stu-id="a243a-3369">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="a243a-3370">TARC</span><span class="sxs-lookup"><span data-stu-id="a243a-3370">TARC</span></span> 
- <span data-ttu-id="a243a-3371">居留證</span><span class="sxs-lookup"><span data-stu-id="a243a-3371">居留證</span></span> 
- <span data-ttu-id="a243a-3372">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="a243a-3372">外僑居留證</span></span> 
- <span data-ttu-id="a243a-3373">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="a243a-3373">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="a243a-3374">泰國人口識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3374">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3375">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3375">Format</span></span>

<span data-ttu-id="a243a-3376">13位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3376">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3377">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3377">Pattern</span></span>

<span data-ttu-id="a243a-3378">13位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-3378">13 digits:</span></span>
- <span data-ttu-id="a243a-3379">第一個數位不是0或9</span><span class="sxs-lookup"><span data-stu-id="a243a-3379">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="a243a-3380">12位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3380">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3381">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3381">Checksum</span></span>

<span data-ttu-id="a243a-3382">是</span><span class="sxs-lookup"><span data-stu-id="a243a-3382">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3383">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3383">Definition</span></span>

<span data-ttu-id="a243a-3384">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3384">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3385">函數 Func_Thai_Citizen_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3385">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3386">會找到來自 Keyword_Thai_Citizen_Id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3386">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="a243a-3387">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3387">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3388">函數 Func_Thai_Citizen_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3388">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3389">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3389">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="a243a-3390">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="a243a-3390">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="a243a-3391">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3391">ID Number</span></span>
- <span data-ttu-id="a243a-3392">識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3392">Identification Number</span></span>
- <span data-ttu-id="a243a-3393">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a243a-3393">บัตรประชาชน</span></span>
- <span data-ttu-id="a243a-3394">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a243a-3394">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="a243a-3395">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a243a-3395">บัตรประชาชน</span></span>
- <span data-ttu-id="a243a-3396">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a243a-3396">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="a243a-3397">土耳其國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3397">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3398">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3398">Format</span></span>

<span data-ttu-id="a243a-3399">11位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3399">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3400">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3400">Pattern</span></span>

<span data-ttu-id="a243a-3401">11位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3401">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3402">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3402">Checksum</span></span>

<span data-ttu-id="a243a-3403">是</span><span class="sxs-lookup"><span data-stu-id="a243a-3403">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3404">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3404">Definition</span></span>

<span data-ttu-id="a243a-3405">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3405">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3406">函數 Func_Turkish_National_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3406">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3407">會找到來自 Keyword_Turkish_National_Id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3407">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="a243a-3408">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3408">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3409">函數 Func_Turkish_National_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3409">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3410">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3410">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="a243a-3411">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="a243a-3411">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="a243a-3412">TC Kimlik 否</span><span class="sxs-lookup"><span data-stu-id="a243a-3412">TC Kimlik No</span></span>
- <span data-ttu-id="a243a-3413">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="a243a-3413">TC Kimlik numarası</span></span>
- <span data-ttu-id="a243a-3414">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="a243a-3414">Vatandaşlık numarası</span></span>
- <span data-ttu-id="a243a-3415">Vatandaşlık 否</span><span class="sxs-lookup"><span data-stu-id="a243a-3415">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="a243a-3416">英國。</span><span class="sxs-lookup"><span data-stu-id="a243a-3416">U.K.</span></span> <span data-ttu-id="a243a-3417">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3417">Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3418">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3418">Format</span></span>

<span data-ttu-id="a243a-3419">以指定格式的18個字母和數位的組合</span><span class="sxs-lookup"><span data-stu-id="a243a-3419">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3420">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3420">Pattern</span></span>

<span data-ttu-id="a243a-3421">18個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="a243a-3421">18 letters and digits:</span></span>
- <span data-ttu-id="a243a-3422">五個字母（不區分大小寫）或數位 "9" 取代字母</span><span class="sxs-lookup"><span data-stu-id="a243a-3422">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="a243a-3423">一個數位</span><span class="sxs-lookup"><span data-stu-id="a243a-3423">One digit</span></span> 
- <span data-ttu-id="a243a-3424">MMDDY 日期格式中的5位數（如果驅動程式是女，則為第7個字元 62 51，而不是1到12，則增加50）</span><span class="sxs-lookup"><span data-stu-id="a243a-3424">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="a243a-3425">兩個字母（不區分大小寫）或數位 "9" 取代字母</span><span class="sxs-lookup"><span data-stu-id="a243a-3425">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="a243a-3426">五位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3426">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3427">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3427">Checksum</span></span>

<span data-ttu-id="a243a-3428">是</span><span class="sxs-lookup"><span data-stu-id="a243a-3428">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3429">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3429">Definition</span></span>

<span data-ttu-id="a243a-3430">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3430">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3431">函數 Func_uk_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3431">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3432">會找到來自 Keyword_uk_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3432">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="a243a-3433">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-3433">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3434">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3434">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="a243a-3435">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a243a-3435">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="a243a-3436">DVLA</span><span class="sxs-lookup"><span data-stu-id="a243a-3436">DVLA</span></span> 
- <span data-ttu-id="a243a-3437">淺 vans</span><span class="sxs-lookup"><span data-stu-id="a243a-3437">light vans</span></span> 
- <span data-ttu-id="a243a-3438">quadbikes</span><span class="sxs-lookup"><span data-stu-id="a243a-3438">quadbikes</span></span> 
- <span data-ttu-id="a243a-3439">汽車轎車</span><span class="sxs-lookup"><span data-stu-id="a243a-3439">motor cars</span></span> 
- <span data-ttu-id="a243a-3440">125cc</span><span class="sxs-lookup"><span data-stu-id="a243a-3440">125cc</span></span> 
- <span data-ttu-id="a243a-3441">sidecar</span><span class="sxs-lookup"><span data-stu-id="a243a-3441">sidecar</span></span> 
- <span data-ttu-id="a243a-3442">三輪車</span><span class="sxs-lookup"><span data-stu-id="a243a-3442">tricycles</span></span> 
- <span data-ttu-id="a243a-3443">摩托車</span><span class="sxs-lookup"><span data-stu-id="a243a-3443">motorcycles</span></span> 
- <span data-ttu-id="a243a-3444">photocard 許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-3444">photocard licence</span></span> 
- <span data-ttu-id="a243a-3445">learner 驅動程式</span><span class="sxs-lookup"><span data-stu-id="a243a-3445">learner drivers</span></span> 
- <span data-ttu-id="a243a-3446">許可證持有者</span><span class="sxs-lookup"><span data-stu-id="a243a-3446">licence holder</span></span> 
- <span data-ttu-id="a243a-3447">許可證持有人</span><span class="sxs-lookup"><span data-stu-id="a243a-3447">licence holders</span></span> 
- <span data-ttu-id="a243a-3448">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-3448">driving licences</span></span> 
- <span data-ttu-id="a243a-3449">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-3449">driving licence</span></span> 
- <span data-ttu-id="a243a-3450">雙控制汽車</span><span class="sxs-lookup"><span data-stu-id="a243a-3450">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="a243a-3451">英國。</span><span class="sxs-lookup"><span data-stu-id="a243a-3451">U.K.</span></span> <span data-ttu-id="a243a-3452">Electoral 編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3452">Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3453">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3453">Format</span></span>

<span data-ttu-id="a243a-3454">兩個字母后接1-4 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3454">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3455">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3455">Pattern</span></span>

<span data-ttu-id="a243a-3456">兩個字母（不區分大小寫）後接1-4 數目</span><span class="sxs-lookup"><span data-stu-id="a243a-3456">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3457">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3457">Checksum</span></span>

<span data-ttu-id="a243a-3458">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3458">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3459">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3459">Definition</span></span>

<span data-ttu-id="a243a-3460">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3460">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3461">正則運算式 Regex_uk_electoral 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3461">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3462">會找到來自 Keyword_uk_electoral 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3462">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3463">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3463">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="a243a-3464">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="a243a-3464">Keyword_uk_electoral</span></span>

- <span data-ttu-id="a243a-3465">理事會提名</span><span class="sxs-lookup"><span data-stu-id="a243a-3465">council nomination</span></span> 
- <span data-ttu-id="a243a-3466">提名表單</span><span class="sxs-lookup"><span data-stu-id="a243a-3466">nomination form</span></span> 
- <span data-ttu-id="a243a-3467">electoral 寄存器</span><span class="sxs-lookup"><span data-stu-id="a243a-3467">electoral register</span></span> 
- <span data-ttu-id="a243a-3468">electoral 輥</span><span class="sxs-lookup"><span data-stu-id="a243a-3468">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="a243a-3469">英國。</span><span class="sxs-lookup"><span data-stu-id="a243a-3469">U.K.</span></span> <span data-ttu-id="a243a-3470">本國健康情況服務號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3470">National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3471">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3471">Format</span></span>

<span data-ttu-id="a243a-3472">以空格分隔的10-17 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3472">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3473">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3473">Pattern</span></span>

<span data-ttu-id="a243a-3474">10-17 位數：</span><span class="sxs-lookup"><span data-stu-id="a243a-3474">10-17 digits:</span></span>
- <span data-ttu-id="a243a-3475">3或10位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3475">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="a243a-3476">一個空格</span><span class="sxs-lookup"><span data-stu-id="a243a-3476">A space</span></span> 
- <span data-ttu-id="a243a-3477">三位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3477">Three digits</span></span> 
- <span data-ttu-id="a243a-3478">一個空格</span><span class="sxs-lookup"><span data-stu-id="a243a-3478">A space</span></span> 
- <span data-ttu-id="a243a-3479">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3479">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3480">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3480">Checksum</span></span>

<span data-ttu-id="a243a-3481">是</span><span class="sxs-lookup"><span data-stu-id="a243a-3481">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3482">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3482">Definition</span></span>

<span data-ttu-id="a243a-3483">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3483">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3484">函數 Func_uk_nhs_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3484">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3485">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="a243a-3485">One of the following is true:</span></span>
    - <span data-ttu-id="a243a-3486">會找到來自 Keyword_uk_nhs_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3486">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="a243a-3487">會找到來自 Keyword_uk_nhs_number1 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3487">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="a243a-3488">會找到來自 Keyword_uk_nhs_number_dob 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3488">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="a243a-3489">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="a243a-3489">The checksum passes.</span></span>

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3490">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3490">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="a243a-3491">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="a243a-3491">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="a243a-3492">全國健康情況服務</span><span class="sxs-lookup"><span data-stu-id="a243a-3492">national health service</span></span> 
- <span data-ttu-id="a243a-3493">Nhs</span><span class="sxs-lookup"><span data-stu-id="a243a-3493">nhs</span></span> 
- <span data-ttu-id="a243a-3494">健康情況服務授權</span><span class="sxs-lookup"><span data-stu-id="a243a-3494">health services authority</span></span> 
- <span data-ttu-id="a243a-3495">健康情況授權單位</span><span class="sxs-lookup"><span data-stu-id="a243a-3495">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="a243a-3496">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="a243a-3496">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="a243a-3497">患者識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3497">patient id</span></span> 
- <span data-ttu-id="a243a-3498">患者識別</span><span class="sxs-lookup"><span data-stu-id="a243a-3498">patient identification</span></span> 
- <span data-ttu-id="a243a-3499">患者否</span><span class="sxs-lookup"><span data-stu-id="a243a-3499">patient no</span></span> 
- <span data-ttu-id="a243a-3500">病人編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3500">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="a243a-3501">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="a243a-3501">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="a243a-3502">Gp</span><span class="sxs-lookup"><span data-stu-id="a243a-3502">GP</span></span> 
- <span data-ttu-id="a243a-3503">DOB</span><span class="sxs-lookup"><span data-stu-id="a243a-3503">DOB</span></span> 
- <span data-ttu-id="a243a-3504">D. B</span><span class="sxs-lookup"><span data-stu-id="a243a-3504">D.O.B</span></span> 
- <span data-ttu-id="a243a-3505">出生日期</span><span class="sxs-lookup"><span data-stu-id="a243a-3505">Date of Birth</span></span> 
- <span data-ttu-id="a243a-3506">出生日期</span><span class="sxs-lookup"><span data-stu-id="a243a-3506">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="a243a-3507">英國。</span><span class="sxs-lookup"><span data-stu-id="a243a-3507">U.K.</span></span> <span data-ttu-id="a243a-3508">本國保險號碼（NINO）</span><span class="sxs-lookup"><span data-stu-id="a243a-3508">National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3509">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3509">Format</span></span>

<span data-ttu-id="a243a-3510">以空格或破折號分隔的7個字元或9個字元</span><span class="sxs-lookup"><span data-stu-id="a243a-3510">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3511">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3511">Pattern</span></span>

<span data-ttu-id="a243a-3512">兩種可能的模式：</span><span class="sxs-lookup"><span data-stu-id="a243a-3512">Two possible patterns:</span></span>

- <span data-ttu-id="a243a-3513">兩個字母（有效的 NINOs 只會使用此前置詞中的特定字元，此模式會驗證; 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-3513">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="a243a-3514">六位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3514">Six digits</span></span>
- <span data-ttu-id="a243a-3515">"A"、"B"、"C" 或 "d" （類似前置詞）只允許在尾碼中使用某些字元; 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="a243a-3515">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="a243a-3516">OR</span><span class="sxs-lookup"><span data-stu-id="a243a-3516">OR</span></span>

- <span data-ttu-id="a243a-3517">兩個字母</span><span class="sxs-lookup"><span data-stu-id="a243a-3517">Two letters</span></span>
- <span data-ttu-id="a243a-3518">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="a243a-3518">A space or dash</span></span>
- <span data-ttu-id="a243a-3519">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3519">Two digits</span></span>
- <span data-ttu-id="a243a-3520">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="a243a-3520">A space or dash</span></span>
- <span data-ttu-id="a243a-3521">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3521">Two digits</span></span>
- <span data-ttu-id="a243a-3522">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="a243a-3522">A space or dash</span></span>
- <span data-ttu-id="a243a-3523">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3523">Two digits</span></span>
- <span data-ttu-id="a243a-3524">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="a243a-3524">A space or dash</span></span>
- <span data-ttu-id="a243a-3525">' A '、' B '、' C ' 或 ' d ' 是 '</span><span class="sxs-lookup"><span data-stu-id="a243a-3525">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3526">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3526">Checksum</span></span>

<span data-ttu-id="a243a-3527">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3527">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3528">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3528">Definition</span></span>

<span data-ttu-id="a243a-3529">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3530">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3530">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3531">會找到來自 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3531">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="a243a-3532">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3532">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3533">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3533">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3534">找不到 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3534">No keyword from Keyword_uk_nino is found.</span></span>

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3535">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3535">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="a243a-3536">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="a243a-3536">Keyword_uk_nino</span></span>

- <span data-ttu-id="a243a-3537">本國保險號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3537">national insurance number</span></span> 
- <span data-ttu-id="a243a-3538">全國保險貢獻</span><span class="sxs-lookup"><span data-stu-id="a243a-3538">national insurance contributions</span></span> 
- <span data-ttu-id="a243a-3539">保護法案</span><span class="sxs-lookup"><span data-stu-id="a243a-3539">protection act</span></span> 
- <span data-ttu-id="a243a-3540">保險</span><span class="sxs-lookup"><span data-stu-id="a243a-3540">insurance</span></span> 
- <span data-ttu-id="a243a-3541">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3541">social security number</span></span> 
- <span data-ttu-id="a243a-3542">保險費應用程式</span><span class="sxs-lookup"><span data-stu-id="a243a-3542">insurance application</span></span> 
- <span data-ttu-id="a243a-3543">醫療應用程式</span><span class="sxs-lookup"><span data-stu-id="a243a-3543">medical application</span></span> 
- <span data-ttu-id="a243a-3544">社交保險</span><span class="sxs-lookup"><span data-stu-id="a243a-3544">social insurance</span></span> 
- <span data-ttu-id="a243a-3545">醫療注意力</span><span class="sxs-lookup"><span data-stu-id="a243a-3545">medical attention</span></span> 
- <span data-ttu-id="a243a-3546">社會保障</span><span class="sxs-lookup"><span data-stu-id="a243a-3546">social security</span></span> 
- <span data-ttu-id="a243a-3547">英國</span><span class="sxs-lookup"><span data-stu-id="a243a-3547">great britain</span></span> 
- <span data-ttu-id="a243a-3548">保險</span><span class="sxs-lookup"><span data-stu-id="a243a-3548">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="a243a-3549">美國/英國</span><span class="sxs-lookup"><span data-stu-id="a243a-3549">U.S. / U.K.</span></span> <span data-ttu-id="a243a-3550">護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3550">Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3551">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3551">Format</span></span>

<span data-ttu-id="a243a-3552">九位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3552">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3553">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3553">Pattern</span></span>

<span data-ttu-id="a243a-3554">九個連續數位</span><span class="sxs-lookup"><span data-stu-id="a243a-3554">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3555">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3555">Checksum</span></span>

<span data-ttu-id="a243a-3556">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3556">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3557">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3557">Definition</span></span>

<span data-ttu-id="a243a-3558">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3558">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3559">函數 Func_usa_uk_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3559">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3560">會找到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3560">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3561">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3561">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="a243a-3562">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a243a-3562">Keyword_passport</span></span>

- <span data-ttu-id="a243a-3563">護照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3563">Passport Number</span></span> 
- <span data-ttu-id="a243a-3564">護照否</span><span class="sxs-lookup"><span data-stu-id="a243a-3564">Passport No</span></span> 
- <span data-ttu-id="a243a-3565">護照#</span><span class="sxs-lookup"><span data-stu-id="a243a-3565">Passport #</span></span> 
- <span data-ttu-id="a243a-3566">護照#</span><span class="sxs-lookup"><span data-stu-id="a243a-3566">Passport#</span></span> 
- <span data-ttu-id="a243a-3567">PassportID</span><span class="sxs-lookup"><span data-stu-id="a243a-3567">PassportID</span></span> 
- <span data-ttu-id="a243a-3568">Passportno</span><span class="sxs-lookup"><span data-stu-id="a243a-3568">Passportno</span></span> 
- <span data-ttu-id="a243a-3569">passportnumber</span><span class="sxs-lookup"><span data-stu-id="a243a-3569">passportnumber</span></span> 
- <span data-ttu-id="a243a-3570">パスポート</span><span class="sxs-lookup"><span data-stu-id="a243a-3570">パスポート</span></span> 
- <span data-ttu-id="a243a-3571">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="a243a-3571">パスポート番号</span></span> 
- <span data-ttu-id="a243a-3572">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="a243a-3572">パスポートのNum</span></span> 
- <span data-ttu-id="a243a-3573">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="a243a-3573">パスポート＃</span></span> 
- <span data-ttu-id="a243a-3574">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a243a-3574">Numéro de passeport</span></span> 
- <span data-ttu-id="a243a-3575">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a243a-3575">Passeport n °</span></span> 
- <span data-ttu-id="a243a-3576">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="a243a-3576">Passeport Non</span></span> 
- <span data-ttu-id="a243a-3577">Passeport#</span><span class="sxs-lookup"><span data-stu-id="a243a-3577">Passeport #</span></span> 
- <span data-ttu-id="a243a-3578">Passeport#</span><span class="sxs-lookup"><span data-stu-id="a243a-3578">Passeport#</span></span> 
- <span data-ttu-id="a243a-3579">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a243a-3579">PasseportNon</span></span> 
- <span data-ttu-id="a243a-3580">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a243a-3580">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="a243a-3581">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3581">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3582">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3582">Format</span></span>

<span data-ttu-id="a243a-3583">8-17 位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3583">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3584">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3584">Pattern</span></span>

<span data-ttu-id="a243a-3585">8-17 連續位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3585">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3586">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3586">Checksum</span></span>

<span data-ttu-id="a243a-3587">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3587">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3588">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3588">Definition</span></span>

<span data-ttu-id="a243a-3589">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3589">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3590">正則運算式 Regex_usa_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3590">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3591">會找到來自 Keyword_usa_Bank_Account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3591">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3592">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3592">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="a243a-3593">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="a243a-3593">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="a243a-3594">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3594">Checking Account Number</span></span> 
- <span data-ttu-id="a243a-3595">檢查帳戶</span><span class="sxs-lookup"><span data-stu-id="a243a-3595">Checking Account</span></span> 
- <span data-ttu-id="a243a-3596">檢查帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-3596">Checking Account #</span></span> 
- <span data-ttu-id="a243a-3597">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3597">Checking Acct Number</span></span> 
- <span data-ttu-id="a243a-3598">檢查帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-3598">Checking Acct #</span></span> 
- <span data-ttu-id="a243a-3599">檢查帳戶否。</span><span class="sxs-lookup"><span data-stu-id="a243a-3599">Checking Acct No.</span></span> 
- <span data-ttu-id="a243a-3600">檢查帳戶否</span><span class="sxs-lookup"><span data-stu-id="a243a-3600">Checking Account No.</span></span> 
- <span data-ttu-id="a243a-3601">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3601">Bank Account Number</span></span> 
- <span data-ttu-id="a243a-3602">銀行帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-3602">Bank Account #</span></span> 
- <span data-ttu-id="a243a-3603">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3603">Bank Acct Number</span></span> 
- <span data-ttu-id="a243a-3604">銀行帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-3604">Bank Acct #</span></span> 
- <span data-ttu-id="a243a-3605">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3605">Bank Acct No.</span></span> 
- <span data-ttu-id="a243a-3606">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3606">Bank Account No.</span></span> 
- <span data-ttu-id="a243a-3607">儲蓄帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3607">Savings Account Number</span></span> 
- <span data-ttu-id="a243a-3608">儲蓄帳戶。</span><span class="sxs-lookup"><span data-stu-id="a243a-3608">Savings Account.</span></span> 
- <span data-ttu-id="a243a-3609">儲蓄帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-3609">Savings Account #</span></span> 
- <span data-ttu-id="a243a-3610">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3610">Savings Acct Number</span></span> 
- <span data-ttu-id="a243a-3611">儲蓄帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-3611">Savings Acct #</span></span> 
- <span data-ttu-id="a243a-3612">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3612">Savings Acct No.</span></span> 
- <span data-ttu-id="a243a-3613">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3613">Savings Account No.</span></span> 
- <span data-ttu-id="a243a-3614">借方科目編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3614">Debit Account Number</span></span> 
- <span data-ttu-id="a243a-3615">借方科目</span><span class="sxs-lookup"><span data-stu-id="a243a-3615">Debit Account</span></span> 
- <span data-ttu-id="a243a-3616">借方科目#</span><span class="sxs-lookup"><span data-stu-id="a243a-3616">Debit Account #</span></span> 
- <span data-ttu-id="a243a-3617">借方帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3617">Debit Acct Number</span></span> 
- <span data-ttu-id="a243a-3618">借方帳戶#</span><span class="sxs-lookup"><span data-stu-id="a243a-3618">Debit Acct #</span></span> 
- <span data-ttu-id="a243a-3619">借方帳戶編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3619">Debit Acct No.</span></span> 
- <span data-ttu-id="a243a-3620">借方科目編號</span><span class="sxs-lookup"><span data-stu-id="a243a-3620">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="a243a-3621">美國駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3621">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3622">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3622">Format</span></span>

<span data-ttu-id="a243a-3623">取決於狀態</span><span class="sxs-lookup"><span data-stu-id="a243a-3623">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3624">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3624">Pattern</span></span>

<span data-ttu-id="a243a-3625">取決於狀態--例如紐約：</span><span class="sxs-lookup"><span data-stu-id="a243a-3625">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="a243a-3626">已格式化的九位數，如 ddd ddd ddd 會相符。</span><span class="sxs-lookup"><span data-stu-id="a243a-3626">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="a243a-3627">九位數的 ddddddddd 不相符。</span><span class="sxs-lookup"><span data-stu-id="a243a-3627">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3628">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3628">Checksum</span></span>

<span data-ttu-id="a243a-3629">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3629">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3630">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3630">Definition</span></span>

<span data-ttu-id="a243a-3631">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3631">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3632">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3632">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3633">找到來自 Keyword_ [state_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3633">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a243a-3634">會找到來自 Keyword_us_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3634">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="a243a-3635">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3635">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3636">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3636">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3637">找到來自 Keyword_ [state_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3637">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a243a-3638">會找到來自 Keyword_us_drivers_license_abbreviations 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3638">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="a243a-3639">找不到 Keyword_us_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3639">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3640">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3640">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="a243a-3641">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="a243a-3641">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="a243a-3642">Dl</span><span class="sxs-lookup"><span data-stu-id="a243a-3642">DL</span></span> 
- <span data-ttu-id="a243a-3643">Dls</span><span class="sxs-lookup"><span data-stu-id="a243a-3643">DLS</span></span> 
- <span data-ttu-id="a243a-3644">民盟</span><span class="sxs-lookup"><span data-stu-id="a243a-3644">CDL</span></span> 
- <span data-ttu-id="a243a-3645">CDLS</span><span class="sxs-lookup"><span data-stu-id="a243a-3645">CDLS</span></span> 
- <span data-ttu-id="a243a-3646">ID</span><span class="sxs-lookup"><span data-stu-id="a243a-3646">ID</span></span> 
- <span data-ttu-id="a243a-3647">IDs</span><span class="sxs-lookup"><span data-stu-id="a243a-3647">IDs</span></span> 
- <span data-ttu-id="a243a-3648">Dl#</span><span class="sxs-lookup"><span data-stu-id="a243a-3648">DL#</span></span> 
- <span data-ttu-id="a243a-3649">Dls#</span><span class="sxs-lookup"><span data-stu-id="a243a-3649">DLS#</span></span> 
- <span data-ttu-id="a243a-3650">民盟#</span><span class="sxs-lookup"><span data-stu-id="a243a-3650">CDL#</span></span> 
- <span data-ttu-id="a243a-3651">CDLS#</span><span class="sxs-lookup"><span data-stu-id="a243a-3651">CDLS#</span></span> 
- <span data-ttu-id="a243a-3652">ID:#</span><span class="sxs-lookup"><span data-stu-id="a243a-3652">ID#</span></span>
- <span data-ttu-id="a243a-3653">IDs#</span><span class="sxs-lookup"><span data-stu-id="a243a-3653">IDs#</span></span> 
- <span data-ttu-id="a243a-3654">識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3654">ID number</span></span> 
- <span data-ttu-id="a243a-3655">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3655">ID numbers</span></span> 
- <span data-ttu-id="a243a-3656">許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-3656">LIC</span></span> 
- <span data-ttu-id="a243a-3657">許可證#</span><span class="sxs-lookup"><span data-stu-id="a243a-3657">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="a243a-3658">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a243a-3658">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="a243a-3659">DriverLic</span><span class="sxs-lookup"><span data-stu-id="a243a-3659">DriverLic</span></span> 
- <span data-ttu-id="a243a-3660">DriverLics</span><span class="sxs-lookup"><span data-stu-id="a243a-3660">DriverLics</span></span> 
- <span data-ttu-id="a243a-3661">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="a243a-3661">DriverLicense</span></span> 
- <span data-ttu-id="a243a-3662">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="a243a-3662">DriverLicenses</span></span> 
- <span data-ttu-id="a243a-3663">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="a243a-3663">Driver Lic</span></span> 
- <span data-ttu-id="a243a-3664">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-3664">Driver Lics</span></span> 
- <span data-ttu-id="a243a-3665">駕照</span><span class="sxs-lookup"><span data-stu-id="a243a-3665">Driver License</span></span> 
- <span data-ttu-id="a243a-3666">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-3666">Driver Licenses</span></span> 
- <span data-ttu-id="a243a-3667">DriversLic</span><span class="sxs-lookup"><span data-stu-id="a243a-3667">DriversLic</span></span> 
- <span data-ttu-id="a243a-3668">DriversLics</span><span class="sxs-lookup"><span data-stu-id="a243a-3668">DriversLics</span></span> 
- <span data-ttu-id="a243a-3669">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="a243a-3669">DriversLicense</span></span> 
- <span data-ttu-id="a243a-3670">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="a243a-3670">DriversLicenses</span></span> 
- <span data-ttu-id="a243a-3671">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-3671">Drivers Lic</span></span> 
- <span data-ttu-id="a243a-3672">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-3672">Drivers Lics</span></span> 
- <span data-ttu-id="a243a-3673">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-3673">Drivers License</span></span> 
- <span data-ttu-id="a243a-3674">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="a243a-3674">Drivers Licenses</span></span> 
- <span data-ttu-id="a243a-3675">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-3675">Driver'Lic</span></span> 
- <span data-ttu-id="a243a-3676">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-3676">Driver'Lics</span></span> 
- <span data-ttu-id="a243a-3677">Driver'License</span><span class="sxs-lookup"><span data-stu-id="a243a-3677">Driver'License</span></span> 
- <span data-ttu-id="a243a-3678">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="a243a-3678">Driver'Licenses</span></span> 
- <span data-ttu-id="a243a-3679">驅動程式「.Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-3679">Driver' Lic</span></span> 
- <span data-ttu-id="a243a-3680">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-3680">Driver' Lics</span></span> 
- <span data-ttu-id="a243a-3681">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-3681">Driver' License</span></span> 
- <span data-ttu-id="a243a-3682">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="a243a-3682">Driver' Licenses</span></span>
- <span data-ttu-id="a243a-3683">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="a243a-3683">Driver'sLic</span></span> 
- <span data-ttu-id="a243a-3684">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="a243a-3684">Driver'sLics</span></span> 
- <span data-ttu-id="a243a-3685">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="a243a-3685">Driver'sLicense</span></span> 
- <span data-ttu-id="a243a-3686">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="a243a-3686">Driver'sLicenses</span></span> 
- <span data-ttu-id="a243a-3687">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="a243a-3687">Driver's Lic</span></span> 
- <span data-ttu-id="a243a-3688">驅動程式的 Lics</span><span class="sxs-lookup"><span data-stu-id="a243a-3688">Driver's Lics</span></span> 
- <span data-ttu-id="a243a-3689">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-3689">Driver's License</span></span> 
- <span data-ttu-id="a243a-3690">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="a243a-3690">Driver's Licenses</span></span> 
- <span data-ttu-id="a243a-3691">識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3691">identification number</span></span> 
- <span data-ttu-id="a243a-3692">識別號碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3692">identification numbers</span></span> 
- <span data-ttu-id="a243a-3693">識別#</span><span class="sxs-lookup"><span data-stu-id="a243a-3693">identification #</span></span> 
- <span data-ttu-id="a243a-3694">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-3694">id card</span></span> 
- <span data-ttu-id="a243a-3695">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-3695">id cards</span></span> 
- <span data-ttu-id="a243a-3696">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="a243a-3696">identification card</span></span> 
- <span data-ttu-id="a243a-3697">身份證</span><span class="sxs-lookup"><span data-stu-id="a243a-3697">identification cards</span></span> 
- <span data-ttu-id="a243a-3698">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="a243a-3698">DriverLic#</span></span> 
- <span data-ttu-id="a243a-3699">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="a243a-3699">DriverLics#</span></span> 
- <span data-ttu-id="a243a-3700">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="a243a-3700">DriverLicense#</span></span> 
- <span data-ttu-id="a243a-3701">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-3701">DriverLicenses#</span></span> 
- <span data-ttu-id="a243a-3702">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="a243a-3702">Driver Lic#</span></span> 
- <span data-ttu-id="a243a-3703">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-3703">Driver Lics#</span></span> 
- <span data-ttu-id="a243a-3704">駕照#</span><span class="sxs-lookup"><span data-stu-id="a243a-3704">Driver License#</span></span> 
- <span data-ttu-id="a243a-3705">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-3705">Driver Licenses#</span></span> 
- <span data-ttu-id="a243a-3706">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="a243a-3706">DriversLic#</span></span> 
- <span data-ttu-id="a243a-3707">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="a243a-3707">DriversLics#</span></span> 
- <span data-ttu-id="a243a-3708">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="a243a-3708">DriversLicense#</span></span> 
- <span data-ttu-id="a243a-3709">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-3709">DriversLicenses#</span></span> 
- <span data-ttu-id="a243a-3710">驅動程式 .Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-3710">Drivers Lic#</span></span> 
- <span data-ttu-id="a243a-3711">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-3711">Drivers Lics#</span></span> 
- <span data-ttu-id="a243a-3712">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-3712">Drivers License#</span></span> 
- <span data-ttu-id="a243a-3713">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-3713">Drivers Licenses#</span></span> 
- <span data-ttu-id="a243a-3714">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-3714">Driver'Lic#</span></span> 
- <span data-ttu-id="a243a-3715">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-3715">Driver'Lics#</span></span> 
- <span data-ttu-id="a243a-3716">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="a243a-3716">Driver'License#</span></span> 
- <span data-ttu-id="a243a-3717">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-3717">Driver'Licenses#</span></span> 
- <span data-ttu-id="a243a-3718">驅動程式「.Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-3718">Driver' Lic#</span></span> 
- <span data-ttu-id="a243a-3719">驅動程式 ' Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-3719">Driver' Lics#</span></span> 
- <span data-ttu-id="a243a-3720">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-3720">Driver' License#</span></span> 
- <span data-ttu-id="a243a-3721">驅動程式的授權#</span><span class="sxs-lookup"><span data-stu-id="a243a-3721">Driver' Licenses#</span></span> 
- <span data-ttu-id="a243a-3722">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="a243a-3722">Driver'sLic#</span></span> 
- <span data-ttu-id="a243a-3723">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="a243a-3723">Driver'sLics#</span></span> 
- <span data-ttu-id="a243a-3724">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="a243a-3724">Driver'sLicense#</span></span> 
- <span data-ttu-id="a243a-3725">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="a243a-3725">Driver'sLicenses#</span></span> 
- <span data-ttu-id="a243a-3726">驅動程式的 .Lic#</span><span class="sxs-lookup"><span data-stu-id="a243a-3726">Driver's Lic#</span></span> 
- <span data-ttu-id="a243a-3727">驅動程式的 Lics#</span><span class="sxs-lookup"><span data-stu-id="a243a-3727">Driver's Lics#</span></span> 
- <span data-ttu-id="a243a-3728">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-3728">Driver's License#</span></span> 
- <span data-ttu-id="a243a-3729">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="a243a-3729">Driver's Licenses#</span></span> 
- <span data-ttu-id="a243a-3730">身份證#</span><span class="sxs-lookup"><span data-stu-id="a243a-3730">id card#</span></span> 
- <span data-ttu-id="a243a-3731">身份證#</span><span class="sxs-lookup"><span data-stu-id="a243a-3731">id cards#</span></span> 
- <span data-ttu-id="a243a-3732">身分識別卡#</span><span class="sxs-lookup"><span data-stu-id="a243a-3732">identification card#</span></span> 
- <span data-ttu-id="a243a-3733">身份證#</span><span class="sxs-lookup"><span data-stu-id="a243a-3733">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="a243a-3734">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="a243a-3734">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="a243a-3735">省/市/自治區縮寫（例如，"NY"）</span><span class="sxs-lookup"><span data-stu-id="a243a-3735">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="a243a-3736">狀態名稱（例如，"紐約"）</span><span class="sxs-lookup"><span data-stu-id="a243a-3736">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="a243a-3737">美國個別的納稅人識別號碼（ITIN）</span><span class="sxs-lookup"><span data-stu-id="a243a-3737">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3738">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3738">Format</span></span>

<span data-ttu-id="a243a-3739">以 "9" 開頭且包含 "7" 或 "8" 的九位數做為第四位數，可選擇性地使用空格或破折號格式化</span><span class="sxs-lookup"><span data-stu-id="a243a-3739">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3740">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3740">Pattern</span></span>

<span data-ttu-id="a243a-3741">格式 化：</span><span class="sxs-lookup"><span data-stu-id="a243a-3741">Formatted:</span></span>
- <span data-ttu-id="a243a-3742">數位 "9"</span><span class="sxs-lookup"><span data-stu-id="a243a-3742">The digit "9"</span></span> 
- <span data-ttu-id="a243a-3743">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3743">Two digits</span></span> 
- <span data-ttu-id="a243a-3744">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="a243a-3744">A space or dash</span></span> 
- <span data-ttu-id="a243a-3745">"7" 或 "8"</span><span class="sxs-lookup"><span data-stu-id="a243a-3745">A "7" or "8"</span></span> 
- <span data-ttu-id="a243a-3746">一個數位</span><span class="sxs-lookup"><span data-stu-id="a243a-3746">A digit</span></span> 
- <span data-ttu-id="a243a-3747">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="a243a-3747">A space, or dash</span></span> 
- <span data-ttu-id="a243a-3748">四位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3748">Four digits</span></span>

<span data-ttu-id="a243a-3749">非</span><span class="sxs-lookup"><span data-stu-id="a243a-3749">Unformatted:</span></span>
- <span data-ttu-id="a243a-3750">數位 "9"</span><span class="sxs-lookup"><span data-stu-id="a243a-3750">The digit "9"</span></span> 
- <span data-ttu-id="a243a-3751">兩位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3751">Two digits</span></span> 
- <span data-ttu-id="a243a-3752">"7" 或 "8"</span><span class="sxs-lookup"><span data-stu-id="a243a-3752">A "7" or "8"</span></span> 
- <span data-ttu-id="a243a-3753">五位數</span><span class="sxs-lookup"><span data-stu-id="a243a-3753">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3754">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3754">Checksum</span></span>

<span data-ttu-id="a243a-3755">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3755">No</span></span>

### <a name="definition"></a><span data-ttu-id="a243a-3756">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3756">Definition</span></span>

<span data-ttu-id="a243a-3757">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3757">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3758">函數 Func_formatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3758">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3759">下列專案中至少有一個為真：</span><span class="sxs-lookup"><span data-stu-id="a243a-3759">At least one of the following is true:</span></span>
    - <span data-ttu-id="a243a-3760">會找到來自 Keyword_itin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3760">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="a243a-3761">函數 Func_us_address 會找到正確日期格式的位址。</span><span class="sxs-lookup"><span data-stu-id="a243a-3761">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="a243a-3762">函數 Func_us_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a243a-3762">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="a243a-3763">會找到來自 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3763">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="a243a-3764">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3765">函數 Func_unformatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3765">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3766">下列專案中至少有一個為真：</span><span class="sxs-lookup"><span data-stu-id="a243a-3766">At least one of the following is true:</span></span>
    - <span data-ttu-id="a243a-3767">會找到來自 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3767">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="a243a-3768">函數 Func_us_address 會找到正確日期格式的位址。</span><span class="sxs-lookup"><span data-stu-id="a243a-3768">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="a243a-3769">函數 Func_us_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a243a-3769">The function Func_us_date finds a date in the right date format.</span></span>

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3770">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3770">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="a243a-3771">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="a243a-3771">Keyword_itin</span></span>

- <span data-ttu-id="a243a-3772">納稅人</span><span class="sxs-lookup"><span data-stu-id="a243a-3772">taxpayer</span></span> 
- <span data-ttu-id="a243a-3773">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="a243a-3773">tax id</span></span> 
- <span data-ttu-id="a243a-3774">納稅識別</span><span class="sxs-lookup"><span data-stu-id="a243a-3774">tax identification</span></span> 
- <span data-ttu-id="a243a-3775">itin</span><span class="sxs-lookup"><span data-stu-id="a243a-3775">itin</span></span> 
- <span data-ttu-id="a243a-3776">Ssn</span><span class="sxs-lookup"><span data-stu-id="a243a-3776">ssn</span></span> 
- <span data-ttu-id="a243a-3777">錫</span><span class="sxs-lookup"><span data-stu-id="a243a-3777">tin</span></span> 
- <span data-ttu-id="a243a-3778">社會保障</span><span class="sxs-lookup"><span data-stu-id="a243a-3778">social security</span></span> 
- <span data-ttu-id="a243a-3779">納稅人</span><span class="sxs-lookup"><span data-stu-id="a243a-3779">tax payer</span></span> 
- <span data-ttu-id="a243a-3780">itins</span><span class="sxs-lookup"><span data-stu-id="a243a-3780">itins</span></span> 
- <span data-ttu-id="a243a-3781">taxid</span><span class="sxs-lookup"><span data-stu-id="a243a-3781">taxid</span></span> 
- <span data-ttu-id="a243a-3782">個別納稅人</span><span class="sxs-lookup"><span data-stu-id="a243a-3782">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="a243a-3783">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="a243a-3783">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="a243a-3784">License</span><span class="sxs-lookup"><span data-stu-id="a243a-3784">License</span></span> 
- <span data-ttu-id="a243a-3785">Dl</span><span class="sxs-lookup"><span data-stu-id="a243a-3785">DL</span></span> 
- <span data-ttu-id="a243a-3786">DOB</span><span class="sxs-lookup"><span data-stu-id="a243a-3786">DOB</span></span> 
- <span data-ttu-id="a243a-3787">出生日期</span><span class="sxs-lookup"><span data-stu-id="a243a-3787">Birthdate</span></span> 
- <span data-ttu-id="a243a-3788">生日</span><span class="sxs-lookup"><span data-stu-id="a243a-3788">Birthday</span></span> 
- <span data-ttu-id="a243a-3789">出生日期</span><span class="sxs-lookup"><span data-stu-id="a243a-3789">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="a243a-3790">U.S. 社會安全號碼（SSN）</span><span class="sxs-lookup"><span data-stu-id="a243a-3790">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="a243a-3791">格式</span><span class="sxs-lookup"><span data-stu-id="a243a-3791">Format</span></span>

<span data-ttu-id="a243a-3792">9位數（可能是格式化或未格式化的模式）</span><span class="sxs-lookup"><span data-stu-id="a243a-3792">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="a243a-3793">如果在2011之前發出，則 SSN 具有強格式，其中的號碼的某些部分必須介於一定範圍內，才是有效的（但沒有任何 checksum）。</span><span class="sxs-lookup"><span data-stu-id="a243a-3793">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="a243a-3794">模式</span><span class="sxs-lookup"><span data-stu-id="a243a-3794">Pattern</span></span>

<span data-ttu-id="a243a-3795">四種功能會在四種不同的模式中尋找主旨 ssn：</span><span class="sxs-lookup"><span data-stu-id="a243a-3795">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="a243a-3796">Func_ssn 會2011以主旨 ssn 的強格式格式化，並以短劃線或空格格式化（ddd-dd-dddd 或 ddd dd dddd）來尋找</span><span class="sxs-lookup"><span data-stu-id="a243a-3796">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="a243a-3797">Func_unformatted_ssn 會以預先2011的強格式格式化，以格式化為九個連續數位（ddddddddd）的主旨 ssn，來尋找</span><span class="sxs-lookup"><span data-stu-id="a243a-3797">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="a243a-3798">Func_randomized_formatted_ssn 會找到以短劃線或空格格式化的2011後主旨 ssn （ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="a243a-3798">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="a243a-3799">Func_randomized_unformatted_ssn 尋找未格式化為九個連續數位的2011後主旨 ssn （ddddddddd）</span><span class="sxs-lookup"><span data-stu-id="a243a-3799">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="a243a-3800">校驗</span><span class="sxs-lookup"><span data-stu-id="a243a-3800">Checksum</span></span>

<span data-ttu-id="a243a-3801">否</span><span class="sxs-lookup"><span data-stu-id="a243a-3801">No</span></span>


### <a name="definition"></a><span data-ttu-id="a243a-3802">定義</span><span class="sxs-lookup"><span data-stu-id="a243a-3802">Definition</span></span>

<span data-ttu-id="a243a-3803">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3803">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3804">函數 Func_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3804">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3805">會找到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3805">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="a243a-3806">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3807">函數 Func_unformatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3807">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3808">會找到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3808">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="a243a-3809">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3809">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3810">函數 Func_randomized_formatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3810">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3811">會找到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3811">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="a243a-3812">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是55%：</span><span class="sxs-lookup"><span data-stu-id="a243a-3812">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a243a-3813">函數 Func_randomized_unformatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="a243a-3813">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a243a-3814">會找到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="a243a-3814">A keyword from Keyword_ssn is found.</span></span>


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a243a-3815">關鍵字</span><span class="sxs-lookup"><span data-stu-id="a243a-3815">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="a243a-3816">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="a243a-3816">Keyword_ssn</span></span>

- <span data-ttu-id="a243a-3817">社會保障</span><span class="sxs-lookup"><span data-stu-id="a243a-3817">Social Security</span></span> 
- <span data-ttu-id="a243a-3818">社會保障#</span><span class="sxs-lookup"><span data-stu-id="a243a-3818">Social Security#</span></span> 
- <span data-ttu-id="a243a-3819">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="a243a-3819">Soc Sec</span></span> 
- <span data-ttu-id="a243a-3820">Ssn</span><span class="sxs-lookup"><span data-stu-id="a243a-3820">SSN</span></span> 
- <span data-ttu-id="a243a-3821">主旨 SSN</span><span class="sxs-lookup"><span data-stu-id="a243a-3821">SSNS</span></span> 
- <span data-ttu-id="a243a-3822">Ssn#</span><span class="sxs-lookup"><span data-stu-id="a243a-3822">SSN#</span></span> 
- <span data-ttu-id="a243a-3823">秒#</span><span class="sxs-lookup"><span data-stu-id="a243a-3823">SS#</span></span> 
- <span data-ttu-id="a243a-3824">Ssid</span><span class="sxs-lookup"><span data-stu-id="a243a-3824">SSID</span></span> 
   
