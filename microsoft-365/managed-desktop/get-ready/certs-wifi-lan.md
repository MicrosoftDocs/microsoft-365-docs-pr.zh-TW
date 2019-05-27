---
title: 準備 Microsoft 受管理的電腦上的憑證和網路設定檔
description: 憑證/wifi/lan
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7c260ce7b3fcb488cb22fb054eeb6ba322fee94b
ms.sourcegitcommit: ef1382ca224a0c108df2633a6550786666691e1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/22/2019
ms.locfileid: "34391264"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>準備 Microsoft 受管理的電腦上的憑證和網路設定檔  
 
使用 Microsoft 受管理電腦的客戶常見需要憑證型驗證。 您可能需要存取 Wi-fi 或 LAN，來連線到 VPN 解決方案，或存取內部資源貴組織中的憑證。   
 
因為 Microsoft 受管理的電腦裝置加入 Azure Active Directory (Azure AD)，並且由 Microsoft Intune 管理，您必須使用簡單憑證註冊通訊協定 (SCEP) 或公用金鑰加密標準 (PKCS) 來部署這類憑證使用 Intune 整合的憑證基礎結構。    
 
## <a name="certificate-requirements"></a>憑證需求 
 
根憑證，才能部署透過 SCEP 或 PKCS 基礎結構的憑證。 其他應用程式與您組織中的服務可能需要部署至您的 Microsoft 受管理的電腦裝置的根憑證。    
 
Microsoft 受管理電腦來部署 SCEP 或 PKCS 憑證之前，您應收集每個服務，則需要在組織中的使用者或裝置憑證的需求。 若要能夠更容易，您可以使用下列其中一個下列規劃範本：  
 
