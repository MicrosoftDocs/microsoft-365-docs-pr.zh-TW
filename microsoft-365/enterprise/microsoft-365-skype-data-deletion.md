---
title: Office 365 商務用 Skype 資料刪除
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，您可以在商務用 Skype 中尋找資料刪除的說明，包含哪些類型的內容不會保留。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a47df4dd0dfdf5551668f8cafc9baa023bd6db1
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332709"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a>Office 365 中的商務用 Skype 資料刪除

商務用 Skype 可在會議中提供對等立即訊息、多方立即訊息和內容上傳活動的封存。 封存功能需要 Exchange，且由使用者的 Exchange 信箱 In-Place Hold 屬性所控制，這會同時歸檔電子郵件和商務用 Skype 內容。

商務用 Skype 中的所有封存都會視為「使用者層級封存」，因為您可以為一或多個特定使用者或使用者群組建立、設定及套用使用者層級的封存原則，以針對一或多個特定使用者或使用者群組來啟用或停用該使用者。 在商務用 Skype 系統管理中心內，無法直接控制封存設定。

在商務用 Skype 中未封存下列類型的內容：

- 對等檔案傳輸
- 對等立即訊息和會議的音訊/視訊
- 對等立即訊息與會議的應用程式共用
- 會議標注 

## <a name="meeting-content-retention"></a>會議內容保留

使用商務用 Skype 的客戶可以將內容上傳至商務用 skype 會議，例如 PowerPoint 簡報、OneNote 檔案及其他檔案。 上傳至會議的內容有如下的保留期：

- **一次性會議** 內容會保留15天，從最後一個人離開會議的時間開始。
- **週期性會議** 內容會在最後一個人離開會議的最後一個會議之後保留15天。 如果有人在15天內加入相同會議會話，保留計時器便會重設。 例如，假設商務用 Skype 會議排定一年每週進行一次，並在第一個實例中將檔案上傳至會議。 如果每週至少有一個人員加入會議會話，該檔案會保留在全年的商務用 Skype Online 伺服器中，在最後一個人離開最後一筆會議之後15天加上15天。
- **立即開會會議** 內容會在會議結束時間後的8小時內保留。

> [!NOTE]
> 如果使用者未獲授權或已停用 (例如，如果 **msRTCSIP msrtcsip-userenabled** 設定為 *False*) ，然後重新獲得授權或重新啟用，則不會保留會議內容。

## <a name="meeting-expiration"></a>會議到期

使用者可以在特定會議結束之後存取該會議，但需注意下列到期時段：

- **單一會議** 會議會在排程的會議結束時間後的14天到期。
- **具有結束日期的週期性會議** -會議會在上次會議約會的排程結束時間之後的14天到期。
- [**立即開會會議**] 會議會在8小時後到期。

## <a name="whiteboard-collaboration"></a>白板協同共同作業

在白板上所做的註釋，所有參與者都看得到。 儲存白板時，白板和所有批註將會儲存在商務用 Skype 伺服器上，而且會根據系統管理員設定的會議內容到期原則，保留在伺服器上。

## <a name="audio-test-service"></a>音訊測試服務

在音訊測試服務通話期間，大約有5秒的時間會記錄) 的語音樣本 (。 語音範例是用來檢查及/或驗證商務用 Skype 通話的音質，取決於錄製品質。 當音訊測試服務通話結束時，語音範例就會被刪除。

## <a name="persistent-group-chat"></a>持續群組聊天

持續群組聊天會儲存群組聊天交談的內容。 若啟用，系統管理員可以控制保留期間、儲存此資訊的伺服器、如果群組聊天記錄已封存以符合合規性或其他目的，以及管理/修改聊天室上的任何屬性。 具有不同角色的使用者具有不同的保存資料存取權，如下所示：

- 管理員可以刪除舊的內容 (例如，在特定日期之前發佈的內容) 從任何聊天室，以避免資料庫的大小大幅增加。 或者，他們可以移除或取代視為對特定聊天室不適當的郵件 (或視為不適當的) 。
- 使用者（包括郵件作者）無法刪除任何聊天室中的內容。
- 聊天室管理員可以停用會議室，但無法刪除會議室。 只有管理員可以在建立聊天室之後刪除聊天室。