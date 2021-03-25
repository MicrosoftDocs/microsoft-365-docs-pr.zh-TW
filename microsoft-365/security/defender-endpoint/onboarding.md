---
title: Microsoft Defender ATP 服務的板載
description: 深入瞭解如何在 Microsoft Defender ATP 服務上架端點
keywords: ''
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
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56645553c43289995012d53d7caf879874e65c8a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186926"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>在 Microsoft Defender for Endpoint service 上架

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

瞭解部署 Microsoft Defender for Endpoint 的各個階段，以及如何設定解決方案內的功能。 

為端點部署 Defender 是三個階段的處理常式：

| [![部署階段-準備](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[階段1：準備](prepare-deployment.md) | [![部署階段-安裝程式](images/phase-diagrams/setup.png)](production-deployment.md)<br>[階段2：設定](production-deployment.md) | ![部署階段-板載](images/phase-diagrams/onboard.png)<br>階段3：板載 |
| ----- | ----- | ----- |
| | |*您在這裡！*|

您目前位於上架階段。

您必須採取下列步驟，才能部署用於端點的 Defender：

- 步驟1：服務的板載端點 
- 步驟2：設定功能 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>步驟1：使用任何支援的管理工具的板載端點
「 [計畫部署](deployment-strategy.md) 」主題概要說明部署用於端點的 Defender 所需執行的一般步驟。  


觀賞這段影片，快速流覽上架程式，並瞭解可用的工具和方法。
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



在識別您的架構之後，您必須決定要使用的部署方法。 您選擇的部署工具會影響您板載端點到服務的方式。 

### <a name="onboarding-tool-options"></a>上架工具選項

下表根據您在上架所需的端點，列出可用的工具。

| 端點     | 工具選項                       |
|--------------|------------------------------------------|
| **Windows**  |  [本機腳本 (最多10個裝置) ](configure-endpoints-script.md) <br>  [群組原則](configure-endpoints-gp.md) <br>  [Microsoft 端點管理員/行動裝置管理員](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 腳本](configure-endpoints-vdi.md)   |
| **macOS**    | [本機腳本](mac-install-manually.md) <br> [Microsoft 端點管理員](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [行動裝置管理](mac-install-with-other-mdm.md) |
| **Linux 伺服器** | [本機腳本](linux-install-manually.md) <br> [木偶](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [以應用程式為基礎](ios-install.md)                                |
| **Android**  | [Microsoft 端點管理員](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>步驟2：設定功能
在上架端點後，您會設定各種功能，例如端點偵測和回應、下一代保護，以及攻擊面降低。 


## <a name="example-deployments"></a>部署範例
在此部署指南中，我們將引導您瞭解如何對板載端點使用兩個部署工具，以及如何設定功能。

範例部署中的工具組括：
- [使用 Microsoft Endpoint Configuration Manager 上架](onboarding-endpoint-configuration-manager.md)
- [使用 Microsoft 端點管理員上架](onboarding-endpoint-manager.md)

您可以使用上述部署工具，在設定下列的 Defender for Endpoint 功能時進行指導：
- 端點偵測和回應設定
- 下一代保護設定
- 攻擊面減少設定

## <a name="related-topics"></a>相關主題
- [使用 Microsoft Endpoint Configuration Manager 上架](onboarding-endpoint-configuration-manager.md)
- [使用 Microsoft 端點管理員上架](onboarding-endpoint-manager.md)
