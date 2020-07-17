---
title: DLP 功能所尋找的項目
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 瞭解資料遺失防護（DLP）功能的尋找方式，以協助您瞭解預先定義的機密資訊類型的運作方式。
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819273"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="8974d-103">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="8974d-103">What the DLP functions look for</span></span>

<span data-ttu-id="8974d-104">資料遺失防護（DLP）包含機密資訊類型，例如信用卡號碼和歐盟卡號，可供您在 DLP 原則中使用。</span><span class="sxs-lookup"><span data-stu-id="8974d-104">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="8974d-105">這些敏感資訊類型會尋找特定的模式，並加以 corroborate，方法是確認正確的格式設定、強制執行校驗和尋找相關的關鍵字或其他資訊。</span><span class="sxs-lookup"><span data-stu-id="8974d-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="8974d-106">此功能的部分功能是由內建函式執行。</span><span class="sxs-lookup"><span data-stu-id="8974d-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="8974d-107">例如，「信用卡號碼敏感資訊類型」會使用函數來尋找類似到期日的日期，以協助 corroborate 號碼是信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="8974d-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="8974d-108">本主題說明這些功能的含義，以協助您瞭解預先定義的機密資訊類型的運作方式。</span><span class="sxs-lookup"><span data-stu-id="8974d-108">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="8974d-109">如需詳細資訊，請參閱[敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="8974d-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="8974d-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="8974d-110">Func_us_date</span></span>

<span data-ttu-id="8974d-111">此函數會以美國常用的格式來尋找日期。這包括「月/日/年」、「月-日-年」和「年月日」的格式。</span><span class="sxs-lookup"><span data-stu-id="8974d-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="8974d-112">月份的名稱或縮寫不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="8974d-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="8974d-113">範例：</span><span class="sxs-lookup"><span data-stu-id="8974d-113">Examples:</span></span>
  
- <span data-ttu-id="8974d-114">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="8974d-114">December 2, 2016</span></span>
    
- <span data-ttu-id="8974d-115">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="8974d-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="8974d-116">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="8974d-116">dec 02 2016</span></span>
    
- <span data-ttu-id="8974d-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="8974d-117">12/2/2016</span></span>
    
- <span data-ttu-id="8974d-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="8974d-118">12/02/16</span></span>
    
- <span data-ttu-id="8974d-119">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="8974d-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="8974d-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="8974d-120">12-2-16</span></span>
    
<span data-ttu-id="8974d-121">公認的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="8974d-121">Accepted month names:</span></span>
  
- <span data-ttu-id="8974d-122">English</span><span class="sxs-lookup"><span data-stu-id="8974d-122">English</span></span>
    
  - <span data-ttu-id="8974d-123">一月份、二月份、三月份、四月、六月、六月、十二月、十二月、十二月、十月、十二月、十二月</span><span class="sxs-lookup"><span data-stu-id="8974d-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="8974d-124">Mar 年4月4月8日（11月11日）。</span><span class="sxs-lookup"><span data-stu-id="8974d-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="8974d-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="8974d-125">Func_eu_date</span></span>

<span data-ttu-id="8974d-126">此函數會以歐盟常用的格式來尋找日期</span><span class="sxs-lookup"><span data-stu-id="8974d-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="8974d-127">（和美國以外的大部分地點）。</span><span class="sxs-lookup"><span data-stu-id="8974d-127">(and most places outside the U.S.).</span></span> <span data-ttu-id="8974d-128">這包括格式「日/月/年」、「日-月-年」和「日月年」。</span><span class="sxs-lookup"><span data-stu-id="8974d-128">This includes the formats "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="8974d-129">月份的名稱或縮寫不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="8974d-129">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="8974d-130">範例：</span><span class="sxs-lookup"><span data-stu-id="8974d-130">Examples:</span></span>
  
- <span data-ttu-id="8974d-131">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="8974d-131">2 Dec 2016</span></span>
    
