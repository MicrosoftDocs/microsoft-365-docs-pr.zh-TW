---
title: 適用於 Office Online Server 和 Office Web Apps Server 的 GDPR
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: 深入了解如何在內部部署 Exchange Server 中解決 GDPR 需求。
ms.openlocfilehash: b1cf86beeeb195396e45e0bc262f1d1b81b21057
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "38749692"
---
# <a name="gdpr-for-office-web-apps-server-and-office-online-server"></a>適用於 Office Web Apps Server 和 Office Online Server 的 GDPR

Office Online Server 和 Office Web Apps Server 遙測資料是以 ULS 記錄的形式儲存。您可以使用 [ULS 檢視器](https://www.microsoft.com/download/details.aspx?id=44020)，從您的內部部署租用戶檢視 ULS 記錄。

每個記錄行包含 CorrelationID。相關的記錄行會共用相同的 CorrelationID。每個 CorrelationID 繫結至單一 SessionID，而一個 SessionID 可能與許多 CorrelationID 相關。每個 SessionID 可能與單一 UserID 相關，某些工作階段是匿名的，因此沒有相關聯的 UserID。為了判斷哪些資料與特定使用者相關聯，會從單一 UserID 對應至與該使用者相關聯的 SessionID、從這些 SessionID 對應至相關聯的 CorrelationID，然後從這些 CorrelationID 對應至這些相互關聯中的所有記錄。請參閱下圖以了解不同識別碼之間的關係。

![](media/gdpr-for-office-online-server-image1.jpg)

## <a name="gathering-logs"></a>收集記錄

舉例來說，若要收集與 UserID 1 相關聯的所有記錄，第一個步驟是收集與 UserID 1 相關聯的所有工作階段 (也就是 SessionID 1 和 SessionID2)。下一步是收集與 SessionID 1 相關聯的所有相互關聯 (也就是 CorrelationIDs 1、2 和 3) 以及與 SessionID 2 相關聯的所有相互關聯 (也就是 CorrelationID 4)。最後，收集與清單中的每個相互關聯相關聯的所有記錄。

1.  啟動 UlsViewer

2.  開啟對應至預期時間範圍的 ULS 記錄；ULS 記錄儲存在 %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS

3.  編輯 | 修改篩選

4.  套用以下篩選：

    -   EventID 等於 apr3y 或

    -   EventID 等於 bp2d6

5.  雜湊的 UserIds 會在其中一個事件的 Message 中

6.  針對 apr3y，Message 會包含 UserID 值和 PUID 值

7.  針對 bp2d6，Message 會包含一些資訊。LoggableUserId 值欄位是雜湊的 UserID。

8.  一旦從其中一個標記取得雜湊的 UserId，該資料列的 WacSessionId 值在 ULSViewer 中會包含與該使用者相關聯的 WacSessionId

9.  收集與有問題的使用者相關聯的所有 WacSessionId 值

10. 針對清單中的第一個 WacSessionId，以所有 EventId 等於 "xmnv"、Message 等於 "UserSessionId=\<WacSessionId\>" 進行篩選 (使用您的 WacSessionId 取代篩選的 \<WacSessionId\> 部分)

11. 收集與該 WacSessionId 相符的所有 Correlation 值

12. 為有問題的使用者針對清單中 WacSessionId 的所有值，重複步驟 10-11

13. 針對所有 Correlation 等於您的清單中第一個 Correlation 進行篩選

14. 收集符合該 Correlation 的所有記錄

15. 為有問題的使用者針對清單中 Correlation 的所有值，重複步驟 13-14

## <a name="types-of-data"></a>資料類型

Office 記錄包含各種不同類型的資料。以下是 ULS 記錄可能包含的資料範例：

-   使用產品時發生的問題的錯誤碼

-   按一下按鈕和與應用程式使用方式相關的其他資料片段

-   應用程式及/或應用程式內特定功能的效能資料

-   使用者電腦所在的一般位置資訊 (例如，從 IP 位址衍生的國家/區域、州和城市)，而不是準確的地理位置

-   瀏覽器的相關基本中繼資料，例如，瀏覽器名稱和版本，以及電腦，例如，作業系統類型和版本

-   來自文件主機的錯誤訊息 (例如，OneDrive、SharePoint、Exchange)

-   應用程式內部程序的相關資訊，與使用者採取的任何動作不相關
