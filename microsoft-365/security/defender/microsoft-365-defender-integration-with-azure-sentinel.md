---
title: Microsoft 365 Defender 與 Azure Sentinel 的整合
description: 使用 Azure Sentinel 做為 Microsoft 365 Defender 事件及事件的 SIEM。
keywords: 事件、警示、調查、分析、回應、關聯、攻擊、電腦、裝置、使用者、身分識別、身分識別、信箱、電子郵件、365、microsoft、m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b9a9a6381c93e2d252f75710adc206868c0a5546
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229908"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="afb4d-104">Microsoft 365 Defender 與 Azure Sentinel 的整合</span><span class="sxs-lookup"><span data-stu-id="afb4d-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="afb4d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="afb4d-105">**Applies to:**</span></span>
- <span data-ttu-id="afb4d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="afb4d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="afb4d-107">azure sentinel 的 Microsoft 365 Defender connector (preview) 將所有 Microsoft 365 Defender 事件及警示資訊傳送至 Azure Sentinel，並保持事件同步。</span><span class="sxs-lookup"><span data-stu-id="afb4d-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="afb4d-108">新增連接器之後，Microsoft 365 Defender 事件 &mdash; （包括所有相關聯的警示、實體及從 microsoft defender for Endpoint 接收的相關資訊）、microsoft defender for Identity、microsoft defender for Office 365 及 Microsoft Cloud App Security &mdash; 會以資料流程的)  (方式傳送至 azure sentinel，以執行與 azure sentinel 的會審和事件回應。</span><span class="sxs-lookup"><span data-stu-id="afb4d-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="afb4d-109">在 azure Sentinel 中，事件仍保持雙向同步處理 Microsoft 365 Defender，可讓您利用 Azure 入口網站中 Microsoft 365 security center 和 azure Sentinel 的優點，以進行事件調查和回應。</span><span class="sxs-lookup"><span data-stu-id="afb4d-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 security center and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="afb4d-110">請留意 Azure Sentinel 整合與 Microsoft 365 Defender (4 分鐘) 的此簡短概述。</span><span class="sxs-lookup"><span data-stu-id="afb4d-110">Watch this short overview of Azure Sentinel integration with Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


<span data-ttu-id="afb4d-111">以下說明運作方式。</span><span class="sxs-lookup"><span data-stu-id="afb4d-111">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Microsoft 365 Defender 和 Azure Sentinel 之間的事件資料流程程與共享":::

## <a name="next-steps"></a><span data-ttu-id="afb4d-113">後續步驟</span><span class="sxs-lookup"><span data-stu-id="afb4d-113">Next steps</span></span>

1. <span data-ttu-id="afb4d-114">深入瞭解[與 Azure Sentinel 的 Microsoft 365 Defender 整合](/azure/sentinel/microsoft-365-defender-sentinel-integration)。</span><span class="sxs-lookup"><span data-stu-id="afb4d-114">Get a deeper understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="afb4d-115">[連線從 Microsoft 365 Defender 到 Azure Sentinel 的資料](/azure/sentinel/connect-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="afb4d-115">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="afb4d-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="afb4d-116">See also</span></span>

- [<span data-ttu-id="afb4d-117">Microsoft 365 Defender 中的事件概覽</span><span class="sxs-lookup"><span data-stu-id="afb4d-117">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="afb4d-118">使用 Azure Sentinel 調查事件</span><span class="sxs-lookup"><span data-stu-id="afb4d-118">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
