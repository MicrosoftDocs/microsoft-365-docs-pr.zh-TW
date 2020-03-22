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
ms.openlocfilehash: bd74551b7e8b2d659724a1222e115a479db76ec8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894297"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="d5030-104">敏感資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="d5030-104">What the sensitive information types look for</span></span>

<span data-ttu-id="d5030-105">Office 365 安全性&amp;與合規性中心的資料遺失防護（DLP）包含許多機密資訊類型，可供您在 DLP 原則中使用。</span><span class="sxs-lookup"><span data-stu-id="d5030-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="d5030-106">本主題列出所有敏感資訊類型，並顯示 DLP 原則在偵測到每種類型時所尋找的功能。</span><span class="sxs-lookup"><span data-stu-id="d5030-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="d5030-107">敏感資訊類型是由正則運算式或函數所識別的模式所定義。</span><span class="sxs-lookup"><span data-stu-id="d5030-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="d5030-108">此外，您也可以使用確切證據（如關鍵字及校驗和）來識別敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="d5030-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="d5030-109">評估程式中也會使用信賴等級和近程。</span><span class="sxs-lookup"><span data-stu-id="d5030-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="d5030-110">ABA 路由號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-111">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-111">Format</span></span>

<span data-ttu-id="d5030-112">格式或未格式化的模式中的9位數</span><span class="sxs-lookup"><span data-stu-id="d5030-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-113">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-113">Pattern</span></span>

<span data-ttu-id="d5030-114">格式 化：</span><span class="sxs-lookup"><span data-stu-id="d5030-114">Formatted:</span></span>
- <span data-ttu-id="d5030-115">以0、1、2、3、6、7或8開頭的四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="d5030-116">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-116">A hyphen</span></span>
- <span data-ttu-id="d5030-117">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-117">Four digits</span></span>
- <span data-ttu-id="d5030-118">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-118">A hyphen</span></span>
- <span data-ttu-id="d5030-119">一個數位</span><span class="sxs-lookup"><span data-stu-id="d5030-119">A digit</span></span>

<span data-ttu-id="d5030-120">未格式化：9以0、1、2、3、6、7或8開頭的連續數位</span><span class="sxs-lookup"><span data-stu-id="d5030-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="d5030-121">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-121">Checksum</span></span>

<span data-ttu-id="d5030-122">否</span><span class="sxs-lookup"><span data-stu-id="d5030-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-123">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-123">Definition</span></span>

<span data-ttu-id="d5030-124">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-125">函數 Func_aba_routing 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-126">會找到來自 Keyword_ABA_Routing 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="d5030-127">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="d5030-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="d5030-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="d5030-129">阿壩</span><span class="sxs-lookup"><span data-stu-id="d5030-129">aba</span></span>
- <span data-ttu-id="d5030-130">阿壩#</span><span class="sxs-lookup"><span data-stu-id="d5030-130">aba #</span></span>
- <span data-ttu-id="d5030-131">aba 路由#</span><span class="sxs-lookup"><span data-stu-id="d5030-131">aba routing #</span></span>
- <span data-ttu-id="d5030-132">aba 路由號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-132">aba routing number</span></span>
- <span data-ttu-id="d5030-133">阿壩#</span><span class="sxs-lookup"><span data-stu-id="d5030-133">aba#</span></span>
- <span data-ttu-id="d5030-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="d5030-134">abarouting#</span></span>
- <span data-ttu-id="d5030-135">aba 編號</span><span class="sxs-lookup"><span data-stu-id="d5030-135">aba number</span></span>
- <span data-ttu-id="d5030-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-136">abaroutingnumber</span></span>
- <span data-ttu-id="d5030-137">美洲銀行協會路由#</span><span class="sxs-lookup"><span data-stu-id="d5030-137">american bank association routing #</span></span>
- <span data-ttu-id="d5030-138">美洲銀行關聯性路由編號</span><span class="sxs-lookup"><span data-stu-id="d5030-138">american bank association routing number</span></span>
- <span data-ttu-id="d5030-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="d5030-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="d5030-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="d5030-141">銀行路由編號</span><span class="sxs-lookup"><span data-stu-id="d5030-141">bank routing number</span></span>
- <span data-ttu-id="d5030-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="d5030-142">bankrouting#</span></span>
- <span data-ttu-id="d5030-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-143">bankroutingnumber</span></span>
- <span data-ttu-id="d5030-144">路由轉口號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-144">routing transit number</span></span>
- <span data-ttu-id="d5030-145">RTN</span><span class="sxs-lookup"><span data-stu-id="d5030-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="d5030-146">阿根廷國內身分識別（DNI）號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-147">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-147">Format</span></span>

<span data-ttu-id="d5030-148">以句點隔開的八位數</span><span class="sxs-lookup"><span data-stu-id="d5030-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-149">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-149">Pattern</span></span>

<span data-ttu-id="d5030-150">八位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-150">Eight digits:</span></span>
- <span data-ttu-id="d5030-151">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-151">Two digits</span></span>
- <span data-ttu-id="d5030-152">一個句點</span><span class="sxs-lookup"><span data-stu-id="d5030-152">A period</span></span>
- <span data-ttu-id="d5030-153">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-153">Three digits</span></span>
- <span data-ttu-id="d5030-154">一個句點</span><span class="sxs-lookup"><span data-stu-id="d5030-154">A period</span></span>
- <span data-ttu-id="d5030-155">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-156">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-156">Checksum</span></span>

<span data-ttu-id="d5030-157">否</span><span class="sxs-lookup"><span data-stu-id="d5030-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-158">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-158">Definition</span></span>

<span data-ttu-id="d5030-159">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-160">正則運算式 Regex_argentina_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-161">會找到來自 Keyword_argentina_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-162">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="d5030-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="d5030-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="d5030-164">阿根廷國內身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="d5030-165">身分識別</span><span class="sxs-lookup"><span data-stu-id="d5030-165">Identity</span></span> 
- <span data-ttu-id="d5030-166">身分識別的國內身分識別卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="d5030-167">DNI</span><span class="sxs-lookup"><span data-stu-id="d5030-167">DNI</span></span> 
- <span data-ttu-id="d5030-168">個人的 NIC 註冊人員</span><span class="sxs-lookup"><span data-stu-id="d5030-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="d5030-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="d5030-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="d5030-170">Registro Nacional de 拉斯維加斯角色</span><span class="sxs-lookup"><span data-stu-id="d5030-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="d5030-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="d5030-171">Identidad</span></span> 
- <span data-ttu-id="d5030-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="d5030-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="d5030-173">澳大利亞銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-174">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-174">Format</span></span>

<span data-ttu-id="d5030-175">包含或不含銀行狀態分公司號碼的6-10 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-176">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-176">Pattern</span></span>

<span data-ttu-id="d5030-177">帳戶號碼是6-10 位數。</span><span class="sxs-lookup"><span data-stu-id="d5030-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="d5030-178">澳大利亞銀行狀態分支編號：</span><span class="sxs-lookup"><span data-stu-id="d5030-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="d5030-179">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-179">Three digits</span></span> 
- <span data-ttu-id="d5030-180">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-180">A hyphen</span></span> 
- <span data-ttu-id="d5030-181">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-182">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-182">Checksum</span></span>

<span data-ttu-id="d5030-183">否</span><span class="sxs-lookup"><span data-stu-id="d5030-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-184">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-184">Definition</span></span>

<span data-ttu-id="d5030-185">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-186">正則運算式 Regex_australia_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="d5030-187">會找到來自 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="d5030-188">正則運算式 Regex_australia_bank_account_number_bsb 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="d5030-189">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-190">正則運算式 Regex_australia_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="d5030-191">會找到來自 Keyword_australia_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-192">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="d5030-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="d5030-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="d5030-194">swift 銀行代碼</span><span class="sxs-lookup"><span data-stu-id="d5030-194">swift bank code</span></span>
- <span data-ttu-id="d5030-195">通信銀行</span><span class="sxs-lookup"><span data-stu-id="d5030-195">correspondent bank</span></span>
- <span data-ttu-id="d5030-196">基礎貨幣</span><span class="sxs-lookup"><span data-stu-id="d5030-196">base currency</span></span>
- <span data-ttu-id="d5030-197">美國帳戶</span><span class="sxs-lookup"><span data-stu-id="d5030-197">usa account</span></span>
- <span data-ttu-id="d5030-198">持有者位址</span><span class="sxs-lookup"><span data-stu-id="d5030-198">holder address</span></span>
- <span data-ttu-id="d5030-199">銀行位址</span><span class="sxs-lookup"><span data-stu-id="d5030-199">bank address</span></span>
- <span data-ttu-id="d5030-200">資訊帳戶</span><span class="sxs-lookup"><span data-stu-id="d5030-200">information account</span></span>
- <span data-ttu-id="d5030-201">基金轉移</span><span class="sxs-lookup"><span data-stu-id="d5030-201">fund transfers</span></span>
- <span data-ttu-id="d5030-202">銀行費用</span><span class="sxs-lookup"><span data-stu-id="d5030-202">bank charges</span></span>
- <span data-ttu-id="d5030-203">銀行詳細資料</span><span class="sxs-lookup"><span data-stu-id="d5030-203">bank details</span></span>
- <span data-ttu-id="d5030-204">銀行資訊</span><span class="sxs-lookup"><span data-stu-id="d5030-204">banking information</span></span>
- <span data-ttu-id="d5030-205">完整名稱</span><span class="sxs-lookup"><span data-stu-id="d5030-205">full names</span></span>
- <span data-ttu-id="d5030-206">國際 原子能 機構</span><span class="sxs-lookup"><span data-stu-id="d5030-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="d5030-207">澳大利亞駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-208">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-208">Format</span></span>

<span data-ttu-id="d5030-209">九個字母和數位</span><span class="sxs-lookup"><span data-stu-id="d5030-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-210">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-210">Pattern</span></span>

<span data-ttu-id="d5030-211">九個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="d5030-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="d5030-212">兩位數或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="d5030-213">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-213">Two digits</span></span> 
- <span data-ttu-id="d5030-214">五個數字或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="d5030-215">OR</span><span class="sxs-lookup"><span data-stu-id="d5030-215">OR</span></span>

- <span data-ttu-id="d5030-216">1-2 選用的字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="d5030-217">4-9 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-217">4-9 digits</span></span>

<span data-ttu-id="d5030-218">OR</span><span class="sxs-lookup"><span data-stu-id="d5030-218">OR</span></span>

- <span data-ttu-id="d5030-219">九個數字或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-220">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-220">Checksum</span></span>

<span data-ttu-id="d5030-221">否</span><span class="sxs-lookup"><span data-stu-id="d5030-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-222">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-222">Definition</span></span>

<span data-ttu-id="d5030-223">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-224">正則運算式 Regex_australia_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-225">會找到來自 Keyword_australia_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="d5030-226">找不到 Keyword_australia_drivers_license_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="d5030-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d5030-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="d5030-229">國際動力允許</span><span class="sxs-lookup"><span data-stu-id="d5030-229">international driving permits</span></span>
- <span data-ttu-id="d5030-230">澳大利亞汽車協會</span><span class="sxs-lookup"><span data-stu-id="d5030-230">australian automobile association</span></span>
- <span data-ttu-id="d5030-231">國際駕駛允許</span><span class="sxs-lookup"><span data-stu-id="d5030-231">international driving permit</span></span>
- <span data-ttu-id="d5030-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="d5030-232">DriverLicence</span></span>
- <span data-ttu-id="d5030-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="d5030-233">DriverLicences</span></span>
- <span data-ttu-id="d5030-234">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-234">Driver Lic</span></span>
- <span data-ttu-id="d5030-235">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-235">Driver Licence</span></span>
- <span data-ttu-id="d5030-236">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-236">Driver Licences</span></span>
- <span data-ttu-id="d5030-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="d5030-237">DriversLic</span></span>
- <span data-ttu-id="d5030-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="d5030-238">DriversLicence</span></span>
- <span data-ttu-id="d5030-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="d5030-239">DriversLicences</span></span>
- <span data-ttu-id="d5030-240">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-240">Drivers Lic</span></span>
- <span data-ttu-id="d5030-241">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-241">Drivers Lics</span></span>
- <span data-ttu-id="d5030-242">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-242">Drivers Licence</span></span>
- <span data-ttu-id="d5030-243">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-243">Drivers Licences</span></span>
- <span data-ttu-id="d5030-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-244">Driver'Lic</span></span>
- <span data-ttu-id="d5030-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-245">Driver'Lics</span></span>
- <span data-ttu-id="d5030-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="d5030-246">Driver'Licence</span></span>
- <span data-ttu-id="d5030-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="d5030-247">Driver'Licences</span></span>
- <span data-ttu-id="d5030-248">驅動程式「.Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-248">Driver' Lic</span></span>
- <span data-ttu-id="d5030-249">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-249">Driver' Lics</span></span>
- <span data-ttu-id="d5030-250">驅動程式 ' 許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-250">Driver' Licence</span></span>
- <span data-ttu-id="d5030-251">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d5030-251">Driver' Licences</span></span>
- <span data-ttu-id="d5030-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="d5030-252">Driver'sLic</span></span>
- <span data-ttu-id="d5030-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="d5030-253">Driver'sLics</span></span>
- <span data-ttu-id="d5030-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="d5030-254">Driver'sLicence</span></span>
- <span data-ttu-id="d5030-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="d5030-255">Driver'sLicences</span></span>
- <span data-ttu-id="d5030-256">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-256">Driver's Lic</span></span>
- <span data-ttu-id="d5030-257">驅動程式的 Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-257">Driver's Lics</span></span>
- <span data-ttu-id="d5030-258">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-258">Driver's Licence</span></span>
- <span data-ttu-id="d5030-259">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-259">Driver's Licences</span></span>
- <span data-ttu-id="d5030-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="d5030-260">DriverLic#</span></span>
- <span data-ttu-id="d5030-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="d5030-261">DriverLics#</span></span>
- <span data-ttu-id="d5030-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="d5030-262">DriverLicence#</span></span>
- <span data-ttu-id="d5030-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="d5030-263">DriverLicences#</span></span>
- <span data-ttu-id="d5030-264">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="d5030-264">Driver Lic#</span></span>
- <span data-ttu-id="d5030-265">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-265">Driver Lics#</span></span>
- <span data-ttu-id="d5030-266">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="d5030-266">Driver Licence#</span></span>
- <span data-ttu-id="d5030-267">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-267">Driver Licences#</span></span>
- <span data-ttu-id="d5030-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="d5030-268">DriversLic#</span></span>
- <span data-ttu-id="d5030-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="d5030-269">DriversLics#</span></span>
- <span data-ttu-id="d5030-270">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="d5030-270">DriversLicence#</span></span>
- <span data-ttu-id="d5030-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="d5030-271">DriversLicences#</span></span>
- <span data-ttu-id="d5030-272">驅動程式 .Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-272">Drivers Lic#</span></span>
- <span data-ttu-id="d5030-273">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-273">Drivers Lics#</span></span>
- <span data-ttu-id="d5030-274">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="d5030-274">Drivers Licence#</span></span>
- <span data-ttu-id="d5030-275">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-275">Drivers Licences#</span></span>
- <span data-ttu-id="d5030-276">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-276">Driver'Lic#</span></span>
- <span data-ttu-id="d5030-277">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-277">Driver'Lics#</span></span>
- <span data-ttu-id="d5030-278">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="d5030-278">Driver'Licence#</span></span>
- <span data-ttu-id="d5030-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="d5030-279">Driver'Licences#</span></span>
- <span data-ttu-id="d5030-280">驅動程式「.Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-280">Driver' Lic#</span></span>
- <span data-ttu-id="d5030-281">驅動程式 ' Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-281">Driver' Lics#</span></span>
- <span data-ttu-id="d5030-282">驅動程式 ' 許可證#</span><span class="sxs-lookup"><span data-stu-id="d5030-282">Driver' Licence#</span></span>
- <span data-ttu-id="d5030-283">驅動程式 ' 授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-283">Driver' Licences#</span></span>
- <span data-ttu-id="d5030-284">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="d5030-284">Driver'sLic#</span></span>
- <span data-ttu-id="d5030-285">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="d5030-285">Driver'sLics#</span></span>
- <span data-ttu-id="d5030-286">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="d5030-286">Driver'sLicence#</span></span>
- <span data-ttu-id="d5030-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="d5030-287">Driver'sLicences#</span></span>
- <span data-ttu-id="d5030-288">驅動程式的 .Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-288">Driver's Lic#</span></span>
- <span data-ttu-id="d5030-289">驅動程式的 Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-289">Driver's Lics#</span></span>
- <span data-ttu-id="d5030-290">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-290">Driver's Licence#</span></span>
- <span data-ttu-id="d5030-291">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="d5030-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="d5030-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="d5030-293">Aaa</span><span class="sxs-lookup"><span data-stu-id="d5030-293">aaa</span></span>
- <span data-ttu-id="d5030-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="d5030-294">DriverLicense</span></span>
- <span data-ttu-id="d5030-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="d5030-295">DriverLicenses</span></span>
- <span data-ttu-id="d5030-296">駕照</span><span class="sxs-lookup"><span data-stu-id="d5030-296">Driver License</span></span>
- <span data-ttu-id="d5030-297">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-297">Driver Licenses</span></span>
- <span data-ttu-id="d5030-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="d5030-298">DriversLicense</span></span>
- <span data-ttu-id="d5030-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="d5030-299">DriversLicenses</span></span>
- <span data-ttu-id="d5030-300">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-300">Drivers License</span></span>
- <span data-ttu-id="d5030-301">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-301">Drivers Licenses</span></span>
- <span data-ttu-id="d5030-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="d5030-302">Driver'License</span></span>
- <span data-ttu-id="d5030-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="d5030-303">Driver'Licenses</span></span>
- <span data-ttu-id="d5030-304">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-304">Driver' License</span></span>
- <span data-ttu-id="d5030-305">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="d5030-305">Driver' Licenses</span></span>
- <span data-ttu-id="d5030-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="d5030-306">Driver'sLicense</span></span>
- <span data-ttu-id="d5030-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="d5030-307">Driver'sLicenses</span></span>
- <span data-ttu-id="d5030-308">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-308">Driver's License</span></span>
- <span data-ttu-id="d5030-309">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-309">Driver's Licenses</span></span>
- <span data-ttu-id="d5030-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="d5030-310">DriverLicense#</span></span>
- <span data-ttu-id="d5030-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-311">DriverLicenses#</span></span>
- <span data-ttu-id="d5030-312">駕照#</span><span class="sxs-lookup"><span data-stu-id="d5030-312">Driver License#</span></span>
- <span data-ttu-id="d5030-313">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-313">Driver Licenses#</span></span>
- <span data-ttu-id="d5030-314">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="d5030-314">DriversLicense#</span></span>
- <span data-ttu-id="d5030-315">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-315">DriversLicenses#</span></span>
- <span data-ttu-id="d5030-316">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-316">Drivers License#</span></span>
- <span data-ttu-id="d5030-317">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-317">Drivers Licenses#</span></span>
- <span data-ttu-id="d5030-318">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="d5030-318">Driver'License#</span></span>
- <span data-ttu-id="d5030-319">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-319">Driver'Licenses#</span></span>
- <span data-ttu-id="d5030-320">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-320">Driver' License#</span></span>
- <span data-ttu-id="d5030-321">驅動程式的授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-321">Driver' Licenses#</span></span>
- <span data-ttu-id="d5030-322">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="d5030-322">Driver'sLicense#</span></span>
- <span data-ttu-id="d5030-323">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="d5030-324">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-324">Driver's License#</span></span>
- <span data-ttu-id="d5030-325">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="d5030-326">澳大利亞醫療帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-327">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-327">Format</span></span>

<span data-ttu-id="d5030-328">10-11 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-329">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-329">Pattern</span></span>

<span data-ttu-id="d5030-330">10-11 位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-330">10-11 digits:</span></span>
- <span data-ttu-id="d5030-331">第一個數位是在2-6 範圍內</span><span class="sxs-lookup"><span data-stu-id="d5030-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="d5030-332">第九位數是檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="d5030-333">第十個數字是問題的位數</span><span class="sxs-lookup"><span data-stu-id="d5030-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="d5030-334">第十位數（選用）是個別數位</span><span class="sxs-lookup"><span data-stu-id="d5030-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-335">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-335">Checksum</span></span>

<span data-ttu-id="d5030-336">是</span><span class="sxs-lookup"><span data-stu-id="d5030-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-337">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-337">Definition</span></span>

<span data-ttu-id="d5030-338">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：</span><span class="sxs-lookup"><span data-stu-id="d5030-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-339">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-340">會找到來自 Keyword_Australia_Medical_Account_Number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="d5030-341">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-341">The checksum passes.</span></span>

<span data-ttu-id="d5030-342">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-343">函數 Func_australian_medical_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-344">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-345">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="d5030-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="d5030-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="d5030-347">銀行帳戶詳細資料</span><span class="sxs-lookup"><span data-stu-id="d5030-347">bank account details</span></span>
- <span data-ttu-id="d5030-348">medicare 付款</span><span class="sxs-lookup"><span data-stu-id="d5030-348">medicare payments</span></span>
- <span data-ttu-id="d5030-349">抵押帳戶</span><span class="sxs-lookup"><span data-stu-id="d5030-349">mortgage account</span></span>
- <span data-ttu-id="d5030-350">銀行付款</span><span class="sxs-lookup"><span data-stu-id="d5030-350">bank payments</span></span>
- <span data-ttu-id="d5030-351">資訊分支</span><span class="sxs-lookup"><span data-stu-id="d5030-351">information branch</span></span>
- <span data-ttu-id="d5030-352">信用卡貸款</span><span class="sxs-lookup"><span data-stu-id="d5030-352">credit card loan</span></span>
- <span data-ttu-id="d5030-353">人體服務部門</span><span class="sxs-lookup"><span data-stu-id="d5030-353">department of human services</span></span>
- <span data-ttu-id="d5030-354">本機服務</span><span class="sxs-lookup"><span data-stu-id="d5030-354">local service</span></span>
- <span data-ttu-id="d5030-355">醫療</span><span class="sxs-lookup"><span data-stu-id="d5030-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="d5030-356">澳大利亞護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-357">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-357">Format</span></span>

<span data-ttu-id="d5030-358">字母后接7位數</span><span class="sxs-lookup"><span data-stu-id="d5030-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-359">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-359">Pattern</span></span>

<span data-ttu-id="d5030-360">字母（不區分大小寫）後接7位數</span><span class="sxs-lookup"><span data-stu-id="d5030-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-361">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-361">Checksum</span></span>

<span data-ttu-id="d5030-362">否</span><span class="sxs-lookup"><span data-stu-id="d5030-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-363">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-363">Definition</span></span>

<span data-ttu-id="d5030-364">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-365">正則運算式 Regex_australia_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-366">會找到 Keyword_passport 或 Keyword_australia_passport_number 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-367">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="d5030-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d5030-368">Keyword_passport</span></span>

- <span data-ttu-id="d5030-369">護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-369">Passport Number</span></span>
- <span data-ttu-id="d5030-370">護照否</span><span class="sxs-lookup"><span data-stu-id="d5030-370">Passport No</span></span>
- <span data-ttu-id="d5030-371">護照#</span><span class="sxs-lookup"><span data-stu-id="d5030-371">Passport #</span></span>
- <span data-ttu-id="d5030-372">護照#</span><span class="sxs-lookup"><span data-stu-id="d5030-372">Passport#</span></span>
- <span data-ttu-id="d5030-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="d5030-373">PassportID</span></span>
- <span data-ttu-id="d5030-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="d5030-374">Passportno</span></span>
- <span data-ttu-id="d5030-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-375">passportnumber</span></span>
- <span data-ttu-id="d5030-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="d5030-376">パスポート</span></span>
- <span data-ttu-id="d5030-377">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="d5030-377">パスポート番号</span></span>
- <span data-ttu-id="d5030-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d5030-378">パスポートのNum</span></span>
- <span data-ttu-id="d5030-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="d5030-379">パスポート ＃</span></span> 
- <span data-ttu-id="d5030-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d5030-380">Numéro de passeport</span></span>
- <span data-ttu-id="d5030-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d5030-381">Passeport n °</span></span>
- <span data-ttu-id="d5030-382">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="d5030-382">Passeport Non</span></span>
- <span data-ttu-id="d5030-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d5030-383">Passeport #</span></span>
- <span data-ttu-id="d5030-384">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d5030-384">Passeport#</span></span>
- <span data-ttu-id="d5030-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d5030-385">PasseportNon</span></span>
- <span data-ttu-id="d5030-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d5030-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="d5030-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="d5030-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="d5030-388">護照</span><span class="sxs-lookup"><span data-stu-id="d5030-388">passport</span></span>
- <span data-ttu-id="d5030-389">護照詳細資料</span><span class="sxs-lookup"><span data-stu-id="d5030-389">passport details</span></span>
- <span data-ttu-id="d5030-390">immigration 與公民</span><span class="sxs-lookup"><span data-stu-id="d5030-390">immigration and citizenship</span></span>
- <span data-ttu-id="d5030-391">澳大利亞英聯邦</span><span class="sxs-lookup"><span data-stu-id="d5030-391">commonwealth of australia</span></span>
- <span data-ttu-id="d5030-392">immigration 部門</span><span class="sxs-lookup"><span data-stu-id="d5030-392">department of immigration</span></span>
- <span data-ttu-id="d5030-393">住家住址</span><span class="sxs-lookup"><span data-stu-id="d5030-393">residential address</span></span>
- <span data-ttu-id="d5030-394">immigration 和公民的部門</span><span class="sxs-lookup"><span data-stu-id="d5030-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="d5030-395">簽證</span><span class="sxs-lookup"><span data-stu-id="d5030-395">visa</span></span>
- <span data-ttu-id="d5030-396">本國身分識別卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-396">national identity card</span></span>
- <span data-ttu-id="d5030-397">護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-397">passport number</span></span>
- <span data-ttu-id="d5030-398">旅遊檔</span><span class="sxs-lookup"><span data-stu-id="d5030-398">travel document</span></span>
- <span data-ttu-id="d5030-399">頒發機構單位</span><span class="sxs-lookup"><span data-stu-id="d5030-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="d5030-400">澳大利亞稅收檔編號</span><span class="sxs-lookup"><span data-stu-id="d5030-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-401">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-401">Format</span></span>

<span data-ttu-id="d5030-402">8-9 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-403">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-403">Pattern</span></span>

<span data-ttu-id="d5030-404">通常會以空格呈現的8-9 位數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d5030-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="d5030-405">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-405">Three digits</span></span> 
- <span data-ttu-id="d5030-406">選擇性的空格</span><span class="sxs-lookup"><span data-stu-id="d5030-406">An optional space</span></span> 
- <span data-ttu-id="d5030-407">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-407">Three digits</span></span> 
- <span data-ttu-id="d5030-408">選擇性的空格</span><span class="sxs-lookup"><span data-stu-id="d5030-408">An optional space</span></span> 
- <span data-ttu-id="d5030-409">最後一個數位是檢查碼的2-3 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-410">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-410">Checksum</span></span>

<span data-ttu-id="d5030-411">是</span><span class="sxs-lookup"><span data-stu-id="d5030-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-412">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-412">Definition</span></span>

<span data-ttu-id="d5030-413">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-414">函數 Func_australian_tax_file_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-415">找不到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="d5030-416">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="d5030-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="d5030-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="d5030-419">澳大利亞商務電話號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-419">australian business number</span></span>
- <span data-ttu-id="d5030-420">邊際稅率</span><span class="sxs-lookup"><span data-stu-id="d5030-420">marginal tax rate</span></span>
- <span data-ttu-id="d5030-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="d5030-421">medicare levy</span></span>
- <span data-ttu-id="d5030-422">產品群組編號</span><span class="sxs-lookup"><span data-stu-id="d5030-422">portfolio number</span></span>
- <span data-ttu-id="d5030-423">服務 veterans</span><span class="sxs-lookup"><span data-stu-id="d5030-423">service veterans</span></span>
- <span data-ttu-id="d5030-424">預繳稅金</span><span class="sxs-lookup"><span data-stu-id="d5030-424">withholding tax</span></span>
- <span data-ttu-id="d5030-425">個人稅收返還</span><span class="sxs-lookup"><span data-stu-id="d5030-425">individual tax return</span></span>
- <span data-ttu-id="d5030-426">稅收檔案編號</span><span class="sxs-lookup"><span data-stu-id="d5030-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="d5030-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="d5030-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="d5030-428">00000000</span><span class="sxs-lookup"><span data-stu-id="d5030-428">00000000</span></span>
- <span data-ttu-id="d5030-429">11111111</span><span class="sxs-lookup"><span data-stu-id="d5030-429">11111111</span></span>
- <span data-ttu-id="d5030-430">22222222</span><span class="sxs-lookup"><span data-stu-id="d5030-430">22222222</span></span>
- <span data-ttu-id="d5030-431">33333333</span><span class="sxs-lookup"><span data-stu-id="d5030-431">33333333</span></span>
- <span data-ttu-id="d5030-432">44444444</span><span class="sxs-lookup"><span data-stu-id="d5030-432">44444444</span></span>
- <span data-ttu-id="d5030-433">55555555</span><span class="sxs-lookup"><span data-stu-id="d5030-433">55555555</span></span>
- <span data-ttu-id="d5030-434">66666666</span><span class="sxs-lookup"><span data-stu-id="d5030-434">66666666</span></span>
- <span data-ttu-id="d5030-435">77777777</span><span class="sxs-lookup"><span data-stu-id="d5030-435">77777777</span></span>
- <span data-ttu-id="d5030-436">88888888</span><span class="sxs-lookup"><span data-stu-id="d5030-436">88888888</span></span>
- <span data-ttu-id="d5030-437">99999999</span><span class="sxs-lookup"><span data-stu-id="d5030-437">99999999</span></span>
- <span data-ttu-id="d5030-438">000000000</span><span class="sxs-lookup"><span data-stu-id="d5030-438">000000000</span></span>
- <span data-ttu-id="d5030-439">111111111</span><span class="sxs-lookup"><span data-stu-id="d5030-439">111111111</span></span>
- <span data-ttu-id="d5030-440">222222222</span><span class="sxs-lookup"><span data-stu-id="d5030-440">222222222</span></span>
- <span data-ttu-id="d5030-441">333333333</span><span class="sxs-lookup"><span data-stu-id="d5030-441">333333333</span></span>
- <span data-ttu-id="d5030-442">444444444</span><span class="sxs-lookup"><span data-stu-id="d5030-442">444444444</span></span>
- <span data-ttu-id="d5030-443">555555555</span><span class="sxs-lookup"><span data-stu-id="d5030-443">555555555</span></span>
- <span data-ttu-id="d5030-444">666666666</span><span class="sxs-lookup"><span data-stu-id="d5030-444">666666666</span></span>
- <span data-ttu-id="d5030-445">777777777</span><span class="sxs-lookup"><span data-stu-id="d5030-445">777777777</span></span>
- <span data-ttu-id="d5030-446">888888888</span><span class="sxs-lookup"><span data-stu-id="d5030-446">888888888</span></span>
- <span data-ttu-id="d5030-447">999999999</span><span class="sxs-lookup"><span data-stu-id="d5030-447">999999999</span></span>
- <span data-ttu-id="d5030-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="d5030-448">0000000000</span></span>
- <span data-ttu-id="d5030-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="d5030-449">1111111111</span></span>
- <span data-ttu-id="d5030-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="d5030-450">2222222222</span></span>
- <span data-ttu-id="d5030-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="d5030-451">3333333333</span></span>
- <span data-ttu-id="d5030-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="d5030-452">4444444444</span></span>
- <span data-ttu-id="d5030-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="d5030-453">5555555555</span></span>
- <span data-ttu-id="d5030-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="d5030-454">6666666666</span></span>
- <span data-ttu-id="d5030-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="d5030-455">7777777777</span></span>
- <span data-ttu-id="d5030-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="d5030-456">8888888888</span></span>
- <span data-ttu-id="d5030-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="d5030-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="d5030-458">Azure DocumentDB 驗證金鑰</span><span class="sxs-lookup"><span data-stu-id="d5030-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="d5030-459">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-459">Format</span></span>

<span data-ttu-id="d5030-460">字串 "DocumentDb"，後面加上下列模式中所述的字元及字串。</span><span class="sxs-lookup"><span data-stu-id="d5030-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-461">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-461">Pattern</span></span>

- <span data-ttu-id="d5030-462">字串 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="d5030-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="d5030-463">介於3-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="d5030-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d5030-464">大於符號（>）、等號（=）、引號（"）或撇號（'）</span><span class="sxs-lookup"><span data-stu-id="d5030-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="d5030-465">任何86的小寫字母或大寫字母、數位、正斜線（/）或加號（+）組合</span><span class="sxs-lookup"><span data-stu-id="d5030-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d5030-466">兩個等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-467">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-467">Checksum</span></span>

<span data-ttu-id="d5030-468">否</span><span class="sxs-lookup"><span data-stu-id="d5030-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-469">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-469">Definition</span></span>

<span data-ttu-id="d5030-470">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-471">正則運算式 CEP_Regex_AzureDocumentDBAuthKey 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-472">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-473">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d5030-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d5030-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d5030-475">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="d5030-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d5030-476">尚未</span><span class="sxs-lookup"><span data-stu-id="d5030-476">contoso</span></span>
- <span data-ttu-id="d5030-477">送交</span><span class="sxs-lookup"><span data-stu-id="d5030-477">fabrikam</span></span>
- <span data-ttu-id="d5030-478">資料庫</span><span class="sxs-lookup"><span data-stu-id="d5030-478">northwind</span></span>
- <span data-ttu-id="d5030-479">沙 箱</span><span class="sxs-lookup"><span data-stu-id="d5030-479">sandbox</span></span>
- <span data-ttu-id="d5030-480">onebox</span><span class="sxs-lookup"><span data-stu-id="d5030-480">onebox</span></span>
- <span data-ttu-id="d5030-481">本地 主機</span><span class="sxs-lookup"><span data-stu-id="d5030-481">localhost</span></span>
- <span data-ttu-id="d5030-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d5030-482">127.0.0.1</span></span>
- <span data-ttu-id="d5030-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="d5030-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-484">Com</span><span class="sxs-lookup"><span data-stu-id="d5030-484">com</span></span>
- <span data-ttu-id="d5030-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="d5030-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-486">網</span><span class="sxs-lookup"><span data-stu-id="d5030-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="d5030-487">Azure IAAS 資料庫連接字串和 Azure SQL 連接字串</span><span class="sxs-lookup"><span data-stu-id="d5030-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="d5030-488">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-488">Format</span></span>

<span data-ttu-id="d5030-489">字串 "Server"、"server" 或 "data source"，後面加上模式中所述的字元及字串（包括字串 "cloudapp"）。</span><span class="sxs-lookup"><span data-stu-id="d5030-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-490">com "或" cloudapp。</span><span class="sxs-lookup"><span data-stu-id="d5030-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-491">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="d5030-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-492">net "，及字串" Password "或" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="d5030-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-493">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-493">Pattern</span></span>

- <span data-ttu-id="d5030-494">字串「伺服器」、「伺服器」或「資料來源」</span><span class="sxs-lookup"><span data-stu-id="d5030-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="d5030-495">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-496">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-496">An equal sign (=)</span></span>
- <span data-ttu-id="d5030-497">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-498">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="d5030-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d5030-499">字串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="d5030-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-500">com "，" cloudapp。</span><span class="sxs-lookup"><span data-stu-id="d5030-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-501">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="d5030-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-502">真實</span><span class="sxs-lookup"><span data-stu-id="d5030-502">net"</span></span>
- <span data-ttu-id="d5030-503">介於1-300 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="d5030-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d5030-504">字串 "Password"、"password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="d5030-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="d5030-505">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-506">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-506">An equal sign (=)</span></span>
- <span data-ttu-id="d5030-507">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-508">一個或多個字元，不是分號（;)、引號（"）或單引號（'）</span><span class="sxs-lookup"><span data-stu-id="d5030-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="d5030-509">分號（;)、引號（"）或撇號（'）</span><span class="sxs-lookup"><span data-stu-id="d5030-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-510">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-510">Checksum</span></span>

<span data-ttu-id="d5030-511">否</span><span class="sxs-lookup"><span data-stu-id="d5030-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-512">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-512">Definition</span></span>

<span data-ttu-id="d5030-513">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-514">正則運算式 CEP_Regex_AzureConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-515">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-516">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d5030-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d5030-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d5030-518">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="d5030-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d5030-519">尚未</span><span class="sxs-lookup"><span data-stu-id="d5030-519">contoso</span></span>
- <span data-ttu-id="d5030-520">送交</span><span class="sxs-lookup"><span data-stu-id="d5030-520">fabrikam</span></span>
- <span data-ttu-id="d5030-521">資料庫</span><span class="sxs-lookup"><span data-stu-id="d5030-521">northwind</span></span>
- <span data-ttu-id="d5030-522">沙 箱</span><span class="sxs-lookup"><span data-stu-id="d5030-522">sandbox</span></span>
- <span data-ttu-id="d5030-523">onebox</span><span class="sxs-lookup"><span data-stu-id="d5030-523">onebox</span></span>
- <span data-ttu-id="d5030-524">本地 主機</span><span class="sxs-lookup"><span data-stu-id="d5030-524">localhost</span></span>
- <span data-ttu-id="d5030-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d5030-525">127.0.0.1</span></span>
- <span data-ttu-id="d5030-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="d5030-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-527">Com</span><span class="sxs-lookup"><span data-stu-id="d5030-527">com</span></span>
- <span data-ttu-id="d5030-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="d5030-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-529">網</span><span class="sxs-lookup"><span data-stu-id="d5030-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="d5030-530">Azure IoT 連接字串</span><span class="sxs-lookup"><span data-stu-id="d5030-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="d5030-531">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-531">Format</span></span>

<span data-ttu-id="d5030-532">字串 "HostName"，後面加上下列模式中所述的字元及字串，包括字串 "azure 裝置。</span><span class="sxs-lookup"><span data-stu-id="d5030-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-533">net "和" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="d5030-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-534">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-534">Pattern</span></span>

