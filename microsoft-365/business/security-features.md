---
title: Microsoft 365 商務版安全性與合規性功能
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: 了解 Microsoft 365 商務版會隨附的安全性功能。
ms.openlocfilehash: 668b83e363a40e61391cbe56b0dbfab88cae7c43
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575691"
---
# <a name="microsoft-365-business-security-and-compliance-features"></a>Microsoft 365 商務版安全性與合規性功能

Microsoft 365 商務版提供簡化的安全性功能，以協助保護您在電腦、 手機和平板電腦上的資料。
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Microsoft 365 商務版系統管理中心的安全性功能

[![標籤，讓您知道變更在系統管理中心，然後您可以在 aka.ms/aboutM365preview 尋找更多詳細資料。](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

您可以管理許多 Microsoft 365 商務版安全性功能，在系統管理中心中，可讓您簡化的方式，以開啟這些功能，開啟或關閉。 在系統管理中心中您可以執行下列動作：
  
  
- [設定 Android 或 iOS 裝置的應用程式管理設定](app-protection-settings-for-android-and-ios.md)。 
    
    這些設定包括某一段之後，然後從非使用中的裝置中刪除檔案、 加密工作檔案，而不需要使用者設定 pin 碼等等。
    
- [設定 Windows 10 裝置的應用程式保護設定](protection-settings-for-windows-10-devices.md)。 
    
    這些設定可以套用至兩公司擁有上的公司資料或個人所擁有的裝置。
    
- [設定 Windows 10 裝置的裝置保護設定](protection-settings-for-windows-10-pcs.md)。 
    
    您可以啟用[BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405)加密，以協助保護資料，以防裝置遺失或遭竊，並啟用[Windows 惡意探索防護](https://go.microsoft.com/fwlink/p/?linkid=871404)進階勒索軟體防護。 
    
- [從裝置移除公司資料](remove-company-data.md)
    
    如果裝置遺失、 遭竊，或是員工離開公司，可以從遠端清除公司資料。
    
- [重設 Windows 10 裝置，為其原廠設定](reset-devices-to-factory-settings.md)。 
    
    您可以有套用至他們的裝置保護設定任何 Windows 10 裝置重設。
    
## <a name="additional-security-features"></a>額外的安全性功能 

Microsoft 365 商務版中的進階的功能可協助您保護網路威脅貴公司及保護機密資訊。
  
- **[Office 365 進階威脅防護](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    進階威脅防護 (ATP) 可協助保護您的業務抵禦複雜的網路釣魚和勒索軟體攻擊為了危及員工或客戶資訊。 功能包括：
    
  - 複雜的附件掃描和 AI 供電分析，以偵測並捨棄危險的郵件。
    
  - 自動檢查來評估的電子郵件中的連結是否他們是網路釣魚配置的一部分。 這會保留您安全，以防止存取不安全的網站。

- **[Intune 中的 Azure 入口網站的完整功能](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    存取 Azure 入口網站中的系統管理中心可讓您設定額外的安全性功能，例如管理 MacOS 裝置、 iPhone 及以及 for Windows，進階的裝置管理的 Android 裝置的 Intune，不能透過 Microsoft365 商務版系統管理中心。
- **Azure AD P1 計劃與相同的[條件式存取](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview)**

    條件式存取可協助保護組織免於登入風險，存取嘗試從非預期的網路或地區設定、 存取嘗試表單有風險的裝置類型，依此類推。 條件式存取原則強制執行之後的第一個驗證完成後，以及使用從第一個驗證事件的訊號來決定是否應該核准嘗試的存取，, 拒絕，或 f （例如第二個表單識別碼） 的其他證明是所需。

    包含的條件式存取功能包括：

    - 根據 [使用者名稱、 群組和角色存取權
    - Access 會[根據應用程式](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Access 會根據位置](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration); 只允許來自信任的 IP 範圍或特定國家/地區的存取 
    - 需要 MFA 的存取
    - 使用[傳統驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)的應用程式的封鎖存取
    - 需要應用程式 tp 使用[Intune 應用程式防護](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - 自訂與協力廠商提供者，例如 IODRIVE 例如 MFA 驗證。
   
    其他功能：
    - 針對混合式 Azure AD[自助密碼重設](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization)
    
## <a name="compliance-features"></a>合規性功能

訂閱包含您 Microsoft 365 商務版功能，幫助您維護合規性和法規的標準。

- **[資料外洩防護原則概觀](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)**(DLP)。 
    
    您可以設定 DLP 以自動偵測敏感資訊，例如信用卡號碼、 社會安全號碼等可防止其不慎您公司外部共用。
    
- **[Exchange Online 封存](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online Archiving 授權可讓要輕鬆地使用持續性資料備份封存的郵件。 它會儲存所有使用者的電子郵件，包括已刪除的項目，以防稍後需要探索或還原。 此外，您可以使用不同的保留原則來保留電子郵件資料的訴訟保留，eDiscovery，或符合規範需求。
    
- **[敏感性標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 商務版包含之所有功能的[Azure 資訊保護方案 1](https://go.microsoft.com/fwlink/p/?linkid=871407)。 您可以使用此計劃建立**敏感度標籤**，可讓您使用 「 不要轉寄 」 和 「 不要複製。 」 等控制項來控制存取電子郵件和文件中的敏感資訊 您也可以分類為 「 機密 」 的敏感資訊，並指定方式可以外部共用高機密性的資訊和公司內。 企業級加密很容易套用至電子郵件] 和 [保持私人資訊的文件。 您也可以安裝 Azure 資訊保護用戶端增益集的 Office 應用程式。 如需詳細資訊，請參閱[Azure 資訊保護整合標示用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)。 敏感度標籤的安裝**AzInfoProtection_UL.exe**。

您可以管理這些功能的安全性群組&amp;規範中心和 Intune 系統管理中心。 經過一段時間的簡化的控制項將會新增至 Microsoft 365 商務版系統管理中心。
  
    
## <a name="faq"></a>常見問題集

 ### <a name="are-these-security-features-available-in-all-markets"></a>所有市場中有這些安全性功能？
  
是，這些功能可在所有銷售 Microsoft 365 商務版是其中的市場。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>如何尋找安全性&amp;合規性中心？
  
1. 使用您的系統管理員認證，[登入 Microsoft 365 商務版](https://portal.microsoft.com/)。 
    
2. 在左側導覽中，找出**系統管理中心**並加以展開。 
    
    ![在 Microsoft 365 系統管理中心左側導覽中，選擇 [系統管理中心]。](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. 選擇 [**安全性&amp;規範**移至安全性&amp;合規性中心。