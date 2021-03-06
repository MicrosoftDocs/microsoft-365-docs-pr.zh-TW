---
title: 提高企業測試環境 Microsoft 365 的 Microsoft 365 安全性
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
description: 使用此測試實驗室指南來啟用您 Microsoft 365 企業版測試環境的其他 Microsoft 365 安全性設定。
ms.openlocfilehash: d1bff8b736e5074f621a173d206f7c5f77841b25
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198348"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>提高企業測試環境 Microsoft 365 的 Microsoft 365 安全性

*此測試實驗室指南僅可用於企業測試環境的 Microsoft 365。*

透過本文中的指示，您可以設定其他 Microsoft 365 設定，以提升企業測試環境 Microsoft 365 中的安全性。

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 按一下[這裡](../downloads/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>階段1：組建您的企業測試環境 Microsoft 365

如果您只想要以輕量的方式設定增加的 Microsoft 365 安全性，請依照[輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。
  
如果您想要在模擬的企業中設定增加的 Microsoft 365 安全性，請依照[傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。
  
> [!NOTE]
> 測試增加的 Microsoft 365 安全性不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active directory 網域服務 (AD DS) 樹系的目錄同步處理。 這裡是以選項形式提供，可讓您測試自動授權和群組成員資格，並在代表一般組織的環境中實驗。 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>階段2：設定增加的 Microsoft 365 安全性

在此階段中，您可以為企業測試環境 Microsoft 365 提高 Microsoft 365 的安全性。 如需詳細資訊和設定，請參閱 [Configure a 租使用者以提高安全性](/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>設定線上 SharePoint 封鎖不支援新式驗證的應用程式

不支援新式驗證的應用程式不能有套用身分[識別和裝置存取](../security/office-365-security/microsoft-365-policies-configurations.md)設定，這是保護 Microsoft 365 訂閱及其數位資產的重要元素。 

1. 請移至 Microsoft 365 系統管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com)) 並以全域系統管理員帳戶登入 Microsoft 365 測試實驗室訂閱。
    
  - 如果您使用的是輕量 Microsoft 365 測試環境，請從您的本機電腦登入。
    
  - 如果您使用模擬的企業 Microsoft 365 測試環境，請使用[Azure 入口網站](https://portal.azure.com)連線到 CLIENT1 虛擬機器，然後從 CLIENT1 登入。
 
2. 在 [新 **Microsoft 365 系統管理中心**] 索引標籤的左功能窗格中，按一下 [系統管理 **中心**]，然後按一下 [ **SharePoint**]。
3. 在 [新增 **SharePoint 系統管理中心**] 索引標籤上，按一下 [**原則] > 存取控制**]。
4. 按一下 [ **不支援新式驗證的應用程式**]，選取 [ **封鎖存取**]，然後按一下 [ **儲存**]。


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>針對 SharePoint、商務用 OneDrive 和 Microsoft Teams 啟用 Office 365 的 Defender

用於 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 的 Defender 可保護您的組織不會因疏忽而共用惡意檔案。

1. 移至 [安全性 & 合規性中心](https://protection.office.com) ，並以全域系統管理員帳戶登入。

2. 在左功能窗格中的 [ **威脅管理**] 底下，按一下 [ **原則**]，然後按一下 [ **安全附件**]。 

3. 在 [**保護檔案位於 SharePoint、OneDrive 及 Microsoft Teams**] 底下。 選取 [**開啟 SharePoint]、[OneDrive] 和 [Microsoft Teams**] 的 ATP。

4. 按一下 **[儲存]**。


### <a name="enable-anti-malware"></a>啟用反惡意程式碼

惡意程式碼是由病毒和間諜軟體組成。 病毒會感染其他程式和資料，同時會擴散到整個電腦，找尋可攻擊的程式。 間諜軟體會收集您的個人資訊 (如登入資訊和個人資料)，並將其傳回給惡意程式碼作者。 

Microsoft 365 具有內建的惡意程式碼和垃圾郵件篩選功能，可協助保護來自惡意軟體的輸入和輸出郵件，並協助您防範垃圾郵件。 如需詳細資訊，請參閱 [反垃圾郵件 & 反惡意程式碼保護](../security/office-365-security/anti-spam-and-anti-malware-protection.md)。

若要確定在具有共同附件檔案類型的檔案上執行反惡意程式碼處理：

1. 按一下瀏覽器上的 [上一步] 按鈕，以回到 [ **原則** ] 頁面。
2. 按一下 [ **反惡意** 代碼]。
3. 按兩下名為 **Default** 的原則。
4. 在 [**反惡意程式碼原則**] 視窗中，按一下 [**設定**]。
4. 在 [ **一般附件類型篩選**] 底下，選取 [ **開啟**]，然後按一下 [ **儲存**]。


## <a name="phase-3-examine-the-security-dashboard"></a>階段3：檢查安全性儀表板

Microsoft 365 中的威脅管理可協助您控制和管理對組織資料的行動裝置存取、協助保護組織避免資料遺失，以及協助保護輸入和輸出郵件免受惡意軟體和垃圾郵件的攻擊。 您也可以使用威脅管理來保護您網域的信譽，並判斷寄件者是否從您的網域中有惡意的電子郵件帳戶。 

若要查看安全性儀表板：

1. 如有需要，請移至 [安全性 & 合規性中心](https://protection.office.com) ，並以全域系統管理員帳戶登入。

2. 在左功能窗格中的 [ **威脅管理**] 底下，按一下 [ **儀表板**]。

請密切瞭解儀表板上的所有卡片，以熟悉所提供的資訊。

如需詳細資訊，請參閱 [安全性儀表板](../security/office-365-security/security-dashboard.md)。


## <a name="phase-4-examine-microsoft-secure-score"></a>階段4：檢查 Microsoft 安全分數

Microsoft Secure 得分會將您的安全性狀況顯示為數字，這表示您目前的層次相對於您訂閱中提供的功能。 此外，它還提供您可以採取以提升分數的改進動作清單。

1. 在您的瀏覽器中建立新的索引標籤，然後移至 [Microsoft 365 的安全性中心](https://security.microsoft.com/)，然後按一下 [**安全計分**]。
2. 在 [ **一覽表**  ] 索引標籤上，記下目前的安全分數，以及其與全域平均及訂閱數量相似之授權的比較方式。
3. 在 [ **改進動作** ] 索引標籤上，通讀您可以採取的動作清單，以提升您的分數。

如需詳細資訊，請參閱 [Microsoft 安全分數](../security/defender/microsoft-secure-score.md)。

## <a name="next-steps"></a>後續步驟

在您的測試環境中探索其他 [資訊保護](m365-enterprise-test-lab-guides.md#information-protection) 功能和功能。

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Microsoft 365 企業版文件](/microsoft-365-enterprise/)