- <span data-ttu-id="8974d-132">02 dec 2016</span><span class="sxs-lookup"><span data-stu-id="8974d-132">02 dec 2016</span></span>
    
- <span data-ttu-id="8974d-133">2 Dec 16</span><span class="sxs-lookup"><span data-stu-id="8974d-133">2 Dec 16</span></span>
    
- <span data-ttu-id="8974d-134">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="8974d-134">2/12/2016</span></span>
    
- <span data-ttu-id="8974d-135">02/12/16</span><span class="sxs-lookup"><span data-stu-id="8974d-135">02/12/16</span></span>
    
- <span data-ttu-id="8974d-136">2月2日-2016</span><span class="sxs-lookup"><span data-stu-id="8974d-136">2-Dec-2016</span></span>
    
- <span data-ttu-id="8974d-137">2-12-16</span><span class="sxs-lookup"><span data-stu-id="8974d-137">2-12-16</span></span>
    
<span data-ttu-id="8974d-138">公認的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="8974d-138">Accepted month names:</span></span>
  
- <span data-ttu-id="8974d-139">English</span><span class="sxs-lookup"><span data-stu-id="8974d-139">English</span></span>
    
  - <span data-ttu-id="8974d-140">一月份、二月份、三月份、四月、六月、六月、十二月、十二月、十二月、十月、十二月、十二月</span><span class="sxs-lookup"><span data-stu-id="8974d-140">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="8974d-141">Mar 年4月4月8日（11月11日）。</span><span class="sxs-lookup"><span data-stu-id="8974d-141">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="8974d-142">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="8974d-142">Dutch</span></span>
    
  - <span data-ttu-id="8974d-143">januari，februari，maart，四月，mei，juni，juli，augustus，九月份，ocktober，十月，11月，十二月</span><span class="sxs-lookup"><span data-stu-id="8974d-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="8974d-144">jan jan maart apr mei 年9月8日9月 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="8974d-144">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="8974d-145">法文</span><span class="sxs-lookup"><span data-stu-id="8974d-145">French</span></span>
    
  - <span data-ttu-id="8974d-146">janvier，février，mars，avril，mai，juin juillet，août，septembre，octobre，novembre，décembre</span><span class="sxs-lookup"><span data-stu-id="8974d-146">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="8974d-147">janv.</span><span class="sxs-lookup"><span data-stu-id="8974d-147">janv.</span></span> <span data-ttu-id="8974d-148">févr.</span><span class="sxs-lookup"><span data-stu-id="8974d-148">févr.</span></span> <span data-ttu-id="8974d-149">mars avril mai juin juil。</span><span class="sxs-lookup"><span data-stu-id="8974d-149">mars avril mai juin juil.</span></span> <span data-ttu-id="8974d-150">août 年9月。</span><span class="sxs-lookup"><span data-stu-id="8974d-150">août sept.</span></span> <span data-ttu-id="8974d-151">2008.</span><span class="sxs-lookup"><span data-stu-id="8974d-151">oct.</span></span> <span data-ttu-id="8974d-152">11 月。</span><span class="sxs-lookup"><span data-stu-id="8974d-152">nov.</span></span> <span data-ttu-id="8974d-153">déc.</span><span class="sxs-lookup"><span data-stu-id="8974d-153">déc.</span></span>
    
- <span data-ttu-id="8974d-154">德文</span><span class="sxs-lookup"><span data-stu-id="8974d-154">German</span></span>
    
  - <span data-ttu-id="8974d-155">jänuar，februar，märz，四月，mai，juni juli，八月，九月份，oktober，11月，dezember</span><span class="sxs-lookup"><span data-stu-id="8974d-155">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="8974d-156">Jan./Jän。</span><span class="sxs-lookup"><span data-stu-id="8974d-156">Jan./Jän.</span></span> <span data-ttu-id="8974d-157">März Apr Juni Juli 08 月 Okt。</span><span class="sxs-lookup"><span data-stu-id="8974d-157">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="8974d-158">Dez 年11月。</span><span class="sxs-lookup"><span data-stu-id="8974d-158">Nov. Dez.</span></span>
    
