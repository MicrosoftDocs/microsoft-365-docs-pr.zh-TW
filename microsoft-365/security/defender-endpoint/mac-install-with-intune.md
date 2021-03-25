---
title: 適用于 Mac 的 Microsoft Defender ATP 的 Intune 型部署
description: 使用 Microsoft Intune 安裝適用于 Mac 的 Microsoft Defender 端點。
keywords: microsoft，defender，atp，mac，安裝，部署，卸載，intune，jamf，macos，catalina，mojave，高塞拉里昂
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
ms.openlocfilehash: 94cb92974b0e73a1254fd024c39d9a6ee620aad3
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199534"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-for-mac"></a>以 Intune 為基礎的 Microsoft Defender for Mac 部署

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> [!NOTE]
> 本檔說明舊版在 macOS 裝置上部署及設定 Microsoft Defender for Endpoint 的方法。 在 MEM 主控台中現在可以使用原生體驗。 在 MEM 主控台中，原生使用者介面的發行方式，可讓系統管理員設定及部署應用程式，並將其傳送至 macOS 裝置。 <br> <br>
>博客文章 [MEM 可簡化 macOS 的 Microsoft Defender For Endpoint 的部署，以](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) 說明新功能。 若要設定應用程式，請移至 [microsoft InTune 中的 Mac 版端點的設定](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos)。 若要部署應用程式，請移至 [使用 Microsoft Intune 的 macOS 裝置新增 Microsoft Defender For Endpoint](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)。

**適用於：**

- [Mac 版端點的 Microsoft Defender](microsoft-defender-endpoint-mac.md)

本主題說明如何透過 Intune 為 Mac 版端點部署 Microsoft Defender。 成功的部署需要完成下列所有步驟：

