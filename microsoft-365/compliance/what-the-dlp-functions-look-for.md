---
title: 資料遺失防護（DLP）功能的尋找目標
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
description: 瞭解資料遺失防護（DLP）功能的尋找目標。
ms.openlocfilehash: ef87be7dde83b1e5ba12456e7801e0554bceb6ea
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536308"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="780d0-103">DLP 功能所尋找的項目</span><span class="sxs-lookup"><span data-stu-id="780d0-103">What the DLP functions look for</span></span>

<span data-ttu-id="780d0-104">資料遺失防護（DLP）包含機密資訊類型，例如信用卡號碼和歐盟卡號，可供您在 DLP 原則中使用。</span><span class="sxs-lookup"><span data-stu-id="780d0-104">Data loss prevention (DLP) includes sensitive information types, such as credit card Number and EU Debit card number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="780d0-105">這些敏感資訊類型會尋找特定的模式，並加以 corroborate，方法是確認正確的格式設定、強制執行校驗和尋找相關的關鍵字或其他資訊。</span><span class="sxs-lookup"><span data-stu-id="780d0-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="780d0-106">此功能的部分功能是由內建函式執行。</span><span class="sxs-lookup"><span data-stu-id="780d0-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="780d0-107">例如，「信用卡號碼敏感資訊類型」會使用函數來尋找類似到期日的日期，以協助 corroborate 號碼是信用卡號碼。</span><span class="sxs-lookup"><span data-stu-id="780d0-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="780d0-108">本文說明這些功能的含義，以協助您瞭解預先定義的機密資訊類型的運作方式。</span><span class="sxs-lookup"><span data-stu-id="780d0-108">This article explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="780d0-109">如需詳細資訊，請參閱[敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="780d0-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="780d0-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="780d0-110">Func_us_date</span></span>

<span data-ttu-id="780d0-111">此函數會以美國常用的格式來尋找日期。這包括「月/日/年」、「月-日-年」和「年月日」的格式。</span><span class="sxs-lookup"><span data-stu-id="780d0-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="780d0-112">月份的名稱或縮寫不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="780d0-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="780d0-113">範例：</span><span class="sxs-lookup"><span data-stu-id="780d0-113">Examples:</span></span>
  
- <span data-ttu-id="780d0-114">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="780d0-114">December 2, 2016</span></span>
    
- <span data-ttu-id="780d0-115">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="780d0-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="780d0-116">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="780d0-116">dec 02 2016</span></span>
    
- <span data-ttu-id="780d0-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="780d0-117">12/2/2016</span></span>
    
- <span data-ttu-id="780d0-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="780d0-118">12/02/16</span></span>
    
- <span data-ttu-id="780d0-119">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="780d0-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="780d0-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="780d0-120">12-2-16</span></span>
    
<span data-ttu-id="780d0-121">公認的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="780d0-121">Accepted month names:</span></span>
  
- <span data-ttu-id="780d0-122">English</span><span class="sxs-lookup"><span data-stu-id="780d0-122">English</span></span>
    
  - <span data-ttu-id="780d0-123">一月份、二月份、三月份、四月、六月、六月、十二月、十二月、十二月、十月、十二月、十二月</span><span class="sxs-lookup"><span data-stu-id="780d0-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="780d0-124">Mar 年4月4月8日（11月11日）。</span><span class="sxs-lookup"><span data-stu-id="780d0-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="780d0-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="780d0-125">Func_eu_date</span></span>

<span data-ttu-id="780d0-126">此函數會以歐盟常用的格式來尋找日期</span><span class="sxs-lookup"><span data-stu-id="780d0-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="780d0-127">（和美國以外的大多數位置），例如「天/月/年」、「日-月-年」和「日月」。</span><span class="sxs-lookup"><span data-stu-id="780d0-127">(and most places outside the U.S.), such as "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="780d0-128">月份的名稱或縮寫不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="780d0-128">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="780d0-129">範例：</span><span class="sxs-lookup"><span data-stu-id="780d0-129">Examples:</span></span>
  
