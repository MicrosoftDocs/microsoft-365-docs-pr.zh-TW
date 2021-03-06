---
title: 使用本機指令碼上線 Windows 10 裝置
description: 使用本機腳本在裝置上部署設定套件，以啟用裝置的上架至服務。
keywords: 使用本機腳本、裝置管理、設定 Microsoft Defender for Endpoint 裝置設定裝置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e15a02753c7a1b346021a4351af24b8fd28315da
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339643"
---
# <a name="onboard-the-windows-10-devices-using-a-local-script"></a>使用本機腳本的 Windows 10 裝置上架

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

您也可以將個別裝置手動上架到 Defender for Endpoint。 在您認可如何在您的網路中上架所有裝置之前測試服務時，您可能會想要執行此動作。

> [!IMPORTANT]
> 此腳本已優化，最多可用於10個裝置。
>
> 若要以規模部署，請使用 [其他部署選項](configure-endpoints.md)。 例如，您可以使用群組原則，將上架腳本部署至生產環境中的超過10個裝置，並使該腳本可用於[板載 Windows 10 裝置](configure-endpoints-gp.md)。

## <a name="onboard-devices"></a>將裝置上線 

[![顯示各種部署路徑的 PDF 影像](images/onboard-script.png)](images/onboard-script.png#lightbox)


請取出[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)或[Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ，以查看部署 Defender for Endpoint 的各種路徑。 


1.  從服務上架嚮導中，開啟 (*WindowsDefenderATPOnboardingPackage.zip*) 的 GP configuration package .zip file。 您也可以從[Microsoft 365 Defender 入口網站](https://security.microsoft.com/)取得此套件：

    1. 在功能窗格中，選取 [**設定**  >  **端點**  >  **裝置管理** 上  >  **架**]。

    1. 選取 [Windows 10] 做為作業系統。

    1. 在 [ **部署方法** ] 欄位中，選取 [ **本機腳本**]。

    1. 按一下 [ **下載套件** ] 並儲存 .zip 檔案。

  
2.  將設定套件的內容解壓至您要板載 (裝置上的位置（例如，桌面) ）。 您應該會有一個名為 *WindowsDefenderATPLocalOnboardingScript* 的檔案。

3.  在裝置上開啟已提升許可權的命令列提示字元，並執行腳本：

    1.  轉至 **[開始]** 並鍵入 **「cmd」**。

    1.  以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。

        ![[開始] 功能表指向以系統管理員身分執行的視窗](images/run-as-admin.png)

4.  輸入指令檔的位置。 如果您已將檔案複製到桌面，請輸入： *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*

5.  按 **enter** 鍵或按一下 **[確定]**。

如需如何手動驗證裝置是否符合及正確報告感應器資料的相關資訊，請參閱 [疑難排解 Microsoft Defender For Endpoint 上架問題](troubleshoot-onboarding.md)。


>[!TIP]
> 在裝置上架後，您可以選擇執行偵測測試，以確認裝置已正確架至服務。 如需詳細資訊，請參閱 [在新架的 Microsoft Defender For endpoint 端點上執行偵測測試](run-detection-test.md)。

## <a name="configure-sample-collection-settings"></a>設定範例集合設定
針對每個裝置，您可以設定設定值，以指出是否可以在要求透過 Microsoft 365 Defender 提交檔案進行深層分析時，從裝置收集範例。

您可以使用 *regedit* 來手動設定裝置的範例共用設定，或建立及執行 *.reg* 檔案。  

設定是透過下列登錄機碼專案設定的：

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
其中：<br>
名稱類型為 D-字。 <br>
可能的值為：
- 0-不允許從此裝置共用範例
- 1-允許共用此裝置的所有檔案類型

當登錄機碼不存在時的預設值為1。


## <a name="offboard-devices-using-a-local-script"></a>使用本機腳本的下架裝置
基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。 傳送給裝置的已到期的脫離套件會遭到拒絕。 下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。

> [!NOTE]
> 上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。

1. 從[Microsoft 365 Defender 入口網站](https://security.microsoft.com/)取得脫離套件：

    1. 在功能窗格中，選取 [**設定**  >  **端點**  >  **裝置管理**  > **脫離**]。

    1. 選取 [Windows 10] 做為作業系統。

    1. 在 [ **部署方法** ] 欄位中，選取 [ **本機腳本**]。

    1. 按一下 [ **下載套件** ] 並儲存 .zip 檔案。

2. 將 .zip 檔案的內容解壓至共用的唯讀位置，可供裝置存取。 您應該有一個名為 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd* 的檔案。

3.  在裝置上開啟已提升許可權的命令列提示字元，並執行腳本：

    1.  轉至 **[開始]** 並鍵入 **「cmd」**。

    1.  以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。

        ![[開始] 功能表指向以系統管理員身分執行的視窗](images/run-as-admin.png)

4.  輸入指令檔的位置。 如果您已將檔案複製到桌面，請輸入： *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd*

5.  按 **enter** 鍵或按一下 **[確定]**。

> [!IMPORTANT]
> 脫離會導致裝置停止將感應器資料傳送至入口網站，但是來自裝置的資料（包括對它所做的任何警示參考）將保留最多6個月。


## <a name="monitor-device-configuration"></a>監視裝置設定
您可以遵循上 [架問題疑難排解](troubleshoot-onboarding.md) 中的不同驗證步驟，確認腳本已成功完成且代理程式正在執行。

監視也可以直接在入口網站上進行，或是使用不同的部署工具來執行。

### <a name="monitor-devices-using-the-portal"></a>使用入口網站監視裝置
1. 移至 Microsoft 365 Defender 入口網站。

2. 按一下 [ **設備清查**]。

3. 驗證裝置是否出現。


## <a name="related-topics"></a>相關主題
- [使用群組原則的板載 Windows 10 裝置](configure-endpoints-gp.md)
- [使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置](configure-endpoints-sccm.md)
- [使用行動裝置管理工具上線 Windows 10 電腦](configure-endpoints-mdm.md)
- [上線非持續 Virtual Desktop Infrastructure (VDI) 裝置](configure-endpoints-vdi.md)
- [在新架的 Microsoft Defender for Endpoint 裝置上執行偵測測試](run-detection-test.md)
- [疑難排解 Microsoft Defender 的端點上架問題](troubleshoot-onboarding.md)