- <span data-ttu-id="8974d-159">義大利文</span><span class="sxs-lookup"><span data-stu-id="8974d-159">Italian</span></span>
    
  - <span data-ttu-id="8974d-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="8974d-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="8974d-161">genn.</span><span class="sxs-lookup"><span data-stu-id="8974d-161">genn.</span></span> <span data-ttu-id="8974d-162">febbr.</span><span class="sxs-lookup"><span data-stu-id="8974d-162">febbr.</span></span> <span data-ttu-id="8974d-163">三月。</span><span class="sxs-lookup"><span data-stu-id="8974d-163">mar.</span></span> <span data-ttu-id="8974d-164">四月。</span><span class="sxs-lookup"><span data-stu-id="8974d-164">apr.</span></span> <span data-ttu-id="8974d-165">magg.</span><span class="sxs-lookup"><span data-stu-id="8974d-165">magg.</span></span> <span data-ttu-id="8974d-166">giugno luglio ag。</span><span class="sxs-lookup"><span data-stu-id="8974d-166">giugno luglio ag.</span></span> <span data-ttu-id="8974d-167">sett.</span><span class="sxs-lookup"><span data-stu-id="8974d-167">sett.</span></span> <span data-ttu-id="8974d-168">奧特。</span><span class="sxs-lookup"><span data-stu-id="8974d-168">ott.</span></span> <span data-ttu-id="8974d-169">11 月。</span><span class="sxs-lookup"><span data-stu-id="8974d-169">nov.</span></span> <span data-ttu-id="8974d-170">Dic。</span><span class="sxs-lookup"><span data-stu-id="8974d-170">dic.</span></span>
    
- <span data-ttu-id="8974d-171">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="8974d-171">Portuguese</span></span>
    
  - <span data-ttu-id="8974d-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="8974d-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="8974d-173">jan fev mar abr mai 06 年6月1日，設定為11月 dez</span><span class="sxs-lookup"><span data-stu-id="8974d-173">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="8974d-174">西班牙文</span><span class="sxs-lookup"><span data-stu-id="8974d-174">Spanish</span></span>
    
  - <span data-ttu-id="8974d-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="8974d-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="8974d-176">enero 年2月。</span><span class="sxs-lookup"><span data-stu-id="8974d-176">enero feb.</span></span> <span data-ttu-id="8974d-177">marzo abr。</span><span class="sxs-lookup"><span data-stu-id="8974d-177">marzo abr.</span></span> <span data-ttu-id="8974d-178">mayo 年6月。</span><span class="sxs-lookup"><span data-stu-id="8974d-178">mayo jun.</span></span> <span data-ttu-id="8974d-179">七月。</span><span class="sxs-lookup"><span data-stu-id="8974d-179">jul.</span></span> <span data-ttu-id="8974d-180">agosto/set。</span><span class="sxs-lookup"><span data-stu-id="8974d-180">agosto sept./set.</span></span> <span data-ttu-id="8974d-181">2008.</span><span class="sxs-lookup"><span data-stu-id="8974d-181">oct.</span></span> <span data-ttu-id="8974d-182">11 月。</span><span class="sxs-lookup"><span data-stu-id="8974d-182">nov.</span></span> <span data-ttu-id="8974d-183">Dic。</span><span class="sxs-lookup"><span data-stu-id="8974d-183">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="8974d-184">Func_eu_date1 （已過時）</span><span class="sxs-lookup"><span data-stu-id="8974d-184">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="8974d-185">此函數已過時，因為它只支援葡萄牙文月份名稱，而這些名稱現在已包含在 `Func_eu_date` 上述函數中。</span><span class="sxs-lookup"><span data-stu-id="8974d-185">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="8974d-186">此函數會以葡萄牙文中常用的格式來尋找日期。</span><span class="sxs-lookup"><span data-stu-id="8974d-186">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="8974d-187">此函數的格式與 `Func_eu_date` 使用的語言不同。</span><span class="sxs-lookup"><span data-stu-id="8974d-187">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="8974d-188">範例：</span><span class="sxs-lookup"><span data-stu-id="8974d-188">Examples:</span></span>
  
