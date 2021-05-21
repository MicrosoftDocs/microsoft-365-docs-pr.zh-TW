---
title: 將非 Microsoft endpoint protection 切換為 Microsoft Defender for Endpoint
description: 將參數設為 Microsoft Defender for Endpoint。 如需概述，請閱讀本文。
keywords: 遷移，windows defender advanced endpoint protection，針對端點，edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/20/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2a2b78089486b432ebf9492de26396b2bb96f94d
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593498"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>將非 Microsoft endpoint protection 切換為 Microsoft Defender for Endpoint

如果您想要從您的非 Microsoft endpoint protection 切換至 [Microsoft defender for](microsoft-defender-endpoint.md) Endpoint (defender for endpoint) ，您就在正確的位置。 使用本文做為指南。

:::image type="content" source="images/nonms-mde-migration.png" alt-text="遷移至端點的 Defender 的概覽":::

當您將參數切換到 Endpoint 時，您會從以主動模式運作的非 Microsoft 方案開始，以被動模式設定 Defender for Endpoint，以 [在使用中的 Defender] 設定為 [使用的端點]，然後移除非 Microsoft 解決方案。

> [!TIP]
> - 如果您目前使用 McAfee 端點安全性 (McAfee) ，請參閱 [從 McAfee 遷移至 Defender For Endpoint](mcafee-to-microsoft-defender-migration.md)。
> - 如果您目前正在使用 symantec Endpoint Protection (symantec) ，請參閱[從 Symantec 遷移至 Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md)。

## <a name="the-migration-process"></a>遷移程式

將端點遷移至 Defender 的程式可以分為三個階段，如下表所述：

![遷移階段-準備、安裝、板載](images/phase-diagrams/migration-phases.png)

|階段 |描述 |
|--|--|
|[準備遷移](switch-to-microsoft-defender-prepare.md) |[在 **準備** 階段](switch-to-microsoft-defender-prepare.md)內： <p>1. 更新您組織的裝置。 <p>2. 取得適用于端點的 Defender。 <p>3. 規劃您的角色和許可權，並授與 Microsoft Defender 資訊安全中心的存取權。 <p>4. 設定您的裝置 proxy 和網際網路設定，以啟用組織裝置和 Defender for Endpoint 之間的通訊。 |
|[設定端點的 Defender](switch-to-microsoft-defender-setup.md) |在 [**安裝** 階段](switch-to-microsoft-defender-setup.md)內： <p>1. 啟用/重新安裝 Microsoft Defender 防毒軟體。 <p>2. 設定用於端點的 Defender。 <p>3. 將用於端點的 Defender 新增至現有解決方案的排除清單。 <p>4. 將現有的解決方案新增至 Microsoft Defender 防毒軟體的排除清單。 <p>5. 設定您的裝置群組、集合及組織單位。 <p>6. 設定反惡意程式碼原則和即時保護設定。|
|[Endpoint to Defender 的板載](switch-to-microsoft-defender-onboard.md) |在 [第 **板** 階段](switch-to-microsoft-defender-onboard.md)期間： <p>1. 將裝置板載 to Defender for Endpoint。 <p>2. 執行偵測測試。 <p>3. 確認 Microsoft Defender 防毒軟體以被動模式執行。 <p>4. 取得 Microsoft Defender 防毒軟體的更新。 <p>5. 卸載現有的 endpoint protection 解決方案。 <p>6. 確定 Endpoint for Endpoint 可以正確運作。 |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中包含的內容？

在此遷移指南中，我們著重于 [下一代保護](microsoft-defender-antivirus-in-windows-10.md) 和 [端點偵測和回應](overview-endpoint-detection-response.md) 功能，成為移至 Defender for endpoint 的起點。 不過，Defender for Endpoint 包含的內容遠遠超過防病毒和 Endpoint protection。 Defender for Endpoint 是一種整合的平臺，可提供預防性保護、破壞性偵測、自動調查和回應。 下表摘要的 Defender for Endpoint 中的功能和功能。 

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

**想要深入瞭解？請參閱 [適用于 Endpoint 的 Defender](microsoft-defender-endpoint.md)。**

## <a name="next-step"></a>後續步驟

- 繼續進行 [遷移的準備工作](switch-to-microsoft-defender-prepare.md)。
