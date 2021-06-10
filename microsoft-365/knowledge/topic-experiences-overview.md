---
title: Microsoft Viva Topics 概觀
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Viva Topics 概觀。
ms.openlocfilehash: c95e611a98609ff13a41854a6fb25b6ae88b43d8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877809"
---
# <a name="microsoft-viva-topics-overview"></a>Microsoft Viva Topics 概觀 

Viva 主題使用 Microsoft AI 技術、Microsoft 365、microsoft Graph、搜尋及其他元件和服務，以在日常使用的 Microsoft 365 應用程式中，為您的使用者提供知識，從 SharePoint 新式頁面、Microsoft Search 及在 Word 中搜尋，PowerPoint，Outlook 和 Excel。

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

<br/>

Viva 主題可協助解決許多公司的重要業務問題，在使用者需要時提供資訊給使用者。 例如，新員工需要快速學習許多新資訊，但在閱讀公司資訊時，會遇到他們完全不知道的詞彙。 為了深入了解，使用者可能需要離開他們正在進行的工作，並花費寶貴的時間搜尋詳細資料，例如詞彙的意義、組織中誰是主題專家，以及可能與詞彙相關的網站和文件。

Viva Topics 使用 AI 來自動搜尋並識別組織中的 *主題*。 它會編譯這些主題的資訊，例如簡短描述、編寫主題的人，以及與主題相關的網站、檔案以及頁面。 知識管理員或參與者可以選擇根據需要更新主題資訊。 這些主題可供您的使用者使用，這表示在新式 SharePoint 網站新聞和頁面中出現的每個主題實例，文字都有醒目提示。 使用者可以選取主題，透過主題詳細資料深入了解主題。 您也可以在 SharePoint 搜尋中找到主題。

## <a name="how-topics-are-displayed-to-users"></a>如何向使用者顯示主題

在 SharePoint 新聞和頁面上的內容中提及主題時，您會看到該主題有醒目提示。 您可以從醒目提示開啟主題摘要。 從摘要的標題開啟主題詳細資料。 系統可以自動識別被提及的主題，也可以由頁面作者使用直接參照將該主題新增到頁面中。 

   ![主題醒目提示](../media/knowledge-management/saturn.png) 

當您在 Word 中使用搜尋、PowerPoint、Outlook 或 Excel （透過搜尋方塊，或是在快顯功能表中選取 [**搜尋**]）時，所顯示的結果也可能會顯示主題摘要。

   ![螢幕擷取畫面透過搜尋方塊顯示 Word 搜尋。](../media/knowledge-management/word-search-2.png)

   ![螢幕擷取畫面透過搜尋快顯功能表，顯示 Word 中的搜尋。](../media/knowledge-management/word-search-1.png)

## <a name="knowledge-indexing"></a>知識索引

Viva Topics 使用 Microsoft AI 技術來識別 Microsoft 365 環境中的 *主題*。

主題是對組織來說關鍵或重要的字詞或詞彙。 它對於組織具有特定意義，且具有相關的資源，可協助使用者了解它是什麼，並尋找更多相關資訊。 對您的組織來說，有許多不同類型的重要主題。 一開始，Microsoft AI 技術著重於下列類型：

- 專案
- 事件
- 組織
- 位置
- 產品
- 創意成果
- 研究領域

當主題經過識別，且 AI 判斷它具有足夠的資訊可做為建議的主題時，*主題頁面* 會顯示透過主題索引收集的資訊，例如：

- 替代名稱和縮寫。
- 主題的簡短描述。
- 可能熟悉此主題的人員。
- 與主題相關的檔案、頁面和網站。

您的知識系統管理員可以選擇對租用戶中所有 SharePoint 網站進行主題編目，或只選取特定網站。

如需詳細資訊，請參閱 [主題探索和 curation](./topic-experiences-discovery-curation.md)。

## <a name="roles"></a>角色

當您在 Microsoft 365 環境中使用 Viva Topics 時，您的使用者將具有下列角色：

