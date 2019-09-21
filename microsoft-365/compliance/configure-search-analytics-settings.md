---
title: 設定搜尋和分析設定
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 0456ee21087c7fe05c3ef96d517feb468c7cfe5e
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076621"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="f6613-102">設定搜尋和分析設定</span><span class="sxs-lookup"><span data-stu-id="f6613-102">Configure search and analytics settings</span></span>

## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="f6613-103">近似重複項目和電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="f6613-103">Near duplicates and email threading</span></span>

<span data-ttu-id="f6613-104">在這個區段中，您可以設定的參數重複資料偵測，接近重複資料偵測和電子郵件執行緒。</span><span class="sxs-lookup"><span data-stu-id="f6613-104">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="f6613-105">啟用/停用： 包含重複資料偵測，接近重複資料偵測和電子郵件執行緒分析流程如果已啟用的一部分。</span><span class="sxs-lookup"><span data-stu-id="f6613-105">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="f6613-106">因為他們建置彼此，您必須啟用所有的這些或全部予以停用。</span><span class="sxs-lookup"><span data-stu-id="f6613-106">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="f6613-107">臨界值： 如果超出臨界值的兩個文件相似性層級，它們會放置在接近重複的設定相同。</span><span class="sxs-lookup"><span data-stu-id="f6613-107">Threshold: if the similarity level of two documents are above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="f6613-108">根據預設隱藏重複項目： 使用預設設定如果開啟此設定時，會套用篩選器來隱藏重複的文件。</span><span class="sxs-lookup"><span data-stu-id="f6613-108">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default.</span></span> <span data-ttu-id="f6613-109">可以在設定必要的工作以手動方式移除篩選。</span><span class="sxs-lookup"><span data-stu-id="f6613-109">The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="f6613-110">字詞的最小值/最大數目： 近似重複項目和電子郵件執行緒會僅在執行最小的數字和最字詞數目上限至少要有的文件。</span><span class="sxs-lookup"><span data-stu-id="f6613-110">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>
<span data-ttu-id="f6613-111">如需詳細資訊，請參閱[接近重複資料偵測](near-duplicates.md)和[電子郵件執行緒](email-threading.md)。</span><span class="sxs-lookup"><span data-stu-id="f6613-111">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="f6613-112">佈景主題</span><span class="sxs-lookup"><span data-stu-id="f6613-112">Themes</span></span>

<span data-ttu-id="f6613-113">在這個區段中，您可以設定的佈景主題的參數。</span><span class="sxs-lookup"><span data-stu-id="f6613-113">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="f6613-114">啟用/停用： 包括叢集一部分分析流程如果已啟用的佈景主題。</span><span class="sxs-lookup"><span data-stu-id="f6613-114">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>
- <span data-ttu-id="f6613-115">以動態方式動態調整的佈景主題數目上限： 在某些情況下，沒有足夠的文件，以產生所需的佈景主題數目。</span><span class="sxs-lookup"><span data-stu-id="f6613-115">Adjust maximum number of themes dynamically dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="f6613-116">如果開啟此設定，然後而不是嘗試強制所需的數目上限的佈景主題，系統會調整佈景主題的數目上限以動態方式。</span><span class="sxs-lookup"><span data-stu-id="f6613-116">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>
- <span data-ttu-id="f6613-117">佈景主題數目上限： 所需的佈景主題數目</span><span class="sxs-lookup"><span data-stu-id="f6613-117">Maximum number of themes: desired number of themes</span></span>
- <span data-ttu-id="f6613-118">包含佈景主題中的數字： 啟用時，產生的佈景主題時，它會包括中的數字。</span><span class="sxs-lookup"><span data-stu-id="f6613-118">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="f6613-119">光學字元辨識 (OCR)</span><span class="sxs-lookup"><span data-stu-id="f6613-119">Optical character recognition (OCR)</span></span>

<span data-ttu-id="f6613-120">時開啟此設定，將會 ingested 成工作集，讓他們可以是可搜尋的映像上執行 OCR。</span><span class="sxs-lookup"><span data-stu-id="f6613-120">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="f6613-121">忽略的文字</span><span class="sxs-lookup"><span data-stu-id="f6613-121">Ignore text</span></span>

<span data-ttu-id="f6613-122">有某些敘述性文字會降低品質的分析，例如冗長的免責聲明，新增至特定的電子郵件，不論電子郵件的內容，其中的執行個體。</span><span class="sxs-lookup"><span data-stu-id="f6613-122">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="f6613-123">如果您知道這種情況下，您可以藉由指定的文字 （支援 RegEx） 和其分析從排除此文字應該如包含文字的模組。</span><span class="sxs-lookup"><span data-stu-id="f6613-123">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>