- [PKCS 憑證範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP 憑證範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>目前，只有 SCEP 憑證設定檔支援 Wi-fi 設定檔部署到 Microsoft 受管理的電腦時使用 EAP 類型。 不支援 PKCS 憑證設定檔。 供參考，請參閱[Intune 中的 Windows 10 裝置加入 Wi-fi 設定](https://docs.microsoft.com/intune/wi-fi-settings-windows)。

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-fi 連線能力需求

若要允許的裝置，以自動提供您所需的 Wi-fi 設定企業網路，您可能需要有 Wi-fi 設定設定檔。 您可以設定這些設定檔部署到您的裝置的 Microsoft 受管理電腦。 如果您的網路安全性需要是屬於本機網域的裝置，您可能也需要評估您的 Wi-fi 網路基礎結構，以確定它是與 Microsoft 受管理的電腦裝置 （Microsoft 受管理的電腦裝置是 Azure AD 加入相容僅限）。 
 
Microsoft 受管理的電腦裝置部署的 Wi-fi 設定之前，您需要將來蒐集每個 Wi-fi 網路貴組織的需求。 若要能夠更容易，您可以使用此[WiFi 設定檔範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)。
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>有線連線能力需求和 802.1 x 驗證 
 
如果您使用 802.1 x 安全的區域網路 (LAN) 從裝置存取您必須將必要的組態詳細資料推送到您的 Microsoft 受管理的電腦裝置。 執行 Windows 10，版本 1809年或更新版本的 Microsoft 受管理的電腦裝置支援部署透過 WiredNetwork 設定服務提供者 (CSP) 802.1 x 組態。 如需詳細資訊，請參閱 < <b0>WiredNetwork 雲端解決方案提供者</b0>文件。 
 
Microsoft 受管理的電腦裝置部署有線的網路組態設定檔之前，請收集有線公司網路的貴組織的需求。 其步驟如下： 
 
 
1. 登入具有您現有的 802.1 x 裝置的設定檔設定並連接至 LAN 網路。  
2. 開啟命令提示字元中使用系統管理認證。 
3. 藉由執行**netsh 介面顯示介面**尋找區域網路介面名稱。 
4. 匯出的 LAN 設定檔來執行**netsh lan 匯出設定檔資料夾的 XML =。 介面 ="interface_name 「**。 
5. 如果您需要測試您匯出的設定檔，Microsoft 受管理的電腦裝置上，執行**netsh lan 新增設定檔 filename="PATH_AND_FILENAME.xml 」 介面 ="INTERFACE_NAME 「**。 
 
 
## <a name="deploy-certificate-infrastructure"></a>憑證基礎結構部署  
 
如果您已有現有的 SCEP 或 PKCS 基礎結構與 Intune 這符合您的需求，您也可以使用它的 Microsoft 受管理的電腦。 如果沒有 SCEP 或 PKCS 基礎結構已經存在，您必須準備一。  
 
如需詳細資訊，請參閱[設定您的裝置，在 Microsoft Intune 中的憑證設定檔](https://docs.microsoft.com/intune/certificates-configure)。 
 
 
 
## <a name="deploy-a-lan-profile"></a>部署 LAN 設定檔 
 
一旦已經匯出您的區域網路設定檔，您可以準備 Microsoft 受管理電腦原則遵循下列步驟：   
 
1. Microsoft Intune 中建立自訂的設定檔，使用下列設定值 （請參閱 <<c0>使用自訂設定的 Intune 中的 Windows 10 裝置） 的 LAN 設定檔。 在**自訂 OMA URI 設定**中，選取 [**新增**]，然後輸入下列值： 
    - 名稱：*現代化工作場所 Windows 10 LAN 設定檔* 
    - 描述： 輸入概述的設定，以及任何其他重要詳細資料的描述。 
    - OMA URI （區分大小寫）： 輸入 *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - 資料類型： 選取**字串 （XML 檔案）**。 
    - 自訂的 XML： 上傳匯出的 XML 檔案。
2. 支援要求提交給 Microsoft 受管理的桌上型電腦 IT 作業使用 Microsoft 受管理的桌上型電腦系統管理入口網站中，若要檢閱並部署 「 現代化工作場所裝置 – Test"的組態設定檔。 Microsoft 受管理的桌上型電腦 IT 作業會讓您知道當要求完成透過管理入口網站中的支援要求。
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>部署憑證和 VPN Fi Wi-fi/設定檔 
 
 
若要部署的憑證和設定檔，請遵循下列步驟：

1. 為每個的根憑證和中繼憑證建立設定檔 （請參閱[建立信任的憑證設定檔](https://docs.microsoft.com/intune/certificates-configure#step-3-create-trusted-certificate-profiles)）。 每個這些設定檔必須包含 DD/MM/YYYY 格式中的到期日的描述。 **將不會部署的憑證設定檔沒有到期日期。**
2. 建立每個 SCEP 或 PKCS 憑證的設定檔 （請參閱[建立 SCEP 憑證設定檔](https://docs.microsoft.com/intune/certificates-scep-configure#create-a-scep-certificate-profile)] 或 [[建立 PKCS 憑證設定檔](https://docs.microsoft.com/intune/certficates-pfx-configure#create-a-pkcs-certificate-profile)） 每一個這些設定檔必須包含 DD/MM/YYYY 格式中的到期日的描述。 **將不會部署的憑證設定檔沒有到期日期。**
3. 建立每個公司 WiFi 設定檔 （請參閱[Windows 10 和更新版本的裝置的 Wi-fi 設定](https://docs.microsoft.com/intune/wi-fi-settings-windows)） 的網路。
4. 針對每個公司的 VPN 建立設定檔 （請參閱[Windows 10 和 Windows Holographic 的裝置設定，以新增使用 Intune 的 VPN 連線](https://docs.microsoft.com/intune/vpn-settings-windows-10)）。
5. 提交支援要求標題為 「 憑證部署 」 或 「 Wi-fi 設定檔部署 」 Microsoft 受管理的桌上型電腦 IT 作業使用 Microsoft 受管理的桌上型電腦系統管理入口網站中，若要檢閱並部署 「 現代化工作場所裝置 – 測試的組態設定檔」。 Microsoft 受管理的桌上型電腦 IT 作業會告知您透過支援要求管理入口網站中完成的要求。 
 
 
