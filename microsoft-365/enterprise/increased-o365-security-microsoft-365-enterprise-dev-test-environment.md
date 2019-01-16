---
title: Microsoft 365 企業版測試環境之增強的 Office 365 安全性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南，讓其他 Office 365 的安全性設定 Microsoft 365 企業版測試環境。
ms.openlocfilehash: 62cf2347d3e003e9368c987912e7748029241501
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866386"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企業版測試環境之增強的 Office 365 安全性

使用本文中的指示，您可以設定以增加安全性 Microsoft 365 企業版測試環境中的其他 Office 365 設定。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境

如果您只想要設定加強的 Office 365 安全性的基本需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您要設定模擬企業中加強的 Office 365 安全性，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。
  
> [!NOTE]
> 測試加強的 Office 365 安全性不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試自動化授權和群組成員資格和代表的典型組織的環境中實驗。 


## <a name="phase-2-configure-increased-office-365-security"></a>階段 2： 設定較高的 Office 365 安全性

在此階段中，您可以啟用加強的 Office 365 安全性 Microsoft 365 企業版測試環境。如需其他詳細資料及設定，請參閱[設定您的 Office 365 租用戶增加安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>設定 SharePoint Online 封鎖不支援經過驗證的應用程式

不支援經過驗證的應用程式不能有[身分識別與裝置存取設定](microsoft-365-policies-configurations.md)套用至他們，這是保護您的 Microsoft 365 訂閱和其數位資產的重要元素。 

1. 移至 [Office 入口網站 ([https://office.com](https://office.com)) 並登入您的 Office 365 試用版訂閱以全域管理員帳戶。
    
  - 如果您使用輕量級的 Microsoft 365 測試環境，從您的本機電腦登入。
    
  - 如果您使用模擬的企業的 Microsoft 365 測試環境，使用[Azure 入口網站](https://portal.azure.com)連線到 CLIENT1 虛擬機器，並從 CLIENT1 登入。
 
2. 從**Microsoft 365 系統管理中心**] 索引標籤上，按一下 [**管理**]。
3. 在 [新**Microsoft 365 系統管理中心**] 索引標籤上按一下 [**系統中心 > SharePoint**。
4. 在 [新增**SharePoint 系統管理中心**] 索引標籤上按一下 [**存取控制**]。
5. 下 **，不支援經過驗證的應用程式**，[**封鎖**，然後再按一下 [**確定]**。


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>啟用 Advanced 威脅保護） for SharePoint、 OneDrive for Business 和 Microsoft 小組

Office 365 進階威脅保護 (ATP) 是一種功能的 Exchange Online Protection (EOP) 可協助保留惡意程式碼不在您的電子郵件。ATP，與您建立原則在 Exchange 系統管理中心 (EAC) 或安全性及規範中心有助於確保您的使用者存取僅或連結會被識別為不是惡意的電子郵件中的附件。如需詳細資訊，請參閱 ＜[進階的威脅保護安全附件及安全的連結](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)。

1. 在瀏覽器中的 [ **Microsoft 365 系統管理中心**] 索引標籤中，按一下 [**系統中心 > 安全性與規範**。
2. 在 [新**的安全性與規範**] 索引標籤上按一下 [**威脅管理 > 原則**。
3. 按一下 [ **ATP 安全附件**。
4. 在 [**安全的附件**] 窗格中，選取 [**開啟 SharePoint、 OneDrive 及 Microsoft 小組 ATP**、] 和 [**儲存**。

### <a name="enable-anti-malware"></a>啟用反惡意程式碼

惡意程式碼是由病毒和間諜軟體所組成。病毒感染其他程式和資料，且其分配整個尋找程式感染的電腦。間諜軟體指的是收集您的個人資訊，例如登入資訊及個人資料，並傳送回惡意程式碼撰寫的惡意程式碼。 

Office 365 內建的惡意軟體和垃圾郵件篩選功能，協助保護惡意軟體輸入及輸出郵件並協助您免受垃圾郵件。如需詳細資訊，請參閱[Office 365 中的反垃圾郵件與反惡意程式碼保護](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

若要確定反惡意程式碼處理正在執行與一般的附件檔案類型的檔案上：

1. 按一下 [在瀏覽器可以回到 [**原則**] 頁面上的 [上一頁] 按鈕。
2. 按一下 [**反惡意程式碼**。
3. 按兩下名為**預設**原則。
4. 在 [**反惡意程式碼原則**] 視窗中，按一下 [**設定**]。
4. [**公用附件類型篩選器**] 中，按一下 [**上 > 儲存**。


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a>階段 3： 檢查 Office 365 的安全性工具和記錄檔

在此階段中，您在查看安全性事件的相關通知您及測量整體的安全性狀況的內建服務。

### <a name="threat-management-dashboard"></a>威脅管理儀表板

Office 365 Threat management 可協助您控制和管理您的組織資料的行動裝置存取、 說明從資料遺失保護您的組織及從惡意軟體和垃圾郵件保護輸入及輸出郵件。您也可以使用 threat management 來保護您的網域信譽並決定要惡意詐騙的寄件者從您的網域帳戶。如需詳細資訊，請參閱[威脅中管理 Office 365 的安全性與規範中心](https://docs.microsoft.com/office365/securitycompliance/threat-management)。

若要檢視 Office 365 威脅管理儀表板中使用下列步驟：

1. 在瀏覽器中的 [ **Microsoft 365 系統管理中心**] 索引標籤中，按一下 [**系統中心 > 安全性與規範**。
2. 在 [新**的安全性與規範**] 索引標籤上按一下 [**威脅管理 > 儀表板**。
3. 新增**儀表板**] 索引標籤上瀏覽器中，記下惡意程式碼趨勢、 洞察力及儀表板的其他小節。

### <a name="office-365-cloud-app-security-dashboard"></a>Office 365 雲端應用程式安全性儀表板

Office 365 雲端應用程式安全性] 先前稱為 「 Office 365 進階安全性管理，可讓您建立的監控和通知您在 Office 365 訂閱中可疑的活動，讓您可以調查並採取可能的原則修復動作。如需詳細資訊，請參閱[概觀 （英文） 的 Office 365 雲端應用程式安全性](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview)。

1. 在瀏覽器中的 [ **Microsoft 365 系統管理中心**] 索引標籤中，按一下 [**系統中心 > 安全性與規範**。
2. 在 [新**的安全性與規範**] 索引標籤上按一下 [**提醒 > 進階提醒的管理 > 移至 Office 365 雲端應用程式安全性**。
3. 在新的**雲端應用程式安全性**] 索引標籤，記下儀表板檢視與所監視之 Office 365 訂閱中的各種活動的預設原則清單。
4. 按一下 [儀表板] 圖示以查看所追蹤的雲端應用程式安全性活動的摘要。
5. 按一下 [**調查**（眼鏡圖示） 然後**活動記錄檔**以查看最新的登入的清單和其他活動。

### <a name="secure-score"></a>安全的分數

1. 在瀏覽器中建立新的索引標籤，並移至**securescore.office.com**。
2. 在**儀表板] 索引標籤**中，記下您目前的安全分數與佇列中的動作清單以增加您分數。

請參閱 ＜ [Configure 增加 security for Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)步驟中的資訊及連結在生產環境中設定這些設定的**資訊保護**階段。

## <a name="next-step"></a>下一步

探索測試環境的其他[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)特色和功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)

