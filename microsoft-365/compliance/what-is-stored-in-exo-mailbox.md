---
title: 儲存在 Exchange Online 信箱中的內容
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
description: 在 Microsoft 365 中，雲端架構應用程式所產生的內容會儲存或關聯至使用者的 Exchange Online 信箱。 您可以使用 Microsoft eDiscovery 工具來搜尋此內容。
ms.openlocfilehash: 975f4ac8be8c2cdeed8dea1d73699607662a1ce9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288140"
---
# <a name="content-stored-in-exchange-online-mailboxes-for-ediscovery"></a>儲存在 eDiscovery Exchange Online 信箱中的內容

Exchange Online 中的信箱主要是用來儲存電子郵件相關專案，例如郵件、行事曆專案、任務和附注。 不過，隨著雲端架構應用程式的變化，也會將其資料儲存在使用者的信箱中。 在信箱中儲存資料的其中一個優點是，您可以使用內容搜尋、核心 eDiscovery 和 Advanced eDiscovery 中的搜尋工具，來尋找、查看及匯出這些雲端架構應用程式中的資料。 某些應用程式中的資料會儲存在信箱中非 IPM) 子樹系中非電子郵件郵件的隱藏資料夾中 (。 其他雲端式應用程式中的資料可能不會儲存 _在信箱中_ ，但會 _與_ 信箱產生關聯，而且會在搜尋 (中傳回，如果該資料符合搜尋查詢) 。 不論是否要將雲端型資料儲存在使用者信箱中或與使用者信箱產生關聯，當使用者開啟其信箱時，通常不會在電子郵件客戶程式中看到資料。

下表列出使用雲端架構信箱儲存或關聯資料的應用程式。 該表也會說明每個應用程式產生的內容類型。

<br>

****

|Microsoft 365 應用程式|說明|
|---|---|
|形式<sup>*</sup>|表單和表單的回應儲存在附加至電子郵件的檔案中，並儲存在建立表單之使用者信箱的隱藏資料夾中。 在2020年4月之前建立的表單會儲存為 PDF 檔案。 在2020之後建立的表單會儲存為 JSON 檔案。 對表單的回應儲存在 CSV 檔案中。 當您從 PST 檔案中的表單匯出內容時，此資料位於以下列全域唯一識別的 (GUID) ： **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87** 之子資料夾中的 **ApplicationDataRoot** 資料夾中。|
|Microsoft 365 群組|電子郵件、行事曆專案、連絡人 (人員) 、便箋和任務都儲存在與 Microsoft 365 群組相關聯的信箱中。|
|Outlook/Exchange Online|電子郵件、行事曆專案、連絡人 (人員) 、便箋和任務都儲存在使用者的信箱中。|
|People|[人脈] 應用程式中的連絡人會儲存在使用者的信箱中， (與 Outlook) 中可存取的連絡人相同。|
|類別排程|在類別排程中建立的計畫會儲存在建立新的計畫時所提供之對應 Microsoft 365 群組的信箱中。 群組信箱的別名是方案的名稱。|
|商務用 Skype|商務用 Skype 中的交談會儲存在使用者信箱的 [交談記錄] 資料夾中。 如果 Skype 會議參與者的信箱設為訴訟暫止或指派給保留原則，則附加至會議的檔案會保留在參與者信箱中。|
|搖擺<sup>*</sup>|Sway 會儲存為附加至電子郵件的 HTML 檔案，並儲存在建立 sway 之使用者信箱的隱藏資料夾中。 當您從您的 PST 檔案的 Sway 匯出內容時，此資料位於名為及下列 GUID: **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba** 子資料夾中的 **ApplicationDataRoot** 資料夾中。|
|工作|工作 app (中的工作會儲存在使用者的信箱中，與 Outlook) 中可存取的任務相同。|
|Teams|屬於 Teams 通道一部分的對話會與 Teams 信箱相關聯。 屬於 Teams (中之聊天清單一部分的交談也稱為 *1 x N 聊天*) 與參與聊天之使用者的信箱相關聯。 此外，會議和 Teams 通道中通話的摘要資訊，與撥打會議或通話的使用者信箱相關聯。 因此，當您搜尋 Teams 內容時，您會搜尋「Teams 信箱」以取得通道交談中的內容，並搜尋使用者信箱中的內容，以取得 1 x N 研討的內容。|
|To-Do|工作 (稱為 *dos*，會儲存在使用者信箱中的 [To-Do] 應用程式) 中的 [待辦事項] 清單中。|
|Yammer|Yammer 群組內的交談和批註會與 Microsoft 365 群組信箱相關聯，以及作者的使用者信箱，以及已提及的使用者或 Cc'ed 使用者) 的任何命名的收件者 ( @。 在 Yammer 團體外傳送的私人郵件會儲存在參與私人郵件之使用者的信箱中。|
|

> [!NOTE]
> <sup>*</sup>在此情況下，如果使用核心 eDiscovery 或 Advanced eDiscovery) 案例中的保留來設定信箱 (，保留中的內容將不會保留。
