---
title: 設定搜尋與分析設定-資料調查
f1.keywords:
- NOCSH
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
description: 瞭解如何在管理資料調查時，設定搜尋及分析設定，例如接近重複專案、電子郵件執行緒及主題。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ebc04e68c4d8854c91ceae75b164cc061e77aad4
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277080"
---
# <a name="configure-search-and-analytics-settings-in-data-investigations"></a><span data-ttu-id="3eca6-103">在資料調查中設定搜尋及分析設定</span><span class="sxs-lookup"><span data-stu-id="3eca6-103">Configure search and analytics settings in Data Investigations</span></span>

## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="3eca6-104">接近重複專案和電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="3eca6-104">Near duplicates and email threading</span></span>

<span data-ttu-id="3eca6-105">在本節中，您可以設定重複偵測、接近重複偵測和電子郵件執行緒的參數。</span><span class="sxs-lookup"><span data-stu-id="3eca6-105">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="3eca6-106">啟用/停用：在分析流程中包含重複偵測、接近重複偵測，以及在分析流程中的電子郵件執行緒（如果已啟用）。</span><span class="sxs-lookup"><span data-stu-id="3eca6-106">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="3eca6-107">因為它們彼此上建立，您必須全部啟用或全部停用。</span><span class="sxs-lookup"><span data-stu-id="3eca6-107">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="3eca6-108">臨界值：如果兩個檔的相似性層級超過臨界值，它們就會放在相同的接近重複的集合中。</span><span class="sxs-lookup"><span data-stu-id="3eca6-108">Threshold: if the similarity level of two documents is above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="3eca6-109">依預設隱藏重複：如果啟用此設定，則預設會在工作集中套用隱藏重複檔案的篩選器。</span><span class="sxs-lookup"><span data-stu-id="3eca6-109">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default.</span></span> <span data-ttu-id="3eca6-110">如有必要，可在工作集內手動移除篩選。</span><span class="sxs-lookup"><span data-stu-id="3eca6-110">The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="3eca6-111">最小/最大文字數目：接近重複專案和電子郵件執行緒只會在至少具有最少字數的檔上執行，最多隻會在文字的最大數目。</span><span class="sxs-lookup"><span data-stu-id="3eca6-111">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>

<span data-ttu-id="3eca6-112">如需詳細資訊，請參閱 [近期重複偵測](near-duplicates.md) 和 [電子郵件執行緒](email-threading.md)。</span><span class="sxs-lookup"><span data-stu-id="3eca6-112">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="3eca6-113">佈景主題</span><span class="sxs-lookup"><span data-stu-id="3eca6-113">Themes</span></span>

<span data-ttu-id="3eca6-114">在本節中，您可以為主題設定參數。</span><span class="sxs-lookup"><span data-stu-id="3eca6-114">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="3eca6-115">啟用/停用：在分析流程中包含主題叢集（如果已啟用）。</span><span class="sxs-lookup"><span data-stu-id="3eca6-115">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>

- <span data-ttu-id="3eca6-116">動態調整主題數目上限：在某些情況下，沒有足夠的檔來產生所需的主題數目。</span><span class="sxs-lookup"><span data-stu-id="3eca6-116">Adjust maximum number of themes dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="3eca6-117">如果開啟此設定，而不是嘗試強制所需的主題數目上限，系統就會自動調整主題的最大數目。</span><span class="sxs-lookup"><span data-stu-id="3eca6-117">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>

- <span data-ttu-id="3eca6-118">主題數目上限：所需的主題數目。</span><span class="sxs-lookup"><span data-stu-id="3eca6-118">Maximum number of themes: desired number of themes.</span></span>

- <span data-ttu-id="3eca6-119">在主題中包含編號：啟用時，它會在產生主題時包含數位。</span><span class="sxs-lookup"><span data-stu-id="3eca6-119">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="3eca6-120">光學字元辨識 (OCR) </span><span class="sxs-lookup"><span data-stu-id="3eca6-120">Optical character recognition (OCR)</span></span>

<span data-ttu-id="3eca6-121">開啟此設定時，會在 ingested 至工作集的影像上執行 OCR，使其可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="3eca6-121">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="3eca6-122">忽略文字</span><span class="sxs-lookup"><span data-stu-id="3eca6-122">Ignore text</span></span>

<span data-ttu-id="3eca6-123">在某些情況下，有些文字會降低 analytics 的品質，例如，即使電子郵件的內容，也會新增至特定電子郵件的冗長免責聲明。</span><span class="sxs-lookup"><span data-stu-id="3eca6-123">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="3eca6-124">如果您知道這種情況，您可以指定 (RegEx 支援的文字，) 以及應排除文字的模組，即可從分析中排除此文字。</span><span class="sxs-lookup"><span data-stu-id="3eca6-124">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>