1. [下載安裝和上架套件](#download-installation-and-onboarding-packages)
1. [用戶端裝置設定](#client-device-setup)
1. [核准系統擴充](#approve-system-extensions)
1. [建立系統設定檔](#create-system-configuration-profiles)
1. [發佈應用程式](#publish-application)

## <a name="prerequisites-and-system-requirements"></a>必要條件和系統需求

開始之前，請參閱 [《 Microsoft Defender For Mac 的主要端點」頁面](microsoft-defender-endpoint-mac.md) ，以取得目前軟體版本之必要條件和系統需求的描述。

## <a name="overview"></a>概觀

下表摘要說明透過 Intune 部署及管理 Mac 的 Microsoft Defender 端點時，所需採取的步驟。 以下是更詳細的步驟。

| 步驟 | 範例檔案名 | BundleIdentifier |
|-|-|-|
| [下載安裝和上架套件](#download-installation-and-onboarding-packages) | WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml | wdav atp |
| [核准 Microsoft Defender for Endpoint 的系統擴充](#approve-system-extensions) | MDATP_SysExt.xml | 不適用 |
| [核准 Microsoft Defender for Endpoint 的內核擴充](#download-installation-and-onboarding-packages) | MDATP_KExt.xml | 不適用 |
| [授與 Microsoft Defender for Endpoint 的完整磁片存取權](#create-system-configuration-profiles-step-8) | MDATP_tcc_Catalina_or_newer.xml | wdav tcc |
| [網路擴充原則](#create-system-configuration-profiles-step-9) | MDATP_NetExt.xml | 不適用 |
| [設定 Microsoft AutoUpdate (MAU) ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-updates#intune) | MDATP_Microsoft_AutoUpdate.xml | autoupdate2 |
| [Microsoft Defender for Endpoint 設定設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-preferences#intune-profile-1)<br/><br/> **附注：** 如果您打算為 macOS 執行協力廠商 AV，請將設定 `passiveMode` 為 `true` 。 | MDATP_WDAV_and_exclusion_settings_Preferences.xml | wdav |
| [設定 Microsoft Defender for Endpoint 和 MS AutoUpdate (MAU) 通知](#create-system-configuration-profiles-step-10) | MDATP_MDAV_Tray_and_AutoUpdate2。 mobileconfig | autoupdate2 或 wdav （.com） |

## <a name="download-installation-and-onboarding-packages"></a>下載安裝和上架套件

從 Microsoft Defender Security Center 下載安裝和上架套件：

1. 在 Microsoft Defender Security Center 中，移至 [**設定**  >  **裝置管理** 上  >  **架**]。

2. 將作業系統設定為 **macOS** ，並將部署方法設定為行動 **裝置管理/Microsoft Intune**。

    ![上架設定螢幕擷取畫面](images/atp-mac-install.png)

3. 選取 [ **下載安裝套件**]。 將其儲存為 _wdav。 pkg_ 至本機目錄。

4. 選取 [ **下載上架] 套件**。 將它儲存成 _WindowsDefenderATPOnboardingPackage.zip_ 相同的目錄。

5. 從下載 IntuneAppUtil [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos) 。

6. 在命令提示字元中，確認您有三個檔案。
  

    ```bash
    ls -l
    ```

    ```Output
    total 721688
    -rw-r--r--  1 test  staff     269280 Mar 15 11:25 IntuneAppUtil
    -rw-r--r--  1 test  staff      11821 Mar 15 09:23 WindowsDefenderATPOnboardingPackage.zip
    -rw-r--r--  1 test  staff  354531845 Mar 13 08:57 wdav.pkg
    ```
7. 解壓縮 .zip 檔案的內容：

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

8. 讓 IntuneAppUtil 成為可執行檔：

    ```bash
    chmod +x IntuneAppUtil
    ```

9. 從 wdav 建立 wdav 套件 intunemac。 pkg：

    ```bash
    ./IntuneAppUtil -c wdav.pkg -o . -i "com.microsoft.wdav" -n "1.0.0"
    ```
    ```Output
    Microsoft Intune Application Utility for Mac OS X
    Version: 1.0.0.0
    Copyright 2018 Microsoft Corporation

    Creating intunemac file for /Users/test/Downloads/wdav.pkg
    Composing the intunemac file output
    Output written to ./wdav.pkg.intunemac.

    IntuneAppUtil successfully processed "wdav.pkg",
    to deploy refer to the product documentation.
    ```

## <a name="client-device-setup"></a>用戶端裝置設定

在標準 [公司入口網站安裝](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp)以外，您不需要 Mac 裝置的任何特殊布建。

1. 確認裝置管理。

    ![確認裝置管理螢幕擷取畫面](./images/mdatp-3-confirmdevicemgmt.png)

    選取 [ **開啟系統喜好** 設定]，然後在清單中尋找 [ **管理設定檔** ]，然後選取 [ **核准 ...**]。您的管理設定檔會顯示為 **已驗證**：

    ![管理設定檔螢幕擷取畫面](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-4-managementprofile)

2. 選取 [ **繼續** ] 並完成註冊。

   您現在可以註冊更多裝置。 您也可以在完成提供系統設定和應用程式套件之後，再註冊。

3. 在 Intune 中，開啟 [**管理**  >  **裝置**  >  **所有裝置**]。 您可以在這裡看到所列的裝置：

   > [!div class="mx-imgBorder"]
   > ![新增裝置螢幕擷取畫面](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-5-alldevices)

## <a name="approve-system-extensions"></a>核准系統擴充

若要核准系統擴充：

1. 在 Intune 中，開啟 [**管理**  >  **裝置** 設定]。 選取 [**管理**  >  **設定檔**  >  **建立設定檔**]。

2. 選擇設定檔的名稱。 將 **平臺** 改為 MacOS **配置檔案類型 = 分機**。 選取 [建立]。

3. 在 [ **基礎** ] 索引標籤中，提供此新設定檔的名稱。

4. 在 [ **設定設定** ] 索引標籤的 [允許的 **系統擴充** ] 區段中，新增下列專案：

    束識別碼         | 小組識別碼
    --------------------------|----------------
    wdav epsext | UBF8T346G9
    wdav netext | UBF8T346G9

    > [!div class="mx-imgBorder"]
    > ![[基礎] 索引標籤的 [設定設定] 中的副檔名設定螢幕擷取畫面](images/mac-system-extension-intune2.png)

5. 在 [ **工作分派** ] 索引標籤中，將此設定檔指派給所有 **使用者 & 所有裝置**。

6. 複查和建立此設定設定檔。

## <a name="create-system-configuration-profiles"></a>建立系統設定檔

1. 在 Intune 中，開啟 [**管理**  >  **裝置** 設定]。 選取 [**管理**  >  **設定檔**  >  **建立設定檔**]。

2. 選擇設定檔的名稱。 將 **平臺 = macOS** 變更為 **Profile type = Custom**。 選取 [ **設定**]。

3. 開啟設定檔，並上傳 intune/kext.xml。 此檔案是在上述其中一個區段中建立的。

4. 選取 [確定]。

    ![從自訂設定設定檔的檔案中匯入設定](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-6-systemconfigurationprofiles)

5. 選取 [**管理**  >  **指派**]。 在 [ **包含** ] 索引標籤中，選取 [ **指派給所有使用者 & 所有裝置**]。

6. 重複步驟1到5，以取得更多設定檔。

7. 建立另一個設定檔，並提供名稱，並上傳 intune/WindowsDefenderATPOnboarding.xml 檔。

8. 從 [我們的 GitHub 存放庫](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)下載 **fulldisk** ，並將其儲存為 **tcc.xml**。 建立另一個設定檔，並提供任何名稱，並將此檔案上傳至該設定檔。<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a>

   > [!CAUTION]
   > macOS 10.15 (Catalina) 包含新的安全性和隱私權增強功能。 從這個版本開始，依預設，應用程式無法存取磁片 (上的某些位置，例如檔、下載、桌面等 ) 不經明確同意。 在缺少這種同意的情況下，Microsoft Defender for Endpoint 無法完全保護您的裝置。
   >
   > 此設定設定檔會授與 Microsoft Defender for Endpoint 的完整磁片存取權。 如果您先前已透過 Intune 設定 Microsoft Defender for Endpoint，建議您使用此設定檔更新部署。

9. 做為端點偵測和回應功能的一部分，Mac 版端點的 Microsoft Defender 會檢查通訊端流量，並將此資訊報告給 Microsoft Defender Security Center 入口網站。 下列原則允許網路分機執行這項功能。 從 [我們的 GitHub 存放庫](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig)下載 **netfilter** ，將其儲存為 netext.xml，然後使用與上述各節相同的步驟進行部署。 <a name = "create-system-configuration-profiles-step-9" id = "create-system-configuration-profiles-step-9"></a>

10. 若要允許 Microsoft Defender for Mac 和 Microsoft 自動更新在 macOS 10.15 (Catalina) 上的 UI 中顯示通知，請 `notif.mobileconfig` 從 [我們的 GitHub 存放庫](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) 下載並將其匯入為自訂的負載。 <a name = "create-system-configuration-profiles-step-10" id = "create-system-configuration-profiles-step-10"></a>

11. 選取 [ **管理 > 指派**]。  在 [ **包含** ] 索引標籤中，選取 [ **指派給所有使用者 & 所有裝置**]。

當 Intune 變更傳播至已註冊的裝置後，您可以在 [**監視**  >  **裝置狀態**] 底下看到它們：

> [!div class="mx-imgBorder"]
> ![監視器中裝置狀態的視圖](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-7-devicestatusblade.png)

## <a name="publish-application"></a>發佈應用程式

1. 在 Intune 中，開啟 [ **管理 > 用戶端應用程式** ] blade。 選取 [ **app > 新增**]。

2. 選取 **應用程式類型 = 其他/業務線應用程式**。

3. 選取 [檔案] **= wdav pkg**。 請選取 **[確定]** 進行上傳。

4. 選取 [ **設定** 並新增必要的資訊]。

5. 使用 **MacOS 高塞拉里昂 10.14** 做為最小作業系統。

6. 將 [ *忽略應用程式版本* ] 設定為 **[是]**。 其他設定可以是任意值。

    > [!CAUTION]
    > 設定 [ *忽略應用程式版本* ] **不** 會影響應用程式透過 Microsoft AutoUpdate 接收更新的能力。 如需如何更新產品的其他資訊，請參閱 [部署 Microsoft Defender For Mac 的更新](mac-updates.md) 。
    >
    > 如果 Intune 上傳的版本低於裝置上的版本，則會安裝較低的版本，因此會有效地將 Microsoft Defender 用於端點。 這可能會導致非運作的應用程式。 如需如何更新產品的其他資訊，請參閱 [部署 Microsoft Defender For Mac 的更新](mac-updates.md) 。 如果您部署了將「忽略」 *應用程式版本* 設定為 [ **否**] 的 Microsoft Defender 端點，請將它變更為 **[是]**。 若仍無法在用戶端裝置上安裝 Microsoft Defender for Endpoint，請卸載 Microsoft Defender for Endpoint，然後推入更新的原則。
     
    > [!div class="mx-imgBorder"]
    > ![在應用程式新增中顯示應用程式資訊](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-8-intuneappinfo)

7. 選取 **[確定]** 並 **新增**]。

    > [!div class="mx-imgBorder"]
    > ![在 [通知] 視窗中顯示的裝置狀態](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-9-intunepkginfo)

8. 可能需要幾分鐘才能上傳套件。 完成後，請從清單中選取套件，然後移至 [ **工作分派** ] 和 [ **新增群組**]。

    > [!div class="mx-imgBorder"]
    > ![用戶端應用程式快照](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-10-clientapps)

9. 將 **工作分派類型** 變更為 [ **必要**]。

10. 選取 [ **包含的群組**]。 選取 **[讓所有裝置都需要此應用程式] = [是]**。 選取 [ **選取要包含的群組** ]，並新增包含您要作為目標之使用者的群組。 選取 **[確定]** 並 **儲存**。

    > [!div class="mx-imgBorder"]
    > ![Intune 指派資訊螢幕擷取畫面](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-11-assignments)

11. 在一段時間之後，將會將應用程式發佈至所有已註冊的裝置。 您可以  >  在 [**裝置安裝狀態**] 底下看到它所列于監視器 **裝置** 中。

    > [!div class="mx-imgBorder"]
    > ![Intune 裝置狀態螢幕擷取畫面](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-12-deviceinstall)

## <a name="verify-client-device-state"></a>驗證用戶端裝置狀態

1. 設定設定檔部署至裝置後，開啟 Mac 裝置上的 [**系統偏好** 設定  >  **設定檔**]。

    ![系統喜好設定螢幕擷取畫面](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-13-systempreferences)<br/>
    ![系統喜好設定設定檔的螢幕擷取畫面](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-14-systempreferencesprofiles)

2. 確認下列設定設定檔已存在且已安裝。 **管理設定檔** 應為 Intune 系統設定檔。 _Wdav-config_ 和 _Wdav-Kext_ 是在 Intune 中新增的系統設定設定檔： ![ 設定檔螢幕擷取畫面](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-15-managementprofileconfig)

3. 您也應該會在右上角看到 Microsoft Defender 圖示：

    > [!div class="mx-imgBorder"]
    > ![狀態列上的 Microsoft Defender 圖示螢幕擷取畫面](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)

## <a name="troubleshooting"></a>疑難排解

問題：未找到授權

解決方案：遵循上述步驟，使用 WindowsDefenderATPOnboarding.xml 建立裝置設定檔

## <a name="logging-installation-issues"></a>記錄安裝問題

如需如何在發生錯誤時，尋找由安裝程式所建立之自動產生記錄的詳細資訊，請參閱 [記錄安裝問題](mac-resources.md#logging-installation-issues)。

## <a name="uninstallation"></a>卸載

請參閱 [卸載](mac-resources.md#uninstalling) 以取得如何從用戶端裝置移除 Microsoft Defender for Mac 之端點的詳細資料。