- <span data-ttu-id="780d0-130">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="780d0-130">2 Dec 2016</span></span>
    
- <span data-ttu-id="780d0-131">02 dec 2016</span><span class="sxs-lookup"><span data-stu-id="780d0-131">02 dec 2016</span></span>
    
- <span data-ttu-id="780d0-132">2 Dec 16</span><span class="sxs-lookup"><span data-stu-id="780d0-132">2 Dec 16</span></span>
    
- <span data-ttu-id="780d0-133">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="780d0-133">2/12/2016</span></span>
    
- <span data-ttu-id="780d0-134">02/12/16</span><span class="sxs-lookup"><span data-stu-id="780d0-134">02/12/16</span></span>
    
- <span data-ttu-id="780d0-135">2月2日-2016</span><span class="sxs-lookup"><span data-stu-id="780d0-135">2-Dec-2016</span></span>
    
- <span data-ttu-id="780d0-136">2-12-16</span><span class="sxs-lookup"><span data-stu-id="780d0-136">2-12-16</span></span>
    
<span data-ttu-id="780d0-137">公認的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="780d0-137">Accepted month names:</span></span>
  
- <span data-ttu-id="780d0-138">English</span><span class="sxs-lookup"><span data-stu-id="780d0-138">English</span></span>
    
  - <span data-ttu-id="780d0-139">一月份、二月份、三月份、四月、六月、六月、十二月、十二月、十二月、十月、十二月、十二月</span><span class="sxs-lookup"><span data-stu-id="780d0-139">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="780d0-140">Mar 年4月4月8日（11月11日）。</span><span class="sxs-lookup"><span data-stu-id="780d0-140">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="780d0-141">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="780d0-141">Dutch</span></span>
    
  - <span data-ttu-id="780d0-142">januari，februari，maart，四月，mei，juni，juli，augustus，九月份，ocktober，十月，11月，十二月</span><span class="sxs-lookup"><span data-stu-id="780d0-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="780d0-143">jan jan maart apr mei 年9月8日9月 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="780d0-143">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="780d0-144">法文</span><span class="sxs-lookup"><span data-stu-id="780d0-144">French</span></span>
    
  - <span data-ttu-id="780d0-145">janvier，février，mars，avril，mai，juin juillet，août，septembre，octobre，novembre，décembre</span><span class="sxs-lookup"><span data-stu-id="780d0-145">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="780d0-146">janv.</span><span class="sxs-lookup"><span data-stu-id="780d0-146">janv.</span></span> <span data-ttu-id="780d0-147">févr.</span><span class="sxs-lookup"><span data-stu-id="780d0-147">févr.</span></span> <span data-ttu-id="780d0-148">mars avril mai juin juil。</span><span class="sxs-lookup"><span data-stu-id="780d0-148">mars avril mai juin juil.</span></span> <span data-ttu-id="780d0-149">août 年9月。</span><span class="sxs-lookup"><span data-stu-id="780d0-149">août sept.</span></span> <span data-ttu-id="780d0-150">2008.</span><span class="sxs-lookup"><span data-stu-id="780d0-150">oct.</span></span> <span data-ttu-id="780d0-151">11 月。</span><span class="sxs-lookup"><span data-stu-id="780d0-151">nov.</span></span> <span data-ttu-id="780d0-152">déc.</span><span class="sxs-lookup"><span data-stu-id="780d0-152">déc.</span></span>
    
- <span data-ttu-id="780d0-153">德文</span><span class="sxs-lookup"><span data-stu-id="780d0-153">German</span></span>
    
  - <span data-ttu-id="780d0-154">jänuar，februar，märz，四月，mai，juni juli，八月，九月份，oktober，11月，dezember</span><span class="sxs-lookup"><span data-stu-id="780d0-154">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="780d0-155">Jan./Jän。</span><span class="sxs-lookup"><span data-stu-id="780d0-155">Jan./Jän.</span></span> <span data-ttu-id="780d0-156">März Apr Juni Juli 08 月 Okt。</span><span class="sxs-lookup"><span data-stu-id="780d0-156">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="780d0-157">Dez 年11月。</span><span class="sxs-lookup"><span data-stu-id="780d0-157">Nov. Dez.</span></span>
    
