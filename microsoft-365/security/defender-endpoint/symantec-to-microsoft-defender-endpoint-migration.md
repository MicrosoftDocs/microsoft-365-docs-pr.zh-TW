---
title: 從 Symantec 遷移至 Microsoft Defender for Endpoint
description: 深入瞭解如何將從 Symantec 切換至 Microsoft Defender 以供端點使用
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
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 6517359c805bb449d075e401283a79a791461630
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218775"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>從 Symantec 遷移至 Microsoft Defender for Endpoint
如果您打算從 Symantec Endpoint Protection (Symantec) 切換至 [Microsoft defender For endpoint](https://docs.microsoft.com/windows/security/threat-protection))  (microsoft defender for endpoint，您就是在正確的位置。 使用本文做為指南。

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="從 Symantec 遷移至 Defender for Endpoint 的概覽":::

當您將 Symantec 從 Symantec 移至 Defender for Endpoint 時，您會以主動模式為您的 Symantec 方案，在被動模式中設定 Defender for Endpoint，並將其設定為使用的端點的 defender，然後再將其設定為使用中模式，並移除 Symantec。

## <a name="the-migration-process"></a>遷移程式

當您從 Symantec 切換至 Microsoft Defender for Endpoint 時，您遵循可以分為三個階段的程式，如下表所述：

![遷移階段-準備、安裝、板載](images/phase-diagrams/migration-phases.png)

|階段 |描述 |
|--|--|
|[準備遷移](symantec-to-microsoft-defender-atp-prepare.md) |在 [ **準備** ] 階段中，您可以取得 microsoft Defender for Endpoint、規劃您的角色和許可權，以及授與 Microsoft Defender Security Center 的存取權。 您也可以設定裝置 proxy 和網際網路設定，以啟用組織裝置和 Microsoft Defender for 端點之間的通訊。 |
|[設定 Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-setup.md) |在 **安裝** 階段中，您可以設定 Microsoft Defender 防病毒、microsoft Defender for Endpoint 和 Symantec endpoint Protection 的設定和排除專案。 您也可以建立裝置群組、集合及組織單位。 最後，您可以設定反惡意程式碼原則和即時保護設定。|
|[在 Microsoft Defender for Endpoint 上的板載](symantec-to-microsoft-defender-atp-onboard.md) |在第 **板** 階段中，您會將裝置上架至 microsoft Defender for endpoint，並驗證這些裝置是否與 microsoft Defender for endpoint 進行通訊。 最後，您會卸載 Symantec，並確定透過 Microsoft Defender for Endpoint 來保護成為 active 模式。 |

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

- 繼續進行 [遷移的準備工作](symantec-to-microsoft-defender-atp-prepare.md)。
