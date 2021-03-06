---
title: 'SharePoint Syntex 協助工具模式 '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: 瞭解如何在訓練 SharePoint Syntex 中的模型時使用協助工具模式。
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515145"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="14108-103">SharePoint Syntex 協助工具模式</span><span class="sxs-lookup"><span data-stu-id="14108-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="14108-104">在 [SharePoint Syntex](index.md)中，使用者可以在使用範例檔時，在模型訓練 (標籤、訓練、測試) 的各個階段中開啟協助工具模式。</span><span class="sxs-lookup"><span data-stu-id="14108-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="14108-105">使用協助工具模式可協助弱視使用者在流覽及標示檔檢視器中的專案時，獲得更輕鬆的鍵盤協助工具。</span><span class="sxs-lookup"><span data-stu-id="14108-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="14108-106">這可協助使用者使用其鍵盤來流覽檔檢視器中的文字，並聽出旁白的旁白，不僅包括選取的) 文字，也包含巨集指令 (例如標記或移除選取文字中的標籤，或是在您訓練模型時使用其他範例檔的標記值。</span><span class="sxs-lookup"><span data-stu-id="14108-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![協助工具模式](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="14108-108">需求</span><span class="sxs-lookup"><span data-stu-id="14108-108">Requirements</span></span>

<span data-ttu-id="14108-109">若要聽到旁白的音訊，請務必在 Windows 10 系統的 [講述人] 設定中開啟「 [講述人」應用程式](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) 。</span><span class="sxs-lookup"><span data-stu-id="14108-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![開啟 [朗讀程式]](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="14108-111">鍵盤使用者的標籤</span><span class="sxs-lookup"><span data-stu-id="14108-111">Labeling for keyboard users</span></span>

<span data-ttu-id="14108-112">針對使用協助工具模式的鍵盤使用者，如果在檢視器的範例檔中標記文字，您可以使用下列按鍵：</span><span class="sxs-lookup"><span data-stu-id="14108-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="14108-113">索引標籤：向前移動並選取下一個字。</span><span class="sxs-lookup"><span data-stu-id="14108-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="14108-114">Tab + Shift：向後移動並選取上一個字。</span><span class="sxs-lookup"><span data-stu-id="14108-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="14108-115">Enter：標籤或從選取的單字移除標籤。</span><span class="sxs-lookup"><span data-stu-id="14108-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="14108-116">向右鍵：向內移動選取的單字中的個別字元。</span><span class="sxs-lookup"><span data-stu-id="14108-116">Right arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="14108-117">向左鍵：向後移動選取的單字中的個別字元。</span><span class="sxs-lookup"><span data-stu-id="14108-117">Left arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="14108-118">如果您要為單一標籤標記多個字，您必須為每個單字加上標籤。</span><span class="sxs-lookup"><span data-stu-id="14108-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="14108-119">敘事</span><span class="sxs-lookup"><span data-stu-id="14108-119">Narration</span></span>

<span data-ttu-id="14108-120">針對使用協助工具模式的講述人使用者，請使用相同的鍵盤導覽，以供鍵盤使用者流覽檢視器中的範例檔。</span><span class="sxs-lookup"><span data-stu-id="14108-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="14108-121">當您流覽範例檔及標籤字串值時，「講述人」會為使用者提供下列音訊提示：</span><span class="sxs-lookup"><span data-stu-id="14108-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="14108-122">當您使用鍵盤流覽檔檢視器時，[講述人] 音訊會將選取的字串狀態。</span><span class="sxs-lookup"><span data-stu-id="14108-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="14108-123">在選取的字串內，[講述人] 音訊會在您使用向左鍵或向右鍵來選取字串中的每個字元時，為您陳述該字串。</span><span class="sxs-lookup"><span data-stu-id="14108-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the left or right arrow keys.</span></span>
- <span data-ttu-id="14108-124">如果您選取一個已標示的字串，則「講述人」會指出值，然後再「標示」。</span><span class="sxs-lookup"><span data-stu-id="14108-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="14108-125">例如，如果標籤值為 "Contoso"，它會將 "Costoso 標示" 狀態。</span><span class="sxs-lookup"><span data-stu-id="14108-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="14108-126">在 [訓練] 索引標籤中，如果您在 [檔檢視器] 中選取只有預測的字串，則 [講述人] 音訊會指出值，然後「預測」。</span><span class="sxs-lookup"><span data-stu-id="14108-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="14108-127">當訓練會在檔中預測的值不符合使用者所標示的值時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="14108-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="14108-128">在 [訓練] 索引標籤中，如果您在已標示及預測的檔檢視器中選取字串，[講述人] 音訊會指出值，然後「標籤及預測」。</span><span class="sxs-lookup"><span data-stu-id="14108-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="14108-129">當訓練成功而且預測值和使用者標籤之間有相符的情況時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="14108-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="14108-130">在查看字串標籤或已移除標籤中的標籤之後，在您結束之前，「朗讀程式音訊」會警告您儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="14108-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="14108-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="14108-131">See Also</span></span>

[<span data-ttu-id="14108-132">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="14108-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="14108-133">建立分類器</span><span class="sxs-lookup"><span data-stu-id="14108-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