- <span data-ttu-id="d5030-535">字串 "HostName"</span><span class="sxs-lookup"><span data-stu-id="d5030-535">The string "HostName"</span></span>
- <span data-ttu-id="d5030-536">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-537">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-537">An equal sign (=)</span></span>
- <span data-ttu-id="d5030-538">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-539">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="d5030-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d5030-540">"Azure 裝置" 字串。</span><span class="sxs-lookup"><span data-stu-id="d5030-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-541">真實</span><span class="sxs-lookup"><span data-stu-id="d5030-541">net"</span></span>
- <span data-ttu-id="d5030-542">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="d5030-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d5030-543">字串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="d5030-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="d5030-544">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-545">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-545">An equal sign (=)</span></span>
- <span data-ttu-id="d5030-546">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-547">任何43的小寫字母或大寫字母、數位、正斜線（/）或加號（+）組合</span><span class="sxs-lookup"><span data-stu-id="d5030-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d5030-548">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-549">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-549">Checksum</span></span>

<span data-ttu-id="d5030-550">否</span><span class="sxs-lookup"><span data-stu-id="d5030-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-551">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-551">Definition</span></span>

<span data-ttu-id="d5030-552">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-553">正則運算式 CEP_Regex_AzureIoTConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-554">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-555">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d5030-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d5030-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d5030-557">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="d5030-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d5030-558">尚未</span><span class="sxs-lookup"><span data-stu-id="d5030-558">contoso</span></span>
- <span data-ttu-id="d5030-559">送交</span><span class="sxs-lookup"><span data-stu-id="d5030-559">fabrikam</span></span>
- <span data-ttu-id="d5030-560">資料庫</span><span class="sxs-lookup"><span data-stu-id="d5030-560">northwind</span></span>
- <span data-ttu-id="d5030-561">沙 箱</span><span class="sxs-lookup"><span data-stu-id="d5030-561">sandbox</span></span>
- <span data-ttu-id="d5030-562">onebox</span><span class="sxs-lookup"><span data-stu-id="d5030-562">onebox</span></span>
- <span data-ttu-id="d5030-563">本地 主機</span><span class="sxs-lookup"><span data-stu-id="d5030-563">localhost</span></span>
- <span data-ttu-id="d5030-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d5030-564">127.0.0.1</span></span>
- <span data-ttu-id="d5030-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="d5030-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-566">Com</span><span class="sxs-lookup"><span data-stu-id="d5030-566">com</span></span>
- <span data-ttu-id="d5030-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="d5030-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-568">網</span><span class="sxs-lookup"><span data-stu-id="d5030-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="d5030-569">Azure 發佈設定密碼</span><span class="sxs-lookup"><span data-stu-id="d5030-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="d5030-570">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-570">Format</span></span>

<span data-ttu-id="d5030-571">字串 "userpwd ="，後面加上字母元字串。</span><span class="sxs-lookup"><span data-stu-id="d5030-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-572">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-572">Pattern</span></span>

- <span data-ttu-id="d5030-573">字串 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="d5030-573">The string "userpwd="</span></span>
- <span data-ttu-id="d5030-574">任何60小寫字母或數位的組合</span><span class="sxs-lookup"><span data-stu-id="d5030-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="d5030-575">引號（"）</span><span class="sxs-lookup"><span data-stu-id="d5030-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-576">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-576">Checksum</span></span>

<span data-ttu-id="d5030-577">否</span><span class="sxs-lookup"><span data-stu-id="d5030-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-578">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-578">Definition</span></span>

<span data-ttu-id="d5030-579">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-580">正則運算式 CEP_Regex_AzurePublishSettingPasswords 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-581">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="d5030-582">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d5030-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d5030-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d5030-584">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="d5030-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d5030-585">尚未</span><span class="sxs-lookup"><span data-stu-id="d5030-585">contoso</span></span>
- <span data-ttu-id="d5030-586">送交</span><span class="sxs-lookup"><span data-stu-id="d5030-586">fabrikam</span></span>
- <span data-ttu-id="d5030-587">資料庫</span><span class="sxs-lookup"><span data-stu-id="d5030-587">northwind</span></span>
- <span data-ttu-id="d5030-588">沙 箱</span><span class="sxs-lookup"><span data-stu-id="d5030-588">sandbox</span></span>
- <span data-ttu-id="d5030-589">onebox</span><span class="sxs-lookup"><span data-stu-id="d5030-589">onebox</span></span>
- <span data-ttu-id="d5030-590">本地 主機</span><span class="sxs-lookup"><span data-stu-id="d5030-590">localhost</span></span>
- <span data-ttu-id="d5030-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d5030-591">127.0.0.1</span></span>
- <span data-ttu-id="d5030-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="d5030-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-593">Com</span><span class="sxs-lookup"><span data-stu-id="d5030-593">com</span></span>
- <span data-ttu-id="d5030-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="d5030-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-595">網</span><span class="sxs-lookup"><span data-stu-id="d5030-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="d5030-596">Azure Redis Cache Connection String</span><span class="sxs-lookup"><span data-stu-id="d5030-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="d5030-597">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-597">Format</span></span>

<span data-ttu-id="d5030-598">字串 "redis。</span><span class="sxs-lookup"><span data-stu-id="d5030-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-599">net "後接下列模式中所述的字元和字串，包含字串" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="d5030-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-600">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-600">Pattern</span></span>

- <span data-ttu-id="d5030-601">字串 "redis。</span><span class="sxs-lookup"><span data-stu-id="d5030-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-602">真實</span><span class="sxs-lookup"><span data-stu-id="d5030-602">net"</span></span>
- <span data-ttu-id="d5030-603">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="d5030-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d5030-604">字串 "password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="d5030-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="d5030-605">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-606">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-606">An equal sign (=)</span></span>
- <span data-ttu-id="d5030-607">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-608">43個字元的任何組合，其為小寫或大寫字母、數位、正斜線（/）或加號（+）</span><span class="sxs-lookup"><span data-stu-id="d5030-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d5030-609">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-610">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-610">Checksum</span></span>

<span data-ttu-id="d5030-611">否</span><span class="sxs-lookup"><span data-stu-id="d5030-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-612">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-612">Definition</span></span>

<span data-ttu-id="d5030-613">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-614">正則運算式 CEP_Regex_AzureRedisCacheConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="d5030-615">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-616">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d5030-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d5030-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d5030-618">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="d5030-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d5030-619">尚未</span><span class="sxs-lookup"><span data-stu-id="d5030-619">contoso</span></span>
- <span data-ttu-id="d5030-620">送交</span><span class="sxs-lookup"><span data-stu-id="d5030-620">fabrikam</span></span>
- <span data-ttu-id="d5030-621">資料庫</span><span class="sxs-lookup"><span data-stu-id="d5030-621">northwind</span></span>
- <span data-ttu-id="d5030-622">沙 箱</span><span class="sxs-lookup"><span data-stu-id="d5030-622">sandbox</span></span>
- <span data-ttu-id="d5030-623">onebox</span><span class="sxs-lookup"><span data-stu-id="d5030-623">onebox</span></span>
- <span data-ttu-id="d5030-624">本地 主機</span><span class="sxs-lookup"><span data-stu-id="d5030-624">localhost</span></span>
- <span data-ttu-id="d5030-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d5030-625">127.0.0.1</span></span>
- <span data-ttu-id="d5030-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="d5030-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-627">Com</span><span class="sxs-lookup"><span data-stu-id="d5030-627">com</span></span>
- <span data-ttu-id="d5030-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="d5030-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-629">網</span><span class="sxs-lookup"><span data-stu-id="d5030-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="d5030-630">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="d5030-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="d5030-631">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-631">Format</span></span>

<span data-ttu-id="d5030-632">字串 "sig"，後面加上下列模式中所述的字元及字串。</span><span class="sxs-lookup"><span data-stu-id="d5030-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-633">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-633">Pattern</span></span>

- <span data-ttu-id="d5030-634">字串 "sig"</span><span class="sxs-lookup"><span data-stu-id="d5030-634">The string "sig"</span></span>
- <span data-ttu-id="d5030-635">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-636">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-636">An equal sign (=)</span></span>
- <span data-ttu-id="d5030-637">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-638">介於43-53 個字元、小寫字母、數位或百分比符號（%）之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="d5030-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="d5030-639">字串 "% 三維"</span><span class="sxs-lookup"><span data-stu-id="d5030-639">The string "%3d"</span></span>
- <span data-ttu-id="d5030-640">非小寫或大寫字母、數位或百分號（%）以外的任何字元</span><span class="sxs-lookup"><span data-stu-id="d5030-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-641">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-641">Checksum</span></span>

<span data-ttu-id="d5030-642">否</span><span class="sxs-lookup"><span data-stu-id="d5030-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-643">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-643">Definition</span></span>

<span data-ttu-id="d5030-644">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-645">正則運算式 CEP_Regex_AzureSAS 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="d5030-646">Azure 服務匯流排連接字串</span><span class="sxs-lookup"><span data-stu-id="d5030-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="d5030-647">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-647">Format</span></span>

<span data-ttu-id="d5030-648">字串 "EndPoint" 後接下列模式中所述的字元及字串，包含字串 "</span><span class="sxs-lookup"><span data-stu-id="d5030-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-649">net "和" SharedAccesKey "。</span><span class="sxs-lookup"><span data-stu-id="d5030-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-650">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-650">Pattern</span></span>

- <span data-ttu-id="d5030-651">字串 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="d5030-651">The string "EndPoint"</span></span>
- <span data-ttu-id="d5030-652">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-653">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-653">An equal sign (=)</span></span>
- <span data-ttu-id="d5030-654">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-655">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="d5030-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d5030-656">字串 "</span><span class="sxs-lookup"><span data-stu-id="d5030-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-657">真實</span><span class="sxs-lookup"><span data-stu-id="d5030-657">net"</span></span>
- <span data-ttu-id="d5030-658">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="d5030-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d5030-659">字串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="d5030-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="d5030-660">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-661">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-661">An equal sign (=)</span></span>
- <span data-ttu-id="d5030-662">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-663">43個字元的任何組合，其為小寫或大寫字母、數位、正斜線（/）或加號（+）</span><span class="sxs-lookup"><span data-stu-id="d5030-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d5030-664">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-665">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-665">Checksum</span></span>

<span data-ttu-id="d5030-666">否</span><span class="sxs-lookup"><span data-stu-id="d5030-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-667">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-667">Definition</span></span>

<span data-ttu-id="d5030-668">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-669">正則運算式 CEP_Regex_AzureServiceBusConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="d5030-670">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-671">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d5030-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d5030-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d5030-673">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="d5030-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d5030-674">尚未</span><span class="sxs-lookup"><span data-stu-id="d5030-674">contoso</span></span>
- <span data-ttu-id="d5030-675">送交</span><span class="sxs-lookup"><span data-stu-id="d5030-675">fabrikam</span></span>
- <span data-ttu-id="d5030-676">資料庫</span><span class="sxs-lookup"><span data-stu-id="d5030-676">northwind</span></span>
- <span data-ttu-id="d5030-677">沙 箱</span><span class="sxs-lookup"><span data-stu-id="d5030-677">sandbox</span></span>
- <span data-ttu-id="d5030-678">onebox</span><span class="sxs-lookup"><span data-stu-id="d5030-678">onebox</span></span>
- <span data-ttu-id="d5030-679">本地 主機</span><span class="sxs-lookup"><span data-stu-id="d5030-679">localhost</span></span>
- <span data-ttu-id="d5030-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d5030-680">127.0.0.1</span></span>
- <span data-ttu-id="d5030-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="d5030-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-682">Com</span><span class="sxs-lookup"><span data-stu-id="d5030-682">com</span></span>
- <span data-ttu-id="d5030-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="d5030-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-684">網</span><span class="sxs-lookup"><span data-stu-id="d5030-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="d5030-685">Azure 儲存體帳戶金鑰</span><span class="sxs-lookup"><span data-stu-id="d5030-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="d5030-686">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-686">Format</span></span>

<span data-ttu-id="d5030-687">字串 "DefaultEndpointsProtocol"，後面加上下列模式中所述的字元及字串（包括字串 "AccountKey"）。</span><span class="sxs-lookup"><span data-stu-id="d5030-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-688">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-688">Pattern</span></span>

- <span data-ttu-id="d5030-689">字串 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="d5030-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="d5030-690">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-691">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-691">An equal sign (=)</span></span>
- <span data-ttu-id="d5030-692">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-693">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="d5030-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d5030-694">字串 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="d5030-694">The string "AccountKey"</span></span>
- <span data-ttu-id="d5030-695">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-696">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-696">An equal sign (=)</span></span>
- <span data-ttu-id="d5030-697">0-2 空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="d5030-698">86個字元的任何組合，其為小寫或大寫字母、數位、正斜線（/）或加號（+）</span><span class="sxs-lookup"><span data-stu-id="d5030-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d5030-699">兩個等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-700">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-700">Checksum</span></span>

<span data-ttu-id="d5030-701">否</span><span class="sxs-lookup"><span data-stu-id="d5030-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-702">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-702">Definition</span></span>

<span data-ttu-id="d5030-703">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-704">正則運算式 CEP_Regex_AzureStorageAccountKey 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-705">正則運算式**CEP_AzureEmulatorStorageAccountFilter 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-706">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-707">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="d5030-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="d5030-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="d5030-709">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="d5030-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d5030-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="d5030-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d5030-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d5030-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d5030-712">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="d5030-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d5030-713">尚未</span><span class="sxs-lookup"><span data-stu-id="d5030-713">contoso</span></span>
- <span data-ttu-id="d5030-714">送交</span><span class="sxs-lookup"><span data-stu-id="d5030-714">fabrikam</span></span>
- <span data-ttu-id="d5030-715">資料庫</span><span class="sxs-lookup"><span data-stu-id="d5030-715">northwind</span></span>
- <span data-ttu-id="d5030-716">沙 箱</span><span class="sxs-lookup"><span data-stu-id="d5030-716">sandbox</span></span>
- <span data-ttu-id="d5030-717">onebox</span><span class="sxs-lookup"><span data-stu-id="d5030-717">onebox</span></span>
- <span data-ttu-id="d5030-718">本地 主機</span><span class="sxs-lookup"><span data-stu-id="d5030-718">localhost</span></span>
- <span data-ttu-id="d5030-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d5030-719">127.0.0.1</span></span>
- <span data-ttu-id="d5030-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="d5030-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-721">Com</span><span class="sxs-lookup"><span data-stu-id="d5030-721">com</span></span>
- <span data-ttu-id="d5030-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="d5030-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-723">網</span><span class="sxs-lookup"><span data-stu-id="d5030-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="d5030-724">Azure 儲存體帳戶金鑰（一般）</span><span class="sxs-lookup"><span data-stu-id="d5030-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-725">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-725">Format</span></span>

<span data-ttu-id="d5030-726">任何86的小寫字母或大寫字母、數位、正斜線（/）或加號（+）的組合，前置或後接下列模式中所述的字元。</span><span class="sxs-lookup"><span data-stu-id="d5030-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-727">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-727">Pattern</span></span>

- <span data-ttu-id="d5030-728">大於符號（>）、撇號（'）、等號（=）、引號（"）或數位記號（#）的0-1</span><span class="sxs-lookup"><span data-stu-id="d5030-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="d5030-729">86個字元的任何組合（低或大寫字母、數位、正斜線（/）或加號（+））</span><span class="sxs-lookup"><span data-stu-id="d5030-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="d5030-730">兩個等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="d5030-731">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-731">Checksum</span></span>

<span data-ttu-id="d5030-732">否</span><span class="sxs-lookup"><span data-stu-id="d5030-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-733">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-733">Definition</span></span>

<span data-ttu-id="d5030-734">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-735">正則運算式 CEP_Regex_AzureStorageAccountKeyGeneric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="d5030-736">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="d5030-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-737">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-737">Format</span></span>

<span data-ttu-id="d5030-738">11位數加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="d5030-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-739">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-739">Pattern</span></span>

<span data-ttu-id="d5030-740">11位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="d5030-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="d5030-741">以 YY 格式表示的六位數和兩個句點。毫米。出生日期的 DD</span><span class="sxs-lookup"><span data-stu-id="d5030-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="d5030-742">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-742">A hyphen</span></span> 
- <span data-ttu-id="d5030-743">三個連續數位（奇數用於男生，即便是女生）</span><span class="sxs-lookup"><span data-stu-id="d5030-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="d5030-744">一個句點</span><span class="sxs-lookup"><span data-stu-id="d5030-744">A period</span></span> 
- <span data-ttu-id="d5030-745">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-746">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-746">Checksum</span></span>

<span data-ttu-id="d5030-747">是</span><span class="sxs-lookup"><span data-stu-id="d5030-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-748">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-748">Definition</span></span>

<span data-ttu-id="d5030-749">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-750">函數 Func_belgium_national_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-751">會找到來自 Keyword_belgium_national_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="d5030-752">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-753">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="d5030-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="d5030-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="d5030-755">身分識別</span><span class="sxs-lookup"><span data-stu-id="d5030-755">Identity</span></span>
- <span data-ttu-id="d5030-756">註冊</span><span class="sxs-lookup"><span data-stu-id="d5030-756">Registration</span></span>
- <span data-ttu-id="d5030-757">識別</span><span class="sxs-lookup"><span data-stu-id="d5030-757">Identification</span></span> 
- <span data-ttu-id="d5030-758">ID</span><span class="sxs-lookup"><span data-stu-id="d5030-758">ID</span></span> 
- <span data-ttu-id="d5030-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="d5030-759">Identiteitskaart</span></span>
- <span data-ttu-id="d5030-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="d5030-760">Registratie nummer</span></span> 
- <span data-ttu-id="d5030-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="d5030-761">Identificatie nummer</span></span> 
- <span data-ttu-id="d5030-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="d5030-762">Identiteit</span></span>
- <span data-ttu-id="d5030-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="d5030-763">Registratie</span></span>
- <span data-ttu-id="d5030-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="d5030-764">Identificatie</span></span> 
- <span data-ttu-id="d5030-765">購買 d'identité</span><span class="sxs-lookup"><span data-stu-id="d5030-765">Carte d’identité</span></span> 
- <span data-ttu-id="d5030-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="d5030-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="d5030-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="d5030-767">numéro d'identification</span></span>
- <span data-ttu-id="d5030-768">identité</span><span class="sxs-lookup"><span data-stu-id="d5030-768">identité</span></span> 
- <span data-ttu-id="d5030-769">題詞</span><span class="sxs-lookup"><span data-stu-id="d5030-769">inscription</span></span> 
- <span data-ttu-id="d5030-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="d5030-770">Identifikation</span></span>
- <span data-ttu-id="d5030-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="d5030-771">Identifizierung</span></span>
- <span data-ttu-id="d5030-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-772">Identifikationsnummer</span></span>
- <span data-ttu-id="d5030-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="d5030-773">Personalausweis</span></span>
- <span data-ttu-id="d5030-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="d5030-774">Registrierung</span></span>
- <span data-ttu-id="d5030-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="d5030-776">巴西 CPF 號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-777">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-777">Format</span></span>

<span data-ttu-id="d5030-778">11位數包含檢查碼，可格式化或未格式化</span><span class="sxs-lookup"><span data-stu-id="d5030-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-779">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-779">Pattern</span></span>

<span data-ttu-id="d5030-780">格式 化：</span><span class="sxs-lookup"><span data-stu-id="d5030-780">Formatted:</span></span>
- <span data-ttu-id="d5030-781">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-781">Three digits</span></span> 
- <span data-ttu-id="d5030-782">一個句點</span><span class="sxs-lookup"><span data-stu-id="d5030-782">A period</span></span> 
- <span data-ttu-id="d5030-783">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-783">Three digits</span></span> 
- <span data-ttu-id="d5030-784">一個句點</span><span class="sxs-lookup"><span data-stu-id="d5030-784">A period</span></span> 
- <span data-ttu-id="d5030-785">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-785">Three digits</span></span> 
- <span data-ttu-id="d5030-786">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-786">A hyphen</span></span> 
- <span data-ttu-id="d5030-787">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-787">Two digits which are check digits</span></span>

<span data-ttu-id="d5030-788">非</span><span class="sxs-lookup"><span data-stu-id="d5030-788">Unformatted:</span></span>
- <span data-ttu-id="d5030-789">11位數的最後兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-790">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-790">Checksum</span></span>

<span data-ttu-id="d5030-791">是</span><span class="sxs-lookup"><span data-stu-id="d5030-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-792">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-792">Definition</span></span>

<span data-ttu-id="d5030-793">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-794">函數 Func_brazil_cpf 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-795">會找到來自 Keyword_brazil_cpf 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="d5030-796">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-796">The checksum passes.</span></span>

<span data-ttu-id="d5030-797">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-798">函數 Func_brazil_cpf 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-799">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-800">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="d5030-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="d5030-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="d5030-802">公積金</span><span class="sxs-lookup"><span data-stu-id="d5030-802">CPF</span></span>
- <span data-ttu-id="d5030-803">識別</span><span class="sxs-lookup"><span data-stu-id="d5030-803">Identification</span></span>
- <span data-ttu-id="d5030-804">註冊</span><span class="sxs-lookup"><span data-stu-id="d5030-804">Registration</span></span>
- <span data-ttu-id="d5030-805">收入</span><span class="sxs-lookup"><span data-stu-id="d5030-805">Revenue</span></span>
- <span data-ttu-id="d5030-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="d5030-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="d5030-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="d5030-807">Imposto</span></span> 
- <span data-ttu-id="d5030-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="d5030-808">Identificação</span></span> 
- <span data-ttu-id="d5030-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="d5030-809">Inscrição</span></span> 
- <span data-ttu-id="d5030-810">Receita</span><span class="sxs-lookup"><span data-stu-id="d5030-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="d5030-811">巴西法律實體編號（CNPJ）</span><span class="sxs-lookup"><span data-stu-id="d5030-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-812">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-812">Format</span></span>

<span data-ttu-id="d5030-813">14位數包含登記編號、分支編號及檢查數位，加上分隔符號</span><span class="sxs-lookup"><span data-stu-id="d5030-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-814">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-814">Pattern</span></span>
<span data-ttu-id="d5030-815">14位數，加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="d5030-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="d5030-816">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-816">Two digits</span></span> 
- <span data-ttu-id="d5030-817">一個句點</span><span class="sxs-lookup"><span data-stu-id="d5030-817">A period</span></span> 
- <span data-ttu-id="d5030-818">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-818">Three digits</span></span> 
- <span data-ttu-id="d5030-819">一個句點</span><span class="sxs-lookup"><span data-stu-id="d5030-819">A period</span></span> 
- <span data-ttu-id="d5030-820">三位數（前八位數為註冊碼）</span><span class="sxs-lookup"><span data-stu-id="d5030-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="d5030-821">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="d5030-821">A forward slash</span></span> 
- <span data-ttu-id="d5030-822">四位數的分支編號</span><span class="sxs-lookup"><span data-stu-id="d5030-822">Four-digit branch number</span></span> 
- <span data-ttu-id="d5030-823">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-823">A hyphen</span></span> 
- <span data-ttu-id="d5030-824">兩位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-825">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-825">Checksum</span></span>

<span data-ttu-id="d5030-826">是</span><span class="sxs-lookup"><span data-stu-id="d5030-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-827">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-827">Definition</span></span>

<span data-ttu-id="d5030-828">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-829">函數 Func_brazil_cnpj 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-830">會找到來自 Keyword_brazil_cnpj 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="d5030-831">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-831">The checksum passes.</span></span>

<span data-ttu-id="d5030-832">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-833">函數 Func_brazil_cnpj 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-834">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-835">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="d5030-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="d5030-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="d5030-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="d5030-837">CNPJ</span></span> 
- <span data-ttu-id="d5030-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="d5030-838">CNPJ/MF</span></span> 
- <span data-ttu-id="d5030-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="d5030-839">CNPJ-MF</span></span> 
- <span data-ttu-id="d5030-840">法律實體的本國登錄</span><span class="sxs-lookup"><span data-stu-id="d5030-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="d5030-841">Taxpayers 登錄</span><span class="sxs-lookup"><span data-stu-id="d5030-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="d5030-842">法律實體</span><span class="sxs-lookup"><span data-stu-id="d5030-842">Legal entity</span></span> 
- <span data-ttu-id="d5030-843">法律實體</span><span class="sxs-lookup"><span data-stu-id="d5030-843">Legal entities</span></span> 
- <span data-ttu-id="d5030-844">註冊狀態</span><span class="sxs-lookup"><span data-stu-id="d5030-844">Registration Status</span></span> 
- <span data-ttu-id="d5030-845">商務版</span><span class="sxs-lookup"><span data-stu-id="d5030-845">Business</span></span> 
- <span data-ttu-id="d5030-846">Company</span><span class="sxs-lookup"><span data-stu-id="d5030-846">Company</span></span>
- <span data-ttu-id="d5030-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="d5030-847">CNPJ</span></span> 
- <span data-ttu-id="d5030-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="d5030-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="d5030-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="d5030-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="d5030-850">CGC</span><span class="sxs-lookup"><span data-stu-id="d5030-850">CGC</span></span> 
- <span data-ttu-id="d5030-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="d5030-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="d5030-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="d5030-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="d5030-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="d5030-853">Situação cadastral</span></span> 
- <span data-ttu-id="d5030-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="d5030-854">Inscrição</span></span> 
- <span data-ttu-id="d5030-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="d5030-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="d5030-856">巴西國身分識別卡（RG）</span><span class="sxs-lookup"><span data-stu-id="d5030-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-857">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-857">Format</span></span>

<span data-ttu-id="d5030-858">Registro Geral （舊格式）：九位數</span><span class="sxs-lookup"><span data-stu-id="d5030-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="d5030-859">Registro de Identidade （RIC）（新格式）：11位數</span><span class="sxs-lookup"><span data-stu-id="d5030-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-860">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-860">Pattern</span></span>

<span data-ttu-id="d5030-861">Registro Geral （舊格式）：</span><span class="sxs-lookup"><span data-stu-id="d5030-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="d5030-862">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-862">Two digits</span></span> 
- <span data-ttu-id="d5030-863">一個句點</span><span class="sxs-lookup"><span data-stu-id="d5030-863">A period</span></span> 
- <span data-ttu-id="d5030-864">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-864">Three digits</span></span> 
- <span data-ttu-id="d5030-865">一個句點</span><span class="sxs-lookup"><span data-stu-id="d5030-865">A period</span></span> 
- <span data-ttu-id="d5030-866">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-866">Three digits</span></span> 
- <span data-ttu-id="d5030-867">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-867">A hyphen</span></span> 
- <span data-ttu-id="d5030-868">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-868">One digit which is a check digit</span></span>

<span data-ttu-id="d5030-869">Registro de Identidade （RIC）（新格式）：</span><span class="sxs-lookup"><span data-stu-id="d5030-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="d5030-870">10位數</span><span class="sxs-lookup"><span data-stu-id="d5030-870">10 digits</span></span> 
- <span data-ttu-id="d5030-871">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-871">A hyphen</span></span> 
- <span data-ttu-id="d5030-872">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-873">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-873">Checksum</span></span>

<span data-ttu-id="d5030-874">是</span><span class="sxs-lookup"><span data-stu-id="d5030-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-875">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-875">Definition</span></span>

<span data-ttu-id="d5030-876">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-877">函數 Func_brazil_rg 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-878">會找到來自 Keyword_brazil_rg 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="d5030-879">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-879">The checksum passes.</span></span>

<span data-ttu-id="d5030-880">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-881">函數 Func_brazil_rg 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-882">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-883">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="d5030-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="d5030-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="d5030-885">Cédula de identidade identity 持卡國 id número de rregistro registro de Iidentidade registro geral RG （此關鍵字區分大小寫） RIC （此關鍵字區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="d5030-886">加拿大銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-887">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-887">Format</span></span>

<span data-ttu-id="d5030-888">七位數或十二位數</span><span class="sxs-lookup"><span data-stu-id="d5030-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-889">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-889">Pattern</span></span>

<span data-ttu-id="d5030-890">加拿大銀行帳戶號碼為七位數或十二位數。</span><span class="sxs-lookup"><span data-stu-id="d5030-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="d5030-891">加拿大銀行帳戶中轉號碼為：</span><span class="sxs-lookup"><span data-stu-id="d5030-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="d5030-892">五位數</span><span class="sxs-lookup"><span data-stu-id="d5030-892">Five digits</span></span> 
- <span data-ttu-id="d5030-893">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-893">A hyphen</span></span> 
- <span data-ttu-id="d5030-894">三位數或</span><span class="sxs-lookup"><span data-stu-id="d5030-894">Three digits OR</span></span>
- <span data-ttu-id="d5030-895">零 "0"</span><span class="sxs-lookup"><span data-stu-id="d5030-895">A zero "0"</span></span> 
- <span data-ttu-id="d5030-896">八位數</span><span class="sxs-lookup"><span data-stu-id="d5030-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-897">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-897">Checksum</span></span>

<span data-ttu-id="d5030-898">否</span><span class="sxs-lookup"><span data-stu-id="d5030-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-899">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-899">Definition</span></span>

<span data-ttu-id="d5030-900">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-901">正則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-902">會找到來自 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="d5030-903">正則運算式 Regex_canada_bank_account_transit_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="d5030-904">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-905">正則運算式 Regex_canada_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-906">會找到來自 Keyword_canada_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-907">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="d5030-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="d5030-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="d5030-909">加拿大節約 bonds</span><span class="sxs-lookup"><span data-stu-id="d5030-909">canada savings bonds</span></span>
- <span data-ttu-id="d5030-910">加拿大收入代理商</span><span class="sxs-lookup"><span data-stu-id="d5030-910">canada revenue agency</span></span>
- <span data-ttu-id="d5030-911">加拿大金融機構</span><span class="sxs-lookup"><span data-stu-id="d5030-911">canadian financial institution</span></span>
- <span data-ttu-id="d5030-912">直接存放表單</span><span class="sxs-lookup"><span data-stu-id="d5030-912">direct deposit form</span></span>
- <span data-ttu-id="d5030-913">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="d5030-913">canadian citizen</span></span>
- <span data-ttu-id="d5030-914">法律代表</span><span class="sxs-lookup"><span data-stu-id="d5030-914">legal representative</span></span>
- <span data-ttu-id="d5030-915">公證</span><span class="sxs-lookup"><span data-stu-id="d5030-915">notary public</span></span>
- <span data-ttu-id="d5030-916">oaths 的英國專員辦公室</span><span class="sxs-lookup"><span data-stu-id="d5030-916">commissioner for oaths</span></span>
- <span data-ttu-id="d5030-917">兒童護理權益</span><span class="sxs-lookup"><span data-stu-id="d5030-917">child care benefit</span></span>
- <span data-ttu-id="d5030-918">通用子級護理</span><span class="sxs-lookup"><span data-stu-id="d5030-918">universal child care</span></span>
- <span data-ttu-id="d5030-919">加拿大子稅務權益</span><span class="sxs-lookup"><span data-stu-id="d5030-919">canada child tax benefit</span></span>
- <span data-ttu-id="d5030-920">所得稅權益</span><span class="sxs-lookup"><span data-stu-id="d5030-920">income tax benefit</span></span>
- <span data-ttu-id="d5030-921">已調和銷售稅</span><span class="sxs-lookup"><span data-stu-id="d5030-921">harmonized sales tax</span></span>
- <span data-ttu-id="d5030-922">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-922">social insurance number</span></span>
- <span data-ttu-id="d5030-923">所得稅退款</span><span class="sxs-lookup"><span data-stu-id="d5030-923">income tax refund</span></span>
- <span data-ttu-id="d5030-924">子稅務權益</span><span class="sxs-lookup"><span data-stu-id="d5030-924">child tax benefit</span></span>
- <span data-ttu-id="d5030-925">territorial 付款</span><span class="sxs-lookup"><span data-stu-id="d5030-925">territorial payments</span></span>
- <span data-ttu-id="d5030-926">機構號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-926">institution number</span></span>
- <span data-ttu-id="d5030-927">放入要求</span><span class="sxs-lookup"><span data-stu-id="d5030-927">deposit request</span></span>
- <span data-ttu-id="d5030-928">銀行資訊</span><span class="sxs-lookup"><span data-stu-id="d5030-928">banking information</span></span>
- <span data-ttu-id="d5030-929">直接存款</span><span class="sxs-lookup"><span data-stu-id="d5030-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="d5030-930">加拿大駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-931">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-931">Format</span></span>

<span data-ttu-id="d5030-932">依省份</span><span class="sxs-lookup"><span data-stu-id="d5030-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-933">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-933">Pattern</span></span>

<span data-ttu-id="d5030-934">涵蓋 Alberta、英屬哥倫比亞、Manitoba、新的 Brunswick、Newfoundland/Labrador、Nova Scotia、安大略、Prince Edward 孤島、魁北克和薩斯的各種模式</span><span class="sxs-lookup"><span data-stu-id="d5030-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-935">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-935">Checksum</span></span>

<span data-ttu-id="d5030-936">否</span><span class="sxs-lookup"><span data-stu-id="d5030-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-937">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-937">Definition</span></span>

