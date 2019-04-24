---
title: 適用於 Microsoft 365 企業版測試環境的增強的 Microsoft 365 安全性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南來啟用其他 Microsoft 365 安全性設定 Microsoft 365 企業版測試環境。
ms.openlocfilehash: 54e05122dcbe5d4e24f092536897f2a8ad449e05
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283653"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>適用於 Microsoft 365 企業版測試環境的增強的 Microsoft 365 安全性

透過本文中的指示，您設定其他 Microsoft 365 若要提高安全性，Microsoft 365 企業版測試環境中。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1： 建置 Microsoft 365 企業版測試環境

如果您只想以具有最小需求的輕量型方式設定增強的 Microsoft 365 安全性，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。
  
如果您想要在模擬的企業中設定增強的 Microsoft 365 安全性，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。
  
> [!NOTE]
> 測試增強的 Microsoft 365 安全性不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 Active Directory 網域服務 (AD DS) 樹系。 它提供了此選項，讓您可以測試自動授權和群組成員資格與代表典型組織的環境中實驗。 


## <a name="phase-2-configure-increased-microsoft-365-security"></a>階段 2： 設定增強的 Microsoft 365 安全性

在這個階段，您可以啟用增強的 Microsoft 365 安全性適用於 Microsoft 365 企業版測試環境。 如需詳細資訊及設定，請參閱 < <b0>Configure Office 365 租用戶以提高安全性</b0>。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>設定 SharePoint Online 來封鎖不支援新式驗證的應用程式

不支援新式驗證的應用程式不能有[身分識別與裝置存取設定](microsoft-365-policies-configurations.md)套用至它們，也就是保護您的 Microsoft 365 訂閱和其數位資產的重要元素。 

1. 移至 Office 入口網站 ([https://office.com](https://office.com)) 並登入 Office 365 試用訂閱以全域管理員帳戶。
    
  - 如果您使用輕量級 Microsoft 365 測試環境，從您本機電腦登入。
    
  - 如果您使用 Microsoft 365 模擬企業版測試環境，使用[Azure 入口網站](https://portal.azure.com)連線至 CLIENT1 虛擬機器，然後從 CLIENT1 登入。
 
2. 從**Microsoft 365 系統管理中心**] 索引標籤上，按一下 [**系統**]。
3. 在 [新的**Microsoft 365 系統管理中心**] 索引標籤，按一下 [**系統管理中心 > SharePoint**。
4. 在 [新的**SharePoint 系統管理中心**] 索引標籤，按一下 [**存取控制**。
5. [] 下 **，不支援新式驗證的應用程式**，按一下 [**封鎖**]，然後按一下 [**確定]**。


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>啟用進階的威脅防護 for SharePoint、 OneDrive for Business 和 Microsoft Teams

Office 365 進階威脅防護 (ATP) 的 SharePoint、 OneDrive 及 Microsoft Teams 會保護您的組織不小心共用惡意檔案。

1. 移至[Office 365 安全性 & 合規性中心](https://protection.office.com)，並使用您的全域系統管理員帳戶登入。

2. 在左側的導覽窗格中，**威脅管理**] 下選擇 [**原則 > 安全附件**]。 

3. 選取 [**開啟 ATP SharePoint、 OneDrive 及 Microsoft Teams**。

4. 按一下 [儲存]****。


### <a name="enable-anti-malware"></a>啟用反惡意程式碼

惡意程式碼是由病毒和間諜軟體組成。 病毒會感染其他程式和資料，同時會擴散到整個電腦，找尋可攻擊的程式。 間諜軟體會收集您的個人資訊 (如登入資訊和個人資料)，並將其傳回給惡意程式碼作者。 

Office 365 具有內建的惡意軟體和垃圾郵件篩選功能，可協助防止惡意軟體的輸入及輸出郵件，並協助保護您免於垃圾郵件。 如需詳細資訊，請參閱[在 Office 365 中的反垃圾郵件 & 反惡意程式碼保護](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

若要確保反惡意程式碼處理正在執行常見的附件檔案類型的檔案：

1. 按一下 [若要返回 [**原則**] 頁面上的瀏覽器的上一頁按鈕。
2. 按一下 [**反惡意程式碼**]。
3. 連按兩下 [名為**預設**的原則。
4. 在**反惡意程式碼原則**] 視窗中，按一下 [**設定**]。
4. [**常見的附件類型篩選器**] 中，按一下 [**在 > 儲存**。


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a>階段 3： 檢查 Office 365 安全性工具和記錄檔

在這個階段，您查看安全性事件的相關通知您以及測量您的整體安全性狀態的內建服務。

### <a name="threat-management-dashboard"></a>威脅管理儀表板

Office 365 威脅管理，可協助您控制和管理行動裝置存取您的組織資料，協助保護組織免於資料遺失，並協助防止惡意軟體和垃圾郵件的輸入及輸出郵件。 您也會使用威脅保護您的網域信譽，並判斷已遭到惡意詐騙的寄件者的管理帳戶從您的網域。 如需詳細資訊，請參閱 <<c0>在 Microsoft 365 安全性中心中的威脅管理。


### <a name="office-365-cloud-app-security-dashboard"></a>Office 365 雲端 App 安全性儀表板

Office 365 雲端 App 安全性，先前稱為 Office 365 進階安全性管理，可讓您建立原則來監視並通知您的 Office 365 訂閱中的可疑活動，讓您進行調查，並採取可能修復動作。 如需詳細資訊，請參閱[概觀的 Office 365 雲端 App 安全性](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview)。

<!--
### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a>後續步驟

請參閱[Configure 增加的 Microsoft 365 安全性](infoprotect-configure-increased-security-office-365.md)步驟中的資訊和連結，以在生產環境中設定這些設定的**資訊保護**階段。

瀏覽額外的[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)功能和測試環境中的功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)

