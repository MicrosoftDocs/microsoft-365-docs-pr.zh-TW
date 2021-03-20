---
title: 將您的 Office 2010 升級至 Microsoft 365-Microsoft 365 系統管理員
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: 深入瞭解如何將 Microsoft Office 升級為組織中使用者的最新 Office 用戶端。
ms.openlocfilehash: 14be8d63b2acb3e4838640dc399595c0ba3f97f5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913991"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>將您的 Microsoft 365 for business 使用者升級至最新的 Office 用戶端

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 到達支援終止

Office 2010 在10月13日，2020已到達支援的結束。 Microsoft 將無法再提供下列專案：

- 問題的技術支援

- 已探索問題的錯誤修正

- 已探索之弱點的安全性修正程式

如需詳細資訊，請參閱 [Office 2010 終止支援藍圖](/deployoffice/endofsupport/office-2010-end-support-roadmap) 。

 **這個主題是正確的嗎？**
  
 如果您是負責組織中商務用 Microsoft 365 訂閱的系統管理員，您會處在正確的位置。 系統管理員通常負責管理使用者、重設密碼、管理 Office 安裝及新增或移除授權等工作。

 [！附注] 如果您不是系統管理員，且有 [Microsoft 365 系列](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) 產品，請參閱 [如何升級 office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) 以取得有關升級舊版 Office 的資訊。

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>準備升級至 Microsoft 365

做為系統管理員，您可以控制您組織中的 Office 人員可以安裝的版本。 強烈建議您在組織中執行舊版 Office 的使用者，例如 Office 2010、Office 2013 或 Office 2016 升級為最新版本，以利用安全性和生產力增強功能。

## <a name="upgrade-steps"></a>升級步驟

下列步驟會引導您完成將使用者升級至最新 Office 桌面用戶端的程式。 建議您先閱讀這些步驟，再開始升級程式。
  
## <a name="step-1---check-system-requirements"></a>步驟 1-檢查系統需求

[檢查 office 的系統需求](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) ，以確保您的裝置與最新版的 Office 相容。 例如，更新版本的 Office 無法安裝在執行 Windows XP 或 Windows Vista 的電腦上。
  
> [!TIP]
> 如果您的組織中有使用者在其電腦或膝上型電腦上執行舊版 Windows，建議您升級至 Windows 10。 Windows 7 已到達支援終止。 如需詳細資訊，請參閱 [Windows 7 的讀取支援結束于2020年1月](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) 。

請參閱 [Windows 10 系統需求](https://www.microsoft.com/windows/windows-10-specifications) ，查看是否可以升級其作業系統。

### <a name="check-application-compatibility"></a>檢查應用程式相容性

為了確保成功升級，我們建議您識別您的 Office 應用程式--包括 VBA 腳本、宏、協力廠商增益集，以及複雜檔和試算表，並評估其與最新 Office 版本的相容性。
  
例如，如果您目前的 Office 安裝使用協力廠商的增益集，請與製造商聯繫，確定它們與最新版的 Office 相容。
  
## <a name="step-2---check-your-existing-subscription-plan"></a>步驟 2-檢查您現有的訂閱計畫

有些 Microsoft 365 方案不包含 Office 的完整桌上出版本，若您的方案不包含 Office，升級步驟會有所不同。
  
不確定您有哪一種訂閱計畫嗎？ 請參閱 [我有哪些 Microsoft 365 for business 訂閱？](../admin-overview/what-subscription-do-i-have.md)
  
如果您現有的計畫包含 Office，請移至 [步驟 3-卸載 office](#step-3---uninstall-office)。
  
如果您現有的計畫不包含 Office，請從下列選項中選取：
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>不含 Office 之方案的升級選項

 **選項1：切換 Office 訂閱**

切換至包含 Office 的訂閱。 請參閱 [切換至其他 Microsoft 365 for business 方案](../../commerce/subscriptions/switch-to-a-different-plan.md)。

**選項2：購買 Office 的個別購買一次，或透過大量授權購買 Office**

 - 購買 Office 的個別購買一次。 請參閱 [Office 家用 &amp; Business](https://products.office.com/home-and-business) Or [office 專業版](https://products.office.com/professional)

     「或」

 - 透過大量授權，購買 Office 的多個副本。 請參閱， [比較透過大量授權可使用的套件](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)。

## <a name="step-3---uninstall-office"></a>步驟 3-卸載 Office

在安裝最新版的 Office 之前，建議您先卸載所有舊版的 Office。 不過，如果您變更升級 Office 的主意，請注意下列在卸載 Office 之後無法重新安裝 Office 的情況。
  
建議您在使用協力廠商增益集時，請與製造商聯繫，以查看是否有更新可搭配最新版 Office 使用。

> [!TIP]
> 如果您在卸載 Office 時發生問題，您可以使用 Microsoft 支援及修復小幫手工具來協助您移除 Office： [下載並執行 Microsoft 支援與修復助理](https://go.microsoft.com/fwlink/?LinkID=2155008)。

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>選取您要卸載的 Office 版本

- [從電腦](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [從 Mac](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>卸載之後嘗試重新安裝舊版 Office 的已知問題

 **透過大量授權的 Office** 如果您無法再存取這些大量授權版本的 Office，您將無法進行重新安裝。

 **電腦上預先安裝的 Office** 如果您沒有光碟或產品金鑰 (如果 Office 隨附一部) 您將無法重新安裝。

 **不支援的訂閱** 如果您的 Office 副本是透過廢止的訂閱（例如 Office 365 Small Business Premium 或 Office 365 中型企業）取得，除非您擁有訂閱隨附的產品金鑰，否則您將無法安裝舊版的 Office。

如果您想要以最新版本的方式安裝舊版的 Office，您可以在 [相同的電腦上，安裝及使用不同版本的 office](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf)，以查看其中支援這項功能的版本清單。 如果您已安裝與舊版 Office 搭配使用的協力廠商增益集，且尚未確定這些增益集與最新版本相容，則並列安裝可能是您的正確選擇。

## <a name="step-4---assign-office-licenses-to-users"></a>步驟 4-將 Office 授權指派給使用者

若尚未執行此動作，請將授權指派給組織中需要安裝 Office 的任何使用者，請參閱 [在 Microsoft 365 for business 中指派授權給使用者](../manage/assign-licenses-to-users.md)。
  
## <a name="step-5---install-office"></a>步驟 5-安裝 Office

在您確認要升級的使用者擁有授權後，最後一個步驟是讓他們安裝 Office，請參閱 [在您的 PC 或 Mac 上下載並安裝或重新安裝 office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)。
  
> [!TIP]
> 如果您不想讓使用者自行安裝 Office，請參閱 [管理 office 365 中的軟體下載設定](/DeployOffice/manage-software-download-settings-office-365)。 您可以使用 [Office 部署工具](/DeployOffice/overview-office-deployment-tool) ，將 office 軟體下載到您的本機網路，然後使用您一般使用的軟體部署方法來部署 office。