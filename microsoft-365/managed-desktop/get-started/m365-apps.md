---
title: Microsoft 365 Apps 企業版
description: 如何部署 Microsoft 365 應用程式、其更新方式及設定的管理方式
keywords: 變更歷程記錄
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 98995084fb7de9ecb434b70b5d38793a20675f19
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840338"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps 企業版

## <a name="initial-deployment"></a>初始部署

Microsoft 受管理的桌面機，可確保在所有 [程式裝置](../service-description/device-list.md)上安裝 Microsoft 365 應用程式 for enterprise (64 位) 。 傳送裝置時，裝置上應會出現下列所有應用程式：

- Word
- Excel
- PowerPoint
- Outlook
- 發行者
- Access
- 商務用 Skype
- OneNote

這種方法會將網路影響降至最低，並確保使用者在收到其裝置時可以立即生產力。 然後，我們會將更多原則部署到受管理的裝置，以設定要使用的應用程式。

> [!NOTE]
> Microsoft 團隊會獨立于適用于企業的 Microsoft 365 應用程式進行部署，而且不會包含在基底影像中。 

### <a name="available-deployment-to-users"></a>適用于使用者的部署

如果使用者在其裝置上沒有 Microsoft 365 應用程式出於任何原因，您可以使用套件，將裝置傳回其預期的狀態。 將使用者新增至新式的辦公 **Office365_Install** 群組，在公司入口網站中，這些應用程式就能使用。

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>適用于企業的 Microsoft 365 應用程式 (32-位) 

Microsoft 受管理的桌面不支援部署 M365 應用程式的32位版本的 enterprise。

## <a name="updates-to-microsoft-365-apps"></a>Microsoft 365 應用程式的更新

Microsoft 365 應用程式已設定為在 [每月的 Enterprise 通道](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)上更新。 這項練習每月都會為您的使用者提供新的 Office 功能，但每月只會收到一次更新，且可預測的發行排程。 更新會在每月的第二個星期二發佈;這些更新可包含功能、安全性和品質更新。 這些更新會自動進行，而且會直接從 Office CDN （適用于該特定通道）上抽出。

Microsoft 受管理的桌面 staggers 每個版本，以找出您環境中的任何潛在問題。 從 Microsoft 365 應用程式產品群組發行的28天后，我們會完成首展。 Microsoft 受管理的桌面排程將更新版本更新成不同的群組，允許驗證和測試的時間如下： 

- 測試：零天
- 第一：零天
- Fast：7天
- 寬：21天

