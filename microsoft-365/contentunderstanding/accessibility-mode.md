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
# <a name="sharepoint-syntex-accessibility-mode"></a>SharePoint Syntex 協助工具模式

在 [SharePoint Syntex](index.md)中，使用者可以在使用範例檔時，在模型訓練 (標籤、訓練、測試) 的各個階段中開啟協助工具模式。 使用協助工具模式可協助弱視使用者在流覽及標示檔檢視器中的專案時，獲得更輕鬆的鍵盤協助工具。

這可協助使用者使用其鍵盤來流覽檔檢視器中的文字，並聽出旁白的旁白，不僅包括選取的) 文字，也包含巨集指令 (例如標記或移除選取文字中的標籤，或是在您訓練模型時使用其他範例檔的標記值。 


![協助工具模式](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>需求

若要聽到旁白的音訊，請務必在 Windows 10 系統的 [講述人] 設定中開啟「 [講述人」應用程式](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) 。

![開啟 [朗讀程式]](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>鍵盤使用者的標籤

針對使用協助工具模式的鍵盤使用者，如果在檢視器的範例檔中標記文字，您可以使用下列按鍵：

- 索引標籤：向前移動並選取下一個字。
- Tab + Shift：向後移動並選取上一個字。
- Enter：標籤或從選取的單字移除標籤。
- 向右鍵：向內移動選取的單字中的個別字元。
- 向左鍵：向後移動選取的單字中的個別字元。

> [!NOTE]
> 如果您要為單一標籤標記多個字，您必須為每個單字加上標籤。


## <a name="narration"></a>敘事

針對使用協助工具模式的講述人使用者，請使用相同的鍵盤導覽，以供鍵盤使用者流覽檢視器中的範例檔。

當您流覽範例檔及標籤字串值時，「講述人」會為使用者提供下列音訊提示：

- 當您使用鍵盤流覽檔檢視器時，[講述人] 音訊會將選取的字串狀態。
- 在選取的字串內，[講述人] 音訊會在您使用向左鍵或向右鍵來選取字串中的每個字元時，為您陳述該字串。
- 如果您選取一個已標示的字串，則「講述人」會指出值，然後再「標示」。  例如，如果標籤值為 "Contoso"，它會將 "Costoso 標示" 狀態。 
- 在 [訓練] 索引標籤中，如果您在 [檔檢視器] 中選取只有預測的字串，則 [講述人] 音訊會指出值，然後「預測」。 當訓練會在檔中預測的值不符合使用者所標示的值時，就會發生這種情況。
- 在 [訓練] 索引標籤中，如果您在已標示及預測的檔檢視器中選取字串，[講述人] 音訊會指出值，然後「標籤及預測」。 當訓練成功而且預測值和使用者標籤之間有相符的情況時，就會發生這種情況。



在查看字串標籤或已移除標籤中的標籤之後，在您結束之前，「朗讀程式音訊」會警告您儲存您的變更。

## <a name="see-also"></a>另請參閱

[建立擷取器](create-an-extractor.md)</br>

[建立分類器](create-a-classifier.md)</br>










 


  
  



