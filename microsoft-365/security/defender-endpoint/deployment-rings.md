---
title: 在環中部署 Microsoft Defender for Endpoint
description: 瞭解如何在環中為端點部署 Microsoft Defender
keywords: 部署、震鈴、評估、試驗、內幕人士快速、內幕人士緩慢、安裝程式、板載、階段、部署、部署、採用、設定
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5aeaa51e5ab8974c8ca26453534396dac14b5853
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297200"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a>在環中部署 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

您可以使用以環為基礎的部署方法來部署 Microsoft Defender for Endpoint。 

部署週期可用於下列案例：
- [新部署](#new-deployments)
- [現有部署](#existing-deployments)

## <a name="new-deployments"></a>新部署

![部署環的影像](images/deployment-rings.png)


震鈴方法是一種方法，可將一組端點識別成板載，並確認符合特定準則，然後再繼續將服務部署到一組較大的裝置。 您可以為每個震鈴定義結束準則，並在移動至下一環之前確定已完成。

採用以震鈴的部署可協助減少在推出服務時可能發生的潛在問題。 透過試驗特定數目的裝置，您可以識別潛在問題，並減輕可能發生的潛在風險。 


表1提供您可能使用的部署環範例。 

**表1**

|**部署通道**|**描述**|
|:-----|:-----|
Evaluate | Ring 1：識別試驗測試的50系統 
試驗 | Ring 2：在實際執行環境中識別下50-100 端點 <br>  
完整部署 | 震鈴3：以較大的增量向環境中的其他環境推出服務



### <a name="exit-criteria"></a>退出準則
這些震鈴的一組出口準則範例包括：
- 裝置庫存清單中顯示裝置
- 在儀表板中顯示警示
- [執行偵測測試](run-detection-test.md)
- [在裝置上執行模擬的攻擊](attack-simulations.md)

### <a name="evaluate"></a>Evaluate
識別您環境中的少量測試電腦，以在服務上架。 理想情況下，這些機器會少於50端點。 


### <a name="pilot"></a>試驗
Microsoft Defender for Endpoint 支援您可以在服務上架的各種端點。 在此震鈴中，根據您所定義的允出準則，識別多個裝置，並決定繼續進行下一個部署環。

下表顯示支援的端點，以及您可以用於板載裝置裝置至服務的對應工具。 

| 端點     | 部署工具                       |
|--------------|------------------------------------------|
| **Windows**  |  [本機腳本 (最多10個裝置) ](configure-endpoints-script.md) <br> 附注：如果您想要在實際執行環境中部署超過10個裝置，請改用「群組原則」方法或下列所列的其他支援工具。<br>  [群組原則](configure-endpoints-gp.md) <br>  [Microsoft 端點管理員/行動裝置管理員](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 腳本](configure-endpoints-vdi.md)   |
| **macOS**    | [本機腳本](mac-install-manually.md) <br> [Microsoft 端點管理員](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [行動裝置管理](mac-install-with-other-mdm.md) |
| **Linux 伺服器** | [本機腳本](linux-install-manually.md) <br> [木偶](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [以應用程式為基礎](ios-install.md)                                |
| **Android**  | [Microsoft 端點管理員](android-intune.md)               | 




### <a name="full-deployment"></a>完整部署
在此階段中，您可以使用 [計畫部署](deployment-strategy.md) 材料來協助您規劃部署。 


使用下列材料，為最適合您組織的端點架構選取適當的 Microsoft Defender。

|**項目**|**描述**|
|:-----|:-----|
|[![Microsoft Defender for Endpoint 部署策略的縮圖影像](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | 架構材料可協助您規劃下列架構的部署： <ul><li> 雲端-原生 </li><li> 共同管理 </li><li> 內部部署</li><li>評估與本機上架</li>




## <a name="existing-deployments"></a>現有部署

### <a name="windows-endpoints"></a>Windows 端點
在 Windows 和/或 Windows 伺服器上，您可以使用 **安全性更新驗證程式 (SUVP)**，選取要提前測試的幾部機器，以提前 (patch 星期二) 。

如需詳細資訊，請參閱：
- [何謂安全性更新驗證程式](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [軟體更新驗證計畫及 Microsoft 惡意程式碼防護中心 TwC 互動時程表第4部分](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a>非 Windows 端點
使用 macOS 和 Linux，您可以使用一些系統，並在 Beta 通道中執行。

>[!NOTE]
>理想情況下，至少有一個安全性管理員和一個開發人員，這樣您就能在組建之前找到相容性、效能和可靠性問題，使其成為目前的通道。

通道選擇會決定提供給裝置的更新類型及頻率。 Beta 中的裝置是第一個接收更新及新功能的方式，後面接著預覽，最後是「目前」。

![內幕用環的影像](images/insider-rings.png)

為了預覽新功能並提供及早的意見反應，建議您將企業中的部分裝置設定為使用 Beta 或 Preview。

>[!WARNING]
>初次安裝後切換通道需要重新安裝產品。 若要切換產品通道，請執行下列動作：卸載現有的套件、重新設定裝置以使用新通道，然後依照此檔中的步驟，從新位置安裝套件。