- <span data-ttu-id="780d0-158">義大利文</span><span class="sxs-lookup"><span data-stu-id="780d0-158">Italian</span></span>
    
  - <span data-ttu-id="780d0-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="780d0-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="780d0-160">genn.</span><span class="sxs-lookup"><span data-stu-id="780d0-160">genn.</span></span> <span data-ttu-id="780d0-161">febbr.</span><span class="sxs-lookup"><span data-stu-id="780d0-161">febbr.</span></span> <span data-ttu-id="780d0-162">三月。</span><span class="sxs-lookup"><span data-stu-id="780d0-162">mar.</span></span> <span data-ttu-id="780d0-163">四月。</span><span class="sxs-lookup"><span data-stu-id="780d0-163">apr.</span></span> <span data-ttu-id="780d0-164">magg.</span><span class="sxs-lookup"><span data-stu-id="780d0-164">magg.</span></span> <span data-ttu-id="780d0-165">giugno luglio ag。</span><span class="sxs-lookup"><span data-stu-id="780d0-165">giugno luglio ag.</span></span> <span data-ttu-id="780d0-166">sett.</span><span class="sxs-lookup"><span data-stu-id="780d0-166">sett.</span></span> <span data-ttu-id="780d0-167">奧特。</span><span class="sxs-lookup"><span data-stu-id="780d0-167">ott.</span></span> <span data-ttu-id="780d0-168">11 月。</span><span class="sxs-lookup"><span data-stu-id="780d0-168">nov.</span></span> <span data-ttu-id="780d0-169">Dic。</span><span class="sxs-lookup"><span data-stu-id="780d0-169">dic.</span></span>
    
- <span data-ttu-id="780d0-170">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="780d0-170">Portuguese</span></span>
    
  - <span data-ttu-id="780d0-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="780d0-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="780d0-172">jan fev mar abr mai 06 年6月1日，設定為11月 dez</span><span class="sxs-lookup"><span data-stu-id="780d0-172">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="780d0-173">西班牙文</span><span class="sxs-lookup"><span data-stu-id="780d0-173">Spanish</span></span>
    
  - <span data-ttu-id="780d0-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="780d0-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="780d0-175">enero 年2月。</span><span class="sxs-lookup"><span data-stu-id="780d0-175">enero feb.</span></span> <span data-ttu-id="780d0-176">marzo abr。</span><span class="sxs-lookup"><span data-stu-id="780d0-176">marzo abr.</span></span> <span data-ttu-id="780d0-177">mayo 年6月。</span><span class="sxs-lookup"><span data-stu-id="780d0-177">mayo jun.</span></span> <span data-ttu-id="780d0-178">七月。</span><span class="sxs-lookup"><span data-stu-id="780d0-178">jul.</span></span> <span data-ttu-id="780d0-179">agosto/set。</span><span class="sxs-lookup"><span data-stu-id="780d0-179">agosto sept./set.</span></span> <span data-ttu-id="780d0-180">2008.</span><span class="sxs-lookup"><span data-stu-id="780d0-180">oct.</span></span> <span data-ttu-id="780d0-181">11 月。</span><span class="sxs-lookup"><span data-stu-id="780d0-181">nov.</span></span> <span data-ttu-id="780d0-182">Dic。</span><span class="sxs-lookup"><span data-stu-id="780d0-182">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="780d0-183">Func_eu_date1 （已過時）</span><span class="sxs-lookup"><span data-stu-id="780d0-183">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="780d0-184">此函數已過時，因為它只支援葡萄牙文月份名稱，而這些名稱現在已包含在 `Func_eu_date` 上述函數中。</span><span class="sxs-lookup"><span data-stu-id="780d0-184">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="780d0-185">此函數會以葡萄牙文中常用的格式來尋找日期。</span><span class="sxs-lookup"><span data-stu-id="780d0-185">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="780d0-186">此函數的格式與 `Func_eu_date` 使用的語言不同。</span><span class="sxs-lookup"><span data-stu-id="780d0-186">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="780d0-187">範例：</span><span class="sxs-lookup"><span data-stu-id="780d0-187">Examples:</span></span>
  