- <span data-ttu-id="8974d-189">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="8974d-189">2 Dez 2016</span></span>
    
- <span data-ttu-id="8974d-190">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="8974d-190">02 dez 2016</span></span>
    
- <span data-ttu-id="8974d-191">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="8974d-191">2 Dez 16</span></span>
    
- <span data-ttu-id="8974d-192">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="8974d-192">2/12/2016</span></span>
    
- <span data-ttu-id="8974d-193">02/12/16</span><span class="sxs-lookup"><span data-stu-id="8974d-193">02/12/16</span></span>
    
- <span data-ttu-id="8974d-194">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="8974d-194">2-Dez-2016</span></span>
    
- <span data-ttu-id="8974d-195">2-12-16</span><span class="sxs-lookup"><span data-stu-id="8974d-195">2-12-16</span></span>
    
<span data-ttu-id="8974d-196">公認的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="8974d-196">Accepted month names:</span></span>
  
- <span data-ttu-id="8974d-197">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="8974d-197">Portuguese</span></span>
    
  - <span data-ttu-id="8974d-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="8974d-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="8974d-199">jan fev mar abr mai 06 年6月1日，設定為11月 dez</span><span class="sxs-lookup"><span data-stu-id="8974d-199">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="8974d-200">Func_eu_date2 （已過時）</span><span class="sxs-lookup"><span data-stu-id="8974d-200">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="8974d-201">此函數已過時，因為它只支援荷蘭月份名稱，而這些名稱現在已包含在 `Func_eu_date` 上述函數中。</span><span class="sxs-lookup"><span data-stu-id="8974d-201">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="8974d-202">此函數會以荷蘭文中常用的格式來尋找日期。</span><span class="sxs-lookup"><span data-stu-id="8974d-202">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="8974d-203">此函數的格式與 `Func_eu_date` 使用的語言不同。</span><span class="sxs-lookup"><span data-stu-id="8974d-203">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="8974d-204">範例：</span><span class="sxs-lookup"><span data-stu-id="8974d-204">Examples:</span></span>
  
- <span data-ttu-id="8974d-205">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="8974d-205">2 Mei 2016</span></span>
    
- <span data-ttu-id="8974d-206">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="8974d-206">02 mei 2016</span></span>
    
- <span data-ttu-id="8974d-207">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="8974d-207">2 Mei 16</span></span>
    
- <span data-ttu-id="8974d-208">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="8974d-208">2/12/2016</span></span>
    
- <span data-ttu-id="8974d-209">02/12/16</span><span class="sxs-lookup"><span data-stu-id="8974d-209">02/12/16</span></span>
    
- <span data-ttu-id="8974d-210">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="8974d-210">2-Mei-2016</span></span>
    
- <span data-ttu-id="8974d-211">2-12-16</span><span class="sxs-lookup"><span data-stu-id="8974d-211">2-12-16</span></span>
    
<span data-ttu-id="8974d-212">公認的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="8974d-212">Accepted month names:</span></span>
  
- <span data-ttu-id="8974d-213">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="8974d-213">Dutch</span></span>
    
  - <span data-ttu-id="8974d-214">januari，februari，maart，四月，mei，juni，juli，augustus，九月份，ocktober，十月，11月，十二月</span><span class="sxs-lookup"><span data-stu-id="8974d-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="8974d-215">jan jan maart apr mei 年9月8日9月 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="8974d-215">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="8974d-216">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="8974d-216">Func_expiration_date</span></span>

