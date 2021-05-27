---
title: 在 Mac 上以 Intune 為基礎之 Microsoft Defender for Endpoint 的部署
description: 使用 Microsoft Intune 在 Mac 上安裝 Microsoft Defender for Endpoint。
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，安裝，部署，卸載，intune，jamf，macos，catalina，mojave，高塞拉里昂
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5aeffdaff39c2f10dfa5164764bff38e99c00010
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684216"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a>在 macOS 上以 Intune 為基礎之 Microsoft Defender for Endpoint 的部署

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [macOS 上適用於端點的 Microsoft Defender](microsoft-defender-endpoint-mac.md)

本主題說明如何透過 Intune 在 macOS 上部署 Microsoft Defender for Endpoint。 成功的部署需要完成下列所有步驟：

1. [下載上架套件](#download-the-onboarding-package)
1. [用戶端裝置設定](#client-device-setup)
1. [核准系統擴充](#approve-system-extensions)
1. [建立系統設定檔](#create-system-configuration-profiles)
1. [發佈應用程式](#publish-application)

## <a name="prerequisites-and-system-requirements"></a>必要條件和系統需求

開始之前，請參閱 [macOS 頁面上的主要 Microsoft Defender For Endpoint](microsoft-defender-endpoint-mac.md) ，以取得目前軟體版本之必要條件和系統需求的描述。

## <a name="overview"></a>概觀

下表摘要說明在 Mac 上透過 Intune 部署及管理 Microsoft Defender for Endpoint 時，所需採取的步驟。 以下是更詳細的步驟。

| 步驟 | 範例檔案名 | BundleIdentifier |
|-|-|-|
| [下載上架套件](#download-the-onboarding-package) | WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml | wdav atp |
| [核准 Microsoft Defender for Endpoint 的系統擴充](#approve-system-extensions) | MDATP_SysExt.xml | 不適用 |
| [核准 Microsoft Defender for Endpoint 的內核擴充](#download-the-onboarding-package) | MDATP_KExt.xml | 不適用 |
| [授與 Microsoft Defender for Endpoint 的完整磁片存取權](#full-disk-access) | MDATP_tcc_Catalina_or_newer.xml | wdav tcc |
| [網路擴充原則](#network-filter) | MDATP_NetExt.xml | 不適用 |
| [設定 Microsoft AutoUpdate (MAU) ](mac-updates.md#intune) | MDATP_Microsoft_AutoUpdate.xml | autoupdate2 |
| [Microsoft Defender for Endpoint 設定設定](mac-preferences.md#intune-profile-1)<br/><br/> **附注：** 如果您打算為 macOS 執行協力廠商 AV，請將設定 `passiveMode` 為 `true` 。 | MDATP_WDAV_and_exclusion_settings_Preferences.xml | wdav |
| [設定 Microsoft Defender for Endpoint 和 MS AutoUpdate (MAU) 通知](mac-updates.md) | MDATP_MDAV_Tray_and_AutoUpdate2。 mobileconfig | autoupdate2 或 wdav （.com） |


## <a name="download-the-onboarding-package"></a>下載上架套件

從 Microsoft Defender 資訊安全中心下載上架套件：

1. 在 Microsoft Defender 資訊安全中心中，移至 **設定**  >  **裝置管理** 上  >  **架**。

2. 將作業系統設定為 **macOS** ，並將部署方法設定為行動 **裝置管理/Microsoft Intune**。

    ![上架設定螢幕擷取畫面](images/atp-mac-install.png)

3. 選取 [ **下載上架] 套件**。 將它儲存成 _WindowsDefenderATPOnboardingPackage.zip_ 相同的目錄。

4. 解壓縮 .zip 檔案的內容：

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    warning:  WindowsDefenderATPOnboardingPackage.zip appears to use backslashes as path separators
      inflating: intune/kext.xml
      inflating: intune/WindowsDefenderATPOnboarding.xml
      inflating: jamf/WindowsDefenderATPOnboarding.plist
    ```

## <a name="create-system-configuration-profiles"></a>建立系統設定檔

下一步是建立 Microsoft Defender for Endpoint 需要的系統設定檔。
在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com/)，開啟 **裝置** 設定  >  **設定檔**。

### <a name="onboarding-blob"></a>上架 blob

此設定檔包含 Microsoft Defender for Endpoint 的授權資訊，但沒有它會報告其未獲授權。

1. 選取 [設定配置 **檔**] 底下的 [**建立設定檔**]。
1. 選取 [**平臺** = **macOS**]，**配置檔案類型** = **範本**。 **範本名稱** =**自訂**。 按一下 ****[建立]。

    > [!div class="mx-imgBorder"]
    > ![自訂設定檔建立](images/mdatp-6-systemconfigurationprofiles-1.png)

1. 選擇設定檔的名稱，例如，"MDATP macOS 上架"。 按 [下一步 **]**。

    > [!div class="mx-imgBorder"]
    > ![自訂設定設定檔名稱](images/mdatp-6-systemconfigurationprofiles-2.png)

1. 為設定設定檔名稱選擇名稱，例如，「MDATP macOS 上架」。
1. 選取您從上述上架套件解壓縮為設定設定檔檔案的 intune/WindowsDefenderATPOnboarding.xml。

    > [!div class="mx-imgBorder"]
    > ![從自訂設定設定檔的檔案中匯入設定](images/mdatp-6-systemconfigurationprofiles.png)

1. 按 [下一步 **]**。
1. 在 [**指派**] 索引標籤上指定裝置。按 **[下一步]**

    > [!div class="mx-imgBorder"]
    > ![自訂設定設定檔-工作分派](images/mdatp-6-systemconfigurationprofiles-2.png)

1. 複習和 **建立**。
1. 開啟 **裝置**  >  **設定檔**，您可以在這裡看到您建立的設定檔。

    > [!div class="mx-imgBorder"]
    > ![自訂設定檔-完成](images/mdatp-6-systemconfigurationprofiles-3.png)

### <a name="approve-system-extensions"></a>核准系統擴充

MacOS 10.15 (Catalina) 或更新版本都需要此設定檔。 舊的 macOS 將會略過此方式。

1. 選取 [設定配置 **檔**] 底下的 [**建立設定檔**]。
1. 選取 [**平臺** = **macOS**]，**配置檔案類型** = **範本**。 **範本名稱** =**分機**。 按一下 ****[建立]。
1. 在 [ **基礎** ] 索引標籤中，提供此新設定檔的名稱。
1. 在 [ **設定設定** ] 索引標籤中，展開 [ **系統擴充** 權] 在 [ **允許的系統擴充** ] 區段中新增下列專案：

    束識別碼         | 小組識別碼
    --------------------------|----------------
    wdav epsext | UBF8T346G9
    wdav netext | UBF8T346G9

    > [!div class="mx-imgBorder"]
    > ![系統擴充設定](images/mac-system-extension-intune2.png)

1. 在 [ **工作分派** ] 索引標籤中，將此設定檔指派給所有 **使用者 & 所有裝置**。
1. 複查和建立此設定設定檔。

### <a name="kernel-extensions"></a>內核擴充

MacOS 10.15 (Catalina) 或更舊版本都需要此設定檔。 它會在較新的 macOS 上忽略。

> [!CAUTION]
> Apple 矽 (M1) 裝置不支援 KEXT。 在這些裝置上安裝包含 KEXT 原則的設定檔將會失敗。

1. 選取 [設定配置 **檔**] 底下的 [**建立設定檔**]。
1. 選取 [**平臺** = **macOS**]，**配置檔案類型** = **範本**。 **範本名稱** =**分機**。 按一下 ****[建立]。
1. 在 [ **基礎** ] 索引標籤中，提供此新設定檔的名稱。
1. 在 [ **設定設定** ] 索引標籤中，展開 [ **核心擴充**]。
1. 將 [ **小組識別碼** ] 設定為 **UBF8T346G9** ，然後按 **[下一步]**。

    > [!div class="mx-imgBorder"]
    > ![內核擴充設定](images/mac-kernel-extension-intune2.png)

1. 在 [ **工作分派** ] 索引標籤中，將此設定檔指派給所有 **使用者 & 所有裝置**。
1. 複查和建立此設定設定檔。

### <a name="full-disk-access"></a>完全磁片存取

   > [!CAUTION]
   > macOS 10.15 (Catalina) 包含新的安全性和隱私權增強功能。 從這個版本開始，依預設，應用程式無法存取磁片 (上的某些位置，例如檔、下載、桌面等 ) 不經明確同意。 在缺少這種同意的情況下，Microsoft Defender for Endpoint 無法完全保護您的裝置。
   >
   > 此設定設定檔會授與 Microsoft Defender for Endpoint 的完整磁片存取權。 如果您先前已透過 Intune 設定 Microsoft Defender for Endpoint，建議您使用此設定檔更新部署。

從 [我們的 GitHub 存放庫](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)下載 [**fulldisk mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) 。

依照上述上 [架 blob](#onboarding-blob)的指示，使用「MDATP 完整磁片存取」做為設定檔名稱，並下載 **fulldisk mobileconfig** 作為設定設定檔名稱。

### <a name="network-filter"></a>網路篩選

在端點偵測和回應功能的一部分中，macOS 的 Microsoft Defender for endpoint 會檢查通訊端流量，並將此資訊報告給 Microsoft Defender 資訊安全中心入口網站。 下列原則允許網路分機執行這項功能。

從 [我們的 GitHub 存放庫](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)下載 [**netfilter mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) 。

依照上述上 [架 blob](#onboarding-blob)的指示，使用「MDATP 網路篩選」做為設定檔名稱，並下載 **netfilter mobileconfig** 作為設定設定檔名稱。

### <a name="notifications"></a>通知

此設定檔是用來允許 Microsoft Defender for Endpoint on macOS 和 Microsoft 自動更新，在 macOS 10.15 (Catalina) 或更新版本的 UI 上顯示通知。

從 [我們的 GitHub 存放庫](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)下載 [**notif mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) 。

依照上述上 [架 blob](#onboarding-blob)的指示，使用「MDATP 網路篩選」做為設定檔名稱，並下載 **notif mobileconfig** 作為設定設定檔名稱。

### <a name="view-status"></a>查看狀態

當 Intune 變更傳播至已註冊的裝置後，您可以在 [**監視**  >  **裝置狀態**] 底下看到它們：

> [!div class="mx-imgBorder"]
> ![監視器中裝置狀態的視圖](images/mdatp-7-devicestatusblade.png)

## <a name="publish-application"></a>發佈應用程式

此步驟可讓您將 Microsoft Defender 用於註冊的電腦。

1. 在 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com/)，開啟 [**應用程式**]。

    > [!div class="mx-imgBorder"]
    > ![準備好建立應用程式](images/mdatp-8-app-before.png)

1. MacOS > 新增，依平臺 > 選取。
1. 選擇 [**應用程式類型**] = **macOS**，按一下 [**選取**]。

    > [!div class="mx-imgBorder"]
    > ![指定應用程式類型](images/mdatp-9-app-type.png)

1. 保留預設值，按 **[下一步]**。

    > [!div class="mx-imgBorder"]
    > ![應用程式屬性](images/mdatp-10-properties.png)

1. 新增工作分派，按 **[下一步]**。

    > [!div class="mx-imgBorder"]
    > ![Intune 指派資訊螢幕擷取畫面](images/mdatp-11-assignments.png)

1. 複習和 **建立**。
1. 您可以  >  **依平臺**  >  **macOS** 來流覽應用程式，以在所有應用程式的清單中查看。

    > [!div class="mx-imgBorder"]
    > ![應用程式清單](images/mdatp-12-applications.png)

 (您可以在 [Intune 部署的 Intune 頁面](/mem/intune/apps/apps-advanced-threat-protection-macos)上找到詳細資訊。 ) 

   > [!CAUTION]
   > 您必須建立所有必要的設定設定檔，並將它們推入所有機器，如上所述。

## <a name="client-device-setup"></a>用戶端裝置設定

除了標準的[公司入口網站安裝](/intune-user-help/enroll-your-device-in-intune-macos-cp)以外，您不需要任何 Mac 裝置的特殊布建功能。

1. 確認裝置管理。

    > [!div class="mx-imgBorder"]
    > ![確認裝置管理螢幕擷取畫面](images/mdatp-3-confirmdevicemgmt.png)

    選取 [ **開啟系統喜好** 設定]，然後在清單中尋找 [ **管理設定檔** ]，然後選取 [ **核准 ...**]。您的管理設定檔會顯示為 **已驗證**：

    ![管理設定檔螢幕擷取畫面](images/mdatp-4-managementprofile.png)

2. 選取 [ **繼續** ] 並完成註冊。

   您現在可以註冊更多裝置。 您也可以在完成提供系統設定和應用程式套件之後，再註冊。

3. 在 Intune 中，開啟 [**管理**  >  **裝置**  >  **所有裝置**]。 您可以在這裡看到所列的裝置：

   > [!div class="mx-imgBorder"]
   > ![新增裝置螢幕擷取畫面](images/mdatp-5-alldevices.png)

## <a name="verify-client-device-state"></a>驗證用戶端裝置狀態

1. 設定設定檔部署至裝置後，開啟 Mac 裝置上的 [**系統偏好** 設定  >  **設定檔**]。

    > [!div class="mx-imgBorder"]
    > ![系統喜好設定螢幕擷取畫面](images/mdatp-13-systempreferences.png)

    ![系統喜好設定設定檔的螢幕擷取畫面](images/mdatp-14-systempreferencesprofiles.png)

2. 確認下列設定設定檔已存在且已安裝。 **管理設定檔** 應為 Intune 系統設定檔。 _Wdav-config_ 和 _Wdav-Kext_ 是在 Intune 中新增的系統設定檔：

    ![設定檔螢幕擷取畫面](images/mdatp-15-managementprofileconfig.png)

3. 您也應該在右上角看到 Microsoft Defender for Endpoint 圖示：

    > [!div class="mx-imgBorder"]
    > ![狀態列中的 Microsoft Defender for Endpoint 圖示螢幕擷取畫面](images/mdatp-icon-bar.png)

## <a name="troubleshooting"></a>疑難排解

問題：未找到授權。

解決方案：遵循上述步驟，使用 WindowsDefenderATPOnboarding.xml 建立裝置設定檔。

## <a name="logging-installation-issues"></a>記錄安裝問題

如需如何在發生錯誤時，尋找由安裝程式所建立之自動產生記錄的詳細資訊，請參閱 [記錄安裝問題](mac-resources.md#logging-installation-issues)。

## <a name="uninstallation"></a>卸載

請參閱 [卸載](mac-resources.md#uninstalling) 以取得如何在 macOS 從用戶端裝置移除 Microsoft Defender for Endpoint 的詳細資料。
