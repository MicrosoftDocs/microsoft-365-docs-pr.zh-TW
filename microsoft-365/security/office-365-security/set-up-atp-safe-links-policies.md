---
title: 設定 Office 365 ATP 安全連結原則
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 設定安全連結原則來保護貴組織，以防範 Word、Excel、PowerPoint 和 Visio 檔案，以及電子郵件中的惡意連結。
ms.openlocfilehash: 86aa69b813641654a0f4b5e2b4049358aeace4df
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193479"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>設定 Office 365 ATP 安全連結原則

> [!IMPORTANT]
> 本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。 如果您是家用版使用者且正在尋找 Outlook 中安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)。

[ATP 安全連結](atp-safe-links.md)([Office 365 進階威脅防護](office-365-atp.md) (ATP) 的功能) 可協助貴組織防範網路釣魚和其他攻擊中使用的惡意連結。 如果您擁有 [Office 365 安全性與合規性中心的必要權限](permissions-in-the-security-and-compliance-center.md)，您可以設定 ATP 安全連結原則，協助確保當人員按一下網址 (URL) 時，您的組織受到保護。 您可以將 ATP 安全連結原則設定為掃描電子郵件中的 URL 和 Office 文件中的 URL。

啟用 ATP 安全連結後，如果使用者按一下電子郵件中的連結，且該 URL 已被組織的自訂封鎖 URL 清單封鎖，或是該 URL 已確定為惡意的，就會開啟警告頁面。
  
