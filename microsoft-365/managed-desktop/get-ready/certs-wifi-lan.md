---
title: 為 Microsoft 受管理的電腦準備認證和網路設定檔
description: 憑證需求和 wi-fi 連線能力
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: a59add6f6821824f189703b3dedd35fda313ec31
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574580"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>為 Microsoft 受管理的電腦準備認證和網路設定檔  
 
憑證型驗證是使用 Microsoft 受管理的電腦之客戶的常見需求。 您可能需要憑證來存取 Wi-Fi 或 LAN，以連線至 VPN 方案，或存取組織中的內部資源。   
 
因為 Microsoft 受管理的電腦裝置會加入 Azure Active Directory (Azure AD) 並由 Microsoft Intune 管理，所以您必須使用簡易憑證註冊通訊協定 (SCEP) 或公開金鑰密碼編譯標準 (與 Intune 整合的憑證基礎結構，部署這類憑證。    
 
## <a name="certificate-requirements"></a>憑證需求 
 
需要有根憑證，才能透過 SCEP 或 PKCS 基礎結構部署憑證。 您組織中的其他應用程式和服務可能需要將根憑證部署至您的 Microsoft 受管理的電腦裝置。    
 
在您將 SCEP 或 PKCS 憑證部署至 Microsoft 受管理的電腦之前，您應該收集組織中需要使用者或裝置憑證的每個服務需求。 若要簡化此活動，您可以使用下列其中一個規劃範本：  
 
- [PKCS 憑證範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP 憑證範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi 連通性需求

若要讓您的商業網路所需的 Wi-Fi 設定自動提供裝置，您可能需要 Wi-Fi 設定檔。 您可以設定 Microsoft 受管理的電腦將這些設定檔部署到裝置。 如果您的網路安全性需要裝置成為本機網域的一部分，您可能也需要評估 Wi-Fi 網路基礎結構，以確保其與 Microsoft 受管理的電腦裝置相容， (Microsoft 受管理的電腦裝置只會以 Azure 方式加入) 。 
 
在您將 Wi-Fi 設定部署至 Microsoft 受管理的電腦裝置之前，您需要收集每個 Wi-Fi 網路的組織需求。 若要讓此活動變得更簡單，您可以使用此 [WiFi 設定檔範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)。
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>有線連線需求和 802.1 x 驗證 
 
如果您使用 802.1 x authentication 來保護從裝置接入局域網 (LAN) ，您必須將必要的設定詳細資料推送至 Microsoft 受管理的電腦裝置。 Microsoft 受管理的電腦執行 Windows 10 的裝置，版本1809或更新版本支援透過 WiredNetwork configuration service provider (CSP) 部署 802.1 x 設定。 如需詳細資訊，請參閱 [WIREDNETWORK CSP](/windows/client-management/mdm/wirednetwork-csp) 檔。 
 
將有線網路設定設定檔部署至 Microsoft 受管理的電腦裝置之前，請先收集您組織的有線公司網路需求。 其步驟如下： 
 
 
1. 登入已設定現有 802.1 x 設定檔的裝置，並連接至局域網網路。  
2. 使用系統管理認證開啟命令提示字元。 
3. 執行 **netsh interface show interface**，以尋找 LAN 介面名稱。 
4. 執行 **netsh LAN 匯出設定檔資料夾，以匯出 LAN 設定檔 XML。 Interface = "interface_name"**。 
5. 如果您需要在 Microsoft 受管理的電腦裝置上測試匯出的設定檔，請執行 **netsh lan add profile filename = "PATH_AND_FILENAME.xml" interface = "INTERFACE_NAME"**。 
 
 
## <a name="deploy-certificate-infrastructure"></a>部署憑證基礎結構  
 
如果您已有使用 Intune 的 SCEP 或 PKCS 基礎結構，且此方法符合您的需求，您也可以將它用於 Microsoft 受管理的電腦。 如果沒有 SCEP 或 PKCS 基礎結構已經存在，您必須準備一個。  
 
如需詳細資訊，請參閱[在 Microsoft Intune 中設定裝置的憑證設定檔](/intune/certificates-configure)。 
 
 
 
## <a name="deploy-a-lan-profile"></a>部署 LAN 設定檔 
 
匯出 LAN 設定檔之後，您可以遵循下列步驟，準備 Microsoft 受管理的電腦的原則：   
 
1. 使用下列設定，在 LAN 設定檔的 Microsoft Intune 中建立自訂設定檔 (請參閱在[Intune) 中使用 Windows 10 裝置的自訂設定](/intune/custom-settings-windows-10)。 在 [**自訂 OMA URI] 設定** 中，選取 [**新增**]，然後輸入下列值： 
    - 名稱： *現代 Workplace-Windows 10 LAN 設定檔* 
    - 描述：輸入提供設定概述的描述，以及任何其他重要的詳細資料。 
    - OMA URI (區分大小寫) ： Enter *。/Device/Vendor/MSFT/WiredNetwork/LanXML*
    - 資料類型： **) 選取字串 (的 XML** 檔案。 
    - 自訂 xml： Upload 匯出的 XML 檔案。
2. 提交支援要求以使用 Microsoft 受管理的電腦系統管理入口網站來 Microsoft 受管理的電腦 IT 作業，以複查及部署「新式工作」裝置–測試」的設定設定檔。 Microsoft 受管理的電腦當您透過管理入口網站中的支援要求完成要求時，IT 作業將會通知您。
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>部署憑證和 Wi-Fi/VPN 設定檔 
 
 
若要部署憑證和設定檔，請遵循下列步驟：

1. 建立每個根和中級憑證的設定檔 (請參閱 [建立信任的憑證設定檔](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)。 每個設定檔都必須有包含到期日為 DD/MM/YYYY 格式的描述。 **不會部署不含到期日的憑證設定檔。**
2. 建立每個 SCEP 或 PKCS 憑證的設定檔 (請參閱 [create a scep certificate profile](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 或 [create a PKCS Certificate Profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) 每個設定檔都必須有一個包含到期日的描述，其格式為 DD/MM/YYYY 格式。 **不會部署不含到期日的憑證設定檔。**
3. 為每個公司 WiFi 網路建立設定檔 (請參閱[Windows 10 和更新的裝置) Wi-Fi 設定](/intune/wi-fi-settings-windows)。
4. 為每個公司 VPN 建立設定檔 (請參閱[Windows 10 和 Windows 全息裝置設定，以使用 Intune) 新增 VPN](/intune/vpn-settings-windows-10)連線。
5. 送出名為 "Certificate deployment" 或 "Wi-Fi 設定檔部署" 的支援要求，以 Microsoft 受管理的電腦使用 Microsoft 受管理的電腦系統管理入口網站的 IT 作業，檢查並部署設定設定檔至「新式工作裝置–測試」。 Microsoft 受管理的電腦當您透過管理入口網站中的支援要求完成要求時，IT 作業將會通知您。 
 
## <a name="steps-to-get-ready"></a>準備就緒的步驟

1. 審查[Microsoft 受管理的電腦的必要條件](prerequisites.md)。
2. 使用 [準備工作評估工具](readiness-assessment-tool.md)。
3. [來賓帳戶的先決條件](guest-accounts.md)
4. [Microsoft 受管理的電腦的網路設定](network.md)
5. [為本文的 Microsoft 受管理的電腦準備憑證和網路設定檔](certs-wifi-lan.md) () 
6. [為 Microsoft 受管理的電腦準備內部部署資源存取](authentication.md)
7. [Microsoft 受管理的電腦中的應用程式](apps.md)
8. [為 Microsoft 受管理的電腦準備對應磁碟機](mapped-drives.md)
9. [為 Microsoft 受管理的電腦準備列印資源](printing.md) 
