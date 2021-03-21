---
title: 設定舊版郵件加密的 Azure Rights Management
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 先前版本的 Office 365 郵件加密，取決於 Microsoft Azure Rights Management (先前稱為 Windows Azure Active Directory Rights Management) 。
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919489"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>設定舊版郵件加密的 Azure Rights Management

本主題說明您必須遵循的步驟，才能啟動並設定 Azure Rights Management (RMS) （Azure 資訊保護的一部分），以用於舊版 Office 365 郵件加密 (OME) 。

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>本文僅適用于舊版的 OME

如果您尚未將組織移至新的 OME 功能，但您已部署 OME，則本文中的資訊適用于您的組織。 Microsoft 建議您在組織合理的情況時，安排移至新的 OME 功能。 如需相關指示，請參閱 [Set up New Office 365 Message Encryption 功能](set-up-new-message-encryption-capabilities.md)。 如果您想要進一步瞭解新功能的運作方式，請參閱 [Office 365 Message Encryption](ome.md)。 本文的其餘部分是在發行新的 OME 功能之前，OME 行為。

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>使用舊版 Office 365 郵件加密的必要條件
<a name="warmprereqs"> </a>

Office 365 郵件加密 (OME) （包括 IRM）取決於 Azure Rights Management (Azure RMS) 。 Azure RMS 是 Azure 資訊保護所使用的保護技術。 若要使用 OME，您的組織必須包含 Exchange Online 或 Exchange Online Protection 訂閱，進而包含 Azure Rights Management 訂閱。
  
- 若不確定您的訂閱所包含的內容，請參閱 [訊息原則、復原和合規性](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)的 Exchange Online 服務說明。

- 如果您有 Azure Rights Management，但未設定 Exchange Online 或 Exchange Online Protection，本文將說明如何啟用 Azure 版權管理，然後描述設定 OME 以搭配 Azure Rights Management 的最佳方式。

- 如果您已設定 OME 以使用 Azure Rights Management for Exchange Online 或 Exchange Online Protection （取決於其設定方式），您可能會立即開始使用 OME 及其新功能。 本文說明如何判斷您是否已正確設定 OME、需要變更設定的方式，以及如果您選擇不要變更設定，會發生什麼事。 例如，若要使用新功能，您必須搭配使用 Azure RMS 與 OME。 您無法搭配內部部署 Active Directory RMS 使用新功能。

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>在 Office 365 中啟動舊版 OME 的 Azure 版權管理

您必須啟用 Azure Rights Management，讓組織中的使用者能夠對傳送的郵件套用資訊保護，並開啟已由 Azure Rights Management 服務保護的郵件和檔案。 如需相關指示，請參閱 [啟用 Azure Rights Management](/azure/information-protection/activate-service)。 當您完成啟用之後，請回到這裡，繼續執行本文中的工作。
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>透過匯入信任的發行網域 (Tpd，將舊版的 OME 設定為使用 Azure RMS) 

TPD 是一種 XML 檔案，其中包含組織的版權管理設定資訊。 例如，TPD 包含伺服器許可方憑證的相關資訊， (SLC) 用於簽署和加密憑證和授權、用於授權和發行的 URLs 等。 您可以使用 Windows PowerShell 將 TPD 匯入您的組織。
  
> [!IMPORTANT]
> 先前，您可以選擇從 Active Directory Rights Management service 將 Tpd 匯入到您的組織中 (AD RMS) 。 不過，這樣做會使您無法使用新的 OME 功能，因此建議您不要這樣做。 如果您的組織目前是以這種方式設定，Microsoft 建議您建立從您的內部部署 Active Directory RMS 遷移至雲端式 Azure 資訊保護的計畫。 如需詳細資訊，請參閱 [從 AD RMS 遷移至 Azure 資訊保護](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。 您必須完成遷移至 Azure 資訊保護後，才能使用新的 OME 功能。
  
 **從 Azure RMS 匯入 Tpd**
  
1. [使用遠端 PowerShell 連接至 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 選擇對應于您組織之地理位置的金鑰共用 URL：

|**位置**|**主要共用位置 URL**|
|:-----|:-----|
|北美  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|歐盟  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|亞洲  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|南美洲  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 for Government (政府社群雲端)  <br/> 此 RMS 金鑰共用位置是針對政府 SKUs 購買 Office 365 的客戶所保留。  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. 執行 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) Cmdlet 以設定金鑰共用位置，如下所示： 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   例如，若您的組織位於北美，若要設定金鑰共用位置：

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. 使用-RMSOnline 參數執行 [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) Cmdlet，以從 Azure Rights Management 匯入 TPD： 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   其中  *TPDName*  是您要用於 TPD 的名稱。 例如，"Contoso 北美 TPD"。 

5. 若要確認您是否已成功將組織設定為使用 Azure Rights Management 服務，請使用-RMSOnline 參數執行 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) Cmdlet，如下所示：

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   此外，此 Cmdlet 還會檢查 Azure 版權管理服務的連線能力、下載 TPD，以及檢查其有效性。

6. 依下列方式執行 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) Cmdlet，以停用 outlook 網頁版和 Outlook 版中的 Azure 版權管理範本： 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. 依下列方式執行 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) Cmdlet，以為您的雲端式電子郵件組織啟用 Azure rights management，並將其設定為使用 Azure rights Management for Office 365 郵件加密：

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. 若要確認您是否已成功匯入 TPD 及 enabled Azure Rights Management，請使用 Test-IRMConfiguration Cmdlet 來測試 Azure 版權管理功能。 如需詳細資訊，請參閱 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration)中的「範例1」。

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>我已將舊版的 OME 設定為使用 Active Directory Rights Management，但不是 Azure 資訊保護，我該怎麼做？
<a name="importTPDs"> </a>

您可以繼續使用現有的 Office 365 郵件加密郵件流程規則與 Active Directory Rights Management，但您無法設定或使用新的 OME 功能。 相反地，您必須遷移到 Azure 資訊保護。 如需有關遷移的詳細資訊及其對您組織的意義，請參閱 [從 AD RMS 遷移到 Azure 資訊保護](/information-protection/deploy-use/prepare-environment-adrms)。
  
## <a name="next-steps"></a>後續步驟
<a name="importTPDs"> </a>

當您完成 Azure Rights Management 安裝程式之後，如果您想要啟用新的 OME 功能，請參閱[設定新的 Office 365 郵件加密功能（以 Azure 資訊保護為](./set-up-new-message-encryption-capabilities.md)基礎）。
  
在您設定組織使用新的 OME 功能之後，您就可以 [定義郵件流程規則，以使用新的 OME 功能來保護電子郵件](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="related-topics"></a>相關主題
<a name="importTPDs"> </a>

[Office 365 中的加密](encryption.md)
  
[關於 Office 365 中加密的技術參考細節](technical-reference-details-about-encryption.md)
  
[什麼是 Azure 版權管理？](/information-protection/understand-explore/what-is-azure-rms)