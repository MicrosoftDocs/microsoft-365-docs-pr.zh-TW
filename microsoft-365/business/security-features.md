---
title: Microsoft 365 商務版安全性和合規性功能
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
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: 瞭解 Microsoft 365 商務版的安全性功能。
ms.openlocfilehash: bd61ad3bf1b34635a7b80f1c9ccf63fa98d31915
ms.sourcegitcommit: 274af83139ad7da3aa33366c3323d533d95c7db4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2019
ms.locfileid: "35017515"
---
# <a name="microsoft-365-business-security-and-compliance-features"></a>Microsoft 365 商務版安全性和合規性功能

Microsoft 365 商務版提供簡化的安全性功能, 可協助保護您的電腦、電話及平板電腦上的資料。
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Microsoft 365 商務版系統管理中心安全性功能

![指向的橫幅https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

您可以在系統管理中心管理許多 Microsoft 365 商務安全性功能, 讓您更簡單的方法開啟或關閉這些功能。 在系統管理中心, 您可以執行下列動作:
  
  
- [設定 Android 或 iOS 裝置的應用程式管理設定](app-protection-settings-for-android-and-ios.md)。 
    
    這些設定包括在設定期間後從非作用中的裝置刪除檔案、加密工作檔案, 以及要求使用者設定 PIN 等等。
    
- [設定 Windows 10 裝置的應用程式保護設定](protection-settings-for-windows-10-devices.md)。 
    
    這些設定可套用至公司擁有或個人所擁有的裝置上的公司資料。
    
- [設定 Windows 10 裝置的裝置保護設定](protection-settings-for-windows-10-pcs.md)。 
    
    您可以啟用[BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405)加密來協助保護資料, 以防裝置遺失或被盜, 並讓[Windows 利用防護](https://go.microsoft.com/fwlink/p/?linkid=871404)提供勒索軟體的高級防護。 
    
- [從裝置移除公司資料](remove-company-data.md)
    
    如果裝置遺失、被竊或員工離開您的公司, 您可以從遠端清除公司資料。
    
- [將 Windows 10 裝置重設為其出廠設定](reset-devices-to-factory-settings.md)。 
    
    您可以重設任何已套用裝置保護設定的 Windows 10 裝置。
    
## <a name="additional-security-features"></a>其他安全性功能 

Microsoft 365 商務版中的高級功能可協助您保護您的公司免遭網路威脅, 並保護機密資訊。
  
- **[Office 365 高級威脅防護](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    高級威脅防護 (ATP) 可協助您的商務用複雜的網路釣魚和勒索軟體攻擊, 以損害員工或客戶資訊。 功能包括:
    
  - 複雜的附件掃描和 AI 分析, 以偵測並捨棄危險的郵件。
    
  - 自動檢查電子郵件中的連結, 以評估是否為網路釣魚架構的一部分。 這可讓您安全地存取不安全的網站。

- **[Azure 入口網站中的 Intune 的完整功能](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    存取 Azure 入口網站中的 Intune 系統管理中心可讓您設定額外的安全性功能, 例如管理 MacOS 裝置、iPhone 和 Android 裝置, 以及 Windows 的高級裝置管理 (無法透過 Microsoft 提供)。365商務系統管理中心。
- **與 Azure AD P1 計畫相同的[條件式存取](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview)**

    條件式存取可協助您的組織防止登入風險、存取非預期網路或地區設定的嘗試、存取嘗試形成有風險的裝置類型, 等等。 在第一次驗證完成後, 會強制執行條件式存取原則, 並且會使用第一個驗證事件中的信號, 來判斷嘗試的存取是否應該經過核准、拒絕或更多校對 (例如, 第二種形式的識別)。必填。

    包含的條件式存取功能包括:

    - 根據 username、group 和 role 存取
    - [根據應用程式](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access)存取 
    - 以[位置為基礎的存取權](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration); 僅允許來自信任的 IP 範圍或特定國家/地區的存取權 
    - 需要 MFA 才能進行存取
    - 封鎖對使用[舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)的應用程式的存取
    - 需要 app tp 使用[Intune 應用程式保護](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - 自訂驗證, 例如使用協力廠商提供者的 MFA (例如, 雙核)。
   
    其他功能:
    - 混合式 Azure AD 的[自助密碼重設](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization)
    
## <a name="compliance-features"></a>合規性功能

您的 Microsoft 365 商務版訂閱包含可協助您維護合規性和法規標準的功能。

- **[資料遺失防護原則概覽](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)**(DLP)。 
    
    您可以設定 DLP 來自動偵測敏感資訊, 例如信用卡號碼、社會保險號碼等等, 以防止在公司外進行意外的共用。
    
- **[Exchange Online 封存](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online 封存授權可讓郵件以連續資料備份的功能輕鬆封存。 它會儲存使用者的所有電子郵件 (包括已刪除的專案), 以防日後發現或還原。 此外, 您也可以使用不同的保留原則, 保留訴訟保留、eDiscovery 或符合規範需求的電子郵件資料。
    
- **[Azure 資訊保護](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    資訊保護可協助您控制電子郵件和檔中的敏感資訊存取, 其控制項如「不要轉寄」和「不要複製」。 您也可以將敏感資訊分類為「機密」, 並指定如何在企業外部和內部共用保密資訊。 企業級加密易於套用至電子郵件和檔, 以將您的資訊保密。 Microsoft 365 商務版包含[Azure 資訊保護方案 1](https://go.microsoft.com/fwlink/p/?linkid=871407)的所有功能。 您也可以安裝 Office 應用程式的 Azure 資訊保護用戶端增益集。 如需詳細資訊, 請參閱[Azure 資訊保護用戶端管理員指南](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)。

您可以在安全性&amp;與合規性中心和 Intune 系統管理中心管理這些功能。 經過一段時間後, 簡化的控制項會新增至 Microsoft 365 商務版系統管理中心。
  
    
## <a name="faq"></a>常見問題集

 ### <a name="are-these-security-features-available-in-all-markets"></a>這些安全性功能是否適用于所有市場？
  
是的, 在銷售 Microsoft 365 商務版的所有市場中, 都可以使用這些功能。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>如何尋找安全性&amp;合規性中心？
  
1. 使用您的系統管理員認證登[入 Microsoft 365 商務](https://portal.microsoft.com/)版。 
    
2. 在左側導覽中, 尋找 [系統**管理中心**] 並展開它。 
    
    ![在 Microsoft 365 系統管理中心的左側導覽中, 選擇 [系統管理中心]。](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. 選擇 **[ &amp;安全性符合性**] 以&amp;移至 [安全規範中心]。