<span data-ttu-id="8974d-217">此函數會以信用卡和轉帳卡所使用的格式來尋找日期，而不是以月為單位來扣除天數。</span><span class="sxs-lookup"><span data-stu-id="8974d-217">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="8974d-218">此函數會比對「月/年」、「月-年」、「[month name] 年] 和「[month 簡寫] 年 "格式的日期。</span><span class="sxs-lookup"><span data-stu-id="8974d-218">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="8974d-219">月份的名稱或縮寫不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="8974d-219">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="8974d-220">範例：</span><span class="sxs-lookup"><span data-stu-id="8974d-220">Examples:</span></span>
  
- <span data-ttu-id="8974d-221">MM/YY--例如01/11 或1/11</span><span class="sxs-lookup"><span data-stu-id="8974d-221">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="8974d-222">MM/YYYY--例如01/2011 或1/2011</span><span class="sxs-lookup"><span data-stu-id="8974d-222">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="8974d-223">MM-YY--例如01-22 或1-11</span><span class="sxs-lookup"><span data-stu-id="8974d-223">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="8974d-224">MM-YYYY--例如01-2000 或1-2000</span><span class="sxs-lookup"><span data-stu-id="8974d-224">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="8974d-225">下列格式支援 YY 或 YYYY：</span><span class="sxs-lookup"><span data-stu-id="8974d-225">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="8974d-226">例如，Month-YYYY--。Jan-2010 或一月-2010 或 Jan-10 或年1月</span><span class="sxs-lookup"><span data-stu-id="8974d-226">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="8974d-227">Month YYYY--例如，"一月 2010" 或 "Jan 2010" 或 "Jan 10" 或 "Jan 10"</span><span class="sxs-lookup"><span data-stu-id="8974d-227">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="8974d-228">MonthYYYY--例如 "january2010" 或 "Jan2010" 或 "january10" 或 "Jan10"</span><span class="sxs-lookup"><span data-stu-id="8974d-228">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="8974d-229">Month/YYYY--例如，' 一月份/2010 ' 或 ' Jan/2010 ' or "Jan/10" 或 "Jan/10"</span><span class="sxs-lookup"><span data-stu-id="8974d-229">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="8974d-230">公認的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="8974d-230">Accepted month names:</span></span>
  
- <span data-ttu-id="8974d-231">English</span><span class="sxs-lookup"><span data-stu-id="8974d-231">English</span></span>
    
  - <span data-ttu-id="8974d-232">一月份、二月份、三月份、四月、六月、六月、十二月、十二月、十二月、十月、十二月、十二月</span><span class="sxs-lookup"><span data-stu-id="8974d-232">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="8974d-233">Jan 02 月4月8日在十二月</span><span class="sxs-lookup"><span data-stu-id="8974d-233">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="8974d-234">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="8974d-234">Func_us_address</span></span>

<span data-ttu-id="8974d-235">此函數會尋找美國的狀態名稱或郵政縮寫後接有效的郵遞區號，就像在通信地址中使用。</span><span class="sxs-lookup"><span data-stu-id="8974d-235">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses.</span></span> <span data-ttu-id="8974d-236">郵遞區號必須是與美國州名稱或縮略語相關聯的正確郵遞區號之一。</span><span class="sxs-lookup"><span data-stu-id="8974d-236">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="8974d-237">美國的狀態名稱及郵遞區號不能以標點符號或字母分隔。</span><span class="sxs-lookup"><span data-stu-id="8974d-237">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="8974d-238">範例：</span><span class="sxs-lookup"><span data-stu-id="8974d-238">Examples:</span></span>
  
- <span data-ttu-id="8974d-239">華盛頓98052</span><span class="sxs-lookup"><span data-stu-id="8974d-239">Washington 98052</span></span>
    
- <span data-ttu-id="8974d-240">華盛頓98052-9998</span><span class="sxs-lookup"><span data-stu-id="8974d-240">Washington 98052-9998</span></span>
    
- <span data-ttu-id="8974d-241">WA 98052</span><span class="sxs-lookup"><span data-stu-id="8974d-241">WA 98052</span></span>
    
- <span data-ttu-id="8974d-242">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="8974d-242">WA 98052-9998</span></span>
    

