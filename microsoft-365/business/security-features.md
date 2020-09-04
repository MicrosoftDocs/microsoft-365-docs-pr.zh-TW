---
title: Microsoft 365 商務版安全性和合規性功能
f1.keywords:
- NOCSH
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: 深入瞭解 Microsoft 365 商務版 Premium 隨附的安全性功能，協助保護電腦、電話和平板電腦上的資料。
ms.openlocfilehash: 5e16d4bf297d363b6f9b44ce854c857e7e5464ed
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357311"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Microsoft 365 商務版安全性和合規性功能

Microsoft 365 商務版特優提供簡化的安全性功能，以協助保護電腦、電話和平板電腦上的資料。
    
## <a name="microsoft-365-admin-center-security-features"></a>Microsoft 365 系統管理中心安全性功能

您可以在系統管理中心管理許多 Microsoft 365 商務版的安全性功能，其可讓您簡化開啟或關閉這些功能的方法。 在系統管理中心中，您可以執行下列作業：
  
- [設定 Android 或 iOS 裝置的應用程式管理設定](app-protection-settings-for-android-and-ios.md) 。 
    
    這些設定包括在設定期間內刪除非作用中裝置上的檔案、加密工作檔，以及要求使用者設定 PIN 等等。
    
- [設定 Windows 10 裝置的應用程式保護設定](protection-settings-for-windows-10-devices.md) 。 
    
    您可以將這些設定套用到公司所擁有的裝置或屬於個人的裝置上的公司資料。
    
- [設定 Windows 10 裝置的裝置保護設定](protection-settings-for-windows-10-pcs.md) 。 
    
    您可以啟用 [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) 加密，協助保護資料以防裝置遺失或遭盜，並啟用 [Windows 利用防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) ，以針對勒索軟體提供高級防護。 
    
- [從裝置移除公司資料](remove-company-data.md)
    
    如果裝置遺失、被竊或員工離開您的公司，您可以從遠端清除公司資料。
    
- [將 Windows 10 裝置重設為其出廠設定](reset-devices-to-factory-settings.md) 。 
    
    您可以重設任何已套用裝置保護設定的 Windows 10 裝置。
    
## <a name="additional-security-features"></a>其他安全性功能 

Microsoft 365 商務版中的高級功能可協助您保護您的公司免受網路威脅，並保護機密資訊。
  
- **[Office 365 進階威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)**
    
    「高級威脅防護 (ATP) 會協助您的企業防禦複雜的網路釣魚和勒索軟體攻擊，以損臔員工或客戶資訊。 功能包括：
    
  - 複雜的附件掃描及 AI 功能的分析，可偵測並捨棄危險的郵件。
    
  - 自動檢查電子郵件中的連結，以評估其是否為網路釣魚架構的一部分。 這可讓您安全地存取不安全的網站。

- **[Azure 入口網站中 Intune 的完整功能](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    存取 Azure 入口網站中的 Intune 系統管理中心，可讓您設定其他安全性功能，例如管理 MacOS 裝置、iPhone 和 Android 裝置，以及 Windows 的高級裝置管理，但無法透過 Microsoft 365 系統管理中心取得。
- **與 Azure AD Premium P1 方案相同的[條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)**


    條件式存取可協助您保護組織避免登入風險、存取意外網路或地區的企圖、存取危險裝置類型的企圖，等等。 在第一個驗證完成後，會強制執行條件式存取原則，並使用第一個驗證事件中的信號，判斷嘗試的存取是否應獲得核准、拒絕，或是需要更多證明 (例如，例如識別) 的第二種格式）。

    條件式存取功能包括：

    - 根據使用者名稱、群組和角色進行存取
    - [根據應用程式](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access)存取 
    - 以[位置為基礎的存取權](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration); 只允許來自信任的 IP 範圍或特定國家/地區的存取 
    - 需要 MFA 才能進行存取
    - 封鎖使用[舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)之應用程式的存取
    - 需要應用程式 tp 使用 [Intune 應用程式保護](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - 自訂驗證，例如使用協力廠商提供者進行 MFA，例如，雙核。
   
    其他功能：
    - 混合式 Azure AD 的[自助密碼重設](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization)
    
## <a name="compliance-features"></a>合規性功能

您的 Microsoft 365 商務版訂閱中包含的功能可協助您維護符合性和法規標準。

- **[資料遺失防護原則](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)** (DLP) 的概覽。 
    
    您可以將 DLP 設定為自動偵測敏感資訊，例如信用卡號碼、社會保險號碼等等，以防止在公司外意外共用。
    
- **[Exchange Online 封存](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online 封存授權可讓郵件透過連續資料備份輕鬆封存。 它會儲存使用者的所有電子郵件，包括已刪除的專案，以備日後進行探索或還原時使用。 此外，您可以使用不同的保留原則來保留電子郵件資料，以用於訴訟保留、eDiscovery，或符合規範的需求。
    
- **[敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 商務版 Premium 包含 [Azure 資訊保護方案 1](https://go.microsoft.com/fwlink/p/?linkid=871407)的所有功能。 透過這項計畫，您可以建立 **靈敏度標籤** ，讓您在電子郵件和檔中控制敏感資訊的存取權，例如「不要轉寄」和「不要複製」控制項。 您也可以將機密資訊分類為「機密」，並指定保密資訊在公司外及公司內部共用的方式。 企業級加密易於套用至電子郵件和檔，以將資訊保密。 您也可以安裝 Office 應用程式的 Azure 資訊保護用戶端增益集。 如需詳細資訊，請參閱 [Azure 資訊保護統一標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)。 若為敏感度標籤，請安裝 **AzInfoProtection_UL.exe**。

您可以在安全性與 &amp; 合規性中心及 Intune 系統管理中心中管理這些功能。 經過一段時間後，簡化的控制項會新增至 Microsoft 365 系統管理中心。
  
    
## <a name="faq"></a>常見問題集

 ### <a name="are-these-security-features-available-in-all-markets"></a>所有市場是否都有這些安全性功能？
  
是的，在銷售 Microsoft 365 商務版津貼的所有市場中，都有提供這些功能。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>如何找到安全性與 &amp; 合規性中心？
  
1. 使用您的系統管理員認證登[入 Microsoft 365 商務版 Premium](https://portal.microsoft.com/) 。 
    
2. 在左側導覽中，尋找 [系統 **管理中心** ] 並展開它。 
    
    ![在 Microsoft 365 系統管理中心的左側導覽中，選擇 [系統管理中心]。](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. 選擇 [ **安全性 &amp; 符合性** ] 以移至 [安全性與 &amp; 合規性中心]。
