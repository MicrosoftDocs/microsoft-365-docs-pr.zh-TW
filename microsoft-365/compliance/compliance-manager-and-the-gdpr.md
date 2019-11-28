---
title: Microsoft Compliance Manager 和 GDPR
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
description: Microsoft Compliance Manager 是在 Microsoft 服務信任入口網站中的可用工作流程為基礎的風險評估工具。 合規性管理員可讓您追蹤、 指派及驗證與 Microsoft 雲端服務相關的法規合規性活動。
ms.openlocfilehash: 0d2edb2f7362fa8e8bea6ae82c417f61072bccff
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633612"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Microsoft Compliance Manager 和 GDPR

一般資料保護規定 (GDPR) 准許歐盟所可能會影響您合規性策略和授權表單特定動作，以管理使用者和客戶使用合規性管理員中的資訊。

## <a name="user-privacy-settings"></a>使用者隱私權設定

某些法規要求的組織必須能夠刪除使用者歷程記錄資料。 合規性管理員提供可讓系統管理員的**使用者隱私權設定**功能：
  
- [使用者搜尋](#search-for-a-user)
- [匯出帳戶資料歷程記錄的報告](#export-a-report-of-account-data-history)
- [刪除使用者資料歷程記錄](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>搜尋使用者

若要搜尋使用者帳戶：
  
1. 輸入使用者的電子郵件別名 (左邊的資訊 @ 符號)，然後從右邊的網域尾碼清單中選擇的網域名稱。 組織具有多個已註冊的網域，重複檢查，確認它是正確的網域名稱尾碼。

2. 當您已輸入正確的使用者名稱時，選取**搜尋**。

3. 不會傳回的使用者帳戶，頁面會顯示**找不到使用者**。 檢查使用者的電子郵件地址資訊並進行修正為必要。 若要重試，選取**搜尋**。

4. 使用者帳戶傳回，從**搜尋**按鈕變更，以**純**文字。 這表示傳回的使用者帳戶是其他函數的作業系統內容，這些函數套用到此使用者帳戶。

5. 若要清除搜尋結果，並搜尋不同的使用者，請選取 [**清除**]。

## <a name="export-a-report-of-account-data-history"></a>匯出帳戶資料歷程記錄的報告

識別每個使用者帳戶，您可能會產生報告的相依性連結到帳戶。 此資訊可讓您重新指派開啟動作項目或確保先前上傳的辨識項的存取。
  
 若要產生並匯出報告：
  
1. 選取 [產生，並下載合規性管理員控制項動作項目目前指派給傳回的使用者帳戶，並由該使用者上傳的文件清單的報表的 [**匯出**]。 如果沒有指派的動作或上傳的文件，錯誤訊息指出 「 沒有為此使用者的資料 」。

2. 報表的作用中瀏覽器視窗背景中下載-如果您沒有看到下載快顯功能表，您想要檢查您的瀏覽器下載記錄。

3. 開啟文件以檢視報告資料。

> [!IMPORTANT]
> 將報告資料不會保留並顯示動作項目指派歷程記錄的狀態變更的歷程記錄清單。 產生的報告是控制項動作項目指派報告執行的時間 （寫入至報表的日期和時間戳記） 的快照。 例如，動作項目任何後續重新指派不同的快照集報表資料如果導致相同的使用者再次產生報告。
  
## <a name="delete-user-data-history"></a>刪除使用者資料歷程記錄

設定所有控制項動作項目指派為 「 未分派' 所傳回的使用者。 會設定任何由 '使用者移除' 所傳回使用者上傳的文件的**上傳的**值。
  
若要刪除的使用者帳戶動作項目和文件上傳記錄：
  
1. 選取 [**刪除**]。

    確認] 對話方塊隨即顯示: 「*這將會移除所有控制項動作項目指派與所選使用者的文件上傳歷程記錄。此巨集指令是永久性動作。您是否確定要繼續？*」

2. 若要選取 [**確定]** 繼續，否則請選擇**取消**。
