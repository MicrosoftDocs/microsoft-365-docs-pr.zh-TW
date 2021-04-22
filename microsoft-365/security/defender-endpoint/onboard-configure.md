---
title: 適用于 Microsoft Defender for Endpoint service 的板載裝置
description: 板載 Windows 10 裝置、伺服器、非 Windows 裝置，並瞭解如何執行偵測測試。
keywords: 上架，Microsoft Defender for Endpoint 上架，sccm，群組原則，mdm，local script，偵測測試
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 05cc5770df5bb05687bb8be69ad89a7abd6875ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933550"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>適用于 Microsoft Defender for Endpoint service 的板載裝置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

您必須前往端點入口網站的上架區段，以上架任何支援的裝置。 視裝置而定，您將會以適當的步驟進行指導，並提供適用于裝置的管理和部署工具選項。 

一般而言，對服務的板載裝置：

- 確認裝置滿足 [最低需求](minimum-requirements.md)
- 視裝置而定，請遵循用於端點入口網站之 Defender 的上架區段中所提供的設定步驟
- 針對您的裝置使用適當的管理工具和部署方法
- 執行偵測測試以驗證裝置是否已正確架及報告給服務

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>上架工具選項
下表根據您在上架所需的端點，列出可用的工具。

| 端點     | 工具選項                       |
|--------------|------------------------------------------|
| **Windows**  |  [本機腳本 (最多10個裝置) ](configure-endpoints-script.md) <br>  [群組原則](configure-endpoints-gp.md) <br>  [Microsoft 端點管理員/行動裝置管理員](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 腳本](configure-endpoints-vdi.md)   |
| **macOS**    | [本機腳本](mac-install-manually.md) <br> [Microsoft 端點管理員](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [行動裝置管理](mac-install-with-other-mdm.md) |
| **Linux 伺服器** | [本機腳本](linux-install-manually.md) <br> [木偶](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [以應用程式為基礎](ios-install.md)                                |
| **Android**  | [Microsoft 端點管理員](android-intune.md)               | 




## <a name="in-this-section"></a>本節內容
主題 | 描述
:---|:---
[將上一版 Windows 上線](onboard-downlevel.md)| 板載 Windows 7 和 Windows 8.1 裝置到 Defender for Endpoint。 
[將 Windows 10 裝置上線](configure-endpoints.md) | 您需要有板載裝置，才能向其報告「Defender for Endpoint service」。 深入瞭解您可以用來設定企業中裝置的工具和方法。
[上架伺服器](configure-server-endpoints.md) |  板載 Windows Server 2008 R2 SP1，Windows Server 2012 R2，Windows Server 2016，Windows Server (SAC) 版本1803和更新版本、Windows Server 2019 和更新版本，以及 Windows Server 2019 core edition to Defender for Endpoint。
[將非 Windows 裝置上線](configure-endpoints-non-windows.md) | Defender for Endpoint 提供 Windows 和非 Windows 平臺的集中式安全性作業體驗。 您可以在 Microsoft Defender Security Center 中查看不同支援作業系統 (OS) 中的警示，並更好地保護組織的網路。 這種經驗利用於協力廠商的安全性產品的感應器資料。 
[在新上線的裝置上執行偵測測試](run-detection-test.md) | 在新的架裝置上執行腳本，以驗證它是否已正確報告至端點服務的 Defender。
[設定 proxy 和網際網路設定](configure-proxy-internet.md)| 設定 proxy 和網際網路連線設定，以啟用與 Defender for Endpoint cloud service 的通訊。
[為上線問題疑難排解](troubleshoot-onboarding.md) | 深入瞭解如何解決上架期間可能發生的問題。

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
