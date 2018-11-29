---
title: 轉換 Microsoft 365 商務版雲端解決方案提供者訂閱 
description: 了解如何將 Microsoft 365 商務版雲端解決方案提供者訂閱從預覽轉換到 GA。 
author: jasongroce
ms.author: jasgro
ms.topic: article 
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business 
keywords: Microsoft 365 商務版, Microsoft 365, SMB, 轉換雲端解決方案提供者訂閱
ms.date: 11/01/2017
ms.openlocfilehash: 8109c0b00f06a15c12bbccf89e7f49dc3fa4b34a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866220"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>轉換 Microsoft 365 商務版雲端解決方案提供者訂閱

如果您有 Microsoft 365 商務版預覽的雲端解決方案提供者訂閱，請依照本指南以了解如何將現有預覽訂閱轉換到 Microsoft 365 商務版 GA (正式上市版)。

**如何將預覽訂閱轉換至 GA**

1. 登入<a href="https://partnercenter.microsoft.com" target="_blank">合作夥伴中心</a>。
2. 從儀表板、 選取**客戶**，然後尋找並選取公司名稱。

    將會列出該公司的訂閱。

    ![合作夥伴中心的客戶訂閱](images/pc_customer_subscriptions_1.png)
    
3. 在公司的**訂閱**] 頁面上，選取 [**新增訂閱**。
4. 在 [**新的訂閱**] 頁面上，選取**適用於小型企業**，然後從清單中選取 [ **Microsoft 365 商務**。
5. 新增授權數目，然後選取 [**下一步： 檢閱**檢閱訂閱，然後選取 [**送出**。

    ![檢視 Microsoft 365 商務版的新訂閱](images/pc_customer_reviewnewsubscription.png)

    **授權型訂閱**會顯示**Microsoft 365 商務預覽**和**Microsoft 365 Business**。您將需要暫停預覽訂閱下一步]。

6. 選取 [ **Microsoft 365 Business 預覽**]。
7. 在**Microsoft 365 商務預覽**] 頁面上，選取要暫停的預覽訂閱**已擱置**。

    ![暫停 Microsoft 365 商務版預覽訂閱](images/pc_customer_m365bpreview_suspend.png)

8. 選取 [**提交**] 以確認。

    在 [**訂閱**] 頁面上，確認**Microsoft 365 商務預覽**狀態會顯示**已擱置**。

    ![確認預覽訂閱狀態為已暫停](images/pc_customer_m365bpreview_suspend_confirm.png)

9. 或者，您也可以驗證授權合約。 若要這樣做，請執行下列步驟：
    1. 從公司的**訂閱**] 頁面上選取**的使用者和授權**。
    2. 從 [**使用者和授權**] 頁面上，選取使用者。
    3. 在 [使用者] 頁面上，檢查 [**指派授權**] 區段中並加以確認它會顯示**Microsoft 365 Business**。

        ![確認 Microsoft 365 商務版授權已指派給使用者](images/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>轉換期間和轉換後對客戶和使用者的影響

轉換期間和轉換後對客戶和使用者並無影響。

## <a name="impact-to-customers-who-dont-transition"></a>對於未轉換客戶的影響

下表摘要顯示對於未從 Microsoft 365 商務版預覽訂閱轉換到 Microsoft 365 商務版訂閱的客戶的影響。

|       | T-0 到 T+30     | T+30 到 T+60 | T+60 到 T+120 | 超過 T+120  |
|-------|-----------------|--------------|---------------|---------------|
| **狀態** | 在寬限期 | 已到期      | 停用      | 取消佈建 |
| **服務影響**                                                        |
| **Microsoft 365 商務版系統管理員入口網站** | 對功能不會造成影響 | 對功能不會造成影響 | 可以新增/刪除使用者、購買訂閱。</br> 無法指派/撤銷授權。 | 將刪除客戶訂閱和所有資料。 系統管理員可以管理其他付費訂閱。 |
| **Office 應用程式**                         | 不會影響使用者 | 不會影響使用者 | Office 會進入精簡功能模式。</br> 使用者只能檢視檔案。 | Office 會進入精簡功能模式。</br> 使用者只能檢視檔案。 |
| **雲端服務 (SharePoint Online、Exchange Online、Skype、Teams 等等)** | 不會影響使用者 | 不會影響使用者 | 使用者和系統管理員不能存取雲端中的資料。 | 將刪除客戶訂閱和所有資料。 |
| **EM+S 元件** | 不會影響系統管理員</br> 不會影響使用者 | 不會影響系統管理員</br> 不會影響使用者 | 功能將停止執行。</br> 請參閱[訂閱到期對行動裝置的影響](#mobile-device-impacts-upon-subscription-expiration)和[訂閱到期對 Windows 10 電腦的影響](#windows-10-pc-impacts-upon-subscription-expiration)以取得詳細資訊。 | 功能將停止執行。</br> 請參閱[訂閱到期對行動裝置的影響](#mobile-device-impacts-upon-subscription-expiration)和[訂閱到期對 Windows 10 電腦的影響](#windows-10-pc-impacts-upon-subscription-expiration)以取得詳細資訊。 |
| **Windows 10 商務版** | 不會影響系統管理員</br> 不會影響使用者 | 不會影響系統管理員</br> 不會影響使用者 | 功能將停止執行。</br> 請參閱[訂閱到期對行動裝置的影響](#mobile-device-impacts-upon-subscription-expiration)和[訂閱到期對 Windows 10 電腦的影響](#windows-10-pc-impacts-upon-subscription-expiration)以取得詳細資訊。 | 功能將停止執行。</br> 請參閱[訂閱到期對行動裝置的影響](#mobile-device-impacts-upon-subscription-expiration)和[訂閱到期對 Windows 10 電腦的影響](#windows-10-pc-impacts-upon-subscription-expiration)以取得詳細資訊。 |
| **對 Windows 10 電腦的 Azure AD 登入** | 不會影響系統管理員</br> 不會影響使用者 | 不會影響系統管理員</br> 不會影響使用者 | 不會影響系統管理員</br> 不會影響使用者 | 一旦刪除租用戶，使用者只能使用本機認證登入。 如果沒有任何本機認證，重新製作裝置映像。 |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>訂閱到期對行動裝置的影響

下表摘要顯示對於行動裝置上應用程式管理原則的影響。

|                            | 完整授權體驗                      | 到期後 T+60 天          |
|----------------------------|------------------------------------------------|------------------------------------|
| **刪除非使用中裝置的工作檔案** | 選定天數後移除工作檔案 | 工作檔案會保留在使用者的個人裝置上 |
| **強迫使用者將所有工作檔案儲存到商務用 OneDrive** | 工作檔案只能儲存到商務用 OneDrive | 工作檔案可以儲存到任何位置 |
| **加密工作檔案** | 工作檔案已加密 | 工作檔案不再加密。</br> 移除安全性原則，並且移除應用程式上的 Office 資料。 |
| **需要 PIN 或指紋來存取 Office 應用程式** | 對應用程式的存取受限制 | 無應用程式層級的存取限制 |
| **登入失敗時重設 PIN 碼** | 對應用程式的存取受限制 | 無應用程式層級的存取限制 |
| **Office 應用程式閒置後需要使用者重新登入** | 需要登入 | 不需登入即可存取應用程式 |
| **已進行 JB/Root 破解的的裝置上拒絕存取工作檔案** | 不能存取已進行 JB/Root 破解的的裝置上的工作檔案 | 可以存取已進行 JB/Root 破解的的裝置上的工作檔案 |
| **允許使用者從 Office 應用程式複製內容到個人應用程式** | 屬於 Microsoft 365 商務版訂閱的應用程式限制複製/貼上 | 可對所有應用程式使用複製/貼上 |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>訂閱到期對 Windows 10 電腦的影響

下表摘要顯示對於 Windows 10 裝置設定原則的影響。

|                            | 完整授權體驗                      | 到期後 T+60 天          |
|----------------------------|------------------------------------------------|------------------------------------|
| **使用 Windows Defender 保護電腦預防威脅** | 使用者無法控制開啟/關閉 | 使用者可以開啟/關閉 Windows 10 電腦上的 Windows Defender |
| **在 Microsoft Edge 中協助保護電腦預防網頁威脅** | Microsoft Edge 中的電腦保護 | 使用者可以開啟/關閉 Microsoft Edge 中的電腦保護 |
| **閒置時關閉裝置螢幕** | 系統管理員定義螢幕逾時間隔原則 | 使用者可以設定螢幕逾時 |
| **允許使用者從 Microsoft Store 下載應用程式** | 由系統管理員定義使用者是否可從 Microsoft Store 下載應用程式 | 使用者可隨時從 Microsoft Store 下載應用程式 |
| **允許使用者存取 Cortana** | 由系統管理員定義使用者對 Cortana 的存取原則 | 使用者裝置開啟/關閉 Cortana |
| **允許使用者從 Microsoft 接收提示與廣告** | 系統管理員定義使用者從 Microsoft 接收提示與廣告的原則 | 使用者可以開啟/關閉從 Microsoft 接收提示與廣告 |
| **允許使用者從 Office 應用程式複製內容到個人應用程式** | 系統管理員定義保持 Windows 10 裝置在最新狀態的原則 | 使用者可以決定何時更新 Windows |




