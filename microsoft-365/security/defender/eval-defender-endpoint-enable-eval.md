---
title: 啟用 Microsoft Defender for Endpoint 評估，啟用 MDE 的評估
description: 啟用您的 Microsoft 365 Defender 試用實驗室或試驗環境（包括檢查授權狀態）和上架 enpoints
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457798"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a>啟用 Microsoft Defender for Endpoint 評估環境


本文將引導您完成使用生產裝置為 Microsoft Defender for Endpoint 設定評估環境的步驟。 


>[!TIP]
>Microsoft Defender for Endpoint 也隨附產品內評估實驗室，您可以在其中新增預先設定的裝置，並執行模擬以評估平臺的功能。 實驗室附帶簡化的設定體驗，可協助快速示範 Microsoft Defender for Enpdoint 的價值，包含許多功能（例如高級搜尋和威脅分析）的指導方針。 如需詳細資訊，請參閱 [評估功能](/defender-endpoint/evaluation-lab.md)。 <br> 在本文所提供的指導方針與評估實驗室之間的主要差異在於，評估環境使用生產裝置，而評估實驗室使用非生產裝置。 

使用下列步驟來啟用 Microsoft Defender for Endpoint 的評估。

![在 Microsoft Defender 評估環境中啟用 Microsoft Defender for Endpoint 的步驟](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [步驟1。檢查授權狀態](#step-1-check-license-state)
- [步驟2。板載端點](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a>步驟 1. 檢查授權狀態

您必須先檢查授權狀態，以確認已正確布建。 您可以透過系統管理中心或 **Microsoft Azure 入口網站** 進行這項作業。


1. 若要查看您的授權，請移至 **Microsoft Azure 入口網站**，並流覽至「 [Microsoft Azure 入口網站授權」一節](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。

   ![Azure 授權頁面影像](../../media/defender/atp-licensing-azure-portal.png)

1. 或者，在系統管理中心中，流覽至 [**帳單**] [  >  **訂閱**]。

    在螢幕上，您會看到所有已布建的授權及其目前的 **狀態**。

    ![計費授權影像](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>步驟 2. 使用任何支援的管理工具的板載端點

確認已正確布建授權狀態之後，即可啟動上架裝置至服務。 

為了評估 Microsoft Defender for Endpoint，我們建議您選擇執行評估的一些 Windows 10 裝置。 

「 [計畫部署](../defender-endpoint/deployment-strategy.md) 」主題概要說明部署用於端點的 Defender 所需執行的一般步驟。  

觀賞這段影片，快速流覽上架程式，並瞭解可用的工具和方法。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a>上架工具選項

下表根據您在上架所需的端點，列出可用的工具。

端點 | 工具選項
:---|:---
**Windows** | [本機腳本 (最多10個裝置，) ](../defender-endpoint/configure-endpoints-script.md)，[群組原則](../defender-endpoint/configure-endpoints-gp.md)， [Microsoft 端點管理員/行動裝置管理員](../defender-endpoint/configure-endpoints-mdm.md)， [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md)， [VDI 腳本](../defender-endpoint/configure-endpoints-vdi.md)，[與 Azure Defender 整合](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)
**macOS** | [本機腳本](../defender-endpoint/mac-install-manually.md)， [Microsoft 端點管理員](../defender-endpoint/mac-install-with-intune.md)， [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md)，行動[裝置管理](../defender-endpoint/mac-install-with-other-mdm.md)
**Linux 伺服器** | [Local script](../defender-endpoint/linux-install-manually.md)、  [Puppet](../defender-endpoint/linux-install-with-puppet.md)、  [Ansible](../defender-endpoint/linux-install-with-ansible.md)
**iOS** | [以應用程式為基礎](../defender-endpoint/ios-install.md)
**Android** | [Microsoft 端點管理員](../defender-endpoint/android-intune.md)



## <a name="next-step"></a>後續步驟
[設定 Microsoft Defender for Endpoint 的試用版](eval-defender-endpoint-pilot.md)
 
回到概述以 [評估 Microsoft Defender For Endpoint](eval-defender-endpoint-overview.md)

回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述