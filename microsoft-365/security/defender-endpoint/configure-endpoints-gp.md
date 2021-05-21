---
title: 透過群組原則從 Microsoft Defender for Endpoint to to Windows 10 板載裝置
description: 使用群組原則在 Windows 10 裝置上部署設定套件，使其可架至服務。
keywords: 使用群組原則、裝置管理、設定 Microsoft Defender for Endpoint 裝置、板載 Microsoft Defender for Endpoint 裝置及群組原則來設定裝置
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 81a3b41fb8e38a224a030571093b2145d2efb3d4
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593426"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>使用群組原則的板載 Windows 10 裝置 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- 群組原則
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> 若要使用群組原則 (GP) 更新若要部署套件，您必須位於 Windows Server 2008 R2 或更新版本。
> 
> 針對 Windows Server 2019，您可能需要將 nt AUTHORITY\Well-Known-System-Account 取代為群組原則喜好設定之 XML 檔案的 nt AUTHORITY\SYSTEM。

## <a name="onboard-devices-using-group-policy"></a>使用群組原則將裝置上線

[![顯示各種部署路徑的 PDF 影像](images/onboard-gp.png)](images/onboard-gp.png#lightbox)

請取出[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)或[Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ，以查看部署 Defender for Endpoint 的各種路徑。 



1. 從服務上架嚮導中，開啟 (*WindowsDefenderATPOnboardingPackage.zip*) 的 GP configuration package .zip file。 您也可以從[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)取得套件：
 
    1. 在功能窗格中，選取 [**設定** 上  >  **架**]。

    1. 選取 [Windows 10] 做為作業系統。
    
    1. 在 [ **部署方法** ] 欄位中，選取 [ **群組原則**]。
    
    1. 按一下 [ **下載套件** ] 並儲存 .zip 檔案。

2. 將 .zip 檔案的內容解壓至共用的唯讀位置，可供裝置存取。 您應該會有一個稱為 *OptionalParamsPolicy* 的資料夾，以及檔案 *WindowsDefenderATPOnboardingScript .cmd*。

3. 開啟「 [群組原則管理主控台](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。

4. 在 [ **群組原則管理編輯器**] 中，移至 [ **電腦** 設定]、[ **喜好** 設定] 及 [控制台 **設定**]。

5. 以滑鼠右鍵按一下 [**排程任務**]，指向 [**新增**]，然後按一下 [**立即工作 (至少 Windows 7)**。

6. 在開啟的 **任務** 視窗中，移至 [**一般**] 索引標籤。在 [**安全性選項**] 底下，按一下 [**變更使用者或群組** 和類型系統]，然後按一下 [**檢查名稱** 然後按一下 **[確定]** NT AUTHORITY\SYSTEM 會顯示為執行工作時所用的使用者帳戶。

7. 選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。

8. 移至 [**動作**] 索引標籤，然後按一下 [**新增 ...** ]確定 [**動作**] 欄位中已選取 [**啟動程式**]。 輸入共用 *WindowsDefenderATPOnboardingScript .cmd* 檔案的檔案名和位置。

9. 按一下 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。

>[!TIP]
> 在裝置上架後，您可以選擇執行偵測測試，以確認裝置已正確架至服務。 如需詳細資訊，請參閱 [在新的架 Defender For Endpoint 裝置上執行偵測測試](run-detection-test.md)。

## <a name="additional-defender-for-endpoint-configuration-settings"></a>其他 Defender for Endpoint configuration 設定
針對每個裝置，您可以使用 Microsoft Defender 資訊安全中心提交檔案進行深入分析時，判斷是否可以從裝置收集範例。

您可以使用「群組原則」 (GP) 設定設定，例如用於 deep analysis 功能的範例共用設定。

### <a name="configure-sample-collection-settings"></a>設定範例集合設定
1.  在您的 GP 管理裝置上，從設定套件複製下列檔案：

    - 將 _AtpConfiguration_ 複製到 _C： \\ Windows \\ PolicyDefinitions_

    - 將 _AtpConfiguration 複製 adml_ into _C： \\ Windows \\ PolicyDefinitions \\ en-US_

    如果您使用的是 [群組原則系統管理範本的中央存放區](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)，請從設定套件複製下列檔案：
    
    - 將 _AtpConfiguration 中的 admx_ 複製到 _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ 原則 \\ PolicyDefinitions_

    - 將 _AtpConfiguration_ 複製到 _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ 原則 \\ PolicyDefinitions \\ en-US_

2.  開啟 [群組原則管理主控台](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)，以滑鼠右鍵按一下您要設定的 GPO，然後按一下 [ **編輯**]。

3.  在 [ **群組原則管理編輯器**] 中，移至 [ **電腦** 設定]。

4.  按一下 [ **原則**]，然後按一下 [系統 **管理範本**]。

5.  按一下 [ **Windows 元件**]，然後 **Windows Defender SmartScreen**]。

6.  選擇啟用或停用裝置的範例共用。

>[!NOTE]
> 如果您未設定值，預設值為啟用範例集合。


## <a name="other-recommended-configuration-settings"></a>其他建議的設定

### <a name="update-endpoint-protection-configuration"></a>更新 endpoint protection 設定

設定上架腳本後，請繼續編輯相同的群組原則，以新增 endpoint protection 設定。 從執行 Windows 10 或伺服器2019的系統執行群組原則編輯，以確保具備所有必要的 Microsoft Defender 防毒軟體功能。 您可能需要關閉並重新開啟群組原則物件，以登錄 Defender ATP 設定設定。

所有原則都位於 `Computer Configuration\Policies\Administrative Templates` 。

**原則位置：** \ Windows 元件 \ Windows Defender SmartScreen *

原則 | 設定 
:---|:---
Enable\Disable 範例集合|   Enabled-「在機器上啟用範例集合」已檢查

<br/>

**原則位置：** \ Windows 元件 \ Microsoft Defender 防毒軟體

原則 | 設定 
:---|:---
設定可能有害之應用程式的偵測 | Enabled、Block

<br/>

**原則位置：** \ Windows 元件 \ Microsoft Defender 防毒軟體 \MAPS

原則 | 設定 
:---|:---
加入 Microsoft MAPS | 已啟用，高級地圖
需要進一步分析時傳送檔範例 | 已啟用，傳送安全範例

<br/>

**原則位置：** \ Windows 元件 \ Microsoft Defender 防毒軟體 \Real-time 保護

原則 | 設定 
:---|:---
關閉即時保護|已停用
開啟行為監控|已啟用
掃描所有已下載的檔案和附件|已啟用
監視電腦上的檔案和程式活動|已啟用

<br/>

**原則位置：** \ Windows Components\Microsoft Defender AntivirusScan

這些設定會設定定期掃描端點。 建議您執行每週的快速掃描（效能允許）。

原則 | 設定 
:---|:---
執行排程掃描之前，請先檢查是否有最新的病毒和間諜軟體安全性情報 |已啟用


<br/>

**原則位置：** \ Windows 元件 \ Microsoft Defender 防毒軟體 \ Microsoft Defender 惡意探索防護 \Attack 表面減少

取得目前攻擊面減少 Guid 的清單，以 [自訂攻擊面降低規則](customize-attack-surface-reduction.md)

1. 開啟 [ **設定攻擊面減少** 原則]。

1. 選取 **已啟用**。

1. 選取 [ **顯示** ] 按鈕。

1. 以值2將每個 GUID 新增至 [ **值名稱** ] 欄位中。

   這只會將每個設定為僅供審核。

   ![攻擊面降低設定的影像](images/asr-guid.png)



原則 | 設定 
:---|:---
設定受控資料夾存取權| 已啟用，稽核模式



## <a name="offboard-devices-using-group-policy"></a>使用群組原則的下架裝置
基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。 傳送給裝置的已到期的脫離套件會遭到拒絕。 下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。

> [!NOTE]
> 上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。

1. 從[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)取得脫離套件：

    1. 在功能窗格中，選取 [**設定**  >  **脫離**]。

    1. 選取 [Windows 10] 做為作業系統。
    
    1. 在 [ **部署方法** ] 欄位中，選取 [ **群組原則**]。

    1. 按一下 [ **下載套件** ] 並儲存 .zip 檔案。

2. 將 .zip 檔案的內容解壓至共用的唯讀位置，可供裝置存取。 您應該有一個名為 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd* 的檔案。

3. 開啟「 [群組原則管理主控台](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) 中，以滑鼠右鍵按一下您要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。

4. 在 [ **群組原則管理編輯器**] 中，移至 [電腦設定] **、** [ **喜好** 設定] 及 [控制台 **設定**]。

5. 以滑鼠右鍵按一下 [ **排程任務**]，指向 [ **新增**]，然後按一下 [ **立即** 工作]。

6. 在開啟的 **任務** 視窗中，移至 [ **一般** ] 索引標籤。在 [ **安全性選項**] 底下，選擇 [ (BUILTIN\SYSTEM]) 的 [本機系統] 使用者帳戶。

7. 選取 [ **執行使用者登入與否** ]，然後選取 [ **以最高特權執行** ] 核取方塊。

8. 移至 [**動作**] 索引標籤，然後按一下 [**新增 ...**]。確定 [**動作**] 欄位中已選取 [**啟動程式**]。 輸入共用  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd* 檔案的檔案名和位置。

9. 按一下 **[確定]** ，然後關閉任何開啟的 GPMC 視窗。

> [!IMPORTANT]
> 脫離會導致裝置停止將感應器資料傳送至入口網站，但是來自裝置的資料（包括對它所做的任何警示參考）將保留最多6個月。


## <a name="monitor-device-configuration"></a>監視裝置設定
使用群組原則時，沒有任何選項可監視裝置上的原則部署。 監控可以直接在入口網站上進行，也可以使用不同的部署工具進行。

## <a name="monitor-devices-using-the-portal"></a>使用入口網站監視裝置
1. 移至[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)。
2. 按一下 [ **裝置清單**]。
3. 驗證裝置是否出現。

> [!NOTE]
> 在 [ **裝置] 清單** 上，裝置開始顯示可能需要幾天。 這包括將原則發佈至裝置所需的時間、使用者登入前所需的時間，以及結束報告端點所需的時間。


## <a name="related-topics"></a>相關主題
- [使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置](configure-endpoints-sccm.md)
- [使用行動裝置管理工具上線 Windows 10 電腦](configure-endpoints-mdm.md)
- [使用本機指令碼上線 Windows 10 裝置](configure-endpoints-script.md)
- [上線非持續 Virtual Desktop Infrastructure (VDI) 裝置](configure-endpoints-vdi.md)
- [在新架 Microsoft Defender for Endpoint 裝置上執行偵測測試](run-detection-test.md)
- [疑難排解 Microsoft Defender 的端點上架問題](troubleshoot-onboarding.md)