- <span data-ttu-id="780d0-188">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="780d0-188">2 Dez 2016</span></span>
    
- <span data-ttu-id="780d0-189">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="780d0-189">02 dez 2016</span></span>
    
- <span data-ttu-id="780d0-190">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="780d0-190">2 Dez 16</span></span>
    
- <span data-ttu-id="780d0-191">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="780d0-191">2/12/2016</span></span>
    
- <span data-ttu-id="780d0-192">02/12/16</span><span class="sxs-lookup"><span data-stu-id="780d0-192">02/12/16</span></span>
    
- <span data-ttu-id="780d0-193">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="780d0-193">2-Dez-2016</span></span>
    
- <span data-ttu-id="780d0-194">2-12-16</span><span class="sxs-lookup"><span data-stu-id="780d0-194">2-12-16</span></span>
    
<span data-ttu-id="780d0-195">公認的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="780d0-195">Accepted month names:</span></span>
  
- <span data-ttu-id="780d0-196">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="780d0-196">Portuguese</span></span>
    
  - <span data-ttu-id="780d0-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="780d0-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="780d0-198">jan fev mar abr mai 06 年6月1日，設定為11月 dez</span><span class="sxs-lookup"><span data-stu-id="780d0-198">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="780d0-199">Func_eu_date2 （已過時）</span><span class="sxs-lookup"><span data-stu-id="780d0-199">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="780d0-200">此函數已過時，因為它只支援荷蘭月份名稱，而這些名稱現在已包含在 `Func_eu_date` 上述函數中。</span><span class="sxs-lookup"><span data-stu-id="780d0-200">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="780d0-201">此函數會以荷蘭文中常用的格式來尋找日期。</span><span class="sxs-lookup"><span data-stu-id="780d0-201">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="780d0-202">此函數的格式與 `Func_eu_date` 使用的語言不同。</span><span class="sxs-lookup"><span data-stu-id="780d0-202">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="780d0-203">範例：</span><span class="sxs-lookup"><span data-stu-id="780d0-203">Examples:</span></span>
  
- <span data-ttu-id="780d0-204">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="780d0-204">2 Mei 2016</span></span>
    
- <span data-ttu-id="780d0-205">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="780d0-205">02 mei 2016</span></span>
    
- <span data-ttu-id="780d0-206">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="780d0-206">2 Mei 16</span></span>
    
- <span data-ttu-id="780d0-207">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="780d0-207">2/12/2016</span></span>
    
- <span data-ttu-id="780d0-208">02/12/16</span><span class="sxs-lookup"><span data-stu-id="780d0-208">02/12/16</span></span>
    
- <span data-ttu-id="780d0-209">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="780d0-209">2-Mei-2016</span></span>
    
- <span data-ttu-id="780d0-210">2-12-16</span><span class="sxs-lookup"><span data-stu-id="780d0-210">2-12-16</span></span>
    
<span data-ttu-id="780d0-211">公認的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="780d0-211">Accepted month names:</span></span>
  
- <span data-ttu-id="780d0-212">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="780d0-212">Dutch</span></span>
    
  - <span data-ttu-id="780d0-213">januari，februari，maart，四月，mei，juni，juli，augustus，九月份，ocktober，十月，11月，十二月</span><span class="sxs-lookup"><span data-stu-id="780d0-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="780d0-214">jan jan maart apr mei 年6月8日9月9日在十二月進行 okt</span><span class="sxs-lookup"><span data-stu-id="780d0-214">jan feb maart apr mei jun jul aug sep sept out okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="780d0-215">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="780d0-215">Func_expiration_date</span></span>

