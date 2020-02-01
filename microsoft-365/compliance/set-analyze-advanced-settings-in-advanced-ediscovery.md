---
title: 設定分析進階設定 Office 365 進階電子文件中
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: '了解如何設定進階的設定，包括近似重複項目、 電子郵件執行緒和佈景主題，Office 365 進階 eDiscovery 中分析處理程序。 '
ms.openlocfilehash: 2c2a104b834d8da9d0d10f93980b4f2cbb6294c8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601510"
---
# <a name="set-analyze-advanced-settings-in-office-365-advanced-ediscovery"></a><span data-ttu-id="68267-103">設定分析進階設定 Office 365 進階電子文件中</span><span class="sxs-lookup"><span data-stu-id="68267-103">Set Analyze advanced settings in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="68267-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="68267-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="68267-106">進階電子文件探索分析模組設定為提供進階的預設參數。</span><span class="sxs-lookup"><span data-stu-id="68267-106">Advanced eDiscovery provides default advanced parameters for Analyze module settings.</span></span> <span data-ttu-id="68267-107">下列程序說明您可以指定的設定。</span><span class="sxs-lookup"><span data-stu-id="68267-107">The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="68267-108">在 [**準備\>分析\>安裝**索引標籤上，按一下 [**進階設定]** （在頁面底部）。</span><span class="sxs-lookup"><span data-stu-id="68267-108">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page).</span></span> <span data-ttu-id="68267-109">會顯示下列面板。</span><span class="sxs-lookup"><span data-stu-id="68267-109">The following panel is displayed.</span></span> 
    
    ![設定分析進階設定](media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="68267-111">在**接近重複項目和電子郵件執行緒參數**，視需要選取下列值：</span><span class="sxs-lookup"><span data-stu-id="68267-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="68267-112">**字詞的最小數目**： 單字、 下方會檔案不會送出供近似重複分析的最小數目。</span><span class="sxs-lookup"><span data-stu-id="68267-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="68267-113">**字詞的最大數目**： 單字、 上述其中一個檔案不會送出近似重複分析的最大數目。</span><span class="sxs-lookup"><span data-stu-id="68267-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="68267-114">**電子郵件相似性**： 最低層級的類似的兩個電子郵件被視為類似。</span><span class="sxs-lookup"><span data-stu-id="68267-114">**Email similarity**: Minimal level of resemblance for two emails to be considered similar.</span></span> <span data-ttu-id="68267-115">值一定是等於或大於文件相似性。</span><span class="sxs-lookup"><span data-stu-id="68267-115">Value is always equal to, or larger than document similarity.</span></span> <span data-ttu-id="68267-116">預設值為 90%。</span><span class="sxs-lookup"><span data-stu-id="68267-116">Default is 90%.</span></span>
    
3. <span data-ttu-id="68267-117">**佈景主題參數**中選取要包含在期間分析處理的佈景主題中的數字的**佈景主題分析中的包含數字**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="68267-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="68267-118">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68267-118">Click **Save**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="68267-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="68267-119">See also</span></span>

[<span data-ttu-id="68267-120">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="68267-120">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="68267-121">了解文件相似性</span><span class="sxs-lookup"><span data-stu-id="68267-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="68267-122">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="68267-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="68267-123">設定忽略文字</span><span class="sxs-lookup"><span data-stu-id="68267-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="68267-124">檢視分析結果</span><span class="sxs-lookup"><span data-stu-id="68267-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