Microsoft 受管理的桌面會設定裝置的7天 [更新期限](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 。 更新可供使用後，必須在七天內安裝。 使用者會 [收到](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 下列數個位置要求的更新：應用程式，在最後期限之前的系統託盤12小時內，而且會在最後期限之前收到15分鐘的警告。 所有 Microsoft 365 應用程式必須關閉，更新才能完成。

### <a name="pausing-or-rolling-back-an-update"></a>暫停或回復更新

若由於任何原因需要暫停或回復 Microsoft 365 應用程式更新，請透過 Microsoft 受管理的桌面入口網站來歸檔系統 [管理員支援要求](../working-with-managed-desktop/admin-support.md) 。

在發行期間，Microsoft 管理的桌面會監控所有 Microsoft 365 應用程式的錯誤率。 如果我們注意到新版本與其前置任務之間的品質差別很大，我們可以透過 Microsoft Managed Desktop Admin 入口網站與您聯繫。 根據嚴重性，我們會詢問您是否要暫停發行，或通知您我們採取行動來緩解問題。 

### <a name="delivery-optimization"></a>傳遞優化

傳遞優化是 Windows 10 中可用的對等發佈技術。 它可讓裝置共用從 Microsoft 透過網際網路下載之裝置的內容，例如更新。 因為裝置可以從其本機網路上的另一個裝置取得更新的某些部分，而不是完全從 Microsoft 下載更新，所以使用它可協助減少網路頻寬。

預設會在執行 Windows 10 企業版或 Windows 10 教育版的裝置上啟用[傳遞優化](https://docs.microsoft.com/deployoffice/delivery-optimization)。 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft 受管理的桌面所管理的設定

Microsoft 會管理部分設定為服務的一部分。 Microsoft 受管理的桌面不會管理 Office 安全性基準，但是您可以遵循 [您管理的設定](#settings-you-manage) 一節中的指導方針來設定。

### <a name="update-settings"></a>更新設定

Microsoft 受管理的桌面維護受管理裝置的所有 [更新設定](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) ，您應該修改這些設定。

### <a name="set-updates-to-occur-automatically"></a>將更新設定為自動進行

**預設值**： Enabled

設定此原則是為了確保所有的 Office 裝置都可以從雲端保持最新狀態。 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>設定必須套用更新的截止期限

**預設值**：7天

**UpdateDeadline** 原則是用來設定使用者在裝置上強制執行更新之前所用的寬限期。 此期限原則也會觸發 [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 給使用者，以通知他們其裝置所需的變更。  

### <a name="defer-updates-on-a-device-for-a-period"></a>推遲裝置上的更新時間

針對每個更新管理裝置群組，這項原則的設定會有所不同，Microsoft 受管理的桌上型電腦必須符合其更新目標：  

- 測試：零天
- 第一：零天
- 快7天
- 寬：21天

### <a name="update-notifications-settings"></a>更新通知設定

**預設值**： False

在 Microsoft 受管理的桌面裝置上，[隱藏更新通知] 設定為 **False** ，可在需要更新時 [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 使用者，以提供最佳的更新體驗。

### <a name="specify-a-location-to-look-for-updates"></a>指定要尋找更新的位置

**預設值**：每月的 Enterprise 通道

使用 **UpdatePath** 和 **UpdateChannel** 原則的組合，以達到更新排程的需求。 設定這些原則，以確保所有 Office 裝置都直接從 CDN 接收更新，以進行每月的 Enterprise 通道。

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>指定 Microsoft 365 應用程式的目標版本

Microsoft 受管理的桌面有時會使用目標版本原則，以復原或固定特定版本的 Office。 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>隱藏啟用或停用 Office 自動更新的選項

**預設值**： Enabled

Microsoft 受管理的桌面需要此設定，以符合 Microsoft 365 應用程式的更新目標。 

### <a name="first-run-settings"></a>第一次執行設定 

有幾個設定會影響第一次執行 Office 的行為。

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>代表使用者接受授權條款

**預設值**： Disabled

當使用者第一次開啟 Microsoft 365 應用程式時，系統會提示他們接受授權條款。 如果您想要代表使用者接受授權條款，請使用 Microsoft Managed Desktop Operations 團隊要求服務要求，以供啟用此設定。 

### <a name="suppress-outlook-mobile-check-box"></a>[隱藏 Outlook mobile] 核取方塊

**預設值**： Disabled

當使用者第一次開啟 Outlook 時，系統會提示您安裝 Outlook Mobile。 如果您不想讓使用者看到該核取方塊，請向 Microsoft Managed Desktop Operations 團隊索要服務要求，要求為您的裝置啟用此設定。 

## <a name="other-settings"></a>其他設定

Microsoft 受管理的桌面也可以隨意設定其他 Microsoft 365 應用程式設定。 

### <a name="disable-personal-onedrive"></a>停用個人 OneDrive

**預設值**： Disabled

有些組織擔心使用者可以存取其裝置上的公司和個人檔案。 您可以使用 Microsoft Managed Desktop Operations 團隊傳送服務要求，以要求啟用此設定。 

## <a name="settings-you-manage"></a>您管理的設定

Microsoft 受管理的桌面尚未設定許多其他原則成為我們的服務的一部分。 您可以使用使用 [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Service 的 Microsoft Intune 來設定這些原則。 若要設定這些原則，請遵循下列步驟：

1.  登入 Microsoft 端點管理員管理中心。
2.  **針對 Office app > 建立，選取應用程式 > 原則**
3.  在 [ **建立原則** 設定] 頁面上，執行下列動作：
    - 輸入名稱。
    - 提供 (選用) 的描述。
    - 在 [ **指派**] 中，選擇 [這項原則是套用至 Microsoft 365 應用程式的所有使用者]，還是只適用于以 web 方式匿名存取檔的使用者。
    - 選取指派給原則設定的 AAD 型安全性群組。 每個原則設定只可指派給一個群組，而每個群組只能指派一個原則設定。
    - 設定要包含在 policy configuration 中的原則設定。 您可以搜尋原則設定名稱，以尋找您要設定的原則設定。 您也可以在應用程式上進行篩選，不論原則是建議的安全性基準，還是原則是否已設定。 [平臺] 欄位會指出是否將原則套用至適用于 Windows 裝置的 Microsoft 365 應用程式、適用于 web 的 Office 或全部。
4.  進行選取之後，請選擇 [ **建立**]。

> [!NOTE]
> Office 配置原則只支援以使用者為基礎的部署