<span data-ttu-id="780d0-216">此函數會以信用卡和轉帳卡所使用的格式來尋找日期，而不是以月為單位來扣除天數。</span><span class="sxs-lookup"><span data-stu-id="780d0-216">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="780d0-217">此函數會比對「月/年」、「月-年」、「[month name] 年] 和「[month 簡寫] 年 "格式的日期。</span><span class="sxs-lookup"><span data-stu-id="780d0-217">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="780d0-218">月份的名稱或縮寫不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="780d0-218">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="780d0-219">範例：</span><span class="sxs-lookup"><span data-stu-id="780d0-219">Examples:</span></span>
  
- <span data-ttu-id="780d0-220">MM/YY--例如01/11 或1/11</span><span class="sxs-lookup"><span data-stu-id="780d0-220">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="780d0-221">MM/YYYY--例如01/2011 或1/2011</span><span class="sxs-lookup"><span data-stu-id="780d0-221">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="780d0-222">MM-YY--例如01-22 或1-11</span><span class="sxs-lookup"><span data-stu-id="780d0-222">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="780d0-223">MM-YYYY--例如01-2000 或1-2000</span><span class="sxs-lookup"><span data-stu-id="780d0-223">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="780d0-224">下列格式支援 YY 或 YYYY：</span><span class="sxs-lookup"><span data-stu-id="780d0-224">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="780d0-225">Month-YYYY--2010 年1月1日或一月-2010 或 Jan-10 或年1月1日</span><span class="sxs-lookup"><span data-stu-id="780d0-225">Month-YYYY -- for example Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="780d0-226">Month YYYY--例如，"一月 2010" 或 "Jan 2010" 或 "Jan 10" 或 "Jan 10"</span><span class="sxs-lookup"><span data-stu-id="780d0-226">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="780d0-227">MonthYYYY--例如 "january2010" 或 "Jan2010" 或 "january10" 或 "Jan10"</span><span class="sxs-lookup"><span data-stu-id="780d0-227">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="780d0-228">Month/YYYY--例如，' 一月份/2010 ' 或 ' Jan/2010 ' or "Jan/10" 或 "Jan/10"</span><span class="sxs-lookup"><span data-stu-id="780d0-228">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="780d0-229">公認的月份名稱：</span><span class="sxs-lookup"><span data-stu-id="780d0-229">Accepted month names:</span></span>
  
- <span data-ttu-id="780d0-230">English</span><span class="sxs-lookup"><span data-stu-id="780d0-230">English</span></span>
    
  - <span data-ttu-id="780d0-231">一月份、二月份、三月份、四月、六月、六月、十二月、十二月、十二月、十月、十二月、十二月</span><span class="sxs-lookup"><span data-stu-id="780d0-231">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="780d0-232">Jan 02 月4月8日在十二月</span><span class="sxs-lookup"><span data-stu-id="780d0-232">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="780d0-233">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="780d0-233">Func_us_address</span></span>

<span data-ttu-id="780d0-234">此函數會尋找美國的狀態名稱或郵政縮寫後接有效的郵遞區號，就像在通信地址中使用。</span><span class="sxs-lookup"><span data-stu-id="780d0-234">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they're used in postal addresses.</span></span> <span data-ttu-id="780d0-235">郵遞區號必須是與美國州名稱或縮略語相關聯的正確郵遞區號之一。</span><span class="sxs-lookup"><span data-stu-id="780d0-235">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="780d0-236">美國的狀態名稱及郵遞區號不能以標點符號或字母分隔。</span><span class="sxs-lookup"><span data-stu-id="780d0-236">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="780d0-237">範例：</span><span class="sxs-lookup"><span data-stu-id="780d0-237">Examples:</span></span>
  
- <span data-ttu-id="780d0-238">華盛頓98052</span><span class="sxs-lookup"><span data-stu-id="780d0-238">Washington 98052</span></span>
    
- <span data-ttu-id="780d0-239">華盛頓98052-9998</span><span class="sxs-lookup"><span data-stu-id="780d0-239">Washington 98052-9998</span></span>
    
- <span data-ttu-id="780d0-240">WA 98052</span><span class="sxs-lookup"><span data-stu-id="780d0-240">WA 98052</span></span>
    
- <span data-ttu-id="780d0-241">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="780d0-241">WA 98052-9998</span></span>
    

