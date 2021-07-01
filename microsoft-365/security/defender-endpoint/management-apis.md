---
title: 管理和 API 概觀
ms.reviewer: ''
description: 深入瞭解 Microsoft Defender for Endpoint 中的管理工具和 API 類別
keywords: 上架，api，siem，rbac，access，portal，integration，調查，回應，實體，實體，使用者內容，應用程式內容，資料流程
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 471db75102eabd4d7fce14ec42d0a47562007aae
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229980"
---
# <a name="overview-of-management-and-apis"></a>管理和 API 概觀

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


的 Defender for Endpoint 支援各種選項，以確保客戶可以輕鬆採用此平臺。

確認客戶環境和結構可以改變，但建立的 Defender 是以彈性和細微的方式控制，以滿足不同客戶的需求。

## <a name="endpoint-onboarding-and-portal-access"></a>端點上架和入口網站存取

裝置上架已完全整合至用戶端裝置和 Azure Defender for server 裝置的 Microsoft 端點管理員和 Microsoft Intune，可提供設定、部署和監控的完整端對端體驗。 此外，Microsoft Defender for Endpoint 會支援用於裝置管理的群組原則及其他協力廠商工具。

Defender for Endpoint 提供精細的控制，可讓具有入口網站存取權的使用者透過角色型存取控制 (RBAC) 的彈性來查看並執行。 RBAC 模型支援所有的安全性小組結構類型：

- 全域分散式組織和安全小組
- 分級模型安全性運作小組
- 以單一集中式全域安全性運作小組進行完全隔離的分部

## <a name="available-apis"></a>可用 APIs
Microsoft Defender for Endpoint 方案是以整合就緒平臺為基礎。

「！的 Defender」會透過一組程式設計 APIs 公開其資料和動作。 這些 APIs 可讓您以使用 Defender for Endpoint 功能來自動化工作流程及創新。

![Microsoft Defender for Endpoint 中可用 API 和整合的影像](images/mdatp-apis.png)

Endpoint APIs 的 Defender 可以分為三種：

- Microsoft Defender for Endpoint APIs
- 原始資料串流 API
- SIEM 整合

## <a name="microsoft-defender-for-endpoint-apis"></a>Microsoft Defender for Endpoint APIs

Defender for Endpoint 提供分層 API 模型，以結構化、清晰且便於使用的模型公開資料和功能，透過標準 Azure AD 型驗證和授權模型公開，允許使用者或 SaaS 應用程式的內容存取。 API 模型設計為以一致的形式公開實體和功能。

觀賞這段影片，以快速瞭解如何使用 Defender 的 Endpoint APIs。
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

**調查 API** 公開大量用於端點公開計算或「已分析」實體的 Defender (例如，裝置、使用者、檔案) 和分散的事件 (例如，程式建立及檔案建立) ，這通常會說明與實體相關的行為，並可透過調查介面存取資料，以允許以查詢為基礎的資料存取。 如需詳細資訊，請參閱 [支援的 APIs](exposed-apis-list.md)。

**回應 API** 公開在服務和裝置上採取動作的能力，讓客戶能夠攝取指示器、管理設定、警示狀態，以及在裝置上採取回應動作，例如隔離裝置與網路、隔離檔案等等。

## <a name="raw-data-streaming-api"></a>原始資料串流 API

使用 Defender for Endpoint raw data stream API，可讓客戶在單一資料流程中發生即時事件及警示，以提供低延遲、高輸送量傳遞機制。

將 Endpoint 事件資訊的 Defender 事件資訊直接推入 Azure 存放區，以進行長期資料保留，或透過視覺化服務或其他資料處理引擎使用 Azure 事件中心以取得消耗。

如需詳細資訊，請參閱 [Raw data 流式 API](raw-data-export.md)。

新的 Microsoft 365 Defender 流式 API 除了裝置事件以外，還包括電子郵件和警示事件。
如需詳細資訊，請參閱[Microsoft 365 Defender 流式 API](../defender/streaming-api.md)。

## <a name="siem-api"></a>SIEM API

當您啟用安全性資訊和事件管理 (SIEM) 整合時，可讓您使用 SIEM 解決方案或直接連線至偵測到的 REST API，從 Microsoft Defender 資訊安全中心提取偵測。 這會以預先填入的值來啟動 SIEM connector access 詳細資料區段，且應用程式會在您的 Azure Active Directory (Azure AD) 租使用者下建立。 如需詳細資訊，請參閱 [SIEM integration](enable-siem-integration.md)。

## <a name="related-topics"></a>相關主題

- [存取適用於端點的 Microsoft Defender API](apis-intro.md)
- [支援的 APIs](exposed-apis-list.md)
- [技術合作夥伴機會](partner-integration.md)