---
title: Microsoft Viva 主題概述
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
description: Viva 主題的概述。
ms.openlocfilehash: f45e0f7c6090d4584526aa9c2abb5ec98213d635
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107635"
---
# <a name="microsoft-viva-topics-overview"></a>Microsoft Viva 主題概述 

Viva 主題使用 Microsoft AI 技術、Microsoft 365、Microsoft Graph、搜尋及其他元件和服務，以在日常使用的 Microsoft 365 應用程式中，向您的使用者傳授知識，從 SharePoint 新式頁面和 Microsoft 搜尋開始。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Viva 主題可協助解決許多公司的重要業務問題-當使用者需要時，提供資訊給使用者。 例如，新員工必須快速瞭解大量的新資訊，並在閱讀公司資訊時遇到不相關的字詞。 若要深入瞭解，使用者可能需要從何處開始，並花寶貴的時間搜尋詳細資料，例如，該術語的相關資訊，組織中的誰是主題專家，也可能是與字詞相關的網站和檔。

Viva 主題使用 AI 自動搜尋及識別您組織中的 **主題** 。 它會編譯其相關資訊，例如簡短描述、使用主題的人員，以及與其相關的網站、檔案及頁面。 知識管理員或參與者可以視需要選擇更新主題資訊。 您的使用者可以使用這些主題，這表示在當今的 SharePoint 網站中的 [新聞] 和 [頁面] 中，該文字會反白顯示。 使用者可選擇透過主題詳細資料深入瞭解主題。 您也可以在 SharePoint 搜尋中找到主題。


## <a name="how-topics-are-displayed-to-users"></a>主題如何顯示給使用者

在 SharePoint 新聞及頁面的內容中提及主題時，您會看到該主題為反白顯示狀態。 您可以從醒目提示中開啟主題摘要。 從摘要的標題開啟主題詳細資料。 您可以自動識別上述主題，也可以使用頁面作者直接參考主題，將其新增至頁面。 

   ![主題要聞](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>知識索引

Viva 主題使用 Microsoft AI 技術來識別 Microsoft 365 環境中的 **主題** 。

主題是一種組織很重要或很重要的片語或字詞。 組織中有特定的意義，也有相關的資源可協助人員瞭解其內容及找到相關資訊。 許多不同類型的主題對您的組織而言很重要。 Microsoft AI 技術最初是以下列類型為重點：
- Project
- 事件
- 組織
- 位置
- 產品
- 創造性工作
- 研究的欄位


在識別主題，並透過 AI 判斷該主題有足夠的資訊可取得建議主題時， **主題頁面** 會顯示透過主題索引所收集到的資訊，例如：

- 替代名稱和縮寫。
- 主題的簡短描述。
- 該主題可能具有專業知識的人員。
- 與主題相關的檔案、頁面和網站。

您的知識管理員可以選擇編目您租使用者中的所有 SharePoint 網站，或只選取某些專案。

請參閱 [主題探索和 curation](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)

## <a name="roles"></a>角色

當您在 Microsoft 365 環境中使用 Viva 主題時，您的使用者將具備下列角色：

- 主題檢視器：可以查看主題的使用者在其至少具有 *讀取* 許可權的現代網站上，以及在 Microsoft Search 中的 SharePoint。 他們可以選取主題要聞，以查看主題頁面中的主題詳細資料。 主題檢視器可提供主題的有用意見反應。

- 參與者：具有編輯現有主題或建立新主題之許可權的使用者。 知識系統管理員可以透過 Microsoft 365 系統管理中心中的 Viva 主題設定，將參與者許可權指派給使用者。 請注意，您也可以選擇讓所有主題查看者都能編輯及建立主題，這樣所有人都可以參與他們所看到的主題。

- 知識管理員：透過主題生命週期指引主題的使用者。 知識主管使用主題中心的 [ **管理主題** ] 頁面，確認 AI-建議的主題、移除不再相關的主題、編輯現有的主題或建立新的主題，以及是否唯一具有存取權的使用者。 知識系統管理員可以透過 Microsoft 365 系統管理中心的「Viva 主題管理員」設定，將知識管理員許可權指派給使用者。 

- 知識系統管理員：知識系統管理員會設定 Viva 主題，並透過 Microsoft 365 系統管理中心中的管理控制措施加以管理。 目前，Microsoft 365 全域或 SharePoint 管理員可以做為知識系統管理員。

如需詳細資訊，請參閱 [Viva 主題角色](topic-experiences-roles.md) 。

## <a name="topic-management"></a>主題管理

主題管理是在您組織 **主題中心** 的「**管理主題**」頁面中完成。 主題中心是在安裝期間建立的，可充當組織的知識中心。 

雖然所有授權的使用者都可以在主題中心看到與其相連的主題，但只有具有「 *管理主題* 」許可權的使用者才能 (知識管理員) 可以查看和使用 [管理主題] 頁面。

知識管理員可以：

- 確認或移除已在您的租使用者中探索的主題。
- 在需要時手動建立新的主題 (例如，如果沒有提供足夠的資訊供透過 AI) 探索。
- 編輯現有的主題頁面。</br>

如需詳細資訊，請參閱 [管理主題中央中的主題](manage-topics.md) 。  


## <a name="admin-controls"></a>系統管理控制

Microsoft 365 系統管理中心中的管理控制可讓您管理您的知識網路。 它們允許 Microsoft 365 全域或 SharePoint 管理員：

- 控制您組織中的哪些使用者可以查看 SharePoint 新式頁面或 SharePoint 搜尋結果中的主題。
- 控制將會編目哪些 SharePoint 網站，以識別主題。
- 排除特定主題的找到。
- 控制哪些使用者可以管理主題中心的主題。
- 控制哪些使用者可以建立及編輯主題。
- 控制可查看主題的使用者。

如需系統管理控制的詳細資訊，請參閱 [指派使用者](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions)權力、 [管理主題可見度](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)及 [管理主題探索](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery) 。

## <a name="topic-curation--feedback"></a>主題 curation & 意見反應

AI 會持續運作，提供您在環境中發生變更時改進主題的建議。 

具有 [編輯] 或 [建立主題] 許可權的使用者，如果想要進行更正或新增其他資訊，可以直接對主題頁面進行更新。 他們也可以新增 AI 無法識別的新主題。 如果這些手動新增的主題有足夠的資訊，而且 AI 能夠識別這類主題，則 AI 的其他建議可能會增強這些手動新增的主題。 

您允許存取權在日常工作中查看主題的使用者可能會詢問該主題是否有用。 系統會查看這些回應，並使用它們來改進主題的醒目提示，並協助決定主題摘要和主題詳細資料中顯示的內容。

此外，具有適當許可權的使用者可以將相關的 Yammer 交談等專案標記為相關專案，並將其新增至特定主題。 

請參閱 [主題探索和 curation](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)


## <a name="see-also"></a>請參閱

