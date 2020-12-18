---
title: '主題經驗 (預覽的概述) '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 主題經驗的概述。
ms.openlocfilehash: 9321f349056c1c4df36b6bd725214f3c6758cf6a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698847"
---
# <a name="topic-experiences-overview-preview"></a>主題經驗 (預覽的概述) 

> [!Note] 
> 本文內容適用于 Project Cortex 私人預覽。 [如需詳細資訊，請參閱 Project Cortex](https://aka.ms/projectcortex)。

主題經驗使用 Microsoft AI 技術、Microsoft 365、Delve、Microsoft Graph、搜尋及其他元件和服務，在您的 Microsoft 365 環境中建立知識網路。 

   ![知識管理流程](../media/knowledge-management/knowledge-management-flowchart.png) </br> 

其目標是將資訊轉換為知識，並在日常使用的應用程式中，將資訊傳送給您的使用者，例如 SharePoint 新式頁面和 Microsoft 搜尋。

主題有助協助解決許多公司的重要業務問題-當使用者需要時，提供資訊給使用者。 例如，新員工必須快速瞭解大量的新資訊，並在閱讀公司資訊時遇到不相關的字詞。 若要深入瞭解，使用者可能需要從何處開始，並花寶貴的時間搜尋詳細資料，例如，該術語的相關資訊，組織中的誰是主題專家，也可能是與字詞相關的網站和檔。

主題經驗使用 AI 自動搜尋及識別您組織中的 **主題** 。 它會編譯其相關資訊，例如相關主題的簡短描述、主題專家、網站、檔案及與其相關的頁面。 知識管理員或參與者可以視需要選擇更新主題資訊。 您的使用者可以使用這些主題，這表示在當今的 SharePoint 網站中的 [新聞] 和 [頁面] 中，該文字會反白顯示。 使用者可選擇透過主題詳細資料深入瞭解主題。 您也可以在 SharePoint 搜尋中找到主題。


## <a name="how-topics-are-displayed-to-users"></a>主題如何顯示給使用者

在 SharePoint 新聞及頁面的內容中提及主題時，您會看到該主題為反白顯示狀態。 您可以從醒目提示中開啟主題摘要。 從摘要的標題開啟主題詳細資料。 您可以自動識別上述主題，也可以使用頁面作者直接參考主題，將其新增至頁面。 

   ![主題要聞](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>知識索引

主題經驗使用 Microsoft AI 技術來識別 Microsoft 365 環境中的 **主題** 。

主題是一種組織很重要或很重要的片語或字詞。 組織中有特定的意義，也有相關的資源可協助人員瞭解其內容及找到相關資訊。

在識別主題，並透過 AI 判斷該主題具有足夠的資訊做為建議主題時，會為其建立一個 **主題頁面** ，其中包含透過主題編制索引所收集的資訊，例如：

- 替代名稱和/或縮寫。
- 主題的簡短描述。
- 熟悉主題的使用者。
- 與主題相關的檔案、頁面和網站。

您的知識管理員可以選擇編目您租使用者中的所有 SharePoint 網站，或只選取某些專案。

## <a name="roles"></a>角色

當您在 Microsoft 365 環境中使用主題經驗時，您的使用者將具備下列角色：

- 主題檢視器：能夠在至少具有 *讀取* 許可權的現代網站 SharePoint 上，以及 Microsoft Search 中，可看到主題要聞的使用者。 他們將能夠選取主題要聞，以查看主題頁面中的主題詳細資料。 主題檢視器將能夠提供主題所用的有用意見意見反應。

- 參與者：具有編輯現有主題或建立新主題之許可權的使用者。 知識系統管理員可以透過 Microsoft 365 系統管理中心中的「經驗」主題中的設定，將參與者許可權指派給使用者。 請注意，您也可以選擇讓所有主題查看者都能編輯及建立主題，這樣他們也可以對他們所看到的主題做為貢獻。

- 知識管理員：透過主題生命週期指引主題的使用者。 知識主管使用主題中心的 [ **管理主題** ] 頁面，確認或移除 AI 建議的主題，以及編輯現有的主題或建立新的主題，以及是否唯一具有存取權的使用者。 知識管理員可以透過 Microsoft 365 系統管理中心的「管理」主題經驗，將「知識管理員」許可權指派給使用者。 

- 知識系統管理員：知識管理員設定主題經驗，並透過 Microsoft 365 系統管理中心中的管理控制措施加以管理。 目前，Microsoft 365 全域或 SharePoint 管理員可以做為知識系統管理員。

如需詳細資訊，請參閱 [主題體驗角色](topic-experiences-roles.md) 。

## <a name="topic-management"></a>主題管理

主題管理是在您組織 **主題中心** 的「**管理主題**」頁面中完成。 主題中心是在安裝期間建立的，可充當組織的知識中心。 

雖然所有授權的使用者都可以在主題中心看到與其相連的主題，但只有具有「 *管理主題* 」許可權 (知識管理員) 的使用者可以查看和使用 [管理主題] 頁面。

知識管理員將能夠：

- 確認或拒絕您租使用者中探索的主題。
- 在需要時手動建立新的主題 (例如，如果沒有提供足夠的資訊供透過 AI) 探索。
- 編輯現有的主題頁面。</br>

如需詳細資訊，請參閱 [管理主題中央中的主題](manage-topics.md) 。  


## <a name="admin-controls"></a>系統管理控制

Microsoft 365 系統管理中心中的管理控制可讓您管理您的知識網路。 它們允許 Microsoft 365 全域或 SharePoint 管理員：

- 控制您組織中的哪些使用者可以查看 SharePoint 新式頁面或 SharePoint 搜尋結果中的主題。
- 控制將編目哪個 SharePoint 網站來搜尋主題。
- 設定主題探索，以排除所找到的特定主題。
- 控制哪些使用者可以管理主題中心的主題。
- 控制哪些使用者可以在主題中心建立及編輯主題。
- 控制哪些使用者可以查看主題。

如需系統管理控制的詳細資訊，請參閱 [指派使用者](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions)權力、 [管理主題可見度](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)及 [管理主題探索](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery) 。

## <a name="topic-curation--feedback"></a>主題 curation & 意見反應

AI 會持續運作，提供您在環境中發生變更時改進主題的建議。 

您允許存取權在日常工作中查看主題的使用者可能會詢問該主題是否有用。 AI 會查看這些回應，並使用它們來協助決定主題摘要和主題詳細資料中顯示的內容。

具有 [編輯] 或 [建立主題] 許可權的使用者，如果想要進行更正或新增其他資訊，可以直接對主題頁面進行更新。 

此外，具有適當許可權的使用者可以將相關的 Yammer 交談等專案標記為相關專案，並將其新增至特定主題。 


## <a name="see-also"></a>請參閱
