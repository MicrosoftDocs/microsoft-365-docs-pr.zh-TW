---
title: 提高 Microsoft 365 企業版測試環境的 Microsoft 365 安全性
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此測試實驗室指南可啟用 Microsoft 365 企業版測試環境的其他 Microsoft 365 安全性設定。
ms.openlocfilehash: 53205f0626ce55c5a9627339f3631964e3374a19
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631666"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>提高 Microsoft 365 企業版測試環境的 Microsoft 365 安全性

*這個測試實驗室指南只能用於 Microsoft 365 企業版測試環境。*

透過本文中的指示，您可以設定其他 Microsoft 365 設定，以提升 Microsoft 365 企業版測試環境中的安全性。

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1：建置您的 Microsoft 365 企業版測試環境

如果您只想以輕量的方式設定增加的 Microsoft 365 安全性，請遵循[輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。
  
如果您想要在模擬的企業中設定增加的 Microsoft 365 安全性，請依照[傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試增加的 Microsoft 365 安全性不需要模擬企業測試環境，其中包括連線到網際網路的模擬內部網路和 Active Directory 網域服務（AD DS）樹系的目錄同步處理。 這裡是以選項形式提供，可讓您測試自動授權和群組成員資格，並在代表一般組織的環境中實驗。 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>階段2：設定增加的 Microsoft 365 安全性

在此階段中，您可以為 Microsoft 365 企業版測試環境啟用增強的 Microsoft 365 安全性。 如需詳細資訊和設定，請參閱[Configure a 租使用者以提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>設定線上 SharePoint 封鎖不支援新式驗證的應用程式

不支援新式驗證的應用程式不能有套用身分[識別和裝置存取](microsoft-365-policies-configurations.md)設定，這是保護您的 Microsoft 365 訂閱及其數位資產的重要元素。 

1. 移至 Microsoft 365 系統管理中心（[https://portal.microsoft.com](https://portal.microsoft.com)），並以全域系統管理員帳戶登入您的 microsoft 365 測試實驗室訂閱。
    
  - 如果您使用的是輕量 Microsoft 365 測試環境，請從您的本機電腦登入。
    
  - 如果您使用模擬的企業 Microsoft 365 測試環境，請使用[Azure 入口網站](https://portal.azure.com)連線至 CLIENT1 虛擬機器，然後從 CLIENT1 登入。
 
2. 在 [新增**Microsoft 365 系統管理中心**] 索引標籤的左導覽**窗格中，** 按一下 [ **SharePoint**]。
3. 在 [新增**SharePoint 系統管理中心**] 索引標籤上，按一下 [**原則] > 存取控制**]。
4. 按一下 [**不支援新式驗證的應用程式**]，選取 [**封鎖存取**]，然後按一下 [**儲存**]。


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>為 SharePoint、商務 OneDrive 公司和 Microsoft 團隊啟用高級威脅防護

Office 365 的高級威脅防護（ATP），適用于 SharePoint、OneDrive 和 Microsoft 團隊，可防止您的組織意外共用惡意檔。

1. 移至[安全性 & 合規性中心](https://protection.office.com)，並以全域系統管理員帳戶登入。

2. 在左功能窗格中的 [**威脅管理**] 底下，按一下 [**原則**]，然後按一下 [ **ATP 安全附件**]。 

3. 在 [**保護 SharePoint、OneDrive 和 Microsoft 小組中的**檔案] 底下。 選取 [**開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP**。

4. 按一下 [儲存]****。


### <a name="enable-anti-malware"></a>啟用反惡意程式碼

惡意程式碼是由病毒和間諜軟體組成。 病毒會感染其他程式和資料，同時會擴散到整個電腦，找尋可攻擊的程式。 間諜軟體會收集您的個人資訊 (如登入資訊和個人資料)，並將其傳回給惡意程式碼作者。 

Microsoft 365 具有內建的惡意程式碼和垃圾郵件篩選功能，可協助保護來自惡意軟體的輸入和輸出郵件，並協助您防範垃圾郵件。 如需詳細資訊，請參閱[在 Office 365 中的反垃圾郵件 & 反惡意程式碼保護](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

若要確定在具有共同附件檔案類型的檔案上執行反惡意程式碼處理：

1. 按一下瀏覽器上的 [上一步] 按鈕，以回到 [**原則**] 頁面。
2. 按一下 [**反惡意**代碼]。
3. 按兩下名為**Default**的原則。
4. 在 [**反惡意程式碼原則**] 視窗中，按一下 [**設定**]。
4. 在 [**一般附件類型篩選**] 底下，選取 [**開啟**]，然後按一下 [**儲存**]。


## <a name="phase-3-examine-the-security-dashboard"></a>階段3：檢查安全性儀表板

Office 365 威脅管理可協助您控制和管理行動裝置對組織資料的存取、協助保護組織避免資料遺失，以及協助保護輸入和輸出郵件免受惡意軟體和垃圾郵件的攻擊。 您也可以使用威脅管理來保護您網域的信譽，並判斷寄件者是否從您的網域中有惡意的電子郵件帳戶。 

若要查看安全性儀表板：

1. 如有需要，請移至[安全性 & 合規性中心](https://protection.office.com)，並以全域系統管理員帳戶登入。

2. 在左功能窗格中的 [**威脅管理**] 底下，按一下 [**儀表板**]。

請密切瞭解儀表板上的所有卡片，以熟悉所提供的資訊。

如需詳細資訊，請參閱[安全性儀表板](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)。


## <a name="phase-4-examine-microsoft-secure-score"></a>階段4：檢查 Microsoft 安全分數

Microsoft Secure 得分會將您的安全性狀況顯示為數字，這表示您目前的層次相對於您訂閱中提供的功能。 此外，它還提供您可以採取以提升分數的改進動作清單。

1. 在您的瀏覽器中建立新的索引標籤，然後移至[Microsoft 365 的安全性中心](https://security.microsoft.com/)，然後按一下 [**安全計分**]。
2. 在 [**一覽表**] 索引標籤上，記下目前的安全分數，以及其與全域平均及訂閱數量相似之授權的比較方式。
3. 在 [**改進動作**] 索引標籤上，通讀您可以採取的動作清單，以提升您的分數。

如需詳細資訊，請參閱[Microsoft 安全分數](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。

## <a name="next-steps"></a>後續步驟

請參閱在**資訊保護**階段[設定增強的 Microsoft 365 步驟安全性](infoprotect-configure-increased-security-office-365.md)，以取得在生產環境中設定這些設定的資訊和連結。

在您的測試環境中探索其他[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)功能和功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
