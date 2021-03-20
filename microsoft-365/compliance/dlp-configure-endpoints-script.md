---
title: 使用本機指令碼上線 Windows 10 裝置
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 使用本機腳本在裝置上部署設定套件，使其可架至服務。
ms.openlocfilehash: 69a8295b170f9186d14862a7247cac3fb4c4ef3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917969"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>使用本機指令碼上線 Windows 10 裝置

適用於：

- [Microsoft 365 端點資料遺失防護 (DLP) ](./endpoint-dlp-learn-about.md)

您也可以將個別裝置手動上架至 Microsoft 365 端點資料遺失防護。 在您認可如何在您的網路中上架所有裝置之前測試服務時，您可能會想要執行此動作。

> [!IMPORTANT]
> 此腳本已優化，最多可用於10個裝置。
>
> 若要以規模部署，請使用 [其他部署選項](dlp-configure-endpoints.md)。 例如，您可以使用群組原則，將上架腳本部署至生產環境中的超過10個裝置，並在其上使用 [Windows 10 裝置](dlp-configure-endpoints-gp.md)中提供的腳本。

## <a name="onboard-devices"></a>板載裝置
 
1.  從 [服務上架] 嚮導中，開啟已下載的 GP configuration 套件 .zip 檔案 (*DeviceComplianceOnboardingPackage.zip*) 。 您也可以從[Microsoft 規範中心](https://compliance.microsoft.com)取得套件

2. 在功能窗格中，選取 [**設定**  >  **裝置上架**]。

3. 在 [ **部署方法** ] 欄位中，選取 [ **本機腳本**]。

4. 按一下 [ **下載套件** ] 並儲存 .zip 檔案。
  
5. 將設定套件的內容解壓至您要板載 (裝置上的位置（例如，桌面) ）。 您應該會有一個名為 *DeviceOnboardingScript* 的檔案。

6.  在裝置上開啟已提升許可權的命令列提示字元，並執行腳本：

7.  轉至 **[開始]** 並鍵入 **「cmd」**。

8.  以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。

![指向以系統管理員身分執行的視窗「開始」功能表](../media/dlp-run-as-admin.png)

9.  輸入指令檔的位置。 如果您已將檔案複製到桌面，請輸入： *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  按 **enter** 鍵或按一下 **[確定]**。

如需如何手動驗證裝置是否符合及正確報告感應器資料的相關資訊，請參閱 [疑難排解 Microsoft Defender Advanced 威脅防護上架問題](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。

## <a name="offboard-devices-using-a-local-script"></a>使用本機腳本的下架裝置
基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。 傳送給裝置的已到期的脫離套件會遭到拒絕。 下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。

> [!NOTE]
> 上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。

1. 從[Microsoft 規範中心](https://compliance.microsoft.com)取得脫離套件

2. 在功能窗格中，選取 [**設定**  >  **裝置脫離**]。

3. 在 [ **部署方法** ] 欄位中，選取 [ **本機腳本**]。

4. 按一下 [ **下載套件** ] 並儲存 .zip 檔案。

5. 將 .zip 檔案的內容解壓縮到可供裝置存取的共用唯讀位置。 您應該有一個名為 *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 的檔案。

6.  在裝置上開啟已提升許可權的命令列提示字元，並執行腳本：

7.  轉至 **[開始]** 並鍵入 **「cmd」**。

8.  以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。

![指向以系統管理員身分執行的視窗「開始」功能表](../media/dlp-run-as-admin.png)

9.  輸入指令檔的位置。 如果您已將檔案複製到桌面，請輸入： *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd*

10.  按 **enter** 鍵或按一下 **[確定]**。

> [!IMPORTANT]
> 脫離會導致裝置停止將感應器資料傳送至入口網站。


## <a name="monitor-device-configuration"></a>監視裝置設定
您可以遵循 [疑難排解上架問題] ( (中的不同驗證步驟， https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 驗證腳本是否順利完成，且代理程式正在執行中。

監視也可以直接在入口網站上進行，或是使用不同的部署工具來執行。

### <a name="monitor-devices-using-the-portal"></a>使用入口網站監視裝置
1. 移至 [Microsoft 365 規範中心](https://compliance.microsoft.com)。

2. 選擇 [**設定**  >  **裝置上架**]  >  **裝置**。

3. 驗證裝置是否出現。


## <a name="related-topics"></a>相關主題
- [使用群組原則的板載 Windows 10 裝置](dlp-configure-endpoints-gp.md)
- [使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置](dlp-configure-endpoints-sccm.md)
- [使用行動裝置管理工具上線 Windows 10 電腦](dlp-configure-endpoints-mdm.md)
- [上線非持續 Virtual Desktop Infrastructure (VDI) 裝置](dlp-configure-endpoints-vdi.md)
- [在新架的 Microsoft Defender ATP 裝置上執行偵測測試](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [疑難排解 Microsoft Defender 高級威脅防護上架問題](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)