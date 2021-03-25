---
title: 規劃用於端點部署的 Microsoft Defender
description: 為您的環境選取最佳的 Microsoft Defender for Endpoint 部署策略
keywords: 部署、規劃、部署策略、雲端原生、管理、部署、評估、上架、本機、群組原則、gp、端點管理員、mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163572"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a>規劃用於端點部署的 Microsoft Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


規劃 Microsoft Defender for Endpoint deployment，使您可以最大化套件中的安全性功能，並更好地保護您的企業免受網路威脅。


此方案提供有關如何識別環境架構的指導方針、選取最符合您需求的部署工具類型，以及如何設定功能的指導方針。


![部署流程的映射](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a>步驟1：識別架構
我們知道每個企業環境都是唯一的，因此我們提供了數個選項，讓您在選擇部署服務的方式上具有彈性。

根據您的環境而定，有些工具更適合特定架構。 

使用下列材料，選取最適合您組織的端點架構的適當 Defender。

| 項目 | 描述 |
|:-----|:-----|
|[![適用于 Defender 的 Endpoint 部署策略的縮圖影像](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | 架構材料可協助您規劃下列架構的部署： <ul><li> 雲端-原生 </li><li> 共同管理 </li><li> 內部部署</li><li>評估與本機上架</li>



## <a name="step-2-select-deployment-method"></a>步驟2：選取部署方法
Defender for Endpoint 支援您可以在服務上架的各種端點。 

下表列出支援的端點和對應的部署工具，您可以使用這些端點和對應的部署工具，以適當地規劃部署。

| 端點     | 部署工具                       |
|--------------|------------------------------------------|
| **Windows**  |  [本機腳本 (最多10個裝置) ](configure-endpoints-script.md) <br>  [群組原則](configure-endpoints-gp.md) <br>  [Microsoft 端點管理員/行動裝置管理員](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 腳本](configure-endpoints-vdi.md)   |
| **macOS**    | [本機腳本](mac-install-manually.md) <br> [Microsoft 端點管理員](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [行動裝置管理](mac-install-with-other-mdm.md) |
| **Linux 伺服器** | [本機腳本](linux-install-manually.md) <br> [木偶](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [以應用程式為基礎](ios-install.md)                                |
| **Android**  | [Microsoft 端點管理員](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a>步驟3：設定功能
在上架端點之後，在 Defender for Endpoint 中設定安全性功能，讓您可以最大化套件中可用的穩健安全性保護。 功能包括：

- 端點偵測及回應
- 下一代保護
- 受攻擊面縮小


  
## <a name="related-topics"></a>相關主題
- [部署階段](deployment-phases.md)
