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
- m365-initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 922ffa3add41dba9896a406dc5705825d2d27aab
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413671"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="117fd-104">在 Microsoft 365 的安全性中心監控和查看報告</span><span class="sxs-lookup"><span data-stu-id="117fd-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="117fd-105">Microsoft 365 的安全性中心提供整個 Microsoft 365 環境中保護和安全性狀態的摘要。</span><span class="sxs-lookup"><span data-stu-id="117fd-105">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="117fd-106">[安全性中心] 包含 **報告** 區段，其可提供各種區域所涵蓋的卡片主機。</span><span class="sxs-lookup"><span data-stu-id="117fd-106">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="117fd-107">安全分析員和系統管理員可以追蹤名片做為日常作業的一部分。</span><span class="sxs-lookup"><span data-stu-id="117fd-107">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="117fd-108">在深入查看中，卡片提供詳細的報表，在某些情況下則為管理選項。</span><span class="sxs-lookup"><span data-stu-id="117fd-108">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="117fd-109">自訂視圖</span><span class="sxs-lookup"><span data-stu-id="117fd-109">Customize views</span></span>

<span data-ttu-id="117fd-110">依預設，紙牌會分為下列類別：</span><span class="sxs-lookup"><span data-stu-id="117fd-110">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="117fd-111">Identity [-使用者](monitor-and-report-identities.md)帳戶和認證</span><span class="sxs-lookup"><span data-stu-id="117fd-111">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="117fd-112">[資料](monitor-data.md) -電子郵件和檔內容</span><span class="sxs-lookup"><span data-stu-id="117fd-112">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="117fd-113">[裝置](monitor-devices.md) -電腦、行動電話及其他裝置</span><span class="sxs-lookup"><span data-stu-id="117fd-113">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="117fd-114">[App](monitor-apps.md) -程式與附加的線上服務</span><span class="sxs-lookup"><span data-stu-id="117fd-114">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="117fd-115">切換至 **Group by 主題**，以重新排列卡片並將其群組為下列主題：</span><span class="sxs-lookup"><span data-stu-id="117fd-115">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="117fd-116">**危險** 卡，可反白顯示可能有危險的實體（例如帳戶和裝置）。</span><span class="sxs-lookup"><span data-stu-id="117fd-116">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="117fd-117">這些卡片也會強調可能的風險來源，例如新的威脅活動和許可權的雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="117fd-117">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="117fd-118">**偵測趨勢** -重點是指出新威脅偵測、異常及違反原則的卡片</span><span class="sxs-lookup"><span data-stu-id="117fd-118">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="117fd-119">包含安全性控制措施（包括裝置上架狀態至管理服務）的設定**與狀況**卡片</span><span class="sxs-lookup"><span data-stu-id="117fd-119">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="117fd-120">**其他-其他** 所有未依其他主題分類的卡片</span><span class="sxs-lookup"><span data-stu-id="117fd-120">**Other** - all other cards not categorized under other topics</span></span>
