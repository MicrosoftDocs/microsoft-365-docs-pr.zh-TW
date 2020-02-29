---
title: Office 365 的 ATP 安全連結的 Teams，safelinks、 安全連結，封鎖惡意連結，office 365 atp，Teams 安全連結，阻止使用者按下不正確的連結，惡意連結
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
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
description: Teams 現在會在您按一下 [時間可以存取安全連結。 您是否正在使用聊天 1 對 1 聊天室、 群組、 之間或通道和索引標籤，如果您有 Office 365 ATP 的訂閱，您必須啟用並使用此安全性功能的能力。
ms.openlocfilehash: ba7ef2ae63b788ec94fbbb15c3c00312177a59d5
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341584"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a>Office 365 小組中的安全連結

> [!IMPORTANT]
> 這項功能是在**公開預覽**中的客戶在 Microsoft Teams 技術採用程式 （點選） 起 2020 年 2 月 28。 此附註會更廣泛地使用 teams 的安全連結時移除 > 一文。

Microsoft Teams，Office 365 雲端式應用程式的管理工作，已使用安全附件 （適用於 Office 365)，但它現在能夠存取安全連結在您按一下 [時間。 您是否正在使用聊天 1 對 1 聊天室、 群組、 之間或通道和索引標籤，如果您有 Office 365 ATP 的訂閱，您必須啟用並使用此安全措施的能力。

以下是其運作方式： 

1. 當您啟動 Teams 應用程式時，Office 365 會檢查以確保使用者所屬的組織具有 Office 365 ATP，且使用者是作用中的安全連結原則以啟用 Microsoft teams 其保護的一部分。

2. 如果上述條件為真，然後 Url 將會驗證的同時按一下 [聊天、 群組聊天、 通道，並在索引標籤中，該使用者的。
 
## <a name="what-will-users-experience"></a>項目將使用者體驗？ 

受保護的所有使用者都必須具有危險物質暴露 Url 此經驗： 

- 如果已從 microsoft Teams 交談，group chat]，按一下連結或通道，從] 頁面上將預設瀏覽器中呈現。 如果按下連結已釘選] 索引標籤中，從 [] 頁面上會出現在小組 GUI 內該索引標籤，並將會停用瀏覽器中開啟的選項，基於安全性考量。

- 此使用者粗俗繼續進行至 URL 的網站。

如果傳送連結的使用者不由 Office 365 ATP 受到保護，他或她可以自由地按一下他/她的機器上的 URL，並解決問題的網站。 這可讓串列重要要注意的 Office 365 系統管理員的人員其受保護的使用者都應該與。

![報告惡意連結和封鎖] 頁面上的傳輸的小組] 頁面上的安全連結。](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

按一下 [teams 此頁面上的 [*返回*] 按鈕將其關閉 （或可能會導致空白頁面使用者可以關閉）。 不過，再按一下連結會導致上場的站台的信譽，讓此頁面會重新出現。

> [!NOTE]
>某些 Office 365 系統管理員將會啟用 [封鎖] 頁面上的，**還是繼續**訊息。 不過，如果安全連結會測量站台的信譽，並更快找到它缺少，沒有進一步點選應該進行。 不建議使用者略過安全措施。 請權衡這您考量啟用仍繼續之前。 

