---
title: 開始使用 Microsoft 合規性延伸模組
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 準備並部署 Microsoft 合規性延伸模組。
ms.openlocfilehash: 084d8fea1bffb012b4a4685dd28ec93df8e29b19
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730507"
---
# <a name="get-started-with-microsoft-compliance-extension"></a>開始使用 Microsoft 合規性延伸模組

使用這些程序以推出 Microsoft 合規性延伸模組。

## <a name="before-you-begin"></a>開始之前

若要使用 Microsoft 合規性延伸模組，必須將裝置上線至端點 DLP。 如果您是 DLP 或端點 DLP 新使用者，請檢閱這些文章

- [深入了解 Microsoft 合規性延伸模組](dlp-chrome-learn-about.md)
- [深入了解資料外洩防護](dlp-learn-about-dlp.md)
- [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)
- [從範本建立 DLP 原則](create-a-dlp-policy-from-a-template.md)
- [深入了解端點資料外洩防護](endpoint-dlp-learn-about.md)
- [開始使用端點資料外洩防護](endpoint-dlp-getting-started.md)
- [Windows 10 裝置的上線工具及方法](dlp-configure-endpoints.md)
- [為端點 DLP 設定裝置 Proxy 和網際網路連線設定](endpoint-dlp-configure-proxy.md)
- [使用端點資料外洩防護](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a>SKU/訂閱授權

在您開始之前，應先確認您的 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 以及任何附加元件。 若要存取和使用端點 DLP 的功能，您必須擁有下列其中一個訂閱或附加元件。

- Microsoft 365 E5
- Microsoft 365 A5 (教育版)
- Microsoft 365 E5 合規性
- Microsoft 365 A5 合規性
- Microsoft 365 E5 資訊保護和控管
- Microsoft 365 A5 資訊保護和控管

如需授權指南的詳細資料，請參閱：[Microsoft 365 安全性與合規性的授權指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

- 您的組織必須獲得端點 DLP 授權
- 您的裝置必須是可以執行 Windows 10 x64 組建 1809 或更新版本。
- 該裝置必須具有反惡意程式碼用戶端版本為 4.18.2101.9 或更新版本。 開啟 **Windows 安全性** 應用程式，選取 **設定** 圖示，然後選取 **關於**，以查看您目前的版本。


### <a name="permissions"></a>權限

可在 [活動總管](data-classification-activity-explorer.md) 中檢視來自端點 DLP 的資料。 有七個角色可以將權限授與活動總管，您用來存取資料的帳戶必須屬於其中任何一個角色的成員。

- 全域系統管理員
- 合規性系統管理員
- 安全性系統管理員
- 合規性資料系統管理員
- 全域讀取者
- 安全性讀取者
- 報告讀取者

### <a name="overall-installation-workflow"></a>整體安裝工作流程

部署 Microsoft 合規性延伸模組是多重階段的流程。您可以選擇一次安裝一部裝置，或使用 Microsoft 端點管理員或群組原則進行全組織部署。

1. [準備您的裝置](#prepare-your-devices)。
2. [基本設定單一裝置自我主控](#basic-setup-single-machine-selfhost)
3. [使用 Microsoft 端點管理員進行部署](#deploy-using-microsoft-endpoint-manager)
4. [使用群組原則進行部署](#deploy-using-group-policy)
5. [測試擴充功能](#test-the-extension)
6. [使用警示管理儀表板檢視 Chrome DLP 警示](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [檢視活動總管中的 Chrome DLP 資料](#viewing-chrome-dlp-data-in-activity-explorer) 

### <a name="prepare-infrastructure"></a>準備基礎結構

如果您要在所有受監視的 Windows 10 裝置上推出 Microsoft 合規性延伸模組，您應該將 Google Chrome 從不受允許的應用程式和瀏覽器清單中移除。 有關詳細資訊，請參閱 [不受允許的瀏覽器](endpoint-dlp-using.md#unallowed-browsers)。 如果您只將 Chrome 推出至少數裝置，您可以將 Chrome 留在不受允許的瀏覽器和應用程式清單上。 Microsoft 合規性延伸模組會在已安裝模組的電腦上略過兩種清單的限制。  

### <a name="prepare-your-devices"></a>準備您的裝置

1. 使用這些主題中的程序以上線您的裝置：
    1. [開始使用端點資料外洩防護](endpoint-dlp-getting-started.md)
    1. [Windows 10 裝置的上線工具及方法](dlp-configure-endpoints.md)
    1. [為端點 DLP 設定裝置 Proxy 和網際網路連線設定](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a>基本設定單一裝置自我主控

這是建議的方法。 

1. 請登入您要在其上安裝 Microsoft 合規性延伸模組的 Windows 10 電腦，然後以系統管理員的身分執行此 PowerShell 指令碼。 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  瀏覽至 [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco)。

3.  使用 Chrome Web Store 頁面上的指示安裝延伸模組。

### <a name="deploy-using-microsoft-endpoint-manager"></a>使用 Microsoft 端點管理員進行部署

使用此設定方法以進行全組織部署。


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a>透過 Microsoft 端點管理員啟用必要的註冊金鑰

1.  使用下列內容建立 PowerShell 指令碼：

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  登入 [Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com)。

3.  瀏覽至 **裝置** > **指令碼** 並選取 **新增**。

4.  在收到系統提示時，瀏覽至已建立的指令碼位置。

5.  選取下列設定：
    1. 使用登入認證執行此指令碼：是
    1. 強制執行指令碼簽章檢查： 否
    1. 在 64 位元 PowerShell 主機中執行指令碼：是

6.  選取適當的裝置群組並應用原則。

#### <a name="microsoft-endpoint-manager-force-install-steps"></a>Microsoft 端點管理員強制安裝步驟

將 Microsoft 合規性延伸模組新增到強制安裝的延伸模組清單之前，務必要擷取 Chrome ADMX。 Google 會記錄 Microsoft 端點管理員中此程序的步驟：[使用 Microsoft Intune - Google Chrome Enterprise Help 管理 Chrome 瀏覽器](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune)。

 在擷取 ADMX 之後，可以依照下列步驟依序建立此延伸模組的組態設定檔。

1.  登入 Microsoft 端點管理員系統管理中心 (https://endpoint.microsoft.com)。

2.  瀏覽至組態設定檔。

3.  選取 **建立設定檔**。

4.  選取 **Windows 10** 做為平台。

5.  選取 **自訂** 作為設定檔類型。

6.  選取 **設定** 索引標籤。

7.  選取 **新增**。

8.  輸入下列原則資訊。
    
    OMA-URI：`./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`<br/>
    資料類型：`String`<br/>
    值：`<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`

9.  按一下 [建立]。

### <a name="deploy-using-group-policy"></a>使用群組原則部署

如果您不想使用 Microsoft 端點管理員，您可以使用群組原則以在組織中部署 Microsoft 合規性延伸模組

1. 您的裝置必須可透過群組原則管理，而且您必須將所有的 Chrome ADMX 都匯入群組原則集中存放區。 如需詳細資訊，請參閱 [如何在 Windows 中建立和管理群組原則系統管理範本的集中存放區](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store)。

2.  使用此 PowerShell 命令以建立 PowerShell 指令碼：

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  開啟 **群組原則管理主控台** 並瀏覽至您的組織單位 (OU)。

4.  按右鍵並選取 **在此網域中建立 GPO 並於此處建立連結**。 當收到系統提示時，請指派一個描述性名稱至此群組原則物件 (GPO) 然後完成建立。

5.  以滑鼠右鍵按一下 GPO，然後 **編輯**。

6.  請前往 **電腦組態** > **喜好設定** > **控制台設定** > **排程工作**。

7.  選取按右鍵並選擇 **新增** > **立即性工作 (至少 Windows 7)** 以建立新的即時性工作。

8.  為工作命名與描述。

9.  選擇對應的帳戶以執行立即工作，例如 NT 授權

10. 選取 **以最高權限執行**。

11. 設定 Windows 10 原則。

12. 在 **動作** 索引標籤中，選取動作 **啟動程式**。

13. 輸入步驟 1 中建立的程式/指令碼路徑。

14. 選取 **套用**。

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a>將 Chrome 擴充功能新增到 ForceInstall 清單

1.  在群組原則管理編輯器中，瀏覽至您的 OU。

2.  展開下列路徑 **電腦/使用者設定** > **原則** > **系統管理範本** > **傳統系統管理範本** > **Google** > **Google Chrome** > **擴充功能**。 此路徑可能會根據您的設定而不同。

3.  選取 **設定強制安裝擴充功能清單**。

4.  以滑鼠右鍵按一下以滑鼠右鍵按一下，選取 **編輯**。

5.  選取 **已啟用**。

6.  選取 **顯示**。 

7.  在 **值** 下方，新增下列項目：`echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`

8.  選取 **OK** 然後選取 **套用**。

### <a name="test-the-extension"></a>測試擴充功能

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a>上傳到雲端服務，或透過不受允許的 Cloud Egress 存取  

1. 建立或取得敏感性項目，並嘗試將檔案上傳到貴組織的限制服務網域之一。 敏感性資料必須與我們其中一個內建的 [敏感性資訊類型](sensitive-information-type-entity-definitions.md)或貴組織的其中一個敏感性資訊類型相符。 您應該會在您正在測試的裝置上收到來自該裝置的 DLP 快顯通知，其中顯示檔案開啟時不允許此動作。

#### <a name="testing-other-dlp-scenarios-in-chrome"></a>在 Chrome 中測試其他 DLP 案例 

現在，您已將 Chrome 從不受允許的瀏覽器/應用程式清單中移除，您可以測試下列案例以確認此行為符合貴組織的需求：

- 使用 [剪貼簿] 將資料從敏感性項目複製到另一份文件
    - 若要測試，請開啟受到保護且防止在 Chrome 瀏覽器中複製到剪貼簿動作的檔案，並嘗試從檔案複製資料。
    - 預期的結果：DLP 快顯通知顯示出當檔案開啟時此動作是不受允許的。
- 列印文件
    - 若要測試，請開啟受到保護且防止在 Chrome 瀏覽器中列印的檔案，並嘗試從檔案列印資料。
    - 預期的結果：DLP 快顯通知顯示出當檔案開啟時此動作是不受允許的。
- 複製到 USB 卸除式媒體
    - 若要測試，請嘗試將檔案儲存到可移除的媒體儲存空間。
    - 預期的結果：DLP 快顯通知顯示出當檔案開啟時此動作是不受允許的。
- 複製到網路共用
    - 若要測試，請嘗試將檔案儲存到網路共用。
    - 預期的結果：DLP 快顯通知顯示出當檔案開啟時此動作是不受允許的。


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a>使用警示管理儀表板檢視 Chrome DLP 警示

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com) 開啟 **資料外洩防護** 頁面，然後選取 **警示**。

2. 請參閱[如何設定和檢視 DLP 原則的警示](dlp-configure-view-alerts-policies.md)中的程序，以檢視您端點 DLP 原則的警示。


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a>檢視 [活動總管] 中的端點 DLP 資料

1. 在 Microsoft 365 合規性中心開啟您網域的 [資料分類](https://compliance.microsoft.com/dataclassification?viewid=overview) 頁面，然後選擇 **活動總管**。

2. 請參閱 [開始使用活動總管](data-classification-activity-explorer.md) 中的程序，以存取及篩選您端裝置的所有資料。

   > [!div class="mx-imgBorder"]
   > ![端點裝置的活動總管篩選](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

### <a name="known-issues-and-limitations"></a>已知問題與限制

1. 不支援雲端出口的封鎖覆寫強制。
2. 不支援無痕模式且必須停用。

## <a name="next-steps"></a>後續步驟
現在您擁有已上線的裝置，且可以在 [活動總管] 中檢視活動資料，您已準備好開始建立可保護您敏感性項目之 DLP 原則的下一個步驟。

- [使用端點資料外洩防護](endpoint-dlp-using.md)

## <a name="see-also"></a>另請參閱

- [深入了解端點資料外洩防護](endpoint-dlp-learn-about.md)
- [使用端點資料外洩防護](endpoint-dlp-using.md)
- [深入了解資料外洩防護](dlp-learn-about-dlp.md)
- [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)
- [開始使用活動總管](data-classification-activity-explorer.md)
- [適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)
- [Windows 10 電腦上線的工具及方法 ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。
- [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [加入 Azure AD 的裝置](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [下載以 Chromium 為基礎的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)。
