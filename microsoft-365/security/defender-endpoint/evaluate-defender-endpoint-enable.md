---
title: 端點評估的試驗性 Defender
description: 啟用您的 Microsoft 365 Defender 試用實驗室或試驗環境。
keywords: Microsoft 365 Defender 試用版，請嘗試 Microsoft 365 Defender，評估 Microsoft 365 Defender，Microsoft 365 Defender 評估實驗室，Microsoft 365 Defender 試驗，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457841"
---
# <a name="pilot-mde-evaluation"></a>試驗 MDE 評估

>[!NOTE]
>為便於您透過一般部署，此案例只會涵蓋 Microsoft Endpoint Configuration Manager 的使用。 Defender for Endpoint 支援使用其他上架工具，但不涵蓋部署指南中的那些案例。 如需詳細資訊，請參閱 [在 Microsoft Defender For Endpoint 中的板載裝置](onboard-configure.md)。

## <a name="step-1-check-license-state"></a>步驟 1. 檢查授權狀態

檢查授權狀態以及是否已正確布建，可透過系統管理中心或透過 **Microsoft Azure 入口網站** 進行。

1. 若要查看您的授權，請移至 **Microsoft Azure 入口網站**，並流覽至「 [Microsoft Azure 入口網站授權」一節](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。

   ![Azure 授權頁面影像](images/atp-licensing-azure-portal.png)

1. 或者，在系統管理中心中，流覽至 [**帳單**] [  >  **訂閱**]。

    在螢幕上，您會看到所有已布建的授權及其目前的 **狀態**。

    ![計費授權影像](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>步驟 2. 使用任何支援的管理工具的板載端點

「 [計畫部署](deployment-strategy.md) 」主題概要說明部署用於端點的 Defender 所需執行的一般步驟。  

觀賞這段影片，快速流覽上架程式，並瞭解可用的工具和方法。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

在識別您的架構之後，您必須決定要使用的部署方法。 您選擇的部署工具會影響您板載端點到服務的方式。

### <a name="onboarding-tool-options"></a>上架工具選項

下表根據您在上架所需的端點，列出可用的工具。

| 端點     | 工具選項                       |
|--------------|------------------------------------------|
| **Windows**  |  [本機腳本 (最多10個裝置) ](../defender-endpoint/configure-endpoints-script.md) <br> [群組原則](../defender-endpoint/configure-endpoints-gp.md) <br> [Microsoft 端點管理員/行動裝置管理員](../defender-endpoint/configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md) <br> [VDI 腳本](../defender-endpoint/configure-endpoints-vdi.md) <br> [與 Azure Defender 整合](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| **macOS**    | [本機指令碼](../defender-endpoint/mac-install-manually.md) <br> [Microsoft 端點管理員](../defender-endpoint/mac-install-with-intune.md) <br> [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md) <br> [行動裝置管理](../defender-endpoint/mac-install-with-other-mdm.md) |
| **Linux 伺服器** | [本機腳本](../defender-endpoint/linux-install-manually.md) <br> [木偶](../defender-endpoint/linux-install-with-puppet.md) <br> [Ansible](../defender-endpoint/linux-install-with-ansible.md)|
| **iOS**      | [以應用程式為基礎](../defender-endpoint/ios-install.md)                                |
| **Android**  | [Microsoft 端點管理員](../defender-endpoint/android-intune.md)               |
