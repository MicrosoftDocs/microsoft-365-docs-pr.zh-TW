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
ms.openlocfilehash: 6934edba6eef03bc9d4bfc5c1c69f127a7d3a0e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817962"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="b0d7c-103">自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="b0d7c-103">Custom sensitive information types</span></span>

<span data-ttu-id="b0d7c-104">Microsoft 365 包含可供您在組織中使用的許多內建的敏感性資訊類型，例如[資料外洩防護](data-loss-prevention-policies.md) (DLP)，或是 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-104">Microsoft 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="b0d7c-105">內建的敏感性資訊類型會根據規則運算式 (regex) 或函數所定義的模式，協助識別及保護信用卡卡號、銀行帳戶號碼、護照號碼等。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-105">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="b0d7c-106">若要深入了解，請參閱[機密資訊類型尋找的目標為何](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-106">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="b0d7c-107">不過，如果您需要識別及保護不同類型的敏感性資訊，例如使用您組織特定格式的員工識別碼或專案編號，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="b0d7c-107">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="b0d7c-108">若要這麼做，您可以建立自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-108">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="b0d7c-109">自訂機密資訊類型的基礎部分如下：</span><span class="sxs-lookup"><span data-stu-id="b0d7c-109">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="b0d7c-110">**主要模式**：員工識別碼、專案編號等等。這通常由規則運算式 (RegEx) 識別，但它也可以是關鍵字清單。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-110">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="b0d7c-111">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number.</span><span class="sxs-lookup"><span data-stu-id="b0d7c-111">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number.</span></span> <span data-ttu-id="b0d7c-112">Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions.</span><span class="sxs-lookup"><span data-stu-id="b0d7c-112">Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions.</span></span> <span data-ttu-id="b0d7c-113">This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span><span class="sxs-lookup"><span data-stu-id="b0d7c-113">This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="b0d7c-114">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for.</span><span class="sxs-lookup"><span data-stu-id="b0d7c-114">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for.</span></span> <span data-ttu-id="b0d7c-115">You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span><span class="sxs-lookup"><span data-stu-id="b0d7c-115">You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![確切辨識項和近似值視窗的圖表](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="b0d7c-117">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for.</span><span class="sxs-lookup"><span data-stu-id="b0d7c-117">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for.</span></span> <span data-ttu-id="b0d7c-118">You can assign higher levels of confidence for matches that are detected by using more evidence.</span><span class="sxs-lookup"><span data-stu-id="b0d7c-118">You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="b0d7c-119">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies.</span><span class="sxs-lookup"><span data-stu-id="b0d7c-119">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies.</span></span> <span data-ttu-id="b0d7c-120">When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span><span class="sxs-lookup"><span data-stu-id="b0d7c-120">When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![執行個體計數和比對正確性選項](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="b0d7c-122">建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="b0d7c-122">Creating custom sensitive information types</span></span>

<span data-ttu-id="b0d7c-123">若要在安全性與合規性中心建立自訂敏感性資訊類型，您可以從數個選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="b0d7c-123">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="b0d7c-124">**使用 EDM** (新增！) 您可以使用以精確資料比對 (EDM) 為基礎的分類來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-124">**Use EDM** (NEW!) You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="b0d7c-125">此方法可讓您使用您可以定期更新的安全資料庫來建立動態敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-125">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="b0d7c-126">請參閱[使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-126">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="b0d7c-127">**使用 PowerShell** 您可以使用 PowerShell 來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-127">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="b0d7c-128">雖然此方法比使用 UI 更複雜，但是您有多個組態選項。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-128">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="b0d7c-129">請參閱[在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-129">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

- <span data-ttu-id="b0d7c-130">**使用 UI** 您可以使用安全性與合規性中心 UI 來設定自訂敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-130">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="b0d7c-131">使用此方法，您可以使用規則運算式、關鍵字和關鍵字字典。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-131">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="b0d7c-132">若要進一步了解，請參閱[建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d7c-132">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>



