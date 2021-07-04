---
title: Microsoft 365 Apps 企業版
description: 如何部署 Microsoft 365 Apps、更新方式及設定的管理方式
keywords: 變更歷程記錄
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 7b1178312178865face58748a37228f60643d5fc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287972"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps 企業版

## <a name="initial-deployment"></a>初始部署

Microsoft 受管理的電腦確保將 Microsoft 365 Apps 企業版 (64 位) 安裝為所有[程式裝置](../service-description/device-list.md)上的影像的一部分。 傳送裝置時，裝置上應會出現下列所有應用程式：

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Access
- 商務用 Skype
- OneNote

這種方法會將網路影響降至最低，並確保使用者在收到其裝置時可以立即生產力。 然後，我們會將更多原則部署到受管理的裝置，以設定要使用的應用程式。

> [!NOTE]
> Microsoft Teams 會與 Microsoft 365 Apps 企業版分開部署，而且不會包含在基底影像中。 

### <a name="available-deployment-to-users"></a>適用于使用者的部署

如果使用者在其裝置上沒有任何原因的 Microsoft 365 Apps，您可以使用套件將裝置傳回其預期的狀態。 將使用者新增至 **新式的工作場所 Office Office365_Install** 群組，且應用程式會在公司入口網站中變為可用。

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps 企業版 (32 位) 

Microsoft 受管理的電腦不支援部署32位版本的 M365 應用程式的 enterprise。

## <a name="updates-to-microsoft-365-apps"></a>Microsoft 365 Apps 的更新

Microsoft 365 Apps 會設定為[每月 Enterprise 通道](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)更新。 這項作法每月都會為您的使用者提供新的 Office 功能，但每月只會收到一次更新的版本，以供預測的發行排程使用。 更新會在每月的第二個星期二發佈;這些更新可包含功能、安全性和品質更新。 這些更新會自動進行，並且直接從該特定通道的 Office CDN 中拉入。

Microsoft 受管理的電腦 staggers 每個版本，以找出您環境中的任何潛在問題。 從 Microsoft 365 應用程式產品群組發行一開始28天，我們就會完成。 Microsoft 受管理的電腦排程將更新版本更新成不同的群組，允許驗證及測試的時間如下： 

- 測試：零天
- 第一：零天
- Fast：3天
- 寬：7天

