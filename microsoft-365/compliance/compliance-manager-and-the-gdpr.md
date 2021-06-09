---
title: Microsoft 合規性管理員和 GDPR
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合規性管理員是 Microsoft 服務信任入口網站中免費的工作流程型風險評估工具。 合規性管理員可讓您追蹤、指派及驗證與 Microsoft 雲端服務相關的法規遵從性活動。
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595800"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Microsoft 合規性管理員和 GDPR

歐盟所頒佈的一般資料保護法規 (GDPR) 會影響您的規範策略，並強制執行管理合規性管理員中所使用的使用者和客戶資訊的特定動作。

## <a name="user-privacy-settings"></a>使用者隱私權設定

某些法規要求組織必須能夠刪除使用者的記錄資料。 合規性管理員提供 **使用者隱私權設定** 功能，可讓系統管理員：
  
- [使用者搜尋](#search-for-a-user)
- [匯出帳戶資料歷程記錄的報告](#export-a-report-of-account-data-history)
- [刪除使用者資料歷程記錄](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>搜尋使用者

若要搜尋使用者帳戶：
  
1. 輸入使用者的電子郵件別名 (@ 符號左邊的資訊) ，然後從右邊的 [網域尾碼] 清單中選擇功能變數名稱。 如果組織有多個註冊的網域，請加倍檢查功能變數名稱尾碼，以確保正確無誤。

2. 當您輸入正確的使用者名稱時，請選取 [ **搜尋**]。

3. 未傳回的使用者帳戶會顯示 [ **找不到使用者**] 頁面。 檢查使用者的電子郵件地址資訊，並視需要進行修正。 若要重試，請選取 [ **搜尋**]。

4. 對於傳回的使用者帳戶，按鈕的文字會從 **搜尋** 變更為 **Clear**。 這表示傳回的使用者帳戶為其他功能的作業內容，且這些功能適用于此使用者帳戶。

5. 若要清除搜尋結果並搜尋不同的使用者，請選取 [ **清除**]。

## <a name="export-a-report-of-account-data-history"></a>匯出帳戶資料歷程記錄的報告

針對每個識別的使用者帳戶，您可以產生連結至該帳戶的相依性報告。 這項資訊可讓您重新指派開啟的動作專案，或確定先前上傳的證據的存取權。
  
 若要產生並匯出報告：
  
1. 選取 [ **匯出** ] 以產生及下載目前指派給傳回之使用者帳戶的合規性管理員控制項動作專案，以及該使用者上傳的檔案清單。 如果沒有任何指派的動作或上傳的檔，錯誤訊息會指出「沒有此使用者的資料」。

2. 在使用中瀏覽器視窗的背景中下載報告（如果您沒有看到您想要檢查瀏覽器下載歷程記錄的下載快顯功能表）。

3. 開啟文件以檢視報告資料。

> [!IMPORTANT]
> 報告資料不是一份歷史清單，可保留及顯示動作專案指派歷程記錄的狀態變更。 產生的報表是在執行報表時所指派之控制項動作專案的快照 (會寫入報告) 中的日期和時間戳記。 例如，任何後續重新分派動作專案時，如果為相同使用者再次產生報表，便會產生不同的快照報告資料。
  
## <a name="delete-user-data-history"></a>刪除使用者資料歷程記錄

將指派給傳回之使用者的所有控制動作專案設定為「未指派」。 將傳回使用者上傳的任何檔的 **上傳** 值，設定為「使用者已移除」。
  
若要刪除使用者帳戶動作專案和檔上傳歷程記錄：
  
1. 選取 [刪除 **]**。

    隨即會顯示確認對話方塊：「*這會移除所有控制項動作專案指派，以及所選使用者的檔上傳記錄。此動作為永久性。您確定要繼續嗎？*

2. 若要繼續，請選取 **[確定]**，否則請選取 [ **取消**]。
