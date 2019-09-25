---
title: 敏感資訊類型在找什麼
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
description: Office 365 安全&amp;合规性中心中的数据丢失防护 （DLP） 包括 80 种敏感信息类型，可供您在 DLP 策略中使用。 本主题列出所有这些敏感信息类型，并显示 DLP 策略在检测每种类型时查找的内容。
ms.openlocfilehash: 820bab0a128f952cf5d96208f5d561f4994bd859
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077639"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="78146-104">敏感資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="78146-104">What the sensitive information types look for</span></span>

<span data-ttu-id="78146-105">Office 365 安全&amp;合规性中心中的数据丢失防护 （DLP） 包括许多敏感信息类型，可供您在 DLP 策略中使用。</span><span class="sxs-lookup"><span data-stu-id="78146-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="78146-106">本主题列出所有这些敏感信息类型，并显示 DLP 策略在检测每种类型时查找的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="78146-107">敏感信息类型由由正则表达式或函数标识的模式定义。</span><span class="sxs-lookup"><span data-stu-id="78146-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="78146-108">此外，关键字和校验和等确凿证据可用于识别敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="78146-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="78146-109">置信度和接近度也用于评估过程。</span><span class="sxs-lookup"><span data-stu-id="78146-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="78146-110">ABA 路由号码</span><span class="sxs-lookup"><span data-stu-id="78146-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-111">格式</span><span class="sxs-lookup"><span data-stu-id="78146-111">Format</span></span>

<span data-ttu-id="78146-112">9 位数字，可能采用格式化或未格式化的模式</span><span class="sxs-lookup"><span data-stu-id="78146-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-113">模式</span><span class="sxs-lookup"><span data-stu-id="78146-113">Pattern</span></span>

<span data-ttu-id="78146-114">格式 化：</span><span class="sxs-lookup"><span data-stu-id="78146-114">Formatted:</span></span>
- <span data-ttu-id="78146-115">四位数字以 0、1、2、3、6、7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="78146-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="78146-116">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-116">A hyphen</span></span>
- <span data-ttu-id="78146-117">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-117">Four digits</span></span>
- <span data-ttu-id="78146-118">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-118">A hyphen</span></span>
- <span data-ttu-id="78146-119">数字</span><span class="sxs-lookup"><span data-stu-id="78146-119">A digit</span></span>

<span data-ttu-id="78146-120">未格式化：9 个连续数字，以 0、1、2、3、6、7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="78146-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="78146-121">校验</span><span class="sxs-lookup"><span data-stu-id="78146-121">Checksum</span></span>

<span data-ttu-id="78146-122">否</span><span class="sxs-lookup"><span data-stu-id="78146-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-123">定義</span><span class="sxs-lookup"><span data-stu-id="78146-123">Definition</span></span>

<span data-ttu-id="78146-124">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-125">函数 Func_aba_路由查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-126">找到关键字_ABA_路由的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="78146-127">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="78146-128">关键字_ABA_路由</span><span class="sxs-lookup"><span data-stu-id="78146-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="78146-129">阿坝</span><span class="sxs-lookup"><span data-stu-id="78146-129">aba</span></span>
- <span data-ttu-id="78146-130">阿坝#</span><span class="sxs-lookup"><span data-stu-id="78146-130">aba #</span></span>
- <span data-ttu-id="78146-131">aba 路由#</span><span class="sxs-lookup"><span data-stu-id="78146-131">aba routing #</span></span>
- <span data-ttu-id="78146-132">aba 路由编号</span><span class="sxs-lookup"><span data-stu-id="78146-132">aba routing number</span></span>
- <span data-ttu-id="78146-133">阿坝#</span><span class="sxs-lookup"><span data-stu-id="78146-133">aba#</span></span>
- <span data-ttu-id="78146-134">阿巴路由#</span><span class="sxs-lookup"><span data-stu-id="78146-134">abarouting#</span></span>
- <span data-ttu-id="78146-135">阿巴数</span><span class="sxs-lookup"><span data-stu-id="78146-135">aba number</span></span>
- <span data-ttu-id="78146-136">aba路由编号</span><span class="sxs-lookup"><span data-stu-id="78146-136">abaroutingnumber</span></span>
- <span data-ttu-id="78146-137">美国银行协会路由#</span><span class="sxs-lookup"><span data-stu-id="78146-137">american bank association routing #</span></span>
- <span data-ttu-id="78146-138">美国银行协会路由号码</span><span class="sxs-lookup"><span data-stu-id="78146-138">american bank association routing number</span></span>
- <span data-ttu-id="78146-139">美国银行协会路由#</span><span class="sxs-lookup"><span data-stu-id="78146-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="78146-140">美国银行协会路由号码</span><span class="sxs-lookup"><span data-stu-id="78146-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="78146-141">银行路由编号</span><span class="sxs-lookup"><span data-stu-id="78146-141">bank routing number</span></span>
- <span data-ttu-id="78146-142">银行路由#</span><span class="sxs-lookup"><span data-stu-id="78146-142">bankrouting#</span></span>
- <span data-ttu-id="78146-143">银行路由编号</span><span class="sxs-lookup"><span data-stu-id="78146-143">bankroutingnumber</span></span>
- <span data-ttu-id="78146-144">路由传输编号</span><span class="sxs-lookup"><span data-stu-id="78146-144">routing transit number</span></span>
- <span data-ttu-id="78146-145">RTN</span><span class="sxs-lookup"><span data-stu-id="78146-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="78146-146">阿根廷国民身份 （DNI） 编号</span><span class="sxs-lookup"><span data-stu-id="78146-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-147">格式</span><span class="sxs-lookup"><span data-stu-id="78146-147">Format</span></span>

<span data-ttu-id="78146-148">按句点分隔的八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-149">模式</span><span class="sxs-lookup"><span data-stu-id="78146-149">Pattern</span></span>

<span data-ttu-id="78146-150">八位数字：</span><span class="sxs-lookup"><span data-stu-id="78146-150">Eight digits:</span></span>
- <span data-ttu-id="78146-151">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-151">Two digits</span></span>
- <span data-ttu-id="78146-152">一个期间</span><span class="sxs-lookup"><span data-stu-id="78146-152">A period</span></span>
- <span data-ttu-id="78146-153">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-153">Three digits</span></span>
- <span data-ttu-id="78146-154">一个期间</span><span class="sxs-lookup"><span data-stu-id="78146-154">A period</span></span>
- <span data-ttu-id="78146-155">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-156">校验</span><span class="sxs-lookup"><span data-stu-id="78146-156">Checksum</span></span>

<span data-ttu-id="78146-157">否</span><span class="sxs-lookup"><span data-stu-id="78146-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-158">定義</span><span class="sxs-lookup"><span data-stu-id="78146-158">Definition</span></span>

<span data-ttu-id="78146-159">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-160">正则表达式 Regex_argentina_national_id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-161">找到关键字_argentina_national_id 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-162">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="78146-163">关键字_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="78146-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="78146-164">阿根廷国民身份号码</span><span class="sxs-lookup"><span data-stu-id="78146-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="78146-165">身分識別</span><span class="sxs-lookup"><span data-stu-id="78146-165">Identity</span></span> 
- <span data-ttu-id="78146-166">身份证明国民身份证</span><span class="sxs-lookup"><span data-stu-id="78146-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="78146-167">DNI</span><span class="sxs-lookup"><span data-stu-id="78146-167">DNI</span></span> 
- <span data-ttu-id="78146-168">国家个人登记处</span><span class="sxs-lookup"><span data-stu-id="78146-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="78146-169">国家身份文献</span><span class="sxs-lookup"><span data-stu-id="78146-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="78146-170">国家个人登记局</span><span class="sxs-lookup"><span data-stu-id="78146-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="78146-171">身份</span><span class="sxs-lookup"><span data-stu-id="78146-171">Identidad</span></span> 
- <span data-ttu-id="78146-172">身份识别</span><span class="sxs-lookup"><span data-stu-id="78146-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="78146-173">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="78146-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-174">格式</span><span class="sxs-lookup"><span data-stu-id="78146-174">Format</span></span>

<span data-ttu-id="78146-175">6-10 位数字，带或不带银行州分行号码</span><span class="sxs-lookup"><span data-stu-id="78146-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-176">模式</span><span class="sxs-lookup"><span data-stu-id="78146-176">Pattern</span></span>

<span data-ttu-id="78146-177">帐号为 6-10 位。</span><span class="sxs-lookup"><span data-stu-id="78146-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="78146-178">澳大利亚银行州分行编号：</span><span class="sxs-lookup"><span data-stu-id="78146-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="78146-179">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-179">Three digits</span></span> 
- <span data-ttu-id="78146-180">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-180">A hyphen</span></span> 
- <span data-ttu-id="78146-181">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-182">校验</span><span class="sxs-lookup"><span data-stu-id="78146-182">Checksum</span></span>

<span data-ttu-id="78146-183">否</span><span class="sxs-lookup"><span data-stu-id="78146-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-184">定義</span><span class="sxs-lookup"><span data-stu-id="78146-184">Definition</span></span>

<span data-ttu-id="78146-185">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-186">正则表达式 Regex_australia_bank_帐户_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="78146-187">找到关键字_澳大利亚_银行_帐户_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="78146-188">正则表达式 Regex_australia_bank_帐户_number_bsb 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="78146-189">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-190">正则表达式 Regex_australia_bank_帐户_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="78146-191">找到关键字_澳大利亚_银行_帐户_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-192">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="78146-193">关键词_澳大利亚_银行_帐户_编号</span><span class="sxs-lookup"><span data-stu-id="78146-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="78146-194">快速银行代码</span><span class="sxs-lookup"><span data-stu-id="78146-194">swift bank code</span></span>
- <span data-ttu-id="78146-195">代理银行</span><span class="sxs-lookup"><span data-stu-id="78146-195">correspondent bank</span></span>
- <span data-ttu-id="78146-196">基础货币</span><span class="sxs-lookup"><span data-stu-id="78146-196">base currency</span></span>
- <span data-ttu-id="78146-197">usa 帐户</span><span class="sxs-lookup"><span data-stu-id="78146-197">usa account</span></span>
- <span data-ttu-id="78146-198">持有人地址</span><span class="sxs-lookup"><span data-stu-id="78146-198">holder address</span></span>
- <span data-ttu-id="78146-199">银行地址</span><span class="sxs-lookup"><span data-stu-id="78146-199">bank address</span></span>
- <span data-ttu-id="78146-200">信息账户</span><span class="sxs-lookup"><span data-stu-id="78146-200">information account</span></span>
- <span data-ttu-id="78146-201">资金转账</span><span class="sxs-lookup"><span data-stu-id="78146-201">fund transfers</span></span>
- <span data-ttu-id="78146-202">银行手续费</span><span class="sxs-lookup"><span data-stu-id="78146-202">bank charges</span></span>
- <span data-ttu-id="78146-203">银行详细信息</span><span class="sxs-lookup"><span data-stu-id="78146-203">bank details</span></span>
- <span data-ttu-id="78146-204">银行信息</span><span class="sxs-lookup"><span data-stu-id="78146-204">banking information</span></span>
- <span data-ttu-id="78146-205">全名</span><span class="sxs-lookup"><span data-stu-id="78146-205">full names</span></span>
- <span data-ttu-id="78146-206">国际 原子能 机构</span><span class="sxs-lookup"><span data-stu-id="78146-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="78146-207">澳大利亚驾照号码</span><span class="sxs-lookup"><span data-stu-id="78146-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-208">格式</span><span class="sxs-lookup"><span data-stu-id="78146-208">Format</span></span>

<span data-ttu-id="78146-209">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="78146-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-210">模式</span><span class="sxs-lookup"><span data-stu-id="78146-210">Pattern</span></span>

<span data-ttu-id="78146-211">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="78146-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="78146-212">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="78146-213">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-213">Two digits</span></span> 
- <span data-ttu-id="78146-214">五位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="78146-215">或</span><span class="sxs-lookup"><span data-stu-id="78146-215">OR</span></span>

- <span data-ttu-id="78146-216">1-2 个可选字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="78146-217">4-9 位</span><span class="sxs-lookup"><span data-stu-id="78146-217">4-9 digits</span></span>

<span data-ttu-id="78146-218">或</span><span class="sxs-lookup"><span data-stu-id="78146-218">OR</span></span>

- <span data-ttu-id="78146-219">九位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-220">校验</span><span class="sxs-lookup"><span data-stu-id="78146-220">Checksum</span></span>

<span data-ttu-id="78146-221">否</span><span class="sxs-lookup"><span data-stu-id="78146-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-222">定義</span><span class="sxs-lookup"><span data-stu-id="78146-222">Definition</span></span>

<span data-ttu-id="78146-223">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-224">正则表达式 Regex_australia_驱动程序_许可证_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-225">找到关键字_澳大利亚_驱动程序_许可证_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="78146-226">找不到关键字_澳大利亚_驱动程序_许可证_数字_排除项中未找到关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-227">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="78146-228">关键词_澳大利亚_驱动程序_许可证_编号</span><span class="sxs-lookup"><span data-stu-id="78146-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="78146-229">国际驾驶证</span><span class="sxs-lookup"><span data-stu-id="78146-229">international driving permits</span></span>
- <span data-ttu-id="78146-230">澳大利亚汽车协会</span><span class="sxs-lookup"><span data-stu-id="78146-230">australian automobile association</span></span>
- <span data-ttu-id="78146-231">国际驾照</span><span class="sxs-lookup"><span data-stu-id="78146-231">international driving permit</span></span>
- <span data-ttu-id="78146-232">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-232">DriverLicence</span></span>
- <span data-ttu-id="78146-233">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-233">DriverLicences</span></span>
- <span data-ttu-id="78146-234">司机李克</span><span class="sxs-lookup"><span data-stu-id="78146-234">Driver Lic</span></span>
- <span data-ttu-id="78146-235">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-235">Driver Licence</span></span>
- <span data-ttu-id="78146-236">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-236">Driver Licences</span></span>
- <span data-ttu-id="78146-237">驱动程序</span><span class="sxs-lookup"><span data-stu-id="78146-237">DriversLic</span></span>
- <span data-ttu-id="78146-238">司机执照</span><span class="sxs-lookup"><span data-stu-id="78146-238">DriversLicence</span></span>
- <span data-ttu-id="78146-239">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-239">DriversLicences</span></span>
- <span data-ttu-id="78146-240">司机许可证</span><span class="sxs-lookup"><span data-stu-id="78146-240">Drivers Lic</span></span>
- <span data-ttu-id="78146-241">司机利茨</span><span class="sxs-lookup"><span data-stu-id="78146-241">Drivers Lics</span></span>
- <span data-ttu-id="78146-242">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-242">Drivers Licence</span></span>
- <span data-ttu-id="78146-243">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-243">Drivers Licences</span></span>
- <span data-ttu-id="78146-244">司机'Lic</span><span class="sxs-lookup"><span data-stu-id="78146-244">Driver'Lic</span></span>
- <span data-ttu-id="78146-245">司机的Lics</span><span class="sxs-lookup"><span data-stu-id="78146-245">Driver'Lics</span></span>
- <span data-ttu-id="78146-246">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-246">Driver'Licence</span></span>
- <span data-ttu-id="78146-247">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-247">Driver'Licences</span></span>
- <span data-ttu-id="78146-248">司机的许可证</span><span class="sxs-lookup"><span data-stu-id="78146-248">Driver' Lic</span></span>
- <span data-ttu-id="78146-249">司机的Lics</span><span class="sxs-lookup"><span data-stu-id="78146-249">Driver' Lics</span></span>
- <span data-ttu-id="78146-250">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-250">Driver' Licence</span></span>
- <span data-ttu-id="78146-251">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-251">Driver' Licences</span></span>
- <span data-ttu-id="78146-252">驾驶员的</span><span class="sxs-lookup"><span data-stu-id="78146-252">Driver'sLic</span></span>
- <span data-ttu-id="78146-253">驾驶员的</span><span class="sxs-lookup"><span data-stu-id="78146-253">Driver'sLics</span></span>
- <span data-ttu-id="78146-254">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-254">Driver'sLicence</span></span>
- <span data-ttu-id="78146-255">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-255">Driver'sLicences</span></span>
- <span data-ttu-id="78146-256">驾驶员的许可证</span><span class="sxs-lookup"><span data-stu-id="78146-256">Driver's Lic</span></span>
- <span data-ttu-id="78146-257">司机的许可证</span><span class="sxs-lookup"><span data-stu-id="78146-257">Driver's Lics</span></span>
- <span data-ttu-id="78146-258">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-258">Driver's Licence</span></span>
- <span data-ttu-id="78146-259">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-259">Driver's Licences</span></span>
- <span data-ttu-id="78146-260">司机#</span><span class="sxs-lookup"><span data-stu-id="78146-260">DriverLic#</span></span>
- <span data-ttu-id="78146-261">司机#</span><span class="sxs-lookup"><span data-stu-id="78146-261">DriverLics#</span></span>
- <span data-ttu-id="78146-262">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-262">DriverLicence#</span></span>
- <span data-ttu-id="78146-263">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-263">DriverLicences#</span></span>
- <span data-ttu-id="78146-264">司机李克#</span><span class="sxs-lookup"><span data-stu-id="78146-264">Driver Lic#</span></span>
- <span data-ttu-id="78146-265">司机利茨#</span><span class="sxs-lookup"><span data-stu-id="78146-265">Driver Lics#</span></span>
- <span data-ttu-id="78146-266">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-266">Driver Licence#</span></span>
- <span data-ttu-id="78146-267">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-267">Driver Licences#</span></span>
- <span data-ttu-id="78146-268">驱动程序#</span><span class="sxs-lookup"><span data-stu-id="78146-268">DriversLic#</span></span>
- <span data-ttu-id="78146-269">司机Lics#</span><span class="sxs-lookup"><span data-stu-id="78146-269">DriversLics#</span></span>
- <span data-ttu-id="78146-270">司机执照#</span><span class="sxs-lookup"><span data-stu-id="78146-270">DriversLicence#</span></span>
- <span data-ttu-id="78146-271">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-271">DriversLicences#</span></span>
- <span data-ttu-id="78146-272">司机许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-272">Drivers Lic#</span></span>
- <span data-ttu-id="78146-273">司机利茨#</span><span class="sxs-lookup"><span data-stu-id="78146-273">Drivers Lics#</span></span>
- <span data-ttu-id="78146-274">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-274">Drivers Licence#</span></span>
- <span data-ttu-id="78146-275">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-275">Drivers Licences#</span></span>
- <span data-ttu-id="78146-276">司机'Lic#</span><span class="sxs-lookup"><span data-stu-id="78146-276">Driver'Lic#</span></span>
- <span data-ttu-id="78146-277">司机的Lics#</span><span class="sxs-lookup"><span data-stu-id="78146-277">Driver'Lics#</span></span>
- <span data-ttu-id="78146-278">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-278">Driver'Licence#</span></span>
- <span data-ttu-id="78146-279">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-279">Driver'Licences#</span></span>
- <span data-ttu-id="78146-280">司机的许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-280">Driver' Lic#</span></span>
- <span data-ttu-id="78146-281">司机的Lics#</span><span class="sxs-lookup"><span data-stu-id="78146-281">Driver' Lics#</span></span>
- <span data-ttu-id="78146-282">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-282">Driver' Licence#</span></span>
- <span data-ttu-id="78146-283">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-283">Driver' Licences#</span></span>
- <span data-ttu-id="78146-284">驾驶员的#</span><span class="sxs-lookup"><span data-stu-id="78146-284">Driver'sLic#</span></span>
- <span data-ttu-id="78146-285">驾驶员的#</span><span class="sxs-lookup"><span data-stu-id="78146-285">Driver'sLics#</span></span>
- <span data-ttu-id="78146-286">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-286">Driver'sLicence#</span></span>
- <span data-ttu-id="78146-287">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-287">Driver'sLicences#</span></span>
- <span data-ttu-id="78146-288">驾驶员的许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-288">Driver's Lic#</span></span>
- <span data-ttu-id="78146-289">司机的许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-289">Driver's Lics#</span></span>
- <span data-ttu-id="78146-290">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-290">Driver's Licence#</span></span>
- <span data-ttu-id="78146-291">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="78146-292">关键词_澳大利亚_驱动程序_许可证_数字_排除</span><span class="sxs-lookup"><span data-stu-id="78146-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="78146-293">Aaa</span><span class="sxs-lookup"><span data-stu-id="78146-293">aaa</span></span>
- <span data-ttu-id="78146-294">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-294">DriverLicense</span></span>
- <span data-ttu-id="78146-295">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-295">DriverLicenses</span></span>
- <span data-ttu-id="78146-296">驾照</span><span class="sxs-lookup"><span data-stu-id="78146-296">Driver License</span></span>
- <span data-ttu-id="78146-297">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-297">Driver Licenses</span></span>
- <span data-ttu-id="78146-298">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-298">DriversLicense</span></span>
- <span data-ttu-id="78146-299">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-299">DriversLicenses</span></span>
- <span data-ttu-id="78146-300">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-300">Drivers License</span></span>
- <span data-ttu-id="78146-301">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-301">Drivers Licenses</span></span>
- <span data-ttu-id="78146-302">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-302">Driver'License</span></span>
- <span data-ttu-id="78146-303">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-303">Driver'Licenses</span></span>
- <span data-ttu-id="78146-304">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-304">Driver' License</span></span>
- <span data-ttu-id="78146-305">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-305">Driver' Licenses</span></span>
- <span data-ttu-id="78146-306">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-306">Driver'sLicense</span></span>
- <span data-ttu-id="78146-307">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-307">Driver'sLicenses</span></span>
- <span data-ttu-id="78146-308">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-308">Driver's License</span></span>
- <span data-ttu-id="78146-309">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-309">Driver's Licenses</span></span>
- <span data-ttu-id="78146-310">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-310">DriverLicense#</span></span>
- <span data-ttu-id="78146-311">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-311">DriverLicenses#</span></span>
- <span data-ttu-id="78146-312">驾照#</span><span class="sxs-lookup"><span data-stu-id="78146-312">Driver License#</span></span>
- <span data-ttu-id="78146-313">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-313">Driver Licenses#</span></span>
- <span data-ttu-id="78146-314">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-314">DriversLicense#</span></span>
- <span data-ttu-id="78146-315">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-315">DriversLicenses#</span></span>
- <span data-ttu-id="78146-316">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-316">Drivers License#</span></span>
- <span data-ttu-id="78146-317">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-317">Drivers Licenses#</span></span>
- <span data-ttu-id="78146-318">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-318">Driver'License#</span></span>
- <span data-ttu-id="78146-319">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-319">Driver'Licenses#</span></span>
- <span data-ttu-id="78146-320">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-320">Driver' License#</span></span>
- <span data-ttu-id="78146-321">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-321">Driver' Licenses#</span></span>
- <span data-ttu-id="78146-322">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-322">Driver'sLicense#</span></span>
- <span data-ttu-id="78146-323">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="78146-324">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-324">Driver's License#</span></span>
- <span data-ttu-id="78146-325">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="78146-326">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="78146-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-327">格式</span><span class="sxs-lookup"><span data-stu-id="78146-327">Format</span></span>

<span data-ttu-id="78146-328">10-11 位</span><span class="sxs-lookup"><span data-stu-id="78146-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-329">模式</span><span class="sxs-lookup"><span data-stu-id="78146-329">Pattern</span></span>

<span data-ttu-id="78146-330">10-11 位：</span><span class="sxs-lookup"><span data-stu-id="78146-330">10-11 digits:</span></span>
- <span data-ttu-id="78146-331">第一个数字在 2-6 范围内</span><span class="sxs-lookup"><span data-stu-id="78146-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="78146-332">第九位数字是校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="78146-333">第十位是问题数字</span><span class="sxs-lookup"><span data-stu-id="78146-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="78146-334">第十一位（可选）是单个数字</span><span class="sxs-lookup"><span data-stu-id="78146-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-335">校验</span><span class="sxs-lookup"><span data-stu-id="78146-335">Checksum</span></span>

<span data-ttu-id="78146-336">是</span><span class="sxs-lookup"><span data-stu-id="78146-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-337">定義</span><span class="sxs-lookup"><span data-stu-id="78146-337">Definition</span></span>

<span data-ttu-id="78146-338">如果接近 300 个字符，DLP 策略 95% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-339">函数 Func_australian_medical_帐户_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-340">找到关键字"澳大利亚"_医疗+帐户_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="78146-341">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-341">The checksum passes.</span></span>

<span data-ttu-id="78146-342">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-343">函数 Func_australian_medical_帐户_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-344">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-345">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="78146-346">关键词_澳大利亚_医疗+帐户_号码</span><span class="sxs-lookup"><span data-stu-id="78146-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="78146-347">银行账户详细信息</span><span class="sxs-lookup"><span data-stu-id="78146-347">bank account details</span></span>
- <span data-ttu-id="78146-348">医疗保险付款</span><span class="sxs-lookup"><span data-stu-id="78146-348">medicare payments</span></span>
- <span data-ttu-id="78146-349">抵押帐户</span><span class="sxs-lookup"><span data-stu-id="78146-349">mortgage account</span></span>
- <span data-ttu-id="78146-350">银行付款</span><span class="sxs-lookup"><span data-stu-id="78146-350">bank payments</span></span>
- <span data-ttu-id="78146-351">信息分支</span><span class="sxs-lookup"><span data-stu-id="78146-351">information branch</span></span>
- <span data-ttu-id="78146-352">信用卡贷款</span><span class="sxs-lookup"><span data-stu-id="78146-352">credit card loan</span></span>
- <span data-ttu-id="78146-353">人类服务部</span><span class="sxs-lookup"><span data-stu-id="78146-353">department of human services</span></span>
- <span data-ttu-id="78146-354">本地服务</span><span class="sxs-lookup"><span data-stu-id="78146-354">local service</span></span>
- <span data-ttu-id="78146-355">医疗</span><span class="sxs-lookup"><span data-stu-id="78146-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="78146-356">澳大利亚护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-357">格式</span><span class="sxs-lookup"><span data-stu-id="78146-357">Format</span></span>

<span data-ttu-id="78146-358">后跟七位数字的字母</span><span class="sxs-lookup"><span data-stu-id="78146-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-359">模式</span><span class="sxs-lookup"><span data-stu-id="78146-359">Pattern</span></span>

<span data-ttu-id="78146-360">字母（不区分大小写）后跟七位数字</span><span class="sxs-lookup"><span data-stu-id="78146-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-361">校验</span><span class="sxs-lookup"><span data-stu-id="78146-361">Checksum</span></span>

<span data-ttu-id="78146-362">否</span><span class="sxs-lookup"><span data-stu-id="78146-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-363">定義</span><span class="sxs-lookup"><span data-stu-id="78146-363">Definition</span></span>

<span data-ttu-id="78146-364">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-365">正则表达式 Regex_australia_Passport_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-366">找到关键字_护照或关键字_澳大利亚_护照_号码的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-367">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="78146-368">关键词_护照</span><span class="sxs-lookup"><span data-stu-id="78146-368">Keyword_passport</span></span>

- <span data-ttu-id="78146-369">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-369">Passport Number</span></span>
- <span data-ttu-id="78146-370">护照号</span><span class="sxs-lookup"><span data-stu-id="78146-370">Passport No</span></span>
- <span data-ttu-id="78146-371">护照#</span><span class="sxs-lookup"><span data-stu-id="78146-371">Passport #</span></span>
- <span data-ttu-id="78146-372">护照#</span><span class="sxs-lookup"><span data-stu-id="78146-372">Passport#</span></span>
- <span data-ttu-id="78146-373">护照ID</span><span class="sxs-lookup"><span data-stu-id="78146-373">PassportID</span></span>
- <span data-ttu-id="78146-374">护照诺</span><span class="sxs-lookup"><span data-stu-id="78146-374">Passportno</span></span>
- <span data-ttu-id="78146-375">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-375">passportnumber</span></span>
- <span data-ttu-id="78146-376">·</span><span class="sxs-lookup"><span data-stu-id="78146-376">パスポート</span></span>
- <span data-ttu-id="78146-377">·\\\\\\\\\\\\\\\\\\\\\\</span><span class="sxs-lookup"><span data-stu-id="78146-377">パスポート番号</span></span>
- <span data-ttu-id="78146-378">\* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="78146-378">パスポートのNum</span></span>
- <span data-ttu-id="78146-379">[ ]</span><span class="sxs-lookup"><span data-stu-id="78146-379">パスポート ＃</span></span> 
- <span data-ttu-id="78146-380">努梅罗·德·德费波特</span><span class="sxs-lookup"><span data-stu-id="78146-380">Numéro de passeport</span></span>
- <span data-ttu-id="78146-381">路路港 n |</span><span class="sxs-lookup"><span data-stu-id="78146-381">Passeport n °</span></span>
- <span data-ttu-id="78146-382">路路港非</span><span class="sxs-lookup"><span data-stu-id="78146-382">Passeport Non</span></span>
- <span data-ttu-id="78146-383">帕塞波特#</span><span class="sxs-lookup"><span data-stu-id="78146-383">Passeport #</span></span>
- <span data-ttu-id="78146-384">帕塞波特#</span><span class="sxs-lookup"><span data-stu-id="78146-384">Passeport#</span></span>
- <span data-ttu-id="78146-385">帕塞波特农</span><span class="sxs-lookup"><span data-stu-id="78146-385">PasseportNon</span></span>
- <span data-ttu-id="78146-386">帕塞波特 |</span><span class="sxs-lookup"><span data-stu-id="78146-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="78146-387">关键词_澳大利亚_护照_号码</span><span class="sxs-lookup"><span data-stu-id="78146-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="78146-388">护照</span><span class="sxs-lookup"><span data-stu-id="78146-388">passport</span></span>
- <span data-ttu-id="78146-389">护照详情</span><span class="sxs-lookup"><span data-stu-id="78146-389">passport details</span></span>
- <span data-ttu-id="78146-390">移民和公民身份</span><span class="sxs-lookup"><span data-stu-id="78146-390">immigration and citizenship</span></span>
- <span data-ttu-id="78146-391">澳大利亚联邦</span><span class="sxs-lookup"><span data-stu-id="78146-391">commonwealth of australia</span></span>
- <span data-ttu-id="78146-392">移民部</span><span class="sxs-lookup"><span data-stu-id="78146-392">department of immigration</span></span>
- <span data-ttu-id="78146-393">住宅地址</span><span class="sxs-lookup"><span data-stu-id="78146-393">residential address</span></span>
- <span data-ttu-id="78146-394">移民和公民部</span><span class="sxs-lookup"><span data-stu-id="78146-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="78146-395">签证</span><span class="sxs-lookup"><span data-stu-id="78146-395">visa</span></span>
- <span data-ttu-id="78146-396">国民身份证</span><span class="sxs-lookup"><span data-stu-id="78146-396">national identity card</span></span>
- <span data-ttu-id="78146-397">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-397">passport number</span></span>
- <span data-ttu-id="78146-398">旅行证件</span><span class="sxs-lookup"><span data-stu-id="78146-398">travel document</span></span>
- <span data-ttu-id="78146-399">颁发机构</span><span class="sxs-lookup"><span data-stu-id="78146-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="78146-400">澳大利亚税务档案号码</span><span class="sxs-lookup"><span data-stu-id="78146-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-401">格式</span><span class="sxs-lookup"><span data-stu-id="78146-401">Format</span></span>

<span data-ttu-id="78146-402">8-9 位</span><span class="sxs-lookup"><span data-stu-id="78146-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-403">模式</span><span class="sxs-lookup"><span data-stu-id="78146-403">Pattern</span></span>

<span data-ttu-id="78146-404">8-9 位数字通常以空格显示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="78146-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="78146-405">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-405">Three digits</span></span> 
- <span data-ttu-id="78146-406">可选空间</span><span class="sxs-lookup"><span data-stu-id="78146-406">An optional space</span></span> 
- <span data-ttu-id="78146-407">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-407">Three digits</span></span> 
- <span data-ttu-id="78146-408">可选空间</span><span class="sxs-lookup"><span data-stu-id="78146-408">An optional space</span></span> 
- <span data-ttu-id="78146-409">2-3 位数字，其中最后一个数字是校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-410">校验</span><span class="sxs-lookup"><span data-stu-id="78146-410">Checksum</span></span>

<span data-ttu-id="78146-411">是</span><span class="sxs-lookup"><span data-stu-id="78146-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-412">定義</span><span class="sxs-lookup"><span data-stu-id="78146-412">Definition</span></span>

<span data-ttu-id="78146-413">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-414">函数 Func_australian_tax_file_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-415">找不到关键字"澳大利亚_澳大利亚"_税务_文件_数字或关键字_数字_排除项中未找到关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="78146-416">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-417">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="78146-418">关键词_澳大利亚_税_文件_数字</span><span class="sxs-lookup"><span data-stu-id="78146-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="78146-419">澳大利亚业务编号</span><span class="sxs-lookup"><span data-stu-id="78146-419">australian business number</span></span>
- <span data-ttu-id="78146-420">边际税率</span><span class="sxs-lookup"><span data-stu-id="78146-420">marginal tax rate</span></span>
- <span data-ttu-id="78146-421">医疗保险税</span><span class="sxs-lookup"><span data-stu-id="78146-421">medicare levy</span></span>
- <span data-ttu-id="78146-422">投资组合编号</span><span class="sxs-lookup"><span data-stu-id="78146-422">portfolio number</span></span>
- <span data-ttu-id="78146-423">服役退伍军人</span><span class="sxs-lookup"><span data-stu-id="78146-423">service veterans</span></span>
- <span data-ttu-id="78146-424">预扣税</span><span class="sxs-lookup"><span data-stu-id="78146-424">withholding tax</span></span>
- <span data-ttu-id="78146-425">个人纳税申报表</span><span class="sxs-lookup"><span data-stu-id="78146-425">individual tax return</span></span>
- <span data-ttu-id="78146-426">税文件编号</span><span class="sxs-lookup"><span data-stu-id="78146-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="78146-427">关键字_数字_排除</span><span class="sxs-lookup"><span data-stu-id="78146-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="78146-428">00000000</span><span class="sxs-lookup"><span data-stu-id="78146-428">00000000</span></span>
- <span data-ttu-id="78146-429">11111111</span><span class="sxs-lookup"><span data-stu-id="78146-429">11111111</span></span>
- <span data-ttu-id="78146-430">22222222</span><span class="sxs-lookup"><span data-stu-id="78146-430">22222222</span></span>
- <span data-ttu-id="78146-431">33333333</span><span class="sxs-lookup"><span data-stu-id="78146-431">33333333</span></span>
- <span data-ttu-id="78146-432">44444444</span><span class="sxs-lookup"><span data-stu-id="78146-432">44444444</span></span>
- <span data-ttu-id="78146-433">55555555</span><span class="sxs-lookup"><span data-stu-id="78146-433">55555555</span></span>
- <span data-ttu-id="78146-434">66666666</span><span class="sxs-lookup"><span data-stu-id="78146-434">66666666</span></span>
- <span data-ttu-id="78146-435">77777777</span><span class="sxs-lookup"><span data-stu-id="78146-435">77777777</span></span>
- <span data-ttu-id="78146-436">88888888</span><span class="sxs-lookup"><span data-stu-id="78146-436">88888888</span></span>
- <span data-ttu-id="78146-437">99999999</span><span class="sxs-lookup"><span data-stu-id="78146-437">99999999</span></span>
- <span data-ttu-id="78146-438">000000000</span><span class="sxs-lookup"><span data-stu-id="78146-438">000000000</span></span>
- <span data-ttu-id="78146-439">111111111</span><span class="sxs-lookup"><span data-stu-id="78146-439">111111111</span></span>
- <span data-ttu-id="78146-440">222222222</span><span class="sxs-lookup"><span data-stu-id="78146-440">222222222</span></span>
- <span data-ttu-id="78146-441">333333333</span><span class="sxs-lookup"><span data-stu-id="78146-441">333333333</span></span>
- <span data-ttu-id="78146-442">444444444</span><span class="sxs-lookup"><span data-stu-id="78146-442">444444444</span></span>
- <span data-ttu-id="78146-443">555555555</span><span class="sxs-lookup"><span data-stu-id="78146-443">555555555</span></span>
- <span data-ttu-id="78146-444">666666666</span><span class="sxs-lookup"><span data-stu-id="78146-444">666666666</span></span>
- <span data-ttu-id="78146-445">777777777</span><span class="sxs-lookup"><span data-stu-id="78146-445">777777777</span></span>
- <span data-ttu-id="78146-446">888888888</span><span class="sxs-lookup"><span data-stu-id="78146-446">888888888</span></span>
- <span data-ttu-id="78146-447">999999999</span><span class="sxs-lookup"><span data-stu-id="78146-447">999999999</span></span>
- <span data-ttu-id="78146-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="78146-448">0000000000</span></span>
- <span data-ttu-id="78146-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="78146-449">1111111111</span></span>
- <span data-ttu-id="78146-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="78146-450">2222222222</span></span>
- <span data-ttu-id="78146-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="78146-451">3333333333</span></span>
- <span data-ttu-id="78146-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="78146-452">4444444444</span></span>
- <span data-ttu-id="78146-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="78146-453">5555555555</span></span>
- <span data-ttu-id="78146-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="78146-454">6666666666</span></span>
- <span data-ttu-id="78146-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="78146-455">7777777777</span></span>
- <span data-ttu-id="78146-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="78146-456">8888888888</span></span>
- <span data-ttu-id="78146-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="78146-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="78146-458">Azure 文档 DB Auth 密钥</span><span class="sxs-lookup"><span data-stu-id="78146-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="78146-459">格式</span><span class="sxs-lookup"><span data-stu-id="78146-459">Format</span></span>

<span data-ttu-id="78146-460">字符串"DocumentDb"后跟以下模式中概述的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="78146-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-461">模式</span><span class="sxs-lookup"><span data-stu-id="78146-461">Pattern</span></span>

- <span data-ttu-id="78146-462">字符串"文档 Db"</span><span class="sxs-lookup"><span data-stu-id="78146-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="78146-463">3-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="78146-464">大于符号 （>）、等号 （\*）、引号 （）或撇号 （'）</span><span class="sxs-lookup"><span data-stu-id="78146-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="78146-465">86 个小写或大写字母、数字、正斜杠 （/） 或加号 （+） 的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="78146-466">两个相等符号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-467">校验</span><span class="sxs-lookup"><span data-stu-id="78146-467">Checksum</span></span>

<span data-ttu-id="78146-468">否</span><span class="sxs-lookup"><span data-stu-id="78146-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-469">定義</span><span class="sxs-lookup"><span data-stu-id="78146-469">Definition</span></span>

<span data-ttu-id="78146-470">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-471">正则表达式 CEP_Regex_AzureDocumentDBAuthKey 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-472">正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-473">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="78146-474">CEP_通用示例关键字</span><span class="sxs-lookup"><span data-stu-id="78146-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="78146-475">（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="78146-476">康托索</span><span class="sxs-lookup"><span data-stu-id="78146-476">contoso</span></span>
- <span data-ttu-id="78146-477">法布里卡姆</span><span class="sxs-lookup"><span data-stu-id="78146-477">fabrikam</span></span>
- <span data-ttu-id="78146-478">北风</span><span class="sxs-lookup"><span data-stu-id="78146-478">northwind</span></span>
- <span data-ttu-id="78146-479">沙 箱</span><span class="sxs-lookup"><span data-stu-id="78146-479">sandbox</span></span>
- <span data-ttu-id="78146-480">一个盒子</span><span class="sxs-lookup"><span data-stu-id="78146-480">onebox</span></span>
- <span data-ttu-id="78146-481">本地 主机</span><span class="sxs-lookup"><span data-stu-id="78146-481">localhost</span></span>
- <span data-ttu-id="78146-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="78146-482">127.0.0.1</span></span>
- <span data-ttu-id="78146-483">试验。</span><span class="sxs-lookup"><span data-stu-id="78146-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="78146-484">Com</span><span class="sxs-lookup"><span data-stu-id="78146-484">com</span></span>
- <span data-ttu-id="78146-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="78146-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="78146-486">网</span><span class="sxs-lookup"><span data-stu-id="78146-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="78146-487">Azure IAAS 数据库连接字符串和 Azure SQL 连接字符串</span><span class="sxs-lookup"><span data-stu-id="78146-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="78146-488">格式</span><span class="sxs-lookup"><span data-stu-id="78146-488">Format</span></span>

<span data-ttu-id="78146-489">字符串"服务器"、"服务器"或"数据源"后跟以下模式中概述的字符和字符串，包括字符串"cloudapp.azure"。</span><span class="sxs-lookup"><span data-stu-id="78146-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="78146-490">com"或"云应用程序.azure"。</span><span class="sxs-lookup"><span data-stu-id="78146-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="78146-491">net"或"数据库.窗口"。</span><span class="sxs-lookup"><span data-stu-id="78146-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="78146-492">net"，以及字符串"密码"或"密码"或"pwd"。</span><span class="sxs-lookup"><span data-stu-id="78146-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-493">模式</span><span class="sxs-lookup"><span data-stu-id="78146-493">Pattern</span></span>

- <span data-ttu-id="78146-494">字符串"服务器"、"服务器"或"数据源"</span><span class="sxs-lookup"><span data-stu-id="78146-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="78146-495">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-496">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-496">An equal sign (=)</span></span>
- <span data-ttu-id="78146-497">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-498">1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="78146-499">字符串"cloudapp.azure"。</span><span class="sxs-lookup"><span data-stu-id="78146-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="78146-500">"网络"，"云应用程序.azure"。</span><span class="sxs-lookup"><span data-stu-id="78146-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="78146-501">net"，或"数据库.窗口"。</span><span class="sxs-lookup"><span data-stu-id="78146-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="78146-502">净</span><span class="sxs-lookup"><span data-stu-id="78146-502">net"</span></span>
- <span data-ttu-id="78146-503">1-300 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="78146-504">字符串"密码"、"密码"或"密码"</span><span class="sxs-lookup"><span data-stu-id="78146-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="78146-505">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-506">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-506">An equal sign (=)</span></span>
- <span data-ttu-id="78146-507">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-508">一个或多个不是分号（;)、引号 （） 或撇号 （'） 的字符</span><span class="sxs-lookup"><span data-stu-id="78146-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="78146-509">分号（;)、引号 （）或撇号 （'）</span><span class="sxs-lookup"><span data-stu-id="78146-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-510">校验</span><span class="sxs-lookup"><span data-stu-id="78146-510">Checksum</span></span>

<span data-ttu-id="78146-511">否</span><span class="sxs-lookup"><span data-stu-id="78146-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-512">定義</span><span class="sxs-lookup"><span data-stu-id="78146-512">Definition</span></span>

<span data-ttu-id="78146-513">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-514">正则表达式 CEP_Regex_Azure 连接字符串查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-515">正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-516">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="78146-517">CEP_通用示例关键字</span><span class="sxs-lookup"><span data-stu-id="78146-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="78146-518">（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="78146-519">康托索</span><span class="sxs-lookup"><span data-stu-id="78146-519">contoso</span></span>
- <span data-ttu-id="78146-520">法布里卡姆</span><span class="sxs-lookup"><span data-stu-id="78146-520">fabrikam</span></span>
- <span data-ttu-id="78146-521">北风</span><span class="sxs-lookup"><span data-stu-id="78146-521">northwind</span></span>
- <span data-ttu-id="78146-522">沙 箱</span><span class="sxs-lookup"><span data-stu-id="78146-522">sandbox</span></span>
- <span data-ttu-id="78146-523">一个盒子</span><span class="sxs-lookup"><span data-stu-id="78146-523">onebox</span></span>
- <span data-ttu-id="78146-524">本地 主机</span><span class="sxs-lookup"><span data-stu-id="78146-524">localhost</span></span>
- <span data-ttu-id="78146-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="78146-525">127.0.0.1</span></span>
- <span data-ttu-id="78146-526">试验。</span><span class="sxs-lookup"><span data-stu-id="78146-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="78146-527">Com</span><span class="sxs-lookup"><span data-stu-id="78146-527">com</span></span>
- <span data-ttu-id="78146-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="78146-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="78146-529">网</span><span class="sxs-lookup"><span data-stu-id="78146-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="78146-530">Azure IoT 连接字符串</span><span class="sxs-lookup"><span data-stu-id="78146-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="78146-531">格式</span><span class="sxs-lookup"><span data-stu-id="78146-531">Format</span></span>

<span data-ttu-id="78146-532">字符串"HostName"后跟以下模式中概述的字符和字符串，包括字符串"azure 设备"。</span><span class="sxs-lookup"><span data-stu-id="78146-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="78146-533">net"和"共享访问密钥"。</span><span class="sxs-lookup"><span data-stu-id="78146-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-534">模式</span><span class="sxs-lookup"><span data-stu-id="78146-534">Pattern</span></span>

- <span data-ttu-id="78146-535">字符串"主机名"</span><span class="sxs-lookup"><span data-stu-id="78146-535">The string "HostName"</span></span>
- <span data-ttu-id="78146-536">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-537">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-537">An equal sign (=)</span></span>
- <span data-ttu-id="78146-538">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-539">1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="78146-540">字符串"Azure 设备"。</span><span class="sxs-lookup"><span data-stu-id="78146-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="78146-541">净</span><span class="sxs-lookup"><span data-stu-id="78146-541">net"</span></span>
- <span data-ttu-id="78146-542">1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="78146-543">字符串"共享访问密钥"</span><span class="sxs-lookup"><span data-stu-id="78146-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="78146-544">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-545">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-545">An equal sign (=)</span></span>
- <span data-ttu-id="78146-546">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-547">43 个小写或大写字母、数字、正斜杠 （/） 或加号 （+） 的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="78146-548">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-549">校验</span><span class="sxs-lookup"><span data-stu-id="78146-549">Checksum</span></span>

<span data-ttu-id="78146-550">否</span><span class="sxs-lookup"><span data-stu-id="78146-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-551">定義</span><span class="sxs-lookup"><span data-stu-id="78146-551">Definition</span></span>

<span data-ttu-id="78146-552">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-553">正则表达式 CEP_Regex_AzureIoT 连接字符串查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-554">正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-555">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="78146-556">CEP_通用示例关键字</span><span class="sxs-lookup"><span data-stu-id="78146-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="78146-557">（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="78146-558">康托索</span><span class="sxs-lookup"><span data-stu-id="78146-558">contoso</span></span>
- <span data-ttu-id="78146-559">法布里卡姆</span><span class="sxs-lookup"><span data-stu-id="78146-559">fabrikam</span></span>
- <span data-ttu-id="78146-560">北风</span><span class="sxs-lookup"><span data-stu-id="78146-560">northwind</span></span>
- <span data-ttu-id="78146-561">沙 箱</span><span class="sxs-lookup"><span data-stu-id="78146-561">sandbox</span></span>
- <span data-ttu-id="78146-562">一个盒子</span><span class="sxs-lookup"><span data-stu-id="78146-562">onebox</span></span>
- <span data-ttu-id="78146-563">本地 主机</span><span class="sxs-lookup"><span data-stu-id="78146-563">localhost</span></span>
- <span data-ttu-id="78146-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="78146-564">127.0.0.1</span></span>
- <span data-ttu-id="78146-565">试验。</span><span class="sxs-lookup"><span data-stu-id="78146-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="78146-566">Com</span><span class="sxs-lookup"><span data-stu-id="78146-566">com</span></span>
- <span data-ttu-id="78146-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="78146-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="78146-568">网</span><span class="sxs-lookup"><span data-stu-id="78146-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="78146-569">Azure 发布设置密码</span><span class="sxs-lookup"><span data-stu-id="78146-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="78146-570">格式</span><span class="sxs-lookup"><span data-stu-id="78146-570">Format</span></span>

<span data-ttu-id="78146-571">字符串"userpwd_"后跟字母数字字符串。</span><span class="sxs-lookup"><span data-stu-id="78146-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-572">模式</span><span class="sxs-lookup"><span data-stu-id="78146-572">Pattern</span></span>

- <span data-ttu-id="78146-573">字符串"userpwd_"</span><span class="sxs-lookup"><span data-stu-id="78146-573">The string "userpwd="</span></span>
- <span data-ttu-id="78146-574">60 个小写字母或数字的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="78146-575">引号 （"）</span><span class="sxs-lookup"><span data-stu-id="78146-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-576">校验</span><span class="sxs-lookup"><span data-stu-id="78146-576">Checksum</span></span>

<span data-ttu-id="78146-577">否</span><span class="sxs-lookup"><span data-stu-id="78146-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-578">定義</span><span class="sxs-lookup"><span data-stu-id="78146-578">Definition</span></span>

<span data-ttu-id="78146-579">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-580">正则表达式 CEP_Regex_AzurePublishSettingPasswords 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-581">正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="78146-582">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="78146-583">CEP_通用示例关键字</span><span class="sxs-lookup"><span data-stu-id="78146-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="78146-584">（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="78146-585">康托索</span><span class="sxs-lookup"><span data-stu-id="78146-585">contoso</span></span>
- <span data-ttu-id="78146-586">法布里卡姆</span><span class="sxs-lookup"><span data-stu-id="78146-586">fabrikam</span></span>
- <span data-ttu-id="78146-587">北风</span><span class="sxs-lookup"><span data-stu-id="78146-587">northwind</span></span>
- <span data-ttu-id="78146-588">沙 箱</span><span class="sxs-lookup"><span data-stu-id="78146-588">sandbox</span></span>
- <span data-ttu-id="78146-589">一个盒子</span><span class="sxs-lookup"><span data-stu-id="78146-589">onebox</span></span>
- <span data-ttu-id="78146-590">本地 主机</span><span class="sxs-lookup"><span data-stu-id="78146-590">localhost</span></span>
- <span data-ttu-id="78146-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="78146-591">127.0.0.1</span></span>
- <span data-ttu-id="78146-592">试验。</span><span class="sxs-lookup"><span data-stu-id="78146-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="78146-593">Com</span><span class="sxs-lookup"><span data-stu-id="78146-593">com</span></span>
- <span data-ttu-id="78146-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="78146-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="78146-595">网</span><span class="sxs-lookup"><span data-stu-id="78146-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="78146-596">Azure Redis 缓存连接字符串</span><span class="sxs-lookup"><span data-stu-id="78146-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="78146-597">格式</span><span class="sxs-lookup"><span data-stu-id="78146-597">Format</span></span>

<span data-ttu-id="78146-598">字符串"redis.cache.windows"。</span><span class="sxs-lookup"><span data-stu-id="78146-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="78146-599">net"后跟以下模式中概述的字符和字符串，包括字符串"密码"或"pwd"。</span><span class="sxs-lookup"><span data-stu-id="78146-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-600">模式</span><span class="sxs-lookup"><span data-stu-id="78146-600">Pattern</span></span>

- <span data-ttu-id="78146-601">字符串"redis.cache.windows"。</span><span class="sxs-lookup"><span data-stu-id="78146-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="78146-602">净</span><span class="sxs-lookup"><span data-stu-id="78146-602">net"</span></span>
- <span data-ttu-id="78146-603">1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="78146-604">字符串"密码"或"密码"</span><span class="sxs-lookup"><span data-stu-id="78146-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="78146-605">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-606">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-606">An equal sign (=)</span></span>
- <span data-ttu-id="78146-607">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-608">43 个字符的任意组合，这些字符是小写或大写字母、数字、正斜杠 （/） 或加号 （+）</span><span class="sxs-lookup"><span data-stu-id="78146-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="78146-609">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-610">校验</span><span class="sxs-lookup"><span data-stu-id="78146-610">Checksum</span></span>

<span data-ttu-id="78146-611">否</span><span class="sxs-lookup"><span data-stu-id="78146-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-612">定義</span><span class="sxs-lookup"><span data-stu-id="78146-612">Definition</span></span>

<span data-ttu-id="78146-613">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-614">正则表达式 CEP_Regex_AzureRedisCache 连接字符串查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="78146-615">正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-616">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="78146-617">CEP_通用示例关键字</span><span class="sxs-lookup"><span data-stu-id="78146-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="78146-618">（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="78146-619">康托索</span><span class="sxs-lookup"><span data-stu-id="78146-619">contoso</span></span>
- <span data-ttu-id="78146-620">法布里卡姆</span><span class="sxs-lookup"><span data-stu-id="78146-620">fabrikam</span></span>
- <span data-ttu-id="78146-621">北风</span><span class="sxs-lookup"><span data-stu-id="78146-621">northwind</span></span>
- <span data-ttu-id="78146-622">沙 箱</span><span class="sxs-lookup"><span data-stu-id="78146-622">sandbox</span></span>
- <span data-ttu-id="78146-623">一个盒子</span><span class="sxs-lookup"><span data-stu-id="78146-623">onebox</span></span>
- <span data-ttu-id="78146-624">本地 主机</span><span class="sxs-lookup"><span data-stu-id="78146-624">localhost</span></span>
- <span data-ttu-id="78146-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="78146-625">127.0.0.1</span></span>
- <span data-ttu-id="78146-626">试验。</span><span class="sxs-lookup"><span data-stu-id="78146-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="78146-627">Com</span><span class="sxs-lookup"><span data-stu-id="78146-627">com</span></span>
- <span data-ttu-id="78146-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="78146-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="78146-629">网</span><span class="sxs-lookup"><span data-stu-id="78146-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="78146-630">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="78146-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="78146-631">格式</span><span class="sxs-lookup"><span data-stu-id="78146-631">Format</span></span>

<span data-ttu-id="78146-632">字符串"sig"后跟以下模式中概述的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="78146-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-633">模式</span><span class="sxs-lookup"><span data-stu-id="78146-633">Pattern</span></span>

- <span data-ttu-id="78146-634">字符串"sig"</span><span class="sxs-lookup"><span data-stu-id="78146-634">The string "sig"</span></span>
- <span data-ttu-id="78146-635">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-636">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-636">An equal sign (=)</span></span>
- <span data-ttu-id="78146-637">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-638">43-53 个字符之间的任意组合，这些字符是小写或大写字母、数字或百分比符号 （%）</span><span class="sxs-lookup"><span data-stu-id="78146-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="78146-639">字符串"%3d"</span><span class="sxs-lookup"><span data-stu-id="78146-639">The string "%3d"</span></span>
- <span data-ttu-id="78146-640">不是小写或大写字母、数字或百分比符号的任何字符 （%）</span><span class="sxs-lookup"><span data-stu-id="78146-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-641">校验</span><span class="sxs-lookup"><span data-stu-id="78146-641">Checksum</span></span>

<span data-ttu-id="78146-642">否</span><span class="sxs-lookup"><span data-stu-id="78146-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-643">定義</span><span class="sxs-lookup"><span data-stu-id="78146-643">Definition</span></span>

<span data-ttu-id="78146-644">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-645">正则表达式 CEP_Regex_AzureSAS 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="78146-646">Azure 服务总线连接字符串</span><span class="sxs-lookup"><span data-stu-id="78146-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="78146-647">格式</span><span class="sxs-lookup"><span data-stu-id="78146-647">Format</span></span>

<span data-ttu-id="78146-648">字符串"EndPoint"后跟以下模式中概述的字符和字符串，包括字符串"servicebus.windows"。</span><span class="sxs-lookup"><span data-stu-id="78146-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="78146-649">net"和"共享AccesKey"。</span><span class="sxs-lookup"><span data-stu-id="78146-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-650">模式</span><span class="sxs-lookup"><span data-stu-id="78146-650">Pattern</span></span>

- <span data-ttu-id="78146-651">字符串"结束点"</span><span class="sxs-lookup"><span data-stu-id="78146-651">The string "EndPoint"</span></span>
- <span data-ttu-id="78146-652">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-653">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-653">An equal sign (=)</span></span>
- <span data-ttu-id="78146-654">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-655">1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="78146-656">字符串"服务总线.窗口。</span><span class="sxs-lookup"><span data-stu-id="78146-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="78146-657">净</span><span class="sxs-lookup"><span data-stu-id="78146-657">net"</span></span>
- <span data-ttu-id="78146-658">1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="78146-659">字符串"共享访问密钥"</span><span class="sxs-lookup"><span data-stu-id="78146-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="78146-660">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-661">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-661">An equal sign (=)</span></span>
- <span data-ttu-id="78146-662">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-663">43 个字符的任意组合，这些字符是小写或大写字母、数字、正斜杠 （/） 或加号 （+）</span><span class="sxs-lookup"><span data-stu-id="78146-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="78146-664">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-665">校验</span><span class="sxs-lookup"><span data-stu-id="78146-665">Checksum</span></span>

<span data-ttu-id="78146-666">否</span><span class="sxs-lookup"><span data-stu-id="78146-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-667">定義</span><span class="sxs-lookup"><span data-stu-id="78146-667">Definition</span></span>

<span data-ttu-id="78146-668">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-669">正则表达式 CEP_Regex_Azure ServiceBusConnectString 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="78146-670">正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-671">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="78146-672">CEP_通用示例关键字</span><span class="sxs-lookup"><span data-stu-id="78146-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="78146-673">（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="78146-674">康托索</span><span class="sxs-lookup"><span data-stu-id="78146-674">contoso</span></span>
- <span data-ttu-id="78146-675">法布里卡姆</span><span class="sxs-lookup"><span data-stu-id="78146-675">fabrikam</span></span>
- <span data-ttu-id="78146-676">北风</span><span class="sxs-lookup"><span data-stu-id="78146-676">northwind</span></span>
- <span data-ttu-id="78146-677">沙 箱</span><span class="sxs-lookup"><span data-stu-id="78146-677">sandbox</span></span>
- <span data-ttu-id="78146-678">一个盒子</span><span class="sxs-lookup"><span data-stu-id="78146-678">onebox</span></span>
- <span data-ttu-id="78146-679">本地 主机</span><span class="sxs-lookup"><span data-stu-id="78146-679">localhost</span></span>
- <span data-ttu-id="78146-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="78146-680">127.0.0.1</span></span>
- <span data-ttu-id="78146-681">试验。</span><span class="sxs-lookup"><span data-stu-id="78146-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="78146-682">Com</span><span class="sxs-lookup"><span data-stu-id="78146-682">com</span></span>
- <span data-ttu-id="78146-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="78146-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="78146-684">网</span><span class="sxs-lookup"><span data-stu-id="78146-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="78146-685">Azure 存储帐户密钥</span><span class="sxs-lookup"><span data-stu-id="78146-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="78146-686">格式</span><span class="sxs-lookup"><span data-stu-id="78146-686">Format</span></span>

<span data-ttu-id="78146-687">字符串"DefaultEndpointsProtocol"后跟以下模式中概述的字符和字符串，包括字符串"帐户密钥"。</span><span class="sxs-lookup"><span data-stu-id="78146-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-688">模式</span><span class="sxs-lookup"><span data-stu-id="78146-688">Pattern</span></span>

- <span data-ttu-id="78146-689">字符串"默认终结点协议"</span><span class="sxs-lookup"><span data-stu-id="78146-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="78146-690">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-691">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-691">An equal sign (=)</span></span>
- <span data-ttu-id="78146-692">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-693">1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="78146-694">字符串"帐户密钥"</span><span class="sxs-lookup"><span data-stu-id="78146-694">The string "AccountKey"</span></span>
- <span data-ttu-id="78146-695">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-696">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-696">An equal sign (=)</span></span>
- <span data-ttu-id="78146-697">0-2 空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="78146-698">86 个字符的任意组合，这些字符是小写或大写字母、数字、正斜杠 （/） 或加号 （+）</span><span class="sxs-lookup"><span data-stu-id="78146-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="78146-699">两个相等符号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-700">校验</span><span class="sxs-lookup"><span data-stu-id="78146-700">Checksum</span></span>

<span data-ttu-id="78146-701">否</span><span class="sxs-lookup"><span data-stu-id="78146-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-702">定義</span><span class="sxs-lookup"><span data-stu-id="78146-702">Definition</span></span>

<span data-ttu-id="78146-703">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-704">正则表达式 CEP_Regex_AzureStorageAccountKey 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-705">正则表达式 CEP_AzureEmulor 存储帐户筛选器**找不到**与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="78146-706">正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-707">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="78146-708">CEP_Azure 仿真器存储帐户筛选器</span><span class="sxs-lookup"><span data-stu-id="78146-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="78146-709">（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="78146-710">Eby8vdM02xNOcqFluwJpllmetlDX1OUzTFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw_\*</span><span class="sxs-lookup"><span data-stu-id="78146-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="78146-711">CEP_通用示例关键字</span><span class="sxs-lookup"><span data-stu-id="78146-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="78146-712">（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="78146-713">康托索</span><span class="sxs-lookup"><span data-stu-id="78146-713">contoso</span></span>
- <span data-ttu-id="78146-714">法布里卡姆</span><span class="sxs-lookup"><span data-stu-id="78146-714">fabrikam</span></span>
- <span data-ttu-id="78146-715">北风</span><span class="sxs-lookup"><span data-stu-id="78146-715">northwind</span></span>
- <span data-ttu-id="78146-716">沙 箱</span><span class="sxs-lookup"><span data-stu-id="78146-716">sandbox</span></span>
- <span data-ttu-id="78146-717">一个盒子</span><span class="sxs-lookup"><span data-stu-id="78146-717">onebox</span></span>
- <span data-ttu-id="78146-718">本地 主机</span><span class="sxs-lookup"><span data-stu-id="78146-718">localhost</span></span>
- <span data-ttu-id="78146-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="78146-719">127.0.0.1</span></span>
- <span data-ttu-id="78146-720">试验。</span><span class="sxs-lookup"><span data-stu-id="78146-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="78146-721">Com</span><span class="sxs-lookup"><span data-stu-id="78146-721">com</span></span>
- <span data-ttu-id="78146-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="78146-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="78146-723">网</span><span class="sxs-lookup"><span data-stu-id="78146-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="78146-724">Azure 存储帐户密钥（通用）</span><span class="sxs-lookup"><span data-stu-id="78146-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="78146-725">格式</span><span class="sxs-lookup"><span data-stu-id="78146-725">Format</span></span>

<span data-ttu-id="78146-726">86 个小写或大写字母、数字、正斜杠 （/） 或加号 （+）的任意组合，前面或后面是下图中概述的字符。</span><span class="sxs-lookup"><span data-stu-id="78146-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-727">模式</span><span class="sxs-lookup"><span data-stu-id="78146-727">Pattern</span></span>

- <span data-ttu-id="78146-728">大于符号 （>）、撇号 （'）、等号 （+）、引号 （）或数字符号 （\*） 的 0-1</span><span class="sxs-lookup"><span data-stu-id="78146-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="78146-729">86 个字符的任意组合，这些字符是小写或大写字母、数字、正斜杠 （/） 或加号 （+）</span><span class="sxs-lookup"><span data-stu-id="78146-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="78146-730">两个相等符号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="78146-731">校验</span><span class="sxs-lookup"><span data-stu-id="78146-731">Checksum</span></span>

<span data-ttu-id="78146-732">否</span><span class="sxs-lookup"><span data-stu-id="78146-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-733">定義</span><span class="sxs-lookup"><span data-stu-id="78146-733">Definition</span></span>

<span data-ttu-id="78146-734">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-735">正则表达式 CEP_Regex_AzureStorageKey 一般查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="78146-736">比利時國民編碼</span><span class="sxs-lookup"><span data-stu-id="78146-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-737">格式</span><span class="sxs-lookup"><span data-stu-id="78146-737">Format</span></span>

<span data-ttu-id="78146-738">11 位数字加上分隔符</span><span class="sxs-lookup"><span data-stu-id="78146-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-739">模式</span><span class="sxs-lookup"><span data-stu-id="78146-739">Pattern</span></span>

<span data-ttu-id="78146-740">11 位数字加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="78146-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="78146-741">格式 YY 的六位数字和两个句点。毫米。出生日期的 DD</span><span class="sxs-lookup"><span data-stu-id="78146-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="78146-742">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-742">A hyphen</span></span> 
- <span data-ttu-id="78146-743">三个连续数字（男性的奇数，甚至女性）</span><span class="sxs-lookup"><span data-stu-id="78146-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="78146-744">一个期间</span><span class="sxs-lookup"><span data-stu-id="78146-744">A period</span></span> 
- <span data-ttu-id="78146-745">作为校验位数的两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-746">校验</span><span class="sxs-lookup"><span data-stu-id="78146-746">Checksum</span></span>

<span data-ttu-id="78146-747">是</span><span class="sxs-lookup"><span data-stu-id="78146-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-748">定義</span><span class="sxs-lookup"><span data-stu-id="78146-748">Definition</span></span>

<span data-ttu-id="78146-749">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-750">函数 Func_belgium_national_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-751">找到关键字_belgium_national_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="78146-752">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-753">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="78146-754">关键字_belgium_国家_数字</span><span class="sxs-lookup"><span data-stu-id="78146-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="78146-755">身分識別</span><span class="sxs-lookup"><span data-stu-id="78146-755">Identity</span></span>
- <span data-ttu-id="78146-756">注册</span><span class="sxs-lookup"><span data-stu-id="78146-756">Registration</span></span>
- <span data-ttu-id="78146-757">识别</span><span class="sxs-lookup"><span data-stu-id="78146-757">Identification</span></span> 
- <span data-ttu-id="78146-758">ID</span><span class="sxs-lookup"><span data-stu-id="78146-758">ID</span></span> 
- <span data-ttu-id="78146-759">身份识别</span><span class="sxs-lookup"><span data-stu-id="78146-759">Identiteitskaart</span></span>
- <span data-ttu-id="78146-760">注册人努默</span><span class="sxs-lookup"><span data-stu-id="78146-760">Registratie nummer</span></span> 
- <span data-ttu-id="78146-761">身份识别 nummer</span><span class="sxs-lookup"><span data-stu-id="78146-761">Identificatie nummer</span></span> 
- <span data-ttu-id="78146-762">身份识别</span><span class="sxs-lookup"><span data-stu-id="78146-762">Identiteit</span></span>
- <span data-ttu-id="78146-763">注册人</span><span class="sxs-lookup"><span data-stu-id="78146-763">Registratie</span></span>
- <span data-ttu-id="78146-764">身份识别</span><span class="sxs-lookup"><span data-stu-id="78146-764">Identificatie</span></span> 
- <span data-ttu-id="78146-765">卡特·德·标识特</span><span class="sxs-lookup"><span data-stu-id="78146-765">Carte d’identité</span></span> 
- <span data-ttu-id="78146-766">numéro d'itriculation</span><span class="sxs-lookup"><span data-stu-id="78146-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="78146-767">numéro d'标识</span><span class="sxs-lookup"><span data-stu-id="78146-767">numéro d'identification</span></span>
- <span data-ttu-id="78146-768">身份\*</span><span class="sxs-lookup"><span data-stu-id="78146-768">identité</span></span> 
- <span data-ttu-id="78146-769">题词</span><span class="sxs-lookup"><span data-stu-id="78146-769">inscription</span></span> 
- <span data-ttu-id="78146-770">标识</span><span class="sxs-lookup"><span data-stu-id="78146-770">Identifikation</span></span>
- <span data-ttu-id="78146-771">身份识别</span><span class="sxs-lookup"><span data-stu-id="78146-771">Identifizierung</span></span>
- <span data-ttu-id="78146-772">识别nummer</span><span class="sxs-lookup"><span data-stu-id="78146-772">Identifikationsnummer</span></span>
- <span data-ttu-id="78146-773">个人</span><span class="sxs-lookup"><span data-stu-id="78146-773">Personalausweis</span></span>
- <span data-ttu-id="78146-774">注册人</span><span class="sxs-lookup"><span data-stu-id="78146-774">Registrierung</span></span>
- <span data-ttu-id="78146-775">注册斯努默</span><span class="sxs-lookup"><span data-stu-id="78146-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="78146-776">巴西公积金号码</span><span class="sxs-lookup"><span data-stu-id="78146-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-777">格式</span><span class="sxs-lookup"><span data-stu-id="78146-777">Format</span></span>

<span data-ttu-id="78146-778">包含校验数字的 11 位数字，可以格式化或未格式化</span><span class="sxs-lookup"><span data-stu-id="78146-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-779">模式</span><span class="sxs-lookup"><span data-stu-id="78146-779">Pattern</span></span>

<span data-ttu-id="78146-780">格式 化：</span><span class="sxs-lookup"><span data-stu-id="78146-780">Formatted:</span></span>
- <span data-ttu-id="78146-781">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-781">Three digits</span></span> 
- <span data-ttu-id="78146-782">一个期间</span><span class="sxs-lookup"><span data-stu-id="78146-782">A period</span></span> 
- <span data-ttu-id="78146-783">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-783">Three digits</span></span> 
- <span data-ttu-id="78146-784">一个期间</span><span class="sxs-lookup"><span data-stu-id="78146-784">A period</span></span> 
- <span data-ttu-id="78146-785">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-785">Three digits</span></span> 
- <span data-ttu-id="78146-786">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-786">A hyphen</span></span> 
- <span data-ttu-id="78146-787">两位数字是支票数字</span><span class="sxs-lookup"><span data-stu-id="78146-787">Two digits which are check digits</span></span>

<span data-ttu-id="78146-788">未格式化：</span><span class="sxs-lookup"><span data-stu-id="78146-788">Unformatted:</span></span>
- <span data-ttu-id="78146-789">11 位数字，其中最后两位数字为支票数字</span><span class="sxs-lookup"><span data-stu-id="78146-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-790">校验</span><span class="sxs-lookup"><span data-stu-id="78146-790">Checksum</span></span>

<span data-ttu-id="78146-791">是</span><span class="sxs-lookup"><span data-stu-id="78146-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-792">定義</span><span class="sxs-lookup"><span data-stu-id="78146-792">Definition</span></span>

<span data-ttu-id="78146-793">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-794">函数 Func_brazil_cpf 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-795">找到关键字_brazil_cpf 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="78146-796">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-796">The checksum passes.</span></span>

<span data-ttu-id="78146-797">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-798">函数 Func_brazil_cpf 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-799">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-800">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="78146-801">关键字_巴西_cpf</span><span class="sxs-lookup"><span data-stu-id="78146-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="78146-802">公积金</span><span class="sxs-lookup"><span data-stu-id="78146-802">CPF</span></span>
- <span data-ttu-id="78146-803">识别</span><span class="sxs-lookup"><span data-stu-id="78146-803">Identification</span></span>
- <span data-ttu-id="78146-804">注册</span><span class="sxs-lookup"><span data-stu-id="78146-804">Registration</span></span>
- <span data-ttu-id="78146-805">收入</span><span class="sxs-lookup"><span data-stu-id="78146-805">Revenue</span></span>
- <span data-ttu-id="78146-806">卡德斯特罗·德佩索亚斯·费西卡斯</span><span class="sxs-lookup"><span data-stu-id="78146-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="78146-807">因波托</span><span class="sxs-lookup"><span data-stu-id="78146-807">Imposto</span></span> 
- <span data-ttu-id="78146-808">身份识别</span><span class="sxs-lookup"><span data-stu-id="78146-808">Identificação</span></span> 
- <span data-ttu-id="78146-809">因斯克里尼奥</span><span class="sxs-lookup"><span data-stu-id="78146-809">Inscrição</span></span> 
- <span data-ttu-id="78146-810">雷切塔</span><span class="sxs-lookup"><span data-stu-id="78146-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="78146-811">巴西法人编号</span><span class="sxs-lookup"><span data-stu-id="78146-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="78146-812">格式</span><span class="sxs-lookup"><span data-stu-id="78146-812">Format</span></span>

<span data-ttu-id="78146-813">14 位数字，包括注册号、分支编号和支票数字，以及分隔符</span><span class="sxs-lookup"><span data-stu-id="78146-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-814">模式</span><span class="sxs-lookup"><span data-stu-id="78146-814">Pattern</span></span>
<span data-ttu-id="78146-815">14 位数字加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="78146-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="78146-816">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-816">Two digits</span></span> 
- <span data-ttu-id="78146-817">一个期间</span><span class="sxs-lookup"><span data-stu-id="78146-817">A period</span></span> 
- <span data-ttu-id="78146-818">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-818">Three digits</span></span> 
- <span data-ttu-id="78146-819">一个期间</span><span class="sxs-lookup"><span data-stu-id="78146-819">A period</span></span> 
- <span data-ttu-id="78146-820">三位数字（前八位数字是注册号码）</span><span class="sxs-lookup"><span data-stu-id="78146-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="78146-821">正向斜杠</span><span class="sxs-lookup"><span data-stu-id="78146-821">A forward slash</span></span> 
- <span data-ttu-id="78146-822">四位分支编号</span><span class="sxs-lookup"><span data-stu-id="78146-822">Four-digit branch number</span></span> 
- <span data-ttu-id="78146-823">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-823">A hyphen</span></span> 
- <span data-ttu-id="78146-824">两位数字是支票数字</span><span class="sxs-lookup"><span data-stu-id="78146-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-825">校验</span><span class="sxs-lookup"><span data-stu-id="78146-825">Checksum</span></span>

<span data-ttu-id="78146-826">是</span><span class="sxs-lookup"><span data-stu-id="78146-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-827">定義</span><span class="sxs-lookup"><span data-stu-id="78146-827">Definition</span></span>

<span data-ttu-id="78146-828">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-829">函数 Func_brazil_cnpj 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-830">找到关键字_brazil_cnpj的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="78146-831">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-831">The checksum passes.</span></span>

<span data-ttu-id="78146-832">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-833">函数 Func_brazil_cnpj 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-834">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-835">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="78146-836">关键词_巴西\cnpj</span><span class="sxs-lookup"><span data-stu-id="78146-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="78146-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="78146-837">CNPJ</span></span> 
- <span data-ttu-id="78146-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="78146-838">CNPJ/MF</span></span> 
- <span data-ttu-id="78146-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="78146-839">CNPJ-MF</span></span> 
- <span data-ttu-id="78146-840">国家法人登记处</span><span class="sxs-lookup"><span data-stu-id="78146-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="78146-841">纳税人登记处</span><span class="sxs-lookup"><span data-stu-id="78146-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="78146-842">法人</span><span class="sxs-lookup"><span data-stu-id="78146-842">Legal entity</span></span> 
- <span data-ttu-id="78146-843">法人</span><span class="sxs-lookup"><span data-stu-id="78146-843">Legal entities</span></span> 
- <span data-ttu-id="78146-844">注册状态</span><span class="sxs-lookup"><span data-stu-id="78146-844">Registration Status</span></span> 
- <span data-ttu-id="78146-845">商務版</span><span class="sxs-lookup"><span data-stu-id="78146-845">Business</span></span> 
- <span data-ttu-id="78146-846">Company</span><span class="sxs-lookup"><span data-stu-id="78146-846">Company</span></span>
- <span data-ttu-id="78146-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="78146-847">CNPJ</span></span> 
- <span data-ttu-id="78146-848">国家佩索阿·朱利亚</span><span class="sxs-lookup"><span data-stu-id="78146-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="78146-849">卡德斯特罗·杰拉尔·德·康特里特</span><span class="sxs-lookup"><span data-stu-id="78146-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="78146-850">CGC</span><span class="sxs-lookup"><span data-stu-id="78146-850">CGC</span></span> 
- <span data-ttu-id="78146-851">佩索阿·法里迪卡</span><span class="sxs-lookup"><span data-stu-id="78146-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="78146-852">佩索亚斯·法里卡</span><span class="sxs-lookup"><span data-stu-id="78146-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="78146-853">西图塔奥地籍</span><span class="sxs-lookup"><span data-stu-id="78146-853">Situação cadastral</span></span> 
- <span data-ttu-id="78146-854">因斯克里尼奥</span><span class="sxs-lookup"><span data-stu-id="78146-854">Inscrição</span></span> 
- <span data-ttu-id="78146-855">埃姆普雷萨</span><span class="sxs-lookup"><span data-stu-id="78146-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="78146-856">巴西国民身份证</span><span class="sxs-lookup"><span data-stu-id="78146-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="78146-857">格式</span><span class="sxs-lookup"><span data-stu-id="78146-857">Format</span></span>

<span data-ttu-id="78146-858">注册人杰拉尔（旧格式）：九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="78146-859">注册（RIC）（新格式）：11 位</span><span class="sxs-lookup"><span data-stu-id="78146-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-860">模式</span><span class="sxs-lookup"><span data-stu-id="78146-860">Pattern</span></span>

<span data-ttu-id="78146-861">注册人杰拉尔（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="78146-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="78146-862">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-862">Two digits</span></span> 
- <span data-ttu-id="78146-863">一个期间</span><span class="sxs-lookup"><span data-stu-id="78146-863">A period</span></span> 
- <span data-ttu-id="78146-864">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-864">Three digits</span></span> 
- <span data-ttu-id="78146-865">一个期间</span><span class="sxs-lookup"><span data-stu-id="78146-865">A period</span></span> 
- <span data-ttu-id="78146-866">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-866">Three digits</span></span> 
- <span data-ttu-id="78146-867">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-867">A hyphen</span></span> 
- <span data-ttu-id="78146-868">一个数字，即校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-868">One digit which is a check digit</span></span>

<span data-ttu-id="78146-869">注册（RIC）（新格式）：</span><span class="sxs-lookup"><span data-stu-id="78146-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="78146-870">10 位</span><span class="sxs-lookup"><span data-stu-id="78146-870">10 digits</span></span> 
- <span data-ttu-id="78146-871">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-871">A hyphen</span></span> 
- <span data-ttu-id="78146-872">一个数字，即校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-873">校验</span><span class="sxs-lookup"><span data-stu-id="78146-873">Checksum</span></span>

<span data-ttu-id="78146-874">是</span><span class="sxs-lookup"><span data-stu-id="78146-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-875">定義</span><span class="sxs-lookup"><span data-stu-id="78146-875">Definition</span></span>

<span data-ttu-id="78146-876">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-877">函数 Func_brazil_rg 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-878">找到关键字_brazil_rg 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="78146-879">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-879">The checksum passes.</span></span>

<span data-ttu-id="78146-880">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-881">函数 Func_brazil_rg 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-882">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-883">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="78146-884">关键字_巴西\rg</span><span class="sxs-lookup"><span data-stu-id="78146-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="78146-885">Cédula de identidade 身份证 国民 ID n_mero de 注册注册注册 GERal RG （此关键字是区分大小写） RIC （此关键字是区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="78146-886">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="78146-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-887">格式</span><span class="sxs-lookup"><span data-stu-id="78146-887">Format</span></span>

<span data-ttu-id="78146-888">七或十二位</span><span class="sxs-lookup"><span data-stu-id="78146-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-889">模式</span><span class="sxs-lookup"><span data-stu-id="78146-889">Pattern</span></span>

<span data-ttu-id="78146-890">加拿大银行帐号为七位或十二位数字。</span><span class="sxs-lookup"><span data-stu-id="78146-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="78146-891">加拿大银行账户中转号码为：</span><span class="sxs-lookup"><span data-stu-id="78146-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="78146-892">五位数字</span><span class="sxs-lookup"><span data-stu-id="78146-892">Five digits</span></span> 
- <span data-ttu-id="78146-893">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-893">A hyphen</span></span> 
- <span data-ttu-id="78146-894">三位或</span><span class="sxs-lookup"><span data-stu-id="78146-894">Three digits OR</span></span>
- <span data-ttu-id="78146-895">零"0"</span><span class="sxs-lookup"><span data-stu-id="78146-895">A zero "0"</span></span> 
- <span data-ttu-id="78146-896">八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-897">校验</span><span class="sxs-lookup"><span data-stu-id="78146-897">Checksum</span></span>

<span data-ttu-id="78146-898">否</span><span class="sxs-lookup"><span data-stu-id="78146-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-899">定義</span><span class="sxs-lookup"><span data-stu-id="78146-899">Definition</span></span>

<span data-ttu-id="78146-900">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-901">正则表达式 Regex_canada_bank_帐户_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-902">找到关键字_加拿大_银行_帐户_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="78146-903">正则表达式 Regex_canada_bank_帐户_传输_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="78146-904">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-905">正则表达式 Regex_canada_bank_帐户_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-906">找到关键字_加拿大_银行_帐户_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-907">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="78146-908">关键词_加拿大_银行_帐户_编号</span><span class="sxs-lookup"><span data-stu-id="78146-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="78146-909">加拿大储蓄债券</span><span class="sxs-lookup"><span data-stu-id="78146-909">canada savings bonds</span></span>
- <span data-ttu-id="78146-910">加拿大税务局</span><span class="sxs-lookup"><span data-stu-id="78146-910">canada revenue agency</span></span>
- <span data-ttu-id="78146-911">加拿大金融机构</span><span class="sxs-lookup"><span data-stu-id="78146-911">canadian financial institution</span></span>
- <span data-ttu-id="78146-912">直接存款表格</span><span class="sxs-lookup"><span data-stu-id="78146-912">direct deposit form</span></span>
- <span data-ttu-id="78146-913">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="78146-913">canadian citizen</span></span>
- <span data-ttu-id="78146-914">法定代表人</span><span class="sxs-lookup"><span data-stu-id="78146-914">legal representative</span></span>
- <span data-ttu-id="78146-915">公证</span><span class="sxs-lookup"><span data-stu-id="78146-915">notary public</span></span>
- <span data-ttu-id="78146-916">宣誓专员</span><span class="sxs-lookup"><span data-stu-id="78146-916">commissioner for oaths</span></span>
- <span data-ttu-id="78146-917">儿童保育津贴</span><span class="sxs-lookup"><span data-stu-id="78146-917">child care benefit</span></span>
- <span data-ttu-id="78146-918">普遍儿童保育</span><span class="sxs-lookup"><span data-stu-id="78146-918">universal child care</span></span>
- <span data-ttu-id="78146-919">加拿大儿童税收优惠</span><span class="sxs-lookup"><span data-stu-id="78146-919">canada child tax benefit</span></span>
- <span data-ttu-id="78146-920">所得税优惠</span><span class="sxs-lookup"><span data-stu-id="78146-920">income tax benefit</span></span>
- <span data-ttu-id="78146-921">统一销售税</span><span class="sxs-lookup"><span data-stu-id="78146-921">harmonized sales tax</span></span>
- <span data-ttu-id="78146-922">社会保险号</span><span class="sxs-lookup"><span data-stu-id="78146-922">social insurance number</span></span>
- <span data-ttu-id="78146-923">所得税退税</span><span class="sxs-lookup"><span data-stu-id="78146-923">income tax refund</span></span>
- <span data-ttu-id="78146-924">儿童税收优惠</span><span class="sxs-lookup"><span data-stu-id="78146-924">child tax benefit</span></span>
- <span data-ttu-id="78146-925">领土付款</span><span class="sxs-lookup"><span data-stu-id="78146-925">territorial payments</span></span>
- <span data-ttu-id="78146-926">机构编号</span><span class="sxs-lookup"><span data-stu-id="78146-926">institution number</span></span>
- <span data-ttu-id="78146-927">存款请求</span><span class="sxs-lookup"><span data-stu-id="78146-927">deposit request</span></span>
- <span data-ttu-id="78146-928">银行信息</span><span class="sxs-lookup"><span data-stu-id="78146-928">banking information</span></span>
- <span data-ttu-id="78146-929">直接存款</span><span class="sxs-lookup"><span data-stu-id="78146-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="78146-930">加拿大驾照号码</span><span class="sxs-lookup"><span data-stu-id="78146-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-931">格式</span><span class="sxs-lookup"><span data-stu-id="78146-931">Format</span></span>

<span data-ttu-id="78146-932">因省而异</span><span class="sxs-lookup"><span data-stu-id="78146-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-933">模式</span><span class="sxs-lookup"><span data-stu-id="78146-933">Pattern</span></span>

<span data-ttu-id="78146-934">各种模式涵盖艾伯塔省、不列颠哥伦比亚省、马尼托巴省、新不伦瑞克省、纽芬兰/拉布拉多省、新斯科舍省、安大略省、爱德华王子岛省、魁北克省和萨斯喀彻温省</span><span class="sxs-lookup"><span data-stu-id="78146-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-935">校验</span><span class="sxs-lookup"><span data-stu-id="78146-935">Checksum</span></span>

<span data-ttu-id="78146-936">否</span><span class="sxs-lookup"><span data-stu-id="78146-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-937">定義</span><span class="sxs-lookup"><span data-stu-id="78146-937">Definition</span></span>

<span data-ttu-id="78146-938">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-939">函数 Func_省_名称_驱动程序_许可证_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-940">找到关键字_省名_驱动程序_许可证名称的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="78146-941">找到关键字_canada_驱动程序_许可证的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-942">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="78146-943">关键词_省名_驱动程序_许可证_名称</span><span class="sxs-lookup"><span data-stu-id="78146-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="78146-944">省缩写，例如 AB</span><span class="sxs-lookup"><span data-stu-id="78146-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="78146-945">省名称，例如艾伯塔省</span><span class="sxs-lookup"><span data-stu-id="78146-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="78146-946">关键词_加拿大_驱动程序_许可证</span><span class="sxs-lookup"><span data-stu-id="78146-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="78146-947">Dl</span><span class="sxs-lookup"><span data-stu-id="78146-947">DL</span></span>
- <span data-ttu-id="78146-948">Dls</span><span class="sxs-lookup"><span data-stu-id="78146-948">DLS</span></span>
- <span data-ttu-id="78146-949">民盟</span><span class="sxs-lookup"><span data-stu-id="78146-949">CDL</span></span>
- <span data-ttu-id="78146-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="78146-950">CDLS</span></span>
- <span data-ttu-id="78146-951">司机</span><span class="sxs-lookup"><span data-stu-id="78146-951">DriverLic</span></span>
- <span data-ttu-id="78146-952">司机</span><span class="sxs-lookup"><span data-stu-id="78146-952">DriverLics</span></span>
- <span data-ttu-id="78146-953">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-953">DriverLicense</span></span>
- <span data-ttu-id="78146-954">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-954">DriverLicenses</span></span>
- <span data-ttu-id="78146-955">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-955">DriverLicence</span></span>
- <span data-ttu-id="78146-956">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-956">DriverLicences</span></span>
- <span data-ttu-id="78146-957">司机李克</span><span class="sxs-lookup"><span data-stu-id="78146-957">Driver Lic</span></span>
- <span data-ttu-id="78146-958">司机利茨</span><span class="sxs-lookup"><span data-stu-id="78146-958">Driver Lics</span></span>
- <span data-ttu-id="78146-959">驾照</span><span class="sxs-lookup"><span data-stu-id="78146-959">Driver License</span></span>
- <span data-ttu-id="78146-960">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-960">Driver Licenses</span></span>
- <span data-ttu-id="78146-961">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-961">Driver Licence</span></span>
- <span data-ttu-id="78146-962">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-962">Driver Licences</span></span>
- <span data-ttu-id="78146-963">驱动程序</span><span class="sxs-lookup"><span data-stu-id="78146-963">DriversLic</span></span>
- <span data-ttu-id="78146-964">司机Lics</span><span class="sxs-lookup"><span data-stu-id="78146-964">DriversLics</span></span>
- <span data-ttu-id="78146-965">司机执照</span><span class="sxs-lookup"><span data-stu-id="78146-965">DriversLicence</span></span>
- <span data-ttu-id="78146-966">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-966">DriversLicences</span></span>
- <span data-ttu-id="78146-967">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-967">DriversLicense</span></span>
- <span data-ttu-id="78146-968">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-968">DriversLicenses</span></span>
- <span data-ttu-id="78146-969">司机许可证</span><span class="sxs-lookup"><span data-stu-id="78146-969">Drivers Lic</span></span>
- <span data-ttu-id="78146-970">司机利茨</span><span class="sxs-lookup"><span data-stu-id="78146-970">Drivers Lics</span></span>
- <span data-ttu-id="78146-971">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-971">Drivers License</span></span>
- <span data-ttu-id="78146-972">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-972">Drivers Licenses</span></span>
- <span data-ttu-id="78146-973">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-973">Drivers Licence</span></span>
- <span data-ttu-id="78146-974">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-974">Drivers Licences</span></span>
- <span data-ttu-id="78146-975">司机'Lic</span><span class="sxs-lookup"><span data-stu-id="78146-975">Driver'Lic</span></span>
- <span data-ttu-id="78146-976">司机的Lics</span><span class="sxs-lookup"><span data-stu-id="78146-976">Driver'Lics</span></span>
- <span data-ttu-id="78146-977">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-977">Driver'License</span></span>
- <span data-ttu-id="78146-978">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-978">Driver'Licenses</span></span>
- <span data-ttu-id="78146-979">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-979">Driver'Licence</span></span>
- <span data-ttu-id="78146-980">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-980">Driver'Licences</span></span>
- <span data-ttu-id="78146-981">司机的许可证</span><span class="sxs-lookup"><span data-stu-id="78146-981">Driver' Lic</span></span>
- <span data-ttu-id="78146-982">司机的Lics</span><span class="sxs-lookup"><span data-stu-id="78146-982">Driver' Lics</span></span>
- <span data-ttu-id="78146-983">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-983">Driver' License</span></span>
- <span data-ttu-id="78146-984">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-984">Driver' Licenses</span></span>
- <span data-ttu-id="78146-985">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-985">Driver' Licence</span></span>
- <span data-ttu-id="78146-986">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-986">Driver' Licences</span></span>
- <span data-ttu-id="78146-987">驾驶员的</span><span class="sxs-lookup"><span data-stu-id="78146-987">Driver'sLic</span></span>
- <span data-ttu-id="78146-988">驾驶员的</span><span class="sxs-lookup"><span data-stu-id="78146-988">Driver'sLics</span></span>
- <span data-ttu-id="78146-989">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-989">Driver'sLicense</span></span>
- <span data-ttu-id="78146-990">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-990">Driver'sLicenses</span></span>
- <span data-ttu-id="78146-991">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-991">Driver'sLicence</span></span>
- <span data-ttu-id="78146-992">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-992">Driver'sLicences</span></span>
- <span data-ttu-id="78146-993">驾驶员的许可证</span><span class="sxs-lookup"><span data-stu-id="78146-993">Driver's Lic</span></span>
- <span data-ttu-id="78146-994">司机的许可证</span><span class="sxs-lookup"><span data-stu-id="78146-994">Driver's Lics</span></span>
- <span data-ttu-id="78146-995">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-995">Driver's License</span></span>
- <span data-ttu-id="78146-996">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-996">Driver's Licenses</span></span>
- <span data-ttu-id="78146-997">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-997">Driver's Licence</span></span>
- <span data-ttu-id="78146-998">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-998">Driver's Licences</span></span>
- <span data-ttu-id="78146-999">佩米斯·德孔杜瓦雷</span><span class="sxs-lookup"><span data-stu-id="78146-999">Permis de Conduire</span></span>
- <span data-ttu-id="78146-1000">id</span><span class="sxs-lookup"><span data-stu-id="78146-1000">id</span></span>
- <span data-ttu-id="78146-1001">Id</span><span class="sxs-lookup"><span data-stu-id="78146-1001">ids</span></span>
- <span data-ttu-id="78146-1002">身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-1002">idcard number</span></span>
- <span data-ttu-id="78146-1003">身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-1003">idcard numbers</span></span>
- <span data-ttu-id="78146-1004">身份证#</span><span class="sxs-lookup"><span data-stu-id="78146-1004">idcard #</span></span>
- <span data-ttu-id="78146-1005">身份证#s</span><span class="sxs-lookup"><span data-stu-id="78146-1005">idcard #s</span></span>
- <span data-ttu-id="78146-1006">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-1006">idcard card</span></span>
- <span data-ttu-id="78146-1007">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-1007">idcard cards</span></span>
- <span data-ttu-id="78146-1008">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-1008">idcard</span></span>
- <span data-ttu-id="78146-1009">识别号</span><span class="sxs-lookup"><span data-stu-id="78146-1009">identification number</span></span>
- <span data-ttu-id="78146-1010">识别号</span><span class="sxs-lookup"><span data-stu-id="78146-1010">identification numbers</span></span>
- <span data-ttu-id="78146-1011">识别#</span><span class="sxs-lookup"><span data-stu-id="78146-1011">identification #</span></span>
- <span data-ttu-id="78146-1012">识别#s</span><span class="sxs-lookup"><span data-stu-id="78146-1012">identification #s</span></span>
- <span data-ttu-id="78146-1013">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-1013">identification card</span></span>
- <span data-ttu-id="78146-1014">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-1014">identification cards</span></span>
- <span data-ttu-id="78146-1015">识别</span><span class="sxs-lookup"><span data-stu-id="78146-1015">identification</span></span> 
- <span data-ttu-id="78146-1016">Dl#</span><span class="sxs-lookup"><span data-stu-id="78146-1016">DL#</span></span>
- <span data-ttu-id="78146-1017">Dls#</span><span class="sxs-lookup"><span data-stu-id="78146-1017">DLS#</span></span> 
- <span data-ttu-id="78146-1018">民盟#</span><span class="sxs-lookup"><span data-stu-id="78146-1018">CDL#</span></span> 
- <span data-ttu-id="78146-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="78146-1019">CDLS#</span></span> 
- <span data-ttu-id="78146-1020">司机#</span><span class="sxs-lookup"><span data-stu-id="78146-1020">DriverLic#</span></span> 
- <span data-ttu-id="78146-1021">司机#</span><span class="sxs-lookup"><span data-stu-id="78146-1021">DriverLics#</span></span> 
- <span data-ttu-id="78146-1022">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1022">DriverLicense#</span></span> 
- <span data-ttu-id="78146-1023">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="78146-1024">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1024">DriverLicence#</span></span> 
- <span data-ttu-id="78146-1025">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1025">DriverLicences#</span></span> 
- <span data-ttu-id="78146-1026">司机李克#</span><span class="sxs-lookup"><span data-stu-id="78146-1026">Driver Lic#</span></span>
- <span data-ttu-id="78146-1027">司机利茨#</span><span class="sxs-lookup"><span data-stu-id="78146-1027">Driver Lics#</span></span> 
- <span data-ttu-id="78146-1028">驾照#</span><span class="sxs-lookup"><span data-stu-id="78146-1028">Driver License#</span></span> 
- <span data-ttu-id="78146-1029">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="78146-1030">驾照#</span><span class="sxs-lookup"><span data-stu-id="78146-1030">Driver License#</span></span> 
- <span data-ttu-id="78146-1031">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1031">Driver Licences#</span></span> 
- <span data-ttu-id="78146-1032">驱动程序#</span><span class="sxs-lookup"><span data-stu-id="78146-1032">DriversLic#</span></span> 
- <span data-ttu-id="78146-1033">司机Lics#</span><span class="sxs-lookup"><span data-stu-id="78146-1033">DriversLics#</span></span> 
- <span data-ttu-id="78146-1034">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1034">DriversLicense#</span></span> 
- <span data-ttu-id="78146-1035">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="78146-1036">司机执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1036">DriversLicence#</span></span> 
- <span data-ttu-id="78146-1037">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1037">DriversLicences#</span></span> 
- <span data-ttu-id="78146-1038">司机许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="78146-1039">司机利茨#</span><span class="sxs-lookup"><span data-stu-id="78146-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="78146-1040">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1040">Drivers License#</span></span> 
- <span data-ttu-id="78146-1041">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="78146-1042">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="78146-1043">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="78146-1044">司机'Lic#</span><span class="sxs-lookup"><span data-stu-id="78146-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="78146-1045">司机的Lics#</span><span class="sxs-lookup"><span data-stu-id="78146-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="78146-1046">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1046">Driver'License#</span></span> 
- <span data-ttu-id="78146-1047">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="78146-1048">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="78146-1049">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="78146-1050">司机的许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="78146-1051">司机的Lics#</span><span class="sxs-lookup"><span data-stu-id="78146-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="78146-1052">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1052">Driver' License#</span></span> 
- <span data-ttu-id="78146-1053">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="78146-1054">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="78146-1055">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="78146-1056">驾驶员的#</span><span class="sxs-lookup"><span data-stu-id="78146-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="78146-1057">驾驶员的#</span><span class="sxs-lookup"><span data-stu-id="78146-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="78146-1058">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="78146-1059">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="78146-1060">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="78146-1061">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="78146-1062">驾驶员的许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="78146-1063">司机的许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="78146-1064">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1064">Driver's License#</span></span> 
- <span data-ttu-id="78146-1065">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="78146-1066">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="78146-1067">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="78146-1068">佩米斯·德孔杜瓦雷#</span><span class="sxs-lookup"><span data-stu-id="78146-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="78146-1069">Id#</span><span class="sxs-lookup"><span data-stu-id="78146-1069">id#</span></span> 
- <span data-ttu-id="78146-1070">Id#</span><span class="sxs-lookup"><span data-stu-id="78146-1070">ids#</span></span> 
- <span data-ttu-id="78146-1071">身份证#</span><span class="sxs-lookup"><span data-stu-id="78146-1071">idcard card#</span></span> 
- <span data-ttu-id="78146-1072">身份证#</span><span class="sxs-lookup"><span data-stu-id="78146-1072">idcard cards#</span></span> 
- <span data-ttu-id="78146-1073">身份证#</span><span class="sxs-lookup"><span data-stu-id="78146-1073">idcard#</span></span> 
- <span data-ttu-id="78146-1074">身份证#</span><span class="sxs-lookup"><span data-stu-id="78146-1074">identification card#</span></span> 
- <span data-ttu-id="78146-1075">身份证#</span><span class="sxs-lookup"><span data-stu-id="78146-1075">identification cards#</span></span> 
- <span data-ttu-id="78146-1076">识别#</span><span class="sxs-lookup"><span data-stu-id="78146-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="78146-1077">加拿大健康服务号码</span><span class="sxs-lookup"><span data-stu-id="78146-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1078">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1078">Format</span></span>

<span data-ttu-id="78146-1079">10 位</span><span class="sxs-lookup"><span data-stu-id="78146-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1080">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1080">Pattern</span></span>

<span data-ttu-id="78146-1081">10 位</span><span class="sxs-lookup"><span data-stu-id="78146-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1082">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1082">Checksum</span></span>

<span data-ttu-id="78146-1083">否</span><span class="sxs-lookup"><span data-stu-id="78146-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1084">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1084">Definition</span></span>

<span data-ttu-id="78146-1085">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1086">正则表达式 Regex_canada_health_service_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1087">找到关键字_canada_health_service_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-1088">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="78146-1089">关键词_加拿大+健康+服务_编号</span><span class="sxs-lookup"><span data-stu-id="78146-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="78146-1090">个人健康号码</span><span class="sxs-lookup"><span data-stu-id="78146-1090">personal health number</span></span>
- <span data-ttu-id="78146-1091">患者信息</span><span class="sxs-lookup"><span data-stu-id="78146-1091">patient information</span></span>
- <span data-ttu-id="78146-1092">保健服务</span><span class="sxs-lookup"><span data-stu-id="78146-1092">health services</span></span>
- <span data-ttu-id="78146-1093">专业服务</span><span class="sxs-lookup"><span data-stu-id="78146-1093">speciality services</span></span>
- <span data-ttu-id="78146-1094">车祸</span><span class="sxs-lookup"><span data-stu-id="78146-1094">automobile accident</span></span>
- <span data-ttu-id="78146-1095">病人医院</span><span class="sxs-lookup"><span data-stu-id="78146-1095">patient hospital</span></span>
- <span data-ttu-id="78146-1096">心理医生</span><span class="sxs-lookup"><span data-stu-id="78146-1096">psychiatrist</span></span>
- <span data-ttu-id="78146-1097">工人补偿</span><span class="sxs-lookup"><span data-stu-id="78146-1097">workers compensation</span></span>
- <span data-ttu-id="78146-1098">残疾</span><span class="sxs-lookup"><span data-stu-id="78146-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="78146-1099">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1100">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1100">Format</span></span>

<span data-ttu-id="78146-1101">两个大写字母后跟六位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1102">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1102">Pattern</span></span>

<span data-ttu-id="78146-1103">两个大写字母后跟六位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1104">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1104">Checksum</span></span>

<span data-ttu-id="78146-1105">否</span><span class="sxs-lookup"><span data-stu-id="78146-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1106">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1106">Definition</span></span>

<span data-ttu-id="78146-1107">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1108">正则表达式 Regex_canada_Passport_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1109">找到关键字_canada_passport_编号或关键字_Passport 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-1110">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="78146-1111">关键词_加拿大_护照_编号</span><span class="sxs-lookup"><span data-stu-id="78146-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="78146-1112">加拿大国籍</span><span class="sxs-lookup"><span data-stu-id="78146-1112">canadian citizenship</span></span>
- <span data-ttu-id="78146-1113">加拿大护照</span><span class="sxs-lookup"><span data-stu-id="78146-1113">canadian passport</span></span>
- <span data-ttu-id="78146-1114">护照申请</span><span class="sxs-lookup"><span data-stu-id="78146-1114">passport application</span></span>
- <span data-ttu-id="78146-1115">护照照片</span><span class="sxs-lookup"><span data-stu-id="78146-1115">passport photos</span></span>
- <span data-ttu-id="78146-1116">认证翻译</span><span class="sxs-lookup"><span data-stu-id="78146-1116">certified translator</span></span>
- <span data-ttu-id="78146-1117">加拿大公民</span><span class="sxs-lookup"><span data-stu-id="78146-1117">canadian citizens</span></span>
- <span data-ttu-id="78146-1118">处理时间</span><span class="sxs-lookup"><span data-stu-id="78146-1118">processing times</span></span>
- <span data-ttu-id="78146-1119">续约申请</span><span class="sxs-lookup"><span data-stu-id="78146-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="78146-1120">关键词_护照</span><span class="sxs-lookup"><span data-stu-id="78146-1120">Keyword_passport</span></span>

- <span data-ttu-id="78146-1121">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-1121">Passport Number</span></span>
- <span data-ttu-id="78146-1122">护照号</span><span class="sxs-lookup"><span data-stu-id="78146-1122">Passport No</span></span>
- <span data-ttu-id="78146-1123">护照#</span><span class="sxs-lookup"><span data-stu-id="78146-1123">Passport #</span></span>
- <span data-ttu-id="78146-1124">护照#</span><span class="sxs-lookup"><span data-stu-id="78146-1124">Passport#</span></span>
- <span data-ttu-id="78146-1125">护照ID</span><span class="sxs-lookup"><span data-stu-id="78146-1125">PassportID</span></span>
- <span data-ttu-id="78146-1126">护照诺</span><span class="sxs-lookup"><span data-stu-id="78146-1126">Passportno</span></span>
- <span data-ttu-id="78146-1127">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-1127">passportnumber</span></span>
- <span data-ttu-id="78146-1128">·</span><span class="sxs-lookup"><span data-stu-id="78146-1128">パスポート</span></span>
- <span data-ttu-id="78146-1129">·\\\\\\\\\\\\\\\\\\\\\\</span><span class="sxs-lookup"><span data-stu-id="78146-1129">パスポート番号</span></span>
- <span data-ttu-id="78146-1130">\* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="78146-1130">パスポートのNum</span></span>
- <span data-ttu-id="78146-1131">·</span><span class="sxs-lookup"><span data-stu-id="78146-1131">パスポート＃</span></span>
- <span data-ttu-id="78146-1132">努梅罗·德·德费波特</span><span class="sxs-lookup"><span data-stu-id="78146-1132">Numéro de passeport</span></span>
- <span data-ttu-id="78146-1133">路路港 n |</span><span class="sxs-lookup"><span data-stu-id="78146-1133">Passeport n °</span></span>
- <span data-ttu-id="78146-1134">路路港非</span><span class="sxs-lookup"><span data-stu-id="78146-1134">Passeport Non</span></span>
- <span data-ttu-id="78146-1135">帕塞波特#</span><span class="sxs-lookup"><span data-stu-id="78146-1135">Passeport #</span></span>
- <span data-ttu-id="78146-1136">帕塞波特#</span><span class="sxs-lookup"><span data-stu-id="78146-1136">Passeport#</span></span>
- <span data-ttu-id="78146-1137">帕塞波特农</span><span class="sxs-lookup"><span data-stu-id="78146-1137">PasseportNon</span></span>
- <span data-ttu-id="78146-1138">帕塞波特 |</span><span class="sxs-lookup"><span data-stu-id="78146-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="78146-1139">加拿大个人健康识别号</span><span class="sxs-lookup"><span data-stu-id="78146-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="78146-1140">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1140">Format</span></span>

<span data-ttu-id="78146-1141">九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1142">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1142">Pattern</span></span>

<span data-ttu-id="78146-1143">九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1144">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1144">Checksum</span></span>

<span data-ttu-id="78146-1145">否</span><span class="sxs-lookup"><span data-stu-id="78146-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1146">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1146">Definition</span></span>

<span data-ttu-id="78146-1147">如果正则表达式 Regex_canada_phin 查找与模式匹配的内容，则 DLP 策略 75% 确信检测到这种类型的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="78146-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="78146-1148">找到至少两个关键字_canada_phin 或关键字_加拿大_省。</span><span class="sxs-lookup"><span data-stu-id="78146-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-1149">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="78146-1150">关键词_加达内</span><span class="sxs-lookup"><span data-stu-id="78146-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="78146-1151">社会保险号</span><span class="sxs-lookup"><span data-stu-id="78146-1151">social insurance number</span></span>
- <span data-ttu-id="78146-1152">健康信息法</span><span class="sxs-lookup"><span data-stu-id="78146-1152">health information act</span></span>
- <span data-ttu-id="78146-1153">所得税信息</span><span class="sxs-lookup"><span data-stu-id="78146-1153">income tax information</span></span>
- <span data-ttu-id="78146-1154">马尼托巴健康</span><span class="sxs-lookup"><span data-stu-id="78146-1154">manitoba health</span></span>
- <span data-ttu-id="78146-1155">健康注册</span><span class="sxs-lookup"><span data-stu-id="78146-1155">health registration</span></span>
- <span data-ttu-id="78146-1156">处方购买</span><span class="sxs-lookup"><span data-stu-id="78146-1156">prescription purchases</span></span>
- <span data-ttu-id="78146-1157">福利资格</span><span class="sxs-lookup"><span data-stu-id="78146-1157">benefit eligibility</span></span>
- <span data-ttu-id="78146-1158">个人健康</span><span class="sxs-lookup"><span data-stu-id="78146-1158">personal health</span></span>
- <span data-ttu-id="78146-1159">委托书</span><span class="sxs-lookup"><span data-stu-id="78146-1159">power of attorney</span></span>
- <span data-ttu-id="78146-1160">注册号</span><span class="sxs-lookup"><span data-stu-id="78146-1160">registration number</span></span>
- <span data-ttu-id="78146-1161">个人健康号码</span><span class="sxs-lookup"><span data-stu-id="78146-1161">personal health number</span></span>
- <span data-ttu-id="78146-1162">执业者转诊</span><span class="sxs-lookup"><span data-stu-id="78146-1162">practitioner referral</span></span>
- <span data-ttu-id="78146-1163">健康专业人士</span><span class="sxs-lookup"><span data-stu-id="78146-1163">wellness professional</span></span>
- <span data-ttu-id="78146-1164">患者转诊</span><span class="sxs-lookup"><span data-stu-id="78146-1164">patient referral</span></span>
- <span data-ttu-id="78146-1165">健康与健康</span><span class="sxs-lookup"><span data-stu-id="78146-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="78146-1166">关键词_加拿大_省</span><span class="sxs-lookup"><span data-stu-id="78146-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="78146-1167">努纳武特</span><span class="sxs-lookup"><span data-stu-id="78146-1167">Nunavut</span></span>
- <span data-ttu-id="78146-1168">魁北克</span><span class="sxs-lookup"><span data-stu-id="78146-1168">Quebec</span></span>
- <span data-ttu-id="78146-1169">西北地区</span><span class="sxs-lookup"><span data-stu-id="78146-1169">Northwest Territories</span></span>
- <span data-ttu-id="78146-1170">安大略省</span><span class="sxs-lookup"><span data-stu-id="78146-1170">Ontario</span></span>
- <span data-ttu-id="78146-1171">不列颠哥伦比亚省</span><span class="sxs-lookup"><span data-stu-id="78146-1171">British Columbia</span></span>
- <span data-ttu-id="78146-1172">艾伯塔省</span><span class="sxs-lookup"><span data-stu-id="78146-1172">Alberta</span></span>
- <span data-ttu-id="78146-1173">萨斯喀彻温省</span><span class="sxs-lookup"><span data-stu-id="78146-1173">Saskatchewan</span></span>
- <span data-ttu-id="78146-1174">马尼托巴省</span><span class="sxs-lookup"><span data-stu-id="78146-1174">Manitoba</span></span>
- <span data-ttu-id="78146-1175">育 空</span><span class="sxs-lookup"><span data-stu-id="78146-1175">Yukon</span></span>
- <span data-ttu-id="78146-1176">纽芬兰和拉布拉多</span><span class="sxs-lookup"><span data-stu-id="78146-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="78146-1177">新不伦瑞克省</span><span class="sxs-lookup"><span data-stu-id="78146-1177">New Brunswick</span></span>
- <span data-ttu-id="78146-1178">新斯科舍省</span><span class="sxs-lookup"><span data-stu-id="78146-1178">Nova Scotia</span></span>
- <span data-ttu-id="78146-1179">爱德华王子岛</span><span class="sxs-lookup"><span data-stu-id="78146-1179">Prince Edward Island</span></span>
- <span data-ttu-id="78146-1180">加拿大</span><span class="sxs-lookup"><span data-stu-id="78146-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="78146-1181">加拿大社会保险号</span><span class="sxs-lookup"><span data-stu-id="78146-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1182">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1182">Format</span></span>

<span data-ttu-id="78146-1183">九位数字，带可选连字符或空格</span><span class="sxs-lookup"><span data-stu-id="78146-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1184">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1184">Pattern</span></span>

<span data-ttu-id="78146-1185">格式 化：</span><span class="sxs-lookup"><span data-stu-id="78146-1185">Formatted:</span></span>
- <span data-ttu-id="78146-1186">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1186">Three digits</span></span> 
- <span data-ttu-id="78146-1187">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="78146-1187">A hyphen or space</span></span> 
- <span data-ttu-id="78146-1188">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1188">Three digits</span></span> 
- <span data-ttu-id="78146-1189">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="78146-1189">A hyphen or space</span></span> 
- <span data-ttu-id="78146-1190">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1190">Three digits</span></span>

<span data-ttu-id="78146-1191">未格式化：九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1192">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1192">Checksum</span></span>

<span data-ttu-id="78146-1193">是</span><span class="sxs-lookup"><span data-stu-id="78146-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1194">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1194">Definition</span></span>

<span data-ttu-id="78146-1195">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1196">函数 Func_canadian_sin 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1197">以下任意组合中至少有两个：</span><span class="sxs-lookup"><span data-stu-id="78146-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="78146-1198">找到关键字_sin 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="78146-1199">找到来自关键字_sin_协作的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="78146-1200">函数 Func_eu_date 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="78146-1201">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1201">The checksum passes.</span></span>

<span data-ttu-id="78146-1202">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1203">函数 Func_无格式化_加拿大_sin 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1204">找到关键字_sin 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="78146-1205">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-1206">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="78146-1207">关键字_辛</span><span class="sxs-lookup"><span data-stu-id="78146-1207">Keyword_sin</span></span>

- <span data-ttu-id="78146-1208">罪</span><span class="sxs-lookup"><span data-stu-id="78146-1208">sin</span></span> 
- <span data-ttu-id="78146-1209">社会保险</span><span class="sxs-lookup"><span data-stu-id="78146-1209">social insurance</span></span> 
- <span data-ttu-id="78146-1210">numero d'保证社会</span><span class="sxs-lookup"><span data-stu-id="78146-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="78146-1211">罪</span><span class="sxs-lookup"><span data-stu-id="78146-1211">sins</span></span> 
- <span data-ttu-id="78146-1212">Ssn</span><span class="sxs-lookup"><span data-stu-id="78146-1212">ssn</span></span> 
- <span data-ttu-id="78146-1213">sns</span><span class="sxs-lookup"><span data-stu-id="78146-1213">ssns</span></span> 
- <span data-ttu-id="78146-1214">社会保障</span><span class="sxs-lookup"><span data-stu-id="78146-1214">social security</span></span> 
- <span data-ttu-id="78146-1215">numero d'保证社会</span><span class="sxs-lookup"><span data-stu-id="78146-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="78146-1216">国家身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-1216">national identification number</span></span> 
- <span data-ttu-id="78146-1217">国家 ID</span><span class="sxs-lookup"><span data-stu-id="78146-1217">national id</span></span> 
- <span data-ttu-id="78146-1218">罪#</span><span class="sxs-lookup"><span data-stu-id="78146-1218">sin#</span></span> 
- <span data-ttu-id="78146-1219">索克因斯</span><span class="sxs-lookup"><span data-stu-id="78146-1219">soc ins</span></span> 
- <span data-ttu-id="78146-1220">社会参与</span><span class="sxs-lookup"><span data-stu-id="78146-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="78146-1221">关键字_辛_协作</span><span class="sxs-lookup"><span data-stu-id="78146-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="78146-1222">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-1222">driver's license</span></span> 
- <span data-ttu-id="78146-1223">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-1223">drivers license</span></span> 
- <span data-ttu-id="78146-1224">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-1224">driver's licence</span></span> 
- <span data-ttu-id="78146-1225">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-1225">drivers licence</span></span> 
- <span data-ttu-id="78146-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="78146-1226">DOB</span></span> 
- <span data-ttu-id="78146-1227">出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-1227">Birthdate</span></span> 
- <span data-ttu-id="78146-1228">生日</span><span class="sxs-lookup"><span data-stu-id="78146-1228">Birthday</span></span> 
- <span data-ttu-id="78146-1229">出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="78146-1230">智利身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1231">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1231">Format</span></span>

<span data-ttu-id="78146-1232">7-8 位数字加上分隔符，校验数字或字母</span><span class="sxs-lookup"><span data-stu-id="78146-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1233">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1233">Pattern</span></span>

<span data-ttu-id="78146-1234">7-8 位数字加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="78146-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="78146-1235">1-2 位</span><span class="sxs-lookup"><span data-stu-id="78146-1235">1-2 digits</span></span> 
- <span data-ttu-id="78146-1236">一个期间</span><span class="sxs-lookup"><span data-stu-id="78146-1236">A period</span></span> 
- <span data-ttu-id="78146-1237">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1237">Three digits</span></span> 
- <span data-ttu-id="78146-1238">一个期间</span><span class="sxs-lookup"><span data-stu-id="78146-1238">A period</span></span> 
- <span data-ttu-id="78146-1239">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1239">Three digits</span></span> 
- <span data-ttu-id="78146-1240">破折号</span><span class="sxs-lookup"><span data-stu-id="78146-1240">A dash</span></span> 
- <span data-ttu-id="78146-1241">一个数字或字母（不区分大小写），这是一个校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1242">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1242">Checksum</span></span>

<span data-ttu-id="78146-1243">是</span><span class="sxs-lookup"><span data-stu-id="78146-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1244">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1244">Definition</span></span>

<span data-ttu-id="78146-1245">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1246">函数 Func_chile_id_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1247">找到关键字_chile_id_card 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="78146-1248">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1248">The checksum passes.</span></span>

<span data-ttu-id="78146-1249">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1250">函数 Func_chile_id_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1251">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-1252">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="78146-1253">关键词_chile_id_卡</span><span class="sxs-lookup"><span data-stu-id="78146-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="78146-1254">国家识别号码</span><span class="sxs-lookup"><span data-stu-id="78146-1254">National Identification Number</span></span> 
- <span data-ttu-id="78146-1255">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-1255">Identity card</span></span> 
- <span data-ttu-id="78146-1256">ID</span><span class="sxs-lookup"><span data-stu-id="78146-1256">ID</span></span> 
- <span data-ttu-id="78146-1257">识别</span><span class="sxs-lookup"><span data-stu-id="78146-1257">Identification</span></span> 
- <span data-ttu-id="78146-1258">罗尔·奥尼科·国家</span><span class="sxs-lookup"><span data-stu-id="78146-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="78146-1259">运行</span><span class="sxs-lookup"><span data-stu-id="78146-1259">RUN</span></span> 
- <span data-ttu-id="78146-1260">罗尔·奥尼科支流</span><span class="sxs-lookup"><span data-stu-id="78146-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="78146-1261">车辙</span><span class="sxs-lookup"><span data-stu-id="78146-1261">RUT</span></span> 
- <span data-ttu-id="78146-1262">奇杜拉·德·伊登迪达</span><span class="sxs-lookup"><span data-stu-id="78146-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="78146-1263">国家身份研究所</span><span class="sxs-lookup"><span data-stu-id="78146-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="78146-1264">塔杰塔·德·卡蒂西翁</span><span class="sxs-lookup"><span data-stu-id="78146-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="78146-1265">身份识别</span><span class="sxs-lookup"><span data-stu-id="78146-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="78146-1266">中国居民身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1267">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1267">Format</span></span>

<span data-ttu-id="78146-1268">18 位</span><span class="sxs-lookup"><span data-stu-id="78146-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1269">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1269">Pattern</span></span>

<span data-ttu-id="78146-1270">18 位：</span><span class="sxs-lookup"><span data-stu-id="78146-1270">18 digits:</span></span>
- <span data-ttu-id="78146-1271">六位数字是地址代码</span><span class="sxs-lookup"><span data-stu-id="78146-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="78146-1272">表格 YYYYMMDD 中的八位数字，即出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="78146-1273">三位数字是订单代码</span><span class="sxs-lookup"><span data-stu-id="78146-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="78146-1274">一个数字，即校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1275">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1275">Checksum</span></span>

<span data-ttu-id="78146-1276">是</span><span class="sxs-lookup"><span data-stu-id="78146-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1277">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1277">Definition</span></span>

<span data-ttu-id="78146-1278">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1279">函数 Func_china_驻留_id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1280">找到关键字_china_居民\id的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="78146-1281">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1281">The checksum passes.</span></span>

<span data-ttu-id="78146-1282">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1283">函数 Func_china_驻留_id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1284">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-1285">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="78146-1286">关键字_中国_居民_id</span><span class="sxs-lookup"><span data-stu-id="78146-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="78146-1287">居民身份证</span><span class="sxs-lookup"><span data-stu-id="78146-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="78146-1288">中国</span><span class="sxs-lookup"><span data-stu-id="78146-1288">PRC</span></span> 
- <span data-ttu-id="78146-1289">国民身份证</span><span class="sxs-lookup"><span data-stu-id="78146-1289">National Identification Card</span></span> 
- <span data-ttu-id="78146-1290">·</span><span class="sxs-lookup"><span data-stu-id="78146-1290">身份证</span></span> 
- <span data-ttu-id="78146-1291">·</span><span class="sxs-lookup"><span data-stu-id="78146-1291">居民 身份证</span></span> 
- <span data-ttu-id="78146-1292">·00年</span><span class="sxs-lookup"><span data-stu-id="78146-1292">居民身份证</span></span> 
- <span data-ttu-id="78146-1293">·</span><span class="sxs-lookup"><span data-stu-id="78146-1293">鉴定</span></span> 
- <span data-ttu-id="78146-1294">·</span><span class="sxs-lookup"><span data-stu-id="78146-1294">身分證</span></span> 
- <span data-ttu-id="78146-1295">·</span><span class="sxs-lookup"><span data-stu-id="78146-1295">居民 身份證</span></span>
- <span data-ttu-id="78146-1296">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="78146-1297">信用卡號碼</span><span class="sxs-lookup"><span data-stu-id="78146-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1298">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1298">Format</span></span>

<span data-ttu-id="78146-1299">16 位数字，可格式化或未格式化（ddddddddddddd），并且必须通过 Luhn 测试。</span><span class="sxs-lookup"><span data-stu-id="78146-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1300">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1300">Pattern</span></span>

<span data-ttu-id="78146-1301">非常复杂和强大的模式，可检测来自全球所有主要品牌的卡，包括 Visa、万事达卡、发现卡、JCB、美国运通卡、礼品卡和餐卡。</span><span class="sxs-lookup"><span data-stu-id="78146-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1302">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1302">Checksum</span></span>

<span data-ttu-id="78146-1303">是，卢恩校验和</span><span class="sxs-lookup"><span data-stu-id="78146-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1304">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1304">Definition</span></span>

<span data-ttu-id="78146-1305">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1306">函数 Func_credit_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1307">下列情况之一是正确的：</span><span class="sxs-lookup"><span data-stu-id="78146-1307">One of the following is true:</span></span>
    - <span data-ttu-id="78146-1308">找到关键字_cc_验证的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="78146-1309">找到关键字_cc_name的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="78146-1310">函数 Func_date_date 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="78146-1311">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1311">The checksum passes.</span></span>

<span data-ttu-id="78146-1312">如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1313">函数 Func_credit_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1314">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-1315">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="78146-1316">关键字_cc_验证</span><span class="sxs-lookup"><span data-stu-id="78146-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="78146-1317">卡验证</span><span class="sxs-lookup"><span data-stu-id="78146-1317">card verification</span></span>
- <span data-ttu-id="78146-1318">卡标识号</span><span class="sxs-lookup"><span data-stu-id="78146-1318">card identification number</span></span>
- <span data-ttu-id="78146-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="78146-1319">cvn</span></span>
- <span data-ttu-id="78146-1320">cid</span><span class="sxs-lookup"><span data-stu-id="78146-1320">cid</span></span>
- <span data-ttu-id="78146-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="78146-1321">cvc2</span></span>
- <span data-ttu-id="78146-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="78146-1322">cvv2</span></span>
- <span data-ttu-id="78146-1323">引脚块</span><span class="sxs-lookup"><span data-stu-id="78146-1323">pin block</span></span>
- <span data-ttu-id="78146-1324">安全代码</span><span class="sxs-lookup"><span data-stu-id="78146-1324">security code</span></span>
- <span data-ttu-id="78146-1325">安全号码</span><span class="sxs-lookup"><span data-stu-id="78146-1325">security number</span></span>
- <span data-ttu-id="78146-1326">安全否</span><span class="sxs-lookup"><span data-stu-id="78146-1326">security no</span></span>
- <span data-ttu-id="78146-1327">问题编号</span><span class="sxs-lookup"><span data-stu-id="78146-1327">issue number</span></span>
- <span data-ttu-id="78146-1328">问题否</span><span class="sxs-lookup"><span data-stu-id="78146-1328">issue no</span></span>
- <span data-ttu-id="78146-1329">密码语法</span><span class="sxs-lookup"><span data-stu-id="78146-1329">cryptogramme</span></span>
- <span data-ttu-id="78146-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="78146-1330">numéro de sécurité</span></span>
- <span data-ttu-id="78146-1331">numero de Securite</span><span class="sxs-lookup"><span data-stu-id="78146-1331">numero de securite</span></span>
- <span data-ttu-id="78146-1332">克雷迪克特卡滕普吕夫努默</span><span class="sxs-lookup"><span data-stu-id="78146-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="78146-1333">克雷迪克特卡滕普鲁夫努默</span><span class="sxs-lookup"><span data-stu-id="78146-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="78146-1334">普雷夫齐弗</span><span class="sxs-lookup"><span data-stu-id="78146-1334">prüfziffer</span></span>
- <span data-ttu-id="78146-1335">普鲁夫齐弗</span><span class="sxs-lookup"><span data-stu-id="78146-1335">prufziffer</span></span>
- <span data-ttu-id="78146-1336">希切赫海茨·科德</span><span class="sxs-lookup"><span data-stu-id="78146-1336">sicherheits Kode</span></span>
- <span data-ttu-id="78146-1337">sicherheits码</span><span class="sxs-lookup"><span data-stu-id="78146-1337">sicherheitscode</span></span>
- <span data-ttu-id="78146-1338">希切赫赫努默</span><span class="sxs-lookup"><span data-stu-id="78146-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="78146-1339">弗法尔达图姆</span><span class="sxs-lookup"><span data-stu-id="78146-1339">verfalldatum</span></span>
- <span data-ttu-id="78146-1340">科迪斯·迪维蒂卡</span><span class="sxs-lookup"><span data-stu-id="78146-1340">codice di verifica</span></span>
- <span data-ttu-id="78146-1341">Cod。</span><span class="sxs-lookup"><span data-stu-id="78146-1341">cod.</span></span> <span data-ttu-id="78146-1342">西库雷扎</span><span class="sxs-lookup"><span data-stu-id="78146-1342">sicurezza</span></span>
- <span data-ttu-id="78146-1343">鳕鱼西库雷扎</span><span class="sxs-lookup"><span data-stu-id="78146-1343">cod sicurezza</span></span>
- <span data-ttu-id="78146-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="78146-1344">n autorizzazione</span></span>
- <span data-ttu-id="78146-1345">塞迪戈</span><span class="sxs-lookup"><span data-stu-id="78146-1345">código</span></span>
- <span data-ttu-id="78146-1346">科迪戈</span><span class="sxs-lookup"><span data-stu-id="78146-1346">codigo</span></span>
- <span data-ttu-id="78146-1347">Cod。</span><span class="sxs-lookup"><span data-stu-id="78146-1347">cod.</span></span> <span data-ttu-id="78146-1348">Seg</span><span class="sxs-lookup"><span data-stu-id="78146-1348">seg</span></span>
- <span data-ttu-id="78146-1349">鳕鱼赛格</span><span class="sxs-lookup"><span data-stu-id="78146-1349">cod seg</span></span>
- <span data-ttu-id="78146-1350">塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1350">código de segurança</span></span>
- <span data-ttu-id="78146-1351">科迪戈·德塞古兰卡</span><span class="sxs-lookup"><span data-stu-id="78146-1351">codigo de seguranca</span></span>
- <span data-ttu-id="78146-1352">科迪戈·德塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1352">codigo de segurança</span></span>
- <span data-ttu-id="78146-1353">塞古兰卡</span><span class="sxs-lookup"><span data-stu-id="78146-1353">código de seguranca</span></span>
- <span data-ttu-id="78146-1354">c_d.</span><span class="sxs-lookup"><span data-stu-id="78146-1354">cód.</span></span> <span data-ttu-id="78146-1355">塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1355">segurança</span></span>
- <span data-ttu-id="78146-1356">Cod。</span><span class="sxs-lookup"><span data-stu-id="78146-1356">cod.</span></span> <span data-ttu-id="78146-1357">塞古兰卡鳕鱼。</span><span class="sxs-lookup"><span data-stu-id="78146-1357">seguranca cod.</span></span> <span data-ttu-id="78146-1358">塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1358">segurança</span></span>
- <span data-ttu-id="78146-1359">c_d.</span><span class="sxs-lookup"><span data-stu-id="78146-1359">cód.</span></span> <span data-ttu-id="78146-1360">塞古兰卡</span><span class="sxs-lookup"><span data-stu-id="78146-1360">seguranca</span></span>
- <span data-ttu-id="78146-1361">塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1361">cód segurança</span></span>
- <span data-ttu-id="78146-1362">鳕鱼塞古兰卡鳕鱼塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="78146-1363">塞古兰卡</span><span class="sxs-lookup"><span data-stu-id="78146-1363">cód seguranca</span></span>
- <span data-ttu-id="78146-1364">努梅罗·德维萨奥</span><span class="sxs-lookup"><span data-stu-id="78146-1364">número de verificação</span></span>
- <span data-ttu-id="78146-1365">numero de 验证卡考</span><span class="sxs-lookup"><span data-stu-id="78146-1365">numero de verificacao</span></span>
- <span data-ttu-id="78146-1366">阿布拉夫</span><span class="sxs-lookup"><span data-stu-id="78146-1366">ablauf</span></span>
- <span data-ttu-id="78146-1367">盖尔蒂格·比斯</span><span class="sxs-lookup"><span data-stu-id="78146-1367">gültig bis</span></span>
- <span data-ttu-id="78146-1368">盖尔蒂格凯茨达图姆</span><span class="sxs-lookup"><span data-stu-id="78146-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="78146-1369">古尔蒂格·比斯</span><span class="sxs-lookup"><span data-stu-id="78146-1369">gultig bis</span></span>
- <span data-ttu-id="78146-1370">古尔蒂格凯茨达图姆</span><span class="sxs-lookup"><span data-stu-id="78146-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="78146-1371">沙登扎</span><span class="sxs-lookup"><span data-stu-id="78146-1371">scadenza</span></span>
- <span data-ttu-id="78146-1372">数据 scad</span><span class="sxs-lookup"><span data-stu-id="78146-1372">data scad</span></span>
- <span data-ttu-id="78146-1373">过期</span><span class="sxs-lookup"><span data-stu-id="78146-1373">fecha de expiracion</span></span>
- <span data-ttu-id="78146-1374">费查·德·韦克</span><span class="sxs-lookup"><span data-stu-id="78146-1374">fecha de venc</span></span>
- <span data-ttu-id="78146-1375">文西门托</span><span class="sxs-lookup"><span data-stu-id="78146-1375">vencimiento</span></span>
- <span data-ttu-id="78146-1376">瓦利多·哈斯塔</span><span class="sxs-lookup"><span data-stu-id="78146-1376">válido hasta</span></span>
- <span data-ttu-id="78146-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="78146-1377">valido hasta</span></span>
- <span data-ttu-id="78146-1378">vto</span><span class="sxs-lookup"><span data-stu-id="78146-1378">vto</span></span>
- <span data-ttu-id="78146-1379">数据到期</span><span class="sxs-lookup"><span data-stu-id="78146-1379">data de expiração</span></span>
- <span data-ttu-id="78146-1380">数据到期</span><span class="sxs-lookup"><span data-stu-id="78146-1380">data de expiracao</span></span>
- <span data-ttu-id="78146-1381">数据 em que 到期</span><span class="sxs-lookup"><span data-stu-id="78146-1381">data em que expira</span></span>
- <span data-ttu-id="78146-1382">有效</span><span class="sxs-lookup"><span data-stu-id="78146-1382">validade</span></span>
- <span data-ttu-id="78146-1383">勇气</span><span class="sxs-lookup"><span data-stu-id="78146-1383">valor</span></span>
- <span data-ttu-id="78146-1384">文奇门托</span><span class="sxs-lookup"><span data-stu-id="78146-1384">vencimento</span></span>
- <span data-ttu-id="78146-1385">文奇</span><span class="sxs-lookup"><span data-stu-id="78146-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="78146-1386">关键字_cc_名称</span><span class="sxs-lookup"><span data-stu-id="78146-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="78146-1387">阿姆克斯</span><span class="sxs-lookup"><span data-stu-id="78146-1387">amex</span></span>
- <span data-ttu-id="78146-1388">美国快递</span><span class="sxs-lookup"><span data-stu-id="78146-1388">american express</span></span>
- <span data-ttu-id="78146-1389">美国快递</span><span class="sxs-lookup"><span data-stu-id="78146-1389">americanexpress</span></span>
- <span data-ttu-id="78146-1390">签证</span><span class="sxs-lookup"><span data-stu-id="78146-1390">Visa</span></span>
- <span data-ttu-id="78146-1391">万事 达</span><span class="sxs-lookup"><span data-stu-id="78146-1391">mastercard</span></span>
- <span data-ttu-id="78146-1392">主卡</span><span class="sxs-lookup"><span data-stu-id="78146-1392">master card</span></span>
- <span data-ttu-id="78146-1393">Mc</span><span class="sxs-lookup"><span data-stu-id="78146-1393">mc</span></span> 
- <span data-ttu-id="78146-1394">万事达卡</span><span class="sxs-lookup"><span data-stu-id="78146-1394">mastercards</span></span>
- <span data-ttu-id="78146-1395">主卡</span><span class="sxs-lookup"><span data-stu-id="78146-1395">master cards</span></span>
- <span data-ttu-id="78146-1396">餐厅俱乐部</span><span class="sxs-lookup"><span data-stu-id="78146-1396">diner's Club</span></span>
- <span data-ttu-id="78146-1397">食客俱乐部</span><span class="sxs-lookup"><span data-stu-id="78146-1397">diners club</span></span>
- <span data-ttu-id="78146-1398">食客俱乐部</span><span class="sxs-lookup"><span data-stu-id="78146-1398">dinersclub</span></span>
- <span data-ttu-id="78146-1399">发现卡</span><span class="sxs-lookup"><span data-stu-id="78146-1399">discover card</span></span>
- <span data-ttu-id="78146-1400">发现卡</span><span class="sxs-lookup"><span data-stu-id="78146-1400">discovercard</span></span>
- <span data-ttu-id="78146-1401">发现卡片</span><span class="sxs-lookup"><span data-stu-id="78146-1401">discover cards</span></span>
- <span data-ttu-id="78146-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="78146-1402">JCB</span></span>
- <span data-ttu-id="78146-1403">日本卡局</span><span class="sxs-lookup"><span data-stu-id="78146-1403">japanese card bureau</span></span>
- <span data-ttu-id="78146-1404">点菜布兰奇</span><span class="sxs-lookup"><span data-stu-id="78146-1404">carte blanche</span></span>
- <span data-ttu-id="78146-1405">卡特布兰奇</span><span class="sxs-lookup"><span data-stu-id="78146-1405">carteblanche</span></span>
- <span data-ttu-id="78146-1406">信用卡</span><span class="sxs-lookup"><span data-stu-id="78146-1406">credit card</span></span>
- <span data-ttu-id="78146-1407">Cc#</span><span class="sxs-lookup"><span data-stu-id="78146-1407">cc#</span></span>
- <span data-ttu-id="78146-1408">cc#：</span><span class="sxs-lookup"><span data-stu-id="78146-1408">cc#:</span></span>
- <span data-ttu-id="78146-1409">有效期</span><span class="sxs-lookup"><span data-stu-id="78146-1409">expiration date</span></span>
- <span data-ttu-id="78146-1410">exp 日期</span><span class="sxs-lookup"><span data-stu-id="78146-1410">exp date</span></span>
- <span data-ttu-id="78146-1411">有效期</span><span class="sxs-lookup"><span data-stu-id="78146-1411">expiry date</span></span>
- <span data-ttu-id="78146-1412">过期日期</span><span class="sxs-lookup"><span data-stu-id="78146-1412">date d’expiration</span></span>
- <span data-ttu-id="78146-1413">日期 d'exp</span><span class="sxs-lookup"><span data-stu-id="78146-1413">date d'exp</span></span>
- <span data-ttu-id="78146-1414">日期过期</span><span class="sxs-lookup"><span data-stu-id="78146-1414">date expiration</span></span>
- <span data-ttu-id="78146-1415">银行卡</span><span class="sxs-lookup"><span data-stu-id="78146-1415">bank card</span></span>
- <span data-ttu-id="78146-1416">银行卡</span><span class="sxs-lookup"><span data-stu-id="78146-1416">bankcard</span></span>
- <span data-ttu-id="78146-1417">卡号</span><span class="sxs-lookup"><span data-stu-id="78146-1417">card number</span></span>
- <span data-ttu-id="78146-1418">卡数</span><span class="sxs-lookup"><span data-stu-id="78146-1418">card num</span></span>
- <span data-ttu-id="78146-1419">卡号</span><span class="sxs-lookup"><span data-stu-id="78146-1419">cardnumber</span></span>
- <span data-ttu-id="78146-1420">牌号</span><span class="sxs-lookup"><span data-stu-id="78146-1420">cardnumbers</span></span>
- <span data-ttu-id="78146-1421">卡号</span><span class="sxs-lookup"><span data-stu-id="78146-1421">card numbers</span></span>
- <span data-ttu-id="78146-1422">信用卡</span><span class="sxs-lookup"><span data-stu-id="78146-1422">creditcard</span></span>
- <span data-ttu-id="78146-1423">信用卡</span><span class="sxs-lookup"><span data-stu-id="78146-1423">credit cards</span></span>
- <span data-ttu-id="78146-1424">信用卡</span><span class="sxs-lookup"><span data-stu-id="78146-1424">creditcards</span></span>
- <span data-ttu-id="78146-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="78146-1425">ccn</span></span>
- <span data-ttu-id="78146-1426">持卡人</span><span class="sxs-lookup"><span data-stu-id="78146-1426">card holder</span></span>
- <span data-ttu-id="78146-1427">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="78146-1427">cardholder</span></span>
- <span data-ttu-id="78146-1428">持卡人</span><span class="sxs-lookup"><span data-stu-id="78146-1428">card holders</span></span>
- <span data-ttu-id="78146-1429">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="78146-1429">cardholders</span></span>
- <span data-ttu-id="78146-1430">支票卡</span><span class="sxs-lookup"><span data-stu-id="78146-1430">check card</span></span>
- <span data-ttu-id="78146-1431">支票卡</span><span class="sxs-lookup"><span data-stu-id="78146-1431">checkcard</span></span>
- <span data-ttu-id="78146-1432">支票卡</span><span class="sxs-lookup"><span data-stu-id="78146-1432">check cards</span></span>
- <span data-ttu-id="78146-1433">支票卡</span><span class="sxs-lookup"><span data-stu-id="78146-1433">checkcards</span></span>
- <span data-ttu-id="78146-1434">借记卡</span><span class="sxs-lookup"><span data-stu-id="78146-1434">debit card</span></span>
- <span data-ttu-id="78146-1435">借记卡</span><span class="sxs-lookup"><span data-stu-id="78146-1435">debitcard</span></span>
- <span data-ttu-id="78146-1436">借记卡</span><span class="sxs-lookup"><span data-stu-id="78146-1436">debit cards</span></span>
- <span data-ttu-id="78146-1437">借记卡</span><span class="sxs-lookup"><span data-stu-id="78146-1437">debitcards</span></span>
- <span data-ttu-id="78146-1438">atm 卡</span><span class="sxs-lookup"><span data-stu-id="78146-1438">atm card</span></span>
- <span data-ttu-id="78146-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="78146-1439">atmcard</span></span>
- <span data-ttu-id="78146-1440">atm 卡</span><span class="sxs-lookup"><span data-stu-id="78146-1440">atm cards</span></span>
- <span data-ttu-id="78146-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="78146-1441">atmcards</span></span>
- <span data-ttu-id="78146-1442">路线</span><span class="sxs-lookup"><span data-stu-id="78146-1442">enroute</span></span>
- <span data-ttu-id="78146-1443">途中</span><span class="sxs-lookup"><span data-stu-id="78146-1443">en route</span></span>
- <span data-ttu-id="78146-1444">卡类型</span><span class="sxs-lookup"><span data-stu-id="78146-1444">card type</span></span>
- <span data-ttu-id="78146-1445">卡特·班凯雷</span><span class="sxs-lookup"><span data-stu-id="78146-1445">carte bancaire</span></span>
- <span data-ttu-id="78146-1446">点菜</span><span class="sxs-lookup"><span data-stu-id="78146-1446">carte de crédit</span></span>
- <span data-ttu-id="78146-1447">点菜信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1447">carte de credit</span></span>
- <span data-ttu-id="78146-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="78146-1448">numéro de carte</span></span>
- <span data-ttu-id="78146-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="78146-1449">numero de carte</span></span>
- <span data-ttu-id="78146-1450">点菜号</span><span class="sxs-lookup"><span data-stu-id="78146-1450">nº de la carte</span></span>
- <span data-ttu-id="78146-1451">点菜</span><span class="sxs-lookup"><span data-stu-id="78146-1451">nº de carte</span></span>
- <span data-ttu-id="78146-1452">克雷迪克特卡特</span><span class="sxs-lookup"><span data-stu-id="78146-1452">kreditkarte</span></span>
- <span data-ttu-id="78146-1453">卡尔特</span><span class="sxs-lookup"><span data-stu-id="78146-1453">karte</span></span>
- <span data-ttu-id="78146-1454">卡尔特宁哈伯</span><span class="sxs-lookup"><span data-stu-id="78146-1454">karteninhaber</span></span>
- <span data-ttu-id="78146-1455">卡尔特宁哈伯斯</span><span class="sxs-lookup"><span data-stu-id="78146-1455">karteninhabers</span></span>
- <span data-ttu-id="78146-1456">克雷迪克特卡特宁哈伯</span><span class="sxs-lookup"><span data-stu-id="78146-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="78146-1457">克雷蒂特卡滕特研究所</span><span class="sxs-lookup"><span data-stu-id="78146-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="78146-1458">克雷蒂特卡滕蒂普</span><span class="sxs-lookup"><span data-stu-id="78146-1458">kreditkartentyp</span></span>
- <span data-ttu-id="78146-1459">艾根特·梅尔南</span><span class="sxs-lookup"><span data-stu-id="78146-1459">eigentümername</span></span>
- <span data-ttu-id="78146-1460">卡尔滕内尔</span><span class="sxs-lookup"><span data-stu-id="78146-1460">kartennr</span></span> 
- <span data-ttu-id="78146-1461">卡尔滕努默</span><span class="sxs-lookup"><span data-stu-id="78146-1461">kartennummer</span></span>
- <span data-ttu-id="78146-1462">克雷迪克特卡滕努默</span><span class="sxs-lookup"><span data-stu-id="78146-1462">kreditkartennummer</span></span>
- <span data-ttu-id="78146-1463">克雷迪克特卡滕-努默</span><span class="sxs-lookup"><span data-stu-id="78146-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="78146-1464">卡塔迪信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1464">carta di credito</span></span>
- <span data-ttu-id="78146-1465">卡塔·卡托</span><span class="sxs-lookup"><span data-stu-id="78146-1465">carta credito</span></span>
- <span data-ttu-id="78146-1466">宪章</span><span class="sxs-lookup"><span data-stu-id="78146-1466">carta</span></span>
- <span data-ttu-id="78146-1467">n 卡塔</span><span class="sxs-lookup"><span data-stu-id="78146-1467">n carta</span></span>
- <span data-ttu-id="78146-1468">星期日。</span><span class="sxs-lookup"><span data-stu-id="78146-1468">nr.</span></span> <span data-ttu-id="78146-1469">宪章</span><span class="sxs-lookup"><span data-stu-id="78146-1469">carta</span></span>
- <span data-ttu-id="78146-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="78146-1470">nr carta</span></span>
- <span data-ttu-id="78146-1471">努梅罗·卡塔</span><span class="sxs-lookup"><span data-stu-id="78146-1471">numero carta</span></span>
- <span data-ttu-id="78146-1472">numero dela carta</span><span class="sxs-lookup"><span data-stu-id="78146-1472">numero della carta</span></span>
- <span data-ttu-id="78146-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="78146-1473">numero di carta</span></span>
- <span data-ttu-id="78146-1474">塔耶塔信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1474">tarjeta credito</span></span>
- <span data-ttu-id="78146-1475">塔耶塔·德·信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1475">tarjeta de credito</span></span>
- <span data-ttu-id="78146-1476">塔耶塔·克雷迪托</span><span class="sxs-lookup"><span data-stu-id="78146-1476">tarjeta crédito</span></span>
- <span data-ttu-id="78146-1477">塔耶塔·德·克雷迪托</span><span class="sxs-lookup"><span data-stu-id="78146-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="78146-1478">塔耶塔·德阿特姆</span><span class="sxs-lookup"><span data-stu-id="78146-1478">tarjeta de atm</span></span>
- <span data-ttu-id="78146-1479">塔耶塔 atm</span><span class="sxs-lookup"><span data-stu-id="78146-1479">tarjeta atm</span></span>
- <span data-ttu-id="78146-1480">塔耶塔·比托</span><span class="sxs-lookup"><span data-stu-id="78146-1480">tarjeta debito</span></span>
- <span data-ttu-id="78146-1481">塔耶塔·德·比乔</span><span class="sxs-lookup"><span data-stu-id="78146-1481">tarjeta de debito</span></span>
- <span data-ttu-id="78146-1482">塔耶塔·德比托</span><span class="sxs-lookup"><span data-stu-id="78146-1482">tarjeta débito</span></span>
- <span data-ttu-id="78146-1483">塔耶塔·德德比托</span><span class="sxs-lookup"><span data-stu-id="78146-1483">tarjeta de débito</span></span>
- <span data-ttu-id="78146-1484">诺德塔耶塔</span><span class="sxs-lookup"><span data-stu-id="78146-1484">nº de tarjeta</span></span>
- <span data-ttu-id="78146-1485">不。</span><span class="sxs-lookup"><span data-stu-id="78146-1485">no.</span></span> <span data-ttu-id="78146-1486">德塔耶塔</span><span class="sxs-lookup"><span data-stu-id="78146-1486">de tarjeta</span></span>
- <span data-ttu-id="78146-1487">没有塔里塔</span><span class="sxs-lookup"><span data-stu-id="78146-1487">no de tarjeta</span></span>
- <span data-ttu-id="78146-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="78146-1488">numero de tarjeta</span></span>
- <span data-ttu-id="78146-1489">内梅罗·德塔耶塔</span><span class="sxs-lookup"><span data-stu-id="78146-1489">número de tarjeta</span></span>
- <span data-ttu-id="78146-1490">塔耶塔没有</span><span class="sxs-lookup"><span data-stu-id="78146-1490">tarjeta no</span></span>
- <span data-ttu-id="78146-1491">塔尔杰塔哈比恩特</span><span class="sxs-lookup"><span data-stu-id="78146-1491">tarjetahabiente</span></span>
- <span data-ttu-id="78146-1492">卡特奥·德·卡迪托</span><span class="sxs-lookup"><span data-stu-id="78146-1492">cartão de crédito</span></span>
- <span data-ttu-id="78146-1493">卡特尼奥·德信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1493">cartão de credito</span></span>
- <span data-ttu-id="78146-1494">卡尔陶·德·克雷迪托</span><span class="sxs-lookup"><span data-stu-id="78146-1494">cartao de crédito</span></span>
- <span data-ttu-id="78146-1495">卡尔陶·德·信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1495">cartao de credito</span></span>
- <span data-ttu-id="78146-1496">卡尔多·德德比托</span><span class="sxs-lookup"><span data-stu-id="78146-1496">cartão de débito</span></span>
- <span data-ttu-id="78146-1497">卡尔陶·德德比托</span><span class="sxs-lookup"><span data-stu-id="78146-1497">cartao de débito</span></span>
- <span data-ttu-id="78146-1498">卡特尼奥·德·比托</span><span class="sxs-lookup"><span data-stu-id="78146-1498">cartão de debito</span></span>
- <span data-ttu-id="78146-1499">卡尔陶·德·比乔</span><span class="sxs-lookup"><span data-stu-id="78146-1499">cartao de debito</span></span>
- <span data-ttu-id="78146-1500">德比托·自治蒂科</span><span class="sxs-lookup"><span data-stu-id="78146-1500">débito automático</span></span>
- <span data-ttu-id="78146-1501">比托自动</span><span class="sxs-lookup"><span data-stu-id="78146-1501">debito automatico</span></span>
- <span data-ttu-id="78146-1502">内梅罗·多·卡托</span><span class="sxs-lookup"><span data-stu-id="78146-1502">número do cartão</span></span>
- <span data-ttu-id="78146-1503">numero do cartío</span><span class="sxs-lookup"><span data-stu-id="78146-1503">numero do cartão</span></span> 
- <span data-ttu-id="78146-1504">内梅罗·多·卡托</span><span class="sxs-lookup"><span data-stu-id="78146-1504">número do cartao</span></span>
- <span data-ttu-id="78146-1505">numero do Cartao</span><span class="sxs-lookup"><span data-stu-id="78146-1505">numero do cartao</span></span>
- <span data-ttu-id="78146-1506">némero de cartéo</span><span class="sxs-lookup"><span data-stu-id="78146-1506">número de cartão</span></span>
- <span data-ttu-id="78146-1507">numero de cartío</span><span class="sxs-lookup"><span data-stu-id="78146-1507">numero de cartão</span></span>
- <span data-ttu-id="78146-1508">内梅罗·德卡托</span><span class="sxs-lookup"><span data-stu-id="78146-1508">número de cartao</span></span>
- <span data-ttu-id="78146-1509">努梅罗·德·卡陶</span><span class="sxs-lookup"><span data-stu-id="78146-1509">numero de cartao</span></span>
- <span data-ttu-id="78146-1510">no do cartéo</span><span class="sxs-lookup"><span data-stu-id="78146-1510">nº do cartão</span></span>
- <span data-ttu-id="78146-1511">no do Cartao</span><span class="sxs-lookup"><span data-stu-id="78146-1511">nº do cartao</span></span>
- <span data-ttu-id="78146-1512">no.</span><span class="sxs-lookup"><span data-stu-id="78146-1512">nº.</span></span> <span data-ttu-id="78146-1513">多卡托</span><span class="sxs-lookup"><span data-stu-id="78146-1513">do cartão</span></span>
- <span data-ttu-id="78146-1514">没有做卡特奥</span><span class="sxs-lookup"><span data-stu-id="78146-1514">no do cartão</span></span>
- <span data-ttu-id="78146-1515">没有做卡陶</span><span class="sxs-lookup"><span data-stu-id="78146-1515">no do cartao</span></span>
- <span data-ttu-id="78146-1516">不。</span><span class="sxs-lookup"><span data-stu-id="78146-1516">no.</span></span> <span data-ttu-id="78146-1517">多卡托</span><span class="sxs-lookup"><span data-stu-id="78146-1517">do cartão</span></span>
- <span data-ttu-id="78146-1518">不。</span><span class="sxs-lookup"><span data-stu-id="78146-1518">no.</span></span> <span data-ttu-id="78146-1519">多卡陶</span><span class="sxs-lookup"><span data-stu-id="78146-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="78146-1520">克羅埃西亞身分證號碼</span><span class="sxs-lookup"><span data-stu-id="78146-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1521">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1521">Format</span></span>

<span data-ttu-id="78146-1522">九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1523">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1523">Pattern</span></span>

<span data-ttu-id="78146-1524">连续九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1525">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1525">Checksum</span></span>

<span data-ttu-id="78146-1526">否</span><span class="sxs-lookup"><span data-stu-id="78146-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1527">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1527">Definition</span></span>

<span data-ttu-id="78146-1528">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1529">函数 Func_croatia_id_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1530">找到关键字_croatia_id_card 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-1531">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="78146-1532">关键字_克罗地亚_id_卡</span><span class="sxs-lookup"><span data-stu-id="78146-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="78146-1533">克罗地亚身份证</span><span class="sxs-lookup"><span data-stu-id="78146-1533">Croatian identity card</span></span>
- <span data-ttu-id="78146-1534">奥索布纳·卡兹尼察</span><span class="sxs-lookup"><span data-stu-id="78146-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="78146-1535">克羅埃西亞個人識別 (OIB) 碼</span><span class="sxs-lookup"><span data-stu-id="78146-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1536">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1536">Format</span></span>

<span data-ttu-id="78146-1537">11 位</span><span class="sxs-lookup"><span data-stu-id="78146-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1538">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1538">Pattern</span></span>

<span data-ttu-id="78146-1539">11 位：</span><span class="sxs-lookup"><span data-stu-id="78146-1539">11 digits:</span></span>
- <span data-ttu-id="78146-1540">10 位</span><span class="sxs-lookup"><span data-stu-id="78146-1540">10 digits</span></span> 
- <span data-ttu-id="78146-1541">最终数字是一个校验数字 用于国际数据交换，字母 HR 添加到 11 位数字之前。</span><span class="sxs-lookup"><span data-stu-id="78146-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1542">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1542">Checksum</span></span>

<span data-ttu-id="78146-1543">是</span><span class="sxs-lookup"><span data-stu-id="78146-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1544">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1544">Definition</span></span>

<span data-ttu-id="78146-1545">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1546">函数 Func_croatia_oib_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1547">找到关键字_croatia_oib_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="78146-1548">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1548">The checksum passes.</span></span>

<span data-ttu-id="78146-1549">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1550">函数 Func_croatia_oib_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1551">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-1552">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="78146-1553">关键字_克罗地亚_oib_数字</span><span class="sxs-lookup"><span data-stu-id="78146-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="78146-1554">个人识别号码</span><span class="sxs-lookup"><span data-stu-id="78146-1554">Personal Identification Number</span></span>
- <span data-ttu-id="78146-1555">奥索布尼·伊登蒂比卡奇斯基·布罗伊</span><span class="sxs-lookup"><span data-stu-id="78146-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="78146-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="78146-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="78146-1557">捷克个人身份号码</span><span class="sxs-lookup"><span data-stu-id="78146-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1558">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1558">Format</span></span>

<span data-ttu-id="78146-1559">九位数字，可选前斜杠（旧格式）10 位数字，可选前斜杠（新格式）</span><span class="sxs-lookup"><span data-stu-id="78146-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1560">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1560">Pattern</span></span>

<span data-ttu-id="78146-1561">九位数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="78146-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="78146-1562">九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1562">Nine digits</span></span>

<span data-ttu-id="78146-1563">或</span><span class="sxs-lookup"><span data-stu-id="78146-1563">OR</span></span>

- <span data-ttu-id="78146-1564">表示出生日期的六位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="78146-1565">正向斜杠</span><span class="sxs-lookup"><span data-stu-id="78146-1565">A forward slash</span></span>
- <span data-ttu-id="78146-1566">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1566">Three digits</span></span>

<span data-ttu-id="78146-1567">10 位数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="78146-1567">10 digits (new format):</span></span>
- <span data-ttu-id="78146-1568">10 位</span><span class="sxs-lookup"><span data-stu-id="78146-1568">10 digits</span></span>

<span data-ttu-id="78146-1569">或</span><span class="sxs-lookup"><span data-stu-id="78146-1569">OR</span></span>

- <span data-ttu-id="78146-1570">表示出生日期的六位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="78146-1571">正向斜杠</span><span class="sxs-lookup"><span data-stu-id="78146-1571">A forward slash</span></span> 
- <span data-ttu-id="78146-1572">四位数字，其中最后一位数字是校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1573">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1573">Checksum</span></span>

<span data-ttu-id="78146-1574">是</span><span class="sxs-lookup"><span data-stu-id="78146-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1575">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1575">Definition</span></span>

<span data-ttu-id="78146-1576">如果 DLP 策略在 300 个字符的接近范围内检测到这种类型的敏感信息，则 DLP 策略有 85% 的置心度：如果函数 Func_捷克_id_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="78146-1577">找到来自关键字_捷克_id_card的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="78146-1578">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="78146-1579">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1579">Keywords</span></span>

- <span data-ttu-id="78146-1580">捷克人个人身份号码</span><span class="sxs-lookup"><span data-stu-id="78146-1580">czech personal identity number</span></span>
- <span data-ttu-id="78146-1581">罗德内·什洛</span><span class="sxs-lookup"><span data-stu-id="78146-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="78146-1582">丹麥個人識別碼</span><span class="sxs-lookup"><span data-stu-id="78146-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1583">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1583">Format</span></span>

<span data-ttu-id="78146-1584">包含连字符的 10 位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1585">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1585">Pattern</span></span>

<span data-ttu-id="78146-1586">10 位：</span><span class="sxs-lookup"><span data-stu-id="78146-1586">10 digits:</span></span>
- <span data-ttu-id="78146-1587">DDMMYY 格式中的六位数字，即出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="78146-1588">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-1588">A hyphen</span></span> 
- <span data-ttu-id="78146-1589">四位数字，其中最终数字为校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1590">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1590">Checksum</span></span>

<span data-ttu-id="78146-1591">是</span><span class="sxs-lookup"><span data-stu-id="78146-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1592">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1592">Definition</span></span>

<span data-ttu-id="78146-1593">如果正则表达式 Regex_d_d_id 查找与模式匹配的内容，则 DLP 策略 75% 确信检测到这种类型的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="78146-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="78146-1594">找到关键字_丹麦_id的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="78146-1595">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-1596">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="78146-1597">关键字_丹麦_id</span><span class="sxs-lookup"><span data-stu-id="78146-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="78146-1598">个人识别号码</span><span class="sxs-lookup"><span data-stu-id="78146-1598">Personal Identification Number</span></span>
- <span data-ttu-id="78146-1599">Cpr</span><span class="sxs-lookup"><span data-stu-id="78146-1599">CPR</span></span>
- <span data-ttu-id="78146-1600">德特中央人登记册</span><span class="sxs-lookup"><span data-stu-id="78146-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="78146-1601">人物</span><span class="sxs-lookup"><span data-stu-id="78146-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="78146-1602">缉毒署</span><span class="sxs-lookup"><span data-stu-id="78146-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1603">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1603">Format</span></span>

<span data-ttu-id="78146-1604">两个字母后跟七位数字</span><span class="sxs-lookup"><span data-stu-id="78146-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1605">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1605">Pattern</span></span>

<span data-ttu-id="78146-1606">模式必须包括以下所有内容：</span><span class="sxs-lookup"><span data-stu-id="78146-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="78146-1607">一个字母（不区分大小写）从这组可能的字母：abcdefghjklmnprstux，这是一个注册代码</span><span class="sxs-lookup"><span data-stu-id="78146-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="78146-1608">一个字母（不区分大小写），这是注册人姓氏的第一个字母</span><span class="sxs-lookup"><span data-stu-id="78146-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="78146-1609">七位数字，最后一位是校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1610">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1610">Checksum</span></span>

<span data-ttu-id="78146-1611">是</span><span class="sxs-lookup"><span data-stu-id="78146-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1612">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1612">Definition</span></span>

<span data-ttu-id="78146-1613">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1614">函数 Func_dea_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1615">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-1616">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1616">Keywords</span></span>

<span data-ttu-id="78146-1617">無</span><span class="sxs-lookup"><span data-stu-id="78146-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="78146-1618">歐盟轉帳卡號碼</span><span class="sxs-lookup"><span data-stu-id="78146-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1619">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1619">Format</span></span>

<span data-ttu-id="78146-1620">16 位</span><span class="sxs-lookup"><span data-stu-id="78146-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1621">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1621">Pattern</span></span>

<span data-ttu-id="78146-1622">非常复杂且强大的模式</span><span class="sxs-lookup"><span data-stu-id="78146-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1623">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1623">Checksum</span></span>

<span data-ttu-id="78146-1624">是</span><span class="sxs-lookup"><span data-stu-id="78146-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1625">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1625">Definition</span></span>

<span data-ttu-id="78146-1626">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1627">函数 Func_eu_借记卡查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1628">以下至少一项是正确的：</span><span class="sxs-lookup"><span data-stu-id="78146-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="78146-1629">找到关键字_eu_借记卡_card 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="78146-1630">找到关键字_卡片_字距_dict的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="78146-1631">找到关键字_卡片_安全_术语_dict的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="78146-1632">找到关键字_卡片_过期_字距_dict的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="78146-1633">函数 Func_date_date 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="78146-1634">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-1635">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="78146-1636">关键字_eu_借记卡</span><span class="sxs-lookup"><span data-stu-id="78146-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="78146-1637">帐号</span><span class="sxs-lookup"><span data-stu-id="78146-1637">account number</span></span> 
- <span data-ttu-id="78146-1638">卡号</span><span class="sxs-lookup"><span data-stu-id="78146-1638">card number</span></span> 
- <span data-ttu-id="78146-1639">卡号。</span><span class="sxs-lookup"><span data-stu-id="78146-1639">card no.</span></span> 
- <span data-ttu-id="78146-1640">安全号码</span><span class="sxs-lookup"><span data-stu-id="78146-1640">security number</span></span> 
- <span data-ttu-id="78146-1641">Cc#</span><span class="sxs-lookup"><span data-stu-id="78146-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="78146-1642">关键字_卡片_字词_dict</span><span class="sxs-lookup"><span data-stu-id="78146-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="78146-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="78146-1643">acct nbr</span></span> 
- <span data-ttu-id="78146-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="78146-1644">acct num</span></span> 
- <span data-ttu-id="78146-1645">acct 否</span><span class="sxs-lookup"><span data-stu-id="78146-1645">acct no</span></span> 
- <span data-ttu-id="78146-1646">美国快递</span><span class="sxs-lookup"><span data-stu-id="78146-1646">american express</span></span> 
- <span data-ttu-id="78146-1647">美国快递</span><span class="sxs-lookup"><span data-stu-id="78146-1647">americanexpress</span></span> 
- <span data-ttu-id="78146-1648">美洲咖啡</span><span class="sxs-lookup"><span data-stu-id="78146-1648">americano espresso</span></span> 
- <span data-ttu-id="78146-1649">阿姆克斯</span><span class="sxs-lookup"><span data-stu-id="78146-1649">amex</span></span> 
- <span data-ttu-id="78146-1650">atm 卡</span><span class="sxs-lookup"><span data-stu-id="78146-1650">atm card</span></span> 
- <span data-ttu-id="78146-1651">atm 卡</span><span class="sxs-lookup"><span data-stu-id="78146-1651">atm cards</span></span> 
- <span data-ttu-id="78146-1652">阿特姆·卡特</span><span class="sxs-lookup"><span data-stu-id="78146-1652">atm kaart</span></span> 
- <span data-ttu-id="78146-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="78146-1653">atmcard</span></span> 
- <span data-ttu-id="78146-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="78146-1654">atmcards</span></span> 
- <span data-ttu-id="78146-1655">阿特姆卡特</span><span class="sxs-lookup"><span data-stu-id="78146-1655">atmkaart</span></span> 
- <span data-ttu-id="78146-1656">阿滕卡滕</span><span class="sxs-lookup"><span data-stu-id="78146-1656">atmkaarten</span></span> 
- <span data-ttu-id="78146-1657">班接触</span><span class="sxs-lookup"><span data-stu-id="78146-1657">bancontact</span></span> 
- <span data-ttu-id="78146-1658">银行卡</span><span class="sxs-lookup"><span data-stu-id="78146-1658">bank card</span></span> 
- <span data-ttu-id="78146-1659">班克卡尔</span><span class="sxs-lookup"><span data-stu-id="78146-1659">bankkaart</span></span> 
- <span data-ttu-id="78146-1660">持卡人</span><span class="sxs-lookup"><span data-stu-id="78146-1660">card holder</span></span> 
- <span data-ttu-id="78146-1661">持卡人</span><span class="sxs-lookup"><span data-stu-id="78146-1661">card holders</span></span> 
- <span data-ttu-id="78146-1662">卡数</span><span class="sxs-lookup"><span data-stu-id="78146-1662">card num</span></span> 
- <span data-ttu-id="78146-1663">卡号</span><span class="sxs-lookup"><span data-stu-id="78146-1663">card number</span></span> 
- <span data-ttu-id="78146-1664">卡号</span><span class="sxs-lookup"><span data-stu-id="78146-1664">card numbers</span></span> 
- <span data-ttu-id="78146-1665">卡类型</span><span class="sxs-lookup"><span data-stu-id="78146-1665">card type</span></span> 
- <span data-ttu-id="78146-1666">卡尔达诺数字</span><span class="sxs-lookup"><span data-stu-id="78146-1666">cardano numerico</span></span> 
- <span data-ttu-id="78146-1667">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="78146-1667">cardholder</span></span> 
- <span data-ttu-id="78146-1668">持 卡 人</span><span class="sxs-lookup"><span data-stu-id="78146-1668">cardholders</span></span> 
- <span data-ttu-id="78146-1669">卡号</span><span class="sxs-lookup"><span data-stu-id="78146-1669">cardnumber</span></span> 
- <span data-ttu-id="78146-1670">牌号</span><span class="sxs-lookup"><span data-stu-id="78146-1670">cardnumbers</span></span> 
- <span data-ttu-id="78146-1671">卡塔比安卡</span><span class="sxs-lookup"><span data-stu-id="78146-1671">carta bianca</span></span> 
- <span data-ttu-id="78146-1672">卡塔·卡托</span><span class="sxs-lookup"><span data-stu-id="78146-1672">carta credito</span></span> 
- <span data-ttu-id="78146-1673">卡塔迪信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1673">carta di credito</span></span> 
- <span data-ttu-id="78146-1674">卡尔陶·德·信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1674">cartao de credito</span></span> 
- <span data-ttu-id="78146-1675">卡尔陶·德·克雷迪托</span><span class="sxs-lookup"><span data-stu-id="78146-1675">cartao de crédito</span></span> 
- <span data-ttu-id="78146-1676">卡尔陶·德·比乔</span><span class="sxs-lookup"><span data-stu-id="78146-1676">cartao de debito</span></span> 
- <span data-ttu-id="78146-1677">卡尔陶·德德比托</span><span class="sxs-lookup"><span data-stu-id="78146-1677">cartao de débito</span></span> 
- <span data-ttu-id="78146-1678">卡特·班凯雷</span><span class="sxs-lookup"><span data-stu-id="78146-1678">carte bancaire</span></span> 
- <span data-ttu-id="78146-1679">点菜布兰奇</span><span class="sxs-lookup"><span data-stu-id="78146-1679">carte blanche</span></span> 
- <span data-ttu-id="78146-1680">卡特布勒</span><span class="sxs-lookup"><span data-stu-id="78146-1680">carte bleue</span></span> 
- <span data-ttu-id="78146-1681">点菜信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1681">carte de credit</span></span> 
- <span data-ttu-id="78146-1682">点菜</span><span class="sxs-lookup"><span data-stu-id="78146-1682">carte de crédit</span></span> 
- <span data-ttu-id="78146-1683">卡特迪信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1683">carte di credito</span></span> 
- <span data-ttu-id="78146-1684">卡特布兰奇</span><span class="sxs-lookup"><span data-stu-id="78146-1684">carteblanche</span></span> 
- <span data-ttu-id="78146-1685">卡特尼奥·德信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1685">cartão de credito</span></span> 
- <span data-ttu-id="78146-1686">卡特奥·德·卡迪托</span><span class="sxs-lookup"><span data-stu-id="78146-1686">cartão de crédito</span></span> 
- <span data-ttu-id="78146-1687">卡特尼奥·德·比托</span><span class="sxs-lookup"><span data-stu-id="78146-1687">cartão de debito</span></span> 
- <span data-ttu-id="78146-1688">卡尔多·德德比托</span><span class="sxs-lookup"><span data-stu-id="78146-1688">cartão de débito</span></span> 
- <span data-ttu-id="78146-1689">cb</span><span class="sxs-lookup"><span data-stu-id="78146-1689">cb</span></span> 
- <span data-ttu-id="78146-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="78146-1690">ccn</span></span> 
- <span data-ttu-id="78146-1691">支票卡</span><span class="sxs-lookup"><span data-stu-id="78146-1691">check card</span></span> 
- <span data-ttu-id="78146-1692">支票卡</span><span class="sxs-lookup"><span data-stu-id="78146-1692">check cards</span></span> 
- <span data-ttu-id="78146-1693">支票卡</span><span class="sxs-lookup"><span data-stu-id="78146-1693">checkcard</span></span>
- <span data-ttu-id="78146-1694">支票卡</span><span class="sxs-lookup"><span data-stu-id="78146-1694">checkcards</span></span> 
- <span data-ttu-id="78146-1695">切卡尔</span><span class="sxs-lookup"><span data-stu-id="78146-1695">chequekaart</span></span> 
- <span data-ttu-id="78146-1696">卷云</span><span class="sxs-lookup"><span data-stu-id="78146-1696">cirrus</span></span> 
- <span data-ttu-id="78146-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="78146-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="78146-1698">控件卡</span><span class="sxs-lookup"><span data-stu-id="78146-1698">controlekaart</span></span> 
- <span data-ttu-id="78146-1699">控件卡滕</span><span class="sxs-lookup"><span data-stu-id="78146-1699">controlekaarten</span></span> 
- <span data-ttu-id="78146-1700">信用卡</span><span class="sxs-lookup"><span data-stu-id="78146-1700">credit card</span></span> 
- <span data-ttu-id="78146-1701">信用卡</span><span class="sxs-lookup"><span data-stu-id="78146-1701">credit cards</span></span> 
- <span data-ttu-id="78146-1702">信用卡</span><span class="sxs-lookup"><span data-stu-id="78146-1702">creditcard</span></span> 
- <span data-ttu-id="78146-1703">信用卡</span><span class="sxs-lookup"><span data-stu-id="78146-1703">creditcards</span></span> 
- <span data-ttu-id="78146-1704">德贝特卡特</span><span class="sxs-lookup"><span data-stu-id="78146-1704">debetkaart</span></span> 
- <span data-ttu-id="78146-1705">德贝特卡尔滕</span><span class="sxs-lookup"><span data-stu-id="78146-1705">debetkaarten</span></span> 
- <span data-ttu-id="78146-1706">借记卡</span><span class="sxs-lookup"><span data-stu-id="78146-1706">debit card</span></span> 
- <span data-ttu-id="78146-1707">借记卡</span><span class="sxs-lookup"><span data-stu-id="78146-1707">debit cards</span></span> 
- <span data-ttu-id="78146-1708">借记卡</span><span class="sxs-lookup"><span data-stu-id="78146-1708">debitcard</span></span> 
- <span data-ttu-id="78146-1709">借记卡</span><span class="sxs-lookup"><span data-stu-id="78146-1709">debitcards</span></span> 
- <span data-ttu-id="78146-1710">比托自动</span><span class="sxs-lookup"><span data-stu-id="78146-1710">debito automatico</span></span> 
- <span data-ttu-id="78146-1711">食客俱乐部</span><span class="sxs-lookup"><span data-stu-id="78146-1711">diners club</span></span> 
- <span data-ttu-id="78146-1712">食客俱乐部</span><span class="sxs-lookup"><span data-stu-id="78146-1712">dinersclub</span></span> 
- <span data-ttu-id="78146-1713">发现</span><span class="sxs-lookup"><span data-stu-id="78146-1713">discover</span></span> 
- <span data-ttu-id="78146-1714">发现卡</span><span class="sxs-lookup"><span data-stu-id="78146-1714">discover card</span></span> 
- <span data-ttu-id="78146-1715">发现卡片</span><span class="sxs-lookup"><span data-stu-id="78146-1715">discover cards</span></span> 
- <span data-ttu-id="78146-1716">发现卡</span><span class="sxs-lookup"><span data-stu-id="78146-1716">discovercard</span></span> 
- <span data-ttu-id="78146-1717">发现卡</span><span class="sxs-lookup"><span data-stu-id="78146-1717">discovercards</span></span> 
- <span data-ttu-id="78146-1718">德比托·自治蒂科</span><span class="sxs-lookup"><span data-stu-id="78146-1718">débito automático</span></span>
- <span data-ttu-id="78146-1719">埃德克</span><span class="sxs-lookup"><span data-stu-id="78146-1719">edc</span></span> 
- <span data-ttu-id="78146-1720">艾根特·梅尔南</span><span class="sxs-lookup"><span data-stu-id="78146-1720">eigentümername</span></span> 
- <span data-ttu-id="78146-1721">欧洲借记卡</span><span class="sxs-lookup"><span data-stu-id="78146-1721">european debit card</span></span> 
- <span data-ttu-id="78146-1722">霍夫德卡特</span><span class="sxs-lookup"><span data-stu-id="78146-1722">hoofdkaart</span></span> 
- <span data-ttu-id="78146-1723">霍夫德卡滕</span><span class="sxs-lookup"><span data-stu-id="78146-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="78146-1724">在维乔</span><span class="sxs-lookup"><span data-stu-id="78146-1724">in viaggio</span></span> 
- <span data-ttu-id="78146-1725">日本卡局</span><span class="sxs-lookup"><span data-stu-id="78146-1725">japanese card bureau</span></span> 
- <span data-ttu-id="78146-1726">日本·卡特迪恩斯特</span><span class="sxs-lookup"><span data-stu-id="78146-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="78146-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="78146-1727">jcb</span></span> 
- <span data-ttu-id="78146-1728">卡尔特</span><span class="sxs-lookup"><span data-stu-id="78146-1728">kaart</span></span> 
- <span data-ttu-id="78146-1729">卡特·努姆</span><span class="sxs-lookup"><span data-stu-id="78146-1729">kaart num</span></span> 
- <span data-ttu-id="78146-1730">卡尔塔安塔尔</span><span class="sxs-lookup"><span data-stu-id="78146-1730">kaartaantal</span></span> 
- <span data-ttu-id="78146-1731">卡尔塔安塔伦</span><span class="sxs-lookup"><span data-stu-id="78146-1731">kaartaantallen</span></span> 
- <span data-ttu-id="78146-1732">卡尔图德</span><span class="sxs-lookup"><span data-stu-id="78146-1732">kaarthouder</span></span> 
- <span data-ttu-id="78146-1733">卡尔特霍德斯</span><span class="sxs-lookup"><span data-stu-id="78146-1733">kaarthouders</span></span> 
- <span data-ttu-id="78146-1734">卡尔特</span><span class="sxs-lookup"><span data-stu-id="78146-1734">karte</span></span>  
- <span data-ttu-id="78146-1735">卡尔特宁哈伯</span><span class="sxs-lookup"><span data-stu-id="78146-1735">karteninhaber</span></span> 
- <span data-ttu-id="78146-1736">卡尔特宁哈伯斯</span><span class="sxs-lookup"><span data-stu-id="78146-1736">karteninhabers</span></span>
- <span data-ttu-id="78146-1737">卡尔滕内尔</span><span class="sxs-lookup"><span data-stu-id="78146-1737">kartennr</span></span> 
- <span data-ttu-id="78146-1738">卡尔滕努默</span><span class="sxs-lookup"><span data-stu-id="78146-1738">kartennummer</span></span> 
- <span data-ttu-id="78146-1739">克雷迪克特卡特</span><span class="sxs-lookup"><span data-stu-id="78146-1739">kreditkarte</span></span> 
- <span data-ttu-id="78146-1740">克雷迪克特卡滕-努默</span><span class="sxs-lookup"><span data-stu-id="78146-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="78146-1741">克雷迪克特卡特宁哈伯</span><span class="sxs-lookup"><span data-stu-id="78146-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="78146-1742">克雷蒂特卡滕特研究所</span><span class="sxs-lookup"><span data-stu-id="78146-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="78146-1743">克雷迪克特卡滕努默</span><span class="sxs-lookup"><span data-stu-id="78146-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="78146-1744">克雷蒂特卡滕蒂普</span><span class="sxs-lookup"><span data-stu-id="78146-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="78146-1745">大师</span><span class="sxs-lookup"><span data-stu-id="78146-1745">maestro</span></span> 
- <span data-ttu-id="78146-1746">主卡</span><span class="sxs-lookup"><span data-stu-id="78146-1746">master card</span></span> 
- <span data-ttu-id="78146-1747">主卡</span><span class="sxs-lookup"><span data-stu-id="78146-1747">master cards</span></span> 
- <span data-ttu-id="78146-1748">万事 达</span><span class="sxs-lookup"><span data-stu-id="78146-1748">mastercard</span></span> 
- <span data-ttu-id="78146-1749">万事达卡</span><span class="sxs-lookup"><span data-stu-id="78146-1749">mastercards</span></span> 
- <span data-ttu-id="78146-1750">Mc</span><span class="sxs-lookup"><span data-stu-id="78146-1750">mc</span></span> 
- <span data-ttu-id="78146-1751">先生现金</span><span class="sxs-lookup"><span data-stu-id="78146-1751">mister cash</span></span> 
- <span data-ttu-id="78146-1752">n 卡塔</span><span class="sxs-lookup"><span data-stu-id="78146-1752">n carta</span></span> 
- <span data-ttu-id="78146-1753">宪章</span><span class="sxs-lookup"><span data-stu-id="78146-1753">carta</span></span> 
- <span data-ttu-id="78146-1754">没有塔里塔</span><span class="sxs-lookup"><span data-stu-id="78146-1754">no de tarjeta</span></span> 
- <span data-ttu-id="78146-1755">没有做卡陶</span><span class="sxs-lookup"><span data-stu-id="78146-1755">no do cartao</span></span> 
- <span data-ttu-id="78146-1756">没有做卡特奥</span><span class="sxs-lookup"><span data-stu-id="78146-1756">no do cartão</span></span> 
- <span data-ttu-id="78146-1757">不。</span><span class="sxs-lookup"><span data-stu-id="78146-1757">no.</span></span> <span data-ttu-id="78146-1758">德塔耶塔</span><span class="sxs-lookup"><span data-stu-id="78146-1758">de tarjeta</span></span> 
- <span data-ttu-id="78146-1759">不。</span><span class="sxs-lookup"><span data-stu-id="78146-1759">no.</span></span> <span data-ttu-id="78146-1760">多卡陶</span><span class="sxs-lookup"><span data-stu-id="78146-1760">do cartao</span></span> 
- <span data-ttu-id="78146-1761">不。</span><span class="sxs-lookup"><span data-stu-id="78146-1761">no.</span></span> <span data-ttu-id="78146-1762">多卡托</span><span class="sxs-lookup"><span data-stu-id="78146-1762">do cartão</span></span> 
- <span data-ttu-id="78146-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="78146-1763">nr carta</span></span> 
- <span data-ttu-id="78146-1764">星期日。</span><span class="sxs-lookup"><span data-stu-id="78146-1764">nr.</span></span> <span data-ttu-id="78146-1765">宪章</span><span class="sxs-lookup"><span data-stu-id="78146-1765">carta</span></span> 
- <span data-ttu-id="78146-1766">努梅里·迪·沙达</span><span class="sxs-lookup"><span data-stu-id="78146-1766">numeri di scheda</span></span> 
- <span data-ttu-id="78146-1767">努梅罗·卡塔</span><span class="sxs-lookup"><span data-stu-id="78146-1767">numero carta</span></span> 
- <span data-ttu-id="78146-1768">努梅罗·德·卡陶</span><span class="sxs-lookup"><span data-stu-id="78146-1768">numero de cartao</span></span> 
- <span data-ttu-id="78146-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="78146-1769">numero de carte</span></span> 
- <span data-ttu-id="78146-1770">numero de cartío</span><span class="sxs-lookup"><span data-stu-id="78146-1770">numero de cartão</span></span> 
- <span data-ttu-id="78146-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="78146-1771">numero de tarjeta</span></span>
- <span data-ttu-id="78146-1772">numero dela carta</span><span class="sxs-lookup"><span data-stu-id="78146-1772">numero della carta</span></span> 
- <span data-ttu-id="78146-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="78146-1773">numero di carta</span></span> 
- <span data-ttu-id="78146-1774">努梅罗·迪·沙达</span><span class="sxs-lookup"><span data-stu-id="78146-1774">numero di scheda</span></span> 
- <span data-ttu-id="78146-1775">numero do Cartao</span><span class="sxs-lookup"><span data-stu-id="78146-1775">numero do cartao</span></span> 
- <span data-ttu-id="78146-1776">numero do cartío</span><span class="sxs-lookup"><span data-stu-id="78146-1776">numero do cartão</span></span> 
- <span data-ttu-id="78146-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="78146-1777">numéro de carte</span></span> 
- <span data-ttu-id="78146-1778">no o 卡特拉</span><span class="sxs-lookup"><span data-stu-id="78146-1778">nº carta</span></span> 
- <span data-ttu-id="78146-1779">点菜</span><span class="sxs-lookup"><span data-stu-id="78146-1779">nº de carte</span></span> 
- <span data-ttu-id="78146-1780">点菜号</span><span class="sxs-lookup"><span data-stu-id="78146-1780">nº de la carte</span></span> 
- <span data-ttu-id="78146-1781">诺德塔耶塔</span><span class="sxs-lookup"><span data-stu-id="78146-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="78146-1782">no do Cartao</span><span class="sxs-lookup"><span data-stu-id="78146-1782">nº do cartao</span></span> 
- <span data-ttu-id="78146-1783">no do cartéo</span><span class="sxs-lookup"><span data-stu-id="78146-1783">nº do cartão</span></span> 
- <span data-ttu-id="78146-1784">no.</span><span class="sxs-lookup"><span data-stu-id="78146-1784">nº.</span></span> <span data-ttu-id="78146-1785">多卡托</span><span class="sxs-lookup"><span data-stu-id="78146-1785">do cartão</span></span> 
- <span data-ttu-id="78146-1786">内梅罗·德卡托</span><span class="sxs-lookup"><span data-stu-id="78146-1786">número de cartao</span></span> 
- <span data-ttu-id="78146-1787">némero de cartéo</span><span class="sxs-lookup"><span data-stu-id="78146-1787">número de cartão</span></span> 
- <span data-ttu-id="78146-1788">内梅罗·德塔耶塔</span><span class="sxs-lookup"><span data-stu-id="78146-1788">número de tarjeta</span></span> 
- <span data-ttu-id="78146-1789">内梅罗·多·卡托</span><span class="sxs-lookup"><span data-stu-id="78146-1789">número do cartao</span></span> 
- <span data-ttu-id="78146-1790">谢达·德尔阿塞格诺</span><span class="sxs-lookup"><span data-stu-id="78146-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="78146-1791">沙达·德尔阿莫斯费拉</span><span class="sxs-lookup"><span data-stu-id="78146-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="78146-1792">沙达·德尔阿莫斯费拉</span><span class="sxs-lookup"><span data-stu-id="78146-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="78146-1793">沙达德拉班卡</span><span class="sxs-lookup"><span data-stu-id="78146-1793">scheda della banca</span></span> 
- <span data-ttu-id="78146-1794">沙达迪控制洛</span><span class="sxs-lookup"><span data-stu-id="78146-1794">scheda di controllo</span></span> 
- <span data-ttu-id="78146-1795">沙达迪比托</span><span class="sxs-lookup"><span data-stu-id="78146-1795">scheda di debito</span></span> 
- <span data-ttu-id="78146-1796">沙达矩阵</span><span class="sxs-lookup"><span data-stu-id="78146-1796">scheda matrice</span></span> 
- <span data-ttu-id="78146-1797">舍德·德尔阿莫斯费拉</span><span class="sxs-lookup"><span data-stu-id="78146-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="78146-1798">舍德迪控制洛</span><span class="sxs-lookup"><span data-stu-id="78146-1798">schede di controllo</span></span> 
- <span data-ttu-id="78146-1799">舍德·迪·比乔</span><span class="sxs-lookup"><span data-stu-id="78146-1799">schede di debito</span></span> 
- <span data-ttu-id="78146-1800">舍德·马特里基</span><span class="sxs-lookup"><span data-stu-id="78146-1800">schede matrici</span></span> 
- <span data-ttu-id="78146-1801">斯科普罗诺·拉沙达</span><span class="sxs-lookup"><span data-stu-id="78146-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="78146-1802">斯科普罗诺·勒舍德</span><span class="sxs-lookup"><span data-stu-id="78146-1802">scoprono le schede</span></span> 
- <span data-ttu-id="78146-1803">独奏</span><span class="sxs-lookup"><span data-stu-id="78146-1803">solo</span></span> 
- <span data-ttu-id="78146-1804">支持迪沙达</span><span class="sxs-lookup"><span data-stu-id="78146-1804">supporti di scheda</span></span> 
- <span data-ttu-id="78146-1805">支持迪沙达</span><span class="sxs-lookup"><span data-stu-id="78146-1805">supporto di scheda</span></span> 
- <span data-ttu-id="78146-1806">开关</span><span class="sxs-lookup"><span data-stu-id="78146-1806">switch</span></span> 
- <span data-ttu-id="78146-1807">塔耶塔 atm</span><span class="sxs-lookup"><span data-stu-id="78146-1807">tarjeta atm</span></span> 
- <span data-ttu-id="78146-1808">塔耶塔信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1808">tarjeta credito</span></span> 
- <span data-ttu-id="78146-1809">塔耶塔·德阿特姆</span><span class="sxs-lookup"><span data-stu-id="78146-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="78146-1810">塔耶塔·德·信贷</span><span class="sxs-lookup"><span data-stu-id="78146-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="78146-1811">塔耶塔·德·比乔</span><span class="sxs-lookup"><span data-stu-id="78146-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="78146-1812">塔耶塔·比托</span><span class="sxs-lookup"><span data-stu-id="78146-1812">tarjeta debito</span></span> 
- <span data-ttu-id="78146-1813">塔耶塔没有</span><span class="sxs-lookup"><span data-stu-id="78146-1813">tarjeta no</span></span>
- <span data-ttu-id="78146-1814">塔尔杰塔哈比恩特</span><span class="sxs-lookup"><span data-stu-id="78146-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="78146-1815">蒂波·德拉·沙达</span><span class="sxs-lookup"><span data-stu-id="78146-1815">tipo della scheda</span></span> 
- <span data-ttu-id="78146-1816">乌菲西奥·贾波内斯·德拉</span><span class="sxs-lookup"><span data-stu-id="78146-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="78146-1817">沙达</span><span class="sxs-lookup"><span data-stu-id="78146-1817">scheda</span></span> 
- <span data-ttu-id="78146-1818">v 支付</span><span class="sxs-lookup"><span data-stu-id="78146-1818">v pay</span></span> 
- <span data-ttu-id="78146-1819">v-支付</span><span class="sxs-lookup"><span data-stu-id="78146-1819">v-pay</span></span> 
- <span data-ttu-id="78146-1820">签证</span><span class="sxs-lookup"><span data-stu-id="78146-1820">visa</span></span> 
- <span data-ttu-id="78146-1821">签证加</span><span class="sxs-lookup"><span data-stu-id="78146-1821">visa plus</span></span> 
- <span data-ttu-id="78146-1822">签证电子</span><span class="sxs-lookup"><span data-stu-id="78146-1822">visa electron</span></span> 
- <span data-ttu-id="78146-1823">内托</span><span class="sxs-lookup"><span data-stu-id="78146-1823">visto</span></span> 
- <span data-ttu-id="78146-1824">维苏姆</span><span class="sxs-lookup"><span data-stu-id="78146-1824">visum</span></span> 
- <span data-ttu-id="78146-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="78146-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="78146-1826">关键词_卡片+安全+术语</span><span class="sxs-lookup"><span data-stu-id="78146-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="78146-1827">卡标识号</span><span class="sxs-lookup"><span data-stu-id="78146-1827">card identification number</span></span>
- <span data-ttu-id="78146-1828">卡验证</span><span class="sxs-lookup"><span data-stu-id="78146-1828">card verification</span></span> 
- <span data-ttu-id="78146-1829">卡迪拉维维卡</span><span class="sxs-lookup"><span data-stu-id="78146-1829">cardi la verifica</span></span> 
- <span data-ttu-id="78146-1830">cid</span><span class="sxs-lookup"><span data-stu-id="78146-1830">cid</span></span> 
- <span data-ttu-id="78146-1831">鳕鱼赛格</span><span class="sxs-lookup"><span data-stu-id="78146-1831">cod seg</span></span> 
- <span data-ttu-id="78146-1832">鳕鱼塞古兰卡</span><span class="sxs-lookup"><span data-stu-id="78146-1832">cod seguranca</span></span> 
- <span data-ttu-id="78146-1833">鳕鱼塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1833">cod segurança</span></span> 
- <span data-ttu-id="78146-1834">鳕鱼西库雷扎</span><span class="sxs-lookup"><span data-stu-id="78146-1834">cod sicurezza</span></span> 
- <span data-ttu-id="78146-1835">Cod。</span><span class="sxs-lookup"><span data-stu-id="78146-1835">cod.</span></span> <span data-ttu-id="78146-1836">Seg</span><span class="sxs-lookup"><span data-stu-id="78146-1836">seg</span></span> 
- <span data-ttu-id="78146-1837">Cod。</span><span class="sxs-lookup"><span data-stu-id="78146-1837">cod.</span></span> <span data-ttu-id="78146-1838">塞古兰卡</span><span class="sxs-lookup"><span data-stu-id="78146-1838">seguranca</span></span> 
- <span data-ttu-id="78146-1839">Cod。</span><span class="sxs-lookup"><span data-stu-id="78146-1839">cod.</span></span> <span data-ttu-id="78146-1840">塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1840">segurança</span></span> 
- <span data-ttu-id="78146-1841">Cod。</span><span class="sxs-lookup"><span data-stu-id="78146-1841">cod.</span></span> <span data-ttu-id="78146-1842">西库雷扎</span><span class="sxs-lookup"><span data-stu-id="78146-1842">sicurezza</span></span> 
- <span data-ttu-id="78146-1843">科迪迪斯·迪·西库雷扎</span><span class="sxs-lookup"><span data-stu-id="78146-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="78146-1844">科迪斯·迪维蒂卡</span><span class="sxs-lookup"><span data-stu-id="78146-1844">codice di verifica</span></span> 
- <span data-ttu-id="78146-1845">科迪戈</span><span class="sxs-lookup"><span data-stu-id="78146-1845">codigo</span></span> 
- <span data-ttu-id="78146-1846">科迪戈·德塞古兰卡</span><span class="sxs-lookup"><span data-stu-id="78146-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="78146-1847">科迪戈·德塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1847">codigo de segurança</span></span> 
- <span data-ttu-id="78146-1848">克米托格拉姆马</span><span class="sxs-lookup"><span data-stu-id="78146-1848">crittogramma</span></span> 
- <span data-ttu-id="78146-1849">密码</span><span class="sxs-lookup"><span data-stu-id="78146-1849">cryptogram</span></span> 
- <span data-ttu-id="78146-1850">密码语法</span><span class="sxs-lookup"><span data-stu-id="78146-1850">cryptogramme</span></span> 
- <span data-ttu-id="78146-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="78146-1851">cv2</span></span> 
- <span data-ttu-id="78146-1852">Cvc</span><span class="sxs-lookup"><span data-stu-id="78146-1852">cvc</span></span> 
- <span data-ttu-id="78146-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="78146-1853">cvc2</span></span> 
- <span data-ttu-id="78146-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="78146-1854">cvn</span></span> 
- <span data-ttu-id="78146-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="78146-1855">cvv</span></span> 
- <span data-ttu-id="78146-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="78146-1856">cvv2</span></span> 
- <span data-ttu-id="78146-1857">塞古兰卡</span><span class="sxs-lookup"><span data-stu-id="78146-1857">cód seguranca</span></span> 
- <span data-ttu-id="78146-1858">塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1858">cód segurança</span></span> 
- <span data-ttu-id="78146-1859">c_d.</span><span class="sxs-lookup"><span data-stu-id="78146-1859">cód.</span></span> <span data-ttu-id="78146-1860">塞古兰卡</span><span class="sxs-lookup"><span data-stu-id="78146-1860">seguranca</span></span> 
- <span data-ttu-id="78146-1861">c_d.</span><span class="sxs-lookup"><span data-stu-id="78146-1861">cód.</span></span> <span data-ttu-id="78146-1862">塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1862">segurança</span></span> 
- <span data-ttu-id="78146-1863">塞迪戈</span><span class="sxs-lookup"><span data-stu-id="78146-1863">código</span></span> 
- <span data-ttu-id="78146-1864">塞古兰卡</span><span class="sxs-lookup"><span data-stu-id="78146-1864">código de seguranca</span></span> 
- <span data-ttu-id="78146-1865">塞古拉尼亚</span><span class="sxs-lookup"><span data-stu-id="78146-1865">código de segurança</span></span> 
- <span data-ttu-id="78146-1866">德卡特控制</span><span class="sxs-lookup"><span data-stu-id="78146-1866">de kaart controle</span></span> 
- <span data-ttu-id="78146-1867">吉夫特·里乌特</span><span class="sxs-lookup"><span data-stu-id="78146-1867">geeft nr uit</span></span> 
- <span data-ttu-id="78146-1868">问题否</span><span class="sxs-lookup"><span data-stu-id="78146-1868">issue no</span></span> 
- <span data-ttu-id="78146-1869">问题编号</span><span class="sxs-lookup"><span data-stu-id="78146-1869">issue number</span></span> 
- <span data-ttu-id="78146-1870">卡尔蒂登蒂卡蒂阿努默</span><span class="sxs-lookup"><span data-stu-id="78146-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="78146-1871">克雷迪克特卡滕普鲁夫努默</span><span class="sxs-lookup"><span data-stu-id="78146-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="78146-1872">克雷迪克特卡滕普吕夫努默</span><span class="sxs-lookup"><span data-stu-id="78146-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="78146-1873">克韦斯特亚安塔尔</span><span class="sxs-lookup"><span data-stu-id="78146-1873">kwestieaantal</span></span> 
- <span data-ttu-id="78146-1874">不。</span><span class="sxs-lookup"><span data-stu-id="78146-1874">no.</span></span> <span data-ttu-id="78146-1875">德尔伊迪齐奥内</span><span class="sxs-lookup"><span data-stu-id="78146-1875">dell'edizione</span></span> 
- <span data-ttu-id="78146-1876">不。</span><span class="sxs-lookup"><span data-stu-id="78146-1876">no.</span></span> <span data-ttu-id="78146-1877">迪西库雷扎</span><span class="sxs-lookup"><span data-stu-id="78146-1877">di sicurezza</span></span> 
- <span data-ttu-id="78146-1878">numero de Securite</span><span class="sxs-lookup"><span data-stu-id="78146-1878">numero de securite</span></span> 
- <span data-ttu-id="78146-1879">numero de 验证卡考</span><span class="sxs-lookup"><span data-stu-id="78146-1879">numero de verificacao</span></span> 
- <span data-ttu-id="78146-1880">numero del'edizione</span><span class="sxs-lookup"><span data-stu-id="78146-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="78146-1881">numero di identicazione dela</span><span class="sxs-lookup"><span data-stu-id="78146-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="78146-1882">沙达</span><span class="sxs-lookup"><span data-stu-id="78146-1882">scheda</span></span> 
- <span data-ttu-id="78146-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="78146-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="78146-1884">努梅罗·范·韦莱格海德</span><span class="sxs-lookup"><span data-stu-id="78146-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="78146-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="78146-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="78146-1886">诺·奥特里扎齐内</span><span class="sxs-lookup"><span data-stu-id="78146-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="78146-1887">努梅罗·德维萨奥</span><span class="sxs-lookup"><span data-stu-id="78146-1887">número de verificação</span></span> 
- <span data-ttu-id="78146-1888">佩尔诺·伊尔·布洛克</span><span class="sxs-lookup"><span data-stu-id="78146-1888">perno il blocco</span></span> 
- <span data-ttu-id="78146-1889">引脚块</span><span class="sxs-lookup"><span data-stu-id="78146-1889">pin block</span></span> 
- <span data-ttu-id="78146-1890">普鲁夫齐弗</span><span class="sxs-lookup"><span data-stu-id="78146-1890">prufziffer</span></span> 
- <span data-ttu-id="78146-1891">普雷夫齐弗</span><span class="sxs-lookup"><span data-stu-id="78146-1891">prüfziffer</span></span> 
- <span data-ttu-id="78146-1892">安全代码</span><span class="sxs-lookup"><span data-stu-id="78146-1892">security code</span></span> 
- <span data-ttu-id="78146-1893">安全否</span><span class="sxs-lookup"><span data-stu-id="78146-1893">security no</span></span> 
- <span data-ttu-id="78146-1894">安全号码</span><span class="sxs-lookup"><span data-stu-id="78146-1894">security number</span></span> 
- <span data-ttu-id="78146-1895">希切海茨·科德</span><span class="sxs-lookup"><span data-stu-id="78146-1895">sicherheits kode</span></span> 
- <span data-ttu-id="78146-1896">sicherheits码</span><span class="sxs-lookup"><span data-stu-id="78146-1896">sicherheitscode</span></span> 
- <span data-ttu-id="78146-1897">希切赫赫努默</span><span class="sxs-lookup"><span data-stu-id="78146-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="78146-1898">斯佩尔德布洛克</span><span class="sxs-lookup"><span data-stu-id="78146-1898">speldblok</span></span> 
- <span data-ttu-id="78146-1899">韦利格海德·内尔</span><span class="sxs-lookup"><span data-stu-id="78146-1899">veiligheid nr</span></span> 
- <span data-ttu-id="78146-1900">维伊格海德桑塔尔</span><span class="sxs-lookup"><span data-stu-id="78146-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="78146-1901">韦利格海德斯码</span><span class="sxs-lookup"><span data-stu-id="78146-1901">veiligheidscode</span></span> 
- <span data-ttu-id="78146-1902">韦利格海德斯努默</span><span class="sxs-lookup"><span data-stu-id="78146-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="78146-1903">弗法尔达图姆</span><span class="sxs-lookup"><span data-stu-id="78146-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="78146-1904">关键字_卡片_过期_术语_dict</span><span class="sxs-lookup"><span data-stu-id="78146-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="78146-1905">阿布拉夫</span><span class="sxs-lookup"><span data-stu-id="78146-1905">ablauf</span></span> 
- <span data-ttu-id="78146-1906">数据到期</span><span class="sxs-lookup"><span data-stu-id="78146-1906">data de expiracao</span></span> 
- <span data-ttu-id="78146-1907">数据到期</span><span class="sxs-lookup"><span data-stu-id="78146-1907">data de expiração</span></span> 
- <span data-ttu-id="78146-1908">数据德尔exp</span><span class="sxs-lookup"><span data-stu-id="78146-1908">data del exp</span></span> 
- <span data-ttu-id="78146-1909">数据 di exp</span><span class="sxs-lookup"><span data-stu-id="78146-1909">data di exp</span></span> 
- <span data-ttu-id="78146-1910">数据迪斯卡登扎</span><span class="sxs-lookup"><span data-stu-id="78146-1910">data di scadenza</span></span> 
- <span data-ttu-id="78146-1911">数据 em que 到期</span><span class="sxs-lookup"><span data-stu-id="78146-1911">data em que expira</span></span> 
- <span data-ttu-id="78146-1912">数据 scad</span><span class="sxs-lookup"><span data-stu-id="78146-1912">data scad</span></span> 
- <span data-ttu-id="78146-1913">数据斯卡登扎</span><span class="sxs-lookup"><span data-stu-id="78146-1913">data scadenza</span></span> 
- <span data-ttu-id="78146-1914">有效日期\*</span><span class="sxs-lookup"><span data-stu-id="78146-1914">date de validité</span></span> 
- <span data-ttu-id="78146-1915">基准 afloop</span><span class="sxs-lookup"><span data-stu-id="78146-1915">datum afloop</span></span> 
- <span data-ttu-id="78146-1916">达图姆·范exp</span><span class="sxs-lookup"><span data-stu-id="78146-1916">datum van exp</span></span> 
- <span data-ttu-id="78146-1917">德阿夫卢普</span><span class="sxs-lookup"><span data-stu-id="78146-1917">de afloop</span></span> 
- <span data-ttu-id="78146-1918">埃斯皮拉</span><span class="sxs-lookup"><span data-stu-id="78146-1918">espira</span></span> 
- <span data-ttu-id="78146-1919">埃斯皮拉</span><span class="sxs-lookup"><span data-stu-id="78146-1919">espira</span></span> 
- <span data-ttu-id="78146-1920">exp 日期</span><span class="sxs-lookup"><span data-stu-id="78146-1920">exp date</span></span> 
- <span data-ttu-id="78146-1921">exp 基准</span><span class="sxs-lookup"><span data-stu-id="78146-1921">exp datum</span></span> 
- <span data-ttu-id="78146-1922">到期</span><span class="sxs-lookup"><span data-stu-id="78146-1922">expiration</span></span> 
- <span data-ttu-id="78146-1923">到期</span><span class="sxs-lookup"><span data-stu-id="78146-1923">expire</span></span> 
- <span data-ttu-id="78146-1924">到期</span><span class="sxs-lookup"><span data-stu-id="78146-1924">expires</span></span> 
- <span data-ttu-id="78146-1925">届满</span><span class="sxs-lookup"><span data-stu-id="78146-1925">expiry</span></span> 
- <span data-ttu-id="78146-1926">过期</span><span class="sxs-lookup"><span data-stu-id="78146-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="78146-1927">费查·德·韦克</span><span class="sxs-lookup"><span data-stu-id="78146-1927">fecha de venc</span></span> 
- <span data-ttu-id="78146-1928">古尔蒂格·比斯</span><span class="sxs-lookup"><span data-stu-id="78146-1928">gultig bis</span></span> 
- <span data-ttu-id="78146-1929">古尔蒂格凯茨达图姆</span><span class="sxs-lookup"><span data-stu-id="78146-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="78146-1930">盖尔蒂格·比斯</span><span class="sxs-lookup"><span data-stu-id="78146-1930">gültig bis</span></span> 
- <span data-ttu-id="78146-1931">盖尔蒂格凯茨达图姆</span><span class="sxs-lookup"><span data-stu-id="78146-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="78146-1932">拉斯卡登扎</span><span class="sxs-lookup"><span data-stu-id="78146-1932">la scadenza</span></span> 
- <span data-ttu-id="78146-1933">沙登扎</span><span class="sxs-lookup"><span data-stu-id="78146-1933">scadenza</span></span> 
- <span data-ttu-id="78146-1934">瓦尔维</span><span class="sxs-lookup"><span data-stu-id="78146-1934">valable</span></span> 
- <span data-ttu-id="78146-1935">有效</span><span class="sxs-lookup"><span data-stu-id="78146-1935">validade</span></span> 
- <span data-ttu-id="78146-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="78146-1936">valido hasta</span></span> 
- <span data-ttu-id="78146-1937">勇气</span><span class="sxs-lookup"><span data-stu-id="78146-1937">valor</span></span> 
- <span data-ttu-id="78146-1938">韦克</span><span class="sxs-lookup"><span data-stu-id="78146-1938">venc</span></span> 
- <span data-ttu-id="78146-1939">文奇门托</span><span class="sxs-lookup"><span data-stu-id="78146-1939">vencimento</span></span> 
- <span data-ttu-id="78146-1940">文西门托</span><span class="sxs-lookup"><span data-stu-id="78146-1940">vencimiento</span></span> 
- <span data-ttu-id="78146-1941">弗鲁普特</span><span class="sxs-lookup"><span data-stu-id="78146-1941">verloopt</span></span> 
- <span data-ttu-id="78146-1942">韦尔瓦尔达格</span><span class="sxs-lookup"><span data-stu-id="78146-1942">vervaldag</span></span> 
- <span data-ttu-id="78146-1943">韦尔瓦尔达图姆</span><span class="sxs-lookup"><span data-stu-id="78146-1943">vervaldatum</span></span> 
- <span data-ttu-id="78146-1944">vto</span><span class="sxs-lookup"><span data-stu-id="78146-1944">vto</span></span> 
- <span data-ttu-id="78146-1945">瓦利多·哈斯塔</span><span class="sxs-lookup"><span data-stu-id="78146-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="78146-1946">欧盟驾照号码</span><span class="sxs-lookup"><span data-stu-id="78146-1946">EU Driver's License Number</span></span>

<span data-ttu-id="78146-1947">要了解更多信息，请参阅[欧盟驾照号码敏感信息类型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="78146-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="78146-1948">欧盟国家身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-1948">EU National Identification Number</span></span>

<span data-ttu-id="78146-1949">要了解更多信息，请参阅[欧盟国家标识号敏感信息类型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="78146-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="78146-1950">欧盟护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-1950">EU Passport Number</span></span>

<span data-ttu-id="78146-1951">要了解更多信息，请参阅[欧盟护照号码敏感信息类型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="78146-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="78146-1952">欧盟社会保险号或等效 ID</span><span class="sxs-lookup"><span data-stu-id="78146-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="78146-1953">要了解更多信息，请参阅[欧盟社会安全号码或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="78146-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="78146-1954">欧盟税务识别号</span><span class="sxs-lookup"><span data-stu-id="78146-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="78146-1955">要了解更多信息，请参阅[欧盟税务识别号敏感信息类型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="78146-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="78146-1956">芬蘭國民身分證</span><span class="sxs-lookup"><span data-stu-id="78146-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="78146-1957">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1957">Format</span></span>

<span data-ttu-id="78146-1958">六位数字加上一个字符，表示一个世纪加上三位数字加上一个校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1959">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1959">Pattern</span></span>

<span data-ttu-id="78146-1960">模式必须包括以下所有内容：</span><span class="sxs-lookup"><span data-stu-id="78146-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="78146-1961">格式 DDMMYY 格式的六位数字，即出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="78146-1962">世纪标记（"-"，"+"或"a"）</span><span class="sxs-lookup"><span data-stu-id="78146-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="78146-1963">三位个人识别号码</span><span class="sxs-lookup"><span data-stu-id="78146-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="78146-1964">数字或字母（不区分大小写），这是校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1965">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1965">Checksum</span></span>

<span data-ttu-id="78146-1966">是</span><span class="sxs-lookup"><span data-stu-id="78146-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1967">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1967">Definition</span></span>

<span data-ttu-id="78146-1968">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1969">函数 Func_finnish_national_id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1970">找到来自关键字_芬兰_国家_id的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="78146-1971">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-1972">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1972">Keywords</span></span>

- <span data-ttu-id="78146-1973">关键字_芬兰_国家_id</span><span class="sxs-lookup"><span data-stu-id="78146-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="78146-1974">索西亚利图瓦图努斯</span><span class="sxs-lookup"><span data-stu-id="78146-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="78146-1975">索图·亨基勒图努斯·赫图</span><span class="sxs-lookup"><span data-stu-id="78146-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="78146-1976">人物贝塞克宁</span><span class="sxs-lookup"><span data-stu-id="78146-1976">Personbeteckning</span></span>
- <span data-ttu-id="78146-1977">人物</span><span class="sxs-lookup"><span data-stu-id="78146-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="78146-1978">芬蘭護照號碼</span><span class="sxs-lookup"><span data-stu-id="78146-1978">Finland Passport Number</span></span>

<span data-ttu-id="78146-1979">格式 9 个字母和数字模式组合 9 个字母和数字：两个字母（不区分大小写）七位数字校验和无定义 DLP 策略是 75% 的置信，它检测到这种类型的敏感信息，如果，300 个字符的邻近性：正则表达式 Regex_finland_Passport_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="78146-1980">找到关键字_芬兰_护照_号码的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="78146-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="78146-1981"></span></span>
<span data-ttu-id="78146-1982">关键词关键字_芬兰人_护照_数字护照帕西</span><span class="sxs-lookup"><span data-stu-id="78146-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="78146-1983">法國駕照編號</span><span class="sxs-lookup"><span data-stu-id="78146-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-1984">格式</span><span class="sxs-lookup"><span data-stu-id="78146-1984">Format</span></span>

<span data-ttu-id="78146-1985">12 位</span><span class="sxs-lookup"><span data-stu-id="78146-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-1986">模式</span><span class="sxs-lookup"><span data-stu-id="78146-1986">Pattern</span></span>

<span data-ttu-id="78146-1987">12 位数字，可验证以折扣类似模式（如法语电话号码）</span><span class="sxs-lookup"><span data-stu-id="78146-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-1988">校验</span><span class="sxs-lookup"><span data-stu-id="78146-1988">Checksum</span></span>

<span data-ttu-id="78146-1989">否</span><span class="sxs-lookup"><span data-stu-id="78146-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-1990">定義</span><span class="sxs-lookup"><span data-stu-id="78146-1990">Definition</span></span>

<span data-ttu-id="78146-1991">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-1992">函数 Func_french_驱动程序_许可证查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-1993">以下至少一项是正确的：</span><span class="sxs-lookup"><span data-stu-id="78146-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="78146-1994">找到关键字_french_驱动程序_许可证的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="78146-1995">函数 Func_eu_date 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-1996">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="78146-1997">关键词_法语_驱动程序_许可证</span><span class="sxs-lookup"><span data-stu-id="78146-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="78146-1998">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-1998">drivers licence</span></span>
- <span data-ttu-id="78146-1999">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-1999">drivers license</span></span>
- <span data-ttu-id="78146-2000">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2000">driving licence</span></span>
- <span data-ttu-id="78146-2001">驾照</span><span class="sxs-lookup"><span data-stu-id="78146-2001">driving license</span></span>
- <span data-ttu-id="78146-2002">佩尔米斯·德孔杜瓦</span><span class="sxs-lookup"><span data-stu-id="78146-2002">permis de conduire</span></span>
- <span data-ttu-id="78146-2003">牌照号码</span><span class="sxs-lookup"><span data-stu-id="78146-2003">licence number</span></span>
- <span data-ttu-id="78146-2004">许可证号</span><span class="sxs-lookup"><span data-stu-id="78146-2004">license number</span></span>
- <span data-ttu-id="78146-2005">许可证号码</span><span class="sxs-lookup"><span data-stu-id="78146-2005">licence numbers</span></span>
- <span data-ttu-id="78146-2006">许可证号</span><span class="sxs-lookup"><span data-stu-id="78146-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="78146-2007">法國國民身分證 (CNI)</span><span class="sxs-lookup"><span data-stu-id="78146-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="78146-2008">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2008">Format</span></span>

<span data-ttu-id="78146-2009">12 位</span><span class="sxs-lookup"><span data-stu-id="78146-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2010">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2010">Pattern</span></span>

<span data-ttu-id="78146-2011">12 位</span><span class="sxs-lookup"><span data-stu-id="78146-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2012">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2012">Checksum</span></span>

<span data-ttu-id="78146-2013">否</span><span class="sxs-lookup"><span data-stu-id="78146-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2014">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2014">Definition</span></span>

<span data-ttu-id="78146-2015">如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2016">正则表达式 Regex_france_cni 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2017">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2017">Keywords</span></span>

<span data-ttu-id="78146-2018">無</span><span class="sxs-lookup"><span data-stu-id="78146-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="78146-2019">法國護照號碼</span><span class="sxs-lookup"><span data-stu-id="78146-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2020">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2020">Format</span></span>

<span data-ttu-id="78146-2021">九位数字和字母</span><span class="sxs-lookup"><span data-stu-id="78146-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2022">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2022">Pattern</span></span>

<span data-ttu-id="78146-2023">九位数字和字母：</span><span class="sxs-lookup"><span data-stu-id="78146-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="78146-2024">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2024">Two digits</span></span> 
- <span data-ttu-id="78146-2025">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="78146-2026">五位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2027">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2027">Checksum</span></span>

<span data-ttu-id="78146-2028">否</span><span class="sxs-lookup"><span data-stu-id="78146-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2029">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2029">Definition</span></span>

<span data-ttu-id="78146-2030">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2031">函数 Func_fr_passport 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2032">找到关键字_Passport中一个关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2033">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="78146-2034">关键词_护照</span><span class="sxs-lookup"><span data-stu-id="78146-2034">Keyword_passport</span></span>

- <span data-ttu-id="78146-2035">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-2035">Passport Number</span></span>
- <span data-ttu-id="78146-2036">护照号</span><span class="sxs-lookup"><span data-stu-id="78146-2036">Passport No</span></span>
- <span data-ttu-id="78146-2037">护照#</span><span class="sxs-lookup"><span data-stu-id="78146-2037">Passport #</span></span>
- <span data-ttu-id="78146-2038">护照#</span><span class="sxs-lookup"><span data-stu-id="78146-2038">Passport#</span></span>
- <span data-ttu-id="78146-2039">护照ID</span><span class="sxs-lookup"><span data-stu-id="78146-2039">PassportID</span></span>
- <span data-ttu-id="78146-2040">护照诺</span><span class="sxs-lookup"><span data-stu-id="78146-2040">Passportno</span></span>
- <span data-ttu-id="78146-2041">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-2041">passportnumber</span></span>
- <span data-ttu-id="78146-2042">·</span><span class="sxs-lookup"><span data-stu-id="78146-2042">パスポート</span></span>
- <span data-ttu-id="78146-2043">·\\\\\\\\\\\\\\\\\\\\\\</span><span class="sxs-lookup"><span data-stu-id="78146-2043">パスポート番号</span></span>
- <span data-ttu-id="78146-2044">\* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="78146-2044">パスポートのNum</span></span>
- <span data-ttu-id="78146-2045">[ ]</span><span class="sxs-lookup"><span data-stu-id="78146-2045">パスポート ＃</span></span> 
- <span data-ttu-id="78146-2046">努梅罗·德·德费波特</span><span class="sxs-lookup"><span data-stu-id="78146-2046">Numéro de passeport</span></span>
- <span data-ttu-id="78146-2047">路路港 n |</span><span class="sxs-lookup"><span data-stu-id="78146-2047">Passeport n °</span></span>
- <span data-ttu-id="78146-2048">路路港非</span><span class="sxs-lookup"><span data-stu-id="78146-2048">Passeport Non</span></span>
- <span data-ttu-id="78146-2049">帕塞波特#</span><span class="sxs-lookup"><span data-stu-id="78146-2049">Passeport #</span></span>
- <span data-ttu-id="78146-2050">帕塞波特#</span><span class="sxs-lookup"><span data-stu-id="78146-2050">Passeport#</span></span>
- <span data-ttu-id="78146-2051">帕塞波特农</span><span class="sxs-lookup"><span data-stu-id="78146-2051">PasseportNon</span></span>
- <span data-ttu-id="78146-2052">帕塞波特 |</span><span class="sxs-lookup"><span data-stu-id="78146-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="78146-2053">法國社會安全號碼 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="78146-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="78146-2054">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2054">Format</span></span>

<span data-ttu-id="78146-2055">15 位</span><span class="sxs-lookup"><span data-stu-id="78146-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2056">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2056">Pattern</span></span>

<span data-ttu-id="78146-2057">必须匹配两种模式之一：</span><span class="sxs-lookup"><span data-stu-id="78146-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="78146-2058">13 位数字后跟空格后跟两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="78146-2059">或</span><span class="sxs-lookup"><span data-stu-id="78146-2059">or</span></span>
- <span data-ttu-id="78146-2060">15 个连续数字</span><span class="sxs-lookup"><span data-stu-id="78146-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2061">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2061">Checksum</span></span>

<span data-ttu-id="78146-2062">是</span><span class="sxs-lookup"><span data-stu-id="78146-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2063">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2063">Definition</span></span>

<span data-ttu-id="78146-2064">如果接近 300 个字符，DLP 策略 95% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2065">函数 Func_french_insee 或 Func_fr_insee 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2066">找到来自关键字_fr_insee的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="78146-2067">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2067">The checksum passes.</span></span>

<span data-ttu-id="78146-2068">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2069">函数 Func_french_insee 或 Func_fr_insee 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2070">找不到来自关键字_fr_insee 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="78146-2071">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2072">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="78146-2073">关键字_fr_insee</span><span class="sxs-lookup"><span data-stu-id="78146-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="78146-2074">因西</span><span class="sxs-lookup"><span data-stu-id="78146-2074">insee</span></span>
- <span data-ttu-id="78146-2075">安全\* 社会</span><span class="sxs-lookup"><span data-stu-id="78146-2075">securité sociale</span></span>
- <span data-ttu-id="78146-2076">安全社会</span><span class="sxs-lookup"><span data-stu-id="78146-2076">securite sociale</span></span>
- <span data-ttu-id="78146-2077">国家 ID</span><span class="sxs-lookup"><span data-stu-id="78146-2077">national id</span></span>
- <span data-ttu-id="78146-2078">国家标识</span><span class="sxs-lookup"><span data-stu-id="78146-2078">national identification</span></span>
- <span data-ttu-id="78146-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="78146-2079">numéro d'identité</span></span>
- <span data-ttu-id="78146-2080">无 d'identit_</span><span class="sxs-lookup"><span data-stu-id="78146-2080">no d'identité</span></span>
- <span data-ttu-id="78146-2081">不。</span><span class="sxs-lookup"><span data-stu-id="78146-2081">no.</span></span> <span data-ttu-id="78146-2082">d'identit®</span><span class="sxs-lookup"><span data-stu-id="78146-2082">d'identité</span></span>
- <span data-ttu-id="78146-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="78146-2083">numero d'identite</span></span>
- <span data-ttu-id="78146-2084">无 d'identite</span><span class="sxs-lookup"><span data-stu-id="78146-2084">no d'identite</span></span>
- <span data-ttu-id="78146-2085">不。</span><span class="sxs-lookup"><span data-stu-id="78146-2085">no.</span></span> <span data-ttu-id="78146-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="78146-2086">d'identite</span></span>
- <span data-ttu-id="78146-2087">社会安全号码</span><span class="sxs-lookup"><span data-stu-id="78146-2087">social security number</span></span>
- <span data-ttu-id="78146-2088">社会保障代码</span><span class="sxs-lookup"><span data-stu-id="78146-2088">social security code</span></span>
- <span data-ttu-id="78146-2089">社会保险号</span><span class="sxs-lookup"><span data-stu-id="78146-2089">social insurance number</span></span>
- <span data-ttu-id="78146-2090">国家识别</span><span class="sxs-lookup"><span data-stu-id="78146-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="78146-2091">d'identité 国家</span><span class="sxs-lookup"><span data-stu-id="78146-2091">d'identité nationale</span></span>
- <span data-ttu-id="78146-2092">社会社会</span><span class="sxs-lookup"><span data-stu-id="78146-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="78146-2093">社会法典</span><span class="sxs-lookup"><span data-stu-id="78146-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="78146-2094">numéro d'保证社会</span><span class="sxs-lookup"><span data-stu-id="78146-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="78146-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="78146-2095">numéro de sécu</span></span>
- <span data-ttu-id="78146-2096">代码 s_cu</span><span class="sxs-lookup"><span data-stu-id="78146-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="78146-2097">德国驾照号码</span><span class="sxs-lookup"><span data-stu-id="78146-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2098">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2098">Format</span></span>

<span data-ttu-id="78146-2099">11 位数字和字母的组合</span><span class="sxs-lookup"><span data-stu-id="78146-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2100">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2100">Pattern</span></span>

<span data-ttu-id="78146-2101">11 位数字和字母（不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="78146-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="78146-2102">数字或字母</span><span class="sxs-lookup"><span data-stu-id="78146-2102">A digit or letter</span></span> 
- <span data-ttu-id="78146-2103">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2103">Two digits</span></span> 
- <span data-ttu-id="78146-2104">六位数字或字母</span><span class="sxs-lookup"><span data-stu-id="78146-2104">Six digits or letters</span></span> 
- <span data-ttu-id="78146-2105">数字</span><span class="sxs-lookup"><span data-stu-id="78146-2105">A digit</span></span> 
- <span data-ttu-id="78146-2106">数字或字母</span><span class="sxs-lookup"><span data-stu-id="78146-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2107">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2107">Checksum</span></span>

<span data-ttu-id="78146-2108">是</span><span class="sxs-lookup"><span data-stu-id="78146-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2109">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2109">Definition</span></span>

<span data-ttu-id="78146-2110">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2111">函数 Func_german_驱动程序_许可证查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2112">以下至少一项是正确的：</span><span class="sxs-lookup"><span data-stu-id="78146-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="78146-2113">找到关键字_german_驱动程序_许可证_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="78146-2114">找到关键字_german_驱动程序_许可证_协作的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="78146-2115">找到关键字_german_驱动程序_许可证的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="78146-2116">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2117">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="78146-2118">关键词_德国_驱动程序_许可证_编号</span><span class="sxs-lookup"><span data-stu-id="78146-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="78146-2119">费勒斯切因</span><span class="sxs-lookup"><span data-stu-id="78146-2119">Führerschein</span></span>
- <span data-ttu-id="78146-2120">富赫勒谢因</span><span class="sxs-lookup"><span data-stu-id="78146-2120">Fuhrerschein</span></span>
- <span data-ttu-id="78146-2121">富埃勒谢因</span><span class="sxs-lookup"><span data-stu-id="78146-2121">Fuehrerschein</span></span>
- <span data-ttu-id="78146-2122">费勒斯切因努默</span><span class="sxs-lookup"><span data-stu-id="78146-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="78146-2123">富勒舍因努默</span><span class="sxs-lookup"><span data-stu-id="78146-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="78146-2124">富埃勒什金努默</span><span class="sxs-lookup"><span data-stu-id="78146-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="78146-2125">费勒斯切因-</span><span class="sxs-lookup"><span data-stu-id="78146-2125">Führerschein-</span></span> 
- <span data-ttu-id="78146-2126">富勒尔切因-</span><span class="sxs-lookup"><span data-stu-id="78146-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="78146-2127">富埃勒谢因-</span><span class="sxs-lookup"><span data-stu-id="78146-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="78146-2128">费勒斯切因努默纳</span><span class="sxs-lookup"><span data-stu-id="78146-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="78146-2129">富勒什金努默纳</span><span class="sxs-lookup"><span data-stu-id="78146-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="78146-2130">富埃勒什金努默纳</span><span class="sxs-lookup"><span data-stu-id="78146-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="78146-2131">费勒斯切因努默·克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="78146-2132">富勒什金努默·克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="78146-2133">富埃勒什金努默·克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="78146-2134">费勒斯切因- Nr</span><span class="sxs-lookup"><span data-stu-id="78146-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="78146-2135">富勒尔切因- Nr</span><span class="sxs-lookup"><span data-stu-id="78146-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="78146-2136">富埃勒谢因- Nr</span><span class="sxs-lookup"><span data-stu-id="78146-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="78146-2137">费勒斯切因-克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="78146-2138">富勒斯切因-克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="78146-2139">富埃勒谢因-克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="78146-2140">费勒斯切因努默纳</span><span class="sxs-lookup"><span data-stu-id="78146-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="78146-2141">富勒什金努默纳</span><span class="sxs-lookup"><span data-stu-id="78146-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="78146-2142">富埃勒什金努默纳</span><span class="sxs-lookup"><span data-stu-id="78146-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="78146-2143">费勒斯切因努默·克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="78146-2144">富勒什金努默·克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="78146-2145">富埃勒什金努默·克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="78146-2146">费勒斯切因- Nr</span><span class="sxs-lookup"><span data-stu-id="78146-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="78146-2147">富勒尔切因- Nr</span><span class="sxs-lookup"><span data-stu-id="78146-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="78146-2148">富埃勒谢因- Nr</span><span class="sxs-lookup"><span data-stu-id="78146-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="78146-2149">费勒斯切因-克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="78146-2150">富勒斯切因-克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="78146-2151">富埃勒谢因-克拉塞</span><span class="sxs-lookup"><span data-stu-id="78146-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="78146-2152">Dl</span><span class="sxs-lookup"><span data-stu-id="78146-2152">DL</span></span> 
- <span data-ttu-id="78146-2153">Dls</span><span class="sxs-lookup"><span data-stu-id="78146-2153">DLS</span></span>
- <span data-ttu-id="78146-2154">德里夫·利奇</span><span class="sxs-lookup"><span data-stu-id="78146-2154">Driv Lic</span></span> 
- <span data-ttu-id="78146-2155">德里夫·利森</span><span class="sxs-lookup"><span data-stu-id="78146-2155">Driv Licen</span></span> 
- <span data-ttu-id="78146-2156">Driv 许可证</span><span class="sxs-lookup"><span data-stu-id="78146-2156">Driv License</span></span>
- <span data-ttu-id="78146-2157">Driv 许可证</span><span class="sxs-lookup"><span data-stu-id="78146-2157">Driv Licenses</span></span> 
- <span data-ttu-id="78146-2158">Driv 许可证</span><span class="sxs-lookup"><span data-stu-id="78146-2158">Driv Licence</span></span> 
- <span data-ttu-id="78146-2159">Driv 许可证</span><span class="sxs-lookup"><span data-stu-id="78146-2159">Driv Licences</span></span> 
- <span data-ttu-id="78146-2160">德里夫·利奇</span><span class="sxs-lookup"><span data-stu-id="78146-2160">Driv Lic</span></span> 
- <span data-ttu-id="78146-2161">司机利森</span><span class="sxs-lookup"><span data-stu-id="78146-2161">Driver Licen</span></span> 
- <span data-ttu-id="78146-2162">驾照</span><span class="sxs-lookup"><span data-stu-id="78146-2162">Driver License</span></span> 
- <span data-ttu-id="78146-2163">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2163">Driver Licenses</span></span> 
- <span data-ttu-id="78146-2164">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2164">Driver Licence</span></span> 
- <span data-ttu-id="78146-2165">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2165">Driver Licences</span></span> 
- <span data-ttu-id="78146-2166">司机许可证</span><span class="sxs-lookup"><span data-stu-id="78146-2166">Drivers Lic</span></span> 
- <span data-ttu-id="78146-2167">司机利森</span><span class="sxs-lookup"><span data-stu-id="78146-2167">Drivers Licen</span></span> 
- <span data-ttu-id="78146-2168">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2168">Drivers License</span></span> 
- <span data-ttu-id="78146-2169">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="78146-2170">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2170">Drivers Licence</span></span> 
- <span data-ttu-id="78146-2171">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2171">Drivers Licences</span></span> 
- <span data-ttu-id="78146-2172">驾驶员的许可证</span><span class="sxs-lookup"><span data-stu-id="78146-2172">Driver's Lic</span></span> 
- <span data-ttu-id="78146-2173">司机的利森</span><span class="sxs-lookup"><span data-stu-id="78146-2173">Driver's Licen</span></span> 
- <span data-ttu-id="78146-2174">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2174">Driver's License</span></span> 
- <span data-ttu-id="78146-2175">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="78146-2176">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2176">Driver's Licence</span></span> 
- <span data-ttu-id="78146-2177">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2177">Driver's Licences</span></span> 
- <span data-ttu-id="78146-2178">驾驶许可证</span><span class="sxs-lookup"><span data-stu-id="78146-2178">Driving Lic</span></span> 
- <span data-ttu-id="78146-2179">驾驶利森</span><span class="sxs-lookup"><span data-stu-id="78146-2179">Driving Licen</span></span> 
- <span data-ttu-id="78146-2180">驾照</span><span class="sxs-lookup"><span data-stu-id="78146-2180">Driving License</span></span> 
- <span data-ttu-id="78146-2181">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2181">Driving Licenses</span></span> 
- <span data-ttu-id="78146-2182">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2182">Driving Licence</span></span> 
- <span data-ttu-id="78146-2183">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="78146-2184">关键词_德国_驱动程序_许可证_协作</span><span class="sxs-lookup"><span data-stu-id="78146-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="78146-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="78146-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="78146-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="78146-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="78146-2187">恩-富赫勒谢因</span><span class="sxs-lookup"><span data-stu-id="78146-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="78146-2188">无费勒斯切因</span><span class="sxs-lookup"><span data-stu-id="78146-2188">No-Führerschein</span></span> 
- <span data-ttu-id="78146-2189">无富勒舍因</span><span class="sxs-lookup"><span data-stu-id="78146-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="78146-2190">无富赫勒谢因</span><span class="sxs-lookup"><span data-stu-id="78146-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="78146-2191">N-费勒斯川</span><span class="sxs-lookup"><span data-stu-id="78146-2191">N-Führerschein</span></span> 
- <span data-ttu-id="78146-2192">N-富勒舍因</span><span class="sxs-lookup"><span data-stu-id="78146-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="78146-2193">N-富埃勒谢因</span><span class="sxs-lookup"><span data-stu-id="78146-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="78146-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="78146-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="78146-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="78146-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="78146-2196">恩-富赫勒谢因</span><span class="sxs-lookup"><span data-stu-id="78146-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="78146-2197">无费勒斯切因</span><span class="sxs-lookup"><span data-stu-id="78146-2197">No-Führerschein</span></span> 
- <span data-ttu-id="78146-2198">无富勒舍因</span><span class="sxs-lookup"><span data-stu-id="78146-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="78146-2199">无富赫勒谢因</span><span class="sxs-lookup"><span data-stu-id="78146-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="78146-2200">N-费勒斯川</span><span class="sxs-lookup"><span data-stu-id="78146-2200">N-Führerschein</span></span> 
- <span data-ttu-id="78146-2201">N-富勒舍因</span><span class="sxs-lookup"><span data-stu-id="78146-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="78146-2202">N-富埃勒谢因</span><span class="sxs-lookup"><span data-stu-id="78146-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="78146-2203">关键词_德国_驱动程序_许可证</span><span class="sxs-lookup"><span data-stu-id="78146-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="78146-2204">澳斯特伦达图姆</span><span class="sxs-lookup"><span data-stu-id="78146-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="78146-2205">欧斯泰隆排序</span><span class="sxs-lookup"><span data-stu-id="78146-2205">ausstellungsort</span></span>
- <span data-ttu-id="78146-2206">奥斯特伦德·贝赫德</span><span class="sxs-lookup"><span data-stu-id="78146-2206">ausstellende behöde</span></span>
- <span data-ttu-id="78146-2207">欧斯泰伦德·比霍德</span><span class="sxs-lookup"><span data-stu-id="78146-2207">ausstellende behorde</span></span>
- <span data-ttu-id="78146-2208">欧斯泰伦德·贝霍德</span><span class="sxs-lookup"><span data-stu-id="78146-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="78146-2209">德國護照號碼</span><span class="sxs-lookup"><span data-stu-id="78146-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2210">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2210">Format</span></span>

<span data-ttu-id="78146-2211">10 位数字或字母</span><span class="sxs-lookup"><span data-stu-id="78146-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2212">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2212">Pattern</span></span>

<span data-ttu-id="78146-2213">模式必须包括以下所有内容：</span><span class="sxs-lookup"><span data-stu-id="78146-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="78146-2214">第一个字符是此集的数字或字母（C、F、G、H、J、K）</span><span class="sxs-lookup"><span data-stu-id="78146-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="78146-2215">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2215">Three digits</span></span> 
- <span data-ttu-id="78146-2216">此集的五位数字或字母（C、-H、J-N、P、R、T、V-Z）</span><span class="sxs-lookup"><span data-stu-id="78146-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="78146-2217">数字</span><span class="sxs-lookup"><span data-stu-id="78146-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2218">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2218">Checksum</span></span>

<span data-ttu-id="78146-2219">是</span><span class="sxs-lookup"><span data-stu-id="78146-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2220">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2220">Definition</span></span>

<span data-ttu-id="78146-2221">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2222">函数 Func_german_Passport 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2223">找到五个关键字列表中任何一个的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="78146-2224">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2224">The checksum passes.</span></span>

<span data-ttu-id="78146-2225">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2226">函数 Func_german_Passport_数据查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2227">找到五个关键字列表中任何一个的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="78146-2228">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2229">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="78146-2230">关键词_德语_护照</span><span class="sxs-lookup"><span data-stu-id="78146-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="78146-2231">雷塞帕斯</span><span class="sxs-lookup"><span data-stu-id="78146-2231">reisepass</span></span>
- <span data-ttu-id="78146-2232">雷塞帕塞</span><span class="sxs-lookup"><span data-stu-id="78146-2232">reisepasse</span></span>
- <span data-ttu-id="78146-2233">雷塞帕塞努默</span><span class="sxs-lookup"><span data-stu-id="78146-2233">reisepassnummer</span></span>
- <span data-ttu-id="78146-2234">护照</span><span class="sxs-lookup"><span data-stu-id="78146-2234">passport</span></span>
- <span data-ttu-id="78146-2235">护照</span><span class="sxs-lookup"><span data-stu-id="78146-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="78146-2236">关键词_德语_护照_协作</span><span class="sxs-lookup"><span data-stu-id="78146-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="78146-2237">格布尔茨达图姆</span><span class="sxs-lookup"><span data-stu-id="78146-2237">geburtsdatum</span></span>
- <span data-ttu-id="78146-2238">澳斯特伦达图姆</span><span class="sxs-lookup"><span data-stu-id="78146-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="78146-2239">欧斯泰隆排序</span><span class="sxs-lookup"><span data-stu-id="78146-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="78146-2240">关键词_德语_护照_号码</span><span class="sxs-lookup"><span data-stu-id="78146-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="78146-2241">无雷塞帕斯 Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="78146-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="78146-2242">关键词_德语_护照1</span><span class="sxs-lookup"><span data-stu-id="78146-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="78146-2243">莱塞帕斯-Nr</span><span class="sxs-lookup"><span data-stu-id="78146-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="78146-2244">关键词_德语_护照2</span><span class="sxs-lookup"><span data-stu-id="78146-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="78146-2245">比特特</span><span class="sxs-lookup"><span data-stu-id="78146-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="78146-2246">德國身分證號碼</span><span class="sxs-lookup"><span data-stu-id="78146-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2247">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2247">Format</span></span>

<span data-ttu-id="78146-2248">自 2010 年 11 月 1 日起：9 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="78146-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="78146-2249">1987年4月1日至2010年10月31日：10位</span><span class="sxs-lookup"><span data-stu-id="78146-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2250">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2250">Pattern</span></span>

<span data-ttu-id="78146-2251">自2010年11月1日起：</span><span class="sxs-lookup"><span data-stu-id="78146-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="78146-2252">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="78146-2253">八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2253">Eight digits</span></span>

<span data-ttu-id="78146-2254">1987年4月1日至2010年10月31日：</span><span class="sxs-lookup"><span data-stu-id="78146-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="78146-2255">10 位</span><span class="sxs-lookup"><span data-stu-id="78146-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2256">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2256">Checksum</span></span>

<span data-ttu-id="78146-2257">否</span><span class="sxs-lookup"><span data-stu-id="78146-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2258">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2258">Definition</span></span>

<span data-ttu-id="78146-2259">如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2260">正则表达式 Regex_germany_id_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2261">找到关键字_germany_id_card 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2262">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="78146-2263">关键字_德杰德_id_卡</span><span class="sxs-lookup"><span data-stu-id="78146-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="78146-2264">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2264">Identity Card</span></span>
- <span data-ttu-id="78146-2265">ID</span><span class="sxs-lookup"><span data-stu-id="78146-2265">ID</span></span>
- <span data-ttu-id="78146-2266">识别</span><span class="sxs-lookup"><span data-stu-id="78146-2266">Identification</span></span>
- <span data-ttu-id="78146-2267">个人</span><span class="sxs-lookup"><span data-stu-id="78146-2267">Personalausweis</span></span>
- <span data-ttu-id="78146-2268">身份识别者</span><span class="sxs-lookup"><span data-stu-id="78146-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="78146-2269">澳斯威</span><span class="sxs-lookup"><span data-stu-id="78146-2269">Ausweis</span></span>
- <span data-ttu-id="78146-2270">标识</span><span class="sxs-lookup"><span data-stu-id="78146-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="78146-2271">希臘國民身分證</span><span class="sxs-lookup"><span data-stu-id="78146-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="78146-2272">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2272">Format</span></span>

<span data-ttu-id="78146-2273">7-8 个字母和数字的组合加上破折号</span><span class="sxs-lookup"><span data-stu-id="78146-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2274">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2274">Pattern</span></span>

<span data-ttu-id="78146-2275">七个字母和数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="78146-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="78146-2276">一个字母（希腊字母的任何字母）</span><span class="sxs-lookup"><span data-stu-id="78146-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="78146-2277">破折号</span><span class="sxs-lookup"><span data-stu-id="78146-2277">A dash</span></span> 
- <span data-ttu-id="78146-2278">六位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2278">Six digits</span></span>

<span data-ttu-id="78146-2279">八个字母和数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="78146-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="78146-2280">两个字母的大写字符出现在希腊字母和拉丁字母 （ABEZHIKMNOPTYX）</span><span class="sxs-lookup"><span data-stu-id="78146-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="78146-2281">破折号</span><span class="sxs-lookup"><span data-stu-id="78146-2281">A dash</span></span> 
- <span data-ttu-id="78146-2282">六位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2283">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2283">Checksum</span></span>

<span data-ttu-id="78146-2284">否</span><span class="sxs-lookup"><span data-stu-id="78146-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2285">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2285">Definition</span></span>

<span data-ttu-id="78146-2286">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2287">正则表达式 Regex_希腊_id_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2288">找到关键字_希腊_id_card 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2289">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="78146-2290">关键词_希腊_id_卡</span><span class="sxs-lookup"><span data-stu-id="78146-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="78146-2291">希腊身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2291">Greek identity Card</span></span>
- <span data-ttu-id="78146-2292">陶托蒂塔</span><span class="sxs-lookup"><span data-stu-id="78146-2292">Tautotita</span></span>
- <span data-ttu-id="78146-2293">[][][][][</span><span class="sxs-lookup"><span data-stu-id="78146-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="78146-2294">[ ]</span><span class="sxs-lookup"><span data-stu-id="78146-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="78146-2295">香港身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2296">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2296">Format</span></span>

<span data-ttu-id="78146-2297">8-9 个字母和数字的组合加上围绕最终字符的可选括号</span><span class="sxs-lookup"><span data-stu-id="78146-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2298">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2298">Pattern</span></span>

<span data-ttu-id="78146-2299">8-9 个字母的组合：</span><span class="sxs-lookup"><span data-stu-id="78146-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="78146-2300">1-2 个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="78146-2301">六位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2301">Six digits</span></span> 
- <span data-ttu-id="78146-2302">最后一个字符（任何数字或字母 A），这是校验数字，可选括在括号中。</span><span class="sxs-lookup"><span data-stu-id="78146-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2303">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2303">Checksum</span></span>

<span data-ttu-id="78146-2304">是</span><span class="sxs-lookup"><span data-stu-id="78146-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2305">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2305">Definition</span></span>

<span data-ttu-id="78146-2306">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2307">函数 Func_kong_kong_id_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2308">找到关键字_kong_kong_id_card 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="78146-2309">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2309">The checksum passes.</span></span>

<span data-ttu-id="78146-2310">如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2311">函数 Func_kong_kong_id_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2312">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2313">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="78146-2314">关键词_洪_孔_id_卡</span><span class="sxs-lookup"><span data-stu-id="78146-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="78146-2315">香港身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2315">hong kong identity card</span></span>
- <span data-ttu-id="78146-2316">香港国际数据中心</span><span class="sxs-lookup"><span data-stu-id="78146-2316">HKIDC</span></span>
- <span data-ttu-id="78146-2317">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2317">id card</span></span>
- <span data-ttu-id="78146-2318">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2318">identity card</span></span>
- <span data-ttu-id="78146-2319">香港身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2319">hk identity card</span></span>
- <span data-ttu-id="78146-2320">香港 ID</span><span class="sxs-lookup"><span data-stu-id="78146-2320">hong kong id</span></span>
- <span data-ttu-id="78146-2321">·</span><span class="sxs-lookup"><span data-stu-id="78146-2321">香港身份證</span></span>
- <span data-ttu-id="78146-2322">·</span><span class="sxs-lookup"><span data-stu-id="78146-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="78146-2323">·</span><span class="sxs-lookup"><span data-stu-id="78146-2323">身份證</span></span>
- <span data-ttu-id="78146-2324">·000年</span><span class="sxs-lookup"><span data-stu-id="78146-2324">身份証</span></span>
- <span data-ttu-id="78146-2325">·</span><span class="sxs-lookup"><span data-stu-id="78146-2325">身分證</span></span>
- <span data-ttu-id="78146-2326">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2326">身分証</span></span>
- <span data-ttu-id="78146-2327">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2327">香港身份証</span></span>
- <span data-ttu-id="78146-2328">·</span><span class="sxs-lookup"><span data-stu-id="78146-2328">香港身分證</span></span>
- <span data-ttu-id="78146-2329">\*</span><span class="sxs-lookup"><span data-stu-id="78146-2329">香港身分証</span></span>
- <span data-ttu-id="78146-2330">·</span><span class="sxs-lookup"><span data-stu-id="78146-2330">香港身份證</span></span>
- <span data-ttu-id="78146-2331">·</span><span class="sxs-lookup"><span data-stu-id="78146-2331">香港居民身份證</span></span>
- <span data-ttu-id="78146-2332">·00.</span><span class="sxs-lookup"><span data-stu-id="78146-2332">香港居民身份証</span></span>
- <span data-ttu-id="78146-2333">·</span><span class="sxs-lookup"><span data-stu-id="78146-2333">香港居民身分證</span></span>
- <span data-ttu-id="78146-2334">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2334">香港居民身分証</span></span>
- <span data-ttu-id="78146-2335">·</span><span class="sxs-lookup"><span data-stu-id="78146-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="78146-2336">·</span><span class="sxs-lookup"><span data-stu-id="78146-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="78146-2337">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="78146-2338">·</span><span class="sxs-lookup"><span data-stu-id="78146-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="78146-2339">·</span><span class="sxs-lookup"><span data-stu-id="78146-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="78146-2340">·</span><span class="sxs-lookup"><span data-stu-id="78146-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="78146-2341">·</span><span class="sxs-lookup"><span data-stu-id="78146-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="78146-2342">·[</span><span class="sxs-lookup"><span data-stu-id="78146-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="78146-2343">·[</span><span class="sxs-lookup"><span data-stu-id="78146-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="78146-2344">·[</span><span class="sxs-lookup"><span data-stu-id="78146-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="78146-2345">·[</span><span class="sxs-lookup"><span data-stu-id="78146-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="78146-2346">·0·11</span><span class="sxs-lookup"><span data-stu-id="78146-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="78146-2347">·[</span><span class="sxs-lookup"><span data-stu-id="78146-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="78146-2348">[了）</span><span class="sxs-lookup"><span data-stu-id="78146-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="78146-2349">·[</span><span class="sxs-lookup"><span data-stu-id="78146-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="78146-2350">·000年</span><span class="sxs-lookup"><span data-stu-id="78146-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="78146-2351">印度永久帐号 （PAN）</span><span class="sxs-lookup"><span data-stu-id="78146-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="78146-2352">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2352">Format</span></span>

<span data-ttu-id="78146-2353">10 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="78146-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2354">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2354">Pattern</span></span>

<span data-ttu-id="78146-2355">10 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="78146-2355">10 letters or digits:</span></span>
- <span data-ttu-id="78146-2356">五个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="78146-2357">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2357">Four digits</span></span> 
- <span data-ttu-id="78146-2358">字母检查数字的字母</span><span class="sxs-lookup"><span data-stu-id="78146-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2359">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2359">Checksum</span></span>

<span data-ttu-id="78146-2360">是</span><span class="sxs-lookup"><span data-stu-id="78146-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2361">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2361">Definition</span></span>

<span data-ttu-id="78146-2362">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2363">正则表达式 Regex_india_永久_帐户_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2364">找到关键字_印度_永久_帐户_编号中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="78146-2365">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2366">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="78146-2367">关键词_印度_永久_帐户_编号</span><span class="sxs-lookup"><span data-stu-id="78146-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="78146-2368">永久帐号</span><span class="sxs-lookup"><span data-stu-id="78146-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="78146-2369">泛</span><span class="sxs-lookup"><span data-stu-id="78146-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="78146-2370">印度唯一识别（阿达哈尔）编号</span><span class="sxs-lookup"><span data-stu-id="78146-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2371">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2371">Format</span></span>

<span data-ttu-id="78146-2372">包含可选空格或破折号的 12 位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2373">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2373">Pattern</span></span>

<span data-ttu-id="78146-2374">12 位：</span><span class="sxs-lookup"><span data-stu-id="78146-2374">12 digits:</span></span>
- <span data-ttu-id="78146-2375">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2375">Four digits</span></span> 
- <span data-ttu-id="78146-2376">可选空格或破折号</span><span class="sxs-lookup"><span data-stu-id="78146-2376">An optional space or dash</span></span> 
- <span data-ttu-id="78146-2377">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2377">Four digits</span></span> 
- <span data-ttu-id="78146-2378">可选空格或破折号</span><span class="sxs-lookup"><span data-stu-id="78146-2378">An optional space or dash</span></span> 
- <span data-ttu-id="78146-2379">最后一个数字，即校验数字</span><span class="sxs-lookup"><span data-stu-id="78146-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2380">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2380">Checksum</span></span>

<span data-ttu-id="78146-2381">是</span><span class="sxs-lookup"><span data-stu-id="78146-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2382">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2382">Definition</span></span>

<span data-ttu-id="78146-2383">如果 DLP 策略在 300 个字符的接近范围内检测到这种类型的敏感信息，则 DLP 策略有 85% 的置相信度：如果函数 Func_india_aadhaar 找到与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="78146-2384">找到关键字_印度_阿达哈尔中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="78146-2385">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2385">The checksum passes.</span></span>
<span data-ttu-id="78146-2386">如果 DLP 策略在 300 个字符的接近范围内检测到这种类型的敏感信息，则 DLP 策略有 75% 的置相信度：如果函数 Func_india_aadhaar 找到与模式匹配的内容， 则该策略已检测到此类敏感信息。</span><span class="sxs-lookup"><span data-stu-id="78146-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="78146-2387">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2387">The checksum passes.</span></span>
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
### <a name="keywords"></a><span data-ttu-id="78146-2388">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="78146-2389">关键词_印度_阿达达尔</span><span class="sxs-lookup"><span data-stu-id="78146-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="78146-2390">阿达尔</span><span class="sxs-lookup"><span data-stu-id="78146-2390">Aadhar</span></span>
- <span data-ttu-id="78146-2391">阿达尔</span><span class="sxs-lookup"><span data-stu-id="78146-2391">Aadhaar</span></span>
- <span data-ttu-id="78146-2392">Uid</span><span class="sxs-lookup"><span data-stu-id="78146-2392">UID</span></span>
- <span data-ttu-id="78146-2393">·但</span><span class="sxs-lookup"><span data-stu-id="78146-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="78146-2394">印度尼西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2395">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2395">Format</span></span>

<span data-ttu-id="78146-2396">包含可选周期的 16 位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2397">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2397">Pattern</span></span>

<span data-ttu-id="78146-2398">16 位：</span><span class="sxs-lookup"><span data-stu-id="78146-2398">16 digits:</span></span>
- <span data-ttu-id="78146-2399">两位省代码</span><span class="sxs-lookup"><span data-stu-id="78146-2399">Two-digit province code</span></span> 
- <span data-ttu-id="78146-2400">期间（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-2400">A period (optional)</span></span> 
- <span data-ttu-id="78146-2401">两位数校验或城市代码</span><span class="sxs-lookup"><span data-stu-id="78146-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="78146-2402">两位数分区代码</span><span class="sxs-lookup"><span data-stu-id="78146-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="78146-2403">期间（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-2403">A period (optional)</span></span> 
- <span data-ttu-id="78146-2404">DDMMYY 格式中的六位数字，即出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="78146-2405">期间（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-2405">A period (optional)</span></span> 
- <span data-ttu-id="78146-2406">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2407">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2407">Checksum</span></span>

<span data-ttu-id="78146-2408">否</span><span class="sxs-lookup"><span data-stu-id="78146-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2409">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2409">Definition</span></span>

<span data-ttu-id="78146-2410">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2411">正则表达式 Regex_indonesia_id_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2412">找到关键字_indonesia_id_card 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="78146-2413">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2414">正则表达式 Regex_indonesia_id_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2415">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="78146-2416">关键字_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="78146-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="78146-2417">Ktp</span><span class="sxs-lookup"><span data-stu-id="78146-2417">KTP</span></span>
- <span data-ttu-id="78146-2418">卡尔图·丹达·彭杜杜克</span><span class="sxs-lookup"><span data-stu-id="78146-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="78146-2419">诺莫尔·因杜克·凯彭杜坎</span><span class="sxs-lookup"><span data-stu-id="78146-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="78146-2420">國際銀行帳號 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="78146-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="78146-2421">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2421">Format</span></span>

<span data-ttu-id="78146-2422">国家/地区代码（两个字母）加上支票数字（两位数字）加上 bban 数字（最多 30 个字符）</span><span class="sxs-lookup"><span data-stu-id="78146-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2423">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2423">Pattern</span></span>

<span data-ttu-id="78146-2424">模式必须包括以下所有内容：</span><span class="sxs-lookup"><span data-stu-id="78146-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="78146-2425">双字母国家代码</span><span class="sxs-lookup"><span data-stu-id="78146-2425">Two-letter country code</span></span>
- <span data-ttu-id="78146-2426">两个检查数字（后跟可选空格）</span><span class="sxs-lookup"><span data-stu-id="78146-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="78146-2427">1-7组四个字母或数字（可以用空格分隔）</span><span class="sxs-lookup"><span data-stu-id="78146-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="78146-2428">1-3 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="78146-2428">1-3 letters or digits</span></span>

<span data-ttu-id="78146-2429">每个国家/地区的格式略有不同。</span><span class="sxs-lookup"><span data-stu-id="78146-2429">The format for each country is slightly different.</span></span> <span data-ttu-id="78146-2430">IBAN 敏感信息类型涵盖以下 60 个国家/地区：</span><span class="sxs-lookup"><span data-stu-id="78146-2430">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="78146-2431">广告， ae， al， 在， 在， az， ba， be， b， bh， ch， c， cy， cz， de， dk， 做， ee， es， fi， fo， fr， gb， ge， gi， g， gr， hr， hu， i， il， 是， 它， kw， kz， lb， li， lt， lu， lv， mc， md， me， m， m， m， m， m， m，， nl， 不， pl， pt， ro， rs， sa， se， si， sk， sm， tn， tr， vg</span><span class="sxs-lookup"><span data-stu-id="78146-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2432">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2432">Checksum</span></span>

<span data-ttu-id="78146-2433">是</span><span class="sxs-lookup"><span data-stu-id="78146-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2434">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2434">Definition</span></span>

<span data-ttu-id="78146-2435">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2436">函数 Func_iban 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2437">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2438">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2438">Keywords</span></span>

<span data-ttu-id="78146-2439">無</span><span class="sxs-lookup"><span data-stu-id="78146-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="78146-2440">IP 位址</span><span class="sxs-lookup"><span data-stu-id="78146-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="78146-2441">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="78146-2442">IPv4：</span><span class="sxs-lookup"><span data-stu-id="78146-2442">IPv4:</span></span>
<span data-ttu-id="78146-2443">复杂模式，它用于 IPv4 地址的格式化（期间）和未格式化（无期间）版本</span><span class="sxs-lookup"><span data-stu-id="78146-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="78146-2444">IPv6：</span><span class="sxs-lookup"><span data-stu-id="78146-2444">IPv6:</span></span>
<span data-ttu-id="78146-2445">复杂模式，它表示格式化的 IPv6 数字（包括冒号）</span><span class="sxs-lookup"><span data-stu-id="78146-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2446">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2447">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2447">Checksum</span></span>

<span data-ttu-id="78146-2448">否</span><span class="sxs-lookup"><span data-stu-id="78146-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2449">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2449">Definition</span></span>

<span data-ttu-id="78146-2450">对于 IPv6，如果接近 300 个字符，则 DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2451">正则表达式 Regex_ipv6_地址查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2452">找不到来自关键字\ip 地址的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="78146-2453">对于 IPv4，如果接近 300 个字符，则 DLP 策略 95% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2454">正则表达式 Regex_ipv4_地址查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2455">找到关键字\ip地址的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="78146-2456">对于 IPv6，如果接近 300 个字符，则 DLP 策略 95% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2457">正则表达式 Regex_ipv6_地址查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2458">找不到来自关键字\ip 地址的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2458">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2459">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="78146-2460">关键字_ip地址</span><span class="sxs-lookup"><span data-stu-id="78146-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="78146-2461">IP（此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="78146-2462">ip 地址</span><span class="sxs-lookup"><span data-stu-id="78146-2462">ip address</span></span> 
- <span data-ttu-id="78146-2463">ip 地址</span><span class="sxs-lookup"><span data-stu-id="78146-2463">ip addresses</span></span>
- <span data-ttu-id="78146-2464">互联网协议</span><span class="sxs-lookup"><span data-stu-id="78146-2464">internet protocol</span></span>
- <span data-ttu-id="78146-2465">IP - 的 、 的</span><span class="sxs-lookup"><span data-stu-id="78146-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="78146-2466">国际疾病分类（ICD-10-CM）</span><span class="sxs-lookup"><span data-stu-id="78146-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="78146-2467">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2467">Format</span></span>

<span data-ttu-id="78146-2468">Dictionary</span><span class="sxs-lookup"><span data-stu-id="78146-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2469">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2469">Pattern</span></span>

<span data-ttu-id="78146-2470">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2471">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2471">Checksum</span></span>

<span data-ttu-id="78146-2472">否</span><span class="sxs-lookup"><span data-stu-id="78146-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2473">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2473">Definition</span></span>

<span data-ttu-id="78146-2474">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2475">找到字典_icd_10_更新的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="78146-2476">找到字典_icd_10_代码中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="78146-2477">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2478">找到字典[icd_10]更新的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

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

<span data-ttu-id="78146-2479">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2479">Keywords</span></span>

<span data-ttu-id="78146-2480">字典[icd_10]更新关键字词典的任何术语，它基于[国际疾病分类，第十修订，临床修改（ICD-10-CM）。](https://go.microsoft.com/fwlink/?linkid=852604)</span><span class="sxs-lookup"><span data-stu-id="78146-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="78146-2481">此类型仅查找术语，而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="78146-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="78146-2482">任何术语从字典_icd_10_代码关键字字典，这是基于[国际疾病分类，第十修订，临床修改（ICD-10-CM）](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="78146-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="78146-2483">此类型只查找保险代码，而不是说明。</span><span class="sxs-lookup"><span data-stu-id="78146-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="78146-2484">国际疾病分类（ICD-9-CM）</span><span class="sxs-lookup"><span data-stu-id="78146-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="78146-2485">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2485">Format</span></span>

<span data-ttu-id="78146-2486">Dictionary</span><span class="sxs-lookup"><span data-stu-id="78146-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2487">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2487">Pattern</span></span>

<span data-ttu-id="78146-2488">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2489">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2489">Checksum</span></span>

<span data-ttu-id="78146-2490">否</span><span class="sxs-lookup"><span data-stu-id="78146-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2491">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2491">Definition</span></span>

<span data-ttu-id="78146-2492">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2493">找到字典_icd_9_更新的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="78146-2494">找到字典_icd_9_代码中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="78146-2495">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2496">找到字典_icd_9_更新的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2497">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2497">Keywords</span></span>

<span data-ttu-id="78146-2498">字典[icd_9_更新关键字词典》中的任何术语，它基于[国际疾病分类，第九修订版，临床修改（ICD-9-CM）。](https://go.microsoft.com/fwlink/?linkid=852605)</span><span class="sxs-lookup"><span data-stu-id="78146-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="78146-2499">此类型仅查找术语，而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="78146-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="78146-2500">任何术语从字典_icd_9_代码关键字字典，这是基于[国际疾病分类，第九修订，临床修改（ICD-9-CM）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="78146-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="78146-2501">此类型只查找保险代码，而不是说明。</span><span class="sxs-lookup"><span data-stu-id="78146-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="78146-2502">愛爾蘭個人公用服務 (PPS) 號碼</span><span class="sxs-lookup"><span data-stu-id="78146-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2503">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2503">Format</span></span>

<span data-ttu-id="78146-2504">旧格式（至 2012 年 12 月 31 日）：</span><span class="sxs-lookup"><span data-stu-id="78146-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="78146-2505">七位数字后跟 1-2 个字母</span><span class="sxs-lookup"><span data-stu-id="78146-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="78146-2506">新格式（2013 年 1 月 1 日及以后）：</span><span class="sxs-lookup"><span data-stu-id="78146-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="78146-2507">七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="78146-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2508">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2508">Pattern</span></span>

<span data-ttu-id="78146-2509">旧格式（至 2012 年 12 月 31 日）：</span><span class="sxs-lookup"><span data-stu-id="78146-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="78146-2510">七位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2510">Seven digits</span></span> 
- <span data-ttu-id="78146-2511">1-2 个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="78146-2512">新格式（2013 年 1 月 1 日及以后）：</span><span class="sxs-lookup"><span data-stu-id="78146-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="78146-2513">七位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2513">Seven digits</span></span> 
- <span data-ttu-id="78146-2514">字母（不区分大小写），这是字母检查数字</span><span class="sxs-lookup"><span data-stu-id="78146-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="78146-2515">字母"A"或"H"（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2516">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2516">Checksum</span></span>

<span data-ttu-id="78146-2517">是</span><span class="sxs-lookup"><span data-stu-id="78146-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2518">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2518">Definition</span></span>

<span data-ttu-id="78146-2519">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2520">函数 Func_ireland_pps 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2521">下列情况之一是正确的：</span><span class="sxs-lookup"><span data-stu-id="78146-2521">One of the following is true:</span></span>
    - <span data-ttu-id="78146-2522">找到关键字_ireland_pps 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="78146-2523">函数 Func_eu_date 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="78146-2524">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2524">The checksum passes.</span></span>

<span data-ttu-id="78146-2525">如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2526">函数 Func_ireland_pps 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2527">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2527">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2528">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="78146-2529">关键字_爱尔兰_pps</span><span class="sxs-lookup"><span data-stu-id="78146-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="78146-2530">个人公共服务号码</span><span class="sxs-lookup"><span data-stu-id="78146-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="78146-2531">PPS 编号</span><span class="sxs-lookup"><span data-stu-id="78146-2531">PPS Number</span></span> 
- <span data-ttu-id="78146-2532">PPS 数字</span><span class="sxs-lookup"><span data-stu-id="78146-2532">PPS Num</span></span> 
- <span data-ttu-id="78146-2533">PPS 号</span><span class="sxs-lookup"><span data-stu-id="78146-2533">PPS No.</span></span> 
- <span data-ttu-id="78146-2534">Pps#</span><span class="sxs-lookup"><span data-stu-id="78146-2534">PPS #</span></span> 
- <span data-ttu-id="78146-2535">Pps#</span><span class="sxs-lookup"><span data-stu-id="78146-2535">PPS#</span></span> 
- <span data-ttu-id="78146-2536">PPSN</span><span class="sxs-lookup"><span data-stu-id="78146-2536">PPSN</span></span> 
- <span data-ttu-id="78146-2537">公共服务卡</span><span class="sxs-lookup"><span data-stu-id="78146-2537">Public Services Card</span></span> 
- <span data-ttu-id="78146-2538">乌伊姆希尔·佩尔桑塔·塞尔布塞·波伊布勒</span><span class="sxs-lookup"><span data-stu-id="78146-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="78146-2539">乌伊姆</span><span class="sxs-lookup"><span data-stu-id="78146-2539">Uimh.</span></span> <span data-ttu-id="78146-2540">Psp</span><span class="sxs-lookup"><span data-stu-id="78146-2540">PSP</span></span> 
- <span data-ttu-id="78146-2541">Psp</span><span class="sxs-lookup"><span data-stu-id="78146-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="78146-2542">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="78146-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2543">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2543">Format</span></span>

<span data-ttu-id="78146-2544">13 位</span><span class="sxs-lookup"><span data-stu-id="78146-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2545">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2545">Pattern</span></span>

<span data-ttu-id="78146-2546">格式 化：</span><span class="sxs-lookup"><span data-stu-id="78146-2546">Formatted:</span></span>
- <span data-ttu-id="78146-2547">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2547">Two digits</span></span> 
- <span data-ttu-id="78146-2548">破折号</span><span class="sxs-lookup"><span data-stu-id="78146-2548">A dash</span></span> 
- <span data-ttu-id="78146-2549">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2549">Three digits</span></span> 
- <span data-ttu-id="78146-2550">破折号</span><span class="sxs-lookup"><span data-stu-id="78146-2550">A dash</span></span> 
- <span data-ttu-id="78146-2551">八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2551">Eight digits</span></span>

<span data-ttu-id="78146-2552">未格式化：</span><span class="sxs-lookup"><span data-stu-id="78146-2552">Unformatted:</span></span>
- <span data-ttu-id="78146-2553">13 个连续数字</span><span class="sxs-lookup"><span data-stu-id="78146-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2554">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2554">Checksum</span></span>

<span data-ttu-id="78146-2555">否</span><span class="sxs-lookup"><span data-stu-id="78146-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2556">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2556">Definition</span></span>

<span data-ttu-id="78146-2557">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2558">正则表达式 Regex_israel_bank_帐户_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2559">找到关键字_israel_bank_帐户_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2560">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="78146-2561">关键词_israel_银行_帐户_编号</span><span class="sxs-lookup"><span data-stu-id="78146-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="78146-2562">银行帐号</span><span class="sxs-lookup"><span data-stu-id="78146-2562">Bank Account Number</span></span> 
- <span data-ttu-id="78146-2563">银行账户</span><span class="sxs-lookup"><span data-stu-id="78146-2563">Bank Account</span></span> 
- <span data-ttu-id="78146-2564">帐号</span><span class="sxs-lookup"><span data-stu-id="78146-2564">Account Number</span></span> 
- <span data-ttu-id="78146-2565">《》</span><span class="sxs-lookup"><span data-stu-id="78146-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="78146-2566">以色列国民身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="78146-2567">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2567">Format</span></span>

<span data-ttu-id="78146-2568">九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2569">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2569">Pattern</span></span>

<span data-ttu-id="78146-2570">连续九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2571">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2571">Checksum</span></span>

<span data-ttu-id="78146-2572">是</span><span class="sxs-lookup"><span data-stu-id="78146-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2573">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2573">Definition</span></span>

<span data-ttu-id="78146-2574">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2575">函数 Func_israeli_national_id_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2576">找到关键字_以色列_国家_ID的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="78146-2577">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2577">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2578">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="78146-2579">关键词_以色列_国家_ID</span><span class="sxs-lookup"><span data-stu-id="78146-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="78146-2580">《》</span><span class="sxs-lookup"><span data-stu-id="78146-2580">מספר זהות</span></span> 
- <span data-ttu-id="78146-2581">国家身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="78146-2582">意大利驾照号码</span><span class="sxs-lookup"><span data-stu-id="78146-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2583">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2583">Format</span></span>

<span data-ttu-id="78146-2584">10 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="78146-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2585">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2585">Pattern</span></span>

- <span data-ttu-id="78146-2586">10 个字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="78146-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="78146-2587">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="78146-2588">字母"A"或"V"（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="78146-2589">七个字母（不区分大小写）、数字或下划线字符</span><span class="sxs-lookup"><span data-stu-id="78146-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="78146-2590">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2591">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2591">Checksum</span></span>

<span data-ttu-id="78146-2592">否</span><span class="sxs-lookup"><span data-stu-id="78146-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2593">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2593">Definition</span></span>

<span data-ttu-id="78146-2594">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2595">正则表达式 Regex_italy_驱动程序_许可证_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2596">找到关键字_italy_驱动程序_许可证_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2597">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="78146-2598">关键词_意大利_驱动程序_许可证_编号</span><span class="sxs-lookup"><span data-stu-id="78146-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="78146-2599">numero di 专利迪吉达</span><span class="sxs-lookup"><span data-stu-id="78146-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="78146-2600">专利迪吉达</span><span class="sxs-lookup"><span data-stu-id="78146-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="78146-2601">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="78146-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2602">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2602">Format</span></span>

<span data-ttu-id="78146-2603">七或八位</span><span class="sxs-lookup"><span data-stu-id="78146-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2604">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2604">Pattern</span></span>

<span data-ttu-id="78146-2605">银行帐号：</span><span class="sxs-lookup"><span data-stu-id="78146-2605">Bank account number:</span></span>
- <span data-ttu-id="78146-2606">七或八位</span><span class="sxs-lookup"><span data-stu-id="78146-2606">Seven or eight digits</span></span>
- <span data-ttu-id="78146-2607">银行账户分行代码：</span><span class="sxs-lookup"><span data-stu-id="78146-2607">Bank account branch code:</span></span>
- <span data-ttu-id="78146-2608">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2608">Four digits</span></span> 
- <span data-ttu-id="78146-2609">空格或破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="78146-2610">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2610">Three digits</span></span>

<span data-ttu-id="78146-2611">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2611">Checksum</span></span>

<span data-ttu-id="78146-2612">否</span><span class="sxs-lookup"><span data-stu-id="78146-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2613">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2613">Definition</span></span>

<span data-ttu-id="78146-2614">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2615">函数 Func_jp_bank_帐户查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2616">找到关键字_jp_bank_帐户的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="78146-2617">下列情况之一是正确的：</span><span class="sxs-lookup"><span data-stu-id="78146-2617">One of the following is true:</span></span>
- <span data-ttu-id="78146-2618">函数 Func_jp_bank_帐户_分支_代码查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2619">找到关键字_jp_bank_分支_code中一个关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="78146-2620">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2621">函数 Func_jp_bank_帐户查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2622">找到关键字_jp_bank_帐户的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2623">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="78146-2624">关键字_jp_银行_帐户</span><span class="sxs-lookup"><span data-stu-id="78146-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="78146-2625">支票帐号</span><span class="sxs-lookup"><span data-stu-id="78146-2625">Checking Account Number</span></span> 
- <span data-ttu-id="78146-2626">支票帐户</span><span class="sxs-lookup"><span data-stu-id="78146-2626">Checking Account</span></span> 
- <span data-ttu-id="78146-2627">支票帐户#</span><span class="sxs-lookup"><span data-stu-id="78146-2627">Checking Account #</span></span> 
- <span data-ttu-id="78146-2628">检查 Acct 编号</span><span class="sxs-lookup"><span data-stu-id="78146-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="78146-2629">检查 Acct#</span><span class="sxs-lookup"><span data-stu-id="78146-2629">Checking Acct #</span></span> 
- <span data-ttu-id="78146-2630">检查 Acct 号</span><span class="sxs-lookup"><span data-stu-id="78146-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="78146-2631">支票帐户号</span><span class="sxs-lookup"><span data-stu-id="78146-2631">Checking Account No.</span></span> 
- <span data-ttu-id="78146-2632">银行帐号</span><span class="sxs-lookup"><span data-stu-id="78146-2632">Bank Account Number</span></span> 
- <span data-ttu-id="78146-2633">银行账户</span><span class="sxs-lookup"><span data-stu-id="78146-2633">Bank Account</span></span> 
- <span data-ttu-id="78146-2634">银行账户#</span><span class="sxs-lookup"><span data-stu-id="78146-2634">Bank Account #</span></span> 
- <span data-ttu-id="78146-2635">银行编号</span><span class="sxs-lookup"><span data-stu-id="78146-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="78146-2636">银行 Acct#</span><span class="sxs-lookup"><span data-stu-id="78146-2636">Bank Acct #</span></span> 
- <span data-ttu-id="78146-2637">银行增加号</span><span class="sxs-lookup"><span data-stu-id="78146-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="78146-2638">银行账户号</span><span class="sxs-lookup"><span data-stu-id="78146-2638">Bank Account No.</span></span> 
- <span data-ttu-id="78146-2639">储蓄帐号</span><span class="sxs-lookup"><span data-stu-id="78146-2639">Savings Account Number</span></span> 
- <span data-ttu-id="78146-2640">储蓄账户</span><span class="sxs-lookup"><span data-stu-id="78146-2640">Savings Account</span></span> 
- <span data-ttu-id="78146-2641">储蓄账户#</span><span class="sxs-lookup"><span data-stu-id="78146-2641">Savings Account #</span></span> 
- <span data-ttu-id="78146-2642">节省费用编号</span><span class="sxs-lookup"><span data-stu-id="78146-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="78146-2643">节省费用#</span><span class="sxs-lookup"><span data-stu-id="78146-2643">Savings Acct #</span></span> 
- <span data-ttu-id="78146-2644">节省费用</span><span class="sxs-lookup"><span data-stu-id="78146-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="78146-2645">储蓄账户号</span><span class="sxs-lookup"><span data-stu-id="78146-2645">Savings Account No.</span></span> 
- <span data-ttu-id="78146-2646">借方帐号</span><span class="sxs-lookup"><span data-stu-id="78146-2646">Debit Account Number</span></span> 
- <span data-ttu-id="78146-2647">借方帐户</span><span class="sxs-lookup"><span data-stu-id="78146-2647">Debit Account</span></span> 
- <span data-ttu-id="78146-2648">借方帐户#</span><span class="sxs-lookup"><span data-stu-id="78146-2648">Debit Account #</span></span> 
- <span data-ttu-id="78146-2649">借方扣号</span><span class="sxs-lookup"><span data-stu-id="78146-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="78146-2650">借方 Acct#</span><span class="sxs-lookup"><span data-stu-id="78146-2650">Debit Acct #</span></span> 
- <span data-ttu-id="78146-2651">借方确认号</span><span class="sxs-lookup"><span data-stu-id="78146-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="78146-2652">借方帐户号</span><span class="sxs-lookup"><span data-stu-id="78146-2652">Debit Account No.</span></span> 
- <span data-ttu-id="78146-2653">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="78146-2654">#アカウントの確認</span><span class="sxs-lookup"><span data-stu-id="78146-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="78146-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="78146-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="78146-2656">·</span><span class="sxs-lookup"><span data-stu-id="78146-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="78146-2657">·</span><span class="sxs-lookup"><span data-stu-id="78146-2657">口座番号の確認</span></span> 
- <span data-ttu-id="78146-2658">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2658">銀行口座番号</span></span> 
- <span data-ttu-id="78146-2659">·</span><span class="sxs-lookup"><span data-stu-id="78146-2659">銀行口座</span></span> 
- <span data-ttu-id="78146-2660">·</span><span class="sxs-lookup"><span data-stu-id="78146-2660">銀行口座＃</span></span> 
- <span data-ttu-id="78146-2661">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="78146-2662">[acct]</span><span class="sxs-lookup"><span data-stu-id="78146-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="78146-2663">·</span><span class="sxs-lookup"><span data-stu-id="78146-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="78146-2664">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2664">銀行口座番号</span></span>
- <span data-ttu-id="78146-2665">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="78146-2666">·</span><span class="sxs-lookup"><span data-stu-id="78146-2666">預金口座</span></span> 
- <span data-ttu-id="78146-2667">·</span><span class="sxs-lookup"><span data-stu-id="78146-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="78146-2668">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="78146-2669">·</span><span class="sxs-lookup"><span data-stu-id="78146-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="78146-2670">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="78146-2671">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="78146-2672">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="78146-2673">\*</span><span class="sxs-lookup"><span data-stu-id="78146-2673">口座番号</span></span> 
- <span data-ttu-id="78146-2674">[</span><span class="sxs-lookup"><span data-stu-id="78146-2674">口座番号＃</span></span> 
- <span data-ttu-id="78146-2675">\*</span><span class="sxs-lookup"><span data-stu-id="78146-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="78146-2676">[ ]</span><span class="sxs-lookup"><span data-stu-id="78146-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="78146-2677">\* \* \*</span><span class="sxs-lookup"><span data-stu-id="78146-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="78146-2678">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="78146-2679">关键字_jp_bank_分支_代码</span><span class="sxs-lookup"><span data-stu-id="78146-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="78146-2680">奥特马基</span><span class="sxs-lookup"><span data-stu-id="78146-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="78146-2681">日本驾照号码</span><span class="sxs-lookup"><span data-stu-id="78146-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2682">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2682">Format</span></span>

<span data-ttu-id="78146-2683">12 位</span><span class="sxs-lookup"><span data-stu-id="78146-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2684">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2684">Pattern</span></span>

<span data-ttu-id="78146-2685">12 个连续数字</span><span class="sxs-lookup"><span data-stu-id="78146-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2686">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2686">Checksum</span></span>

<span data-ttu-id="78146-2687">否</span><span class="sxs-lookup"><span data-stu-id="78146-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2688">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2688">Definition</span></span>

<span data-ttu-id="78146-2689">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2690">函数 Func_jp_驱动程序_许可证_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2691">找到关键字_jp_驱动程序_许可证号码的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2692">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="78146-2693">关键字_jp_驱动程序_许可证_编号</span><span class="sxs-lookup"><span data-stu-id="78146-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="78146-2694">Dl#</span><span class="sxs-lookup"><span data-stu-id="78146-2694">dl#</span></span> 
- <span data-ttu-id="78146-2695">DL#</span><span class="sxs-lookup"><span data-stu-id="78146-2695">DL＃</span></span> 
- <span data-ttu-id="78146-2696">Dls#</span><span class="sxs-lookup"><span data-stu-id="78146-2696">dls#</span></span> 
- <span data-ttu-id="78146-2697">DLS\*</span><span class="sxs-lookup"><span data-stu-id="78146-2697">DLS＃</span></span> 
- <span data-ttu-id="78146-2698">驾照</span><span class="sxs-lookup"><span data-stu-id="78146-2698">driver license</span></span> 
- <span data-ttu-id="78146-2699">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2699">driver licenses</span></span> 
- <span data-ttu-id="78146-2700">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2700">drivers license</span></span> 
- <span data-ttu-id="78146-2701">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2701">driver's license</span></span> 
- <span data-ttu-id="78146-2702">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2702">drivers licenses</span></span> 
- <span data-ttu-id="78146-2703">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2703">driver's licenses</span></span> 
- <span data-ttu-id="78146-2704">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-2704">driving licence</span></span> 
- <span data-ttu-id="78146-2705">利利奇#</span><span class="sxs-lookup"><span data-stu-id="78146-2705">lic#</span></span> 
- <span data-ttu-id="78146-2706">LIC\*</span><span class="sxs-lookup"><span data-stu-id="78146-2706">LIC＃</span></span> 
- <span data-ttu-id="78146-2707">利茨#</span><span class="sxs-lookup"><span data-stu-id="78146-2707">lics#</span></span> 
- <span data-ttu-id="78146-2708">状态 ID</span><span class="sxs-lookup"><span data-stu-id="78146-2708">state id</span></span> 
- <span data-ttu-id="78146-2709">状态标识</span><span class="sxs-lookup"><span data-stu-id="78146-2709">state identification</span></span> 
- <span data-ttu-id="78146-2710">状态标识号</span><span class="sxs-lookup"><span data-stu-id="78146-2710">state identification number</span></span> 
- <span data-ttu-id="78146-2711">·</span><span class="sxs-lookup"><span data-stu-id="78146-2711">低所得国＃</span></span> 
- <span data-ttu-id="78146-2712">·007·</span><span class="sxs-lookup"><span data-stu-id="78146-2712">免許証</span></span> 
- <span data-ttu-id="78146-2713">\*ID</span><span class="sxs-lookup"><span data-stu-id="78146-2713">状態ID</span></span>
- <span data-ttu-id="78146-2714">\* \*</span><span class="sxs-lookup"><span data-stu-id="78146-2714">状態の識別</span></span> 
- <span data-ttu-id="78146-2715">·</span><span class="sxs-lookup"><span data-stu-id="78146-2715">状態の識別番号</span></span> 
- <span data-ttu-id="78146-2716">·000年</span><span class="sxs-lookup"><span data-stu-id="78146-2716">運転免許</span></span> 
- <span data-ttu-id="78146-2717">·</span><span class="sxs-lookup"><span data-stu-id="78146-2717">運転免許証</span></span> 
- <span data-ttu-id="78146-2718">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="78146-2719">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2720">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2720">Format</span></span>

<span data-ttu-id="78146-2721">两个字母后跟七位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2722">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2722">Pattern</span></span>

<span data-ttu-id="78146-2723">两个字母（不区分大小写）后跟七位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2724">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2724">Checksum</span></span>

<span data-ttu-id="78146-2725">否</span><span class="sxs-lookup"><span data-stu-id="78146-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2726">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2726">Definition</span></span>

<span data-ttu-id="78146-2727">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2728">函数 Func_jp_passport 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2729">找到关键字_jp_Passport中一个关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2730">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="78146-2731">关键词_jp_护照</span><span class="sxs-lookup"><span data-stu-id="78146-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="78146-2732">·</span><span class="sxs-lookup"><span data-stu-id="78146-2732">パスポート</span></span> 
- <span data-ttu-id="78146-2733">·\\\\\\\\\\\\\\\\\\\\\\</span><span class="sxs-lookup"><span data-stu-id="78146-2733">パスポート番号</span></span> 
- <span data-ttu-id="78146-2734">\* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="78146-2734">パスポートのNum</span></span> 
- <span data-ttu-id="78146-2735">·</span><span class="sxs-lookup"><span data-stu-id="78146-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="78146-2736">日本居民登记号</span><span class="sxs-lookup"><span data-stu-id="78146-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2737">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2737">Format</span></span>

<span data-ttu-id="78146-2738">11 位</span><span class="sxs-lookup"><span data-stu-id="78146-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2739">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2739">Pattern</span></span>

<span data-ttu-id="78146-2740">11 个连续数字</span><span class="sxs-lookup"><span data-stu-id="78146-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2741">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2741">Checksum</span></span>

<span data-ttu-id="78146-2742">否</span><span class="sxs-lookup"><span data-stu-id="78146-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2743">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2743">Definition</span></span>

<span data-ttu-id="78146-2744">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2745">函数 Func_jp_驻留_注册_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2746">找到关键字_jp_居民_注册_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2747">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="78146-2748">关键字_jp_居民_注册_编号</span><span class="sxs-lookup"><span data-stu-id="78146-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="78146-2749">居民登记号</span><span class="sxs-lookup"><span data-stu-id="78146-2749">Resident Registration Number</span></span>
- <span data-ttu-id="78146-2750">居民登记号</span><span class="sxs-lookup"><span data-stu-id="78146-2750">Resident Register Number</span></span> 
- <span data-ttu-id="78146-2751">居民基本登记号码</span><span class="sxs-lookup"><span data-stu-id="78146-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="78146-2752">居民登记号</span><span class="sxs-lookup"><span data-stu-id="78146-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="78146-2753">居民登记号</span><span class="sxs-lookup"><span data-stu-id="78146-2753">Resident Register No.</span></span> 
- <span data-ttu-id="78146-2754">居民基本登记处号</span><span class="sxs-lookup"><span data-stu-id="78146-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="78146-2755">基本居民登记册号</span><span class="sxs-lookup"><span data-stu-id="78146-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="78146-2756">[][][</span><span class="sxs-lookup"><span data-stu-id="78146-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="78146-2757">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="78146-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="78146-2758">·\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\</span><span class="sxs-lookup"><span data-stu-id="78146-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="78146-2759">·000年</span><span class="sxs-lookup"><span data-stu-id="78146-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="78146-2760">日本社会保险号</span><span class="sxs-lookup"><span data-stu-id="78146-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="78146-2761">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2761">Format</span></span>

<span data-ttu-id="78146-2762">7-12 位</span><span class="sxs-lookup"><span data-stu-id="78146-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2763">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2763">Pattern</span></span>

<span data-ttu-id="78146-2764">7-12 位：</span><span class="sxs-lookup"><span data-stu-id="78146-2764">7-12 digits:</span></span>
- <span data-ttu-id="78146-2765">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2765">Four digits</span></span> 
- <span data-ttu-id="78146-2766">连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="78146-2767">六位或</span><span class="sxs-lookup"><span data-stu-id="78146-2767">Six digits OR</span></span>
- <span data-ttu-id="78146-2768">7-12 个连续数字</span><span class="sxs-lookup"><span data-stu-id="78146-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2769">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2769">Checksum</span></span>

<span data-ttu-id="78146-2770">否</span><span class="sxs-lookup"><span data-stu-id="78146-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2771">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2771">Definition</span></span>

<span data-ttu-id="78146-2772">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2773">函数 Func_jp_sin 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2774">找到关键字_jp_sin 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="78146-2775">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2776">函数 Func_jp_sin_pre_1997 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2777">找到关键字_jp_sin 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2777">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2778">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="78146-2779">关键字_jp_sin</span><span class="sxs-lookup"><span data-stu-id="78146-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="78146-2780">社会保险号</span><span class="sxs-lookup"><span data-stu-id="78146-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="78146-2781">社会保险数字</span><span class="sxs-lookup"><span data-stu-id="78146-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="78146-2782">社会保险号</span><span class="sxs-lookup"><span data-stu-id="78146-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="78146-2783">\*</span><span class="sxs-lookup"><span data-stu-id="78146-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="78146-2784">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="78146-2785">日本居留卡号</span><span class="sxs-lookup"><span data-stu-id="78146-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2786">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2786">Format</span></span>

<span data-ttu-id="78146-2787">12 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="78146-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2788">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2788">Pattern</span></span>

<span data-ttu-id="78146-2789">12 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="78146-2789">12 letters and digits:</span></span>
- <span data-ttu-id="78146-2790">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="78146-2791">八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2791">Eight digits</span></span> 
- <span data-ttu-id="78146-2792">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2793">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2793">Checksum</span></span>

<span data-ttu-id="78146-2794">否</span><span class="sxs-lookup"><span data-stu-id="78146-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2795">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2795">Definition</span></span>

<span data-ttu-id="78146-2796">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2797">正则表达式 Regex_jp_暂留_card_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2798">找到关键字_jp_居住_卡_号码的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2799">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="78146-2800">关键字_jp_居住_卡_编号</span><span class="sxs-lookup"><span data-stu-id="78146-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="78146-2801">居住卡号</span><span class="sxs-lookup"><span data-stu-id="78146-2801">Residence card number</span></span>
- <span data-ttu-id="78146-2802">居住卡无</span><span class="sxs-lookup"><span data-stu-id="78146-2802">Residence card no</span></span>
- <span data-ttu-id="78146-2803">居住卡#</span><span class="sxs-lookup"><span data-stu-id="78146-2803">Residence card #</span></span>
- <span data-ttu-id="78146-2804">·[</span><span class="sxs-lookup"><span data-stu-id="78146-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="78146-2805">马来西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2806">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2806">Format</span></span>

<span data-ttu-id="78146-2807">包含可选连字符的 12 位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2808">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2808">Pattern</span></span>

<span data-ttu-id="78146-2809">12 位：</span><span class="sxs-lookup"><span data-stu-id="78146-2809">12 digits:</span></span>
- <span data-ttu-id="78146-2810">格式为 YYMMDD 的六位数字，即出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="78146-2811">破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-2811">A dash (optional)</span></span> 
- <span data-ttu-id="78146-2812">双字母出生地代码</span><span class="sxs-lookup"><span data-stu-id="78146-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="78146-2813">破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-2813">A dash (optional)</span></span> 
- <span data-ttu-id="78146-2814">三个随机数字</span><span class="sxs-lookup"><span data-stu-id="78146-2814">Three random digits</span></span> 
- <span data-ttu-id="78146-2815">一位性别代码</span><span class="sxs-lookup"><span data-stu-id="78146-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2816">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2816">Checksum</span></span>

<span data-ttu-id="78146-2817">否</span><span class="sxs-lookup"><span data-stu-id="78146-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2818">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2818">Definition</span></span>

<span data-ttu-id="78146-2819">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2820">正则表达式 Regex_malaysia_id_card_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2821">找到关键字_马马\id_card_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2822">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="78146-2823">关键词_马来西亚_id_卡_编号</span><span class="sxs-lookup"><span data-stu-id="78146-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="78146-2824">数字应用卡</span><span class="sxs-lookup"><span data-stu-id="78146-2824">digital application card</span></span>
- <span data-ttu-id="78146-2825">i/c</span><span class="sxs-lookup"><span data-stu-id="78146-2825">i/c</span></span>
- <span data-ttu-id="78146-2826">i/c 否</span><span class="sxs-lookup"><span data-stu-id="78146-2826">i/c no</span></span>
- <span data-ttu-id="78146-2827">Ic</span><span class="sxs-lookup"><span data-stu-id="78146-2827">ic</span></span>
- <span data-ttu-id="78146-2828">ic 无</span><span class="sxs-lookup"><span data-stu-id="78146-2828">ic no</span></span>
- <span data-ttu-id="78146-2829">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2829">id card</span></span>
- <span data-ttu-id="78146-2830">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2830">identification Card</span></span>
- <span data-ttu-id="78146-2831">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2831">identity card</span></span>
- <span data-ttu-id="78146-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="78146-2832">k/p</span></span>
- <span data-ttu-id="78146-2833">k/p 否</span><span class="sxs-lookup"><span data-stu-id="78146-2833">k/p no</span></span>
- <span data-ttu-id="78146-2834">卡德·阿库恩·迪里</span><span class="sxs-lookup"><span data-stu-id="78146-2834">kad akuan diri</span></span>
- <span data-ttu-id="78146-2835">卡德·阿普利卡西数字</span><span class="sxs-lookup"><span data-stu-id="78146-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="78146-2836">卡德彭纳兰马来西亚</span><span class="sxs-lookup"><span data-stu-id="78146-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="78146-2837">Kp</span><span class="sxs-lookup"><span data-stu-id="78146-2837">kp</span></span>
- <span data-ttu-id="78146-2838">kp 否</span><span class="sxs-lookup"><span data-stu-id="78146-2838">kp no</span></span>
- <span data-ttu-id="78146-2839">迈卡德</span><span class="sxs-lookup"><span data-stu-id="78146-2839">mykad</span></span>
- <span data-ttu-id="78146-2840">迈卡斯</span><span class="sxs-lookup"><span data-stu-id="78146-2840">mykas</span></span>
- <span data-ttu-id="78146-2841">迈基德</span><span class="sxs-lookup"><span data-stu-id="78146-2841">mykid</span></span>
- <span data-ttu-id="78146-2842">迈普尔</span><span class="sxs-lookup"><span data-stu-id="78146-2842">mypr</span></span>
- <span data-ttu-id="78146-2843">迈门特拉</span><span class="sxs-lookup"><span data-stu-id="78146-2843">mytentera</span></span>
- <span data-ttu-id="78146-2844">马来西亚身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2844">malaysia identity card</span></span>
- <span data-ttu-id="78146-2845">马来西亚身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2845">malaysian identity card</span></span>
- <span data-ttu-id="78146-2846">恩里克</span><span class="sxs-lookup"><span data-stu-id="78146-2846">nric</span></span>
- <span data-ttu-id="78146-2847">个人身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="78146-2848">荷兰公民服务 （BSN） 号码</span><span class="sxs-lookup"><span data-stu-id="78146-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2849">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2849">Format</span></span>

<span data-ttu-id="78146-2850">包含可选空格的 8-9 位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2851">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2851">Pattern</span></span>

<span data-ttu-id="78146-2852">8-9 位：</span><span class="sxs-lookup"><span data-stu-id="78146-2852">8-9 digits:</span></span>
- <span data-ttu-id="78146-2853">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2853">Three digits</span></span> 
- <span data-ttu-id="78146-2854">空格（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-2854">A space (optional)</span></span> 
- <span data-ttu-id="78146-2855">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2855">Three digits</span></span> 
- <span data-ttu-id="78146-2856">空格（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-2856">A space (optional)</span></span> 
- <span data-ttu-id="78146-2857">2-3 位</span><span class="sxs-lookup"><span data-stu-id="78146-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2858">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2858">Checksum</span></span>

<span data-ttu-id="78146-2859">是</span><span class="sxs-lookup"><span data-stu-id="78146-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2860">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2860">Definition</span></span>

<span data-ttu-id="78146-2861">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2862">函数 Func_荷兰_bsn 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2863">找到关键字_荷兰_bsn的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="78146-2864">函数 Func_eu_date2 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="78146-2865">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2865">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2866">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="78146-2867">关键字_荷兰\bsn</span><span class="sxs-lookup"><span data-stu-id="78146-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="78146-2868">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="78146-2868">Citizen service number</span></span> 
- <span data-ttu-id="78146-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="78146-2869">BSN</span></span> 
- <span data-ttu-id="78146-2870">汉堡服务努默</span><span class="sxs-lookup"><span data-stu-id="78146-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="78146-2871">苏武努默</span><span class="sxs-lookup"><span data-stu-id="78146-2871">Sofinummer</span></span> 
- <span data-ttu-id="78146-2872">佩松斯格邦登·努默</span><span class="sxs-lookup"><span data-stu-id="78146-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="78146-2873">佩松斯努默</span><span class="sxs-lookup"><span data-stu-id="78146-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="78146-2874">新西兰卫生部编号</span><span class="sxs-lookup"><span data-stu-id="78146-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2875">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2875">Format</span></span>

<span data-ttu-id="78146-2876">三个字母、一个空格（可选）和四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2877">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2877">Pattern</span></span>

<span data-ttu-id="78146-2878">三个字母（不区分大小写）空格（可选）四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2879">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2879">Checksum</span></span>

<span data-ttu-id="78146-2880">是</span><span class="sxs-lookup"><span data-stu-id="78146-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2881">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2881">Definition</span></span>

<span data-ttu-id="78146-2882">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2883">函数 Func_new___________health_s_health_s_s_health_s_s_health_s_health_s_s_health_s_s 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2884">找到关键字_nz_字词的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="78146-2885">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2885">The checksum passes.</span></span>

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

<span data-ttu-id="78146-2886">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2886">Keywords</span></span>

<span data-ttu-id="78146-2887">关键字_nz_字词</span><span class="sxs-lookup"><span data-stu-id="78146-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="78146-2888">国家卫生报告</span><span class="sxs-lookup"><span data-stu-id="78146-2888">NHI</span></span> 
- <span data-ttu-id="78146-2889">JPRatingExplicitAllowed</span><span class="sxs-lookup"><span data-stu-id="78146-2889">New Zealand</span></span> 
- <span data-ttu-id="78146-2890">健康情況</span><span class="sxs-lookup"><span data-stu-id="78146-2890">Health</span></span> 
- <span data-ttu-id="78146-2891">治疗</span><span class="sxs-lookup"><span data-stu-id="78146-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="78146-2892">挪威身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2893">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2893">Format</span></span>

<span data-ttu-id="78146-2894">11 位</span><span class="sxs-lookup"><span data-stu-id="78146-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2895">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2895">Pattern</span></span>

<span data-ttu-id="78146-2896">11 位：</span><span class="sxs-lookup"><span data-stu-id="78146-2896">11 digits:</span></span>
- <span data-ttu-id="78146-2897">DDMMYY 格式中的六位数字，即出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="78146-2898">三位个人号码</span><span class="sxs-lookup"><span data-stu-id="78146-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="78146-2899">两个检查数字</span><span class="sxs-lookup"><span data-stu-id="78146-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2900">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2900">Checksum</span></span>

<span data-ttu-id="78146-2901">是</span><span class="sxs-lookup"><span data-stu-id="78146-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2902">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2902">Definition</span></span>

<span data-ttu-id="78146-2903">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2904">函数 Func_norway_id_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2905">找到关键字_norway_id_号码的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="78146-2906">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2906">The checksum passes.</span></span>
- <span data-ttu-id="78146-2907">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2908">函数 Func_norway_id_numbe 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2909">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2909">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2910">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="78146-2911">关键字_norway_id_编号</span><span class="sxs-lookup"><span data-stu-id="78146-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="78146-2912">个人识别号码</span><span class="sxs-lookup"><span data-stu-id="78146-2912">Personal identification number</span></span>
- <span data-ttu-id="78146-2913">挪威身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="78146-2914">身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-2914">ID Number</span></span>
- <span data-ttu-id="78146-2915">识别</span><span class="sxs-lookup"><span data-stu-id="78146-2915">Identification</span></span>
- <span data-ttu-id="78146-2916">人物</span><span class="sxs-lookup"><span data-stu-id="78146-2916">Personnummer</span></span>
- <span data-ttu-id="78146-2917">费德塞尔斯努默</span><span class="sxs-lookup"><span data-stu-id="78146-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="78146-2918">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2919">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2919">Format</span></span>

<span data-ttu-id="78146-2920">12 位数字由连字符分隔</span><span class="sxs-lookup"><span data-stu-id="78146-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2921">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2921">Pattern</span></span>

<span data-ttu-id="78146-2922">12 位：</span><span class="sxs-lookup"><span data-stu-id="78146-2922">12 digits:</span></span>
- <span data-ttu-id="78146-2923">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2923">Four digits</span></span> 
- <span data-ttu-id="78146-2924">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-2924">A hyphen</span></span> 
- <span data-ttu-id="78146-2925">七位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2925">Seven digits</span></span> 
- <span data-ttu-id="78146-2926">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-2926">A hyphen</span></span> 
- <span data-ttu-id="78146-2927">一位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2928">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2928">Checksum</span></span>

<span data-ttu-id="78146-2929">否</span><span class="sxs-lookup"><span data-stu-id="78146-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2930">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2930">Definition</span></span>

<span data-ttu-id="78146-2931">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2932">正则表达式 Regex_philippines_unified_id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2933">找到关键字_philippines_id 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2934">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="78146-2935">关键字_菲律宾_id</span><span class="sxs-lookup"><span data-stu-id="78146-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="78146-2936">统一多用途 ID</span><span class="sxs-lookup"><span data-stu-id="78146-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="78146-2937">UMID</span><span class="sxs-lookup"><span data-stu-id="78146-2937">UMID</span></span> 
- <span data-ttu-id="78146-2938">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-2938">Identity Card</span></span> 
- <span data-ttu-id="78146-2939">皮纳格-伊桑多莱宁 ID</span><span class="sxs-lookup"><span data-stu-id="78146-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="78146-2940">波蘭身分證明卡</span><span class="sxs-lookup"><span data-stu-id="78146-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="78146-2941">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2941">Format</span></span>

<span data-ttu-id="78146-2942">三个字母和六位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2943">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2943">Pattern</span></span>

<span data-ttu-id="78146-2944">三个字母（不区分大小写）后跟六位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2945">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2945">Checksum</span></span>

<span data-ttu-id="78146-2946">是</span><span class="sxs-lookup"><span data-stu-id="78146-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2947">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2947">Definition</span></span>

<span data-ttu-id="78146-2948">如果 DLP 策略在 300 个字符的接近范围内检测到这种类型的敏感信息，则 DLP 策略有 75% 的置相信度：如果函数 Func_polish_national_id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="78146-2949">找到关键字_波兰_国家_id_passport_号码的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="78146-2950">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2951">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="78146-2952">关键字_波兰_国家_id_护照_编号</span><span class="sxs-lookup"><span data-stu-id="78146-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="78146-2953">多埃德·奥索比斯蒂</span><span class="sxs-lookup"><span data-stu-id="78146-2953">Dowód osobisty</span></span>
- <span data-ttu-id="78146-2954">努默·多沃杜·奥索比斯特戈</span><span class="sxs-lookup"><span data-stu-id="78146-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="78146-2955">纳兹瓦伊·努塞尔·多沃杜·奥索比斯特戈</span><span class="sxs-lookup"><span data-stu-id="78146-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="78146-2956">纳兹瓦·伊·多沃杜·奥索比斯特戈</span><span class="sxs-lookup"><span data-stu-id="78146-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="78146-2957">纳兹瓦·伊·里·多沃杜·托萨莫奇</span><span class="sxs-lookup"><span data-stu-id="78146-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="78146-2958">多埃德·托萨莫奇</span><span class="sxs-lookup"><span data-stu-id="78146-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="78146-2959">道琼斯指数。</span><span class="sxs-lookup"><span data-stu-id="78146-2959">dow.</span></span> <span data-ttu-id="78146-2960">操作系统。</span><span class="sxs-lookup"><span data-stu-id="78146-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="78146-2961">波蘭國民身分證 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="78146-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="78146-2962">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2962">Format</span></span>

<span data-ttu-id="78146-2963">11 位</span><span class="sxs-lookup"><span data-stu-id="78146-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2964">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2964">Pattern</span></span>

<span data-ttu-id="78146-2965">11 个连续数字</span><span class="sxs-lookup"><span data-stu-id="78146-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2966">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2966">Checksum</span></span>

<span data-ttu-id="78146-2967">是</span><span class="sxs-lookup"><span data-stu-id="78146-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2968">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2968">Definition</span></span>

<span data-ttu-id="78146-2969">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2970">函数 Func_pesel_标识_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2971">找到关键字_pesel_标识_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="78146-2972">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-2973">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="78146-2974">关键字_pesel_标识_数字</span><span class="sxs-lookup"><span data-stu-id="78146-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="78146-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="78146-2975">Nr PESEL</span></span>
- <span data-ttu-id="78146-2976">佩塞尔</span><span class="sxs-lookup"><span data-stu-id="78146-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="78146-2977">波蘭護照</span><span class="sxs-lookup"><span data-stu-id="78146-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="78146-2978">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2978">Format</span></span>

<span data-ttu-id="78146-2979">两个字母和七位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2980">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2980">Pattern</span></span>

<span data-ttu-id="78146-2981">两个字母（不区分大小写）后跟七位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-2982">校验</span><span class="sxs-lookup"><span data-stu-id="78146-2982">Checksum</span></span>

<span data-ttu-id="78146-2983">是</span><span class="sxs-lookup"><span data-stu-id="78146-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-2984">定義</span><span class="sxs-lookup"><span data-stu-id="78146-2984">Definition</span></span>

<span data-ttu-id="78146-2985">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-2986">函数 Func_polish_Passport_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-2987">找到关键字_波兰_国家_id_passport_号码的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="78146-2988">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-2988">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-2989">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="78146-2990">关键字_波兰_国家_id_护照_编号</span><span class="sxs-lookup"><span data-stu-id="78146-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="78146-2991">努默·帕斯波特</span><span class="sxs-lookup"><span data-stu-id="78146-2991">Numer paszportu</span></span>
- <span data-ttu-id="78146-2992">星期日。</span><span class="sxs-lookup"><span data-stu-id="78146-2992">Nr.</span></span> <span data-ttu-id="78146-2993">帕什波特</span><span class="sxs-lookup"><span data-stu-id="78146-2993">Paszportu</span></span>
- <span data-ttu-id="78146-2994">帕什波特</span><span class="sxs-lookup"><span data-stu-id="78146-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="78146-2995">葡萄牙公民證號碼</span><span class="sxs-lookup"><span data-stu-id="78146-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-2996">格式</span><span class="sxs-lookup"><span data-stu-id="78146-2996">Format</span></span>

<span data-ttu-id="78146-2997">八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-2998">模式</span><span class="sxs-lookup"><span data-stu-id="78146-2998">Pattern</span></span>

<span data-ttu-id="78146-2999">八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3000">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3000">Checksum</span></span>

<span data-ttu-id="78146-3001">否</span><span class="sxs-lookup"><span data-stu-id="78146-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3002">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3002">Definition</span></span>

<span data-ttu-id="78146-3003">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3004">正则表达式 Regex_portugal_citizen_card_card 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3005">找到关键字_portugal_公民卡的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3006">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="78146-3007">关键词_portugal_公民_卡片</span><span class="sxs-lookup"><span data-stu-id="78146-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="78146-3008">公民卡</span><span class="sxs-lookup"><span data-stu-id="78146-3008">Citizen Card</span></span>
- <span data-ttu-id="78146-3009">国民身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3009">National ID Card</span></span>
- <span data-ttu-id="78146-3010">副本</span><span class="sxs-lookup"><span data-stu-id="78146-3010">CC</span></span>
- <span data-ttu-id="78146-3011">卡托·德西达多</span><span class="sxs-lookup"><span data-stu-id="78146-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="78146-3012">比埃尔特·德·伊登达德</span><span class="sxs-lookup"><span data-stu-id="78146-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="78146-3013">沙特阿拉伯国民身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="78146-3014">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3014">Format</span></span>

<span data-ttu-id="78146-3015">10 位</span><span class="sxs-lookup"><span data-stu-id="78146-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3016">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3016">Pattern</span></span>

<span data-ttu-id="78146-3017">10 个连续数字</span><span class="sxs-lookup"><span data-stu-id="78146-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3018">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3018">Checksum</span></span>

<span data-ttu-id="78146-3019">否</span><span class="sxs-lookup"><span data-stu-id="78146-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3020">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3020">Definition</span></span>

<span data-ttu-id="78146-3021">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3022">正则表达式 Regex_saudi_arabia_national_id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3023">找到关键字_saudi_arabia_national_id 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-3024">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="78146-3025">关键字_沙特_阿拉伯\国家_id</span><span class="sxs-lookup"><span data-stu-id="78146-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="78146-3026">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3026">Identification Card</span></span> 
- <span data-ttu-id="78146-3027">I 卡号</span><span class="sxs-lookup"><span data-stu-id="78146-3027">I card number</span></span> 
- <span data-ttu-id="78146-3028">識別碼</span><span class="sxs-lookup"><span data-stu-id="78146-3028">ID number</span></span> 
- <span data-ttu-id="78146-3029">《》</span><span class="sxs-lookup"><span data-stu-id="78146-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="78146-3030">新加坡国民登记身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3031">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3031">Format</span></span>

<span data-ttu-id="78146-3032">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="78146-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3033">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3033">Pattern</span></span>

- <span data-ttu-id="78146-3034">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="78146-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="78146-3035">字母"F"、"G"、"S"或"T"（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="78146-3036">七位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3036">Seven digits</span></span> 
- <span data-ttu-id="78146-3037">字母检查数字</span><span class="sxs-lookup"><span data-stu-id="78146-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3038">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3038">Checksum</span></span>

<span data-ttu-id="78146-3039">是</span><span class="sxs-lookup"><span data-stu-id="78146-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3040">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3040">Definition</span></span>

<span data-ttu-id="78146-3041">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3042">正则表达式 Regex_singapore_nric 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3043">找到来自关键字_新加坡\nric的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="78146-3044">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-3044">The checksum passes.</span></span>

<span data-ttu-id="78146-3045">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3046">正则表达式 Regex_singapore_nric 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3047">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-3047">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-3048">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="78146-3049">关键字_新加坡\nric</span><span class="sxs-lookup"><span data-stu-id="78146-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="78146-3050">国民登记身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="78146-3051">身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-3051">Identity Card Number</span></span> 
- <span data-ttu-id="78146-3052">国家</span><span class="sxs-lookup"><span data-stu-id="78146-3052">NRIC</span></span> 
- <span data-ttu-id="78146-3053">Ic</span><span class="sxs-lookup"><span data-stu-id="78146-3053">IC</span></span> 
- <span data-ttu-id="78146-3054">外国身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="78146-3055">翅</span><span class="sxs-lookup"><span data-stu-id="78146-3055">FIN</span></span> 
- <span data-ttu-id="78146-3056">·</span><span class="sxs-lookup"><span data-stu-id="78146-3056">身份证</span></span> 
- <span data-ttu-id="78146-3057">·</span><span class="sxs-lookup"><span data-stu-id="78146-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="78146-3058">南非身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3059">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3059">Format</span></span>

<span data-ttu-id="78146-3060">13 位可能包含空格的数字</span><span class="sxs-lookup"><span data-stu-id="78146-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3061">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3061">Pattern</span></span>

<span data-ttu-id="78146-3062">13 位：</span><span class="sxs-lookup"><span data-stu-id="78146-3062">13 digits:</span></span>
- <span data-ttu-id="78146-3063">格式为 YYMMDD 的六位数字，即出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="78146-3064">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3064">Four digits</span></span> 
- <span data-ttu-id="78146-3065">单位数公民身份指标</span><span class="sxs-lookup"><span data-stu-id="78146-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="78146-3066">数字"8"或"9"</span><span class="sxs-lookup"><span data-stu-id="78146-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="78146-3067">一个数字，即校验和数字</span><span class="sxs-lookup"><span data-stu-id="78146-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3068">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3068">Checksum</span></span>

<span data-ttu-id="78146-3069">是</span><span class="sxs-lookup"><span data-stu-id="78146-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3070">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3070">Definition</span></span>

<span data-ttu-id="78146-3071">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3072">函数 Func_south_africa_id_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3073">找到关键字_南非_非洲_标识_编号的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="78146-3074">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3075">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="78146-3076">关键词_南非_非洲_识别_数字</span><span class="sxs-lookup"><span data-stu-id="78146-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="78146-3077">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3077">Identity card</span></span>
- <span data-ttu-id="78146-3078">ID</span><span class="sxs-lookup"><span data-stu-id="78146-3078">ID</span></span>
- <span data-ttu-id="78146-3079">识别</span><span class="sxs-lookup"><span data-stu-id="78146-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="78146-3080">韩国居民登记号</span><span class="sxs-lookup"><span data-stu-id="78146-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3081">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3081">Format</span></span>

<span data-ttu-id="78146-3082">包含连字符的 13 位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3083">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3083">Pattern</span></span>

<span data-ttu-id="78146-3084">13 位：</span><span class="sxs-lookup"><span data-stu-id="78146-3084">13 digits:</span></span>
- <span data-ttu-id="78146-3085">格式为 YYMMDD 的六位数字，即出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="78146-3086">连字符</span><span class="sxs-lookup"><span data-stu-id="78146-3086">A hyphen</span></span> 
- <span data-ttu-id="78146-3087">由世纪和性别决定的一个数字</span><span class="sxs-lookup"><span data-stu-id="78146-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="78146-3088">四位出生区域代码</span><span class="sxs-lookup"><span data-stu-id="78146-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="78146-3089">一个数字，用于区分上述数字相同的人员</span><span class="sxs-lookup"><span data-stu-id="78146-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="78146-3090">校验数字。</span><span class="sxs-lookup"><span data-stu-id="78146-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3091">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3091">Checksum</span></span>

<span data-ttu-id="78146-3092">是</span><span class="sxs-lookup"><span data-stu-id="78146-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3093">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3093">Definition</span></span>

<span data-ttu-id="78146-3094">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3095">函数 Func_south_korea_驻留_数字查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3096">找到关键字_南_韩国_居民号码的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="78146-3097">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-3097">The checksum passes.</span></span>

<span data-ttu-id="78146-3098">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3099">函数 Func_south_korea_驻留_数字查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3100">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-3100">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-3101">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="78146-3102">关键词_南_韩国_居民_号码</span><span class="sxs-lookup"><span data-stu-id="78146-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="78146-3103">国民身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3103">National ID card</span></span> 
- <span data-ttu-id="78146-3104">公民登记号码</span><span class="sxs-lookup"><span data-stu-id="78146-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="78146-3105">朱明·德翁诺克·贝尼奥</span><span class="sxs-lookup"><span data-stu-id="78146-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="78146-3106">RRN</span><span class="sxs-lookup"><span data-stu-id="78146-3106">RRN</span></span> 
- <span data-ttu-id="78146-3107">《 》</span><span class="sxs-lookup"><span data-stu-id="78146-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="78146-3108">西班牙社會安全號碼 (SSN)</span><span class="sxs-lookup"><span data-stu-id="78146-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="78146-3109">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3109">Format</span></span>

<span data-ttu-id="78146-3110">11-12 位</span><span class="sxs-lookup"><span data-stu-id="78146-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3111">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3111">Pattern</span></span>

<span data-ttu-id="78146-3112">11-12 位：</span><span class="sxs-lookup"><span data-stu-id="78146-3112">11-12 digits:</span></span>
- <span data-ttu-id="78146-3113">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3113">Two digits</span></span> 
- <span data-ttu-id="78146-3114">正向斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="78146-3115">7-8 位</span><span class="sxs-lookup"><span data-stu-id="78146-3115">7-8 digits</span></span> 
- <span data-ttu-id="78146-3116">正向斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="78146-3117">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3118">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3118">Checksum</span></span>

<span data-ttu-id="78146-3119">是</span><span class="sxs-lookup"><span data-stu-id="78146-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3120">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3120">Definition</span></span>

<span data-ttu-id="78146-3121">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3122">函数 Func_spanish_social_安全_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3123">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3124">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3124">Keywords</span></span>

<span data-ttu-id="78146-3125">無</span><span class="sxs-lookup"><span data-stu-id="78146-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="78146-3126">SQL 服务器连接字符串</span><span class="sxs-lookup"><span data-stu-id="78146-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="78146-3127">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3127">Format</span></span>

<span data-ttu-id="78146-3128">字符串"用户 ID"、"用户 ID"、"uid"或"UserId"后跟以下模式中概述的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="78146-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3129">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3129">Pattern</span></span>

- <span data-ttu-id="78146-3130">字符串"用户 ID"、"用户 ID"、"uid"或"用户 Id"</span><span class="sxs-lookup"><span data-stu-id="78146-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="78146-3131">1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="78146-3132">字符串"密码"或"pwd"，其中"pwd"前面没有小写字母</span><span class="sxs-lookup"><span data-stu-id="78146-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="78146-3133">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-3133">An equal sign (=)</span></span>
- <span data-ttu-id="78146-3134">任何不是美元符号 （$）、百分比符号 （%））的字符（），大于符号 （>），在符号 （*）、 引号 （）、分号 （;)、左大括号 （*） 或左括号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="78146-3135">非分号（;)、正斜杠 （/） 或引号 （"））的 7-128 个字符的任意组合</span><span class="sxs-lookup"><span data-stu-id="78146-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="78146-3136">分号 （;)或引号 （"）</span><span class="sxs-lookup"><span data-stu-id="78146-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3137">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3137">Checksum</span></span>

<span data-ttu-id="78146-3138">否</span><span class="sxs-lookup"><span data-stu-id="78146-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3139">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3139">Definition</span></span>

<span data-ttu-id="78146-3140">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3141">正则表达式 CEP_Regex_SQLServer 连接字符串查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3142">**找不到**来自 CEP_全局筛选的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="78146-3143">正则表达式 CEP_Password PlaceHolder**找不到**与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3144">正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-3145">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="78146-3146">CEP_全局筛选</span><span class="sxs-lookup"><span data-stu-id="78146-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="78146-3147">一些密码</span><span class="sxs-lookup"><span data-stu-id="78146-3147">some-password</span></span>
- <span data-ttu-id="78146-3148">一些密码</span><span class="sxs-lookup"><span data-stu-id="78146-3148">somepassword</span></span>
- <span data-ttu-id="78146-3149">秘密密码</span><span class="sxs-lookup"><span data-stu-id="78146-3149">secretPassword</span></span>
- <span data-ttu-id="78146-3150">样品</span><span class="sxs-lookup"><span data-stu-id="78146-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="78146-3151">CEP_密码放置器</span><span class="sxs-lookup"><span data-stu-id="78146-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="78146-3152">（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="78146-3153">密码或 pwd 后跟 0-2 空格、等号 （+）、0-2 空格和星号 （\*） -- OR --</span><span class="sxs-lookup"><span data-stu-id="78146-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="78146-3154">密码或密码后跟：</span><span class="sxs-lookup"><span data-stu-id="78146-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="78146-3155">等号 （\*）</span><span class="sxs-lookup"><span data-stu-id="78146-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="78146-3156">小于符号 （<）</span><span class="sxs-lookup"><span data-stu-id="78146-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="78146-3157">1-200 个字符的任意组合，这些字符是大写或小写字母、数字、星号 （*）、连字符 （-）、下划线 （*） 或空格字符</span><span class="sxs-lookup"><span data-stu-id="78146-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="78146-3158">大于符号 （>）</span><span class="sxs-lookup"><span data-stu-id="78146-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="78146-3159">CEP_通用示例关键字</span><span class="sxs-lookup"><span data-stu-id="78146-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="78146-3160">（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="78146-3161">康托索</span><span class="sxs-lookup"><span data-stu-id="78146-3161">contoso</span></span>
- <span data-ttu-id="78146-3162">法布里卡姆</span><span class="sxs-lookup"><span data-stu-id="78146-3162">fabrikam</span></span>
- <span data-ttu-id="78146-3163">北风</span><span class="sxs-lookup"><span data-stu-id="78146-3163">northwind</span></span>
- <span data-ttu-id="78146-3164">沙 箱</span><span class="sxs-lookup"><span data-stu-id="78146-3164">sandbox</span></span>
- <span data-ttu-id="78146-3165">一个盒子</span><span class="sxs-lookup"><span data-stu-id="78146-3165">onebox</span></span>
- <span data-ttu-id="78146-3166">本地 主机</span><span class="sxs-lookup"><span data-stu-id="78146-3166">localhost</span></span>
- <span data-ttu-id="78146-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="78146-3167">127.0.0.1</span></span>
- <span data-ttu-id="78146-3168">试验。</span><span class="sxs-lookup"><span data-stu-id="78146-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="78146-3169">Com</span><span class="sxs-lookup"><span data-stu-id="78146-3169">com</span></span>
- <span data-ttu-id="78146-3170">s-int.</span><span class="sxs-lookup"><span data-stu-id="78146-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="78146-3171">网</span><span class="sxs-lookup"><span data-stu-id="78146-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="78146-3172">瑞典國民身分證號</span><span class="sxs-lookup"><span data-stu-id="78146-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="78146-3173">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3173">Format</span></span>

<span data-ttu-id="78146-3174">10 或 12 位数字和可选分隔符</span><span class="sxs-lookup"><span data-stu-id="78146-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3175">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3175">Pattern</span></span>

<span data-ttu-id="78146-3176">10 或 12 位数字和可选分隔符：</span><span class="sxs-lookup"><span data-stu-id="78146-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="78146-3177">2-4 位（可选）</span><span class="sxs-lookup"><span data-stu-id="78146-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="78146-3178">日期格式 YYMMDD 的六位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="78146-3179">"-"或"+"（可选）的分隔符，加上</span><span class="sxs-lookup"><span data-stu-id="78146-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="78146-3180">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3181">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3181">Checksum</span></span>

<span data-ttu-id="78146-3182">是</span><span class="sxs-lookup"><span data-stu-id="78146-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3183">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3183">Definition</span></span>

<span data-ttu-id="78146-3184">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3185">函数 Func_swedish_national_identifier 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3186">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3187">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3187">Keywords</span></span>

<span data-ttu-id="78146-3188">否</span><span class="sxs-lookup"><span data-stu-id="78146-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="78146-3189">瑞典護照號碼</span><span class="sxs-lookup"><span data-stu-id="78146-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3190">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3190">Format</span></span>

<span data-ttu-id="78146-3191">八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3192">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3192">Pattern</span></span>

<span data-ttu-id="78146-3193">连续八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3194">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3194">Checksum</span></span>

<span data-ttu-id="78146-3195">否</span><span class="sxs-lookup"><span data-stu-id="78146-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3196">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3196">Definition</span></span>

<span data-ttu-id="78146-3197">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3198">正则表达式 Regex_sweden_Passport_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3199">下列情况之一是正确的：</span><span class="sxs-lookup"><span data-stu-id="78146-3199">One of the following is true:</span></span>
    - <span data-ttu-id="78146-3200">找到关键字_Passport中一个关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="78146-3201">找到关键字_sweden_Passport 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3201">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-3202">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="78146-3203">关键词_瑞典护照</span><span class="sxs-lookup"><span data-stu-id="78146-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="78146-3204">签证要求</span><span class="sxs-lookup"><span data-stu-id="78146-3204">visa requirements</span></span> 
- <span data-ttu-id="78146-3205">外国人登记卡</span><span class="sxs-lookup"><span data-stu-id="78146-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="78146-3206">申根签证</span><span class="sxs-lookup"><span data-stu-id="78146-3206">Schengen visas</span></span> 
- <span data-ttu-id="78146-3207">申根签证</span><span class="sxs-lookup"><span data-stu-id="78146-3207">Schengen visa</span></span> 
- <span data-ttu-id="78146-3208">签证处理</span><span class="sxs-lookup"><span data-stu-id="78146-3208">Visa Processing</span></span> 
- <span data-ttu-id="78146-3209">签证类型</span><span class="sxs-lookup"><span data-stu-id="78146-3209">Visa Type</span></span> 
- <span data-ttu-id="78146-3210">单个条目</span><span class="sxs-lookup"><span data-stu-id="78146-3210">Single Entry</span></span> 
- <span data-ttu-id="78146-3211">多个条目</span><span class="sxs-lookup"><span data-stu-id="78146-3211">Multiple Entry</span></span> 
- <span data-ttu-id="78146-3212">G3 手续费</span><span class="sxs-lookup"><span data-stu-id="78146-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="78146-3213">关键词_护照</span><span class="sxs-lookup"><span data-stu-id="78146-3213">Keyword_passport</span></span>

- <span data-ttu-id="78146-3214">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-3214">Passport Number</span></span> 
- <span data-ttu-id="78146-3215">护照号</span><span class="sxs-lookup"><span data-stu-id="78146-3215">Passport No</span></span> 
- <span data-ttu-id="78146-3216">护照#</span><span class="sxs-lookup"><span data-stu-id="78146-3216">Passport #</span></span> 
- <span data-ttu-id="78146-3217">护照#</span><span class="sxs-lookup"><span data-stu-id="78146-3217">Passport#</span></span> 
- <span data-ttu-id="78146-3218">护照ID</span><span class="sxs-lookup"><span data-stu-id="78146-3218">PassportID</span></span> 
- <span data-ttu-id="78146-3219">护照诺</span><span class="sxs-lookup"><span data-stu-id="78146-3219">Passportno</span></span> 
- <span data-ttu-id="78146-3220">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-3220">passportnumber</span></span> 
- <span data-ttu-id="78146-3221">·</span><span class="sxs-lookup"><span data-stu-id="78146-3221">パスポート</span></span> 
- <span data-ttu-id="78146-3222">·\\\\\\\\\\\\\\\\\\\\\\</span><span class="sxs-lookup"><span data-stu-id="78146-3222">パスポート番号</span></span> 
- <span data-ttu-id="78146-3223">\* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="78146-3223">パスポートのNum</span></span> 
- <span data-ttu-id="78146-3224">·</span><span class="sxs-lookup"><span data-stu-id="78146-3224">パスポート＃</span></span> 
- <span data-ttu-id="78146-3225">努梅罗·德·德费波特</span><span class="sxs-lookup"><span data-stu-id="78146-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="78146-3226">路路港 n |</span><span class="sxs-lookup"><span data-stu-id="78146-3226">Passeport n °</span></span> 
- <span data-ttu-id="78146-3227">路路港非</span><span class="sxs-lookup"><span data-stu-id="78146-3227">Passeport Non</span></span> 
- <span data-ttu-id="78146-3228">帕塞波特#</span><span class="sxs-lookup"><span data-stu-id="78146-3228">Passeport #</span></span> 
- <span data-ttu-id="78146-3229">帕塞波特#</span><span class="sxs-lookup"><span data-stu-id="78146-3229">Passeport#</span></span> 
- <span data-ttu-id="78146-3230">帕塞波特农</span><span class="sxs-lookup"><span data-stu-id="78146-3230">PasseportNon</span></span> 
- <span data-ttu-id="78146-3231">帕塞波特 |</span><span class="sxs-lookup"><span data-stu-id="78146-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="78146-3232">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="78146-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="78146-3233">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3233">Format</span></span>

<span data-ttu-id="78146-3234">四个字母后跟 5-31 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="78146-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3235">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3235">Pattern</span></span>

<span data-ttu-id="78146-3236">四个字母后跟 5-31 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="78146-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="78146-3237">四个字母的银行代码（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="78146-3238">可选空间</span><span class="sxs-lookup"><span data-stu-id="78146-3238">An optional space</span></span> 
- <span data-ttu-id="78146-3239">4-28 个字母或数字（基本银行帐号 （BBAN））</span><span class="sxs-lookup"><span data-stu-id="78146-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="78146-3240">可选空间</span><span class="sxs-lookup"><span data-stu-id="78146-3240">An optional space</span></span> 
- <span data-ttu-id="78146-3241">1-3 个字母或数字（BBAN 的余数）</span><span class="sxs-lookup"><span data-stu-id="78146-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3242">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3242">Checksum</span></span>

<span data-ttu-id="78146-3243">否</span><span class="sxs-lookup"><span data-stu-id="78146-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3244">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3244">Definition</span></span>

<span data-ttu-id="78146-3245">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3246">正则表达式 Regex_swift 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3247">找到关键字_swift 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3248">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="78146-3249">关键字_swift</span><span class="sxs-lookup"><span data-stu-id="78146-3249">Keyword_swift</span></span>

- <span data-ttu-id="78146-3250">国际标准化组织 9362</span><span class="sxs-lookup"><span data-stu-id="78146-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="78146-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="78146-3251">iso 9362</span></span> 
- <span data-ttu-id="78146-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="78146-3252">iso9362</span></span> 
- <span data-ttu-id="78146-3253">迅速\#</span><span class="sxs-lookup"><span data-stu-id="78146-3253">swift\#</span></span> 
- <span data-ttu-id="78146-3254">快速码</span><span class="sxs-lookup"><span data-stu-id="78146-3254">swiftcode</span></span> 
- <span data-ttu-id="78146-3255">快速数</span><span class="sxs-lookup"><span data-stu-id="78146-3255">swiftnumber</span></span> 
- <span data-ttu-id="78146-3256">快速路由编号</span><span class="sxs-lookup"><span data-stu-id="78146-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="78146-3257">快速代码</span><span class="sxs-lookup"><span data-stu-id="78146-3257">swift code</span></span> 
- <span data-ttu-id="78146-3258">快速数#</span><span class="sxs-lookup"><span data-stu-id="78146-3258">swift number #</span></span> 
- <span data-ttu-id="78146-3259">快速路由编号</span><span class="sxs-lookup"><span data-stu-id="78146-3259">swift routing number</span></span> 
- <span data-ttu-id="78146-3260">二元数</span><span class="sxs-lookup"><span data-stu-id="78146-3260">bic number</span></span> 
- <span data-ttu-id="78146-3261">二元代码</span><span class="sxs-lookup"><span data-stu-id="78146-3261">bic code</span></span> 
- <span data-ttu-id="78146-3262">比奇\#</span><span class="sxs-lookup"><span data-stu-id="78146-3262">bic \#</span></span> 
- <span data-ttu-id="78146-3263">比奇\#</span><span class="sxs-lookup"><span data-stu-id="78146-3263">bic\#</span></span> 
- <span data-ttu-id="78146-3264">银行标识符代码</span><span class="sxs-lookup"><span data-stu-id="78146-3264">bank identifier code</span></span> 
- <span data-ttu-id="78146-3265">·09362</span><span class="sxs-lookup"><span data-stu-id="78146-3265">標準化9362</span></span> 
- <span data-ttu-id="78146-3266">\*</span><span class="sxs-lookup"><span data-stu-id="78146-3266">迅速＃</span></span> 
- <span data-ttu-id="78146-3267">SWIFT |</span><span class="sxs-lookup"><span data-stu-id="78146-3267">SWIFTコード</span></span> 
- <span data-ttu-id="78146-3268">斯威夫特</span><span class="sxs-lookup"><span data-stu-id="78146-3268">SWIFT番号</span></span> 
- <span data-ttu-id="78146-3269">\*</span><span class="sxs-lookup"><span data-stu-id="78146-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="78146-3270">BIC_</span><span class="sxs-lookup"><span data-stu-id="78146-3270">BIC番号</span></span> 
- <span data-ttu-id="78146-3271">BIC |</span><span class="sxs-lookup"><span data-stu-id="78146-3271">BICコード</span></span> 
- <span data-ttu-id="78146-3272">\*\* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="78146-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="78146-3273">国际正常化组织 9362</span><span class="sxs-lookup"><span data-stu-id="78146-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="78146-3274">快速\#</span><span class="sxs-lookup"><span data-stu-id="78146-3274">rapide \#</span></span> 
- <span data-ttu-id="78146-3275">代码 SWIFT</span><span class="sxs-lookup"><span data-stu-id="78146-3275">code SWIFT</span></span> 
- <span data-ttu-id="78146-3276">勒努梅罗·德·斯威夫特</span><span class="sxs-lookup"><span data-stu-id="78146-3276">le numéro de swift</span></span> 
- <span data-ttu-id="78146-3277">迅速的numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="78146-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="78146-3278">勒努梅罗BIC</span><span class="sxs-lookup"><span data-stu-id="78146-3278">le numéro BIC</span></span> 
- <span data-ttu-id="78146-3279">\#BIC</span><span class="sxs-lookup"><span data-stu-id="78146-3279">\# BIC</span></span> 
- <span data-ttu-id="78146-3280">代码识别器 de banque</span><span class="sxs-lookup"><span data-stu-id="78146-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="78146-3281">台湾国民身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="78146-3282">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3282">Format</span></span>

<span data-ttu-id="78146-3283">一个字母（英文）后跟九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3284">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3284">Pattern</span></span>

<span data-ttu-id="78146-3285">一个字母（英文）后跟九位数字：</span><span class="sxs-lookup"><span data-stu-id="78146-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="78146-3286">一个字母（英文，不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="78146-3287">数字"1"或"2"</span><span class="sxs-lookup"><span data-stu-id="78146-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="78146-3288">八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3289">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3289">Checksum</span></span>

<span data-ttu-id="78146-3290">是</span><span class="sxs-lookup"><span data-stu-id="78146-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3291">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3291">Definition</span></span>

<span data-ttu-id="78146-3292">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3293">函数 Func_t_t_national_id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3294">找到关键字_台湾_国家_id的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="78146-3295">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3296">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="78146-3297">关键字_台湾_国家_id</span><span class="sxs-lookup"><span data-stu-id="78146-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="78146-3298">·007年</span><span class="sxs-lookup"><span data-stu-id="78146-3298">身份證字號</span></span> 
- <span data-ttu-id="78146-3299">·</span><span class="sxs-lookup"><span data-stu-id="78146-3299">身份證</span></span> 
- <span data-ttu-id="78146-3300">·</span><span class="sxs-lookup"><span data-stu-id="78146-3300">身份證號碼</span></span> 
- <span data-ttu-id="78146-3301">|</span><span class="sxs-lookup"><span data-stu-id="78146-3301">身份證號</span></span> 
- <span data-ttu-id="78146-3302">·</span><span class="sxs-lookup"><span data-stu-id="78146-3302">身分證字號</span></span> 
- <span data-ttu-id="78146-3303">·</span><span class="sxs-lookup"><span data-stu-id="78146-3303">身分證</span></span> 
- <span data-ttu-id="78146-3304">·</span><span class="sxs-lookup"><span data-stu-id="78146-3304">身分證號碼</span></span> 
- <span data-ttu-id="78146-3305">|</span><span class="sxs-lookup"><span data-stu-id="78146-3305">身份證號</span></span> 
- <span data-ttu-id="78146-3306">[ ]</span><span class="sxs-lookup"><span data-stu-id="78146-3306">身分證統一編號</span></span> 
- <span data-ttu-id="78146-3307">[ ]</span><span class="sxs-lookup"><span data-stu-id="78146-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="78146-3308">·</span><span class="sxs-lookup"><span data-stu-id="78146-3308">簽名</span></span> 
- <span data-ttu-id="78146-3309">·000年</span><span class="sxs-lookup"><span data-stu-id="78146-3309">蓋章</span></span> 
- <span data-ttu-id="78146-3310">\*</span><span class="sxs-lookup"><span data-stu-id="78146-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="78146-3311">·000年</span><span class="sxs-lookup"><span data-stu-id="78146-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="78146-3312">台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3313">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3313">Format</span></span>

- <span data-ttu-id="78146-3314">生物识别护照号码：九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="78146-3315">非生物护照号码：九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3316">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3316">Pattern</span></span>
<span data-ttu-id="78146-3317">生物识别护照号码：</span><span class="sxs-lookup"><span data-stu-id="78146-3317">Biometric passport number:</span></span>
- <span data-ttu-id="78146-3318">数字"3"</span><span class="sxs-lookup"><span data-stu-id="78146-3318">The digit "3"</span></span> 
- <span data-ttu-id="78146-3319">八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3319">Eight digits</span></span>

<span data-ttu-id="78146-3320">非生物护照号码：</span><span class="sxs-lookup"><span data-stu-id="78146-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="78146-3321">九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3322">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3322">Checksum</span></span>

<span data-ttu-id="78146-3323">否</span><span class="sxs-lookup"><span data-stu-id="78146-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3324">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3324">Definition</span></span>

<span data-ttu-id="78146-3325">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3326">正则表达式 Regex_taiwan_Passport 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3327">找到关键字_taiwan_Passport的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3328">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="78146-3329">关键词_台湾护照</span><span class="sxs-lookup"><span data-stu-id="78146-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="78146-3330">中华民国护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-3330">ROC passport number</span></span> 
- <span data-ttu-id="78146-3331">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-3331">Passport number</span></span> 
- <span data-ttu-id="78146-3332">护照无</span><span class="sxs-lookup"><span data-stu-id="78146-3332">Passport no</span></span> 
- <span data-ttu-id="78146-3333">护照数量</span><span class="sxs-lookup"><span data-stu-id="78146-3333">Passport Num</span></span> 
- <span data-ttu-id="78146-3334">护照#</span><span class="sxs-lookup"><span data-stu-id="78146-3334">Passport #</span></span> 
- <span data-ttu-id="78146-3335">·</span><span class="sxs-lookup"><span data-stu-id="78146-3335">护照</span></span> 
- <span data-ttu-id="78146-3336">·</span><span class="sxs-lookup"><span data-stu-id="78146-3336">中華民國護照</span></span> 
- <span data-ttu-id="78146-3337">赞胡埃·明古什·哈佐</span><span class="sxs-lookup"><span data-stu-id="78146-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="78146-3338">台湾居民证（ARC/TARC）号码</span><span class="sxs-lookup"><span data-stu-id="78146-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3339">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3339">Format</span></span>

<span data-ttu-id="78146-3340">10 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="78146-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3341">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3341">Pattern</span></span>

<span data-ttu-id="78146-3342">10 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="78146-3342">10 letters and digits:</span></span>
- <span data-ttu-id="78146-3343">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="78146-3344">八位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3345">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3345">Checksum</span></span>

<span data-ttu-id="78146-3346">否</span><span class="sxs-lookup"><span data-stu-id="78146-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3347">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3347">Definition</span></span>

<span data-ttu-id="78146-3348">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3349">正则表达式 Regex_TAIWAN_驻留_证书查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3350">找到关键字_taiwan_居民\证书中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3351">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="78146-3352">关键词_台湾_居民_证书</span><span class="sxs-lookup"><span data-stu-id="78146-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="78146-3353">居民证</span><span class="sxs-lookup"><span data-stu-id="78146-3353">Resident Certificate</span></span> 
- <span data-ttu-id="78146-3354">居民证书</span><span class="sxs-lookup"><span data-stu-id="78146-3354">Resident Cert</span></span> 
- <span data-ttu-id="78146-3355">居民证书。</span><span class="sxs-lookup"><span data-stu-id="78146-3355">Resident Cert.</span></span> 
- <span data-ttu-id="78146-3356">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3356">Identification card</span></span> 
- <span data-ttu-id="78146-3357">外国人居住证明</span><span class="sxs-lookup"><span data-stu-id="78146-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="78146-3358">弧</span><span class="sxs-lookup"><span data-stu-id="78146-3358">ARC</span></span> 
- <span data-ttu-id="78146-3359">台湾地区居民证</span><span class="sxs-lookup"><span data-stu-id="78146-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="78146-3360">TARC</span><span class="sxs-lookup"><span data-stu-id="78146-3360">TARC</span></span> 
- <span data-ttu-id="78146-3361">·</span><span class="sxs-lookup"><span data-stu-id="78146-3361">居留證</span></span> 
- <span data-ttu-id="78146-3362">·\*</span><span class="sxs-lookup"><span data-stu-id="78146-3362">外僑居留證</span></span> 
- <span data-ttu-id="78146-3363">[</span><span class="sxs-lookup"><span data-stu-id="78146-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="78146-3364">泰国人口识别码</span><span class="sxs-lookup"><span data-stu-id="78146-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="78146-3365">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3365">Format</span></span>

<span data-ttu-id="78146-3366">13 位</span><span class="sxs-lookup"><span data-stu-id="78146-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3367">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3367">Pattern</span></span>

<span data-ttu-id="78146-3368">13 位：</span><span class="sxs-lookup"><span data-stu-id="78146-3368">13 digits:</span></span>
- <span data-ttu-id="78146-3369">第一个数字不是 0 或 9</span><span class="sxs-lookup"><span data-stu-id="78146-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="78146-3370">12 位</span><span class="sxs-lookup"><span data-stu-id="78146-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3371">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3371">Checksum</span></span>

<span data-ttu-id="78146-3372">是</span><span class="sxs-lookup"><span data-stu-id="78146-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3373">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3373">Definition</span></span>

<span data-ttu-id="78146-3374">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3375">函数 Func_Thai_Citizen_Id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3376">找到关键字_泰语_公民\Id的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="78146-3377">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3378">函数 Func_Thai_Citizen_Id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-3379">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="78146-3380">关键词_泰语+公民\ID</span><span class="sxs-lookup"><span data-stu-id="78146-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="78146-3381">身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-3381">ID Number</span></span>
- <span data-ttu-id="78146-3382">识别号</span><span class="sxs-lookup"><span data-stu-id="78146-3382">Identification Number</span></span>
- <span data-ttu-id="78146-3383">《》</span><span class="sxs-lookup"><span data-stu-id="78146-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="78146-3384">《》</span><span class="sxs-lookup"><span data-stu-id="78146-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="78146-3385">《》</span><span class="sxs-lookup"><span data-stu-id="78146-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="78146-3386">《》</span><span class="sxs-lookup"><span data-stu-id="78146-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="78146-3387">土耳其国民身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3388">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3388">Format</span></span>

<span data-ttu-id="78146-3389">11 位</span><span class="sxs-lookup"><span data-stu-id="78146-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3390">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3390">Pattern</span></span>

<span data-ttu-id="78146-3391">11 位</span><span class="sxs-lookup"><span data-stu-id="78146-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3392">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3392">Checksum</span></span>

<span data-ttu-id="78146-3393">是</span><span class="sxs-lookup"><span data-stu-id="78146-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3394">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3394">Definition</span></span>

<span data-ttu-id="78146-3395">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3396">函数 Func_土耳其_National_Id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3397">找到关键字_土耳其语_国家_Id的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="78146-3398">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3399">函数 Func_土耳其_National_Id 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-3400">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="78146-3401">关键字_土耳其语_国家_ID</span><span class="sxs-lookup"><span data-stu-id="78146-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="78146-3402">TC 金利克 否</span><span class="sxs-lookup"><span data-stu-id="78146-3402">TC Kimlik No</span></span>
- <span data-ttu-id="78146-3403">TC 金利克·努马拉斯</span><span class="sxs-lookup"><span data-stu-id="78146-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="78146-3404">瓦坦达莱克·努马拉斯</span><span class="sxs-lookup"><span data-stu-id="78146-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="78146-3405">瓦坦达莱克 否</span><span class="sxs-lookup"><span data-stu-id="78146-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="78146-3406">英国。</span><span class="sxs-lookup"><span data-stu-id="78146-3406">U.K.</span></span> <span data-ttu-id="78146-3407">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="78146-3407">Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3408">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3408">Format</span></span>

<span data-ttu-id="78146-3409">指定格式的 18 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="78146-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3410">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3410">Pattern</span></span>

<span data-ttu-id="78146-3411">18 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="78146-3411">18 letters and digits:</span></span>
- <span data-ttu-id="78146-3412">五个字母（不区分大小写）或数字"9"代替字母</span><span class="sxs-lookup"><span data-stu-id="78146-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="78146-3413">一位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3413">One digit</span></span> 
- <span data-ttu-id="78146-3414">出生日期日期格式 DDMMY 中的五位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3414">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="78146-3415">两个字母（不区分大小写）或数字"9"代替字母</span><span class="sxs-lookup"><span data-stu-id="78146-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="78146-3416">五位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3417">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3417">Checksum</span></span>

<span data-ttu-id="78146-3418">是</span><span class="sxs-lookup"><span data-stu-id="78146-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3419">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3419">Definition</span></span>

<span data-ttu-id="78146-3420">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3421">函数 Func_uk_驱动程序_许可证查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3422">找到关键字_uk_驱动程序_许可证的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="78146-3423">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3424">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="78146-3425">关键字_uk_驱动程序_许可证</span><span class="sxs-lookup"><span data-stu-id="78146-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="78146-3426">DVLA</span><span class="sxs-lookup"><span data-stu-id="78146-3426">DVLA</span></span> 
- <span data-ttu-id="78146-3427">轻型货车</span><span class="sxs-lookup"><span data-stu-id="78146-3427">light vans</span></span> 
- <span data-ttu-id="78146-3428">四轮摩托车</span><span class="sxs-lookup"><span data-stu-id="78146-3428">quadbikes</span></span> 
- <span data-ttu-id="78146-3429">汽车</span><span class="sxs-lookup"><span data-stu-id="78146-3429">motor cars</span></span> 
- <span data-ttu-id="78146-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="78146-3430">125cc</span></span> 
- <span data-ttu-id="78146-3431">侧车</span><span class="sxs-lookup"><span data-stu-id="78146-3431">sidecar</span></span> 
- <span data-ttu-id="78146-3432">三轮车</span><span class="sxs-lookup"><span data-stu-id="78146-3432">tricycles</span></span> 
- <span data-ttu-id="78146-3433">摩托车</span><span class="sxs-lookup"><span data-stu-id="78146-3433">motorcycles</span></span> 
- <span data-ttu-id="78146-3434">照片卡许可证</span><span class="sxs-lookup"><span data-stu-id="78146-3434">photocard licence</span></span> 
- <span data-ttu-id="78146-3435">学员驱动程序</span><span class="sxs-lookup"><span data-stu-id="78146-3435">learner drivers</span></span> 
- <span data-ttu-id="78146-3436">牌照持有人</span><span class="sxs-lookup"><span data-stu-id="78146-3436">licence holder</span></span> 
- <span data-ttu-id="78146-3437">牌照持有人</span><span class="sxs-lookup"><span data-stu-id="78146-3437">licence holders</span></span> 
- <span data-ttu-id="78146-3438">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3438">driving licences</span></span> 
- <span data-ttu-id="78146-3439">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3439">driving licence</span></span> 
- <span data-ttu-id="78146-3440">双控制车</span><span class="sxs-lookup"><span data-stu-id="78146-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="78146-3441">英国。</span><span class="sxs-lookup"><span data-stu-id="78146-3441">U.K.</span></span> <span data-ttu-id="78146-3442">选举人名册号码</span><span class="sxs-lookup"><span data-stu-id="78146-3442">Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3443">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3443">Format</span></span>

<span data-ttu-id="78146-3444">两个字母后跟 1-4 位</span><span class="sxs-lookup"><span data-stu-id="78146-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3445">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3445">Pattern</span></span>

<span data-ttu-id="78146-3446">两个字母（不区分大小写）后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="78146-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3447">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3447">Checksum</span></span>

<span data-ttu-id="78146-3448">否</span><span class="sxs-lookup"><span data-stu-id="78146-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3449">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3449">Definition</span></span>

<span data-ttu-id="78146-3450">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3451">正则表达式 Regex_uk_选举查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3452">找到关键字_uk_选举的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3452">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-3453">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="78146-3454">关键字_uk_选举</span><span class="sxs-lookup"><span data-stu-id="78146-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="78146-3455">理事会提名</span><span class="sxs-lookup"><span data-stu-id="78146-3455">council nomination</span></span> 
- <span data-ttu-id="78146-3456">提名表格</span><span class="sxs-lookup"><span data-stu-id="78146-3456">nomination form</span></span> 
- <span data-ttu-id="78146-3457">选举登记册</span><span class="sxs-lookup"><span data-stu-id="78146-3457">electoral register</span></span> 
- <span data-ttu-id="78146-3458">选举名册</span><span class="sxs-lookup"><span data-stu-id="78146-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="78146-3459">英国。</span><span class="sxs-lookup"><span data-stu-id="78146-3459">U.K.</span></span> <span data-ttu-id="78146-3460">国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="78146-3460">National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3461">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3461">Format</span></span>

<span data-ttu-id="78146-3462">10-17 位由空格分隔的数字</span><span class="sxs-lookup"><span data-stu-id="78146-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3463">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3463">Pattern</span></span>

<span data-ttu-id="78146-3464">10-17 位：</span><span class="sxs-lookup"><span data-stu-id="78146-3464">10-17 digits:</span></span>
- <span data-ttu-id="78146-3465">3 位或 10 位</span><span class="sxs-lookup"><span data-stu-id="78146-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="78146-3466">空间</span><span class="sxs-lookup"><span data-stu-id="78146-3466">A space</span></span> 
- <span data-ttu-id="78146-3467">三位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3467">Three digits</span></span> 
- <span data-ttu-id="78146-3468">空间</span><span class="sxs-lookup"><span data-stu-id="78146-3468">A space</span></span> 
- <span data-ttu-id="78146-3469">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3470">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3470">Checksum</span></span>

<span data-ttu-id="78146-3471">是</span><span class="sxs-lookup"><span data-stu-id="78146-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3472">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3472">Definition</span></span>

<span data-ttu-id="78146-3473">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3474">函数 Func_uk_nhs_number 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3475">下列情况之一是正确的：</span><span class="sxs-lookup"><span data-stu-id="78146-3475">One of the following is true:</span></span>
    - <span data-ttu-id="78146-3476">找到关键字_uk_nhs_号码的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="78146-3477">找到关键字_uk_nhs_number1的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="78146-3478">找到关键字_uk_nhs_number_dob 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="78146-3479">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="78146-3479">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-3480">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="78146-3481">关键字_uk_nhs_数字</span><span class="sxs-lookup"><span data-stu-id="78146-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="78146-3482">国家卫生服务</span><span class="sxs-lookup"><span data-stu-id="78146-3482">national health service</span></span> 
- <span data-ttu-id="78146-3483">Nhs</span><span class="sxs-lookup"><span data-stu-id="78146-3483">nhs</span></span> 
- <span data-ttu-id="78146-3484">卫生服务管理局</span><span class="sxs-lookup"><span data-stu-id="78146-3484">health services authority</span></span> 
- <span data-ttu-id="78146-3485">卫生当局</span><span class="sxs-lookup"><span data-stu-id="78146-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="78146-3486">关键字_uk_nhs_数字1</span><span class="sxs-lookup"><span data-stu-id="78146-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="78146-3487">患者 ID</span><span class="sxs-lookup"><span data-stu-id="78146-3487">patient id</span></span> 
- <span data-ttu-id="78146-3488">患者识别</span><span class="sxs-lookup"><span data-stu-id="78146-3488">patient identification</span></span> 
- <span data-ttu-id="78146-3489">患者无</span><span class="sxs-lookup"><span data-stu-id="78146-3489">patient no</span></span> 
- <span data-ttu-id="78146-3490">患者人数</span><span class="sxs-lookup"><span data-stu-id="78146-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="78146-3491">关键词_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="78146-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="78146-3492">Gp</span><span class="sxs-lookup"><span data-stu-id="78146-3492">GP</span></span> 
- <span data-ttu-id="78146-3493">DOB</span><span class="sxs-lookup"><span data-stu-id="78146-3493">DOB</span></span> 
- <span data-ttu-id="78146-3494">D.O.B</span><span class="sxs-lookup"><span data-stu-id="78146-3494">D.O.B</span></span> 
- <span data-ttu-id="78146-3495">出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-3495">Date of Birth</span></span> 
- <span data-ttu-id="78146-3496">出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="78146-3497">英国。</span><span class="sxs-lookup"><span data-stu-id="78146-3497">U.K.</span></span> <span data-ttu-id="78146-3498">国民保险号码</span><span class="sxs-lookup"><span data-stu-id="78146-3498">National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="78146-3499">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3499">Format</span></span>

<span data-ttu-id="78146-3500">7 个字符或 9 个字符，由空格或破折号分隔</span><span class="sxs-lookup"><span data-stu-id="78146-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3501">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3501">Pattern</span></span>

<span data-ttu-id="78146-3502">两种可能的模式：</span><span class="sxs-lookup"><span data-stu-id="78146-3502">Two possible patterns:</span></span>

- <span data-ttu-id="78146-3503">两个字母（有效的 NINOs 仅使用前缀中的某些字符，此模式可验证该字符;不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="78146-3504">六位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3504">Six digits</span></span>
- <span data-ttu-id="78146-3505">"A"、"B"，"C"或"D"（与前缀一样，后缀中只允许某些字符;不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="78146-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="78146-3506">或</span><span class="sxs-lookup"><span data-stu-id="78146-3506">OR</span></span>

- <span data-ttu-id="78146-3507">两个字母</span><span class="sxs-lookup"><span data-stu-id="78146-3507">Two letters</span></span>
- <span data-ttu-id="78146-3508">空格或破折号</span><span class="sxs-lookup"><span data-stu-id="78146-3508">A space or dash</span></span>
- <span data-ttu-id="78146-3509">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3509">Two digits</span></span>
- <span data-ttu-id="78146-3510">空格或破折号</span><span class="sxs-lookup"><span data-stu-id="78146-3510">A space or dash</span></span>
- <span data-ttu-id="78146-3511">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3511">Two digits</span></span>
- <span data-ttu-id="78146-3512">空格或破折号</span><span class="sxs-lookup"><span data-stu-id="78146-3512">A space or dash</span></span>
- <span data-ttu-id="78146-3513">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3513">Two digits</span></span>
- <span data-ttu-id="78146-3514">空格或破折号</span><span class="sxs-lookup"><span data-stu-id="78146-3514">A space or dash</span></span>
- <span data-ttu-id="78146-3515">"A"，"B"，"C"或"D"</span><span class="sxs-lookup"><span data-stu-id="78146-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3516">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3516">Checksum</span></span>

<span data-ttu-id="78146-3517">否</span><span class="sxs-lookup"><span data-stu-id="78146-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3518">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3518">Definition</span></span>

<span data-ttu-id="78146-3519">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3520">函数 Func_uk_nino 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3521">找到关键字_uk_nino 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="78146-3522">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3523">函数 Func_uk_nino 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3524">找不到来自关键字_uk_nino 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3524">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-3525">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="78146-3526">关键词_uk_nino</span><span class="sxs-lookup"><span data-stu-id="78146-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="78146-3527">国民保险号</span><span class="sxs-lookup"><span data-stu-id="78146-3527">national insurance number</span></span> 
- <span data-ttu-id="78146-3528">国家保险缴款</span><span class="sxs-lookup"><span data-stu-id="78146-3528">national insurance contributions</span></span> 
- <span data-ttu-id="78146-3529">保护法</span><span class="sxs-lookup"><span data-stu-id="78146-3529">protection act</span></span> 
- <span data-ttu-id="78146-3530">保险</span><span class="sxs-lookup"><span data-stu-id="78146-3530">insurance</span></span> 
- <span data-ttu-id="78146-3531">社会安全号码</span><span class="sxs-lookup"><span data-stu-id="78146-3531">social security number</span></span> 
- <span data-ttu-id="78146-3532">保险申请</span><span class="sxs-lookup"><span data-stu-id="78146-3532">insurance application</span></span> 
- <span data-ttu-id="78146-3533">医疗应用</span><span class="sxs-lookup"><span data-stu-id="78146-3533">medical application</span></span> 
- <span data-ttu-id="78146-3534">社会保险</span><span class="sxs-lookup"><span data-stu-id="78146-3534">social insurance</span></span> 
- <span data-ttu-id="78146-3535">医疗护理</span><span class="sxs-lookup"><span data-stu-id="78146-3535">medical attention</span></span> 
- <span data-ttu-id="78146-3536">社会保障</span><span class="sxs-lookup"><span data-stu-id="78146-3536">social security</span></span> 
- <span data-ttu-id="78146-3537">英国</span><span class="sxs-lookup"><span data-stu-id="78146-3537">great britain</span></span> 
- <span data-ttu-id="78146-3538">保险</span><span class="sxs-lookup"><span data-stu-id="78146-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="78146-3539">美国/英国</span><span class="sxs-lookup"><span data-stu-id="78146-3539">U.S. / U.K.</span></span> <span data-ttu-id="78146-3540">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-3540">Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3541">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3541">Format</span></span>

<span data-ttu-id="78146-3542">九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3543">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3543">Pattern</span></span>

<span data-ttu-id="78146-3544">连续九位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3545">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3545">Checksum</span></span>

<span data-ttu-id="78146-3546">否</span><span class="sxs-lookup"><span data-stu-id="78146-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3547">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3547">Definition</span></span>

<span data-ttu-id="78146-3548">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3549">函数 Func_usa_uk_passport 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3550">找到关键字_Passport中一个关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3551">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="78146-3552">关键词_护照</span><span class="sxs-lookup"><span data-stu-id="78146-3552">Keyword_passport</span></span>

- <span data-ttu-id="78146-3553">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-3553">Passport Number</span></span> 
- <span data-ttu-id="78146-3554">护照号</span><span class="sxs-lookup"><span data-stu-id="78146-3554">Passport No</span></span> 
- <span data-ttu-id="78146-3555">护照#</span><span class="sxs-lookup"><span data-stu-id="78146-3555">Passport #</span></span> 
- <span data-ttu-id="78146-3556">护照#</span><span class="sxs-lookup"><span data-stu-id="78146-3556">Passport#</span></span> 
- <span data-ttu-id="78146-3557">护照ID</span><span class="sxs-lookup"><span data-stu-id="78146-3557">PassportID</span></span> 
- <span data-ttu-id="78146-3558">护照诺</span><span class="sxs-lookup"><span data-stu-id="78146-3558">Passportno</span></span> 
- <span data-ttu-id="78146-3559">护照号码</span><span class="sxs-lookup"><span data-stu-id="78146-3559">passportnumber</span></span> 
- <span data-ttu-id="78146-3560">·</span><span class="sxs-lookup"><span data-stu-id="78146-3560">パスポート</span></span> 
- <span data-ttu-id="78146-3561">·\\\\\\\\\\\\\\\\\\\\\\</span><span class="sxs-lookup"><span data-stu-id="78146-3561">パスポート番号</span></span> 
- <span data-ttu-id="78146-3562">\* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="78146-3562">パスポートのNum</span></span> 
- <span data-ttu-id="78146-3563">·</span><span class="sxs-lookup"><span data-stu-id="78146-3563">パスポート＃</span></span> 
- <span data-ttu-id="78146-3564">努梅罗·德·德费波特</span><span class="sxs-lookup"><span data-stu-id="78146-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="78146-3565">路路港 n |</span><span class="sxs-lookup"><span data-stu-id="78146-3565">Passeport n °</span></span> 
- <span data-ttu-id="78146-3566">路路港非</span><span class="sxs-lookup"><span data-stu-id="78146-3566">Passeport Non</span></span> 
- <span data-ttu-id="78146-3567">帕塞波特#</span><span class="sxs-lookup"><span data-stu-id="78146-3567">Passeport #</span></span> 
- <span data-ttu-id="78146-3568">帕塞波特#</span><span class="sxs-lookup"><span data-stu-id="78146-3568">Passeport#</span></span> 
- <span data-ttu-id="78146-3569">帕塞波特农</span><span class="sxs-lookup"><span data-stu-id="78146-3569">PasseportNon</span></span> 
- <span data-ttu-id="78146-3570">帕塞波特 |</span><span class="sxs-lookup"><span data-stu-id="78146-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="78146-3571">美国银行账户号码</span><span class="sxs-lookup"><span data-stu-id="78146-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3572">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3572">Format</span></span>

<span data-ttu-id="78146-3573">8-17 位</span><span class="sxs-lookup"><span data-stu-id="78146-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3574">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3574">Pattern</span></span>

<span data-ttu-id="78146-3575">8-17 个连续数字</span><span class="sxs-lookup"><span data-stu-id="78146-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3576">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3576">Checksum</span></span>

<span data-ttu-id="78146-3577">否</span><span class="sxs-lookup"><span data-stu-id="78146-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3578">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3578">Definition</span></span>

<span data-ttu-id="78146-3579">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3580">正则表达式 Regex_usa_bank_帐户_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3581">找到关键字_usa_Bank_帐户的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3582">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="78146-3583">关键字_usa_银行_帐户</span><span class="sxs-lookup"><span data-stu-id="78146-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="78146-3584">支票帐号</span><span class="sxs-lookup"><span data-stu-id="78146-3584">Checking Account Number</span></span> 
- <span data-ttu-id="78146-3585">支票帐户</span><span class="sxs-lookup"><span data-stu-id="78146-3585">Checking Account</span></span> 
- <span data-ttu-id="78146-3586">支票帐户#</span><span class="sxs-lookup"><span data-stu-id="78146-3586">Checking Account #</span></span> 
- <span data-ttu-id="78146-3587">检查 Acct 编号</span><span class="sxs-lookup"><span data-stu-id="78146-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="78146-3588">检查 Acct#</span><span class="sxs-lookup"><span data-stu-id="78146-3588">Checking Acct #</span></span> 
- <span data-ttu-id="78146-3589">检查 Acct 号</span><span class="sxs-lookup"><span data-stu-id="78146-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="78146-3590">支票帐户号</span><span class="sxs-lookup"><span data-stu-id="78146-3590">Checking Account No.</span></span> 
- <span data-ttu-id="78146-3591">银行帐号</span><span class="sxs-lookup"><span data-stu-id="78146-3591">Bank Account Number</span></span> 
- <span data-ttu-id="78146-3592">银行账户#</span><span class="sxs-lookup"><span data-stu-id="78146-3592">Bank Account #</span></span> 
- <span data-ttu-id="78146-3593">银行编号</span><span class="sxs-lookup"><span data-stu-id="78146-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="78146-3594">银行 Acct#</span><span class="sxs-lookup"><span data-stu-id="78146-3594">Bank Acct #</span></span> 
- <span data-ttu-id="78146-3595">银行增加号</span><span class="sxs-lookup"><span data-stu-id="78146-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="78146-3596">银行账户号</span><span class="sxs-lookup"><span data-stu-id="78146-3596">Bank Account No.</span></span> 
- <span data-ttu-id="78146-3597">储蓄帐号</span><span class="sxs-lookup"><span data-stu-id="78146-3597">Savings Account Number</span></span> 
- <span data-ttu-id="78146-3598">储蓄账户。</span><span class="sxs-lookup"><span data-stu-id="78146-3598">Savings Account.</span></span> 
- <span data-ttu-id="78146-3599">储蓄账户#</span><span class="sxs-lookup"><span data-stu-id="78146-3599">Savings Account #</span></span> 
- <span data-ttu-id="78146-3600">节省费用编号</span><span class="sxs-lookup"><span data-stu-id="78146-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="78146-3601">节省费用#</span><span class="sxs-lookup"><span data-stu-id="78146-3601">Savings Acct #</span></span> 
- <span data-ttu-id="78146-3602">节省费用</span><span class="sxs-lookup"><span data-stu-id="78146-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="78146-3603">储蓄账户号</span><span class="sxs-lookup"><span data-stu-id="78146-3603">Savings Account No.</span></span> 
- <span data-ttu-id="78146-3604">借方帐号</span><span class="sxs-lookup"><span data-stu-id="78146-3604">Debit Account Number</span></span> 
- <span data-ttu-id="78146-3605">借方帐户</span><span class="sxs-lookup"><span data-stu-id="78146-3605">Debit Account</span></span> 
- <span data-ttu-id="78146-3606">借方帐户#</span><span class="sxs-lookup"><span data-stu-id="78146-3606">Debit Account #</span></span> 
- <span data-ttu-id="78146-3607">借方扣号</span><span class="sxs-lookup"><span data-stu-id="78146-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="78146-3608">借方 Acct#</span><span class="sxs-lookup"><span data-stu-id="78146-3608">Debit Acct #</span></span> 
- <span data-ttu-id="78146-3609">借方确认号</span><span class="sxs-lookup"><span data-stu-id="78146-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="78146-3610">借方帐户号</span><span class="sxs-lookup"><span data-stu-id="78146-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="78146-3611">美国驾照号码</span><span class="sxs-lookup"><span data-stu-id="78146-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="78146-3612">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3612">Format</span></span>

<span data-ttu-id="78146-3613">取决于状态</span><span class="sxs-lookup"><span data-stu-id="78146-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3614">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3614">Pattern</span></span>

<span data-ttu-id="78146-3615">取决于州 - 例如，纽约：</span><span class="sxs-lookup"><span data-stu-id="78146-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="78146-3616">九位格式为 ddd ddd dd 的数字将匹配。</span><span class="sxs-lookup"><span data-stu-id="78146-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="78146-3617">九位数字（如 ddddddddd）将不匹配。</span><span class="sxs-lookup"><span data-stu-id="78146-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3618">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3618">Checksum</span></span>

<span data-ttu-id="78146-3619">否</span><span class="sxs-lookup"><span data-stu-id="78146-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3620">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3620">Definition</span></span>

<span data-ttu-id="78146-3621">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3622">函数 Func_new_york_驱动程序_许可证_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3623">找到关键字_状态_名称_驱动程序_许可证_名称的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="78146-3624">找到关键字_us_驱动程序_许可证的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="78146-3625">如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3626">函数 Func_new_york_驱动程序_许可证_编号查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3627">找到关键字_状态_名称_驱动程序_许可证_名称的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="78146-3628">找到关键字_us_驱动程序_许可证_缩写的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="78146-3629">找不到关键字_us_驱动程序_许可证的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
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
```

### <a name="keywords"></a><span data-ttu-id="78146-3630">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="78146-3631">关键字_us_驱动程序_许可证_缩写</span><span class="sxs-lookup"><span data-stu-id="78146-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="78146-3632">Dl</span><span class="sxs-lookup"><span data-stu-id="78146-3632">DL</span></span> 
- <span data-ttu-id="78146-3633">Dls</span><span class="sxs-lookup"><span data-stu-id="78146-3633">DLS</span></span> 
- <span data-ttu-id="78146-3634">民盟</span><span class="sxs-lookup"><span data-stu-id="78146-3634">CDL</span></span> 
- <span data-ttu-id="78146-3635">CDLS</span><span class="sxs-lookup"><span data-stu-id="78146-3635">CDLS</span></span> 
- <span data-ttu-id="78146-3636">ID</span><span class="sxs-lookup"><span data-stu-id="78146-3636">ID</span></span> 
- <span data-ttu-id="78146-3637">Id</span><span class="sxs-lookup"><span data-stu-id="78146-3637">IDs</span></span> 
- <span data-ttu-id="78146-3638">Dl#</span><span class="sxs-lookup"><span data-stu-id="78146-3638">DL#</span></span> 
- <span data-ttu-id="78146-3639">Dls#</span><span class="sxs-lookup"><span data-stu-id="78146-3639">DLS#</span></span> 
- <span data-ttu-id="78146-3640">民盟#</span><span class="sxs-lookup"><span data-stu-id="78146-3640">CDL#</span></span> 
- <span data-ttu-id="78146-3641">CDLS#</span><span class="sxs-lookup"><span data-stu-id="78146-3641">CDLS#</span></span> 
- <span data-ttu-id="78146-3642">Id#</span><span class="sxs-lookup"><span data-stu-id="78146-3642">ID#</span></span>
- <span data-ttu-id="78146-3643">Id#</span><span class="sxs-lookup"><span data-stu-id="78146-3643">IDs#</span></span> 
- <span data-ttu-id="78146-3644">識別碼</span><span class="sxs-lookup"><span data-stu-id="78146-3644">ID number</span></span> 
- <span data-ttu-id="78146-3645">身份证号码</span><span class="sxs-lookup"><span data-stu-id="78146-3645">ID numbers</span></span> 
- <span data-ttu-id="78146-3646">LIC</span><span class="sxs-lookup"><span data-stu-id="78146-3646">LIC</span></span> 
- <span data-ttu-id="78146-3647">LIC#</span><span class="sxs-lookup"><span data-stu-id="78146-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="78146-3648">关键字_us_驱动程序_许可证</span><span class="sxs-lookup"><span data-stu-id="78146-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="78146-3649">司机</span><span class="sxs-lookup"><span data-stu-id="78146-3649">DriverLic</span></span> 
- <span data-ttu-id="78146-3650">司机</span><span class="sxs-lookup"><span data-stu-id="78146-3650">DriverLics</span></span> 
- <span data-ttu-id="78146-3651">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3651">DriverLicense</span></span> 
- <span data-ttu-id="78146-3652">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3652">DriverLicenses</span></span> 
- <span data-ttu-id="78146-3653">司机李克</span><span class="sxs-lookup"><span data-stu-id="78146-3653">Driver Lic</span></span> 
- <span data-ttu-id="78146-3654">司机利茨</span><span class="sxs-lookup"><span data-stu-id="78146-3654">Driver Lics</span></span> 
- <span data-ttu-id="78146-3655">驾照</span><span class="sxs-lookup"><span data-stu-id="78146-3655">Driver License</span></span> 
- <span data-ttu-id="78146-3656">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3656">Driver Licenses</span></span> 
- <span data-ttu-id="78146-3657">驱动程序</span><span class="sxs-lookup"><span data-stu-id="78146-3657">DriversLic</span></span> 
- <span data-ttu-id="78146-3658">司机Lics</span><span class="sxs-lookup"><span data-stu-id="78146-3658">DriversLics</span></span> 
- <span data-ttu-id="78146-3659">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3659">DriversLicense</span></span> 
- <span data-ttu-id="78146-3660">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3660">DriversLicenses</span></span> 
- <span data-ttu-id="78146-3661">司机许可证</span><span class="sxs-lookup"><span data-stu-id="78146-3661">Drivers Lic</span></span> 
- <span data-ttu-id="78146-3662">司机利茨</span><span class="sxs-lookup"><span data-stu-id="78146-3662">Drivers Lics</span></span> 
- <span data-ttu-id="78146-3663">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3663">Drivers License</span></span> 
- <span data-ttu-id="78146-3664">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="78146-3665">司机'Lic</span><span class="sxs-lookup"><span data-stu-id="78146-3665">Driver'Lic</span></span> 
- <span data-ttu-id="78146-3666">司机的Lics</span><span class="sxs-lookup"><span data-stu-id="78146-3666">Driver'Lics</span></span> 
- <span data-ttu-id="78146-3667">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3667">Driver'License</span></span> 
- <span data-ttu-id="78146-3668">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="78146-3669">司机的许可证</span><span class="sxs-lookup"><span data-stu-id="78146-3669">Driver' Lic</span></span> 
- <span data-ttu-id="78146-3670">司机的Lics</span><span class="sxs-lookup"><span data-stu-id="78146-3670">Driver' Lics</span></span> 
- <span data-ttu-id="78146-3671">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3671">Driver' License</span></span> 
- <span data-ttu-id="78146-3672">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3672">Driver' Licenses</span></span>
- <span data-ttu-id="78146-3673">驾驶员的</span><span class="sxs-lookup"><span data-stu-id="78146-3673">Driver'sLic</span></span> 
- <span data-ttu-id="78146-3674">驾驶员的</span><span class="sxs-lookup"><span data-stu-id="78146-3674">Driver'sLics</span></span> 
- <span data-ttu-id="78146-3675">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="78146-3676">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="78146-3677">驾驶员的许可证</span><span class="sxs-lookup"><span data-stu-id="78146-3677">Driver's Lic</span></span> 
- <span data-ttu-id="78146-3678">司机的许可证</span><span class="sxs-lookup"><span data-stu-id="78146-3678">Driver's Lics</span></span> 
- <span data-ttu-id="78146-3679">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3679">Driver's License</span></span> 
- <span data-ttu-id="78146-3680">驾驶执照</span><span class="sxs-lookup"><span data-stu-id="78146-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="78146-3681">识别号</span><span class="sxs-lookup"><span data-stu-id="78146-3681">identification number</span></span> 
- <span data-ttu-id="78146-3682">识别号</span><span class="sxs-lookup"><span data-stu-id="78146-3682">identification numbers</span></span> 
- <span data-ttu-id="78146-3683">识别#</span><span class="sxs-lookup"><span data-stu-id="78146-3683">identification #</span></span> 
- <span data-ttu-id="78146-3684">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3684">id card</span></span> 
- <span data-ttu-id="78146-3685">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3685">id cards</span></span> 
- <span data-ttu-id="78146-3686">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3686">identification card</span></span> 
- <span data-ttu-id="78146-3687">身份证</span><span class="sxs-lookup"><span data-stu-id="78146-3687">identification cards</span></span> 
- <span data-ttu-id="78146-3688">司机#</span><span class="sxs-lookup"><span data-stu-id="78146-3688">DriverLic#</span></span> 
- <span data-ttu-id="78146-3689">司机#</span><span class="sxs-lookup"><span data-stu-id="78146-3689">DriverLics#</span></span> 
- <span data-ttu-id="78146-3690">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3690">DriverLicense#</span></span> 
- <span data-ttu-id="78146-3691">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="78146-3692">司机李克#</span><span class="sxs-lookup"><span data-stu-id="78146-3692">Driver Lic#</span></span> 
- <span data-ttu-id="78146-3693">司机利茨#</span><span class="sxs-lookup"><span data-stu-id="78146-3693">Driver Lics#</span></span> 
- <span data-ttu-id="78146-3694">驾照#</span><span class="sxs-lookup"><span data-stu-id="78146-3694">Driver License#</span></span> 
- <span data-ttu-id="78146-3695">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="78146-3696">驱动程序#</span><span class="sxs-lookup"><span data-stu-id="78146-3696">DriversLic#</span></span> 
- <span data-ttu-id="78146-3697">司机Lics#</span><span class="sxs-lookup"><span data-stu-id="78146-3697">DriversLics#</span></span> 
- <span data-ttu-id="78146-3698">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3698">DriversLicense#</span></span> 
- <span data-ttu-id="78146-3699">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="78146-3700">司机许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="78146-3701">司机利茨#</span><span class="sxs-lookup"><span data-stu-id="78146-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="78146-3702">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3702">Drivers License#</span></span> 
- <span data-ttu-id="78146-3703">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="78146-3704">司机'Lic#</span><span class="sxs-lookup"><span data-stu-id="78146-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="78146-3705">司机的Lics#</span><span class="sxs-lookup"><span data-stu-id="78146-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="78146-3706">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3706">Driver'License#</span></span> 
- <span data-ttu-id="78146-3707">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="78146-3708">司机的许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="78146-3709">司机的Lics#</span><span class="sxs-lookup"><span data-stu-id="78146-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="78146-3710">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3710">Driver' License#</span></span> 
- <span data-ttu-id="78146-3711">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="78146-3712">驾驶员的#</span><span class="sxs-lookup"><span data-stu-id="78146-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="78146-3713">驾驶员的#</span><span class="sxs-lookup"><span data-stu-id="78146-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="78146-3714">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="78146-3715">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="78146-3716">驾驶员的许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="78146-3717">司机的许可证#</span><span class="sxs-lookup"><span data-stu-id="78146-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="78146-3718">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3718">Driver's License#</span></span> 
- <span data-ttu-id="78146-3719">驾驶执照#</span><span class="sxs-lookup"><span data-stu-id="78146-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="78146-3720">身份证#</span><span class="sxs-lookup"><span data-stu-id="78146-3720">id card#</span></span> 
- <span data-ttu-id="78146-3721">身份证#</span><span class="sxs-lookup"><span data-stu-id="78146-3721">id cards#</span></span> 
- <span data-ttu-id="78146-3722">身份证#</span><span class="sxs-lookup"><span data-stu-id="78146-3722">identification card#</span></span> 
- <span data-ttu-id="78146-3723">身份证#</span><span class="sxs-lookup"><span data-stu-id="78146-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="78146-3724">关键字_状态_名称_驱动程序_许可证_名称</span><span class="sxs-lookup"><span data-stu-id="78146-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="78146-3725">状态缩写（例如，"NY"）</span><span class="sxs-lookup"><span data-stu-id="78146-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="78146-3726">州名称（例如"纽约"）</span><span class="sxs-lookup"><span data-stu-id="78146-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="78146-3727">美国个人纳税人识别号 （ITIN）</span><span class="sxs-lookup"><span data-stu-id="78146-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="78146-3728">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3728">Format</span></span>

<span data-ttu-id="78146-3729">以"9"开头，包含"7"或"8"作为第四位数字的九位数字，可选用空格或破折号格式</span><span class="sxs-lookup"><span data-stu-id="78146-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3730">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3730">Pattern</span></span>

<span data-ttu-id="78146-3731">格式 化：</span><span class="sxs-lookup"><span data-stu-id="78146-3731">Formatted:</span></span>
- <span data-ttu-id="78146-3732">数字"9"</span><span class="sxs-lookup"><span data-stu-id="78146-3732">The digit "9"</span></span> 
- <span data-ttu-id="78146-3733">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3733">Two digits</span></span> 
- <span data-ttu-id="78146-3734">空格或破折号</span><span class="sxs-lookup"><span data-stu-id="78146-3734">A space or dash</span></span> 
- <span data-ttu-id="78146-3735">"7"或"8"</span><span class="sxs-lookup"><span data-stu-id="78146-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="78146-3736">数字</span><span class="sxs-lookup"><span data-stu-id="78146-3736">A digit</span></span> 
- <span data-ttu-id="78146-3737">空格或破折号</span><span class="sxs-lookup"><span data-stu-id="78146-3737">A space, or dash</span></span> 
- <span data-ttu-id="78146-3738">四位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3738">Four digits</span></span>

<span data-ttu-id="78146-3739">未格式化：</span><span class="sxs-lookup"><span data-stu-id="78146-3739">Unformatted:</span></span>
- <span data-ttu-id="78146-3740">数字"9"</span><span class="sxs-lookup"><span data-stu-id="78146-3740">The digit "9"</span></span> 
- <span data-ttu-id="78146-3741">两位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3741">Two digits</span></span> 
- <span data-ttu-id="78146-3742">"7"或"8"</span><span class="sxs-lookup"><span data-stu-id="78146-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="78146-3743">五位数字</span><span class="sxs-lookup"><span data-stu-id="78146-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3744">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3744">Checksum</span></span>

<span data-ttu-id="78146-3745">否</span><span class="sxs-lookup"><span data-stu-id="78146-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="78146-3746">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3746">Definition</span></span>

<span data-ttu-id="78146-3747">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3748">函数 Func_格式化_itin 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3749">以下至少一项是正确的：</span><span class="sxs-lookup"><span data-stu-id="78146-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="78146-3750">找到关键字_itin 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="78146-3751">函数 Func_us_地址以正确的日期格式查找地址。</span><span class="sxs-lookup"><span data-stu-id="78146-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="78146-3752">函数 Func_us_date 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="78146-3753">找到关键字_itin_协作中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="78146-3754">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3755">函数 Func_无格式化_itin 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3756">以下至少一项是正确的：</span><span class="sxs-lookup"><span data-stu-id="78146-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="78146-3757">找到关键字_itin_协作中的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="78146-3758">函数 Func_us_地址以正确的日期格式查找地址。</span><span class="sxs-lookup"><span data-stu-id="78146-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="78146-3759">函数 Func_us_date 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-3759">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="78146-3760">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="78146-3761">关键字_itin</span><span class="sxs-lookup"><span data-stu-id="78146-3761">Keyword_itin</span></span>

- <span data-ttu-id="78146-3762">纳税人</span><span class="sxs-lookup"><span data-stu-id="78146-3762">taxpayer</span></span> 
- <span data-ttu-id="78146-3763">税 ID</span><span class="sxs-lookup"><span data-stu-id="78146-3763">tax id</span></span> 
- <span data-ttu-id="78146-3764">税务识别</span><span class="sxs-lookup"><span data-stu-id="78146-3764">tax identification</span></span> 
- <span data-ttu-id="78146-3765">itin</span><span class="sxs-lookup"><span data-stu-id="78146-3765">itin</span></span> 
- <span data-ttu-id="78146-3766">Ssn</span><span class="sxs-lookup"><span data-stu-id="78146-3766">ssn</span></span> 
- <span data-ttu-id="78146-3767">锡</span><span class="sxs-lookup"><span data-stu-id="78146-3767">tin</span></span> 
- <span data-ttu-id="78146-3768">社会保障</span><span class="sxs-lookup"><span data-stu-id="78146-3768">social security</span></span> 
- <span data-ttu-id="78146-3769">纳税人</span><span class="sxs-lookup"><span data-stu-id="78146-3769">tax payer</span></span> 
- <span data-ttu-id="78146-3770">itins</span><span class="sxs-lookup"><span data-stu-id="78146-3770">itins</span></span> 
- <span data-ttu-id="78146-3771">出租车</span><span class="sxs-lookup"><span data-stu-id="78146-3771">taxid</span></span> 
- <span data-ttu-id="78146-3772">个人纳税人</span><span class="sxs-lookup"><span data-stu-id="78146-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="78146-3773">关键词_itin_协作</span><span class="sxs-lookup"><span data-stu-id="78146-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="78146-3774">License</span><span class="sxs-lookup"><span data-stu-id="78146-3774">License</span></span> 
- <span data-ttu-id="78146-3775">Dl</span><span class="sxs-lookup"><span data-stu-id="78146-3775">DL</span></span> 
- <span data-ttu-id="78146-3776">DOB</span><span class="sxs-lookup"><span data-stu-id="78146-3776">DOB</span></span> 
- <span data-ttu-id="78146-3777">出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-3777">Birthdate</span></span> 
- <span data-ttu-id="78146-3778">生日</span><span class="sxs-lookup"><span data-stu-id="78146-3778">Birthday</span></span> 
- <span data-ttu-id="78146-3779">出生日期</span><span class="sxs-lookup"><span data-stu-id="78146-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="78146-3780">美国社会安全号码 （SSN）</span><span class="sxs-lookup"><span data-stu-id="78146-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="78146-3781">格式</span><span class="sxs-lookup"><span data-stu-id="78146-3781">Format</span></span>

<span data-ttu-id="78146-3782">9 位数字，可能采用格式化或未格式化的模式</span><span class="sxs-lookup"><span data-stu-id="78146-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="78146-3783">如果在 2011 年年中之前发布，SSN 具有强格式，其中数字的某些部分必须属于有效范围（但没有校验和）。</span><span class="sxs-lookup"><span data-stu-id="78146-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="78146-3784">模式</span><span class="sxs-lookup"><span data-stu-id="78146-3784">Pattern</span></span>

<span data-ttu-id="78146-3785">四种函数以四种不同的模式查找 SSN：</span><span class="sxs-lookup"><span data-stu-id="78146-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="78146-3786">Func_ssn 查找具有 2011 年前强格式的 SSN，这些格式采用破折号或空格（dd-dd-dd-dd dd dd dd dd dd dd ddd ddd） 格式设置格式</span><span class="sxs-lookup"><span data-stu-id="78146-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="78146-3787">Func_无格式化_ssn 查找具有 2011 年前强格式的 SSN，这些格式未格式化为九位连续数字 （ddddddd）</span><span class="sxs-lookup"><span data-stu-id="78146-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="78146-3788">Func_随机_格式化_ssn 查找 2011 年后使用破折号或空格格式化的 SSN（dd-dd-dd-ddd or ddd dd dd dd dd dd dd ddd）</span><span class="sxs-lookup"><span data-stu-id="78146-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="78146-3789">Func_随机_未格式化_ssn 查找未格式化为九位连续数字的 2011 后 SSN（ddddddd）</span><span class="sxs-lookup"><span data-stu-id="78146-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="78146-3790">校验</span><span class="sxs-lookup"><span data-stu-id="78146-3790">Checksum</span></span>

<span data-ttu-id="78146-3791">否</span><span class="sxs-lookup"><span data-stu-id="78146-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="78146-3792">定義</span><span class="sxs-lookup"><span data-stu-id="78146-3792">Definition</span></span>

<span data-ttu-id="78146-3793">如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3794">函数 Func_ssn 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3795">找到关键字\sn 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3795">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="78146-3796">函数 Func_us_date 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-3796">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="78146-3797">函数 Func_us_地址以正确的格式查找地址。</span><span class="sxs-lookup"><span data-stu-id="78146-3797">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="78146-3798">如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3798">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3799">函数 Func_无格式化_ssn 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3799">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3800">找到关键字\sn 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3800">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="78146-3801">函数 Func_us_date 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-3801">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="78146-3802">函数 Func_us_地址以正确的格式查找地址。</span><span class="sxs-lookup"><span data-stu-id="78146-3802">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="78146-3803">如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3803">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3804">函数 Func_随机_格式化_ssn 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3804">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3805">找到关键字\sn 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3805">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="78146-3806">函数 Func_us_date 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-3806">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="78146-3807">函数 Func_us_地址以正确的格式查找地址。</span><span class="sxs-lookup"><span data-stu-id="78146-3807">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="78146-3808">如果接近 300 个字符，DLP 策略的置量为 55%，它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3808">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3809">函数 Func_随机_未格式化_ssn 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3809">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3810">找到关键字\sn 的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3810">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="78146-3811">函数 Func_us_date 以正确的日期格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="78146-3811">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="78146-3812">函数 Func_us_地址以正确的格式查找地址。</span><span class="sxs-lookup"><span data-stu-id="78146-3812">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="78146-3813">如果接近 300 个字符，DLP 策略有 40% 的确信检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="78146-3813">A DLP policy is 40% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="78146-3814">函数 Func_ssn 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3814">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3815">函数 Func_无格式化_ssn 找不到与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3815">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3816">函数 Func_随机_未格式化_ssn 找不到与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3816">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3817">找不到关键字_sn 中产生的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3817">A keyword from Keyword_ssn is not found.</span></span>
 
<span data-ttu-id="78146-3818">或</span><span class="sxs-lookup"><span data-stu-id="78146-3818">Or</span></span>

- <span data-ttu-id="78146-3819">函数 Func_随机_格式化_ssn 查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3819">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3820">函数 Func_无格式化_ssn 找不到与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3820">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3821">函数 Func_随机_未格式化_ssn 找不到与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="78146-3821">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="78146-3822">找不到关键字_sn 中产生的关键字。</span><span class="sxs-lookup"><span data-stu-id="78146-3822">A keyword from Keyword_ssn is not found.</span></span>

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="78146-3823">關鍵字</span><span class="sxs-lookup"><span data-stu-id="78146-3823">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="78146-3824">关键字\ssn</span><span class="sxs-lookup"><span data-stu-id="78146-3824">Keyword_ssn</span></span>

- <span data-ttu-id="78146-3825">社会保障</span><span class="sxs-lookup"><span data-stu-id="78146-3825">Social Security</span></span> 
- <span data-ttu-id="78146-3826">社会保障#</span><span class="sxs-lookup"><span data-stu-id="78146-3826">Social Security#</span></span> 
- <span data-ttu-id="78146-3827">索克秒</span><span class="sxs-lookup"><span data-stu-id="78146-3827">Soc Sec</span></span> 
- <span data-ttu-id="78146-3828">Ssn</span><span class="sxs-lookup"><span data-stu-id="78146-3828">SSN</span></span> 
- <span data-ttu-id="78146-3829">SSNS</span><span class="sxs-lookup"><span data-stu-id="78146-3829">SSNS</span></span> 
- <span data-ttu-id="78146-3830">Ssn#</span><span class="sxs-lookup"><span data-stu-id="78146-3830">SSN#</span></span> 
- <span data-ttu-id="78146-3831">SS#</span><span class="sxs-lookup"><span data-stu-id="78146-3831">SS#</span></span> 
- <span data-ttu-id="78146-3832">Ssid</span><span class="sxs-lookup"><span data-stu-id="78146-3832">SSID</span></span> 
   

