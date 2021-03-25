---
title: 從 McAfee 遷移至 Microsoft Defender for Endpoint
description: 將 McAfee 切換至 Microsoft Defender for Endpoint。 如需概述，請閱讀本文。
keywords: 遷移、windows defender 高級威脅防護、atp、edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 53d9e68fa357d07cf70ab2282de9cee9fc0bd90d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185632"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>從 McAfee 遷移至 Microsoft Defender for Endpoint

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

如果您打算從 McAfee 端點安全性 (McAfee) 至 [Microsoft defender For endpoint](https://docs.microsoft.com/windows/security/threat-protection))  (microsoft defender for endpoint，您就是在正確的位置。 使用本文做為指南。


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="從 McAfee 遷移至 Defender for Endpoint 的概覽":::

當您將 McAfee 的參數切換至 Defender 時，您會從使用中的 McAfee 方案開始，以被動模式設定 Defender，以 [在被動模式中設定 Defender]，並在 [在使用中的電腦上安裝 Defender]，然後將 [Defender] 設定為使用模式並移除 McAfee。

## <a name="the-migration-process"></a>遷移程式

當您從 McAfee 切換至 Microsoft Defender for Endpoint 時，您遵循可以分為三個階段的程式： Prepare、Setup 及板載。 

![遷移階段-準備設定板載](images/phase-diagrams/migration-phases.png)

|階段 |描述 |
|--|--|
|[準備遷移](mcafee-to-microsoft-defender-prepare.md) |在 [ [**準備**](mcafee-to-microsoft-defender-prepare.md) ] 階段中，您會更新組織的裝置、取得 microsoft Defender 的端點、規劃您的角色和許可權，以及授與 Microsoft Defender Security Center 的存取權。 您也可以設定裝置 proxy 和網際網路設定，以啟用組織裝置和 Microsoft Defender for 端點之間的通訊。 |
|[設定 Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-setup.md) |在 [**安裝**](mcafee-to-microsoft-defender-setup.md) 階段中，您會啟用 Microsoft Defender 防病毒，並確定其為被動模式，並為 Microsoft Defender 防病毒、microsoft Defender for Endpoint 和 McAfee 設定 & 排除的設定。 您也可以建立裝置群組、集合及組織單位。 最後，您可以設定反惡意程式碼原則和即時保護設定。|
|[在 Microsoft Defender for Endpoint 上的板載](mcafee-to-microsoft-defender-onboard.md) |在第 [**板**](mcafee-to-microsoft-defender-onboard.md) 階段中，您會將裝置上架至 microsoft Defender for endpoint，並驗證這些裝置是否與 microsoft Defender for endpoint 進行通訊。 最後，您會卸載 McAfee，並確定透過 Microsoft Defender 防毒軟體 & Microsoft Defender for Endpoint 中的保護處於 active 模式。 |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中包含的內容？

在此遷移指南中，我們著重于 [下一代保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 和 [端點偵測和回應](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) 功能，成為移至 Microsoft Defender for endpoint 的起點。 不過，Microsoft Defender for Endpoint 包含的內容遠遠超過防病毒和 Endpoint protection。 適用於端點的 Microsoft Defender 是用於預防性保護、入侵後偵測、自動調查及回應的整合式平台。 下表摘要說明 Microsoft Defender for Endpoint 中的功能和功能。 

| 功能/功能 | 描述 |
|---|---|
| [威脅 & 弱點管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | 威脅 & 弱點管理功能可協助識別、評估和修正整個 (端點的弱點，如裝置) 。 |
| [受攻擊面縮小](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | 攻擊面減少規則可協助保護貴組織的裝置和應用程式免受 cyberthreats 和攻擊。 |
| [下一代保護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | 下一代保護包括 Microsoft Defender 防毒程式，可協助封鎖威脅和惡意程式碼。 |
| [端點偵測及回應](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | 端點偵測和回應功能偵測、調查和回應入侵嘗試和主動侵犯。  |
| [進階搜捕](advanced-hunting-overview.md) | 高級搜尋功能可讓您的安全性作業小組找到已知或潛在威脅的指標和實體。 |
| [行為封鎖和包容](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | 行為封鎖和包容功能可協助您找出威脅，並根據其行為和程式樹（即使當威脅已開始執行時）加以阻止。 |
| [自動化調查與補救措施](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | 自動化調查和回應功能會檢查提醒並採取立即修正動作，以解決違規行為。 |
| [威脅搜尋服務](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft 威脅專家)  | 「威脅搜尋服務」會為安全性運作小組提供專家級的監控和分析，並協助確保重要威脅不會丟失。 |

**想要深入瞭解？請參閱 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection)。**

## <a name="next-step"></a>下一步

- 繼續進行 [遷移的準備工作](mcafee-to-microsoft-defender-prepare.md)。
