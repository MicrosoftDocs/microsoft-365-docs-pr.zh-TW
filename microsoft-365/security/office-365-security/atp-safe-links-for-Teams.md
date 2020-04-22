---
title: 用於小組、safelinks、安全連結、封鎖惡意連結、office 365 atp、小組安全連結的 ATP 安全連結，讓使用者無法按一下 [不良連結]，惡意連結
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 當您按一下時，小組現在可存取安全的連結。 不論您是使用聊天1開聊天、群組還是頻道，以及標籤式，如果您有 Office 365 ATP 的訂閱，您就能夠啟用和使用此安全功能。
ms.openlocfilehash: 88fe9756188eb16a2347d3c0cd4a98b4003ff457
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635995"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a>Teams 中的安全連結

> [!IMPORTANT]
> 這項功能是針對 Microsoft 小組技術採用計畫（點擊）中的客戶**公開預覽**，在2020年2月28日。 當小組的安全連結更廣泛可用時，就會從文章中移除此附注。

Microsoft 團隊是用來管理工作的 Microsoft 雲端式應用程式，已使用安全附件（適用于 Office 365），但在您按下時，它現在可以存取安全連結。 不論您是使用聊天1開聊天、群組還是頻道，以及標籤式，如果您有 Office 365 ATP 的訂閱，您就能啟用和使用此安全措施。

以下為運作方式： 

1. 當您啟動小組應用程式時，Microsoft 365 將會檢查使用者是否屬於具有 Office 365 ATP 的組織，而且使用者屬於使用中安全連結原則的一部分，其保護為 Microsoft 團隊啟用。

2. 如果上述為 true，則會在聊天、群組聊天、頻道及該使用者的索引標籤中按一下時，驗證 URLs。
 
## <a name="what-will-users-experience"></a>使用者將體驗什麼？ 

所有受保護的使用者都會有這種具有危險性的經驗 URLs： 

- 如果從小組交談、群組聊天或通道按一下連結，則頁面會在預設瀏覽器中呈現。 如果從固定的索引標籤中按一下連結，該頁面會出現在該索引標籤中的小組 GUI 中，而且會停用在瀏覽器中開啟的選項，以進行安全性用途。

- 將會封鎖此使用者以繼續前往 URL 的網站。

如果傳送連結的使用者未受到 Office 365 ATP 的保護，他或她可以隨意按一下其機器上的 URL，並解決問題網站。 這使得系統管理員知道誰是受保護的使用者，且應該是非常重要的。

![「小組的安全連結」頁面報告惡意連結，並封鎖頁面的傳輸。](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

按一下小組中此頁面上的 [*上一步*] 按鈕，即可將其關閉（或可能導致空白頁面使用者可以關閉）。 不過，再次按一下連結會導致網站的信譽 reassessment，讓此頁面重新顯示。

> [!NOTE]
>有些 Microsoft 365 系統管理員會在封鎖頁面上啟用 [**繼續**進行] 訊息。 不過，如果安全連結測量網站的信譽，但找不到，則不應再進行按一下。 不建議使用者略過安全性度量。 請先將此因素權衡為您的考慮，再啟用繼續。 

