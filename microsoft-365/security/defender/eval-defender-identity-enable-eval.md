---
title: 為 Microsoft Defender 身分識別啟用評估環境、設定 MDI 實例、安裝及設定 MDI 感應器，讓 MDI 感應器偵測到本機系統管理員
description: 安裝 & 設定感應器，並在其他電腦上探索本機管理員，以在 Microsoft 365 Defender 試用實驗室或試驗環境中設定 Microsoft Defender 身分識別。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457780"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>啟用 Microsoft Defender 身分識別的評估環境

**適用於：**
- Microsoft 365 Defender

本文是設定 Microsoft Defender 身分識別的評估環境過程中， [步驟2之 2](eval-defender-identity-overview.md) 。 如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-identity-overview.md)。

使用下列步驟來設定您的 Microsoft Defender 以供身分識別環境使用。 

![在 Microsoft Defender 評估環境中啟用 Microsoft Defender 身分識別的步驟](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [步驟1。設定用於身分識別實例的 Defender](#step-1-set-up-the-defender-for-identity-instance)
- [步驟2。安裝及設定感應器](#step-2-install-and-configure-the-sensor)
- [步驟3。在具有感應器的電腦上設定事件記錄及 proxy 設定](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [步驟4。允許 Defender for Identity 識別其他電腦上的本機系統管理員](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>步驟 1. 設定用於身分識別實例的 Defender

登入用於身分識別入口網站的 Defender，以建立您的實例，然後將此實例連線到您的 Active Directory 環境。 

|  |步驟     |其他相關資訊  |
|---------|---------|---------|
|1      | 建立身分識別實例的 Defender        | [快速入門：建立您的 Microsoft Defender for Identity 實例](/defender-for-identity/install-step1)        |
|2      | 在 Active Directory 樹系中連線身分識別實例的 Defender   | [快速入門：連線至您的 Active Directory 樹系](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a>步驟 2. 安裝及設定感應器

接下來，在內部部署環境中的網域控制站和 AD FS 伺服器上，下載、安裝和設定適用于身分識別感應器的 Defender。

|  |步驟     |其他相關資訊  |
|---------|---------|---------|
|1      | 決定您需要的身分識別感應器的 Microsoft Defender 數目。        | [規劃 Microsoft Defender 身分識別的容量](/defender-for-identity/capacity-planning)   |
|2      | 下載感應器安裝套件  |  [快速入門：下載適用于身分識別感應器安裝套件的 Microsoft Defender](/defender-for-identity/install-step3)   |
|3      | 安裝適用于身分識別感應器的 Defender    |  [快速入門：安裝 Microsoft Defender for Identity 感應器](/defender-for-identity/install-step4)       |
|4      | 設定感應器       |  [設定 Microsoft Defender 的身分識別感應器設定 ](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>步驟 3. 在具有感應器的電腦上設定事件記錄及 proxy 設定

在您安裝感應器的機器上，設定 Windows 事件記錄檔集合及網際網路 proxy 設定，以啟用及增強偵測功能。

|  |步驟     |其他相關資訊  |
|---------|---------|---------|
|1      | 設定 Windows 事件記錄檔集合         | [設定 Windows 事件集合](/defender-for-identity/configure-windows-event-collection)        |
|2      | 設定網際網路 proxy 設定        | [為身分識別感應器設定 Microsoft Defender 的端點 proxy 和網際網路連線設定](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>步驟 4： 允許 Defender for Identity 識別其他電腦上的本機系統管理員

Microsoft Defender for Identity 橫向移動路徑偵測取決於識別特定電腦上的本機系統管理員的查詢。 使用用於身分識別服務帳戶的 Defender 來執行這些查詢。 

為了確保 Windows 的用戶端和伺服器能夠讓您的 Defender 身分識別帳戶執行 SAM，除了網路存取原則中所列的已設定帳戶之外，還必須對群組原則進行修改，以新增身分識別服務帳戶的 defender。 請務必將群組原則套用至 **除網域控制站以外** 的所有電腦。

如需如何進行此作業的指示，請參閱 [Configure Microsoft Defender For Identity to to remote a to a remote 呼叫 TO SAM](/defender-for-identity/install-step8-samr)。 

## <a name="next-steps"></a>後續步驟

步驟3之3： [試驗 Microsoft Defender 身分識別](eval-defender-identity-pilot.md)

回到概述以 [評估 Microsoft Defender 身分識別](eval-defender-identity-overview.md)

回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述