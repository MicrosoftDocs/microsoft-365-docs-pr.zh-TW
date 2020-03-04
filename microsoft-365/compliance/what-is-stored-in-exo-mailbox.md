---
title: Exchange Online 信箱中儲存的內容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 在 Office 365 雲端式應用程式所產生的資料是儲存，或使用者的 Exchange Online 信箱相關聯。
ms.openlocfilehash: 88cd2bf459ed7a50c06194b22f2ae6a999380d51
ms.sourcegitcommit: 9a4084ce2b80bac883412e0ec956b6c0cc18d0f5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2020
ms.locfileid: "42400980"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Exchange Online 信箱中儲存的內容

Exchange Online 中的信箱主要用來儲存郵件、 行事曆項目、 工作及備忘稿例如電子郵件相關項目。 但是，變更為更多的基於雲端的 Office 365 應用程式也會儲存其資料在使用者的信箱。 將資料儲存在信箱中的其中一個優勢是，您可以使用內容搜尋、 核心 eDiscovery、 進階的 eDiscovery 中搜尋工具資料調查尋找、 檢視和匯出資料從這些雲端式應用程式。 從這些應用程式的一些資料儲存在隱藏的資料夾位於信箱中的非人際郵件 (非 IPM) 樹狀子目錄。 其他雲端式應用程式的資料可能不會儲存_在_信箱，但其_相關聯_的信箱，並 （如果該資料符合搜尋查詢），在搜尋中傳回。 不論是否儲存在雲端式資料或使用者信箱相關聯，資料通常中不可見的電子郵件用戶端使用者開啟其信箱時。

下表列出 [儲存] 或 [建立資料與基於雲端的信箱關聯的 Office 365 應用程式。 下表也會說明每個應用程式產生的內容類型。

|Office 365 應用程式|說明|
|:---------|:---------|
|Forms|（儲存為 PDF 檔案） 的表單和表單 （儲存 CSV 檔案中） 的回覆電子郵件附加且儲存在隱藏的資料夾中建立表單之使用者的信箱。 當您匯出內容從 PST 檔案中的表單時，此資料位於**ApplicationDataRoot**資料夾的子資料夾中名為下列項目全域唯一識別 (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**。|
|Office 365 群組|電子郵件、 行事曆項目、 連絡人 （人員）、 備忘稿和工作會儲存在與 Office 365 群組相關聯的信箱。|
|Outlook/Exchange Online|電子郵件、 行事曆項目、 連絡人 （人員）、 備忘稿和工作會儲存在使用者的信箱。|
|人員|人員應用程式 （也就是可在 Outlook 中存取該組相同的連絡人） 的連絡人會儲存在使用者的信箱。|
|類別排程|建立類別排程中的計劃會儲存在對應的 Office 365 群組時建立新的計劃佈建的信箱。 群組信箱的別名是計劃的名稱。|
|商務用 Skype|在商務用 Skype 對話會儲存在使用者的信箱中的 [交談歷程記錄] 資料夾。 如果 Skype 會議的參與者的信箱處於訴訟暫止狀態或指派到保留原則後，附加至會議的檔案會保留在參與者信箱。|
|Sway|Sways 會儲存為 HTML 檔案附加到電子郵件，並儲存在隱藏的資料夾中建立 sway 之使用者的信箱。 當您匯出內容從 PST 檔案中的 Sway 時，此資料位於名為下列 guid 的子資料夾中的 [ **ApplicationDataRoot** ] 資料夾中） **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**。|
|工作|在 [工作] app 中的工作 （也就是可在 Outlook 中存取的相同的工作） 會儲存在使用者的信箱。|
|Teams|與小組信箱的小組通道一部分的交談相關聯。 交談屬於 [聊天室] 清單中 （也稱為*1 x N 聊天室*） 的 microsoft Teams 相關聯的參與聊天室的使用者信箱。 此外，會議與通話中的小組通道的摘要資訊與相關聯的撥入會議或通話的使用者信箱。 因此搜尋的 Teams 內容時，您應通道交談中搜尋內容的團隊信箱，然後在 1 x N 聊天中搜尋使用者信箱的內容。| 
|To-Do|工作 (稱為*to-dos*，它們儲存於待辦事項清單) 中的待辦事項應用程式會儲存在使用者的信箱。|
||||

> [!NOTE]
> 在這個階段中，如果保留在信箱上 （藉由使用 eDiscovery 和進階電子文件探索案例中的保留），從表單和 Sway 的內容將不會保留此保留。 