- 主題檢視者：可以在 SharePoint 新式網站上看到主題醒目提示的使用者，他們至少具有 *讀取* 存取權，以及 Microsoft 搜尋。 他們可以選取主題醒目提示，以查看主題頁面中的主題詳細資料。 主題檢視者可以針對主題的實用性提供意見反應。

- 參與者：擁有編輯現有主題或建立新主題之權限的使用者。 知識系統管理員可透過 Microsoft 365 系統管理中心的 Viva Topics 設定，將參與者權限指派給使用者。 請注意，您也可以選擇將編輯和建立主題的權限提供給所有主題檢視者，讓每個人都能參與他們看到的主題。

- 知識管理員：在主題生命週期中引導主題的使用者。 知識主管使用主題中心的 [ **管理主題** ] 頁面，確認 AI-建議的主題、移除不再相關的主題、編輯現有的主題或建立新的主題，以及是否唯一具有存取權的使用者。 知識系統管理員透過 Microsoft 365 系統管理中心的 Viva Topics 系統管理員設定，將知識管理員權限指派給使用者。 

- 知識管理員：系統管理員會設定 Viva 主題，並透過 Microsoft 365 系統管理中心中的管理控制措施加以管理。 目前，Microsoft 365 全域或 SharePoint 系統管理員可以擔任知識系統管理員。

如需詳細資訊，請參閱 [Viva 主題角色](topic-experiences-roles.md)。

## <a name="topic-management"></a>主題管理

主題管理是在您組織 *主題中心* 的「**管理主題**」頁面中完成。 主題中心是在安裝期間建立的，可充當組織的知識中心。 

雖然所有授權的使用者都可以在主題中心看到與其相連的主題，但只有具有「 *管理主題* 」許可權的使用者才能 (知識管理員) 可以查看和使用 [ **管理主題** ] 頁面。

知識管理員可以：

- 確認或移除在租用戶中發現的主題。
- 根據需要手動建立新主題 (例如，如果提供的資訊不足，無法透過 AI 找到時)。
- 編輯現有的主題頁面。

如需詳細資訊，請參閱 [管理主題中心中的主題](manage-topics.md)。  

## <a name="admin-controls"></a>系統管理控制項

Microsoft 365 系統管理中心中的管理控制可讓您管理 Viva 主題。 它們允許 Microsoft 365 全域或 SharePoint 系統管理員進行以下作業：

- 控制組織中哪些使用者可以在 SharePoint 新式頁面或在 SharePoint 搜尋結果中看到主題。
- 控制要對哪些 SharePoint 網站進行編目以識別主題。
- 排除特定主題，以不被找到。
- 控制哪些使用者可以在主題中心管理主題。
- 控制哪些使用者可以建立及編輯主題。
- 控制哪些使用者可以檢視主題。

如需系統管理控制的詳細資訊，請參閱 [指派使用者](./plan-topic-experiences.md#user-permissions)權力、 [管理主題可見度](./topic-experiences-knowledge-rules.md)及 [管理主題探索](./topic-experiences-discovery.md)。

## <a name="topic-curation--feedback"></a>主題內容篩選與意見反應

隨著環境的變化，AI 將不斷為您提供建議，以改善您的主題。 

具有編輯或建立主題權限的使用者可以直接更新主題頁面，以便進行修正或新增其他資訊。 他們也可以新增 AI 無法識別的新主題。 如果這些手動新增的主題有足夠的資訊，而且 AI 能夠識別這類主題，則 AI 的其他建議可能會增強這些手動新增的主題。

系統可能會詢問您允許查看其日常工作中的主題的使用者，主題對他們來說是否實用。 系統會查看這些回應，並使用它們來改善主題醒目提示，並協助決定主題摘要和主題詳細資料中顯示的內容。

此外，具有適當權限的使用者可以標記與主題相關的項目 (例如 Yammer 交談)，並將它們新增到特定主題。 

如需詳細資訊，請參閱 [主題探索和 curation](./topic-experiences-discovery-curation.md)。

## <a name="see-also"></a>另請參閱

[使用 Microsoft 搜尋來尋找 Viva 主題中的主題](./search.md)