Microsoft 受管理的電腦會設定裝置的7天[更新期限](/deployoffice/configure-update-settings-microsoft-365-apps)。 更新可供使用後，必須在七天內安裝。 使用者會 [收到](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 下列數個位置要求的更新：應用程式，在最後期限之前的系統託盤12小時內，而且會在最後期限之前收到15分鐘的警告。 所有 Microsoft 365 Apps 都必須關閉，更新才會完成。

### <a name="pausing-or-rolling-back-an-update"></a>暫停或回復更新

如果您出於任何原因需要暫停或復原 Microsoft 365 的應用程式更新，請透過 Microsoft 受管理的電腦入口網站，將系統[管理員支援要求](../working-with-managed-desktop/admin-support.md)歸檔。

在發行時，Microsoft 受管理的電腦會監控所有 Microsoft 365 Apps 的錯誤率。 如果我們注意到新版本與其前置任務之間的品質差別很大，我們可以透過 Microsoft 受管理的電腦管理入口網站與您聯繫。 根據嚴重性，我們會詢問您是否要暫停發行，或通知您我們採取行動來緩解問題。 

### <a name="delivery-optimization"></a>傳遞優化

傳遞優化是 Windows 10 中可用的對等發佈技術。 它可讓裝置共用從 Microsoft 透過網際網路下載之裝置的內容，例如更新。 因為裝置可以從其本機網路上的另一個裝置取得更新的某些部分，而不是完全從 Microsoft 下載更新，所以使用它可協助減少網路頻寬。

預設會在執行 Windows 10 企業版或 Windows 10 教育版版本的裝置上啟用[傳遞優化](/deployoffice/delivery-optimization)。 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>由 Microsoft 受管理的電腦管理設定

Microsoft 會管理部分設定為服務的一部分。 Microsoft 受管理的電腦不會管理 Office 的安全性基準，但是您可以遵循[您管理設定](#settings-you-manage)中的指導方針加以設定。

### <a name="update-settings"></a>更新設定

Microsoft 受管理的電腦維護受管理裝置的所有[更新設定](/deployoffice/configure-update-settings-microsoft-365-apps)，您應該修改這些設定。

### <a name="set-updates-to-occur-automatically"></a>將更新設定為自動進行

**預設值**： Enabled

設定此原則是為了確保所有 Office 裝置都可以從雲端保持最新狀態。 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>設定必須套用更新的截止期限

**預設值**：7天

**UpdateDeadline** 原則是用來設定使用者在裝置上強制執行更新之前所用的寬限期。 此期限原則也會觸發 [通知](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 給使用者，以通知他們其裝置所需的變更。  

### <a name="defer-updates-on-a-device-for-a-period"></a>推遲裝置上的更新時間

針對每個更新管理裝置群組，此原則的設定會有所不同，而且 Microsoft 受管理的電腦以滿足其更新目標的要求：  

- 測試：零天
- 第一：零天
- 快7天
- 寬：21天

### <a name="update-notifications-settings"></a>更新通知設定

**預設值**： False

[隱藏更新通知] 設定會在 Microsoft 受管理的電腦裝置上設定為 **False** ，以便在需要更新時 [通知](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)使用者，以提供最佳的更新經驗。

### <a name="specify-a-location-to-look-for-updates"></a>指定要尋找更新的位置

**預設值**：每月 Enterprise 通道

使用 **UpdatePath** 和 **UpdateChannel** 原則的組合，以達到更新排程的需求。 設定這些原則，以確保所有 Office 裝置都直接從每月 Enterprise 通道的 CDN 接收更新。

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>指定 Microsoft 365 Apps 的目標版本

目標版本原則有時候會用 Microsoft 受管理的電腦，以復原或固定特定版本的 Office。 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>隱藏啟用或停用 Office 自動更新的選項

**預設值**： Enabled

Microsoft 受管理的電腦以滿足 Microsoft 365 應用程式的更新目標，必須要有此設定。 

### <a name="first-run-settings"></a>第一次執行設定 

在 Office 第一次執行時，有數個設定會影響行為。

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>代表使用者接受授權條款

**預設值**： Disabled

當使用者第一次開啟 Microsoft 365 應用程式時，系統會提示他們接受授權條款。 如果您想要代表使用者接受授權條款，請將服務要求歸檔至 Microsoft 受管理的電腦作業小組要求啟用此設定。 

### <a name="suppress-outlook-mobile-check-box"></a>隱藏 Outlook 行動裝置核取方塊

**預設值**： Disabled

當使用者第一次開啟時 Outlook 系統會提示他們安裝 Outlook Mobile。 如果您不想讓使用者看到該核取方塊，請將服務要求歸檔至 Microsoft 受管理的電腦作業小組要求為您的裝置啟用此設定。 

## <a name="other-settings"></a>其他設定

其他一些 Microsoft 365 應用程式設定 Microsoft 受管理的電腦可以選擇性地加以設定。 

### <a name="disable-personal-onedrive"></a>停用個人 OneDrive

**預設值**： Disabled

有些組織擔心使用者可以存取其裝置上的公司和個人檔案。 您可以將服務要求與 Microsoft 受管理的電腦作業小組一起要求啟用此設定。 

## <a name="settings-you-manage"></a>您管理的設定

還有許多其他原則 Microsoft 受管理的電腦尚未設定為我們的服務的一部分。 您可以使用 Microsoft Intune，使用[Office 雲端原則](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied)服務來設定這些原則。 若要設定這些原則，請遵循下列步驟：

1. 登入 Microsoft 端點管理員系統管理中心。
2. **針對 Office > 建立的應用程式選取應用程式 > 原則**
3. 在 [ **建立原則** 設定] 頁面上，執行下列動作：
    - 輸入名稱。
    - 提供 (選用) 的描述。
    - 在 [**工作分派**] 中，選擇是否要將這個原則套用至 Microsoft 365 Apps 企業版的所有使用者，或僅針對使用 Office 網頁版匿名存取檔的使用者。
    - 選取指派給原則設定的 AAD 型安全性群組。 每個原則設定只可指派給一個群組，而每個群組只能指派一個原則設定。
    - 設定要包含在 policy configuration 中的原則設定。 您可以搜尋原則設定名稱，以尋找您要設定的原則設定。 您也可以在應用程式上進行篩選，不論原則是建議的安全性基準，還是原則是否已設定。 [平臺] 欄位會指出是否將原則套用至 Windows 裝置、Office 網頁版或全部的 Microsoft 365 Apps 企業版。
4. 進行選取之後，請選擇 [ **建立**]。

> [!NOTE]
> Office設定原則只支援以使用者為基礎的部署