<span data-ttu-id="d5030-938">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-939">函數 Func_ [province_name] _drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-940">找到來自 Keyword_ [province_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="d5030-941">會找到來自 Keyword_canada_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-942">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="d5030-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="d5030-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="d5030-944">省/直轄市縮寫，例如 AB</span><span class="sxs-lookup"><span data-stu-id="d5030-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="d5030-945">省/市名稱，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="d5030-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="d5030-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d5030-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="d5030-947">Dl</span><span class="sxs-lookup"><span data-stu-id="d5030-947">DL</span></span>
- <span data-ttu-id="d5030-948">Dls</span><span class="sxs-lookup"><span data-stu-id="d5030-948">DLS</span></span>
- <span data-ttu-id="d5030-949">民盟</span><span class="sxs-lookup"><span data-stu-id="d5030-949">CDL</span></span>
- <span data-ttu-id="d5030-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="d5030-950">CDLS</span></span>
- <span data-ttu-id="d5030-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="d5030-951">DriverLic</span></span>
- <span data-ttu-id="d5030-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="d5030-952">DriverLics</span></span>
- <span data-ttu-id="d5030-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="d5030-953">DriverLicense</span></span>
- <span data-ttu-id="d5030-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="d5030-954">DriverLicenses</span></span>
- <span data-ttu-id="d5030-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="d5030-955">DriverLicence</span></span>
- <span data-ttu-id="d5030-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="d5030-956">DriverLicences</span></span>
- <span data-ttu-id="d5030-957">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-957">Driver Lic</span></span>
- <span data-ttu-id="d5030-958">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-958">Driver Lics</span></span>
- <span data-ttu-id="d5030-959">駕照</span><span class="sxs-lookup"><span data-stu-id="d5030-959">Driver License</span></span>
- <span data-ttu-id="d5030-960">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-960">Driver Licenses</span></span>
- <span data-ttu-id="d5030-961">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-961">Driver Licence</span></span>
- <span data-ttu-id="d5030-962">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-962">Driver Licences</span></span>
- <span data-ttu-id="d5030-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="d5030-963">DriversLic</span></span>
- <span data-ttu-id="d5030-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="d5030-964">DriversLics</span></span>
- <span data-ttu-id="d5030-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="d5030-965">DriversLicence</span></span>
- <span data-ttu-id="d5030-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="d5030-966">DriversLicences</span></span>
- <span data-ttu-id="d5030-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="d5030-967">DriversLicense</span></span>
- <span data-ttu-id="d5030-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="d5030-968">DriversLicenses</span></span>
- <span data-ttu-id="d5030-969">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-969">Drivers Lic</span></span>
- <span data-ttu-id="d5030-970">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-970">Drivers Lics</span></span>
- <span data-ttu-id="d5030-971">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-971">Drivers License</span></span>
- <span data-ttu-id="d5030-972">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-972">Drivers Licenses</span></span>
- <span data-ttu-id="d5030-973">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-973">Drivers Licence</span></span>
- <span data-ttu-id="d5030-974">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-974">Drivers Licences</span></span>
- <span data-ttu-id="d5030-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-975">Driver'Lic</span></span>
- <span data-ttu-id="d5030-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-976">Driver'Lics</span></span>
- <span data-ttu-id="d5030-977">Driver'License</span><span class="sxs-lookup"><span data-stu-id="d5030-977">Driver'License</span></span>
- <span data-ttu-id="d5030-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="d5030-978">Driver'Licenses</span></span>
- <span data-ttu-id="d5030-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="d5030-979">Driver'Licence</span></span>
- <span data-ttu-id="d5030-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="d5030-980">Driver'Licences</span></span>
- <span data-ttu-id="d5030-981">驅動程式「.Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-981">Driver' Lic</span></span>
- <span data-ttu-id="d5030-982">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-982">Driver' Lics</span></span>
- <span data-ttu-id="d5030-983">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-983">Driver' License</span></span>
- <span data-ttu-id="d5030-984">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="d5030-984">Driver' Licenses</span></span>
- <span data-ttu-id="d5030-985">驅動程式 ' 許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-985">Driver' Licence</span></span>
- <span data-ttu-id="d5030-986">驅動程式 ' 授權</span><span class="sxs-lookup"><span data-stu-id="d5030-986">Driver' Licences</span></span>
- <span data-ttu-id="d5030-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="d5030-987">Driver'sLic</span></span>
- <span data-ttu-id="d5030-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="d5030-988">Driver'sLics</span></span>
- <span data-ttu-id="d5030-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="d5030-989">Driver'sLicense</span></span>
- <span data-ttu-id="d5030-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="d5030-990">Driver'sLicenses</span></span>
- <span data-ttu-id="d5030-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="d5030-991">Driver'sLicence</span></span>
- <span data-ttu-id="d5030-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="d5030-992">Driver'sLicences</span></span>
- <span data-ttu-id="d5030-993">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-993">Driver's Lic</span></span>
- <span data-ttu-id="d5030-994">驅動程式的 Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-994">Driver's Lics</span></span>
- <span data-ttu-id="d5030-995">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-995">Driver's License</span></span>
- <span data-ttu-id="d5030-996">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-996">Driver's Licenses</span></span>
- <span data-ttu-id="d5030-997">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-997">Driver's Licence</span></span>
- <span data-ttu-id="d5030-998">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-998">Driver's Licences</span></span>
- <span data-ttu-id="d5030-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="d5030-999">Permis de Conduire</span></span>
- <span data-ttu-id="d5030-1000">id</span><span class="sxs-lookup"><span data-stu-id="d5030-1000">id</span></span>
- <span data-ttu-id="d5030-1001">Id</span><span class="sxs-lookup"><span data-stu-id="d5030-1001">ids</span></span>
- <span data-ttu-id="d5030-1002">idcard 編號</span><span class="sxs-lookup"><span data-stu-id="d5030-1002">idcard number</span></span>
- <span data-ttu-id="d5030-1003">idcard 編號</span><span class="sxs-lookup"><span data-stu-id="d5030-1003">idcard numbers</span></span>
- <span data-ttu-id="d5030-1004">idcard#</span><span class="sxs-lookup"><span data-stu-id="d5030-1004">idcard #</span></span>
- <span data-ttu-id="d5030-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="d5030-1005">idcard #s</span></span>
- <span data-ttu-id="d5030-1006">idcard 卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-1006">idcard card</span></span>
- <span data-ttu-id="d5030-1007">idcard 卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-1007">idcard cards</span></span>
- <span data-ttu-id="d5030-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="d5030-1008">idcard</span></span>
- <span data-ttu-id="d5030-1009">識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1009">identification number</span></span>
- <span data-ttu-id="d5030-1010">識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1010">identification numbers</span></span>
- <span data-ttu-id="d5030-1011">識別#</span><span class="sxs-lookup"><span data-stu-id="d5030-1011">identification #</span></span>
- <span data-ttu-id="d5030-1012">識別 #s</span><span class="sxs-lookup"><span data-stu-id="d5030-1012">identification #s</span></span>
- <span data-ttu-id="d5030-1013">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1013">identification card</span></span>
- <span data-ttu-id="d5030-1014">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-1014">identification cards</span></span>
- <span data-ttu-id="d5030-1015">識別</span><span class="sxs-lookup"><span data-stu-id="d5030-1015">identification</span></span> 
- <span data-ttu-id="d5030-1016">Dl#</span><span class="sxs-lookup"><span data-stu-id="d5030-1016">DL#</span></span>
- <span data-ttu-id="d5030-1017">Dls#</span><span class="sxs-lookup"><span data-stu-id="d5030-1017">DLS#</span></span> 
- <span data-ttu-id="d5030-1018">民盟#</span><span class="sxs-lookup"><span data-stu-id="d5030-1018">CDL#</span></span> 
- <span data-ttu-id="d5030-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="d5030-1019">CDLS#</span></span> 
- <span data-ttu-id="d5030-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="d5030-1020">DriverLic#</span></span> 
- <span data-ttu-id="d5030-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="d5030-1021">DriverLics#</span></span> 
- <span data-ttu-id="d5030-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="d5030-1022">DriverLicense#</span></span> 
- <span data-ttu-id="d5030-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="d5030-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="d5030-1024">DriverLicence#</span></span> 
- <span data-ttu-id="d5030-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="d5030-1025">DriverLicences#</span></span> 
- <span data-ttu-id="d5030-1026">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="d5030-1026">Driver Lic#</span></span>
- <span data-ttu-id="d5030-1027">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-1027">Driver Lics#</span></span> 
- <span data-ttu-id="d5030-1028">駕照#</span><span class="sxs-lookup"><span data-stu-id="d5030-1028">Driver License#</span></span> 
- <span data-ttu-id="d5030-1029">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="d5030-1030">駕照#</span><span class="sxs-lookup"><span data-stu-id="d5030-1030">Driver License#</span></span> 
- <span data-ttu-id="d5030-1031">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-1031">Driver Licences#</span></span> 
- <span data-ttu-id="d5030-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="d5030-1032">DriversLic#</span></span> 
- <span data-ttu-id="d5030-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="d5030-1033">DriversLics#</span></span> 
- <span data-ttu-id="d5030-1034">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="d5030-1034">DriversLicense#</span></span> 
- <span data-ttu-id="d5030-1035">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="d5030-1036">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="d5030-1036">DriversLicence#</span></span> 
- <span data-ttu-id="d5030-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="d5030-1037">DriversLicences#</span></span> 
- <span data-ttu-id="d5030-1038">驅動程式 .Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="d5030-1039">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="d5030-1040">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-1040">Drivers License#</span></span> 
- <span data-ttu-id="d5030-1041">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="d5030-1042">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="d5030-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="d5030-1043">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="d5030-1044">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="d5030-1045">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="d5030-1046">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="d5030-1046">Driver'License#</span></span> 
- <span data-ttu-id="d5030-1047">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="d5030-1048">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="d5030-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="d5030-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="d5030-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="d5030-1050">驅動程式「.Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="d5030-1051">驅動程式 ' Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="d5030-1052">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-1052">Driver' License#</span></span> 
- <span data-ttu-id="d5030-1053">驅動程式的授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="d5030-1054">驅動程式 ' 許可證#</span><span class="sxs-lookup"><span data-stu-id="d5030-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="d5030-1055">驅動程式 ' 授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="d5030-1056">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="d5030-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="d5030-1057">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="d5030-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="d5030-1058">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="d5030-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="d5030-1059">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="d5030-1060">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="d5030-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="d5030-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="d5030-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="d5030-1062">驅動程式的 .Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="d5030-1063">驅動程式的 Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="d5030-1064">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-1064">Driver's License#</span></span> 
- <span data-ttu-id="d5030-1065">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="d5030-1066">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="d5030-1067">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="d5030-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="d5030-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="d5030-1069">Id#</span><span class="sxs-lookup"><span data-stu-id="d5030-1069">id#</span></span> 
- <span data-ttu-id="d5030-1070">Id#</span><span class="sxs-lookup"><span data-stu-id="d5030-1070">ids#</span></span> 
- <span data-ttu-id="d5030-1071">idcard 卡片#</span><span class="sxs-lookup"><span data-stu-id="d5030-1071">idcard card#</span></span> 
- <span data-ttu-id="d5030-1072">idcard 卡片#</span><span class="sxs-lookup"><span data-stu-id="d5030-1072">idcard cards#</span></span> 
- <span data-ttu-id="d5030-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="d5030-1073">idcard#</span></span> 
- <span data-ttu-id="d5030-1074">身分識別卡#</span><span class="sxs-lookup"><span data-stu-id="d5030-1074">identification card#</span></span> 
- <span data-ttu-id="d5030-1075">身份證#</span><span class="sxs-lookup"><span data-stu-id="d5030-1075">identification cards#</span></span> 
- <span data-ttu-id="d5030-1076">識別#</span><span class="sxs-lookup"><span data-stu-id="d5030-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="d5030-1077">加拿大健康情況服務號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1078">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1078">Format</span></span>

<span data-ttu-id="d5030-1079">10位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1080">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1080">Pattern</span></span>

<span data-ttu-id="d5030-1081">10位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1082">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1082">Checksum</span></span>

<span data-ttu-id="d5030-1083">否</span><span class="sxs-lookup"><span data-stu-id="d5030-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1084">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1084">Definition</span></span>

<span data-ttu-id="d5030-1085">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1086">正則運算式 Regex_canada_health_service_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1087">會找到來自 Keyword_canada_health_service_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-1088">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="d5030-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="d5030-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="d5030-1090">個人健康號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1090">personal health number</span></span>
- <span data-ttu-id="d5030-1091">患者資訊</span><span class="sxs-lookup"><span data-stu-id="d5030-1091">patient information</span></span>
- <span data-ttu-id="d5030-1092">健康情況服務</span><span class="sxs-lookup"><span data-stu-id="d5030-1092">health services</span></span>
- <span data-ttu-id="d5030-1093">speciality 服務</span><span class="sxs-lookup"><span data-stu-id="d5030-1093">speciality services</span></span>
- <span data-ttu-id="d5030-1094">汽車意外</span><span class="sxs-lookup"><span data-stu-id="d5030-1094">automobile accident</span></span>
- <span data-ttu-id="d5030-1095">病人醫院</span><span class="sxs-lookup"><span data-stu-id="d5030-1095">patient hospital</span></span>
- <span data-ttu-id="d5030-1096">心理醫生</span><span class="sxs-lookup"><span data-stu-id="d5030-1096">psychiatrist</span></span>
- <span data-ttu-id="d5030-1097">工作人員薪酬</span><span class="sxs-lookup"><span data-stu-id="d5030-1097">workers compensation</span></span>
- <span data-ttu-id="d5030-1098">殘疾</span><span class="sxs-lookup"><span data-stu-id="d5030-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="d5030-1099">加拿大護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1100">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1100">Format</span></span>

<span data-ttu-id="d5030-1101">兩個大寫字母後接六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1102">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1102">Pattern</span></span>

<span data-ttu-id="d5030-1103">兩個大寫字母後接六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1104">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1104">Checksum</span></span>

<span data-ttu-id="d5030-1105">否</span><span class="sxs-lookup"><span data-stu-id="d5030-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1106">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1106">Definition</span></span>

<span data-ttu-id="d5030-1107">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1108">正則運算式 Regex_canada_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1109">會找到 Keyword_canada_passport_number 或 Keyword_passport 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-1110">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="d5030-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="d5030-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="d5030-1112">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="d5030-1112">canadian citizenship</span></span>
- <span data-ttu-id="d5030-1113">加拿大護照</span><span class="sxs-lookup"><span data-stu-id="d5030-1113">canadian passport</span></span>
- <span data-ttu-id="d5030-1114">護照應用程式</span><span class="sxs-lookup"><span data-stu-id="d5030-1114">passport application</span></span>
- <span data-ttu-id="d5030-1115">護照相片</span><span class="sxs-lookup"><span data-stu-id="d5030-1115">passport photos</span></span>
- <span data-ttu-id="d5030-1116">認證的翻譯員</span><span class="sxs-lookup"><span data-stu-id="d5030-1116">certified translator</span></span>
- <span data-ttu-id="d5030-1117">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="d5030-1117">canadian citizens</span></span>
- <span data-ttu-id="d5030-1118">處理時間</span><span class="sxs-lookup"><span data-stu-id="d5030-1118">processing times</span></span>
- <span data-ttu-id="d5030-1119">更新應用程式</span><span class="sxs-lookup"><span data-stu-id="d5030-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="d5030-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d5030-1120">Keyword_passport</span></span>

- <span data-ttu-id="d5030-1121">護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1121">Passport Number</span></span>
- <span data-ttu-id="d5030-1122">護照否</span><span class="sxs-lookup"><span data-stu-id="d5030-1122">Passport No</span></span>
- <span data-ttu-id="d5030-1123">護照#</span><span class="sxs-lookup"><span data-stu-id="d5030-1123">Passport #</span></span>
- <span data-ttu-id="d5030-1124">護照#</span><span class="sxs-lookup"><span data-stu-id="d5030-1124">Passport#</span></span>
- <span data-ttu-id="d5030-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="d5030-1125">PassportID</span></span>
- <span data-ttu-id="d5030-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="d5030-1126">Passportno</span></span>
- <span data-ttu-id="d5030-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-1127">passportnumber</span></span>
- <span data-ttu-id="d5030-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="d5030-1128">パスポート</span></span>
- <span data-ttu-id="d5030-1129">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="d5030-1129">パスポート番号</span></span>
- <span data-ttu-id="d5030-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d5030-1130">パスポートのNum</span></span>
- <span data-ttu-id="d5030-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="d5030-1131">パスポート＃</span></span>
- <span data-ttu-id="d5030-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d5030-1132">Numéro de passeport</span></span>
- <span data-ttu-id="d5030-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d5030-1133">Passeport n °</span></span>
- <span data-ttu-id="d5030-1134">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="d5030-1134">Passeport Non</span></span>
- <span data-ttu-id="d5030-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d5030-1135">Passeport #</span></span>
- <span data-ttu-id="d5030-1136">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d5030-1136">Passeport#</span></span>
- <span data-ttu-id="d5030-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d5030-1137">PasseportNon</span></span>
- <span data-ttu-id="d5030-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d5030-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="d5030-1139">加拿大個人健康身分識別號碼（PHIN）</span><span class="sxs-lookup"><span data-stu-id="d5030-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1140">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1140">Format</span></span>

<span data-ttu-id="d5030-1141">九位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1142">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1142">Pattern</span></span>

<span data-ttu-id="d5030-1143">九位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1144">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1144">Checksum</span></span>

<span data-ttu-id="d5030-1145">否</span><span class="sxs-lookup"><span data-stu-id="d5030-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1146">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1146">Definition</span></span>

<span data-ttu-id="d5030-1147">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：正則運算式 Regex_canada_phin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="d5030-1148">至少會找到兩個 Keyword_canada_phin 或 Keyword_canada_provinces 中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-1149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="d5030-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="d5030-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="d5030-1151">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1151">social insurance number</span></span>
- <span data-ttu-id="d5030-1152">狀況資訊法案</span><span class="sxs-lookup"><span data-stu-id="d5030-1152">health information act</span></span>
- <span data-ttu-id="d5030-1153">所得稅資訊</span><span class="sxs-lookup"><span data-stu-id="d5030-1153">income tax information</span></span>
- <span data-ttu-id="d5030-1154">manitoba 健康情況</span><span class="sxs-lookup"><span data-stu-id="d5030-1154">manitoba health</span></span>
- <span data-ttu-id="d5030-1155">健康情況登記</span><span class="sxs-lookup"><span data-stu-id="d5030-1155">health registration</span></span>
- <span data-ttu-id="d5030-1156">處方購買</span><span class="sxs-lookup"><span data-stu-id="d5030-1156">prescription purchases</span></span>
- <span data-ttu-id="d5030-1157">效益資格</span><span class="sxs-lookup"><span data-stu-id="d5030-1157">benefit eligibility</span></span>
- <span data-ttu-id="d5030-1158">個人健康情況</span><span class="sxs-lookup"><span data-stu-id="d5030-1158">personal health</span></span>
- <span data-ttu-id="d5030-1159">律師的權力</span><span class="sxs-lookup"><span data-stu-id="d5030-1159">power of attorney</span></span>
- <span data-ttu-id="d5030-1160">登記編號</span><span class="sxs-lookup"><span data-stu-id="d5030-1160">registration number</span></span>
- <span data-ttu-id="d5030-1161">個人健康號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1161">personal health number</span></span>
- <span data-ttu-id="d5030-1162">practitioner 參照</span><span class="sxs-lookup"><span data-stu-id="d5030-1162">practitioner referral</span></span>
- <span data-ttu-id="d5030-1163">wellness 專業版</span><span class="sxs-lookup"><span data-stu-id="d5030-1163">wellness professional</span></span>
- <span data-ttu-id="d5030-1164">患者參考</span><span class="sxs-lookup"><span data-stu-id="d5030-1164">patient referral</span></span>
- <span data-ttu-id="d5030-1165">健康情況與 wellness</span><span class="sxs-lookup"><span data-stu-id="d5030-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="d5030-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="d5030-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="d5030-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="d5030-1167">Nunavut</span></span>
- <span data-ttu-id="d5030-1168">魁北克</span><span class="sxs-lookup"><span data-stu-id="d5030-1168">Quebec</span></span>
- <span data-ttu-id="d5030-1169">西北領地</span><span class="sxs-lookup"><span data-stu-id="d5030-1169">Northwest Territories</span></span>
- <span data-ttu-id="d5030-1170">安大略省</span><span class="sxs-lookup"><span data-stu-id="d5030-1170">Ontario</span></span>
- <span data-ttu-id="d5030-1171">不列顛哥倫比亞省</span><span class="sxs-lookup"><span data-stu-id="d5030-1171">British Columbia</span></span>
- <span data-ttu-id="d5030-1172">阿爾比省</span><span class="sxs-lookup"><span data-stu-id="d5030-1172">Alberta</span></span>
- <span data-ttu-id="d5030-1173">薩斯喀徹爾省</span><span class="sxs-lookup"><span data-stu-id="d5030-1173">Saskatchewan</span></span>
- <span data-ttu-id="d5030-1174">馬尼托巴省</span><span class="sxs-lookup"><span data-stu-id="d5030-1174">Manitoba</span></span>
- <span data-ttu-id="d5030-1175">育 空</span><span class="sxs-lookup"><span data-stu-id="d5030-1175">Yukon</span></span>
- <span data-ttu-id="d5030-1176">紐芬蘭和 Labrador</span><span class="sxs-lookup"><span data-stu-id="d5030-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="d5030-1177">新不倫瑞克省</span><span class="sxs-lookup"><span data-stu-id="d5030-1177">New Brunswick</span></span>
- <span data-ttu-id="d5030-1178">新斯科舍省</span><span class="sxs-lookup"><span data-stu-id="d5030-1178">Nova Scotia</span></span>
- <span data-ttu-id="d5030-1179">艾德華王子島</span><span class="sxs-lookup"><span data-stu-id="d5030-1179">Prince Edward Island</span></span>
- <span data-ttu-id="d5030-1180">加拿大</span><span class="sxs-lookup"><span data-stu-id="d5030-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="d5030-1181">加拿大社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1182">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1182">Format</span></span>

<span data-ttu-id="d5030-1183">具有選擇性連字號或空格的九位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1184">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1184">Pattern</span></span>

<span data-ttu-id="d5030-1185">格式 化：</span><span class="sxs-lookup"><span data-stu-id="d5030-1185">Formatted:</span></span>
- <span data-ttu-id="d5030-1186">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1186">Three digits</span></span> 
- <span data-ttu-id="d5030-1187">連字號或空格</span><span class="sxs-lookup"><span data-stu-id="d5030-1187">A hyphen or space</span></span> 
- <span data-ttu-id="d5030-1188">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1188">Three digits</span></span> 
- <span data-ttu-id="d5030-1189">連字號或空格</span><span class="sxs-lookup"><span data-stu-id="d5030-1189">A hyphen or space</span></span> 
- <span data-ttu-id="d5030-1190">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1190">Three digits</span></span>

<span data-ttu-id="d5030-1191">未格式化：九位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1192">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1192">Checksum</span></span>

<span data-ttu-id="d5030-1193">是</span><span class="sxs-lookup"><span data-stu-id="d5030-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1194">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1194">Definition</span></span>

<span data-ttu-id="d5030-1195">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1196">函數 Func_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1197">下列其中一種組合，至少有兩種：</span><span class="sxs-lookup"><span data-stu-id="d5030-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="d5030-1198">會找到來自 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="d5030-1199">會找到來自 Keyword_sin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="d5030-1200">函數 Func_eu_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d5030-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d5030-1201">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1201">The checksum passes.</span></span>

<span data-ttu-id="d5030-1202">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1203">函數 Func_unformatted_canadian_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1204">會找到來自 Keyword_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="d5030-1205">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-1206">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="d5030-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="d5030-1207">Keyword_sin</span></span>

- <span data-ttu-id="d5030-1208">罪</span><span class="sxs-lookup"><span data-stu-id="d5030-1208">sin</span></span> 
- <span data-ttu-id="d5030-1209">社交保險</span><span class="sxs-lookup"><span data-stu-id="d5030-1209">social insurance</span></span> 
- <span data-ttu-id="d5030-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="d5030-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="d5030-1211">罪</span><span class="sxs-lookup"><span data-stu-id="d5030-1211">sins</span></span> 
- <span data-ttu-id="d5030-1212">Ssn</span><span class="sxs-lookup"><span data-stu-id="d5030-1212">ssn</span></span> 
- <span data-ttu-id="d5030-1213">主旨 ssn</span><span class="sxs-lookup"><span data-stu-id="d5030-1213">ssns</span></span> 
- <span data-ttu-id="d5030-1214">社會保障</span><span class="sxs-lookup"><span data-stu-id="d5030-1214">social security</span></span> 
- <span data-ttu-id="d5030-1215">numero d'assurance 社交</span><span class="sxs-lookup"><span data-stu-id="d5030-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="d5030-1216">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1216">national identification number</span></span> 
- <span data-ttu-id="d5030-1217">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1217">national id</span></span> 
- <span data-ttu-id="d5030-1218">罪#</span><span class="sxs-lookup"><span data-stu-id="d5030-1218">sin#</span></span> 
- <span data-ttu-id="d5030-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="d5030-1219">soc ins</span></span> 
- <span data-ttu-id="d5030-1220">社交 ins</span><span class="sxs-lookup"><span data-stu-id="d5030-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="d5030-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="d5030-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="d5030-1222">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-1222">driver's license</span></span> 
- <span data-ttu-id="d5030-1223">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-1223">drivers license</span></span> 
- <span data-ttu-id="d5030-1224">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-1224">driver's licence</span></span> 
- <span data-ttu-id="d5030-1225">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-1225">drivers licence</span></span> 
- <span data-ttu-id="d5030-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="d5030-1226">DOB</span></span> 
- <span data-ttu-id="d5030-1227">出生日期</span><span class="sxs-lookup"><span data-stu-id="d5030-1227">Birthdate</span></span> 
- <span data-ttu-id="d5030-1228">生日</span><span class="sxs-lookup"><span data-stu-id="d5030-1228">Birthday</span></span> 
- <span data-ttu-id="d5030-1229">出生日期</span><span class="sxs-lookup"><span data-stu-id="d5030-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="d5030-1230">智利身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1231">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1231">Format</span></span>

<span data-ttu-id="d5030-1232">7-8 位數加上分隔符號 a check digits 或字母</span><span class="sxs-lookup"><span data-stu-id="d5030-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1233">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1233">Pattern</span></span>

<span data-ttu-id="d5030-1234">7-8 位數加上分隔符號：</span><span class="sxs-lookup"><span data-stu-id="d5030-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="d5030-1235">1-2 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1235">1-2 digits</span></span> 
- <span data-ttu-id="d5030-1236">一個句點</span><span class="sxs-lookup"><span data-stu-id="d5030-1236">A period</span></span> 
- <span data-ttu-id="d5030-1237">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1237">Three digits</span></span> 
- <span data-ttu-id="d5030-1238">一個句點</span><span class="sxs-lookup"><span data-stu-id="d5030-1238">A period</span></span> 
- <span data-ttu-id="d5030-1239">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1239">Three digits</span></span> 
- <span data-ttu-id="d5030-1240">虛線</span><span class="sxs-lookup"><span data-stu-id="d5030-1240">A dash</span></span> 
- <span data-ttu-id="d5030-1241">一個數位或字母（不區分大小寫），這是一種檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1242">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1242">Checksum</span></span>

<span data-ttu-id="d5030-1243">是</span><span class="sxs-lookup"><span data-stu-id="d5030-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1244">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1244">Definition</span></span>

<span data-ttu-id="d5030-1245">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1246">函數 Func_chile_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1247">會找到來自 Keyword_chile_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="d5030-1248">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1248">The checksum passes.</span></span>

<span data-ttu-id="d5030-1249">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1250">函數 Func_chile_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1251">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-1252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="d5030-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="d5030-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="d5030-1254">國家識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1254">National Identification Number</span></span> 
- <span data-ttu-id="d5030-1255">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-1255">Identity card</span></span> 
- <span data-ttu-id="d5030-1256">ID</span><span class="sxs-lookup"><span data-stu-id="d5030-1256">ID</span></span> 
- <span data-ttu-id="d5030-1257">識別</span><span class="sxs-lookup"><span data-stu-id="d5030-1257">Identification</span></span> 
- <span data-ttu-id="d5030-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="d5030-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="d5030-1259">運行</span><span class="sxs-lookup"><span data-stu-id="d5030-1259">RUN</span></span> 
- <span data-ttu-id="d5030-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="d5030-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="d5030-1261">車轍</span><span class="sxs-lookup"><span data-stu-id="d5030-1261">RUT</span></span> 
- <span data-ttu-id="d5030-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="d5030-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="d5030-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="d5030-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="d5030-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="d5030-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="d5030-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="d5030-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="d5030-1266">中國居民身分識別卡片（中國）號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1267">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1267">Format</span></span>

<span data-ttu-id="d5030-1268">18位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1269">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1269">Pattern</span></span>

<span data-ttu-id="d5030-1270">18位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-1270">18 digits:</span></span>
- <span data-ttu-id="d5030-1271">六位數的位址碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="d5030-1272">在 YYYYMMDD 中的八位數（出生日期）</span><span class="sxs-lookup"><span data-stu-id="d5030-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d5030-1273">三位數的訂單碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="d5030-1274">一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1275">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1275">Checksum</span></span>

<span data-ttu-id="d5030-1276">是</span><span class="sxs-lookup"><span data-stu-id="d5030-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1277">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1277">Definition</span></span>

<span data-ttu-id="d5030-1278">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1279">函數 Func_china_resident_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1280">會找到來自 Keyword_china_resident_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="d5030-1281">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1281">The checksum passes.</span></span>

<span data-ttu-id="d5030-1282">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1283">函數 Func_china_resident_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1284">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-1285">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="d5030-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="d5030-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="d5030-1287">常駐身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="d5030-1288">中國</span><span class="sxs-lookup"><span data-stu-id="d5030-1288">PRC</span></span> 
- <span data-ttu-id="d5030-1289">全國身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1289">National Identification Card</span></span> 
- <span data-ttu-id="d5030-1290">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-1290">身份证</span></span> 
- <span data-ttu-id="d5030-1291">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-1291">居民 身份证</span></span> 
- <span data-ttu-id="d5030-1292">居民身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-1292">居民身份证</span></span> 
- <span data-ttu-id="d5030-1293">鑒定</span><span class="sxs-lookup"><span data-stu-id="d5030-1293">鉴定</span></span> 
- <span data-ttu-id="d5030-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-1294">身分證</span></span> 
- <span data-ttu-id="d5030-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-1295">居民 身份證</span></span>
- <span data-ttu-id="d5030-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="d5030-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="d5030-1297">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1298">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1298">Format</span></span>

<span data-ttu-id="d5030-1299">14至16位數，可格式化或未格式化（dddddddddddddddd），且必須透過 Luhn 測試。</span><span class="sxs-lookup"><span data-stu-id="d5030-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1300">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1300">Pattern</span></span>

<span data-ttu-id="d5030-1301">非常複雜且健全的模式，可偵測全球所有主要品牌的卡，包括簽證、MasterCard、探索卡、JCB、美洲 Express、禮品卡和 diner 卡。</span><span class="sxs-lookup"><span data-stu-id="d5030-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1302">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1302">Checksum</span></span>

<span data-ttu-id="d5030-1303">是，Luhn 檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1304">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1304">Definition</span></span>

<span data-ttu-id="d5030-1305">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1306">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1307">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="d5030-1307">One of the following is true:</span></span>
    - <span data-ttu-id="d5030-1308">會找到來自 Keyword_cc_verification 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="d5030-1309">會找到來自 Keyword_cc_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="d5030-1310">函數 Func_expiration_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d5030-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d5030-1311">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1311">The checksum passes.</span></span>

<span data-ttu-id="d5030-1312">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1313">函數 Func_credit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1314">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-1315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="d5030-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="d5030-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="d5030-1317">名片驗證</span><span class="sxs-lookup"><span data-stu-id="d5030-1317">card verification</span></span>
- <span data-ttu-id="d5030-1318">卡片識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1318">card identification number</span></span>
- <span data-ttu-id="d5030-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="d5030-1319">cvn</span></span>
- <span data-ttu-id="d5030-1320">cid</span><span class="sxs-lookup"><span data-stu-id="d5030-1320">cid</span></span>
- <span data-ttu-id="d5030-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="d5030-1321">cvc2</span></span>
- <span data-ttu-id="d5030-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="d5030-1322">cvv2</span></span>
- <span data-ttu-id="d5030-1323">pin 區區塊</span><span class="sxs-lookup"><span data-stu-id="d5030-1323">pin block</span></span>
- <span data-ttu-id="d5030-1324">安全性代碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1324">security code</span></span>
- <span data-ttu-id="d5030-1325">安全性號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1325">security number</span></span>
- <span data-ttu-id="d5030-1326">安全性否</span><span class="sxs-lookup"><span data-stu-id="d5030-1326">security no</span></span>
- <span data-ttu-id="d5030-1327">發行編號</span><span class="sxs-lookup"><span data-stu-id="d5030-1327">issue number</span></span>
- <span data-ttu-id="d5030-1328">問題否</span><span class="sxs-lookup"><span data-stu-id="d5030-1328">issue no</span></span>
- <span data-ttu-id="d5030-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="d5030-1329">cryptogramme</span></span>
- <span data-ttu-id="d5030-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="d5030-1330">numéro de sécurité</span></span>
- <span data-ttu-id="d5030-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="d5030-1331">numero de securite</span></span>
- <span data-ttu-id="d5030-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="d5030-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="d5030-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d5030-1334">prüfziffer</span></span>
- <span data-ttu-id="d5030-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="d5030-1335">prufziffer</span></span>
- <span data-ttu-id="d5030-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="d5030-1336">sicherheits Kode</span></span>
- <span data-ttu-id="d5030-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="d5030-1337">sicherheitscode</span></span>
- <span data-ttu-id="d5030-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="d5030-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="d5030-1339">verfalldatum</span></span>
- <span data-ttu-id="d5030-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="d5030-1340">codice di verifica</span></span>
- <span data-ttu-id="d5030-1341">Cod。</span><span class="sxs-lookup"><span data-stu-id="d5030-1341">cod.</span></span> <span data-ttu-id="d5030-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="d5030-1342">sicurezza</span></span>
- <span data-ttu-id="d5030-1343">貨至 sicurezza</span><span class="sxs-lookup"><span data-stu-id="d5030-1343">cod sicurezza</span></span>
- <span data-ttu-id="d5030-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d5030-1344">n autorizzazione</span></span>
- <span data-ttu-id="d5030-1345">código</span><span class="sxs-lookup"><span data-stu-id="d5030-1345">código</span></span>
- <span data-ttu-id="d5030-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="d5030-1346">codigo</span></span>
- <span data-ttu-id="d5030-1347">Cod。</span><span class="sxs-lookup"><span data-stu-id="d5030-1347">cod.</span></span> <span data-ttu-id="d5030-1348">Seg</span><span class="sxs-lookup"><span data-stu-id="d5030-1348">seg</span></span>
- <span data-ttu-id="d5030-1349">貨至 seg</span><span class="sxs-lookup"><span data-stu-id="d5030-1349">cod seg</span></span>
- <span data-ttu-id="d5030-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1350">código de segurança</span></span>
- <span data-ttu-id="d5030-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="d5030-1351">codigo de seguranca</span></span>
- <span data-ttu-id="d5030-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1352">codigo de segurança</span></span>
- <span data-ttu-id="d5030-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="d5030-1353">código de seguranca</span></span>
- <span data-ttu-id="d5030-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="d5030-1354">cód.</span></span> <span data-ttu-id="d5030-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1355">segurança</span></span>
- <span data-ttu-id="d5030-1356">Cod。</span><span class="sxs-lookup"><span data-stu-id="d5030-1356">cod.</span></span> <span data-ttu-id="d5030-1357">seguranca 貨。</span><span class="sxs-lookup"><span data-stu-id="d5030-1357">seguranca cod.</span></span> <span data-ttu-id="d5030-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1358">segurança</span></span>
- <span data-ttu-id="d5030-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="d5030-1359">cód.</span></span> <span data-ttu-id="d5030-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="d5030-1360">seguranca</span></span>
- <span data-ttu-id="d5030-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1361">cód segurança</span></span>
- <span data-ttu-id="d5030-1362">貨至付款 seguranca，segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="d5030-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="d5030-1363">cód seguranca</span></span>
- <span data-ttu-id="d5030-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="d5030-1364">número de verificação</span></span>
- <span data-ttu-id="d5030-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="d5030-1365">numero de verificacao</span></span>
- <span data-ttu-id="d5030-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="d5030-1366">ablauf</span></span>
- <span data-ttu-id="d5030-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="d5030-1367">gültig bis</span></span>
- <span data-ttu-id="d5030-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="d5030-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="d5030-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="d5030-1369">gultig bis</span></span>
- <span data-ttu-id="d5030-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="d5030-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="d5030-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="d5030-1371">scadenza</span></span>
- <span data-ttu-id="d5030-1372">資料 scad</span><span class="sxs-lookup"><span data-stu-id="d5030-1372">data scad</span></span>
- <span data-ttu-id="d5030-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="d5030-1373">fecha de expiracion</span></span>
- <span data-ttu-id="d5030-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="d5030-1374">fecha de venc</span></span>
- <span data-ttu-id="d5030-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="d5030-1375">vencimiento</span></span>
- <span data-ttu-id="d5030-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="d5030-1376">válido hasta</span></span>
- <span data-ttu-id="d5030-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="d5030-1377">valido hasta</span></span>
- <span data-ttu-id="d5030-1378">vto</span><span class="sxs-lookup"><span data-stu-id="d5030-1378">vto</span></span>
- <span data-ttu-id="d5030-1379">資料 de expiração</span><span class="sxs-lookup"><span data-stu-id="d5030-1379">data de expiração</span></span>
- <span data-ttu-id="d5030-1380">資料 de expiracao</span><span class="sxs-lookup"><span data-stu-id="d5030-1380">data de expiracao</span></span>
- <span data-ttu-id="d5030-1381">資料 em mail.que expira</span><span class="sxs-lookup"><span data-stu-id="d5030-1381">data em que expira</span></span>
- <span data-ttu-id="d5030-1382">validade</span><span class="sxs-lookup"><span data-stu-id="d5030-1382">validade</span></span>
- <span data-ttu-id="d5030-1383">勇氣</span><span class="sxs-lookup"><span data-stu-id="d5030-1383">valor</span></span>
- <span data-ttu-id="d5030-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="d5030-1384">vencimento</span></span>
- <span data-ttu-id="d5030-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="d5030-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="d5030-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="d5030-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="d5030-1387">amex</span><span class="sxs-lookup"><span data-stu-id="d5030-1387">amex</span></span>
- <span data-ttu-id="d5030-1388">美洲 express</span><span class="sxs-lookup"><span data-stu-id="d5030-1388">american express</span></span>
- <span data-ttu-id="d5030-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="d5030-1389">americanexpress</span></span>
- <span data-ttu-id="d5030-1390">簽證</span><span class="sxs-lookup"><span data-stu-id="d5030-1390">Visa</span></span>
- <span data-ttu-id="d5030-1391">萬事 達</span><span class="sxs-lookup"><span data-stu-id="d5030-1391">mastercard</span></span>
- <span data-ttu-id="d5030-1392">主卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1392">master card</span></span>
- <span data-ttu-id="d5030-1393">Mc</span><span class="sxs-lookup"><span data-stu-id="d5030-1393">mc</span></span> 
- <span data-ttu-id="d5030-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="d5030-1394">mastercards</span></span>
- <span data-ttu-id="d5030-1395">主卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1395">master cards</span></span>
- <span data-ttu-id="d5030-1396">diner 俱樂部</span><span class="sxs-lookup"><span data-stu-id="d5030-1396">diner's Club</span></span>
- <span data-ttu-id="d5030-1397">diners 俱樂部</span><span class="sxs-lookup"><span data-stu-id="d5030-1397">diners club</span></span>
- <span data-ttu-id="d5030-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="d5030-1398">dinersclub</span></span>
- <span data-ttu-id="d5030-1399">探索卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-1399">discover card</span></span>
- <span data-ttu-id="d5030-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="d5030-1400">discovercard</span></span>
- <span data-ttu-id="d5030-1401">探索卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-1401">discover cards</span></span>
- <span data-ttu-id="d5030-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="d5030-1402">JCB</span></span>
- <span data-ttu-id="d5030-1403">日本卡片局</span><span class="sxs-lookup"><span data-stu-id="d5030-1403">japanese card bureau</span></span>
- <span data-ttu-id="d5030-1404">購買 blanche</span><span class="sxs-lookup"><span data-stu-id="d5030-1404">carte blanche</span></span>
- <span data-ttu-id="d5030-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="d5030-1405">carteblanche</span></span>
- <span data-ttu-id="d5030-1406">信用卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1406">credit card</span></span>
- <span data-ttu-id="d5030-1407">Cc#</span><span class="sxs-lookup"><span data-stu-id="d5030-1407">cc#</span></span>
- <span data-ttu-id="d5030-1408">抄送 #：</span><span class="sxs-lookup"><span data-stu-id="d5030-1408">cc#:</span></span>
- <span data-ttu-id="d5030-1409">有效期</span><span class="sxs-lookup"><span data-stu-id="d5030-1409">expiration date</span></span>
- <span data-ttu-id="d5030-1410">到期日</span><span class="sxs-lookup"><span data-stu-id="d5030-1410">exp date</span></span>
- <span data-ttu-id="d5030-1411">有效期</span><span class="sxs-lookup"><span data-stu-id="d5030-1411">expiry date</span></span>
- <span data-ttu-id="d5030-1412">日期 d'expiration</span><span class="sxs-lookup"><span data-stu-id="d5030-1412">date d’expiration</span></span>
- <span data-ttu-id="d5030-1413">日期 d'exp</span><span class="sxs-lookup"><span data-stu-id="d5030-1413">date d'exp</span></span>
- <span data-ttu-id="d5030-1414">到期日</span><span class="sxs-lookup"><span data-stu-id="d5030-1414">date expiration</span></span>
- <span data-ttu-id="d5030-1415">銀行卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1415">bank card</span></span>
- <span data-ttu-id="d5030-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="d5030-1416">bankcard</span></span>
- <span data-ttu-id="d5030-1417">卡號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1417">card number</span></span>
- <span data-ttu-id="d5030-1418">卡號</span><span class="sxs-lookup"><span data-stu-id="d5030-1418">card num</span></span>
- <span data-ttu-id="d5030-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-1419">cardnumber</span></span>
- <span data-ttu-id="d5030-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="d5030-1420">cardnumbers</span></span>
- <span data-ttu-id="d5030-1421">卡號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1421">card numbers</span></span>
- <span data-ttu-id="d5030-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="d5030-1422">creditcard</span></span>
- <span data-ttu-id="d5030-1423">信用卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1423">credit cards</span></span>
- <span data-ttu-id="d5030-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="d5030-1424">creditcards</span></span>
- <span data-ttu-id="d5030-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="d5030-1425">ccn</span></span>
- <span data-ttu-id="d5030-1426">持卡人</span><span class="sxs-lookup"><span data-stu-id="d5030-1426">card holder</span></span>
- <span data-ttu-id="d5030-1427">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="d5030-1427">cardholder</span></span>
- <span data-ttu-id="d5030-1428">持卡人</span><span class="sxs-lookup"><span data-stu-id="d5030-1428">card holders</span></span>
- <span data-ttu-id="d5030-1429">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="d5030-1429">cardholders</span></span>
- <span data-ttu-id="d5030-1430">檢查卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-1430">check card</span></span>
- <span data-ttu-id="d5030-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="d5030-1431">checkcard</span></span>
- <span data-ttu-id="d5030-1432">檢查卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-1432">check cards</span></span>
- <span data-ttu-id="d5030-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="d5030-1433">checkcards</span></span>
- <span data-ttu-id="d5030-1434">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1434">debit card</span></span>
- <span data-ttu-id="d5030-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="d5030-1435">debitcard</span></span>
- <span data-ttu-id="d5030-1436">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1436">debit cards</span></span>
- <span data-ttu-id="d5030-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="d5030-1437">debitcards</span></span>
- <span data-ttu-id="d5030-1438">atm 卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1438">atm card</span></span>
- <span data-ttu-id="d5030-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="d5030-1439">atmcard</span></span>
- <span data-ttu-id="d5030-1440">atm 卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1440">atm cards</span></span>
- <span data-ttu-id="d5030-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="d5030-1441">atmcards</span></span>
- <span data-ttu-id="d5030-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="d5030-1442">enroute</span></span>
- <span data-ttu-id="d5030-1443">途中</span><span class="sxs-lookup"><span data-stu-id="d5030-1443">en route</span></span>
- <span data-ttu-id="d5030-1444">卡片類型</span><span class="sxs-lookup"><span data-stu-id="d5030-1444">card type</span></span>
- <span data-ttu-id="d5030-1445">購買 bancaire</span><span class="sxs-lookup"><span data-stu-id="d5030-1445">carte bancaire</span></span>
- <span data-ttu-id="d5030-1446">反 crédit</span><span class="sxs-lookup"><span data-stu-id="d5030-1446">carte de crédit</span></span>
- <span data-ttu-id="d5030-1447">購買退款</span><span class="sxs-lookup"><span data-stu-id="d5030-1447">carte de credit</span></span>
- <span data-ttu-id="d5030-1448">numéro 的重複購買</span><span class="sxs-lookup"><span data-stu-id="d5030-1448">numéro de carte</span></span>
- <span data-ttu-id="d5030-1449">numero 的重複購買</span><span class="sxs-lookup"><span data-stu-id="d5030-1449">numero de carte</span></span>
- <span data-ttu-id="d5030-1450">de 照購買</span><span class="sxs-lookup"><span data-stu-id="d5030-1450">nº de la carte</span></span>
- <span data-ttu-id="d5030-1451">消除購買的 n º</span><span class="sxs-lookup"><span data-stu-id="d5030-1451">nº de carte</span></span>
- <span data-ttu-id="d5030-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="d5030-1452">kreditkarte</span></span>
- <span data-ttu-id="d5030-1453">karte</span><span class="sxs-lookup"><span data-stu-id="d5030-1453">karte</span></span>
- <span data-ttu-id="d5030-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="d5030-1454">karteninhaber</span></span>
- <span data-ttu-id="d5030-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="d5030-1455">karteninhabers</span></span>
- <span data-ttu-id="d5030-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="d5030-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="d5030-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="d5030-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="d5030-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="d5030-1458">kreditkartentyp</span></span>
- <span data-ttu-id="d5030-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="d5030-1459">eigentümername</span></span>
- <span data-ttu-id="d5030-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="d5030-1460">kartennr</span></span> 
- <span data-ttu-id="d5030-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1461">kartennummer</span></span>
- <span data-ttu-id="d5030-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1462">kreditkartennummer</span></span>
- <span data-ttu-id="d5030-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="d5030-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1464">carta di credito</span></span>
- <span data-ttu-id="d5030-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1465">carta credito</span></span>
- <span data-ttu-id="d5030-1466">憲章</span><span class="sxs-lookup"><span data-stu-id="d5030-1466">carta</span></span>
- <span data-ttu-id="d5030-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="d5030-1467">n carta</span></span>
- <span data-ttu-id="d5030-1468">星期日。</span><span class="sxs-lookup"><span data-stu-id="d5030-1468">nr.</span></span> <span data-ttu-id="d5030-1469">憲章</span><span class="sxs-lookup"><span data-stu-id="d5030-1469">carta</span></span>
- <span data-ttu-id="d5030-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="d5030-1470">nr carta</span></span>
- <span data-ttu-id="d5030-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="d5030-1471">numero carta</span></span>
- <span data-ttu-id="d5030-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="d5030-1472">numero della carta</span></span>
- <span data-ttu-id="d5030-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="d5030-1473">numero di carta</span></span>
- <span data-ttu-id="d5030-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1474">tarjeta credito</span></span>
- <span data-ttu-id="d5030-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1475">tarjeta de credito</span></span>
- <span data-ttu-id="d5030-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="d5030-1476">tarjeta crédito</span></span>
- <span data-ttu-id="d5030-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="d5030-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="d5030-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="d5030-1478">tarjeta de atm</span></span>
- <span data-ttu-id="d5030-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="d5030-1479">tarjeta atm</span></span>
- <span data-ttu-id="d5030-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="d5030-1480">tarjeta debito</span></span>
- <span data-ttu-id="d5030-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="d5030-1481">tarjeta de debito</span></span>
- <span data-ttu-id="d5030-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="d5030-1482">tarjeta débito</span></span>
- <span data-ttu-id="d5030-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="d5030-1483">tarjeta de débito</span></span>
- <span data-ttu-id="d5030-1484">消除 tarjeta 的 n º</span><span class="sxs-lookup"><span data-stu-id="d5030-1484">nº de tarjeta</span></span>
- <span data-ttu-id="d5030-1485">不。</span><span class="sxs-lookup"><span data-stu-id="d5030-1485">no.</span></span> <span data-ttu-id="d5030-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d5030-1486">de tarjeta</span></span>
- <span data-ttu-id="d5030-1487">無 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d5030-1487">no de tarjeta</span></span>
- <span data-ttu-id="d5030-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d5030-1488">numero de tarjeta</span></span>
- <span data-ttu-id="d5030-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d5030-1489">número de tarjeta</span></span>
- <span data-ttu-id="d5030-1490">tarjeta 否</span><span class="sxs-lookup"><span data-stu-id="d5030-1490">tarjeta no</span></span>
- <span data-ttu-id="d5030-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="d5030-1491">tarjetahabiente</span></span>
- <span data-ttu-id="d5030-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="d5030-1492">cartão de crédito</span></span>
- <span data-ttu-id="d5030-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1493">cartão de credito</span></span>
- <span data-ttu-id="d5030-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="d5030-1494">cartao de crédito</span></span>
- <span data-ttu-id="d5030-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1495">cartao de credito</span></span>
- <span data-ttu-id="d5030-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="d5030-1496">cartão de débito</span></span>
- <span data-ttu-id="d5030-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="d5030-1497">cartao de débito</span></span>
- <span data-ttu-id="d5030-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="d5030-1498">cartão de debito</span></span>
- <span data-ttu-id="d5030-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="d5030-1499">cartao de debito</span></span>
- <span data-ttu-id="d5030-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="d5030-1500">débito automático</span></span>
- <span data-ttu-id="d5030-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="d5030-1501">debito automatico</span></span>
- <span data-ttu-id="d5030-1502">número 執行 cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1502">número do cartão</span></span>
- <span data-ttu-id="d5030-1503">numero 執行 cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1503">numero do cartão</span></span> 
- <span data-ttu-id="d5030-1504">número 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1504">número do cartao</span></span>
- <span data-ttu-id="d5030-1505">numero 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1505">numero do cartao</span></span>
- <span data-ttu-id="d5030-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1506">número de cartão</span></span>
- <span data-ttu-id="d5030-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1507">numero de cartão</span></span>
- <span data-ttu-id="d5030-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1508">número de cartao</span></span>
- <span data-ttu-id="d5030-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1509">numero de cartao</span></span>
- <span data-ttu-id="d5030-1510">n º do cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1510">nº do cartão</span></span>
- <span data-ttu-id="d5030-1511">n º do cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1511">nº do cartao</span></span>
- <span data-ttu-id="d5030-1512">n º。</span><span class="sxs-lookup"><span data-stu-id="d5030-1512">nº.</span></span> <span data-ttu-id="d5030-1513">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1513">do cartão</span></span>
- <span data-ttu-id="d5030-1514">無 do cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1514">no do cartão</span></span>
- <span data-ttu-id="d5030-1515">無 do cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1515">no do cartao</span></span>
- <span data-ttu-id="d5030-1516">不。</span><span class="sxs-lookup"><span data-stu-id="d5030-1516">no.</span></span> <span data-ttu-id="d5030-1517">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1517">do cartão</span></span>
- <span data-ttu-id="d5030-1518">不。</span><span class="sxs-lookup"><span data-stu-id="d5030-1518">no.</span></span> <span data-ttu-id="d5030-1519">執行 cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="d5030-1520">克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1521">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1521">Format</span></span>

<span data-ttu-id="d5030-1522">九位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1523">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1523">Pattern</span></span>

<span data-ttu-id="d5030-1524">九個連續數位</span><span class="sxs-lookup"><span data-stu-id="d5030-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1525">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1525">Checksum</span></span>

<span data-ttu-id="d5030-1526">否</span><span class="sxs-lookup"><span data-stu-id="d5030-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1527">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1527">Definition</span></span>

<span data-ttu-id="d5030-1528">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1529">函數 Func_croatia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1530">會找到來自 Keyword_croatia_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-1531">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="d5030-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="d5030-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="d5030-1533">克羅地亞身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1533">Croatian identity card</span></span>
- <span data-ttu-id="d5030-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="d5030-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="d5030-1535">克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1536">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1536">Format</span></span>

<span data-ttu-id="d5030-1537">11位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1538">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1538">Pattern</span></span>

<span data-ttu-id="d5030-1539">11位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-1539">11 digits:</span></span>
- <span data-ttu-id="d5030-1540">10位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1540">10 digits</span></span> 
- <span data-ttu-id="d5030-1541">最後一個數位是檢查碼用於國際資料交換的目的，在11位數之前新增字母「HR」。</span><span class="sxs-lookup"><span data-stu-id="d5030-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1542">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1542">Checksum</span></span>

<span data-ttu-id="d5030-1543">是</span><span class="sxs-lookup"><span data-stu-id="d5030-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1544">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1544">Definition</span></span>

<span data-ttu-id="d5030-1545">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1546">函數 Func_croatia_oib_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1547">會找到來自 Keyword_croatia_oib_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="d5030-1548">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1548">The checksum passes.</span></span>

<span data-ttu-id="d5030-1549">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1550">函數 Func_croatia_oib_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1551">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-1552">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="d5030-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="d5030-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="d5030-1554">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1554">Personal Identification Number</span></span>
- <span data-ttu-id="d5030-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="d5030-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="d5030-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="d5030-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="d5030-1557">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1558">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1558">Format</span></span>

<span data-ttu-id="d5030-1559">具有選用正斜線的九位數（舊格式）10位數（選用反斜線（新格式））</span><span class="sxs-lookup"><span data-stu-id="d5030-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1560">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1560">Pattern</span></span>

<span data-ttu-id="d5030-1561">九位數（舊格式）：</span><span class="sxs-lookup"><span data-stu-id="d5030-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="d5030-1562">九位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1562">Nine digits</span></span>

<span data-ttu-id="d5030-1563">OR</span><span class="sxs-lookup"><span data-stu-id="d5030-1563">OR</span></span>

- <span data-ttu-id="d5030-1564">六位數代表出生日期</span><span class="sxs-lookup"><span data-stu-id="d5030-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="d5030-1565">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="d5030-1565">A forward slash</span></span>
- <span data-ttu-id="d5030-1566">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1566">Three digits</span></span>

<span data-ttu-id="d5030-1567">10位數（新格式）：</span><span class="sxs-lookup"><span data-stu-id="d5030-1567">10 digits (new format):</span></span>
- <span data-ttu-id="d5030-1568">10位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1568">10 digits</span></span>

<span data-ttu-id="d5030-1569">OR</span><span class="sxs-lookup"><span data-stu-id="d5030-1569">OR</span></span>

- <span data-ttu-id="d5030-1570">六位數代表出生日期</span><span class="sxs-lookup"><span data-stu-id="d5030-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="d5030-1571">一個正斜線</span><span class="sxs-lookup"><span data-stu-id="d5030-1571">A forward slash</span></span> 
- <span data-ttu-id="d5030-1572">最後一個數位是檢查碼的四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1573">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1573">Checksum</span></span>

<span data-ttu-id="d5030-1574">是</span><span class="sxs-lookup"><span data-stu-id="d5030-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1575">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1575">Definition</span></span>

<span data-ttu-id="d5030-1576">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：函數 Func_czech_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="d5030-1577">會找到來自 Keyword_czech_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="d5030-1578">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="d5030-1579">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1579">Keywords</span></span>

- <span data-ttu-id="d5030-1580">捷克個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1580">czech personal identity number</span></span>
- <span data-ttu-id="d5030-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="d5030-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="d5030-1582">丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1583">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1583">Format</span></span>

<span data-ttu-id="d5030-1584">10位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1585">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1585">Pattern</span></span>

<span data-ttu-id="d5030-1586">10位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-1586">10 digits:</span></span>
- <span data-ttu-id="d5030-1587">DDMMYY 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="d5030-1588">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-1588">A hyphen</span></span> 
- <span data-ttu-id="d5030-1589">四位數的最後一個數位是檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1590">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1590">Checksum</span></span>

<span data-ttu-id="d5030-1591">是</span><span class="sxs-lookup"><span data-stu-id="d5030-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1592">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1592">Definition</span></span>

<span data-ttu-id="d5030-1593">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：正則運算式 Regex_denmark_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="d5030-1594">會找到來自 Keyword_denmark_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="d5030-1595">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-1596">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="d5030-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="d5030-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="d5030-1598">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1598">Personal Identification Number</span></span>
- <span data-ttu-id="d5030-1599">Cpr</span><span class="sxs-lookup"><span data-stu-id="d5030-1599">CPR</span></span>
- <span data-ttu-id="d5030-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="d5030-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="d5030-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="d5030-1602">藥品強制代理人（DEA）號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1603">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1603">Format</span></span>

<span data-ttu-id="d5030-1604">兩個字母后接7位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1605">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1605">Pattern</span></span>

<span data-ttu-id="d5030-1606">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="d5030-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="d5030-1607">這組可能字母的一個字母（不區分大小寫）： abcdefghjklmnprstux，也就是報名者程式碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="d5030-1608">一個字母（不區分大小寫），這是報名者姓氏的第一個字母</span><span class="sxs-lookup"><span data-stu-id="d5030-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="d5030-1609">七位數，最後一個是檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1610">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1610">Checksum</span></span>

<span data-ttu-id="d5030-1611">是</span><span class="sxs-lookup"><span data-stu-id="d5030-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1612">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1612">Definition</span></span>

<span data-ttu-id="d5030-1613">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1614">函數 Func_dea_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1615">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-1616">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1616">Keywords</span></span>

<span data-ttu-id="d5030-1617">無</span><span class="sxs-lookup"><span data-stu-id="d5030-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="d5030-1618">歐盟轉帳卡號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1619">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1619">Format</span></span>

<span data-ttu-id="d5030-1620">16位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1621">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1621">Pattern</span></span>

<span data-ttu-id="d5030-1622">非常複雜且健全的模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1623">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1623">Checksum</span></span>

<span data-ttu-id="d5030-1624">是</span><span class="sxs-lookup"><span data-stu-id="d5030-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1625">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1625">Definition</span></span>

<span data-ttu-id="d5030-1626">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1627">函數 Func_eu_debit_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1628">下列專案中至少有一個為真：</span><span class="sxs-lookup"><span data-stu-id="d5030-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="d5030-1629">會找到來自 Keyword_eu_debit_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="d5030-1630">會找到來自 Keyword_card_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="d5030-1631">會找到來自 Keyword_card_security_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="d5030-1632">會找到來自 Keyword_card_expiration_terms_dict 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="d5030-1633">函數 Func_expiration_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d5030-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d5030-1634">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-1635">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="d5030-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="d5030-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="d5030-1637">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1637">account number</span></span> 
- <span data-ttu-id="d5030-1638">卡號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1638">card number</span></span> 
- <span data-ttu-id="d5030-1639">卡片編號</span><span class="sxs-lookup"><span data-stu-id="d5030-1639">card no.</span></span> 
- <span data-ttu-id="d5030-1640">安全性號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1640">security number</span></span> 
- <span data-ttu-id="d5030-1641">Cc#</span><span class="sxs-lookup"><span data-stu-id="d5030-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="d5030-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="d5030-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="d5030-1643">帳戶 nbr</span><span class="sxs-lookup"><span data-stu-id="d5030-1643">acct nbr</span></span> 
- <span data-ttu-id="d5030-1644">帳戶號</span><span class="sxs-lookup"><span data-stu-id="d5030-1644">acct num</span></span> 
- <span data-ttu-id="d5030-1645">帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-1645">acct no</span></span> 
- <span data-ttu-id="d5030-1646">美洲 express</span><span class="sxs-lookup"><span data-stu-id="d5030-1646">american express</span></span> 
- <span data-ttu-id="d5030-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="d5030-1647">americanexpress</span></span> 
- <span data-ttu-id="d5030-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="d5030-1648">americano espresso</span></span> 
- <span data-ttu-id="d5030-1649">amex</span><span class="sxs-lookup"><span data-stu-id="d5030-1649">amex</span></span> 
- <span data-ttu-id="d5030-1650">atm 卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1650">atm card</span></span> 
- <span data-ttu-id="d5030-1651">atm 卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1651">atm cards</span></span> 
- <span data-ttu-id="d5030-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="d5030-1652">atm kaart</span></span> 
- <span data-ttu-id="d5030-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="d5030-1653">atmcard</span></span> 
- <span data-ttu-id="d5030-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="d5030-1654">atmcards</span></span> 
- <span data-ttu-id="d5030-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="d5030-1655">atmkaart</span></span> 
- <span data-ttu-id="d5030-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="d5030-1656">atmkaarten</span></span> 
- <span data-ttu-id="d5030-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="d5030-1657">bancontact</span></span> 
- <span data-ttu-id="d5030-1658">銀行卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1658">bank card</span></span> 
- <span data-ttu-id="d5030-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="d5030-1659">bankkaart</span></span> 
- <span data-ttu-id="d5030-1660">持卡人</span><span class="sxs-lookup"><span data-stu-id="d5030-1660">card holder</span></span> 
- <span data-ttu-id="d5030-1661">持卡人</span><span class="sxs-lookup"><span data-stu-id="d5030-1661">card holders</span></span> 
- <span data-ttu-id="d5030-1662">卡號</span><span class="sxs-lookup"><span data-stu-id="d5030-1662">card num</span></span> 
- <span data-ttu-id="d5030-1663">卡號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1663">card number</span></span> 
- <span data-ttu-id="d5030-1664">卡號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1664">card numbers</span></span> 
- <span data-ttu-id="d5030-1665">卡片類型</span><span class="sxs-lookup"><span data-stu-id="d5030-1665">card type</span></span> 
- <span data-ttu-id="d5030-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="d5030-1666">cardano numerico</span></span> 
- <span data-ttu-id="d5030-1667">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="d5030-1667">cardholder</span></span> 
- <span data-ttu-id="d5030-1668">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="d5030-1668">cardholders</span></span> 
- <span data-ttu-id="d5030-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-1669">cardnumber</span></span> 
- <span data-ttu-id="d5030-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="d5030-1670">cardnumbers</span></span> 
- <span data-ttu-id="d5030-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="d5030-1671">carta bianca</span></span> 
- <span data-ttu-id="d5030-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1672">carta credito</span></span> 
- <span data-ttu-id="d5030-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1673">carta di credito</span></span> 
- <span data-ttu-id="d5030-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1674">cartao de credito</span></span> 
- <span data-ttu-id="d5030-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="d5030-1675">cartao de crédito</span></span> 
- <span data-ttu-id="d5030-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="d5030-1676">cartao de debito</span></span> 
- <span data-ttu-id="d5030-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="d5030-1677">cartao de débito</span></span> 
- <span data-ttu-id="d5030-1678">購買 bancaire</span><span class="sxs-lookup"><span data-stu-id="d5030-1678">carte bancaire</span></span> 
- <span data-ttu-id="d5030-1679">購買 blanche</span><span class="sxs-lookup"><span data-stu-id="d5030-1679">carte blanche</span></span> 
- <span data-ttu-id="d5030-1680">購買 bleue</span><span class="sxs-lookup"><span data-stu-id="d5030-1680">carte bleue</span></span> 
- <span data-ttu-id="d5030-1681">購買退款</span><span class="sxs-lookup"><span data-stu-id="d5030-1681">carte de credit</span></span> 
- <span data-ttu-id="d5030-1682">反 crédit</span><span class="sxs-lookup"><span data-stu-id="d5030-1682">carte de crédit</span></span> 
- <span data-ttu-id="d5030-1683">購買 di credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1683">carte di credito</span></span> 
- <span data-ttu-id="d5030-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="d5030-1684">carteblanche</span></span> 
- <span data-ttu-id="d5030-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1685">cartão de credito</span></span> 
- <span data-ttu-id="d5030-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="d5030-1686">cartão de crédito</span></span> 
- <span data-ttu-id="d5030-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="d5030-1687">cartão de debito</span></span> 
- <span data-ttu-id="d5030-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="d5030-1688">cartão de débito</span></span> 
- <span data-ttu-id="d5030-1689">cb</span><span class="sxs-lookup"><span data-stu-id="d5030-1689">cb</span></span> 
- <span data-ttu-id="d5030-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="d5030-1690">ccn</span></span> 
- <span data-ttu-id="d5030-1691">檢查卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-1691">check card</span></span> 
- <span data-ttu-id="d5030-1692">檢查卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-1692">check cards</span></span> 
- <span data-ttu-id="d5030-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="d5030-1693">checkcard</span></span>
- <span data-ttu-id="d5030-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="d5030-1694">checkcards</span></span> 
- <span data-ttu-id="d5030-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="d5030-1695">chequekaart</span></span> 
- <span data-ttu-id="d5030-1696">卷雲</span><span class="sxs-lookup"><span data-stu-id="d5030-1696">cirrus</span></span> 
- <span data-ttu-id="d5030-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="d5030-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="d5030-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="d5030-1698">controlekaart</span></span> 
- <span data-ttu-id="d5030-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="d5030-1699">controlekaarten</span></span> 
- <span data-ttu-id="d5030-1700">信用卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1700">credit card</span></span> 
- <span data-ttu-id="d5030-1701">信用卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1701">credit cards</span></span> 
- <span data-ttu-id="d5030-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="d5030-1702">creditcard</span></span> 
- <span data-ttu-id="d5030-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="d5030-1703">creditcards</span></span> 
- <span data-ttu-id="d5030-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="d5030-1704">debetkaart</span></span> 
- <span data-ttu-id="d5030-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="d5030-1705">debetkaarten</span></span> 
- <span data-ttu-id="d5030-1706">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1706">debit card</span></span> 
- <span data-ttu-id="d5030-1707">轉帳卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1707">debit cards</span></span> 
- <span data-ttu-id="d5030-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="d5030-1708">debitcard</span></span> 
- <span data-ttu-id="d5030-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="d5030-1709">debitcards</span></span> 
- <span data-ttu-id="d5030-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="d5030-1710">debito automatico</span></span> 
- <span data-ttu-id="d5030-1711">diners 俱樂部</span><span class="sxs-lookup"><span data-stu-id="d5030-1711">diners club</span></span> 
- <span data-ttu-id="d5030-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="d5030-1712">dinersclub</span></span> 
- <span data-ttu-id="d5030-1713">發現</span><span class="sxs-lookup"><span data-stu-id="d5030-1713">discover</span></span> 
- <span data-ttu-id="d5030-1714">探索卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-1714">discover card</span></span> 
- <span data-ttu-id="d5030-1715">探索卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-1715">discover cards</span></span> 
- <span data-ttu-id="d5030-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="d5030-1716">discovercard</span></span> 
- <span data-ttu-id="d5030-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="d5030-1717">discovercards</span></span> 
- <span data-ttu-id="d5030-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="d5030-1718">débito automático</span></span>
- <span data-ttu-id="d5030-1719">edc</span><span class="sxs-lookup"><span data-stu-id="d5030-1719">edc</span></span> 
- <span data-ttu-id="d5030-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="d5030-1720">eigentümername</span></span> 
- <span data-ttu-id="d5030-1721">歐洲借貸卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1721">european debit card</span></span> 
- <span data-ttu-id="d5030-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="d5030-1722">hoofdkaart</span></span> 
- <span data-ttu-id="d5030-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="d5030-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="d5030-1724">在 viaggio</span><span class="sxs-lookup"><span data-stu-id="d5030-1724">in viaggio</span></span> 
- <span data-ttu-id="d5030-1725">日本卡片局</span><span class="sxs-lookup"><span data-stu-id="d5030-1725">japanese card bureau</span></span> 
- <span data-ttu-id="d5030-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="d5030-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="d5030-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="d5030-1727">jcb</span></span> 
- <span data-ttu-id="d5030-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="d5030-1728">kaart</span></span> 
- <span data-ttu-id="d5030-1729">kaart 編號</span><span class="sxs-lookup"><span data-stu-id="d5030-1729">kaart num</span></span> 
- <span data-ttu-id="d5030-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="d5030-1730">kaartaantal</span></span> 
- <span data-ttu-id="d5030-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="d5030-1731">kaartaantallen</span></span> 
- <span data-ttu-id="d5030-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="d5030-1732">kaarthouder</span></span> 
- <span data-ttu-id="d5030-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="d5030-1733">kaarthouders</span></span> 
- <span data-ttu-id="d5030-1734">karte</span><span class="sxs-lookup"><span data-stu-id="d5030-1734">karte</span></span>  
- <span data-ttu-id="d5030-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="d5030-1735">karteninhaber</span></span> 
- <span data-ttu-id="d5030-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="d5030-1736">karteninhabers</span></span>
- <span data-ttu-id="d5030-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="d5030-1737">kartennr</span></span> 
- <span data-ttu-id="d5030-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1738">kartennummer</span></span> 
- <span data-ttu-id="d5030-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="d5030-1739">kreditkarte</span></span> 
- <span data-ttu-id="d5030-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="d5030-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="d5030-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="d5030-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="d5030-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="d5030-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="d5030-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="d5030-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="d5030-1745">大師</span><span class="sxs-lookup"><span data-stu-id="d5030-1745">maestro</span></span> 
- <span data-ttu-id="d5030-1746">主卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1746">master card</span></span> 
- <span data-ttu-id="d5030-1747">主卡</span><span class="sxs-lookup"><span data-stu-id="d5030-1747">master cards</span></span> 
- <span data-ttu-id="d5030-1748">萬事 達</span><span class="sxs-lookup"><span data-stu-id="d5030-1748">mastercard</span></span> 
- <span data-ttu-id="d5030-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="d5030-1749">mastercards</span></span> 
- <span data-ttu-id="d5030-1750">Mc</span><span class="sxs-lookup"><span data-stu-id="d5030-1750">mc</span></span> 
- <span data-ttu-id="d5030-1751">mister 現金</span><span class="sxs-lookup"><span data-stu-id="d5030-1751">mister cash</span></span> 
- <span data-ttu-id="d5030-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="d5030-1752">n carta</span></span> 
- <span data-ttu-id="d5030-1753">憲章</span><span class="sxs-lookup"><span data-stu-id="d5030-1753">carta</span></span> 
- <span data-ttu-id="d5030-1754">無 de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d5030-1754">no de tarjeta</span></span> 
- <span data-ttu-id="d5030-1755">無 do cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1755">no do cartao</span></span> 
- <span data-ttu-id="d5030-1756">無 do cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1756">no do cartão</span></span> 
- <span data-ttu-id="d5030-1757">不。</span><span class="sxs-lookup"><span data-stu-id="d5030-1757">no.</span></span> <span data-ttu-id="d5030-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d5030-1758">de tarjeta</span></span> 
- <span data-ttu-id="d5030-1759">不。</span><span class="sxs-lookup"><span data-stu-id="d5030-1759">no.</span></span> <span data-ttu-id="d5030-1760">執行 cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1760">do cartao</span></span> 
- <span data-ttu-id="d5030-1761">不。</span><span class="sxs-lookup"><span data-stu-id="d5030-1761">no.</span></span> <span data-ttu-id="d5030-1762">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1762">do cartão</span></span> 
- <span data-ttu-id="d5030-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="d5030-1763">nr carta</span></span> 
- <span data-ttu-id="d5030-1764">星期日。</span><span class="sxs-lookup"><span data-stu-id="d5030-1764">nr.</span></span> <span data-ttu-id="d5030-1765">憲章</span><span class="sxs-lookup"><span data-stu-id="d5030-1765">carta</span></span> 
- <span data-ttu-id="d5030-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="d5030-1766">numeri di scheda</span></span> 
- <span data-ttu-id="d5030-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="d5030-1767">numero carta</span></span> 
- <span data-ttu-id="d5030-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1768">numero de cartao</span></span> 
- <span data-ttu-id="d5030-1769">numero 的重複購買</span><span class="sxs-lookup"><span data-stu-id="d5030-1769">numero de carte</span></span> 
- <span data-ttu-id="d5030-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1770">numero de cartão</span></span> 
- <span data-ttu-id="d5030-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d5030-1771">numero de tarjeta</span></span>
- <span data-ttu-id="d5030-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="d5030-1772">numero della carta</span></span> 
- <span data-ttu-id="d5030-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="d5030-1773">numero di carta</span></span> 
- <span data-ttu-id="d5030-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="d5030-1774">numero di scheda</span></span> 
- <span data-ttu-id="d5030-1775">numero 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1775">numero do cartao</span></span> 
- <span data-ttu-id="d5030-1776">numero 執行 cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1776">numero do cartão</span></span> 
- <span data-ttu-id="d5030-1777">numéro 的重複購買</span><span class="sxs-lookup"><span data-stu-id="d5030-1777">numéro de carte</span></span> 
- <span data-ttu-id="d5030-1778">n º carta</span><span class="sxs-lookup"><span data-stu-id="d5030-1778">nº carta</span></span> 
- <span data-ttu-id="d5030-1779">消除購買的 n º</span><span class="sxs-lookup"><span data-stu-id="d5030-1779">nº de carte</span></span> 
- <span data-ttu-id="d5030-1780">de 照購買</span><span class="sxs-lookup"><span data-stu-id="d5030-1780">nº de la carte</span></span> 
- <span data-ttu-id="d5030-1781">消除 tarjeta 的 n º</span><span class="sxs-lookup"><span data-stu-id="d5030-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="d5030-1782">n º do cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1782">nº do cartao</span></span> 
- <span data-ttu-id="d5030-1783">n º do cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1783">nº do cartão</span></span> 
- <span data-ttu-id="d5030-1784">n º。</span><span class="sxs-lookup"><span data-stu-id="d5030-1784">nº.</span></span> <span data-ttu-id="d5030-1785">執行 cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1785">do cartão</span></span> 
- <span data-ttu-id="d5030-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1786">número de cartao</span></span> 
- <span data-ttu-id="d5030-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="d5030-1787">número de cartão</span></span> 
- <span data-ttu-id="d5030-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="d5030-1788">número de tarjeta</span></span> 
- <span data-ttu-id="d5030-1789">número 執行 cartao</span><span class="sxs-lookup"><span data-stu-id="d5030-1789">número do cartao</span></span> 
- <span data-ttu-id="d5030-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="d5030-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="d5030-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="d5030-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="d5030-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="d5030-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="d5030-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="d5030-1793">scheda della banca</span></span> 
- <span data-ttu-id="d5030-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="d5030-1794">scheda di controllo</span></span> 
- <span data-ttu-id="d5030-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="d5030-1795">scheda di debito</span></span> 
- <span data-ttu-id="d5030-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="d5030-1796">scheda matrice</span></span> 
- <span data-ttu-id="d5030-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="d5030-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="d5030-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="d5030-1798">schede di controllo</span></span> 
- <span data-ttu-id="d5030-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="d5030-1799">schede di debito</span></span> 
- <span data-ttu-id="d5030-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="d5030-1800">schede matrici</span></span> 
- <span data-ttu-id="d5030-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="d5030-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="d5030-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="d5030-1802">scoprono le schede</span></span> 
- <span data-ttu-id="d5030-1803">獨奏</span><span class="sxs-lookup"><span data-stu-id="d5030-1803">solo</span></span> 
- <span data-ttu-id="d5030-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="d5030-1804">supporti di scheda</span></span> 
- <span data-ttu-id="d5030-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="d5030-1805">supporto di scheda</span></span> 
- <span data-ttu-id="d5030-1806">開關</span><span class="sxs-lookup"><span data-stu-id="d5030-1806">switch</span></span> 
- <span data-ttu-id="d5030-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="d5030-1807">tarjeta atm</span></span> 
- <span data-ttu-id="d5030-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1808">tarjeta credito</span></span> 
- <span data-ttu-id="d5030-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="d5030-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="d5030-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="d5030-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="d5030-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="d5030-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="d5030-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="d5030-1812">tarjeta debito</span></span> 
- <span data-ttu-id="d5030-1813">tarjeta 否</span><span class="sxs-lookup"><span data-stu-id="d5030-1813">tarjeta no</span></span>
- <span data-ttu-id="d5030-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="d5030-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="d5030-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="d5030-1815">tipo della scheda</span></span> 
- <span data-ttu-id="d5030-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="d5030-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="d5030-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="d5030-1817">scheda</span></span> 
- <span data-ttu-id="d5030-1818">v 支付</span><span class="sxs-lookup"><span data-stu-id="d5030-1818">v pay</span></span> 
- <span data-ttu-id="d5030-1819">v-支付</span><span class="sxs-lookup"><span data-stu-id="d5030-1819">v-pay</span></span> 
- <span data-ttu-id="d5030-1820">簽證</span><span class="sxs-lookup"><span data-stu-id="d5030-1820">visa</span></span> 
- <span data-ttu-id="d5030-1821">簽證加</span><span class="sxs-lookup"><span data-stu-id="d5030-1821">visa plus</span></span> 
- <span data-ttu-id="d5030-1822">簽證電</span><span class="sxs-lookup"><span data-stu-id="d5030-1822">visa electron</span></span> 
- <span data-ttu-id="d5030-1823">visto</span><span class="sxs-lookup"><span data-stu-id="d5030-1823">visto</span></span> 
- <span data-ttu-id="d5030-1824">visum</span><span class="sxs-lookup"><span data-stu-id="d5030-1824">visum</span></span> 
- <span data-ttu-id="d5030-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="d5030-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="d5030-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="d5030-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="d5030-1827">卡片識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1827">card identification number</span></span>
- <span data-ttu-id="d5030-1828">名片驗證</span><span class="sxs-lookup"><span data-stu-id="d5030-1828">card verification</span></span> 
- <span data-ttu-id="d5030-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="d5030-1829">cardi la verifica</span></span> 
- <span data-ttu-id="d5030-1830">cid</span><span class="sxs-lookup"><span data-stu-id="d5030-1830">cid</span></span> 
- <span data-ttu-id="d5030-1831">貨至 seg</span><span class="sxs-lookup"><span data-stu-id="d5030-1831">cod seg</span></span> 
- <span data-ttu-id="d5030-1832">貨至 seguranca</span><span class="sxs-lookup"><span data-stu-id="d5030-1832">cod seguranca</span></span> 
- <span data-ttu-id="d5030-1833">貨至 segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1833">cod segurança</span></span> 
- <span data-ttu-id="d5030-1834">貨至 sicurezza</span><span class="sxs-lookup"><span data-stu-id="d5030-1834">cod sicurezza</span></span> 
- <span data-ttu-id="d5030-1835">Cod。</span><span class="sxs-lookup"><span data-stu-id="d5030-1835">cod.</span></span> <span data-ttu-id="d5030-1836">Seg</span><span class="sxs-lookup"><span data-stu-id="d5030-1836">seg</span></span> 
- <span data-ttu-id="d5030-1837">Cod。</span><span class="sxs-lookup"><span data-stu-id="d5030-1837">cod.</span></span> <span data-ttu-id="d5030-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="d5030-1838">seguranca</span></span> 
- <span data-ttu-id="d5030-1839">Cod。</span><span class="sxs-lookup"><span data-stu-id="d5030-1839">cod.</span></span> <span data-ttu-id="d5030-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1840">segurança</span></span> 
- <span data-ttu-id="d5030-1841">Cod。</span><span class="sxs-lookup"><span data-stu-id="d5030-1841">cod.</span></span> <span data-ttu-id="d5030-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="d5030-1842">sicurezza</span></span> 
- <span data-ttu-id="d5030-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d5030-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="d5030-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="d5030-1844">codice di verifica</span></span> 
- <span data-ttu-id="d5030-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="d5030-1845">codigo</span></span> 
- <span data-ttu-id="d5030-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="d5030-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="d5030-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1847">codigo de segurança</span></span> 
- <span data-ttu-id="d5030-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="d5030-1848">crittogramma</span></span> 
- <span data-ttu-id="d5030-1849">密碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1849">cryptogram</span></span> 
- <span data-ttu-id="d5030-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="d5030-1850">cryptogramme</span></span> 
- <span data-ttu-id="d5030-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="d5030-1851">cv2</span></span> 
- <span data-ttu-id="d5030-1852">Cvc</span><span class="sxs-lookup"><span data-stu-id="d5030-1852">cvc</span></span> 
- <span data-ttu-id="d5030-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="d5030-1853">cvc2</span></span> 
- <span data-ttu-id="d5030-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="d5030-1854">cvn</span></span> 
- <span data-ttu-id="d5030-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="d5030-1855">cvv</span></span> 
- <span data-ttu-id="d5030-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="d5030-1856">cvv2</span></span> 
- <span data-ttu-id="d5030-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="d5030-1857">cód seguranca</span></span> 
- <span data-ttu-id="d5030-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1858">cód segurança</span></span> 
- <span data-ttu-id="d5030-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="d5030-1859">cód.</span></span> <span data-ttu-id="d5030-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="d5030-1860">seguranca</span></span> 
- <span data-ttu-id="d5030-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="d5030-1861">cód.</span></span> <span data-ttu-id="d5030-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1862">segurança</span></span> 
- <span data-ttu-id="d5030-1863">código</span><span class="sxs-lookup"><span data-stu-id="d5030-1863">código</span></span> 
- <span data-ttu-id="d5030-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="d5030-1864">código de seguranca</span></span> 
- <span data-ttu-id="d5030-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="d5030-1865">código de segurança</span></span> 
- <span data-ttu-id="d5030-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="d5030-1866">de kaart controle</span></span> 
- <span data-ttu-id="d5030-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="d5030-1867">geeft nr uit</span></span> 
- <span data-ttu-id="d5030-1868">問題否</span><span class="sxs-lookup"><span data-stu-id="d5030-1868">issue no</span></span> 
- <span data-ttu-id="d5030-1869">發行編號</span><span class="sxs-lookup"><span data-stu-id="d5030-1869">issue number</span></span> 
- <span data-ttu-id="d5030-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="d5030-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="d5030-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="d5030-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="d5030-1873">kwestieaantal</span></span> 
- <span data-ttu-id="d5030-1874">不。</span><span class="sxs-lookup"><span data-stu-id="d5030-1874">no.</span></span> <span data-ttu-id="d5030-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="d5030-1875">dell'edizione</span></span> 
- <span data-ttu-id="d5030-1876">不。</span><span class="sxs-lookup"><span data-stu-id="d5030-1876">no.</span></span> <span data-ttu-id="d5030-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d5030-1877">di sicurezza</span></span> 
- <span data-ttu-id="d5030-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="d5030-1878">numero de securite</span></span> 
- <span data-ttu-id="d5030-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="d5030-1879">numero de verificacao</span></span> 
- <span data-ttu-id="d5030-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="d5030-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="d5030-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="d5030-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="d5030-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="d5030-1882">scheda</span></span> 
- <span data-ttu-id="d5030-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d5030-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="d5030-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="d5030-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="d5030-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="d5030-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="d5030-1886">n º autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d5030-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="d5030-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="d5030-1887">número de verificação</span></span> 
- <span data-ttu-id="d5030-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="d5030-1888">perno il blocco</span></span> 
- <span data-ttu-id="d5030-1889">pin 區區塊</span><span class="sxs-lookup"><span data-stu-id="d5030-1889">pin block</span></span> 
- <span data-ttu-id="d5030-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="d5030-1890">prufziffer</span></span> 
- <span data-ttu-id="d5030-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="d5030-1891">prüfziffer</span></span> 
- <span data-ttu-id="d5030-1892">安全性代碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1892">security code</span></span> 
- <span data-ttu-id="d5030-1893">安全性否</span><span class="sxs-lookup"><span data-stu-id="d5030-1893">security no</span></span> 
- <span data-ttu-id="d5030-1894">安全性號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1894">security number</span></span> 
- <span data-ttu-id="d5030-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="d5030-1895">sicherheits kode</span></span> 
- <span data-ttu-id="d5030-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="d5030-1896">sicherheitscode</span></span> 
- <span data-ttu-id="d5030-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="d5030-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="d5030-1898">speldblok</span></span> 
- <span data-ttu-id="d5030-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="d5030-1899">veiligheid nr</span></span> 
- <span data-ttu-id="d5030-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="d5030-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="d5030-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="d5030-1901">veiligheidscode</span></span> 
- <span data-ttu-id="d5030-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="d5030-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="d5030-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="d5030-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="d5030-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="d5030-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="d5030-1905">ablauf</span></span> 
- <span data-ttu-id="d5030-1906">資料 de expiracao</span><span class="sxs-lookup"><span data-stu-id="d5030-1906">data de expiracao</span></span> 
- <span data-ttu-id="d5030-1907">資料 de expiração</span><span class="sxs-lookup"><span data-stu-id="d5030-1907">data de expiração</span></span> 
- <span data-ttu-id="d5030-1908">資料 del exp</span><span class="sxs-lookup"><span data-stu-id="d5030-1908">data del exp</span></span> 
- <span data-ttu-id="d5030-1909">資料 di exp</span><span class="sxs-lookup"><span data-stu-id="d5030-1909">data di exp</span></span> 
- <span data-ttu-id="d5030-1910">資料 di scadenza</span><span class="sxs-lookup"><span data-stu-id="d5030-1910">data di scadenza</span></span> 
- <span data-ttu-id="d5030-1911">資料 em mail.que expira</span><span class="sxs-lookup"><span data-stu-id="d5030-1911">data em que expira</span></span> 
- <span data-ttu-id="d5030-1912">資料 scad</span><span class="sxs-lookup"><span data-stu-id="d5030-1912">data scad</span></span> 
- <span data-ttu-id="d5030-1913">資料 scadenza</span><span class="sxs-lookup"><span data-stu-id="d5030-1913">data scadenza</span></span> 
- <span data-ttu-id="d5030-1914">日期 de validité</span><span class="sxs-lookup"><span data-stu-id="d5030-1914">date de validité</span></span> 
- <span data-ttu-id="d5030-1915">基準 afloop</span><span class="sxs-lookup"><span data-stu-id="d5030-1915">datum afloop</span></span> 
- <span data-ttu-id="d5030-1916">基準 van exp</span><span class="sxs-lookup"><span data-stu-id="d5030-1916">datum van exp</span></span> 
- <span data-ttu-id="d5030-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="d5030-1917">de afloop</span></span> 
- <span data-ttu-id="d5030-1918">espira</span><span class="sxs-lookup"><span data-stu-id="d5030-1918">espira</span></span> 
- <span data-ttu-id="d5030-1919">espira</span><span class="sxs-lookup"><span data-stu-id="d5030-1919">espira</span></span> 
- <span data-ttu-id="d5030-1920">到期日</span><span class="sxs-lookup"><span data-stu-id="d5030-1920">exp date</span></span> 
- <span data-ttu-id="d5030-1921">exp 基準</span><span class="sxs-lookup"><span data-stu-id="d5030-1921">exp datum</span></span> 
- <span data-ttu-id="d5030-1922">到期</span><span class="sxs-lookup"><span data-stu-id="d5030-1922">expiration</span></span> 
- <span data-ttu-id="d5030-1923">到期</span><span class="sxs-lookup"><span data-stu-id="d5030-1923">expire</span></span> 
- <span data-ttu-id="d5030-1924">到期</span><span class="sxs-lookup"><span data-stu-id="d5030-1924">expires</span></span> 
- <span data-ttu-id="d5030-1925">屆滿</span><span class="sxs-lookup"><span data-stu-id="d5030-1925">expiry</span></span> 
- <span data-ttu-id="d5030-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="d5030-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="d5030-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="d5030-1927">fecha de venc</span></span> 
- <span data-ttu-id="d5030-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="d5030-1928">gultig bis</span></span> 
- <span data-ttu-id="d5030-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="d5030-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="d5030-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="d5030-1930">gültig bis</span></span> 
- <span data-ttu-id="d5030-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="d5030-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="d5030-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="d5030-1932">la scadenza</span></span> 
- <span data-ttu-id="d5030-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="d5030-1933">scadenza</span></span> 
- <span data-ttu-id="d5030-1934">valable</span><span class="sxs-lookup"><span data-stu-id="d5030-1934">valable</span></span> 
- <span data-ttu-id="d5030-1935">validade</span><span class="sxs-lookup"><span data-stu-id="d5030-1935">validade</span></span> 
- <span data-ttu-id="d5030-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="d5030-1936">valido hasta</span></span> 
- <span data-ttu-id="d5030-1937">勇氣</span><span class="sxs-lookup"><span data-stu-id="d5030-1937">valor</span></span> 
- <span data-ttu-id="d5030-1938">venc</span><span class="sxs-lookup"><span data-stu-id="d5030-1938">venc</span></span> 
- <span data-ttu-id="d5030-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="d5030-1939">vencimento</span></span> 
- <span data-ttu-id="d5030-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="d5030-1940">vencimiento</span></span> 
- <span data-ttu-id="d5030-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="d5030-1941">verloopt</span></span> 
- <span data-ttu-id="d5030-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="d5030-1942">vervaldag</span></span> 
- <span data-ttu-id="d5030-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="d5030-1943">vervaldatum</span></span> 
- <span data-ttu-id="d5030-1944">vto</span><span class="sxs-lookup"><span data-stu-id="d5030-1944">vto</span></span> 
- <span data-ttu-id="d5030-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="d5030-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="d5030-1946">歐盟駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1946">EU Driver's License Number</span></span>

<span data-ttu-id="d5030-1947">若要深入瞭解，請參閱[歐盟駕駛執照號碼的敏感資訊類型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d5030-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="d5030-1948">歐盟國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1948">EU National Identification Number</span></span>

<span data-ttu-id="d5030-1949">若要深入瞭解，請參閱《[歐盟全國身分識別號碼機密資訊類型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d5030-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="d5030-1950">歐盟護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1950">EU Passport Number</span></span>

<span data-ttu-id="d5030-1951">若要深入瞭解，請參閱[歐盟護照號碼機密資訊類型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d5030-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="d5030-1952">歐盟社會安全號碼或同等識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="d5030-1953">若要深入瞭解，請參閱[歐盟社會安全號碼或對等識別碼機密資訊類型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="d5030-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="d5030-1954">歐盟納稅識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="d5030-1955">若要深入瞭解，請參閱[歐盟納稅識別號碼機密資訊類型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="d5030-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="d5030-1956">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1957">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1957">Format</span></span>

<span data-ttu-id="d5030-1958">六位數加上一個表示世紀的字元加上三個數字加上檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1959">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1959">Pattern</span></span>

<span data-ttu-id="d5030-1960">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="d5030-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="d5030-1961">DDMMYY 出生日期格式格式的六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="d5030-1962">世紀標記（'-'、' + ' 或 ' a '）</span><span class="sxs-lookup"><span data-stu-id="d5030-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="d5030-1963">三位數的個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="d5030-1964">一種檢查碼的數位或字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1965">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1965">Checksum</span></span>

<span data-ttu-id="d5030-1966">是</span><span class="sxs-lookup"><span data-stu-id="d5030-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1967">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1967">Definition</span></span>

<span data-ttu-id="d5030-1968">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1969">函數 Func_finnish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1970">會找到來自 Keyword_finnish_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="d5030-1971">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-1972">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1972">Keywords</span></span>

- <span data-ttu-id="d5030-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="d5030-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="d5030-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="d5030-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="d5030-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="d5030-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="d5030-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="d5030-1976">Personbeteckning</span></span>
- <span data-ttu-id="d5030-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="d5030-1978">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1978">Finland Passport Number</span></span>

<span data-ttu-id="d5030-1979">設定九個字母和數位的組合，九個字母和數位的組合：兩個字母（不區分大小寫）七位數校驗和無定義 DLP 原則在下列情況下，偵測到這種敏感資訊的置信量是75%300個字元的鄰近性：正則運算式 Regex_finland_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="d5030-1980">會找到來自 Keyword_finland_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="d5030-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="d5030-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span></span>
<span data-ttu-id="d5030-1982">Keyword_finland_passport_number Passport Passi 的關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="d5030-1983">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="d5030-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-1984">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-1984">Format</span></span>

<span data-ttu-id="d5030-1985">12位數</span><span class="sxs-lookup"><span data-stu-id="d5030-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-1986">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-1986">Pattern</span></span>

<span data-ttu-id="d5030-1987">12位數與折扣類似的模式，例如法國電話號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-1988">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-1988">Checksum</span></span>

<span data-ttu-id="d5030-1989">否</span><span class="sxs-lookup"><span data-stu-id="d5030-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-1990">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-1990">Definition</span></span>

<span data-ttu-id="d5030-1991">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-1992">函數 Func_french_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-1993">下列專案中至少有一個為真：</span><span class="sxs-lookup"><span data-stu-id="d5030-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="d5030-1994">會找到來自 Keyword_french_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="d5030-1995">函數 Func_eu_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d5030-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-1996">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="d5030-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d5030-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="d5030-1998">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-1998">drivers licence</span></span>
- <span data-ttu-id="d5030-1999">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-1999">drivers license</span></span>
- <span data-ttu-id="d5030-2000">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2000">driving licence</span></span>
- <span data-ttu-id="d5030-2001">駕照</span><span class="sxs-lookup"><span data-stu-id="d5030-2001">driving license</span></span>
- <span data-ttu-id="d5030-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="d5030-2002">permis de conduire</span></span>
- <span data-ttu-id="d5030-2003">許可號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2003">licence number</span></span>
- <span data-ttu-id="d5030-2004">授權號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2004">license number</span></span>
- <span data-ttu-id="d5030-2005">許可證號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2005">licence numbers</span></span>
- <span data-ttu-id="d5030-2006">授權號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="d5030-2007">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="d5030-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2008">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2008">Format</span></span>

<span data-ttu-id="d5030-2009">12位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2010">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2010">Pattern</span></span>

<span data-ttu-id="d5030-2011">12位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2012">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2012">Checksum</span></span>

<span data-ttu-id="d5030-2013">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2014">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2014">Definition</span></span>

<span data-ttu-id="d5030-2015">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2016">正則運算式 Regex_france_cni 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2017">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2017">Keywords</span></span>

<span data-ttu-id="d5030-2018">無</span><span class="sxs-lookup"><span data-stu-id="d5030-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="d5030-2019">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2020">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2020">Format</span></span>

<span data-ttu-id="d5030-2021">九個數字和字母</span><span class="sxs-lookup"><span data-stu-id="d5030-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2022">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2022">Pattern</span></span>

<span data-ttu-id="d5030-2023">九個數字和字母：</span><span class="sxs-lookup"><span data-stu-id="d5030-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="d5030-2024">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2024">Two digits</span></span> 
- <span data-ttu-id="d5030-2025">兩個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="d5030-2026">五位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2027">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2027">Checksum</span></span>

<span data-ttu-id="d5030-2028">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2029">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2029">Definition</span></span>

<span data-ttu-id="d5030-2030">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2031">函數 Func_fr_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2032">會找到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2033">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="d5030-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d5030-2034">Keyword_passport</span></span>

- <span data-ttu-id="d5030-2035">護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2035">Passport Number</span></span>
- <span data-ttu-id="d5030-2036">護照否</span><span class="sxs-lookup"><span data-stu-id="d5030-2036">Passport No</span></span>
- <span data-ttu-id="d5030-2037">護照#</span><span class="sxs-lookup"><span data-stu-id="d5030-2037">Passport #</span></span>
- <span data-ttu-id="d5030-2038">護照#</span><span class="sxs-lookup"><span data-stu-id="d5030-2038">Passport#</span></span>
- <span data-ttu-id="d5030-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="d5030-2039">PassportID</span></span>
- <span data-ttu-id="d5030-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="d5030-2040">Passportno</span></span>
- <span data-ttu-id="d5030-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-2041">passportnumber</span></span>
- <span data-ttu-id="d5030-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="d5030-2042">パスポート</span></span>
- <span data-ttu-id="d5030-2043">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2043">パスポート番号</span></span>
- <span data-ttu-id="d5030-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d5030-2044">パスポートのNum</span></span>
- <span data-ttu-id="d5030-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="d5030-2045">パスポート ＃</span></span> 
- <span data-ttu-id="d5030-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d5030-2046">Numéro de passeport</span></span>
- <span data-ttu-id="d5030-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d5030-2047">Passeport n °</span></span>
- <span data-ttu-id="d5030-2048">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="d5030-2048">Passeport Non</span></span>
- <span data-ttu-id="d5030-2049">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d5030-2049">Passeport #</span></span>
- <span data-ttu-id="d5030-2050">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d5030-2050">Passeport#</span></span>
- <span data-ttu-id="d5030-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d5030-2051">PasseportNon</span></span>
- <span data-ttu-id="d5030-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d5030-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="d5030-2053">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="d5030-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2054">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2054">Format</span></span>

<span data-ttu-id="d5030-2055">15位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2056">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2056">Pattern</span></span>

<span data-ttu-id="d5030-2057">必須符合下列其中一種模式：</span><span class="sxs-lookup"><span data-stu-id="d5030-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="d5030-2058">13位數後接一個空格後接兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="d5030-2059">或</span><span class="sxs-lookup"><span data-stu-id="d5030-2059">or</span></span>
- <span data-ttu-id="d5030-2060">15個連續數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2061">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2061">Checksum</span></span>

<span data-ttu-id="d5030-2062">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2063">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2063">Definition</span></span>

<span data-ttu-id="d5030-2064">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2065">函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2066">會找到來自 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="d5030-2067">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2067">The checksum passes.</span></span>

<span data-ttu-id="d5030-2068">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2069">函數 Func_french_insee 或 Func_fr_insee 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2070">找不到 Keyword_fr_insee 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="d5030-2071">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2072">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="d5030-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="d5030-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="d5030-2074">insee</span><span class="sxs-lookup"><span data-stu-id="d5030-2074">insee</span></span>
- <span data-ttu-id="d5030-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="d5030-2075">securité sociale</span></span>
- <span data-ttu-id="d5030-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="d5030-2076">securite sociale</span></span>
- <span data-ttu-id="d5030-2077">國家識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2077">national id</span></span>
- <span data-ttu-id="d5030-2078">本國身分識別</span><span class="sxs-lookup"><span data-stu-id="d5030-2078">national identification</span></span>
- <span data-ttu-id="d5030-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="d5030-2079">numéro d'identité</span></span>
- <span data-ttu-id="d5030-2080">無 d'identité</span><span class="sxs-lookup"><span data-stu-id="d5030-2080">no d'identité</span></span>
- <span data-ttu-id="d5030-2081">不。</span><span class="sxs-lookup"><span data-stu-id="d5030-2081">no.</span></span> <span data-ttu-id="d5030-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="d5030-2082">d'identité</span></span>
- <span data-ttu-id="d5030-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="d5030-2083">numero d'identite</span></span>
- <span data-ttu-id="d5030-2084">無 d'identite</span><span class="sxs-lookup"><span data-stu-id="d5030-2084">no d'identite</span></span>
- <span data-ttu-id="d5030-2085">不。</span><span class="sxs-lookup"><span data-stu-id="d5030-2085">no.</span></span> <span data-ttu-id="d5030-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="d5030-2086">d'identite</span></span>
- <span data-ttu-id="d5030-2087">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2087">social security number</span></span>
- <span data-ttu-id="d5030-2088">社會安全性碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2088">social security code</span></span>
- <span data-ttu-id="d5030-2089">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2089">social insurance number</span></span>
- <span data-ttu-id="d5030-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="d5030-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="d5030-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="d5030-2091">d'identité nationale</span></span>
- <span data-ttu-id="d5030-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="d5030-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="d5030-2093">le 程式碼 de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="d5030-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="d5030-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="d5030-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="d5030-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="d5030-2095">numéro de sécu</span></span>
- <span data-ttu-id="d5030-2096">程式碼 sécu</span><span class="sxs-lookup"><span data-stu-id="d5030-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="d5030-2097">德文駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2098">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2098">Format</span></span>

<span data-ttu-id="d5030-2099">11位數和字母的組合</span><span class="sxs-lookup"><span data-stu-id="d5030-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2100">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2100">Pattern</span></span>

<span data-ttu-id="d5030-2101">11個數字和字母（不區分大小寫）：</span><span class="sxs-lookup"><span data-stu-id="d5030-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="d5030-2102">一個數位或字母</span><span class="sxs-lookup"><span data-stu-id="d5030-2102">A digit or letter</span></span> 
- <span data-ttu-id="d5030-2103">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2103">Two digits</span></span> 
- <span data-ttu-id="d5030-2104">六個數字或字母</span><span class="sxs-lookup"><span data-stu-id="d5030-2104">Six digits or letters</span></span> 
- <span data-ttu-id="d5030-2105">一個數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2105">A digit</span></span> 
- <span data-ttu-id="d5030-2106">一個數位或字母</span><span class="sxs-lookup"><span data-stu-id="d5030-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2107">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2107">Checksum</span></span>

<span data-ttu-id="d5030-2108">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2109">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2109">Definition</span></span>

<span data-ttu-id="d5030-2110">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2111">函數 Func_german_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2112">下列專案中至少有一個為真：</span><span class="sxs-lookup"><span data-stu-id="d5030-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="d5030-2113">會找到來自 Keyword_german_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="d5030-2114">會找到來自 Keyword_german_drivers_license_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="d5030-2115">會找到來自 Keyword_german_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="d5030-2116">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2117">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="d5030-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="d5030-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2119">Führerschein</span></span>
- <span data-ttu-id="d5030-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2120">Fuhrerschein</span></span>
- <span data-ttu-id="d5030-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2121">Fuehrerschein</span></span>
- <span data-ttu-id="d5030-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="d5030-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="d5030-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="d5030-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="d5030-2125">Führerschein-</span></span> 
- <span data-ttu-id="d5030-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="d5030-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="d5030-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="d5030-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="d5030-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d5030-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="d5030-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d5030-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="d5030-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d5030-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="d5030-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="d5030-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="d5030-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="d5030-2134">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="d5030-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="d5030-2135">Fuhrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="d5030-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="d5030-2136">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="d5030-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="d5030-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="d5030-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="d5030-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="d5030-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d5030-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="d5030-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d5030-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="d5030-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="d5030-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="d5030-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="d5030-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="d5030-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="d5030-2146">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="d5030-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="d5030-2147">Fuhrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="d5030-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="d5030-2148">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="d5030-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="d5030-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="d5030-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="d5030-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="d5030-2152">Dl</span><span class="sxs-lookup"><span data-stu-id="d5030-2152">DL</span></span> 
- <span data-ttu-id="d5030-2153">Dls</span><span class="sxs-lookup"><span data-stu-id="d5030-2153">DLS</span></span>
- <span data-ttu-id="d5030-2154">Driv 許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2154">Driv Lic</span></span> 
- <span data-ttu-id="d5030-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="d5030-2155">Driv Licen</span></span> 
- <span data-ttu-id="d5030-2156">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="d5030-2156">Driv License</span></span>
- <span data-ttu-id="d5030-2157">Driv 授權</span><span class="sxs-lookup"><span data-stu-id="d5030-2157">Driv Licenses</span></span> 
- <span data-ttu-id="d5030-2158">Driv 許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2158">Driv Licence</span></span> 
- <span data-ttu-id="d5030-2159">Driv 許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2159">Driv Licences</span></span> 
- <span data-ttu-id="d5030-2160">Driv 許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2160">Driv Lic</span></span> 
- <span data-ttu-id="d5030-2161">驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="d5030-2161">Driver Licen</span></span> 
- <span data-ttu-id="d5030-2162">駕照</span><span class="sxs-lookup"><span data-stu-id="d5030-2162">Driver License</span></span> 
- <span data-ttu-id="d5030-2163">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-2163">Driver Licenses</span></span> 
- <span data-ttu-id="d5030-2164">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2164">Driver Licence</span></span> 
- <span data-ttu-id="d5030-2165">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-2165">Driver Licences</span></span> 
- <span data-ttu-id="d5030-2166">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-2166">Drivers Lic</span></span> 
- <span data-ttu-id="d5030-2167">驅動程式 Licen</span><span class="sxs-lookup"><span data-stu-id="d5030-2167">Drivers Licen</span></span> 
- <span data-ttu-id="d5030-2168">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-2168">Drivers License</span></span> 
- <span data-ttu-id="d5030-2169">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="d5030-2170">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2170">Drivers Licence</span></span> 
- <span data-ttu-id="d5030-2171">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-2171">Drivers Licences</span></span> 
- <span data-ttu-id="d5030-2172">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-2172">Driver's Lic</span></span> 
- <span data-ttu-id="d5030-2173">驅動程式的 Licen</span><span class="sxs-lookup"><span data-stu-id="d5030-2173">Driver's Licen</span></span> 
- <span data-ttu-id="d5030-2174">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-2174">Driver's License</span></span> 
- <span data-ttu-id="d5030-2175">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="d5030-2176">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-2176">Driver's Licence</span></span> 
- <span data-ttu-id="d5030-2177">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-2177">Driver's Licences</span></span> 
- <span data-ttu-id="d5030-2178">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2178">Driving Lic</span></span> 
- <span data-ttu-id="d5030-2179">驅車 Licen</span><span class="sxs-lookup"><span data-stu-id="d5030-2179">Driving Licen</span></span> 
- <span data-ttu-id="d5030-2180">駕照</span><span class="sxs-lookup"><span data-stu-id="d5030-2180">Driving License</span></span> 
- <span data-ttu-id="d5030-2181">駕駛授權</span><span class="sxs-lookup"><span data-stu-id="d5030-2181">Driving Licenses</span></span> 
- <span data-ttu-id="d5030-2182">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2182">Driving Licence</span></span> 
- <span data-ttu-id="d5030-2183">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="d5030-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="d5030-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="d5030-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="d5030-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="d5030-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="d5030-2188">非 Führerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2188">No-Führerschein</span></span> 
- <span data-ttu-id="d5030-2189">非 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="d5030-2190">非 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="d5030-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2191">N-Führerschein</span></span> 
- <span data-ttu-id="d5030-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="d5030-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="d5030-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="d5030-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="d5030-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="d5030-2197">非 Führerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2197">No-Führerschein</span></span> 
- <span data-ttu-id="d5030-2198">非 Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="d5030-2199">非 Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="d5030-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2200">N-Führerschein</span></span> 
- <span data-ttu-id="d5030-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="d5030-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="d5030-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="d5030-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d5030-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="d5030-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="d5030-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="d5030-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="d5030-2205">ausstellungsort</span></span>
- <span data-ttu-id="d5030-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="d5030-2206">ausstellende behöde</span></span>
- <span data-ttu-id="d5030-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="d5030-2207">ausstellende behorde</span></span>
- <span data-ttu-id="d5030-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="d5030-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="d5030-2209">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2210">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2210">Format</span></span>

<span data-ttu-id="d5030-2211">10位數或字母</span><span class="sxs-lookup"><span data-stu-id="d5030-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2212">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2212">Pattern</span></span>

<span data-ttu-id="d5030-2213">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="d5030-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="d5030-2214">第一個字元是來自此集合的數位或字母（C、F、G、H、J、K）</span><span class="sxs-lookup"><span data-stu-id="d5030-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="d5030-2215">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2215">Three digits</span></span> 
- <span data-ttu-id="d5030-2216">來自此集合的五個數字或字母（C、-H、J-N、P、R、T、V-Z）</span><span class="sxs-lookup"><span data-stu-id="d5030-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="d5030-2217">一個數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2218">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2218">Checksum</span></span>

<span data-ttu-id="d5030-2219">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2220">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2220">Definition</span></span>

<span data-ttu-id="d5030-2221">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2222">函數 Func_german_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2223">找到任何五個關鍵字清單中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="d5030-2224">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2224">The checksum passes.</span></span>

<span data-ttu-id="d5030-2225">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2226">函數 Func_german_passport_data 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2227">找到任何五個關鍵字清單中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="d5030-2228">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2229">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="d5030-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="d5030-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="d5030-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="d5030-2231">reisepass</span></span>
- <span data-ttu-id="d5030-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="d5030-2232">reisepasse</span></span>
- <span data-ttu-id="d5030-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-2233">reisepassnummer</span></span>
- <span data-ttu-id="d5030-2234">護照</span><span class="sxs-lookup"><span data-stu-id="d5030-2234">passport</span></span>
- <span data-ttu-id="d5030-2235">護照</span><span class="sxs-lookup"><span data-stu-id="d5030-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="d5030-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="d5030-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="d5030-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="d5030-2237">geburtsdatum</span></span>
- <span data-ttu-id="d5030-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="d5030-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="d5030-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="d5030-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="d5030-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="d5030-2241">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="d5030-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="d5030-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="d5030-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="d5030-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="d5030-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="d5030-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="d5030-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="d5030-2245">bnationalit</span><span class="sxs-lookup"><span data-stu-id="d5030-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="d5030-2246">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2247">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2247">Format</span></span>

<span data-ttu-id="d5030-2248">自11月2010：9個字母和數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="d5030-2249">從1年4月1987至31年10月2010：10位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2250">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2250">Pattern</span></span>

<span data-ttu-id="d5030-2251">自11月1日2010：</span><span class="sxs-lookup"><span data-stu-id="d5030-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="d5030-2252">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="d5030-2253">八位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2253">Eight digits</span></span>

<span data-ttu-id="d5030-2254">從1年4月1987至31年10月2010：</span><span class="sxs-lookup"><span data-stu-id="d5030-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="d5030-2255">10位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2256">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2256">Checksum</span></span>

<span data-ttu-id="d5030-2257">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2258">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2258">Definition</span></span>

<span data-ttu-id="d5030-2259">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2260">正則運算式 Regex_germany_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2261">會找到來自 Keyword_germany_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2262">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="d5030-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="d5030-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="d5030-2264">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2264">Identity Card</span></span>
- <span data-ttu-id="d5030-2265">ID</span><span class="sxs-lookup"><span data-stu-id="d5030-2265">ID</span></span>
- <span data-ttu-id="d5030-2266">識別</span><span class="sxs-lookup"><span data-stu-id="d5030-2266">Identification</span></span>
- <span data-ttu-id="d5030-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="d5030-2267">Personalausweis</span></span>
- <span data-ttu-id="d5030-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="d5030-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="d5030-2269">Ausweis</span></span>
- <span data-ttu-id="d5030-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="d5030-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="d5030-2271">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2272">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2272">Format</span></span>

<span data-ttu-id="d5030-2273">7-8 字母和數位的組合，加上破折號</span><span class="sxs-lookup"><span data-stu-id="d5030-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2274">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2274">Pattern</span></span>

<span data-ttu-id="d5030-2275">七個字母和數位（舊格式）：</span><span class="sxs-lookup"><span data-stu-id="d5030-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="d5030-2276">一個字母（希臘文字母表的任何字母）</span><span class="sxs-lookup"><span data-stu-id="d5030-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="d5030-2277">虛線</span><span class="sxs-lookup"><span data-stu-id="d5030-2277">A dash</span></span> 
- <span data-ttu-id="d5030-2278">六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2278">Six digits</span></span>

<span data-ttu-id="d5030-2279">八個字母和數位（新格式）：</span><span class="sxs-lookup"><span data-stu-id="d5030-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="d5030-2280">兩個字母大寫字元會同時出現于希臘字母和拉丁字母表中（ABEZHIKMNOPTYX）</span><span class="sxs-lookup"><span data-stu-id="d5030-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="d5030-2281">虛線</span><span class="sxs-lookup"><span data-stu-id="d5030-2281">A dash</span></span> 
- <span data-ttu-id="d5030-2282">六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2283">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2283">Checksum</span></span>

<span data-ttu-id="d5030-2284">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2285">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2285">Definition</span></span>

<span data-ttu-id="d5030-2286">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2287">正則運算式 Regex_greece_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2288">會找到來自 Keyword_greece_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2289">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="d5030-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="d5030-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="d5030-2291">希臘文身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-2291">Greek identity Card</span></span>
- <span data-ttu-id="d5030-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="d5030-2292">Tautotita</span></span>
- <span data-ttu-id="d5030-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="d5030-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="d5030-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="d5030-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="d5030-2295">中國香港身分識別卡（HKID）號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2296">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2296">Format</span></span>

<span data-ttu-id="d5030-2297">8-9 字母和數位的組合，以及最後一個字元兩邊的 optional 括弧</span><span class="sxs-lookup"><span data-stu-id="d5030-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2298">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2298">Pattern</span></span>

<span data-ttu-id="d5030-2299">8-9 個字母的組合：</span><span class="sxs-lookup"><span data-stu-id="d5030-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="d5030-2300">1-2 個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="d5030-2301">六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2301">Six digits</span></span> 
- <span data-ttu-id="d5030-2302">最後一個字元（任何數位或字母 A），也就是檢查碼，也可以以括弧括住。</span><span class="sxs-lookup"><span data-stu-id="d5030-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2303">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2303">Checksum</span></span>

<span data-ttu-id="d5030-2304">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2305">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2305">Definition</span></span>

<span data-ttu-id="d5030-2306">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2307">函數 Func_hong_kong_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2308">會找到來自 Keyword_hong_kong_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="d5030-2309">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2309">The checksum passes.</span></span>

<span data-ttu-id="d5030-2310">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2311">函數 Func_hong_kong_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2312">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2313">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="d5030-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="d5030-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="d5030-2315">中國香港身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-2315">hong kong identity card</span></span>
- <span data-ttu-id="d5030-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="d5030-2316">HKIDC</span></span>
- <span data-ttu-id="d5030-2317">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2317">id card</span></span>
- <span data-ttu-id="d5030-2318">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2318">identity card</span></span>
- <span data-ttu-id="d5030-2319">hk 身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-2319">hk identity card</span></span>
- <span data-ttu-id="d5030-2320">中國香港號</span><span class="sxs-lookup"><span data-stu-id="d5030-2320">hong kong id</span></span>
- <span data-ttu-id="d5030-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2321">香港身份證</span></span>
- <span data-ttu-id="d5030-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="d5030-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2323">身份證</span></span>
- <span data-ttu-id="d5030-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="d5030-2324">身份証</span></span>
- <span data-ttu-id="d5030-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-2325">身分證</span></span>
- <span data-ttu-id="d5030-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="d5030-2326">身分証</span></span>
- <span data-ttu-id="d5030-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="d5030-2327">香港身份証</span></span>
- <span data-ttu-id="d5030-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-2328">香港身分證</span></span>
- <span data-ttu-id="d5030-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="d5030-2329">香港身分証</span></span>
- <span data-ttu-id="d5030-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2330">香港身份證</span></span>
- <span data-ttu-id="d5030-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2331">香港居民身份證</span></span>
- <span data-ttu-id="d5030-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="d5030-2332">香港居民身份証</span></span>
- <span data-ttu-id="d5030-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-2333">香港居民身分證</span></span>
- <span data-ttu-id="d5030-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="d5030-2334">香港居民身分証</span></span>
- <span data-ttu-id="d5030-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d5030-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="d5030-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="d5030-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d5030-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="d5030-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="d5030-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="d5030-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d5030-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="d5030-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="d5030-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d5030-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="d5030-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="d5030-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d5030-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="d5030-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="d5030-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d5030-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="d5030-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="d5030-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="d5030-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="d5030-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="d5030-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="d5030-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="d5030-2351">印度永久帳戶號碼（PAN）</span><span class="sxs-lookup"><span data-stu-id="d5030-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2352">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2352">Format</span></span>

<span data-ttu-id="d5030-2353">10個字母或數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2354">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2354">Pattern</span></span>

<span data-ttu-id="d5030-2355">10個字母或數位：</span><span class="sxs-lookup"><span data-stu-id="d5030-2355">10 letters or digits:</span></span>
- <span data-ttu-id="d5030-2356">五個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="d5030-2357">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2357">Four digits</span></span> 
- <span data-ttu-id="d5030-2358">以字母檢查碼表示的字母</span><span class="sxs-lookup"><span data-stu-id="d5030-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2359">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2359">Checksum</span></span>

<span data-ttu-id="d5030-2360">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2361">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2361">Definition</span></span>

<span data-ttu-id="d5030-2362">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2363">正則運算式 Regex_india_permanent_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2364">會找到來自 Keyword_india_permanent_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="d5030-2365">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2366">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="d5030-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="d5030-2368">永久帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="d5030-2369">泛</span><span class="sxs-lookup"><span data-stu-id="d5030-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="d5030-2370">印度唯一識別碼（Aadhaar）號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2371">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2371">Format</span></span>

<span data-ttu-id="d5030-2372">12位數包含選擇性空格或短杠</span><span class="sxs-lookup"><span data-stu-id="d5030-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2373">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2373">Pattern</span></span>

<span data-ttu-id="d5030-2374">12位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-2374">12 digits:</span></span>
- <span data-ttu-id="d5030-2375">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2375">Four digits</span></span> 
- <span data-ttu-id="d5030-2376">選擇性的空格或破折號</span><span class="sxs-lookup"><span data-stu-id="d5030-2376">An optional space or dash</span></span> 
- <span data-ttu-id="d5030-2377">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2377">Four digits</span></span> 
- <span data-ttu-id="d5030-2378">選擇性的空格或破折號</span><span class="sxs-lookup"><span data-stu-id="d5030-2378">An optional space or dash</span></span> 
- <span data-ttu-id="d5030-2379">最後一位數的檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2380">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2380">Checksum</span></span>

<span data-ttu-id="d5030-2381">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2382">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2382">Definition</span></span>

<span data-ttu-id="d5030-2383">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：函數 Func_india_aadhaar 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="d5030-2384">會找到來自 Keyword_india_aadhar 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="d5030-2385">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2385">The checksum passes.</span></span>
<span data-ttu-id="d5030-2386">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：函數 Func_india_aadhaar 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="d5030-2387">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2387">The checksum passes.</span></span>
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
### <a name="keywords"></a><span data-ttu-id="d5030-2388">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="d5030-2389">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="d5030-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="d5030-2390">Aadhar</span><span class="sxs-lookup"><span data-stu-id="d5030-2390">Aadhar</span></span>
- <span data-ttu-id="d5030-2391">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="d5030-2391">Aadhaar</span></span>
- <span data-ttu-id="d5030-2392">Uid</span><span class="sxs-lookup"><span data-stu-id="d5030-2392">UID</span></span>
- <span data-ttu-id="d5030-2393">आधार</span><span class="sxs-lookup"><span data-stu-id="d5030-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="d5030-2394">印尼身分識別卡（KTP）號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2395">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2395">Format</span></span>

<span data-ttu-id="d5030-2396">包含選用句點的16位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2397">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2397">Pattern</span></span>

<span data-ttu-id="d5030-2398">16位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-2398">16 digits:</span></span>
- <span data-ttu-id="d5030-2399">兩位數的省碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2399">Two-digit province code</span></span> 
- <span data-ttu-id="d5030-2400">一個句點（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-2400">A period (optional)</span></span> 
- <span data-ttu-id="d5030-2401">兩位數攝政或城市碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="d5030-2402">兩位數的 subdistrict 程式碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="d5030-2403">一個句點（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-2403">A period (optional)</span></span> 
- <span data-ttu-id="d5030-2404">DDMMYY 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="d5030-2405">一個句點（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-2405">A period (optional)</span></span> 
- <span data-ttu-id="d5030-2406">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2407">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2407">Checksum</span></span>

<span data-ttu-id="d5030-2408">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2409">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2409">Definition</span></span>

<span data-ttu-id="d5030-2410">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2411">正則運算式 Regex_indonesia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2412">會找到來自 Keyword_indonesia_id_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="d5030-2413">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2414">正則運算式 Regex_indonesia_id_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2415">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="d5030-2416">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="d5030-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="d5030-2417">Ktp</span><span class="sxs-lookup"><span data-stu-id="d5030-2417">KTP</span></span>
- <span data-ttu-id="d5030-2418">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="d5030-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="d5030-2419">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="d5030-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="d5030-2420">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="d5030-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2421">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2421">Format</span></span>

<span data-ttu-id="d5030-2422">國家/地區代碼（兩個字母）加上檢查碼（兩位數）加上 bban 號碼（最多30個字元）</span><span class="sxs-lookup"><span data-stu-id="d5030-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2423">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2423">Pattern</span></span>

<span data-ttu-id="d5030-2424">模式必須包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="d5030-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="d5030-2425">兩個字母的國家/地區碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2425">Two-letter country code</span></span>
- <span data-ttu-id="d5030-2426">兩個檢查碼位數（後面接著選擇性的空格）</span><span class="sxs-lookup"><span data-stu-id="d5030-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="d5030-2427">1-7 四個字母或數位的群組（可以以空格隔開）</span><span class="sxs-lookup"><span data-stu-id="d5030-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="d5030-2428">1-3 個字母或數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2428">1-3 letters or digits</span></span>

<span data-ttu-id="d5030-2429">每個國家/地區的格式稍有不同。</span><span class="sxs-lookup"><span data-stu-id="d5030-2429">The format for each country is slightly different.</span></span> <span data-ttu-id="d5030-2430">IBAN 敏感資訊類型涵蓋下列60個國家/地區：</span><span class="sxs-lookup"><span data-stu-id="d5030-2430">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="d5030-2431">ad，ae，al，at，az，ba，是，bg，bh，ch，cr，cy，cz，de，深色，do，ee，es，fi，，gl，fr，gb，中，hu，，il，），it，kw，kz，lb，li，fr，mu，，nl-nl，no，pl，pt，ro，rs，sa，se，si，sk，sm，tn，tr，vg</span><span class="sxs-lookup"><span data-stu-id="d5030-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2432">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2432">Checksum</span></span>

<span data-ttu-id="d5030-2433">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2434">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2434">Definition</span></span>

<span data-ttu-id="d5030-2435">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2436">函數 Func_iban 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2437">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2438">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2438">Keywords</span></span>

<span data-ttu-id="d5030-2439">無</span><span class="sxs-lookup"><span data-stu-id="d5030-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="d5030-2440">IP 位址</span><span class="sxs-lookup"><span data-stu-id="d5030-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2441">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="d5030-2442">IPv4：</span><span class="sxs-lookup"><span data-stu-id="d5030-2442">IPv4:</span></span>
<span data-ttu-id="d5030-2443">用於格式化（句點）及未格式化（無期間）的 IPv4 位址版本的複雜模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="d5030-2444">IPv6：</span><span class="sxs-lookup"><span data-stu-id="d5030-2444">IPv6:</span></span>
<span data-ttu-id="d5030-2445">IPv6 數位格式（包含冒號）的複雜模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2446">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2447">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2447">Checksum</span></span>

<span data-ttu-id="d5030-2448">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2449">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2449">Definition</span></span>

<span data-ttu-id="d5030-2450">針對 IPv6，如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2451">正則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2452">找不到 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="d5030-2453">針對 IPv4，如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2454">正則運算式 Regex_ipv4_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2455">會找到來自 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="d5030-2456">針對 IPv6，如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是95%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2457">正則運算式 Regex_ipv6_address 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2458">找不到 Keyword_ipaddress 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2458">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2459">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="d5030-2460">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="d5030-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="d5030-2461">IP （此關鍵字區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="d5030-2462">ip 位址</span><span class="sxs-lookup"><span data-stu-id="d5030-2462">ip address</span></span> 
- <span data-ttu-id="d5030-2463">ip 位址</span><span class="sxs-lookup"><span data-stu-id="d5030-2463">ip addresses</span></span>
- <span data-ttu-id="d5030-2464">網際網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="d5030-2464">internet protocol</span></span>
- <span data-ttu-id="d5030-2465">IP-כתובתה</span><span class="sxs-lookup"><span data-stu-id="d5030-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="d5030-2466">國際分類的疾病（ICD-10-釐米）</span><span class="sxs-lookup"><span data-stu-id="d5030-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2467">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2467">Format</span></span>

<span data-ttu-id="d5030-2468">Dictionary</span><span class="sxs-lookup"><span data-stu-id="d5030-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2469">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2469">Pattern</span></span>

<span data-ttu-id="d5030-2470">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2471">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2471">Checksum</span></span>

<span data-ttu-id="d5030-2472">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2473">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2473">Definition</span></span>

<span data-ttu-id="d5030-2474">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2475">會找到來自 Dictionary_icd_10_updated 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="d5030-2476">會找到來自 Dictionary_icd_10_codes 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="d5030-2477">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2478">會找到 Dictionary_icd_10_ 更新的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

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

<span data-ttu-id="d5030-2479">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2479">Keywords</span></span>

<span data-ttu-id="d5030-2480">Dictionary_icd_10_updated 關鍵字字典中的任何字詞，其基礎是以[疾病的國際分類，第十個修訂版本、臨床修改（icd-10 釐米）](https://go.microsoft.com/fwlink/?linkid=852604)為基礎。</span><span class="sxs-lookup"><span data-stu-id="d5030-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="d5030-2481">這種類型只會尋找字詞，而不是保險碼。</span><span class="sxs-lookup"><span data-stu-id="d5030-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="d5030-2482">Dictionary_icd_10_codes 關鍵字字典中的任何字詞，其基礎是以[疾病的國際分類，第十個修訂版本、臨床修改（icd-10 釐米）](https://go.microsoft.com/fwlink/?linkid=852604)為基礎。</span><span class="sxs-lookup"><span data-stu-id="d5030-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="d5030-2483">這種類型只會查看保險業代碼，而不是描述。</span><span class="sxs-lookup"><span data-stu-id="d5030-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="d5030-2484">國際疾病（ICD-9 CM）分類</span><span class="sxs-lookup"><span data-stu-id="d5030-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2485">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2485">Format</span></span>

<span data-ttu-id="d5030-2486">Dictionary</span><span class="sxs-lookup"><span data-stu-id="d5030-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2487">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2487">Pattern</span></span>

<span data-ttu-id="d5030-2488">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2489">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2489">Checksum</span></span>

<span data-ttu-id="d5030-2490">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2491">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2491">Definition</span></span>

<span data-ttu-id="d5030-2492">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2493">會找到來自 Dictionary_icd_9_updated 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="d5030-2494">會找到來自 Dictionary_icd_9_codes 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="d5030-2495">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2496">會找到來自 Dictionary_icd_9_updated 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2497">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2497">Keywords</span></span>

<span data-ttu-id="d5030-2498">Dictionary_icd_9_updated 關鍵字字典中的任何字詞，其基礎是根據[疾病的國際分類，第九個修訂版本，臨床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="d5030-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="d5030-2499">這種類型只會尋找字詞，而不是保險碼。</span><span class="sxs-lookup"><span data-stu-id="d5030-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="d5030-2500">Dictionary_icd_9_codes 關鍵字字典中的任何字詞，其基礎是根據[疾病的國際分類，第九個修訂版本，臨床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="d5030-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="d5030-2501">這種類型只會查看保險業代碼，而不是描述。</span><span class="sxs-lookup"><span data-stu-id="d5030-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="d5030-2502">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2503">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2503">Format</span></span>

<span data-ttu-id="d5030-2504">舊格式（直到12月2012日）：</span><span class="sxs-lookup"><span data-stu-id="d5030-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="d5030-2505">七位數後接1-2 個字母</span><span class="sxs-lookup"><span data-stu-id="d5030-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="d5030-2506">新格式（1月2013日和之後）：</span><span class="sxs-lookup"><span data-stu-id="d5030-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="d5030-2507">七位數後接兩個字母</span><span class="sxs-lookup"><span data-stu-id="d5030-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2508">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2508">Pattern</span></span>

<span data-ttu-id="d5030-2509">舊格式（直到12月2012日）：</span><span class="sxs-lookup"><span data-stu-id="d5030-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="d5030-2510">七位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2510">Seven digits</span></span> 
- <span data-ttu-id="d5030-2511">1-2 個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="d5030-2512">新格式（1月2013日和之後）：</span><span class="sxs-lookup"><span data-stu-id="d5030-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="d5030-2513">七位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2513">Seven digits</span></span> 
- <span data-ttu-id="d5030-2514">字母（不區分大小寫）是字母檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="d5030-2515">字母 "A" 或 "H" （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2516">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2516">Checksum</span></span>

<span data-ttu-id="d5030-2517">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2518">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2518">Definition</span></span>

<span data-ttu-id="d5030-2519">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2520">函數 Func_ireland_pps 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2521">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="d5030-2521">One of the following is true:</span></span>
    - <span data-ttu-id="d5030-2522">會找到來自 Keyword_ireland_pps 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="d5030-2523">函數 Func_eu_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d5030-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="d5030-2524">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2524">The checksum passes.</span></span>

<span data-ttu-id="d5030-2525">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2526">函數 Func_ireland_pps 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2527">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2527">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2528">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="d5030-2529">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="d5030-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="d5030-2530">個人公開服務號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="d5030-2531">PPS 號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2531">PPS Number</span></span> 
- <span data-ttu-id="d5030-2532">PPS 數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2532">PPS Num</span></span> 
- <span data-ttu-id="d5030-2533">PPS No。</span><span class="sxs-lookup"><span data-stu-id="d5030-2533">PPS No.</span></span> 
- <span data-ttu-id="d5030-2534">Pps#</span><span class="sxs-lookup"><span data-stu-id="d5030-2534">PPS #</span></span> 
- <span data-ttu-id="d5030-2535">Pps#</span><span class="sxs-lookup"><span data-stu-id="d5030-2535">PPS#</span></span> 
- <span data-ttu-id="d5030-2536">PPSN</span><span class="sxs-lookup"><span data-stu-id="d5030-2536">PPSN</span></span> 
- <span data-ttu-id="d5030-2537">公用服務卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-2537">Public Services Card</span></span> 
- <span data-ttu-id="d5030-2538">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="d5030-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="d5030-2539">Uimh.</span><span class="sxs-lookup"><span data-stu-id="d5030-2539">Uimh.</span></span> <span data-ttu-id="d5030-2540">Psp</span><span class="sxs-lookup"><span data-stu-id="d5030-2540">PSP</span></span> 
- <span data-ttu-id="d5030-2541">Psp</span><span class="sxs-lookup"><span data-stu-id="d5030-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="d5030-2542">以色列銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2543">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2543">Format</span></span>

<span data-ttu-id="d5030-2544">13位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2545">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2545">Pattern</span></span>

<span data-ttu-id="d5030-2546">格式 化：</span><span class="sxs-lookup"><span data-stu-id="d5030-2546">Formatted:</span></span>
- <span data-ttu-id="d5030-2547">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2547">Two digits</span></span> 
- <span data-ttu-id="d5030-2548">虛線</span><span class="sxs-lookup"><span data-stu-id="d5030-2548">A dash</span></span> 
- <span data-ttu-id="d5030-2549">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2549">Three digits</span></span> 
- <span data-ttu-id="d5030-2550">虛線</span><span class="sxs-lookup"><span data-stu-id="d5030-2550">A dash</span></span> 
- <span data-ttu-id="d5030-2551">八位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2551">Eight digits</span></span>

<span data-ttu-id="d5030-2552">非</span><span class="sxs-lookup"><span data-stu-id="d5030-2552">Unformatted:</span></span>
- <span data-ttu-id="d5030-2553">13個連續數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2554">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2554">Checksum</span></span>

<span data-ttu-id="d5030-2555">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2556">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2556">Definition</span></span>

<span data-ttu-id="d5030-2557">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2558">正則運算式 Regex_israel_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2559">會找到來自 Keyword_israel_bank_account_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2560">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="d5030-2561">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="d5030-2562">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2562">Bank Account Number</span></span> 
- <span data-ttu-id="d5030-2563">銀行帳戶</span><span class="sxs-lookup"><span data-stu-id="d5030-2563">Bank Account</span></span> 
- <span data-ttu-id="d5030-2564">帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2564">Account Number</span></span> 
- <span data-ttu-id="d5030-2565">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="d5030-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="d5030-2566">以色列國家識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2567">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2567">Format</span></span>

<span data-ttu-id="d5030-2568">九位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2569">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2569">Pattern</span></span>

<span data-ttu-id="d5030-2570">九個連續數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2571">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2571">Checksum</span></span>

<span data-ttu-id="d5030-2572">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2573">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2573">Definition</span></span>

<span data-ttu-id="d5030-2574">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2575">函數 Func_israeli_national_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2576">會找到來自 Keyword_Israel_National_ID 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="d5030-2577">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2577">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2578">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="d5030-2579">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="d5030-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="d5030-2580">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="d5030-2580">מספר זהות</span></span> 
- <span data-ttu-id="d5030-2581">本國識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="d5030-2582">義大利駕照編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2583">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2583">Format</span></span>

<span data-ttu-id="d5030-2584">10個字母和數位的組合</span><span class="sxs-lookup"><span data-stu-id="d5030-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2585">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2585">Pattern</span></span>

- <span data-ttu-id="d5030-2586">10個字母和數位的組合：</span><span class="sxs-lookup"><span data-stu-id="d5030-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="d5030-2587">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="d5030-2588">字母 "A" 或 "V" （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="d5030-2589">七個字母（不區分大小寫）、數位或底線字元</span><span class="sxs-lookup"><span data-stu-id="d5030-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="d5030-2590">一個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2591">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2591">Checksum</span></span>

<span data-ttu-id="d5030-2592">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2593">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2593">Definition</span></span>

<span data-ttu-id="d5030-2594">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2595">正則運算式 Regex_italy_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2596">會找到來自 Keyword_italy_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2597">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="d5030-2598">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="d5030-2599">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="d5030-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="d5030-2600">patente di guida</span><span class="sxs-lookup"><span data-stu-id="d5030-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="d5030-2601">日本銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2602">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2602">Format</span></span>

<span data-ttu-id="d5030-2603">7或8位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2604">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2604">Pattern</span></span>

<span data-ttu-id="d5030-2605">銀行帳戶號碼：</span><span class="sxs-lookup"><span data-stu-id="d5030-2605">Bank account number:</span></span>
- <span data-ttu-id="d5030-2606">7或8位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2606">Seven or eight digits</span></span>
- <span data-ttu-id="d5030-2607">銀行帳戶分支程式碼：</span><span class="sxs-lookup"><span data-stu-id="d5030-2607">Bank account branch code:</span></span>
- <span data-ttu-id="d5030-2608">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2608">Four digits</span></span> 
- <span data-ttu-id="d5030-2609">一個空格或破折號（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="d5030-2610">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2610">Three digits</span></span>

<span data-ttu-id="d5030-2611">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2611">Checksum</span></span>

<span data-ttu-id="d5030-2612">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2613">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2613">Definition</span></span>

<span data-ttu-id="d5030-2614">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2615">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2616">會找到來自 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="d5030-2617">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="d5030-2617">One of the following is true:</span></span>
- <span data-ttu-id="d5030-2618">函數 Func_jp_bank_account_branch_code 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2619">會找到來自 Keyword_jp_bank_branch_code 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="d5030-2620">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2621">函數 Func_jp_bank_account 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2622">會找到來自 Keyword_jp_bank_account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2623">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="d5030-2624">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="d5030-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="d5030-2625">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2625">Checking Account Number</span></span> 
- <span data-ttu-id="d5030-2626">檢查帳戶</span><span class="sxs-lookup"><span data-stu-id="d5030-2626">Checking Account</span></span> 
- <span data-ttu-id="d5030-2627">檢查帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-2627">Checking Account #</span></span> 
- <span data-ttu-id="d5030-2628">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="d5030-2629">檢查帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-2629">Checking Acct #</span></span> 
- <span data-ttu-id="d5030-2630">檢查帳戶否。</span><span class="sxs-lookup"><span data-stu-id="d5030-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="d5030-2631">檢查帳戶否</span><span class="sxs-lookup"><span data-stu-id="d5030-2631">Checking Account No.</span></span> 
- <span data-ttu-id="d5030-2632">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2632">Bank Account Number</span></span> 
- <span data-ttu-id="d5030-2633">銀行帳戶</span><span class="sxs-lookup"><span data-stu-id="d5030-2633">Bank Account</span></span> 
- <span data-ttu-id="d5030-2634">銀行帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-2634">Bank Account #</span></span> 
- <span data-ttu-id="d5030-2635">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="d5030-2636">銀行帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-2636">Bank Acct #</span></span> 
- <span data-ttu-id="d5030-2637">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="d5030-2638">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2638">Bank Account No.</span></span> 
- <span data-ttu-id="d5030-2639">儲蓄帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2639">Savings Account Number</span></span> 
- <span data-ttu-id="d5030-2640">儲蓄帳戶</span><span class="sxs-lookup"><span data-stu-id="d5030-2640">Savings Account</span></span> 
- <span data-ttu-id="d5030-2641">儲蓄帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-2641">Savings Account #</span></span> 
- <span data-ttu-id="d5030-2642">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="d5030-2643">儲蓄帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-2643">Savings Acct #</span></span> 
- <span data-ttu-id="d5030-2644">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="d5030-2645">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2645">Savings Account No.</span></span> 
- <span data-ttu-id="d5030-2646">借方科目編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2646">Debit Account Number</span></span> 
- <span data-ttu-id="d5030-2647">借方科目</span><span class="sxs-lookup"><span data-stu-id="d5030-2647">Debit Account</span></span> 
- <span data-ttu-id="d5030-2648">借方科目#</span><span class="sxs-lookup"><span data-stu-id="d5030-2648">Debit Account #</span></span> 
- <span data-ttu-id="d5030-2649">借方帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="d5030-2650">借方帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-2650">Debit Acct #</span></span> 
- <span data-ttu-id="d5030-2651">借方帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="d5030-2652">借方科目編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2652">Debit Account No.</span></span> 
- <span data-ttu-id="d5030-2653">口座番號を當座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="d5030-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="d5030-2654">#アカウントの確認、勘定番號の確認</span><span class="sxs-lookup"><span data-stu-id="d5030-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="d5030-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="d5030-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="d5030-2656">勘定番號の確認</span><span class="sxs-lookup"><span data-stu-id="d5030-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="d5030-2657">口座番號の確認</span><span class="sxs-lookup"><span data-stu-id="d5030-2657">口座番号の確認</span></span> 
- <span data-ttu-id="d5030-2658">銀行口座番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2658">銀行口座番号</span></span> 
- <span data-ttu-id="d5030-2659">銀行口座</span><span class="sxs-lookup"><span data-stu-id="d5030-2659">銀行口座</span></span> 
- <span data-ttu-id="d5030-2660">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="d5030-2660">銀行口座＃</span></span> 
- <span data-ttu-id="d5030-2661">銀行の勘定番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="d5030-2662">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="d5030-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="d5030-2663">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="d5030-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="d5030-2664">銀行口座番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2664">銀行口座番号</span></span>
- <span data-ttu-id="d5030-2665">普通預金口座番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="d5030-2666">預金口座</span><span class="sxs-lookup"><span data-stu-id="d5030-2666">預金口座</span></span> 
- <span data-ttu-id="d5030-2667">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="d5030-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="d5030-2668">貯蓄勘定の數</span><span class="sxs-lookup"><span data-stu-id="d5030-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="d5030-2669">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="d5030-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="d5030-2670">貯蓄勘定番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="d5030-2671">普通預金口座番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="d5030-2672">引き落とし口座番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="d5030-2673">口座番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2673">口座番号</span></span> 
- <span data-ttu-id="d5030-2674">口座番號＃</span><span class="sxs-lookup"><span data-stu-id="d5030-2674">口座番号＃</span></span> 
- <span data-ttu-id="d5030-2675">デビットのacct番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="d5030-2676">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="d5030-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="d5030-2677">デビットACCTの番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="d5030-2678">デビット口座番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="d5030-2679">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="d5030-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="d5030-2680">Otemachi</span><span class="sxs-lookup"><span data-stu-id="d5030-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="d5030-2681">日本駕照編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2682">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2682">Format</span></span>

<span data-ttu-id="d5030-2683">12位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2684">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2684">Pattern</span></span>

<span data-ttu-id="d5030-2685">12個連續數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2686">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2686">Checksum</span></span>

<span data-ttu-id="d5030-2687">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2688">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2688">Definition</span></span>

<span data-ttu-id="d5030-2689">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2690">函數 Func_jp_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2691">會找到來自 Keyword_jp_drivers_license_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2692">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="d5030-2693">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="d5030-2694">Dl#</span><span class="sxs-lookup"><span data-stu-id="d5030-2694">dl#</span></span> 
- <span data-ttu-id="d5030-2695">DL</span><span class="sxs-lookup"><span data-stu-id="d5030-2695">DL＃</span></span> 
- <span data-ttu-id="d5030-2696">Dls#</span><span class="sxs-lookup"><span data-stu-id="d5030-2696">dls#</span></span> 
- <span data-ttu-id="d5030-2697">DL</span><span class="sxs-lookup"><span data-stu-id="d5030-2697">DLS＃</span></span> 
- <span data-ttu-id="d5030-2698">駕照</span><span class="sxs-lookup"><span data-stu-id="d5030-2698">driver license</span></span> 
- <span data-ttu-id="d5030-2699">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-2699">driver licenses</span></span> 
- <span data-ttu-id="d5030-2700">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-2700">drivers license</span></span> 
- <span data-ttu-id="d5030-2701">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-2701">driver's license</span></span> 
- <span data-ttu-id="d5030-2702">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-2702">drivers licenses</span></span> 
- <span data-ttu-id="d5030-2703">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-2703">driver's licenses</span></span> 
- <span data-ttu-id="d5030-2704">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2704">driving licence</span></span> 
- <span data-ttu-id="d5030-2705">許可證#</span><span class="sxs-lookup"><span data-stu-id="d5030-2705">lic#</span></span> 
- <span data-ttu-id="d5030-2706">許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-2706">LIC＃</span></span> 
- <span data-ttu-id="d5030-2707">lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-2707">lics#</span></span> 
- <span data-ttu-id="d5030-2708">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2708">state id</span></span> 
- <span data-ttu-id="d5030-2709">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2709">state identification</span></span> 
- <span data-ttu-id="d5030-2710">狀態識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2710">state identification number</span></span> 
- <span data-ttu-id="d5030-2711">低所得國＃</span><span class="sxs-lookup"><span data-stu-id="d5030-2711">低所得国＃</span></span> 
- <span data-ttu-id="d5030-2712">免許証</span><span class="sxs-lookup"><span data-stu-id="d5030-2712">免許証</span></span> 
- <span data-ttu-id="d5030-2713">狀態ID</span><span class="sxs-lookup"><span data-stu-id="d5030-2713">状態ID</span></span>
- <span data-ttu-id="d5030-2714">狀態の識別</span><span class="sxs-lookup"><span data-stu-id="d5030-2714">状態の識別</span></span> 
- <span data-ttu-id="d5030-2715">狀態の識別番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2715">状態の識別番号</span></span> 
- <span data-ttu-id="d5030-2716">運転免許</span><span class="sxs-lookup"><span data-stu-id="d5030-2716">運転免許</span></span> 
- <span data-ttu-id="d5030-2717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="d5030-2717">運転免許証</span></span> 
- <span data-ttu-id="d5030-2718">運転免許証番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="d5030-2719">日本護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2720">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2720">Format</span></span>

<span data-ttu-id="d5030-2721">兩個字母后接7位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2722">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2722">Pattern</span></span>

<span data-ttu-id="d5030-2723">兩個字母（不區分大小寫）後接7位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2724">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2724">Checksum</span></span>

<span data-ttu-id="d5030-2725">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2726">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2726">Definition</span></span>

<span data-ttu-id="d5030-2727">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2728">函數 Func_jp_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2729">會找到來自 Keyword_jp_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2730">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="d5030-2731">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="d5030-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="d5030-2732">パスポート</span><span class="sxs-lookup"><span data-stu-id="d5030-2732">パスポート</span></span> 
- <span data-ttu-id="d5030-2733">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2733">パスポート番号</span></span> 
- <span data-ttu-id="d5030-2734">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d5030-2734">パスポートのNum</span></span> 
- <span data-ttu-id="d5030-2735">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="d5030-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="d5030-2736">日本居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2737">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2737">Format</span></span>

<span data-ttu-id="d5030-2738">11位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2739">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2739">Pattern</span></span>

<span data-ttu-id="d5030-2740">11個連續數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2741">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2741">Checksum</span></span>

<span data-ttu-id="d5030-2742">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2743">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2743">Definition</span></span>

<span data-ttu-id="d5030-2744">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2745">函數 Func_jp_resident_registration_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2746">會找到來自 Keyword_jp_resident_registration_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2747">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="d5030-2748">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="d5030-2749">常駐登記編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2749">Resident Registration Number</span></span>
- <span data-ttu-id="d5030-2750">常駐寄存器號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2750">Resident Register Number</span></span> 
- <span data-ttu-id="d5030-2751">居民基本登錄號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="d5030-2752">常駐登記編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="d5030-2753">居民收銀機否。</span><span class="sxs-lookup"><span data-stu-id="d5030-2753">Resident Register No.</span></span> 
- <span data-ttu-id="d5030-2754">居民基本登錄否。</span><span class="sxs-lookup"><span data-stu-id="d5030-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="d5030-2755">基本居民收銀機 No。</span><span class="sxs-lookup"><span data-stu-id="d5030-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="d5030-2756">住民登録番號、登録番號をレジデント</span><span class="sxs-lookup"><span data-stu-id="d5030-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="d5030-2757">住民基本登録番號、登録番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="d5030-2758">住民基本レジストリ番號を常駐</span><span class="sxs-lookup"><span data-stu-id="d5030-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="d5030-2759">登録番號を常駐住民基本台帳登録番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="d5030-2760">日本社交保險號碼（SIN）</span><span class="sxs-lookup"><span data-stu-id="d5030-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2761">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2761">Format</span></span>

<span data-ttu-id="d5030-2762">7-12 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2763">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2763">Pattern</span></span>

<span data-ttu-id="d5030-2764">7-12 位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-2764">7-12 digits:</span></span>
- <span data-ttu-id="d5030-2765">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2765">Four digits</span></span> 
- <span data-ttu-id="d5030-2766">連字號（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="d5030-2767">六位數或</span><span class="sxs-lookup"><span data-stu-id="d5030-2767">Six digits OR</span></span>
- <span data-ttu-id="d5030-2768">7-12 連續位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2769">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2769">Checksum</span></span>

<span data-ttu-id="d5030-2770">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2771">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2771">Definition</span></span>

<span data-ttu-id="d5030-2772">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2773">函數 Func_jp_sin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2774">會找到來自 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="d5030-2775">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2776">函數 Func_jp_sin_pre_1997 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2777">會找到來自 Keyword_jp_sin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2777">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2778">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="d5030-2779">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="d5030-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="d5030-2780">社交保險保險編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="d5030-2781">社交保險編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="d5030-2782">社交保險號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="d5030-2783">社會保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="d5030-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="d5030-2784">社會保険番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="d5030-2785">日本住家電話卡號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2786">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2786">Format</span></span>

<span data-ttu-id="d5030-2787">12個字母和數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2788">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2788">Pattern</span></span>

<span data-ttu-id="d5030-2789">12個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="d5030-2789">12 letters and digits:</span></span>
- <span data-ttu-id="d5030-2790">兩個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="d5030-2791">八位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2791">Eight digits</span></span> 
- <span data-ttu-id="d5030-2792">兩個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2793">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2793">Checksum</span></span>

<span data-ttu-id="d5030-2794">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2795">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2795">Definition</span></span>

<span data-ttu-id="d5030-2796">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2797">正則運算式 Regex_jp_residence_card_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2798">會找到來自 Keyword_jp_residence_card_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2799">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="d5030-2800">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="d5030-2801">住家電話卡號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2801">Residence card number</span></span>
- <span data-ttu-id="d5030-2802">不含住宅卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-2802">Residence card no</span></span>
- <span data-ttu-id="d5030-2803">住宅卡片#</span><span class="sxs-lookup"><span data-stu-id="d5030-2803">Residence card #</span></span>
- <span data-ttu-id="d5030-2804">在留カード番號</span><span class="sxs-lookup"><span data-stu-id="d5030-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="d5030-2805">馬來西亞識別碼卡片編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2806">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2806">Format</span></span>

<span data-ttu-id="d5030-2807">12位數包含選擇性連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2808">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2808">Pattern</span></span>

<span data-ttu-id="d5030-2809">12位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-2809">12 digits:</span></span>
- <span data-ttu-id="d5030-2810">YYMMDD 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d5030-2811">破折號（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-2811">A dash (optional)</span></span> 
- <span data-ttu-id="d5030-2812">兩個字母的出生代碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="d5030-2813">破折號（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-2813">A dash (optional)</span></span> 
- <span data-ttu-id="d5030-2814">三個亂數字</span><span class="sxs-lookup"><span data-stu-id="d5030-2814">Three random digits</span></span> 
- <span data-ttu-id="d5030-2815">一位數的性別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2816">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2816">Checksum</span></span>

<span data-ttu-id="d5030-2817">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2818">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2818">Definition</span></span>

<span data-ttu-id="d5030-2819">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2820">正則運算式 Regex_malaysia_id_card_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2821">會找到來自 Keyword_malaysia_id_card_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2822">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="d5030-2823">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="d5030-2824">數位 application 卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-2824">digital application card</span></span>
- <span data-ttu-id="d5030-2825">i/c</span><span class="sxs-lookup"><span data-stu-id="d5030-2825">i/c</span></span>
- <span data-ttu-id="d5030-2826">i/c 否</span><span class="sxs-lookup"><span data-stu-id="d5030-2826">i/c no</span></span>
- <span data-ttu-id="d5030-2827">Ic</span><span class="sxs-lookup"><span data-stu-id="d5030-2827">ic</span></span>
- <span data-ttu-id="d5030-2828">內部公司編號</span><span class="sxs-lookup"><span data-stu-id="d5030-2828">ic no</span></span>
- <span data-ttu-id="d5030-2829">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2829">id card</span></span>
- <span data-ttu-id="d5030-2830">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-2830">identification Card</span></span>
- <span data-ttu-id="d5030-2831">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2831">identity card</span></span>
- <span data-ttu-id="d5030-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="d5030-2832">k/p</span></span>
- <span data-ttu-id="d5030-2833">k/p 否</span><span class="sxs-lookup"><span data-stu-id="d5030-2833">k/p no</span></span>
- <span data-ttu-id="d5030-2834">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="d5030-2834">kad akuan diri</span></span>
- <span data-ttu-id="d5030-2835">kad aplikasi 數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="d5030-2836">kad pengenalan 馬來西亞</span><span class="sxs-lookup"><span data-stu-id="d5030-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="d5030-2837">Kp</span><span class="sxs-lookup"><span data-stu-id="d5030-2837">kp</span></span>
- <span data-ttu-id="d5030-2838">kp 否</span><span class="sxs-lookup"><span data-stu-id="d5030-2838">kp no</span></span>
- <span data-ttu-id="d5030-2839">mykad</span><span class="sxs-lookup"><span data-stu-id="d5030-2839">mykad</span></span>
- <span data-ttu-id="d5030-2840">mykas</span><span class="sxs-lookup"><span data-stu-id="d5030-2840">mykas</span></span>
- <span data-ttu-id="d5030-2841">mykid</span><span class="sxs-lookup"><span data-stu-id="d5030-2841">mykid</span></span>
- <span data-ttu-id="d5030-2842">mypr</span><span class="sxs-lookup"><span data-stu-id="d5030-2842">mypr</span></span>
- <span data-ttu-id="d5030-2843">mytentera</span><span class="sxs-lookup"><span data-stu-id="d5030-2843">mytentera</span></span>
- <span data-ttu-id="d5030-2844">馬來西亞身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-2844">malaysia identity card</span></span>
- <span data-ttu-id="d5030-2845">馬來西亞身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-2845">malaysian identity card</span></span>
- <span data-ttu-id="d5030-2846">nric</span><span class="sxs-lookup"><span data-stu-id="d5030-2846">nric</span></span>
- <span data-ttu-id="d5030-2847">個人身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="d5030-2848">荷蘭公民服務（BSN）號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2849">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2849">Format</span></span>

<span data-ttu-id="d5030-2850">8-9 位數包含選擇性空格</span><span class="sxs-lookup"><span data-stu-id="d5030-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2851">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2851">Pattern</span></span>

<span data-ttu-id="d5030-2852">8-9 位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-2852">8-9 digits:</span></span>
- <span data-ttu-id="d5030-2853">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2853">Three digits</span></span> 
- <span data-ttu-id="d5030-2854">一個空格（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-2854">A space (optional)</span></span> 
- <span data-ttu-id="d5030-2855">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2855">Three digits</span></span> 
- <span data-ttu-id="d5030-2856">一個空格（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-2856">A space (optional)</span></span> 
- <span data-ttu-id="d5030-2857">2-3 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2858">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2858">Checksum</span></span>

<span data-ttu-id="d5030-2859">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2860">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2860">Definition</span></span>

<span data-ttu-id="d5030-2861">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2862">函數 Func_netherlands_bsn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2863">會找到來自 Keyword_netherlands_bsn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="d5030-2864">函數 Func_eu_date2 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d5030-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="d5030-2865">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2865">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2866">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="d5030-2867">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="d5030-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="d5030-2868">公民服務號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2868">Citizen service number</span></span> 
- <span data-ttu-id="d5030-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="d5030-2869">BSN</span></span> 
- <span data-ttu-id="d5030-2870">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="d5030-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="d5030-2871">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="d5030-2871">Sofinummer</span></span> 
- <span data-ttu-id="d5030-2872">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="d5030-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="d5030-2873">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="d5030-2874">紐西蘭健康情況號碼的部</span><span class="sxs-lookup"><span data-stu-id="d5030-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2875">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2875">Format</span></span>

<span data-ttu-id="d5030-2876">三個字母、一個空格（選用）及四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2877">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2877">Pattern</span></span>

<span data-ttu-id="d5030-2878">三個字母（不區分大小寫）一個空格（選用）四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2879">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2879">Checksum</span></span>

<span data-ttu-id="d5030-2880">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2881">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2881">Definition</span></span>

<span data-ttu-id="d5030-2882">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2883">函數 Func_new_zealand_ministry_of_health_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2884">會找到來自 Keyword_nz_terms 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="d5030-2885">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2885">The checksum passes.</span></span>

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

<span data-ttu-id="d5030-2886">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2886">Keywords</span></span>

<span data-ttu-id="d5030-2887">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="d5030-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="d5030-2888">NHI</span><span class="sxs-lookup"><span data-stu-id="d5030-2888">NHI</span></span> 
- <span data-ttu-id="d5030-2889">紐西蘭</span><span class="sxs-lookup"><span data-stu-id="d5030-2889">New Zealand</span></span> 
- <span data-ttu-id="d5030-2890">醫療保健</span><span class="sxs-lookup"><span data-stu-id="d5030-2890">Health</span></span> 
- <span data-ttu-id="d5030-2891">治療</span><span class="sxs-lookup"><span data-stu-id="d5030-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="d5030-2892">挪威身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2893">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2893">Format</span></span>

<span data-ttu-id="d5030-2894">11位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2895">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2895">Pattern</span></span>

<span data-ttu-id="d5030-2896">11位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-2896">11 digits:</span></span>
- <span data-ttu-id="d5030-2897">DDMMYY 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="d5030-2898">三位數個人號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="d5030-2899">兩個檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2900">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2900">Checksum</span></span>

<span data-ttu-id="d5030-2901">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2902">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2902">Definition</span></span>

<span data-ttu-id="d5030-2903">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2904">函數 Func_norway_id_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2905">會找到來自 Keyword_norway_id_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="d5030-2906">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2906">The checksum passes.</span></span>
- <span data-ttu-id="d5030-2907">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2908">函數 Func_norway_id_numbe 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2909">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2909">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2910">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="d5030-2911">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="d5030-2912">個人身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2912">Personal identification number</span></span>
- <span data-ttu-id="d5030-2913">挪威文識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="d5030-2914">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2914">ID Number</span></span>
- <span data-ttu-id="d5030-2915">識別</span><span class="sxs-lookup"><span data-stu-id="d5030-2915">Identification</span></span>
- <span data-ttu-id="d5030-2916">Personnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-2916">Personnummer</span></span>
- <span data-ttu-id="d5030-2917">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="d5030-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="d5030-2918">菲律賓統一多用途識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2919">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2919">Format</span></span>

<span data-ttu-id="d5030-2920">以連字號隔開的12位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2921">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2921">Pattern</span></span>

<span data-ttu-id="d5030-2922">12位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-2922">12 digits:</span></span>
- <span data-ttu-id="d5030-2923">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2923">Four digits</span></span> 
- <span data-ttu-id="d5030-2924">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-2924">A hyphen</span></span> 
- <span data-ttu-id="d5030-2925">七位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2925">Seven digits</span></span> 
- <span data-ttu-id="d5030-2926">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-2926">A hyphen</span></span> 
- <span data-ttu-id="d5030-2927">一個數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2928">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2928">Checksum</span></span>

<span data-ttu-id="d5030-2929">否</span><span class="sxs-lookup"><span data-stu-id="d5030-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2930">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2930">Definition</span></span>

<span data-ttu-id="d5030-2931">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2932">正則運算式 Regex_philippines_unified_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2933">會找到來自 Keyword_philippines_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2934">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="d5030-2935">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="d5030-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="d5030-2936">統一的多重用途識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="d5030-2937">UMID</span><span class="sxs-lookup"><span data-stu-id="d5030-2937">UMID</span></span> 
- <span data-ttu-id="d5030-2938">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-2938">Identity Card</span></span> 
- <span data-ttu-id="d5030-2939">Pinag-isang 多 Layunin 識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="d5030-2940">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="d5030-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2941">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2941">Format</span></span>

<span data-ttu-id="d5030-2942">三個字母和六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2943">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2943">Pattern</span></span>

<span data-ttu-id="d5030-2944">三個字母（不區分大小寫）後接六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2945">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2945">Checksum</span></span>

<span data-ttu-id="d5030-2946">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2947">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2947">Definition</span></span>

<span data-ttu-id="d5030-2948">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：函數 Func_polish_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="d5030-2949">會找到來自 Keyword_polish_national_id_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="d5030-2950">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2951">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="d5030-2952">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="d5030-2953">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="d5030-2953">Dowód osobisty</span></span>
- <span data-ttu-id="d5030-2954">轉寄 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="d5030-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="d5030-2955">Nazwa i 轉寄 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="d5030-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="d5030-2956">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="d5030-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="d5030-2957">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="d5030-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="d5030-2958">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="d5030-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="d5030-2959">道鐘斯指數。</span><span class="sxs-lookup"><span data-stu-id="d5030-2959">dow.</span></span> <span data-ttu-id="d5030-2960">作業系統。</span><span class="sxs-lookup"><span data-stu-id="d5030-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="d5030-2961">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="d5030-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2962">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2962">Format</span></span>

<span data-ttu-id="d5030-2963">11位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2964">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2964">Pattern</span></span>

<span data-ttu-id="d5030-2965">11個連續數位</span><span class="sxs-lookup"><span data-stu-id="d5030-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2966">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2966">Checksum</span></span>

<span data-ttu-id="d5030-2967">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2968">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2968">Definition</span></span>

<span data-ttu-id="d5030-2969">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2970">函數 Func_pesel_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2971">會找到來自 Keyword_pesel_identification_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="d5030-2972">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-2973">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="d5030-2974">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="d5030-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="d5030-2975">Nr PESEL</span></span>
- <span data-ttu-id="d5030-2976">PESEL</span><span class="sxs-lookup"><span data-stu-id="d5030-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="d5030-2977">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="d5030-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2978">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2978">Format</span></span>

<span data-ttu-id="d5030-2979">兩個字母和七位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2980">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2980">Pattern</span></span>

<span data-ttu-id="d5030-2981">兩個字母（不區分大小寫）後接7位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-2982">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-2982">Checksum</span></span>

<span data-ttu-id="d5030-2983">是</span><span class="sxs-lookup"><span data-stu-id="d5030-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-2984">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-2984">Definition</span></span>

<span data-ttu-id="d5030-2985">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-2986">函數 Func_polish_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-2987">會找到來自 Keyword_polish_national_id_passport_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="d5030-2988">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-2988">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-2989">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="d5030-2990">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="d5030-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="d5030-2991">轉寄 paszportu</span><span class="sxs-lookup"><span data-stu-id="d5030-2991">Numer paszportu</span></span>
- <span data-ttu-id="d5030-2992">星期日。</span><span class="sxs-lookup"><span data-stu-id="d5030-2992">Nr.</span></span> <span data-ttu-id="d5030-2993">Paszportu</span><span class="sxs-lookup"><span data-stu-id="d5030-2993">Paszportu</span></span>
- <span data-ttu-id="d5030-2994">Paszport</span><span class="sxs-lookup"><span data-stu-id="d5030-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="d5030-2995">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-2996">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-2996">Format</span></span>

<span data-ttu-id="d5030-2997">八位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-2998">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-2998">Pattern</span></span>

<span data-ttu-id="d5030-2999">八位數</span><span class="sxs-lookup"><span data-stu-id="d5030-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3000">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3000">Checksum</span></span>

<span data-ttu-id="d5030-3001">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3002">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3002">Definition</span></span>

<span data-ttu-id="d5030-3003">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3004">正則運算式 Regex_portugal_citizen_card 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3005">會找到來自 Keyword_portugal_citizen_card 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-3006">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="d5030-3007">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="d5030-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="d5030-3008">公民卡片</span><span class="sxs-lookup"><span data-stu-id="d5030-3008">Citizen Card</span></span>
- <span data-ttu-id="d5030-3009">國際身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-3009">National ID Card</span></span>
- <span data-ttu-id="d5030-3010">副本</span><span class="sxs-lookup"><span data-stu-id="d5030-3010">CC</span></span>
- <span data-ttu-id="d5030-3011">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="d5030-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="d5030-3012">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="d5030-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="d5030-3013">沙烏地阿拉伯國際身分識別</span><span class="sxs-lookup"><span data-stu-id="d5030-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3014">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3014">Format</span></span>

<span data-ttu-id="d5030-3015">10位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3016">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3016">Pattern</span></span>

<span data-ttu-id="d5030-3017">10個連續數位</span><span class="sxs-lookup"><span data-stu-id="d5030-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3018">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3018">Checksum</span></span>

<span data-ttu-id="d5030-3019">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3020">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3020">Definition</span></span>

<span data-ttu-id="d5030-3021">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3022">正則運算式 Regex_saudi_arabia_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3023">會找到來自 Keyword_saudi_arabia_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3024">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="d5030-3025">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="d5030-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="d5030-3026">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-3026">Identification Card</span></span> 
- <span data-ttu-id="d5030-3027">我的卡片編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3027">I card number</span></span> 
- <span data-ttu-id="d5030-3028">識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3028">ID number</span></span> 
- <span data-ttu-id="d5030-3029">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="d5030-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="d5030-3030">新加坡國家註冊身分識別卡片（NRIC）號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3031">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3031">Format</span></span>

<span data-ttu-id="d5030-3032">九個字母和數位</span><span class="sxs-lookup"><span data-stu-id="d5030-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3033">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3033">Pattern</span></span>

- <span data-ttu-id="d5030-3034">九個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="d5030-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="d5030-3035">字母 "F"、"G"、"S" 或 "T" （不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="d5030-3036">七位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3036">Seven digits</span></span> 
- <span data-ttu-id="d5030-3037">字母檢查碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3038">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3038">Checksum</span></span>

<span data-ttu-id="d5030-3039">是</span><span class="sxs-lookup"><span data-stu-id="d5030-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3040">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3040">Definition</span></span>

<span data-ttu-id="d5030-3041">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3042">正則運算式 Regex_singapore_nric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3043">會找到來自 Keyword_singapore_nric 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="d5030-3044">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-3044">The checksum passes.</span></span>

<span data-ttu-id="d5030-3045">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3046">正則運算式 Regex_singapore_nric 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3047">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-3047">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3048">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="d5030-3049">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="d5030-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="d5030-3050">國家註冊身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="d5030-3051">身分識別卡號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3051">Identity Card Number</span></span> 
- <span data-ttu-id="d5030-3052">NRIC</span><span class="sxs-lookup"><span data-stu-id="d5030-3052">NRIC</span></span> 
- <span data-ttu-id="d5030-3053">Ic</span><span class="sxs-lookup"><span data-stu-id="d5030-3053">IC</span></span> 
- <span data-ttu-id="d5030-3054">外識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="d5030-3055">翅</span><span class="sxs-lookup"><span data-stu-id="d5030-3055">FIN</span></span> 
- <span data-ttu-id="d5030-3056">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-3056">身份证</span></span> 
- <span data-ttu-id="d5030-3057">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="d5030-3058">南非識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3059">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3059">Format</span></span>

<span data-ttu-id="d5030-3060">可以包含空格的13位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3061">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3061">Pattern</span></span>

<span data-ttu-id="d5030-3062">13位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-3062">13 digits:</span></span>
- <span data-ttu-id="d5030-3063">YYMMDD 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d5030-3064">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3064">Four digits</span></span> 
- <span data-ttu-id="d5030-3065">單一數位的公民指示器</span><span class="sxs-lookup"><span data-stu-id="d5030-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="d5030-3066">數位 "8" 或 "9"</span><span class="sxs-lookup"><span data-stu-id="d5030-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="d5030-3067">一個數位的校驗和位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3068">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3068">Checksum</span></span>

<span data-ttu-id="d5030-3069">是</span><span class="sxs-lookup"><span data-stu-id="d5030-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3070">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3070">Definition</span></span>

<span data-ttu-id="d5030-3071">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3072">函數 Func_south_africa_identification_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3073">會找到來自 Keyword_south_africa_identification_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="d5030-3074">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-3075">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="d5030-3076">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="d5030-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="d5030-3077">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-3077">Identity card</span></span>
- <span data-ttu-id="d5030-3078">ID</span><span class="sxs-lookup"><span data-stu-id="d5030-3078">ID</span></span>
- <span data-ttu-id="d5030-3079">識別</span><span class="sxs-lookup"><span data-stu-id="d5030-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="d5030-3080">韓國居民登記號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3081">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3081">Format</span></span>

<span data-ttu-id="d5030-3082">13位數包含連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3083">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3083">Pattern</span></span>

<span data-ttu-id="d5030-3084">13位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-3084">13 digits:</span></span>
- <span data-ttu-id="d5030-3085">YYMMDD 之日期格式的六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="d5030-3086">連字號</span><span class="sxs-lookup"><span data-stu-id="d5030-3086">A hyphen</span></span> 
- <span data-ttu-id="d5030-3087">一個數位是由世紀和性別決定</span><span class="sxs-lookup"><span data-stu-id="d5030-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="d5030-3088">四位數的出生區功能變數代碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="d5030-3089">一種用來區分先前號碼相同之人員的數位</span><span class="sxs-lookup"><span data-stu-id="d5030-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="d5030-3090">檢查碼。</span><span class="sxs-lookup"><span data-stu-id="d5030-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3091">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3091">Checksum</span></span>

<span data-ttu-id="d5030-3092">是</span><span class="sxs-lookup"><span data-stu-id="d5030-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3093">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3093">Definition</span></span>

<span data-ttu-id="d5030-3094">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3095">函數 Func_south_korea_resident_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3096">會找到來自 Keyword_south_korea_resident_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="d5030-3097">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-3097">The checksum passes.</span></span>

<span data-ttu-id="d5030-3098">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3099">函數 Func_south_korea_resident_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3100">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-3100">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3101">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="d5030-3102">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="d5030-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="d5030-3103">國民身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-3103">National ID card</span></span> 
- <span data-ttu-id="d5030-3104">公民註冊號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="d5030-3105">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="d5030-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="d5030-3106">RRN</span><span class="sxs-lookup"><span data-stu-id="d5030-3106">RRN</span></span> 
- <span data-ttu-id="d5030-3107">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="d5030-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="d5030-3108">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="d5030-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3109">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3109">Format</span></span>

<span data-ttu-id="d5030-3110">11-12 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3111">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3111">Pattern</span></span>

<span data-ttu-id="d5030-3112">11-12 位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-3112">11-12 digits:</span></span>
- <span data-ttu-id="d5030-3113">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3113">Two digits</span></span> 
- <span data-ttu-id="d5030-3114">一個正斜線（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="d5030-3115">7-8 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3115">7-8 digits</span></span> 
- <span data-ttu-id="d5030-3116">一個正斜線（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="d5030-3117">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3118">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3118">Checksum</span></span>

<span data-ttu-id="d5030-3119">是</span><span class="sxs-lookup"><span data-stu-id="d5030-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3120">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3120">Definition</span></span>

<span data-ttu-id="d5030-3121">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3122">函數 Func_spanish_social_security_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3123">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-3124">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3124">Keywords</span></span>

<span data-ttu-id="d5030-3125">無</span><span class="sxs-lookup"><span data-stu-id="d5030-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="d5030-3126">SQL Server 連接字串</span><span class="sxs-lookup"><span data-stu-id="d5030-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3127">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3127">Format</span></span>

<span data-ttu-id="d5030-3128">字串 "User Id"、"User ID"、"uid" 或 "UserId"，後面加上下列模式中所述的字元及字串。</span><span class="sxs-lookup"><span data-stu-id="d5030-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3129">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3129">Pattern</span></span>

- <span data-ttu-id="d5030-3130">字串 "User Id"、"User ID"、"uid" 或 "UserId"</span><span class="sxs-lookup"><span data-stu-id="d5030-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="d5030-3131">介於1-200 小寫或大寫字母、數位、符號、特殊字元或空格之間的任何組合</span><span class="sxs-lookup"><span data-stu-id="d5030-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="d5030-3132">字串 "Password" 或 "pwd"，其中 "pwd" 前面不是小寫字母</span><span class="sxs-lookup"><span data-stu-id="d5030-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="d5030-3133">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-3133">An equal sign (=)</span></span>
- <span data-ttu-id="d5030-3134">不是貨幣符號（$）的任何字元、百分比符號（%）、大於符號（>）、符號（@）、引號（"）、分號（;)、左大括弧（[）或左中括弧（{）</span><span class="sxs-lookup"><span data-stu-id="d5030-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="d5030-3135">任何7-128 個字元的組合，不是分號（;)、正斜線（/）或引號（"）</span><span class="sxs-lookup"><span data-stu-id="d5030-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="d5030-3136">一個分號（;)或引號（"）</span><span class="sxs-lookup"><span data-stu-id="d5030-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3137">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3137">Checksum</span></span>

<span data-ttu-id="d5030-3138">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3139">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3139">Definition</span></span>

<span data-ttu-id="d5030-3140">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3141">正則運算式 CEP_Regex_SQLServerConnectionString 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3142">找**不**到來自 CEP_GlobalFilter 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="d5030-3143">正則運算式**CEP_PasswordPlaceHolder 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3144">正則運算式**CEP_CommonExampleKeywords 不會找到符合**模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3145">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="d5030-3146">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="d5030-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="d5030-3147">部分密碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3147">some-password</span></span>
- <span data-ttu-id="d5030-3148">somepassword</span><span class="sxs-lookup"><span data-stu-id="d5030-3148">somepassword</span></span>
- <span data-ttu-id="d5030-3149">secretPassword</span><span class="sxs-lookup"><span data-stu-id="d5030-3149">secretPassword</span></span>
- <span data-ttu-id="d5030-3150">樣品</span><span class="sxs-lookup"><span data-stu-id="d5030-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="d5030-3151">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="d5030-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="d5030-3152">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="d5030-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d5030-3153">密碼或密碼後接0-2 個空格、等號（=）、0-2 空間及星號（\*）-OR------------------</span><span class="sxs-lookup"><span data-stu-id="d5030-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="d5030-3154">密碼或密碼，接著：</span><span class="sxs-lookup"><span data-stu-id="d5030-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="d5030-3155">等號（=）</span><span class="sxs-lookup"><span data-stu-id="d5030-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="d5030-3156">小於符號（<）</span><span class="sxs-lookup"><span data-stu-id="d5030-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="d5030-3157">1-200 個字元的任何組合，其大小大寫或小寫字母、數位、星號（\*）、連字號（-）、底線（_）或空白字元</span><span class="sxs-lookup"><span data-stu-id="d5030-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="d5030-3158">大於符號（>）</span><span class="sxs-lookup"><span data-stu-id="d5030-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="d5030-3159">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="d5030-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="d5030-3160">（請注意，在技術上而言，這個敏感資訊類型是使用正則運算式來識別這些關鍵字，而不是關鍵字清單。）</span><span class="sxs-lookup"><span data-stu-id="d5030-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="d5030-3161">尚未</span><span class="sxs-lookup"><span data-stu-id="d5030-3161">contoso</span></span>
- <span data-ttu-id="d5030-3162">送交</span><span class="sxs-lookup"><span data-stu-id="d5030-3162">fabrikam</span></span>
- <span data-ttu-id="d5030-3163">資料庫</span><span class="sxs-lookup"><span data-stu-id="d5030-3163">northwind</span></span>
- <span data-ttu-id="d5030-3164">沙 箱</span><span class="sxs-lookup"><span data-stu-id="d5030-3164">sandbox</span></span>
- <span data-ttu-id="d5030-3165">onebox</span><span class="sxs-lookup"><span data-stu-id="d5030-3165">onebox</span></span>
- <span data-ttu-id="d5030-3166">本地 主機</span><span class="sxs-lookup"><span data-stu-id="d5030-3166">localhost</span></span>
- <span data-ttu-id="d5030-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d5030-3167">127.0.0.1</span></span>
- <span data-ttu-id="d5030-3168">testacs.</span><span class="sxs-lookup"><span data-stu-id="d5030-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-3169">Com</span><span class="sxs-lookup"><span data-stu-id="d5030-3169">com</span></span>
- <span data-ttu-id="d5030-3170">s-int。</span><span class="sxs-lookup"><span data-stu-id="d5030-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="d5030-3171">網</span><span class="sxs-lookup"><span data-stu-id="d5030-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="d5030-3172">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="d5030-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3173">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3173">Format</span></span>

<span data-ttu-id="d5030-3174">10或12位數和選擇性分隔符號</span><span class="sxs-lookup"><span data-stu-id="d5030-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3175">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3175">Pattern</span></span>

<span data-ttu-id="d5030-3176">10或12位數和選用的分隔符號：</span><span class="sxs-lookup"><span data-stu-id="d5030-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="d5030-3177">2-4 位數（選用）</span><span class="sxs-lookup"><span data-stu-id="d5030-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="d5030-3178">日期格式 YYMMDD 的六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="d5030-3179">分隔符號 "-" 或 "+" （選用），加上</span><span class="sxs-lookup"><span data-stu-id="d5030-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="d5030-3180">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3181">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3181">Checksum</span></span>

<span data-ttu-id="d5030-3182">是</span><span class="sxs-lookup"><span data-stu-id="d5030-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3183">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3183">Definition</span></span>

<span data-ttu-id="d5030-3184">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3185">函數 Func_swedish_national_identifier 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3186">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-3187">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3187">Keywords</span></span>

<span data-ttu-id="d5030-3188">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="d5030-3189">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3190">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3190">Format</span></span>

<span data-ttu-id="d5030-3191">八位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3192">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3192">Pattern</span></span>

<span data-ttu-id="d5030-3193">八個連續數位</span><span class="sxs-lookup"><span data-stu-id="d5030-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3194">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3194">Checksum</span></span>

<span data-ttu-id="d5030-3195">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3196">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3196">Definition</span></span>

<span data-ttu-id="d5030-3197">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3198">正則運算式 Regex_sweden_passport_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3199">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="d5030-3199">One of the following is true:</span></span>
    - <span data-ttu-id="d5030-3200">會找到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="d5030-3201">會找到來自 Keyword_sweden_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3201">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3202">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="d5030-3203">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="d5030-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="d5030-3204">簽證要求</span><span class="sxs-lookup"><span data-stu-id="d5030-3204">visa requirements</span></span> 
- <span data-ttu-id="d5030-3205">外部註冊卡</span><span class="sxs-lookup"><span data-stu-id="d5030-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="d5030-3206">Schengen 簽證</span><span class="sxs-lookup"><span data-stu-id="d5030-3206">Schengen visas</span></span> 
- <span data-ttu-id="d5030-3207">Schengen 簽證</span><span class="sxs-lookup"><span data-stu-id="d5030-3207">Schengen visa</span></span> 
- <span data-ttu-id="d5030-3208">簽證處理</span><span class="sxs-lookup"><span data-stu-id="d5030-3208">Visa Processing</span></span> 
- <span data-ttu-id="d5030-3209">簽證類型</span><span class="sxs-lookup"><span data-stu-id="d5030-3209">Visa Type</span></span> 
- <span data-ttu-id="d5030-3210">單一專案</span><span class="sxs-lookup"><span data-stu-id="d5030-3210">Single Entry</span></span> 
- <span data-ttu-id="d5030-3211">多重專案</span><span class="sxs-lookup"><span data-stu-id="d5030-3211">Multiple Entry</span></span> 
- <span data-ttu-id="d5030-3212">G3 處理費用</span><span class="sxs-lookup"><span data-stu-id="d5030-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="d5030-3213">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d5030-3213">Keyword_passport</span></span>

- <span data-ttu-id="d5030-3214">護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3214">Passport Number</span></span> 
- <span data-ttu-id="d5030-3215">護照否</span><span class="sxs-lookup"><span data-stu-id="d5030-3215">Passport No</span></span> 
- <span data-ttu-id="d5030-3216">護照#</span><span class="sxs-lookup"><span data-stu-id="d5030-3216">Passport #</span></span> 
- <span data-ttu-id="d5030-3217">護照#</span><span class="sxs-lookup"><span data-stu-id="d5030-3217">Passport#</span></span> 
- <span data-ttu-id="d5030-3218">PassportID</span><span class="sxs-lookup"><span data-stu-id="d5030-3218">PassportID</span></span> 
- <span data-ttu-id="d5030-3219">Passportno</span><span class="sxs-lookup"><span data-stu-id="d5030-3219">Passportno</span></span> 
- <span data-ttu-id="d5030-3220">passportnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-3220">passportnumber</span></span> 
- <span data-ttu-id="d5030-3221">パスポート</span><span class="sxs-lookup"><span data-stu-id="d5030-3221">パスポート</span></span> 
- <span data-ttu-id="d5030-3222">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="d5030-3222">パスポート番号</span></span> 
- <span data-ttu-id="d5030-3223">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d5030-3223">パスポートのNum</span></span> 
- <span data-ttu-id="d5030-3224">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="d5030-3224">パスポート＃</span></span> 
- <span data-ttu-id="d5030-3225">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d5030-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="d5030-3226">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d5030-3226">Passeport n °</span></span> 
- <span data-ttu-id="d5030-3227">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="d5030-3227">Passeport Non</span></span> 
- <span data-ttu-id="d5030-3228">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d5030-3228">Passeport #</span></span> 
- <span data-ttu-id="d5030-3229">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d5030-3229">Passeport#</span></span> 
- <span data-ttu-id="d5030-3230">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d5030-3230">PasseportNon</span></span> 
- <span data-ttu-id="d5030-3231">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d5030-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="d5030-3232">SWIFT 程式碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3233">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3233">Format</span></span>

<span data-ttu-id="d5030-3234">四個字母后接5-31 個字母或數位</span><span class="sxs-lookup"><span data-stu-id="d5030-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3235">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3235">Pattern</span></span>

<span data-ttu-id="d5030-3236">四個字母后接5-31 個字母或數位：</span><span class="sxs-lookup"><span data-stu-id="d5030-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="d5030-3237">四個字母的銀行代碼（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="d5030-3238">選擇性的空格</span><span class="sxs-lookup"><span data-stu-id="d5030-3238">An optional space</span></span> 
- <span data-ttu-id="d5030-3239">4-28 個字母或數位（基本銀行帳戶號碼（BBAN））</span><span class="sxs-lookup"><span data-stu-id="d5030-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="d5030-3240">選擇性的空格</span><span class="sxs-lookup"><span data-stu-id="d5030-3240">An optional space</span></span> 
- <span data-ttu-id="d5030-3241">1-3 個字母或數位（BBAN 的其餘部分）</span><span class="sxs-lookup"><span data-stu-id="d5030-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3242">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3242">Checksum</span></span>

<span data-ttu-id="d5030-3243">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3244">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3244">Definition</span></span>

<span data-ttu-id="d5030-3245">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3246">正則運算式 Regex_swift 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3247">會找到來自 Keyword_swift 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-3248">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="d5030-3249">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="d5030-3249">Keyword_swift</span></span>

- <span data-ttu-id="d5030-3250">標準化9362的國際組織</span><span class="sxs-lookup"><span data-stu-id="d5030-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="d5030-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="d5030-3251">iso 9362</span></span> 
- <span data-ttu-id="d5030-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="d5030-3252">iso9362</span></span> 
- <span data-ttu-id="d5030-3253">迅速\#</span><span class="sxs-lookup"><span data-stu-id="d5030-3253">swift\#</span></span> 
- <span data-ttu-id="d5030-3254">swiftcode</span><span class="sxs-lookup"><span data-stu-id="d5030-3254">swiftcode</span></span> 
- <span data-ttu-id="d5030-3255">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-3255">swiftnumber</span></span> 
- <span data-ttu-id="d5030-3256">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="d5030-3257">swift 程式碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3257">swift code</span></span> 
- <span data-ttu-id="d5030-3258">swift 號碼#</span><span class="sxs-lookup"><span data-stu-id="d5030-3258">swift number #</span></span> 
- <span data-ttu-id="d5030-3259">swift 路由編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3259">swift routing number</span></span> 
- <span data-ttu-id="d5030-3260">bic 編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3260">bic number</span></span> 
- <span data-ttu-id="d5030-3261">bic 程式碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3261">bic code</span></span> 
- <span data-ttu-id="d5030-3262">bic\#</span><span class="sxs-lookup"><span data-stu-id="d5030-3262">bic \#</span></span> 
- <span data-ttu-id="d5030-3263">bic\#</span><span class="sxs-lookup"><span data-stu-id="d5030-3263">bic\#</span></span> 
- <span data-ttu-id="d5030-3264">銀行識別碼代碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3264">bank identifier code</span></span> 
- <span data-ttu-id="d5030-3265">標準化9362</span><span class="sxs-lookup"><span data-stu-id="d5030-3265">標準化9362</span></span> 
- <span data-ttu-id="d5030-3266">迅速＃</span><span class="sxs-lookup"><span data-stu-id="d5030-3266">迅速＃</span></span> 
- <span data-ttu-id="d5030-3267">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="d5030-3267">SWIFTコード</span></span> 
- <span data-ttu-id="d5030-3268">SWIFT番號</span><span class="sxs-lookup"><span data-stu-id="d5030-3268">SWIFT番号</span></span> 
- <span data-ttu-id="d5030-3269">迅速なルーティング番號</span><span class="sxs-lookup"><span data-stu-id="d5030-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="d5030-3270">BIC番號</span><span class="sxs-lookup"><span data-stu-id="d5030-3270">BIC番号</span></span> 
- <span data-ttu-id="d5030-3271">BICコード</span><span class="sxs-lookup"><span data-stu-id="d5030-3271">BICコード</span></span> 
- <span data-ttu-id="d5030-3272">銀行識別コードのための國際組織</span><span class="sxs-lookup"><span data-stu-id="d5030-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="d5030-3273">組織 internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="d5030-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="d5030-3274">rapide\#</span><span class="sxs-lookup"><span data-stu-id="d5030-3274">rapide \#</span></span> 
- <span data-ttu-id="d5030-3275">程式碼 SWIFT</span><span class="sxs-lookup"><span data-stu-id="d5030-3275">code SWIFT</span></span> 
- <span data-ttu-id="d5030-3276">le numéro 解除的 swift</span><span class="sxs-lookup"><span data-stu-id="d5030-3276">le numéro de swift</span></span> 
- <span data-ttu-id="d5030-3277">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="d5030-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="d5030-3278">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="d5030-3278">le numéro BIC</span></span> 
- <span data-ttu-id="d5030-3279">\#BIC</span><span class="sxs-lookup"><span data-stu-id="d5030-3279">\# BIC</span></span> 
- <span data-ttu-id="d5030-3280">程式碼 identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="d5030-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="d5030-3281">臺灣國家 ID</span><span class="sxs-lookup"><span data-stu-id="d5030-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3282">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3282">Format</span></span>

<span data-ttu-id="d5030-3283">一個字母（英文）後後的九位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3284">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3284">Pattern</span></span>

<span data-ttu-id="d5030-3285">一個字母（英文）後接9位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="d5030-3286">一個字母（英文、不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="d5030-3287">數位 "1" 或 "2"</span><span class="sxs-lookup"><span data-stu-id="d5030-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="d5030-3288">八位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3289">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3289">Checksum</span></span>

<span data-ttu-id="d5030-3290">是</span><span class="sxs-lookup"><span data-stu-id="d5030-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3291">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3291">Definition</span></span>

<span data-ttu-id="d5030-3292">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3293">函數 Func_taiwanese_national_id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3294">會找到來自 Keyword_taiwanese_national_id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="d5030-3295">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-3296">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="d5030-3297">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="d5030-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="d5030-3298">身份證字號</span><span class="sxs-lookup"><span data-stu-id="d5030-3298">身份證字號</span></span> 
- <span data-ttu-id="d5030-3299">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-3299">身份證</span></span> 
- <span data-ttu-id="d5030-3300">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3300">身份證號碼</span></span> 
- <span data-ttu-id="d5030-3301">身份證號</span><span class="sxs-lookup"><span data-stu-id="d5030-3301">身份證號</span></span> 
- <span data-ttu-id="d5030-3302">身分證字號</span><span class="sxs-lookup"><span data-stu-id="d5030-3302">身分證字號</span></span> 
- <span data-ttu-id="d5030-3303">身分證</span><span class="sxs-lookup"><span data-stu-id="d5030-3303">身分證</span></span> 
- <span data-ttu-id="d5030-3304">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3304">身分證號碼</span></span> 
- <span data-ttu-id="d5030-3305">身份證號</span><span class="sxs-lookup"><span data-stu-id="d5030-3305">身份證號</span></span> 
- <span data-ttu-id="d5030-3306">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3306">身分證統一編號</span></span> 
- <span data-ttu-id="d5030-3307">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="d5030-3308">簽名</span><span class="sxs-lookup"><span data-stu-id="d5030-3308">簽名</span></span> 
- <span data-ttu-id="d5030-3309">蓋章</span><span class="sxs-lookup"><span data-stu-id="d5030-3309">蓋章</span></span> 
- <span data-ttu-id="d5030-3310">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="d5030-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="d5030-3311">簽章</span><span class="sxs-lookup"><span data-stu-id="d5030-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="d5030-3312">臺灣護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3313">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3313">Format</span></span>

- <span data-ttu-id="d5030-3314">生物識別護照號碼：9位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="d5030-3315">非生物識別護照號碼：9位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3316">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3316">Pattern</span></span>
<span data-ttu-id="d5030-3317">生物識別護照號碼：</span><span class="sxs-lookup"><span data-stu-id="d5030-3317">Biometric passport number:</span></span>
- <span data-ttu-id="d5030-3318">數位 "3"</span><span class="sxs-lookup"><span data-stu-id="d5030-3318">The digit "3"</span></span> 
- <span data-ttu-id="d5030-3319">八位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3319">Eight digits</span></span>

<span data-ttu-id="d5030-3320">無生物識別護照號碼：</span><span class="sxs-lookup"><span data-stu-id="d5030-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="d5030-3321">九位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3322">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3322">Checksum</span></span>

<span data-ttu-id="d5030-3323">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3324">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3324">Definition</span></span>

<span data-ttu-id="d5030-3325">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3326">正則運算式 Regex_taiwan_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3327">會找到來自 Keyword_taiwan_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-3328">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="d5030-3329">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="d5030-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="d5030-3330">ROC 護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3330">ROC passport number</span></span> 
- <span data-ttu-id="d5030-3331">護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3331">Passport number</span></span> 
- <span data-ttu-id="d5030-3332">護照否</span><span class="sxs-lookup"><span data-stu-id="d5030-3332">Passport no</span></span> 
- <span data-ttu-id="d5030-3333">護照編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3333">Passport Num</span></span> 
- <span data-ttu-id="d5030-3334">護照#</span><span class="sxs-lookup"><span data-stu-id="d5030-3334">Passport #</span></span> 
- <span data-ttu-id="d5030-3335">護照</span><span class="sxs-lookup"><span data-stu-id="d5030-3335">护照</span></span> 
- <span data-ttu-id="d5030-3336">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="d5030-3336">中華民國護照</span></span> 
- <span data-ttu-id="d5030-3337">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="d5030-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="d5030-3338">臺灣居民憑證（ARC/TARC）號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3339">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3339">Format</span></span>

<span data-ttu-id="d5030-3340">10個字母和數位</span><span class="sxs-lookup"><span data-stu-id="d5030-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3341">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3341">Pattern</span></span>

<span data-ttu-id="d5030-3342">10個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="d5030-3342">10 letters and digits:</span></span>
- <span data-ttu-id="d5030-3343">兩個字母（不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="d5030-3344">八位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3345">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3345">Checksum</span></span>

<span data-ttu-id="d5030-3346">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3347">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3347">Definition</span></span>

<span data-ttu-id="d5030-3348">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3349">正則運算式 Regex_taiwan_resident_certificate 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3350">會找到來自 Keyword_taiwan_resident_certificate 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-3351">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="d5030-3352">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="d5030-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="d5030-3353">常駐憑證</span><span class="sxs-lookup"><span data-stu-id="d5030-3353">Resident Certificate</span></span> 
- <span data-ttu-id="d5030-3354">常駐 Cert</span><span class="sxs-lookup"><span data-stu-id="d5030-3354">Resident Cert</span></span> 
- <span data-ttu-id="d5030-3355">常駐 Cert。</span><span class="sxs-lookup"><span data-stu-id="d5030-3355">Resident Cert.</span></span> 
- <span data-ttu-id="d5030-3356">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-3356">Identification card</span></span> 
- <span data-ttu-id="d5030-3357">外部居民憑證</span><span class="sxs-lookup"><span data-stu-id="d5030-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="d5030-3358">ARC</span><span class="sxs-lookup"><span data-stu-id="d5030-3358">ARC</span></span> 
- <span data-ttu-id="d5030-3359">臺灣地區常駐憑證</span><span class="sxs-lookup"><span data-stu-id="d5030-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="d5030-3360">TARC</span><span class="sxs-lookup"><span data-stu-id="d5030-3360">TARC</span></span> 
- <span data-ttu-id="d5030-3361">居留證</span><span class="sxs-lookup"><span data-stu-id="d5030-3361">居留證</span></span> 
- <span data-ttu-id="d5030-3362">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="d5030-3362">外僑居留證</span></span> 
- <span data-ttu-id="d5030-3363">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="d5030-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="d5030-3364">泰國人口識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3365">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3365">Format</span></span>

<span data-ttu-id="d5030-3366">13位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3367">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3367">Pattern</span></span>

<span data-ttu-id="d5030-3368">13位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-3368">13 digits:</span></span>
- <span data-ttu-id="d5030-3369">第一個數位不是0或9</span><span class="sxs-lookup"><span data-stu-id="d5030-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="d5030-3370">12位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3371">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3371">Checksum</span></span>

<span data-ttu-id="d5030-3372">是</span><span class="sxs-lookup"><span data-stu-id="d5030-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3373">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3373">Definition</span></span>

<span data-ttu-id="d5030-3374">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3375">函數 Func_Thai_Citizen_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3376">會找到來自 Keyword_Thai_Citizen_Id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="d5030-3377">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3378">函數 Func_Thai_Citizen_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3379">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="d5030-3380">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="d5030-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="d5030-3381">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3381">ID Number</span></span>
- <span data-ttu-id="d5030-3382">識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3382">Identification Number</span></span>
- <span data-ttu-id="d5030-3383">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d5030-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="d5030-3384">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d5030-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="d5030-3385">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d5030-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="d5030-3386">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="d5030-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="d5030-3387">土耳其國身分識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3388">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3388">Format</span></span>

<span data-ttu-id="d5030-3389">11位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3390">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3390">Pattern</span></span>

<span data-ttu-id="d5030-3391">11位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3392">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3392">Checksum</span></span>

<span data-ttu-id="d5030-3393">是</span><span class="sxs-lookup"><span data-stu-id="d5030-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3394">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3394">Definition</span></span>

<span data-ttu-id="d5030-3395">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3396">函數 Func_Turkish_National_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3397">會找到來自 Keyword_Turkish_National_Id 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="d5030-3398">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3399">函數 Func_Turkish_National_Id 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3400">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="d5030-3401">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="d5030-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="d5030-3402">TC Kimlik 否</span><span class="sxs-lookup"><span data-stu-id="d5030-3402">TC Kimlik No</span></span>
- <span data-ttu-id="d5030-3403">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="d5030-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="d5030-3404">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="d5030-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="d5030-3405">Vatandaşlık 否</span><span class="sxs-lookup"><span data-stu-id="d5030-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="d5030-3406">英國。</span><span class="sxs-lookup"><span data-stu-id="d5030-3406">U.K.</span></span> <span data-ttu-id="d5030-3407">駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3407">Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3408">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3408">Format</span></span>

<span data-ttu-id="d5030-3409">以指定格式的18個字母和數位的組合</span><span class="sxs-lookup"><span data-stu-id="d5030-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3410">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3410">Pattern</span></span>

<span data-ttu-id="d5030-3411">18個字母和數位：</span><span class="sxs-lookup"><span data-stu-id="d5030-3411">18 letters and digits:</span></span>
- <span data-ttu-id="d5030-3412">五個字母（不區分大小寫）或數位 "9" 取代字母</span><span class="sxs-lookup"><span data-stu-id="d5030-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="d5030-3413">一個數位</span><span class="sxs-lookup"><span data-stu-id="d5030-3413">One digit</span></span> 
- <span data-ttu-id="d5030-3414">MMDDY 日期格式中的5位數（如果驅動程式是女，則為第7個字元 62 51，而不是1到12，則增加50）</span><span class="sxs-lookup"><span data-stu-id="d5030-3414">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="d5030-3415">兩個字母（不區分大小寫）或數位 "9" 取代字母</span><span class="sxs-lookup"><span data-stu-id="d5030-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="d5030-3416">五位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3417">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3417">Checksum</span></span>

<span data-ttu-id="d5030-3418">是</span><span class="sxs-lookup"><span data-stu-id="d5030-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3419">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3419">Definition</span></span>

<span data-ttu-id="d5030-3420">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3421">函數 Func_uk_drivers_license 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3422">會找到來自 Keyword_uk_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="d5030-3423">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-3424">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="d5030-3425">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d5030-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="d5030-3426">DVLA</span><span class="sxs-lookup"><span data-stu-id="d5030-3426">DVLA</span></span> 
- <span data-ttu-id="d5030-3427">淺 vans</span><span class="sxs-lookup"><span data-stu-id="d5030-3427">light vans</span></span> 
- <span data-ttu-id="d5030-3428">quadbikes</span><span class="sxs-lookup"><span data-stu-id="d5030-3428">quadbikes</span></span> 
- <span data-ttu-id="d5030-3429">汽車轎車</span><span class="sxs-lookup"><span data-stu-id="d5030-3429">motor cars</span></span> 
- <span data-ttu-id="d5030-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="d5030-3430">125cc</span></span> 
- <span data-ttu-id="d5030-3431">sidecar</span><span class="sxs-lookup"><span data-stu-id="d5030-3431">sidecar</span></span> 
- <span data-ttu-id="d5030-3432">三輪車</span><span class="sxs-lookup"><span data-stu-id="d5030-3432">tricycles</span></span> 
- <span data-ttu-id="d5030-3433">摩托車</span><span class="sxs-lookup"><span data-stu-id="d5030-3433">motorcycles</span></span> 
- <span data-ttu-id="d5030-3434">photocard 許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-3434">photocard licence</span></span> 
- <span data-ttu-id="d5030-3435">learner 驅動程式</span><span class="sxs-lookup"><span data-stu-id="d5030-3435">learner drivers</span></span> 
- <span data-ttu-id="d5030-3436">許可證持有者</span><span class="sxs-lookup"><span data-stu-id="d5030-3436">licence holder</span></span> 
- <span data-ttu-id="d5030-3437">許可證持有人</span><span class="sxs-lookup"><span data-stu-id="d5030-3437">licence holders</span></span> 
- <span data-ttu-id="d5030-3438">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-3438">driving licences</span></span> 
- <span data-ttu-id="d5030-3439">駕駛許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-3439">driving licence</span></span> 
- <span data-ttu-id="d5030-3440">雙控制汽車</span><span class="sxs-lookup"><span data-stu-id="d5030-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="d5030-3441">英國。</span><span class="sxs-lookup"><span data-stu-id="d5030-3441">U.K.</span></span> <span data-ttu-id="d5030-3442">Electoral 編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3442">Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3443">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3443">Format</span></span>

<span data-ttu-id="d5030-3444">兩個字母后接1-4 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3445">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3445">Pattern</span></span>

<span data-ttu-id="d5030-3446">兩個字母（不區分大小寫）後接1-4 數目</span><span class="sxs-lookup"><span data-stu-id="d5030-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3447">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3447">Checksum</span></span>

<span data-ttu-id="d5030-3448">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3449">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3449">Definition</span></span>

<span data-ttu-id="d5030-3450">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3451">正則運算式 Regex_uk_electoral 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3452">會找到來自 Keyword_uk_electoral 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3452">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3453">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="d5030-3454">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="d5030-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="d5030-3455">理事會提名</span><span class="sxs-lookup"><span data-stu-id="d5030-3455">council nomination</span></span> 
- <span data-ttu-id="d5030-3456">提名表單</span><span class="sxs-lookup"><span data-stu-id="d5030-3456">nomination form</span></span> 
- <span data-ttu-id="d5030-3457">electoral 寄存器</span><span class="sxs-lookup"><span data-stu-id="d5030-3457">electoral register</span></span> 
- <span data-ttu-id="d5030-3458">electoral 輥</span><span class="sxs-lookup"><span data-stu-id="d5030-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="d5030-3459">英國。</span><span class="sxs-lookup"><span data-stu-id="d5030-3459">U.K.</span></span> <span data-ttu-id="d5030-3460">本國健康情況服務號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3460">National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3461">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3461">Format</span></span>

<span data-ttu-id="d5030-3462">以空格分隔的10-17 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3463">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3463">Pattern</span></span>

<span data-ttu-id="d5030-3464">10-17 位數：</span><span class="sxs-lookup"><span data-stu-id="d5030-3464">10-17 digits:</span></span>
- <span data-ttu-id="d5030-3465">3或10位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="d5030-3466">一個空格</span><span class="sxs-lookup"><span data-stu-id="d5030-3466">A space</span></span> 
- <span data-ttu-id="d5030-3467">三位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3467">Three digits</span></span> 
- <span data-ttu-id="d5030-3468">一個空格</span><span class="sxs-lookup"><span data-stu-id="d5030-3468">A space</span></span> 
- <span data-ttu-id="d5030-3469">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3470">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3470">Checksum</span></span>

<span data-ttu-id="d5030-3471">是</span><span class="sxs-lookup"><span data-stu-id="d5030-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3472">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3472">Definition</span></span>

<span data-ttu-id="d5030-3473">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3474">函數 Func_uk_nhs_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3475">下列其中一項為真：</span><span class="sxs-lookup"><span data-stu-id="d5030-3475">One of the following is true:</span></span>
    - <span data-ttu-id="d5030-3476">會找到來自 Keyword_uk_nhs_number 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="d5030-3477">會找到來自 Keyword_uk_nhs_number1 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="d5030-3478">會找到來自 Keyword_uk_nhs_number_dob 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="d5030-3479">校驗和通過。</span><span class="sxs-lookup"><span data-stu-id="d5030-3479">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3480">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="d5030-3481">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="d5030-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="d5030-3482">全國健康情況服務</span><span class="sxs-lookup"><span data-stu-id="d5030-3482">national health service</span></span> 
- <span data-ttu-id="d5030-3483">Nhs</span><span class="sxs-lookup"><span data-stu-id="d5030-3483">nhs</span></span> 
- <span data-ttu-id="d5030-3484">健康情況服務授權</span><span class="sxs-lookup"><span data-stu-id="d5030-3484">health services authority</span></span> 
- <span data-ttu-id="d5030-3485">健康情況授權單位</span><span class="sxs-lookup"><span data-stu-id="d5030-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="d5030-3486">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="d5030-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="d5030-3487">患者識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3487">patient id</span></span> 
- <span data-ttu-id="d5030-3488">患者識別</span><span class="sxs-lookup"><span data-stu-id="d5030-3488">patient identification</span></span> 
- <span data-ttu-id="d5030-3489">患者否</span><span class="sxs-lookup"><span data-stu-id="d5030-3489">patient no</span></span> 
- <span data-ttu-id="d5030-3490">病人編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="d5030-3491">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="d5030-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="d5030-3492">Gp</span><span class="sxs-lookup"><span data-stu-id="d5030-3492">GP</span></span> 
- <span data-ttu-id="d5030-3493">DOB</span><span class="sxs-lookup"><span data-stu-id="d5030-3493">DOB</span></span> 
- <span data-ttu-id="d5030-3494">D. B</span><span class="sxs-lookup"><span data-stu-id="d5030-3494">D.O.B</span></span> 
- <span data-ttu-id="d5030-3495">出生日期</span><span class="sxs-lookup"><span data-stu-id="d5030-3495">Date of Birth</span></span> 
- <span data-ttu-id="d5030-3496">出生日期</span><span class="sxs-lookup"><span data-stu-id="d5030-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="d5030-3497">英國。</span><span class="sxs-lookup"><span data-stu-id="d5030-3497">U.K.</span></span> <span data-ttu-id="d5030-3498">本國保險號碼（NINO）</span><span class="sxs-lookup"><span data-stu-id="d5030-3498">National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3499">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3499">Format</span></span>

<span data-ttu-id="d5030-3500">以空格或破折號分隔的7個字元或9個字元</span><span class="sxs-lookup"><span data-stu-id="d5030-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3501">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3501">Pattern</span></span>

<span data-ttu-id="d5030-3502">兩種可能的模式：</span><span class="sxs-lookup"><span data-stu-id="d5030-3502">Two possible patterns:</span></span>

- <span data-ttu-id="d5030-3503">兩個字母（有效的 NINOs 只會使用此前置詞中的特定字元，此模式會驗證; 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="d5030-3504">六位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3504">Six digits</span></span>
- <span data-ttu-id="d5030-3505">"A"、"B"、"C" 或 "d" （類似前置詞）只允許在尾碼中使用某些字元; 不區分大小寫）</span><span class="sxs-lookup"><span data-stu-id="d5030-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="d5030-3506">OR</span><span class="sxs-lookup"><span data-stu-id="d5030-3506">OR</span></span>

- <span data-ttu-id="d5030-3507">兩個字母</span><span class="sxs-lookup"><span data-stu-id="d5030-3507">Two letters</span></span>
- <span data-ttu-id="d5030-3508">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="d5030-3508">A space or dash</span></span>
- <span data-ttu-id="d5030-3509">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3509">Two digits</span></span>
- <span data-ttu-id="d5030-3510">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="d5030-3510">A space or dash</span></span>
- <span data-ttu-id="d5030-3511">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3511">Two digits</span></span>
- <span data-ttu-id="d5030-3512">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="d5030-3512">A space or dash</span></span>
- <span data-ttu-id="d5030-3513">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3513">Two digits</span></span>
- <span data-ttu-id="d5030-3514">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="d5030-3514">A space or dash</span></span>
- <span data-ttu-id="d5030-3515">' A '、' B '、' C ' 或 ' d ' 是 '</span><span class="sxs-lookup"><span data-stu-id="d5030-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3516">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3516">Checksum</span></span>

<span data-ttu-id="d5030-3517">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3518">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3518">Definition</span></span>

<span data-ttu-id="d5030-3519">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3520">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3521">會找到來自 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="d5030-3522">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3523">函數 Func_uk_nino 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3524">找不到 Keyword_uk_nino 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3524">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3525">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="d5030-3526">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="d5030-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="d5030-3527">本國保險號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3527">national insurance number</span></span> 
- <span data-ttu-id="d5030-3528">全國保險貢獻</span><span class="sxs-lookup"><span data-stu-id="d5030-3528">national insurance contributions</span></span> 
- <span data-ttu-id="d5030-3529">保護法案</span><span class="sxs-lookup"><span data-stu-id="d5030-3529">protection act</span></span> 
- <span data-ttu-id="d5030-3530">保險</span><span class="sxs-lookup"><span data-stu-id="d5030-3530">insurance</span></span> 
- <span data-ttu-id="d5030-3531">社會安全號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3531">social security number</span></span> 
- <span data-ttu-id="d5030-3532">保險費應用程式</span><span class="sxs-lookup"><span data-stu-id="d5030-3532">insurance application</span></span> 
- <span data-ttu-id="d5030-3533">醫療應用程式</span><span class="sxs-lookup"><span data-stu-id="d5030-3533">medical application</span></span> 
- <span data-ttu-id="d5030-3534">社交保險</span><span class="sxs-lookup"><span data-stu-id="d5030-3534">social insurance</span></span> 
- <span data-ttu-id="d5030-3535">醫療注意力</span><span class="sxs-lookup"><span data-stu-id="d5030-3535">medical attention</span></span> 
- <span data-ttu-id="d5030-3536">社會保障</span><span class="sxs-lookup"><span data-stu-id="d5030-3536">social security</span></span> 
- <span data-ttu-id="d5030-3537">英國</span><span class="sxs-lookup"><span data-stu-id="d5030-3537">great britain</span></span> 
- <span data-ttu-id="d5030-3538">保險</span><span class="sxs-lookup"><span data-stu-id="d5030-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="d5030-3539">美國/英國</span><span class="sxs-lookup"><span data-stu-id="d5030-3539">U.S. / U.K.</span></span> <span data-ttu-id="d5030-3540">護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3540">Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3541">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3541">Format</span></span>

<span data-ttu-id="d5030-3542">九位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3543">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3543">Pattern</span></span>

<span data-ttu-id="d5030-3544">九個連續數位</span><span class="sxs-lookup"><span data-stu-id="d5030-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3545">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3545">Checksum</span></span>

<span data-ttu-id="d5030-3546">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3547">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3547">Definition</span></span>

<span data-ttu-id="d5030-3548">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3549">函數 Func_usa_uk_passport 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3550">會找到來自 Keyword_passport 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-3551">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="d5030-3552">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="d5030-3552">Keyword_passport</span></span>

- <span data-ttu-id="d5030-3553">護照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3553">Passport Number</span></span> 
- <span data-ttu-id="d5030-3554">護照否</span><span class="sxs-lookup"><span data-stu-id="d5030-3554">Passport No</span></span> 
- <span data-ttu-id="d5030-3555">護照#</span><span class="sxs-lookup"><span data-stu-id="d5030-3555">Passport #</span></span> 
- <span data-ttu-id="d5030-3556">護照#</span><span class="sxs-lookup"><span data-stu-id="d5030-3556">Passport#</span></span> 
- <span data-ttu-id="d5030-3557">PassportID</span><span class="sxs-lookup"><span data-stu-id="d5030-3557">PassportID</span></span> 
- <span data-ttu-id="d5030-3558">Passportno</span><span class="sxs-lookup"><span data-stu-id="d5030-3558">Passportno</span></span> 
- <span data-ttu-id="d5030-3559">passportnumber</span><span class="sxs-lookup"><span data-stu-id="d5030-3559">passportnumber</span></span> 
- <span data-ttu-id="d5030-3560">パスポート</span><span class="sxs-lookup"><span data-stu-id="d5030-3560">パスポート</span></span> 
- <span data-ttu-id="d5030-3561">パスポート番號</span><span class="sxs-lookup"><span data-stu-id="d5030-3561">パスポート番号</span></span> 
- <span data-ttu-id="d5030-3562">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="d5030-3562">パスポートのNum</span></span> 
- <span data-ttu-id="d5030-3563">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="d5030-3563">パスポート＃</span></span> 
- <span data-ttu-id="d5030-3564">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="d5030-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="d5030-3565">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="d5030-3565">Passeport n °</span></span> 
- <span data-ttu-id="d5030-3566">Passeport 非</span><span class="sxs-lookup"><span data-stu-id="d5030-3566">Passeport Non</span></span> 
- <span data-ttu-id="d5030-3567">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d5030-3567">Passeport #</span></span> 
- <span data-ttu-id="d5030-3568">Passeport#</span><span class="sxs-lookup"><span data-stu-id="d5030-3568">Passeport#</span></span> 
- <span data-ttu-id="d5030-3569">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="d5030-3569">PasseportNon</span></span> 
- <span data-ttu-id="d5030-3570">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="d5030-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="d5030-3571">美國銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3572">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3572">Format</span></span>

<span data-ttu-id="d5030-3573">8-17 位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3574">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3574">Pattern</span></span>

<span data-ttu-id="d5030-3575">8-17 連續位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3576">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3576">Checksum</span></span>

<span data-ttu-id="d5030-3577">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3578">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3578">Definition</span></span>

<span data-ttu-id="d5030-3579">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3580">正則運算式 Regex_usa_bank_account_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3581">會找到來自 Keyword_usa_Bank_Account 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d5030-3582">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="d5030-3583">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="d5030-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="d5030-3584">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3584">Checking Account Number</span></span> 
- <span data-ttu-id="d5030-3585">檢查帳戶</span><span class="sxs-lookup"><span data-stu-id="d5030-3585">Checking Account</span></span> 
- <span data-ttu-id="d5030-3586">檢查帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-3586">Checking Account #</span></span> 
- <span data-ttu-id="d5030-3587">檢查帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="d5030-3588">檢查帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-3588">Checking Acct #</span></span> 
- <span data-ttu-id="d5030-3589">檢查帳戶否。</span><span class="sxs-lookup"><span data-stu-id="d5030-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="d5030-3590">檢查帳戶否</span><span class="sxs-lookup"><span data-stu-id="d5030-3590">Checking Account No.</span></span> 
- <span data-ttu-id="d5030-3591">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3591">Bank Account Number</span></span> 
- <span data-ttu-id="d5030-3592">銀行帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-3592">Bank Account #</span></span> 
- <span data-ttu-id="d5030-3593">銀行帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="d5030-3594">銀行帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-3594">Bank Acct #</span></span> 
- <span data-ttu-id="d5030-3595">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="d5030-3596">銀行帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3596">Bank Account No.</span></span> 
- <span data-ttu-id="d5030-3597">儲蓄帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3597">Savings Account Number</span></span> 
- <span data-ttu-id="d5030-3598">儲蓄帳戶。</span><span class="sxs-lookup"><span data-stu-id="d5030-3598">Savings Account.</span></span> 
- <span data-ttu-id="d5030-3599">儲蓄帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-3599">Savings Account #</span></span> 
- <span data-ttu-id="d5030-3600">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="d5030-3601">儲蓄帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-3601">Savings Acct #</span></span> 
- <span data-ttu-id="d5030-3602">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="d5030-3603">儲蓄帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3603">Savings Account No.</span></span> 
- <span data-ttu-id="d5030-3604">借方科目編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3604">Debit Account Number</span></span> 
- <span data-ttu-id="d5030-3605">借方科目</span><span class="sxs-lookup"><span data-stu-id="d5030-3605">Debit Account</span></span> 
- <span data-ttu-id="d5030-3606">借方科目#</span><span class="sxs-lookup"><span data-stu-id="d5030-3606">Debit Account #</span></span> 
- <span data-ttu-id="d5030-3607">借方帳戶號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="d5030-3608">借方帳戶#</span><span class="sxs-lookup"><span data-stu-id="d5030-3608">Debit Acct #</span></span> 
- <span data-ttu-id="d5030-3609">借方帳戶編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="d5030-3610">借方科目編號</span><span class="sxs-lookup"><span data-stu-id="d5030-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="d5030-3611">美國駕駛執照號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3612">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3612">Format</span></span>

<span data-ttu-id="d5030-3613">取決於狀態</span><span class="sxs-lookup"><span data-stu-id="d5030-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3614">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3614">Pattern</span></span>

<span data-ttu-id="d5030-3615">取決於狀態--例如紐約：</span><span class="sxs-lookup"><span data-stu-id="d5030-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="d5030-3616">已格式化的九位數，如 ddd ddd ddd 會相符。</span><span class="sxs-lookup"><span data-stu-id="d5030-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="d5030-3617">九位數的 ddddddddd 不相符。</span><span class="sxs-lookup"><span data-stu-id="d5030-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3618">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3618">Checksum</span></span>

<span data-ttu-id="d5030-3619">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3620">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3620">Definition</span></span>

<span data-ttu-id="d5030-3621">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3622">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3623">找到來自 Keyword_ [state_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="d5030-3624">會找到來自 Keyword_us_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="d5030-3625">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3626">函數 Func_new_york_drivers_license_number 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3627">找到來自 Keyword_ [state_name] _drivers_license_name 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="d5030-3628">會找到來自 Keyword_us_drivers_license_abbreviations 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="d5030-3629">找不到 Keyword_us_drivers_license 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3630">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="d5030-3631">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="d5030-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="d5030-3632">Dl</span><span class="sxs-lookup"><span data-stu-id="d5030-3632">DL</span></span> 
- <span data-ttu-id="d5030-3633">Dls</span><span class="sxs-lookup"><span data-stu-id="d5030-3633">DLS</span></span> 
- <span data-ttu-id="d5030-3634">民盟</span><span class="sxs-lookup"><span data-stu-id="d5030-3634">CDL</span></span> 
- <span data-ttu-id="d5030-3635">CDLS</span><span class="sxs-lookup"><span data-stu-id="d5030-3635">CDLS</span></span> 
- <span data-ttu-id="d5030-3636">ID</span><span class="sxs-lookup"><span data-stu-id="d5030-3636">ID</span></span> 
- <span data-ttu-id="d5030-3637">IDs</span><span class="sxs-lookup"><span data-stu-id="d5030-3637">IDs</span></span> 
- <span data-ttu-id="d5030-3638">Dl#</span><span class="sxs-lookup"><span data-stu-id="d5030-3638">DL#</span></span> 
- <span data-ttu-id="d5030-3639">Dls#</span><span class="sxs-lookup"><span data-stu-id="d5030-3639">DLS#</span></span> 
- <span data-ttu-id="d5030-3640">民盟#</span><span class="sxs-lookup"><span data-stu-id="d5030-3640">CDL#</span></span> 
- <span data-ttu-id="d5030-3641">CDLS#</span><span class="sxs-lookup"><span data-stu-id="d5030-3641">CDLS#</span></span> 
- <span data-ttu-id="d5030-3642">ID:#</span><span class="sxs-lookup"><span data-stu-id="d5030-3642">ID#</span></span>
- <span data-ttu-id="d5030-3643">IDs#</span><span class="sxs-lookup"><span data-stu-id="d5030-3643">IDs#</span></span> 
- <span data-ttu-id="d5030-3644">識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3644">ID number</span></span> 
- <span data-ttu-id="d5030-3645">識別碼號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3645">ID numbers</span></span> 
- <span data-ttu-id="d5030-3646">許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-3646">LIC</span></span> 
- <span data-ttu-id="d5030-3647">許可證#</span><span class="sxs-lookup"><span data-stu-id="d5030-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="d5030-3648">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="d5030-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="d5030-3649">DriverLic</span><span class="sxs-lookup"><span data-stu-id="d5030-3649">DriverLic</span></span> 
- <span data-ttu-id="d5030-3650">DriverLics</span><span class="sxs-lookup"><span data-stu-id="d5030-3650">DriverLics</span></span> 
- <span data-ttu-id="d5030-3651">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="d5030-3651">DriverLicense</span></span> 
- <span data-ttu-id="d5030-3652">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="d5030-3652">DriverLicenses</span></span> 
- <span data-ttu-id="d5030-3653">驅動程式許可證</span><span class="sxs-lookup"><span data-stu-id="d5030-3653">Driver Lic</span></span> 
- <span data-ttu-id="d5030-3654">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-3654">Driver Lics</span></span> 
- <span data-ttu-id="d5030-3655">駕照</span><span class="sxs-lookup"><span data-stu-id="d5030-3655">Driver License</span></span> 
- <span data-ttu-id="d5030-3656">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-3656">Driver Licenses</span></span> 
- <span data-ttu-id="d5030-3657">DriversLic</span><span class="sxs-lookup"><span data-stu-id="d5030-3657">DriversLic</span></span> 
- <span data-ttu-id="d5030-3658">DriversLics</span><span class="sxs-lookup"><span data-stu-id="d5030-3658">DriversLics</span></span> 
- <span data-ttu-id="d5030-3659">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="d5030-3659">DriversLicense</span></span> 
- <span data-ttu-id="d5030-3660">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="d5030-3660">DriversLicenses</span></span> 
- <span data-ttu-id="d5030-3661">驅動程式 .Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-3661">Drivers Lic</span></span> 
- <span data-ttu-id="d5030-3662">驅動程式 Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-3662">Drivers Lics</span></span> 
- <span data-ttu-id="d5030-3663">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-3663">Drivers License</span></span> 
- <span data-ttu-id="d5030-3664">驅動程式授權</span><span class="sxs-lookup"><span data-stu-id="d5030-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="d5030-3665">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-3665">Driver'Lic</span></span> 
- <span data-ttu-id="d5030-3666">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-3666">Driver'Lics</span></span> 
- <span data-ttu-id="d5030-3667">Driver'License</span><span class="sxs-lookup"><span data-stu-id="d5030-3667">Driver'License</span></span> 
- <span data-ttu-id="d5030-3668">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="d5030-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="d5030-3669">驅動程式「.Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-3669">Driver' Lic</span></span> 
- <span data-ttu-id="d5030-3670">驅動程式 ' Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-3670">Driver' Lics</span></span> 
- <span data-ttu-id="d5030-3671">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-3671">Driver' License</span></span> 
- <span data-ttu-id="d5030-3672">驅動程式的授權</span><span class="sxs-lookup"><span data-stu-id="d5030-3672">Driver' Licenses</span></span>
- <span data-ttu-id="d5030-3673">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="d5030-3673">Driver'sLic</span></span> 
- <span data-ttu-id="d5030-3674">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="d5030-3674">Driver'sLics</span></span> 
- <span data-ttu-id="d5030-3675">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="d5030-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="d5030-3676">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="d5030-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="d5030-3677">驅動程式的 .Lic</span><span class="sxs-lookup"><span data-stu-id="d5030-3677">Driver's Lic</span></span> 
- <span data-ttu-id="d5030-3678">驅動程式的 Lics</span><span class="sxs-lookup"><span data-stu-id="d5030-3678">Driver's Lics</span></span> 
- <span data-ttu-id="d5030-3679">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-3679">Driver's License</span></span> 
- <span data-ttu-id="d5030-3680">駕駛執照</span><span class="sxs-lookup"><span data-stu-id="d5030-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="d5030-3681">識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3681">identification number</span></span> 
- <span data-ttu-id="d5030-3682">識別號碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3682">identification numbers</span></span> 
- <span data-ttu-id="d5030-3683">識別#</span><span class="sxs-lookup"><span data-stu-id="d5030-3683">identification #</span></span> 
- <span data-ttu-id="d5030-3684">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-3684">id card</span></span> 
- <span data-ttu-id="d5030-3685">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-3685">id cards</span></span> 
- <span data-ttu-id="d5030-3686">身分識別卡</span><span class="sxs-lookup"><span data-stu-id="d5030-3686">identification card</span></span> 
- <span data-ttu-id="d5030-3687">身份證</span><span class="sxs-lookup"><span data-stu-id="d5030-3687">identification cards</span></span> 
- <span data-ttu-id="d5030-3688">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="d5030-3688">DriverLic#</span></span> 
- <span data-ttu-id="d5030-3689">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="d5030-3689">DriverLics#</span></span> 
- <span data-ttu-id="d5030-3690">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="d5030-3690">DriverLicense#</span></span> 
- <span data-ttu-id="d5030-3691">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="d5030-3692">驅動程式許可證#</span><span class="sxs-lookup"><span data-stu-id="d5030-3692">Driver Lic#</span></span> 
- <span data-ttu-id="d5030-3693">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-3693">Driver Lics#</span></span> 
- <span data-ttu-id="d5030-3694">駕照#</span><span class="sxs-lookup"><span data-stu-id="d5030-3694">Driver License#</span></span> 
- <span data-ttu-id="d5030-3695">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="d5030-3696">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="d5030-3696">DriversLic#</span></span> 
- <span data-ttu-id="d5030-3697">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="d5030-3697">DriversLics#</span></span> 
- <span data-ttu-id="d5030-3698">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="d5030-3698">DriversLicense#</span></span> 
- <span data-ttu-id="d5030-3699">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="d5030-3700">驅動程式 .Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="d5030-3701">驅動程式 Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="d5030-3702">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-3702">Drivers License#</span></span> 
- <span data-ttu-id="d5030-3703">驅動程式授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="d5030-3704">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="d5030-3705">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="d5030-3706">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="d5030-3706">Driver'License#</span></span> 
- <span data-ttu-id="d5030-3707">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="d5030-3708">驅動程式「.Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="d5030-3709">驅動程式 ' Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="d5030-3710">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-3710">Driver' License#</span></span> 
- <span data-ttu-id="d5030-3711">驅動程式的授權#</span><span class="sxs-lookup"><span data-stu-id="d5030-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="d5030-3712">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="d5030-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="d5030-3713">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="d5030-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="d5030-3714">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="d5030-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="d5030-3715">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="d5030-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="d5030-3716">驅動程式的 .Lic#</span><span class="sxs-lookup"><span data-stu-id="d5030-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="d5030-3717">驅動程式的 Lics#</span><span class="sxs-lookup"><span data-stu-id="d5030-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="d5030-3718">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-3718">Driver's License#</span></span> 
- <span data-ttu-id="d5030-3719">駕駛執照#</span><span class="sxs-lookup"><span data-stu-id="d5030-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="d5030-3720">身份證#</span><span class="sxs-lookup"><span data-stu-id="d5030-3720">id card#</span></span> 
- <span data-ttu-id="d5030-3721">身份證#</span><span class="sxs-lookup"><span data-stu-id="d5030-3721">id cards#</span></span> 
- <span data-ttu-id="d5030-3722">身分識別卡#</span><span class="sxs-lookup"><span data-stu-id="d5030-3722">identification card#</span></span> 
- <span data-ttu-id="d5030-3723">身份證#</span><span class="sxs-lookup"><span data-stu-id="d5030-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="d5030-3724">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="d5030-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="d5030-3725">省/市/自治區縮寫（例如，"NY"）</span><span class="sxs-lookup"><span data-stu-id="d5030-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="d5030-3726">狀態名稱（例如，"紐約"）</span><span class="sxs-lookup"><span data-stu-id="d5030-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="d5030-3727">美國個別的納稅人識別號碼（ITIN）</span><span class="sxs-lookup"><span data-stu-id="d5030-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3728">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3728">Format</span></span>

<span data-ttu-id="d5030-3729">以 "9" 開頭且包含 "7" 或 "8" 的九位數做為第四位數，可選擇性地使用空格或破折號格式化</span><span class="sxs-lookup"><span data-stu-id="d5030-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3730">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3730">Pattern</span></span>

<span data-ttu-id="d5030-3731">格式 化：</span><span class="sxs-lookup"><span data-stu-id="d5030-3731">Formatted:</span></span>
- <span data-ttu-id="d5030-3732">數位 "9"</span><span class="sxs-lookup"><span data-stu-id="d5030-3732">The digit "9"</span></span> 
- <span data-ttu-id="d5030-3733">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3733">Two digits</span></span> 
- <span data-ttu-id="d5030-3734">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="d5030-3734">A space or dash</span></span> 
- <span data-ttu-id="d5030-3735">"7" 或 "8"</span><span class="sxs-lookup"><span data-stu-id="d5030-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="d5030-3736">一個數位</span><span class="sxs-lookup"><span data-stu-id="d5030-3736">A digit</span></span> 
- <span data-ttu-id="d5030-3737">一個空格或破折號</span><span class="sxs-lookup"><span data-stu-id="d5030-3737">A space, or dash</span></span> 
- <span data-ttu-id="d5030-3738">四位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3738">Four digits</span></span>

<span data-ttu-id="d5030-3739">非</span><span class="sxs-lookup"><span data-stu-id="d5030-3739">Unformatted:</span></span>
- <span data-ttu-id="d5030-3740">數位 "9"</span><span class="sxs-lookup"><span data-stu-id="d5030-3740">The digit "9"</span></span> 
- <span data-ttu-id="d5030-3741">兩位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3741">Two digits</span></span> 
- <span data-ttu-id="d5030-3742">"7" 或 "8"</span><span class="sxs-lookup"><span data-stu-id="d5030-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="d5030-3743">五位數</span><span class="sxs-lookup"><span data-stu-id="d5030-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3744">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3744">Checksum</span></span>

<span data-ttu-id="d5030-3745">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="d5030-3746">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3746">Definition</span></span>

<span data-ttu-id="d5030-3747">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3748">函數 Func_formatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3749">下列專案中至少有一個為真：</span><span class="sxs-lookup"><span data-stu-id="d5030-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="d5030-3750">會找到來自 Keyword_itin 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="d5030-3751">函數 Func_us_address 會找到正確日期格式的位址。</span><span class="sxs-lookup"><span data-stu-id="d5030-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="d5030-3752">函數 Func_us_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d5030-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="d5030-3753">會找到來自 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="d5030-3754">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3755">函數 Func_unformatted_itin 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3756">下列專案中至少有一個為真：</span><span class="sxs-lookup"><span data-stu-id="d5030-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="d5030-3757">會找到來自 Keyword_itin_collaborative 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="d5030-3758">函數 Func_us_address 會找到正確日期格式的位址。</span><span class="sxs-lookup"><span data-stu-id="d5030-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="d5030-3759">函數 Func_us_date 會找到正確日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d5030-3759">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="d5030-3760">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="d5030-3761">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="d5030-3761">Keyword_itin</span></span>

- <span data-ttu-id="d5030-3762">納稅人</span><span class="sxs-lookup"><span data-stu-id="d5030-3762">taxpayer</span></span> 
- <span data-ttu-id="d5030-3763">納稅識別碼</span><span class="sxs-lookup"><span data-stu-id="d5030-3763">tax id</span></span> 
- <span data-ttu-id="d5030-3764">納稅識別</span><span class="sxs-lookup"><span data-stu-id="d5030-3764">tax identification</span></span> 
- <span data-ttu-id="d5030-3765">itin</span><span class="sxs-lookup"><span data-stu-id="d5030-3765">itin</span></span> 
- <span data-ttu-id="d5030-3766">Ssn</span><span class="sxs-lookup"><span data-stu-id="d5030-3766">ssn</span></span> 
- <span data-ttu-id="d5030-3767">錫</span><span class="sxs-lookup"><span data-stu-id="d5030-3767">tin</span></span> 
- <span data-ttu-id="d5030-3768">社會保障</span><span class="sxs-lookup"><span data-stu-id="d5030-3768">social security</span></span> 
- <span data-ttu-id="d5030-3769">納稅人</span><span class="sxs-lookup"><span data-stu-id="d5030-3769">tax payer</span></span> 
- <span data-ttu-id="d5030-3770">itins</span><span class="sxs-lookup"><span data-stu-id="d5030-3770">itins</span></span> 
- <span data-ttu-id="d5030-3771">taxid</span><span class="sxs-lookup"><span data-stu-id="d5030-3771">taxid</span></span> 
- <span data-ttu-id="d5030-3772">個別納稅人</span><span class="sxs-lookup"><span data-stu-id="d5030-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="d5030-3773">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="d5030-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="d5030-3774">License</span><span class="sxs-lookup"><span data-stu-id="d5030-3774">License</span></span> 
- <span data-ttu-id="d5030-3775">Dl</span><span class="sxs-lookup"><span data-stu-id="d5030-3775">DL</span></span> 
- <span data-ttu-id="d5030-3776">DOB</span><span class="sxs-lookup"><span data-stu-id="d5030-3776">DOB</span></span> 
- <span data-ttu-id="d5030-3777">出生日期</span><span class="sxs-lookup"><span data-stu-id="d5030-3777">Birthdate</span></span> 
- <span data-ttu-id="d5030-3778">生日</span><span class="sxs-lookup"><span data-stu-id="d5030-3778">Birthday</span></span> 
- <span data-ttu-id="d5030-3779">出生日期</span><span class="sxs-lookup"><span data-stu-id="d5030-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="d5030-3780">U.S. 社會安全號碼（SSN）</span><span class="sxs-lookup"><span data-stu-id="d5030-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="d5030-3781">格式</span><span class="sxs-lookup"><span data-stu-id="d5030-3781">Format</span></span>

<span data-ttu-id="d5030-3782">9位數（可能是格式化或未格式化的模式）</span><span class="sxs-lookup"><span data-stu-id="d5030-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="d5030-3783">如果在2011之前發出，則 SSN 具有強格式，其中的號碼的某些部分必須介於一定範圍內，才是有效的（但沒有任何 checksum）。</span><span class="sxs-lookup"><span data-stu-id="d5030-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="d5030-3784">模式</span><span class="sxs-lookup"><span data-stu-id="d5030-3784">Pattern</span></span>

<span data-ttu-id="d5030-3785">四種功能會在四種不同的模式中尋找主旨 ssn：</span><span class="sxs-lookup"><span data-stu-id="d5030-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="d5030-3786">Func_ssn 會2011以主旨 ssn 的強格式格式化，並以短劃線或空格格式化（ddd-dd-dddd 或 ddd dd dddd）來尋找</span><span class="sxs-lookup"><span data-stu-id="d5030-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="d5030-3787">Func_unformatted_ssn 會以預先2011的強格式格式化，以格式化為九個連續數位（ddddddddd）的主旨 ssn，來尋找</span><span class="sxs-lookup"><span data-stu-id="d5030-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="d5030-3788">Func_randomized_formatted_ssn 會找到以短劃線或空格格式化的2011後主旨 ssn （ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="d5030-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="d5030-3789">Func_randomized_unformatted_ssn 尋找未格式化為九個連續數位的2011後主旨 ssn （ddddddddd）</span><span class="sxs-lookup"><span data-stu-id="d5030-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="d5030-3790">校驗</span><span class="sxs-lookup"><span data-stu-id="d5030-3790">Checksum</span></span>

<span data-ttu-id="d5030-3791">否</span><span class="sxs-lookup"><span data-stu-id="d5030-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="d5030-3792">定義</span><span class="sxs-lookup"><span data-stu-id="d5030-3792">Definition</span></span>

<span data-ttu-id="d5030-3793">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是85%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3794">函數 Func_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3795">會找到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3795">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="d5030-3796">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是75%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3797">函數 Func_unformatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3797">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3798">會找到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3798">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="d5030-3799">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是65%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3799">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3800">函數 Func_randomized_formatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3800">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3801">會找到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3801">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="d5030-3802">如果接近300個字元以內，則 DLP 原則偵測到此敏感資訊類型的置信量是55%：</span><span class="sxs-lookup"><span data-stu-id="d5030-3802">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="d5030-3803">函數 Func_randomized_unformatted_ssn 找到符合模式的內容。</span><span class="sxs-lookup"><span data-stu-id="d5030-3803">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="d5030-3804">會找到來自 Keyword_ssn 的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="d5030-3804">A keyword from Keyword_ssn is found.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="d5030-3805">關鍵字</span><span class="sxs-lookup"><span data-stu-id="d5030-3805">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="d5030-3806">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="d5030-3806">Keyword_ssn</span></span>

- <span data-ttu-id="d5030-3807">社會保障</span><span class="sxs-lookup"><span data-stu-id="d5030-3807">Social Security</span></span> 
- <span data-ttu-id="d5030-3808">社會保障#</span><span class="sxs-lookup"><span data-stu-id="d5030-3808">Social Security#</span></span> 
- <span data-ttu-id="d5030-3809">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="d5030-3809">Soc Sec</span></span> 
- <span data-ttu-id="d5030-3810">Ssn</span><span class="sxs-lookup"><span data-stu-id="d5030-3810">SSN</span></span> 
- <span data-ttu-id="d5030-3811">主旨 SSN</span><span class="sxs-lookup"><span data-stu-id="d5030-3811">SSNS</span></span> 
- <span data-ttu-id="d5030-3812">Ssn#</span><span class="sxs-lookup"><span data-stu-id="d5030-3812">SSN#</span></span> 
- <span data-ttu-id="d5030-3813">秒#</span><span class="sxs-lookup"><span data-stu-id="d5030-3813">SS#</span></span> 
- <span data-ttu-id="d5030-3814">Ssid</span><span class="sxs-lookup"><span data-stu-id="d5030-3814">SSID</span></span> 
   
