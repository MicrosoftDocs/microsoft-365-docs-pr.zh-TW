---
title: 監視和查看報告-安全性中心
description: 說明 Microsoft 365 安全性中心如何深入瞭解保護及安全性狀態。
keywords: 安全性，惡意程式碼，Microsoft 365，M365，security center，monitor，report，status
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d52c401c4b2e995e5ec18895c158f77ce0fce746
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356880"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a>在 Microsoft 365 的安全性中心監控和查看報告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> 想要體驗 Microsoft 365 Defender？ 您可以 [在實驗室環境中進行評估](https://aka.ms/mtp-trial-lab) ，或 [在實際執行中執行您的試驗專案](https://aka.ms/m365d-pilotplaybook)。
>

Microsoft 365 的安全性中心提供整個 Microsoft 365 環境中保護和安全性狀態的摘要。

[安全性中心] 包含 **報告** 區段，其可提供各種區域所涵蓋的卡片主機。 安全分析員和系統管理員可以追蹤名片做為日常作業的一部分。 在深入查看中，卡片提供詳細的報表，在某些情況下則為管理選項。

## <a name="customize-views"></a>自訂視圖

依預設，紙牌會分為下列類別：
  
* Identity [-使用者](monitor-and-report-identities.md)帳戶和認證
* [資料](monitor-data.md) -電子郵件和檔內容
* [裝置](monitor-devices.md) -電腦、行動電話及其他裝置
* [App](monitor-apps.md) -程式與附加的線上服務

切換至 **Group by 主題**，以重新排列卡片並將其群組為下列主題：

* **危險** 卡，可反白顯示可能有危險的實體（例如帳戶和裝置）。 這些卡片也會強調可能的風險來源，例如新的威脅活動和許可權的雲端應用程式  
* **偵測趨勢** -重點是指出新威脅偵測、異常及違反原則的卡片
* 包含安全性控制措施（包括裝置上架狀態至管理服務）的設定 **與狀況** 卡片
* **其他-其他** 所有未依其他主題分類的卡片