[我們會持續將新功能新增至 ATP](office-365-atp.md#new-features-in-office-365-atp)。 新增新功能後，您可能需要調整現有的 ATP 安全連結原則。

## <a name="what-to-do"></a>處理方式 
  
1. 檢閱必要條件。
    
2. 檢閱和編輯每個人都適用的預設 ATP 安全連結原則。 例如，您可以[設定 ATP 安全連結的自訂封鎖 URL 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。
    
3. 新增或編輯特定電子郵件收件者的原則，包括[針對 ATP 安全連結設定自訂「不要重寫」URL 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。
    
4. 了解 ATP 安全連結原則選項 (在本文中)，包括最近變更的設定。
    
## <a name="step-1-review-the-prerequisites"></a>步驟 1：檢閱必要條件

- 請確認您組織有 [Office 365 進階威脅防護](office-365-atp.md)。
    
- 請確定您具有必要權限。 若要定義 (或編輯) ATP 原則，您必須獲派適當的角色。 下表中有一些範例描述： <br>

    |角色  |指派位置/條件  |
    |---------|---------|
    |Office 365 全域管理員 |註冊購買 Office 365 的人會預設為為全域系統管理員。 (請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入了解。)         |
    |安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

    若要深入了解角色和權限，請參閱 [Office 365 安全性的權限與合規性中心](permissions-in-the-security-and-compliance-center.md)。

- 確定 Office 用戶端已設定為使用[新式驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (這會用於 Office 文件中的 ATP 安全連結保護)。
    
- [了解 ATP 安全連結原則選項](#step-4-learn-about-atp-safe-links-policy-options) (在本文中)。 

- 最多需要 30 分鐘的時間，最新或更新的原則才會散佈至所有 Office 365 資料中心。
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>步驟2：定義 (或檢閱) 每個人都適用的 ATP 安全連結原則

當您擁有 [Office 365 進階威脅防護](office-365-atp.md)時，您會有貴組織中每個人都適用的預設 ATP 安全連結原則。 請務必檢閱，並視需要編輯預設原則。
  
1. 移至 [https://protection.office.com](https://protection.office.com) 然後以您的公司或學校帳戶當入。 
    
2. 在左側導覽中，選擇 [威脅管理]**** 下方的 [原則]** \> [安全連結]******。
    
3. 在 **套用於整個組織的原則**區段中，選取 [預設] ****，然後選擇 [編輯] **** (編輯按鈕類似鉛筆)。<br/>![按一下 [編輯] 已編輯安全連結防護預設原則](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. 在 [封鎖下列 URL]**** 區段中，指定您想要防止貴組織中的人員造訪的一或多個 URL。 (請參閱[使用 ATP 安全連結來設定自訂的封鎖 URL 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。)
    
5. 在 [套用到電子郵件以外內容的設定]**** 區段中，選取 (或清除) 您要使用的選項。 (建議您選取所有選項。) 
    
6. 選擇 [儲存]****。
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>步驟3：新增 (或編輯) 適用於特定電子郵件收件者的 ATP 安全連結原則

在您檢閱 (或編輯) 每個人都適用的預設 ATP 安全連結原則之後，下一個步驟是定義您會套用到特定收件者的其他原則。 例如，您可定義其他原則，以指定預設原則的例外狀況。 
  
1. 移至 [https://protection.office.com](https://protection.office.com) 然後以您的公司或學校帳戶當入。 
    
2. 在左側導覽中，選擇 [威脅管理]**** 下方的 [原則]****。
    
3. 選擇 [安全連結]****。
    
4. 在 [適用於特定收件者的原則]**** 區段中，選擇 [新增]**** ([新增] 按鈕類似加號 (**+**))。<br/>![選擇 [新增] 以新增特定電子郵件收件者的安全連結原則](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. 指定原則的名稱、描述及設定。<br/>**範例：** 若要設定名為「禁止直接點選」的原則，該原則不允許貴組織中特定群組的人員在沒有 ATP 安全連結保護的情況下點選特定網站，您可以指定下列建議設定： 
    
    - 在 [名稱]**** 方塊中，鍵入「禁止直接點選」。

    - 在 [描述]**** 方塊中，鍵入類似以下的描述：禁止特定群組中的人員在未經 ATP 安全連結驗證的情況下點選網站。

    - 在 [**選取郵件中未知的可能惡意 URLs 動作**] 底下，選擇 [**開啟**]。

    - 如果您看到 **[選取 Microsoft 小組中未知或潛在惡意 URLs 的動作**]，請選擇 [**開啟**]。 <br/>

    - 如果您想要為可疑和指向檔案的 URL 啟用 URL 引爆功能 (建議使用)，請選取 [針對可疑的連結和指向檔案的連結套用即時 URL 掃描]****。 如果您希望只有在完全掃描 URL 之後才讓使用者接收郵件，則選取 [等到 URL 掃描完成再傳遞郵件]****。

    - 如果您想要針對在組織內使用者間傳送的郵件啟用安全連結 (建議使用)，請選取 [將安全連結套用至組織內傳送的郵件]****。

    - 如果您不希望個別使用者覆寫「進行中的掃描」** 或「已封鎖 URL」** 通知頁面，請選取 [不允許使用者點選原始 URL]****。

    - (選用) 在 [不要重寫下列 URL]**** 區段中，指定一或多個被認為對貴組織很安全的 URL。 (請參閱[使用 ATP 安全連結來設定自訂「不要重寫」URL 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))

    - 在 [套用至]**** 區段中，選擇 [收件者是以下的成員]****，然後選擇您想要包含在原則中的群組。 選擇 [新增]****，然後選擇 [確認]****。
    
6. 選擇 [儲存]****。

> [!NOTE]
> 具有較高優先順序的 ATP 安全連結原則將優先執行。 如果使用者受制于兩個或多個原則，則只有較高優先順序的原則才能生效。
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>步驟 4：了解 ATP 安全連結原則選項

當您設定或編輯 ATP 安全連結原則時，會看到幾個可用的選項。 如果您想知道這些選項的功能，下表會說明有每個選項及其效用。 請記住，要定義或編輯的主要 ATP 安全連結原則有兩種：
- 每個人都適用的[預設原則](#default-policy-options)；以及  
- [特定收件者的其他原則](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>預設原則選項

預設原則選項適用於貴組織中的每個人。

|此選項  |執行此動作  |
|---------|---------|
| **封鎖下列 URL** <br/>    | 可讓貴組織擁有自動封鎖的自訂 URL 清單。 使用者按一下此清單中的 URL 後，就會前往說明 URL 為何遭到封鎖的[警告頁面](atp-safe-links-warning-pages.md)。 若要深入了解，請參閱[使用 Office 365 ATP 安全連結來設定自訂封鎖的 URL 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。 |
| **Office 365 專業增強版、iOS 版與 Android 版 Office** <br/>    | 選取此選項時，ATP 安全連結保護適用于 Word、Excel URLs 及 PowerPoint 檔案中的 Windows 或 Mac 作業系統、Outlook 中的電子郵件、iOS 或 Android 裝置上的 Office 檔、Windows 上的 Visio 2016 檔案，以及在 Office 應用程式的 web 版本（Word、PowerPoint、Excel、Outlook 及 OneNote）中開啟的檔案，只要使用者已登入 Office 365。 |
| **當使用者按一下 ATP 安全連結時不要追蹤** <br/>  | 選取此選項時，不會儲存 [Word]、[Excel]、[PowerPoint]、[Visio 檔] 及 [Outlook 電子郵件訊息] 中 URLs 的資料。  <br/> |
|**不要讓使用者點選原始 URL 的 ATP 安全連結** <br/> |若選取此選項，使用者就無法繼續將[警告頁面](atp-safe-links-warning-pages.md)傳送到被判定是惡意的 URL。  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>適用於特定電子郵件收件者的原則

|此選項  |執行此動作  |
|---------|---------|
|**關閉** <br/> |不要掃描電子郵件中的 URL。  <br/> 可讓您定義例外狀況規則，例如以下規則：不要掃描特定收件者群組的電子郵件中的 URL。  <br/> |
|**開啟** <br/> |當使用者按一下電子郵件中的 URL 並啟用 Windows 上 Outlook (C2R) 中的 ATP 安全連結時，重寫 URL 以透過 ATP 安全連結防護路由傳送使用者。  <br/> 如果 URL 沒有令人信服的信譽，則在點選已封鎖或惡意的 URL 清單時檢查 URL，並以非同步方式在背景觸發 URL 引爆。  <br/> |
|**Microsoft 小組中的未知或潛在的惡意 URLs** |當您使用並選取此選項時，它會開啟 Microsoft 團隊聊天和頻道中的 ATP 安全連結。 當使用者在 Microsoft 小組聊天或通道中按一下 URL 時，會檢查連結。 會針對封鎖或惡意的 URLs 清單，檢查此 URL，並在背景中以非同步方式觸發 URL 的引爆（如果 URL 不具備有效的信譽）。 |
|**針對可疑的連結和指向檔案的連結套用即時 URL 掃描** <br/> |若選取此選項，則會掃描指向可下載內容的可疑 URL 和連結。  <br/> |
|**等待 URL 掃描完成再傳遞郵件** <br/> |若選取此選項，則會保留包含要掃描 URL 的郵件，直到 URL 完成掃描且確認是安全的，才會傳遞這些郵件。  <br/> |
|**將安全連結套用至組織內傳送的郵件** <br/> | 選取此選項時，只要電子郵件帳戶主控于 Office 365，就會將 ATP 安全連結保護套用至組織中的人員所傳送的電子郵件。  <br/> |
|**不要追蹤使用者點選** <br/> |若選取此選項，則不會儲存來自外部寄件者的電子郵件中 URL 的點選資料。 目前不支援追蹤組織內傳送的電子郵件中連結的 URL 點選。  <br/> |
|**不允許使用者點選原始 URL** <br/> |若選取此選項，使用者就無法繼續將[警告頁面](atp-safe-links-warning-pages.md)傳送到被判定是惡意的 URL。  <br/> |
|**不要重寫下列 URL** <br/> |將 URL 保留原樣。 保留不需要掃描貴組織中特定電子郵件收件者群組的自訂安全 URL 清單。  如需詳細資料 (包括支援萬用字元星號 (\*) 的近期變更)，請參閱[使用 ATP 安全連結來設定自訂「不要重寫」URL 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。  <br/> |
   
## <a name="next-steps"></a>後續步驟

在您的 ATP 安全連結原則就緒後，您就可以透過查看報告，查看 ATP 對您的組織的運作方式。 請參閱下列資源，以深入了解詳細資訊：

- [檢視 Office 365 進階威脅防護的報告](view-reports-for-atp.md)

- [使用安全性與合規性中心的總管](threat-explorer.md)

隨時掌握最新的 ATP 功能。 瀏覽 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。
