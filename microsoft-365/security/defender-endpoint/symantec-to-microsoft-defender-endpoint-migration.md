---
title: 從 Symantec 遷移至 Microsoft Defender for Endpoint
description: 深入瞭解如何將從 Symantec 切換至 Microsoft Defender 以供端點使用
keywords: 遷移，Microsoft Defender for Endpoint，edr
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
ms.date: 05/10/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 3e3a30ac4d03a40157fd7ec7f06e6e2a82c685a0
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327387"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>從 Symantec 遷移至 Microsoft Defender for Endpoint
如果您打算從 symantec Endpoint Protection (symantec) 切換至[microsoft defender for](microsoft-defender-endpoint.md) endpoint (microsoft defender for endpoint) ，您就是在正確的位置。 使用本文做為指南。

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
|[準備遷移](symantec-to-microsoft-defender-atp-prepare.md) |在 [**準備**] 階段中，您會取得 Microsoft Defender for Endpoint，規劃您的角色和許可權，並授與 Microsoft Defender 資訊安全中心的存取權。 您也可以設定裝置 proxy 和網際網路設定，以啟用組織裝置和 Microsoft Defender for 端點之間的通訊。 |
|[設定 Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-setup.md) |在 **設定** 階段，您可以為 Microsoft Defender 防毒軟體和 Symantec Endpoint Protection 設定設定和排除專案。 您也可以建立裝置群組、集合及組織單位。 最後，您可以設定反惡意程式碼原則和即時保護設定。|
|[在 Microsoft Defender for Endpoint 上的板載](symantec-to-microsoft-defender-atp-onboard.md) |在第 **板** 階段中，您會將裝置上架至 microsoft Defender for endpoint，並驗證這些裝置是否與 microsoft Defender for endpoint 進行通訊。 最後，您會卸載 Symantec，並確定透過 Microsoft Defender for Endpoint 來保護成為 active 模式。 |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中包含的內容？

在此遷移指南中，我們著重于 [下一代保護](microsoft-defender-antivirus-in-windows-10.md) 和 [端點偵測和回應](overview-endpoint-detection-response.md) 功能，成為移至 Microsoft Defender for endpoint 的起點。 不過，Microsoft Defender for Endpoint 包含的內容遠遠超過防病毒和 Endpoint protection。 適用於端點的 Microsoft Defender 是用於預防性保護、入侵後偵測、自動調查及回應的整合式平台。 下表摘要說明 Microsoft Defender for Endpoint 中的功能和功能。 

| 功能/功能 | 描述 |
|---|---|
| [威脅與漏洞管理](next-gen-threat-and-vuln-mgt.md) | 威脅 & 弱點管理功能可協助識別、評估和修正整個端點的弱點 (例如裝置) 。 |
| [攻擊面縮減](overview-attack-surface-reduction.md) | 攻擊面減少規則可協助保護貴組織的裝置和應用程式免受 cyberthreats 和攻擊。 |
| [新一代保護](microsoft-defender-antivirus-in-windows-10.md) | 下一代保護包括可協助封鎖威脅和惡意程式碼的 Microsoft Defender 防毒軟體。 |
| [端點偵測及回應](overview-endpoint-detection-response.md) | 端點偵測和回應功能偵測、調查和回應入侵嘗試和主動侵犯。  |
| [進階搜捕](advanced-hunting-overview.md) | 高級搜尋功能可讓您的安全性作業小組找到已知或潛在威脅的指標和實體。 |
| [行為封鎖和包含專案](behavioral-blocking-containment.md) | 行為封鎖和包容功能可協助您找出威脅，並根據其行為和程式樹（即使當威脅已開始執行時）加以阻止。 |
| [自動化調查和修正](automated-investigations.md) | 自動化調查和回應功能會檢查提醒並採取立即修正動作，以解決違規行為。 |
| [威脅搜尋服務](microsoft-threat-experts.md) (Microsoft 威脅專家)  | 「威脅搜尋服務」會為安全性運作小組提供專家級的監控和分析，並協助確保重要威脅不會丟失。 |

**想要深入瞭解？請參閱 [Microsoft Defender For Endpoint](microsoft-defender-endpoint.md)。**

## <a name="next-step"></a>下一步

- 繼續進行 [遷移的準備工作](symantec-to-microsoft-defender-atp-prepare.md)。
