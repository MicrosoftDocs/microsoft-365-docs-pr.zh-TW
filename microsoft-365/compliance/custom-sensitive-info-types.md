---
title: DLP 的自訂敏感性資訊類型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 取得資料遺失防護（DLP）的自訂機密資訊類型概覽，例如 [主要模式]、[字元近似] 和 [信任等級]。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3b3e30c75641dde16726e1d98c8f12c4437b0df6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685473"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="6d539-103">自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="6d539-103">Custom sensitive information types</span></span>

<span data-ttu-id="6d539-104">Microsoft 365 包含可供您在組織中使用的許多內建的敏感性資訊類型，例如[資料外洩防護](data-loss-prevention-policies.md) (DLP)，或是 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="6d539-104">Microsoft 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="6d539-105">內建的敏感性資訊類型會根據規則運算式 (regex) 或函數所定義的模式，協助識別及保護信用卡卡號、銀行帳戶號碼、護照號碼等。</span><span class="sxs-lookup"><span data-stu-id="6d539-105">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="6d539-106">若要深入了解，請參閱[機密資訊類型尋找的目標為何](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="6d539-106">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="6d539-107">不過，如果您需要識別及保護不同類型的敏感性資訊，例如使用您組織特定格式的員工識別碼或專案編號，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="6d539-107">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="6d539-108">若要這麼做，您可以建立自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="6d539-108">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="6d539-109">自訂機密資訊類型的基礎部分如下：</span><span class="sxs-lookup"><span data-stu-id="6d539-109">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="6d539-110">**主要模式**：員工識別碼、專案編號等等。這通常由規則運算式 (RegEx) 識別，但它也可以是關鍵字清單。</span><span class="sxs-lookup"><span data-stu-id="6d539-110">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="6d539-p103">**其他辨識項**：假設您正在尋找九位數的員工識別碼。並非所有的九位數都是員工識別碼，因此您可以搜尋其他文字：像是 "employee"、"badge"、"ID" 這類的關鍵字，或其他以規則運算式為基礎的文字模式。此支援辨識項 (也稱為_支援_或_確切_辨識項)，可增加在內容中找到的九位數確實為員工識別碼的可能性。</span><span class="sxs-lookup"><span data-stu-id="6d539-p103">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="6d539-p104">**字元近似值**：主要模式與支援辨識項彼此越接近，偵測到的內容越可能是您要尋找的內容，這是合理的。您可以指定主要模式與支援辨識項之間的字元距離 (也稱為_近似值視窗_)，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="6d539-p104">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![確切辨識項和近似值視窗的圖表](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="6d539-p105">**信賴等級**：您具有的支援辨識項越多，相符項目包含您要尋找的機密資訊的可能性就越高。您可以針對使用更多辨識項偵測到的相符項目指派更高等級的信賴。</span><span class="sxs-lookup"><span data-stu-id="6d539-p105">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="6d539-p106">滿足條件時，模式會傳回計數和信賴等級，您可以在 DLP 原則的條件中使用。當您將會偵測機密資訊類型的條件新增至 DLP 原則時，可以編輯計數和信賴等級，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="6d539-p106">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![執行個體計數和比對正確性選項](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="6d539-122">建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="6d539-122">Creating custom sensitive information types</span></span>

<span data-ttu-id="6d539-123">若要在安全性與合規性中心建立自訂敏感性資訊類型，您可以從數個選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="6d539-123">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="6d539-124">**使用 EDM** 您可以使用以精確資料比對 (EDM) 為基礎的分類來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="6d539-124">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="6d539-125">此方法可讓您使用您可以定期更新的安全資料庫來建立動態敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="6d539-125">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="6d539-126">請參閱[使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="6d539-126">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="6d539-127">**使用 PowerShell** 您可以使用 PowerShell 來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="6d539-127">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="6d539-128">雖然此方法比使用 UI 更複雜，但是您有多個組態選項。</span><span class="sxs-lookup"><span data-stu-id="6d539-128">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="6d539-129">請參閱[在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="6d539-129">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

- <span data-ttu-id="6d539-130">**使用 UI** 您可以使用安全性與合規性中心 UI 來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="6d539-130">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="6d539-131">使用此方法，您可以使用規則運算式、關鍵字和關鍵字字典。</span><span class="sxs-lookup"><span data-stu-id="6d539-131">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="6d539-132">若要進一步了解，請參閱[建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="6d539-132">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6d539-133">Microsoft 365 資訊保護目前支援預覽版的雙位元組字元集語言：</span><span class="sxs-lookup"><span data-stu-id="6d539-133">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="6d539-134">中文 (簡體)</span><span class="sxs-lookup"><span data-stu-id="6d539-134">Chinese (simplified)</span></span>
> - <span data-ttu-id="6d539-135">中文 (繁體)</span><span class="sxs-lookup"><span data-stu-id="6d539-135">Chinese (traditional)</span></span>
> - <span data-ttu-id="6d539-136">韓文</span><span class="sxs-lookup"><span data-stu-id="6d539-136">Korean</span></span>
> - <span data-ttu-id="6d539-137">日文</span><span class="sxs-lookup"><span data-stu-id="6d539-137">Japanese</span></span>
> 
><span data-ttu-id="6d539-138">此預覽僅限商愛業雲端中，且僅限部署至：</span><span class="sxs-lookup"><span data-stu-id="6d539-138">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="6d539-139">日本</span><span class="sxs-lookup"><span data-stu-id="6d539-139">Japan</span></span>
> - <span data-ttu-id="6d539-140">韓國</span><span class="sxs-lookup"><span data-stu-id="6d539-140">Korea</span></span>
> - <span data-ttu-id="6d539-141">中國</span><span class="sxs-lookup"><span data-stu-id="6d539-141">China</span></span>
> - <span data-ttu-id="6d539-142">香港特別行政區</span><span class="sxs-lookup"><span data-stu-id="6d539-142">Hong Kong</span></span>
> - <span data-ttu-id="6d539-143">澳門特別行政區</span><span class="sxs-lookup"><span data-stu-id="6d539-143">Macau</span></span>
> - <span data-ttu-id="6d539-144">台灣</span><span class="sxs-lookup"><span data-stu-id="6d539-144">Taiwan</span></span>
>
><span data-ttu-id="6d539-145">這項支援適用於敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="6d539-145">This support is available for sensitive information types.</span></span> <span data-ttu-id="6d539-146">如需詳細資訊，請參閱 [資訊保護支援雙位元組字元集的版本資訊 (預覽版)](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="6d539-146">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

